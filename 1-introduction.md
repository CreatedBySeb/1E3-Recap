---
permalink: /1-introduction
---
## Introduction

### Overview
Programming is the act of writing instructions that can be compiled into machine code which can then be run by a computer. Software design is the act of coming up with a software-based solution to a problem. These are two distinct parts of the creation process for a program. The first step is typically coming up with an algorithim (using mathematical notation or *'psuedocode'*), and then the second is the implementation of that algorithim in a programming language. Pseudocode is just writing the steps of a process in a language that's similar to written and spoken English in order to devise an algorithim to solve a problem. Here's an example of psuedocode:
```
Ask for sky colour
If sky is blue:
	Say good weather
Else:
	Say bad weather
```
The pseudocode specifies the general solution to the problem, rather than one specific implementation of the solution in a certain programming language. There are many tools that you can use to create pseudocode (as it has no specific form). These can be step-by-step instructions, actual code with stubs (functions that don't yet exist) or something like a flowchart. The important thing is to think about the design of the solution before you start writing it. Once you have written code in a programming language, it must be *'compiled'* into machine code using another program called a *'compiler'*, before it can be run on the computer.

### Bits and Bytes
Programming has two fundamental units, bits and bytes. A bit is a binary value, either 1 or 0. A byte is a collection of 8 bits. The more bits used together, the exponentially larger the value that can be stored (1 bit can store 2 values, 2 bits can store 4 values, 3 bits can store 8 values and so on, the maxmimum value stored is given by 2^n - 1). One byte can hold 256 different values. The difference between bits and bytes is important when looking at their values as there is a factor of 8 between them, which can be a lot with higher order numbers.

### Variables and Functions
Variables are a way of storing data in a progarm. Variables have a type which represents what kind of data they store, and a name which is the reference used to access the variable. Similarly, functions also have a type which represents what kind of data they give when run, and also have a name which is used to run (or *'call'*) the function, but may also have parameters (or *'arguments'*) which can be given to the function when it is called.
```c++
int someVariable = 3; // An example of an integer variable with an initial value of 3

// An example of a function which gives a float (floating point or decimal number), and takes a single parameter of an integer number
float someFunction(int number) {
	return 3.0 * number;
} 
```

### Types
Variables and functions must have a type, here are some of the most important types and what they represent. Additional types can be added by libraries, or you later on, but we won't deal with most of them yet.
- `bool` represents a boolean value (true/false). It can only have a value of `true` or `false`.
- `int` represents an integer number. It can only have whole number values.
- `long` also represents an integer number. It can store 256 times more values than an int.
- `float` represents a floating point (decimal) number. It uses 32 bits and has 6 digits of decimal precision.
- `double` also represents a floating point number. It uses *double* the number of bits (64) and has 15 digits of decimal precision.
- `char` represents a single character. It is one byte (or 8 bits) in size.
- `string` represents a string of characters. Its capacity varies depending on how it is created (which we'll discuss later).
- `void` is only for a function and says that the function will not return any value.

### Scope
One very important principal in programming is the idea of scope. Scope is the set of rules that governs what variables and functions a statement is able to access. The highest level of scope in a file is the file itself, which is typically where functions such as the main function (which we'll encounter later) reside, where constants are defined and where other code is included. A statement can only access variables and functions in its own scope or a higher scope, but not a lower scope or a seperate scope of the same level. Here is an example of scope in action:
```c++
int a = 1; // a is in the highest scope, sometimes called the global scope.

int function() {
	// a is still accessible within this function, because the function is a lower scope and can see variables at a higher scope.
	int b = 2;

	if (true) {
		// Both a and b are accessible within this function, because they both reside in higher scopes
		// (Notice how the indentation is indicative of the scope, while this is not always true it's a good practice we'll discuss later)
		int c = 3
	}

	// c is no longer accessible, since it was declared in a lower scope (within the if statement)
	// However b is still accessible, since it was declared in this scope.
}

// Now b is no longer accessible since the function's scope is lower than the file's scope

int otherFunction() {
	// b is not accessible here either, because although this scope is at the same depth as the other function, it is not within that scope, it is a seperate scope.
}
```