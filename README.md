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