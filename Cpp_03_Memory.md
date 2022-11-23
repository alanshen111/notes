# Cpp_03_Memory
## The Stack
The *stack* is a temporary storage. It makes programs very fast because you can quickly add and remove data. This function will add data to it's stack frame (a subsection of the full stack):

![](https://miro.medium.com/max/640/1*eVvNywgj1GKO3QgDiEH9pg.png)

and when the function ends, the stack frame is dumped.

##### The Heap
Sometimes the stack is too small. Instead of storing values on the stack, we can store **values** on the **heap**, and **addresses to those values** on the **stack**. This can be achieved through the use of pointers.

![](https://miro.medium.com/max/828/1*zf0ME9pmZfFUXekM_upFzw.png)

Languages without pointers do this for you automatically.

![](https://miro.medium.com/max/828/1*vpYAtlRU8HJdSpcTHvSSdg.png)

## Dynamic Memory Allocation

Here is an `int` array of size `n`.

```cpp
ptr = (int*) malloc(n * sizeof(int));
```
Ok, but why not just
```cpp
int arr[n];
```
Let's say `n` is user input. This means `n` is an undefined value while compiling, so `arr[n]` can not be compiled at compile time. `malloc` lets you allocate memory during runtime.
> In C++, try to use `new`/`free` isntead of `malloc`/`delete`, since it has much better behaviour, such as automatic type casting and throwing on failure. The only time you use `malloc` is if you ever need to `realloc`.

##### Memory Leaks

``` cpp
int* ptr = new int(5);
int* array = new int[10];
// code
// return without deallocating
return;
```
For every `new`, there should be a `delete`.
``` cpp
int* ptr = new int(5);
int* array = new int[10];
// code
delete ptr;
delete [] array; // without [], only the first element is freed
return;
```
Be careful about assignments as well.
``` cpp
char* str1 = new char [30];
char* str2 = new char [40];

str2 = str1; // Bad! Now the 40 bytes are impossible to free.

delete [] str2; // This deletes the 30 bytes.
delete [] str1; // Possible access violation.
```
