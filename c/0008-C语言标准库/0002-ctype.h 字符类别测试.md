在头文件<ctype.h>中定义了一些测试字符的函数。在这些函数中，每个函数的参数都是整型int，而每个参数的值或者为EOF，或者为char类型的字符。<ctype.h>中定义的标准函数列表如下：
<ctype.h>中定义的函数
```  
函数定义, 函数功能简介
int isalnum(int c), 检查字符是否是字母或数字
int isalpha(int c), 检查字符是否是字母
int isascii(int c), 检查字符是否是ASCII码
int iscntrl(int c), 检查字符是否是控制字符
int isdigit(int c), 检查字符是否是数字字符
int isgraph(int c), 检查字符是否是可打印字符
int islower(int c), 检查字符是否是小写字母
int isprint(int c), 检查字符是否是可打印字符
int ispunct(int c), 检查字符是否是标点字符
int isspace(int c), 检查字符是否是空格符
int isupper(int c), 检查字符是否是大写字母
int isxdigit(int c), 检查字符是否是十六进制数字字符
int toupper(int c), 将小写字母转换为大写字母
int tolower(int c), 将大写字母转换为小写字母
```