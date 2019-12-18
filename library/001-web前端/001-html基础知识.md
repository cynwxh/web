# HTML基础知识
### 什么是HTML？
```
HTML 是用来描述网页的一种语言。
HTML 指的是超文本标记语言: HyperText Markup Language
HTML 不是一种编程语言，而是一种标记语言
标记语言是一套标记标签 (markup tag)
HTML 使用标记标签来描述网页
HTML 文档包含了HTML 标签及文本内容
HTML文档也叫做 web 页面
```

### HTML编辑器
> 可以使用专业的 HTML 编辑器来编辑 HTML，推荐两款常用的编辑器：

1. Sublime Text：http://www.sublimetext.com/
2. VS Code：https://code.visualstudio.com/

### HTML标签
> HTML 标记标签通常被称为 HTML 标签 (HTML tag)。
```
HTML 标签是由尖括号包围的关键词，比如 <html>
HTML 标签通常是成对出现的，比如 <b> 和 </b>
标签对中的第一个标签是开始标签，第二个标签是结束标签
开始和结束标签也被称为开放标签和闭合标签
```
 HTML标题
```
HTML 标题（Heading）是通过<h1> - <h6> 标签来定义的.

<h1>这是一个标题</h1>
<h2>这是一个标题</h2>
<h3>这是一个标题</h3>
```
 HTML段落
```
HTML 段落是通过标签 <p> 来定义的.

<p>这是一个段落</p>
```
 HTML链接
```
HTML链接是通过标签<a>来定义的.
<a href="www.baidu.com">这是一个链接</a>
```
 HTML图像
```
HTML图像时通过标签<img>来定义的.
<img src="http://img/img.png">
```

### HTML元素
> HTML 元素以开始标签起始
HTML 元素以结束标签终止
元素的内容是开始标签与结束标签之间的内容
某些 HTML 元素具有空内容（empty content）
空元素在开始标签中进行关闭（以开始标签的结束而结束）
大多数 HTML 元素可拥有属性

### HTML属性
> 属性是 HTML 元素提供的附加信息.
* HTML 元素可以设置属性
* 属性可以在元素中添加附加信息
* 属性一般描述于开始标签
* 属性总是以名称/值对的形式出现，比如：name="value"。

下面列出了适用于大多数 HTML 元素的属性：
| 属性 | 描述 |
| :---:|:---:|
|class|为html元素定义一个或多个类名（classname）(类名从样式文件引入)|
|id|定义元素的唯一id|
|style|规定元素的行内样式（inline style）|
|title|描述了元素的额外信息 (作为工具条使用)|

### HTML 头部
```
使用 <title> 标签定义HTML文档的标题
使用 <base> 定义页面中所有链接默认的链接目标地址。
使用 <meta> 元素来描述HTML文档的描述，关键词，作者，字符集等。
```
```
HTML <head> 元素

<head> 元素包含了所有的头部标签元素。在 <head>元素中你可以插入脚本（scripts）, 样式文件（CSS），及各种meta信息。
可以添加在头部区域的元素标签为: <title>, <style>, <meta>, <link>, <script>, <noscript>, and <base>.


HTML <title> 元素

<title> 标签定义了不同文档的标题。
<title> 在 HTML/XHTML 文档中是必须的。
<title> 元素:
1.定义了浏览器工具栏的标题
2.当网页添加到收藏夹时，显示在收藏夹中的标题
3.显示在搜索引擎结果页面的标题

HTML <base> 元素
<base> 标签描述了基本的链接地址/链接目标，该标签作为HTML文档中所有的链接标签的默认链接:
<head>
<base href="http://www.runoob.com/images/" target="_blank">
</head>

HTML <link> 元素

<link> 标签定义了文档与外部资源之间的关系。
<link> 标签通常用于链接到样式表:
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>

HTML <style> 元素

<style> 标签定义了HTML文档的样式文件引用地址.
在<style> 元素中你也可以直接添加样式来渲染 HTML 文档:
<head>
<style type="text/css">
body {background-color:yellow}
p {color:blue}
</style>
</head>
```
```
HTML <meta> 元素

meta标签描述了一些基本的元数据。
<meta> 标签提供了元数据.元数据也不显示在页面上，但会被浏览器解析。
META 元素通常用于指定网页的描述，关键词，文件的最后修改时间，作者，和其他元数据。
元数据可以使用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他Web服务。
<meta> 一般放置于 <head> 区域
<meta> 标签- 使用实例
```
为搜索引擎定义关键词:
```
<meta name="keywords" content="HTML, CSS, XML, XHTML, JavaScript">
```
为网页定义描述内容:
```
<meta name="description" content="免费 Web & 编程 教程">
```
定义网页作者:
```
<meta name="author" content="Runoob">
```
每30秒钟刷新当前页面:
```
<meta http-equiv="refresh" content="30">
```
```
HTML <script> 元素

<script>标签用于加载脚本文件，如： JavaScript。
<script> 元素在以后的章节中会详细描述。
```
HTML head 元素

| 标签 | 描述 |
|:---:|:---:|
|`<head>`|定义了文档的信息|
|`<title>`|	定义了文档的标题|
|`<base>`|	定义了页面链接标签的默认链接地址|
|`<link>`|	定义了一个文档和外部资源之间的关系|
|`<meta>`|	定义了HTML文档中的元数据|
|`<script>`|	定义了客户端的脚本文件|
|`<style>`|	定义了HTML文档的样式文件|

### 标签的种类
* 水平排列 a b i span  img
* 垂直排列 h p div
* 能设置大小 div h p
* 不能设置大小 a b i span img
* 行元素（标签） 横排 不能设置宽高
* 块元素（标签） 竖排 能设置宽高
* 行内块元素 横排 能设置宽高

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
* label标签：出发对应表单元素 没有任何样式的行元素
```
<input type="radio" name="sex" value="man" id="man"><label for="man">男</label>
        <input type="radio" name="sex" value="woman" id="woman"><label for="woman">女</label>
        <input type="checkbox" name="hobby" value="study" id="study"><label for="study">学习</label>
```
### 表格
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



### 元素类型转化 display
disolay:block;将任意标签转化成块元素

display:inline;将任意元素转换为行元素

display:inline-block;将任意标签转换为行内块元素

display:none;将任意标签隐藏



