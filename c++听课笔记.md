# Class 1 : 1st

C++ programs consist of **classes**, **functions**, **variables**, and  other component parts

classes  类 ；functions 函数  ；variables  变量

To get a sense of how a program **fits together**, you must see a complete working program

fits together合适适应

```c++
#include <iostream>
int main()
{
   std::cout<<"Hello World!\n"
   return 0;
   }
```

程序时formal language  ;人类时national language ;软件visual studio ; IC 集成电路 IDE集成开发环境 star key   *  ;  preprocessor处理器 ; cpu: center precessing unit  ; iostream: 输入输出（I/O）

The first character is the **# (pound) symbol**, which is a signal to a program called the **preprocessor**

Each time you start your compiler, the **preprocessor is run first**



#  Class 1 :2nd 

angle brackets 角括号 ； console output =  cout = printf  ；**automatically** 自动的

Usually, functions are **invoked** or **called** by other functions, but **main()** **is special**

别的函数都是由程序员决定是否调用，main是被操作系统来调用的

brace 拥抱 、大括号 ； Parentheses小括号 ；std : standard标准 ;  colon冒号

ANSI-compliant compiler  ；  cout 属于std库中的一个函数  ；less than 小于号

endl结束并换行 

## A Simple Program - Namespace 

程序命名空间 ；给程序划分层次 ；compiler 编译器：将程序转换为计算机语言

When **using namespaces**, just put the characters std followed by **two** 

**colons** before the *cout*

**redirection operator (<<)**输出

**in double quotes (“”)**



# Class 2 1st



hierarchy层次  hierarchical   editor编辑器

```c++
using std::cout;
using std::endl;//简化
using namespace std；//正常情况下不实用，全加进来
```

## Commenting Your Programs

Commenting注释  ; confusing不清楚  ； ignore忽略 ； single-line  **multiline**  ； C是C++的子集即superset、subset



# Class 2 2nd

executed执行 ;  

When the **function finishes**, it **returns** control to the line of code immediately following  the call to the function

prototype  ；  Function definition ；global全局  ； 

```c++
int Add(int first, int second)
{
  std::cout<<"Add() received"<< first<<"and"<<second<<"\n";
  return (first+second);
}//返回整型，一般函数名首字母是小写，参数也是整型
```

cin =console input 从键盘输入  ； greater than大于号 ；C++顺序编译 ; Variables变量 ；Constants常量

## Overview

store存储 ； execution执行 ; manipulate操纵



# Class 3 : 1st

## Lecture 3 – Classes & Objects

object 对象/物件 ;methodology方法；brown 棕色； puffy 肿胀的 ;  silver bullets 万能钥匙 ； delivered 配送；发行

Object - Oriented  让程序从smart-scale变成large-scale ； inherit 继承  ；include 这也是一种继承

object -> characteristics -> behavior  （用Function表示）

program : data + algorithm (算法)   self -defined 自定义  struct + function = object



# Class 3 : 2nd

manipulate 操作；

```c++
class Cat
{
unsigned int itsAge;
unsigned int itsWeight;
void Menw();
}
```

unsigned无符号  + :position -:negative  unsigned只有正没有负  ；void 空  ； instance实例

Declaring the class **does not allocate memory** for a Cat

32位是4字节，64位是8字节 

concept(generic)  instance(specific)  integer =int 整数

## Classes Versus Objects

Versus = VS; pet 宠物 ; individual 具体的 ;  access 存取 ： dot operator（.） ；

## Private Versus Public Access

private 只能在内部进行定义，public可以在外部进行定义；计算机更加趋向于private



# Class 4 :1st

##  Making Member Data Private

As a **general rule** of design, you should keep the **data members** of a class **private**

**accessor methods**通过特殊的方式进行与外部交互，最简单的方式就是set 和 get

 ```c++
unsigned int getAge();
void setAge(unsigned int age);
unsigned int getWeight();
void setWeight(unsigned int weight);   //accessor methods
 ```

所有main server 都是 Public, 数据都是private

##  Making Member Data Private

Why bother with this extra level of **indirect access**? 

indirect access间接存取； prototype原型

## Implementing Class Methods

implementing实现 



# Class 4:2nd

## Adding Constructors & Destructors

Constructors构造 ；Destructors破坏；任何Class都有Constructors ； 

The constructor can **take parameters** as needed, but it **cannot have a** **return value, not even void**  

```c++
Cat(int initAge);
~Cat();一个是构造一个是拆除，两个只有一个参数initAge
```

默认的Constructors是没有参数，而此时已经有写上参数，没有参数的为 Default Constructor

