 

> Learning how Java stores, represents, and works with different types of data.

---
## 🎯 Objective
In Day 01, we learned the basic structure of Java and how a Java program is compiled and executed.

Today, we learn how Java programs **store and manage information using variables and data types**.

### By the end of Day 02, I will understand:

- What is a variable?
- Declaration, initialization, and assignment
- Primitive data types
- Reference data types
- `byte`, `short`, `int`, and `long`
- `float` and `double`
- `char` and `boolean`
- `String`
- Constants using `final`
- Type conversion
- Type casting
- Widening and narrowing conversion
- Integer overflow
- Choosing appropriate data types

---


# 🧠 1. What is a Variable?
A **variable** is a named location used by a program to store a value.

For example, an employee management system may need to store:

```text
Employee Name → Samarth
Age           → 22
Salary        → 45000.50
Grade         → A
Active        → true
```

In Java:

```java
String employeeName = "Samarth";
int age = 22;
double salary = 45000.50;
char grade = 'A';
boolean active = true;
```

A variable can be understood as:

```text
Data Type + Variable Name + Value
```

Example:

```java
int age = 22;
```

```text
int  → Data Type
age  → Variable Name
22   → Value
```

---

# 💡 2. Why Do We Need Variables?

Without variables, information has to be hard-coded.

Example:

```java
System.out.println("Employee Name: Samarth");
System.out.println("Age: 22");
System.out.println("Salary: 45000");
```

This becomes difficult to maintain when an application has many employees.

Instead, we can store the information:

```java
String employeeName = "Samarth";
int age = 22;
double salary = 45000;
```

Then use the variables:

```java
System.out.println("Employee Name: " + employeeName);
System.out.println("Age: " + age);
System.out.println("Salary: " + salary);
```

### Why this is better

Variables allow programs to:

- Store information
- Reuse information
- Modify values
- Perform calculations
- Build dynamic applications

---

# 📝 3. Variable Declaration

Declaration means telling Java the **data type and name** of a variable.

```java
int age;
```

Here:

```text
int → Data Type
age → Variable Name
```

At this point, the variable has been declared.

---

# 🟢 4. Variable Initialization

Initialization means giving a variable its initial value.

```java
int age = 22;
```

This performs declaration and initialization together.

```text
int age;
    ↓
Declaration

int age = 22;
    ↓
Declaration + Initialization
```

---

# 🔄 5. Assignment

A variable can receive a new value after it has been declared.

```java
int age = 22;

age = 23;
```

Now:

```text
age → 23
```

Example:

```java
int salary = 40000;

salary = 50000;

System.out.println(salary);
```

Output:

```text
50000
```

---

# 🧱 6. Java Data Types

Java data types can broadly be divided into two categories:

```text
Java Data Types
│
├── Primitive Data Types
│
└── Reference Data Types
```

---

# 🟢 7. Primitive Data Types

Java has **8 primitive data types**.

| Data Type | Size | Example | Common Usage |
|---|---:|---|---|
| `byte` | 8-bit | `100` | Small integer values |
| `short` | 16-bit | `30000` | Small-to-medium integer values |
| `int` | 32-bit | `500000` | General integer values |
| `long` | 64-bit | `9000000000L` | Large integer values |
| `float` | 32-bit | `10.5f` | Single-precision decimal values |
| `double` | 64-bit | `10.5` | Double-precision decimal values |
| `char` | 16-bit | `'A'` | Single UTF-16 code unit |
| `boolean` | JVM-dependent | `true` | Logical true/false values |

---

# 🔹 8. byte

`byte` is an 8-bit signed integer.

Range:

```text
-128 to 127
```

Example:

```java
byte temperature = 35;

System.out.println(temperature);
```

Output:

```text
35
```

It can be useful when working with small integer ranges.

---

# 🔹 9. short

`short` is a 16-bit signed integer.

Range:

```text
-32,768 to 32,767
```

Example:

```java
short population = 30000;

System.out.println(population);
```

In ordinary business applications, `int` is generally used more often.

---

# 🔹 10. int

`int` is a 32-bit signed integer.

It is the common default for general whole-number calculations.

Example:

```java
int age = 22;
int employeeId = 1001;
int quantity = 50;
```

### Example Program

```java
public class IntegerExample {

    public static void main(String[] args) {

        int age = 22;
        int employeeId = 1001;

        System.out.println("Age: " + age);
        System.out.println("Employee ID: " + employeeId);
    }
}
```

