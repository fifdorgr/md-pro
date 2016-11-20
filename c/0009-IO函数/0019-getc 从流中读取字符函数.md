函数原型：int getc(FILE *fp);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：从fp所指向的文件中读取一个字符。该函数与前面所讲到的fgetc作用类似。读取字符后，文件指针fp自动指向下一个字符。
返回值：返回所读的字符，若文件结束或出错返回EOF。
例程如下 应用getc函数从标准输入文件中读取一个字符。
```  
include <stdio.h>
int main(void)
{
   char ch;
   printf("Input a character:");
  /* 从标准输入文件中读取一个字符 */
   ch = getc(stdin);
   /*显示该字符*/
   printf("The character input was: '%c'\n", ch);
   return 0;
}
```
#### 例程说明：
本程序是从标准输入文件（键盘）中读取一个字符，存入变量ch，并显示在屏幕上。
例程如下应用getc函数从一般文件中读取字符。
```  
include <stdio.h>
void main( void )
{
    FILE *fp;
    char ch;
    /*以写的方式打开名为test.txt的文件*/
    fp=fopen("test.txt","w");
    /*写入字符串*/
    fprintf(fp,"This is a test.");
    fclose(fp);
    /*再以读的方式打开名为test.txt的文件*/
    fp=fopen("test.txt","r");
    /*将文件指针指向文件开头*/
    fseek(fp,0L,SEEK_SET);
    /*应用getc函数从文件中循环读取字符并显示出来*/
    while(feof(fp)==0)
    {

        ch=getc(fp);
        printf("%c",ch);
    }
    fclose(fp);
    return 0;
}
```

#### 例程说明：
（1）首先以写的方式打开名为test.txt的文件，并将字符串"This is a test." 写入字符串。

（2）再以读的方式打开名为test.txt的文件，并将文件指针指向文件开头。

（3）最后，应用getc函数从文件中循环读取字符，直到文件结束为止，并将读取的字符显示到终端屏幕。
注意：本例程与上例不同，上例是从标准输入文件（键盘）中读取一个字符，本例是从一般文件中读取字符，关键在于函数的参数不同。
