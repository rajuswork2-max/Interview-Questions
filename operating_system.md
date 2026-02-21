# Operating System (OS) Interview Questions

## Basic Level

**Q1: What is an Operating System and what is its primary purpose?**
**Answer:**
An Operating System acts as the bridge between the computer hardware and the user applications. Its primary purposes are:
* **Resource Management:** Managing CPU, memory, disk space, and I/O devices efficiently.
* **Abstraction:** Hiding complex hardware details (like disk sectors) behind simple concepts (like files and folders).

**Q2: What is the difference between a Process and a Thread?**
**Answer:**
* **Process:** An independent program in execution. It has its own dedicated memory space, variables, and code. Process creation is "heavyweight" (takes more time and resources).
* **Thread:** A smaller unit of execution that lives *inside* a process. Multiple threads within the same process share the same memory space and resources, making thread creation "lightweight" and communication between them much faster.

**Q3: Explain what a Context Switch is.**
**Answer:**
A context switch is the process where the OS pauses the currently running process (or thread), saves its state (CPU registers, program counter), and loads the state of the next process to run. This happens so quickly that it creates the illusion that multiple programs are running simultaneously.

## Intermediate Level

**Q4: What is Virtual Memory and why is it useful?**
**Answer:**
Virtual memory is a technique that gives the illusion of having a massive amount of RAM.
* **How it works:** The OS divides memory into blocks called "pages". It keeps actively used pages in physical RAM and moves inactive pages to the hard drive (swap space).
* **Why it's useful:** It allows programs larger than the physical RAM to run, and it isolates processes from each other, increasing security.

**Q5: What is a Deadlock? Can you name the four necessary conditions for it?**
**Answer:**
A deadlock is a situation where two or more processes are permanently stuck because they are waiting for resources held by each other.
The four necessary conditions (Coffman conditions) are:
1. **Mutual Exclusion:** A resource can be held by only one process at a time.
2. **Hold and Wait:** A process is holding a resource while waiting for another.
3. **No Preemption:** Resources cannot be forcibly taken away from a process.
4. **Circular Wait:** Process A waits for B, B waits for C, and C waits for A.

**Q6: What is the difference between a Mutex and a Semaphore?**
**Answer:**
* **Mutex (Mutual Exclusion):** A locking mechanism used to ensure only *one* thread can access a shared resource at a time. It has an ownership concept (the thread that locked it must unlock it).
* **Semaphore:** A signaling mechanism that uses a counter to allow a *certain number* of threads to access a resource simultaneously (e.g., allowing exactly 3 threads to use a database connection pool).

## Advanced Level

**Q7: Describe "Thrashing" and how it affects system performance.**
**Answer:**
Thrashing occurs when a computer's virtual memory subsystem is in a constant state of paging. 
Because RAM is full, the OS spends almost all of its CPU time swapping pages between RAM and the hard drive, rather than actually executing the application code. This causes the system to freeze or become extremely slow.

**Q8: What is Priority Inversion and what is the standard solution for it?**
**Answer:**
* **The Problem:** Priority inversion happens when a low-priority task holds a lock on a resource needed by a high-priority task. A medium-priority task then preempts the low-priority task. Now, the high-priority task is effectively blocked by both the low and medium-priority tasks.
* **The Solution:** **Priority Inheritance.** The OS temporarily elevates the priority of the low-priority task to match the high-priority task until it releases the lock, preventing the medium-priority task from interrupting.

**Q9: Explain the difference between Paging and Segmentation.**
**Answer:**
Both are memory management techniques:
* **Paging:** Divides memory into fixed-size blocks (pages). It solves external fragmentation but can lead to internal fragmentation (wasted space inside a page). The division is invisible to the user.
* **Segmentation:** Divides memory into variable-sized blocks based on logical components of the program (like the stack, data, or code). It reflects how the programmer views memory but can lead to external fragmentation.
