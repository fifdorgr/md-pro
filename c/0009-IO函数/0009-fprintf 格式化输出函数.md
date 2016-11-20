函数原型：int fprintf(FILE *fp, char *format[, argument,...]);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：把argument的值以format所指定的格式输出到fp指向的文件中。这个函数理解起来和printf类似，在一般的使用中，第二个参数可以是一个字符串的头指针，也可以就是一个字符串。例如：fprintf(fp, "Cannot open this file!!")，意思就是把字符串Cannot open this file!!输出到文件fp中去。该函数一般用作终端的出错提示或是在磁盘中生成错误报告。
返回值：如果正确返回实际输出字符数，若错误则返回一个负数。
例程如下 用fprintf函数向终端发出出错提示。
```  
include <stdio.h>
int main(void)
{
   FILE *fp;
     /*以只读方式打开名为test.txt的文件*/
   if ((fp = fopen("\\test.txt", "rt"))
       == NULL)
   {
      fprintf(stderr, "Cannot open this file!!\n");
      return 1;    /*若该文件不能打开，在屏幕上显示出错提示*/
   }
      /*若该文件能够打开，在屏幕上显示正确提示*/
      fprintf(stderr,"Have open this file!!\n");
   return 0;
}
```

#### 例程说明：

（1）首先，以只读方式打开名为test.txt的文件，如果文件不能打开，这返回NULL。

（2）若该文件不能打开，在屏幕上显示出错提示。

（3）若该文件能够打开，在屏幕上显示正确提示。

注意：该函数中第一个参数是stderr，这是C语言中标准出错输出指针，它指向标准的出错输出文件，也就是显示器。因为，在操作系统中，I/O设备都是用文件进行管理的，因此设备都配有相应的控制文件。在C语言中，有三个文件与终端相联系，因此系统定义了三个文件指针。见下表：
```  
设备文件	文件指针
标准输入	stdin
标准输出	stdout
标准出错输出	stderr
```
在系统运行时，程序自动打开这三个标准文件。
本例程的运行结果为：
（1）如果不能打开文件：
Cannot open this file!!
（2）如果可以打开文件：
Have open this file!!
例程如下用fprintf函数在磁盘中生成错误报告。
```  
include <stdio.h>
int main(void)
{
   FILE *fp1,*fp2;
/*以只读方式打开名为test.txt的文件*/
   if ((fp1 = fopen("text.txt", "rt"))
       == NULL)
   {
	/*若文件打不开，则生成错误报告*/
      fp2=fopen("report.txt","w");
      fprintf(fp2, "Cannot open this file!!\n");
      return 1;
   }
     return 0;
}
```

#### 例程说明：

（1）首先，以只读方式打开名为test.txt的文件，如果文件不能打开，这返回NULL。

（2）若该文件不能打开，则以写的方式打开一个名为report.txt的文件，并按照格式要求向文件中写入字符串"Cannot open this file!!\n"，即生成了一个错误报告。

注意：这里函数fprintf的第一个参数为文件指针，是用户自定义的，与上一例程的系统定义的文件指针stderr不同。fprintf函数与printf函数的使用类似，其实printf函数是fprintf函数的一个特例，printf函数只能向标准输出文件（显示器）输出数据，而fprintf函数也可以向一般用户定义的文件输出数据。
