函数原型：int printf( const char *format [, argument]... );
头文件：include<stdio.h>
是否是标准函数：是
函数功能：按format指向的格式字符串所规定的格式，将输出表列argument的值输出到标准输出设备。该函数与fprintf类似，但只能将argument的值输出到标准输出设备stdout,即显示器屏幕，而不能输出到用户自定义的文件中。
返回值：输出字符的个数，若出错则返回一个负数。
例程如下 应用printf函数输出字符串。
```  
include <stdio.h>
include <string.h>
int main(void)
{
  int a=1;
  char ch='r';
  char str[]="This is a test!";
  printf("Output a string.\n");
  printf("%s",str);
  printf("The integer is %d\n",a);
  printf("The character is %c\n",ch);
  return 0;
}
```

#### 例程说明：
（1）首先在标准输出设备stdout,即显示器屏幕上打印出"Output a string.\n"。

（2）再打印出字符串str中的内容："This is a test!"。

（3）再打印出整型数a：The integer is 1。

（4）再打印出字符ch：The character is r。
