CMS
> 成品: phpcms,dedecms,帝国cms,Discuz

> 博客系统WordPress,论坛系统PHPwind

> 半成品:thinkphp,yii




开发:
1. 传统MVC,模板+thinkPHP(数据+模板=html)
2. 后台接口:restfullAPI+thinkPHP(给前台数据,ajax获取,前台:数据加模板=html(vue,react,angular)
    * 接口开发方式又叫做前后台分离
3. 前端MVC客户端框架:backbone.js,Emberjs,angular.js1.0
4. 组件化+单项数据流:react,Vue,angular2.0~6.0


# Node.js

> 浏览器是JavaScript的运行环境

> node.js是一个让js运行在服务器端的的开发平台,主要用于操作服务器文件,数据库,http协议等系统底层的一些东西

node.js集成v8引擎(Chrome浏览器中JavaScript编译器)


单线程,异步I/O,基于事件驱动,高并发
运行速度快(依赖于V8引擎)


运行nodejs
```
C:\Users\Administrator>d:

D:\>cd web全栈\后台\nodejs

D:\web全栈\后台\nodejs>node text.js
10
10

D:\web全栈\后台\nodejs>
```



node.js模块系统

1. 在nodejs中一个介绍文件就是一个模块
2. 模块的作用域
    * 在一个模块中定义的变量/函数作用范围只属于当前的模块.
3. 模块分类:原生模块,文件模块
    * 文件模块的三种类型.js.node.json

## 模块操作

在每一个模块中都有三个变量

* 导出模块:exports,module
* 加载模块:require

a.js
```
function sum(){
    
}
//第一种方式
exports.sum=sum
//第二种方式
module.exports.sum=sum
```
想直接导出一个非对象的数据
a.js
```
//require得到的结果是module.exports的值
//module.exports={}
module.exports=function(){ 
    return a+b;
}
```

使用模块
b.js
```
var obj=require('./a.js')
obj.sum();
```

nodejs中相对路径,当前目录./不可忽略


版本号:修复bug更新Z位,修复bug,新增功能,向下兼容,更新Y位,新增功能,向下不兼容,更新X位


## npm
1. npm -v
2. npm install 包名/npm i 包名
3. npm uninstall 包名(卸载)
4. npm install 包名@版本号
5. npm update 包名 (更新指定包,不写包名更新所有包)
6. npm ls (列出当前安装了哪些包)
7. npm search 包名(搜索指定的包)
8. npm init (通过向导的方式生成package.json文件)
9. npm adduser(添加npm账号)
10. npm publish (上传包)
11. npm unpublish 包名@版本号(撤销自己发布过的某一个版本的包)
12. npm install(自动查找package.json下载开发依赖和生产依赖)

### 保存到生产依赖(保存至dependencies下)
npm install <包名> --save
npm install <包名> -s

### 保存到开发依赖(保存至devDependencies下)
npm install <包名> --save-dev
npm install <包名> -d

### 本地安装
> 本地安装的包,可以通过require访问
### 全局安装
> 命令行工具,安装到全局
http-sever 简单的http命令行服务器



### 全局变量:不加var
```
a=999//global.a=999
```

> 在nodejs当中,在所有同步代码执行结束后才会执行异步的代码,在某个地方看到了回调函数,那么就是异步代码



> arguments中存放的是回调函数返回的结果

> 箭头函数中arguments返回的结果不同



post方式
```
req.on('data',function(data){
            result +=data;
        })
        req.on('end',function(data){
            var contentType = req.headers['content-type'];
            if(contentType =='application/x-www-form-urlencoded'){
                var obj = querystring.parse(result);
                console.log(obj);
            }else if(contentType == 'application/json'){
                var obj  = JSON.parse(result);
                console.log(obj);
            }
            res.end('ok');
        })
    }else if(pathname == '/reg2'){
        res.end('ok2');
    }
```



> DOMContentLoaded 页面结构加载完成
> load 所有资源加载完成

router.use 中间件使用

router.METHOD(PATH,CALLBACK) 路由系统

router.router 链式路由



获取时间戳
* new Date().getTime
* +new Date()
* Date.now()



### Express是一个路由和中间件的web框

#### 静态资源目录
```
app.use(express.static('public'));
app.use(express.static('public2'));
```
#### 虚拟目录
```
app.use('static',express.static('public');
```
Express应用程序可以使用以下类型的中间件:
* 应用程序级中间件
* 路由器级中间件
* 错误处理中间件
* 内置中间件
* 第三方中间件

> 通过使用和函数将应用程序级中间件绑定到app对象的实例，其中是中间件函数以小写形式处理的请求的HTTP方法（例如GET，PUT或POST）。app.use()app.METHOD()METHOD






# 考试系统

1. 提出需求
2. 分析需求
3. 分析业务流程
    * 分析竞品
    * 结合自身需求改进业务流程
4. 架构选型



req.body 获取post提交的数据
req.query 获取get提交的数据


### web开发索要考虑的问题

* 精确还原设计稿
* 兼容、项目需求、类型
* 兼容测试、性能测试
* 性能优化 3秒 
    * 设计考虑
    * 前台 
        * 减少HTTP请求数量 图标->图片 背景精灵、字体图标（icon font）
        * 文件压缩 css、js、html、img（<100k）
        * 懒加载
        * 公共库
        * 合理的代码结构
    * 后台 gizp 架构优化、代码优化、缓存（redis)
    * 服务器