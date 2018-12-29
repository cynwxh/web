# debug
* 程序出现问题
    * 错误：语法、变量、使用了不推荐的方式
    * 异常：程序正常运行，但是结果不符合预期
* 调试错误
    * 输出 var_dump(),echo,print_r()
    * 工具 Xdebug
* 配置phpstorm Xdebug调试工具
* 下载Xdebug
    * https://xdebug.org/download.php
* PHP版本要与
* xdebug.remote_enable = 1



# session
* session_start() 
    * 创建唯一ID
    * 验证ID
* session_destory()
    * 销毁sessionID，文件销毁

# CMS内容管理系统
前台:输入用户名密码，提交给后台

后台:接收用户提交的用户名和密码

1. 判断用户名密码是否为空，如果为空则退出，返回信息不能为空 ，如果正常则程序继续执行
2. 先判断用户名是否存在，不存在返回结果，存在则继续执行
3. 存在:验证密码是否正确，不正确返回结果，正确则继续执行
4. 正确:登录成功
    session_start() 
    * 给前台返回session_id
    * 创建以session_id命名的文件
    * 给$_SESSION记录，用户登录状态(权限)
    * 状态$_SESSION['islogin']=true
5. 跳转到操作页
    * header('location:admin.php');


# 连接数据库
```
$host = "localhost";
$username = "root";
$password = "";
$db="user";
// 创建连接
$connect = new mysqli($host, $username, $password,$db);
// 检测连接
if ($connect->connect_error) {
    echo "连接失败:".iconv("GBK","utf-8").$connect->connect_error;
}
echo "连接成功";
```