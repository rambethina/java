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