### Output

```text
Age: 22
Employee ID: 1001
```

---

# 🔹 11. long

`long` is a 64-bit signed integer.

It is useful when a value may exceed the range of `int`.

Example:

```java
long population = 1400000000L;
```

The `L` indicates that the literal is a `long`.

Another example:

```java
long distance = 9876543210L;
```

---

# 🔹 12. float

`float` represents a single-precision floating-point value.

Example:

```java
float percentage = 85.5f;
```

The `f` is used because decimal literals such as `85.5` are `double` by default.

Example:

```java
float temperature = 36.5f;

System.out.println(temperature);
```

Output:

```text
36.5
```

---

# 🔹 13. double

`double` represents a double-precision floating-point value.

Example:

```java
double salary = 45000.50;
double productPrice = 1499.99;
double distance = 125.75;
```

Example:

```java
double productPrice = 1499.99;

System.out.println("Product Price: " + productPrice);
```

Output:

```text
Product Price: 1499.99
```

> For financial calculations requiring exact decimal behavior, Java applications commonly use `BigDecimal` rather than `double`.

---

# 🔹 14. char

`char` represents a single UTF-16 code unit.

Use **single quotes**.

```java
char grade = 'A';
```

Example:

```java
char grade = 'A';

System.out.println("Grade: " + grade);
```

Output:

```text
Grade: A
```

### Important Difference

```java
'A'    // char
"A"    // String
```

---

# 🔹 15. boolean

`boolean` represents a logical value:

```text
true
false
```

Example:

```java
boolean isLoggedIn = true;
boolean isPaymentSuccessful = false;
boolean isAccountBlocked = false;
```

Example:

```java
boolean isEmployeeActive = true;

System.out.println("Employee Active: " + isEmployeeActive);
```

Output:

```text
Employee Active: true
```

Boolean values become especially useful when we learn conditional statements.

---

# 🔵 16. String

`String` is **not a primitive data type**.

It is a Java class used to represent text.

Example:

```java
String employeeName = "Samarth";
String city = "Pune";
String course = "MCA";
```

Example:

```java
String employeeName = "Samarth";

System.out.println("Employee Name: " + employeeName);
```

Output:

```text
Employee Name: Samarth
```

---

# 📊 17. Primitive vs Reference Types

A simplified view:

```text
Java Data Types
│
├── Primitive
│   ├── byte
│   ├── short
│   ├── int
│   ├── long
│   ├── float
│   ├── double
│   ├── char
│   └── boolean
│
└── Reference
    ├── String
    ├── Arrays
    ├── Classes
    ├── Objects
    └── Interfaces
```

Reference types will become clearer when we study **classes and objects**.

---

# 💻 18. Complete Variables Example

### VariablesDemo.java

```java
public class VariablesDemo {

    public static void main(String[] args) {

        String employeeName = "Samarth";
        int age = 22;
        double salary = 45000.50;
        char grade = 'A';
        boolean active = true;

        System.out.println("Employee Name : " + employeeName);
        System.out.println("Age           : " + age);
        System.out.println("Salary        : " + salary);
        System.out.println("Grade         : " + grade);
        System.out.println("Active        : " + active);
    }
}
```

### Output

```text
Employee Name : Samarth
Age           : 22
Salary        : 45000.5
Grade         : A
Active        : true
```

---

# 🔒 19. Constants Using final

A variable declared using `final` cannot be reassigned after initialization.

Example:

```java
final int MAX_LOGIN_ATTEMPTS = 3;
```

This is valid:

```java
final int MAX_LOGIN_ATTEMPTS = 3;

System.out.println(MAX_LOGIN_ATTEMPTS);
```

This is not valid:

```java
MAX_LOGIN_ATTEMPTS = 5;
```

It produces a compilation error because the variable is `final`.

Common naming style:

```text
MAX_USERS
MAX_LOGIN_ATTEMPTS
DEFAULT_TIMEOUT
```

---

# 🔄 20. Type Conversion

Type conversion means converting a value from one compatible type to another.

Two important concepts are:

```text
Type Conversion
│
├── Widening Conversion
│
└── Narrowing Conversion
```

---

# 🟢 21. Widening Conversion

Widening conversion moves a value to a compatible numeric type that can represent the source value.

Example:

```java
int marks = 85;

double convertedMarks = marks;

System.out.println(convertedMarks);
```

Output:

```text
85.0
```

No explicit cast is required.

---

