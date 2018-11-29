---
title: Installation
description: |
  Installing a C compiler
---

# Installing a C compiler

C is a compiled language. That means we need a program to convert our source code to an executable or library in binary format that contains instructions for your CPU.
The most commonly used compiler is [GCC](https://www.gnu.org/software/gcc/).

You are free to use any compiler and or environment that support the [C11](https://en.wikipedia.org/wiki/C11_(C_standard_revision)) language standard.

## To install GCC
- On MacOs via homebrew: brew install gcc. 
- On linux via your distribution package manager.
- On Windows. Install this via the minGW installer [mingw-get](https://osdn.net/projects/mingw/releases/p15522) and select the gcc-g++ package.

## Check installation

- Open a terminal window of your favorite shell and type `gcc -v`. This should show the settings and version of the gcc compiler.
- Create a new file called `hello.c` with the following content:

```C
#include <stdio.h>
int main() {
  printf("Hello world!");
  return 0;
}
```
- Compile the file with the following command: `gcc hello.c`
- When no output filename is given it defaults to `a` or `a.exe` on windows 
- Execute the file `./a` or `a.exe` or `./a.exe` depending on your shell.
- You should now see `Hello world!`.

There are many free and payed C Integrated Development Environments. Feel free to try different ones. 