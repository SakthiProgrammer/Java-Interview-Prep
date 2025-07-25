## Exception Handling

### ✅ **What is Exception Handling in Java?**

**Exception handling** in Java is a **mechanism to handle runtime errors**, so the normal flow of the application can be maintained. Instead of crashing the program, Java lets you catch and respond to errors like file not found, divide by zero, or invalid input.

---

### 🧠 **Key Keywords in Java Exception Handling:**

* `try`: Block of code that might throw an exception.
* `catch`: Block that handles the exception.
* `finally`: Block that is always executed, whether an exception occurs or not.
* `throw`: Used to explicitly throw an exception.
* `throws`: Declares exceptions in method signature.

---

### 🔁 **Syntax Example:**

```java
try {
    // risky code
} catch (ExceptionType name) {
    // handling code
} finally {
    // cleanup code
}
```

---

### 💡 **Real-Time Example (Interview Style):**

Imagine you're building a **cab booking system** (like your portfolio project). A user enters their pickup time, and your system needs to convert that input into a proper time format.

#### ✅ **Code Example:**

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class BookingSystem {
    public static void main(String[] args) {
        String inputTime = "25:61"; // Invalid time format

        try {
            SimpleDateFormat sdf = new SimpleDateFormat("HH:mm");
            Date time = sdf.parse(inputTime); // This may throw ParseException
            System.out.println("Pickup time is: " + time);
        } catch (ParseException e) {
            System.out.println("Invalid time format entered. Please enter time like HH:mm (e.g., 14:30)");
        } finally {
            System.out.println("Thank you for using our cab booking system.");
        }
    }
}
```

---

### 🎯 **Interview Tip:**

If the interviewer asks **"Why is exception handling important?"**, say:

> "Exception handling ensures that the application doesn't crash unexpectedly. It helps in showing user-friendly error messages, logging the issue for debugging, and continuing the application flow where possible."


---

## ✅ What is `try-catch` in Java?

* **`try` block**: Code that **might throw an exception** is placed here.
* **`catch` block**: Code that **handles the exception** is placed here.

It prevents the program from crashing unexpectedly and lets you respond to errors in a user-friendly way.

---

## 🔹 Syntax:

```java
try {
    // Code that may throw an exception
} catch (ExceptionType e) {
    // Code to handle the exception
}
```

---

## ✅ Simple Example: Divide by Zero

```java
public class TryCatchExample {
    public static void main(String[] args) {
        try {
            int a = 10;
            int b = 0;
            int result = a / b; // this line causes an exception
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: Cannot divide by zero.");
        }
    }
}
```

### 🔍 Output:

```
Error: Cannot divide by zero.
```

---

## 🔎 Explanation:

| Code Line                     | What Happens                                          |
| ----------------------------- | ----------------------------------------------------- |
| `int result = a / b;`         | Tries to divide by 0 → throws `ArithmeticException`   |
| `catch (ArithmeticException)` | Catches the error and prints a friendly message       |
| `System.out.println(...)`     | This message is shown instead of crashing the program |

---

## ✅ Real-Life Analogy:

Think of `try` as saying:

> “Try this task, but if there’s a problem, don’t panic — go to the `catch` and handle it.”

---

## ✅ One More Example: NullPointerException

```java
public class TryCatchNull {
    public static void main(String[] args) {
        try {
            String name = null;
            System.out.println(name.length()); // causes NullPointerException
        } catch (NullPointerException e) {
            System.out.println("Error: You tried to access something from a null value.");
        }
    }
}
```

### 🧠 Output:

```
Error: You tried to access something from a null value.
---

## ✅ What is `finally` Block in Java?

The `finally` block is a special block in Java that **always executes**, whether:

* an exception is thrown or not,
* the exception is caught or not,
* `return` is used in the method.

---

### 🔹 Why use `finally`?

To **perform cleanup** actions like:

* closing files,
* releasing database connections,
* cleaning up memory,
* showing thank-you messages.

---

## ✅ Syntax:

```java
try {
    // risky code
} catch (Exception e) {
    // exception handling
} finally {
    // cleanup code (always runs)
}
```

