函数原型：int islower(int c);
头文件：include<ctype.h>
是否是标准函数：是
函数功能：检查字符c是否是小写字母（a~z）。
返回值：当c为小写字母时，返回1，否则返回0。
例程如下： 应用islower函数统计字符串中的小写字母个数。
```  
include <stdio.h>
include <ctype.h>
int main(void)
{
    char ch;
    int i=0;
    ch=getchar();
    while(ch!=EOF){
        if(islower(ch))i++;
        ch=getchar();
    }
    printf("%d",i);
    getchar();
    return 0;
}
```

#### 例程说明：

本例程先输入一串任意的字符，然后应用islower函数统计字符串中的小写字母个数。最后，在屏幕上显示出小写字母的个数。本例程的运行结果是：
```  
djcvGGJH4623^Z
4
```
注意：^Z是Ctrl+Z组合键的屏幕显示，即结束标志EOF。
