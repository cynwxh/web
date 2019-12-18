


# jokes环境搭建

框架: react react-dom react-router-dom

构建: webpack+webpack-cli+webpack-dev-server + babel +less

## 目录
dist 打包后文件所在目录

static 公共资源

webpack.dev.config.js 开发配置

webpack.pro.config.js 生产配置

.babelrc

postcss.config.js

src (/api,/pages,/components,/main.jsx,/router.jsx)

package.json

readme.md



 ```
mkdir jokes


创建package.json
npm init
 ```

入口文件index.js

Git:有

keywords:jokes

## webpack配置

postcss.config.js配置

webpack,
babel-loader, @babel/core, @babel/preset-env, @babel/preset-react

css-loader, style-loader, postcss-loader, autoprefixer, 
less, less-loader,

url-loader, image-webpack-loader

file-loader

------
.babelrc
```
{
preset:["@babel/preset-env",]
}
```
---
### 开发环境配置
```js
const webpack =require('webpack')
const path =require('path')
const HtmlWebpackPlugin=require('html-webpack-plugin')
module.exports={
    "mode":"development",
    "entry":"./src/main",
    output:{
        filename:"[name].js"
    },
    resolve:{
        extensions: [".js", ".json",".jsx"],
        alias: {
            '@': path.resolve(__dirname, './src')
        }
    },
    module:{
        rules:[
            //.css 文件  style-loader css-loader postcss-loader
            {
                test:/\.css$/,
                loader:"style-loader!css-loader!postcss-loader"
            },
            //.less文件  less less-loader postcss-loader
            {
                test:/\.less$/,
                loader:"style-loader!css-loader!postcss-loader!less-loader"
            },
            //.jsx文件 babel-core babel-loader babel-preset-env babel-preset-react
            {
                test:/\.jsx?$/,
                exclude:/node_modules/,
                loader:"babel-loader"
            },
            {
                test: /\.(png|jpg|gif|jpeg|bmp)$/,
                loader: 'url-loader?limit=10000'
            },
            {
                test:/\.(woff|woff2|svg|ttf|eot)($|\?)/i,
                loader:'url-loader?limit=500000'
            }
        ]
    },
    plugins:[
        new webpack.ProvidePlugin({
            "React": "react",
            "ReactDOM":'react-dom'
        }),
        new webpack.BannerPlugin("Copyright cyn inc."),
        new HtmlWebpackPlugin({
            template:"static/index.html",
            hash:true
        }),
        new webpack.HotModuleReplacementPlugin()
    ]
}
```



生产环境配置

```js
const webpack =require('webpack')
const path =require('path')
const HtmlWebpackPlugin=require('html-webpack-plugin')
const MiniCssExtractPlugin = require('mini-css-extract-plugin')
var OptimizeCSSPlugin = require('optimize-css-assets-webpack-plugin')
module.exports={
    "mode":"production",
    "entry":"./src/main.jsx",
    output:{
        filename:"js/[name].js"
    },
    resolve:{
        extensions: [".js", ".json",".jsx"],
        alias: {
            '@': path.resolve(__dirname, './src')
        }
    },
    module:{
        rules:[
           {
                test: /\.css$/,
                use: [
                    MiniCssExtractPlugin.loader,
                    'css-loader',
                    'postcss-loader',
                ]
            },
            {
                test: /\.less$/,
                use: [
                    MiniCssExtractPlugin.loader,
                    'css-loader',
                    'less-loader',
                    'postcss-loader',
                ]
            },
            //.jsx文件 babel-core babel-loader babel-preset-env babel-preset-react
            {
                test:/\.jsx?$/,
                exclude:/node_modules/,
                loader:"babel-loader"
            },
            {
                test: /\.(png|jpg|gif|jpeg|bmp)$/,
                loader: ['url-loader?limit=10&name=images/[name].[ext]','image-webpack-loader?{progressive:true, optimizationLevel: 7, interlaced: false, pngquant:{quality: "65-90", speed: 4}}']
            },
            {
                test:/\.(woff|woff2|svg|ttf|eot)($|\?)/i,
                loader:'url-loader?limit=50&name=fonts/[name].[ext]'
            }
        ]
    },
    plugins:[
        new webpack.ProvidePlugin({
               "React": "react",
               "ReactDOM":'react-dom'
        }),
        new webpack.BannerPlugin("Copyright cyn inc."),
        new HtmlWebpackPlugin({
            template:"static/index.html",
            hash:true,
            minify:{
                caseSensitive: false,
                collapseBooleanAttributes: true,
                collapseWhitespace: true
            }
        }),
        new MiniCssExtractPlugin({
            filename:'css/[name].css'
        }),
        new OptimizeCSSPlugin({
            cssProcessorOptions: {
                safe: true
            }
        }),
        new webpack.HotModuleReplacementPlugin()
    ],
    optimization:{
        splitChunks:{
            chunks:"all"
        }
    }
}
```


static/index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    <div id="app"></div>
</body>
</html>
```


src/compontents,
/pages,/api,/main.jsx,/router.jsx


main.jsx
```
import "u-reset.css"
ReactDOM.render(<h1>hello,react</h1>,document.querySelector('#app'))
```

package.json 
```
"scripts": {
    "start": "webpack-dev-server --open --progress --config webpack.dev.config.js",
    "build": "webpack-cli --progress --config webpack.pro.config.js"
  },
 ```
 
 
 
 
 ## 路由
 ```
 const routes=router :[
 {
     path:"/"
     component:jokeImg,
     meta:{
         icon
         title
         activeClassName
     }
 },
 ]
 
 ```
 
 
 ```
 aonst app=<Router>
 <div classNmae>
 ```