---

## ✅ Example: Division with Cleanup Message

```java
public class FinallyExample {
    public static void main(String[] args) {
        try {
            int a = 10, b = 0;
            int result = a / b; // throws ArithmeticException
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: Cannot divide by zero.");
        } finally {
            System.out.println("This will always be printed.");
        }
    }
}
```

### 🔍 Output:

```
Error: Cannot divide by zero.  
This will always be printed.
```

Even though there is an error and it was caught, the `finally` block **still runs**.

---

## ✅ Example 2: No Exception Happens

```java
public class FinallyExample2 {
    public static void main(String[] args) {
        try {
            int a = 10, b = 2;
            int result = a / b;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error occurred.");
        } finally {
            System.out.println("Cleanup done in finally block.");
        }
    }
}
```

### 🔍 Output:

```
Result: 5  
Cleanup done in finally block.
```

---

## ✅ Summary:

| Part      | Runs When           | Purpose                         |
| --------- | ------------------- | ------------------------------- |
| `try`     | Normal/risky code   | Code that may cause error       |
| `catch`   | If exception occurs | Handle error                    |
| `finally` | Always              | Cleanup, logging, final message |

---

## ✅ Types of Exception in Java?

An **exception** is an unwanted or unexpected event that disrupts the normal flow of a program.

Java has **two main types** of exceptions:

```
1. Checked Exceptions
2. Unchecked Exceptions
```

---

## 🔹 1. **Checked Exceptions (Compile-Time Exceptions)**

### ✅ What is it?
Checked exceptions are errors that the Java compiler checks while you're writing the code.
You must handle them using try-catch or throws, or your code won't compile.
* These are exceptions **checked by the compiler** at compile time.
* If not handled (using `try-catch` or `throws`), the program will **not compile**.


### 📌 Examples:

* `IOException`
* `SQLException`
* `FileNotFoundException`
* `ClassNotFoundException`

### 🔧 Example:

```java
import java.io.*;

public class CheckedExample {
    public static void main(String[] args) throws IOException {
        FileReader file = new FileReader("test.txt"); // File may not exist
        file.close();
    }
}
```

> 🔔 Compiler forces us to handle or declare this using `throws`.

---

## 🔹 2. **Unchecked Exceptions (Runtime Exceptions)**

### ✅ What is it?
Unchecked exceptions are errors that happen only while running the program.
Java does not force you to handle them.

* These occur at **runtime**, not checked at compile time.
* Program will compile, but may crash at runtime if not handled.

### 📌 Examples:

* `ArithmeticException`
* `NullPointerException`
* `ArrayIndexOutOfBoundsException`
* `NumberFormatException`

### 🔧 Example:

```java
public class UncheckedExample {
    public static void main(String[] args) {
        int a = 10 / 0; // ArithmeticException at runtime
        System.out.println(a);
    }
}
```

> 🔔 Compiler does **not** force you to handle it, but you should.

---

## 🔹 3. **Error (Not an Exception, But Still Throwable)**

### ✅ What is it?

* Represents **serious issues** that applications usually **should not try to handle**.

### 📌 Examples:

* `OutOfMemoryError`
* `StackOverflowError`
* `VirtualMachineError`

---

## ✅ Exception Class Hierarchy:

```
               Throwable
               /       \
         Exception     Error
           /     \
Checked    Runtime (Unchecked)
Exception   Exception
```

---

## 🧠 Summary Table:

| Type                | Checked by Compiler | Example                          | When to Handle         |
| ------------------- | ------------------- | -------------------------------- | ---------------------- |
| Checked Exception   | ✅ Yes               | IOException, SQLException        | Must be handled        |
| Unchecked Exception | ❌ No                | ArithmeticException, NullPointer | Optional (but advised) |
| Error               | ❌ No                | OutOfMemoryError, StackOverflow  | Not handled (serious)  |

---

## ✅ What is a Custom Exception in Java?

A **custom exception** is a user-defined exception that lets you **create your own error types** specific to your application logic.

