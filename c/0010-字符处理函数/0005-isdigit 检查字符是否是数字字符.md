函数原型：int isdigit( int c );
头文件：include<ctype.h>
是否是标准函数：是
函数功能：检查字符c 是否是数字字符（0~9）。
返回值：是数字字符返回1，否则返回0。
例程如下：应用isdigit函数统计字符串中数字个数。
```  
include <stdio.h>
include <ctype.h>
int main(void)
{
    char ch;
    int i=0;
    ch=getchar();
    while(ch!=EOF){
        if(isdigit(ch))i++;
        ch=getchar();
    }
    printf("%d",i);
}
```
#### 例程说明：

（1）首先，程序中设置字符型变量ch用以接收输入的字符，设置整型变量i，并初始化i=0，用以统计输入的字符串中数字的个数。

（2）当输入的字符不是EOF时，程序循环执行，并应用isdigit函数判断用户输入的字符是否是数字字符，如果是则在变量i上加1。

（3）最后显示输入的字符串中数字个数。

注意：利用Ctrl+Z组合键输入的字符就是EOF。
本例程的运行结果为：
```  
abc123def567ghi^Z
6
```
