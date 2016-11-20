函数原型：int fread(void *buf, int size, int count, FILE *fp);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：从fp指向的文件中读取长度为size 的count个数据项，并将它输入到以buf为首地址的缓冲区中。此时，文件指针fp会自动增加实际读入数据的字节数，即fp指向最后读入字符的下一个字符位置。
返回值：返回实际读入数据项的个数，即count值。若遇到错误或文件结束返回0。
例程如下 应用fread函数从文件中读取数据到缓冲区。
```  
include <string.h>
include <stdio.h>
int main(void)
{
   FILE *fp;
   char str[] = "this is a test";
   char buf[20];

   if ((fp = fopen("test.txt", "w+"))
       == NULL)
   {
      fprintf(stderr,
              "Cannot open output file!!\n");
      return 1;
   }

   /* 向文件中写入字符串数组中的数据 */
   fwrite(str, strlen(str), 1, fp);
   /* 将文件指针定位到文件开头 */
   fseek(fp, SEEK_SET, 0);
   /* 把文件中的数据读出并显示 */
   fread(buf, strlen(str), 1, fp);
   printf("%s\n", buf);
   fclose(fp);
   return 0;
}
```

#### 例程说明：

（1）程序首先以读写方式打开名为test.txt的文件。这里有一个判断，若打开文件失败，则在屏幕上显示出错信息。

（2）应用fwrite函数向文件写入数据。有关fwrite函数后面做详细介绍。

（3）应用fseek函数将文件指针定位到文件开头。

（4）应用fread函数把文件中的数据读入内存。这里读取一个长度为strlen(str)的字符串，并将该字符串存入以buf为首地址的内存缓冲区中。

（5）显示该字符串。
