函数原型：int ungetc(char c, FILE *fp);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：把字符c退回到fp所指向的文件流中，并清除文件的结束标志。fp所指向的文件既可以是用户自定义的文件，又可以是系统定义的标准文件。
返回值：成功返回字符c，否则返回EOF。
例程如下 应用ungetc函数向标准输入文件退回字符。
```  
include <stdio.h>
include <ctype.h>
int main( void )
{
   int i=0;
   char ch;
   puts("Input an integer followed by a char:");
   /* 读取字符直到输入非数字或EOF */
   while((ch = getchar()) != EOF && isdigit(ch))
      i = 10 * i + ch - 48; /* 将ASCII码转换为整数值*/
   /* 如果输入非数字，将其退回输入流 */
   if (ch != EOF)
      ungetc(ch, stdin);
   printf("i = %d, next char in buffer = %c\n", i, getchar());
   return 0;
}
```

#### 例程说明：

（1）首先从终端输入一串字符串，要求输入整型数字，并以非数字字符结尾。

（2）程序读取字符，直到输入非数字或EOF为止，并将数字字符串转换为整型数。例如：将字符串"123"转换为整型数123。

（3）再将结尾的非数字字符退回到标准输入文件（stdin）。

（4）显示退回到标准输入文件中的字符。

注意：所谓将结尾的非数字字符退回到标准输入文件，就是说将数字字符串后面的那个非数字字符退回到标准输入文件中去。例如：输入的字符串为"123abc"，那么退回的字符就是a。这样，程序将前面的字符串"123"转换为整型数123，并存入变量i中。a作为数字字符串输入的结束标志（因为 a是继数字字符之后的第一个非数字字符），被退回到标准输入文件（stdin）。于是，再调用getchar函数读取的字符就应该是刚刚退回到标准输入文件中的字符a。因此，本段例程的执行结果为：
```  
Input an integer followed by a char:
123abc
i = 123, next char in buffer = a
```
即：输入的字符串中123 为整型数，接下来的字符为a。
