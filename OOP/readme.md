

# **Object-Oriented Programming (OOP)**  
OOP is a programming paradigm that uses "objects" to represent data and methods to manipulate that data.


### **1. Class & Object**  
A **class** is a blueprint for creating objects, and an **object** is an instance of a class.

#### **Example Code: Class and Object**  
```java
// Define a class named Dog
class Dog {
    String name; // attribute

    // Constructor
    Dog(String name) {
        this.name = name;
    }

    // Method to display dog's name
    void bark() {
        System.out.println(name + " says Woof!");
    }
}

// Create an object of the Dog class
public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog("Buddy"); // Object instantiation
        myDog.bark(); // Output: Buddy says Woof!
    }
}
```


### **2. Access Specifiers**  
Access specifiers control the visibility of classes, methods, and variables. The main access specifiers in Java are `public`, `protected`, `private`, and package-private (default).

- **Public**: Accessible from anywhere in the program.
- **Protected**: Accessible within the same package and subclasses.
- **Private**: Accessible only within the class it is declared.
- **Package-private**: Accessible only within classes in the same package (default, no specifier).

#### **Example Code: Access Specifiers with Getters and Setters**  
```java
class Person {
    private String name; // Private variable
    private int age;     // Private variable
    private String ssn;  // Private variable

    // Constructor
    Person(String name, int age, String ssn) {
        this.name = name;
        this.age = age;
        this.ssn = ssn;
    }

    // Getter for name
    public String getName() {
        return name;
    }

    // Setter for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter for age
    public int getAge() {
        return age;
    }

    // Setter for age
    public void setAge(int age) {
        this.age = age;
    }

    // Public method to display information
    public void displayInfo() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        // Accessing private variable within the class
        System.out.println("SSN: " + ssn);
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person("Alice", 30, "123-45-6789");
        person.displayInfo(); // Accessible

        // Accessing public methods
        System.out.println("Public Name: " + person.getName()); // Using getter
        person.setName("Bob"); // Using setter
        System.out.println("Updated Name: " + person.getName()); // Output: Bob

        // System.out.println("Private SSN: " + person.ssn); // Not accessible, will cause an error
    }
}
```

- **Getters**: Methods that allow access to private variables.
- **Setters**: Methods that allow modification of private variables.
- **Encapsulation**: A key principle in OOP that restricts direct access to some of an object’s components, promoting data protection.

