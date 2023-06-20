---
title: Week Seven
sidebar: mydoc_sidebar
permalink: mydoc_week_seven.html
folder: mydoc
---

# Object Oriented Programming

## Exercise Part One

Your final project we will be developing an E-commerce application, but we tackle this in phases. For todays class we will look a small part of the E-commerce application.

Let us assume we are selling ***Books*** in our E-commerce application. For a book we will store the following attributes.

* ISBN Number
* Title
* Author (assume it is only one author for now)

We will also need a ***Cart*** module. During the checkout process we will ***add Books to our cart*** and we will want to

* Print out details of our cart.
* We may also want to calculate the total number of books in our Cart.
* And also we may want to calculate the total Amount/cost.

***Exercise***

Figure out the following (***Do not worry about implementation at this stage.***)

* Classes you need.
* Instances variables for each class.
* Functions/methods for each class.

## Part Two

* Implement the Book Class
  * Define instance variables.
  * Provide a constructor - For now assume the input arguments to be ISBN Number, Title and Author
  * Create a method to printBookDetails
* Create a new class called - ECommerceStarter with a main method to test our Book class
  * Create objects of the Book class.
  * Call printBookDetails on objects to print details of the Book class.

## Part Three

 Let us assume we are going to read book details from a file, and each line in the file has details for ***a book and the fields are seperate by comma***. 

 ```text
ISNB0001, How to program in Java, John Doe, 21.2
ISNB0002, How to program in JavaScript, Sally Smith, 19.2
```

Let us also assume we can read a line from the file, which is details for a Book, Can you suggest changes to our existing implementation if we need to initialize a Book.

## Part Four

Implement a new Book Constructor which takes a String, which is a comma separated list of book attributes.
Use the new Constructor in your main class. You can assume that order of fields in the comma separated string is fixed.

```
public class Book {

    //Instance Variables
    private String ISBN;
    private String title;
    private String author;
    private double cost;

    //Constructor - initialize instance variables
    public Book(String isbnInput, String titleInput, String authorInput, double costInput) {
        this.ISBN = isbnInput;
        this.title = titleInput;
        this.author = authorInput;
        this.cost = costInput;
    }

    public Book(String commaSeperatedLine) {
        //your implementation
        // look at split method in String,
        // initialize instance variable
    }

    public void printBookDetails() {
        System.out.println("ISBN Number :"+ISBN + " title : "+title+ " author: "+ this.author+ " cost:"+cost);
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

       // Call your new constructor here
    }
}
```

## Static variable

This is a variable per Class, Not a variable per Object. A good example would be count of books.

## Part Six

Implement a Cart Class






