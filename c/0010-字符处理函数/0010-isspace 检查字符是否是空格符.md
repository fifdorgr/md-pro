函数原型：int isspace(int c);
头文件：include<ctype.h>
是否是标准函数：是
函数功能：检查字符c是否为空格符space、制表符tab或是换行符。空格符space的ASCII码为32，制表符tab的ASCII码为9，换行符的ASCII码则为
返回值：当c为空格符或制表符时，返回1，否则返回0。
例程如下： 应用isspace函数转换空格符、制表符和换行符。
```  
include <stdio.h>
include <ctype.h>
int main(void)
{
    char s[]="space |NewLine\n|table\t|";
    int i;
    printf("%s",s);
    printf("\n");
    for(i=0;i<strlen(s);i++)
    {
        if(isspace(s[i])) putchar('.');
        else putchar(s[i]);
    }
    getchar();
    return 0;
}
```
#### 例程说明：
（1）首先，将字符串"space |NewLine\n|table\t|"存入以s为首地址的缓冲区中，并在屏幕上显示该字符串。其中，' '、'\n'、'\t'分别为空格符、换行符、制表符，在屏幕上显示其字符原样。

（2）再通过isspace函数检测出该字符串中的这些空格符、换行符、制表符，将其转换为'.'字符，并输出到终端屏幕。
注意：本例程并没有改变原字符串数组中的存储内容，只是在输出时将字符串中的空格符、换行符、制表符转换为'.'字符并输出到终端屏幕。本例程的运行结果是：
```  
space |NewLine
|table  |
space.|NewLine.|table.|
```
