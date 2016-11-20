函数原型：void rewind(FILE *stream);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：将文件指针fp重新定位在文件开头，并清除文件的结束标志和错误标志。该函数与函数fseek功能类似，但不同的是，该函数可以清除文件的结束标志和错误标志，而函数fseek不能；另外，该函数不能像函数fseek一样返回一个值表明操作是否成功，因为该函数无返回值。
返回值：无。
例程如下 应用函数rewind重定位文件指针。
```  
include <stdio.h>
void main( void )
{
   FILE *fp;
   int data1, data2;
   data1 = 1;
   data2 = 2;
   if( (fp = fopen( "test.txt", "w+" )) != NULL )
   {
      fprintf( fp, "%d %d", data1, data2 );
      printf( "The values written are: %d and %d\n", data1, data2 );
	  data1=0;
      data2=0;
      rewind( fp );
      fscanf( fp, "%d %d", &data1, &data2 );
      printf( "The values read are: %d and %d\n", data1, data2 );
      fclose( fp );
   }
}
```

#### 例程说明：
（1）首先以写的方式打开一个名为"test.txt"的文件。

（2）应用fprintf函数向该文件写入data1，data2两个整型数，其值分别为1，2。此时，文件指针fp已指向文件尾。

（3）在屏幕上显示这两个数。

（4）再将变量data1和data2置0。

（4）应用rewind函数重定位文件指针，将文件指针fp重新定位在文件开头。

（5）再应用fscanf函数向data1，data2两个变量中读入文件中的数字。

（6）在屏幕上显示这两个数。
注意：在应用fprintf函数向该文件写入data1，data2两个整型数后，文件指针fp会自动指向文件尾。只有再应用函数rewind、fseek才能将文件指针重新定位到文件开头，以便读取文件。本例中，将data1和data2置0的目的是为了说明应用fscanf函数向data1，data2两个变量中读入文件中的数字的结果是正确的。本程序的运行结果为：
```  
The values written are: 1 and 2
The values read are: 1 and 2
```
