函数原型：int putchar(char ch);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：将字符串ch输出到标准输出文件stdout上。也就是说将字符串ch输出到显示器屏幕上。
返回值：返回输出的字符ch，若出错，则返回EOF。
例程如下 应用putchar函数在屏幕上显示字符。
```  
include <stdio.h>
int main()
{
    char str[]="This is a test!\n";
    int i=0;
    while(str[i]){
        putchar(str[i]);
        i++;
    }
}
```

#### 例程说明：

（1）首先将字符串"This is a test!\n"存入字符串数组str中。

（2）应用putchar函数，循环地将字符串输出到标准输出文件（终端屏幕）上。
注意：该函数与putc函数不同，它只能向标准输出文件，也就是终端屏幕上输出字符。而putc函数既可以向标准输出文件上输出字符，又可以向一般用户自定义文件上输出字符。
