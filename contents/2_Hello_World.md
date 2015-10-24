## `Hello World!`

Now that the expectations and disclaimers are out of the way, Welcome to the tutorial on Modern C++! This is where the real fun begins and the code starts to flow. Let's start with a short overview of programming and get some basic terminology out of the way...

Programming is essentially instructing the computer to solve a problem. In this tutorial, the instructions or *source code* are written in C++ (well, duh!) in plaintext and stored in a file with a `.cpp` suffix or extension. This is a naming convention commonly followed for files containing C++ code. The file itself is usually called a *source file*.

The computer, which works with binary, cannot understand the contents of the *source file* as they stand. The next step therefore is to *translate* the contents of the *soruce file* into binary. This step is called **compilation** and is performed with the aid of a special program called a `compiler`.

During the *compilation* process, the `compiler` will check the contents of the *source file* to make sure they follow the various rules of C++. Any instructions that are out of line will be flagged as an *error* and the programmer **must** fix them. Once there are no *errors*, the `compiler` produces an executable file, usually called `a.out` on Linux systems, which can be run by the computer.

The above steps are common for the programs that we shall be writing over the course of this tutorial. Now, without further ado, let's get to the interesting bit.


### `Hello World!` in C++
It is [customary](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program) to begin the journey of learning a new language with the `Hello World!` program. One way to write this well known toy program in C++ is as follows:
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
### Getting it to Work
The program listing for `Hello World!` is just that: some words and punctuation arranged in a pretty manner. To get the computer to run this program, the following steps are necessary:
* ~~Type in~~ (who am I kidding?) `copy-paste` the program listing into a text editor and save it as `hello.cpp`
* Compile of the *source file* just created via the command:
    `g++ --std=c++11 hello.cpp -o a.out`
* Hopefully, there are no errors and a binary file named `a.out` is created
* Check that the program indeed works by running the binary via the command: `./a.out`
* This should run the program and print `Hello, World!` on the console

##### Running the program Online
[Here](http://cpp.sh/2vm5q) is "Hello, World!" program running online in CPP Shell.

#### Dealing with Errors
If there are errors during compilation, please take a look at [this](misc_gcc_errors.md) note for additional info on some common errors and how to go about understanding and fixing them.

#### Making sense of it all
This is just the beginning of things and naturally there will be stuff that is not very clear. The whole thing may even look hopelessly complicated, it is not. In the next chapter, we'll take a closer look at what makes up this toy program and how it works.

[Index](../Index.md)
