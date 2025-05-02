
# C Programming Basics

### ✅ **Primitive vs Non-Primitive Data Types in C**

| **Category**         | **Type**     | **Description**                              | **Example**                                | **Storage**      |
| -------------------- | ------------ | -------------------------------------------- | ------------------------------------------ | ---------------- |
| 🔹 Primitive         | `int`        | Integer (whole numbers)                      | `int age = 21;`                            | 2 or 4 bytes     |
|                      | `float`      | Single precision decimal                     | `float gpa = 3.75;`                        | 4 bytes          |
|                      | `double`     | Double precision decimal                     | `double pi = 3.1415;`                      | 8 bytes          |
|                      | `char`       | Single character                             | `char grade = 'A';`                        | 1 byte           |
|                      | `short`      | Short integer                                | `short s = 1000;`                          | 2 bytes          |
|                      | `long`       | Long integer                                 | `long big = 1000000L;`                     | 4 or 8 bytes     |
|                      | `bool`       | Boolean (true/false, from `<stdbool.h>`)     | `bool flag = true;`                        | 1 byte           |
| -------------------- | ------------ | -------------------------------------------- | ------------------------------------       | ---------------- |
| 🔸 Non-Primitive     | `array`      | Collection of elements of same type          | `int a[5] = {1, 2, 3, 4, 5};`              | Depends on size  |
|                      | `pointer`    | Stores address of another variable           | `int *p = &a;`                             | 4 or 8 bytes     |
|                      | `struct`     | Group of different data types                | `struct Person {int age; char name[20];};` | Varies           |
|                      | `union`      | Like struct, but shared memory               | `union Data {int i; float f;};`            | Size of largest  |
|                      | `enum`       | Named integer constants                      | `enum Days {MON, TUE};`                    | 4 bytes (int)    |

---




### 1. **Introduction to C**
#### Your First "Hello, World!" Program
```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

---

### 2. **Variables and Data Types**
#### Example: Declaring and Using Variables
```c
#include <stdio.h>

int main() {
    int age = 25;
    float height = 5.9;
    char grade = 'A';

    printf("Age: %d, Height: %.1f, Grade: %c\n", age, height, grade);
    return 0;
}
```

---

### 3. **Control Structures**
#### Example: Using if-else
```c
#include <stdio.h>

int main() {
    int number = 10;

    if (number > 0) {
        printf("The number is positive.\n");
    } else if (number < 0) {
        printf("The number is negative.\n");
    } else {
        printf("The number is zero.\n");
    }
    return 0;
}
```

#### Example: Using a for Loop
```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 5; i++) {
        printf("Count: %d\n", i);
    }
    return 0;
}
```

---

### 4. **Functions**
#### Example: A Simple Function
```c
#include <stdio.h>

void greet() {
    printf("Hello from a function!\n");
}

int main() {
    greet();
    return 0;
}
```


### 5. **Pointers**
#### Example: Pointer Basics
```c
#include <stdio.h>

int main() {
    int number = 10;
    int *ptr = &number;

    printf("Value: %d, Address: %p\n", *ptr, ptr);
    return 0;
}
```
