---
title: Week Six
sidebar: mydoc_sidebar
permalink: mydoc_week_six_2022.html
folder: mydoc
---

## Sentence Exercise

* Part One - Find first index of word.
* Part Two - Find last index of word.
* Part Three - Create methods if you have not done already.
* Part Four -  Move to new class called SentenceUtils.

## Assignment

## For loops revisited & Execution flow

Exercise will be added after we go over assignment in class.

```
public class WeekFiveAssignment {
    public static void main(String args[]) {

        int[] numbers = {42, 20, 1, 13};

        // 1, 13, 20, 42

        // i = 0; i < 4, i++

        for(int j =0; j < numbers.length ; j++) {
            for (int i = 0; i < numbers.length-1; i++) {
                if(numbers[i] > numbers[i+1]) {
                    int temp = numbers[i];
                    numbers[i] = numbers[i+1];
                    numbers[i+1] = temp;
                }
            }
        }


        for (int i= 0; i < numbers.length; i++) {
            System.out.println("value of i is: "+i+ " and number at that position is: "+numbers[i]);
        }


    }
}
```

## while
* [while](https://www.w3schools.com/java/java_while_loop.asp)


```
public class WeekSixExTwo {

    public static void main(String args[]) {
        int i = 0;
        while (i < 5) {
            System.out.println(i);
            i++;
        }
    }
}
```

Exercise

STEP 1: 
Create a program that prints the following using a while loop, initialize the value of i to be number of * you want to print.

`****************`

HINT: instead of `System.out.println` use `System.out.print`

STEP 2: 
Put the print logic in a function/method instead and call function in your main method. 
NOTE :- you will be using the following function in your assignment.

```
public static void printBorder(int size) {
   // your implementation here
}
```


## switch case
* [switch case](https://www.w3schools.com/java/java_switch.asp)

```
public class WeekSixExThree {

    public static void main(String args[]) {
        int day = 4;
        switch (day) {
        case 6:
            System.out.println("Today is Saturday");
            break;
        case 7:
            System.out.println("Today is Sunday");
            break;
        default:
            System.out.println("Looking forward to the Weekend");
        }
    }
}
```

## break

* [break](https://www.w3schools.com/java/java_break.asp)


```
public class WeekSixExFour {

    public static void main(String args[]) {
        for (int i = 0; i < 10; i++) {
            if (i == 4) {
                break;
            }
            System.out.println(i);
        }
    }
}
```

## Assignment / Mid term project

You will use all the concepts you learned from week 1-5

Note: Your implementations does not need to take my suggestions into account. Look at suggestions only if you need an idea on what functions/methods you need to create. You can put all your code in main method but I would like you to think how to break apart your program into small functions/methods that you can reuse.

Output formatter.

* Output should be surrounded by *
* Key Value pairs should be properly spaced.

Sample input
```
public class Week6MidTerm {
    public static void main(String args[]) {

        String[] keysArray = {"First Name", "Last Name", "Primary Phone"};
        String[] valuesArray = {"John", "Doe", "111-111-1111"};

        // Your Implementation
    }
}
```

Example output
```
******************************
* First Name   : John        *
* Last Name    : Doe         *
* Primary Phone: 111-111-1111*
******************************
```

OR

```
************************************
* First Name      : John           *
* Last Name       : Doe            *
* Primary Phone   : 111-111-1111   *
************************************
```
Requirements

* Users should be able to pass in 2 string arrays, 
    * An array of keys - example, this array will contain First Name, Last Name, Primary Phone
    * An array of values - example, this array will contain John, Doe, 111-111-1111
* `:` seperator should be aligned & ending * should also align.
* starting and ending line should contain `*` and also align based on strings arrays that are passed.

Suggestions

* create a print method that takes in 2 arrays(keys array & values array) and prints the output. This method should be called in main method
```
public static void output(String[] keysArray, String[] valuesArray){
  /*
  pseudo code
  int maxKeySize = getSizeOfBiggestStringInArray(keysArray); //Look below for method definition.
  int maxValuesSize = getSizeOfBiggestStringInArray(valuesArray);

  To print top border use System.out.print instead of System.out.print, you can use a while loop or for loop. - I would recommend creating a function called printBorder, look at while loop exercise.

  Print each row, Use a for loop. I would recommend creating a function to print, look below at printRow - I provided a complete implementation.

  Print bottom border.
  */
}
```

* Create a method that takes an input array of strings and returns the max length, which should be the lenght of biggest string in the array.

```
public static int getSizeOfBiggestStringInArray(String[] inputArray){
// your implementation here.
}
```

* Create a method to print a Row (Complete implemetation below, You dont need to change anything below.)

```
    public static void printRow(String key, String value, int maxKeySize, int maxValueSize){
        // Reference - https://www.javatpoint.com/java-string-format 
        // Out of the box method that formats strings.
        // Since you may not be familiar with using format method I provided a sample implementation.
        // This is not the only implementation, but you can use this as a sample.
        // %30s - format that add 30 spaces to the beginning of string.
        // %-30s - format that add 30 spaces to the end of string.
  
        String keyOutput = String.format("%-" + maxKeySize + "s", key);
        String valueOutput = String.format("%-" + maxValueSize + "s", value);

        System.out.println("*"+keyOutput+":"+valueOutput+"*");
    }
```