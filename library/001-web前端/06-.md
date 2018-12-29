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

## css3文字样式
### 文字阴影
* text-shadow:水平偏移 垂直偏移 模糊程度 颜色；

### 首行缩进
* text-indent: px/em
* 1em表示当前标签的font-size的大小

### word-break:break-all;
* 英文文字换行规则，截断英文单词填满整行

### 字间距
* letter-spacing:px;

### 文字描边
* webkit-text-stroke:1px red;1像素 红色描边

## 过渡
* transition,当某一个样式发生改变，这个样式的变化经过一定的时间
* transition:需要过度的样式 时间 运动方式(贝塞尔曲线) 延时
    * 运动方式ease:慢-快-慢
    * 运动方式linear:匀速
```
transition: background 1s linear 1s;
<!--背景颜色过度一秒 匀速 延时一秒-->
```
* 第一个过渡写完逗号隔开写第二个
* 哪个标签需要样式变化，标签本身加transition，不能加到hover上
* 某些样式不能过渡，没有中间值的不能过度
* 过度必须要有初始值和结束值 值必须确定

## css3动画
1.绘制动画

@keyframes name{
    0%{
        初始样式
    }
    100%{
        结束样式
    }
}

2.播放动画

.box{
    animation:动画名称 时间 动画方式 延时 播放次数(无穷大infinite) 是否往复播放(alternate) 是否保留初始/结束帧(both 初始和结束帧都保留)；
}

## css3 2D转换 transform
平移，旋转，缩放
相对自身移动，不会影响其他元素

1.transform:translate(水平平移 ，垂直平移)；单位使用百分比指相对于自身的百分比
```
position: absolute;
top: 50%;
left: 50%;
transform: translate(-50%,-50%)
<!--水平垂直居中-->
```

2.transform:rotate(角度);       旋转  transform-origin：px % top/right..转换中心点

3.transform:scale(倍数)   缩放


## css3 3D转换  transform
平移，旋转，缩放

景深：用户到3D场景的距离

1. transform:translate3d(x,y,z)
2. transform:rotate3d(x,y,z,旋转角度)xyz指是否旋转
3. transform:scale3d(x,y,z)   xyz的值是缩放倍数

