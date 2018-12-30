# HTML,CSS基础知识
* br标签：换行
* hr标签：分割线<br>
* HTML实体：用特殊的代码表示特殊的符号<br>
* &nbsp；空格<br>
* &lt；小于号  &gt；大于号<br>
* css  层叠样式表
修改标签样式
* 查错
1. link是否引入
2. 网页中审查元素 检查路径
3. 查看元素  检查标签样式
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
margin:间距
* div：为页面划分区域
* span:没有任何默认样式
* 宽度：width
* 高度：hight
* 背景颜色：background-color
### css选择器
* 标签选择器（根据标签名称选择标签）
* 类名选择器
    1. 由数字，字母，下划线，连接符组成
    2. 只能由字母开头
    3. 语义化
    4. 驼峰命名法pingMu
#### float(浮动)
* 将一个元素居左(float:left;)或居右(float:right;)对齐
* 使div水平排列