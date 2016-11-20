函数原型：int fscanf(FILE *fp, char *format[,argument...]);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：从fp所指向的文件中按format给定的格式读取数据到argument所指向的内存单元。其中argument是指针，指针类型要与输入的格式format相一致。例如：fscanf(stdin, "%d", &i)；&i是整型的指针，输入的格式format也要为整型，即"%d"。
返回值：返回已输入的数据个数。若错误或文件结束返回EOF。
例程如下 应用fscanf函数从终端向内存输入数据。
```  
include <stdlib.h>
include <stdio.h>
int main(void)
{
   char ch;
   printf("Please input an character ");
   /* 从标准输入文件中读取一个字符，并送至ch */
   if (fscanf(stdin, "%c", &ch))
      printf("The character  was: %c\n",ch);
   else
   {
        /*出错提示*/
      fprintf(stderr, "Error reading an character from stdin!!\n");
      exit(1);
   }
   return 0;
}
```

#### 例程说明：
（1）首先，程序提示用户从键盘输入一个字符。这时，标准输入文件指针stdin指向该字符。

（2）调用fscanf函数从标准输入文件中读取一个字符，并送至ch。这里应该注意两点：
1. fscanf函数的第一个参数不是用户定义的文件指针，而是系统定义的标准输入文件指针stdin。但用法与用户定义的文件指针类似。
2. &ch是指向字符型数据的指针，因此，输入的格式format也要为字符型"%c"，它们必须保持一致。

（3）该函数的使用与scanf类似。其实，scanf函数是fscanf函数的一个特例，它只能从标准输入文件（键盘终端）中输入数据。而fscanf函数则也可以从一般用户定义的文件中输入数据。
