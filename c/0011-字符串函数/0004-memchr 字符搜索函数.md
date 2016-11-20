函数原型：void *memchr(void *s, char ch, unsigned n)
头文件：include<string.h>
是否是标准函数：是
函数功能：在数组的前n个字节中搜索字符 ch。
返回值：返回一个指针，它指向ch在s 中第一次出现的位置。如果在s的前n个字符中找不到匹配，返回NULL。
例程12.31应用函数memchr搜索一个字符串的子串。
```  
include <string.h>
include <stdio.h>
int main(void)
{
   char *str="I love China\n";
   char *p;
   p=memchr(str,'C',strlen(str));
   if(p)
         printf("%s",p);
   else
        printf("The character was not found\n") ;
}
```

#### 例程说明：

（1）首先初始化字符串“I love China\n”，将首地址赋值给str。

（2）在字符串str中查找字符’C’出现的位置，并返回以第一个字符’C’开头的字符子串的指针。

（3）如果返回值不为NULL，打印该子串。
本例程的运行结果为：
```  
China
```
