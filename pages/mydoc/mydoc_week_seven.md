---
title: Week Seven
sidebar: mydoc_sidebar
permalink: mydoc_week_seven.html
folder: mydoc
---

## Questions of Midterm assignment

## Introduction Class, Objects
* [Class & Objects](https://www.w3schools.com/java/java_classes.asp)

## In Class Exercise One

Assume we are going to build a eCommerce application that sells books.

Identify what attributes a book would contain.

As an example you can look at [amazon](https://www.amazon.com/gp/browse.html?rw_useCurrentProtocol=1&node=8192263011&ref_=bhp_brws_100bks)

You can click on each book to identify attributes of a book.

## Create an object of a class

Example

Create Class

```
public class Dog {
    public String name;
    public String breed;
    public String[] traits;

    public void printDetails() {
        System.out.println("Name of dog is :"+name);
        System.out.println("Name of breed is :"+breed);
        System.out.println("The following are traits of this dog");
        for(int i = 0; i < traits.length; i++) {
            System.out.println(traits[i])
        }
    }
}
```

Create Object in main method, I am creating another class that has a main method

```
public class WeekSevenEx1 {
    Dog dogOne = new Dog();
    dogOne.name = "Grady";
    dogOne.breed = "Pug"
    dogOne.traits = {"friendly", "naughty"};

    dogOne.printDetails();
}
```

## In Class Exercise (Continuation of Exercise One)

* Create a Book class
* Define attributes of the Book (From part one of the Exercise)
* Create a print method that prints the values of attributes of the Book

* Create another class that containts main method.
* Create couple of Objects of Book class and print details of each book.

## Class constructor
* [Constructor](https://www.w3schools.com/java/java_constructors.asp)

## Access modifiers
* [access modifiers](https://www.w3schools.com/java/java_modifiers.asp)


