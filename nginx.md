>一、将网页用ftp工具上传到服务器
- 选择整个文件放在root目录下
>二、改nginx.conf配置文件
- 1、切换到conf: `cd /usr/local/webserver/nginx/conf/`
- 2、"ls"查看这个目录有没有`nginx.conf`这个文件
- 3、`vi nginx.conf` 按`i`进入编辑模式
- 4、找到 `location /`
    ```
    将root html改为网页项目，例：root /root/motor;
    将index改为index index.flex.html index.flex.htm;
    ```
- 5、更改完成按esc,然后输入 `:wq` 保存退出
- 6、`cd ..` 返回上一层目录(conf -> nginx)
- 7、`ls`查看有没有`sbin`
- 8、执行`./sbin/nginx -s reload` 重新载入配置文件
>三、403Forbidden
- 1、`ls`查看目录下`logs`,logs存储的是日志文件
- 2、`vi logs/error.log`
- 3、看到了permission denied字眼,权限问题
- 4、再次打开nginx.conf `vi conf/nginx.conf` 按`i进入编辑模式
- 5、将`user`前的`#`号去掉，`nobody`改为`root`
- 5、更改完成按esc,然后输入 `:wq` 保存退出
- 6、`cd ..` 返回上一层目录(conf -> nginx)
- 7、执行`./sbin/nginx -s reload` 重新载入配置文件

>补充
- 1、vi打开文件后 没有修改的话 :q 退出
- 2、vi打开文件后 修改了文件的话 :wq 保存并退出
- 3、/usr/local/webserver/nginx/sbin/nginx -s reload 重新载入配置文件
- 4、/usr/local/webserver/nginx/sbin/nginx -s reopen 重启 Nginx
- 5、/usr/local/webserver/nginx/sbin/nginx -s stop 停止 Nginx