👉 You create it by **extending** the `Exception` class (for **checked exception**) or `RuntimeException` class (for **unchecked exception**).

---

## 🧱 Steps to Create Custom Exception:

### Step 1: Create your exception class

### Step 2: Use `throw` to throw the exception

### Step 3: Handle it using `try-catch`

---

## ✅ Example: Create a Custom Exception for Cab Booking Age Check

### 🔹 Step 1: Create Custom Exception Class

```java
// Custom exception by extending Exception (checked exception)
public class AgeRestrictionException extends Exception {
    public AgeRestrictionException(String message) {
        super(message);
    }
}
```

---

### 🔹 Step 2 & 3: Use It in a Real Program

```java
public class CabBooking {

    public static void main(String[] args) {
        try {
            bookCab(15); // age below 18 will trigger custom exception
        } catch (AgeRestrictionException e) {
            System.out.println("Booking failed: " + e.getMessage());
        }
    }

    public static void bookCab(int age) throws AgeRestrictionException {
        if (age < 18) {
            throw new AgeRestrictionException("You must be 18 or older to book a cab.");
        }
        System.out.println("Cab booked successfully for age: " + age);
    }
}
```

---

## 🔍 Output:

```
Booking failed: You must be 18 or older to book a cab.
```

---

## ✅ When to Use Custom Exceptions?

* When you want to give **meaningful errors** in your application.
* To **separate business logic errors** from Java's built-in exceptions.
* For better **code readability and maintainability**.

---

## ✅ Checked vs Unchecked Custom Exception

| Type                | Extend Class               | When It Occurs               |
| ------------------- | -------------------------- | ---------------------------- |
| Checked Exception   | `extends Exception`        | Compile-time (must handle)   |
| Unchecked Exception | `extends RuntimeException` | Runtime (optional to handle) |

### 🔹 Unchecked Example:

```java
public class AgeRestrictionRuntimeException extends RuntimeException {
    public AgeRestrictionRuntimeException(String msg) {
        super(msg);
    }
}
```

Then throw it like:

```java
throw new AgeRestrictionRuntimeException("Must be 18 or older!");
```

## Some  simple Java code test for Exception handling
---

## ✅ 🔹 **Java Code Test Question**

### 🔸🧠 Question:

What will be the **output** of the following Java program?

```java
public class TestException {
    public static void main(String[] args) {
        try {
            int[] numbers = {1, 2, 3};
            System.out.println(numbers[3]); // Accessing invalid index
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic Exception caught");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array Index Out Of Bounds Exception caught");
        } finally {
            System.out.println("Finally block executed");
        }
        System.out.println("Program continues...");
    }
}
```

---

### 🔸💭 Options:

A)

```
Arithmetic Exception caught  
Finally block executed  
Program continues...
```

B)

```
Array Index Out Of Bounds Exception caught  
Finally block executed  
Program continues...
```

C)

```
Finally block executed  
Program terminated
```

D)

```
Compilation error
```

---

### ✅ 🟩 **Correct Answer: B**

### 🔍 Explanation:

* `numbers[3]` causes `ArrayIndexOutOfBoundsException`
* It's caught in the corresponding `catch` block
* `finally` block **always runs**
* Program continues normally

---

## 🎯 Output:

```
Array Index Out Of Bounds Exception caught  
Finally block executed  
Program continues...
```

---

### ✅ **🧪 Test Question: What will be the output of the following Java code?**

```java
public class TestChallenge {
    public static void main(String[] args) {
        try {
            int[] arr = new int[3];
            arr[5] = 10; // Line A
            System.out.println("Inside try block");
        } catch (ArithmeticException e) {
            System.out.println("Caught ArithmeticException");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Caught ArrayIndexOutOfBoundsException"); // Line B
        } catch (Exception e) {
            System.out.println("Caught General Exception");
        } finally {
            System.out.println("Finally block executed"); // Line C
        }
        System.out.println("Program continues..."); // Line D
    }
}
```

---

### ✅ **Options:**

**A.**

```
Caught ArrayIndexOutOfBoundsException
Finally block executed
Program continues...
```

**B.**

