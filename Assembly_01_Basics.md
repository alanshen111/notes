# Assembly_01_Basics
Coding in assembly languages involves directly manipulating computer memory. Examples will mostly be written in Linux x64 (which is Microsoft lingo for x86_64).
## Assemblers
`asm` files are assembled into object files. A notable assembler is [NASM](https://www.nasm.us/).
![](https://cs.lmu.edu/~ray/images/asmlink.gif)

## Syscalls
`syscall`s are basic library functions. When a `syscall` is reached, the computer checks `rax` for the function ID. If necessary, the computer will then check `rdi`, `rsi`, `rdx`, `r10`, `r8`, and `r9` for arguments, with `rdi` and `r9` being the first and sixth arguments, respectively.

[Here](https://chromium.googlesource.com/chromiumos/docs/+/master/constants/syscalls.md#tables) is a good resource for all the x64 `syscall` IDs, as well as their arguments and `man` pages.

Here is "Hello, World" in x64 assembly:

``` shell
nasm -felf64 hello.asm
ld hello.o -o hello
./hello
```
