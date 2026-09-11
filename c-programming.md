# 🖥️ C Programming: Zero to Hero Guide

> Comprehensive notes on C fundamentals, memory management, pointers, and systems programming.


---

### 📘 [Entry #1/5] User Input in C: Using `scanf()` and Addressing Memory
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 03:42 AM

#### 💡 Overview
Reading integers, floats, and characters from user input with the address-of operator `&`.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int num1, num2;

    printf("Enter two integers separated by space: ");
    // &num1 gives the memory address of num1 so scanf can write the value into it
    scanf("%d %d", &num1, &num2);

    int sum = num1 + num2;
    printf("Sum of %d and %d is: %d\n", num1, num2, sum);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `scanf()` requires the memory address of the variable (`&variable`), not just the variable name.
- The `&` operator is called the 'Address-Of' operator.
- Always check input return values to avoid reading undefined uninitialized memory.

---

### 📘 [Entry #2/5] Dynamic Memory Allocation in C: `malloc()`, `calloc()`, and `free()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 03:42 AM

#### 💡 Overview
Allocating heap memory dynamically at runtime and preventing memory leaks.

#### 💻 Code & Implementation
```c
#include <stdio.h>
#include <stdlib.h> // Required for malloc, calloc, free

int main() {
    int n = 5;
    // malloc allocates n * sizeof(int) bytes on the Heap
    int* arr = (int*)malloc(n * sizeof(int));

    if (arr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Initialize array
    for (int i = 0; i < n; i++) {
        arr[i] = (i + 1) * 10;
    }

    printf("Dynamically allocated array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // CRITICAL: Always free allocated heap memory when finished
    free(arr);
    arr = NULL; // Prevent dangling pointer

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `malloc(size)` allocates uninitialized memory block on the Heap.
- `calloc(count, size)` allocates and zeroes out all allocated bytes.
- `free(ptr)` releases memory back to the OS. Failing to call `free` causes memory leaks.

---

### 📘 [Entry #1/31] User Input in C: Using `scanf()` and Addressing Memory
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 7, 2026, 10:14 PM

#### 💡 Overview
Reading integers, floats, and characters from user input with the address-of operator `&`.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int num1, num2;

    printf("Enter two integers separated by space: ");
    // &num1 gives the memory address of num1 so scanf can write the value into it
    scanf("%d %d", &num1, &num2);

    int sum = num1 + num2;
    printf("Sum of %d and %d is: %d\n", num1, num2, sum);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `scanf()` requires the memory address of the variable (`&variable`), not just the variable name.
- The `&` operator is called the 'Address-Of' operator.
- Always check input return values to avoid reading undefined uninitialized memory.

---

### 📘 [Entry #8/31] Introduction to C: Structure of a C Program & `main()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 7, 2026, 10:15 PM

#### 💡 Overview
Understanding C compilation, header files, the `main()` function entry point, and standard I/O.

#### 💻 Code & Implementation
```c
#include <stdio.h> // Preprocessor directive to include Standard Input/Output library

// Execution of every C program begins in the main() function
int main() {
    // printf prints formatted text to the terminal
    // \n adds a newline character
    printf("Hello, World! Welcome to C Programming.\n");

    // return 0 signals to the Operating System that the program executed successfully
    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `#include <stdio.h>` is a preprocessor command that tells the compiler to include the standard input/output header file.
- `int main()` is the entry point where the program starts execution. `int` means it returns an integer status code.
- `printf()` sends text to the screen; the semicolon `;` ends every statement in C.

---

### 📘 [Entry #9/31] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 7, 2026, 10:15 PM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #14/31] Dynamic Memory Allocation in C: `malloc()`, `calloc()`, and `free()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 7, 2026, 10:15 PM

#### 💡 Overview
Allocating heap memory dynamically at runtime and preventing memory leaks.

#### 💻 Code & Implementation
```c
#include <stdio.h>
#include <stdlib.h> // Required for malloc, calloc, free

int main() {
    int n = 5;
    // malloc allocates n * sizeof(int) bytes on the Heap
    int* arr = (int*)malloc(n * sizeof(int));

    if (arr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Initialize array
    for (int i = 0; i < n; i++) {
        arr[i] = (i + 1) * 10;
    }

    printf("Dynamically allocated array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // CRITICAL: Always free allocated heap memory when finished
    free(arr);
    arr = NULL; // Prevent dangling pointer

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `malloc(size)` allocates uninitialized memory block on the Heap.
- `calloc(count, size)` allocates and zeroes out all allocated bytes.
- `free(ptr)` releases memory back to the OS. Failing to call `free` causes memory leaks.

---

### 📘 [Entry #15/31] C Data Types, Variables & Format Specifiers
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 7, 2026, 10:15 PM

#### 💡 Overview
Basic primitive types: `int`, `float`, `double`, `char`, memory sizes, and format specifiers (`%d`, `%f`, `%c`, `%s`).

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int age = 20;              // Integer: 4 bytes (e.g. 10, -50, 1000)
    float gpa = 8.75f;         // Floating-point: 4 bytes (single precision)
    double pi = 3.1415926535;  // Double precision float: 8 bytes
    char grade = 'A';          // Single character: 1 byte (enclosed in single quotes)

    printf("Age: %d\n", age);          // %d for integers
    printf("GPA: %.2f\n", gpa);        // %.2f prints float with 2 decimal places
    printf("Pi: %.6lf\n", pi);         // %lf for double
    printf("Grade: %c\n", grade);      // %c for character

    // sizeof operator returns size in bytes
    printf("Size of int: %lu bytes\n", sizeof(int));
    printf("Size of double: %lu bytes\n", sizeof(double));

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- In C, you must declare variable types before using them (statically typed language).
- Format specifiers tell `printf` and `scanf` how to interpret binary data in memory.
- `sizeof()` is a compile-time operator that returns the byte size of data types.

---

### 📘 [Entry #24/31] User Input in C: Using `scanf()` and Addressing Memory
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 7, 2026, 10:16 PM

#### 💡 Overview
Reading integers, floats, and characters from user input with the address-of operator `&`.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int num1, num2;

    printf("Enter two integers separated by space: ");
    // &num1 gives the memory address of num1 so scanf can write the value into it
    scanf("%d %d", &num1, &num2);

    int sum = num1 + num2;
    printf("Sum of %d and %d is: %d\n", num1, num2, sum);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `scanf()` requires the memory address of the variable (`&variable`), not just the variable name.
- The `&` operator is called the 'Address-Of' operator.
- Always check input return values to avoid reading undefined uninitialized memory.

---

### 📘 [Entry #29/31] Introduction to C: Structure of a C Program & `main()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 7, 2026, 10:16 PM

