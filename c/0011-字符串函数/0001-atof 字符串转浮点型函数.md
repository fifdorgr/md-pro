函数原型：float atof(const char *str);
头文件：include<stdlib.h>
是否是标准函数：是
函数功能：将字符串转换成浮点值，也就是将字符串str转换成浮点值然后获取转换后的结果。
返回值：返回转换后的浮点值
例程如下： 应用atol将字符串转换成浮点值。
```  
include <stdio.h>
include <stdlib.h>
int main(void)
{
   char *str="12345.67";
   float result;
   result=atof(str);
   printf("string=%s\nfloat =%f\n",str,result);
   getch();
   return 0;
}
```

#### 例程说明：
（1）首先，程序声明了一个字符串作为待转换的字符串，声明的浮点型变量result用于获取转换结果。

（2）程序通过调用atol将字符串转换为相应的浮点型变量，获取转换结果，转换规则与strtoX函数相同。

（3）最后将转换结果打印出来。
本例程的运行结果是：
```  
string =12345.67
float=12345.669922
```

注意：本例程中，转换成浮点数的结果有些奇怪，它并不等于我们字符串中变量的值，而是存在一定的误差，虽然误差很小，但是可以看出误差是从原字符串中的最后一位开始的，这是由于在转换过程中函数内部在实现时采用的转换方式造成的，如果想避免这种误差，可以使用strtoX系列函数。
