函数原型：char *gets(char *buf);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：从标准输入文件stdin（键盘）中读取一个字符串，并把该字符串存入以buf为首地址的缓冲区中。该函数与fgets类似，但它只能从标准输入文件stdin中读取字符串，而且没有长度限制。
返回值：返回其参数，即缓冲区指针buf，若出错则返回空NULL。
例程如下 应用gets函数从键盘读取字符串。
```  
include <stdio.h>
int main(void)
{
   char string[30];
   printf("Input a string:");
   /*从终端输入字符串，注意不要超过30个字符*/
   gets(string);
   /*显示该字符串*/
   printf("The string input was: %s\n",string);
   return 0;
}
```

#### 例程说明：

（1）首先，程序开辟一个可容纳30个字符的字符串数组空间，并在屏幕上提示用户输入一个字符串。

（2）应用gets函数接收键盘输入的字符串，并把它存储到以string为首地址的缓冲区中。

（3）最后，将以string为首地址的缓冲区中的内容显示出来，即在屏幕上显示输入的字符串。
