可变参数表<stdarg.h>中的宏是用来定义参数可变的函数的。在C语言中，有些库函数或者用户自定义的函数的参数是可变的，常用省略号“……”（例如库函数中的printf），定义这样的函数就要使用到<stdarg.h>中的宏。

#### 1、va_list

用于保存宏va_start，va_arg以及va_end所需信息的数据类型。

#### 2、<stdarg.h>中还定义了三个宏
```  
void va_start(va_list ap, parmN);
type va_arg(va_list ap,type);
void va_end (va_list ap);
```
va_start的作用是初始化ap，因此va_start要在所有其它的va_开头的宏前面最先使用(除了用va_list定义变量外)，后面的va_copy, va_arg, va_end都要使用到ap。在一对va_start和va_end之间不能再次使用va_start宏。其中，parmN为"..."之前的最后一个参数。例如,printf函数定义为：printf(const char *format, ...); 那么在printf函数中的va_start使用之后, parmN 的值就等于*format。
va_arg的作用就是返回参数列表ap中的下一个具有type类型的参数,每次调用va_arg都会修改ap的值,这样才能连续不断地获取下一个type类型的参数。
va_end与va_start构成了一个scope，va_end标志着结束，va_end之后ap就无效了。
