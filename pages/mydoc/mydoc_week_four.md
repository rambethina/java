---
title: Week Four
sidebar: mydoc_sidebar
permalink: mydoc_week_four.html
folder: mydoc
---

## Assignment

## Next Week - Volunteers to teach following sections.
* [Arithmetic Operators](https://www.w3schools.com/java/java_operators.asp)
* [Java Comparison Operators](https://www.w3schools.com/java/java_operators.asp)

## Refresher Week 1 - 3.
* Naming convention 
  * class - PascalCase
  * methods - camelCase
  * variables - camelCase
* main method.
* variables & data types
* methods/functions.

## Revisit Assignment

## Methods Introduction 
* Methods with no arguments and void return type

```
public class WeekFourExOne {

    public static void main(String args[]) {
        sayHello();
    }

    public static void sayHello(){
        System.out.println("Hello");
    }
}
```

## In Class Exercise 1 (Methods with no arguments & does not return a value)
Create a method that prints any string. Call newly created method in your main method.

## Methods Continued
* Methods with arguments and void return type

```
public class WeekFourExTwo {

    public static void main(String args[]) {
        sayHello("Hello");
    }

    public static void sayHello(String inputParameter){
        System.out.println(inputParameter);
    }
}
```

## In Class Exercise 2 (Methods with arguments & does not return a value)
Create a new method called `printString` that takes an input string, and print the value of input parameter.

Assume the following main method implementation. As part of this exercise you will implement printString method.

```
    public static void main(String args[]) {
        System.out.println("**************************");
        printString("Java Facts");
        printString("In Java everything must be defined within a class.");
        printString("In Java Class names must be PascalCase.");
        printString("In Java method names must be camelCase.");
        printString("In Java main method is the starting point for execution.");
        System.out.println("**************************");
    }

```

Output should be
```
**************************
* Java facts.
* In Java everything must be defined within a class.
* In Java Class names must be PascalCase.
* In Java method names must be camelCase.
* In Java main method is the starting point for execution.
**************************
```

## Methods Continued
* Methods with arguments and return type

```
public class WeekFourExThree {

    public static void main(String args[]) {
        String stringOne = format("Java facts.");
        String stringTwo = format("In Java everything must be defined within a class.");
        System.out.println(stringOne);
        System.out.println(stringTwo);
    }

    public static String format(String inputParameter){
        return "* " + inputParameter;
    }
}
```

## In Class Exercise 3 (Methods with arguments & return a value)

Create a method that calculates area of a square. The method should take length as an input parameter and return area (return integer value.)

Call area method within your main main method passing any integer. Print value returned from your method.

## [Array data type](https://www.w3schools.com/java/java_arrays.asp)

Example
```
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
cars[0] = "Opel";
System.out.println(cars[0]);
```


## Assignment
Goals - Use methods where possible.

Continuation of Validate & Sanitize Input. We will build on assignment from previous week and course work today.

Write a program that takes care of the following sanitization rules.

* First name and Last name must should start with a Capital Letter. (Week 3 assignment & course work today.)
* Phone numbers can be input in any of the following patterns, but must be sanitized, Look below for possible input values and output value.
  Input
  * 555-123-1245
  * (555) 123-1245
  * 555.123.1245

 Output
   5551231245

Sample starting Class, Feel free to change values.

```
public class WeekFourAssignment {

    public static void main(String args[]) {
        String firstName = "abraham";
        String lastName = "lincoln";

        String primaryPhone = "555-123-1245";
        String secondaryPhone = "555.123.1246";

        // Call to methods that sanitize input.

        // Print results.
    }
    
    //method to sanitize names

    //method to sanitize phone numbers

}
```