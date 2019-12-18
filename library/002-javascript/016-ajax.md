## ajax 异步的javascript和XML  发送接收数据
> 不刷新页面的情况下 请求和接收数据

**必须在服务器环境下运行**
> 服务器:apache tomcat nginx

* wamp:windows apache MySQL php
* lamp
* malp


由XMLHttpRequest 对象Javascript 和 DOM


## 用法
### 1.实例化


```js
var xhr = new XMLHttpRequest();
```


### 2.打开连接

> psot 请求需要设置头信息

xhr.setRequestHeader("Content-Type", "application/x-www-form-urlencoded");

```js
xhr.setRequestHeader("Content-Type", "application/x-www-form-urlencoded");
xhr.open(发送方式,目标地址,是否异步)

xhr.open("get","1.php?name=value&name2=value2",true)
xhr.open("post","1.php",true)
```

### 3.发送
```js
xhr.send("post数据");
```
> 数据放置位置：get数据放到地址后面，post数据放到send方法参数中



### 4.等待响应

> 通过事件检测ajax是否执行完成:判断状态码是否正常

> readystatechange 靠事件触发 当ajax状态改变时就会触发该事件

> readyState: 事件触发状态码 0-4


```js
xhr.onreadystatechange=function(){
    //readyState 值为4，说明接收到的数据已经处理好了
    if(xhr.readyState==4){
        //后台的服务器的状态码 200表示请求正常 
        if(xhr.status==200){
            xhr.response
        }
        
    }
}
```


### 5.通过response获取数据


ajax请求到的数据，只能在ajax的事件里使用



### get&post
* get 查
    * 从url发送
    * 有长度限制
    * 安全性差
        * 可以存书签、历史记录
* post 增
    * 从请求头信息发送
    * 容量大
    * 安全性相对较好
        * 不能存书签、没有历史记录
* put 改
* delete 删
* 使用
    * get 只请求数据
    * post 修改数据
    * 后台规定



#### 异步&同步
同步：前面代码执行完成，后面代码才执行
异步：后面代码不需要等待前面代码执行完成



### 使用场景
1. 登录注册
2. 页面初始数据的获取
3. 轮询(时间函数定时获取数据)
4. 请求API接口 获取数据进行页面渲染



## 跨域

> 跨域名访问资源，跨域名访问资源会报错


> 域名不同、协议不同、端口号不同，有一个不同就会出现跨域


### 解决跨域
```php
<?php
$href =$_GET['href'];
echo file_get_contents( $href );
?>
```

1. 后台没有跨域
2. JSONP跨域
    * html打开文件，没有跨域问题，用script标签打开API
    * <script src="API地址"></script>

> API返回的数据必须是调用函数 name()

### 异步编程
> 当一次请求需要的参数，是从上一次请求的结果中得到，将第二次请求放到第一次请求的成功函数里


## promise
> 解决回调函数嵌套问题 ES6


```js 
new Promise((resolve,reject)=>{
    //resolve 代码执行成功之后执行的下一段代码
    ajax({
        success:function(){
            resolve();//等价于调用了then方法
        },
        error:function(){
            reject();//等价于调用了catch方法
        }
    })
})
pro.then()
pro.catch()
```

#### then catch finally

* then 执行成功
* catch 捕获错误
* finally 成功错误都会执行



```js
new Promise((resolve,reject)=>{
    ajax({
        url:"1.txt",
        success(m1){
            resolve(m1)
        }
    })
}).then((m1)=>{
    return new Promise((resolve,reject)=>{
        ajax({
            url:"2.txt",
            success(m2){
                resolve(m1+m2)
            }
        })
    })
}).then((m2)=>{
    a
    ajax({
        url:"3.txt",
        success(m3){
            console.log(m2+m3)
        }
    })
}).catch(err=>{
    console.log("错误")
}).finally(()=>{
    console.log("你是真的秀")
})
```