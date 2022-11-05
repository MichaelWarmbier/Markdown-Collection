# Introduction to Computer Science & Programming

**Author**: Michael Warmbier<br>
**Last Updated**: November 5th, 2022<br>
**Version**: In-Progress

### What is this document about?

_Introduction to Computer Science & Programming_ is a educational document summarizing the concepts typically associated with an introductory class in Computer Science. The information contained within this document is meant to cover a large portion of what is covered in a typical college course; depending on the lecturer and the cirriculum of that specific course, topics may vary.

This document is intended to be a reference for studying, as well as any educational use. This document is _not a cheat sheet_. 

### What language does this document focus on?

All the implementational portions included use code and code examples intended for the **C++ programming language**.

# Section 1.0: Concepts to Understand

There are many concepts that one should be familiar _before_ programming. It might seem unnecessary, but understanding these concepts to some degree prior to getting into things may save you some confusion when trying to understand more complex topics down the line. Being a programmer does not just mean syntax-familiarity; it also means understanding how things work and how to take advantage of the tools you have.

  * [1.1.0: Definition of Computer Science](#11--definition-of-computer-science)
  * [1.2.0: What is Programming?](#12--what-is-programming-)
  * [1.3.0: Computer/Programming Language Hierachy](#13--computer-programming-language-hierachy)
  * [1.3.0: Binary, Hexadecimal & Numerical Systems](#13--binary--hexadecimal---numerical-systems)
  * [1.4.0: Compilers and IDEs](#14--compilers-and-ides)
  * [1.5: Languages Compiled, Assembled and Interpreted](#15--languages-compiled--assembled-and-interpreted)
  * [1.6.0: Hardware vs Software](#16--hardware-vs-software)
  * [1.7.0: Computers as Hardware](#17--computer-as-hardware)
  * [1.8.0: Scope of CompSci: What Can We Do?](#18--scope-of-compsci--what-can-we-do-)

## 1.01: Definition of Computer Science

In literal terms, Computer Science is **the study of computation, automation and information[¹](https://en.wikipedia.org/wiki/Computer_science)**. This, however, is an oversimplification of one of the broadest fields of study available. Computer Science contains a large scope of topics, most of which have their own dedicated professionals and careers. These disciplines can be theoretical or practical, and are not limited to the use or capabilities of computers themselves. 

Many fields within _Computer Science_ may be associated with others, such as Mathematics and/or Physics. These relationships can be a matter of perspective, such as with Discrete Mathematics, or instead a matter of concepts applied in different contexts. 

###### ¹ https://en.wikipedia.org/wiki/Computer_science

## 1.02: What is Programming?

_Programming_, essentially **writing instructions to get a result from a machine**, is a subcategory of Computer Science focused on creating _software_ used for practically any digital application; including, but not limited to scientific, mathematical and personal use.

Programming is used as a tool to create solutions using computation. Instructions are written by a _programmer_ and then through a system generally described as _compilation_, these instuctions are then converted into digital logic which is designed for use by physical _hardware_ to perform actions that lead to the desired result. In simplification, a program "speaks" to a computer and tells it what to do.

## 1.03: Computer/Programming Language Hierachy

The _programming language_ hierachy is a simplification of the process described in the previous section, wherein instructions are eventually read by a machine.

<p align="center"><img src="https://i.imgur.com/kvGAKRC.png"></p>

**Digital Logic**: hardware on a computer is capable of interpreting machine code and applying it physically through binary impulses. This is called digital logic. A modern computer can process millions of these impulses a second.

**Machine Code**: digital logic written as strings of binary, exclusively in 1s and 0s. Machine code and binary are _not_ the logic itself, but the closest representation of it that may be displayed as text.

**Low-Level Language**: almost direct translation of machine code into human-readable syntax. This language is almost always referred to as _Assembly_. However, _machine code_ may also be considered its own low-level language. Each statement within Assembly relies on an _opcode_ instruction and zero or more _operands_.

**High-Level Language**: a language that includes complex programming tools included within itself which typically would rely on large sums of low-level code, along with a more easy-to-read _syntax_. Concepts from low-level languages are built upon and simplified as much smaller and user-friendly instructions.

```
Some Popular High-Level Programming Languages
----------------------------------------------
C++ | C# | C
JavaScript
Java
Python
PHP
```

## 1.04: Binary, Hexadecimal & Numerical Systems

A _numerical system_ is a system for representing numbers. However, unlike other systems such as Roman Numerals, _positional numerical systems_, including our very own _decimal_ system, or base 10, are significantly easier for computers to read and understand. To simplify this process even further, we only ask that computers read as little as two digits `[0 - 1]`, rather than our human-standard ten `[0 - 9]`.

This two-digit system is called _binary_. Also known as base 2, binary is much harder for humans to understand, which is why its reserved for machines. Its logical simplicity makes the process of reading it much less strenuous for a computer. 

Additionally, there is another commonly used numerical system called _hexadecimal_, or base 16. Hexadecimal numbers require less digits as they increase in size, compared to decimal and binary. Because of this, its use is usually reserved for displaing values that may reach large quantities, like positions in memory, which can have hundreds of thousands of values. It uses digits `1 - 9`, like decimal, as well as `A B C D E and F`.

```
System       | Value
--------------------------
Decimal:       703
Binary:        1010111111
Hexadecimal:   2BF
```

###### Value included in this example is arbitrary. Any value within a positional numerical system may be translated mathematical to any others.

```
Name        |  Base  |  Digits
--------------------------------
Binary      | 2      | 0 - 1
Octal       | 8      | 0 - 7
Decimal     | 10     | 0 - 9
Hexadecimal | 16     | 0 - 9, A - F
```

### Binary Terminology

<p align="left">

**Bit (b):** a single binary digit. Either a `1` or a `0`.

**Nibble:** four binary digits.

**Byte (B):** eight binary digits. Each byte can have a range of `[0 - 255]`, or 256 possible values.

**Kilobyte (kB):** one thousand bytes. Sometimes represented as a **kibibyte (KB)**, or 1024 bytes instead.

**Megabyte (MB):** one million bytes.

**Gigabyte (GB):** one billion bytes.

**Terrabyte (TB):** one trillion bytes.

<p>

## 1.05: Compilers and IDEs

An _integrated development environment_, or _IDE_, is a specific type of software that provides an environment and tools for developers and/or programmers. It's important to note, however, that an IDE is _not_ what compiles code. While some IDEs (such as Visual Studio) may have a compiler built into them, the compiler may also be a separate application all together. 

High-level and low-level code is essentially text, stored in a text file which is denoted by a file extension to be read by a compiler as a specific language to then be compiled. Because of this, a program as simple as Windows' _Notepad_ can be used to write code. However, IDEs typically provide useful tools such as accurate searching, syntax highlighting, debugging and of course, a built-in compiler. 

```
Example of Common File Extensions:
----------------------------------
C++: .cpp
JavaScript: .js
Assembly: .asm
HTML: .html or .htm
```
###### Note: HTML is _not_ a programming language.

## 1.06: Languages Compiled, Assembled and Interpreted

While code being _compiled_ is a general description of what happens, there are differences in how this occurs in different contexts and programming languages.

**Compiled Languages**: a language that is compiled is turned into machine code, or binary, prior to being used. On Windows, this result is typically represented by a executable file, or exe. C++ is an example of a compiled language. They rely on compiler applications, such as g++. 

**Interpreted Languages**: a language that is interpreted is compiled _as it runs_, rather than preemtively. This allows for more flexible code, but also may lead to more issues that won't be caught until the code is in runtime, which may make debugging a more difficult task. Python is an example of an interpreted language. They rely on interpreters, which are usually built into applications such as web browsers.

**Assembled Languages**: An assembled languange is one that may be directly translated to machine code, through the use of an assembler application. This is typically only used in the context of the assembly language.

## 1.06: Hardware vs Software

_Software and hardware_ are both important aspects of computers that allow them to operate properly. While hardware is much more explicit, software is a more general term; adware, malware and firmware are all types of software.

While the suffix _ware_ is meant to refer to tools, it is easier to consider it a reference to a specific type of computer component or product. 

**Hardware**: physical devices located within the machine as part of its operation. These devices do not need to be permanent; even a USB is considered hardware.

**Software**: digital tools and applications that a computer can run and utilize. Software, unlike hardware (typically), has the potential to be malicious.

## 1.07: Computers as Hardware

The inside of a typical desktop computer can be easily isolated to a small number of parts that work together to maintain the machine.

**Motherboad (MB)**: the "circulatory system" of the computer. This device connects all the hardware together through paths known as _busses_ that transfer data and information.

<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b7/Computer-motherboard.jpg/220px-Computer-motherboard.jpg"></p>

**Central Processing Unit (CPU)**: the "brain" of the computer. Composed of several other smaller processing units, the CPU processes and calculates all the data the computer interacts with, and sends it to the appropriate location.

<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/d/dc/Intel_80486DX2_top.jpg" width="150"></p>

**Graphics Processing Unit (GPU)**: the "eyes" of the computer. Unlike the CPU, the GPU is _not_ necessarily required for the computer to operate. Its purpose is to take on the much more computationally intensive task of graphics processing for applications that utilize it.

<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/f/f3/Sapphire-Radeon-HD-5570-Video-Card.jpg" width="160"></p>

**Random-Access Memory (RAM)**: the "short-term memory" of the computer. RAM is fast, volatile (temporary) storage used to hold onto things the computer will need short-term.

<p align="center"><img src="https://5.imimg.com/data5/CY/FF/MY-12308096/computer-ram-500x500.jpg" width="150"></p>

**Storage**: the "permanent memory" of the computer. The storage is usually slower than the RAM, but is non-volatile and is used to store applications, the operating system and personal files. Several devices are storage devices, such as hard disk drives (HDDs) and solid state drives (SSDs). These types are non-removable (while the computer is powered), however flash drives, floppy disks and optical disks are examples of always-removable storage.

<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f8/Laptop-hard-drive-exposed.jpg/220px-Laptop-hard-drive-exposed.jpg" width="150">
</p>

**Power Supply Unit (PSU)**: the "heart" of the compuer. This device connects a power supply to you computer and handles the transfer of electricity.

<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/6/62/PSU-Open1.jpg" width="150"></p>

**Input Devices**: removable devices meant to interact with the computer in some fashion. Examples include a mouse, keyboard, microphone and a camera.

<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/2/22/3-Tasten-Maus_Microsoft.jpg" width="150"></p>

**Output Devices**: removable devices meant for the computer to interact with the user in some fashion. Examples include a monitor, speaker and a projector.


###### Other devices, such as CPU cooling fans and wifi adapers may also be attached to a computer. Regardless, those listed above are the most significant to understand.


## 1.08: Scope of CompSci: What Can We Do?

The scope map of Computer Science is broad. There are many disciplines to explore, study and interact with. Below are a list of a few of the significant and/or interesting ones.

<p align="center">
  <img src="https://i.imgur.com/YobenhI.jpg">
</p>

###### Credit: [Domain of Science](https://www.flickr.com/photos/95869671@N08/36231833334)

**General Programming**: the simple implementation of basic applications for general use.

**Website Development**: the development and design of front-end and back-end web applications.

**Software Engineering**: the complex design, implementation and management of sotware in a systematic fashion.

**Game Development**: the design of interactable and choice driven experiences, typically for entertainment.

**Mobile Development**: the design of software specifically for mobile devices.

**Data Science**: a combination of math and complex programming systems to exrapolate information and data.

**Information Technology**: the use of computers to store, exchange and retrieve information, typically within the context of businesses.

**Computer Engineering**: a branch of eletrical engineering focused on the components of computers.

**Theoreteical Computer Science**: a subset of computer science focusing on mathematic and abstract ideas such as logic and compuation.

**Networking**: the interconnections of devices through networks and servers to exchange information.

**Artificial Intelligence**: applications designed to display forms of intelligence through use of decision making and even machine learning.

**Virtual Reality**: simulation of realistic and directly interactable environments for use in entertainment, training and convenience.

**Discrete Mathematics and Logic**: branch of mathematics concerned with the study of objects that may only contain distinct values.

**Information Theory**: the study of storage, quantification and exchange of information.

**Cryptograpy**: the study of creating and solving codes, typically through algorithms for use of secure communication within networks and between peers.

# Section 2.0: Programming in Practice

Programming is logical in nature. This means that understanding how everything you type works will help you predict an exact outcome, similar to evaluating problems in mathematics. Syntax _may_ vary from language to language, however most high-level languages _share_ similar tools and keywords that have become standard in practice.

All code blocks within this section are, unless stated otherwise, written in C++.

**tba: table of contents**

## 2.01: Getting Started

Choosing a tool, or a set of them, for writing and compiling code may seem like a simple and almost irrelevant task; if the result is the same, does it even matter? However the environment that you choose may greatly impact your ability to understand what you're doing. It may seem appealing to choose an IDE such as _Visual Studio's_ to start working, since it's a very well-known and mainstream application. Maybe you'd prefer a cloud-based compiler, like _Replit_, which is easy to get started with and lets you save your code and access it from anywhere. Regardless of what you choose make sure you don't feel overwhelmed.

Most IDEs with built-in compilers will compile the code when you press "run". This produces an executable file of some kind, which will immediately be opened. By default, these types of applications will be opened in a _terminal_ or _console window_ application. These are the application associated with readining the compiled binary inside these files.

![img](https://i.imgur.com/oXbGKjf.png)


###### The Replit C++ IDE. On the right-hand side is the terminal output, on the left is the coding window and file explorer.

## 2.02: Process of Compilation

There are several types of file extensions that C++ compilers look for when creating code. At first, however, you will just be using one: `.cpp`.

C++ has a notoriously complex compilation process. However, this is mainly attributed to (optional) manual compilation. When simplified, the process is much easier to understand:

### Step 1: Preprocessing

There are several aspects of C++ that rely on preprocessing. Preprocessed code is code which is desginated to be added later. You often see this when using `#include` to include outside code. This step takes the files you asked for and inserts their code into the main document for you.

### Step 2: Compilation

After all the code is in one place, it is then compiled into Assembly code. Once compiled, it is assembled into binary. These files are referred to as object files.

### Step 3: Linking

Once compiled, the object files are then linked together for a final output. This output is either a **library** file, a file meant to house code to quickly be used in future projects, or an **executable**, a file specifically for executing an application.

### Result

When using an IDE built-in with a compiler, this entire process is done behind the scenes. When running your code, it is compiled and then opened, usually with a **command prompt** or **terminal**.

## 2.03: Programming Priors

Before you begin writing in any programming language, you should understand some common traits each of them _may_ include.

### Flow of Code

Most programming languages are meant to be read _line-by-line_. What this means is that when your computer reads your code, each line will be read in order. Take this code for example:

```c++
cout << "Hello"; // print "hello"
cout << "World"; // print "world"
```

This code print two words to the screen. Here's the output:

```
HelloWorld
```

If we reverse it instead:

```c++
cout << "World"; // print "hello"
cout << "Hello"; // print "world"
```

This becomes the output:

```
WorldHello
```

Understanding this is critical to **troubleshooting** and **tracing** your code. In some cases, the line being actively read will jump from one location to another. It's your job to understand when this happens in order to properly read the code from start to finish.

### Keywords

You'll often come across **keywords** when programming. Keywords are words reserved by the language for some built-in element. For example, with this **if statement**:

```c++
if (3 < x) // code goes here
```

`if` is one example a keyword. It is built in to almost any modern language and has the job of handling something that will be covered later called **conditional logic**. Because its a keyword, nothing else may share its name.

### Statements

A **statement** is a single instruction. In C++, a statement _almost always_ ends with a semicolon `;`. 

Statments typically are written on their own line, but can share a line as well:

```cpp
int x = 3; x = x + 4; cout << x;
```

In some cases, a statement will be followed by another statement before finishing on a semicolon. Or instead, a **code block**.

### Code Blocks

**Code blocks** are clusters of statements. This is usually done to group together instructions and avoid repetition:

```C++
if (x) // one statement

if (x) {
  // one statement
  // two statements
  // ..
}
```

Some languages, however, such as _Python_, do not rely on brackets to signify the scope of these code blocks, and instead use indentation:

```py
if x:
  # one statement
  # two statements
```
###### Note: this code is written in Python

## 2.04: Boilerplate Code

_Boilerplate code_ is code which is repetitive and obligatory. It's the type of code you will use over and over when programming. In the case of C++, its starter boilerplate code looks like this:

```C++
#include <iostream>

int main() {

  return 0;
}
```

This is where most of your applications will begin when writing them. Right now, if you run this code _nothing_ will happen, but the application will start and end with no errors. 

### main()

The "main function", shown above as `int main()`, contains all the code that is run when you start you application. Everything within the brackets `{ }` following its _decleration_ will be that code.

`return 0` is the statement that _ends_ the program. The value `0` can technically be replaced with any other integer, but typically isn't. The purpose of returning a value is for debugging. If a compiler that you are using tells you that your application finished with exit code `0`, that means it exited succesfully, with no issues. The keyword `int` at the beginning of the `main()` decleration is what determins an integer will be returned. This portion, however, is **non-negotioable**. Main functions _must_ return an integer. If no return statement is given, most compilers will automatically return a value of their own.

More details on functions and how they operate will be described in a later section.

###### Note: any code snippets shown without `main()`, unless otherwise stated, are implied to be written within it to avoid repetition.

### Header Code

Above your main function is code that is meant to provide information about your program. It does not contain code that the compiler will try to run automatically. This particular code is referred to as **header code**. Preprocessor statements, such as `#include` statements, are part of this header code. This code may also be isolated in its own **header file** with the extension `.h` rather than `.cpp` and included using the syntax `#include "path_to_file.h"`.

### Include

As mentioned in the "Process of Compilation" section, the **include** keyword is used to attach outside documents to your program through preprocessing. In this case, we included a standard **library**, a prewritten code packaged for us to use, named `iostream`. This library is almost always included with our install of a C++ compiler and is very important for a lot of the code we use when starting off.

`iostream` stands for "input-output stream" and will be what we rely on for input and output when beginner programming.

## 2.05: Comments

In coding, a **comment** is a portion of our document that is ignored when compiled. Its purpose is to create notes for either our future use or the future use of someone else who looks at our code.

C++ has two ways to define a comment:

Typing `//` will comment out everything on that line (a line is finished when you press the end-line, or enter, key). Any code written on this line will be ignored:

```cpp
// This was a triumph << "hello" << endl;
```

Typing `/*` will comments out _everything_ after it. That is, until it is connected by `*/`.

```cpp
/* I'm making a note here: huge success */ cout << "hello" << endl;
```

## 2.06: Output

In C++, there are two primary ways to print information to the screen.

`printf()`, which stands for **print formatted**, is a **function** that displays the text inside it to the screen.

And `cout`, which standsa for **character output**, outputs anything between it and a `<<` operator to the screen.

Both are contained inside the `<iostream>` library and require it to be used:

```cpp
printf("Hello");
cout << "World";
```

###### Note: Text in C++ _must_ be contained in quotes `"`. More is explained in the _Strings_ section.

Output:
```
HelloWorld
```

Both of these methods work, but they each have their own quirks. For the purpose of this document, however, we will strictly be using the more commonly used `cout` method.

When using `cout`, text strings may be chained together, concatenated, using the `<<` symbol:

```cpp
cout << "Chain" << "Me" << "Together";
```
A good way to visualize what is going on is to imagine the text being "pushed" by the arrows into "cout", representing the screen itself.

Also included in the `<iostream>` library is the `endl` object, which when used will print an endline character.

```cpp
cout << "This line" << endl << "That line";
```

Output:

```
This line
That line
```

Text isn't the only thing that can be output, we can also output numbers and small arithmetic equations as well:

```cpp
cout << 14 << endl;
cout << 64 + 92 << endl;
```

Output:
```
14
156
```

## 2.07: Variables

A **variable** is a reservation in memory which allows us to store and manipulate data. In C++, variables have _specific types_ that tell us what kind of data they are. They can also be defined as **constants**.

A **constant** is a variable that is _unable_ to be changed. It's declared by preemptively typing the `const` keyword:

```cpp
int x = 3; // we can change this later; a variable
const int y = 4; // this is permanent; a constant
```

The **data type** of a variable is declared _prior_ to its name. In the above example we used **int**, which is an **integer**, but there are several we can choose from. Here are some important ones:

| Syntax    | Name  |  Use | 
|-----------|-------|------|
| int  | Integer  |  Whole numbers |  
| float  |  Floating-Point |  Numbers with decimals |  
| double |  Double Precision Floating Point |  Numbers with a lot of decimals  |   
| char | Character  | A single character |  

### Integers `int`

An **integer** is a data type which stores whole numbers. This means that no matter what math is done before storing its result in an `int`, it will never contain decimal precision.

### Floating-Point `float`

A **floating-point number** is a number that may include floating-points, or decimals. However, it may also store whole numbers, which will typically be represented with a `.0` at the end. For example, the integer `6` would be represented as `6.0`.

### Double Precision Floating-Point `double`

A **double** is almost exactly the same as a **float**. The only difference being how many decimals it can have, or more accurately, how precise it may be.

### Character `char`

A **character** is a symbol that we can write/read as text. These symbols are contained within **single-quotes**:

```cpp
char myCharacter = '@';
```

### Vocabulary

There are several words to remember when understanding variables:

**Declare**: declaring a variable means stating that it exists. Declared variables do _not_ need to have data immediately assigned to them.

```cpp
int myInt;
```

**Initialize**: a variable is initialized when given a value for the first time. This can be done _after_ declaration, or _during_ it.

```cpp
int myInt = 3;
```

**Define**: a variable is defined when it is given a value, regardless of whether or not its the initial value.

```cpp
int myInt = 6; // Declared and initialized (defined initially)
myInt = 3; // Redefined
```

The data type for a variable is only declared _once_. Afterwhich, any other calls to the variable only use its name, otherwise known as its **identifier**.

### Identifiers

An identifier is a name for some element of code that can be whatever you want, within reason. Specifically, identifiers can _not_ start with a number, but may start with an underscore `_` symbol. They cannot include special or punctuational symbols, such as `@ ! % ? &`. They also are case sensitive; they must be referred to exactly how they were originally named:

```cpp
// Valid identifiers:

int variable;
int _myVar;

// Invalid identifiers:

int 2_variable;
int a_new_variable_!;
```

### Variables in Summary

In summary, the syntax for declaring and initializing a variable is as follows:

`<data_type> <identifier> = <data>;`

A variable may be constant and unchanging, and it may be any of a variety of different data types. Data types may _not_ mix. For example:

```cpp
int x = 3;
char c;
c = x;
```

This code would cause an **error**, since a variable with the type `char` may not be defined with type `int`.

## 2.10: Arithmetic

tba// 

## 2.09: Escape Sequences

Escape sequences are a string of characters that represent a single unique character that cannot normally be typed. Despite being made of several characters, it only represents one. Ordinarily, however, single-quotes may not contain more than one character:

```cpp
char a = 'G'; // works
char b = '%3'; // doesn't work
char c = '/n'; // works (escape sequence)
```

Here is a list of all the significant escape sequences to understand in the beginning:

Escape Sequence | Description
----------------|------------
\a    | Audible bell sound
\b    | Backspace
\n    | Newline character
\\'   | `'` symbol
\\"   | `"` symbol
\\\   |`\` symbol

When using these characters and displaying them as output, they will act as intended.

Code:

```cpp
cout << "Hello\nWorld";
```

Output:

```
Hello
World
```

## 2.10: ASCII Standard

The **American Standard Code for Information Interchange**, or **ASCII**, is the standard character encoding method used by computers. 

Character encoding is the process of assigning numerical values to visual characters. This is done because computers compute in numbers, so eventually _everything_ must be encoded to binary. This also means that `char` data types _can_ store integers:

```cpp
char myChar = 84;
cout << myChar;
```

However, when output, these integers will be treated as their encoded counterpart.

Output:

```
T
```

Below is the full table of ASCII characters, including its extended entries. 

![img](https://microsoft.github.io/makecode-csp/static/010b16b23ea4e9d9474b1d6bb4969a52/518fe/ascii-table.jpg)

###### Note: the `char` keyword is only able to store values up to a byte in size. This is because the ASCII table only has 255 values, the maximum amount of values storable in a byte.

## 2.11: Arrays

In its most simplified application, an **array** is a variable that may store more than one variable (of the same type). It is defined by giving a variable a size:

```cpp
int myArr[5];
```

In this example, we created an array with a total potential of _five_ items. It can now be defined using brackets `{ }` containing a set of values.

```cpp
myArray[5] = {1, 2, 3, 4, 5};
```

Accessing an array, however, is different than defining it. When _defining_ an array, we use the square brackets `[ ]` to contain its size. When _reading_ or _storing data_ in an array, we use the brackets to access what we're after. 

```cpp
cout << myArray[4]; // reading from an array value
myArray[4] = 12;    // storing a value in an array
```

This will access the _fifth_ element in the array. This is because arrays begin at index _zero_. If we have an array with `[10]` elements, then the range of which we can access the array is `[0] - [9]`. So, in the case above, the output would be:

```
5
```

Arrays can also be accessed using variables, such as with this example:

```cpp
int numbers[10] = {1, 2, 3, 4, 5, 6, 7, 8 , 9, 10};
int index = 4;
cout << numbers[index] << endl;
index++;
cout << numbers[index];
```

Output:
```
5
6
```
###### Note: it is _very_ important to always remember that array indexes start at zero. 
<br>
Arrays aren't always very useful on their own, however, they are much more applicable to programming when used in conjunction with **loops**.
