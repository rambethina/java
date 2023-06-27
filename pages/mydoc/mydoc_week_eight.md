---
title: Week Eight
sidebar: mydoc_sidebar
permalink: mydoc_week_eight.html
folder: mydoc
---

## OOP - Continued from last week & Refresher

-- Refresher - Project we were working on....

Your final project we will be developing an E-commerce application, but we tackle this in phases. For todays class we will look a small part of the E-commerce application.

Let us assume we are selling ***Books*** in our E-commerce application. For a book we will store the following attributes.

* ISBN Number
* Title
* Author (assume it is only one author for now)

We will also need a ***Cart*** module. During the checkout process we will ***add Books to our cart*** and we will want to

* Print out details of our cart.
* We may also want to calculate the total number of books in our Cart.
* And also we may want to calculate the total Amount/cost.

-- Completed so far.

* Completed Book Class
  * Identified and added instance variables.
  * Created 2 constructors.
  * Added method printBookDetails
* Create a Main Class `ECommerceSimple` to test our implementation of the Book.

## Access modifiers

[Access Modifiers](https://www.w3schools.com/java/java_modifiers.asp)

## Static

A static varaible and static methods are variables & methods per class not per Object...They dont have any state. In the following example count is created as a static variable. Also notice how static variable is accessed in the ECommerceSimple class `Book.count` instead of javaBook.count or cPlusPlusBook.count

[Static key word](https://www.w3schools.com/java/java_class_methods.asp)

```text
public class Book {

    //Instance Variables
    private String ISBN;
    private String title;
    private String author;
    private double cost;

    public static int count = 0;

    //Constructor - initialize instance variables
    public Book(String isbnInput, String titleInput, String authorInput, double costInput) {
        this.ISBN = isbnInput;
        this.title = titleInput;
        this.author = authorInput;
        this.cost = costInput;
        this.count++;
    }

    public Book(String commaSeperatedLine) {
        //your implementation
        // look at split method in String,
        // initialize instance variable

        String[] bookDetails = commaSeperatedLine.split(",");
        this.ISBN = bookDetails[0];
        this.title = bookDetails[1];
        this.author = bookDetails[2];
        this.cost = Double.parseDouble(bookDetails[3]);
    }

    public void printBookDetails() {
        System.out.println(" ISBN Number :"+ISBN + " title : "+title+ " author: "+ this.author+ " cost:"+cost);
    }


}
```

```text
public class ECommerceSimple {

    public static void main(String[] args) {
        Book javaBook = new Book("ISNB0001", "How to program in Java", "John Doe", 24.5);
        javaBook.printBookDetails();

        Book cPlusPlusBook = new Book("ISNB0002", "How to program in c Plus Plus", "Sally Smith", 19.9);
        cPlusPlusBook.printBookDetails();

        Book bookInitializedFromLine = new Book("ISNB0003, How to program in JavaScript, Adam, 21.2");

        bookInitializedFromLine.printBookDetails();

        System.out.println("Total number of books :"+ Book.count);
    }
}
```

## Packages

[Packages](https://www.w3schools.com/java/java_packages.asp)

Think of it as a way to organize your code. There are 2 parts 

* Creating a package/folder and adding your class to new packages, adding package statement at the start of the file.
* Import package when you need it.

## while loop

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

## Data structures

Data Structure in java is defined as the collection of data pieces that offers an effective means of storing and organising data in a computer.

For today lecture we will discuss Arrays. In the next weeks lecture will talk about Maps, Sets, Queues and Stacks.

## Array List & Iterator pattern

* [Array List](https://www.w3schools.com/java/java_arraylist.asp)

Note: Look at import statements.
Note: We are using using type casting `String car = (String) carsIterator.next();`

```text
import java.util.ArrayList;
import java.util.Iterator;

public class ArrayExample {

    public static void main(String[] args) {
        ArrayList carsArray = new ArrayList();
        
        carsArray.add("Tesla");
        carsArray.add("Honda");
        carsArray.add("BMW");

        Iterator carsIterator = carsArray.iterator();
        
        while(carsIterator.hasNext()) {
            String car = (String) carsIterator.next();
            System.out.println(car);
        }
        
    }
}
```

## InClass Exercise

Modify the exercise we have been working on.

In the exercise so far we have assumed that we can have only one author. Modify your program so that it can take upto 10 authors.

*** Part One ***

Do not implement yet, discuss

*** Part Two ***

Lets implement


## Homework

Lets begin implementation of the Cart class.

* Provide instance variables. (Cart contains a list of books.)
* Provide a constructor to instialize your instance variables.
* Provide implementations for the following methods.
  * Add book to Cart: This method takes a book as an input argument and adds it to the list.
  * getTotal: This method iterates over the list gets each books cost, adds it up and returns total.

* Change your main class ECommerceSimple to test your new Cart class. Sample Mock implementation below.


```text
public class ECommerceSimple {

    public static void main(String[] args) {
        Book javaBook = new Book("ISNB0001", "How to program in Java", "John Doe", 24.5);
        javaBook.printBookDetails();

        Book cPlusPlusBook = new Book("ISNB0002", "How to program in c Plus Plus", "Sally Smith", 19.9);
        cPlusPlusBook.printBookDetails();

        Book bookInitializedFromLine = new Book("ISNB0003, How to program in JavaScript, Adam, 21.2");

        /*
        Initialize cart object.

        Cart myCart = new Cart();
        myCart.addBook(javaBook);
        myCart.addBook(cPlusPlusBook);
        myCart.addBook(bookInitializedFromLine);

        double cartTotal = myCart.getTotal();

        System.out.println("Cart Total: " + cartTotal);
        */
    }
}
```
