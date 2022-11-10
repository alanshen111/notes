# Shell_01_Basics

### The Shell/Terminal

#### The Prompt

When you start the terminal, you will see a *prompt*.
```Shell
alan@computer:~$
```
- `alan`|name of the user, helpful info if using a shared computer
- `computer`|name of the computer
- `~`|the current working directory (home)

#### Commands
You can use the prompt to run some commands.
```Shell
alan@computer:~$ echo hello
hello
```
- `echo`|program to be run
- `hello`|argument supplied to the program

Note that commands are parsed by whitespace. If you would like to use whitespace or other special characters (e.g., a directory named `“My Photos”`), you can either quote the argument with `'` or `"`. This is why a lot of programs have trouble installing in folders named with special characters.

```Shell
alan@computer:~$ cd “C:\Users\alan\My Photos”
```
Alright, so how does the shell know what `echo` means?  If the shell is asked to execute a command that doesn’t match one of its programming keywords, it consults an environment variable called `$PATH`.

```Shell
alan@computer:~$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
alan@computer:~$ which echo
/bin/echo
```
We can see the printed `$PATH` is just a list of directories, separated by `:`s. When we run `echo`, the shell will search through these directories for a file with the name `echo`, and run it. The `which` command prints out the used directory.

#### Navigation

```Shell
alan@computer:~$ pwd
/home
alan@computer:~$ cd ..
alan@computer:~$ pwd
/
```
- `pwd`|print working directory
- `cd`|change directory
- `.`|current directory
- `..`|parent of curent directory
- `/`|the root directory
  - note that on windows, `C:\` is the root directory

```Shell
alan@computer:~$ ls -l /home
drwxr-xr-x 1 alan  users  4096 Nov 09  2022 folder1
```

- `ls`|list files
- `-l`|long format flag
- `drwxr-xr-x`|permissions
  - `d`|this file is a directory
  - `rwx`|`alan` can read, write and execute
  - `r-x`|`users` can read and execute only
  - `r-x`|anyone else can read and execute only

```Shell
alan@computer:~$ chmod +x folder1
alan@computer:~$ chmod a+x folder1
```
the above two commands do the same thing.
- `chmod`|change mode
- `a`|for everyone

#### I/O

```Shell
alan@computer:~$ echo qiuqiu > file1.txt
```
instead of `echo` outputting to the terminal, we output to `file1.txt`.
```Shell
alan@computer:~$ grep qiuqiu < file1.txt > file2.txt
```
`grep` will search for regex `qiuqiu` in `file1.txt`, and output to `file2.txt`.

#### Commands Summary
Command|Function
 -|-
 `echo`|prints arguments
`which`|prints the directory of a program
`pwd`|prints working directory
`cd`|change directory to home
`cd dir`|change directory to `dir`
`cd ..`|change directory to parent of curent directory
`ls -al`|list files with long format, including hidden files
`chmod +x`|give permission to executeto everyone
`rm`|delete file
`cp file1 file2`|copy `file1` to `file2`
`mv file1 dir`|move `file1` to `dir`
`touch`|create a file
`more`|outputs the contents of a file
`grep pattern file1`|search for `pattern` in `file1`
`locate`|finds the instances of a file
`ssh user@host`|connect on `ssh`
`date`|show date and time
`w`|show who is online
`whoami`|shows who you are 😳
