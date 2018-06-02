---
sidebar: auto
---

# 伊甸园

VueEden 是一个美观的后台管理系统/集成方案，简称 Eden（伊甸园）。Eden 在后台集成解决方案引入没有过于复杂，只包含了最基础和最常用的功能。也易移除模块，当做基础样式模板进行开发。这使得理解伊甸园代码并修改和大刀阔斧的魔改都变得非常友好。

## 特点/技术栈

- 舒适配色与布局
- 权限控制
- 动态路由
- MOCK 数据
- 登录登出
- 界面锁定
- 伸缩侧边栏
- 自适应布局
- 页面标签控制
- 国际化多语言
- 个人中心

还有更多...

此项目主要使用了 `vue`、`vuex`、`vue-router`、`element-ui`、`stylus` 进行开发。并使用 `ESLint` 进行代码检查工具并配合 `prettier` 进行格式化，无需担心代码风格。而插件除了 echarts 外，没有引入另外的大型库。所以例如富文本编辑器、excel处理等等功能需自行添加。

## 开发环境

nodejs 版本必须大于 8 以上。使用了 `vue-cli3` 脚手架进行基础搭建，这使得项目没有直接暴露 Webpack 配置文件而直接通过 vue.config.js 里配置进行更改。具体配置信息可到 [vue-cli 官方文档](https://github.com/vuejs/vue-cli/blob/dev/docs/README.md) 查看。

```js
module.exports = {
  baseUrl: process.env.baseUrl,
  outputDir: process.env.outputDir,
  lintOnSave: true,
  chainWebpack: config => {
    config.resolve.alias
      .set('vue$', 'vue/dist/vue.esm.js')
      .set('@', resolve('src'))
      .set('assets', resolve('src/assets'))
      .set('components', resolve('src/components'))
      .set('api', resolve('src/api'))
      .set('utils', resolve('src/utils'))
      .set('store', resolve('src/store'))
      .set('router', resolve('src/router'))

    config.resolve.extensions
      .add('.js')
      .add('.vue')
      .add('.styl')
  }
}
```

最主要的配置如上，非常简单。目前通过 `.env.[mode]` 方式设置环境变量，你可以在目录看到 `.env.development` 与 `.env.production` 这两个文件。


## 样式

全局样式目录 `src/assets/styl/index.styl`，变量值可存放在同级目录的 `variables.styl`。而 `element-ui` 处理了主题色覆盖，覆盖样式文件存放在 `src/theme` 目录下。