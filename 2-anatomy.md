---
permalink: /2-anatomy
---
## Anatomy of a Program

In C++, every program must consist of **at least** one function, which should be called main and return an integer. This means the simplest possible *proper* program in C++ is:

```c++
int main() {
	return 0;
}
```

I'll break down this basic program a little to explain what each of the parts do:
- Line 1 defines a function `main` which we promise will give back a type of `int`. The starting point of a C++ program will always be a function called 'main' which gives back an integer.
- Line 2 returns a value for this function, in this case we are just returning the integer number 0. The integer returned by this function is known as the *'exit code'*. This is meant to represent the outcome of the program, i.e. whether it succeeded or failed. An exit code of 0 is deemed a success, where as any other number is deemed a failure. In complex programs, different exit codes will signify different errors.
- Line 3 ends the *'block'* of code. Curly brackets ('{' and '}') are used to signify a block of code, which could be executed when a function is called, or when a condition is true (we'll look at this with control flow later).

Furthermore, I'm going to break down Line 1 even further, because it's important to understand:
- The `int` part is the type of the function, it tells us what type of value the function will return when it is finished.
- The `main` part is the name of the function, it is used to call the function elsewhere in the code (or to identify the starting point in the case of 'main')
- The `()` (round brackets, or parentheses) contain the parameters of the function. We have no parameters in the example above, but if you want to pass values to the function this is where the order and type of those values can be defined (we'll look at this more with functions in-depth later).

In reality, most programs will be more complex, and may often require other pieces of code from things called *'libraries'*, which are collections of variables and functions that someone else has written already to perform certain tasks. These libraries can be included by using something called a *'preprocessor directive'*, specifically an *'include directive'*. Preprocessor directives are instructions to the compiler that some additional function should be performed when compiling the program. Include directives tell the compiler that additional code from a different file should be included into the program. Here's an example of a common include directive which includes *'iostream'*, a library for input/output streams:
```c++
#include <iostream>
```

Aside from these preprocessor directives, each instruction, such as a mathematical operation, variable assignment or function call, in a program is known as a *'statement'*. By convention, we usually keep to one statement per line and statements are usually punctuated with a `;` (semicolon), but this is not always the case. You can have multiple statements on a line (as long as they are punctuated by semicolons, an example of which is in a for statement), and some statements aren't punctuated by a semicolon (such as in the condition for an if statement).
```c++
int i = 0; i = 2; i = i + 3; // Valid statements on a single line

if (i == 4) { // The condition for an if statement doesn't have a semicolon
	i = 6;
}
```

### Best Practices
Although less strictly to do with anatomy of a program, program design and layout is very important. Choosing sensible names for functions and variables, using correct indentation, clearly spacing out your code and using comments when needed to explain things are all important parts of program design. These are each outlined below:
- Generally, expressive names are better than short names, 'sumOfNumbers' is a better name than 's' or 'nums', similarly 'addTwo' is better than 'plus'.
- Indentation should be consistent with scope, with one level of indentation per depth of scope.
- Operators (such as '=' and '+') should have spaces on either side like so: `2 + 2` to make it easier to read, however you shouldn't put a space between a function's name and its parameters (use `myFunction()` instead of `myFunction ()`).
- Expressive names should largely be self explanatory, but occasionally it may be necessary to explain things further, and this is when comments should be used to provide additional information.

### Naming Conventions
Firstly, there are two main casing schemes you may use when naming your variables:
1. `camelCase` capitalises the first letter of each word in a name.
2. `snake_case` puts an undescore between each word in a name.

Both are equally valid, but you should stick to one scheme in a program, with the following exceptions:
- Constants are usually named with `UPPER_SNAKE_CASE`, for example `TAX_RATE`.
- Custom types are usually named with `UpperCamelCase`, for example `EmployeeRecord`.