函数原型：int fseek(FILE *fp, long offset, int base);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：重定位流上的文件指针，即将fp指向的文件的位置指针移向以base为基准，以offset为偏移量的位置。该函数有三个参数：fp为文件指针，offset为偏移量，即位移offset个字节，base为指针移动的基准，即起始点。其中，基准base用0、1或2表示。在ANSI C标准指定的名字如下表
ANSI C标准指定的起始点名字
```  
起始点	名字  	数字代码
文件当前位置	SEEK_CUR	1
文件开始位置	SEEK_SET	0
文件末尾位置	SEEK_END	2
```
偏移量用长整型数表示。ANSI C标准规定，在数的末尾加L就表示长整型数。该函数在随机读取较长的顺序文件时是很有用的。
返回值：成功返回0，否则返回非0。
例程如下 文件指针的定位演示。
```  
include <stdio.h>
void main( void )
{
   FILE *fp;
   char line[81];
   int  result;
    /*以读写的方式打开打开名为test.txt的文件*/
   fp = fopen( "test.txt", "w+" );
   if( fp == NULL )
      printf( "The file test.txt was not opened！\n" );
   else
   {
      /*按照规定格式将字符串写入文件*/
      fprintf( fp, "The fseek begins here:
                       "This is the file 'test.txt'.\n" );
          /*将文件指针定位到离文件头23个字节处*/
      result = fseek( fp, 23L, SEEK_SET);
      if( result )
         perror( "Fseek failed" );
      else
      {
         printf( "File pointer is set to middle of first line.\n" );
         /*从fp指向的文件中读取字符串*/
         fgets( line, 80, fp );
         /*显示读取的字符串*/
         printf( "%s", line );
      }
      fclose(fp);
   }
}
```

#### 例程说明：

（1）首先，程序以读写的方式打开打开名为test.txt的文件。

（2）然后，应用fprintf函数按照规定格式将字符串"The fseek begins here: ""This is the file 'test.txt'.\n"写入文件。

（3）再将文件指针定位到离文件头23个字节处，即将文件指针fp定位在字符串"This is the file 'test.txt'.\n"的开头。

（4）然后，应用fgets函数从fp指向的文件中读取字符串，并显示在屏幕上。
本程序的运行结果为在屏幕上显示出以下字符串：
```  
File pointer is set to middle of first line.
This is the file 'test.txt'.
```
