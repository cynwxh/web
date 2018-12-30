### css选择器
* 标签选择器
* 类名选择器 .
* id选择器  #
* 后代选择器  父标签 子标签
    * 减少类名的使用
    * 类名可以重复使用
* 群组选择器  标签1，标签2，标签3
### 标签的种类
* 水平排列 a b i span  img
* 垂直排列 h p div
* 能设置大小 div h p
* 不能设置大小 a b i span img
* 行元素（标签） 横排 不能设置宽高
* 块元素（标签） 竖排 能设置宽高
* 行内块元素 横排 能设置宽高
### 元素类型转化 display
disolay:block;将任意标签转化成块元素

display:inline;将任意元素转换为行元素

display:inline-block;将任意标签转换为行内块元素

display:none;将任意标签隐藏
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
### 网页布局规范
* 通屏宽内容，宽度设置为100%或者不设置宽度
* 内宽：固定宽度 水平居中
* 确定位置