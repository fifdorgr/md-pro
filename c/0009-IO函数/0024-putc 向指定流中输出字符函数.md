函数原型：int putc(int ch, FILE *fp);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：向指定的文件输出一个字符。该函数有两个参数，ch是用户指定的字符，fp是文件指针。函数将字符ch输出到fp指定的文件中。
返回值：返回输出的字符ch，若出错则返回EOF。
例程如下 应用putc函数向标准输出文件输出字符。
```  
include <stdio.h>
int main(void)
{
   char str[] = "Hello world!";
   int i = 0;
   while (str[i]){
      putc(str[i], stdout);
      i++;
      }
   return 0;
}
```

#### 例程说明：
（1）首先将字符串"Hello world!"存入字符串数组str中。

（2）循环地将数组str中的内容输出到标准输出文件（显示器）上。
例程如下 应用putc函数向用户自定义文件输出字符。
```  
include <stdio.h>
int main(void)
{
   FILE *fp;
   int i = 0;
   char str[]="This is a test!";
   fp=fopen("test.txt","w");
   while (str[i]){
      putc(str[i], fp);
      i++;
      }
    fclose(fp);
   return 0;
}
```

#### 例程说明：

（1）首先将字符串"This is a test!" 存入字符串数组str中。

（2）以写的方式打开一个名为"test.txt"文件，并利用函数putc将数组str中的内容输出到文件"test.txt"中。

（3）关闭文件。

注意：该函数既可以向标准输出文件输出字符，又可以向用户自定义文件输出字符。而且，每当向文件输出一个字符时，文件指针就会自动向后移一个字节。
