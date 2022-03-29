---
title: Week One
sidebar: mydoc_sidebar
permalink: mydoc_week_two.html
folder: mydoc
---

## Goal - Hello World exercise

* Kahoot (Get used to Kahoot, Logistics)
* Hello World Program
* Deep dive Hello World Program ()
* In Class Exercise
* Comments
* Kahoot (Week 2 course content, Basics, Comments)
* Variables
* Common data types (if we have time, we will look at more data types in next class)
* Assignment
  
## Hello World Exercise.

## Creating a new project in IntelliJ

Find IntelliJ IDEA CE (you may have an icon in your Desktop or Applications), Open it.

* Create a New Project
* In the next screen make sure SDK is populated.
* Click on Next.
* Give a project name.

* Right click on src -> New -> Java Class.
* Give a name -> WeekTwoHelloWorld.
* Hello world code auto generates.
* Inorder to run your progam, Right click on the class you created and click on Run

Hello world exercise

```
//Name of class is WeekTwoHelloWorld
// Notice there is a main method in WeekTwoHelloWorld class
public class WeekTwoHelloWorld {
   
    //main method
    //Notice the opening and closing ()
    //Notice opening and closing {}
    public static void main(String args[]) {
        System.out.println("Replace Content");
    }
}
```

## Observations
* Java is case sensitive. (ie WeekTwoHelloWorld is different from weektwoHelloWorld,  weektwoHelloWorld would be considered a new class.)
* Name of file and class should be the same.
* In Java everything must be in a class.
* In Java if you want to print something, you will normally use System.out.println(), and pass the contents to print within ""

## In Class Exercise.

* Create a program to print one of the following
  * Java is an OOP (Object oriented programming).
  * In Java everything must be in a class.
  * Java is case sensitive. 
  * In Java comments will not be executed.

Whats wrong with the code below.

```
public class WeekTwoHelloWorld {
    public static void main(String args[]) {
        System.out.println("Replace Content");
}
```

Whats wrong with the code below.

```
public class WeekTwoHelloWorld {
    public static void main(String args[]) {
        System.out.println("Replace Content";
    }
}
```

Whats wrong with the code below.

```
public class WeekTwoHelloWorld {
    public static void main(string args[]) {
        System.out.println("Replace Content)";
    }
}
```

## Comments
* Refer [w3schools](https://www.w3schools.com/java/java_comments.asp)

## Kahoot

## Variables
* Refer [w3schools](https://www.w3schools.com/java/java_variables.asp)

## Assignments
* [Install Git on your system.](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) 
  * [Windows](https://git-scm.com/download/win), You can also follow the [video](https://www.simplilearn.com/tutorials/git-tutorial/git-installation-on-windows), Watch video upto 1min 30 sec.
  * if you are using a mac git may already be installed. On your terminal type in `git --version` , If git is not installed you will be prompted to install git. If git is installed you may see something similar to below
  ```
  git --version
  git version 2.24.3 (Apple Git-128)
  ```
* [Create a github account.](https://www.wikihow.com/Create-an-Account-on-GitHub)
* Suggested reading. [Getting started in FTC](https://gm0.org/en/stable/docs/getting-started-in-ftc/index.html)


FAQ


