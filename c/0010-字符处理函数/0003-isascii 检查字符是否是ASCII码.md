函数原型：int isascii(int c);
头文件：include<ctype.h>
是否是标准函数：是
函数功能：检查字符c 是否是ASCII码，所谓ASCII码是指0x00~0x7F之间的字符。
返回值：是ASCII码返回1，否则返回0。
例程如下：应用isascii检查字符属性。
```  
include <stdio.h>
include <ctype.h>
int main(void)
{
    int c;
    c='A';
    printf("%c:%s\n",c,isascii(c)?"yes":"no");
    c=0x7f;
    printf("%c:%s\n",c,isascii(c)?"yes":"no");
    c=0x80;
    printf("%c:%s\n",c,isascii(c)?"yes":"no");
    getchar();
    return 0;
}
```
#### 例程说明：

本例程应用isascii函数判断字符'A'、0x7f、0x80是否是ASCII码，如果是，显示"yes",不是则显示"no"。本例程的运行结果是：
```  
A:yes
?:yes
?:no
```
注意：所谓ASCII码是指0x00~0x7F之间的字符，本例程中十六进制数0x7f的字符显示为?，属于ASCII码，因此显示yes；0x80的字符显示为?，不属于ASCII码，因此显示no。
