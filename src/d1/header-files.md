# Header Files

For now we have been typing in one file, but this is a bad practice on the long run, so we need to modulize our code.

## Do We Have Multiple Types Of Files In C++?

Yes! Let me explain ... the first reason we have to deal with many number of files is to organise our code, and this has some benefits one of them is maintainability.

Compiling C programs requires you to work with five kinds of files:

- __Source files__: These files contain function definitions, and have names which end in `.c` by convention. Note: `.cc` and `.cpp` are C++ files; not C files. e.g., `foo.c`

- __Header files__: These files contain function prototypes and various pre-processor statements. They are used to allow source code files to access externally-defined functions. Header files end in `.h` by convention. e.g., `foo.h`

- __Object files__: These files are produced as the output of the compiler. They consist of function definitions in binary form, but they are not executable by themselves. Object files end in `.o` by convention, although on some operating systems (e.g. Windows, MS-DOS), they often end in `.obj`. e.g., foo.o foo.obj

- __Binary executables__: These are produced as the output of a program called a _"linker"_. The linker links together a number of object files to produce a binary file which can be directly executed. Binary executables have no special suffix on Unix operating systems, although they generally end in `.exe` on Windows. e.g., `foo` `foo.exe`

- __Libraries__: A library is a compiled binary but is not in itself an an executable (i.e., there is no `main()` function in a library). A library contains functions that may be used by more than one program. A library should ship with header files which contain prototypes for all functions in the library; these header files should be referenced (e.g; `#include <library.h>`) in any source file that uses the library. The linker then needs to be referred to the library so the program can successfully compiled. There are two types of libraries: _static_ and _dynamic_.

  - __Static library__:  A static library (`.a` files for POSIX systems and `.lib` files for Windows — not to be confused with [DLL import library files](https://msdn.microsoft.com/en-us/library/windows/desktop/ms682592(v=vs.85).aspx), which also use the `.lib` extension) is statically built into the program . Static libraries have the advantage that the program knows exactly which version of a library is used. On the other hand, the sizes of executables are bigger as all used library functions are included. e.g., `libfoo.a` `foo.lib`

  - __Dynamic library__: A dynamic library (`.so` files for most POSIX systems, `.dylib` for OSX and `.dll` files for Windows) is dynamically linked at runtime by the program. These are also sometimes referred to as shared libraries because one library image can be shared by many programs. Dynamic libraries have the advantage of taking up less disk space if more than one application is using the library. Also, they allow library updates (bug fixes) without having to rebuild executables. e.g., `foo.so` `foo.dylib` `foo.dll`

Check out this website for more info: <https://riptutorial.com/c/example/4361/file-types>.

In this book we will use only header files and source files.

## What Is A Header File?

From the name it's just a file, however it is written in a specific format to make the compiler able to work with it.

Header files are not some thing new, acctually we have been using one form the beginning it (`iostream`).

`iostream` is a header file that contains some code we want to use it, so we write <br>`#include <iostream>` at the _"head"_ of our file (that's a way to remember the name).

In header files we mostly put the signature of our functions.

First let's make sure we have 3 files in our folder: `myfile.h`, `myfile.cpp` and `main.cpp`. We will work on the previous "add" program.

In the header file (`myfile.h`) put your necessary includes and signatures.

```cpp
// myfile.h

inline int add(int, int, int);

inline int add(int, int);

inline double add(double, double);
```

In the source file implement your functions.

```cpp
// myfile.cpp

#include <myfile.h>

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
```

Now include your header file in `main.cpp`.

```cpp
#include <myfile.h>
#include <iostream>

int main()
{
  std::cout << add(1, 2) << std::endl;

  std::cout << add(1.1, 4.0) << std::endl;

  std::cout << add(1.3, (double)4) << std::endl;

  std::cout << (int)add(1.5, 4.3) << std::endl;
}
```

To run this new setup you need to feed the compiler with 2 files instead of one.

```bash
$ g++ main.cpp myfile.cpp -o main
```

```bash
$ ./main # this makes us run the code
3
5.1
5.3
5
```
