函数原型：FILE *tmpfile(void);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：创建一个临时文件。该文件以w+b（二进制读写）方式打开，当该文件被关闭时，该文件会被自动删除。
返回值：返回指向临时文件的指针，如果文件打不开则返回EOF。
例程如下 创建一个临时文件。
```  
include <stdio.h>
include <process.h>
int main(void)
{
   FILE *tempfp;
   tempfp = tmpfile();
   if (tempfp)
      printf("Temporary file be created!!\n");
   else
   {
      printf("Unable to create the temporary file!!\n");
      exit(1);
   }
    sleep(20);
   return 0;
}
```

#### 例程说明：
（1）首先应用tmpfile函数创建一个临时文件，并将文件指针赋值给FILE型变量tempfp。

（2）如果创建临时文件成功，则在终端显示提示：Temporary file be created!!

（3）如果创建不成功，则显示提示：Unable to create the temporary file!!

（4）程序挂起20秒。

注意：这里将程序挂起20秒的目的是为了让用户看到生成的临时文件。这是因为当程序执行完时，系统会自动删除临时文件，那样用户就感觉不到临时文件的创建了。当该程序运行时，会在当前文件夹下生成一个临时文件。
临时文件的作用是暂时存储程序运行过程中需要的数据，当程序运行完毕时，这些数据也就没有用了。
