## 标签
* br标签：换行
* hr标签：分割线<br>
* HTML实体：用特殊的代码表示特殊的符号<br>
* &nbsp；空格<br>
* &lt；小于号  &gt；大于号<br>

### 列表标签
* ul无序列表标签
* ol有序列表标签
* ul的直接子元素只能是li

### 表单标签 form
* 前台填写信息发送给后台
* form 表单的容器
* action属性：表单信息发送到目标地址
* method属性：表单发送数据的方式(get post)

### 表单控件 input 行内块标签
* type属性 表单控件的类型
    * text：单行文本框(name必填)
    * password：密码框(name必填)
    * radio：单选按钮(name必填value必填)
    * checkbox:复选(name必填value必填)
    * submit:提交按钮(value必填)
    * reset：重置按钮(value必填)
    * file：文件上传(name必填)
    * color：颜色(name必填)
    * date：日期(name必填)
    * range：滑条(name必填)
    * number：输入数字(name必填)
    * select：下拉框
* name属性：表单控件的名称 需要提交数据的控件的name属性是必填的
* value属性：指表单控件的默认值
* placeholder属性：提示文字
```
<input type="text" name="user" placeholder="请输入账号">
```
* readonly属性：表单元素只读(不可修改)
* disabled属性：表单元素禁用(功能失效)
* required属性：表单元素必填，不填写无法提交表单

### label标签
* label标签：触发对应表单元素 没有任何样式的行元素
```
<input type="radio" name="sex" value="man" id="man"><label for="man">男</label>
        <input type="radio" name="sex" value="woman" id="woman"><label for="woman">女</label>
        <input type="checkbox" name="hobby" value="study" id="study"><label for="study">学习</label>
```
## ifram标签
* 引入一个网页
```
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>iframe</title>
    <style>
        iframe{
        width: 100%;
        height: 500px;
        }
    </style>
</head>
<body>
    <iframe src="../mi/index.html" frameborder="0"></iframe>
</body>
</html>
```
## import标签
* 引入css样式 在css文件顶部引入
```
@import "reset.css";
```

## css选择器
* 标签选择器（根据标签名称选择标签）
* 类名选择器
    1. 由数字，字母，下划线，连接符组成
    2. 只能由字母开头
    3. 语义化
    4. 驼峰命名法pingMu
* id选择器  #
* 后代选择器  父标签 子标签
    * 减少类名的使用
    * 类名可以重复使用
* 群组选择器  标签1，标签2，标签3
## 伪类选择器
* :link  选中未被访问的超链接
* :visited  选中已被访问的超链接
* :hover  选中鼠标悬浮的的超链接
* :active  选中被鼠标激活的超链接
### 鼠标移入父元素，使子元素属性改变
```
div:hover a{
    color:red;
}
```
### 交叉选择器：选中同时符合多个选择器的标签
```
.box.list{}
<div class="box list"></div>
<!--选中的是既有box类名又有list类名的标签-->
```
### 子代选择器 父>子 只能选中直接子元素
```
.box>a{}
<div class="box">
<a>         <!--选中的是直接子元素-->
<a></a>
</a>
</div>
```
### 属性选择器
* [属性名] 选中拥有该属性名的标签
```
[type]{}
<!--选中有type属性的标签-->
```

* [属性名="属性值"] 选中属性名等于该属性值的标签
    
```
[type="text"]{}
<!--选中type=text的标签-->
```
* [属性名^=属性值] 选中属性名中以该属性值开头的标签
```
[class^=box]{}
<div class="box1"></div>
<div class="box2"></div>
<!--box1和box2都将被选中-->
```
* [属性名$=属性值] 选中属性名中以该属性值结尾的标签
```
[class^=box]{}
<div class="nbox"></div>
<div class="bbox"></div>
<!--nbox和bbox都将被选中-->
```
* [属性名*=属性值] 选中属性名中包含该属性值的标签
```
[class^=box]{}
<div class="box1"></div>
<div class="box2"></div>
<!--box1和box2都将被选中-->
```
##  css伪元素选择器
* ::after
* ::before
* 向网页中添加内容
```
.box::after{
    content:  world;
}
    /* 向.box后添加内容 */
.box::before{
    content: hello;
}
    /* 向.box前添加内容 */
```
## css结构伪类选择器
* :first-child 选中作为子元素的第一个标签
* :last-child
选中作为子元素的最后一个标签
* nth-child(n)选中作为子元素第n个标签
* nth-last-child选中作为子元素倒数第n个标签
* first-of-type选中同类型标签中的第一个标签
* last-of-type选中同类型标签中的z最后一个标签
* nth-of-type选中同类型标签中的第n个标签
* nth-last-of-type选中同类型标签中倒数第n个标签

## 排除选择器
* :not(:lastchild)排除最后一个

### 盒子模型
* 标签的内容(content)，边框(border)，内边距(padding)，外间距(margin)
* 内容(content)：标签内部的其他标签
* 边框(border)：border:width  style color; border:5px solid red;
    * 实线：solid
    * 虚线：dashed
    * 双线：double
    * 内嵌：inset
