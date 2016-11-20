在头文件<setjmp.h>中定义了一种特别的函数调用和函数返回顺序的方式。这种方式不同于以往的函数调用和返回顺序，它允许程序流程立即从一个深层嵌套的函数中返回。
<setjmp.h>中定义了两个宏：
```  
int setjmp(jmp_buf env);  /*设置调转点*/
```
和
```  
longjmp(jmp_buf jmpb, int retval);   /*跳转*/
```
宏setjmp的功能是将当前程序的状态保存在结构env，为调用宏longjmp设置一个跳转点。setjmp将当前信息保存在env中供longjmp使用。其中env是jmp_buf结构类型的，该结构定义为：
```  
typedef struct {
	unsigned	j_sp;
	unsigned	j_ss;
	unsigned	j_flag;
	unsigned	j_cs;
	unsigned	j_ip;
	unsigned	j_bp;
	unsigned	j_di;
	unsigned	j_es;
	unsigned	j_si;
	unsigned	j_ds;
}	jmp_buf[1];
```
直接调用setjmp时，返回值为0，这一般用于初始化（设置跳转点时）。以后再调用longjmp宏时用env变量进行跳转。程序会自动跳转到setjmp宏的返回语句处，此时setjmp的返回值为非0，由longjmp的第二个参数指定。
下面通过例子来理解<setjmp.h>中定义的这两个宏。
例程9-1 非局部跳转演示。
```  
include <setjmp.h> 
jmp_buf env;   /*定义jmp_buf类型变量*/
int main(void) 
{ 
   int value; 
   value = setjmp(env);  /*调用setjmp，为longjmp设置跳转点*/
   if (value != 0) 
   {
      printf("Longjmp with value %d\n", value);
      exit(value);    /*退出程序*/
   } 
   printf("Jump  ... \n");
   longjmp(env,1);       /*跳转到setjmp语句处*/
   return 0; 
}
```
本例程先应用setjmp宏为longjmp设置跳转点，当第一次调用setjmp时返回值为0，并将程序的当前状态（寄存器的相关状态）保存在结构变量env中。当程序执行到longjmp时，系统会根据setjmp保存下来的状态env跳转到setjmp语句处，并根据longjmp的第二个参数设置此时setjmp的返回值。
本例程的运行结果为：
```  
Jump  ...
Longjmp with value 1
```
一般地，宏setjmp和longjmp是成对使用的，这样程序流程可以从一个深层嵌套的函数中返回。