#### 💡 Overview
Understanding C compilation, header files, the `main()` function entry point, and standard I/O.

#### 💻 Code & Implementation
```c
#include <stdio.h> // Preprocessor directive to include Standard Input/Output library

// Execution of every C program begins in the main() function
int main() {
    // printf prints formatted text to the terminal
    // \n adds a newline character
    printf("Hello, World! Welcome to C Programming.\n");

    // return 0 signals to the Operating System that the program executed successfully
    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `#include <stdio.h>` is a preprocessor command that tells the compiler to include the standard input/output header file.
- `int main()` is the entry point where the program starts execution. `int` means it returns an integer status code.
- `printf()` sends text to the screen; the semicolon `;` ends every statement in C.

---

### 📘 [Entry #7/35] Introduction to C: Structure of a C Program & `main()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 10:26 AM

#### 💡 Overview
Understanding C compilation, header files, the `main()` function entry point, and standard I/O.

#### 💻 Code & Implementation
```c
#include <stdio.h> // Preprocessor directive to include Standard Input/Output library

// Execution of every C program begins in the main() function
int main() {
    // printf prints formatted text to the terminal
    // \n adds a newline character
    printf("Hello, World! Welcome to C Programming.\n");

    // return 0 signals to the Operating System that the program executed successfully
    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `#include <stdio.h>` is a preprocessor command that tells the compiler to include the standard input/output header file.
- `int main()` is the entry point where the program starts execution. `int` means it returns an integer status code.
- `printf()` sends text to the screen; the semicolon `;` ends every statement in C.

---

### 📘 [Entry #9/35] Dynamic Memory Allocation in C: `malloc()`, `calloc()`, and `free()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 10:26 AM

#### 💡 Overview
Allocating heap memory dynamically at runtime and preventing memory leaks.

#### 💻 Code & Implementation
```c
#include <stdio.h>
#include <stdlib.h> // Required for malloc, calloc, free

int main() {
    int n = 5;
    // malloc allocates n * sizeof(int) bytes on the Heap
    int* arr = (int*)malloc(n * sizeof(int));

    if (arr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Initialize array
    for (int i = 0; i < n; i++) {
        arr[i] = (i + 1) * 10;
    }

    printf("Dynamically allocated array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // CRITICAL: Always free allocated heap memory when finished
    free(arr);
    arr = NULL; // Prevent dangling pointer

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `malloc(size)` allocates uninitialized memory block on the Heap.
- `calloc(count, size)` allocates and zeroes out all allocated bytes.
- `free(ptr)` releases memory back to the OS. Failing to call `free` causes memory leaks.

---

### 📘 [Entry #11/35] C Data Types, Variables & Format Specifiers
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 10:27 AM

#### 💡 Overview
Basic primitive types: `int`, `float`, `double`, `char`, memory sizes, and format specifiers (`%d`, `%f`, `%c`, `%s`).

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int age = 20;              // Integer: 4 bytes (e.g. 10, -50, 1000)
    float gpa = 8.75f;         // Floating-point: 4 bytes (single precision)
    double pi = 3.1415926535;  // Double precision float: 8 bytes
    char grade = 'A';          // Single character: 1 byte (enclosed in single quotes)

    printf("Age: %d\n", age);          // %d for integers
    printf("GPA: %.2f\n", gpa);        // %.2f prints float with 2 decimal places
    printf("Pi: %.6lf\n", pi);         // %lf for double
    printf("Grade: %c\n", grade);      // %c for character

    // sizeof operator returns size in bytes
    printf("Size of int: %lu bytes\n", sizeof(int));
    printf("Size of double: %lu bytes\n", sizeof(double));

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- In C, you must declare variable types before using them (statically typed language).
- Format specifiers tell `printf` and `scanf` how to interpret binary data in memory.
- `sizeof()` is a compile-time operator that returns the byte size of data types.

---

### 📘 [Entry #15/35] User Input in C: Using `scanf()` and Addressing Memory
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 10:27 AM

#### 💡 Overview
Reading integers, floats, and characters from user input with the address-of operator `&`.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int num1, num2;

    printf("Enter two integers separated by space: ");
    // &num1 gives the memory address of num1 so scanf can write the value into it
    scanf("%d %d", &num1, &num2);

    int sum = num1 + num2;
    printf("Sum of %d and %d is: %d\n", num1, num2, sum);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `scanf()` requires the memory address of the variable (`&variable`), not just the variable name.
- The `&` operator is called the 'Address-Of' operator.
- Always check input return values to avoid reading undefined uninitialized memory.

---

### 📘 [Entry #17/35] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 10:27 AM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #22/35] C Data Types, Variables & Format Specifiers
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 10:27 AM

#### 💡 Overview
Basic primitive types: `int`, `float`, `double`, `char`, memory sizes, and format specifiers (`%d`, `%f`, `%c`, `%s`).

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int age = 20;              // Integer: 4 bytes (e.g. 10, -50, 1000)
    float gpa = 8.75f;         // Floating-point: 4 bytes (single precision)
    double pi = 3.1415926535;  // Double precision float: 8 bytes
    char grade = 'A';          // Single character: 1 byte (enclosed in single quotes)

    printf("Age: %d\n", age);          // %d for integers
    printf("GPA: %.2f\n", gpa);        // %.2f prints float with 2 decimal places
    printf("Pi: %.6lf\n", pi);         // %lf for double
    printf("Grade: %c\n", grade);      // %c for character

    // sizeof operator returns size in bytes
    printf("Size of int: %lu bytes\n", sizeof(int));
    printf("Size of double: %lu bytes\n", sizeof(double));

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- In C, you must declare variable types before using them (statically typed language).
- Format specifiers tell `printf` and `scanf` how to interpret binary data in memory.
- `sizeof()` is a compile-time operator that returns the byte size of data types.

---

### 📘 [Entry #26/35] Introduction to C: Structure of a C Program & `main()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 10:28 AM

