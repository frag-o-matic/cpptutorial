### Index

#### A Taste of C++

0 [Introduction](contents/0_Introduction.md)

1 [Environment](contents/1_Environment.md)

2 [Hello, World!](contents/2_Hello_World.md)

3 [A Closer Look at Hello, World!](contents/3_Closer_Look.md)

4 [Abstraction, Blackboxes and Magic](contents/4_Abstraction.md)

#### Basic C++

5 C++ Language Features
  * Syntax, Keywords and other Minutiae
  * Types and Variables
   - Built-in Types: Integrals, Floating-points, Boolean and `void`
   - Type-deduction and `auto`
   - `const` variables
  * Operators
	- Arithmetic and Assignment
	- Logical and Comparison
	- Increment and Decrement
	- Precedence and Associativity
  * Loops
	- `for`, `while` and `do-while`
  * Functions and Lambdas
	- Motivation and Usage
	- Pass by Reference and `const` Parameters
	- Recursion
	- Function Overloading
 * User Defined Types
   - Encapsulation and `class`es
   - Access specifiers `public` & `private`
   - `static`, `const` and `mutable` members
   - Member Functions and the `const` suffix
  * Introduction to the Standard Library
  - Containers
	- `vector`s
	- `string` and `stringstream`
	- Range-based `for` and Iterators
  - Algorithms
	- `find` and `count`
	- `find_if`, `for_each` and `transform`
	- Introduction to Lambdas and inline Predicate Functions
  * Exceptions
	- Handling unexpected conditions
		- `throw`ing exceptions
		- `catch` blocks and cleanup
		- Where is `finally`?
	- `std::exception`
	- Exception Guarantees

#### Object Oriented Programming features of C++

6 OOP features in C++
  * Inheritance and code-level reuse
	- `protected` access specifier
	- Function Hiding
	- Multiple Inheritance
  * Polymorphism
	- Operators for User-defined Types
	- Function Overriding instead of Function Hiding
	- References as facilitators of Polymorphism
	- Achieveing Function Overriding with `virtual` and `override`
	- Preventing Function Overriding with `final`
	- Interfaces in C++ via Pure `virtual` Functions

#### The Rest of C++

7 Misc Topics in C++
  * Enumerations and `enum class`
  * Name collision and `namespace`s
  * Templates
  * Streams
  * Files

8 The `C` in `C++`
  * Overview of the Compilation Process
	- Stages of Compilation
	- Linkage & Visibility
  * Low-level and Machine dependent stuff
	- `<cstdint>` and integrals with fixed sizes
	- `volatile`, `static`-linkage and `extern`
  * Bitwise Operator and Hacks
  * `union`s and thier (ab)uses 
  * Arrays and Pointers
	- Arrays and `std::array` : The Lesser `vector`s
	- Pointers and the Heap 
	- Memory Management in C++ : Introducing `new` and `delete`

9 Pointers and Memory Management in C++
  * Raw Pointers in C++ and RAII
  * Smart Pointers and Ownership: `unique_ptr` and `shared_ptr`
  * The `this` Pointer
  * How `virtual` really Works
 
10 Another Look at the STL
  * Useful Standard Containers
	- `list`s and `deque`s
	- `map`s and `set`s
  * Useful Standard Algorithms
	- `swap`ping and `copy`ing
	- `fill`, `generate` and `rotate`

#### Real-world C++

11 Existing code & Legacy C++
  * Verbose Loops
  * Repeated `virtual`s and missing `override`s
  * Raw `new` and `delete`
  * `auto_ptr`s and Function Objects
  
12 Mixing with `C` code
  * `char*` and Friends
  * C-style I/O: `printf` and `scanf`
  * Name-mangling and `extern C`
  * Getting `vector`s and `string`s to play nice with C code