```c++
Cat::Cat(int initAge)
{
itsAge = initAge
itsWeight = -1
}
```

```c++
Cat frisky(5);
frisky.meow();
```

## Including *const* Member Functions

const 常量 做函数后尽量不修改数据

compiliy error 编译出错; runtime error运行出错，最好是编译出错

**setAge() cannot be const** because it changes the member variable itsAge

**getAge()**, on the other hand, **can and should be const** because it does not change the class at all   只读的最好加上const，这样不会改写，好处在于后面不会被修改



# Class 5 ;1st

## Where to Put Class Declarations & Method Definitions

scalable scale规模大小  Definitions声明定义  interface 

Scalable :Convent ;rule 

# Where to Put Class Declarations & Method 

Definitions

# Where to Put Class Declarations & Method 



































# Class 11 :2 nd

```c++
#include <iostream>
using namespace std;

class ElectricMotor
{
public:
    ElectricMotor () {};
    virtual ~ElectricMotor () {};

public:
    void StartMotor ()
    {
        Accelerate ();
        Cruise ();
    }

    void StopMotor ()
    {
        cout << "Motor stopped" << endl;
    };

class Fan : private ElectricMotor
{
public:
    Fan () {};
    ~Fan () {}

    void StartFan ()
    {
        StartMotor ();
    }

    void StopFan ()
    {
        StopMotor ();
    }
};

```

Public inheritance :不仅继承后子类可以使用，其他也可以使用,变成子类的一部分,，可以继承下去给后代，

Private inheritance与Public inheritance相反

Imagine :想象  ;Fan粉丝/风扇  ;Electric motor电动摩托 ; scenario场景

使用是<font color =red>继承</font>是重写代码的一种方式

Fan的内部可以看到Electric motor的程序，外部用户看不到，父类的属性对程序员是私有的。只在definition和declaration可见

 

# Class 9 :1 st

```c++
#include <iostream>
using namespace std;

enum BREED { GOLDEN, CAIRN, DANDIE, SHETLAND, DOBERMAN, LAB };

class Mammal
{
public:
    // constructors
    Mammal();
    Mammal(int age);
    ~Mammal();

    //accessors
    int GetAge() const { return itsAge; }
    void SetAge(int age) { itsAge = age; }
    int GetWeight() const { return itsWeight; }
    void SetWeight(int weight) { itsWeight = weight; }

    //Other methods
    void Speak() const { cout << "Mammal sound!\n"; }
    void Sleep() const { cout << "shhh. I'm sleeping.\n"; }

protected:
    int itsAge;
    int itsWeight;
};

class Dog : public Mammal
{
public:

    // Constructors
    Dog();
    Dog(int age);
    Dog(int age, int weight);
    Dog(int age, BREED breed);
    Dog(int age, int weight, BREED breed);
    ~Dog();

    // Accessors
    BREED GetBreed() const { return itsBreed; }
    void SetBreed(BREED breed) { itsBreed = breed; }

    // Other methods
    void WagTail() const { cout << "Tail wagging...\n"; }
    void BegForFood() const { cout << "Begging for food...\n"; }

private:
    BREED itsBreed;
};

Mammal::Mammal():
itsAge(1),
itsWeight(5)
{
    cout << "Mammal constructor..." << endl;
}

Mammal::Mammal(int age):
itsAge(age),
itsWeight(5)
{
    cout << "Mammal(int) constructor..." << endl;
}

Mammal::~Mammal()
{
    cout << "Mammal destructor..." << endl;
}

Dog::Dog():
Mammal(),
itsBreed(GOLDEN)
{
    cout << "Dog constructor..." << endl;
}

Dog::Dog(int age):
Mammal(age),
itsBreed(GOLDEN)
{
    cout << "Dog(int) constructor..." << endl;
}

Dog::Dog(int age, int weight):
Mammal(age),
itsBreed(GOLDEN)
{
    itsWeight = weight;
    cout << "Dog(int, int) constructor..." << endl;
}

Dog::Dog(int age, int weight, BREED breed):
Mammal(age),
itsBreed(breed)
{
    itsWeight = weight;
    cout << "Dog(int, int, BREED) constructor..." << endl;
}

Dog::Dog(int age, BREED breed):
Mammal(age),
itsBreed(breed)
{
    cout << "Dog(int, BREED) constructor..." << endl;
}

Dog::~Dog()
{
    cout << "Dog destructor..." << endl;
}
int main()
{
    Dog Fido;
    Dog rover(5);
    Dog buster(6,8);
    Dog yorkie (3,GOLDEN);
    Dog dobbie (4,20,DOBERMAN);
    Fido.Speak();
    rover.WagTail();
    cout << "Yorkie is " << yorkie.GetAge()
        << " years old" << endl;
    cout << "Dobbie weighs ";
    cout << dobbie.GetWeight() << " pounds" << endl;
    return 0;
}
```

