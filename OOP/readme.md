

# **Object-Oriented Programming (OOP)**  
![oop.gif](oop.gif)

OOP is a programming paradigm that uses "objects" to represent data and methods to manipulate that data.


## **1. Class & Object**  
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


## **2. Access Specifiers**  
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


## **Encapsulation**  
Encapsulation is an OOP principle that combines data (attributes) and methods (functions) that operate on the data into a single unit called a class. It restricts direct access to some of the object's components, which is a means of protecting the integrity of the data.

### **Data Hiding**  
Data hiding is the practice of restricting access to the internal state of an object, allowing only controlled access through public methods (getters and setters). This promotes better maintainability and reduces the risk of unintended interference.

#### **Example Code: Encapsulation and Data Hiding**  
```java
class BankAccount {
    private String accountNumber; // Data hiding: accountNumber is private
    private double balance;        // Data hiding: balance is private

    // Constructor
    public BankAccount(String accountNumber, double initialBalance) {
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }

    // Getter for accountNumber
    public String getAccountNumber() {
        return accountNumber;
    }

    // Getter for balance
    public double getBalance() {
        return balance;
    }

    // Method to deposit money
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount; // Modify balance using a method
            System.out.println("Deposited: " + amount);
        } else {
            System.out.println("Deposit amount must be positive.");
        }
    }

    // Method to withdraw money
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount; // Modify balance using a method
            System.out.println("Withdrew: " + amount);
        } else {
            System.out.println("Invalid withdrawal amount.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        BankAccount account = new BankAccount("12345", 1000.00);
        
        // Accessing account information through getters
        System.out.println("Account Number: " + account.getAccountNumber());
        System.out.println("Initial Balance: " + account.getBalance());

        // Performing operations on the account
        account.deposit(500.00); // Output: Deposited: 500.0
        System.out.println("Updated Balance: " + account.getBalance()); // Output: Updated Balance: 1500.0
        
        account.withdraw(200.00); // Output: Withdrew: 200.0
        System.out.println("Final Balance: " + account.getBalance()); // Output: Final Balance: 1300.0

        // Attempting direct access to private variable (will cause an error)
        // System.out.println(account.balance); // Error: balance has private access in BankAccount
    }
}
```



- **Encapsulation**: Bundles data and methods into a single unit (class).
- **Data Hiding**: Restricts direct access to class variables, promoting data integrity and security.
- **Access Control**: Uses private variables with public methods (getters and setters) to control access and modification.


## **Constructors**

A constructor is a special method in a class that is called when an object of the class is created. It is used to initialize objects. Constructors can be categorized into three types:

### **1. Default Constructor (Non-Parameterized Constructor)**
A default constructor does not take any parameters. If no constructor is defined, Java provides a default constructor automatically, which initializes object attributes to their default values.

#### **Example Code: Default Constructor**
```java
class Dog {
    String name;
    int age;

    // Default constructor
    Dog() {
        name = "Unknown"; // Default value for name
        age = 0;          // Default value for age
    }

    void displayInfo() {
        System.out.println("Dog Name: " + name + ", Age: " + age);
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog1 = new Dog(); // Calls default constructor
        dog1.displayInfo(); // Output: Dog Name: Unknown, Age: 0
    }
}
```

### **2. Parameterized Constructor**
A parameterized constructor allows you to initialize an object with specific values by accepting parameters.

#### **Example Code: Parameterized Constructor**
```java
class Dog {
    String name;
    int age;

    // Parameterized constructor
    Dog(String name, int age) {
        this.name = name; // Using 'this' to distinguish instance variable
        this.age = age;
    }

    void displayInfo() {
        System.out.println("Dog Name: " + name + ", Age: " + age);
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog2 = new Dog("Buddy", 3); // Calls parameterized constructor
        dog2.displayInfo(); // Output: Dog Name: Buddy, Age: 3
    }
}
```

### **3. Copy Constructor**
A copy constructor creates a new object as a copy of an existing object. It typically takes another object of the same class as a parameter.

#### **Example Code: Copy Constructor**
```java
class Dog {
    String name;
    int age;

    // Parameterized constructor
    Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Copy constructor
    Dog(Dog another) {
        this.name = another.name; // Copying values from the existing object
        this.age = another.age;
    }

    void displayInfo() {
        System.out.println("Dog Name: " + name + ", Age: " + age);
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog3 = new Dog("Max", 5); // Original object
        dog3.displayInfo(); // Output: Dog Name: Max, Age: 5

        Dog dog4 = new Dog(dog3); // Calls copy constructor
        dog4.displayInfo(); // Output: Dog Name: Max, Age: 5
    }
}
```


- **Default Constructor (Non-Parameterized)**: Initializes object with default values; no parameters.
- **Parameterized Constructor**: Initializes object with specific values; takes parameters.
- **Copy Constructor**: Initializes a new object as a copy of an existing object; takes another object of the same class as a parameter.


### **Constructor Overloading**  
Constructor overloading occurs when a class has multiple constructors with different parameters. This allows for creating objects in different ways.

#### **Example Code: Constructor Overloading**  
```java
class Rectangle {
    int length;
    int width;

    // Constructor with no parameters
    Rectangle() {
        length = 1;
        width = 1;
    }

    // Constructor with one parameter
    Rectangle(int side) {
        length = side;
        width = side; // Square
    }

    // Constructor with two parameters
    Rectangle(int length, int width) {
        this.length = length; // Using 'this' to distinguish between parameters and instance variables
        this.width = width;
    }

    void displayInfo() {
        System.out.println("Length: " + length + ", Width: " + width);
    }
}

public class Main {
    public static void main(String[] args) {
        Rectangle rect1 = new Rectangle(); // Calls constructor with no parameters
        rect1.displayInfo(); // Output: Length: 1, Width: 1

        Rectangle rect2 = new Rectangle(5); // Calls constructor with one parameter
        rect2.displayInfo(); // Output: Length: 5, Width: 5

        Rectangle rect3 = new Rectangle(4, 6); // Calls constructor with two parameters
        rect3.displayInfo(); // Output: Length: 4, Width: 6
    }
}
```


### **This Pointer**  
The `this` keyword is a reference to the current object in a method or constructor. It is used to distinguish between instance variables and parameters with the same name and can also be used to call other constructors.

#### **Example Code: Using `this` Pointer**  
```java
class Person {
    private String name;
    private int age;

    // Parameterized constructor
    Person(String name, int age) {
        this.name = name; // 'this' distinguishes instance variable from parameter
        this.age = age;
    }

    // Method to display info
    void displayInfo() {
        System.out.println("Name: " + name + ", Age: " + age);
    }

    // Method to demonstrate 'this' in method
    void updateName(String name) {
        this.name = name; // 'this' refers to the instance variable
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person("Alice", 25);
        person.displayInfo(); // Output: Name: Alice, Age: 25

        person.updateName("Bob"); // Update name using method
        person.displayInfo(); // Output: Name: Bob, Age: 25
    }
}
```


- **Constructor Overloading**: Multiple constructors with different parameters.
- **This Pointer**: Refers to the current object, used to differentiate between instance variables and parameters or to invoke other constructors.
