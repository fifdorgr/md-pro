函数原型：char *strchr(char *str, char c);
头文件：include<string.h>
是否是标准函数：是
函数功能：在字符串中查找给定字符的第一次匹配，也就是在字符串str中查找字符c第一次出现的位置
返回值：第一次匹配位置的指针
例程如下： 应用strchr匹配字符串中字符。
```  
include <stdio.h>
include <string.h>
int main(void)
{
    char str[15] ={""};
    char *ptr, c = 'r';
    strcpy(str, "Hello World");
    ptr = strchr(str, c);
    if (ptr)
       printf("The character %c is at position: %d\n", c, ptr-str);
    else
       printf("The character was not found\n");
    strcpy(str, "Aloha");
    if (ptr)
       printf("The character %c is at position: %d\n", c, ptr-str);
    else
       printf("The character was not found\n");
    getch();
    return 0;
}
```

#### 例程说明：

（1）首先，程序声明了一个字符串和一个字符数组以及一个字符，并对字符变量赋予了我们要查找的值。

（2）程序通过调用strcpy 赋予了字符数组一个值，然后调用strchr函数在字符数组中查找第一次与字符变量c匹配的字符，也就是查找第一个'r' 字符，返回的结果为指向第一个匹配字符的指针。根据返回值输出匹配结果。

（3）程序第二次通过调用strcpy 赋予了字符数组一个值，然后调用strchr函数在字符数组中查找第一次与字符变量c匹配的字符，也就是查找第一个'r' 字符，最后根据返回值输出匹配结果。

（4）第二次匹配已经给字符串重新赋值，我们理解新的字符串似乎应该是"Aloha"，从而没有与'r'匹配的字符，但实际的运行结果却令人大吃一惊。这时因为在重新赋值时"Aloha"虽然将"Hello"覆盖掉，但是后面的字符仍然在数组中保留，因此在做匹配的时候仍然得到与第一次匹配相同的结果。

（5）对结果进行输出时，如果匹配成功，那么我们输出匹配的字符在数组中的位置，如果匹配不成功，则显示没有找到。

本例程的运行结果是：
```  
The character r is at position 8
The character r is at position 8
```
注意：本例程中，对字符串中字符匹配的返回值是指向匹配位置的指针，我们获取到该指针后，与数组的头指针做减法，也就是与数组变量名做减法，就可以获得我们得到的指针在数组中对应的下标。
