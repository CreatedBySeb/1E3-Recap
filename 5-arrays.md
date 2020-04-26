---
permalink: /5-arrays
---
## Arrays
The concept of a list comes up a lot in problems you may wish to solve with a program. Most programs deal with structured data of some kind, and an ordered or unordered list is a very common type of structured data we see a lot in our lives (think to-do lists on your phone, or a series of text messages). Arrays are one (fixed) way of representing these list formats of data. Arrays must have a fixed length, which they cannot exceed (exceeding their size is known as overflow). The size must be defined when the array is originally initialised. Array variables are declared a little differently to variables we've seen so far, here is a sample declaration for an uninitialised `int` array with space for six items.
```c++
int myArray[6];
```
Notice that the type keyword for the variable refers to the type of the array (arrays can only be of a single type). Then square brackets (*the accessor operator*) are used to define the size of the array at the end of the variable name. When an array is declared like this, its members are uninitialised, and similar to an uninitialised variable, each member may contain random garbage data. It is also possible to initialise an array in its declaration:
```c++
int myArray[6] = {1, 2, 3, 4, 5, 6};
```
Notice that, even though square brackets are used for the size definition, the array literal (the hard-coded value of the array) is contained between curly brackets. Many other programming languages will use square brackets for array literals, so it is important to remember that this is not the case in C++! Arrays are indexed starting at 0, this means that the first element in our array literal (`1`) is at index 0 in the array. Now, you can set or access its elements:
```c++
myArray[3]; // equal to 4
myArray[3] = 7;
myArray[3]; // equal to 7
```
Something important worth noting, is that how arrays work underneath, is actually as a set of pointers. You may remember pointers and references from before, and an array is really a collection of pointers to a set of variables. This is crucial to remember, because it means that when you pass an array as a parameter, you are passing a set of pointers, so any changes you make to the elements of an array inside of a function, will affect the array at any level of scope, as if you had passed it by reference or as a pointer.
```c++
int myArray[3] = {1, 2, 3};

void doThing(int a[3]) {
	a[1] = 6;
}

doThing(myArray);
myArray[1]; // This will now be equal to six.
```

### Using Arrays
Given that arrays are lists of items, it is quite possible that you may want to iterate through arrays, we can use existing control flow principles that we have already explored to do so quite easily:
```c++
int myArray[6] = {7, 1, 6, 20, 3, 5};

for (int i = 0; i < 6; i++) {
	myArray[i]; // This will evaluate to the array member referenced by i, for each run of the loop, i will increase, until it is equal to the index of the last member in the array.
}
```
However, hardcoding array lengths, and then re-using those hardcoded values is a terrible practice, because if you change the length and then forget to update that elsewhere, you can cause many errors. A better way to have a hardcoded value is using constants like so:
```c++
const int ARRAY_LENGTH = 6;
int myArray[ARRAY_LENGTH] = {7, 1, 6, 20, 3, 5};

for (int i = 0; i < ARRAY_LENGTH; i++) {
	myArray[i]; // This will evaluate to the array member referenced by i, for each run of the loop, i will increase, until it is equal to the index of the last member in the array.
}
```
With this type of approach, I can always just change the single constant to change the length of the array, and the for loop will continue to function as intended. However, sometimes you may wish to be more dynamic with your array length, and there are multiple ways to do this, but essentially what you need to do is just keep track of how many items you have read in with a counter.