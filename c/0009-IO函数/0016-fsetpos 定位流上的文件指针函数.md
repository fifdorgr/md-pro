函数原型：int fsetpos(FILE *fp, const fpos_t *pos);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：将文件指针定位在pos指定的位置上。该函数的功能与前面提到的fgetpos相反，是将文件指针fp按照pos指定的位置在文件中定位。pos值以内部格式存储,仅由fgetpos和fsetpos使用。
返回值：成功返回0，否则返回非0。
例程如下 应用fsetpos函数定位文件指针。
```  
include <stdio.h>
void main( void )
{
   FILE   *fp;
   fpos_t pos;
   char   buffer[50];
   /*以只读方式打开名为test.txt的文件*/
   if( (fp = fopen( "test.txt", "rb" )) == NULL )
      printf( "Trouble opening file\n" );
   else
   {
      /*设置pos值*/
      pos = 10;
      /*应用fsetpos函数将文件指针fp按照
      pos指定的位置在文件中定位*/
      if( fsetpos( fp, &pos ) != 0 )
        perror( "fsetpos error" );
            else
            {
                /*从新定位的文件指针开始读取16个字符到buffer缓冲区*/
                fread( buffer, sizeof( char ), 16, fp );
                 /*显示结果*/
                printf( "16 bytes at byte %ld: %.16s\n", pos, buffer );
                }
      }
   fclose( fp );
}
```

#### 例程说明：

（1）首先，程序以只读方式打开名为test.txt的文件。在这里，test.txt文件中已存入字符串This is a test for testing the function of fsetpos.

（2）将pos设置为10。应用fsetpos函数将文件指针fp按照pos指定的位置在文件中定位。这样文件指针fp指向字符串中test的字母t。

（3）再从新定位的文件指针开始读取16个字符到buffer缓冲区，也就是说读取字符串"test for testing"到缓冲区buffer。

（4）最后显示结果：16 bytes at byte 10: test for testing 。
