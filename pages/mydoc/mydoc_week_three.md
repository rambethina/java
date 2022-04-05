---
title: Week Three
sidebar: mydoc_sidebar
permalink: mydoc_week_three.html
folder: mydoc
---

## Goal - Variables Introduction, Data Types, String Class
* [Variables](mydoc_week_thress.html#goal---variables-introduction)
* Data Types
* In Class Exercise
* Method - brief introduction
* String Class & Use predefined methods.

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

