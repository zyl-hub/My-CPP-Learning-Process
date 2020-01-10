- [第一章](#第一章)
- [第二章](#第二章)
  * [枚举类型](#枚举类型)
  * [类型别名](#类型别名)
  * [进位制](#进位制)
  * [常量的定义](#常量的定义)
  * [各种类型的混合运算](#各种类型的混合运算)
  * [强制转换的类型](#强制转换的类型)
- [第三章](#第三章)
  * [问号冒号运算符](#问号冒号)
  * [复合赋值时变量类型一致](#复合赋值时变量类型一致)
  * [优先级](#优先级)
- [第四章](#第四章)
  * [break和continue语句](#break和continue语句)
  * [基于哨兵的循环](#基于哨兵的循环)
- [第五章](#第五章)
  * [批量处理数据--数组](#批量处理数据--数组)
  * [查找方法](#查找方法)
  * [二维数组](#二维数组)
  * [字符串](#字符串)
- [第六章](#第六章)
  * [函数定义](#函数定义)
  * [return语句](#return语句)
  * [调用](#调用)
  * [变量的作用域](#变量的作用域)
  * [数组作为函数参数](#数组作为函数参数)
  * [带默认值的函数](#带默认值的函数)
- [第七章](#第七章)
  * [指针变量](#指针变量)
  * [指针与const](#指针与const)
- [第八章](#第八章)
  * [结构体](#结构体)
  * [结构体作为函数的参数](#结构体作为函数的参数)
- [第九章](#第九章)
  * [思想方法](#思想方法)
  * [头文件的写法](#头文件的写法)
- [第十章](#第十章)
  * [类的定义](#类的定义)
  * [对象的使用](#对象的使用)
  * [构造函数](#构造函数)
  * [对象的析构](#对象的析构)
  * [析构的顺序](#析构的顺序)
  * [const与类](#const与类)
  * [静态成员](#静态成员)
  * [友元](#友元)
- [第十一章](#第十一章)
  * [运算符重载的定义](#运算符重载的定义)
  * [运算符重载的方法](#运算符重载的方法)
- [第十二章](#第十二章)
  * [组合](#组合)
  * [继承](#继承)
- [第十三章](#第十三章)
  * [类模板的定义](#类模板的定义)
  * [类模板的实例化](#类模板的实例化)
- [第十四章](#第十四章)
  * [基于控制台的输入输出](#基于控制台的输入输出)
  * [基于文件的输入输出](#基于文件的输入输出)
- [第十五章](#第十五章)
  * [传统的异常处理方法](#传统的异常处理方法)
  * [异常处理机制](#异常处理机制)

# 第一章

并没有什么好说的

# 第二章

```c++
short int==short
unsigned int counter; //定义一个计数器
```

## 枚举类型

定义后使用与int等类似

先定义变量类型为name再使用

## 类型别名

例子：

```c++
typedef int INTEGER
```

## 进位制

```c++
123 十进制
0123 八进制
0x123 十六进制
eN 表示十的多少次方只能为整次方
```

## 常量的定义

```c++
#define X //XXX使用时会机械复制例如
#define X 3+5
X*X->3+5*3+5
```

因此一般使用const来定义常量，例如

```c++
const int x; //定义x为int型常量
```

## 各种类型的混合运算

bool,char,short一起计算会转为int

其余往数值中占用内存大的那个转化

int+double->double

## 强制转换的类型

```c++
static_cast
reinterpret_cast
const_cast
dynamic_cast
```

用法

转换类型<变量名>(表达式)

用法

转换类型<变量名>(表达式)

cin.get()一次获得一个字符

# 第三章

## 问号冒号

真返回左值，假返回右值 x>y?x:y;

```c++
switch(score/10)
{
  case 10:cout<<"A";break;
  case 9:cout<<"A";break;
         ..
}
srand(time(NULL)); //随机数种子初始化
rand()%10; //更好地生成随机数
a=0,a+=1,a+=2,a+=3,a+=4,a+=5; //结果为15
//最简单的死循环for(;;);
//终止方式ctrl+c
```

## 复合赋值时变量类型一致

x++ 先赋值后改数  //////////////

++x 先改数后赋值  //////////////

x+=y 

x-=y

## 优先级

算数运算>关系运算>逻辑运算符>赋值运算

关系运算符是左结合的，例子

-2<-1<0 -> (-2<-1)<0

# 第四章

## break和continue语句

break跳出当前循环语句，执行循环语句的下一个语句

continue跳出当前循环周期，执行下一循环周期,使用实例

输出ABC的全排列

```c++
#include<iostream>
using namespace std;
int main()
{
  char ch1,ch2,ch3;
  for(ch1='A';ch1<='C';++ch1)
    for(ch2='A';ch2<='C';++ch2)
      if(ch1=ch2) continue;
  else for(ch3='A';ch3<='C';++ch3)
    if(ch3==ch1||ch3==ch2) continue;
  else cout<<ch1<<ch2<<ch3<<'\t';
  return 0;
}
```

## 基于哨兵的循环

根据条件判断确定是否执行循环

while()循环

```c++
do {

}
while()
```

可以用break跳出循环

枚举法

贪婪法

# 第五章

## 批量处理数据--数组

定义方式type name[size]

初始化type name[size]={data1;data2;...}

数组的大小不能用变量来指定

int a=10;

int array[a];是非法的

但

```c++
#define a 10
int array[a];
//或
const int a=10;
int array[a];
```

是可行的

数组下标从0开始

## 查找方法

顺序查找

二分查找

排序方法

直接选择排序

冒泡排序法(未掌握)

排序n个元素要n-1次起泡

用break检验是否排序完成，加快代码效率

## 二维数组

```c++
type name[row][column]
赋值方式
int a[3][3]={
  1,2,3,4...
}
int a[3][3]={
  {
    ...
  }
}
```

## 字符串

赋初值方式,三种

```c++
char ch[]={'H','i' ,'S'...};
char ch[]={"Hello,world"};
char ch[]="Hello,world";
```

注意会存储一个'\0'

输入

cin>>ch;

cin.getline(name,length,signOfEnd);

输出

cout<<ch;

或者循环输出

字符串处理函数

```c++
ctrcpy()
strncpy()
strlen() 
```

# 第六章

## 函数定义

```c++
type name(a,b..){

}
```

## return语句

return执行后函数即结束

## 调用

func();

## 变量的作用域

在一个程序块中定义变量，这些变量值在本程序块中有效

变量的存储类别(迷惑)

auto

static //表示只有本文件可以使用该变量

register //存入cpu，加快了运行速度

extern  //外部

static的局部变量

//当把static用于局部变量时在函数运行完毕后变量仍然不消亡，后续仍然可以使用

//这就可以实现用函数内定义的变量在cpp中使用

如果定义点以前的函数或者另外一个cpp中也要使用某一全局变量，要用extern声明

extern type name;

## 数组作为函数参数

声明方式

```c++
type func(type name[size]);
```

定义

```c++
type func(type name[size]){
  ..;
}
```

使用

func(name);

定义

```c++
type func(type name[size]){
  ..;
}
```

使用

```c++
func(name);
```

## 带默认值的函数

例如

void print(int value,int base=10);

注意默认值放在右边  ///////////////////

内联函数

初始化时

```c++
inline type func(type name){
  ..;
}
```

重载函数

多个参数类型不同的同名函数

函数模板(迷惑)

定义及使用方式

```c++
template<class T>
T func(T a,T b..){
  ..;
}
func<type,type..>(a,b..);
```

递归函数

格式

```c++
type func(type name..){
  if(?){
    return ?;
  }
  else return func(xx);
}
```

# 第七章

## 指针变量

定义

```c++
type *name;
//注意一次定义多个指针时，每个指针都要加*
```

赋值

```c++
type x,*p=&x;
```

或者

type x,*p;

p=&x;

&取地址运算符，相当于指针p指向一个地址

*运算符：根据指针类型，返回其指向的变量

或者

```c++
type x,*p;
p=&x;
```

&取地址运算符，相当于指针p指向一个地址

*运算符：根据指针类型，返回其指向的变量

或者

```c++
type x,*p;
p=&x;
```

&取地址运算符，相当于指针p指向一个地址

*运算符：根据指针类型，返回其指向的变量

```c++
void *p;
```

统配指针，可以与任何类型的指针的互相赋值

## 指针与const

const int *p=&x;

用了const表明指针指的是一个常量 //常量指针

int *const p=&x;

表示指针本身是一个常量  //指针常量

```c++
const int * const p=&x;
```

空指针常量nullptr

指针运算

对指针进行算数运算

对指针只能加减运算

动态变量的创建

```c++
new type;
```

例如

创建整形的动态变量

```c++
int *p;
p=new int;
```

创建动态数组

```c++
int *p;
p=new int[10];
```

动态数组不能为元素赋初值

动态二维数组不能通过一个简单的new实现

动态变量的消亡

回收

例子

```c++
int *p=new int(10);
delete p;
```

回收动态数组

delete [] 指针变量

内存泄漏，不及时delete

查找new操作的失误

```c++
if(!p)
//或者
if(p==NULL)
```

或者使用宏定义

assert(p!=0);

字符串再讨论

数组与指针的关系

指针与函数

指针作为形式参数，例子

```c++
void swap(int *a,int *b){
  int c=*a;
  *a=*b;
  *b=c;
}
```

数组作为函数参数再讨论

字符串作为函数的参数

返回指针的函数

命名函数时要带上指针的标志

引用类型与函数

例子

```c++
int i;
int &j=i; //必须立即初始化，不能在定义完成后进行初始化
```

相当于给i一个别名

相当于给i一个别名

更加复杂的例子

```c++
int i;
int &j1=i;
int &j2=j1;
```

可以引用的条件

引用类型变量的初值一般是一个同类型的变量

声明的引用类型是常量，他的初值也可以是一个常量

引用传递

引用传递参数

例子

```c++
void swap(int &a,int &b){
  int c;
  c=a;
  a=b;
  b=c;
}
```

常量的引用传递

引用传递可以减小函数调用的代价，引用传递有风险，可能导致实际参

数的值改变，为解决这一问题，用const限定引用传递的参数

返回引用的函数

好像正常写就行

指针数组与多级指针

指针数组

定义

type *name[len];

多级指针

char *string[10];

其中string为二级指针

# 第八章

## 结构体

定义方式

```c++
struct name{
  ...;
};
```

例如

```c++
struct studentT{
  char no[10];
  char name[10];
  int Chinese;
  int Math;
  int English;
};
```

此时studentT相当于type,所以就有各种类型的变量

.运算符号可以取出结构体类型的变量中的某一字段

结构体中套结构体要用多次.运算符

还有->运算符可以使用

## 结构体作为函数的参数

例子

```c++
struct pointT{
  double x,y;
};
void setPoint(double x,double y,pointT &p);
void setPoint(double x,double y,pointT &p){
  p.x=x;
  p.y=y;
}
```

# 第九章

## 思想方法

自顶向下的分解，将大问题拆解为小问题

## 头文件的写法

```c++
#ifndef _name_h
#define _name_h
  //头文件真正需要写的内容
#endif
```

# 第十章

## 类的定义

```c++
class name{
  private:
    ..;
  public:
    ..;
};
```



## 对象的使用

对象的定义

存储类别 类名 对象列表;

```c++
static Rational r1;
Rational array[20];
```

动态对象

```c++
Rational *rp;
rp=new Rational;`
```

动态数组

```c++
rp=new Rational[20];
```

释放内存

```c++
delete rp;
delete [] rp;
```

对象的操作

同结构体中的操作

name.func(..)

this指针(迷惑)

隐藏的指向本类型的指针形参this,它指向当前调用函数的对象。成员函数中对对象成员的访问是通过this指针实现的

```c++
void create(int n,int d){
  num=n;
  den=d;
  ReductFraction();
}
void create(int n,int d){
  this->num=n;
  this->den=d;
  this->ReductFraction();
}
```

对象的构造与析构

对象的构造

## 构造函数

在定义变量时自动调用

规定构造函数不能有返回类型  /////////

甚至指定为void也不行  //////////

拷贝构造函数/复制构造函数

## 对象的析构

析构函数

没有参数也没有返回值  //////////

格式

```c++
~classname(){
  if(??){
    delete [] ..;
  }
}
```

## 析构的顺序

后构造的先析构

然后是静态变量

然后是全局变量

有括号的括号结束就没了

## const与类

常量数据成员

例如

```c++
class Test{
    private:
    	const int size;
    public:
    	Test(int sz);
    void display();
};
```

常量数据成员的值只能在构造函数中设定

常量对象

```c++
const Rational r1(1,3);
```

常量成员函数

常量数据成员只能调用常量成员函数,例子

```c++
class Rational{
    private:
    	int num;
    	int den;
    
    	void ReductFraction();
    
    public:
    	void display() const {cout<<num<<'/'<<den;} //即为常量成员函数
};
```

## 静态成员

静态数据成员

静态数据成员定义方式

```c++
class SavingAccount{
    private:
    	static double rate;
};
```

在实现文件中

```c++
double SavingAccount::rate = 0.05;
```

静态成员函数

定义方式

```c++
static void funcName(?){
    rate = newRate;
}
```

调用方式

```c++
className::funcName(?);
```

静态常量成员

```c++
static const type name;
```

## 友元

友元函数函数破坏了函数的封装性和隐藏性

可以实现访问私有成员函数

声明方式

可以写在类的外面

```c++
friend type className::func(type); //声明className中func函数为当前的class的友元
friend class className;	//声明className类为当前类的友元
```

# 第十一章

## 运算符重载的定义

教会c++对类类型的变量执行内置运算符

## 运算符重载的方法

```c++
type operator+(const className &obj) const;
```

# 第十二章

## 组合

含有对象成员的类

## 继承

已有的类被称为基类或父类

继承实现的新类称为派生类或子类

派生类的定义

```c++
class className:继承类型 baseClassName
{
    新增加的成员的声明;
}
```

例子

```c++
class Base{
    private:
    	int x;
    public:
    	void setx(int k); 
};

class Derived1:public Base{
    private:
		int y;
    public:
    	void sety(int k);
};
```

重定义基类的函数

例子

```c++
void display() const {
    car::display();
    cout<<'\t'<<seat<<'\t'<<price<<endl;
}
```

# 第十三章

## 类模板的定义

```c++
template <class T1,class T2...>
type className<T>::funcName(形式参数表)
{..;}
```

类模板的成员函数的定义具有如下形式

1. 必须以关键字template开头，后写模板类型参数表
2. 必须用作用域限定符"::"说明它是哪个类的成员函数
3. 类名必须包含其模板形式参数

## 类模板的实例化

定义

类模板名<模板的实际参数表> 对象表

```c++
Array<int> array1(20,30);
```

# 第十四章

## 基于控制台的输入输出

```c++
cout.put('A');
cout.put(65);
//put的返回值是自身的一个引用，因此
cout.put('A').put('\n');
//相当于
cout.put('A');
cout.put('\n');
```

```c++
cout.write(string,10);
cin.read(buffer,size);
```

## 基于文件的输入输出

定义一个输入流对象

```c++
ifstream name;
name.open("file");
//或
ifstream name("file");
//或
ifstream name("flie",ifstream::in);
```

定义一个输出流对象

```c++
ofstream name;
name.open("file");
//或
ofstream name("file");
//或
ofstream name("flie",ofstream::out);
```

定义一个输入输出流对象

```c++
fstream name;
name.open("file");
//或
fstream name("file");
//或
fstream name("flie", fstream::in | fstream::out);
```

关闭文件

```c++
name.close();
```

# 第十五章

## 传统的异常处理方法

检测到错误时就地解决

## 异常处理机制

异常抛出

例子

```c++
throw myerror("something bad happened");
throw 5;
throw<操作数》;
```

操作数可以为任意类型，如果操作数是一个对象，则称为异常对象

异常捕获

```c++
try{
    可能出现异常的代码;
}
catch(类型1 参数1){处理该异常的代码}
catch(类型2 参数2){处理该异常的代码}
```

如果try中抛出异常代码，退出try语句块，直接执行catch等代码

如果try中没有抛出异常，则执行完try块的最后一个语句后，跳出所有的catch处理器

一个catch块就是一个异常处理器，他的形式如下

```c++
catch(捕获的异常类型 参数){
    异常处理代码;
}
```

