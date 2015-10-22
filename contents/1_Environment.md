### Environment

This section deals with the operating system and environment used for creating and executing code from the tutorial. Several tools used during development are also discussed briefly.

### Tools of the Trade

To create and run C++ applications we need, at the very least a text editor (to write our source code in) and compiler (to translate the source code into instructions that the computer can understand). Acutally, the complier a bunch of smaller programs working together to convert your source code into machine instructions, more on this later.

A number of additional tools will be used depending on the size of the project and number of people working on it. These are not of much importance for the purposes of this tutorial (section "Misc Tools" and later) and are dealt with here for expository purposes.

### Setup

Linux is the OS of choice for running the programs in the tutorial. Further, it is assumed that a recent version of [clang](http://clang.llvm.org/) or [gcc](https://gcc.gnu.org/) compiler is available for use. Ubuntu users can install the required stuff by executing the following command:

`sudo apt-get install build-essential`

This command will install the `gcc` compiler and its dependencies. Examples in this tutorial have been compiled with `gcc`.

### Misc Tools

Developing non-trivial software in C++ often requires some additional tools as well. The most important ones are:

* version control - to keep track of various code and configuration files. git recommeneded
* a [debugger](https://en.wikipedia.org/wiki/Debugger) - to diagnose program crashes and bugs. [gdb](https://www.gnu.org/software/gdb/) or [lldb](http://lldb.llvm.org/) recommended, depending on compiler in use
* a memory checker/profiler - to detect runtime issues and measure performance. [valgrind](http://valgrind.org/) recommended

Larger projects, tend to deploy additional tools such as:
* a build system - which is responsbile for fetching and building various modules that make up a project in the right order. Eg: [automake](https://www.gnu.org/software/automake/) or [cmake](https://cmake.org/)
* a pretty printer - for formatting source code as per project standards and guidelines. Eg: [Artistic Style](http://astyle.sourceforge.net/) or [clang-format](http://clang.llvm.org/docs/ClangFormat.html) 
* a static analyzer - to detect common mistakes and potential use of language features in an unsafe way. Eg: [cppcheck](http://cppcheck.sourceforge.net/) and [clang-analyzer](http://clang-analyzer.llvm.org/)

Other tools for collaboration, code-review and package and release management etc are also often used on larger project, but these are language agnostic and often driven by the software development methodology in use. Such tools are out of scope of this tutorial.

### Note on Online Compilers

There are a plenty of websites that allow users to compile and run C++ programs via thier web-browsers. Some of the more popular ones are [ideone](https://ideone.com/) and [codepad](http://codepad.org/). For demonstrating various sample programs used in this tutorial, the online compiler at [CPP Shell](http://cpp.sh/) will be used. This website allows users to enter input for thier programs via thier browsers. It uses GCC 4.9.2 as the compiler compiler.

### Note on IDEs

There are a bunch of really good [IDE](https://en.wikipedia.org/wiki/Integrated_development_environment)s available for C++ development on Linux. Some popular choices are: [Eclipse](https://eclipse.org/cdt/), [Qt Creator](http://www.qt.io/ide/) [CodeLite](http://codelite.org/) and [Code::Blocks](http://www.codeblocks.org/). For this tutorial however, an IDE is neither necessary nor recommended. 

The code examples are short and concise to the point that advanced features offered by IDEs are really wasted on these short programs. Moreover, from a learning perspective a simple workflow (comprising of editing code in a text editor and compiling on the command-line) will help in grasping fully the process of creating and running C++ programs. Additionally, using [UNIX as the IDE](http://blog.sanctum.geek.nz/series/unix-as-ide/), helps stay true to the [UNIX philosophy](https://en.wikipedia.org/wiki/Unix_philosophy#Do_One_Thing_and_Do_It_Well).

PS: There is nothing inherently "good" or "bad" with using IDEs, while it is true that IDEs can make developers more productive by providing really quick ways for manipulating and navigating non-trivial codebases, it is also true that they "hide" a lot of the complexity behind wizards and GUI screens. Moderation and the use of the right tool for the right task is key. [reddit](https://www.reddit.com/r/programming/comments/1ywo5v/does_relying_on_an_ide_for_development_make_you_a/) and [./](http://developers.slashdot.org/story/14/02/24/1845209/does-relying-on-an-ide-make-you-a-bad-programmer) are in on this debate as well. Some other interesting links related to this dilemma are [here](http://programmers.stackexchange.com/questions/39798/being-ide-dependent-how-can-it-harm-me), [here](https://michaelochurch.wordpress.com/2013/01/09/ide-culture-vs-unix-philosophy/) and [here](http://radar.oreilly.com/2014/01/to-ide-or-not-to-ide.html).

### Note on Text Editors

A good text editor is an indispensible tool for developers. Most of the work that developers do involves manipulating text-- be it code, configuration files or documentation, therefore being proficient in a text editor will really help improve your producivity. Just stay clear of [editor fanaticism](https://en.wikipedia.org/wiki/Editor_war). 

There's a maddeningly wide choice of text-editors out there. If you're just starting out try a few common ones and pick one that you're comfortable with. Text-editors are more or less on par with each other in terms of features these days, and each has its own idiosyncracies. On Linux, the usual suspects are: [vim](http://www.vim.org/about.php) and [emacs](https://www.gnu.org/software/emacs/). For graphical environment users, there are editors such as [geany](http://www.geany.org/) and [gEdit](https://wiki.gnome.org/Apps/Gedit). Commerical software [SublimeText](http://www.sublimetext.com/) and [UltraEdit](http://www.ultraedit.com/products/ultraedit.html) are in the race as well.


