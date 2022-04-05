---
title: Week Three
sidebar: mydoc_sidebar
permalink: mydoc_week_three.html
folder: mydoc
---

## Refresher Hello World Exercise.

## Variables Introduction
* Refer [w3schools](https://www.w3schools.com/java/java_variables.asp)

## Data types
* Refer [w3schools](https://www.w3schools.com/java/java_data_types.asp)

```
public class WeekThreeExOne {
    public static void main(String args[]) {
        // variable_type variable_name = value;
        int year = 2022;                    // Integer (whole number)
        char gender = 'M';                  // Character
        boolean isPrimaryEmail = true;      // Boolean valid values are true or false
        String firstName = "Ram";           // String
    }
}
```

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

Create a program to print above registration details. As a part of the exercise you will practice.
* Syntax for declaring a variable.
* Choosing the correct data type.
* Initialize variables with values.
* Solving any compilation issues.
* 
Example - In the following example we created a variable called firstName of type String and assigned it a value Ram, As a part of the exercise add you will need to add remaining registration fields.


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
* In general a method is a block of code that does something. For example length method in [String class](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html) calculates the length of the string. A method normally has the following
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


Example - Find length of first name String. (Note - string length method does not take any input arguments/parameters, returns a int value that is the length of the string)
```
public class WeekThreeExOne {
    public static void main(String args[]) {

        String firstName = "Ram_Bethina";

        System.out.println("First Name : "+firstName.length());

        
    }
}
```

## In Class Exercise
* Convert values provided in First Name to Upper Case, ie if I declare `String firstName = "Ram Bethina"` output of my program should be `First Name : RAM BETHINA`, HINT - User toUpperCase() method.


Example - concatenate 2 strings. (Note - string concat takes an input argument and returns a contactenated string)
```
public class WeekThreeExOne {
    public static void main(String args[]) {

        String firstName = "Ram";

        System.out.println("First Name : "+firstName.concat(" Bethina"));

        
    }
}
```
## In Class Exercise
* Assume `String fullName = "abraham lincoln";` Write a program that prints out first 8 characters, HINT use substring method. 
  

## Assignment - Input cleanser

Normally user input data needs to be cleaned. As part of our program we are going to implement a simple input cleanser.

 Assume that we do not want '_' in first name and last name,

PART 1 - Write a program that replaces any occurence of underscore `_` with a space `  `.

 ```
 public class WeekThreeExOne {
    public static void main(String args[]) {

        String firstName = "Ram_Bethina";

        System.out.println("First Name : "+firstName.<HOME WORK, REPLACE WITH A FUNCTION IN THE STRING CLASS THAT REPLACES _ WITH EMPTY SPACE>);
    }
}
```
OUTPUT SHOULD BE 

`First Name : Ram Bethina`

Hint - You may want to use the following method on String class.
* replaceAll - Look at API for additional details., But at a high level this takes 2 arguments. As an example `replaceAll(" ", "_")` will replace all occurences for space with underscore

PART 2 - (This may be a bit more challenging but I would like you to give it a try.) Write a program that capitalizes the first letter of first name.
So if I declare my first name to be 

`String firstName = "ram bethina";`

OUTPUT SHOULD BE 

`First Name : Ram bethina`

Hint, you may want to use the following String API methods.
* substring
* toUpperCase
* concat

## Assignment submission
* I would prefer if you send me a link to your project in github, If you dont have time to get git working you can slack me the assignment for this week.
* If you completed last weeks assignment you may have created a github account. If not create a github account.
* Please follow the [link](https://www.youtube.com/watch?v=mf2-MOl0VXY) which talks thru IntelliJ integration with git and github. 



