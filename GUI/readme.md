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
### 类中访问修饰符
public 成员可
- private
- protected
- public
- internal
- protected internal

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
## out 的使用
在方法中能够返回多个不同的值， 也能返回相同类型的值。

##  静态字段
````
class DStatic
{
  int Mem1;
  static int Mem2 = 20;  // static variant
}

static void Main(string[] args)
{
    Console.WriteLine("Hello World!");
    DStatic d1 = new DStatic();
    DStatic d2 = new DStatic();
    d1.Mem1 = 5;
    Console.WriteLine("The static number is {0}", DStatic.Mem2);
    DStatic.Mem2 = 10;  // need use the class itself to access the static 
    Console.WriteLine("The static number is {0}", DStatic.Mem2);
}
````
 访问类中的静态变量，需要用到类本身去调用，不能用其实例。
 ##  静态方法
 实例无法调用静态方法，需要用到类本身去调用。
 
 ## 方法的重载
 方法可以被重载但必须有不同的签名， 签名包括：
 - 方法的名称
 - 参数的数目
 - 参数的数据类型和顺序
 - 参数的修饰符。
 - 返回值类型 以及形参 不属于签名的一部分
 
 
## 常量
常量对每个实例都是可见的，常量没有自己的存储位置，而是编译时被编译器替代。 类似于C和C++中的define值。
## 属性
属性是代表类的实例或类中一个数据项的成员。
属性和字段不同的是他是一个函数成员
- 它不为数据存储分配内存
- 它执行代码
属性是指定的一组两个匹配的，成为访问器的方法。
- set 访问器位属性赋值
- get 访问器从属性获取值
````
static void Main(string[] args)
{
    Console.WriteLine("Hello World!");
    UseProperty Exampl1 = new UseProperty();
    Console.WriteLine("The data get by property is {0}", Exampl1.MyValue);
    Exampl1.MyValue = 5;
    Console.WriteLine("The data get by property is {0}", Exampl1.MyValue);

}

static void Main(string[] args)
{
    Console.WriteLine("Hello World!");
    UseProperty Exampl1 = new UseProperty();
    Console.WriteLine("The data get by property is {0}", Exampl1.MyValue);
    Exampl1.MyValue = 5;
    Console.WriteLine("The data get by property is {0}", Exampl1.MyValue);

}
````
属性可以定义只读和只写类型。
- 自动实现属性
编译器会创建隐形的后备字段。
````
class UseProperty1
{
    public int MyValue
    {
        set;    get;
    }

}

static void Main(string[] args)
{

    UseProperty1 C1 = new UseProperty1();
    Console.WriteLine("the automatic property is {0}", C1.MyValue);
    C1.MyValue = 20;
    Console.WriteLine("the automatic property is {0}", C1.MyValue);

}
````
- 静态属性
不能访问类的实例成员， 不管类是否有实例他们都是存在的， 从类的外部访问是必须使用类名引用不能使用实例名。
````
class UseStaticProperty
{
    public static int Get_Set { set; get; }
    public void Display()
    {
        Console.WriteLine("my value is {0}", Get_Set); // internal access
    }

}

static void Main(string[] args)
{
    Console.WriteLine("Access from outside {0}", UseStaticProperty.Get_Set);
    UseStaticProperty C2 = new UseStaticProperty();
    C2.Display();
    UseStaticProperty.Get_Set = 30;
    C2.Display();
    Console.WriteLine("Access from outside {0}", UseStaticProperty.Get_Set);
    //C2.Get_Set = 30; illeagal operation
}
````
## 构造函数
每创建一个新的实例时执行
- 和类同名的方法
- 不能有返回值
- 可以单参数
- 可以被重载
