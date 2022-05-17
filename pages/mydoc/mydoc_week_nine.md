---
title: Week Nine
sidebar: mydoc_sidebar
permalink: mydoc_week_nine.html
folder: mydoc
---

## Introduction to data structures

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


## Programming an OOP system

* For our final project we will work on creating an eCommerce system. During this class will one
module in our eCommerce Application.

Inventory module should satisfy the following
* Store items in our inventory.
* Display items in our inventory.
* Total cost of our inventory.
* Search based on ISBN Number.