#### 💡 Overview
Understanding C compilation, header files, the `main()` function entry point, and standard I/O.

#### 💻 Code & Implementation
```c
#include <stdio.h> // Preprocessor directive to include Standard Input/Output library

// Execution of every C program begins in the main() function
int main() {
    // printf prints formatted text to the terminal
    // \n adds a newline character
    printf("Hello, World! Welcome to C Programming.\n");

    // return 0 signals to the Operating System that the program executed successfully
    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `#include <stdio.h>` is a preprocessor command that tells the compiler to include the standard input/output header file.
- `int main()` is the entry point where the program starts execution. `int` means it returns an integer status code.
- `printf()` sends text to the screen; the semicolon `;` ends every statement in C.

---

### 📘 [Entry #27/35] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 10:28 AM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #31/35] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 10:28 AM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #33/35] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 10:28 AM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #35/35] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 10:28 AM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #6/31] Dynamic Memory Allocation in C: `malloc()`, `calloc()`, and `free()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 09:12 PM

#### 💡 Overview
Allocating heap memory dynamically at runtime and preventing memory leaks.

#### 💻 Code & Implementation
```c
#include <stdio.h>
#include <stdlib.h> // Required for malloc, calloc, free

int main() {
    int n = 5;
    // malloc allocates n * sizeof(int) bytes on the Heap
    int* arr = (int*)malloc(n * sizeof(int));

    if (arr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Initialize array
    for (int i = 0; i < n; i++) {
        arr[i] = (i + 1) * 10;
    }

    printf("Dynamically allocated array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // CRITICAL: Always free allocated heap memory when finished
    free(arr);
    arr = NULL; // Prevent dangling pointer

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `malloc(size)` allocates uninitialized memory block on the Heap.
- `calloc(count, size)` allocates and zeroes out all allocated bytes.
- `free(ptr)` releases memory back to the OS. Failing to call `free` causes memory leaks.

---

### 📘 [Entry #8/31] User Input in C: Using `scanf()` and Addressing Memory
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 09:12 PM

#### 💡 Overview
Reading integers, floats, and characters from user input with the address-of operator `&`.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int num1, num2;

    printf("Enter two integers separated by space: ");
    // &num1 gives the memory address of num1 so scanf can write the value into it
    scanf("%d %d", &num1, &num2);

    int sum = num1 + num2;
    printf("Sum of %d and %d is: %d\n", num1, num2, sum);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `scanf()` requires the memory address of the variable (`&variable`), not just the variable name.
- The `&` operator is called the 'Address-Of' operator.
- Always check input return values to avoid reading undefined uninitialized memory.

---

### 📘 [Entry #14/31] Introduction to C: Structure of a C Program & `main()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 09:13 PM

#### 💡 Overview
Understanding C compilation, header files, the `main()` function entry point, and standard I/O.

#### 💻 Code & Implementation
```c
#include <stdio.h> // Preprocessor directive to include Standard Input/Output library

// Execution of every C program begins in the main() function
int main() {
    // printf prints formatted text to the terminal
    // \n adds a newline character
    printf("Hello, World! Welcome to C Programming.\n");

    // return 0 signals to the Operating System that the program executed successfully
    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `#include <stdio.h>` is a preprocessor command that tells the compiler to include the standard input/output header file.
- `int main()` is the entry point where the program starts execution. `int` means it returns an integer status code.
- `printf()` sends text to the screen; the semicolon `;` ends every statement in C.

---

### 📘 [Entry #16/31] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 09:13 PM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #17/31] C Data Types, Variables & Format Specifiers
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 09:13 PM