```c++
Mammal();

Mammal(int age);
```

overload的含义：一个名字一样但是参数不一样或者名字不一样或者输入不一样的函数，程序中Dog()也是overload

Dog继承了Mammal，子类向父类传参数，因为某些成员没有自己定义。

Dog要初始化则他的父类Mammal也要初始化

调用fido. speck()是因为Mammal有speck函数

程序解释：对Mammal函数进行重写，父类Mammal将数据成员声明为protected以便派生类Dog进行访问，父类Mammal定义了itsAge ；itsWeight两个数据成员，子类Dog继承Mammal后进行重写为Dog() ; Dog(int age) ; Dog(int age, int weight) ; Dog(int age, BREED breed) ; Dog(int age, int weight, BREED breed)，并向父类Mammal传参数，每次都输出"Mammal constructor..."以及子类对应的结果，这其中Dog类要初始化时他的父类Mammal也要初始化且Mammal只能调用一个参数在同时调用两个或三个参数时需要进行补充。Fido.Speak调用了父类Mammal的speak函数输出 "Mammal sound!"且通过Fido调用了Dog类扩展的方法wagTail，所以输出"Tail wagging...",在main函数中rover；buster；yorkie ；dobbie分别调用Dog类，yorkie以及dobbie还调用了BREED中的一个常量，其中由于BREED是一种枚举常量所以breed常量只能取BREED的枚举常量中的一个，于是分别输出Yorkie is 3 years old ; Dobbie weighs 20 pounds ，最后输出Dog和Mammal的destructor 。



# Class 16 1st ,Macros,Series

##  lecture 6-1.1  

## Programming Conversion Operators

```c++
operator int() 
{ 
 // implementation
  return intValue
  }
```

<font color=red>double->float</font>由于计算机的字节限制所以这是不可实现的

```c++
CDate C;
 int y = (int)c;
 y=?
```

如何实现复杂的类型转化为int型，不是都能实现，但例如日期等情况下可实现或是转换为字符串char*或是double

```c++
operator int ()
{
return ((m_nYear*10000)+(m_nMonth*1000)+m_nDay);
}
```

## Binary Operators

static 是 C/C++ 中很常用的修饰符，它被用来控制变量的存储方式和可见性。对多个对象来说，静态数据成员只存储一处，供所有对象共用。静态数据成员的值对每个对象都是一样，但它的值是可以更新的。只要对静态数据成员的值更新一次，保证所有对象存取更新后的相同的值，这样可以提高时间效率。

```c++
return-type operator_type (parameter1,parameter2);
```

## Programming Binary Addition (a+b) and Subtraction (a-b) Operators

 ```c++
CDate operator+(int nDaysToAdd)
{
 CDate newDate(m_nDay,m_nMonth,m_nYear);
 newDate.addDays(nDaysToAdd);
 return newDate;
}
 ```

```c++
cDate datePlus10(mDate+10)；
```

## Lecture 7——Introduction to Macros and Templates

Macros宏  ; "#"pound symbol预处理,预处理时甚至可以对源文件进行某种改动

## The #define Preprocessor Directive

You can create substitutions using the #define command

```c++
#define BIG 512
```

BIG相当于一个常量（constant）; substitutions 替换 ；预处理做的指令会让源程序在编译前进行某种变化，512是字符串 ，把BIG替换512，在源程序中写的是BIG ，好处就是可读性更强。

You instruct the precompiler to substitute the string 512 wherever it sees the string BIG

```C++
#define BIG 512
int myArray[BIG];
```

## Macro Function

The #define directive can also be used to creat macro functions

A macro function is a symbol created using #define that takes an argument ,much like a funtion doed

The preprocessor substitutes the substitution string for whatever argument it is given

```
#define Twice(x)((x)*2)
```

argument常量 ； Parentheses小括号

<font color=red>用Twice（x）代替（x）*2</font>

A macro can have Macro Functions ,and each parameter can be used repeatdly in the replacement text



# Class 17  1st 

# Slicing

## Note that the virtual function magic operates only on pointers and references. 

## Passing an object by value does not enable the virtual functions to be invoked. Listing 11.10 illus-trates this problem.

slicing切片 ;  sequential ;  

每一个object都有一个唯一的指针 ，把内存进行切片 pointers 和references表示object而不用备份来表示 

## passing by reference & passing by value

一个是形参，一个是实参，一个是地址，一个是复制品

