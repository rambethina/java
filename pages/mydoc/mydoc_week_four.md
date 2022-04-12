---
title: Week Four
sidebar: mydoc_sidebar
permalink: mydoc_week_four.html
folder: mydoc
---

## Assignment

## Next Week Volunteers
Operators

## Refresher Week 1 - 3.

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

## In Class Exercise 1
Create a method that prints any string. Call method in your main method.

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

## In Class Exercise 2
Change method you created in exercise 1, Take an input string, and print the value of input parameter.

To help you out assume the following main method implementation. As part of this exercise you will implement printString method.

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

## In Class Exercise 2
Expand on assignment from last week or what we covered in class.
As part of the assignment we santized first name, as a next step sanitize last name too.
Use method & avoid code duplication.

## Assignment
Goals - Use methods where possible.

Continuation of Validate & Sanitize Input. We will build on assignment from previous week and course work today.

* First name and Last name must not contain any `_` and they should start with a Capital Letter. (Week 3 assignment & course work today.)
* Phone numbers can be input in any of the following patterns, but must be sanitized.
  Input
  * 555-123-1245
  * (555) 123-1245 
  * 555.123.1245

 Output
   5551231245
