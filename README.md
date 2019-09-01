# mt-app

来源于慕课网《全栈开发美团网》，仅供个人学习之用。

> My geometric Nuxt.js project

## 创建项目

```
? Project name mt-app
? Project description My geometric Nuxt.js project
? Author name LiChen
? Choose the package manager Yarn
? Choose UI framework Element
? Choose custom server framework Koa
? Choose Nuxt.js modules Axios
? Choose linting tools ESLint
? Choose test framework None
? Choose rendering mode Universal (SSR)
```

## Build Setup

``` bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

For detailed explanation on how things work, checkout [Nuxt.js docs](https://nuxtjs.org).

## 安装依赖

1. 为了使项目中能够正常使用es6语法，需要做以下操作：

   1. 在项目根目录下新建一个.babelrc配置文件加入以下内容：

      ```
      {
          "presets": ["env"]
      }
      ```

   2. 那么就需要安装`yarn add babel-preset-env --dev`

   3. 安装`yarn add babel-cli --dev `

   4. 将package.json中启动脚步文件中加入使用babel如下：

      ```
      "scripts": {
          "dev": "cross-env NODE_ENV=development nodemon server/index.js --watch server --exec babel-node",
          "build": "nuxt build",
          "start": "cross-env NODE_ENV=production node server/index.js --exec babel-node",
          ...
      ```

   此时如果你已经将index.js中的语法转换成es6如使用import替代require，等待项目自动重新编译，成功～

2. 安装webpack

   ```
   yarn add --dev webpack
   yarn add --dev webpack-cli
   ```

> Tips：如果安装依赖过程中有warn，那么需要解决这些warn（根据提示）

3. 为了能够使用scss，需要安装以下依赖：

   ```
   yarn add sass-loader node-sass
   ```


## 需求分析

- 模板设计：复用代码
- 组件设计：抽象组件
- 数据结构设计：合理结合模板和数据 
- 接口设计：为数据结构设计服务

## 模板设计

首先考虑下页面该如何布局，提取出公共的部分作为组件，然后再细化。

### 首页

#### 整体布局

![](https://raw.githubusercontent.com/xiaxinandye/GitImage/master/mt-app/20190828143541.png)

来思考下首页的header怎么设计，应该分为哪些组件，header分为上下两个结构topBar、searchBar

#### 城市定位服务组件

#### 用户组件

##### nav

#### searchBar

搜索框，有3个状态：

1. 搜索框失去焦点时：只是显示默认文本
2. 搜索框聚焦时，并且没有输入文本时：下拉框显示热门搜索列表
3. 搜索框聚焦时，并且输入文本时：下拉框显示相关搜索列表



