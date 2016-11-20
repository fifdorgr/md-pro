函数原型：int isprint(int c);
头文件：include<ctype.h>
是否是标准函数：是
函数功能：检查字符c是否为可打印字符（含空格），其ASCII码在0x20-0x7e之间。
返回值：是可打印字符返回1，否则返回0。
例程如下：应用isprint函数判断可打印字符。
```  
include <stdio.h>
include <ctype.h>
int main(void)
{
    int c;
    c='A';
    printf("%c:%s\n",c,isprint(c)?"yes":"no");
    c=' ';
    printf("%c:%s\n",c,isprint(c)?"yes":"no");
    c=0x7f;
    printf("%c:%s\n",c,isprint(c)?"yes":"no");
    getchar();
    return 0;
}
```

#### 例程说明：

本例程与例程11-6相似，应用isprint函数判断字符'A'、' '、0x7f是否是可打印字符（包括空格）。如果是，显示"yes",不是则显示"no"。本例程的运行结果是：
```  
A:yes
 :yes
?:no
```
