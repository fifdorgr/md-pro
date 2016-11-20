函数原型：int fwrite(void *buf, int size, int count, FILE *fp);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：将buf所指向的count*size个字节的数据输出到文件指针fp所指向的文件中去。该函数与fread相对，输出数据后，文件指针fp自动指向输出的最后一个字符的下一个位置。该函数常用于分批将数据块输出到文件中。
返回值：返回实际写入文件数据项个数。
例程如下 应用fwrite函数向文件中写入数据块。
```  
include <stdio.h>
struct exp_struct
{
  int i;
  char ch;
};
int main(void)
{
   FILE *fp;
   struct exp_struct s;
    /*以写的方式打开名为test.txt的文件*/
   if ((fp = fopen("test.txt","wb")) == NULL)
   {
      fprintf(stderr, "Cannot open the test.txt");
      return 1;
   }
   /*向结构体中的成员赋值*/
   s.i = 0;
   s.ch = 'A';
    /* 将一个结构体数据块写入文件 */
   fwrite(&s, sizeof(s), 1, fp);
   fclose(fp);
   return 0;
}
```

#### 例程说明：
（1）程序先声明一个结构体类型struct exp_struct，这样一个结构体变量就是一个小数据块。

（2）再以写的方式打开名为test.txt的文件。

（3）然后向结构体中的成员变量赋值，并将赋值好的数据块应用fwrite函数写入fp 所指向的文件中。这里参数sizeof(s)是该结构体变量的大小，1指只写入文件1个数据块。

（4）最后关闭该文件。
