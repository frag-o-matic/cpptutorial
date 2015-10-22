### Hello World

One way to write the well known "Hello, World!" program in C++ is as follows:
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
When run, this program prints out the line "Hello, World!" on screen and terminates. See [here] (https://en.wikipedia.org/wiki/%22Hello,_World!%22_program) for background on "Hello, World!" program.

### Getting it to Work
To get the computer to run this program, the following steps are necessary:
* Type the program in a text editor and save it as `hello.cpp`. The `.cpp` is a naming convention that identifies the file as plain-text containing C++ source code.
* Compile the code to obtain a runnable binary. This is achieved by the following command:
`g++ --std=c++11 hello.cpp -o a.out`
* Run the binary, named `a.out` by running the following command:
`./a.out`
* This should run the program and print `Hello, World!`

##### Running Sample
[Here](http://cpp.sh/2vm5q) is "Hello, World!" running in CPP Shell.
