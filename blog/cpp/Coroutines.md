# Coroutines

Coroutine 是一个能暂停运行而后恢复运行的函数。

Coroutine 是无堆栈的：它们通过返回给调用者来暂停执行，恢复执行所需的数据必须与堆栈分离独立存储。这意味着允许我们异步执行代码（无需显式回调处理非阻塞I/O），或者惰性计算无限序列的算法。

Coroutine 特征：

+ 使用co_await操作符暂停执行直到恢复

  ```c++
  task<> tcp_echo_server() {
    char data[1024];
    while (true) {
      size_t n = co_await socket.async_read_some(buffer(data));
      co_await async_write(socket, buffer(data, n));
    }
  }
  ```

  

+ 使用co_yield关键字暂停执行并返回数据

  ```c++
  generator<int> itoa(int n = 0) {
    while (true)
      co_yield n++;
  }
  ```

  

+ 使用co_return关键字完成执行并返回数据

  ```c++
  lazy<int> f() {
    co_return 7;
  }
  ```

协程不是系统级线程，可以认为协程是线程里不同的函数，这些函数之间可以相互**快速**切换。

协程和用户态线程非常接近，用户态线程之间的切换不需要陷入内核，但部分操作系统中用户态线程的切换需要内核态线程的辅助。

协程适用于 IO 密集型的任务。是编程语言（或者 lib）提供的特性，原生协程支持的语言有：c++20、golang、python 等。