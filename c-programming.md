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
