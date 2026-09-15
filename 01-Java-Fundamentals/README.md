# ☕ Day 01 — Java Fundamentals

<p align="center">
  <b>Starting my Java journey from the fundamentals — understanding not just how to write Java, but how Java actually works.</b>
</p>

---

## 📌 Today's Goal

Before writing complex Java programs, it is important to understand what happens behind the scenes when we write and run Java code.

By the end of Day 01, I should be able to explain:

- What Java is
- Why Java is platform-independent
- How Java source code becomes executable
- What JDK, JRE, and JVM do
- What Java Bytecode is
- How a basic Java program is structured
- How to compile and run Java programs
- How `main()` works
- How to display output using `System.out.println()`

---

# 1️⃣ What is Java?

**Java** is a high-level, class-based, object-oriented programming language.

It was designed to allow developers to write programs that can run on different operating systems without rewriting the entire program for each platform.

Java is widely used for:

- Backend Development
- Enterprise Applications
- Banking Systems
- E-Commerce Platforms
- Android Applications
- Cloud Applications
- Desktop Applications
- Distributed Systems

---

## 💡 Simple Example

Suppose we create:

```java
public class HelloJava {

    public static void main(String[] args) {
        System.out.println("Hello, Java!");
    }
}
```

This program simply displays:

```text
Hello, Java!
```

It looks simple, but several things happen behind the scenes before this output appears.

We will understand that process below.

---

# 2️⃣ Why is Java Platform Independent?

One of Java's most important ideas is:

> **Write Once, Run Anywhere (WORA)**

Consider that we write a program on Windows:

```text
HelloJava.java
```

Java does not normally compile this source code directly into Windows-specific machine code.

Instead, the Java compiler converts it into:

```text
HelloJava.class
```

The `.class` file contains **Java Bytecode**.

That bytecode can then be executed by a compatible JVM on different operating systems.

### Execution Idea

```text
                   Java Source Code
                         │
                         ▼
                  HelloJava.java
                         │
                         │ javac
                         ▼
                   Java Bytecode
                         │
                         ▼
                  HelloJava.class
                         │
              ┌──────────┼──────────┐
              ▼          ▼          ▼
          Windows JVM  Linux JVM  macOS JVM
              │          │          │
              ▼          ▼          ▼
           Program     Program     Program
            Runs        Runs        Runs
```

### 🧠 Key Point

The **bytecode is portable**, while the JVM implementation is designed for the target platform.

This JVM-based architecture is what enables Java's platform independence.

---

# 3️⃣ JDK, JRE and JVM

These three terms are fundamental in Java.

```text
┌───────────────────────────────────────┐
│                  JDK                  │
│                                       │
│   Development Tools                   │
│   javac, java, javadoc, jar, etc.     │
│                                       │
│   ┌───────────────────────────────┐   │
│   │              JRE              │   │
│   │                               │   │
│   │   Runtime Libraries           │   │
│   │                               │   │
│   │   ┌───────────────────────┐   │   │
│   │   │          JVM          │   │   │
│   │   │                       │   │   │
│   │   │ Executes Bytecode     │   │   │
│   │   └───────────────────────┘   │   │
│   └───────────────────────────────┘   │
└───────────────────────────────────────┘
```

Let's understand them individually.

---

## 🔹 JVM — Java Virtual Machine

**JVM stands for Java Virtual Machine.**

Its primary job is to execute Java bytecode.

Suppose we have:

```text
HelloJava.class
```

The JVM loads the class and executes its bytecode on the current machine.

Conceptually:

```text
Bytecode
   ↓
  JVM
   ↓
Execution on the current platform
```

### JVM Responsibilities

The JVM is involved in tasks such as:

- Loading classes
- Verifying bytecode
- Executing bytecode
- Managing runtime memory
- Garbage collection
- Providing runtime services

### Easy Way to Remember

> **JVM = Executes Java Bytecode**

---

## 🔹 JRE — Java Runtime Environment

