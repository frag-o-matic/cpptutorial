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

