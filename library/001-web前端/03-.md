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
### cursor：鼠标移入的形状
    * pointer 手形，可点击
    * text 文字形状
    
### iconfont
* 找到图标添加入库，引入字体的css文件，直接使用标签，需把类名改为iconfont
```
<div><i class="iconfont">&#xe600;</i>购物车</div>
```

### css的引用
* link 外部css文件
* style标签内写css样式
* 行内样式
```
<div class="box" style="background:red;></div>
```

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

### 文字的修饰
* text-decoration:underline/line-through/overline;(下划线，删除线，上划线)