**JRE stands for Java Runtime Environment.**

Conceptually, the JRE provides the environment required to **run Java applications**.

A simplified way to understand it is:

```text
JRE
│
├── JVM
│
└── Runtime Libraries
```

### Easy Way to Remember

> **JRE = Environment required to run Java applications**

---

## 🔹 JDK — Java Development Kit

**JDK stands for Java Development Kit.**

It contains the tools developers need to develop Java applications.

Important tools include:

```text
javac    → Java Compiler
java     → Java Application Launcher
jar      → Archive Tool
javadoc  → Documentation Generator
```

A simplified conceptual relationship is:

```text
JDK
│
├── Development Tools
│
└── Java Runtime Components
```

### Easy Way to Remember

> **JDK = Everything required to develop Java applications**

---

## ⚡ JDK vs JRE vs JVM — Quick Comparison

| Component | Full Form | Main Purpose |
|---|---|---|
| **JVM** | Java Virtual Machine | Executes Java bytecode |
| **JRE** | Java Runtime Environment | Provides the Java runtime environment |
| **JDK** | Java Development Kit | Provides tools for Java development |

### Memory Trick

```text
JDK → Develop
JRE → Run
JVM → Execute Bytecode
```

---

# 4️⃣ What is Java Bytecode?

Consider this Java source code:

```java
public class HelloJava {

    public static void main(String[] args) {
        System.out.println("Hello, Java!");
    }
}
```

The source file is:

```text
HelloJava.java
```

When we compile it:

```bash
javac HelloJava.java
```

the Java compiler generates:

```text
HelloJava.class
```

The `.class` file contains **bytecode**.

Bytecode is an intermediate instruction format designed for the JVM.

```text
Source Code
     ↓
   javac
     ↓
 Bytecode
     ↓
    JVM
     ↓
Execution
```

---

# 5️⃣ Complete Java Execution Process

Let's understand the complete journey.

### Step 1 — Write Source Code

Create:

```text
HelloJava.java
```

---

### Step 2 — Compile

Run:

```bash
javac HelloJava.java
```

Here:

```text
javac = Java Compiler
```

The compiler checks the source code and, if compilation succeeds, generates:

```text
HelloJava.class
```

---

### Step 3 — Run

Now execute:

```bash
java HelloJava
```

Notice:

```bash
java HelloJava
```

not:

```bash
java HelloJava.class
```

The Java launcher starts the JVM and loads the `HelloJava` class.

---

### Step 4 — Output

```text
Hello, Java!
```

So the complete flow is:

```text
HelloJava.java
      │
      │ javac
      ▼
HelloJava.class
      │
      │ java HelloJava
      ▼
     JVM
      │
      ▼
Hello, Java!
```

---

# 6️⃣ Understanding Our First Java Program

Now let's examine the code instead of simply copying it.

```java
public class HelloJava {

    public static void main(String[] args) {

        System.out.println("Hello, Java!");

    }
}
```

---

## 🔍 Line 1

```java
public class HelloJava
```

### `public`

The class is accessible from outside its package subject to Java's access rules.

We will study access modifiers properly later.

### `class`

The `class` keyword declares a Java class.

### `HelloJava`

This is the name of our class.

Because this class is declared `public`, the source filename must be:

```text
HelloJava.java
```

---

# 7️⃣ Understanding `main()`

```java
public static void main(String[] args)
```

This is the standard entry point for launching this Java application.

Let's break it down.

### `public`

The method can be accessed by the Java launcher.

### `static`

The method belongs to the class, so Java can invoke it without first creating an object of `HelloJava`.

### `void`

The method does not return a value.

### `main`

The method name recognized as the application entry point.

### `String[] args`

An array of strings used to receive command-line arguments.

Example:

```bash
java HelloJava Samarth
```

Later we can access `"Samarth"` through `args`.

We will study arrays properly in a future module.

---

# 8️⃣ Understanding `System.out.println()`