#### 💡 Overview
Basic primitive types: `int`, `float`, `double`, `char`, memory sizes, and format specifiers (`%d`, `%f`, `%c`, `%s`).

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int age = 20;              // Integer: 4 bytes (e.g. 10, -50, 1000)
    float gpa = 8.75f;         // Floating-point: 4 bytes (single precision)
    double pi = 3.1415926535;  // Double precision float: 8 bytes
    char grade = 'A';          // Single character: 1 byte (enclosed in single quotes)

    printf("Age: %d\n", age);          // %d for integers
    printf("GPA: %.2f\n", gpa);        // %.2f prints float with 2 decimal places
    printf("Pi: %.6lf\n", pi);         // %lf for double
    printf("Grade: %c\n", grade);      // %c for character

    // sizeof operator returns size in bytes
    printf("Size of int: %lu bytes\n", sizeof(int));
    printf("Size of double: %lu bytes\n", sizeof(double));

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- In C, you must declare variable types before using them (statically typed language).
- Format specifiers tell `printf` and `scanf` how to interpret binary data in memory.
- `sizeof()` is a compile-time operator that returns the byte size of data types.

---

### 📘 [Entry #20/31] C Data Types, Variables & Format Specifiers
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 09:13 PM

#### 💡 Overview
Basic primitive types: `int`, `float`, `double`, `char`, memory sizes, and format specifiers (`%d`, `%f`, `%c`, `%s`).

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int age = 20;              // Integer: 4 bytes (e.g. 10, -50, 1000)
    float gpa = 8.75f;         // Floating-point: 4 bytes (single precision)
    double pi = 3.1415926535;  // Double precision float: 8 bytes
    char grade = 'A';          // Single character: 1 byte (enclosed in single quotes)

    printf("Age: %d\n", age);          // %d for integers
    printf("GPA: %.2f\n", gpa);        // %.2f prints float with 2 decimal places
    printf("Pi: %.6lf\n", pi);         // %lf for double
    printf("Grade: %c\n", grade);      // %c for character

    // sizeof operator returns size in bytes
    printf("Size of int: %lu bytes\n", sizeof(int));
    printf("Size of double: %lu bytes\n", sizeof(double));

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- In C, you must declare variable types before using them (statically typed language).
- Format specifiers tell `printf` and `scanf` how to interpret binary data in memory.
- `sizeof()` is a compile-time operator that returns the byte size of data types.

---

### 📘 [Entry #26/31] C Data Types, Variables & Format Specifiers
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 09:14 PM

#### 💡 Overview
Basic primitive types: `int`, `float`, `double`, `char`, memory sizes, and format specifiers (`%d`, `%f`, `%c`, `%s`).

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int age = 20;              // Integer: 4 bytes (e.g. 10, -50, 1000)
    float gpa = 8.75f;         // Floating-point: 4 bytes (single precision)
    double pi = 3.1415926535;  // Double precision float: 8 bytes
    char grade = 'A';          // Single character: 1 byte (enclosed in single quotes)

    printf("Age: %d\n", age);          // %d for integers
    printf("GPA: %.2f\n", gpa);        // %.2f prints float with 2 decimal places
    printf("Pi: %.6lf\n", pi);         // %lf for double
    printf("Grade: %c\n", grade);      // %c for character

    // sizeof operator returns size in bytes
    printf("Size of int: %lu bytes\n", sizeof(int));
    printf("Size of double: %lu bytes\n", sizeof(double));

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- In C, you must declare variable types before using them (statically typed language).
- Format specifiers tell `printf` and `scanf` how to interpret binary data in memory.
- `sizeof()` is a compile-time operator that returns the byte size of data types.

---

### 📘 [Entry #28/31] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 09:14 PM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #30/31] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 8, 2026, 09:14 PM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #1/31] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 9, 2026, 10:36 AM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #4/31] Introduction to C: Structure of a C Program & `main()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 9, 2026, 10:37 AM

#### 💡 Overview
Understanding C compilation, header files, the `main()` function entry point, and standard I/O.

#### 💻 Code & Implementation
```c
#include <stdio.h> // Preprocessor directive to include Standard Input/Output library

// Execution of every C program begins in the main() function
int main() {
    // printf prints formatted text to the terminal
    // \n adds a newline character
    printf("Hello, World! Welcome to C Programming.\n");

    // return 0 signals to the Operating System that the program executed successfully
    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `#include <stdio.h>` is a preprocessor command that tells the compiler to include the standard input/output header file.
- `int main()` is the entry point where the program starts execution. `int` means it returns an integer status code.
- `printf()` sends text to the screen; the semicolon `;` ends every statement in C.

---

### 📘 [Entry #6/31] C Data Types, Variables & Format Specifiers
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 9, 2026, 10:37 AM

#### 💡 Overview
Basic primitive types: `int`, `float`, `double`, `char`, memory sizes, and format specifiers (`%d`, `%f`, `%c`, `%s`).

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int age = 20;              // Integer: 4 bytes (e.g. 10, -50, 1000)
    float gpa = 8.75f;         // Floating-point: 4 bytes (single precision)
    double pi = 3.1415926535;  // Double precision float: 8 bytes
    char grade = 'A';          // Single character: 1 byte (enclosed in single quotes)

    printf("Age: %d\n", age);          // %d for integers
    printf("GPA: %.2f\n", gpa);        // %.2f prints float with 2 decimal places
    printf("Pi: %.6lf\n", pi);         // %lf for double
    printf("Grade: %c\n", grade);      // %c for character

    // sizeof operator returns size in bytes
    printf("Size of int: %lu bytes\n", sizeof(int));
    printf("Size of double: %lu bytes\n", sizeof(double));

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- In C, you must declare variable types before using them (statically typed language).
- Format specifiers tell `printf` and `scanf` how to interpret binary data in memory.
- `sizeof()` is a compile-time operator that returns the byte size of data types.

