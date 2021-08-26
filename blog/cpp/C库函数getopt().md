# C库函数getopt()

2021.08.26

<hr>

```c++
头文件 
  #include <unistd.h>
定义函数：
int getopt(int argc, char * const argv[], const char * optstring);
```

函数说明：getopt()用来分析命令行参数。

1. 参数argc 和argv 是由main()传递的参数个数和内容，同main函数中参数；
2. 参数optstring 则代表欲处理的选项字符串。

返回在argv 中下一个的选项字母，此字母会对应参数optstring 中的字母。

如果选项字符串里的字母后接着冒号":"，则表示还有相关的参数，全域变量optarg 即会指向此额外参数。
如果getopt()找不到符合的参数则会印出错信息，并将全域变量optopt 设为"?"字符, 如果不希望getopt()印出错信息，则只要将全域变量opterr 设为0 即可。

返回值：如果找到符合的参数则返回此参数字母, 如果参数不包含在参数optstring 的选项字母则返回"?"字符,分析结束则返回-1.