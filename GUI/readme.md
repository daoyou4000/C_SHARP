In this folder, the process how to develop the GUI by C# will be demonstrated. 

## Quick shortcut, VS 快捷键
- **///**: 添加备注, 选中一个方法，可以添加总结
- **Ctrl + K + C**: Comment
- **Ctrl + K + U**: Uncomment
- **Home**: 将编辑器光标到行头
- **END**: 将编辑器光标到行尾
- **Ctrl + K + D**: 快速对其代码
- **#Region and #EndRegion**: 折叠冗余代码
- **Ctrl + J**: 快速弹出只能提示
- **F1** 转到帮助文档
- **F5** 开始debug.

## Data type 数据类型
- **int** 整型 32bit
- **double** 整形，浮点型， 64bit
- **decimal** 只能存储 钱， 28-29精确度
- **string** 字符串 用""
- **char** 最多最少存一个 用''
## 命名法则
- Camel rule: 首单词的首字母小写，其余每个单词首字母大写， 多用于给变量命名: highSchool
- Pascal rule: 每个单词的首字母大写，多用于给类和方法命名。 Main()
- **+**, 在字符串中式连接的意思，否则是相加
- 占位符
````
Console.WriteLine("the first number is {0}, the second number is {1}, the third number is {2},", n1, n2,n3);
````
## C# 输入
只能用string 进行接收
````
string name = Console.ReaLine();
````
##转移符
- **\n** 换行
- **\"** 英文半角双引号
- **\t** tab， 字符排版
- **\b**  退格键
- **\r\n** windows 系统文本中换一行
- 使用 \ 会识别报错，C# 会认为是转移符.
@ 符号会取消转移符。
````
string path = "F:\CAN\LOG\log.text";
string path = "F:\\CAN\\LOG\\log.text";
string path = @"F:\\CAN\\LOG\\log.text";
````

## 类型转换
- 隐式类型转换条件: 1, 两种类型兼容，2，目标类型大于源类型。
- 强制类型转换: (int), (double) 变量前面

````
int a = 10;
int b = 3;
double c = a /b;
Console.WriteLine("{0}",d);

double d  = 10;
double c = d /b;
Console.WriteLine("{0:0.00}",d); // 小数点后保留两位


````

在这个运算中，a/b 会先求得结果3， 然后赋值给c, 因此结果是 3.

