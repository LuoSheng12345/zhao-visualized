<template>
    <div class="flex flex-col max-w-2xl m-auto">
        <h1>关于</h1>
        <div>
            <p>这个项目是基于俺Fork的编程随想的太子党关系网络的视觉化。去这儿看俺Fork的Repo: <a href="https://github.com/LuoSheng12345/zhao" target="_blank">github.com/LuoSheng12345/zhao</a></p>
            <p>这个项目可以说是俺给党建党百年的贺礼</p>
            <p>如果你发现这个网站上的数据有问题，比如错误、缺失、过时，请参考<a href="https://github.com/LuoSheng12345/zhao/blob/master/README.md" target="_blank">这篇文章</a>对太子党关系网络这个项目做出贡献</p>
            <p>如果你想进一步提升这个网站本身的体验，可以<a href="https://github.com/LuoSheng12345/zhao-visualized">从这里</a>查看本网站的项目</p>
        </div>
        <h1>这网站咋用</h1>
        <div>
            <h2 class="text-xl font-semibold">手机上用不太了！上电脑上用去！</h2>
            <p>
                上面可以选展示哪些个家族，鼠标移上去的话还可以只显示某个家族。
            </p>
            <p>
                每个点都可以点击，点击之后右边会出个简单的介绍。每个点之间的连线也可以点击（要点的比较准才有用，如果点不中的话建议用滚轮放大再点）。
            </p>
            <p>
                点的大小代表一个人有多少连线。连线越多点越大。
            </p>
        </div>
        <h1>信息有错误，缺失，过时？</h1>
        <div>
            <h2>来填写下面这个表单，为此项目做贡献</h2>
            <iframe src="https://docs.google.com/forms/d/e/1FAIpQLSe5ufFmkNkY1RJf4oETmElwxHnVOqs_dor9Y44MJpZ7vD0uaw/viewform?embedded=true" class="w-full" height="630" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
            <p>看不见这个表单的话也可以<a href="https://forms.gle/8v69z19Vroxy8UXP9">来这里</a>填写这份表单</p>
        </div>
    </div>
</template>

<style scoped>
h1{
    @apply text-2xl font-bold
}
p{
    @apply my-2
}
a{
    @apply text-blue-600 underline
}
</style>