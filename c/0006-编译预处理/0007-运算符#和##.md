在ANSI C中，有两个仅用于宏替换的运算符：和。
在带参数的宏替换中，如果有带的形参，那么在宏扩展时实参应替换该与形参，且将实参加上双引号，变为实际的字符串变量，即形参被“实参”代替。如包含下列宏定义的源程序：
```  
define STRING(i) i
…
printf(STRING(example\n));
```
将被替换为：
```  
printf("example\n");
```
即形参i被实参example\n加上双引号变为“example\n”替换。
而当另一个宏替换的运算持号出现在宏替换中时，它起的作用是：被删除，它连接的前后两个词法单位会合而为一，如果附近有空格，也将会披消除，这种方式通常用来构造标识符。如：
```  
define LINKSTRING(str1,str2) str1str2
```
则LINKSTRING(file,name)将在宏替换时变成filename。