---

### 📘 [Entry #10/31] User Input in C: Using `scanf()` and Addressing Memory
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 9, 2026, 10:37 AM

#### 💡 Overview
Reading integers, floats, and characters from user input with the address-of operator `&`.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int num1, num2;

    printf("Enter two integers separated by space: ");
    // &num1 gives the memory address of num1 so scanf can write the value into it
    scanf("%d %d", &num1, &num2);

    int sum = num1 + num2;
    printf("Sum of %d and %d is: %d\n", num1, num2, sum);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `scanf()` requires the memory address of the variable (`&variable`), not just the variable name.
- The `&` operator is called the 'Address-Of' operator.
- Always check input return values to avoid reading undefined uninitialized memory.

---

### 📘 [Entry #11/31] Dynamic Memory Allocation in C: `malloc()`, `calloc()`, and `free()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 9, 2026, 10:37 AM

#### 💡 Overview
Allocating heap memory dynamically at runtime and preventing memory leaks.

#### 💻 Code & Implementation
```c
#include <stdio.h>
#include <stdlib.h> // Required for malloc, calloc, free

int main() {
    int n = 5;
    // malloc allocates n * sizeof(int) bytes on the Heap
    int* arr = (int*)malloc(n * sizeof(int));

    if (arr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Initialize array
    for (int i = 0; i < n; i++) {
        arr[i] = (i + 1) * 10;
    }

    printf("Dynamically allocated array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // CRITICAL: Always free allocated heap memory when finished
    free(arr);
    arr = NULL; // Prevent dangling pointer

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `malloc(size)` allocates uninitialized memory block on the Heap.
- `calloc(count, size)` allocates and zeroes out all allocated bytes.
- `free(ptr)` releases memory back to the OS. Failing to call `free` causes memory leaks.

---

### 📘 [Entry #21/31] C Data Types, Variables & Format Specifiers
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 9, 2026, 10:38 AM

#### 💡 Overview
Basic primitive types: `int`, `float`, `double`, `char`, memory sizes, and format specifiers (`%d`, `%f`, `%c`, `%s`).

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int age = 20;              // Integer: 4 bytes (e.g. 10, -50, 1000)
    float gpa = 8.75f;         // Floating-point: 4 bytes (single precision)
    double pi = 3.1415926535;  // Double precision float: 8 bytes
    char grade = 'A';          // Single character: 1 byte (enclosed in single quotes)

    printf("Age: %d\n", age);          // %d for integers
    printf("GPA: %.2f\n", gpa);        // %.2f prints float with 2 decimal places
    printf("Pi: %.6lf\n", pi);         // %lf for double
    printf("Grade: %c\n", grade);      // %c for character

    // sizeof operator returns size in bytes
    printf("Size of int: %lu bytes\n", sizeof(int));
    printf("Size of double: %lu bytes\n", sizeof(double));

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- In C, you must declare variable types before using them (statically typed language).
- Format specifiers tell `printf` and `scanf` how to interpret binary data in memory.
- `sizeof()` is a compile-time operator that returns the byte size of data types.

---

### 📘 [Entry #22/31] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 9, 2026, 10:38 AM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #25/31] Dynamic Memory Allocation in C: `malloc()`, `calloc()`, and `free()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 9, 2026, 10:38 AM

#### 💡 Overview
Allocating heap memory dynamically at runtime and preventing memory leaks.

#### 💻 Code & Implementation
```c
#include <stdio.h>
#include <stdlib.h> // Required for malloc, calloc, free

int main() {
    int n = 5;
    // malloc allocates n * sizeof(int) bytes on the Heap
    int* arr = (int*)malloc(n * sizeof(int));

    if (arr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Initialize array
    for (int i = 0; i < n; i++) {
        arr[i] = (i + 1) * 10;
    }

    printf("Dynamically allocated array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // CRITICAL: Always free allocated heap memory when finished
    free(arr);
    arr = NULL; // Prevent dangling pointer

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `malloc(size)` allocates uninitialized memory block on the Heap.
- `calloc(count, size)` allocates and zeroes out all allocated bytes.
- `free(ptr)` releases memory back to the OS. Failing to call `free` causes memory leaks.

---

### 📘 [Entry #31/31] Introduction to C: Structure of a C Program & `main()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 9, 2026, 10:38 AM

#### 💡 Overview
Understanding C compilation, header files, the `main()` function entry point, and standard I/O.

#### 💻 Code & Implementation
```c
#include <stdio.h> // Preprocessor directive to include Standard Input/Output library

// Execution of every C program begins in the main() function
int main() {
    // printf prints formatted text to the terminal
    // \n adds a newline character
    printf("Hello, World! Welcome to C Programming.\n");

    // return 0 signals to the Operating System that the program executed successfully
    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `#include <stdio.h>` is a preprocessor command that tells the compiler to include the standard input/output header file.
- `int main()` is the entry point where the program starts execution. `int` means it returns an integer status code.
- `printf()` sends text to the screen; the semicolon `;` ends every statement in C.

---

### 📘 [Entry #6/30] Dynamic Memory Allocation in C: `malloc()`, `calloc()`, and `free()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 10, 2026, 07:33 PM

#### 💡 Overview
Allocating heap memory dynamically at runtime and preventing memory leaks.

