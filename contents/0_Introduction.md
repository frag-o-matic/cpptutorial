### Introduction

This tutorial is a short introdution to the C++ programming language and the modern style of writing C++. This section deals with some introductory material and (very briefly) the history C++.

### Pre-requisites

This tutorial assumes that you've had some exposure to programming and CS. It also assumes you're familiar with Linux and the CLI interface (will be updating later for Windows). Knowledge of C is not necessary. Complete beginners may have difficulty following along.

### History

C++ is a low/mid level language that supports several different styles of programming. In India, it is quite well known as a object-oriented language and is often [taught](http://www.insightiitb.org/2015/an-exclusive-interview-with-bjarne-stroustrup/) as the first or second programming language in undergraduate-level courses. C++ is quite an [old](https://en.wikipedia.org/wiki/C%2B%2B#History) language and [Bjarne Stroustrup](http://www.stroustrup.com/bio.html), the creator of this language started work on C++ back in 1979. 2015 is the 30th [anniversary](http://www.cpp-lang.io/30-years-of-cpp-bjarne-stroustrup/) of the release of CFront, the first generally available C++ compiler.

C++ has come a long way since its creation and is used today in production systems across a diverse range of industries. The language itself and the way it is used have evolved in different ways over the past couple of decades, however, the way it is taught hasn't changed much. Stroustrup, the creator of the language, has often expressed his concern at the way C++ is taught. See: [here](http://www.stroustrup.com/nantes-interview-english.html), [here](https://web.archive.org/web/20070322215259/http://slashslash.info/2006/08/bjarne-stroustrup-on-teaching-c.html) and [here](http://www.stroustrup.com/Myths-final.pdf).

### Why C++

Considering C++ is quite an old language it is natural to ask "Why would one use C++ today? Surely there are better alternatives...". [This](https://channel9.msdn.com/posts/C-and-Beyond-2011-Herb-Sutter-Why-C) talk by Herb Sutter provides the answer to this question quite succintly. In essence, C++ is *still* the king when performance matters. JetBrains and O'Reilly have a nice little [ebook](https://www.jetbrains.com/cpp-today-oreilly/books/Cplusplus_Today.pdf) along these lines.

### C++ Today

Modern C++, that is to say, C++ as standardized in [C++11](https://en.wikipedia.org/wiki/C%2B%2B11) and [C++14](https://en.wikipedia.org/wiki/C%2B%2B14) (with [C++17](https://en.wikipedia.org/wiki/C%2B%2B17) on its way) makes it really easy to write safe and high-performance programs. It is therefore quite important to un-lean C++ "of the old" and learn how to properly use "modern" C++.

Modern C++ is not just about new keywords and language features, although the new features form a significant part of the big-picture, it is the shift in the way code is written that is of paramount importance. Modern C++ is not written as a just "better C". It has its own distinct [idioms](https://channel9.msdn.com/Events/BUILD/BUILD2011/TOOL-835T)  and [style](https://github.com/isocpp/CppCoreGuidelines), following which makes is easy to write safe code, without taking any performance hits, as compared to "old style" C++ code.

While on this topic, it is important to know that "modern" C++ still maintains backward compatibility with "older" or "legacy" C++ code out there.
