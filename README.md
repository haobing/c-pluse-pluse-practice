# c-practice
练习C++
只有用static修饰的成员函数才可以不用申明对象，直接用类：：函数的形式访问
例子：
class tim{
static void pri(void)
{
cout<<"fsdadfd"<<endl;
}
};
可以直接调用tim::pri函数运行。
STL容器：
我们能够定义的容器的类型有三个限制：

1元素类型必须支持等于操作符；（对于类类型struct或class，即指等于号==重载）

2、元素类型必须支持小于操作符；（对于类类型struct或class,即指小于号<重载

3、元素类型必须支持一个缺省值（对于类类型，即指缺省构造函数）；

例子：
struct people{
	int age;
	int sextype;
	char name[20];
	bool operator<(const cont &man) const
	{
		return age<man.age;
	}
	bool operator==(const cont &ma) const
	{
		return sextype==ma.sextype;
	}
};

如果要把静态成员数据设为私有，该如何访问？
通过公有静态成员函数访问。
注意：设置了静态成员变量，要给静态成员变量设置初值

初始化列表的初始化变量顺序是根据成员变量的声明顺序来执行的。

虚函数就是允许被其子类重新定义的成员函数。
虚函数采用了一种虚调用的方法，虚调用是一种可以在 只有部分信息的 情况下 工作的机制，特别允许我们调用一个只知道接口而不知道其 准确类型的函数，但是如果要创建一个对象，你势必要知道对象的准确类型，因此构造函数不能为空
虚函数是非常有效的，但不能把每一个函数都声明为虚函数.
因为虚函数是有代价的，由于每个虚函数的对象都需要维护一个V表，因此使用虚函数时会产生额外的系统开销，如果是一个很小的类，且不想派生其他的类，那么根本没有必要使用虚函数。

子类重新定义父类虚函数的做法，称为重写。
重写的函数必须有一致的参数表和返回值。
重载是指编写一个与已有函数同名但是参数表不同的函数

宏，内联函数，模板都可以在编译时解析，但是虚函数不可以，他必须在运行时才能确定

多态是通过继承和虚函数实现的
