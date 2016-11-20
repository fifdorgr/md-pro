函数原型：char *strncat (char *dest, char *src, int n);
头文件：include<string.h>
是否是标准函数：是
函数功能：将一个字符串的子串连接到另一个字符串末端，也就是把字符串src的前n个字符连接到字符串dest后面，连接后的结果放在字符串dest中
返回值：指向字符串dest的指针
例程如下：应用strncat连接字符串子串。
```  
include <string.h>
include <string.h>
include <stdio.h>
int main(void)
{
    char dest[30]={""};
    char *favorite = "I love", *tabs = "\t\n", *language = "C++";
    strcnat(dest, favorite,6);
    strncat(dest, tabs,1);
    strncat(dest, language,1);
    printf("%s\n", dest);
    getch();
    return 0;
}
```

#### 例程说明：

（1）首先，程序声明了一个字符数组和三个字符串变量，将字符数组dest初始化位空串，其余三个字符串变量分别赋予初值，其中字符串tans由两个字符组成，一个制表符和一个换行符。

（2）程序通过调用strncat函数实现字符串子串的连接，首先将字符串favorite的前六个字符添加到字符数组dest的末端，其效果与直接调用strcat函数相同，然后继续调用两次strncat函数，依次将字符串tabs和字符串language的首字符陆续连接到字符数组dest的末端，从而完成整个字符串子串的连接操作。

（3）最后将最终的结果输出，由于未将字符串tabs中的换行符添加到字符数组dest中，因此所有输出结果应在同一行。

本例程的运行结果是：
```  
I love	C
```
注意：本例程中，字符串tabs中的内容比较新奇，它并不是我们一般的字符，而是两个转义说明符构成的特殊字符，C语言内部在处理过程中遇到转义说明符时会作特殊处理，本例中会将' \t'看做制表符，将' \n'看做换行符。
