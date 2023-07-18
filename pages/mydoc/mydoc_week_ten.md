---
title: Week Ten
sidebar: mydoc_sidebar
permalink: mydoc_week_ten.html
folder: mydoc
---

## Data structures

* Map
  * Example - Retrieving infromation where there is a large volume of data and we know the key.
  * Example - Handling duplicates.

```java
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

```java
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

```java
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
```

## Enums

* Refer [w3schools](https://www.w3schools.com/java/java_enums.asp)

```java
public enum DogBreeds {
    PUG,
    POODLE
}
```

```java
public class Dog {
    public String name;
    public DogBreeds breed;

    public Dog(String name, DogBreeds dogBreed) {
        this.name = name;
        this.breed = dogBreed;
    }

    public void printDogDetails() {
        System.out.println("Name of dog is :"+name);
        System.out.println("Breed of dog is :"+breed);
    }
}
```

```java
public class WeekNineEnum {

    public static void main(String[] args) {

        Dog myDog = new Dog("Grady", DogBreeds.PUG);
        myDog.printDogDetails();

    }
}
```

## Exceptions

* [Exceptions](https://www.w3schools.com/java/java_try_catch.asp)



## User Input

* [User Input](https://www.w3schools.com/java/java_user_input.asp)

```java
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


## FTC Simulator if you need it

* We will be using a [simulator](https://github.com/Beta8397/virtual_robot), Please download before next class


## InClass Assignment

We will begin with last weeks homework....

Lets begin implementation of the Cart class.

Provide instance variables. (Cart contains a list of books.)
Provide a constructor to instialize your instance variables.
Provide implementations for the following methods.
Add book to Cart: This method takes a book as an input argument and adds it to the list.
getTotal: This method iterates over the list gets each books cost, adds it up and returns total.
Change your main class ECommerceSimple to test your new Cart class. Sample Mock implementation below.

Sample Main class Implementation

```java
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

For in class exercise.

Enhance our eCommerce application. Let us assume our we would also like to sell Computers. For each computer let us assume we would like to capture the following details

* Serial Number - This is the unique identifier for a computer similar to ISBN Number for a book.
* Brand - Examples Mac, Dell, HP
* Cost

Change your existing program to add computers to your cart.

Couple of things you may want to do.

* Create an interface or abstract class called Product and implement or extend `Product` so you can have a generic method in Cart called `addProduct`
* In your Cart you may also want to have a list of products instead of a list of books or computers.
