# Type System in C++

Before we dive into type system let's take a brief look at what we have as types in the language.

## Rule to follow

In C++ we write a variable as follows:

```cpp
DATA_TYPE VARIABLE_NAME = VALUE;
```

We can only declare a variable in one line and give it a value in other place in the code like so.

```cpp
DATA_TYPE VARIABLE_NAME;
...
...
VARIABLE_NAME = VALUE;
```

Let's take an example; we can declare a variable of type `int` to showcase the usage:

```cpp
#include <iostream>

int main()
{
  int number = 3;

  std::cout << number << std::endl;

  return 0;
}
```

Let's run the code:

```bash
$ g++ main.cpp -o main && ./main
3
```

BTW you can get rid of `std::` in front of commands by `using namespace std;` but I don't recommend it ❌

```cpp
#include <iostream>

using namespace std;

int main()
{
  cout << "Hi" << endl;
}
```

Also the `return` statement is optional in `main`.

---

<br/>

Think a little about this code ⁉️:

```cpp
#include <iostream>

int main()
{
  int number;

  std::cout << number << std::endl;

  number = 5;

  std::cout << number << std::endl;

  return 0;
}
```

<br/>

---

## Types in C++

In short (as mentioned before) what types do to variables don't really matters, what matters is the size of the type that is allocated in memory.

The following is a list of most data types in the language with its size:

- `int`
- `float`
- `double`
- `char`
- `bool`

