函数原型：char *strstr(char *str1, char *str2);
头文件：include<string.h>
是否是标准函数：是
函数功能：在字符串中查找另一个字符串首次出现的位置，也就是在字符串str1中查找第一次出现字符串str2的位置。
返回值：返回第一次匹配字符串的指针
例程如下： 应用strstr匹配字符串。
```  
include <stdio.h>
include <string.h>
int main(void)
{
    char *str1 = "Borland International",*str2 = "nation";
    char *result;
    result=strstr(str1, str2);
    if(result)
        printf("The substring is: %s\n", ptr);
    else
        printf("Not found the substring");
    getch();
    return 0;
}
```

#### 例程说明：
（1）首先，程序声明了三个字符串变量并给前两个变量赋予初值，其中字符指针result用于记录匹配字符串的位置。

（2）程序通过调用strstr进行字符串匹配，查找字符串str1中首次出现字符串str2的位置，返回匹配结果。

（3）输出匹配结果时以匹配字符串的首字符作为子串的第一个字符输出，如果匹配不成功显示没有找到。

本例程的运行结果是：
```  
The substring is national
```

注意：本例程中，匹配成功时的返回结果并不是进行匹配的字符串，而是第一次匹配成功的字符串首字符的指针。
