函数原型：char *strrchr(char *str, char c);
头文件：include<string.h>
是否是标准函数：是
函数功能：在字符串中查找给定字符的最后一次匹配，也就是在字符串str中查找字符c最后一次出现的位置
返回值：最后一次匹配位置的指针
例程如下： 应用strrchr匹配字符串中字符。
```  
include <stdio.h>
include <string.h>
int main(void)
{
    char str[15]={""};
    char *ptr, c = 'o';
    strcpy(str, "Hello World");
    ptr = strchr(str, c);
    if (ptr)
       printf("The first character %c is at position: %d\n", c, ptr-str);
    else
       printf("The character was not found\n");
    ptr = strrchr(str, c);
    if (ptr)
       printf("The last character %c is at position: %d\n", c, ptr-str);
    else
       printf("The character was not found\n");
    getch();
    return 0;
}
```

#### 例程说明：

（1）首先，程序声明了一个字符串和一个字符数组以及一个字符，并对字符变量赋予了我们要查找的值。

（2）程序通过调用strcpy 赋予了字符数组一个值，然后调用strchr函数在字符数组中查找第一次与字符变量c匹配的字符，也就是查找最后一个'o' 字符，返回的结果为指向第一个匹配字符的指针。根据返回值输出匹配结果。

（3）然后程序调用strrchr函数在字符数组中查找最后一次与字符变量c匹配的字符，也就是查找最后一个'o' 字符，最后根据返回值输出匹配结果。

（4）在字符数组中有两个'o'字符，因此调用strchr函数应该返回第一个'o'字符的指针，调用strrchr函数应该返回最后一个'o'字符的指针。

（5）对结果进行输出时，如果匹配成功，那么我们输出匹配的字符在数组中的位置，如果匹配不成功，则显示没有找到。

本例程的运行结果是：
```  
The first character r is at position 4
The last character r is at position 7
```

注意：本例程中，如果字符串中只有一个'o'字符，那么无论调用哪种字符串中字符匹配函数都会返回相同的结果。
