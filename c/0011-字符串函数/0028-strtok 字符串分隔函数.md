函数原型：char *strstr(char *str1, char *str2);
头文件：include<string.h>
是否是标准函数：是
函数功能：在字符串中查找单词，这个单词始有第二个字符串中定义的分隔符分开，也就是在字符串str1中查找由字符串str2定义的分隔符，以分隔符为界，分隔出来的分隔符前面的所有字符组成一个单词，分离出第一个单词后将第一个参数置为空，可以继续分隔第二个单词。
返回值：返回分隔出的单词的指针
例程如下： 应用strtok分隔字符串。
```  
include <stdio.h>
include <string.h>
int main(void)
{
    char *str1="I am very\thappy,to,stduy\nC\nprogramme";
    char *str2=" ,\t\n";
    char *token;
    printf("%s\n\nTokens:\n",str1);
    token = strtok(str1,str2);
    while( token != NULL )
    {
        printf("%s\n",token);
        token = strtok(NULL,str2);
    }
    getch();
    return 0;
}
```

#### 例程说明：
（1）首先，程序声明了三个字符串变量并给前两个变量赋予初值，其中第二个字符串是用于分隔的分隔符集，最后一个token用于记录分隔出来的单词，应该注意到第一个字符串中有许多分隔符。

（2）为了突出分隔结果，我们首先将字符串str1打印出来，它是按照标准输出的格式进行输出。

（3）程序通过调用strtok进行字符串分隔，查找字符串str1中首次出现字符串str2任意分隔符的位置，然后将分隔符之前的所有字符组成一个单词返回给token变量，从而得到分隔出来的首个单词。

（4）在循环体中，我们每次循环都要将上一次分隔出来的单词打印出来，另外就像前面所说，将strtok函数第一个参数置为空可以达到继续进行分隔的目的，也就是在上一次分隔出来的单词之后继续进行分隔，直到所有单词都分隔完毕，token变量会得到空的返回值，我们结束循环。

（5）打印分隔结果时，以换行区分每次分隔出的单词。

本例程的运行结果是：
```  
I am very		happy,to,study
C
Programme
Token:
I
am
very
happy
to
study
C
Programme
```

注意：本例程中，一定要记住如果在第一次分隔出单词后想继续进行分隔操作，务必要将函数的第一个参数置为空。
