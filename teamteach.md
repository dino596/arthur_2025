---
layout: post
title: Team Teach Memories
description:  Memorable things from Team Teaches
type: issue
permalink: /teamteach
comments: true
---

### Unit 1: Primitive & Reference Types
In this unit, we learned about the fundamentals to understanding how the language handles data. Primitive types, like `int`, `float`, `char`, and `boolean`, represent simple values and are stored directly in memory, offering efficient performance. Reference types, such as arrays, classes, and interfaces, store references (or memory addresses) to objects rather than the actual data. This distinction helps developers understand how data is managed, manipulated, and optimized in memory. Mastering data types is key to writing efficient, clear code, as it influences how variables are declared, how operators interact with them, and how data structures are implemented.
```java
public class Account {
    private String name;
    private double balance;
    private int accountNumber;

    private static int lastAccountNumber = 0;
    private static double interestRate = 0.04;

    public Account(String name, double balance) {
        this.name = name;
        this.balance = balance;
        accountNumber = lastAccountNumber++;
    }

    public double calculateInterest() {
        return balance *= interestRate;
    }
}
```

### Unit 2: Using Objects
In this unit, we learned about objects: essential Java concepts for building a strong foundation in object-oriented programming. By understanding how to create and initialize objects, write and call methods, and use important classes like `String` and `Math`, you gain the tools needed to manipulate data and perform complex operations. The ability to overload methods and constructors, as well as efficiently use string methods and mathematical functions, allows for more flexible and powerful programming. These topics not only improve coding skills but also help in writing cleaner, more efficient, and maintainable Java code.
```java
public class Circle {
    public double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    public double circumference() {
        return 2 * Math.PI * radius;
    }

    public double area() {
        return Math.PI * Math.pow(radius, 2);
    }
}
public class Main {
    public static void main(String[] args) {
        Circle circle1 = new Circle(5.0);
        Circle circle2 = new Circle(7.0);

        System.out.println("Circle 1:");
        System.out.println("Radius: " + circle1.radius);
        System.out.println("Circumference: " + circle1.circumference());
        System.out.println("Area: " + circle1.area());

        System.out.println("\nCircle 2:");
        System.out.println("Radius: " + circle2.radius);
        System.out.println("Circumference: " + circle2.circumference());
        System.out.println("Area: " + circle2.area());
    }
}
```

### Unit 3: Boolean
In this unit, we learned about Boolean logic, which is crucial when programming in Java, as it forms the foundation for controlling program flow. In Java, Boolean expressions are used in conditional statements like `if`, `else`, and `switch`, as well as in loops like `while` and `for`. These structures enable Java programs to make decisions based on true or false conditions, allowing developers to implement complex algorithms and decision-making processes. Understanding Boolean logic in Java is essential for writing efficient, well-structured code, as it drives the logic behind everything from basic comparisons to advanced control structures.
```java
import java.util.Scanner;

public class PrimeClub {
    int age;
    double income;
    boolean student;

    public PrimeClub() {
        Scanner input = new Scanner(System.in);
        System.out.println("input age: ");
        age = input.nextInt();
        System.out.println("input income: ");
        income = input.nextDouble();
        System.out.println("are you a student");
        student = input.next().toLowerCase().equals("yes");
    }

    public PrimeClub(int age, double income, boolean student) {
        this.age = age;
        this.income = income;
        this.student = student;
    }

    private boolean checkBasicMembership() {
        return (age > 18 && income >= 20000);
    }

    private boolean checkPremiumMembership() {
        return (age > 25 && income >= 50000);
    }

    private boolean checkStudent() {
        return student;
    }

    private boolean checkSenior() {
        return age > 65;
    }

    public static void main() {
        PrimeClub member = new PrimeClub();

        if (member.checkPremiumMembership()) {
            System.out.println("you qualify for premium membership");
        } else if (member.checkSenior()) {
            System.out.println("you qualify for senior discount");
        } else if (member.checkStudent()) {
            System.out.println("you qualify for student discount");
        } else if (member.checkBasicMembership()) {
            System.out.println("you qualify for basic membership");
        } else {
            System.out.println("you do not qualify for any memberships or discounts");
        }
    }
}

PrimeClub.main();
```

