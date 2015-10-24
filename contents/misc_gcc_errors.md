## Note on Compiler Errors

Compilation errors reported by `gcc` tend to technically accurate, but do little to help identify the underlying problem. However, dealing with compiler errors and correcting them is a necessary part of programming, so let's go over some common compiler errors that might crop up when the `Hello, World!` program listing is compiled.

* Missing out a `;` at the end of a line can lead and error message similar to this:
    ```
    hello.cpp: In function ‘int main()’:
    hello.cpp:8: error: expected `;' before ‘return’
    ```
The first line `hello.cpp:In function ‘int main()’` gives you a general idea of where the compilation failed. The beginning of the sentence, viz. `hello.cpp:8` indicates exact position of the error (`hello.cpp` is the filename and `8` is linenumber containing the error). The `error: expected ``;'` bit indicates what went wrong. Putting this all together, in this case, it seems that the compiler was looking for a `;` on line 8 in file `hello.cpp` but couldn't find one. Instead it found a `return` statement.

* Typos in the code may result in errors such as the following:
  ```
  hello.cpp:2: error: ‘lnt’ does not name a type
  ```
  Which seems to be a typo on line 2: `lnt` (starting with a lowercase `l`) was keyed in where `int` (starting with a lowercase `i`) was expected. Since C++ is case-sensitive, typing `int` with an uppercase `I` will result in a similar error:
  ```
  hello.cpp:2: error: ‘Int’ does not name a type
  ```
  Another common source of errors is missing out on delimiters, for example, if on Line 8 a `"` double quotation mark was missed, errors similar to:
  ```
  hello.cpp:8:13: warning: missing terminating " character
  hello.cpp:8: error: missing terminating " character
  hello.cpp: In function ‘int main()’:
  hello.cpp:12: error: expected primary-expression before ‘return’
  hello.cpp:12: error: expected `;' before ‘return’
  ```
  would be generated. In this case the very first line of the error message clearly spells out the nature of the problem (`warning: missing terminating " character`) and its location (`hello.cpp:8:13`, here `8` and `13` are the line and column numbers respectively). However, this simple mistake is interesting: Because the compiler does not stop till the entire file has been processed, a syntax error near the beginning can lead to syntax errors down the line.
  In this case the error messages ` hello.cpp:12: error: expected primary-expression before ‘return’` and `hello.cpp:12: error: expected `;' before ‘return’` are just a side-effect of the missing `"` on Line 8.
  
* Another possible source or error is naming the entry point something other than `main()`. This results in errors along the lines of:
    ```
    /usr/lib/gcc/i486-linux-gnu/4.3.3/../../../../lib/crt1.o: In function `_start':
    /build/buildd/glibc-2.9/csu/../sysdeps/i386/elf/start.S:115: undefined reference to `main'
    collect2: ld returned 1 exit status
    ```
Line 2 in this error message has the information we seek: `undefined reference to ``main'`.

Here is a [list](http://www.csee.umbc.edu/courses/undergraduate/202/fall04/Projects/CommonErrors.shtml) of some other common errors produced by `gcc`.
