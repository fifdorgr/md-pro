函数原型：int toupper(int c);
头文件：include<ctype.h>
是否是标准函数：是
函数功能：将c转化为相应的大写字母。
返回值：如果c为小写英文字母，则返回对应的大写字母；否则返回原来的值。
例程如下： 应用toupper函数将小写字母转换为大写字母。
```  
include <stdio.h>
include <ctype.h>
int main(void)
{
    char str[]="This Is A Test!";
    int i;
    printf("%s\n",str);
    for(i=0;i<strlen(str);i++)
    {
        putchar(toupper(str[i]));
    }
    getchar();
    return 0;
}
```

#### 例程说明：

本例程利用toupper函数将字符串中的小写字母转换为大写字母，并输出到终端。本例程的运行结果为：
```  
This Is A Test!
THIS IS A TEST!
```
