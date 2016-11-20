函数原型： int isxdigit(int c);
头文件：include<ctype.h>
是否是标准函数：是
函数功能：检查字符c是否为十六进制数字。
返回值：当c为A-F,a-f或0-9之间的十六进制数字时，返回非零值，否则返回0。
例程如下：应用isxdigit函数检查字符属性。
```  
include <stdio.h>
include <ctype.h>
int main(void)
{
     char c;
     c='f';
     printf("%c:%s\n",c,isxdigit(c)?"yes":"no");
     c='1';
     printf("%c:%s\n",c,isxdigit(c)?"yes":"no");
     c='$';
     printf("%c:%s\n",c,isxdigit(c)?"yes":"no");
     getchar();
     return 0;
}
```

#### 例程说明：

本例程应用isxdigit函数判断字符'f'、'1'、'$'是否是十六进制数字，如果是，显示"yes",不是则显示"no"。本例程的运行结果是：
```  
f:yes
1:yes
$:no
```
