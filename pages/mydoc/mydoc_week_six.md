---
title: Week Six
sidebar: mydoc_sidebar
permalink: mydoc_week_six.html
folder: mydoc
---

## Sentence Exercise

* Creating a new project may be better.
* Create a new class called StaticSentenceExercise with your main method.
* Part One - Last weeks in class exericse, Find first index of word. (We will implement this as a refresher for last couple weeks content, we will refresh our topics on methods/functions, for loops etc.). Also create this new method called firstOccurenceOfWord in a new class called SentenceUtility.
* Part Two - Find last index of word. Create a new method called lastOccurenceOfWord in SentenceUtility class  (Try implementing on your own, but if you need help look below in SentenceUtility class, lastOccurenceOfWord)

Your final implementation may look like

```
public class SentenceUtility {

    public static int firstOccurenceOfWord(String sentence, String word) {
        String[] allWords = sentence.split(" ");
        for (int i = 0; i < allWords.length; i++) {
            String currentWord = allWords[i];
            if (currentWord.equalsIgnoreCase(word)) {
                return i;
            }
        }
        return -1;
    }

    public static int lastOccurenceOfWord(String sentence, String word) {

        String[] allWords = sentence.replace(",", "")
                .split(" ");
        for (int i = allWords.length - 1; i > 0; i--) {
            String currentWord = allWords[i];
            if (currentWord.equalsIgnoreCase(word)) {
                return i;
            }
        }
        return -1;
    }

    public static void printWordsInReverse(String sentence) {
        String[] allWords = sentence.split(" ");
        for (int i = allWords.length - 1; i > 0; i--) {
            String currentWord = allWords[i];
            System.out.println(currentWord);
        }
    }
}
```

```
public class StaticSentenceExercise {

    public static void main(String[] args) {
        String constitutionalConventionSentence = "The Constitutional Convention in Philadelphia met between May and September of 1787 to address the problems of the weak central government that existed under the Articles of Confederation.";

        int indexOfWordConvention = SentenceUtility.firstOccurenceOfWord(constitutionalConventionSentence, "Convention");

        System.out.println("Index of word convention :"+ indexOfWordConvention);

//        SentenceUtility.printWordsInReverse(constitutionalConventionSentence);

        String gettyburgAddressSentence = "Four score and seven years ago our fathers brought forth on this continent, a new nation, conceived in Liberty, and dedicated to the proposition that all men are created equal.";

        int indexOfWordLiberty = SentenceUtility.lastOccurenceOfWord(gettyburgAddressSentence,"Liberty,");

        System.out.println("Index of word Liberty :"+ indexOfWordLiberty);

    }
}
```

### Observations

* Notice how a static method on another class is called. `ClassName.method` -> `SentenceUtility.firstOccurenceOfWord`


## Object Oriented Programming

* [What is OOP](https://www.w3schools.com/java/java_oop.asp)
* Examples of Object Oriented Programming based on the examples we have already seen.

Below are two examples of Sentences

Example one: - constitutional convention (constitutionalConventionSentence)

"The Constitutional Convention in Philadelphia met between May and September of 1787 to address the problems of the weak central government that existed under the Articles of Confederation."

Example two: - Gettysburg Address (gettysburgAddressSentence)

"Four score and seven years ago our fathers brought forth on this continent, a new nation, conceived in Liberty, and dedicated to the proposition that all men are created equal."

In OOP we can assume that Sentence is a class, and constitutionalConventionSentence & gettysburgAddressSentence are instances of Sentence, or ***Objects***

A class can be thought of as a template ie our Sentence class in a template and we can multiple instances/objects of Sentence constitutionalConventionSentence & gettysburgAddressSentence being 2 of them.

### Sentence Class

```
public class Sentence {

    private String sentenceString;
    private String[] allWords;

    //Constructor
    //Special method which does not have a return type.
    //Initialize values of instance variables ie initialize value of sentenceString
    public Sentence(String sentenceInput) {
        this.sentenceString = sentenceInput;
        allWords = this.sentenceString.split(" ");
    }

    //Functions/methods of sentence class, notice we do not need to pass sentence as an input argument
    public int getFirstIndexOfWord(String word){
        for (int i = allWords.length - 1; i > 0; i--) {
            String currentWord = allWords[i];
            if (currentWord.equalsIgnoreCase(word)) {
                return i;
            }
        }
        return -1;
    }

    //Functions/methods of sentence class, notice we do not need to pass sentence as an input argument
    public int getLastIndexOfWord(String word){
        //provide implementation
        return 0;
    }
}

```

```
public class SentenceMain {

    public static void main(String[] args) {
        Sentence constitutionalConventionSentence =
                new Sentence("The Constitutional Convention in Philadelphia met between May and September of 1787 to address the problems of the weak central government that existed under the Articles of Confederation.");
        int indexOfWordConvention = constitutionalConventionSentence.getFirstIndexOfWord("Convention");
        System.out.println("Index of word convention :"+ indexOfWordConvention);

        Sentence gettyburgAddressSentence =
                new Sentence("Four score and seven years ago our fathers brought forth on this continent, a new nation, conceived in Liberty, and dedicated to the proposition that all men are created equal.");
        int indexOfWordLiberty = gettyburgAddressSentence.getFirstIndexOfWord("Liberty");
        System.out.println("Index of word Liberty :"+ indexOfWordLiberty);

    }
}
```


### In Class exercise

Provide implementations for getLastIndexOfWord in Sentence class. Test your new method by calling it in main method.


### Observations

* We create an object of a class using the ***new*** key word.
* Looing at SentenceMain class main  method notice we are not passing sentence to getFirstIndexOfWord method. On which sentence are we getting the getFirstIndexOfWord?

## Assignment

Create a class called Circle with

 * instance variable radius
 * provide a constructor
 * provide 2 methods which calculate area and circumference.

Test your new class Circle created.

```
public class CircleMainTest {

    public static void main(String[] args) {
        Circle smallCircle = new Circle(5);

        System.out.println("Area of small circle is :"+ smallCircle.area());
        System.out.println("Circumference of small circle is :"+ smallCircle.circumference());

        Circle bigCircle = new Circle(15);

        System.out.println("Area of small circle is :"+ bigCircle.area());
        System.out.println("Circumference of small circle is :"+ bigCircle.circumference());
    }
}
```