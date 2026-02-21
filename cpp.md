# C++ Interview Questions

## Basic Level

**Q1: What is C++ and how does it differ from C?**
**Answer:**
C++ is a compiled, general-purpose programming language. The main difference is that C++ is an Object-Oriented language, meaning it supports Classes, Inheritance, and Polymorphism, whereas C is a purely procedural language. C++ also introduces features like references, templates, and exception handling.

**Q2: What is the difference between `new` and `malloc()`?**
**Answer:**
* `malloc()` is a C library function that simply allocates raw memory on the heap and returns a `void` pointer. It does not initialize the memory.
* `new` is a C++ operator. It allocates memory on the heap AND automatically calls the constructor of the class to properly initialize the object. It returns a pointer of the specific object type.

**Q3: What are access specifiers in C++?**
**Answer:**
They determine the visibility of class members:
* **public:** Members can be accessed from outside the class.
* **private:** Members can only be accessed by functions inside the class itself.
* **protected:** Members can be accessed inside the class and by any derived (child) classes.

## Intermediate Level

**Q4: What is a Reference vs. a Pointer?**
**Answer:**
* **Pointer:** Stores a memory address. It can be reassigned to point elsewhere, it can be `nullptr`, and you use the `*` or `->` operators to access the value.
* **Reference:** An alias for an existing variable. It must be initialized when created, it cannot be reassigned, and it cannot be null. It shares the same syntax as a normal variable.

**Q5: Explain the `virtual` keyword and Virtual Functions.**
**Answer:**
Placing the `virtual` keyword before a function in a base class allows that function to be overridden by a derived class. It tells the compiler to use "dynamic linkage" (late binding), ensuring the correct overridden function is called at runtime when accessed via a base class pointer.

**Q6: What is a Destructor, and why should base class destructors be virtual?**
**Answer:**
A destructor (`~MyClass()`) cleans up resources (like dynamic memory) when an object goes out of scope. 
If a derived class object is deleted through a base class pointer, and the base class destructor is NOT virtual, only the base class destructor will be called, resulting in a resource leak for the derived part. Making it virtual ensures the derived destructor runs first.

## Advanced Level

**Q7: What are Smart Pointers? (Name the three main types)**
**Answer:**
Smart pointers automatically manage dynamic memory to prevent memory leaks, eliminating the need to call `delete`.
1. **`std::unique_ptr`:** Owns the object exclusively. When it goes out of scope, the memory is deleted.
2. **`std::shared_ptr`:** Keeps a reference count. Multiple shared pointers can own the same object. The memory is deleted only when the last `shared_ptr` is destroyed (count reaches zero).
3. **`std::weak_ptr`:** Observes a `shared_ptr` but doesn't increase the reference count (used to break circular references).

**Q8: What is `std::move` and what are Move Semantics?**
**Answer:**
Move semantics optimize performance radically. Instead of doing "deep copies" of large objects (like allocating new memory and copying a 1GB array), `std::move` casts an object into an "rvalue reference". This tells the compiler to "steal" the internal memory pointers from a temporary source object and move them to the new object, leaving the temporary source empty. It turns a massive O(N) copy operation into an instant O(1) pointer swap.

**Q9: What is the Rule of Three / Rule of Five?**
**Answer:**
* **Rule of Three:** If a class needs a custom **Destructor** (to free dynamic memory), it almost certainly also needs a custom **Copy Constructor** and a custom **Copy Assignment Operator** to handle deep copying and prevent dangling pointers.
* **Rule of Five (Modern C++):** Adds the **Move Constructor** and **Move Assignment Operator** to the rule above for optimal performance using move semantics.
