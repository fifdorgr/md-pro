## Xdebug 
合适的调试器是软件开发中最有用的工具之一，它使你可以跟踪程序执行结果并监视程序堆栈中的信息。
Xdebug 是一个 php 的调试器，它可以被用来在很多 IDE(集成开发环境) 中做断点调试以及堆栈检查。它还可以像 PHPUnit 和 KCacheGrind 一样，做代码覆盖检查或者程序性能跟踪。

如果你仍在使用 `var_dump()`/`print_r()` 调错，经常会发现自己处于困境，并且仍然找不到解决办法。这时，你该使用调试器了。

[安装 Xdebug][xdebug-install] 可能很费事，但其中一个最重要的「远程调试」特性 —— 如果你在本地开发，并在虚拟机或者其他服务器上测试，远程调试可能是你想要的一种方式。

通常，你需要修改你的 Apache VHost 或者 .htaccess 文件的这些值:

```ini
php_value xdebug.remote_host=192.168.?.?
php_value xdebug.remote_port=9000
```

「remote host」 和 「remote port」 这两项对应和你本地开发机监听的地址和端口。然后将你的 IDE 设置成「listen for connections」模式，并访问网址：

    http://your-website.example.com/index.php?XDEBUG_SESSION_START=1

你的 IDE 将会拦截当前执行的脚本状态，运行你设置的断点并查看内存中的值。

图形化的调试器可以让你非常容易的逐步的查看代码、变量，以及运行时的 evel 代码。许多 IDE 已经内置或提供了插件支持 XDebug 图形化调试器。比如 MacGDBp 是 Mac 上的一个免费，开源的单机调试器。

 * [学习更多 Xdebug][xdebug-docs]
 * [学习更多 MacGDBp][macgdbp-install]


[xdebug-install]: http://xdebug.org/docs/install
[xdebug-docs]: http://xdebug.org/docs/
[macgdbp-install]: http://www.bluestatic.org/software/macgdbp/
