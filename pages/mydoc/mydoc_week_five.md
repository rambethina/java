---
title: Week Five
sidebar: mydoc_sidebar
permalink: mydoc_week_five.html
folder: mydoc
---

## Assignment

## In Class Exercise

## Methods/Functions summary
* Why

## Operators
* [Arithmetic Operators](https://www.w3schools.com/java/java_operators.asp)
* [Java Comparison Operators](https://www.w3schools.com/java/java_operators.asp)

```
public class WeekFiveEx1 {
    public static void main(String args[]) {

        //Assignment operators
        int x = 2;
        int y = 1;
        int sum = x + y;
        int multiplication = x * y;
        int division = x / y;
        int modulus = x % y;
        System.out.println("Sum :"+sum);
        System.out.println("Multiplication :"+multiplication);
        System.out.println("Division :"+division);
        System.out.println("Modulus :"+modulus);
//        System.out.println(x++);
//        System.out.println(++x);
//        System.out.println(x);

        //Comparison Operators
        System.out.println(x>y);
        System.out.println(x==y);
        System.out.println(x!=y);
        System.out.println(x<y);
    }
}
```

## In Class Exercise
Swap values of x & y and print results
```
int x = 20;
int y = 30;

/*
NOTE - THE FOLLOWING WILL NOT WORK, YOU CAN TRY IT THOUGH
x = y;
y = x;

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
public class WeekFiveEx2 {
    public static void main(String args[]) {

        int x = 2;
        int y = 1;

        if(x > y) {
            System.out.println("x is greater than y");
        }
    }
}
```

```
if (condition) {
  // block of code to be executed if the condition is true
} else {
  // block of code to be executed if the condition is false
}
```

In class exercise
Use WeekFiveEx2 as a starting point and add the else clause above to `print y is greater than x`

Ternary operator
```
variable = (condition) ? expressionTrue :  expressionFalse;
```


## Array Data type
* [Array data types](https://www.w3schools.com/java/java_arrays.asp)
* Exercise below as part of for loop.

## for loop
* [for loop](https://www.w3schools.com/java/java_for_loop.asp)
* Print values in array
```
public class WeekFiveEx3 {
    public static void main(String args[]) {

        int[] numbers = {42, 20, 1, 13};
        System.out.println(numbers[0]);

        for(int i = 0; i < numbers.length; i++) {
            System.out.println(numbers[i]);
        }
    }
}
```

## while loop (if we have time.)
* [while loop](https://www.w3schools.com/java/java_while_loop.asp)

```
public class WeekFiveEx4 {
    public static void main(String args[]) {
        int i = 0;
        while(i < 10) {
            System.out.println(i);
            i++;
        }
    }
}
```

## Sort array so highest number is at the end of the array.

Input
```
int[] numbers = {42, 20, 1, 13};
```

Iterate over your array after you implement step 1 & 2 and output must be
```

Number at index 0: 20
Number at index 1: 1
Number at index 2: 13
Number at index 3: 42
```

STEP 1  - if number at index or i is greater than number at index + 1 or i + 1, print `number at index is greater than number at index + 1 where i is : ......

Sample code
```
int[] numbers = {42, 20, 1, 13};
for(int i = 0; i < numbers.length -1; i++) { //NOTE LOOK AT MY FINAL CONDITION numbers.length -1
    //if(number[i] > number[i+1]) {
        // print statement -> number at index is greater than number at index + 1 where i is : ......
    // }
   
}
```
STEP 2 - if number at index or i is greater than number at index + 1 or i + 1 then swap elements at index or i and index + 1 or i +1.
Sample code
```
int[] numbers = {42, 20, 1, 13};
for(int i = 0; i < numbers.length -1; i++) { //NOTE LOOK AT MY FINAL CONDITION numbers.length -1
    //if(number[i] > number[i+1]) {
        // print statement -> number at index is greater than number at index + 1 where i is : ......
        // your swap code here.
        // look at in class exercise to swap numbers
    // }
   
}
```