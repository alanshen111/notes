# Cpp_02_Pointers
## Confusing Syntax
```c
int* p = &i;
int& r = i;
```
- *the pointer* `p` points to the *address of* `i`.
- *the reference* `r` refers to `i`.

```c
int foo(int *x){
   *x++;
}
```
the function `foo()` expects *a pointer* `x` as an argument. Inside the function, *the value* `x` *points to* is incremented.

## Pointers vs References

A reference is just a pointer that can not change.
```c
a = 4;
&b = a;
```
`b` is a reference to`a`. If `b` changes, so does `a`, and vice versa.
```cpp
a = 4;
*b = a;
```
`b` is a pointer to `a`. If `*b` changes, so does `a`, and vice versa. If `b` changes, it points to something else.

##### Passing by Value/Reference/Pointer

```c
int foo(int x){
   x++;
}
```
This does nothing, because x is just a value copy.
```c
int foo(int& x){
   x++;
}
```
This will increment the passed argument. As mentioned earlier, changes to references will change the refered value. Similarly, changing dereferenced pointers will also change their pointed value.