# 🔻 22. Narrowing Conversion

Narrowing conversion moves a value to a type that may not represent all of the original value.

An explicit cast is normally required.

Example:

```java
double price = 999.99;

int convertedPrice = (int) price;

System.out.println(convertedPrice);
```

Output:

```text
999
```

The decimal portion is discarded.

It is **not rounded**.

---

# ⚠️ 23. Data Loss During Casting

Example:

```java
double salary = 45000.99;

int salaryValue = (int) salary;

System.out.println(salaryValue);
```

Output:

```text
45000
```

The `.99` is lost.

Therefore, narrowing conversions should be performed carefully.

---

# 💥 24. Integer Overflow

Every integer type has a limited range.

The range of `int` is:

```text
-2,147,483,648
to
 2,147,483,647
```

Consider:

```java
int number = 2147483647;

number = number + 1;

System.out.println(number);
```

Output:

```text
-2147483648
```

The calculation exceeds the maximum value representable by `int`, resulting in integer overflow behavior.

---

# 🏢 25. Real-World Example — Employee Payroll

Imagine an organization needs to store employee payroll information.

We need:

```text
Employee ID
Employee Name
Age
Monthly Salary
Performance Grade
Active Status
```

We can select:

```text
Employee ID      → int
Employee Name    → String
Age              → int
Monthly Salary   → double
Performance      → char
Active Status    → boolean
```

### EmployeePayroll.java

```java
public class EmployeePayroll {

    public static void main(String[] args) {

        int employeeId = 1001;
        String employeeName = "Samarth";
        int age = 22;
        double monthlySalary = 45000.50;
        char performanceGrade = 'A';
        boolean active = true;

        System.out.println("======================================");
        System.out.println("          EMPLOYEE PAYROLL");
        System.out.println("======================================");

        System.out.println("Employee ID       : " + employeeId);
        System.out.println("Employee Name     : " + employeeName);
        System.out.println("Age               : " + age);
        System.out.println("Monthly Salary    : ₹" + monthlySalary);
        System.out.println("Performance Grade : " + performanceGrade);
        System.out.println("Active            : " + active);

        System.out.println("======================================");
    }
}
```

### Output

```text
======================================
          EMPLOYEE PAYROLL
======================================
Employee ID       : 1001
Employee Name     : Samarth
Age               : 22
Monthly Salary    : ₹45000.5
Performance Grade : A
Active            : true
======================================
```

---

# 💰 26. Extending the Payroll Example

We can use the salary variable to calculate annual salary and bonus.

```java
double annualSalary = monthlySalary * 12;
double bonus = annualSalary * 0.10;
double totalCompensation = annualSalary + bonus;

System.out.println("Annual Salary      : ₹" + annualSalary);
System.out.println("Annual Bonus       : ₹" + bonus);
System.out.println("Total Compensation : ₹" + totalCompensation);
```

This gives us a preview of **Day 03 — Operators**.

---

# 🧪 27. Data Types Example

### DataTypesDemo.java

```java
public class DataTypesDemo {

    public static void main(String[] args) {

        byte smallNumber = 100;
        short mediumNumber = 30000;
        int number = 500000;
        long largeNumber = 9000000000L;

        float temperature = 36.5f;
        double distance = 125.75;

        char grade = 'A';
        boolean passed = true;

        System.out.println("byte    : " + smallNumber);
        System.out.println("short   : " + mediumNumber);
        System.out.println("int     : " + number);
        System.out.println("long    : " + largeNumber);
        System.out.println("float   : " + temperature);
        System.out.println("double  : " + distance);
        System.out.println("char    : " + grade);
        System.out.println("boolean : " + passed);
    }
}
```

---

# 🔄 28. Type Casting Example

### TypeCastingDemo.java

```java
public class TypeCastingDemo {

    public static void main(String[] args) {

        // Widening conversion
        int marks = 85;
        double convertedMarks = marks;

        System.out.println("Original marks  : " + marks);
        System.out.println("Converted marks : " + convertedMarks);

        // Narrowing conversion
        double price = 999.99;
        int convertedPrice = (int) price;

        System.out.println("Original price  : " + price);
        System.out.println("Converted price : " + convertedPrice);
    }
}
```

### Output

```text
Original marks  : 85
Converted marks : 85.0
Original price  : 999.99
Converted price : 999
```

---

# 🎯 29. Practice Challenge — Student Result

Create:

```text
StudentResult.java
```

A college wants to store information about a student.

