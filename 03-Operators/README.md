

---

## 🎯 Objective

In Day 02, we learned how to store information using variables and data types.

Today, we will learn how to **work with those values** using Java operators.

For example:

```java
int salary = 50000;
int bonus = 5000;

int totalSalary = salary + bonus;
```

Here, the `+` operator performs an addition.

By the end of Day 03, I will understand:

- What is an operator?
- What is an operand?
- Arithmetic operators
- Assignment operators
- Relational operators
- Equality operators
- Logical operators
- Unary operators
- Increment and decrement
- Ternary operator
- Operator precedence
- Expressions
- Real-world calculations
- Banking transaction example

---

# 🧠 1. What is an Operator?

An **operator** is a symbol that tells Java to perform an operation on one or more values.

Example:

```java
int result = 10 + 20;
```

Here:

```text
10       → Operand
+        → Operator
20       → Operand
```

The result is:

```text
30
```

### Simple Idea

```text
Operand + Operator + Operand
        ↓
      Result
```

---

# 📚 2. Types of Operators in Java

Java provides several categories of operators:

```text
Operators
│
├── Arithmetic
├── Assignment
├── Relational
├── Equality
├── Logical
├── Unary
├── Ternary
└── Bitwise / Shift
```

In this module, we will focus mainly on the operators used in everyday Java application development.

---

# ➕ 3. Arithmetic Operators

Arithmetic operators are used to perform mathematical calculations.

| Operator | Meaning | Example |
|---|---|---|
| `+` | Addition | `10 + 5` |
| `-` | Subtraction | `10 - 5` |
| `*` | Multiplication | `10 * 5` |
| `/` | Division | `10 / 5` |
| `%` | Remainder | `10 % 3` |

---

## ➕ Addition

```java
int a = 10;
int b = 20;

int result = a + b;

System.out.println(result);
```

Output:

```text
30
```

---

## ➖ Subtraction

```java
int salary = 50000;
int deduction = 5000;

int remainingSalary = salary - deduction;

System.out.println(remainingSalary);
```

Output:

```text
45000
```

---

## ✖️ Multiplication

```java
int price = 100;
int quantity = 5;

int total = price * quantity;

System.out.println(total);
```

Output:

```text
500
```

---

## ➗ Division

```java
int totalMarks = 450;
int subjects = 5;

int average = totalMarks / subjects;

System.out.println(average);
```

Output:

```text
90
```

### ⚠️ Important

When both operands are integers, Java performs integer division.

Example:

```java
int result = 10 / 3;

System.out.println(result);
```

Output:

```text
3
```

The decimal portion is not retained.

If we want a decimal result:

```java
double result = 10.0 / 3;

System.out.println(result);
```

Output will be approximately:

```text
3.3333333333333335
```

---

# 🔢 4. Modulus Operator `%`

The `%` operator returns the **remainder** after division.

Example:

```java
int result = 10 % 3;

System.out.println(result);
```

Output:

```text
1
```

Because:

```text
10 ÷ 3

3 × 3 = 9

10 - 9 = 1
```

So:

```text
10 % 3 = 1
```

---

## 🌍 Real-World Example — Even or Odd

The modulus operator can help determine whether a number is even or odd.

```java
int number = 20;

int remainder = number % 2;

System.out.println(remainder);
```

Output:

```text
0
```

If the remainder is `0`, the number is even.

Example:

```text
20 % 2 = 0 → Even
21 % 2 = 1 → Odd
```

We will combine this concept with `if/else` when we learn conditional statements.

---

# 📝 5. Assignment Operator

The basic assignment operator is:

```java
=
```

Example:

```java
int age = 22;
```

This assigns `22` to the variable `age`.

---

# 🔄 6. Compound Assignment Operators

Java provides shorthand assignment operators.

| Operator | Equivalent |
|---|---|
| `+=` | `a = a + b` |
| `-=` | `a = a - b` |
| `*=` | `a = a * b` |
| `/=` | `a = a / b` |
| `%=` | `a = a % b` |

---

## Example: `+=`

