## 定位 position
### 固定定位 position:fixed;
```
position:fixed;
top: 100px;left: 100px;
```
### 相对定位 position:relative;
* 根据自身原来位置进行偏移
```
position: relative;
top: 100px;left: 100px; <!--根据自身原位置向向下向右移动100像素-->
```
### 绝对定位 position:absolute;
* 跟其他定位配合使用，根据右定位属性的父元素
```
position: absolute;
top: 100px;left: 100px;
```
###  z-index 控制定位元素的上下关系
* 定位元素默认层级为0
* 层级设置整数，数字越大越靠上
```
z-index:1；
```


正方形变圆形
```
border-radios:50%；   <!--圆角属性50%-->
```

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