#### 💻 Code & Implementation
```c
#include <stdio.h>
#include <stdlib.h> // Required for malloc, calloc, free

int main() {
    int n = 5;
    // malloc allocates n * sizeof(int) bytes on the Heap
    int* arr = (int*)malloc(n * sizeof(int));

    if (arr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Initialize array
    for (int i = 0; i < n; i++) {
        arr[i] = (i + 1) * 10;
    }

    printf("Dynamically allocated array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // CRITICAL: Always free allocated heap memory when finished
    free(arr);
    arr = NULL; // Prevent dangling pointer

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `malloc(size)` allocates uninitialized memory block on the Heap.
- `calloc(count, size)` allocates and zeroes out all allocated bytes.
- `free(ptr)` releases memory back to the OS. Failing to call `free` causes memory leaks.

---

### 📘 [Entry #7/30] C Data Types, Variables & Format Specifiers
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 10, 2026, 07:33 PM

#### 💡 Overview
Basic primitive types: `int`, `float`, `double`, `char`, memory sizes, and format specifiers (`%d`, `%f`, `%c`, `%s`).

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int age = 20;              // Integer: 4 bytes (e.g. 10, -50, 1000)
    float gpa = 8.75f;         // Floating-point: 4 bytes (single precision)
    double pi = 3.1415926535;  // Double precision float: 8 bytes
    char grade = 'A';          // Single character: 1 byte (enclosed in single quotes)

    printf("Age: %d\n", age);          // %d for integers
    printf("GPA: %.2f\n", gpa);        // %.2f prints float with 2 decimal places
    printf("Pi: %.6lf\n", pi);         // %lf for double
    printf("Grade: %c\n", grade);      // %c for character

    // sizeof operator returns size in bytes
    printf("Size of int: %lu bytes\n", sizeof(int));
    printf("Size of double: %lu bytes\n", sizeof(double));

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- In C, you must declare variable types before using them (statically typed language).
- Format specifiers tell `printf` and `scanf` how to interpret binary data in memory.
- `sizeof()` is a compile-time operator that returns the byte size of data types.

---

### 📘 [Entry #9/30] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 10, 2026, 07:33 PM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #18/30] User Input in C: Using `scanf()` and Addressing Memory
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 10, 2026, 07:34 PM

#### 💡 Overview
Reading integers, floats, and characters from user input with the address-of operator `&`.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int num1, num2;

    printf("Enter two integers separated by space: ");
    // &num1 gives the memory address of num1 so scanf can write the value into it
    scanf("%d %d", &num1, &num2);

    int sum = num1 + num2;
    printf("Sum of %d and %d is: %d\n", num1, num2, sum);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `scanf()` requires the memory address of the variable (`&variable`), not just the variable name.
- The `&` operator is called the 'Address-Of' operator.
- Always check input return values to avoid reading undefined uninitialized memory.

---

### 📘 [Entry #19/30] Introduction to C: Structure of a C Program & `main()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 10, 2026, 07:34 PM

#### 💡 Overview
Understanding C compilation, header files, the `main()` function entry point, and standard I/O.

#### 💻 Code & Implementation
```c
#include <stdio.h> // Preprocessor directive to include Standard Input/Output library

// Execution of every C program begins in the main() function
int main() {
    // printf prints formatted text to the terminal
    // \n adds a newline character
    printf("Hello, World! Welcome to C Programming.\n");

    // return 0 signals to the Operating System that the program executed successfully
    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `#include <stdio.h>` is a preprocessor command that tells the compiler to include the standard input/output header file.
- `int main()` is the entry point where the program starts execution. `int` means it returns an integer status code.
- `printf()` sends text to the screen; the semicolon `;` ends every statement in C.

---

### 📘 [Entry #3/31] User Input in C: Using `scanf()` and Addressing Memory
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 07:57 PM

#### 💡 Overview
Reading integers, floats, and characters from user input with the address-of operator `&`.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int num1, num2;

    printf("Enter two integers separated by space: ");
    // &num1 gives the memory address of num1 so scanf can write the value into it
    scanf("%d %d", &num1, &num2);

    int sum = num1 + num2;
    printf("Sum of %d and %d is: %d\n", num1, num2, sum);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `scanf()` requires the memory address of the variable (`&variable`), not just the variable name.
- The `&` operator is called the 'Address-Of' operator.
- Always check input return values to avoid reading undefined uninitialized memory.

---

### 📘 [Entry #8/27] Introduction to C: Structure of a C Program & `main()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 07:57 PM

#### 💡 Overview
Understanding C compilation, header files, the `main()` function entry point, and standard I/O.

#### 💻 Code & Implementation
```c
#include <stdio.h> // Preprocessor directive to include Standard Input/Output library

// Execution of every C program begins in the main() function
int main() {
    // printf prints formatted text to the terminal
    // \n adds a newline character
    printf("Hello, World! Welcome to C Programming.\n");

    // return 0 signals to the Operating System that the program executed successfully
    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `#include <stdio.h>` is a preprocessor command that tells the compiler to include the standard input/output header file.
- `int main()` is the entry point where the program starts execution. `int` means it returns an integer status code.
- `printf()` sends text to the screen; the semicolon `;` ends every statement in C.

---

### 📘 [Entry #10/27] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 07:58 PM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #11/27] C Data Types, Variables & Format Specifiers
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 07:58 PM

