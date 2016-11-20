函数原型：long strtol(char *str, char **endptr, int base);
头文件：include<stdlib.h>
是否是标准函数：是
函数功能：将字符串转换为长整型值，也就是将字符串str转换为长整型值，其中进行转换字符串必须是长整型的字符表示格式，如果字符串中有非法的非数字字符，则第二个参数将负责获取该非法字符，即字符串指针endptr用于进行错误检测，转换在此非法字符处停止进行。
返回值：返回转换后的长整型结果
例程如下： 应用strtol将字符串转换为长整型值。
```  
include <stdio.h>
include <string.h>
include <stdlib.h>
int main(void)
{
    char str[20], *endptr;
    long result;
    while(1)
    {
        printf("Input a long:");
        gets(str);
        result=strtod(str,&endptr);
        if(result!=-1)
            printf("The number is %ld\n",result);
        else
            break;
    }
    getch();
    return 0;
}
```

#### 例程说明：

（1）首先，程序声明了一个用于转换的字符数组和一个用于进行错误检测的字符串指针，长整型result用于获取转换结果。

（2）程序通过循环不断接收从标准输入流中输入的字符串，并通过调用strtol将输入的字符串转换为长整型值，通过返回值获取转换结果，并通过第二个参数进行错误检测。循环的最后将转换结果打印出来。

（3）程序规定将字符串"-1"作为循环结束的标志，除非通过输入结束标志，否则循环条件总是成立的。

（4）如果输入一个正确的长整型字符串，程序会正确转换；如果输入小数，程序会将小数点后面的截断；如果转换的数过大，超过了长整型范围，程序返回长整型所能接受的最大值；如果输入期间出现了非法字符，程序停止转换并保留已转换的结果；如果第一个就是非法字符则返回零。

本例程的运行结果是：
```  
Input a long: -15
The number is -15
Input a long: 1234.5678
The number is 1234
Input a long: 333333333333
The number is 2147483647
Input a long: -34abc
The number is -34
Input a long: abc
The number is 0
Input a float: -1
```

注意：本例程中，将字符串中的小数转换为长整型时，程序会将小数点看作非法字符，从而停止转换继续进行，因此无论小数点后面的数是多少都会截断，而不是我们习惯上的四舍五入或者五舍六入。
