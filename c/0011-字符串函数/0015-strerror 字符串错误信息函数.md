函数原型：char *strerror(int errnum);
头文件：include<string.h>
是否是标准函数：是
函数功能：获取程序出现错误的字符串信息，也就是根据错误代码errnum查找到具体的错误信息。
返回值：返回错误信息
例程如下： 应用strerror查看几种错误信息。
```  
include <stdio.h>
include <errno.h>
int main(void)
{
    char *error;
    int i;
    for(i=0;i<12;i++)
    {
        error=strerror(i);
        printf("%s",error);
    }
    getch();
    return 0;
}
```

#### 例程说明：

（1）首先，程序声明了一个字符串用于获取错误信息，声明的整型变量既作为循环变量又作为错误信息代码。

（2）程序通过调用strerror根据错误代码获取到具体的错误信息，其中这些代表具体错误信息的字符串在相应的头文件中定义。循环只取了前十二种错误信息，实际的错误种类还有更多。

（3）每次循环将具体错误信息打印出来。

本例程的运行结果是：
```  
Error 0
Invalid function number
No such file or directory
Path not found
Too many open files
Permission denied
Bad file number
Memory arena trashed
Not enough memory
Invalid memory block address
Invalid environment
Invalid format
```

注意：本例程中，如果读者有兴趣，不妨看看一共系统定义了多少种错误信息，通过更改循环变量将各种错误信息打印出来。
