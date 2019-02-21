# Vue 兼容 IE9 全功能正常使用的全面解决方案

Vue 官方对于 ie 浏览器版本兼容情况的描述是 ie9+，即是 ie9 及更高的版本。经过测试，Vue 的核心框架 vuejs 本身，以及生态的官方核心插件（VueRouter、Vuex等）均可以在 ie9 上正常使用。

Vue 的作者尤雨溪对于 Vue 的学习建议 中有提及为了将项目更好的生态化/工程化，要尽可能学习及使用新的 ECMAScript 规范。目前 ES6/ES2015 是可用度和稳定度较高的规范，文档齐全，国内还有 阮一峰 《ECMAScript 6 入门》 做了大量的文档翻译，开发环境可谓完善。然而版本较旧的浏览器并不支持 es6 规范，尤其是 ie 浏览器，即使是最高的 ie11 版本，对于 es6 规范也支持得并不全。如此则需要对所有原生不支持 ES6 特性的浏览器做兼容性处理。

本文将针对使用 Vue 生态开发完成的网站，以 ie9 版本为基础兼容目标，实现全功能正常使用的全面兼容解决方案。

ES6兼容


在 ie9 的环境上，es6 的部分新对象、表达式，并不支持，解决方案是使用 babel-polyfill 组件，它可以将 es6 的代码翻译成低版本浏览器可以识别的 es5 代码

```
npm install babel-polyfill -s
```


安装完成后，在项目的主入口文件 main.js 的首行就可以直接引用
```
import "babel-polyfill";
```

在项目使用 vue-cli 生成的代码中，根目录有一个 .babelrc 文件，这是项目使用 babel 的配置文件。在默认生成的模板内容中，增加 "useBuiltIns": "entry" 的设置内容，这是一个指定哪些内容需要被 polyfill(兼容) 的设置

useBuiltIns 有三个设置选项

* false - 不做任何操作

* entry - 根据浏览器版本的支持，将 polyfill 需求拆分引入，仅引入有浏览器不支持的polyfill

* usage - 检测代码中 ES6/7/8 等的使用情况，仅仅加载代码中用到的 polyfill


```
{
  "presets": [
    ["env", {
      "modules": false,
      "targets": {
        "browsers": ["> 1%", "last 2 versions", "not ie <= 8"]
      },
      "useBuiltIns": "entry"
    }],
    "stage-2"
  ]
}
```


