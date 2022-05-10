---
title: Week Eight
sidebar: mydoc_sidebar
permalink: mydoc_week_eight.html
folder: mydoc
---

## Class revisited

## Final project - Exercise

Goal: Based on following description figure out List of classes, instance variables per class methods per class

Let us build a simple eCommerce application similar to Amazon. Our simple eCommerce should satisfy the following

* User should be able to register. During registration they will provide the following
    * email address
    * password
    * first name
    * last name
    * shipping address (line1, line2, city, state, country, postal code)
    * mailing address (line1, line2, city, state, country, postal code)
    * phone number
* Our eCommerce application should allow multiple users to register.
* Registered users should be able to login with their email address and password.
* After logging users should be able to browse the list of books. We should display the list based on the inventory we have.
* For each book users should see the following information
    * ISBN number (unique identifier of a book)
    * Title
    * Cost
    * Book Category. (Valid values being Educational, History, Travel, Cookings)
    * Author.
* Users should be able to choose a book and add it to their cart, remove it from their cart.
* Users should be able to see total cost of their cart.
* After a user checkouts, inventory should be updated accordingly.


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

