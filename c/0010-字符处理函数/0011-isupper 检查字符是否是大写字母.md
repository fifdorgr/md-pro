函数原型：int isupper(int c);
头文件：include<ctype.h>
是否是标准函数：是
函数功能：检查字符c是否是大写字母（A~Z）。
返回值：当c为大写字母时，返回1，否则返回0。
例程如下： 应用isupper函数统计字符串中的小写字母个数。
```  
include <stdio.h>
include <ctype.h>
int main(void)
{
    char ch;
    int i=0;
    ch=getchar();
    while(ch!=EOF){
        if(isupper(ch))i++;
        ch=getchar();
    }
    printf("%d",i);
    getchar();
    return 0;
}
```

#### 例程说明：

本例程利用函数isupper统计输入的字符串中大写字母的个数。最后，在屏幕上显示出小写字母的个数。本例程的运行结果是：
```  
ABCDEabcFG123^Z
7
```
