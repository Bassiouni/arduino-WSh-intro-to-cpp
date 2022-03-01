# Solution

```cpp
// hypot.h

inline double hypot(double a, double b);
```

```cpp
// hypot.cpp

#include <math.h>

#include "hypot.h"

inline double hypot(double a, double b)
{
  return sqrt(a * a, b * b);
}
```

```cpp
// main.cpp

#include <iostream>

#include "hypot.h"

int main()
{
  std::cout << hypot(3, 4) << std::endl; // 5
}
```
