# css基础知识

### css的引用
* link 外部css文件
* style标签内写css样式
* 行内样式
```
<div class="box" style="background:red;></div>
```
### 布局
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

### 样式的继承
* 父元素的样式作用到子元素上
* 文字样式可以被继承
    * font-family\color\line-height\text-align等等
* 除文字外所有样式都不能被继承

### 样式的优先级
* 默认样式，继承的样式，id,class,标签名
* 行内样式>id>class>标签名>默认样式>继承的样式
* 优先级最高 ：!important;
* 选择器选的越精确优先级越高

### 文字样式
字体 颜色 字号  加粗  倾斜 下划线
* 颜色：color
* 字体：font-family  'font-family:"微软雅黑","苹方"'
* 字号：font-size  网页默认字号16px，最小字号12px
* 加粗：font-weight
    * normal 正常500
    * bold 加粗700
    * 100-900数字越大字体越粗（一般不用正常500，加粗700）
* 倾斜：font-style
    * normal 正常
    * italic 倾斜
* 水平位置（图片，文字）：text-align
    * left 左对齐
    * right 右对齐
    * center 居中对齐
* 垂直位置：line-height  (行高，一行文字所占高度)
    * 行高设置为与容器高度相同，文字会垂直居中
* text-decoration:underline/line-through/overline;(下划线，删除线，上划线)

### css选择器
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
* 伪类选择器
    * :link  选中未被访问的超链接
    * :visited  选中已被访问的超链接
    * :hover  选中鼠标悬浮的的超链接
    * :active  选中被鼠标激活的超链接
* 交叉选择器：选中同时符合多个选择器的标签
```
.box.list{}
<div class="box list"></div>
<!--选中的是既有box类名又有list类名的标签-->
```
* 子代选择器 父>子 只能选中直接子元素
```
.box>a{}
<div class="box">
<a>         <!--选中的是直接子元素-->
<a></a>
</a>
</div>
```
* 属性选择器
1. [属性名] 选中拥有该属性名的标签
```
[type]{}
<!--选中有type属性的标签-->
```
2. [属性名="属性值"] 选中属性名等于该属性值的标签
    
```
[type="text"]{}
<!--选中type=text的标签-->
```
3. [属性名^=属性值] 选中属性名中以该属性值开头的标签
```
[class^=box]{}
<div class="box1"></div>
<div class="box2"></div>
<!--box1和box2都将被选中-->
```
4. [属性名$=属性值] 选中属性名中以该属性值结尾的标签
```
[class^=box]{}
<div class="nbox"></div>
<div class="bbox"></div>
<!--nbox和bbox都将被选中-->
```
5. [属性名*=属性值] 选中属性名中包含该属性值的标签
```
[class^=box]{}
<div class="box1"></div>
<div class="box2"></div>
<!--box1和box2都将被选中-->
```
*  css伪元素选择器
1. ::after
2. ::before
3. 向网页中添加内容
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
* css结构伪类选择器
1. :first-child 选中作为子元素的第一个标签
2. :last-child
选中作为子元素的最后一个标签
3. nth-child(n)选中作为子元素第n个标签
4. nth-last-child选中作为子元素倒数第n个标签
5. first-of-type选中同类型标签中的第一个标签
6. last-of-type选中同类型标签中的z最后一个标签
7. nth-of-type选中同类型标签中的第n个标签
8. nth-last-of-type选中同类型标签中倒数第n个标签

* 排除选择器
1. :not(:lastchild)排除最后一个
margin:间距
2. div：为页面划分区域
3. span:没有任何默认样式
4. 宽度：width
5. 高度：hight
6. 背景颜色：background-color

## 盒子模型
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

### float浮动
* 浮动会破坏文档流，不存在三种元素种类的区别 横排，可以设置宽高
* 将一个元素居左(float:left;)或居右(float:right;)对齐
* 使div水平排列

### 浮动的注意事项
* 浮动的子元素不能自动撑开父元素
    * 父元素添加css样式：overflow:hiden;(隐藏超出的部分，计算父元素高度会把浮动的子元素的高度也算上)
    * 在没有高度的末尾加一个空的块标签，并且给空的块标签添加样式style="clear:both;"清除浮动的影响
