函数原型：int remove(char *filename);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：删除以filename为文件名的文件。该函数的参数为欲删除文件的文件名，如果是单纯的文件名，就表明删除当前文件夹下的文件，否则要写明文件的路径。
返回值：成功删除文件返回0，否则返回-1。
例程如下 应用remove函数删除文件。
```  
include <stdio.h>
void main()
{
   if( remove( "test.txt" ) == -1 )
      perror( "Could not delete test.txt!!" );
   else
      printf( "Deleted test.txt \n" );
}
```

#### 例程说明：

（1）首先要在当前文件夹下建立文件test.txt。

（2）再利用remove函数删除该文件。若删除成功，则在终端显示字符串"Deleted test.txt \n"，否则显示字符串"Could not delete test.txt!!: No such file or directory"。
注意：前面已经讲过perror函数是按照一定格式要求向终端输出错误信息，因此，若删除文件成功，程序运行的结果为：
```  
Deleted test.txt
```
若删除失败，则程序运行的结果为：
```  
Could not delete test.txt!!: No such file or directory
```
这里，利用perror函数显示的完整的错误信息包括：用户自定义字符串，冒号，系统报错信息，换行符。
