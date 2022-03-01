# The `const` keyword

`const` is sort of a promise that you promised that something will be _constant_ (that's it's not going to change!).

Note that at the end of the day it's just a promise and you can bypass that hole _"promise"_ thing, and you can break your promise just like you can in real life!

__Of course__ it's an advanced thing and we are not going to cover it here, however it should be mentioned.

So how can we use constants?

## `const` In Variables

## `const` In Pointers

## `const` In Functions

<!-- In C++ we have 2 types of constants: `const` and `constexpr`.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

The primary difference between `const` and `constexpr` variables is that the initialization of a const variable can be deferred until run time. A `constexpr` variable must be initialized at compile time. All `constexpr` variables are const. -->
