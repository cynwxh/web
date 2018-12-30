# 响应式
> 同一套网页可以适应不同尺寸的设备

* . 检测浏览器尺寸，根据不同尺寸采用不同的css

### 原理：css媒体查询

* . @media 设备名称 and (需要检测的样式){
    css样式
}

* . @media screen and (max-width:1200px){
    css样式
}

* . max-width:1200px 最大宽度1200px,表示宽度小于等于1200px

* . min-width:1200px 最小宽度1200px,表示宽度大于等于1200px
### 阈值

1. pc 大屏幕 >1200px

`@media screen and (min-width:1200px){}`

2. pc 小屏幕 992-1200px

`@media screen and (min-width:992px) and (max-width:1200px){}`

3. 平板 768-992px

`@media screen and (min-width:768px) and (max-width:992px){}`

4. 手机 <768px

`@media screen and (max-width:768px){}`

### 如何实现响应式

1. 宽度
* 修改内宽
    * pc大屏：1200
    * pc小屏(992-1200):970
    * 平板(768-992):750
    * 手机(<768):100%
* 内宽中的元素尽量使用 百分比
2. 控制显示与隐藏(dispaly)


响应式注意事项：
* @media 要放到css的末尾
* @media 中的选择器要和原本的选择器优先级相同



## codding

* git clone 仓库地址将网上仓库下载到本地 
* git pull  将网上仓库的内容同步到本地
* git status    查看本地仓库已修改的文件
* git add .  将全部已修改文件添加准备上传 
* git commit -m"注释说明"   添加注释说明  必须添加
* git push      将本地文件上传到服务器 
