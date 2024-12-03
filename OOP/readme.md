

# **Object-Oriented Programming (OOP)**  
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


