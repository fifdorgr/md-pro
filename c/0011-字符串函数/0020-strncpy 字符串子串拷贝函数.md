函数原型： char * strncpy (char *dest,char * src, int n);
头文件：include<string.h>
是否是标准函数：是
函数功能：实现字符串子串的拷贝工作，也就是把字符串src中的前n个字符拷贝到字符串dest中。
返回值：指向字符串dest的指针
例程如下： 应用strncpy实现字符串子串拷贝。
```  
include <stdio.h>
include <string.h>
int main(void)
{
    char dest[20]={""};
    char *src1="Hello World",*src2 ="Aloha";
    strncpy(dest,src1,5);
    strncpy(dest,src2,5);
    if(!strcmp(dest,src1))
        printf("dest is equal to src1");
    else if(!strcmp(dest,src2))
        printf("dest is equal to src2");
    else
        printf("dest is %s",dest);
    printf("%s\n", dest);
    getch();
    return 0;
}
```

#### 例程说明：

（1）首先，程序声明了两个字符串和一个字符数组并分别赋予了初值，本例中省去了用于记录比较结果result变量。

（2）程序通过调用strncpy函数将字符串src1中的前五个字符组成的子串拷贝到字符数组dest中，然后又将调用strncpy函数将字符串src2中的前五个字符组成的子串拷贝到字符数组dest中。通过调用一系列的strcmp字符串比较函数，从而达到验证dest变量中的最终内容的目的。

（3）最终的字符串dest中内容的到底是什么呢，是"Hello"，还是"Aloha"，亦或是" HelloAloha"。通过第一次调用strncpy函数，字符串dest中的内容由空串变成"Hello"，再次调用strncpy函数则会从字符串dest的下标为零处逐一覆盖，也就是"Aloha"覆盖了原来的" Hello "，并不是将"Aloha"添加到末端。

（4）最后将拷贝结果和验证结果输出。

本例程的运行结果是：
```  
Aloha
dest is equal to src2
```

注意：本例程中，在检验字符串dest的内容时，if判断中并没有使用像上例中的result变量，我们只关心比较的结果是否为零，直接通过将函数作为判断条件，从而利用函数的返回值进行判断是一个简单而有效的方法。
