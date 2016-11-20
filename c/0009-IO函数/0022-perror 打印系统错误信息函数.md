函数原型：void perror(char *string);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：将错误信息输出到标准出错输出stderr。该函数的参数是字符串指针，指向错误信息字符串。也可以就是一个字符串，直接在参数中输入要显示的错误信息。但要注意，完整的错误信息不仅包括用户在参数中自己定义的字符串，还包括一个冒号，系统报错信息，和一个换行符。该函数主要用作向终端进行错误提示。
返回值：无。
例程如下 应用perror函数显示错误信息。
```  
include <stdio.h>
int main(void)
{
   FILE *fp;
   /*企图以读的方式打开文件test.txt*/
   fp = fopen("test.txt", "r");
   if (fp==NULL)
    /*该文件不存在，在终端显示错误信息*/
      perror("Unable to open file for reading");
   return 0;
}
```

#### 例程说明：
（1）首先程序企图以读的方式打开文件test.txt，但在这里该文件并不存在。

（2）然后，利用函数perror在终端显示错误信息"Unable to open file for reading: No such file or directory"。
具体的运行结果格式如下：
```  
Unable to open file for reading: No such file or directory
```
注意：完整的错误信息包括：用户自定义字符串，冒号，系统报错信息，换行符。