Consider:

```java
System.out.println("Hello, Java!");
```

Breaking it down:

```text
System
   ↓
 out
   ↓
println()
```

### `System`

A built-in Java class.

### `out`

The standard output stream.

### `println()`

Prints the supplied value and then moves the cursor to a new line.

Example:

```java
System.out.println("Java");
System.out.println("Learning Journey");
```

Output:

```text
Java
Learning Journey
```

Compare it with:

```java
System.out.print("Java ");
System.out.print("Learning Journey");
```

Output:

```text
Java Learning Journey
```

So:

```text
println() → Print + New Line
print()   → Print without automatically adding a new line
```

---

# 9️⃣ Comments in Java

Comments help developers explain code.

The Java compiler ignores comments.

## Single-Line Comment

```java
// Display welcome message
System.out.println("Welcome");
```

## Multi-Line Comment

```java
/*
   This program demonstrates
   basic Java console output.
*/
```

## Documentation Comment

```java
/**
 * Demonstrates a basic Java application.
 */
```

Documentation comments are commonly associated with Java's documentation tooling.

---

# 🔟 Java Naming Conventions

Writing code that works is important.

Writing code that other developers can easily understand is also important.

### Classes — PascalCase

```text
HelloJava
StudentProfile
BankAccount
EmployeeManagement
```

### Variables — camelCase

```text
studentName
employeeSalary
accountBalance
```

### Methods — camelCase

```text
calculateSalary()
displayProfile()
withdrawMoney()
```

### Constants — UPPER_SNAKE_CASE

```text
MAX_USERS
MIN_BALANCE
DEFAULT_TIMEOUT
```

We will understand variables, methods and constants properly in upcoming modules.

---

# 1️⃣1️⃣ Program 1 — Hello Java

Create:

```text
HelloJava.java
```

```java
/**
 * My first Java program.
 */
public class HelloJava {

    public static void main(String[] args) {

        System.out.println("=================================");
        System.out.println("     JAVA LEARNING JOURNEY");
        System.out.println("=================================");
        System.out.println("Hello, Java!");
        System.out.println("Day 01: Java Fundamentals");
        System.out.println("Status: Learning Started 🚀");
        System.out.println("=================================");

    }
}
```

### Expected Output

```text
=================================
     JAVA LEARNING JOURNEY
=================================
Hello, Java!
Day 01: Java Fundamentals
Status: Learning Started 🚀
=================================
```

---

# 1️⃣2️⃣ Real-World Example — Employee Welcome System

Imagine a company has an internal employee application.

When an employee opens the application, the system displays basic information.

For now, we will use only today's concepts.

Create:

```text
EmployeeWelcome.java
```

```java
public class EmployeeWelcome {

    public static void main(String[] args) {

        System.out.println("====================================");
        System.out.println("       EMPLOYEE PORTAL");
        System.out.println("====================================");

        System.out.println("Employee Name : Samarth");
        System.out.println("Department    : Engineering");
        System.out.println("Role          : Java Developer");
        System.out.println("Status        : Active");

        System.out.println("====================================");
        System.out.println("Welcome to the organization!");
        System.out.println("====================================");

    }
}
```

### Output

```text
====================================
       EMPLOYEE PORTAL
====================================
Employee Name : Samarth
Department    : Engineering
Role          : Java Developer
Status        : Active
====================================
Welcome to the organization!
====================================
```

---

## 🤔 But Is This Good Real-World Code?

Not yet.

Notice that we wrote:

```java
System.out.println("Employee Name : Samarth");
System.out.println("Department    : Engineering");
System.out.println("Role          : Java Developer");
```

The employee information is **hard-coded**.

If another employee opens the system, we would have to change the source code.

That's obviously not how a real employee system should work.

Eventually we want something closer to:

```text
User Input / Database
        ↓
Employee Object
        ↓
Business Logic
        ↓
Employee Portal
```

But we haven't learned those concepts yet.

That's intentional.

