# CPP函数的const

函数后加const表示该函数是**只读**函数，**该函数不可修改类的属性**。如果要修改数据成员的值，则编译器按错误处理。

函数后面加 const表示函数不可以修改class成员

```c++
int getValue() const;
```

前面使用const 表示返回值为const

```c++
const int getValue();
```



