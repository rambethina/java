---
title: Week Ten
sidebar: mydoc_sidebar
permalink: mydoc_week_ten.html
folder: mydoc
---

## Continue from last week.
* Exceptions
* Files

## Data structures
* Map

```
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;

public class MapSample {

    public static void main(String[] args) {
        Map sampleMap = new HashMap<>();
        sampleMap.put("1", "one");
        sampleMap.put("2", "two");
        sampleMap.put("3", "three");

        Iterator iterator = sampleMap.keySet().iterator();
        while(iterator.hasNext()) {
            String key = (String) iterator.next();
            System.out.println(key);
            String value = (String) sampleMap.get(key);
            System.out.println(value);
        }
    }
}
```

* Queue - First In First Out
    * Example - Reservation system

```
import java.util.PriorityQueue;

public class QueueSample {

    public static void main(String[] args) {
        PriorityQueue priorityQueue = new PriorityQueue();
        priorityQueue.add("one");
        priorityQueue.add("two");
        priorityQueue.add("three");

        System.out.println(priorityQueue.poll());
        System.out.println(priorityQueue.poll());
        System.out.println(priorityQueue.poll());


    }
}
```

* Stack - First in last out
    * Example - browser back button
import java.util.Stack;

public class StackSample {

    public static void main(String[] args) {
        Stack stack = new Stack();
        stack.push("one");
        stack.push("two");
        stack.push("three");

        System.out.println(stack.pop());
        System.out.println(stack.pop());
        System.out.println(stack.pop());
    }
}

## Interface

```
public interface Shape {
    public double area();
}

```

```
public class Square implements Shape{
    private int length;

    public Square(int length) {
        this.length = length;
    }

    @Override
    public double area() {
        return length*length;
    }
}
```


## Abstract class

```
public abstract class Product {

    double price;

    public Product(double price) {
        this.price = price;
    }

    public abstract void printDetails();
}
```

```
import java.util.Arrays;

public class Book extends Product{

    private final String isbnNumber;
    private String title;
    private String author;
    private String category;
//    private double price;
    private String[] reviews;

    public Book(String isbnNumber, String title, String author, String category, double price, String[] reviews) {
        super(price);
        this.title = title;
        this.isbnNumber = isbnNumber;
        this.author = author;
        this.category = category;
//        this.price = price;
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

    @Override
    public void printDetails() {
        System.out.println(" ** Product details **");

        System.out.println("Title :"+title);
        System.out.println("Price :"+price);
    }
}
```

## User Input
* [User Input](https://www.w3schools.com/java/java_user_input.asp)

```
import java.util.Scanner;  // Import the Scanner class

class Main {
  public static void main(String[] args) {
    Scanner myObj = new Scanner(System.in);  // Create a Scanner object
    System.out.println("Enter username");

    String userName = myObj.nextLine();  // Read user input
    System.out.println("Username is: " + userName);  // Output user input
  }
}
```


## FINAL PROJECT
Let us build a simple eCommerce application similar to Amazon (But way simpler). Our eCommerce application has the following modules

* Registration & Login (Optional)
* Inventory (Mandatory)
* Checkout (Mandatory)

Our simple eCommerce should satisfy the following

Registration & Login

* User should be able to register. During registration they will provide the following
    * email address
    * password
    * first name
    * last name
    * shipping address (line1, line2, city, state, country, postal code)
    * mailing address (line1, line2, city, state, country, postal code)
    * phone number
* After registration sanitize user input before storing in our database.(for now we will store in a file)
    * You can look at previous assignments. (Sanitization steps will be added later, but for now assume that you will have to sanitize input)
* Our eCommerce application should allow multiple users to register.
* Registered users should be able to login with their email address and password.

Inventory
* After logging users should be able to browse the list of books. We should display the list based on the inventory we have.
* You can assume list of books in inventory will be provided in a flat file.(Sample file below) - [Read from a file](https://rambethina.github.io/java/mydoc_week_nine.html#working-with-files)
* For each book users should see the following information
    * ISBN number (unique identifier of a book)
    * Title
    * Cost
    * Book Category. (Valid values being Educational, History, Travel, Cookings)
    * Author.
* Users should be able to choose a book and add it to their cart, remove it from their cart.
* Users should be able to see total cost of their cart.
* After a user checkouts, 
    * inventory should be updated accordingly.
    * Print a summary of User details
    * Print cart details with total amount and shipping address.


SAMPLE FLAT FILE
ISBN001, How to program in cPlusPlus, 19.2, Educational, John Doe
ISBN001, How to program in cPlusPlus, 19.2, Educational, John Doe
ISBN002, How to program in Java, 22.6, Educational, Sally Smith
ISBN003, Destinations of a life time, 6.99, Travel, James Madison
ISBN004, Top 100 places to visit, 6.45, Travel, James Franklin
ISBN005, French revolution, 12.33, History, Fances wade
ISBN006, Civil war, 33.0, History, Davis Mark
ISBN002, How to program in Java, 22.6, Educational, Sally Smith
ISBN005, French revolution, 12.33, History, Fances wade
ISBN003, Destinations of a life time, 6.99, Travel, James Madison
