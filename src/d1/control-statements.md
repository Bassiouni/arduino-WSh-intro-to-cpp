# Control Statements && Ligical Operators

Nothing new here! All we need to know the logical operator and the syntax to write them.

## Types Of Control Statements

We have 2 types:

- if/else
- switch

### Switch Statement

We use `switch` to take action from a given number (yes `switch` only applies to _integral_ types).

The syntax is as follows:

```cpp
switch (NUM_TYPE_VARIABLE)
{
case VAL_FOR_CASE_1:
  // code
  break;

case VAL_FOR_CASE_2:
  // code
  break;

...

default:  // note that the `default` section of `switch` is optional
  // code
  break;
}
```

Dummy examples:

```cpp
#include <iostream>

int main()
{
  short x = '1';

  switch (x)
  {
    case 0:
      // code
      break;

    case 1:
      // code
      break;

    case '2': // note that we can check for `char` types as they are integral types
      // code
      break;
  }
}
```

### If/Else

There are 2 ways to write `if`: the one-line way and the block way

```cpp
// one-line way

if (EXP)
  CODE;
else
  CODE;

// block way

if (EXP)
{
  // code
}
else 
{
  // code
}

// Note we can mix between both

if (true) 
{
  // code
} 
else CODE;

if (true) CODE; 
else 
{
  // code
}
```

Note:

```cpp
else if (EXP) ...
```

is the same as

```cpp
else 
{
  if (EXP) ...
}
```

## Logical Operators

- AND -> `&&`
- OR -> `||`

__[__ NOT -> `!` __]__

Note that the NOT operator is not logical one but a bit-wise one.

__Exercise__: Improve the last question by accepting only positive values.
