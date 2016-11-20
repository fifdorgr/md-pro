函数原型：int fgetpos( FILE *stream, fpos_t *pos );
头文件：include<stdio.h>
是否是标准函数：是
函数功能：取得当前文件的指针所指的位置，并把该指针所指的位置数存放到pos所指的对象中。pos值以内部格式存储,仅由fgetpos和fsetpos使用。其中fsetpos的功能与fgetpos相反，为了详细介绍，将在后节给与说明。
返回值：成功返回0，失败返回非0，并设置errno。
例程如下：应用fgetpos函数取得当前文件的指针所指的位置。
```  
include <string.h>
include <stdio.h>
int main(void)
{
   FILE *fp;
   char string[] = "This is a test";
   fpos_t pos;
   /* 以读写方式打开一个名为test.txt的文件 */
   fp = fopen("test.txt", "w+");
   /* 将字符串写入文件 */
   fwrite(string, strlen(string), 1, fp);
   /* 取得指针位置并存入&pos所指向的对象 */
   fgetpos(fp, &pos);
   printf("The file pointer is at byte %ld\n", pos);
    /*重设文件指针的位置*/
   fseek(fp,3,0);
    /* 再次取得指针位置并存入&pos所指向的对象 */
   fgetpos(fp, &pos);
   printf("The file pointer is at byte %ld\n", pos);
   fclose(fp);
   return 0;
}
```

例程说明：

（1）首先，程序以读写方式打开一个名为test.txt的文件，并把字符串"This is a test"写入文件。注意：字符串共14个字节，地址为0~13。用fwrite函数写入后，文件指针自动指向文件最后一个字节的下一个位置。即这时的fp的值应该是14。

（2）再用fgetpos函数取得指针位置并存入&pos所指向的对象，此时， pos中的内容为14。然后在屏幕上显示出The file pointer is at byte 14。

（3）再用fseek函数重设文件指针的位置，让fp的值为3，即指向文件中第4个字节。
再次取得指针位置并存入&pos所指向的对象。然后在屏幕上显示出The file pointer is at byte 3。
