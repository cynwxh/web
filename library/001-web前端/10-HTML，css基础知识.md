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