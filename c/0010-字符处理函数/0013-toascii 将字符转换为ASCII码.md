函数原型：int toascii(int c);
头文件：include<ctype.h>
是否是标准函数：是
函数功能：将c转化为相应的ASCII码。
返回值：返回转换后的数值，也就是转换后的ASCII码。
例程如下： 应用toascii函数将整型数字转换为相应的ASCII码。
```  
include <stdio.h>
include <ctype.h>
main()
{
    int s[]={1,2,3,4,5,6};
    int i;
    for(i=0;i<6;i++)
        {
            printf("%d",s[i]);
        }
    printf("\n");
    for(i=0;i<6;i++)
        {
            putchar(toascii(s[i]));
        }
    getchar();
    return 0;
}
```
#### 例程说明：

（1）首先，在整型数组中存入1~6六个整型数字，并将其显示在终端屏幕上。

（2）循环地将数组中的每个数字转换为其对应的ASCII码，并将其以字符的形式显示在终端屏幕上。本例程的运行结果为：
```  
1 2 3 4 5 6
??? ? ? ?
```
