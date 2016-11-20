函数原型：char *strcat (char *dest,char *src);
头文件：include<string.h>
是否是标准函数：是
函数功能：将两个字符串连接合并成一个字符串，也就是把字符串src连接到字符串dest后面，连接后的结果放在字符串dest中
返回值：指向字符串dest的指针
例程如下：
应用strcat连接字符串。
```  
include <string.h>
include <stdio.h>
int main( )
{
 	char dest[20]={“ ”};
    char *hello = "hello ", *space = " ", *world = "world";
 	strcat(dest, hello);
   	strcat(dest, space);
    strcat(dest, world);
   	printf("%s\n", destination);
    getch();
   	return 0;
}
```

#### 例程说明：

（1）首先，程序声明了一个字符数组和三个字符串变量，将字符数组dest初始化位空串，其余三个字符串变量分别赋予初值。

（2）程序通过调用strcat函数实现字符串的连接，首先将字符串hello添加到字符数组dest的末端，此时字符数组dest的值有空串变为"hello"，然后继续调用两次strcat函数，依次将字符串space和字符串world陆续连接到字符数组dest的末端，从而完成整个字符串的连接操作。

（3）最后将最终的结果输出。

本例程的运行结果是：
```  
hello world
```
注意：本例程中，开始对字符数组dest初始化位空是必要的，对声明的变量进行初始化是一个很好的习惯，如果不对字符数组dest进行初始化程序会产生运行时的错误，有兴趣的读者可以试试未初始化程序的输出结果。
