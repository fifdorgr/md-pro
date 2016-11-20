函数原型：int strcspn(char *str1, char *str2);
头文件：include<string.h>
是否是标准函数：是
函数功能：在字符串中查找第一个属于字符集的下标，即从开始有多少个字符不属于字符集，也就是在字符串str1中查找第一个属于字符集str2中任何一个字符的下标，即字符串str1中从开始一直有多少个字符不属于字符集str2中的字符。
返回值：所找到的字符串中段的长度
例程如下： 应用strspn逆匹配字符串中字符集。
```  
include <string.h>
include <stdio.h>
int main(void)
{
    char *str1="tomato",*str2="carrot";
    char *str= "abc";
    int  result;
    result = strcspn(str1,str);
    if(result)
        printf("The first %d is congruent\n",result);
    else
        printf("No character is congruent\n");
    result = strcspn(str2,str);
    if(result)
        printf("The first %d is congruent\n",result);
    else
        printf("No character is congruent\n");
    getch();
    return 0;
}
```

#### 例程说明：

（1）首先，程序声明了三个字符串并分别赋予初值，其中最后一个变量是用于逆匹配的字符集。

（2）程序通过调用strcspn进行字符集的逆匹配，它从字符串str1中的第一个字符开始检查是不是属于字符串str中的任意字符，如果不属于就继续逆匹配，直到逆匹配不成功，本例中会发现直到遇到字符'a'才逆匹配失败，因为字符'a'属于字符串str中的某个字符。然后输出匹配结果。

（3）程序第二次通过调用strspn对字符串str2进行字符集逆匹配，发现第一个字符即属于字符集str中的某字符。

（4）输出匹配结果是显示前多少个字符逆匹配成功。

本例程的运行结果是：
```  
The first 3 is congruent
No character is congruent
```

注意：本例程中，字符集逆匹配与字符集匹配两者的匹配方式截然相反，字符串匹配是当字符串中字符等于字符集中任意字符是匹配成功，字符串逆匹配是当字符串中字符不等于字符集中任意字符是匹配成功。
