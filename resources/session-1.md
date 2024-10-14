## STL
STL is the abriviation of Standard Template Library. They are called standard because come built-in to
the C++ core language. STL comes pretty handly in the competitive programming scenario. Think of STL as
a fancy toolbox where you can find almost all of your necessary daily drive tools.


## Array (`std::array`)
To use `std::array` we have to include the array library in our code.
```c++
#include <array>
``` 

 - **Signature:** std::array<$data_type$, $size$> var_name;
 
**To know more about `std::array` visite the link below** <br>
Reference: https://cplusplus.com/reference/array/array/


## Why `std::array` and 
It has friendly value semantics, so that it can be passed to or returned from functions by value. Its 
interface makes it more convenient to find the size, and use with STL-style iterator-based algorithms.


## Iterator 
An iterator in C++ is a pointer-like object that points to an element of the STL container. They are 
generally used to loop through the contents of the STL container in C++. Don't mix it up with `raw c pointer`.

- Iterating over an array with `c++ iterators`
```c++
std::array<int, 5> arr = {3, 1, 4, 1, 5};
	
for (std::array<int, 5>::iterator it = arr.begin(); it != arr.end(); it++)
	std::cout << *it << endl;

```

Here, it is an iterator type (_i.e_ `std::array<T, N>::iterator`). Well that's a very long type name
to type. It get's even worse when we are creating an array of pairs. The the iterator type will be 
`std::array<std::pair<T, T>, N>::iterator`. 

So what's the solution for this situaltion? The answer is to use `auto`.

- Iterating over an array with `c++ iterators` - **Refined version**
```c++
std::array<int, 5> arr = {3, 1, 4, 1, 5};
	
for (auto it = arr.begin(); it != arr.end(); it++)
	std::cout << *it << endl;
```

- Some usefull methods: `at()`, `empty()`, `size()`, `fill()`
- Sort an array with `std::sort`. (_n.b you have to include algorithm library
to use this_).<br>
**Signature**: std::sort($L point$, $R point$)
```c++
#include <algorithm>

... ...

std::sort(arr.begin(), arr.end());
```

## String
The STL provides a special string container for human-language data, such as words,
sentences, and markup languages. Available in the `<string>` header.

- **How to use `std::string`!? Shut up fam! you already know.**
```c++
#include <string>

int main()
{
	std::string m = "Hi mom!\n"s;
	
	std::cout << m;
	
	return 0;
}
```

- Some usefull methods: `empty`, `length`, `front`, `back`
- Need **UTF-32** support on string? use `std::u32string`


## Comparing Strings
- Use `s == other` to compare two strings in $lexiographical$ order.
```c++
std::string m = "abc";
std::string n = "bac";

m == n ? cout << "same\n" : cout << "not same\n";

```

- Use `s.compare(other)` to compare between the value of strings.
```c++
std::string m = "abc";
std::string n = "bzc";

int cmp = m.compare(n);

if (cmp == 0)
	cout << "equal\n";
else if(cmp > 0)
	cout << "m is greater than n\n";
else
	cout << "m is less than n\n";

```