# PHPCMS

## 配置域名

1. 修改D:\wamp\bin\apache\apache2.4.9\conf\httpd.conf文件
```
# Virtual hosts
Include conf/extra/httpd-vhosts.conf
```
2. 修改D:\wamp\bin\apache\apache2.4.9\conf\extra\httpd-vhosts.conf文件
```
<VirtualHost *:80>
    ServerAdmin uek-info.com
    DocumentRoot "d:/wamp/www/uek-info"
    ServerName www.uek-info.com
    ErrorLog "logs/www.uek-info.com-error.log"
    CustomLog "logs/www.uek-info.com-access.log" common
</VirtualHost>
```
3. 修改C:\Windows\System32\drivers\etc\hosts文件
```
添加 127.0.0.1       www.uek-info.com
```


从PHPcms内容管理系统中取出数据,展示到指定的模板上




PHPCMS模板标签

{pc:content  action=""  catid="" return="data" num="" page="$page"}
{loop $data $v}
{/loop}
{/pc}


在没一个页面都有$catid,$parentid,$top_parentid


导航选中效果$top_parentid


友情链接,logo 类型1,文字 类型0