function (student)在passing by reference直接修改，而passing by value是复制不会对原本的进行修改； 在面向对象基础中，object通过继承关系有层次关系，virtual function 最大的好处是实现多态。一般情况下都是passing by reference，系统在底层都是按照passing by reference，只有特殊情况下运行指令使用passing by value ,否则失去多态性。

```c++
void valueFunction(Mammal);//passing by value
void ptrFuntion(Mammal*);
void refFunction(Mammal&);
```

Mammal*直接传地址，而Mammal&传的是object，但是在传在前把地址拿出来. 

``` c++
ptrFunction(ptr);//WOOF!
refFunction(*ptr);//WOOF!
ValueFunction(*ptr);//失去多态性//Mammal speck!
```

# Creating Virtual Destructors

## It is legal and common to pass a pointer to a derived object when a pointer to a base object is expected. 

## What happens when that pointer to a derived subject is deleted? If the destructor is virtual, as it should be, the right thing happens—the derived class’s destructoris called. 

## Because the derived class’s destructor automatically invokes the base class’s destructor, the entire object is properly destroyed.

## The rule of thumb is this: If any function in your class is virtual, the destructor should beas well.

# Virtual Copy Constructors

## Constructors cannot be virtual

## Nonetheless, at times, your program desperately needs to be able to pass in a pointer to a base object and have a copy of the correct derived object that is created. 

## A common solution to this problem is to create a Clone() method in the base class and to make it virtual. 

## The Clone() method creates a new object copy of the current class and returns that object.

## Because each derived class overrides the Clone() method, a copy of the derived class is created. 

 a virtual copy construtor ； enum枚举

```c++
Mamal(const Mammal &rhs);//加const表示传进来的参数不能修改是常量
virtual void speak() const ;//speak()函数内部不能修改，只能读
```

```c++
virtual Mammal* clone()
{
return new Mammal(*this);
}
int getAge() const
{
    return itsAge;
}
```

enapsulation封装

```c++
class Cat : public Mammal
 {
 public:
 Cat() { cout << “Cat constructor...\n”; }
 ~Cat() { cout << “Cat destructor...\n”; }
 Cat (const Cat &);
 void Speak()const { cout << “Meow!\n”; }
 virtual Mammal* Clone() { return new Cat(*this); }
 };

 Cat::Cat(const Cat & rhs):
Mammal(rhs)
 {
 cout << “Cat copy constructor...\n”;
 }
```



# Class 18 

## Macro Functions 

Data safety | sacurity  ,  Data safety: 数据的conversion Correctness  ;  computer security ; programing 

different type: Assignement or Conversion ;  program : Compiling Time or Runtime

The preprocessor and the Compiler ;  #define TWICE(X) ((X)*2)

## A macro can have Macro Functions , and each parameter can be used repeatedly in the replacement text

```c++
#define Max(x,y) ((x)>(y)?(x):(y))
#define Min(x,y) ((x)>(y)?(x):(y))
```

opening parenthese 左小括号  ； closing parenthese 右小括号 ;  C语言是大小写敏感的

## The preprocessor is not as forgiving of whitespaces as is the compiler

不能在函数后头和函数表直接有空格，因为没有语法词法的分析

## Why All the parenthese?

CUBE立方体 

~~~c++
#define CUBE(a) ((a)*(a)*(a))
#define THREE(a) a*a*a
y=CUBE(a+b)
z=THREE(a+b)
~~~

此时Z的值会出现问题，因为THREE没有加括号

## How macros&poor type safety GO Hand-in-Hand

Macros Versus Functions and Templates 

Macros suffer from four peoblems in C++

confusing迷惑 ； tricky 诡计多端

Threrfore,it is unavailable in most debuggers 

大多数调试器会把宏去掉而进行调试

Macros are not type safe 可能让程序在运行时出错

anathema讨厌的 ； absolute value绝对值 ； undermine暗中破坏

## Inline Functions 

An Introduction to Templates 定义函数时也定义可变的类型，让函数更多多元化



# Class 20 lecture 8 -Threading

## What is Concurrency?

Concurrency occurs when multiple copies of a program run simultaneously while communicating with each other.

Simply put ,concurrency is when two tasks are oberlapped.

A simple concurrent application uses a single machine to store the program's instruction, but that process is executed by multiple different threads.

overlapped 互相覆盖，互相有交集 ； 并发的程序是完全独立的，只是可能存在程序间的交互，所有经典的程序都是异步运行

传统的程序设计技术是：

```mermaid
graph LR
	A(main) --> B(function) --> C(function) --> D(function) --> E(Exit)
```

现代的程序设计技术是  ex:Go 默认是并发性语言

