---
title: Week Five
sidebar: mydoc_sidebar
permalink: mydoc_week_five.html
folder: mydoc
---

## Assignment

## Operators
* [Arithmetic Operators](https://www.w3schools.com/java/java_operators.asp)
* [Java Comparison Operators](https://www.w3schools.com/java/java_operators.asp)

## In Class Exercise
Swap values of x & y and print results
```
int x = 20;
int y = 30;

/*
Some code here

create a temp variable as below

int temp;

store value of x in temp variable as below

temp = x;

now assign value of x to y as below

x = y;

now assign value of temp to y as below

y = temp;

*/

System.out.println(x); // should print 30;
System.out.println(y); // should print 20;
```


## if..else

```
if (condition) {
  // block of code to be executed if the condition is true
}
```

```
if (condition) {
  // block of code to be executed if the condition is true
} else {
  // block of code to be executed if the condition is false
}
```

Ternary operator
```
variable = (condition) ? expressionTrue :  expressionFalse;
```

## Array Data type
* [Array data types](https://www.w3schools.com/java/java_arrays.asp)

```
int[] numbers = {42, 20, 1, 13};
System.out.println(numbers[0]);
```

## for loop
* [for loop](https://www.w3schools.com/java/java_for_loop.asp)
* Print values in array
```
int[] numbers = {42, 20, 1, 13};
for(int i = 0; i < numbers.length; i++) {
    System.out.println(number[i]);
}
```

## Sort array so highest number is at the end of the array.

Input
```
int[] numbers = {42, 20, 1, 13};
```

Output must be
```
numbers = {20, 1, 13, 42};
```

STEP 1 - if number at index is greater than number at index + 1, print `number at index is greater than number at index + 1 where i is : ......

Sample code
```
int[] numbers = {42, 20, 1, 13};
for(int i = 0; i < numbers.length; i++) {
    //if(number[i] > number[i+1])
}
```