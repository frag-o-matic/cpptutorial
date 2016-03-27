### Types and Variables

#### Data
Computers work with **data**, which is just some information of interest that one is working with. Computers generally store data in **variables** in the main memory (aka RAM) as a bunch of bits. Often, data is also written out to files so that it may be used at a later point in time. At a very fundamental level, data has no inherent meaning associated with it: it is just a bunch of bits in memory or in a file. It is, therefore, upto the programmer to keep track of the various bits of data and determine which bunch of bits mean what. The concept of **datatypes** or **types** helps us do exactly that.

#### Types
To a computer all data is the same: a bunch of bits that are operated upon and transformed into a different bunch of bits. How then does one check if a particular operation is valid for a bunch of bits? That is the question that **datatypes** (aka **types**) address.

Types, then basically are constraints that apply to piece of data -- these constraints could be things like the range of valid values, operations that are vaild/"make sense" on a give type etc. 

By associating a **type** with a variable (or an expression, an identifier, etc), we can use the type information to determine what operations are valid on a given entity. This check on what is vaild/"make sense" on a give type is called [type-checking](https://en.wikipedia.org/wiki/Type_system#Type_checking). Having strict type checking helps avoid an entire class of errors that may occur due to brainfarts: using a string such as `"abcd"` as a number.

#### Type Systems and Type Safety

A [typesystem](https://en.wikipedia.org/wiki/Type_system) is a bunch of rules that a language uses to define what entities get what type. To quote for the Wikipedia:

> A type system associates a type with each computed value and, by examining the flow of these values, attempts to ensure or prove that no type errors can occur. The particular type system in question determines exactly what constitutes a type error, but in general the aim is to prevent operations expecting a certain kind of value from being used with values for which that operation does not make sense (logic errors); memory errors will also be prevented

Most languages specify a type system, even if it is very simple and forgiving, as in the case of C. Having a type system is important it leads to [type safety](https://en.wikipedia.org/wiki/Type_safety), which is a fancy way of saying that a compiler/interpreter (or some other tool) can detect and flag errors, subtle or otherwise, that occur due to mismatching types. In many cases, mixing types, for example, treating a string as a number is meaningless. In other cases, this may be subtle, for example, mixing a floating point number and an integer may result in loss of data in the fractional part.

#### C++ and Type-Stuff
C++ has a [rich type system](https://msdn.microsoft.com/en-us/library/hh279663.aspx): variables, expressions and functions etc. all have specific types. The compiler generally checks and ensures that code uses the right type: one does not simply assign a `string` to an `int` in C++. Types in C++ are classified as:

**Built-in Types**: These are fundamental types the language defines right off the bat and available for the programmer to use. This category includes the very basic building blocks of a program, types such as `int`, `float` and `bool`.

or 

**User-define Types**: User-defined types, or UDTs, are as the name implies, types created by the user (programmer) to make their lives easier. Most non-trivial problems deal with data as a group and it makes sense to group this data into a new type that can be used throughout the program. C++ allows programmers to define datatypes as they see fit. Typically these would be `class`es or `struct`s.

We'll start with the built-in types now and delve into User-defined types as we progress.

#### Fundamental Types
The fundamental aka built-in types in C++ fall into four categories:

* **Character**: which are single character literals, for example, a letter such as `A` or an ASCII special character such as `\0` (the `NULL` character, which also happens to be the C-style string terminator). This category includes items that are `char` or `unsigned char`. The wide-character type `wchar_t` (more on this later) also fits in here.
* **Integral**: which are whole numbers of various sizes and could be `signed` (both negative and positive values possible) or `unsigned` (only zero and positive values possible). This category includes `short`, `int`, `long` and `long long` along with their variations. Additionally, sizes, difference etc are also likely to be integrals.
* **Floating-point**: which are types for storing reals (numbers with a whole and fractional part, such as `3.14`). In terms of types, this translates into `float`, `double` and `long double`. 
* **Boolean**: which is a simple type with two values: `true` and `false`. 

In addition, the language has two specific types:

* `void`: which denotes "no type"/"no applicable" or "incomplete type information"
* `nullptr_t`: which represents an invalid pointer

More details, see [types](http://en.cppreference.com/w/cpp/language/type) and [fundamental types](http://en.cppreference.com/w/cpp/language/types) on C++ Reference website.

It is upto the programmer to select the right type for an entity. All types have a typical size and a range of valid values associated with them, although this varies with operating systems and compilers.


#### Putting Types to Use
Types and typesystems exist to help programmers attach meaning to entities they use in code. The simplest entity one can use in code is a **variable**, which is an identifier for some location in the main memory. Variables in C++ must be associated with a type and the compiler checks the code to ensure that all variables are used within constraints applicable to the type they are associated with.

##### Declaration, Definition and Initialization
When using C++, these terms are used quite frequently. There is a [question](https://stackoverflow.com/questions/23345554/the-differences-between-initialize-define-declare-a-variable) on SO that deals with these terms. In a nutshell, here's what these terms mean:

* **Declaration**: Specify a new entity in your code. This could be a variable, a function or a user defined type
* **Definition**: Provide definition to a previously declared entity
* **Initialization**: Generally, this is declaration and definition done in one go, typically for an entity that you've introduced and want to use immediately

Let's take a look at how these terms apply to variables. Declaring a variable is very simple, one need only specify the type and an identifier for the variable, for example:

    int x;

Declares a variable `x` of type `int` and assigns an unspecified value to it, which is bad™. Let's try fixing that:

    int x;
    x=42;

These two statements declare `x` as an `int` and define (in this case assign) its value to be `42`. Now, `x` will contain the value `42` until someone changes it.

It is possible to combine the two statements into one via:

    int x=0;

The above statement declares and initializes `x` to `0`. This is how code is usually written. Declaring variables of other types is similar:

    char resp = 'N';
    float pi = 3.1416;
    bool ready = false;

But, there is one gotcha... one cannot declare variables of type `void`. The use of this type will be clear as we proceed further.

#### auto

The C++11 standard introduced the [`auto`](https://msdn.microsoft.com/en-IN/library/dd293667.aspx) keyword, which basically tells the compiler: "figure out the type for me". Usually variables are declared as so:

    int x = 0;   // the 0 says I'm an int, d' oh!

Which contains some repetitive information: the type of the value `0` used to initialize `x` is known to the compiler and can be used to **deduce** that `x` must be an `int`. When using C++11, one can (and usually will) write the above line of code as:

    auto x = 0;   // that 0 will make x an int

The `auto` form is preferable as it prevents you from having to repeat yourself (the type is apparent from the initializer value) and prevents you from having to type out long typenames such as: `std::map<int, std::vector<float>>::iterator` everytime you need to use them. There are other advantages as well.

##### Note about auto type-deduction
For most part, `auto` works as one would expect, but the rules of type-deduction when using `auto` are a bit obtuse in some circumstances, and it is recommened to be aware about them. A [chapter](https://www.safaribooksonline.com/library/view/effective-modern-c/9781491908419/ch01.html) in Scott Meyer's "Effective Modern C++" is dedicated to this topic.

#### `const`, `volatile` and Fixed Width Integrals

#### cv-Qualifiers
C++ allows the programmer to specify certain additional information when creating entities: one can choose to indicate if a given entity will remain constant throughout the program execution and/or if it can be modified outside of the program itself. This is done with the qualifiers `const` and `volatile` respectively.

    const int NUM_RECORDS = 42;

The line of code declares a constant named `NUM_RECORDS` with a value of `42`. The qualifier `const` indicates the that value of this variable is expected to remain unchanged through out the lifetime of the program. 

For variables that represent hardware resources (such as memory mapped I/O ports), one can expect that the value of the variable can change outside of the program itself and this can be expressed by the line of code below:

    volatile int portReg;

Both `const` and `volatile` are called ["type qualifiers"](http://en.cppreference.com/w/cpp/language/cv) and are applicable in various contexts in code and they allow the compiler to make specific decisions with regards to optimizing (or not) the code in question


##### Fixed Width Integrals

Typically C++ types have a typical width (and by extension a range of valid values), for example, an `int` is typically 4 bytes wide and can hold values from -2147483648 to 2147483647. However, the width of a type is not generally guaranteed and can vary across systems.

Integral types of known widths are useful in various contexts such as while bit-shifiting for computing checksums etc. and C++11 provides various integral types that are guaranteed to be atleast a specified number of bytes wide. For example a `int8_t` is guaranteed to be atleast 1 byte (8-bits) wide. Using fixed width integrals in code is very simple:

    int x = 42; // expecting an int to be 4-bytes wide
    int32_t anotherX = 42; // this one is guaranteed to be atleast 4-bytes wide

See [this](http://en.cppreference.com/w/cpp/types/integer) page for more info on fixed width types.
