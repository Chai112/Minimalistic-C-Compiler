# Minimal-C Programming Language & Compiler
### Made by Chaidhat Chaimongkol, starting on 27 August 2019

## About
This is a personal project of mine of trying to teach myself...
1. how compilers work
2. how to write assembly (for an x86_64 Intel architecture)
3. modifying the C programming language

it's a fun challenge.\
\
I aim to develop a very simple, easy to read, inefficient compiler which compiles my variant of C (called Minimal-C or Min-C)
into x86_64 assembly as a *.o* file. No optimisations, as little confusion as possible (I hope) so that other people can look
at the source code and understand what on earth is going on. 

## Install
Mac & Windows are OK, tested on Mac\
Please download the repository and cd into it via console prompt or terminal.\
Make sure [GNU Make is installed](http://gnuwin32.sourceforge.net/packages/make.htm), do
```
make
```
Source code will be compiled by GNU Make into an executable, mcc.\
Run the executable with -h flag for instructions.
```
./mcc -h
```
## Minimal-C
"*C is too powerful*" - no one ever.\
Minimal-C (Min-C) is my take on a simplified, derated version of the C Programming language.\
Mainly made because I neither got the skill or patience to fully follow the C ISOs to call it a 'C Compiler'. 
\

**Capabilities**
* preprocessor statements and macros (`#include`, `#define`, `#ifdef`, etc.)
* standard Min-C library (`<minclib>`)
* comments (`/`, `/*`, `*/`)
* data types (`char`, `short`, `int`, `double`)
* arthimetic (`+,` `-`, `\*`, `/`, `%`) with parentheses
* equality testing (`!=`, `==`)
* pointers (`*`, `&`)
* *very* limited use of arrays
* *very* limited use of strings (char arrays)
* basic data structures (structs)
* code structures & scope (`{`, `}`)
* functions
* if statements
* control flow (`for`, `while` loops)
* running system commands
* user I/O

That's it.


## Min-C Compiler (MCC)
Compiles Min-C into x86_64 assembly *.o* files then asks linker to link into binaries\
**What it does**
1. reads input char by char, being lexed into tokens
2. preprocesses and parses one by one into an Abstract Syntax Tree in one pass
3. generate an Intermediate Representation based on that AST
4. assemble code from the IR, as an *.o* file
5. ask the system's linker (ld) to link the file. I ain't writing that.
