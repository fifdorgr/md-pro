头文件<signal.h>中提供了一些处理程序运行期间引发的各种异常条件的功能，例如一些来自外部的中断信号等。
在<signal.h>中只定义了两个函数：
```  
int signal(int sig, sigfun fname);
```
和
```  
int raise(int sig);
```
signal函数的作用是设置某一信号的对应动作。其中参数sig用来指定哪一个信号被设置处理函数。在标准C 中支持的信号如下表。
标准C支持的信号
```  
取值, 说明, 默认执行动作, 使用的操作系统
SIGABRT, 异常中止, 中止程序, UNIX DOS
SIGPPE, 算术运算错误, 中止程序, UNIX DOS
SIGILL, 非法硬件指令, 中止程序, UNIX DOS
SIGINT, 终端中断, 中止程序, UNIX DOS
SIGSEGV, 无效的内存访问, 中止程序, UNIX DOS
SIGTERM, 中止信号, 中止程序, UNIX DOS
```
参数fname是一个指向函数的指针，当sig的信号发生时程序会自动中断转而执行fname指向的函数。执行完毕再返回断点继续执行程序。系统提供了两个常量函数指针，可以作为函数的参数传递。它们分别是：
```  
SIG_DEF：执行默认的系统第一的函数。
SIG_IGN：忽略此信号。
```
raise函数的作用是向正在执行的程序发送一个信号，从而使得当前进程产生一个中断而转向信号处理函数signal执行。其中参数sig为信号名称，它的取值范围同函数signal中的参数sig取值范围相同，见表9-6。
下面通过例子理解函数signal和raise。
例程9-2 signall和raise函数演示
```  
include <stdio.h>
include <signal.h>
void Print1();
void Print2();
int main()
{   signal(SIGINT,Print1);
    printf("Please enter Ctr+c for interupt\n") ;
    getchar();
    signal(SIGSEGV,Print2);
    printf("Please enter any key for a interupt\n");
    getchar();
    raise(SIGSEGV);

}
void Print1()
{
    printf("This is a SIGINT interupt!\n");
}
void Print2()
{
    printf("This is a SIGSEGV interupt!\n");
}
```
本例程首先通过用户终端输入Ctrl+c产生一个终端中断，然后应用signal函数调用中断处理函数Print1；再通过raise函数生成一个无效内存访问中断，并通过signal函数调用中断处理函数Print2。
本例程的运行结果为：
```  
Please enter Ctr+c for interupt
^C
This is a SIGINT interupt!

Please enter any key for a interupt
a
This is a SIGSEGV interupt!
```
