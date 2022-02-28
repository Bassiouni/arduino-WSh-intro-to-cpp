# Hello World Program in C++

So let's write the first program in C++!

```cpp
// main.cpp

#include <iostream>

int main()
{
  std::cout << "Hello, World!" << std::endl;

  return 0;
}
```

__For now__ all we need to do is to write our in the `main` function

# How to run the code

First we took that C++ is a compiled language .. so we need some sort of a compiler to be able to run our code.

We have a variety of options like (for example):

- GCC [GNU C Compiler] (in Windows it is called MinGW)
- Clang/LLVM
- Visual Studio Community (for Windows users)
- TCC [Tiny C Compiler]
- 8c
- Intel C++
- IBM XLC++
- Turbo C++

For arm bases computing:

- Keil C++ compiler
- Texas Instruments code generation tools for C/C++
- MPLAB XC++ Compiler

If you choose Visual Studio you can simply run the project through the run button.

In this tutorial we will use GCC in the terminal.

GCC provides a program called `g++`, this is the C++ compiler!

# Let's Compile!

In the terminal we will write the following

```bash
$ g++ NAME_OF_FILE_CODE -o NAME_OF_OUTPUT_FILE
```

In our case we wrote a file called `main.cpp` .. so we will write:

```bash
$ g++ main.cpp -o main
```

Now if we look at our directory we will find two files `main.cpp` && `main`.

To run the program we write:

```bash
$ ./main
Hello, World!
```

Any code we will write we will make the same steps

---
# References

- [What is a compiler](https://en.wikipedia.org/wiki/Compiler)
- [GCC](https://gcc.gnu.org)
- [Visual Studio](https://visualstudio.microsoft.com/vs/features/cplusplus/)
