# C++ 代码练习

## 仓库内容
学习侯捷老师的关于c++的系列讲解，将视频中的代码写下，并在代码的适当地方填写解释

> 1. [侯捷C++手把手教学(上),适合新手](https://www.bilibili.com/video/BV1aW411H7Xa?p=1)
> 2. [侯捷手把手教学C++(下)已补充完毕](https://www.bilibili.com/video/BV1sW411J7JQ?p=1)
> 3. [侯捷——C++11新特性](https://www.bilibili.com/video/BV1p4411v7Dh?p=1)
> 4. [【C++】C++ STL与泛型编程高级-侯捷](https://www.bilibili.com/video/BV1Yb411p7UK?p=1)
> 5. [侯捷 讲解C++内存管理（全60集）](https://www.bilibili.com/video/BV1it411g776?p=1)



## 知识点目录

**C++入门**

1. [头文件和类的声明](#头文件和类的声明)

2. [内联函数](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/complex.h#L11)

3. [构造函数-初始列](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/complex.h#L9)

4. [单例模式](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/Singleton.h)

   > 使用static修饰的变量保证单例，ctor函数放在private内 避免其他用户可以直接调用构造函数

5. [常量(const)成员函数](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/complex.h#L13)

6. [友元函数](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/complex.h#L25)

   > 一个对象的成员函数是该类其他对象的[友元函数](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/complex.h#L18)

7. [操作符重载](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/complex.h#L40)(忘记了的话查看[视频](https://www.bilibili.com/video/BV1aW411H7Xa?p=5))

   > 操作符重载就是重新定义操作符对应的函数，其中重载之后的返回值需要仔细考虑
   >
   > 例如 c+=3 重载+=之后 如果返回c对应的类的话就可以执行 b+=c+=4 
   >
   > 例如 cout << b << c 重载 << 之后 返回osstream 这样能继续输出。

8. [深拷贝和浅拷贝](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/string.h)

9. [拷贝构造](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/string.h#L39)和[拷贝赋值](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/string.h#L50)

10. [带指针对象的析构函数](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/string.h#L68)

11. [static成员变量](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/account.h)

12. [类模板](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/template-com.h)和[函数模板](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/account-test.cpp#L21)

13. [类继承](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/oop-demo.h)

14. [设计模式](https://www.bilibili.com/video/BV1aW411H7Xa?p=13)

15. [转换函数conversion-function](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/conversion-function.cpp)

16. [pointer-like class](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/pointer-like.cpp)

    > 补充智能指针的知识

17. [仿函数](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/function-like.cpp)

    > 继续学习

18. [namespace](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/namespace.cpp)

19. [成员模板](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/member-templete.cpp)

20. [模板特化](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/specialization.cpp)和[模板偏特化](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/partial-specialization.cpp)

21. [引用](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/reference.cpp)

22. [虚指针和虚表,动态绑定](#虚指针和虚表)

    > 当进行动态绑定的时候 就会安装下面的流程进行查找需要的函数,每个包含虚函数的对象在内存中都包含一个虚指针，这个指针是指向一个虚表 这个虚表可以看成一个数组 用来存这个对象的虚函数列表 然后依据虚函数的下标位置进行调用函数执行(*p->vptr[n])(p) 类似这样的调用

23. [new delete new[] delete[]](#new和delete)

24. [const](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/const.cpp)

25. C++11 new [auto](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/auto.cpp) [ranged-base](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/ranged-base-for.cpp) 

26. [variadic-templates](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/variadic-templates.cpp)(太难了)

27. [重载new()和delete()](https://www.bilibili.com/video/BV1sW411J7JQ?p=2)

    重载new 每个声明都要有独特的参数列，`Foo* pf = new(300, 'a')Foo`也可以重载delete() 只有当new所调用的ctor抛出异常才会调用这些重载版本的delete()

**C++11/14**

1. variadic-templates

2. Space in Template Expressions

   ```c++
   vector<list<int> > 在每个版本都适用
   vector<list<int>>  c++11后可以
   ```

3. nullptr and std::nullptr_t

   ```c++
   // C++11之后指针可以用 nullptr代替 0 or NULL
   void f(int);
   void f(void*);
   f(0); // call f(int)
   f(NULL); // call f(int) if NULL is 0 ambiguous
   f(nullptr); // call f(void*)
   ```

4. auto

   ```c++
   // #1 c++11 you can declare a var or an object without specifiying type by using auto
   auto i = 42;
   double f();
   auto d = f();
   // #2 auto用于2种情况 第一种是type太长 另一种是复杂的表达式 lambda 
   vector<int> v;
   // vector<int>::iterator pos;
   // pos = v.begin();
   auto pos = v.begin();
   auto l = [](int x) -> bool{}
   ```

5. Uniform Initialization (一致性初始化)

   > 原理: 编译器看到大括号 {t1,t2,tn}变做出一个 Initializer_list<T> 他关联到一个array<T,n> 调用ctor的时候 array内的元素被编译器被逐一赋值给ctor
   >
   > 但如果参数参数是个Initializer_list<T> 那就将参数打包直接发给函数

   ```c++
   // 如何初始化一个对象或变量，c++11 之前 新手很容易困惑 初始化可能发生在() {} =操作符
   // c++11 后统一一个方法 用{}
   int a[] = {1,2,3,4};
   vector<int> v{2,3,4,5,6};
   vector<string> city {
     "New York", "London", "Beijing"
   };
   comlex<int> c{4.0, 3.0}; // 等价于 c(4.0, 3.0);
   
   // c++ 11 之前
   Rect r1 = {3,7,&area};
   Rect r1(3,7,&area);
   ```

6. Initializer Lists

   ```c++
   
   ```

   

**STL**

## 头文件和类的声明

[示例代码](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B/complex.h#L1)

<p align =“center”>
	<img src="./imag/head-class.jpg" width="70%" height="50%" />
</p>

## 虚指针和虚表

[示例代码](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/object-model.cpp)

<p align =“center”>
	<img src="./imag/vtbl.jpg" width="70%" height="50%" />
</p>
<p align =“center”>
	<img src="./imag/vtbl2.jpg" width="70%" height="50%" />
</p>

## new和delete
[示例代码](https://github.com/yangsoon/cpptest/blob/master/c%2B%2B2/new-delete.cpp) 

<p align =“center”>
	<img src="./imag/new.jpg" width="70%" height="50%" />
</p>
<p align =“center”>
	<img src="./imag/delete.jpg" width="70%" height="50%" />
</p>
<p align =“center”>
	<img src="./imag/delete[].jpg" width="70%" height="50%" />
</p>
