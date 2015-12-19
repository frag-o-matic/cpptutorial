### C++ Language Features
C++ is generally thought of a "better C", since they both share a similar set of features, viz, general purpose languages targetting performance sensitive applications. While C++ does have a lot in common with C, it is a completely different beast with its own idioms and way of doing things. Here, we take a brief look at whats on offer for the C++ programmer, along with some "higher" level issues such as coding standards, libraries and compilers etc.

#### A General Purpose & Multi-Paradigm Language
C++ is described as a "general purpose" (meaning its versatile enough to be used for a wide variety of problem domains and hardware) and "Multi-Paradigm" (which means that it supports various conceptual models or "styles" of programming such as imperative, object-oriented and to some extent, functional). While this classification has nothing to do with the language itself, it does serve to highlight the flexibility of the language and the "many ways to skin a cat" aspect of it.

While C++ is quite flexible, much of C++ code follows the [object-oriented](https://en.wikipedia.org/wiki/Object-oriented_programming) style of programming. Newer code also tends to have some functional programming aspects (most notably via `auto` for type-inference and `lambdas` for algorithm predicates and the like) mixed in.

tl;dr: C++ is flexible enough to be used in many problem domains and the programmer can choose to mix-and-match various programming "styles" while writing C++ code. Usually, much of the C++ code out there is written in OO-style with some aspects of functional programming.

#### Coding Style and Standards
C++ is in widespread use and as such there is no "one-true" way of doing things. Users generally come up with their own styles and coding guidelines. A new effort is afoot to create a unified set of [core](https://github.com/isocpp/CppCoreGuidelines) langauge guidelines that help to enforce correct and safe usage of various language features. Other, more detailed standards that follow a "formulaic" approach can be found [here](https://isocpp.org/wiki/faq/coding-standards#coding-std-wars).

#### Compilers and Libraries
C++ is all about choices and there are more than a handful of (free and commercial) choices when it comes to compiling C++. A few of the popular ones are are:

* [GCC](https://gcc.gnu.org/) -- this is what we restrict ourselves to
* [Clang](http://clang.llvm.org/) -- a promising new upstart with cool features a better error reporting and 
* [MSVC](https://www.visualstudio.com/) -- the C++ compiler which is a part of the Visual Studio suite

The C++ language comes with a standard library, the Standard Template Library (aka STL). The STL has a lot of general purpose [stuff](http://en.cppreference.com/w/cpp/header): containers, algorithms and utilities such as I/O facilities. The STL is *huge* and we will only touch upon several introductory features of the STL.

Apart from the STL, there is a huge [list](https://github.com/fffaraz/awesome-cpp) of frameworks, libraries and the like for many problem domains. Consider looking at these rather than "rolling your own". A particularly useful library is [boost](http://www.boost.org/). Boost augments the STL with a lot of useful stuff.

#### C++ Minutae
We conculde the overview of the "C++ goodies" with a brief look at some minutiae of the language. These are necessary as we progress onwards to hands-on usage of the langauge and to understand some of the errors that the compilers spit out.

##### Case-sensitivity
C++ is case-sensitive, i.e `int`, `Int` and `INT` are 3 different entities.

##### Keywords
Keywords are words with a special meaning assigned to them. These words **MUST NOT** be used in your programs in ways other than their intended meaning. A nice list of C++ keywords can be found [here](http://en.cppreference.com/w/cpp/keyword).

##### Identifiers
An identifier is a name (sequence of characters, numners and the `_`), which are used to label various entities in the language. Generally, names of classes, functions and variables are identifiers. Identifiers must be unqiue, are case-sensitive and must begin with a non-numberic character. Details on identifiers can be found [here](http://en.cppreference.com/w/cpp/language/identifiers).

##### Statements and Expressions
A `statement` is an instruction to the compiler. Statements include instructions for branching, looping and executing other statements or functions. An `expression` is a statement that performs a calculation such as an assignment, arithmetic and/or logical operations. Further reading on [statements](http://en.cppreference.com/w/cpp/language/statements) and [expressions](http://en.cppreference.com/w/cpp/language/expressions).

##### Syntax and Semantics
*Syntax* deals with technical correctness of a piece of code (i.e set of `statements` and `expressions`) while *Semantics* applies to the correctness of intent or meaning of said piece of code. While compiling code, errors may be reported for violation of either of these properties.

* *Syntax Errors* occur when the programmer writes code that isn't valid within the constraints of the language.
* *Semantic Errors* occur when a valid construct doesn't "make sense".

A good overview of syntatic and semantic errors is presented [here](http://space.wccnet.edu/~pmillis/cps120/cps120_pgm_syntax.pdf).
