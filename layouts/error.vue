<template>
    <div class="text-center"> 
        <h1 class="text-6xl font-extrabold">{{error.statusCode}}</h1>
        <h1 class="text-2xl">出事儿啦！</h1>
        <h2 class="text-lg mb-10">为啥出事儿: {{error.message}}</h2>

        <nuxt-link to="/" class="bg-green-200 p-4 font-bold text-4xl rounded-xl shadow-xl">按这儿回首页</nuxt-link>
    </div>
</template>

<script>
export default {
    props:['error']
}
</script>