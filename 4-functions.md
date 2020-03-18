---
permalink: /4-functions
---
## Functions
Functions are reuseable pieces of code which can be called multiple times in different situations. Functions can take parameters or arguments, which provide input to the function, and can return values, which provide output from the function. Functions are frequently used to avoid repetition of code, or to break up large blocks of code into smaller components with specific purposes. When designing functions, each function should fulfil a single purpose.

### Declaration and Definition
There are two stages to the creation of a function, its *declaration* and its *definition*. Sometimes these will both happen at the same time, but other times you may need to declare a function before you define it. Declaration is where you decide the return type and parameters of the function, and definition is where you decide the actual code to be run when the function is called. A function can only be used after it has been declared, but may be used before it has been defined. The definition types must match the declaration types exactly. Here is an example of seperate function declaration and definition: 
```c++
// Declaration
bool isBigger(int num1, int num2);

isBigger(2, 3) // Call

// Definition
bool isBigger(int num1, int num2) {
	return num1 > num2;
}
```

### Overloading
Although not used (yet) in the course, overloading is an important concept to be aware of for debugging. In C++, multiple functions with the same name, but different arguments can exist. The name and arguments types of a given function are called its *call signature* and the combination of name and types is how the compiler knows which function definition to use. Here are some examples of overloaded functions:
```c++
void printThing(int integer) {
	cout << integer;
}

void printThing(string words) {
	cout << words;
}

void printThing(float number) {
	cout << number;
}
```
It is unlikely you will need to use overloads in the course, but you may occasionally get error messages about mismatching call signatures, which mean that a function call does not align correctly with a present function declaration, so it is important to be aware of the existence of overloads to explain these errors.

### Values and References
In C++, there are three ways a parameter can be passed to a function, as a value (which is the default), as a reference or as a pointer. The difference in these is relatively straightforward but quite important. Essentially, it boils down to that when you pass a variable as a value, you're not actually passing the variable to the function at all, you're just taking the value stored in the variable and passing that value. You may be wondering what the difference is between passing the variable and passing the value, but passing the value is like me telling you what is inside of a box, as opposed to giving you the box. If you have the box, you can take the value out of it, or put a different value in. This is what passing as a reference or as a pointer. The difference between a reference and a pointer is a bit technical, but essentially a reference references a single particular variable, where as a pointer can be reassigned to point at another variable after initialisation.
- Pass by value: Original value is immutable (cannot be changed)
- Pass by reference: Original value is mutable (can be changed), and is always the same variable
- Pass by pointer: Original value is mutable (can be changed), but may be reassigned to a different variable