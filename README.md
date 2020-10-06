第一章
===
1.3 注释简介
---
注释内每行都以一个*开头
```cpp
/*
 * 注释内每行都以一个*开头
 * Each line in a comment begins with an asterisk
 */
```
第二章
===
2.1.2 类型转换
---
```
原码: 0000 0001
反码: 1111 1110
补码: 1111 1111 (取反加1)
```
Attention: 切勿滥用带符号类型和无符号类型，size_t经常导致warning

2.1.3 字面值常量
---
```cpp
'a'
"abcdef"
```
字符串字面值的类型实际上是由常量字符构成的数组

2.2.1 变量定义
---
***初始值***<br>
```int i {0};```<br>
C++11新特性：可以使用花括号来初始化变量

***默认初始化***<br>
定义于任何函数体之外的变量被初始化为0。<br>
string类规定如果没有指定初值则生成一个空串

2.2.2 变量声明和定义的关系
---
``` extern int i; //声明i而非定义i ```

使用`extern`关键字来声明但不定义变量

2.2.4 名字的作用域
---
```cpp
#include<iostream>
int reused = 20;
int main()
{
	int reused = 10;
	std::cout << "global: " << ::reused << std::endl << "local: " << reused << std::endl;
	return 0;
}
```
使用`::`(作用域操作符)显式地访问全局变量`reused`

2.4 const限定符
---
与define的区别：
>1. 起作用的阶段
>>define在预处理阶段<br>
>>const在编译或运行阶段<br>
>>```
>>const int i = get_size(); //运行时初始化
>>const int j = 42; //编译时初始化
>>```

>2. 起作用的方式<br>
>>define为简单的字符串替换<br>
>>const有对应的数据类型

>3. 存储方式
>>define被使用时即展开，存在多个备份<br>
>>const只读， 只有一个备份

>4. 调试方便
>>define在预处理时已被替换，无法调试<br>
>>const可调试
