---
title: C++封装1
date: 2019-03-01 22:32:51
tags: 
    - C++
---
## 面向对象编程
* 对象: 任何具有状态和行为的实体。
* 类: 对象的集合
* 继承: 当一个对象获取父对象的所有属性和行为。提供代码可重用性，运行时多态性
* 多态: 当一个任务通过不同的方式执行时，即被称为多态性。使用函数重载和函数重写来实现多态
* 抽象: 隐藏内部细节和显示功能被称为抽象。使用抽象类和接口来实现抽象
* 封装: 将代码和数据绑定在一起的单个单元
* OOP相对于面向过程的编程语言: 开发和维护更加容易，面向过程的语言代码随着项目的扩大而增长
* OOP提供数据隐藏，而面向过程的编程语言中可以从任何地方访问数据
* OOP提供更加有效地模拟真实世界的能力
### C++对象和类
1. 对象是一个真实世界的实体，具有状态(数据)和行为(功能)。对象在运行时创建，是一个运行时实体
2. 对象是类的一个具体实例。类的所有成员都可以通过对象访问
`Student s1; //Student是类型，s1是引用Student的一个实例的引用变量`
3. 类是一个模板，可以从中创建对象。有字段，有方法，有构造函数等等
```
Class Student{
    public:
        int id;
        int age;
        String name;
}
// 一个具有三个字段的C++的类
```
4. C++类和对象示例
```
#include <iostream>
#include <string>
#include <string.h>
using namespace std;


class Student1
{
public:
    int num;
    int age;
    string name;
};

class Student2
{
    public:
        int num;
        int age;
        string name;
        void insert(int age1, int num1, string name1)
        {
            age = age1;
            num = num1;
            name = name1;
        }
        void display()
        {
            cout << num << endl;
            cout << age << endl;
            cout << name << endl;
        }
};

int main()
{
    // 创建一个类的实例，初始化对象并打印对象值
    Student1 s1;
    s1.name = "Sunjuan";
    s1.num = 101;
    s1.age = 25;
    cout << s1.num << endl;
    cout << s1.age << endl;
    cout << s1.name << endl;

    // 通过方法初始化和显示数据
    Student2 s2;
    s2.insert(18,102,"Sunj");
    s2.display();
    system("pause");
    return 1;
}
```
5. this指针
* 是一个const指针，指向当前的对象，可以访问当前对象的所有成员。this的值不能被修改，任何一切企图修改该指针的操作，如复制、递增、递减都是不允许的
* 用于将当前对象作为参数传递给另一个方法
* 用来引用当前类的实例变量
* 用来声明索引器
* this只能用在类的内部，通过this可以访问类的所有成员，包括private,protected,public
* 用于区分成员函数的参数和成员变量重名
* this只能在成员函数中使用，其他地方使用的非法的
* 只有当对象被创建后this才有意义，因此不能再static成员函数中使用
* this是成员函数的一个形参，在调用成员函数时，将对象的地址作为实参传递给this。this本质上是成员函数的局部变量

6. static关键字(面想过程的和面向对象的)
* 面向过程程序设计中的static涉及普通变量和函数
| 静态全局变量 | 静态局部变量 | 静态函数 | 
| :---: | :---: | :---: |
| 存储在全局数据区 | 存储在全局数据区 | 存储在代码区 | 
| 未经初始化的被程序自动初始化为0 | 在程序执行到该对象的声明处时被首次初始化，即以后的函数调用不再进行初始化 | 无初始化 | 
| 在整个文件内部可见，在文件外不可见 | 其作用域为局部作用域，当定义它的函数或语句块结束时，其作用域随之结束 | 静态函数不能被其它文件所用 | 
| 可以实现文件内部数据的共享，不能被其他文件所用，其他文件中可以定义相同的变量名称不会冲突 | 驻留在全局数据区，直到程序运行结束 | 其它文件中可以定义相同名字的函数，不会发生冲突 |

* 一个完整的程序的内存分布
| 代码区 | 全局数据区 | 堆区 | 栈区 | 
| :---: | :---: | :---: | :---: |
| 存放代码 | 静态数据，不会因为函数的退出而释放空间 | new产生的动态数据 | 函数内部的自动变量，函数退出空间释放 | 

* 面向对象的程序设计中的static涉及类
| 静态数据成员 | 静态成员函数 | 
| :---: | :---: | 
| 静态数据成员保存在全局数据区，只会被分配一次内存，被属于本类的所有对象所拥有 | 类的内部实现，被属于本类的所有对象所拥有 |
| 静态数据成员定义时要分配空间，所以不能在类声明中定义 | 普通成员函数都隐藏了一个this指针，指向类的对象本身，因为普通成员函数总是具体的属于某个类的具体对象。而静态成员函数不带this指针。出现在类体外的函数定义不能指定关键字static| 
| 静态数据成员和普通数据成员一样遵从public,protected,private访问规则 | 静态成员函数访问静态数据成员和访问静态成员函数，静态成员函数不能访问非静态成员函数和非静态数据成员，非静态成员函数可以任意地访问静态成员函数和静态数据成员 | 
| 静态数据成员初始化与一般数据成员初始化不同。静态数据成员初始化的格式为：＜数据类型＞＜类名＞::＜静态数据成员名＞=＜值＞ | 无需初始化 | 
| 类的静态数据成员有两种访问形式：＜类对象名＞.＜静态数据成员名＞ 或 ＜类类型名＞::＜静态数据成员名＞ | 调用静态成员函数，可以用成员访问操作符(.)和(->)为一个类的对象或指向类对象的指针调用静态成员函数，也可以直接使用如下格式：＜类名＞::＜静态成员函数名＞（＜参数表＞）调用类的静态成员函数。 |
| 静态数据成员没有进入程序的全局名字空间，因此不存在与程序中其它全局名字冲突的可能性 | 静态成员函数 | 
| 可以实现信息隐藏。静态数据成员可以是private成员，而全局变量不能 | 静态成员函数 | 

7. struct结构体
* 结构体是值类型而类是引用类型。
* 结构体可用于轻量级对象。
* 结构体定义前需要添加struct说明，

8. enum枚举
* 具有固定的常量集合的类
* 提高类型的安全性，可以遍历
* 很容易在Switch语句中使用
* 可以有字段，构造函数和方法

9. 友元函数
* 友元函数：定义在类的外部，但是有权访问类的所有私有和保护成员
* 定义方式，在类内声明，类外定义。类内声明就是在普通函数前加一个friend修饰。定义方式和普通函数相同。形式参数为需要访问的类。

10. 继承：自动获其父的所有属性和行为的过程。重用、扩展或者修改在其他类中定义的属性和行为
* 子类继承父类，派生类继承基类
* 重用父类的代码，提高代码的重用性
* 可以多级继承

11. C++聚合
* 聚合是一个进程，一个类将另一个类定义为实体引用（一个类作为另一个类的成员）

12. C++多态
* 编译时多态: 通过函数重载和操作符重载来实现，静态绑定或者早期绑定
* 运行时多态: 通过方法覆盖来实现，动态绑定或者后期绑定

13. 对象实例化的两种方式


14. 