Instead of:

```java
int salary = 40000;

salary = salary + 5000;
```

We can write:

```java
int salary = 40000;

salary += 5000;
```

Result:

```text
45000
```

---

## Example: `-=`

```java
int balance = 10000;

balance -= 2500;

System.out.println(balance);
```

Output:

```text
7500
```

---

## Example: `*=`

```java
int price = 100;

price *= 5;

System.out.println(price);
```

Output:

```text
500
```

---

# ⚖️ 7. Relational Operators

Relational operators compare values.

The result is a `boolean`:

```text
true
false
```

| Operator | Meaning |
|---|---|
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |

Example:

```java
int age = 22;

System.out.println(age > 18);
```

Output:

```text
true
```

Another example:

```java
int salary = 30000;

System.out.println(salary > 50000);
```

Output:

```text
false
```

---

# 🟰 8. Equality Operators

Java provides:

```text
==  → Equal to
!=  → Not equal to
```

Example:

```java
int age = 22;

System.out.println(age == 22);
```

Output:

```text
true
```

Example:

```java
int age = 22;

System.out.println(age != 18);
```

Output:

```text
true
```

---

# ⚠️ Important: `=` vs `==`

This is one of the most common beginner mistakes.

### `=`

Assignment:

```java
int age = 22;
```

Means:

> Store `22` in `age`.

### `==`

Comparison:

```java
age == 22
```

Means:

> Is `age` equal to `22`?

Remember:

```text
=   → Assignment
==  → Comparison
```

---

# 🧠 9. Logical Operators

Logical operators combine or modify boolean expressions.

| Operator | Meaning |
|---|---|
| `&&` | AND |
| `||` | OR |
| `!` | NOT |

---

# 🔗 10. AND Operator `&&`

`&&` returns `true` only when **both conditions are true**.

Example:

```java
int age = 25;
boolean hasLicense = true;

boolean canDrive = age >= 18 && hasLicense;

System.out.println(canDrive);
```

Output:

```text
true
```

Think:

```text
Condition 1 → true
Condition 2 → true
              ↓
             AND
              ↓
            true
```

If either condition is false:

```text
true && false → false
false && true → false
false && false → false
```

---

# 🔀 11. OR Operator `||`

`||` returns `true` when **at least one condition is true**.

Example:

```java
boolean hasEmail = true;
boolean hasPhone = false;

boolean canContact = hasEmail || hasPhone;

System.out.println(canContact);
```

Output:

```text
true
```

Because at least one condition is true.

```text
true || true   → true
true || false  → true
false || true  → true
false || false → false
```

---

# ❗ 12. NOT Operator `!`

The `!` operator reverses a boolean value.

Example:

```java
boolean active = true;

System.out.println(!active);
```

Output:

```text
false
```

Another example:

```java
boolean loggedIn = false;

System.out.println(!loggedIn);
```

Output:

```text
true
```

---

# 🔢 13. Unary Operators

Unary operators work with a single operand.

Common unary operators include:

```text
+
-
++
--
!
```

Example:

```java
int number = 10;

number++;

System.out.println(number);
```

Output:

```text
11
```

---

# ➕ 14. Increment Operator `++`

The increment operator increases a value by `1`.

```java
int count = 10;

count++;

System.out.println(count);
```

Output:

```text
11
```

This is equivalent to:

```java
count = count + 1;
```

or:

```java
count += 1;
```

---

# ➖ 15. Decrement Operator `--`

The decrement operator decreases a value by `1`.

```java
int count = 10;

count--;

System.out.println(count);
```

Output:

```text
9
```

Equivalent to:

```java
count = count - 1;
```

---

# ⚠️ 16. Prefix vs Postfix

This is an important Java concept.

Consider:

```java
int number = 10;

int result = ++number;
```

Here `number` is increased first.

```text
number → 11
result → 11
```

This is **prefix increment**.

---

Now:

```java
int number = 10;

int result = number++;
```

Here the current value is used first, then `number` is increased.

```text
result → 10
number → 11
```

This is **postfix increment**.

---

