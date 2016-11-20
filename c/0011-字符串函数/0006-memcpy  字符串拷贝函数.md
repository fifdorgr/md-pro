函数原型：void *memcpy(void *destin, void *source, unsigned n)
头文件：include<string.h>
是否是标准函数：是
函数功能：从source所指的对象中复制n个字符到destin所指的对象中。但是，如果这种复制发生在重叠对象之间，其行为是不可预知的。
返回值：destin
例程如下：利用函数memcpy进行字符串拷贝。
```  
include <stdio.h>
include <string.h>
int main(void)
{
   char *s = "";
   char *d = "This is a test for memcpy function";
   char *ptr;
   printf("destination before memcpy: %s\n", d);
   ptr = memcpy(d, s, strlen(s));
   if (ptr)
      printf("destination after memcpy: %s\n", d);
   else
      printf("memcpy failed\n");
   return 0;
}
```

#### 例程说明：
（1）首先定义两个字符串s和d，并赋初值，且d的长度大于s。

（2）显示字符串d的原始内容。

（3）通过函数memcpy将字符串s复制到字符串d中，并返回字符串d的首指针。

（4）如果拷贝成功，再次显示字符串d的内容。

本例程的运行结果为：
```  
destination before memcpy: This is a test for memcpy function
destination after memcpy:  test for memcpy function
```
注意：
1、memcpy与strcpy的不同在于应用memcpy进行字符串的拷贝可以指定拷贝串的长度。另外memcpy的参数为void指针类型，因此它还可以对非字符型对象进行操作，而strcpy只适用于字符串的拷贝。
2、前面提到，如果复制过程中发生在重叠对象之间，其行为是不可预知的。例如下面这个例子：
```  
include <string.h>
include <stdio.h>
int main(void)
{
  char *d = "1234567890";
  char *p;
  p=d+3;
  printf(" %s\n", d);
  memcpy(p, d, 6);
  printf(" %s\n", d);
  return 0;
}
```
由于字符串p是字符串d的一个子串，在调用memcpy时，复制的字符串在d和p之间又重叠，因此该复制行为是不可预知的，结果也自然难以保证。这段程序的运行结果为：
```  
1234567890
1231231230
```
显然这不是期望得到的结果。
