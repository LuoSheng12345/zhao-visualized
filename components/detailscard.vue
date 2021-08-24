<template>
    <div>
        <div v-if="isNode">
            <!-- node -->
            <h1>{{nodeHeading}}</h1>
            <p></p>

        </div>
        <div v-if="isEdge">

        </div>
    </div>
</template>
<script>
export default {
    props:['eve'],
    computed:{
        eData(){
            return this.eve.data
        },
        isNode(){
            return this.eve.dataType=='node'
        },
        isEdge(){
            return this.eve.dataType=='edge'
        },
        nodeHeading(){
            return this.eData.name
        }
    }
}
</script>