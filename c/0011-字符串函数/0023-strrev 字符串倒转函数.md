函数原型：char *strrev(char *str);
头文件：include<string.h>
是否是标准函数：否
函数功能：将字符串进行倒转，也就是将字符串str中的第一个字符与最后一个字符交换，第二个字符与倒数第二个字符交换，以此类推。
返回值：返回倒转后字符串的指针
例程如下： 应用strrev将字符串倒转。
```  
include <stdio.h>
include <string.h>
int main(void)
{
    char *str = "Able was I ere I saw Elba";
    printf("Before: %s\n",str);
    strrev(str);
    printf("After: %s\n",str);
    getch();
    return 0;
}
```

#### 例程说明：
（1）首先，程序声明了一个字符数组并赋予初值，应该注意到字符数组的初值很有意思，类似于回文。

（2）程序通过调用strrev将原字符串中的所有内容倒转，第一个字符与最后一个字符交换，第二个字符与倒数第二个字符交换，以此类推。

（3）最后将倒转前后字符串的值打印出来。

本例程的运行结果是：
```  
Able was I ere I saw Elba
ablE was I ere I saw elbA
```

注意：本例程中，字符数组中的初值并不是严格意义上的回文，将它倒转后会发现与原字符串并不是完全一样。
