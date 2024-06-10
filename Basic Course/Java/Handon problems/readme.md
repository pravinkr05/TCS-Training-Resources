JDK vs JRE vs JVM

hello.java ----> hello.class(javac hello.java) ----> output (java hello.class)

class A {}
public class B extends A{}

Java class does not supports multiple inheritence but java interface does. reason - dimond shape - because when A inherits from B and C class 
and B,C inherits from D. suppose B and C overrides a fun() methods then A will get confused which fun should use.

interface do not defines method so there is no case of ambiguity or confusion.


Four piller - inheritence, encapsulation, polymorphism, abstraction
abstraction vs interface
interface = 100%abstraction , can't create object , support multiple inheritence

Encapsulation - Encapsulation is a principle of wrapping the data (variables) and the code acting on the data (methods) together as a single unit. In Java, this is achieved by making the variables of a class private and providing public getter and setter methods to modify and view the variable values. 

public class Person {
    private String name;
    private int age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}


Inheritance - Inheritance is a mechanism where one class acquires the properties and behaviors of a parent class. The class that inherits is called the subclass (or derived class), and the class being inherited from is called the superclass (or base class).

extends: Used to inherit from a class.
implements: Used to implement an interface.

class Animal {
    void eat() {
        System.out.println("Animal eats");
    }
}

class Cat extends Animal {
    void meow() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Cat cat = new Cat();
        cat.eat();
        cat.meow();
    }
}

Polymorphism - An entity can exist in many forms. Polymorphism is achieved through method overriding (runtime polymorphism) and method overloading (compile-time polymorphism).

// Compile-time polymorphism
class Math {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}

// Runtime polymorphism
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Math math = new Math();
        System.out.println(math.add(2, 3)); // 5
        System.out.println(math.add(2.0, 3.0)); // 5.0

        Animal animal = new Dog();
        animal.sound(); // Dog barks
    }
}


Abstraction - It is used to hide the implementation details and only show the functionalities. while encapsulation hides the data by making its private to protect from outside access.
    Used to declare common characteristics of subclasses. Cannot be instantiated directly and may contain abstract methods (without implementation) and concrete methods (with implementation).

abstract class Shape{
    abstact void draw();
    
}
class Circle extends Shape{
    void draw(){
        //circle is drawing...
    }
    
}


//interface- only have abstract methods (no implementation), 100% abstraction, multiple inheritence, members by default public, interface can extends interface.
interface drawable{
    void draw();
}
class circle implements drawable{
    void draw(){
        //circlr is drawing...
    }
}



Design a class hierarchy with a base class Animal and derived classes Dog and Cat. Demonstrate method overriding by implementing a sound() method in each class.

class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.sound(); // Dog barks

        Animal cat = new Cat();
        cat.sound(); // Cat meows
    }
}


Implement an abstract class Shape with an abstract method area(). Create derived classes Circle and Rectangle that implement the area() method.

abstract class Shape {
    abstract double area();
}

class Circle extends Shape {
    private double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    @Override
    double area() {
        return Math.PI * radius * radius;
    }
}

class Rectangle extends Shape {
    private double length;
    private double width;

    Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    @Override
    double area() {
        return length * width;
    }
}

public class Main {
    public static void main(String[] args) {
        Shape circle = new Circle(5);
        System.out.println("Circle area: " + circle.area()); // Circle area: 78.53981633974483

        Shape rectangle = new Rectangle(4, 5);
        System.out.println("Rectangle area: " + rectangle.area()); // Rectangle area: 20.0
    }
}






