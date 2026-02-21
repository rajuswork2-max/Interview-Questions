# Object-Oriented Programming (OOP) Interview Questions

## Basic Level

**Q1: What are the four main pillars of OOP?**
**Answer:**
1. **Encapsulation:** Wrapping data (variables) and code acting on the data (methods) together as a single unit (class).
2. **Abstraction:** Hiding complex implementation details and showing only the essential features of an object.
3. **Inheritance:** The mechanism where a new class inherits properties and behaviors from an existing class.
4. **Polymorphism:** The ability to present the same interface for differing underlying forms (data types or classes).

**Q2: What is the difference between a Class and an Object?**
**Answer:**
* **Class:** A logical entity or blueprint. It defines the structure, variables, and methods that an object will have. (e.g., A blueprint for a Car).
* **Object:** A physical entity or an instance of a class. It occupies memory and holds specific data states. (e.g., A red Toyota Corolla parked in the driveway).

**Q3: What are Constructors and what is their purpose?**
**Answer:**
A constructor is a special method inside a class that is automatically invoked when an object of that class is created. Its main purpose is to initialize the new object's variables and allocate any necessary memory or resources at birth.

## Intermediate Level

**Q4: Explain the difference between Method Overloading and Method Overriding.**
**Answer:**
* **Method Overloading (Compile-Time Polymorphism):** Defining multiple methods in the *same class* with the *same name* but different parameters (different number or type of arguments).
* **Method Overriding (Run-Time Polymorphism):** Defining a method in a *child class* that has the exact same name and signature as a method in its *parent class*, effectively replacing the parent's behavior for that child object.

**Q5: What is the difference between an Abstract Class and an Interface?**
**Answer:**
* **Abstract Class:** Can have both abstract methods (without a body) and concrete methods (with a body). It represents a core identity ("is-a" relationship) and can contain state (instance variables).
* **Interface:** Historically, it can only contain abstract methods and constants (though modern languages allow default methods). It represents a capability or contract ("can-do" relationship). A class can implement multiple interfaces but usually only inherit from one abstract class.

**Q6: What is Encapsulation and how is it practically implemented?**
**Answer:**
Encapsulation is data hiding. It is implemented by declaring the class variables as `private` (so outer code cannot directly modify them) and providing `public` getter and setter methods to access and update the value securely. This prevents the object from entering an invalid state.

## Advanced Level

**Q7: Why do modern design practices favor "Composition over Inheritance"?**
**Answer:**
Inheritance creates tight, fragile class hierarchies. If a parent class changes, all children are affected. Also, a child class inherently inherits all of the parent's baggage, even if it only needs part of it.
Composition builds complex objects by combining smaller, distinct objects. Instead of a "IS-A" relationship (A Car IS A Vehicle), it uses a "HAS-A" relationship (A Car HAS An Engine). This leads to much more modular, flexible, and testable code.

**Q8: What is the "Diamond Problem" in multiple inheritance?**
**Answer:**
It occurs when a class inherits from two classes, both of which inherit from a single common grandmother class. If the two parent classes both override a method from the grandmother, the grandchild class faces an ambiguity: which version of the method should it inherit? 
Languages like Java/C# solve this by outright banning multiple inheritance of classes, allowing it only for interfaces.

**Q9: What is "Late Binding" (Dynamic Dispatch)?**
**Answer:**
It is a mechanism used to resolve polymorphic function calls at runtime. When a virtual function is called through a base class pointer or reference, the program checks the actual object type at runtime using a Virtual Table (vtable), and calls the appropriate overridden function in the derived class, rather than deciding which function to call at compile time (early binding).
