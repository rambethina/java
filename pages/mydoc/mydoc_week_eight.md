---
title: Week Eight
sidebar: mydoc_sidebar
permalink: mydoc_week_eight.html
folder: mydoc
---

## Class revisited

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

## In class exercise. 
* Part of last weeks class, Make sure Book class works.
* Create a new project and copy the following classes and run main program.


```
public class Book {

    public String title;
    public String author;
    public String category;
    public double price;
    public String[] reviews;

    public void print() {
        System.out.println("*** Start Book details ***");
        System.out.println("Title : "+title);
        System.out.println("Author : "+author);
        System.out.println("Category : "+category);
        System.out.println("Price : "+price);
        System.out.println("******* Reviews ********");
        for(int i = 0; i < reviews.length; i++) {
            System.out.println(reviews[i]);
        }
        System.out.println("*** End Book details ***");
    }
}

```

```
public class WeekEightStarter {

    public static void main(String[] args) {

        Book bookOne = new Book();
        bookOne.title = "How to program in Java";
        bookOne.author = "John Doe";
        bookOne.price = 20.2;
        bookOne.category = "Educational";
        bookOne.reviews = new String[] {"Good book", "Verbose"};

        bookOne.print();
    }
}
```

## Break
* Time for questions
* Look at final project below, read the project documentation and think thru what classes you need, what instances variables you need per class and methods you need for each class.
## Final project - Exercise

Goal: Based on following description figure out
* List of classes, 
* Instance variables per class ,
* Methods per class

Let us build a simple eCommerce application similar to Amazon (But way simpler). Our simple eCommerce should satisfy the following

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
* After logging users should be able to browse the list of books. We should display the list based on the inventory we have.
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
* Modify your main, Use the newly created constructor to intialize your instance variables. 

If you dont have exercise from previous class, here is a starting point.

```
public class Book {

    public String title;
    public String author;
    public String category;
    public double price;
    public String[] reviews;

    public void print() {
        System.out.println("*** Start Book details ***");
        System.out.println("Title : "+title);
        System.out.println("Author : "+author);
        System.out.println("Category : "+category);
        System.out.println("Price : "+price);
        System.out.println("******* Reviews ********");
        for(int i = 0; i < reviews.length; i++) {
            System.out.println(reviews[i]);
        }
        System.out.println("*** End Book details ***");
    }
}

```

```
public class WeekEightStarter {

    public static void main(String[] args) {

        Book bookOne = new Book();
        bookOne.title = "How to program in Java";
        bookOne.author = "John Doe";
        bookOne.price = 20.2;
        bookOne.category = "Educational";
        bookOne.reviews = new String[] {"Good book", "Verbose"};

        bookOne.print();
    }
}
```

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

## Enums
* Refer [w3schools](https://www.w3schools.com/java/java_enums.asp)

```
public enum DogBreeds {
    PUG,
    POODLE
}
```

```
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

```
public class WeekEightExEnum {

    public static void main(String[] args) {

        Dog myDog = new Dog("Grady", DogBreeds.PUG);
        myDog.printDogDetails();

    }
}
```

## Exercises - Use enums in your book class

* Create an enum for Book Categories -> BookCategory
* Assume only valid values are
```
Educational, 
History, 
Travel, 
Cookings
```
* Change your Book class and main class to use enums


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