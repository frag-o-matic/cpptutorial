## A Close Look at `Hello, World!`

Now that we have a program written, compiled and running, its time take a look at its innards and learn what makes the whole thing work. We'll examine the program in two steps to get a better understanding of what is going on:

* *Understanding the Source* : Taking a closer look at the various pieces that make up a C++ **source file** will yeild a deeper insight of the structure of C++ programs and help surface the meaning behind some of the **statements** ~~typed-in~~ `copy-paste`d earlier.
* *Debugging the Binary* : Examining the running program is a good first step in introducing debuggers and the debugging process, which is an indispensible tool for diagnosing programs that compile fine but don't quite work the way they're supposed to.

### Understanding the Source

Let's take another look at the `Hello, World!` [program](http://cpp.sh/2vm5q) from the previous chapter:

```cpp
// Hello, World! Program
// File: hello.cpp
// Compile With: g++ --std=c++11 hello.cpp -o a.out
#include <iostream>

int main()
{
  std::cout<<"Hello, World!"<<std::endl;
  return 0;
}
```
As it stands, the above program can be broken down into the following logically pieces, starting with the first line of source:

* The first 3 lines (each starting with a `//`), which are comments. Comments are handy little notes written by programmers, for programmers and are completely ignored by the compiler. Programmers usually use comments to explain the intent or purpose of code they've just written. In the above example however, comments are used to convey additional information (viz. the command for compiling the example). In C++, comments begin with `//` (two forward slashes) and continue upto the end of the line. C++ also supports multi-line comments that begin with `/*` and end with `*/` and span across multiple lines: 

    ```cpp
    /* Hello, World! Program
     File: hello.cpp
     Compile With: g++ --std=c++11 hello.cpp -o a.out */
    #include <iostream>
    ```
The change in commenting style makes no difference whatsoever to compiler (remember, compilers simply ignore any comments).

* The `#include` statement, immediately after the comments, is a directive for "pulling-in" code from other files. The filename to be "pulled-in" is enclosed between the two angle brackets (`<` and `>`) just after the `#include` directive. As the source file `hello.cpp` containing the example is processed, code from the file `iostream` gets "pulled-in" and pasted into `hello.cpp`. The compiler then processes code from both `iostream` and `hello.cpp` as if they were a single file. This method of pulling stuff in makes it easy to re-use pre-existing code saving both time and effort required for accomplishing common tasks. In the `Hello, World!` example, the `#include <iostream>` is a directive that "pulls-in" code from `iostream` which contains code allowing the programmer to display text on screen and read input from the keyboard.

* The most important part of the **source file** is the bit following the `#include` statment. The line in question:
    ```cpp
    int main()
    ```
defines the "entry point" for the `Hello, World!` example. An entry point is where a program begins execution. `main()` is by convention the entry point for all C++ programs. If your program does not have a `main()`, the compiler will complain, usually something along the lines of:
    ```
    undefined reference to `main'
    ```

* Near the very end of `main()` is the `return` statement:
    ```cpp
    return 0;
    ```
Although not strictly necessary, having a `return` statement at the end of `main()` is a good habit to get into. The `return` marks the end of `main()` and the value `0` following the `return`, indicates a successful run of your program.

#### Notes about Miscellaneous syntax elements

* The `;` (semicolons) at the end of each **statement** in `main()` serve to mark the end of one complete **statement**. Basically they're a Programmer's way of saying "I'm done with this bit, let's move on to the next" to the compiler. Missing out semicolons will produce errors similar to
    ```
     In function 'int test()': 8:3: error: expected ';' before 'return'
    ```
* The `{` and `}` (curly-braces) specify the extent of statements that make up `main()`. Generally, these are used to group `statement`s into a `block`. A `block` is a just a bunch of instructions that are treated as a single unit. The `block` is then treated as the extent for various other language constructs (such as conditionals, loops and functions). 

The semicolons and curly-braces are necessary because **whitspace** (spaces, tabs and newlines) is ignored by the compiler and there is no easy way to infer the end of a **statement** or identify the beginning and end of a group of **statement**s without these markers.

### Debugging the Binary
WIP
