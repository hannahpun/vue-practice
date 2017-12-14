# sss-nuxt

> Nuxt.js project

## Build Setup

``` bash
# install dependencies
$ npm install # Or yarn install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, checkout the [Nuxt.js docs](https://github.com/nuxt/nuxt.js).



HTML meta 那些屬性寫在 nuxt.config.js
## [nuxt.config](https://zh.nuxtjs.org/guide/configuration)
可以定義 router, 
```
//css
module.exports = {
  css: [
    // 加载一个 node.js 模块
    'hover.css/css/hover-min.css',
    // 同样加载一个 node.js 模块，不过我们定义所需的预处理器
    { src: 'bulma', lang: 'sass' },
    // 项目中的 CSS 文件
    '~assets/css/main.css',
    // 项目中的 Sass 文件
    { src: '~assets/css/main.scss', lang: 'scss' } // 指定 scss 而非 sass
  ]
}
```


# Directory

```
-| assets/ 資源目錄
----| images/
-------| index.vue
----| sass/
-| pages/
----| index.vue
-| static/ 靜態目錄
-| layouts/ 
----| default.vue
----| error.vue 放 404 500 等錯誤頁面
-| store/ 
----| index.js
```
## store
```
import Vue from 'vue'
import Vuex from 'vuex'

Vue.use(Vuex)

const store = () => new Vuex.Store({

  state: {
    counter: 0
  },
  mutations: {
    increment (state) {
      state.counter++
    }
  }
})

export default store
```

## layouts
```
// default.vue layout
<template>
  <nuxt/>
</template>
```
可以有客製化 layout 例如 layouts/blog.vue
```
<template>
  <div>
    <div>这里是博客导航</div>
    <nuxt/>
  </div>
</template>
```
在 pages/posts.vue 里， 可以指定页面组件使用 blog 布局。
```
<script>
export default {
  layout: 'blog'
}
</script>
```

## assets
```
  <img src="~assets/image.png">
```

## static
不需要通过 Webpack 处理的静态资源文件，可以放置在 static 目录中 像 robots.txt 或 sitemap.xml 
```
<!-- 引用 static 目录下的图片 -->
<img src="/my-image.png"/>
```

