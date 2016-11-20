函数原型：int ispunct(int c);
头文件：include<ctype.h>
是否是标准函数：是
函数功能：检查字符c是否是除字母、数字、空格之外的可打印字符，也就是检查字符c是否是标点字符。
返回值：当c为标点符号时，返回1，否则返回0。
例程如下： 应用ispunct函数判断标点字符。
```  
include <stdio.h>
include <ctype.h>
include <string.h>
int main(void)
{
    char s[]="He said:Oh!Very well!";
    int i;
    printf("%s\n",s);
    for(i=0;i<strlen(s);i++)
    {
         if(ispunct(s[i])) printf("^");
         else printf(".");
    }
    return 0;
}
```
#### 例程说明：

（1）首先，将字符串"He said:Oh!Very well!"存入以s为首地址的缓冲区中，并在屏幕上显示该字符串。

（2）循环检查该字符串中的每个字符，并在屏幕上显示的该字符串下方作出标记，即：如果不是标点字符，打印"."，如果是标点字符，打印"^"。本例程的运行结果是：
```  
He said:Oh!Very well!
```