### Unit 4: Iteration
We taught this unit. Iteration in Java is used to repeatedly execute a block of code as long as a specified condition is met. This is achieved through loops, such as `for`, `while`, and `do-while`, allowing a program to process data efficiently, automate repetitive tasks, and handle dynamic data structures like arrays and lists. Iteration is important because it simplifies tasks that would otherwise require extensive manual coding, making programs more concise and adaptable. It is essential for operations like searching, sorting, and modifying large datasets, enabling Java programs to handle complex computations effectively. String iteration in Java refers to the process of traversing each character in a string, typically to perform operations like searching, modifying, or analyzing the content. This can be done using loops such as `for`, `while`, or enhanced `for` loops. For example, using a `for` loop, you can iterate through a string character by character by accessing each character via its index with the `charAt()` method. String iteration is important for tasks like counting specific characters, checking patterns, or modifying the string's contents, making it a key technique for text processing in Java.
```java
public class CaesarCipher {
    private int key;
    private String phrase;

    public CaesarCipher(int key, String phrase) {
        this.key = key;
        this.phrase = phrase;
    }

    public String encrypt() {
        // your code here

        return null; // return encrypted phrase here
    }
}

CaesarCipher test1 = new CaesarCipher(3, "hello world");
CaesarCipher test2 = new CaesarCipher(10, "abcdefg");
CaesarCipher test3 = new CaesarCipher(20, "i love csa");

System.out.println("test 1: " + test1.encrypt());
System.out.println("test 2: " + test2.encrypt());
System.out.println("test 3: " + test3.encrypt());
```

### Unit 5: Writing Classes
In this unit, we learned to write classes in Java. In Unit 5, we explored the anatomy of a class, understanding how fields, methods, and constructors come together to create objects. I learned how constructors initialize these objects, how accessor and mutator methods manage object properties, and how static variables and methods work at the class level rather than the instance level. This knowledge is essential because it helps you organize your code into reusable, modular components, making it more maintainable, scalable, and efficient—key skills for building complex, real-world applications.
```java
public class BankAccount {
    private String accountHolderName;
    private double balance;

    private static int totalAccounts;

    public BankAccount() {
        this.accountHolderName = "Unknown";
        this.balance = 0.0;

        totalAccounts++;
    }

    public BankAccount(String accountHolderName, double balance) {
        this.accountHolderName = accountHolderName;
        this.balance = balance;

        totalAccounts++;
    }

    public void setAccountHolderName(String accountHolderName) {
        this.accountHolderName = accountHolderName;
    }

    public void deposit(int amount) {
        balance += amount;
    }

    public void withdraw(int amount) {
        balance -= amount;
    } 

    public String getAccountHolderName() {
        return accountHolderName;
    }

    public double getBalance() {
        return balance;
    }

    public int getTotalAccounts() {
        return totalAccounts;
    }

    public static void BankApp() {
        BankAccount Alice = new BankAccount("Alice", 500);
        BankAccount Bob = new BankAccount("Bob", 0);
        BankAccount Charlie = new BankAccount("Charlie", 1000);

        Bob.deposit(1000);
        Charlie.withdraw(250);

        System.out.printf("Account Holder: %s\nBalance: %.1f\n\n", Alice.getAccountHolderName(), Alice.getBalance());
        System.out.printf("Account Holder: %s\nBalance: %.1f\n\n", Bob.getAccountHolderName(), Bob.getBalance());
        System.out.printf("Account Holder: %s\nBalance: %.1f\n\n", Charlie.getAccountHolderName(), Charlie.getBalance());
        
        System.out.println("Total number of accounts created: " + BankAccount.totalAccounts);
    }
}

BankAccount.BankApp();
```

### Unit 6: Arrays
In this unit, we explored the fundamentals of arrays in Java. I learned how to declare, initialize, and access array elements, which helped me understand how to efficiently traverse and manipulate them. Through topics like array creation, one-dimensional traversal, and enhanced for loops, I practiced building algorithms that use arrays to solve problems. By mastering these concepts, I gained the ability to manage collections of data in a structured way, which improved my ability to write effective and scalable Java programs.
```java
int [] numbers = {1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20};

int shift = 2; //y
int space = 4; //x

/* function */
private int [] shiftRight(int [] values, int shift, int space) {
    /* code here */
    
    int t = 0;
    int[] arr = new int[(int)Math.ceil((double)values.length / space)];
    for (int i = 0; i < values.length; i++) {
        if (i % space == 0) {
            arr[t] = values[i];
            t++;
        }
    }
    
    int[] shifted = new int[arr.length];
    for (int i = 0; i < arr.length; i++) {
        shifted[Math.abs((i + shift) % arr.length)] = arr[i];
    }
    
    t = 0;
    for (int i = 0; i < values.length; i++) {
        if (i % space == 0) {
            values[i] = shifted[t];
            t++;
        }
    }
    
    return values;
}

for ( int value : shiftRight(numbers, shift, space)) {
    System.out.println(value);
}
```

