函数原型：int sprintf(char *string, char *farmat [,argument,...]);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：将格式化的数据存储到以string为首地址的缓冲区中。参数argument要被转化为farmat规定的格式，并按照这个规定的格式向字符串数组写入数据。这里应该注意，sprintf函数与printf函数和fprint函数不同，前者是向缓冲区（即数组）写入格式化数据，后者是向标准输出文件（stdout）和用户自定义文件输出格式化数据。
返回值：返回存储在string中数据的字节数。
例程如下 应用sprintf函数向指定缓冲区写入数据。
```  
include <stdio.h>
include <math.h>
int main(void)
{
   char str[80];
   sprintf(str, "An approximation of Pi is %f\n", M_PI);
   puts(str);
   return 0;
}
```

#### 例程说明：
（1）首先开辟一个80字节大小的缓冲区str，即：该缓冲区以str为首地址。

（2）再将指定的字符串写入缓冲区str中。其中，M_PI是math.h中定义的常量3.141593。

（3）应用puts函数向终端输出该字符串。
注意：puts函数的作用是把str指定的字符串输出到标准输出设备，并且将字符串结束标志'/0'转换为回车换行符。因此，该程序运行的结果是：
```  
An approximation of Pi is 3.141593
```
除了规定字符串中的换行符外，程序还将'/0'转换为换行符。
