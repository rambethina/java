---
title: Week Three
sidebar: mydoc_sidebar
permalink: mydoc_week_three.html
folder: mydoc
---

## Goal - Variables Introduction, Data Types, String Class
* [Variables](https://rambethina.github.io/java/mydoc_week_three.html#variables-introduction)
* [Data Types](https://rambethina.github.io/java/mydoc_week_three.html#data-types)
* [In Class Exercise](https://rambethina.github.io/java/mydoc_week_three.html#in-class-exercise)
* [Method - brief introduction](https://rambethina.github.io/java/mydoc_week_three.html#methods)
* [String Class & Use predefined methods.](https://rambethina.github.io/java/mydoc_week_three.html#string-methods)
* [Assignment - Input cleanser](https://rambethina.github.io/java/mydoc_week_three.html#string-methods)

## Variables Introduction
* Refer [w3schools](https://www.w3schools.com/java/java_variables.asp)

## Data types
* Refer [w3schools](https://www.w3schools.com/java/java_data_types.asp)

## In Class Exercise
For our final project we will build a simple eCommerce App (Similar to amazon), Part of the project will involve registration.
Assume we are going to collect the following information during registration.
- email
- primary email (Assume only valid values are true or false)
- first name
- last name
- middle initial (Assume this can only be a single letter)
- DOB Month
- DOB Day
- DOB Year

Create a program to print registration details.

Example - In the following example we created a variable called firstName of type String and assigned it a value Ram

Goal - Use correct data types to initialize values.

```
public class WeekThreeExOne {
    public static void main(String args[]) {

        String firstName = "Ram";

        System.out.println("First Name : "+firstName);
    }
}
```

## Methods
* Refer [w3schools](https://www.w3schools.com/java/java_methods.asp), We will revisit methods in much more detail in the next couple of weeks.
* In general a method is a block of code that does something. For example length method in [String class](https://docs.oracle.com/javase/8/docs/api/) calculates the length of the string. A method normally has the following
  * name of method
  * return value and type
  * arguments/parameters
  * body/implementation - we will not worry about this for this class, we will revisit this next week.

## String methods
* Example methods that return a value
  * length
  * toUpperCase
* Example methods that take an argument
  * substring

## Assignment - Input cleanser

Normally user input data needs to be cleaned. As part of our program we are going to implement a simple input cleanser.

 Assume that we do not want '_' in first name and last name,

 Write a program that replaces any occurence of _ with a space.

 ```
 public class WeekThreeExOne {
    public static void main(String args[]) {

        String firstName = "Ram_Bethina";

        System.out.println("First Name : "+firstName.<HOME WORK, REPLACE WITH A FUNCTION IN THE STRING CLASS THAT REPLACES _ WITH EMPTY SPACE>);
    }
}

OUTPUT SHOULD BE First Name : Ram Bethina
```

