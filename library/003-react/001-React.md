react只负责视图
组件化开发思想
VDOM(通过虚拟DOM提升渲染效率)虚拟DOM可以渲染多个终端



### react 环境
1. 学习,测试,浏览器引入
* react.js
* react-dom.js
* babel.min.js

2. 基于webpack
* webpack构建环境
* webpack,webpack-cli,loader,插件

3. reactAPI
* react.createElement()
* ReactDOM.render

### 创建组件
* 函数式创建
```
function xxx (props){
    return view
}
```
* 类创建
```
class xxx extends React.Compontent{
    render(){
        return view
    }
}
```


jsx 渲染{...}


### react 属性 
* dangerouslySetInnerHTML
* ref
* key

### react生命周期

初始化
* [constructor]
* static getDerivedStateFromProps
* [render]
* [componentDidMount]

运行中

* getDrivedStateFromProps 修改状态
* [shouldComponentUpdate] 决定组件是否要更新
* render
* getSnapsshtBforeUpdate
* componentDidUpdate 组件更新完成

销毁

* [componentWillUnmount] 组件销毁之前的清理工作
1. 在componentDidMount原生绑定事件,清理事件绑定
2. 用到了定时器函数,清理定时器

DOM操作
1. ref
2. ReactDOM.findDOMNode

属性与状态
* 属性是组件之间传递数据
* 状态是自身维护的数据
### react事件
this指向
* xxx.bind
* constructor
* class{
    xxx=()=>{}
}
事件对象

### 组件组合
### 组件沟通
* 父->子 props
* 子->父 回调函数
### react 表单

约束表单
```
<input type="text" value={this.state.xxx} onChange>
````
非约束表单

### 路由
react 一切皆组件

    react-router-dom
    import{
        HashRouter,
        BrowserRouter,
        Router,
        Link,
        NavLink
    } from "react-router-dom"

路由基本使用
```
<HashRouter>
<div>
<Router path=""  component={}/>
</div>
</HashRouter>
```



## 开发react项目

1. 自己搭建开发环境
- webpack+babel+loader+plugins+....
- react +react-dom+react-router-dom
2. react官方命令行工具
```
安装 npm install create-react-app
创建 create-react-app <项目名称>
修改配置文件 npm run eject
```
3. 组件库
```
npm install antd --save
```
/                       登陆
/main                   主页
/main/dashbord          仪表盘
/main/exam              在线考试
/main/me-exam           我的考试
/main/system            系统设置
/main/system/personal   修改信息
/main/sysytem/password  修改密码

```
router.js
impost Login from "./pages/login"
impost Main from "./pages/Main"
import Dashboard from "./pages/Dashboard"
import ExamOnline from "./pages/ExamOnline"
import System from "./pages/System"
import Password from "./pages/System/Password"
import Perdonal from "./pages/System/Personal"
const routes=[
{
    path:'/',exact:true,component:Login
},
{
    path:'/main',component:Main,children:[
    {
        path:'/Dashbord',
        component:Dashbord,
        mate:{
            icon:'',
            title:'仪表盘'
        }
    },{
        path:'/main/examOnline',
        component:ExamOnline,
        mate:{
            icon:'',
            title:'在线考试'
        }
    },{
        path:'/main/exammine',
        component:Exammine,
        mate:{
            icon:'',
            title:'我的考试'
        }
    }，{
        path:'/main/sysytem',
        component:System,
        mate:{
            icon:'',
            title:'系统设置'
        }，
        children:[
        {
            path:'/main/sysytem/password',
            components:Password,
            meta:{
                icon:'',
                title:'修改密码'
            }
        }，
        {
            path:'/main/sysytem/personal',
            components:Personal,
            meta:{
                icon:'',
                title:'个人信息'
            }
        }
        ]
    }，
    
    ]
},
]
```



#### 数据可视化
* d3.js
* echars
* hchars
* AntV  优先考虑G2  移动端F2



#### 考试系统前台部分
权限验证
* 页面级别： 控制用户是否有权限访问某个页面
* 页面元素级别 ：根据用户角色控制用户是否有权限操作某个部分


将判断是否登录重新封装成一个组件，判断是否登录选择返回的是正常的路由还是重定向
```
import React,{Component} from "react"
import {Route,Redireact} from "react-route-dom"

export default class AuthRouetr extends Component {
    render(){
        const isLogin=sessionStorage.getItem("token")!==null;
        var {component:Component,...rest}=this.props
        return  <Router  render={props=>{
            if(islogin){
                return <Component {...props}/>
            }else{
                return <Redirect
            }
        }
    }
}
```
