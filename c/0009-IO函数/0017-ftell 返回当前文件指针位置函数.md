函数原型：long ftell(FILE *fp);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：返回当前文件指针的位置。这个位置是指当前文件指针相对于文件开头的位移量。
返回值：返回文件指针的位置，若出错则返回–1L。
例程如下 应用ftell返回文件指针位置。
```  
include <stdio.h>
int main(void)
{
   FILE *fp;
   fp = fopen("test.txt", "w+");
   /*按照格式要求将字符串写入文件*/
   fprintf(fp, "This is a test");
   /*读出文件指针fp的位置*/
   printf("The file pointer is at byte %ld\n", ftell(fp));
   fclose(fp);
   return 0;
}
```

#### 例程说明：

（1）首先以写方式打开名为test.txt的文件，按照格式要求将字符串写入文件。注意：字符串共14个字符，地址为0~13。调用fprintf函数后，文件指针自动移到读入的最后一个字符的下一个位置，本例中就是文件的结束符，它的地址是14。

（2）应用ftell函数读出文件指针fp的位置。
注意：本题中ftell函数的返回值实际上就是该文件的长度。在实际的应用中，函数ftell常用来计算文件的长度。
