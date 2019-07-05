首先服务器要安装 `nginx`，Centos 7 安装可以参考这篇文章

[Linux系统 Cent os7安装nginx详细教程](https://blog.csdn.net/weixin_43507323/article/details/88896147)

安装 `nginx` 之后，尝试启动 nginx 可能会提示端口被占用，解决方法可以参考这篇文章

[nginx重启 failed (98: Address already in use)](https://blog.csdn.net/zqinghai/article/details/73484394)

nginx 启动成功后，在浏览器输入服务器 ip 就可以看到 nginx 首页了。

接着使用 `secureCRT` 连接服务器，连接成功后，右键点击标签页，`Connect SFTP Session`，会多出一个 SFTP 标签页，在这个标签页中，使用 `ls` 这种命令就是操作服务器，使用 `lls` 这种命令就是操作本地。多出的 `l` 表示 `local`，也就是操作本地的意思。

首先，使用 `cd` 命令进入想存放文件的目录，这里是 `/usr/local/nginx` 目录。

```
cd /usr/local/nginx
```

然后，使用 `lcd` 命令进入本地文件的目录，比如 `/Users/user/home/server` 这个目录下，有一个 `test.html` 文件

```
lcd /Users/user/home/server
```

此时会切换到本地的 server 目录，使用 `put` 命令把当前目录下的 `test.html` 文件上传到服务器

```
put test.html
```

`test.html` 会被上传到服务器上的 `/usr/local/nginx` 目录，使用 `http://ip/test.html` 就可以访问这个 html 文件了。