```
Caught ArithmeticException
Finally block executed
Program continues...
```

**C.**

```
Caught General Exception
Program continues...
```

**D.**

```
Caught ArrayIndexOutOfBoundsException
Program stops
```

---

### ✅ **Correct Answer: A**

---

### ✅ **Explanation:**

* Line A throws `ArrayIndexOutOfBoundsException` because index 5 does not exist.
* It's caught in the **second `catch` block**, not the first (`ArithmeticException`) or third (`Exception`).
* Then, the **`finally` block always executes**, no matter what.
* After that, the program **continues normally**.

---

### ✅ **🧪 Test Question: What will be the output of the following Java code?**

```java
class InvalidAgeException extends Exception {
    public InvalidAgeException(String message) {
        super(message);
    }
}

public class VotingTest {
    public static void checkEligibility(int age) throws InvalidAgeException {
        if (age < 18) {
            throw new InvalidAgeException("Not eligible for voting");
        } else {
            System.out.println("Eligible to vote");
        }
    }

    public static void main(String[] args) {
        try {
            checkEligibility(16);  // Line A
        } catch (InvalidAgeException e) {
            System.out.println("Caught Exception: " + e.getMessage());  // Line B
        } finally {
            System.out.println("Check completed");  // Line C
        }
    }
}
```

---

### ✅ **Options:**

**A.**

```
Eligible to vote
Check completed
```

**B.**

```
Caught Exception: Not eligible for voting
Check completed
```

**C.**

```
Exception in thread "main" InvalidAgeException
```

**D.**

```
Not eligible for voting
Eligible to vote
Check completed
```

---

### ✅ **Correct Answer: B**

---

### ✅ **Explanation:**

* `checkEligibility(16)` throws a **custom checked exception** (`InvalidAgeException`) because age is less than 18.
* It's caught in the `catch` block and the message is printed.
* `finally` block always runs → `"Check completed"` is printed.
* This is a **classic example of `throw`, `throws`, try-catch-finally, and custom exceptions**.

---
Perfect, Ramana! Here's a **challenging scenario** involving:

* `throw` and `throws`
* a method that is *declared* to throw an exception but is **never called**
* and **nested try-catch inside a loop**

---

### ✅ **🧪 Test Question: What will be the output of the following code?**

```java
class NetworkException extends Exception {
    public NetworkException(String message) {
        super(message);
    }
}

public class ServerTest {

    // Method declared with throws but never called
    public static void connectToServer() throws NetworkException {
        throw new NetworkException("Failed to connect");
    }

    public static void main(String[] args) {
        for (int i = 1; i <= 3; i++) {
            try {
                System.out.println("Attempt " + i);
                if (i == 2) {
                    throw new ArithmeticException("Math error"); // Only on 2nd attempt
                }
                System.out.println("Success in attempt " + i);
            } catch (ArithmeticException e) {
                System.out.println("Caught: " + e.getMessage());
            } finally {
                System.out.println("Cleaning up for attempt " + i);
            }
        }

        System.out.println("Program completed");
    }
}
```

---

### ✅ **Options:**

**A.**

```
Attempt 1
Success in attempt 1
Cleaning up for attempt 1
Attempt 2
Caught: Math error
Cleaning up for attempt 2
Attempt 3
Success in attempt 3
Cleaning up for attempt 3
Program completed
```

**B.**

```
Caught: Math error
Cleaning up for attempt 2
Program completed
```

**C.**

```
Attempt 2
Caught: Math error
Cleaning up for attempt 2
Program completed
```

**D.**

```
Failed to connect
Caught: NetworkException
Cleaning up
```

---

### ✅ **Correct Answer: A**

---

### ✅ **Explanation:**

* The method `connectToServer()` is declared with `throws` and even throws an exception, but it is **never called**, so it has no effect.
* The loop runs **three times**.

  * Attempt 1: no exception, prints success.
  * Attempt 2: throws and catches `ArithmeticException`, prints error.
  * Attempt 3: normal again.
* The `finally` block runs **every time** after the try-catch.
* Then "Program completed" is printed.

---