<!-- <table style="text-align:center;">
  <tbody>
    <tr>
      <th rowspan="2"> Type specifier
      </th>
      <th rowspan="2"> Equivalent type
      </th>
      <th colspan="2"> Width in bits by data model
      </th>
    </tr>
    <tr>
      <th> C++ Standart
      </th>
      <th> x64 - 64 bit
      </th>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;">
          <span class="t-c">
            <span class="mw-geshi cpp source-cpp"><span class="kw4">short</span></span></span>
        </div>
      </td>
      <td rowspan="4">
        <span class="t-c">
          <span class="mw-geshi cpp source-cpp">
            <span class="kw4">short</span>
            <span class="kw4">int</span>
          </span>
        </span>
      </td>
      <td rowspan="6"> at least<br> <b>16</b>
      </td>
      <td rowspan="6"> <b>16</b>
      </td>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;">
          <span class="t-c">
            <span class="mw-geshi cpp source-cpp">
              <span class="kw4">short</span>
              <span class="kw4">int</span>
            </span>
          </span>
        </div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;">
          <span class="t-c">
            <span class="mw-geshi cpp source-cpp">
              <span class="kw4">signed</span>
              <span class="kw4">short</span>
            </span>
          </span>
        </div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;">
          <span class="t-c">
            <span class="mw-geshi cpp source-cpp">
              <span class="kw4">signed</span>
              <span class="kw4">short</span>
              <span class="kw4">int</span>
            </span>
          </span>
        </div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;">
          <span class="t-c">
            <span class="mw-geshi cpp source-cpp">
              <span class="kw4">unsigned</span>
              <span class="kw4">short</span>
            </span>
          </span>
        </div>
      </td>
      <td rowspan="2">
        <span class="t-c">
          <span class="mw-geshi cpp source-cpp">
            <span class="kw4">unsigned</span>
            <span class="kw4">short</span>
            <span class="kw4">int</span>
          </span>
        </span>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;">
          <span class="t-c">
            <span class="mw-geshi cpp source-cpp">
              <span class="kw4">unsigned</span>
              <span class="kw4">short</span>
              <span class="kw4">int</span>
            </span>
          </span>
        </div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;">
          <span class="t-c">
            <span class="mw-geshi cpp source-cpp">
              <span class="kw4">int</span>
            </span>
          </span>
        </div>
      </td>
      <td rowspan="3">
        <span class="t-c">
          <span class="mw-geshi cpp source-cpp">
            <span class="kw4">int</span>
          </span>
        </span>
      </td>
      <td rowspan="5">
        at least<br>
        <b>16</b>
      </td>
      <td rowspan="5"> <b>32</b>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;">
          <span class="t-c">
            <span class="mw-geshi cpp source-cpp">
              <span class="kw4">signed</span>
            </span>
          </span>
        </div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;">
          <span class="t-c">
            <span class="mw-geshi cpp source-cpp">
              <span class="kw4">signed</span>
              <span class="kw4">int</span>
            </span>
          </span>
        </div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;">
          <span class="t-c">
            <span class="mw-geshi cpp source-cpp">
              <span class="kw4">unsigned</span>
            </span>
          </span>
        </div>
      </td>
      <td rowspan="2"> <span class="t-c"><span class="mw-geshi cpp source-cpp"><span class="kw4">unsigned</span> <span
              class="kw4">int</span></span></span>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;"><span class="t-c"><span
              class="mw-geshi cpp source-cpp"><span class="kw4">unsigned</span> <span
                class="kw4">int</span></span></span></div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;"><span class="t-c"><span
              class="mw-geshi cpp source-cpp"><span class="kw4">long</span></span></span></div>
      </td>
      <td rowspan="4"> <span class="t-c"><span class="mw-geshi cpp source-cpp"><span class="kw4">long</span> <span
              class="kw4">int</span></span></span>
      </td>
      <td rowspan="6"> at least<br> <b>32</b>
      </td>
      <td rowspan="6"> <b>32/64</b><br>
        depends<br>on the<br>compiler
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;"><span class="t-c"><span
              class="mw-geshi cpp source-cpp"><span class="kw4">long</span> <span class="kw4">int</span></span></span>
        </div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;"><span class="t-c"><span
              class="mw-geshi cpp source-cpp"><span class="kw4">signed</span> <span
                class="kw4">long</span></span></span></div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;"><span class="t-c"><span
              class="mw-geshi cpp source-cpp"><span class="kw4">signed</span> <span class="kw4">long</span> <span
                class="kw4">int</span></span></span></div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;"><span class="t-c"><span
              class="mw-geshi cpp source-cpp"><span class="kw4">unsigned</span> <span
                class="kw4">long</span></span></span></div>
      </td>
      <td rowspan="2"> <span class="t-c"><span class="mw-geshi cpp source-cpp"><span class="kw4">unsigned</span> <span
              class="kw4">long</span> <span class="kw4">int</span></span></span>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;"><span class="t-c"><span
              class="mw-geshi cpp source-cpp"><span class="kw4">unsigned</span> <span class="kw4">long</span> <span
                class="kw4">int</span></span></span></div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;"><span class="t-c"><span
              class="mw-geshi cpp source-cpp"><span class="kw4">long</span> <span class="kw4">long</span></span></span>
        </div>
      </td>
      <td rowspan="4"> <span class="t-c"><span class="mw-geshi cpp source-cpp"><span class="kw4">long</span> <span
              class="kw4">long</span> <span class="kw4">int</span></span></span> <br> <span
          class="t-mark-rev t-since-cxx11">(C++11)</span>
      </td>
      <td rowspan="6"> at least<br> <b>64</b>
      </td>
      <td rowspan="6"> <b>64</b>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;"><span class="t-c"><span
              class="mw-geshi cpp source-cpp"><span class="kw4">long</span> <span class="kw4">long</span> <span
                class="kw4">int</span></span></span></div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;"><span class="t-c"><span
              class="mw-geshi cpp source-cpp"><span class="kw4">signed</span> <span class="kw4">long</span> <span
                class="kw4">long</span></span></span></div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;"><span class="t-c"><span
              class="mw-geshi cpp source-cpp"><span class="kw4">signed</span> <span class="kw4">long</span> <span
                class="kw4">long</span> <span class="kw4">int</span></span></span></div>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;"><span class="t-c"><span
              class="mw-geshi cpp source-cpp"><span class="kw4">unsigned</span> <span class="kw4">long</span> <span
                class="kw4">long</span></span></span></div>
      </td>
      <td rowspan="2"> <span class="t-c"><span class="mw-geshi cpp source-cpp"><span class="kw4">unsigned</span> <span
              class="kw4">long</span> <span class="kw4">long</span> <span class="kw4">int</span></span></span> <br>
        <span class="t-mark-rev t-since-cxx11">(C++11)</span>
      </td>
    </tr>
    <tr>
      <td>
        <div style="text-align:left; width:auto; margin-left:auto; margin-right:auto;"><span class="t-c"><span
              class="mw-geshi cpp source-cpp"><span class="kw4">unsigned</span> <span class="kw4">long</span> <span
                class="kw4">long</span> <span class="kw4">int</span></span></span></div>
      </td>
    </tr>
  </tbody>
</table> -->

A very common way is to use the `sizeof` operator to know the size in bytes.

```cpp
#include <iostream>

int main()
{
  std::cout << sizeof int << std::endl;
}
```

Also we can use it as follows:

```cpp
#include <iostream>

int main()
{
  std::cout << sizeof(int) << std::endl;
}

```

We can also save some headaches by `#include <cinttypes>`.

It gives us a variety of types to use indicated by size of bits like `uint8_t`.
