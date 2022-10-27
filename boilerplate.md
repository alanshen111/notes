# Boilerplate

## The Main() Function 
---

```C
int main(int argc, char **argv) {
  return 0; 
}
```
- `argc`: # **arg**ument **c**ount
- `argv`: **arg**ument **v**ector
- 
So, if you ran your program like this:
```Shell
foo@bar:~$ cd ./program hello world
```
- `argc` = 3
- `argv` = [`./program`, `hello`, `world`, *null*]
  -  Note that the last element is always a null pointer.

- returning 0 indicates success, error otherwise
- main() must return int

```C
int main(void) {
  return 0; 
}
```
