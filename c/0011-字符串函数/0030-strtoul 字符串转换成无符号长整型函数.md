函数原型：unsigned long strtoul(char *str, char **endptr, int base);
头文件：include<stdlib.h>
是否是标准函数：是
函数功能：将字符串转换为无符号长整型值，也就是将字符串str转换为无符号长整型值，其中进行转换字符串必须是无符号长整型的字符表示格式，如果字符串中有非法的非数字字符，则第二个参数将负责获取该非法字符，即字符串指针endptr用于进行错误检测，转换在此非法字符处停止进行。
返回值：返回转换后的无符号长整型结果
例程如下： 应用strtoul将字符串转换为无符号长整型值。
```  
include <stdio.h>
include <string.h>
include <stdlib.h>
int main(void)
{
    char str[20], *endptr;
    unsigned long result;
    while(1)
    {
        printf("Input an unsigned long:");
        gets(str);
        result=strtoud(str,&endptr);
        if(result!=-1)
            printf("The number is %lu\n",result);
        else
            break;
    }
    getch();
    return 0;
}
```

#### 例程说明：
（1）首先，程序声明了一个用于转换的字符数组和一个用于进行错误检测的字符串指针，无符号长整型result用于获取转换结果。

（2）程序通过循环不断接收从标准输入流中输入的字符串，并通过调用strtoul将输入的字符串转换为无符号长整型值，通过返回值获取转换结果，并通过第二个参数进行错误检测。循环的最后将转换结果打印出来。

（3）程序规定将字符串"1"作为循环结束的标志，除非通过输入结束标志，否则循环条件总是成立的。

（4）如果输入一个正确的长整型字符串，程序会正确转换；如果输入一个负数，程序返回零。

本例程的运行结果是：
```  
Input a long: 100
The number is 100
Input a long: -36
The number is 0
Input a float: 1
```
注意：本例程中，输入负数的时候程序会将负号看作非法字符，从而停止转换继续进行，没有发生任何实际的转换。
