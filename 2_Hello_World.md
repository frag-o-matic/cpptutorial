### Hello World

The well known "Hello, World!" program in C++:

    #include<iostream>
    int main()
    {
      std::cout<<"Hello, World!"<<std::endl;
      return 0;
    }

When run, this program prints out the line "Hello, World!" on screen and terminates. See [this] (https://en.wikipedia.org/wiki/%22Hello,_World!%22_program) for background on Hello World programs.

### Getting it to Work
To get the computer to run this program, the following steps are necessary:
* Type the program in a text editor and save it as `hello.cpp`. The `.cpp` is a naming convention that identifies the file as plain-text containing C++ source code.
* Compile the code to obtain a runnable binary. This is achieved by the following command:
`g++ --std=c++11 hello.cpp -o a.out`
* Run the binary, named `a.out` by running the following command:
`./a.out`
* This should run the program and print `Hello, World!`

#### Note on Online Compilers
There are a lot of websites that allow users to compile and run C++ programs via thier web-browsers. Some common ones are [ideone](https://ideone.com/) and [codepad](http://codepad.org/). For the purposes of this tutorial [CPP Shell](http://cpp.sh/) will be used to execute sample progams. This website allows users to enter input for programs. [This](http://cpp.sh/8h5dk) is the "Hello, World!" program running in CPP Shell.
