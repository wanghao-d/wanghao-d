# C++main函数参数理解

2021.08.26

<hr>

argc 是 argument count的缩写，表示传入main函数的参数个数；

argv 是 argument vector的缩写，表示传入main函数的参数序列或指针，并且第一个参数argv[0]一定是程序的名称，并且包含了程序所在的完整路径，所以确切的说需要我们输入的main函数的参数个数应该是argc-1个；
