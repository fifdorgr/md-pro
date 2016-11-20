上述介绍的基本类型可以带修饰性前缀，即类型修饰符，用来适用更多不同特点的数据处理的需要，扩大C语言基本数据类型的使用范围。C语言共有4种类型修饰符：long（长型）、short（短型）、signed（有符号型）、unsigned（无符号型）。short型和long型用于整型和字符型，其中long型还可以用于双精度型。short型不常用，对于不同机型取值范围不同，这里不再介绍。long int（简写为long）型的存储长度为4个字节，范围为，用于存储整数超过int型取值范围的情况。long double型存储长度16个字节，约24位有效数字，取值范围超过double型的数据。31312~21?
例如：
```  
long int a;
unsigned int b;
short int c;
```
分别表示a是长整型，b是无符号整型，c是短整型数据。

有符号型signed和无符号型unsigned适用于char型、int型和long型三种类型，区别在于它们的最高位是否作为符号位。unsigned char型取值范围为0~255，unsigned int（简写为unsigned）型取值范围未0~65535，unsigned long型取值范围为。
