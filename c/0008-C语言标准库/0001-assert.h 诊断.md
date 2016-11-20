<assert.h>中只定义了一个带参的宏assert，其定义形式如下：
```  
void assert (int 表达式)
```
assert宏用于为程序增加诊断功能，它可以测试一个条件并可能使程序终止。
在执行语句：
```  
assert(表达式);
```
时，如果表达式为0，则在终端显示一条信息：
```  
Assertion failed: 0, file 源文件名, line 行号
Abnormal program termination
```
然后调用abort终止程序的执行。
在<assert.h>中，带参宏assert是被定义为条件编译的，如果在源文件中定义了宏NDEBUG，则即使包含了头文件<assert.h>，assert宏也将被忽略。
