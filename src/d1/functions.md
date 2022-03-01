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

## Examples

```cpp
int add(int x, int y)
{
  return x + y;
}

char get_next_char(char a)
{
  return a + 1;
}
```

We can call these functions in `main`:

```cpp
int main()
{
  std::cout << add(1, 2) << std::endl;
  std::cout << get_next_char('a') << std::endl;
}
```
