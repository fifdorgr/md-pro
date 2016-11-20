函数原型：char *fgets(char *string, int n, FILE *fp);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：从fp所指的文件中读取一个长度为(n-1)的字符串，并将该字符串存入以string为起始地址的缓冲区中。fgets函数有三个参数，其中string为缓冲区首地址，n规定了要读取的最大长度，fp为文件指针。
返回值：返回地址string，若遇到文件结束符或出错，返回NULL。用feof 或ferror判断是否出错。
例程如下：用fgets函数从文件中读取字符串。
```  
include <string.h>
include <stdio.h>
int main(void)
{
   FILE *fp;
   char string[] = "This is a test";
   char str[20];
   /* 以读写的方式打开一个名为test.txt的文件 */
   fp = fopen("test.txt", "w+");
   /* 将字符串写入文件 */
   fwrite(string, strlen(string), 1, fp);
   /* 文件指针定位在文件开头*/
   fseek(fp, 0, SEEK_SET);
   /* 从文件中读一个长为strlen(string)的字符串 */
   fgets(str, strlen(string)+1, fp);
   /* 显示该字符串 */
   printf("%s", str);
   fclose(fp);
   return 0;
}
```

#### 例程说明：

（1）首先，以读写的方式打开一个名为test.txt的文件，并将字符串写入文件。
应用fseek函数将文件指针定位在文件开头。

（2）从文件中读一个长为strlen(string)的字符串，这里应注意第二个参数若为n，则表示从fp所指的文件中读取一个长度为(n-1)的字符串。因此，这里的参数为strlen(string)+1，表示读取一个长度为strlen(string)的字符串。把字符串读到以str为首地址的数组中。

（3）最后显示该字符串。
