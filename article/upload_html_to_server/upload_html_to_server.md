使用 `secureCRT` 连接服务器，连接成功后，右键点击标签页，`Connect SFTP Session`，会多出一个 SFTP 标签页，在这个标签页中，使用 `ls` 这种命令就是操作服务器，使用 `lls` 这种命令就是操作本地。多出的 `l` 表示 `local`，也就是操作本地的意思。

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

