**# mp-vue-scoped**



### 插件意义

由于目前taro for vue不支持vue的css scoped，所以通过webpecak插件的形式实现类似的效果



### 快速开始

```shell
# npm
npm install mp-vue-scoped

# pnpm 
pnpm add mp-vue-scoped
```

### taro配置

```js
mini: {
  ...
  webpackChain(chain) {
    chain.module
      .rule('vueFiles')
      .test(/\.vue$/)
      .include.add(resolve(__dirname, '../src')) // 配置要转换的vue文件的范围
      .end()
      .use('mp-vue-scoped')
      .loader('mp-vue-scoped');
  },
    ...
},
```

然后就可以愉快的玩耍了



### 迭代方向

- [ ] 阻止父组件对子组件的样式穿透
- [ ] 实现vue的`:deep()`深度选择器功能

> 目前这个插件仅仅是处于能用的阶段，并没有完整的实现原生vue的scoped全部功能。欢迎加入共建！