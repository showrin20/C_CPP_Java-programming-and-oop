# **Java Programming Overview**  
Java is a high-level, object-oriented, platform-independent programming language.


### **1. Introduction to Java**  
"Hello, World!" program demonstrates Java basics.  
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```



### **2. Setup Java Environment**  
Install JDK, set `JAVA_HOME`, and use `javac` and `java` commands.



### **3. Operators and Expressions**  
Arithmetic operations using Java operators.  
```java
int result = 5 + 3; // Output: 8
```



### **4. String Class and Printing**  
Manipulate and display strings.  
```java
String message = "Hello, Java!";
System.out.println(message.toUpperCase());
```



### **5. Conditional Statements**  
Control program flow with `if-else`.  
```java
int number = 10;
if (number > 0) {
    System.out.println("Positive");
} else {
    System.out.println("Negative");
}
```



### **6. Loops**  
Iterate with loops.  
```java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```



### **7. Arrays**  
Work with collections of elements.  
```java
int[] numbers = {1, 2, 3, 4};
System.out.println(numbers[0]); // Output: 1
```



### **8. Methods and Packages**  
Encapsulate code in reusable methods.  
```java
public static int add(int a, int b) {
    return a + b;
}
```



### **9. Exception Handling**  
Handle runtime errors gracefully.  
```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero");
}
```



### **10. Multithreading**  
Run parallel threads.  
```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread running");
    }
}
new MyThread().start();
```



### **11. `java.lang` Package**  
Use fundamental Java classes.  
```java
String str = "123";
int num = Integer.parseInt(str);
System.out.println(num);
```

---

### **12. Annotations and Javadoc**  
Add metadata to code.  
```java
@Override
public String toString() {
    return "Example";
}
```



### **13. Lambda Expressions**  
Simplify functional programming.  
```java
Runnable r = () -> System.out.println("Lambda Expression");
r.run();
```



### **14. Java IO**  
Read and write files.  
```java
import java.io.File;
File file = new File("example.txt");
System.out.println(file.exists());
```



### **15. Collection Framework**  
Work with dynamic data structures.  
```java
import java.util.ArrayList;
ArrayList<String> list = new ArrayList<>();
list.add("Java");
System.out.println(list.get(0));
```



### **16. Network Programming**  
Handle networking tasks.  
```java
import java.net.InetAddress;
InetAddress ip = InetAddress.getLocalHost();
System.out.println(ip);
```


### **17. AWT**  
Create GUI applications.  
```java
import java.awt.Frame;
Frame frame = new Frame("AWT Example");
frame.setSize(300, 300);
frame.setVisible(true);
```



### **18. Swing**  
Enhance GUIs with Swing components.  
```java
import javax.swing.JButton;
import javax.swing.JFrame;
JFrame frame = new JFrame("Swing Example");
JButton button = new JButton("Click Me");
frame.add(button);
frame.setSize(200, 200);
frame.setVisible(true);
```