```mermaid
graph TD
A(main) --> B1(function)
A(main) --> B2(function)
A(main) --> B3(function)
B1 --> D(Exit)
B2 --> D(Exit)
B3 --> D(Exit)
```

尽量不用并发技术而用其他的替代，例如做游戏的时候用game engire 

A date race is a common issue you may encounter in C++ concurrency and mmulti-threaded processes

Data races in C++ occur when at least two threads can simultaneously acccess a variable or memory location, and at least of those threads tries to access that variable 

This can result in undefined behavior 

Regardless of its challenges, concurrency is very important for handling multiple tasks at once

race 竞争 在同步与异步之间寻找平衡 ; handle/process 处理

``` c++
#include<thread>//利用thread

void hello()
{
    std::cout << "Hello Concurrent World\n";
    
}

int main()
{
    std::thread t(hello);//生成Object/class,定义了一个t,应该用大写
    t.join();
}
```

join() 合并; fork()分叉; synchronize同步,如果join执行的不彻底的话会造成有些线程还活着，对线程失去控制。

# Hello Concurrent World

The first difference is the extra #include<thread>

Second,the code for writing the message has been moved to a separate function because every thread has to have an initial function, where the new thread of execution begins

Third, rather than writing directly to standard output or calling hello() from main(), this program launches a new thread to do it ,bringing the thread count to two

The initial thread that starts at main()

The new thread that starts at hello()

After the new thread has been launched, the inital thread continues execution

If it did not wait for the new thread to finish , it would merrily (cheerful and lively) continue to the end of main() and end the program -possibly before the new thread had a chance to run

This is why the call to join（） is there

This causes the calling thread to wait for the thread associated with the std::thread object, in this case

launches发射

# Managing Threads 

The C++ Standard Library makes most thread-management tasks relatively easy, with almost everything managed through the  std::thread object associated with a given thread 

For those tasks that are not so straightforword ,the library provides the flexibility to build what you need from the basic building blocks

```c++
struct func{
    int &i;
    
    func(int &i_):i(i_)
    {
    }
    
    void operator()()
    {
        for(unsigned j=0;j<1000000;++j)
        {
            do_something(i);
        }
    }
};
```

underscore下划线 （26+26+1+10）63个字符可以给变量起名字，尽量用长名字



# 2020.12.14

## Running Threads in the Background

### Consider an application such as a word peocessor that can edit multiple documents at once

### One way to handle this internally is to run each document-editing window in its own thread

### Each thread runs the same code but with different data relaing to the document being edited and the corresponding window peperties

### Opending a new document therefore requires starting a new thread

peperties属性

foreground功能性  Backgrond非功能性，保证安全，性能提升



# Passing Arguments to a Thread Function

## According the previous examples, passing arguments to the callable object or function is fundamentally as simole as passing additional arguments to the std::thread constructor

## But it is improtant to bear in mind that by default the arguments are copied into internal storage , where they can be accessed by the nwely created thread of execution , and the passed to the callable object of function as r-values

## This is done even if the corresponding parameter in the function is expecting a reference 

```c++
void f (int i ,std::string const& s);
std::thread t (f,3,"Hello");
```



# Sharing Data Between Threads 

## if you are sharing data between threads, you need to rules for

Which thread can access which bit of data

when and how any updatas are communicated to the other threads that care about that data

The ease with which data can be shared betwwen multiple threads in a single process is not only a benefit - it can also be a big drawback

asynchrows    squchrowous

modifying修改



# Protecting Shared Data with Mutexes

it is nice if you could mark all the pieces of code that access the data structure as mutually exclusive such that if any thread is running one of them, any other thread that tries to access that data structure has to wait until the first thread is finished

That makes it impossible for a thread to see a broken invariant except when it is 



# CLASS 21

engines:program 程序 process 进程

detach 彻底剪短

管理线程（功能性）fore ground, background

nonfuction function poteniat可能的

dailing程序回收时而其他后续进程还在使用

执行main是foreground detach是为转background

terminating终端

``` c++ 
#include <unistd.h>
```

in this case, the new thread associated with my-thread is probaby still running when opps() exits bacause you have explicitly decided not to wait for it by calling detach()

if the threads is still running, the next call to do_somethingg (i) accesses an already destroyed variable

it is easy to make the mistake with multithreaded code bacause it is not necessiarity immediately apparent that this has happened 

implicit 隐藏

one common way to handle this scenario is to make the thread function self-contained and copy the data into the thread rather than sharing the  data

it is a bad idea to create a thread within  a function that has access to the local variables in that function unless the thread is guaranteed to finish before the function exits

you can ensure that the thread has completed execution before the function exits by joining with the thread.

























































 





