```
<div style="clear:both;"></div>
```
### iconfont
* 找到图标添加入库，引入字体的css文件，直接使用标签，需把类名改为iconfont
```
<div><i class="iconfont">&#xe600;</i>购物车</div>
```
### cursor：鼠标移入的形状
    * pointer 手形，可点击
    * text 文字形状

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
### 鼠标移入父元素，使子元素属性改变
```
div:hover a{
    color:red;
}
```

## flex布局(弹性盒模型)
* display:flex;

### 容器
控制项目的水平垂直排列方式

#### flex-direction  主轴方向(项目排列方向)
* row (默认)从左到右
* row-reverse  从右向左
* column  【从上到下】
* column-reverse  从下到上

#### flex-wrap  项目是否换行
* now wrap 默认不会自动换行
* wrap 项目宽度超过主轴自动换行

#### justify-content 【主轴方向的对齐方式】
* flex-start (默认)主轴起点对齐
* center 主轴中间对齐
* flex-end 主轴终点对齐
* space-between 主轴两端对齐
* space-around 项目两侧间隔相同

#### algin-items 【交叉轴的对齐方式】
* stretch(默认)项目未设置高度，高度默认占满整个交叉轴
* flex-start (默认)交叉轴起点对齐
* center 交叉轴中间对齐
* flex-end 交叉轴终点对齐

#### align-content 当项目换行后，多个主轴的对齐方式
* stretch(默认)项目未设置高度，高度默认占满整个交叉轴
* flex-start 主轴起点对齐
* center 主轴中间对齐
* flex-end 主轴终点对齐
* space-between 主轴两端对齐
* space-around 项目两侧间隔相同

### 项目(直接子元素)
特点
* 内容没有行元素、行内块、块元素的区别
* 内容不能浮动

#### order 项目排列顺序
* order:整数（默认位置是0）;数字越大 排列越靠后
* 【flex-shrink】 (项目宽度超过主轴)项目是否自动缩小
    * 默认值1，会自动缩小
    * 0，不会自动缩小
* 【flex-grow】(项目宽度没有填满主轴)项目是否自动放大
    * 默认值0，不会自动放大
    * 1，会自动放大
* flex:grow shrink basise;(项目放大，缩小，实际宽度)
* flex:1 1 auto;(既允许放大又允许缩小 宽度自动 等于flex:none;允许放大允许缩小)
* flex:0 0 auto;(不允许放大又不允许缩小 宽度自动 等于flex:auto;不允许放大不允许缩小)
* algin-self  项目自身交叉轴对齐方式
    * flex-start (默认)交叉轴起点对齐
    * center 交叉轴中间对齐
    * flex-end 交叉轴终点对齐


* vh,长度单位，把屏幕高度分成一百份，100vh表示一屏高
* vw,长度单位，把屏幕宽度分成一百份，100vh表示一屏宽

## 兼容性
* pc浏览器
    * ie
    * 谷歌
    * 360、搜狗、QQ、uc、百度
* 手机浏览器
    * uc、QQ、360
    * 手机自带
    * APP自带浏览器
* H5:标签

* 语义化标签兼容
```
section,articl,asid,heade,footer,nav,figure,figcaption,time,mark,main{
    display:block;
}
```

### CSS3:样式、选择器、响应式、单位、flex
#### CSS3样式
* 大部分IE8及以下不兼容
#### 浏览器前缀
* ie:-ms-
* 火狐:-moz-
* 谷歌:-webkit-

#### CSS3选择器
* IE8及以下不兼容：结构伪类选择器    :not

#### 单位:vh,vw兼容性差，尽量不用
#### flex兼容性不是很好，必须添加兼容性写法，兼容语法写前面

-webkit-前缀，浏览器

Autoprefix css   自动添加前缀的插件
### 网页布局规范

* 通屏宽内容，宽度设置为100%或者不设置宽度
* 内宽：固定宽度 水平居中
* 确定位置
