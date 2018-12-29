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

# HTML5
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

# css选择器
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