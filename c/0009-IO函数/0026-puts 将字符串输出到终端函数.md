函数原型：int puts(char *string);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：将string指向的字符串输出到标准输出设备（stdout），并将'\0'转换为回车换行符'\n'。在C语言中，字符串以’\0’结尾。该函数不仅可以将字符串输出到标准输出设备，而且要将字符串的结束标志转换为回车换行。
返回值：成功则返回换行符，若失败则返回EOF。
例程如下 应用puts函数向终端输出字符串。
```  
include <stdio.h>
int main(void)
{
   char string[] = "This is a test!\n";
   puts(string);
   return 0;
}
```

#### 例程说明：

（1）首先，将字符串"This is a test!\n"存入以string为首地址的缓冲区。

（2）应用puts函数将该字符串显示在标准输出设备上。
注意：该函数将字符串的结尾标志'\0'转换为回车换行符'\n'。因此，程序运行的结果为：
```  
This is a test!
```
