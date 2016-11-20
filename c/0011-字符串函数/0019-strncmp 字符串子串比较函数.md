函数原型： int strncmp (char *str1,char * str2, int n);
头文件：include<string.h>
是否是标准函数：是
函数功能：比较两个字符串子串的大小，也就是把字符串str1的前n个字符组成的子串和字符串str2的前n个字符组成的子串进行比较，从首字符开始逐字符的进行比较，直到某个字符不相同或比较到第n个字符为止。
返回值：若字符串str1前n个字符组成的子串大于字符串str2前n个字符组成的子串返回结果大于零，若字符串str1前n个字符组成的子串小于字符串str2前n个字符组成的子串返回结果小于零，若字符串str1前n个字符组成的子串等于字符串str2前n个字符组成的子串返回结果等于零
例程如下： 应用strncmp比较字符串子串大小。
```  
include <string.h>
include <string.h>
int main(void)
{
    char *str1="Hello World";
    char *str2="Hello C Programme";
    int result;
    result=strncmp(str1,str2,5);
    if(!result)
        printf("%s is identical to %s in the first 5 words",str1,str2);
    else if(result<0)
        printf("%s is less than %s in the first 5 words",str1,str2);
    else
        printf("%s is great than %s in the first 5 words",str1,str2);
    printf("\n");
    result=strncmp(str1,str2,10);
     if(!result)
        printf("%s is identical to %s in the first 10 words",str1,str2);
    else if(result<0)
        printf("%s is less than %s in the first 10 words",str1,str2);
    else
        printf("%s is great than %s in the first 10 words",str1,str2);
    getch();
    return 0;
}
```

#### 例程说明：
（1）首先，程序声明了两个字符串变量并分别赋予了初值，整型变量result用于记录字符串子串的比较结果。

（2）程序通过调用strncmp函数比较字符串str1和字符串str2的前5个字符组成的子串，由于两个字符串的前五个字符相同，因此两个子串的比较结果应为相等，返回结果为零。然后将比较结果输出。

（3）程序第二次调用strncmp函数比较字符串str2和字符串str3的前10个字符组成的子串，由于从第七个字符开始出现不等的情况，分别为' w'和' C'，根据ASIC码表中小写字母在后，即' w'的ASIC码大，返回结果大于零。最后输出比较结果。

（4）输出时显示的输出比较结果并指明比较范围。
本例程的运行结果是：
```  
Hello World is identical to Hello C Programme in the first 5 words
Hello World is great than Hello C Programme in the first 10 words
```

注意：本例程中，要注意子串比较的过程中子串的大小应不小于零且不超过字符串的长度，虽然子串的长短参数不会产生编译时的错误和最终结果的输出，但在比较前检查比较范围是一个很好的习惯。
