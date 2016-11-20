函数原型：int scanf(char *format[,argument,...]);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：从标准输入设备（键盘）按照format指定的格式字符串所规定的格式，将数据输入到argument所指定的内存单元。scanf函数与printf函数相对，前者是从标准输入设备输入数值，后者是从标准输出设备输出数值。
返回值：成功返回输入的字符个数，否则遇到结束符返回EOF，出错返回0。
例程如下 应用scanf函数输入数据。
```  
include <stdio.h>
void main( void )
{
    int i;
    char ch;
    float f;
    printf("Please input an integer:\n");
    scanf("%d",&i);
    getchar();
    printf("Please input a character:\n");
    scanf("%c",&ch);
    getchar();
    printf("Please input an float:\n");
    scanf("%f",&f);
    getchar();
    printf("These values are:%d,%c,%f",i,ch,f);
}
```

#### 例程说明：

（1）应用scanf函数向预先声明的三个变量空间输入一个整型数、一个字符、一个浮点数。

（2）在屏幕上显示这三个值。
注意：scanf函数与fscanf函数类似，但只能从标准输入设备文件读取数值，而不能像fscanf函数一样从一般用户自定义文件中读取数值。scanf函数常用作程序设计中数据的输入函数。
