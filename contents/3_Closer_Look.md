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

While compiling the `Hello, World!` example, there might be errors reported by the compiler, `gcc`. Please take a look at [this](misc_gcc_errors.md) note for additional info on some common errors and how to go about understanding and fixing them.

### Debugging the Binary

#### What is Debugging?

*Debugging*, a task that goes hand-in-hand with programming, basically involves running a program binary in a controlled manner with the aim of resolving defects. A *defect* (aka *bug*) is an oddity in program behaviour and occurs when the program does not perform its intended task or behaves unexpected. The controlled environment for debugging can be created with the aid of a special program called a *debugger*. See [here](https://en.wikipedia.org/wiki/Debugging) for a more formal and thorough treatment of *debugging* and [here](https://en.wikipedia.org/wiki/Debugger) for details on debuggers.

In a nutshell, the power and utility of debuggers stems from the fact that they:

* can control the speed of execution of the program being debugged, which allows programmers can pause code exection and jump over parts of code they're not interested. Since computers are so fast, it is near impossible to identify the exact location and cause of *defects* in a program running at its usual speed (the "problem code" will already have executed by the time we realize what is going on). Jumping over parts no related to the problem at hand and pausing at places where the bug may possibly be hiding makes the whole process quicker. Thus, being able to control the speed and length of program execution is real handy when bug-hunting.

* allow looking at the state of the program being debugged, as it is running, which allows programmers to identify when exactly things being to go wrong. Looking at parts of a program, the path of execution that the program takes and the results of calculations it performs are all clues that can help zero-in on the cause of a *defect*. The debugger allows the programmer to take a good look at all these (and more).

Normal program execution doesn't afford this kind of control, although crude work-arounds can be applied to afford some level of control. These (and many, many other advanced) features in debuggers make them a highly indispensible tool.

While the main motivation for *debugging* is to identify (and fix) *defects*, it is also useful for observing how program execution really occurs. This information is really handy in many different situations, such as for identifying areas of improvement.

For the purposes of this tutorial, the [GNU Debugger](https://www.gnu.org/software/gdb/) aka `gdb` will be used for *debugging* the sample code, starting with the "Hello, World!" sample from the previous chapter.

#### Changes to Facilitate Debugging

Before we can begin debugging "Hello, World!" we'll need to pass additional command-line options to the compiler, so that additional information for facilitating debugging is added to the generated binary:
  ```
  g++ --std=c++11 -ggdb -O0 hello.cpp -o a.out`
  ```
A brief description of what these two options do is given below:
* `-ggdb` instructs the compiler to generate and embed detailed information for debugging within the generated binary. Normally, debug information is kept to a minimum in order to reduce the size of generated `a.out` file.
* `-O0` which instructs the compiler not to perform any optimizations. Optimizations are clever little tricks that the compiler pulls behind the scenes to make your code run faster (this flag is not really necessary, since it is usually the default).
  <sup>**PS:** Just to avoid any confusion, this option is the capital alphabet `O` followed by the numeral zero `0`.</sup>

#### A Taste of Debugging

After the *source file* has been re-compiled with the above options, we're ready to go. The debugger can be invoked via the command line by pass the name of the binary to be debugged as a parameter:
  ```
  test@test-desktop:~$ gdb a.out
  ```
After printing a bunch of information, the following prompt is displayed:
  ```
  (gdb)
  ```
Which indicates that the debugger is ready to accept commands, which are simple English words like `start`, `step` and `continue`, from the programmer. These commands instruct the debugger to perform various actions and afford a lot of control over the binary being debugged. For example, typing the command `start` at the prompt will begin running the binary being debugged:

  ```
  (gdb) start
  Breakpoint 1 at 0x80486c5: file hello.cpp, line 7.
  Starting program: /home/test/a.out 
  main () at hello.cpp:7
   
  (gdb) 
  ```
However, instead of printing `Hello, World!` and terminating, as it normally would, we see that the debugger has begun executing the program, but stopped just after entering `main()`. This feature of the debugger which allows the programmer to pause the program at a specific place, such as just after entering `main()`, is called a *breakpoint*. True to their name, *breakpoint*s are positions in code (usually identified by a line number: `file hello.cpp, line 7`, in the listing) where the debugger "breaks" (or pauses) program execution and allows the programmer to run more commands (presumably to poke around and look at the state of the running program). We'll see later how to specify and use *breakpoint*s for debugging at a later time. `start` essentially is short hand for "add *breakpoint* in `main()`".

After `start`ing debugging (or pausing at a different `breakpoint`) we can use the command `step` to have the debugger execute one source-line and stop right after that:

```
(gdb) step
Hello, World!
8		return 0;
```
This feature called *single-stepping*, allows running the program "line-by-line", thus giving the programmer an opportunity to analyse what the program does as each line of code executes. This feature is quite useful for identifying excatly where deviations from expected behaviour occur. 

We can continue `step`ping thorugh the program till it terminates normally:

```
(gdb) step
9	}
(gdb) step
0xb7d5f775 in __libc_start_main () from /lib/tls/i686/cmov/libc.so.6
(gdb) step
Single stepping until exit from function __libc_start_main, 
which has no line number information.

Program exited normally.
(gdb) 
```

We can also let the program run to completion, just like when it does without a debugger, via the `continue` command:

```
(gdb) start
Breakpoint 3 at 0x80486c5: file hello.cpp, line 7.
Starting program: /home/seed/a.out 
main () at hello.cpp:7
7		std::cout<<"Hello, World!"<<std::endl;
(gdb) continue
Continuing.
Hello, World!

Program exited normally.
(gdb)
```

Although not very useful for this particular instance, the `continue` command resumes normal execution until another *breakpoint* is encountered. This feature thus allows the programmer to "jump" over large portions of the source code which are irrelevant to the problem at hand, because it . We'll take a closer look at this feature in the topics to come.

After *debugging* is complete, we can exit the debugger and return to the command-prompt, via the `quit` command, like so:
   ```
   Program exited normally.
   (gdb) quit
   test@test-desktop:~$
   ```

[Index](../Index.md)