The program should contain:

```text
Student Name
Roll Number
Age
Percentage
Grade
Passed/Failed
```

Expected output:

```text
======================================
          STUDENT RESULT
======================================
Name       : Samarth
Roll No    : 101
Age        : 22
Percentage : 87.5
Grade      : A
Passed     : true
======================================
```

### Requirements

- Use appropriate Java data types.
- Use variables.
- Use `System.out.println()`.
- Add comments.
- Do not use `Scanner` yet.
- Do not use `if/else` yet.

---

# 🎤 30. Interview Questions

### Q1. What is a variable?

A variable is a named storage location used to hold a value during program execution.

### Q2. How many primitive data types are available in Java?

Java has eight:

```text
byte
short
int
long
float
double
char
boolean
```

### Q3. Is String a primitive data type?

No. `String` is a class and therefore a reference type.

### Q4. What is the difference between int and long?

`int` is a 32-bit signed integer, while `long` is a 64-bit signed integer.

### Q5. Why do we use L with a long literal?

Example:

```java
long population = 9000000000L;
```

`L` explicitly makes the integer literal a `long`.

### Q6. Why do we use f with float values?

Decimal literals are `double` by default.

```java
float value = 10.5f;
```

### Q7. What is type casting?

Type casting is explicitly converting a value to another compatible type.

Example:

```java
int result = (int) 99.99;
```

### Q8. What is widening conversion?

It is a numeric conversion to a type that can represent the source value without requiring an explicit cast in the applicable conversion.

### Q9. What is narrowing conversion?

It is a conversion to a narrower numeric type that may lose information and generally requires an explicit cast.

### Q10. What does final do?

For a variable, `final` prevents reassignment after initialization.

---

# ❌ 31. Common Beginner Mistakes

### Mistake 1 — Using double quotes for char

Wrong:

```java
char grade = "A";
```

Correct:

```java
char grade = 'A';
```

---

### Mistake 2 — Forgetting L

Wrong:

```java
long population = 9000000000;
```

Correct:

```java
long population = 9000000000L;
```

---

### Mistake 3 — Forgetting f

Wrong:

```java
float percentage = 85.5;
```

Correct:

```java
float percentage = 85.5f;
```

---

### Mistake 4 — Thinking String is primitive

```java
String name = "Samarth";
```

`String` is a reference type.

---

### Mistake 5 — Ignoring data loss

```java
double price = 999.99;
int value = (int) price;
```

Result:

```text
999
```

The fractional part is discarded.

---

# 📁 32. Day 02 Repository Structure

```text
02-Variables-and-Data-Types/
│
├── README.md
├── VariablesDemo.java
├── DataTypesDemo.java
├── TypeCastingDemo.java
├── EmployeePayroll.java
└── StudentResult.java
```

---

# ✅ 33. Day 02 Checklist

Before completing Day 02, I should be able to explain:

- [ ] What is a variable?
- [ ] Declaration
- [ ] Initialization
- [ ] Assignment
- [ ] Primitive data types
- [ ] Reference data types
- [ ] byte
- [ ] short
- [ ] int
- [ ] long
- [ ] float
- [ ] double
- [ ] char
- [ ] boolean
- [ ] String
- [ ] final
- [ ] Type conversion
- [ ] Widening conversion
- [ ] Narrowing conversion
- [ ] Type casting
- [ ] Integer overflow

---

# 🏁 34. Day 02 Summary

Today I learned how Java programs store and work with data.

The basic idea is:

```text
Data
 ↓
Data Type
 ↓
Variable
 ↓
Value
 ↓
Program Logic
```

Example:

```java
String employeeName = "Samarth";
int age = 22;
double salary = 45000.50;
char grade = 'A';
boolean active = true;
```

Choosing the correct data type helps a program represent information appropriately.

---

# 📈 Learning Progress

```text
Day 01 → Java Fundamentals
             ↓
Day 02 → Variables & Data Types
             ↓
Day 03 → Operators
             ↓
Day 04 → Input & Output
             ↓
Day 05 → Conditional Statements
```

---

# 🚀 Next — Day 03

## Operators

Coming next:

- Arithmetic operators
- Relational operators
- Logical operators
- Assignment operators
- Unary operators
- Increment and decrement
- Ternary operator
- Operator precedence
- Expressions
- Salary calculation
- Banking transaction example
- Practice problems

---

<p align="center">
  ☕ Learn → Code → Understand → Practice → Build
</p>
