# vuepress2-plugin-demo-block
## 介绍
基于Vuepress2的插件，它可以帮助你在编写组件库文档的时候增加示例代码和预览。

## 安装

### 安装 VuePress

请参考 Vuepress2 官方文档，[点此查看](https://v2.vuepress.vuejs.org/zh/guide/getting-started.html)

### 安装插件

使用 `yarn` 安装 `vuepress2-plugin-demo-block` 插件

```bash
yarn add vuepress2-plugin-demo-block -D
```

或者使用 `npm` 安装它：

```bash
npm i vuepress2-plugin-demo-block --save-dev
```

如果你的网络环境不佳，推荐使用 [cnpm](https://github.com/cnpm/cnpm)。

### 配置插件

打开 .vuepress/config.js 文件，然后在合适的位置引用插件：

- **配置扫描路径** `componentsDir`

```js
module.exports = {
  ...
  plugins: [[
    'vuepress2-plugin-demo-block',
    {
      componentsDir: path.resolve(__dirname, './../examples')
    }
  ]],
  ...
}
```
::: warning 注意
componentsDir 必传，为动态注册组件的基础路径，目录结构可参考 element-plus
:::

## 引入组件
可在`docs/.vuepress/clientAppEnhance.js`引入组件，需要注意的是，第三方库可能还需要依赖，例如`ant-design-vue`还需要`less`和`less-loader`，请自行安装

```js
import { defineClientAppEnhance } from "@vuepress/client";

// import Antd from "ant-design-vue";
// import "ant-design-vue/dist/antd.css";

// import ElementPlus from "element-plus";
// import "element-plus/dist/index.css";

// import ArcoVue from '@arco-design/web-vue';
// import ArcoVueIcon from '@arco-design/web-vue/es/icon';
// import '@arco-design/web-vue/dist/arco.css';

export default defineClientAppEnhance(({ app, router, siteData }) => {
  // app.use(Antd)
  // app.use(ElementPlus)
  // app.use(ArcoVue);
  // app.use(ArcoVueIcon);
});
```