## Comparison

### Prefix

```java
int number = 10;

int result = ++number;
```

Result:

```text
number = 11
result = 11
```

### Postfix

```java
int number = 10;

int result = number++;
```

Result:

```text
number = 11
result = 10
```

---

# ❓ 17. Ternary Operator

The ternary operator is a compact way to choose between two expressions based on a condition.

Syntax:

```java
condition ? valueIfTrue : valueIfFalse;
```

Example:

```java
int age = 20;

String result = age >= 18 ? "Eligible" : "Not Eligible";

System.out.println(result);
```

Output:

```text
Eligible
```

Conceptually:

```text
age >= 18 ?
    ↓
 ┌──┴──┐
true  false
 ↓      ↓
Eligible Not Eligible
```

We'll compare this with `if/else` when we learn conditional statements.

---

# 🧮 18. Operator Precedence

When an expression contains multiple operators, Java follows precedence rules.

Example:

```java
int result = 10 + 5 * 2;
```

The multiplication happens before addition.

Therefore:

```text
5 × 2 = 10

10 + 10 = 20
```

Output:

```text
20
```

Not:

```text
30
```

---

# 🟢 19. Using Parentheses

Parentheses can make the intended order explicit.

```java
int result = (10 + 5) * 2;

System.out.println(result);
```

Output:

```text
30
```

Compare:

```java
10 + 5 * 2
```

Result:

```text
20
```

and:

```java
(10 + 5) * 2
```

Result:

```text
30
```

### Best Practice

When an expression could be confusing, use parentheses to make your intention clear.

---

# 🧑‍💻 20. Complete Arithmetic Example

### ArithmeticDemo.java

```java
public class ArithmeticDemo {

    public static void main(String[] args) {

        int a = 20;
        int b = 6;

        System.out.println("Addition       : " + (a + b));
        System.out.println("Subtraction    : " + (a - b));
        System.out.println("Multiplication : " + (a * b));
        System.out.println("Division       : " + (a / b));
        System.out.println("Remainder      : " + (a % b));
    }
}
```

Output:

```text
Addition       : 26
Subtraction    : 14
Multiplication : 120
Division       : 3
Remainder      : 2
```

---

# 👨‍💼 21. Real-World Problem — Employee Salary Calculator

Imagine a company wants to calculate an employee's annual compensation.

### Given:

```text
Monthly Salary = ₹50,000
Annual Bonus   = 10%
```

We can calculate:

```java
double monthlySalary = 50000;

double annualSalary = monthlySalary * 12;
double bonus = annualSalary * 0.10;
double totalCompensation = annualSalary + bonus;
```

Complete program:

### SalaryCalculator.java

```java
public class SalaryCalculator {

    public static void main(String[] args) {

        double monthlySalary = 50000;

        double annualSalary = monthlySalary * 12;
        double bonus = annualSalary * 0.10;
        double totalCompensation = annualSalary + bonus;

        System.out.println("======================================");
        System.out.println("        EMPLOYEE SALARY REPORT");
        System.out.println("======================================");

        System.out.println("Monthly Salary     : ₹" + monthlySalary);
        System.out.println("Annual Salary      : ₹" + annualSalary);
        System.out.println("Annual Bonus       : ₹" + bonus);
        System.out.println("Total Compensation : ₹" + totalCompensation);

        System.out.println("======================================");
    }
}
```

Output:

```text
======================================
        EMPLOYEE SALARY REPORT
======================================
Monthly Salary     : ₹50000.0
Annual Salary      : ₹600000.0
Annual Bonus       : ₹60000.0
Total Compensation : ₹660000.0
======================================
```

---

# 🏦 22. Real-World Problem — Banking Transaction

Suppose a bank account has:

```text
Initial Balance = ₹50,000
Deposit         = ₹10,000
Withdrawal      = ₹5,000
```

We can calculate the balance using assignment operators.

### BankingTransaction.java

