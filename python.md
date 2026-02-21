# Python Interview Questions

## Basic Level

**Q1: What are Lists, Tuples, and Dictionaries in Python?**
**Answer:**
* **List (`[1, 2, 3]`):** An ordered, mutable (changeable) collection of items.
* **Tuple (`(1, 2, 3)`):** An ordered, immutable (unchangeable) collection of items. Used for fixed data.
* **Dictionary (`{'a': 1}`):** An unordered collection of key-value pairs. Optimized for fast lookups based on a unique key.

**Q2: Is Python an interpreted or compiled language?**
**Answer:**
It is technically both, but mostly considered interpreted. Python source code `.py` is first compiled into a hidden intermediate "bytecode" (`.pyc` file), and this bytecode is then interpreted and executed line-by-line by the Python Virtual Machine (PVM) at runtime.

**Q3: What are `*args` and `**kwargs`?**
**Answer:**
They allow a function to accept a variable number of arguments.
* `*args` takes unlimited positional arguments and stores them in a tuple.
* `**kwargs` takes unlimited keyword arguments (named arguments) and stores them in a dictionary.

## Intermediate Level

**Q4: What is the difference between `==` and `is`?**
**Answer:**
* `==` checks for **Equality**. It compares the actual *values* of the objects to see if they are equivalent.
* `is` checks for **Identity**. It compares the memory addresses to see if they are the exact same physical object in memory.

**Q5: What is a Generator and the `yield` keyword?**
**Answer:**
A generator is a special type of iterator. Instead of returning a giant list all at once (which consumes massive memory), a generator computes and returns values one at a time using the `yield` keyword. It suspends its state and pauses until the next value is requested, making it highly memory efficient for large datasets.

**Q6: Explain "Shallow Copy" vs. "Deep Copy".**
**Answer:**
If you have a nested list: `list_a = [[1, 2], [3, 4]]`
* **Shallow Copy (`copy.copy()`):** Creates a new outer list, but fills it with *references* to the internal child lists. If you change a child list in the copy, the original is affected.
* **Deep Copy (`copy.deepcopy()`):** Recursively creates new copies of the outer list AND all internal child objects. They are completely separated in memory.

## Advanced Level

**Q7: What is the GIL (Global Interpreter Lock)?**
**Answer:**
The GIL is a mechanism used in CPython (the standard Python implementation). It acts as a mutex lock that prevents multiple native OS threads from executing Python bytecodes at the *exact same time*. 
This makes standard Python memory management thread-safe but prevents standard threads from utilizing multiple CPU cores for heavy mathematical (CPU-bound) tasks.

**Q8: Explain Python Decorators.**
**Answer:**
A decorator is a design pattern that allows you to modify or extend the behavior of a function without permanently modifying the function itself. In code, it is a function that takes another function as an argument, wraps it in some new logic (like adding a timer or checking permissions), and returns the new wrapped function. It is applied using the `@decorator_name` syntax above a function.

**Q9: What are Dunder or Magic Methods?**
**Answer:**
Dunder (Double UNDERscore) methods in Python class definitions (like `__init__`, `__str__`, `__len__`, `__add__`) are special methods invoked automatically under the hood by built-in Python syntax.
For example, defining `__add__(self, other)` in a custom Vector class explains to Python exactly what to do when a user types `vector1 + vector2`.
