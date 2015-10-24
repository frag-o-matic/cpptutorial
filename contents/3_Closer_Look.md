## A Closer Look at `Hello, World!`

Now that we have a program written, compiled and running, its time take a look at its innards and learn what makes the whole thing work. We'll examine the program in two steps to get a better understanding of what is going on:

* **Understanding the Source** : Taking a closer look at the various pieces that make up a C++ *source file* will yeild a deeper insight of the structure of C++ programs and help surface the meaning behind some of the alphabet soup in `hello.cpp`.
* **Debugging the Binary** : Examining the running program is a good first step in introducing debuggers and the debugging process, which is an indispensible tool for diagnosing programs that compile fine but don't quite work the way they're supposed to.

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

* The most important part of the *source file* is the bit following the `#include` statment. The line in question:
    ```cpp
    int main()
    ```
defines the "entry point" for the `Hello, World!` example. An entry point is where a program begins execution. `main()` is by convention the entry point for all C++ programs. If your program does not have a `main()`, the compiler will complain.

* Near the very end of `main()` is the `return` statement:
    ```cpp
    return 0;
    ```
Although not strictly necessary, having a `return` statement at the end of `main()` is a good habit to get into. The `return` marks the end of `main()` and the value `0` following the `return`, indicates a successful run of your program.

#### Miscellaneous Syntax Elements

C++ code usually has a bunch of recurring punctuation marks peppered all over the *source file*. Some really obvious ones are:

* The `;` (semicolons) that appear at the end of each *statement* and since there's usually one *statement* per line, there's usually one at the end of line. These semicolons are the programmer's way of saying "I'm done with this bit, let's move on to the next" to the compiler. Missing out on semicolons will cause the compiler to produce errors.

* The `{` and `}` (curly-braces) specify the extent of statements that make up `main()`. Generally, these are used to group `statement`s into a `block`. A `block` is a just a bunch of instructions that are treated as a single unit. The `block` is then treated as the extent for various other language constructs (such as conditionals, loops and functions). 

In C++ *whitspace* (spaces, tabs and newlines) is irrelevant by the compiler (which is different from say Python or Haskell) and therefore these markers are an easy way to indicate the end of a *statement* and for demarcating the beginning and end of a group of *statement*s that need to be treated as a block.

##### Note on Compiler Errors

While compiling the `Hello, World!` example, there might be errors reported by the compiler, `gcc`. Please take a look at [this](contents/misc_gcc_errors.md) note for additional info on some common errors and how to go about understanding and fixing them.

### Debugging the Binary

#### What is Debugging?

*Debugging*, a task that goes hand-in-hand with programming, basically involves running a program binary in a controlled manner with the aim of resolving defects. A *defect* (aka *bug*) is an oddity in program behaviour and occurs when the program does not perform its intended task or behaves unexpected. The controlled environment for debugging can be created with the aid of a special program called a *debugger*. See [here](https://en.wikipedia.org/wiki/Debugging) for a more formal and thorough treatment of *debugging* and [here](https://en.wikipedia.org/wiki/Debugger) for details on debuggers.

For the purposes of this tutorial, the *debugging* process will be used as a tool to aid understanding of what is really going on with the sample programs and as brief introduction to the things to try when needs to be done when a C++ program does not perform as expected. The [GNU Debugger](https://www.gnu.org/software/gdb/) aka `gdb` will be used to demonstrate the debugging process.

#### Changes to Facilitate Debugging

Before we can begin debugging the "Hello, World!" binary `a.out`, a recompilation is necessary. This time around, we'll instruct the compiler, to add additional information for facilitating debugging. The new command for compiling with debug information is as follows: 
  ```
  g++ --std=c++11 -ggdb -O0 hello.cpp -o a.out`
  ```
The two new options here are:
* `-ggdb`, which instructs the compiler to generate and include detailed information for debugging. Normally, debug information is kept to a minimum in order to reduce the size of generated `a.out` file.
* `-O0` which instructs the compiler not to perform any optimizations (this flag is not really necessary, since it is usually the default). Optimizations are clever tricks that the compiler pulls behind the scenes to make it run faster. 
  <sup>**PS:** Just to avoid any confusion, this option is the capital alphabet `O` followed by the numeral zero `0`.</sup>

#### Launching the Debugger

WIP 

#### Basics of Debugging

WIP