As this repository progresses, we will improve this simple program using:

```text
Variables
   ↓
User Input
   ↓
Methods
   ↓
Classes & Objects
   ↓
Collections
   ↓
Exception Handling
   ↓
Database
   ↓
Backend Application
```

This allows us to see **how basic Java concepts evolve into real applications.**

---

# 🧩 Practice Challenge

Now create:

```text
StudentProfile.java
```

### Problem

A college wants a simple console program that displays a student's profile.

The output should look similar to:

```text
====================================
          STUDENT PROFILE
====================================
Name           : Samarth
Course         : MCA
Year           : 2
Learning       : Java
Status         : Active
====================================
```

### Rules

For Day 01:

- Use `public class`
- Use `main()`
- Use `System.out.println()`
- Add at least one comment
- Do **not** use variables yet
- Do **not** use `Scanner` yet

Those concepts are coming next.

---

# 🧠 Interview Corner

### Q1. What is Java?

Java is a high-level, class-based, object-oriented programming language whose compiled bytecode can run on a compatible JVM.

### Q2. What is JVM?

JVM stands for Java Virtual Machine. It loads and executes Java bytecode and provides runtime services such as memory management.

### Q3. What is bytecode?

Bytecode is the intermediate instruction format generated when Java source code is compiled.

### Q4. What is the difference between JDK, JRE and JVM?

```text
JDK → Development tools and Java runtime components
JRE → Java runtime environment
JVM → Executes Java bytecode
```

### Q5. Why is Java platform-independent?

Java source code is normally compiled into portable bytecode rather than directly into platform-specific machine instructions. A compatible JVM executes that bytecode on the target platform.

### Q6. What does `javac` do?

`javac` compiles Java source code into Java class files containing bytecode.

### Q7. What is the purpose of `main()`?

It provides the standard entry point used when launching a Java application in this form.

---

# ❌ Common Beginner Mistakes

### Wrong filename

```text
hello.java
```

while the code contains:

```java
public class HelloJava
```

Correct:

```text
HelloJava.java
```

---

### Running `.class` directly

❌ Wrong:

```bash
java HelloJava.class
```

✅ Correct:

```bash
java HelloJava
```

---

### Missing semicolon

❌

```java
System.out.println("Hello")
```

✅

```java
System.out.println("Hello");
```

---

### Incorrect capitalization

Java is case-sensitive.

These are different:

```text
System
system

String
string

HelloJava
hellojava
```

---

# 📁 Day 01 Structure

After completing today's exercises:

```text
01-Java-Fundamentals/
│
├── README.md
├── HelloJava.java
├── EmployeeWelcome.java
└── StudentProfile.java
```

---

# ✅ Day 01 Checklist

Before marking Day 01 complete, I should be able to explain:

- [ ] What Java is
- [ ] Why Java is platform-independent
- [ ] JDK
- [ ] JRE
- [ ] JVM
- [ ] Bytecode
- [ ] `.java` vs `.class`
- [ ] `javac`
- [ ] `java`
- [ ] `main()`
- [ ] `System.out.println()`
- [ ] Java comments
- [ ] Basic naming conventions

---

# 🏁 Day 01 Summary

Today I learned the basic architecture behind Java execution.

```text
Write Code
    ↓
.java File
    ↓
Compile with javac
    ↓
.class / Bytecode
    ↓
JVM
    ↓
Program Execution
```

The most important takeaway is:

> **Java source code is compiled into bytecode, and the JVM executes that bytecode on the target platform.**

---

## 🚀 Next

### Day 02 — Variables & Data Types

Next, the hard-coded employee information will become actual program data.

We will explore:

- Variables
- Primitive Data Types
- Reference Types
- Literals
- Type Conversion
- Type Casting
- Constants
- Memory basics
- Overflow and underflow
- Real-world employee/payroll example

---

<p align="center">
  <b>☕ Learn → Code → Understand → Practice → Build</b>
</p>
