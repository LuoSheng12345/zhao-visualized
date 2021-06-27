<template>
  <div>
    <Nuxt />
    <div class="fixed z-25 bottom-0 left-0 flex flex-col">
      <nuxt-link to="/" class="navi">看图</nuxt-link>
      <nuxt-link to="/about" class="navi">关于</nuxt-link>

    </div>
  </div>
</template>

<style scoped>
.navi{
  @apply bg-gray-200 p-3 m-2 shadow-lg rounded-xl text-2xl font-semibold
}
.nuxt-link-exact-active{
  @apply bg-gray-800 text-white
}

</style>
