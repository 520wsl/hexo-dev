---
title: VueJS安装
categories:
- 工具
- 安装教程
tags:
- VueJS
---

## 安装
- [官网](https://cn.vuejs.org/)
- [开发手册](https://cn.vuejs.org/v2/guide/installation.html)
- [点击下载](http://vuejs.org/js/vue.js)
- 直接下载并用 `<script>` 标签引入，Vue 会被注册为一个全局变量。重要提示：在开发时请用开发版本，遇到常见错误它会给出友好的警告。

## CDN
- 推荐：[unpkg](https://unpkg.com/vue/dist/vue.js), 会保持和 npm 发布的最新的版本一致。可以在 unpkg.com/vue/ 浏览 npm 包资源。
- 也可以从 [jsdelivr](https://cdn.jsdelivr.net/vue/2.1.3/vue.js) 或 [cdnjs](https://cdnjs.cloudflare.com/ajax/libs/vue/2.1.3/vue.js) 获取，不过这两个服务版本更新可能略滞后。

### NPM
-在用 `Vue.js `构建大型应用时推荐使用 `NPM` 安装， NPM 能很好地和诸如 `Webpack` 或 `Browserify` 模块打包器配合使用。 Vue.js 也提供配套工具来开发[单文件组件](https://cn.vuejs.org/v2/guide/single-file-components.html)。

```javascript
# 最新稳定版
$ npm install vue
```

## 命令行工具
- Vue.js提供[官方命令行工具](https://github.com/vuejs/vue-cli),可用于快速搭建大型单页应用。该工具提供开箱即用的构建工具配置，带来现代化的前端开发流程。只需几分钟即可创建并启动一个带热重载、保存时静态检查以及可用于生产环境的构建配置的项目：

```javascript
# 全局安装 vue-cli
$ npm install --global vue-cli
# 创建一个基于 webpack 模板的新项目
$ vue init webpack my-project
# 安装依赖，走你
$ cd my-project
$ npm install
$ npm run dev
```