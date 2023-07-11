---
title: Week Nine
sidebar: mydoc_sidebar
permalink: mydoc_week_nine_2022.html
folder: mydoc
---

# Inheritance

## Interfaces

```java
package com.mynewclass;

public interface Shape {
    public double area();
}
```

```java
package com.mynewclass;

public class Cirlce implements Shape{

    private double radius;
    private static double PI = 3.14;

    public Cirlce(double inputRadius) {
        this.radius = inputRadius;
    }

    public double getArea(){
        return PI*radius*radius;
    }

    @Override
    public double area() {
        return PI*radius*radius;
    }
}
```

```java
package com;

import com.mynewclass.Cirlce;
import com.mynewclass.Shape;

public class InterfaceMain {

    public static void main(String[] args) {
        Shape smallCirle = new Cirlce(20.2);
        System.out.println(smallCirle.area());
    }
}

```


Another example: Let us assume I am working on a raised bed garden and would like to calculate total area of my raised bed. Let us assume we have different shaped for individual beds.

```java
package com.mynewclass;

public class Rectangle implements Shape{
    
    private double width;
    private double height;
    
    public Rectangle(double width, double height) {
        this.width = width;
        this.height = height;
    }
    @Override
    public double area() {
        return width * height;
    }
}
```

```java
import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class InterfaceComplexMain {

    public static void main(String[] args) {
        Shape smallCirle = new Cirlce(20.2);
        Shape squareLotOne = new Rectangle(12.1, 23.1);

        List lots = new ArrayList<Shape>();
        double totalRaisedBedArea = 0.0;

        lots.add(smallCirle);
        lots.add(squareLotOne);

        Iterator<Shape> lotsIterator = lots.iterator();
        while (lotsIterator.hasNext()) {
            totalRaisedBedArea += lotsIterator.next().area();
        }

        System.out.println(totalRaisedBedArea);
    }
}

```



## Abstract Class

```java
package asbstractsamples;

import java.util.*;

public abstract class AbstractShape {


    Comparator c = new Comparator<String>()
    {
        public int compare(String s1, String s2) {
            return Integer.compare(s1.length(), s2.length());
        }
    };

    public void prettyPrint(){
        System.out.println("");
        List<String> printDetails = getPrintLineItems();

        ArrayList copy = new ArrayList (printDetails);

        Collections.sort( printDetails, c);
        int start = 0;

        int maxSize = printDetails.get(printDetails.size()-1).length();

        while(start < maxSize + 2) {
            System.out.print("*");
            start++;
        }
        System.out.println("");
        Iterator iterator = copy.iterator();
        while(iterator.hasNext()) {
            System.out.println("*"+ iterator.next());
        }

        start = 0;

        while(start < maxSize + 2) {
            System.out.print("*");
            start++;
        }
        System.out.println("");
    }

    public abstract double area();

    public abstract List<String> getPrintLineItems();
}
```

```java
package asbstractsamples;

import java.util.ArrayList;
import java.util.List;

public class CircleImpl extends AbstractShape{

    private double radius;
    private static double PI = 3.14;

    public CircleImpl(double radius) {
        this.radius = radius;
    }

    @Override
    public double area() {
        return PI * this.radius * this.radius;
    }

    @Override
    public List<String> getPrintLineItems() {
        List details = new ArrayList();
        details.add("This is a circle");
        details.add("Area is calculated by multiplying PI * radius * radius :");
        details.add("The area is "+area());
        return details;
    }
}
```

```java
package asbstractsamples;

import java.util.ArrayList;
import java.util.List;

public class RectangleImpl extends AbstractShape{
    private double width;
    private double height;


    public RectangleImpl(double width, double height) {
        this.width = width;
        this.height = height;
    }

    @Override
    public double area() {
        return width * height;
    }

    @Override
    public List<String> getPrintLineItems() {
        List details = new ArrayList();
        details.add("This is
        
         a rectangle");
        details.add("Area is calculated by multiplying lenght * height");
        details.add("The area is "+area());
        return details;
    }
}
```

```java
package asbstractsamples;

public class AbstractMain {

    public static void main(String[] args) {
        AbstractShape rect = new RectangleImpl(20, 30);
        rect.prettyPrint();


        AbstractShape circle = new CircleImpl(32);
        circle.prettyPrint();
    }
}
```

Output

```text

***************************************************
*This is a rectangle
*Area is calculated by multiplying lenght * height
*The area is 600.0
***************************************************

**********************************************************
*This is a circle
*Area is calculated by multiplying PI * radius * radius :
*The area is 3215.36
**********************************************************
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
