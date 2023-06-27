---
title: Week Eight
sidebar: mydoc_sidebar
permalink: mydoc_week_eight.html
folder: mydoc
---

## OOP - Continued from laste week & Refresher

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

```
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

```
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

## while loop

## Data structures

## Array List

## Iterator pattern

## InClass Exercise.

