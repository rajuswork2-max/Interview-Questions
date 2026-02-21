# C Programming Interview Questions

## Basic Level

**Q1: What is a Pointer in C?**
**Answer:**
A pointer is a special variable that stores the raw memory address of another variable. Instead of holding a default value like `10`, it holds an address like `0x7ffee9b`.

**Q2: What is the difference between local and global variables?**
**Answer:**
* **Local Variables:** Declared inside a function block. They only exist while the function is executing and cannot be accessed outside it.
* **Global Variables:** Declared outside all functions. They exist for the entire lifetime of the program and can be accessed and modified by any function.

**Q3: What are Header Files (`.h`) in C?**
**Answer:**
Header files contain C function declarations (prototypes) and macro definitions. They are included in `.c` files using `#include <stdio.h>`. They allow you to share function definitions across multiple different source code files.

## Intermediate Level

**Q4: Compare `malloc()` vs `calloc()`.**
**Answer:**
Both are used for dynamic memory allocation on the heap.
* `malloc(size)` allocates a single block of memory of the specified size. Crucially, the memory is left uninitialized (full of garbage data).
* `calloc(number_of_elements, element_size)` allocates multiple blocks of memory. Crucially, it initializes all allocated bytes to zero.

**Q5: What is a Memory Leak?**
**Answer:**
A memory leak happens when a program dynamically allocates memory using `malloc` but fails to release it using `free()` when it is no longer needed. If a program runs continuously (like a server) and leaks memory, it will eventually consume all available RAM and crash.

**Q6: Explain Pass by Value vs. Pass by Reference.**
**Answer:**
* **Pass by Value:** A copy of the actual variable is passed to the function. Modifying the copy inside the function does not affect the original variable.
* **Pass by Reference (via Pointers):** The memory address of the variable is passed to the function. By dereferencing the pointer, the function directly modifies the original variable in the caller's scope.

## Advanced Level

**Q7: What is a Dangling Pointer?**
**Answer:**
A dangling pointer is a pointer that contains the memory address of an object that has been freed or deleted. 
If you allocate memory, store the address in pointer `P`, and then call `free(P)`, the memory is returned to the OS, but `P` still holds the old address. If you try to dereference `P` later, it results in Undefined Behavior (crashes or data corruption).

**Q8: Why is the `volatile` keyword used?**
**Answer:**
The `volatile` keyword tells the compiler that a variable's value can be changed unexpectedly by something outside the surrounding program code (like an operating system hardware interrupt or a separate concurrent thread). This prevents the compiler from aggressively optimizing the code and ensures that every time the variable is referenced, the program directly reads from physical memory rather than utilizing a cached CPU register.

**Q9: What is a Function Pointer?**
**Answer:**
Like a normal pointer holds the address of a variable, a function pointer holds the memory address of executable code (a function). This allows you to pass functions as arguments to other functions (creating "callbacks"), or store arrays of functions to build state machines and avoid massive `switch-case` statements.
