# aliyun_ecs_guide

## 机器购买&HelloWorld
### 购买ECS :centos 
### 安装nginx http://www.runoob.com/linux/nginx-install-setup.html
* runoob 这里有大量的靠谱软件配置内容
### 配置80端口可访问 https://blog.csdn.net/inite/article/details/73658214
* nginx布置 /usr/local/webserver/nginx/sbin/nginx


## Nginx
### 以下包含了 Nginx 常用的几个命令：

* /usr/local/webserver/nginx/sbin/nginx -s reload            # 重新载入配置文件
* /usr/local/webserver/nginx/sbin/nginx -s reopen            # 重启 Nginx
* /usr/local/webserver/nginx/sbin/nginx -s stop              # 停止 Nginx

## 几个参考帖子：
https://www.itony.net/post/aliyun-centos7-ghost.html
https://blog.csdn.net/scythe666/article/details/51872380

最要命的一个点，nginx是监听80端口，在ecs起起来nginx后就可以看到的默认主页了，阿里云的其他端口需要配置安全组，
就是2368端口，始终远程无法访问

在远程服务器上是可以通过 curl http://127.0.0.1:80 访问到nginx主页html内容，且也可以通过curl http://127.0.0.1:2368 访问到html内容，
但在client端直接访问服务器 外网ip:2368 就是无法访问

最后在论坛中看到 作者 @王赛的一个 问答，终于解决了
http://47.100.45.236:2368/
