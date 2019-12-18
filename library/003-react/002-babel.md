babel 
命令行使用 安装:npm install -g babel-cli

命令

``` 
输出到命令行
babel xxx.js

输出到文件 
--out-file|-o
babel a.js -o b.js
检测文件变化
babel a.js -w b.js
编译整个文件夹
--out -dir |-d
babel lib -d js
babel lib -d -w js
将ES6编译为ES5 安装插件
npm install babel-preset-env 

在跟目录创建配置文件 .babelrc
{
    "presets":["env"]
}
