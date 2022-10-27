# Basics

### The Main() Function

```C
#include <stdio.h>
int main(int argc, char **argv) {
  // do stuff
  return 0;
}
```

#### Arguments

- `argc`: **arg**ument **c**ount
- `argv`: **arg**ument **v**ector

So, if you ran your program like this:

```Shell
./program hello world
```

- `argc` = 3
- `argv` = [`./program`, `hello`, `world`, *null*]

Note that the last element is always a null pointer (`argv[argc] == null`).

#### Returning
- returning 0 indicates success, error otherwise
- main() must return int

#### Simpler

This is also perfectly valid, if you don't care about arguments.

```C
#include <stdio.h>
int main(void) {
  // do stuff
  return 0;
}
```
Note that there can only be one main function in a program.