### Unit 7: ArrayLists
In this unit, we discovered how they provide a dynamic way to manage collections of objects. I learned how to declare, initialize, and manipulate ArrayLists, gaining skills in adding, removing, and accessing elements. By exploring key methods like `add()`, `remove()`, and `get()`, I understood how ArrayLists can grow and shrink as needed, unlike traditional arrays. This flexibility allowed me to write more efficient code for managing variable-sized data collections. Overall, mastering ArrayLists enhanced my ability to handle complex data structures and improved my programming skills in Java.
```java
import java.util.ArrayList;

public class SortTest
{
    public static void someSortingAlgorithm(ArrayList<Integer> elements) {   
        /* code */
        for (int i = 0; i < elements.size() - 1; i++) {
            int min = i;
            for (int j = i + 1; j < elements.size(); j++) {
                if (elements.get(j) < elements.get(min)) {
                    min = j;
                }
            }
            int t = elements.get(i);
            elements.set(i, elements.get(min));
            elements.set(min, t);
        }
        System.out.println(elements);
    }

    public static void main(String[] args)
    {
        ArrayList<Integer> arr1 = new ArrayList<>();
        arr1.add(85);
        arr1.add(92);
        arr1.add(76);
        arr1.add(88);
        arr1.add(67);
        arr1.add(94);
        arr1.add(73);
        arr1.add(89);
        arr1.add(91);
        arr1.add(82);
        arr1.add(78);
        arr1.add(88);
        arr1.add(95);
        arr1.add(60);
        arr1.add(84);
        arr1.add(77);
        arr1.add(91);
        arr1.add(68);
        arr1.add(97);
        arr1.add(83);

        /* code */
        someSortingAlgorithm(arr1);
    }
}

SortTest.main(null);
```

### Unit 8: 2D Arrays
In this unit, we learned about 2D arrays in Java, including their structure and various use cases. I discovered how to declare and initialize 2D arrays and determine their size, which deepened my understanding of how data can be organized in rows and columns, much like a matrix or a chessboard. I practiced accessing and updating values within a 2D array and explored traversing these arrays using nested iteration statements. This included learning the difference between row-major and column-major order traversal, which is essential for efficiently accessing elements. Additionally, I worked on creating algorithms that utilized 2D array traversals, solidifying my knowledge of this important data structure and its real-world applications, such as in spreadsheets and image processing.
```java
public class Main {
    public static void main(String[] args) {
        int[][] Array1 = {
            {1,2,3},
            {4,5,6}
        };
        for(int i1 = 0; i1 < Array1[0].length; i1++){
            System.out.println("Column " + (i1+1));
            for(int i = 0; i < Array1.length; i++){
                System.out.println(Array1[i][i1]);
            }
        }
    }
}


Main.main(null)
```

### Unit 9: Inheritance
In this unit, we learned about the fundamental concepts of superclasses and subclasses. I discovered that a superclass, or parent class, serves as a template that provides common attributes and behaviors shared by its subclasses, which are the child classes that inherit from the superclass. This relationship allows subclasses to extend or modify the functionality of the superclass while adding their own unique features. I also became familiar with the basic syntax for declaring a subclass using the `extends` keyword, which helps to create a clear hierarchical structure in my code.
```java
public class Shape {
    protected String name;
    private int length;
    private int width;

    public Shape() {
        this.name = "Shape";
        this.length = 10;
        this.width = 5;
    }

    public Shape(String name, int length, int width) {
        this.name = name;
        this.length = length;
        this.width = width;
    }

    public String get_name() {
        return this.name;
    }

    public int get_length() {
        return this.length;
    }

    public int get_width() {
        return this.width;
    }

    public void set_name(String n) {
        this.name = n;
    }

    public void set_length(int a) {
        this.length = a;
    }

    public void set_width(int b) {
        this.width = b;
    }

    public double calc_area() {
        return this.length * this.width;
    }

    public void print_shape() {
        System.out.println("Shape: " + this.name);
    }

    public void print_something() {
        System.out.println("This is a shape");
    }
}

public class Rectangle extends Shape {
    public Rectangle() {
        super();
    }

    public Rectangle(String name, int length, int width) {
        super(name, length, width);
    }

    @Override
    public double calc_area() {
        return (this.get_length() * this.get_width());
    }

    @Override
    public void print_something() {
        System.out.println("This is a rectangle");
    }
}

public class Triangle extends Shape {
    public Triangle() {
        super();
    }

    public Triangle(String name, int length, int width) {
        super(name, length, width);
    }

    @Override
    public double calc_area() {
        return (get_length() * get_width() * 0.5);
    }
}

public class Driver {
    public static void main(String[] args) {
        Shape s1 = new Shape();
        Shape s2 = new Rectangle("rectangle", 4, 10);
        Shape s3 = new Triangle("triangle", 5, 20);

        System.out.println("Area of s1 = " + s1.calc_area());
        System.out.println("Area of s2 = " + s2.calc_area());
        System.out.println("Area of s3 = " + s3.calc_area());

        s1.print_shape();
        s2.print_shape();

        s1.print_something();
        s2.print_something();
    }
}

Driver.main(new String[0]);
```