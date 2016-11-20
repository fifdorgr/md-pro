函数原型：void setbuf(FILE *fp, char *buf);
		  void setvbuf(FILE *fp, char *buf, int type, unsigned size);
头文件：include<stdio.h>
是否是标准函数：是
函数功能： 这两个函数使得打开文件后，用户可以建立自己的文件缓冲区，而不必使用fopen函数打开文件时设定的默认缓冲区。
setbuf函数的定义中，参数buf指定的缓冲区大小由stdio.h中定义的宏BUFSIZE的值决定，缺省值default为512字节。而当buf为NULL时，setbuf函数将使文件I/O不带缓冲区。而对setvbuf函数，则由malloc函数来分配缓冲区。参数size指明了缓冲区的长度(必须大于0)，而参数type则表明了缓冲的类型，其取值如下表：
setvbuf函数中参数type的取值含义
```  
type 值	  含义
_IOFBF	文件全部缓冲，即缓冲区装满后，才能对文件读写
_IOLBF	文件行缓冲，即缓冲区接收到一个换行符时，才能对文件读写
_IONBF 	文件不缓冲，此时忽略buf,size的值，直接读写文件，不再经过文件缓冲区缓冲
```
返回值：无。
例程如下 应用setbuf函数指定文件的缓冲区。
```  
include <stdio.h>
void main( void )
{
   char buf[BUFSIZ];
   FILE *fp1, *fp2;
   if( ((fp1 = fopen( "test1.txt", "a" )) != NULL) &&
       ((fp2 = fopen( "test2.txt", "w" )) != NULL) )
   {
      /* 应用setbuf函数给文件流fp1指定缓冲区buf */
      setbuf( fp1, buf );
      /*显示缓冲区地址*/
      printf( "fp1 set to user-defined buffer at: %Fp\n", buf );
      /* 文件流fp2不指定缓冲区*/
      setbuf( fp2, NULL );
      /*信息提示不分配缓冲区*/
      printf( "fp2 buffering disabled\n" );
      fclose(fp1);
      fclose(fp2);
   }
}
```

#### 例程说明：
（1）首先开辟一个大小为BUFSIZ的缓冲区，用作指定文件的缓冲区。这里，BUFSIZE为stdio.h中定义的宏，缺省值为512字节。

（2）以追加的方式和写的方式打开名为"test1.txt"和"test2.txt"的文件。

（3）应用setbuf函数给文件流fp1指定缓冲区buf，其中buf为缓冲区的首地址。并在屏幕上显示该首地址。

（4）文件流fp2不指定缓冲区，也就是第二个参数设置为NULL。并信息提示不分配缓冲区。

（5）关闭两个文件。

注意：使用setbuf函数指定文件的缓冲区时，一定要在文件读写之前。一旦用户自己指定了文件的缓冲区，文件的读写就要在用户指定的缓冲区中进行，而不在系统默认指定的缓冲区中进行。函数setvbuf的用法与setbuf类似，只是它的缓冲区大小可以动态分配，由函数的参数指定，而且缓冲区的类型也可以由参数指定。
