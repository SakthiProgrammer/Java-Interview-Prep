
## 📚 Table of Contents

| Topic | Description |
|-------|-------------|
| [Programming](#programming) | What is Programming, real-world examples |
| [Types of Programming Paradigms](#types-of-progamming-language-paradigms) | Procedural, Functional, OOP |
| [Static vs Dynamic Languages](#static-vs-dynamic-language) | Type systems and comparisons |
| [Memory Management](#what-is-memory-management) | Java Memory model and Garbage Collection |

## Programming

**Computer at very minute level, Only Understand Zero and Ones (0 & 1) Known as Binary Code**

### 📘 What is Programming?

Programming is the process of writing instructions (called **code**) that a computer can execute to perform specific tasks, solve problems, or automate processes.

It involves using a **programming language** (like **Java, Python, C++**) to communicate with the computer effectively.


### 🌍 **Real-World Example: Programming**

Programming is like writing a **recipe** for a chef:

* The **recipe steps** = Program instructions
* The **chef** = Computer
* The **dish** = Output or result of the program

If the steps are written clearly, the chef (computer) can successfully prepare the dish (run the program without errors).



### 🌍 **Real-World Example: Programming Language**

| Communication Type    | Example                                                                                     |
|-----------------------|---------------------------------------------------------------------------------------------|
| **Human to Human**    | Humans use **English, Tamil**, or other languages to communicate with each other.           |
| **Human to Computer** | Humans use **Programming Languages** like **Java, Python, C++** to communicate with computers. |

Humans can't directly understand machine code, so we use programming languages as a bridge to give instructions to computers in a way they can understand, using a compiler or interpreter.

At the most basic level, computers only understand machine code, which is made up of zeros and ones (0 & 1), called binary code. Programming languages let us write instructions in a way that's easy for us to read, and then the compiler or interpreter translates them into binary so the computer can run them.

### ✅ **Example (Java Program)**

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");  // Simple instruction to print text
    }
}
```

> This is a program that **instructs the computer to display** `Hello, World!` on the screen.

### Types of Progamming Language (paradigms) 

| 💻 Programming Type       | 📘 Definition | 🌍 Real-World Example |
|------------------------|------------|--------------------|
| **Procedural Programming** | A style of programming where instructions are executed step-by-step in a sequence. | A **cooking recipe** where each step is followed in order. Example Language: **C** |
| **Functional Programming** | Programming based on mathematical functions, avoiding state and mutable data. | A **vending machine**: You give an input (money) and receive an output (snack) without altering the machine's internals. Example Language: **Haskell, Scala** |
| **Object-Oriented Programming (OOP)** | Programming that models real-world entities as objects with attributes and behaviors. | **Car design:** A car (object) has properties (color, speed) and actions (drive, brake). Example Language: **Java, C++** |

---
Java is **primarily Object-Oriented**, but it also supports **Procedural Programming** concepts.

### 🔹 **Explanation**

* **Object-Oriented:**
  Java is designed around classes and objects. Everything revolves around defining entities (`class`) with attributes and behaviors (methods).

> Example: `Car`, `Employee` as objects with properties and methods.

* **Procedural:**
  Java allows writing code using **procedures or methods (functions)** that perform operations step by step, similar to procedural languages like C.

> Example: A `main()` method that sequences instructions is procedural.

---

### ✅ **Example**

```java
public class Example {
    public static void main(String[] args) {
        greet();  // procedural style
    }

    static void greet() {
        System.out.println("Hello, World!");
    }
}
```

Even though the method is static and procedural, it's still inside a **class** because Java mandates that everything must be within a class structure — aligning it with object-oriented principles.

---

### ✅ **Summary Statement for Interview**

> "Java supports both **Object-Oriented** and **Procedural Programming**. While it enforces OOP by requiring code to reside inside classes, we can still write methods that follow a procedural sequence, combining both paradigms effectively."

---
### Static vs Dynamic Language


| Feature                  | Static Typed Languages                             | Dynamic Typed Languages                            |
|--------------------------|----------------------------------------------------|----------------------------------------------------|
| **Type Checking**        | At **compile time**                              | At **runtime**                                    |
| **Error Detection**      | Early detection of type errors                   | Errors may occur during execution                 |
| **Performance**          | More optimized due to compile-time checks        | Slightly slower due to runtime checks             |
| **Examples**             | Java, C, C++                                      | Python, JavaScript, Ruby                         |
| **Real-World Example**   | A **blueprint-based house construction** where all materials and dimensions are predefined     | A chef who decides the ingredients while cooking based on taste preference|

#### ✅ **Summary:**

- **Static Languages:** Provide higher safety, early error detection, and optimized performance, but are less flexible.
- **Dynamic Languages:** Offer more flexibility and faster development, especially for prototypes, but can lead to runtime errors if not handled carefully.

--- 

### What is Memory Management?

 Memory Management in Java is the process of efficiently allocating, using, and deallocating memory to ensure that applications run smoothly without running out of memory. It is managed automatically by the Java Virtual Machine (JVM).

**Real-World Example:** Like managing the seating arrangement in a busy restaurant — seats (memory) are allocated to customers (data), cleaned up and made available again when they leave (deallocation/garbage collection), ensuring the restaurant operates smoothly without running out of space. This is handled automatically by the **Java Virtual Machine (JVM)**.

Java Memory is broadly divided into:

1. **Stack:**
   - Stores **local variables**, method calls, and references to objects in the heap.
   - Operates on a **Last-In, First-Out (LIFO)** principle.
   - Memory in the stack is automatically allocated and deallocated when methods are called and return.
   - **Real-World Example:** Like a **stack of plates** in a cafeteria; the last plate placed on top is the first one taken off.
   - **Key Point for Interview:** Stack memory is faster but limited in size. If too many method calls occur, it may cause a **StackOverflowError**.

2. **Heap:**
   - Stores **objects and their instance variables**.
   - Memory is allocated dynamically at runtime.
   - Access to heap memory is slower than stack but more flexible.
   - **Real-World Example:** Like a **warehouse** where items (objects) are placed in different locations and managed as needed.
   - **Key Point for Interview:** Heap memory is shared among all threads, and improper handling can lead to **Memory Leaks**.

3. **Garbage Collection (GC):**
   - An **automatic background process** managed by the JVM that identifies and deletes objects from the heap that are no longer referenced.
   - Helps prevent memory leaks and optimizes memory usage.
   - **Real-World Example:** Like a **cleaning crew in a warehouse** that removes items no longer needed.
   - **Key Point for Interview:** Developers cannot directly free memory but can make objects eligible for GC by removing all references.

