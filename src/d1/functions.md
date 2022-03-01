# Functions

I'm assuming that you know what functions are used for.

## How To Write A Function

```text
RETURN_TYPE FUNCTION_NAME() 
{
  BLOCK_OF_CODE;
}
```

```text
RETURN_TYPE FUNCTION_NAME(ARGS)
{
  BODY_OF_THE_FUNCTION;
}
```

Note that if we wrote it like this:

```text
RETURN_TYPE FUNCTION_NAME(ARGS);
```

```text
RETURN_TYPE FUNCTION_NAME();
```

We are not give it a body; this is called a _prototype_ in which we use the function signature only.

But note that the function should have a body.

## Example

```cpp
int add(int x, int y)
{
  return x + y;
}

char getNextChar(char a)
{
  return a + 1;
}
```

We can call these functions in `main`:

```cpp
int main()
{
  std::cout << add(1, 2) << std::endl; // 3
  std::cout << getNextChar('a') << std::endl; // b
}
```

## What About A Function With No Return Type?

In this case we use the `void` keyword.

```cpp
void fn()
{
  // ...
}
```

An example:

```cpp
#include <iostream>

char C = 'M';

inline void increment() // `inline` is for compiler optimisation
{
  C++; // lol
}

int main()
{
  std::cout << C << std::endl;

  increment();

  std::cout << C << std::endl;
}
```

## Function Overloading

The Meaning of _overloading_ is we can create multiple functions with the same name but with a different sifnature.

For example we created a function that adds 2 `int`s, we can create another one for `double`s, or a third one that adds 3 `int`s.

```cpp
#include <iostream>

inline int add(int n1, int n2, int n3)
{
  return n1 + n2 + n3;
}

inline int add(int n1, int n2)
{
  return n1 + n2;
}

inline double add(double n1, double n2)
{
  return n1 + n2;
}

int main()
{
  std::cout << add(1, 2) << std::endl; // 3

  std::cout << add(1.1, 4.0) << std::endl; // 5.1

  std::cout << add(1.3, (double)4) << std::endl; // 5.3

  std::cout << (int)add(1.5, 4.3) << std::endl; // 5
}
```

## Function Prototyping

In C++, the code of function declaration should be before the function call. However, if we want to define a function after the function call, we need to use the function prototype. For example:

```cpp
// function prototype
void add(int, int); // function prototyping

int main() {
  // calling the function before declaration.
  add(5, 3);
  return 0;
}

// function definition
void add(int a, int b) {
  cout << (a + b);
}
```

__!__ Example:

```cpp
// using function definition after main() function
// function prototype is declared before main()

#include <iostream>

// function prototype
int add(int, int);

int main() {
  int sum;

  // calling the function and storing
  // the returned value in sum
  sum = add(100, 78);

  std::cout << "100 + 78 = " << sum << std::endl;

  return 0;
}

// function definition
int add(int a, int b) {
  return (a + b);
}
```
