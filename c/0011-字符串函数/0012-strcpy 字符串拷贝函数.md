函数原型： char * strcpy (char *dest,char * src);
头文件：include<string.h>
是否是标准函数：是
函数功能：实现字符串的拷贝工作，也就是把字符串src中的内容拷贝到字符串dest中，使两个字符串的内容相同。
返回值：指向字符串dest的指针
例程如下： 应用strcpy实现字符串拷贝。
```  
include <stdio.h>
include <string.h>
int main(void)
{
    char dest[20] ={""};
    char *src = "Hello World";
    int result;
    strcpy(dest,src);
    printf("%s\n", dest);
    result=strcmp(dest,src);
    if(!result)
        printf("dest is equal to src");
     else
        printf("dest is not equal to src");
    getch();
    return 0;
}
```

#### 例程说明：

（1）首先，程序声明了一个字符串和一个字符数组并给分别赋予了初值，整型变量result用于记录字符串子串的比较结果。

（2）程序通过调用strcpy函数将字符串src中的内容拷贝到字符数组dest中，使得两者具有相同的内容。为了验证两个变量中的内容是否真的一样，通过调用strcmp对两个字符串中的内容进行比较。

（3）最后将拷贝结果和比较结果输出。

本例程的运行结果是：
```  
Hello World
dest is equal to src
```

注意：本例程中，向字符数组中赋值时要保证字符数组中有足够的空间，虽然有时候即便空间不够也会打印出正确的结果，但随着程序的运行，不能保证超出下标范围的部分还能以正确的型式存在。
