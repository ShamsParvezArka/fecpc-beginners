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

Reference: https://cplusplus.com/reference/iostream/


## `std::` !?
Whenever we encounter `std::<something>` in out code, then it means that it's a part of standard library. And this standard library utils are `namespaced` under `std`



## Array
An Array is a group of similar elements.
DO I HAVE TO SAY MORE ABOUT ARRAY!? C'mon guys

* C-style array
```c++
#include <iostream>

#define SIZE 5

int main()
{
        int container[SIZE] = { 3, 1, 4, 1, 5 };
        container[3] = 333;

        for (size_t i = 0; i < SIZE; i++)
                std::cout << container[i] << std::endl;

        return 0;
}
```

* C++ standard array
```c++
#include <iostream>
#include <array>

int main()
{
    std::array<int, 10> container = { 3, 1, 4, 1, 5 };

    std::cout << container.size() << std::endl;
    std::cout << container.max_size() << std::endl;

    if (container.empty())
        std::cout << "array is empty" << std::endl;
    else
        std::cout << "array is non-empty" << std::endl;

    for (size_t i = 0; i < 10; i++)
        std::cout << container[i] << std::endl;


    return 0;
}
```

To know more about `std::array` click the link below
Reference: https://en.cppreference.com/w/cpp/container/array


## `std::endl` and why not to use
`endl` stands for end-of-line. So what it does is create a new line. But `\n` also does the same job right? Now here's the fact, `std::endl` and `\n` are not the same.

`std::endl` creates a new line and also flushes the new line buffer where `\n`   only creates a new line. So `std::endl` typically takes longer time than `\n`.


## Loops
Loops are the _black magic_ thing that does the same work over and over again. So far we only know about traditional loops. But there's another kind of loop that exists in `C++` . It's called **range based loop**.

* Traditional loop
```c++
#include <iostream>
#include <array>

int main()
{
    std::array<int, 5> container = { 3, 1, 4, 1, 5 };

    for (size_t i = 0; i < 5; i++)
        std::cout << container[i] << std::endl;

    return 0;
}
```

* Range based loop
```c++
#include <iostream>
#include <array>

int main()
{
    std::array<int, 5> container = { 3, 1, 4, 1, 5 };

    for (auto &i : container)
        std::cout << i << "\n";

    return 0;
}
```


## `auto` keyword
`auto` detects the desired data-type automatically in compile time. You might be thinking, _"Ow what a cool feature, maybe I should use this quite often!"_. **NO!** Don't use auto like that. It is created to resolve some special cases. Otherwise your codebase will turn into a dumpster fire.


## Passing reference with `&`
`&` is the C++ standard to pass a value/$fn$/object by reference. Pass by reference solves 2 major problems.
1. value doesn't get copied overtime.
2. we can use `this.something` instead of `this->something` and don't have to dereference with `*variable`.

But keep in mind that while manipulating with reference, it produces side-effects.

To know more about `side effects` click the link below
Reference: https://softwareengineering.stackexchange.com/questions/40297/what-is-a-side-effect


## Conditions

_This part is intentionally left blank_


## Tricks
- Swap two numbers without using a temporary variable.
```c++
void swap(int &a, int &b)
{
    a = a ^ b;
    b = a ^ b;
    a = a ^ b;
}
```

- Even-odd detection without $modulo$ operator
```c++
int is_even(int &n)
{
    return ((n & 1) == 1) ? 0 : 1;
}
```
**n.b** _make sure to wrap `n & 1` with parentheses like this `(n & 1)` Because comparison operator has a higher precedence than bitwise operator_
