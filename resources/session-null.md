## Why C++ not  C
`C++` by default comes with a lot of handy utilities. For example, `std::vector`, `std::unordered_map`, `std::pair` and so on. So, you don't have to waste your precious time reinventing the wheel from scratch in a pivotal moment.


## Primitives
| Data type          | Stride  | Range                                                    |
| ------------------ | ------- | -------------------------------------------------------- |
| char               | 1 byte  | -128 ... 127                                             |
| short              | 2 bytes | -32,768 ... 32,767                                       |
| int                | 4 bytes | -2,147,483,648 ... 2,147,483,647                         |
| long long          | 8 bytes | -9,223,372,036,854,775,808 ... 9,223,372,036,854,775,807 |
| float              | 4 bytes | 3.4E +/- 38                                              |
| double             | 8 bytes | 1.7E +/- 308                                             |
| unsigned char      | 1 byte  | 0 ... 255                                                |
| unsigned short     | 2 bytes | 0 ... 65,535                                             |
| unsigned int       | 4 bytes | 0 ... 4,294,967,295                                      |
| unsigned long long | 8 bytes | 0 ... 18,446,744,073,709,551,615                         |


## I/O Stream
`iostream` is `stdio.h` equivalent in C++. Provides basic input, output functionalities

* Taking input
```c++
#include <iostream>
int main()
{
        // Single variable input
        int a;
        std::cin >> a;

        // Multiple variable input
        int x, y;
        std::cin >> x >> y;

        return 0;
}
```

* Taking output
```c++
#include <iostream>
#include <string>

int main()
{
        std::string prompt = "value of pi";
        float pi = 3.141592f;

        std::cout << prompt << ": " << pi;

        return 0;
}

```

** To know more about iostream visite the link below** <br>
Reference: https://cplusplus.com/reference/iostream/


## `std::` !?
Whenever we encounter `std::<something>` in out code, then it means that it's a part of standard library. And this standard library utils are `namespaced` under `std`

## `std::endl` and why not to use
`endl` stands for end-of-line. So what it does is create a new line. But `\n` also does the same job right? Now here's the fact, `std::endl` and `\n` are not the same.

`std::endl` creates a new line and also flushes the new line buffer where `\n`   only creates a new line. So `std::endl` typically takes longer time than `\n`.