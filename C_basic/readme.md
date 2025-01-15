
# C Programming Basics


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
