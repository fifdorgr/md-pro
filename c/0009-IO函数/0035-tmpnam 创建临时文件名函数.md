函数原型：char *tmpnam(char *string);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：创建一个临时文件名，用以打开一个临时文件。
返回值：创建成功返回指向该文件名的指针，否则返回NULL。
例程如下
```  
include <string.h>
include <stdio.h>
main()
{
    char tmp[10];
    tmpnam(tmp);
    printf("The temporary name is %s\n",name);
}
```

#### 例程说明：

（1）首先定义一个字符型数组tmp。

（2）调用tmpnam函数生成一个临时文件名。

（3）打印出该临时文件名。

注意：应用函数tmpnam生成的临时文件名是不同于任何已存在文件名的有效文件名。本函数用于给临时文件创建文件名。