```java
public class BankingTransaction {

    public static void main(String[] args) {

        double balance = 50000;

        double deposit = 10000;
        balance += deposit;

        double withdrawal = 5000;
        balance -= withdrawal;

        System.out.println("================================");
        System.out.println("       BANK ACCOUNT");
        System.out.println("================================");

        System.out.println("Initial Balance : ₹50000");
        System.out.println("Deposit         : ₹" + deposit);
        System.out.println("Withdrawal      : ₹" + withdrawal);
        System.out.println("Final Balance   : ₹" + balance);

        System.out.println("================================");
    }
}
```

Output:

```text
================================
       BANK ACCOUNT
================================
Initial Balance : ₹50000
Deposit         : ₹10000
Withdrawal      : ₹5000
Final Balance   : ₹55000
================================
```

This is still a simplified example. A real banking application would need validation, transaction rules, persistence, concurrency control, and proper monetary representation.

---

# 🔐 23. Real-World Example — Login Eligibility

Suppose an application should allow access only when:

```text
User is active
AND
User has valid credentials
```

We can represent this using `&&`.

```java
boolean accountActive = true;
boolean credentialsValid = true;

boolean loginAllowed = accountActive && credentialsValid;

System.out.println("Login Allowed: " + loginAllowed);
```

Output:

```text
Login Allowed: true
```

This is a simple example of how logical operators are used in application logic.

---

# 🧪 24. Complete Operators Example

### OperatorsDemo.java

```java
public class OperatorsDemo {

    public static void main(String[] args) {

        int a = 20;
        int b = 5;

        // Arithmetic
        System.out.println("Addition: " + (a + b));
        System.out.println("Subtraction: " + (a - b));
        System.out.println("Multiplication: " + (a * b));
        System.out.println("Division: " + (a / b));
        System.out.println("Remainder: " + (a % b));

        // Relational
        System.out.println("a > b: " + (a > b));
        System.out.println("a < b: " + (a < b));

        // Equality
        System.out.println("a == b: " + (a == b));
        System.out.println("a != b: " + (a != b));

        // Logical
        boolean condition1 = true;
        boolean condition2 = false;

        System.out.println("condition1 && condition2: " + (condition1 && condition2));
        System.out.println("condition1 || condition2: " + (condition1 || condition2));
        System.out.println("!condition1: " + (!condition1));

        // Assignment
        int value = 10;
        value += 5;

        System.out.println("After += : " + value);
    }
}
```

---

# 🧠 25. Operator Quick Reference

| Category | Operators |
|---|---|
| Arithmetic | `+ - * / %` |
| Assignment | `= += -= *= /= %=` |
| Relational | `> < >= <=` |
| Equality | `== !=` |
| Logical | `&& || !` |
| Unary | `+ - ++ -- !` |
| Ternary | `? :` |

---

# ⚠️ 26. Common Beginner Mistakes

## Mistake 1 — Confusing `=` and `==`

Wrong concept:

```java
age = 18;
```

This assigns `18`.

Comparison:

```java
age == 18
```

This checks whether `age` equals `18`.

---

## Mistake 2 — Integer Division

```java
int result = 5 / 2;

System.out.println(result);
```

Output:

```text
2
```

Not:

```text
2.5
```

For a decimal result:

```java
double result = 5.0 / 2;

System.out.println(result);
```

Output:

```text
2.5
```

---

## Mistake 3 — Incorrect `++` Understanding

These are different:

```java
++number
```

and:

```java
number++
```

The difference becomes important when the expression's value is used immediately.

---

## Mistake 4 — Ignoring Operator Precedence

```java
int result = 10 + 5 * 2;
```

Result:

```text
20
```

Use parentheses when you want a different order:

```java
int result = (10 + 5) * 2;
```

Result:

```text
30
```

---

# 🧩 27. Practice Challenge 1 — Shopping Bill

Create:

```text
ShoppingBill.java
```

A customer purchases:

```text
Laptop      = ₹50,000
Mouse       = ₹1,000
Keyboard    = ₹2,000
```

Calculate:

```text
Subtotal
Discount
Final Amount
```

Assume:

```text
Discount = 10%
```

Expected output:

