函数原型：long atol(const char *str);
头文件：include<stdlib.h>
是否是标准函数：是
函数功能：将字符串转换成长整数值，也就是将字符串str转换成长整型值然后获取转换后的结果。
返回值：返回转换后的长整型值
例程如下： 应用atol将字符串转换成长整型值。
```  
include <stdio.h>
include <stdlib.h>
int main(void)
{
   char *str="12345.67";
   long result;
   result=atol(str);
   printf("string=%s\nlong =%ld\n",str,result);
   getch();
   return 0;
}
```

#### 例程说明：

（1）首先，程序声明了一个字符串作为待转换的字符串，声明的长整型变量result用于获取转换结果。

（2）程序通过调用atol将字符串转换为相应的长整型变量，获取转换结果，转换规则与strtoX函数相同。

（3）最后将转换结果打印出来。
本例程的运行结果是：
```  
string =12345.67
long=12345
```
