---
title: Week Twelve
sidebar: mydoc_sidebar
permalink: mydoc_week_thirteen.html
folder: mydoc
---

## Static
* [Static keyword](https://www.w3schools.com/java/ref_keyword_static.asp)
* [Static in a class](https://www.w3schools.com/js/js_class_static.asp)
* Variables per class. (Instance variables are variables per method).
* After you run the programs notice the value of count

```
package com.inventory;

public class Book {

    String title;
    String author;

    static int count;
    public Book(String inputTitle, String inputAuthor) {
        title = inputTitle;
        author = inputAuthor;
        count++;
    }


    @Override
    public String toString() {
        return "Book{" +
                "title='" + title + '\'' +
                ", author='" + author + '\'' +
                ", count=" + count +
                '}';
    }
}

```

```
package com.inventory;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class Inventory {

    List booksList;

    public Inventory() {
        booksList = new ArrayList();
    }

    public void populateInventory() {
        Book bookOne = new Book("How to program in Java", "John Doe");
        Book bookTwo = new Book("How to program in CPlusPlus", "John Doe");
        booksList.add(bookOne);
        booksList.add(bookTwo);
    }

    // print Inventory

    public void printInventory() {
        Iterator iterator = booksList.iterator();
        while(iterator.hasNext()) {
            Book book = (Book)iterator.next();
            System.out.println(book.toString());
        }
    }

    // search for books

    public Book search(String name){
       Iterator iterator = booksList.iterator();
       while(iterator.hasNext()) {
           Book book = (Book)iterator.next();
           if(book.title == name) {
               return book;
           }
       }
       return null;
    }

}

```

```
import com.inventory.Inventory;
import com.inventory.Book;

public class ECommerceMain {

    public static void main(String[] args) {
        Inventory myInventory = new Inventory();

        myInventory.populateInventory();
        myInventory.printInventory();

        Book searchedBook = myInventory.search("How to program in Java");
        System.out.println(searchedBook.toString());
    }
}
```


## Type casting
```
public class CastingExample {

    public static void main(String[] args) {
        double doubleValue = 17.3;

        int intValue = (int)doubleValue;

        System.out.println(intValue);
    }
}
```

Also notice casting in 

```
    public void printInventory() {
        Iterator iterator = booksList.iterator();
        while(iterator.hasNext()) {
            Book book = (Book)iterator.next();
            System.out.println(book.toString());
        }
    }
```

## Abstract class

## State machines
* [State Machines](https://rambethina.github.io/java/mydoc_week_twelve.html#in-class-exercise)

## Encoders
* [Example using encoders](https://rambethina.github.io/java/mydoc_week_twelve.html#encoders)

## Game pad controls & Servo
* [Game pad controls & Servo](https://rambethina.github.io/java/mydoc_week_twelve.html#game-pad-controls--servo)

## Inclass exercise
* [Drive in a square](https://rambethina.github.io/java/mydoc_week_twelve.html#in-class-exercises)
* [Solution](https://rambethina.github.io/java/mydoc_week_twelve.html#in-class-exercises)
* [Run exercise and figure out the problem](https://rambethina.github.io/java/mydoc_week_twelve.html#in-class-exercise-1)