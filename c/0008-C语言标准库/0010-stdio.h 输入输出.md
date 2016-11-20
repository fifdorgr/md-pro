在头文件<stdio.h>中定义了输入输出函数，类型和宏。这些函数、类型和宏几乎占到标准库的三分之一。
下面给出头文件<stdio.h>中声明的函数以及功能简介，见下表。
<stdio.h>中声明的函数
```  
函数定义, 函数功能简介
FILE *fopen(char *filename, char *type), 打开一个文件
FILE *fropen(char *filename, char *type,FILE *fp), 打开一个文件，并将该文件关联到fp指定的流
int fflush(FILE *stream), 清除一个流
int fclose(FILE *stream), 关闭一个文件
int remove(char *filename), 删除一个文件
int rename(char *oldname, char *newname), 重命名文件
FILE *tmpfile(void), 以二进制方式打开暂存文件
char *tmpnam(char *sptr), 创建一个唯一的文件名
int setvbuf(FILE *stream, char *buf, int type, unsigned size), 把缓冲区与流相关
int printf(char *format...), 产生格式化输出的函数
int fprintf(FILE *stream, char *format[, argument,...]), 传送格式化输出到一个流中
int scanf(char *format[,argument,...]), 执行格式化输入
int fscanf(FILE *stream, char *format[,argument...]), 从一个流中执行格式化输入
int fgetc(FILE *stream), 从流中读取字符
char *fgets(char *string, int n, FILE *stream), 从流中读取一字符串
int fputc(int ch, FILE *stream), 送一个字符到一个流中
int fputs(char *string, FILE *stream), 送一个字符到一个流中
int getc(FILE *stream), 从流中取字符
int getchar(void), 从stdin流中读字符
char *gets(char *string), 从流中取一字符串
int putchar(int ch), 在stdout上输出字符
int puts(char *string), 送一字符串到流中
int ungetc(char c, FILE *stream), 把一个字符退回到输入流中
int fread(void *ptr, int size, int nitems, FILE *stream), 从一个流中读数据
int fwrite(void *ptr, int size, int nitems, FILE *stream), 写内容到流中
int fseek(FILE *stream, long offset, int fromwhere), 重定位流上的文件指针
long ftell(FILE *stream), 返回当前文件指针
int rewind(FILE *stream), 将文件指针重新指向一个流的开头
int fgetpos(FILE *stream), 取得当前文件的句柄
int fsetpos(FILE *stream, const fpos_t *pos), 定位流上的文件指针
void clearerr(FILE *stream), 复位错误标志
int feof(FILE *stream), 检测流上的文件结束符
int ferror(FILE *stream), 检测流上的错误
void perror(char *string), 系统错误信息
```
在头文件<stdio.h>中还定义了一些类型和宏。