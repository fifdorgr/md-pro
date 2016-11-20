函数原型：char *strpbrk(char *str1, char *str2);
头文件：include<string.h>
是否是标准函数：是
函数功能：在字符串中查找第一个属于字符集的字符位置，也就是在字符串str1中查找第一个属于字符集str2中任意字符的位置。
返回值：返回第一个匹配字符的指针
例程如下： 应用strpbrk匹配字符集字符。
```  
include <stdio.h>
include <string.h>
int main(void)
{
    char *str1="There are 5 pigs in the hogpen";
    char *str2="0123456789";
    char *result;
    result = strpbrk(str1,str2);
    if(result)
        printf("%s\n",result++);
    else
        printf("There are no numbers any more");
    result = strpbrk(result,str2);
    if(result)
        printf("%s\n",result++);
    else
        printf("There are no numbers any more");
    getch();
    return 0;
}
```

#### 例程说明：

（1）首先，程序声明了三个字符串变量并给前两个变量赋予初值，其中字符指针result用于记录匹配字符的位置。

（2）程序通过调用strcspn进行字符集字符的匹配，它从字符串str1中查找第一个属于字符集str2中任意字符的字符，具体到本例中就是在字符串str1种查找第一个数字字符，如果匹配成功我们会获得指向第一个数字字符的指针，利用该返回值输出匹配结果。

（3）然后我们在上一次匹配字符的下一个字符作为首字符的子串中继续匹配，程序第二次通过调用strspn完成上述功能，并用同样的输出方式输出匹配结果，如没有数字字符可以获得显示匹配失败。

（4）输出匹配结果时我们并没有将匹配的字符输出，取而代之的是将以匹配字符作为第一个字符的字符串字串输出。

本例程的运行结果是：
```  
5 pigs in the hogpen
There are no numbers any more
```

注意：本例程中，值得注意的是匹配成功时结果的输出。由于获得了匹配成功的字符的指针，因此我们可以利用该指针输出字符串的字串，利用自增操作符我们移动一个位置又可以对尚未匹配的子串继续进行下一次匹配。
