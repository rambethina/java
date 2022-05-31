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
    * Example - Ticket queue

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