```text
======================================
          SHOPPING BILL
======================================
Laptop       : ₹50000
Mouse        : ₹1000
Keyboard     : ₹2000
--------------------------------------
Subtotal     : ₹53000
Discount     : ₹5300
Final Amount : ₹47700
======================================
```

Use arithmetic operators.

---

# 🧩 28. Practice Challenge 2 — Student Marks

Create:

```text
MarksCalculator.java
```

A student receives marks in five subjects:

```text
Java       = 85
Database   = 90
Python     = 80
Networks   = 75
Web        = 88
```

Calculate:

```text
Total Marks
Average Marks
```

Use:

```text
+
/
```

Expected output should contain:

```text
Total Marks   : ...
Average Marks : ...
```

---

# 🧩 29. Practice Challenge 3 — Bank Balance

Create:

```text
BankBalance.java
```

Initial balance:

```text
₹25,000
```

Transactions:

```text
Deposit    = ₹5,000
Withdrawal = ₹3,000
```

Calculate the final balance using:

```text
+=
-=
```

---

# 🎤 30. Interview Questions

### Q1. What is an operator?

An operator is a symbol that tells Java to perform an operation on one or more operands.

### Q2. What is the difference between `=` and `==`?

```text
=   → Assignment
==  → Equality comparison
```

### Q3. What does `%` do?

It returns the remainder of a division.

Example:

```java
10 % 3
```

Result:

```text
1
```

### Q4. What is the difference between `&&` and `||`?

```text
&& → Both conditions must be true
|| → At least one condition must be true
```

### Q5. What does `!` do?

It reverses a boolean value.

```java
!true
```

becomes:

```text
false
```

### Q6. What is the difference between `++x` and `x++`?

Both increase `x` by one, but they differ in when the incremented value is produced within the surrounding expression.

### Q7. What is the ternary operator?

It is a conditional operator using the syntax:

```java
condition ? valueIfTrue : valueIfFalse;
```

### Q8. What is operator precedence?

Operator precedence determines the order in which operators are evaluated within an expression.

### Q9. What is integer division?

When both operands are integers, division produces an integer result with the fractional part discarded.

Example:

```java
10 / 3
```

Result:

```text
3
```

---

# 📁 31. Day 03 Repository Structure

```text
03-Operators/
│
├── README.md
├── ArithmeticDemo.java
├── OperatorsDemo.java
├── SalaryCalculator.java
├── BankingTransaction.java
├── ShoppingBill.java
└── MarksCalculator.java
```

---

# ✅ 32. Day 03 Checklist

Before completing Day 03, I should be able to explain:

- [ ] What is an operator?
- [ ] What is an operand?
- [ ] Arithmetic operators
- [ ] Assignment operators
- [ ] Compound assignment
- [ ] Relational operators
- [ ] Equality operators
- [ ] `=`
- [ ] `==`
- [ ] `!=`
- [ ] Logical AND `&&`
- [ ] Logical OR `||`
- [ ] Logical NOT `!`
- [ ] Increment `++`
- [ ] Decrement `--`
- [ ] Prefix increment
- [ ] Postfix increment
- [ ] Ternary operator
- [ ] Operator precedence
- [ ] Integer division
- [ ] Modulus operator

---

# 🏁 33. Day 03 Summary

Today we learned how Java performs operations on data.

The basic flow is:

```text
Variables
    ↓
Values
    ↓
Operators
    ↓
Expressions
    ↓
Result
```

For example:

```java
double monthlySalary = 50000;

double annualSalary = monthlySalary * 12;
double bonus = annualSalary * 0.10;
double total = annualSalary + bonus;
```

We have now moved from simply **storing data** to actually **processing data**.

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

# 🚀 Next — Day 04

## Input & Output

Coming next:

- `Scanner`
- User input
- `System.out`
- `System.in`
- Reading integers
- Reading decimals
- Reading strings
- Input validation basics
- Building interactive programs
- Real-world employee data entry
- Calculator application
- Practice problems

---

<p align="center">
  ☕ Learn → Code → Understand → Practice → Build
</p>
