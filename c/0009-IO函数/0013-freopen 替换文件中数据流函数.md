函数原型：FILE *freopen(char *filename, char *type, FILE *fp);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：关闭fp所指向的文件，并将该文件中的数据流替换到filename所指向的文件中去。该函数共三个参数：第一个参数filename是文件流将要替换到的文件名路径；第二个参数type是文件打开的方式，它与fopen中的文件打开方式类似；第三个参数fp是要被替换的文件指针。
返回值：返回一个指向新文件的指针，即指向filename文件的指针。若出错，则返回NULL。
例程如下 关闭一个终端，并将数据流替换至一个新文件中。
```  
include <stdio.h>
int main(void)
{
    FILE *Nfp;
   /* 替换标准输出文件上的数据流到新文件test.txt */
   if (Nfp=freopen("test.txt", "w", stdout)
       == NULL)
      fprintf(stderr, "error redirecting stdout\n");
   /* 标准输出文件上的数据流将会被替换到新文件中 */
   printf("This will go into a file.");

   /* 关闭标准输出文件 */
   fclose(stdout);
   /*关闭新生成的文件*/
   fclose(Nfp);
   return 0;
}
```

#### 例程说明：

（1）首先，程序以写的方式打开名为test.txt的文件，将标准输出文件上的数据流"This will go into a file."替换到新生成的文件test.txt中。freopen函数返回一个指向新文件的指针，即指向文件test.txt的指针，并将它存放到Nfp中。

（2）然后关闭标准输出文件，fclose(stdout)。

（3）最后关闭新生成的文件fclose(Nfp)。

（4）本程序的执行结果是在当前目录下生成一个文件test.txt，并将原终端的数据流"This will go into a file."重新写入test.txt文件中。