* top bottom left right center
* 内边距(padding)：内容到边框的距离
* 外间距(margin)：容器到容器之间的距离
### 使用盒子模型的注意事项
* padding和border会使元素变大
    * box-sizing:border-box;固定border的大小而不是content的大小
    * padding两个参数指上下左右  三个指上 左右 下  四个指上右下左
* 部分标签有默认样式
    * margin:h p body hr
* 垂直方向的margin会发生合并
* 行元素不能设置上下margin/padding/border，不占据页面位置
* 子元素的margin-top会作用于父元素
    * 父子元素都没有浮动
    * 父元素没有border-top或padding-top
    * 子元素必须是第一个子元素
    * 解决方法：使用父元素的padding-top替代子元素的margin-top

### 浮动
* 标签居左或居右
* 使块元素横排

### 浮动的注意事项
* 浮动的子元素不能自动撑开父元素
    * 父元素添加css样式：overflow:hiden;(隐藏超出的部分，计算父元素高度会把浮动的子元素的高度也算上)
    * 在没有高度的末尾加一个空的块标签，并且给空的块标签添加样式style="clear:both;"清除浮动的影响
```
<div style="clear:both;"></div>
```
* 浮动会破坏文档流，不存在三种元素种类的区别 横排，可以设置宽高


## 布局
* 行元素/行内块水平居中：text-align:center;
* 行元素垂直居中：line-hight
* 块元素水平垂直居中：定位
```
width: 200px;
height: 200px;
background-color: aqua;
position: absolute;
top: 50%;left: 50%;
margin-top: -100px;
margin-left:-100px;
```


## 样式的继承
* 父元素的样式作用到子元素上
* 文字样式可以被继承
    * font-family\color\line-height\text-align等等
* 除文字外所有样式都不能被继承

## 样式的优先级
* 默认样式，继承的样式，id,class,标签名
* 行内样式>id>class>标签名>默认样式>继承的样式
* 优先级最高 ：!important;
* 选择器选的越精确优先级越高

## 表格
cellspacing属性：单元格的间距
```
<table cellspacing="0">
```
colspan属性：合并列单元格
rowspan属性：合并行单元格
```
<td colspan="2"></td><!-- 合并两列-->
<td sowspan="2"</td><!--合并两行-->
```



## css3新增样式
### 颜色
* red
* 十六进制 #000000;
* rgb(0,0,0)
* rgba(0,0,0,0.5) 黑色，半透明 (新增颜色透明度设置)
```
background-color:rgba(0, 0, 0, 0.5); <!--透明度50%的黑色-->
```
* hsla() 色调 饱和度 亮度 透明度 (新增)


* 透明度 opacity：0-1  调节整个标签的透明度
```
<img src="../mi/images/1.jpg" alt="" style="opacity: 0.2;"> <!--使图片透明度变为20%-->
```
### 背景
* background-color
* background-image:url()
* background-repeat:no-repeat; 背景图片是否平铺
* background-position:center; 图片的位置
```
background-position: 50px 50px;<!--水平位置50px，垂直位置50px-->
background-position: left top;<!--左上角-->

```


* background-size:宽 高/%/cover/contain;
    * 图片的宽高，一般只设置一个值
    * 100%指占满容器
    * cover指等比例缩放，直到刚好占满容器(图片可能会缺失)
    * contain指背景图片等比例缩放，直到宽或者高占满容器(可能占不满容器)
* background简写
```
background:#fff url(../images/1.jpg) no-repeat center/200px;
<!--背景：白色 图片填充 没有平铺 居中 宽度200px-->
background:#fff url(../mi/images/1.jpg) no-repeat center/cover;
<!--背景五个属性简写格式 背景：白色 图片填充 没有平铺 居中 图片大小占满容器-->
```
* 背景图片固定定位到 屏幕
```
background-attachment: fixed;
```
    * 全屏背景图
* 背景的作用范围
```
background-clip: border-box/padding-box;
<!--背景作用到边框/内边距-->
```
* 背景七个属性简写
```
background: color image repeat position size clip attachment;
```

### 背景精灵
* 将所有图片放在一张图片上面，通过定位调整位置
```
background: url(images/1.jpg) no-repeat -200px -100px;
<!--背景填充为图片 无平铺 向左移动200px 向上移动100px-->
```

### 背景渐变
* 线性渐变  background-image: linear-gradient(方向，颜色1，颜色2)
```
background-image: linear-gradient(to right,red 20%,blue)
<!--从左向右，红色到蓝色的线性渐变，百分数指颜色在容器中的位置-->
background-image: linear-gradient(0deg,red,blue)
<!--0度(从下到上)，红色到蓝色的线性渐变-->
```
## css3边框
### 圆角
* border-radius:上右下左；单位 px
```
border-radius:20px 20px;
```
### 阴影
* box-shadow: 水平偏移 垂直偏移 模糊程度 阴影大小 颜色 内外；
```
box-shadow: 20px 20px 20px 10px red inset;
<!--向左向下20px 20px的模糊 大小10px 红色 内阴影-->
box-shadow: 20px 20px 20px 10px red inset,20px 20px 20px 10px blue;
<!--向左向下20px 20px的模糊 大小10px 红色 内阴影，向左向下20px 20px的模糊 大小10px 蓝色 外阴影-->
```
* overflow：hidden（超出隐藏）



* 兼容

```html
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
<meta name="renderer" content="webkit" />
```


