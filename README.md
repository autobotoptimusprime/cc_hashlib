# cc_hashlib
* A C++ header-only hash algorithm library (including md5, sha1, sha256, sha224, sha384, sha512);
* Use this library like Python's hashlib;
* minimum required standard: C++11
* 这是一个header-only风格的C++哈希算法库 (包含md5, sha1, sha256, sha224, sha384, sha512等算法);
* 用法与Python的hashlib库类似
* 需要编译器支持C++11及以上的标准
## example/例子
* Use this library only including the header `hashlib`
* 仅需include头文件`hashlib`即可
```c++
#include "hashlib"
```
* Get md5 of a string by using `ccat::hash::md5`
* 使用`ccat::hash::md5`获取字符串的md5值
```c++
#include <iostream>
#include "hashlib"
auto main() ->int {
    ccat::hash::md5 m{"hello world"};
    std::cout << m.hexdigest() << '\n'; //result: 5eb63bbbe01eeed093cb22bb8f5acdc3
    return 0;
}
```
* And also you can use the method `update` or `operator<<` 
* 你也可以使用`update` 或 `operator<<`
```c++
#include <iostream>
#include "hashlib"
auto main() ->int {
    ccat::hash::md5 m{};
    m.update("hello world"); //or m.update("hello"); m.update(" world");
    std::cout << m.hexdigest() << '\n'; //result: 5eb63bbbe01eeed093cb22bb8f5acdc3
    return 0;
}
```
```c++
#include <iostream>
#include "hashlib"
auto main() ->int {
    ccat::hash::md5 m{};
    m << "hello world"; //or `m << "hello" << " world";`
    std::cout << m.hexdigest() << '\n'; //result: 5eb63bbbe01eeed093cb22bb8f5acdc3
    return 0;
}
```
* Other hash algorithms are used in the same way as `ccat::hash::md5`
* More hash algorithms will be supported in the future
* 其它算法的用法与`ccat::hash::md5`相类似
* 后续将支持更多哈希算法
