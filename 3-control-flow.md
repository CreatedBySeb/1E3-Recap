---
permalink: /3-control-flow
---
## Control Flow
Control flow is the idea surrounding how you can run certain pieces of code when certain conditions are met. This is very important when creating programs as it is unlikely that the situation will be identical every single time, solving one instance of a problem isn't nearly as useful as a resuseable solution. Control flow has two main parts, a condition that must be fulfilled and a resulting block or statement which will be executed when the condition is fulfilled.

### Boolean Logic
The core of all of control flow is the idea of boolean logic (true/false values). We've looked at the boolean type already, but there are a few operators which are very useful in boolean logic:
- `<a> && <b>` (and) returns `true` only if both a and b evaluate to `true` and returns `false` for every other combination.
- `<a> || <b>` (or) returns `true` if either a or b (or both) evaluate to `true`, and returns `false` only if both sides return `false`.
- `!<statement>` (inverse) returns the opposite boolean value of the statement, so if the statement evaluates to `true` it returns `false` and vice-versa.

### If Statements
If statements are the most basic, but also one of the most useful control flow tools. They run the code inside of them when their condition evaluates to the boolean value `true` (or the number `1` which is the binary value for true). They use the following syntax:
```c++
if (<condition>) {
	// Code to execute
}

// For example:
if (i == 3) {
	// i is equal to 3
}
```
If statements can also be chained together using the else keyword like so:
```c++
if (i == 3) {
	// i is equal to 3
} else if (i == 2) {
	// i is equal to 2
} else if (i > 1) {
	// i is greater than 1, but not equal to 2 or 3
} else {
	// i must be some other number
}
```
If an else keyword has an if statement, the following code will only be executed if the condition is true and all previous if statements have been false. 

### While Loop
While loops are the most basic type of loops. They run the code inside of them in a loop until their condition evaluates to the boolean value `false` (or the number `0` which is the binary value for false). The condition is only checked at the end of each iteration of the loop. They use the following syntax:
```c++
while (<condition>) {
	// Code to execute
}

// For example:
int i = 0;

while (i < 6) {
	// Will run while i is less than 6
	i++;
}

// i is now 6

int j = 3;

while (j == 2) {
	// This won't run even once, as the condition is never met
}
```
While loops can be stacked inside each other, but you likely want to use different variables for each stacked loop, to ensure that they aren't overwriting each other (unless that is specifically what you want to do).

### For Loops
For loops are a slightly different form of loop. Any for loop can be written as a while loop, but for loops provide a nicer syntax for what is a very common operation. Similar to while loops, they run the code inside of them in a loop until their condition evaluated to the boolean value `false`. The condition is also only checked at the end of each iteration of the loop. The initialiser is only run once before the condition is checked for the first iteration of the loop, and the updater is run at the end of each iteration of the loop before the condition is checked for the next iteration. They use the following syntax:
```c++
for (<initialiser>; <condition>; <updater>) {
	// Code to execute
}

// For example:
for (int i = 0; i < 6; i++) {
	// Will run for each value of i less than 6
}

// i is now 6
```
Notice that the for statement in this example is the same as the while statement in the previous example, it just is much easier to read. This style of loop appears so often that for loops were created just to make the common syntax easier to read, but any for loop can be written as a while loop, and any while loop can actually be written as a for loop (it just doesn't always make it easier to read, make the decision on a case by case basis).

### Switch Statements
Switch statements are quite similar to if statements, but provide an easier way to list many similar conditions with discrete values. Switch statements take a certain expression and check multiple conditions against the expression. Each condition can only be a single value, for example, a number (`1`), a boolean value (`true`) or a string (`"Some string"`). Any switch statement can be rewritten as a chain of if and else statements using the boolean operators. They use the following syntax:
```c++
switch (<expression>) {
	case <condition>:
		// Code to execute
		break;

	default:
		// Code to execute if no condition matches
}

// For example:

string input;
cin >> input;

switch (input) {
	case "hello":
	case "hi":
	case "hey":
		cout << "Hello!";
		break;

	case "bye":
	case "goodbye":
	case "see ya":
		cout << "Goodbye!";
		break;

	case "marco":
		cout << "Polo!";
		break;

	default:
		cout << "I'm not sure what you said";
}
```
Switch statements are very useful in specific situations, usually when you want to compare a certain variable or expression against a specific set of exact values. 