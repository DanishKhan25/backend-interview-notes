# Object-Oriented Programming (OOP)

> Core pillar of Java - Classes, Inheritance, Polymorphism, Encapsulation

## Four Pillars of OOP

### 1. Encapsulation

Hiding internal details, exposing only what's necessary.

```java
public class User {
    private String email;      // Private - hidden
    private String password;   // Private - hidden
    
    public String getEmail() {
        return email;          // Controlled access
    }
    
    public void setEmail(String email) {
        if (email.contains("@")) {
            this.email = email;
        }
    }
}
```

### 2. Inheritance

Child class inherits properties from parent class.

```java
public class Animal {
    public void eat() {
        System.out.println("Animal eating");
    }
}

public class Dog extends Animal {
    public void bark() {
        System.out.println("Dog barking");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat();   // Inherited from Animal
        dog.bark();  // Own method
    }
}
```

### 3. Polymorphism

One object, multiple forms. Compile-time (Method Overloading) and Runtime (Method Overriding).

```java
// Method Overloading (Compile-time)
public class Calculator {
    public int add(int a, int b) { return a + b; }
    public double add(double a, double b) { return a + b; }
    public int add(int a, int b, int c) { return a + b + c; }
}

// Method Overriding (Runtime)
public abstract class Shape {
    public abstract void draw();
}

public class Circle extends Shape {
    @Override
    public void draw() {
        System.out.println("Drawing Circle");
    }
}
```

### 4. Abstraction

Hiding complexity, showing only essential features.

```java
public abstract class Vehicle {
    abstract void start();
    abstract void stop();
    
    public void honk() {
        System.out.println("Honk!");
    }
}

public class Car extends Vehicle {
    @Override
    void start() { System.out.println("Car starting"); }
    
    @Override
    void stop() { System.out.println("Car stopping"); }
}
```

## Classes and Objects

```java
public class Person {
    // Attributes
    private String name;
    private int age;
    
    // Constructor
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    // Getter
    public String getName() { return name; }
    
    // Setter
    public void setAge(int age) { this.age = age; }
}

// Usage
Person person = new Person("Danish", 30);
System.out.println(person.getName());
```

## Static vs Instance

```java
public class Counter {
    public static int totalCount = 0;   // Shared across all instances
    public int instanceCount = 0;        // Each instance has its own
    
    public Counter() {
        totalCount++;       // Increments for all
        instanceCount++;    // Increments only for this instance
    }
}
```

## Common Interview Questions

- **What's the difference between abstract class and interface?**
- **Can you override static methods?** No
- **What is the super keyword used for?** Access parent class methods/constructors
