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
##转义符
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

## 异常捕获
-try - catch
````
try
{
  可能出现异常的代码
}
catch
{
  出现异常后执行的代码
}
````
## break and continue
- break: 终止循环
- continue: 终止本次循环

## 类
由以下元素定义:
- 名称
- 保存数据成员的数据结构
- 一些行为及约束条件

通过实例化类型而创建的对象被称为类型的对象或类型的实例。

## 数据类型
16 种预定义简单类型:
![image](https://github.com/daoyou4000/C_SHARP/blob/f2ac1cb15145cd7934d01383ca3bd7725d3c17b7/image/datatype.PNG)

6 种用户定义类型
- 类类型（class)
- 结构类型 struct
- 数组 array
- 枚举 enum
- 委托 delegate
- 接口类型 interface

## 三元表达式
表达式1 (bool)? 表达式2: 表达式3  
````
bool result = 3 < 5? true: false;
````
## 复杂数据类型
- 常量，const
- 枚举，enum
Enum.Pasre(); 转换字符串到枚举类型
int 到枚举转换
string 到枚举类型转换
- 结构 struct
````
public struct Person
{
  public string _name;
  public int _age;
  public Gender _gender; // _gender 下划线表示字段
}
````