#### 💡 Overview
Basic primitive types: `int`, `float`, `double`, `char`, memory sizes, and format specifiers (`%d`, `%f`, `%c`, `%s`).

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int age = 20;              // Integer: 4 bytes (e.g. 10, -50, 1000)
    float gpa = 8.75f;         // Floating-point: 4 bytes (single precision)
    double pi = 3.1415926535;  // Double precision float: 8 bytes
    char grade = 'A';          // Single character: 1 byte (enclosed in single quotes)

    printf("Age: %d\n", age);          // %d for integers
    printf("GPA: %.2f\n", gpa);        // %.2f prints float with 2 decimal places
    printf("Pi: %.6lf\n", pi);         // %lf for double
    printf("Grade: %c\n", grade);      // %c for character

    // sizeof operator returns size in bytes
    printf("Size of int: %lu bytes\n", sizeof(int));
    printf("Size of double: %lu bytes\n", sizeof(double));

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- In C, you must declare variable types before using them (statically typed language).
- Format specifiers tell `printf` and `scanf` how to interpret binary data in memory.
- `sizeof()` is a compile-time operator that returns the byte size of data types.

---

### 📘 [Entry #12/27] Dynamic Memory Allocation in C: `malloc()`, `calloc()`, and `free()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 07:58 PM

#### 💡 Overview
Allocating heap memory dynamically at runtime and preventing memory leaks.

#### 💻 Code & Implementation
```c
#include <stdio.h>
#include <stdlib.h> // Required for malloc, calloc, free

int main() {
    int n = 5;
    // malloc allocates n * sizeof(int) bytes on the Heap
    int* arr = (int*)malloc(n * sizeof(int));

    if (arr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Initialize array
    for (int i = 0; i < n; i++) {
        arr[i] = (i + 1) * 10;
    }

    printf("Dynamically allocated array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // CRITICAL: Always free allocated heap memory when finished
    free(arr);
    arr = NULL; // Prevent dangling pointer

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `malloc(size)` allocates uninitialized memory block on the Heap.
- `calloc(count, size)` allocates and zeroes out all allocated bytes.
- `free(ptr)` releases memory back to the OS. Failing to call `free` causes memory leaks.

---

### 📘 [Entry #13/27] User Input in C: Using `scanf()` and Addressing Memory
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 07:58 PM

#### 💡 Overview
Reading integers, floats, and characters from user input with the address-of operator `&`.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int num1, num2;

    printf("Enter two integers separated by space: ");
    // &num1 gives the memory address of num1 so scanf can write the value into it
    scanf("%d %d", &num1, &num2);

    int sum = num1 + num2;
    printf("Sum of %d and %d is: %d\n", num1, num2, sum);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `scanf()` requires the memory address of the variable (`&variable`), not just the variable name.
- The `&` operator is called the 'Address-Of' operator.
- Always check input return values to avoid reading undefined uninitialized memory.

---

### 📘 [Entry #24/27] Dynamic Memory Allocation in C: `malloc()`, `calloc()`, and `free()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 07:59 PM

#### 💡 Overview
Allocating heap memory dynamically at runtime and preventing memory leaks.

#### 💻 Code & Implementation
```c
#include <stdio.h>
#include <stdlib.h> // Required for malloc, calloc, free

int main() {
    int n = 5;
    // malloc allocates n * sizeof(int) bytes on the Heap
    int* arr = (int*)malloc(n * sizeof(int));

    if (arr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Initialize array
    for (int i = 0; i < n; i++) {
        arr[i] = (i + 1) * 10;
    }

    printf("Dynamically allocated array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // CRITICAL: Always free allocated heap memory when finished
    free(arr);
    arr = NULL; // Prevent dangling pointer

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `malloc(size)` allocates uninitialized memory block on the Heap.
- `calloc(count, size)` allocates and zeroes out all allocated bytes.
- `free(ptr)` releases memory back to the OS. Failing to call `free` causes memory leaks.

---

### 📘 [Entry #26/27] Introduction to C: Structure of a C Program & `main()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 07:59 PM

#### 💡 Overview
Understanding C compilation, header files, the `main()` function entry point, and standard I/O.

#### 💻 Code & Implementation
```c
#include <stdio.h> // Preprocessor directive to include Standard Input/Output library

// Execution of every C program begins in the main() function
int main() {
    // printf prints formatted text to the terminal
    // \n adds a newline character
    printf("Hello, World! Welcome to C Programming.\n");

    // return 0 signals to the Operating System that the program executed successfully
    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `#include <stdio.h>` is a preprocessor command that tells the compiler to include the standard input/output header file.
- `int main()` is the entry point where the program starts execution. `int` means it returns an integer status code.
- `printf()` sends text to the screen; the semicolon `;` ends every statement in C.

---

### 📘 [Entry #2/30] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 08:59 PM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #7/30] User Input in C: Using `scanf()` and Addressing Memory
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 09:00 PM

#### 💡 Overview
Reading integers, floats, and characters from user input with the address-of operator `&`.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int num1, num2;

    printf("Enter two integers separated by space: ");
    // &num1 gives the memory address of num1 so scanf can write the value into it
    scanf("%d %d", &num1, &num2);

    int sum = num1 + num2;
    printf("Sum of %d and %d is: %d\n", num1, num2, sum);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `scanf()` requires the memory address of the variable (`&variable`), not just the variable name.
- The `&` operator is called the 'Address-Of' operator.
- Always check input return values to avoid reading undefined uninitialized memory.

---

### 📘 [Entry #15/30] Introduction to C: Structure of a C Program & `main()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 09:00 PM

#### 💡 Overview
Understanding C compilation, header files, the `main()` function entry point, and standard I/O.

