函数原型：int fflush(FILE *fp);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：清除一个流，即清除文件缓冲区，当文件以写方式打开时，将缓冲区内容写入文件。也就是说，对于ANSI C规定的是缓冲文件系统，函数fflush用于将缓冲区的内容输出到文件中去。
返回值：如果成功刷新，fflush返回0。指定的流没有缓冲区或者只读打开时也返回0值。返回EOF指出一个错误。
例程如下：第一种方式读写文件
```  
include <string.h>
include <stdio.h>
include <conio.h>
include <io.h>
int main(void)
{
   FILE *stream1,*stream2;
   char test[20]="This is a test";
   char res[20];
   /*以写的方式打开文件test.txt*/
   stream1 = fopen("test.txt", "w");
   /*向文件写入字符串*/
   fwrite(test,15,1,stream1);
   /*以读的方式打开文件test.txt*/
   stream2 = fopen("test.txt", "r");
   /*将文件内容读入缓冲区*/
 if(fread(res,15,1,stream2))
        printf("%s",res);
   else
        printf("Read error!\n");
   fclose(stream1);
   fclose(stream2);
   getch();
   return 0;
}
```
例程如下：：第二种方式读写文件
```  
include <string.h>
include <stdio.h>
include <conio.h>
include <io.h>
int main(void)
{
   FILE *stream1,*stream2;
   char test[20]="This is a test";
   char res[20];
   /*以写的方式打开文件test.txt*/
   stream1 = fopen("test.txt", "w");
   /*向文件写入字符串*/
   fwrite(test,15,1,stream1);
	/*将缓冲区的内容写入文件*/
   fflush(stream1);
   /*以读的方式打开文件test.txt*/
   stream2 = fopen("test.txt", "r");
   /*将文件内容读入缓冲区*/
 if(fread(res,15,1,stream2))
        printf("%s",res);
   else
        printf("Read error!\n");
   fclose(stream1);
   fclose(stream2);
   getch();
   return 0;
}
```
例程说明：

例程如下：中定义了两个文件指针stream1和stream2。

（1）首先以写的方式打开文件test.txt，用指针stream1指向该文件，并向文件中写入字符串"This is a test"。

（2）不关闭该文件，以读的方式打开文件test.txt，并用指针stream2指向该文件，试图将刚刚写入的字符串读入到内存缓冲区中。如果读入成功，打印出该字符串，否则报错。

实践证明，例程如下：的输出结果是在屏幕上显示错误信息Read error!。

例程如下：中定义了两个文件指针stream1和stream2。

（1）首先以写的方式打开文件test.txt，用指针stream1指向该文件，并向文件中写入字符串"This is a test"。

（2）调用fflush函数将缓冲区的内容写入文件。

（3）不关闭该文件，以读的方式打开文件test.txt，并用指针stream2指向该文件，试图将刚刚写入的字符串读入到内存缓冲区中。如果读入成功，打印出该字符串，否则报错。

实践证明，例程如下：的输出结果是在屏幕上显示字符串"This is a test"。
产生这样的效果原因在于：例程如下：中将文件打开后，指针stream1指向的是该文件的内存缓冲区，将字符串写入后也只是写到了文件的内存缓冲区中，而并没有写到磁盘上的文件中。而当以读的方式打开该文件时，该文件中的内容实际为空，也就是stream2指向的缓冲区中内容为空。因此读文件发生错误。而例程如下：中，在写完文件后调用函数fflush，将缓冲区的内容写到文件中，这样再以读的方式打开该文件时，文件中已经存有了字符串，因此可以正常读出。

注意：如果在写完文件后调用函数fclose关闭该文件，同样可以达到将缓冲区的内容写到文件中的目的，但是那样系统开销较大。
