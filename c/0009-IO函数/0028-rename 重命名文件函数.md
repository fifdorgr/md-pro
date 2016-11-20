函数原型：int rename(char *oldname, char *newname);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：把由oldname所指的文件名改为由newname所指的文件名。该函数有两个参数，oldname为旧的文件名，newname为欲改成的新文件名。应当注意，oldname所指的文件一定要存在，newname所指的文件一定不存在。应用该函数可将一个文件的旧文件名oldname改为新文件名newname，但不能改变文件的路径。
返回值：成功返回0，出错返回-1。
例程如下 应用rename函数重命名文件。
```  
include <stdio.h>
int main(void)
{
  if( rename("oldname.txt","newname.txt")==0)
      printf("Rename successful!!");
  else
      printf("Rename fail!!");
}
```

#### 例程说明：

（1）首先，在当前文件夹下建立一个文件"oldname.txt"。

（2）应用rename函数重命名该文件，将其改名为"newname.txt"。若重命名成功，在屏幕上显示"Rename successful!!"提示字符串；否则显示"Rename fail!!"提示字符串。
