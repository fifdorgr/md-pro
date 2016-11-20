函数原型：int isalnum( int c );
头文件：include<ctype.h>
是否是标准函数：是
函数功能：检查字符c 是否是字母（alpha）或数字（number）。
返回值：是字母或数字返回1，否则返回0。
例程如下： 应用isalnum检查字符属性。
```  
include <stdio.h>
include <ctype.h>
int main( void )
{
   char c,ch;
   scanf("%c",&c);
   ch=getchar();
   while(c!='e') {
        if(isalnum(c))
            printf("This is a alpha or a number\n");
        else
            printf("This is a particulate character\n");
        scanf("%c",&c);
        ch=getchar();
   }
   return 1;
}
```

#### 例程说明：

（1）首先，程序声明了两个字符型变量，用以接收来自终端的字符。

（2）当用户输入的字符不是'e'且是字母或数字字符时，就在屏幕上显示"This is a alpha or a number"提示信息。当用户输入的字符不是'e'且不是字母或数字字符时，就在屏幕上显示"This is a particulate character"提示信息。

（3）当用户输入字符'e'时，程序退出。
注意：本例程中，scanf函数用以接收欲判断的字符，getchar函数用以接收回车换行符。本例程的运行结果为：
```  
a
This is a alpha or a number
2
This is a alpha or a number

This is a particulate character
e
```
