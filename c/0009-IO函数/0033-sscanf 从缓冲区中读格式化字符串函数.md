函数原型：int sscanf(char *string, char *format[,argument,...]);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：将string指定的数据读到argument所指定的位置。其中，参数argument是与format格式要求相符合的变量指针。也就是说，如果format指定的格式为"%d"，则argument就必须是整型变量的指针。这里应该注意，sscanf函数与scanf函数和fscanf函数不同，前者是从指定的缓冲区读格式化数据到新的缓冲区中，而后者是从标准输入文件（stdin）和用户自定义文件中读取格式化数据到缓冲区中。
返回值：成功返回已分配空间的数量，返回0表示没用空间分配，返回EOF表示出错。
例程如下 应用sscanf函数读取格式化数据。
```  
include <stdio.h>
void main( void )
{
   char  str[] = "1 2 3...";
   char  s[81];
   char  c;
   int   i;
   float fp;
   /* 从缓冲区str中读取数据 */
   sscanf( str, "%s", s );
   sscanf( str, "%c", &c );
   sscanf( str, "%d", &i );
   sscanf( str, "%f", &fp );
   /* 输出已读取的数据 */
   printf( "String    = %s\n", s );
   printf( "Character = %c\n", c );
   printf( "Integer:  = %d\n", i );
   printf( "Real:     = %f\n", fp );
}
```

#### 例程说明：
（1）首先开辟一个以str为首地址的缓冲区，并初始化其内容。

（2）应用sscanf函数从缓冲区str中读取数据。分别以格式要求"%s"、"%c"、"%d"、"%f"读取，并存入相应的变量中。

（3）输出已读取的数据。
