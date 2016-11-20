函数原型：int fgetc(FILE *fp);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：从流中读取字符，即从fp所指定的文件中取得下一个字符。这里需要注意，在每取完一个字符时fp会自动向下移动一个字节。这样编成时，程序员就不用再对fp控制了。这种功能在许多读写函数中都有体现。
返回值：返回所得到的字符，若读入错误。返回EOF。
例程如下：应用fgetc函数从文件中自动读取字符。
```  
include <string.h>
include <stdio.h>
include <conio.h>
int main(void)
{
   FILE *fp;
   char string[] = "This is a test";
   char ch;
   /* 以读写方式打开一个名为test.txt的文件 */
   fp = fopen("test.txt", "w+");
   /* 向文件中写入字符串string */
   fwrite(string, strlen(string), 1, fp);
   /* 将fp指针指向文件首 */
   fseek(fp, 0, SEEK_SET);
   do
   {
      /* 从文件中读一个字符 */
      ch = fgetc(fp);
      /* 显示该字符 */
      putch(ch);
   } while (ch != EOF);
   fclose(fp);
   return 0;
}
```

例程说明：

（1）首先程序先以读写方式打开一个名为test.txt的文件，并向该文件中写入一个字符串。

（2）再应用fseek函数将文件指针fp定位在文件的开头，再循环地将字符逐一读出。这里每读出一个字符，指针fp会自动地向后移一个字节，直至读到文件尾，即EOF标志，循环才停止。因为fgetc函数的返回值为得到的字符，所以用一个字符型变量ch 来接受读出的字符。

（3）最后的运行结果是在屏幕上打印出This is a test字符串。
