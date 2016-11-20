## Docker 简介 
除了 Vagrant, Docker 是另一个实现生产和开发环境统一的非常棒的方案. 

Docker 为各种应用程序提供了 Linux 容器. 

你可以安装 Docker 镜像, 如 MySQL 和 PostgreSQL 等, 并且不会污染到你的本地机器, 可以看下 [Docker Hub Registry][docker-hub], 在这里你可以找到你想要的, 提前配置好的, 允许你简单几部就能运行起来的 Linux 容器. 

### 例子: 在 Docker 里面运行 PHP 应用

在你成功 [安装 Docker][docker-install] 后, 你只需要一步就可以安装 Apache + PHP.

下面的命令, 会下载一个功能齐全的 Apache 和 最新版本的 PHP, 并会设置 WEB 目录 `/path/to/your/php/files` 运行在 `http://localhost:8080`:

```console
docker run -d --name my-php-webserver -p 8080:80 -v /path/to/your/php/files:/var/www/html/ php:apache
```

在使用 `docker run` 命令以后, 如果你想停止, 或者再次开启容器的话, 只需要执行以下命令: 

```console
docker stop my-php-webserver
```

```console
docker start my-php-webserver
```

### 了解更多关于 Docker 的信息

The commands mentioned above only show a quick way to run an Apache web server with PHP support but there are a lot
more things that you can do with Docker. 

上面的命令能让你轻松使用 Apache + PHP 环境, 然而, Docker 还提供了好多别的命令, 例如, 作为 PHP 程序员, 一个最重要的事情, 是让你的 Web Server 和数据库链接起来, 怎么实现可以仔细看下 [Docker User Guide][docker-doc].

* [Docker Website][Docker]
* [Docker Installation][docker-install]
* [Docker Images at the Docker Hub Registry][docker-hub]
* [Docker User Guide][docker-doc]


[Docker]: http://docker.com/
[docker-hub]: https://registry.hub.docker.com/
[docker-install]: https://docs.docker.com/installation/
[docker-doc]: https://docs.docker.com/userguide/
