<template>
  <div>
    <div>
      <maingraph @charClicked="gotEvent"/>
    </div>
    <div class="z-50 right-0 top-0 w-64 h-screen fixed bg-white shadow-xl" v-if="clicked">
      <button @click="clicked=null" class="absolute right-0 text-lg bg-red-200 rounded shadow p-2 m-1">X点这儿关上</button>
      <div v-if="clicked.type=='node'" class="mt-20 pl-3">
        <h1 class="text-2xl font-semibold">{{clicked.data.name}}</h1>
        <h2 class="text-lg font-medium" v-if="clicked.data.category!=0">{{clicked.data.isAlive?'还没死':'死了'}}</h2>
        <p v-if="clicked.data.category!=0">{{clicked.data.info.desc}}</p>
      </div>
      <div v-if="clicked.type=='edge'" class="mt-20 pl-3">
        <h1 class="text-lg"><b>{{clicked.target.name}}</b> 是 <b>{{clicked.source.name}}</b> 的 <b>{{clicked.relationship}}</b></h1>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data:()=>({
    mode:0,
    clicked:null,
  }),
  methods:{
    gotEvent(e){
      this.clicked=e
    }
  }

}
</script>