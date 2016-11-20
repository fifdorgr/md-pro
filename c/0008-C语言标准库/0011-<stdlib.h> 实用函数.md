在头文件<stdlib.h>中声明了一些实现数值转换，内存分配等类似功能的函数。下面给出头文件<stdlib.h>中声明的函数以及功能简介，见下表。
<stdlib.h>中声明的函数
```  
函数定义, 函数功能简介
double atof(const char *s), 将字符串s转换为double类型
int atoi(const char *s) , 将字符串s转换为int类型
long atol(const char *s), 将字符串s转换为long类型
double strtod (const char*s,char **endp) , 将字符串s前缀转换为double型
long strtol(const char*s,char **endp,int base), 将字符串s前缀转换为long型
unsinged long strtol(const char*s,char **endp,int base), 将字符串s前缀转换为unsinged long型
int rand(void), 产生一个0~RAND_MAX之间的伪随机数
void srand(unsigned int seed) , 初始化随机数发生器
void *calloc(size_t nelem, size_t elsize), 分配主存储器
void *malloc(unsigned size), 内存分配函数
void *realloc(void *ptr, unsigned newsize), 重新分配主存
void free(void *ptr), 释放已分配的块
void abort(void), 异常终止一个进程
void exit(int status), 终止应用程序
int atexit(atexit_t func), 注册终止函数
char *getenv(char *envvar), 从环境中取字符串
void *bsearch(const void *key, const void *base, size_t *nelem, size_t width, int(*fcmp)(const void *, const *)), 二分法搜索函数
void qsort(void *base, int nelem, int width, int (*fcmp)()), 使用快速排序例程进行排序
int abs(int i), 求整数的绝对值
long labs(long n), 取长整型绝对值
div_t  div(int number, int denom), 将两个整数相除, 返回商和余数
ldiv_t ldiv(long lnumer, long ldenom), 两个长整型数相除, 返回商和余数
```
有关上面列出的这些标准实用函数的功能、用法、例程等。