#### 💻 Code & Implementation
```c
#include <stdio.h> // Preprocessor directive to include Standard Input/Output library

// Execution of every C program begins in the main() function
int main() {
    // printf prints formatted text to the terminal
    // \n adds a newline character
    printf("Hello, World! Welcome to C Programming.\n");

    // return 0 signals to the Operating System that the program executed successfully
    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `#include <stdio.h>` is a preprocessor command that tells the compiler to include the standard input/output header file.
- `int main()` is the entry point where the program starts execution. `int` means it returns an integer status code.
- `printf()` sends text to the screen; the semicolon `;` ends every statement in C.

---

### 📘 [Entry #17/30] Dynamic Memory Allocation in C: `malloc()`, `calloc()`, and `free()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 09:00 PM

#### 💡 Overview
Allocating heap memory dynamically at runtime and preventing memory leaks.

#### 💻 Code & Implementation
```c
#include <stdio.h>
#include <stdlib.h> // Required for malloc, calloc, free

int main() {
    int n = 5;
    // malloc allocates n * sizeof(int) bytes on the Heap
    int* arr = (int*)malloc(n * sizeof(int));

    if (arr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Initialize array
    for (int i = 0; i < n; i++) {
        arr[i] = (i + 1) * 10;
    }

    printf("Dynamically allocated array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // CRITICAL: Always free allocated heap memory when finished
    free(arr);
    arr = NULL; // Prevent dangling pointer

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `malloc(size)` allocates uninitialized memory block on the Heap.
- `calloc(count, size)` allocates and zeroes out all allocated bytes.
- `free(ptr)` releases memory back to the OS. Failing to call `free` causes memory leaks.

---

### 📘 [Entry #18/30] C Data Types, Variables & Format Specifiers
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 09:01 PM

#### 💡 Overview
Basic primitive types: `int`, `float`, `double`, `char`, memory sizes, and format specifiers (`%d`, `%f`, `%c`, `%s`).

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int age = 20;              // Integer: 4 bytes (e.g. 10, -50, 1000)
    float gpa = 8.75f;         // Floating-point: 4 bytes (single precision)
    double pi = 3.1415926535;  // Double precision float: 8 bytes
    char grade = 'A';          // Single character: 1 byte (enclosed in single quotes)

    printf("Age: %d\n", age);          // %d for integers
    printf("GPA: %.2f\n", gpa);        // %.2f prints float with 2 decimal places
    printf("Pi: %.6lf\n", pi);         // %lf for double
    printf("Grade: %c\n", grade);      // %c for character

    // sizeof operator returns size in bytes
    printf("Size of int: %lu bytes\n", sizeof(int));
    printf("Size of double: %lu bytes\n", sizeof(double));

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- In C, you must declare variable types before using them (statically typed language).
- Format specifiers tell `printf` and `scanf` how to interpret binary data in memory.
- `sizeof()` is a compile-time operator that returns the byte size of data types.

---

### 📘 [Entry #20/30] Introduction to C: Structure of a C Program & `main()`
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 09:01 PM

#### 💡 Overview
Understanding C compilation, header files, the `main()` function entry point, and standard I/O.

#### 💻 Code & Implementation
```c
#include <stdio.h> // Preprocessor directive to include Standard Input/Output library

// Execution of every C program begins in the main() function
int main() {
    // printf prints formatted text to the terminal
    // \n adds a newline character
    printf("Hello, World! Welcome to C Programming.\n");

    // return 0 signals to the Operating System that the program executed successfully
    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `#include <stdio.h>` is a preprocessor command that tells the compiler to include the standard input/output header file.
- `int main()` is the entry point where the program starts execution. `int` means it returns an integer status code.
- `printf()` sends text to the screen; the semicolon `;` ends every statement in C.

---

### 📘 [Entry #21/30] C Pointers Explained: Address-of (`&`) & Dereference (`*`)
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 09:01 PM

#### 💡 Overview
What pointers are, how they store memory addresses, and how dereferencing works in C.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int value = 42;
    
    // int* declares a pointer to an integer
    // &value gets the memory address of 'value'
    int* ptr = &value;

    printf("Value of variable: %d\n", value);
    printf("Memory address of variable (&value): %p\n", (void*)&value);
    printf("Pointer variable stores address (ptr): %p\n", (void*)ptr);
    
    // Dereferencing: *ptr accesses the value at the stored address
    printf("Value fetched via pointer (*ptr): %d\n", *ptr);

    // Modifying value through pointer
    *ptr = 100;
    printf("New value of variable after *ptr = 100: %d\n", value);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- A pointer is simply a variable that stores the memory address of another variable.
- `&` (Address-Of): Gets the hexadecimal memory location where data lives in RAM.
- `*` (Dereference): Follows the address to read or modify the actual stored data.

---

### 📘 [Entry #22/30] User Input in C: Using `scanf()` and Addressing Memory
> **Track:** `C-PROGRAMMING` | **Updated:** Sep 11, 2026, 09:01 PM

#### 💡 Overview
Reading integers, floats, and characters from user input with the address-of operator `&`.

#### 💻 Code & Implementation
```c
#include <stdio.h>

int main() {
    int num1, num2;

    printf("Enter two integers separated by space: ");
    // &num1 gives the memory address of num1 so scanf can write the value into it
    scanf("%d %d", &num1, &num2);

    int sum = num1 + num2;
    printf("Sum of %d and %d is: %d\n", num1, num2, sum);

    return 0;
}
```

#### 🎯 Key Concepts & Takeaways
- `scanf()` requires the memory address of the variable (`&variable`), not just the variable name.
- The `&` operator is called the 'Address-Of' operator.
- Always check input return values to avoid reading undefined uninitialized memory.
