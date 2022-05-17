---
title: Week Nine
sidebar: mydoc_sidebar
permalink: mydoc_week_nine.html
folder: mydoc
---

## Introduction to data structures & Iterator

* Arrays
* Map (We will review in the next lecture)
* Queue (We will review in the next lecture)
* Stack (We will review in the next lecture)

```
import java.util.Arrays;

public class Book {

    private final String isbnNumber;
    private String title;
    private String author;
    private String category;
    private double price;
    private String[] reviews;

    public Book(String isbnNumber, String title, String author, String category, double price, String[] reviews) {
        this.title = title;
        this.isbnNumber = isbnNumber;
        this.author = author;
        this.category = category;
        this.price = price;
        this.reviews = reviews;
    }

    @Override
    public String toString() {
        return "Book{" +
                "title='" + title + '\'' +
                ", author='" + author + '\'' +
                ", category='" + category + '\'' +
                ", price=" + price +
                ", reviews=" + Arrays.toString(reviews) +
                '}';
    }

    public double getPrice() {
        return price;
    }
}
```

```
import java.util.Arrays;

public class ArrayListSample {

    public static void main(String[] args) {
        List bookList = new ArrayList<Book>();

        bookList.add(
                new Book("ISBN001", "How to program in java", "John Doe", "Educational", 29.2, new String[]{
                        "first review for how to program in java"}));
        bookList.add(
                new Book("ISBN002", "How to program in cPlusPlus", "John Doe", "Educational", 19.2, new String[]{
                        "first review"}));
        bookList.add(
                new Book("ISBN002", "How to program in cPlusPlus", "John Doe", "Educational", 19.2, new String[]{
                        "first review"}));

        Iterator<Book> iterator = bookList.iterator();
        while(iterator.hasNext()) {
            Book book = iterator.next();
            System.out.println(book.toString());
        }
    }
}
```

## Packages & Imports
* [Packages](https://www.w3schools.com/java/java_packages.asp)


## Programming an OOP system - Reference implementation

* For our final project we will work on creating an [eCommerce system](https://rambethina.github.io/java/mydoc_week_eight.html#final-project-more-details-will-be-added-later-this-section-is-more-of-a-helper-to-think-through-object-oriented-programming). During this class we will implement one
module in our eCommerce Application.

Inventory module should satisfy the following
* Store items in our inventory. (In reference it is hardcoded in `com.inventory.Inventory`, initializeInventory() method, later you will read from a file instead. )
* Display items in our inventory.
* Total cost of our inventory. (Sample provided for this function)
* Search based on ISBN Number.(Inclass exercise)

[Sample starter](https://github.com/rambethina/ECommerceInventoryModule)

Download project
* Click on Code button (Green Button)
* Download Zip

* Create a new intelliJ project, Select download location and leave defaults.

* Note usage of the following
    * packages
    * implementation of totalAmount in `com.inventory.Inventory`

## In Class Exercise

* Create a new search method in Inventory module.
    * Take ISBN number as input and return true or false based on book being in inventory.
        * Use totalAmount in `com.inventory.Inventory` as a reference.

## Exceptions
* [Exception handling](https://www.w3schools.com/java/java_try_catch.asp)

## Working with files

* [readings from files](https://www.w3schools.com/java/java_files_read.asp)

```
import java.io.File;  // Import the File class
import java.io.FileNotFoundException;  // Import this class to handle errors
import java.util.Scanner; // Import the Scanner class to read text files

public class ReadFile {
  public static void main(String[] args) {
    try {
      File myObj = new File("filename.txt");
      Scanner myReader = new Scanner(myObj);
      while (myReader.hasNextLine()) {
        String data = myReader.nextLine();
        System.out.println(data);
      }
      myReader.close();
    } catch (FileNotFoundException e) {
      System.out.println("An error occurred.");
      e.printStackTrace();
    }
  }
}
```

## In Class Exercise & Assignment for the week

* Continue implementation of Inventory module.
* Initialize inventory from a file instead(ie remove hard coded values.)
* Create another constructor in your book class that takes a string.
    * constructor should split string, You can assume that `,` is a seperator & order of string is defined as
    * ISBN number,Title, Author,Category, Price
    * Example `ISBN001,How to program in cPlusPlus,John Doe,Educational, 19.2`


