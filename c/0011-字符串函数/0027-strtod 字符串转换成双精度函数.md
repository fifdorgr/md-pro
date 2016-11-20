函数原型：double strtod(char *str, char **endptr);
头文件：include<stdlib.h>
是否是标准函数：是
函数功能：将字符串转换非双精度值，也就是将字符串str转换为双精度值，其中进行转换字符串必须是双精度数的字符表示格式，如果字符串中有非法的非数字字符，则第二个参数将负责获取该非法字符，即字符串指针endptr用于进行错误检测，转换在此非法字符处停止进行。
返回值：返回转换后的双精度结果
例程如下： 应用strtod将字符串转换为双精度值。
```  
include <stdio.h>
include <string.h>
include <stdlib.h>
int main(void)
{
    char str[20], *endptr;
    double result;
    while(1)
    {
        printf("Input a float:");
        gets(str);
        result=strtod(str,&endptr);
        if(result==-1)
            printf("The number is %lf\n",str,result);
        else
            break;
    }
    getch();
    return 0;
}
```

#### 例程说明：
（1）首先，程序声明了一个用于转换的字符数组和一个用于进行错误检测的字符串指针，双精度result用于获取转换结果。

（2）程序通过循环不断接收从标准输入流中输入的字符串，并通过调用strtod将输入的字符串转换为双精度值，通过返回值获取转换结果，并通过第二个参数进行错误检测。循环的最后将转换结果打印出来。

（3）程序规定将字符串"-1"作为循环结束的标志，除非通过输入结束标志，否则循环条件总是成立的。

（4）如果输入一个正确的双精度字符串，程序会正确的转换并补齐尾数；如果输入整数，程序会自动将其转换成双精度数；如果小数点后面的位数过长，超过了双精度的范围，程序会采取截断的方式；如果输入期间出现了非法字符，程序停止转换并保留已转换的结果；如果第一个就是非法字符则返回零。

本例程的运行结果是：
```  
Input a float: 4.2
The number is 4.20000
Input a float: 79
The number is 79.00000
Input a float: 1.1111111111
The number is 1.111111
Input a float: 34.45abc
The number is 34.450000
Input a float:abc
The number is 0.000000
Input a float: -1
```

注意：本例程中，即便转换出现非法字符循环也不会停止，而只是通过第二个参数捕捉到了非法字符，可以编写程序对非法字符进行处理，本例中并没有这样做，循环只是以输入循环结束标志循环结束依据。
