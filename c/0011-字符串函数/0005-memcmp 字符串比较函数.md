函数原型：void *memcmp(char *s1, char *s2, unsigned n)
头文件：include<string.h>
是否是标准函数：是
函数功能：比较s1所指向的字符串与s2所指向的字符串的前n个字符。
返回值：根据s1所指向的对象的大于、等于、小于s2所指向的对象，函数memcmp分别返回大于、等于、小于0的值。
例程如下：比较两个字符串。
```  
include <stdio.h>
include <string.h>
int main(void)
{
    char *str1="ABCDEF";
    char *str2="ABCDEf";
    int s1,s2;
    s1=memcmp(str1,str2,6);
    s2=memcmp(str1,str2,5);
    printf("The comparison of 6 character\n");
    if(s1>0)printf("%s>%s\n",str1,str2);
    else
        if(s1<0)printf("%s<%s\n",str1,str2);
    else
         printf("%s=%s\n",str1,str2);
    printf("The comparison of 5 character\n");
    if(s2>0)printf("%s>%s\n",str1,str2);
    else
        if(s2<0)printf("%s<%s\n",str1,str2);
    else
         printf("%s=%s\n",str1,str2);
}
```

#### 例程说明：

（1）首先初始化两个字符串“ABCDEF”和“ABCDEf”。

（2）然后应用函数memcmp将这两个字符串按照不同的字符个数进行比较，将返回的比较结果复制给变量s1和s2。

（3）显示比较结果。

本例程的运行结果为：
```  
The comparison of 6 character
ABCDEF<ABCDEf
The comparison of 5 character
ABCDEF=ABCDEf
```
注意：
由于字符串比较的方法是从左至右按照字符的ASCII码进行比较的，因此在比较6个字符时，字符串“ABCDEF”<“ABCDEf”（f的ASCII值大于F的ASCII值）；而只比较5个字符时，字符串“ABCDEF”=“ABCDEf”。
