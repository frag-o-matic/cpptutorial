## A Close Look at `Hello, World!`

Now that we have a program written, compiled and running, its time take a look at some of the innards that make the whole thing work. The program will be examined in two ways:

* Understanding the Source : Examining the various pieces in the source code will a little more insight into the structure of C++ programs and the explore the meaning behind instructions that were keyed-in by rote.
* Debugging the Binary : Examining the running program will introduce debuggers and debugging and provide some insight into how programs really run.

### Understanding the Source

Let's take another look at the Hello, World! [program](http://cpp.sh/2vm5q) from the previous chapter:

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
As it stands, the above program can be broken down in to various parts, starting from the top (the first line of source), there are:

* The first 3 lines (each starting with a `//`), which are comments. Comments are handy little notes written by programmers, for programmers and are completely ignored by the compiler. Programmers usually use comments to explain the intent or purpose of code they've just written. In the above example however, comments are used to convey additional information (viz. the command for compiling the example) rather than explain its purpose. In C++, comments begin with `//` (two forward slashes) and continue upto the end of the line. C++ also supports multi-line comments that begin with `/*` and end with `*/` and span across multiple lines. Eg: 

    ```cpp
    /* Hello, World! Program
     File: hello.cpp
     Compile With: g++ --std=c++11 hello.cpp -o a.out */
    #include <iostream>
    ```
Demonstrates the use of multi-line comments. The change in commenting style makes no difference whatsoever to program (remember, compilers simply ignore comments).

* The `#include` statement is a directive for "pulling-in" code from other files. The filename to be "pulled-in" is enclosed between the two angle brackets (`<` and `>`). As the source file `hello.cpp` containing the example is processed, code from the file `iostream` gets "pulled-in". This "pulled-in" makes it easy to use simple text-based (command-line) I/O. In other words, `#include <iostream>` is a directive that "pulls-in" code allowing the programmer to display text on screen and read input from the keyboard.

* The most important part of the code is the like following the `#include` statment. The line:
    ```cpp
    int main()
    ```
defines the "entry point" for your code. The entry point is where program executing begins (i.e the starting point of your code). `main()` is by convention the entry point for all C++ programs. If your program does not have a `main()`, the compiler will complain, usually something along the lines of:
    ```
    undefined reference to `main'
    ```

* The end of `main()` is marked by the `return` statement:
    ```cpp
    return 0;
    ```
Although not strictly necessary, having a `return` statement is a good habit to get into. The value `0` following the `return`, indicates successful execution of your program.

#### Notes about Miscellaneous syntax elements

* The `;` (semicolons) at the end of each statement in `main()` serve to mark the end of one complete `statement`. Basically they're a Programmer's way of saying "I'm done with this bit, let's move on to the next" to the compiler. Missing out semicolons will produce errors similar to
    ```
     In function 'int test()': 8:3: error: expected ';' before 'return'
    ```
* The `{` and `}` (curly-braces) specify the extent of statements that make up `main()`. Generally, these are used to group `statement`s into a `block`. A `block` is a just a bunch of instructions that are treated as a single unit. The `block` is then treated as the extent for various other language constructs (such as conditionals, loops and functions). 

### Debugging the Binary
WIP
