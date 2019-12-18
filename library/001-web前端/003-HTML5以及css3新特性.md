# HTML5新特性
* 简化的html语法
* 标签：新增，删除
    * 语义化标签
        * header标签 头部
        * footer标签 底部
        * section标签 区块
        * main标签 主界面
        * nav标签 导航
    * 优点:
        * 代码可读性提高
        * 有利于搜索引擎优化 SEO
* 接口API：调用硬件设备
* 网页视频音频
* canvans 网页画图
* 网页存储

## css3新特性
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