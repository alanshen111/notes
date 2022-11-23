# Cpp_01_Basics

> Note that all notes on C are applicable to C++, as C++ is largely as superclass of C. Then why do you need to know C? Legacy code, and your job description says so.

### Compilation

You can't just run a `.cpp` file, you need to compile it and make an executable. This is commonly done with `g++`.

```Shell
g++ -o executable hello.cpp
```
To run, simply use:
```Shell
./executable
```
### The `main()` Function

```C
int main(int argc, char **argv) {
  // do stuff
  return 0;
}
```

#### Arguments

- `argc`: argument count
- `argv`: argument vector, with `**argv` being a pointer to the first element of the array. An equvialent and more explicit representation can be `*argv[]`.

So, if you ran your program like this:

```Shell
./program hello world
```

- `argc` = 3
- `argv` = [`./program`, `hello`, `world`, *null*]

Note that the last element is always a null pointer (`argv[argc] == null`).

#### Returning
- `main()` must return int
- returning 0 indicates success, any other integer should be considered an error flag


#### Simpler

This argument-less `main()` function is also perfectly valid, if you don't care about arguments.

```C
int main(void) {
  // do stuff
  return 0;
}
```
Note that there can only be one `main()` function in a program.
