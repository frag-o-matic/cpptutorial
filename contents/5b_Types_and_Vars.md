### Types and Variables

#### Data
Computers work with **data**, which is just some information of interest that one is working with. Computers generally store data in **variables** in the main memory (aka RAM) as a bunch of bits. Often, data is also written out to files so that it may be used at a later point in time. At a very fundamental level, data has no inherent meaning associated with it: it is just a bunch of bits in memory or in a file. It is, therefore, upto the programmer to keep track of the various bits of data and determine which bunch of bits mean what. The concept of **datatypes** or **types** helps us do exactly that.

#### Types and Type-systems
To a computer all data is the same: a bunch of bits that it must operate upon. How then does the computer figure out the constraints and range of values applicable to a particular piece of data? It does that by keeping track of the **type** of data at each memory location. Data is typically held in variables and by associating some additional information with each variable, called the type, the computer and programmers can easily keep track of what a bunch of bits mean. 

The **type** of a variable is typically specified (either explicitly or via inference) in code and this information is then used by the compiler to determine what operations are valid on a given variable. The type, thus acts as a constratint on the various operations permitted on a piece of data. This constratint is very useful as it helps us avoid an entire calss of errors that may occur due to wrong usage of data (eg: using a string such as `"abcd"` as a number)
