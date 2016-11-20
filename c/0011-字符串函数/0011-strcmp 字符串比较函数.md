函数原型：int strcmp (char *str1,char * str2);
头文件：include<string.h>
是否是标准函数：是
函数功能：比较两个字符串的大小，也就是把字符串str1和字符串str2从首字符开始逐字符的进行比较，直到某个字符不相同或比较到最后一个字符为止，字符的比较为ASIC码的比较
返回值：若字符串str1大于字符串str2返回结果大于零，若字符串str1小于字符串str2返回结果小于零，若字符串str1等于字符串str2返回结果等于零
例程如下： 应用strcmp比较字符串大小。
```  
include <string.h>
include <stdio.h>
int main(void)
{
    char *str1 = "Canada", *str2 = "China", *str3 = "china";
    int result;
    result = strcmp(str1, str2);
    if (result < 0)
        printf("%s is less than %s", str1,str2);
    else
        printf("%s is not less than %s", str1,str2);
    printf("\n");
    result = strcmp(str2, str3);
    if (result < 0)
        printf("%s is less than %s", str2,str3);
    else
        printf("%s is not less than %s", str2,str3);
    getch();
    return 0;
}
```

#### 例程说明：

（1）首先，程序声明了三个字符串变量并分别赋予了初值，注意字符串str2和字符串str3的区别在于首字母是否大写，整型变量result用于记录字符串的比较结果。

（2）程序通过调用strcmp函数比较字符串str1和字符串str2，在首字符相同的情况下第二个字符' a'的ASIC码小于' h'的ASIC码，因此比较结果为字符串str1小于字符串str2，返回结果小于零。第二次调用strcmp函数比较字符串str2和字符串str3，由于在ASIC码表中小写字母在后，小写字母的ASIC码大于大写字母，即' C'小于' c'，因此比较结果为字符串str2小于字符串str3，返回结果小于零。

（3）最后将最终的结果输出，为了使输出结果一目了然，在两次比较中间的printf函数输出了一个换行。
本例程的运行结果是：
```  
Canada is less than China
China is less than china
```

注意：本例程中，字符串的比较结果为首个两个不等字符之间ASIC码的差值，如果我们将第一次比较的结果result输出，应该是' a'的ASIC与码与' h'的ASIC码的差值，有兴趣的读者可以试试输出结果。
