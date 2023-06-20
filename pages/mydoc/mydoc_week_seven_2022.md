---
title: Week Seven
sidebar: mydoc_sidebar
permalink: mydoc_week_seven_2022.html
folder: mydoc
---

## Questions - Midterm assignment
* [Midterm Assignment](https://rambethina.github.io/java/mydoc_week_six.html#assignment--mid-term-project)
* Due Date: May 17, 2022
* Submit a link to github project
## Introduction Class, Objects
* [Class & Objects](https://www.w3schools.com/java/java_classes.asp)

Couple of example

```
Dog

Attributes:
    - name
    - breed
    - traits (Array)

Methods:
    - printDetails
```


```
Circle
Attributes:
    - radius

Methods:
    - calcuateArea
    - calculateCircumference

```

## In Class Exercise One

Assume we are going to build a eCommerce application that sells books.

Identify what attributes a book would contain.

As an example you can look at [amazon](https://www.amazon.com/gp/browse.html?rw_useCurrentProtocol=1&node=8192263011&ref_=bhp_brws_100bks)

You can click on each book to identify attributes of a book.

## Optional in class exercise
Given an array

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
            System.out.println(traits[i]);
        }
    }
}
```

Create Object in main method, I am creating another class that has a main method

```
public class WeekSevenEx1 {
    public static void main(String args[]) {
        Dog dogOne = new Dog();
        dogOne.name = "Grady";
        dogOne.breed = "Pug";
        dogOne.traits = new String[]{"friendly", "naughty"};

        dogOne.printDetails();

        Dog dogTwo = new Dog();
        dogTwo.name = "Comet";
        dogTwo.breed = "Poodle";
        dogTwo.traits = new String[]{"Playful", "lazy"};

        dogTwo.printDetails();
    }

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

```
public class Dog {
    public String name;
    public String breed;
    public String[] traits;

    //Constructor
    public Dog(String name, String breed, String[] traits) {
        this.name = name;
        this.breed = breed;
        this.traits = traits;
    }

    public void printDetails() {
        System.out.println("Name of dog is :"+name);
        System.out.println("Name of breed is :"+breed);
        System.out.println("The following are traits of this dog");
        for(int i = 0; i < traits.length; i++) {
            System.out.println(traits[i]);
        }
    }
}
```

```
public class WeekSevenEx2 {

    public static void main(String args[]) {
        Dog dogTwo = new Dog("Grady", "Pug", new String[]{"friendly", "naughty"});

        dogTwo.printDetails();
    }

}
```

## In Class Exercise (Continuation of Exercise One)
* Create a constructor for the Book class you created
* Modify you main, Use the newly created constructor to intialize your instance variables. 
## Access modifiers
* [access modifiers](https://www.w3schools.com/java/java_modifiers.asp)

```
public class Dog {
    String name;
    String breed;
    String[] traits;

    //Constructor
    public Dog(String name, String breed, String[] traits) {
        this.name = name;
        this.breed = breed;
        this.traits = traits;
    }

    public void printDetails() {
        System.out.println("Name of dog is :"+name);
        System.out.println("Name of breed is :"+breed);
        System.out.println("The following are traits of this dog");
        for(int i = 0; i < traits.length; i++) {
            System.out.println(traits[i]);
        }
    }
}
```

Note the following will result in a compilation error
```
public class WeekSevenEx2 {

    public static void main(String args[]) {
        Dog dogOne = new Dog("Grady", "Pug",new String[]{"friendly", "naughty"});

        System.out.println(dogOne.name); // should result in a compilation error since name is a private variable
        dogOne.printDetails();
    }

}
```
## static key word
Static variables are class variables, Their value is the same irrespective of the Object

Exercise
* Implement Circle class
* Suggested instance variables for your class `int radius`
* Implement area methods

```
Area of circle can be calculated as 

double area = radius * radius * Math.PI; // notice how we are using PI from Math class, Since its a static variable
```


## Assignment
* [Create a github account if you have not done so](https://github.com/www.wikihow.com/Create-an-Account-on-GitHub)
* [Git integration with IntelliJ](https://www.youtube.com/watch?v=mf2-MOl0VXY)