# jQuery

> js的函数库，封装了js功能:获取，样式，内容，属性，动画，ajax

> 3个版本:版本1兼容ie6-8，版本2和3不兼容

## 特点
1. 隐式循环
2. 链式调用:每个方法结束之后都会将jQuery对象再返回


### 获取
1. $(选择器)


> jquery 获取到的元素和原生获取的元素不同

> jquery对象不能用原生对象的属性和方法


### 筛选
1. eq(n) 【选出下标为n元素 负数表示倒数】
2. filter(选择器/jquery对象/原生对象) 【过滤筛选】
3. is(选择器/jquery对象/原生对象) 判断所选元素有无符合条件的内容
4. has(后代) 筛选出拥有该后代的元素
5. not() 排除符合条件的元素
6. children() 获取到所匹配元素的所有直接子元素
7. find(条件) 【获取符合条件的所有子元素】
8. parent() 获取直接父元素
9. parents(条件) 【获取符合条件的所有祖先元素】
10. end()  【jquery对象恢复到筛选之前的状态】


### 操控内容、样式、属性
1. html() 修改内容(识别标签),同innerHTNL
    * html(function(i,val){}) 可接收一个函数，函数参数1是下标，参数2是标签原本的内容；函数的返回值就是标签的内容
2. text() 修改内容(不识别标签),同innerText
3. val() 表单元素的内容


#### 控制类名、
1. addClass()
2. removeclass()
3. toggleclass()  如果类名存在则删除，不存在则添加
4. hasclass() 检查元素是否有该类名


#### 控制属性
1. arrt(属性名[属性值])
    * div.arrt("id")  获取对应标签的属性值
    * div.arrt("id","abc") 设置对应标签的属性值



## 事件
1. $(function(){})等价于 window.onload=function(){}
2. on(事件名称,[子元素选择器],fun)
    * 第二个参数用于事件委派:原本在父元素的事件必选在该子元素上触发
3. off() 移除事件
4. hover(fun1(),fun2())移入移出



### 修改样式
1. css()  【可以设置和获取样式】
    * css({color:"#fff",background:"#fff"})
    * css("color","red")
2. offset()  【标签到浏览器的距离】  {top:8,left:8}
    * 可以修改 offset({top:8,left:8})
3. position() 标签到有定位属性的父元素的距离
4. scrollTop()  scrollLeft()  【滚动条的距离】
5. width()  height() 【元素内容宽高，不包含padding和border】
6. innerWidth() 包含padding 不能设置
7. outerWidth() 不包含padding border 不能设置


### 动画
1. animate (需要动画的样式，动画时间，动画方式，动画结束之后执行的函数)
2. hide(事件，fun)
3. slideDown()  slideUp()  滑动显示与隐藏
4. fadeIn() 【透明度显示】
5. stop() 停止元素所有动画


### 节点操作
1. A.append(B)  B追加到A末尾
2. A.appendTo(B)  A追加到B末尾
3. A.prepend(B) B追加到A开头
4. A.prependTo(B) A追加到B开头
5. after()  before()  放在标签前面、后面
6. empty() 清空元素的内容
7. remove() 删除一个元素
8. detach() 删除一个元素(元素上的事件会保留)
9. clone()  复制元素


### jQuery对象与原生对象的转化
1. 原生对象->jQuery对象  $(原生对象)
2. jQuery对象->原生对象 
    * jquery[0]
    * get(下标)  将jQuery对象转化为数组
    * get(0)===jquery[0]


### each遍历
```js
 $,each(obj,function(i,val){
     console.log(i,val)
 })
```

 
## ajax
```js
$.ajax({
    url:"",
    data:{},
    async:true,
    dataType:"json",
    success:function(){},
    error:function(){},
    contentType:""  //数据编码方式
    jsonp:"",  //回调函数的参数名
    jsonpCallback:"aaa"  //回调函数所用的函数名
})
```