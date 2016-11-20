函数原型：char *strset(char *str, char c);
头文件：include<string.h>
是否是标准函数：否
函数功能：将字符串原有字符全部设定为指定字符，也就是将字符串str中的所有字符全部用字符c进行替换.
返回值：返回指向被替换字符串的指针
例程如下： 应用strset将字符串设定为指定字符。
```  
include <stdio.h>
include <string.h>
int main(void)
{
   char str[11]="0123456789";
   char symbol='a';
   printf("Before: %s\n",str);
   strset(str,symbol);
   printf("After: %s\n",str);
   getch();
   return 0;
}
```
#### 例程说明：

（1）首先，程序声明了一个字符数组和一个字符变量并赋予初值，字符变量代表用于替换的字符。

（2）程序通过调用strset将原字符串中的所有内容用字符'a'替换，相当于覆盖了原值并重新设定了字符串的值。

（3）最后将设定前后字符串的值打印出来。

本例程的运行结果是：
```  
0123456789
aaaaaaaaaa
```

注意：本例程中，字符数组中指存储了十个字符，但是下表确是十一，利用字符串的相关知识可以理解该问题，有兴趣的读者可以将下表改成十或在字符串赋值的时候多加一个字符，看看程序会输出什么。
