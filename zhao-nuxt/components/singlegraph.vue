<template>
  <div>
    <div ref="chart1" class="w-screen h-screen"></div>
  </div>
</template>

<script>
var echarts = require('echarts');

export default {
  async mounted(){
    let myChart=echarts.init(this.$refs.chart1)
    myChart.showLoading()
    
    try {
      let zhaoP=await this.$axios.get('/zhao.json')
      let graph=zhaoP.data

      graph.nodes.forEach(node => {
        node.symbolSize=node.connections*3+5
        if(node.category!=0){
          let cat=graph.categories.filter(x=>x.cid==node.category)[0]
          if(cat){
            node.value=cat.name+' 家族'
          }
        }
      });

      graph.links.forEach(link=>{
        link.value=link.relationship
      })


      let option = {
          title: {
              text: '太子党关系网络',
              top: 'bottom',
              left: 'right'
          },
          tooltip: {},
          legend: [{
              selectedMode: 'single',
              data: graph.categories.map(function (a) {
                  return a.name;
              })
          }],
          series: [
              {
                  // name: 'Les Miserables',
                  type: 'graph',
                  layout: 'force',
                  draggable:true,
                  data: graph.nodes,
                  links: graph.links,
                  categories: graph.categories,
                  roam: true,
                  label: {
                      position: 'right'
                  },
                  lineStyle: {
                    color: 'source',
                  },
                  force: {
                      repulsion: 100
                  },
                  emphasis: {
                    focus: 'adjacency',
                    lineStyle: {
                        width: 5
                    }
                  }
              }
          ]
      };

      myChart.setOption(option)
      myChart.hideLoading()

      myChart.on('click',this.clickEvent)


    } catch (error) {
      alert(`出问题了，原因是 ${error}. 看不懂的话刷新一下试试`)
      console.error(error)
      return
    }
    
  },
    methods:{
    clickEvent(e){
      if(e.dataType=='edge'){
        let sourceId=e.data.source
        let targetId=e.data.target
        let sour=this.zhao.nodes.filter(x=>x.id==sourceId)[0]
        let tar=this.zhao.nodes.filter(x=>x.id==targetId)[0]
        let relation=e.data.relationship

        this.$emit('charClicked',{
          type:'edge',
          source:sour,
          target:tar,
          relationship:relation
        })
      }else if(e.dataType=='node'){
        this.$emit('charClicked',{
          type:'node',
          data:e.data
        })
      }
    }
  }

}
</script>