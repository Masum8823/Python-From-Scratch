# 22. Python Fundamentals Practice Exercises

## 1. Introduction

এই ফাইলের উদ্দেশ্য হলো Python Fundamentals chapter-এ শেখা বিষয়গুলো নিজে code লিখে practice করা।

এই exercises-এ আমরা practice করব:

- Python syntax and program structure
- `print()` and `input()`
- Comments and variables
- Identifiers and naming conventions
- Literals and constants
- Expressions and operators
- Multiple assignment and unpacking
- Type conversion
- Basic debugging
- Clean and readable code

**Practice Rule:** প্রতিটি problem প্রথমে নিজে solve করার চেষ্টা করবে। সরাসরি solution copy না করে code কীভাবে কাজ করছে তা বোঝার চেষ্টা করবে।

## 2. How to Practice

প্রতিটি exercise-এর জন্য এই workflow অনুসরণ করো:

1. Problem statement ভালোভাবে পড়ো।
2. Input, process এবং expected output বোঝো।
3. প্রয়োজন হলে কাগজে calculation করো।
4. Python code লেখো।
5. Program execute করো।
6. Expected output-এর সঙ্গে actual output মিলিয়ে দেখো।
7. ভুল হলে error message পড়ে debugging করো।
8. Code-কে clean ও readable করার চেষ্টা করো।

প্রতিটি problem আলাদা `.py` file-এ রাখতে পারো।

উদাহরণ:

```text
02_Python_Fundamentals/
└── practice/
    ├── exercise_01_hello.py
    ├── exercise_02_personal_info.py
    ├── exercise_03_addition.py
    └── ...
```

## 3. Level 1 — Basic Output and Syntax

### Exercise 1: Hello Python

একটি program লেখো, যা নিচের output দেখাবে।

Expected output:

```text
Hello, Python!
I am learning Python programming.
```

Requirements:

- দুটি `print()` statement ব্যবহার করো।
- String-এর quotation mark সঠিকভাবে ব্যবহার করো।

### Exercise 2: Print Personal Information

নিজের নাম, department এবং university-এর নাম আলাদা লাইনে দেখাও।

Expected output-এর উদাহরণ:

```text
Name: Masum
Department: CSE
University: Northern University Bangladesh
```

Requirements:

- প্রতিটি line-এর জন্য meaningful output label ব্যবহার করো।
- Code readable রাখো।

### Exercise 3: Print a Calculation

নিচের calculation-গুলোর result `print()` দিয়ে দেখাও।

- `10 + 20`
- `50 - 15`
- `6 * 7`
- `100 / 4`

Expected output:

```text
30
35
42
25.0
```

### Exercise 4: Use Comments

একটি program লেখো, যেখানে:

- একটি single-line comment থাকবে।
- দুটি number variable-এ রাখা হবে।
- তাদের sum হিসাব করা হবে।
- Result output হিসেবে দেখানো হবে।

### Exercise 5: Print Multiple Values

নিচের value-গুলো একটি `print()` statement দিয়ে দেখাও:

```text
Python 3 Beginner
```

তারপর `sep` parameter ব্যবহার করে output দেখাও:

```text
Python-3-Beginner
```

## 4. Level 2 — Variables and Assignment

### Exercise 6: Store and Display Variables

নিচের তথ্যগুলো variable-এ রাখো:

- Name
- Age
- Department
- CGPA

তারপর প্রতিটি variable-এর value output হিসেবে দেখাও।

### Exercise 7: Variable Reassignment

একটি variable-এ প্রথমে `10` assign করো। এরপর একই variable-এ `25` assign করো।

প্রতিবার assignment-এর পরে value print করো।

Expected output:

```text
10
25
```

### Exercise 8: Swap Two Variables

দুটি variable-এর value swap করো।

Initial values:

```python
a = 10
b = 20
```

Expected output:

```text
Before swapping: 10 20
After swapping: 20 10
```

প্রথমে temporary variable ব্যবহার করে solve করো। এরপর Python-এর multiple assignment ব্যবহার করে solve করো।

### Exercise 9: Multiple Assignment

একটি statement ব্যবহার করে তিনটি variable-এ `10`, `20` এবং `30` assign করো।

তারপর তাদের value print করো।

### Exercise 10: Unpacking

নিচের tuple থেকে তিনটি value আলাদা variable-এ রাখো।

```python
student = ("Masum", 22, "CSE")
```

Expected output:

```text
Name: Masum
Age: 22
Department: CSE
```

### Exercise 11: Meaningful Variable Names

নিচের code-টি clean ও readable করে rewrite করো।

```python
a = 500
b = 4
c = a * b
print(c)
```

এমন variable name ব্যবহার করো, যা দেখলে বোঝা যায় প্রতিটি variable কী বোঝাচ্ছে।

## 5. Level 3 — Data Types and Type Conversion

### Exercise 12: Check Data Types

নিচের value-গুলো variable-এ assign করো এবং `type()` দিয়ে তাদের type দেখাও।

```python
age = 22
cgpa = 3.95
name = "Masum"
is_student = True
```

### Exercise 13: Integer Conversion

User-এর কাছ থেকে একটি integer input নাও এবং তার দ্বিগুণ দেখাও।

Example:

```text
Enter a number: 15
Double: 30
```

Hint: `input()` থেকে পাওয়া value-কে `int()` দিয়ে convert করতে হবে।

### Exercise 14: Float Conversion

User-এর কাছ থেকে দুটি decimal number input নাও এবং তাদের average বের করো।

Example:

```text
Enter first number: 10.5
Enter second number: 20.5
Average: 15.5
```

### Exercise 15: String Concatenation

দুটি string variable তৈরি করো:

```python
first_name = "Abdulla"
last_name = "Masum"
```

দুটি string একত্র করে পুরো নাম output হিসেবে দেখাও।

### Exercise 16: Investigate `input()`

নিচের code execute করো।

```python
value = input("Enter a value: ")

print(value)
print(type(value))
```

এবার `25`, `3.5` এবং `hello` input দিয়ে পরীক্ষা করো।

প্রতিটি ক্ষেত্রে `type()` কী দেখায় এবং কেন দেখায়, তা নিজের ভাষায় ব্যাখ্যা করো।

### Exercise 17: Boolean Investigation

নিচের code-এর output অনুমান করো, তারপর execute করে যাচাই করো।

```python
print(bool(0))
print(bool(1))
print(bool(""))
print(bool("Python"))
print(bool("False"))
```

প্রতিটি result-এর কারণ বোঝার চেষ্টা করো।

## 6. Level 4 — Operators and Expressions

### Exercise 18: Arithmetic Operations

দুটি integer input নিয়ে নিচের result-গুলো দেখাও:

- Sum
- Difference
- Product
- Division
- Floor division
- Remainder

Example:

```text
First number: 17
Second number: 5
Sum: 22
Difference: 12
Product: 85
Division: 3.4
Floor Division: 3
Remainder: 2
```

### Exercise 19: Calculate Rectangle Area

Rectangle-এর length এবং width input নিয়ে area বের করো।

Formula:

\[
\text{Area}=\text{Length}\times\text{Width}
\]

Example:

```text
Enter length: 8
Enter width: 5
Area: 40.0
```

### Exercise 20: Calculate Circle Area

Circle-এর radius input নিয়ে area হিসাব করো।

Formula:

\[
\text{Area}=\pi r^2
\]

Hint: `math` module থেকে `pi` ব্যবহার করতে পারো।

### Exercise 21: Temperature Conversion

Celsius temperature input নিয়ে Fahrenheit-এ convert করো।

Formula:

\[
F=\frac{9}{5}C+32
\]

Example:

```text
Enter Celsius: 25
Fahrenheit: 77.0
```

### Exercise 22: Calculate Average Marks

তিনটি subject-এর marks input নিয়ে average বের করো।

Formula:

\[
\text{Average}=\frac{m_1+m_2+m_3}{3}
\]

Result দুই decimal place পর্যন্ত দেখাও।

### Exercise 23: Operator Precedence

নিচের expression-গুলোর result আগে অনুমান করো, তারপর Python-এ পরীক্ষা করো।

```python
print(10 + 5 * 2)
print((10 + 5) * 2)
print(20 / 5 + 2)
print(2 ** 3 ** 2)
print(17 // 5)
print(17 % 5)
```

প্রতিটি expression-এ কোন operator আগে কাজ করেছে, তা ব্যাখ্যা করো।

### Exercise 24: Comparison Operators

দুটি number নিয়ে নিচের comparison-গুলো দেখাও:

- `==`
- `!=`
- `>`
- `<`
- `>=`
- `<=`

প্রতিটি result `True` অথবা `False` হবে।

### Exercise 25: Logical Operators

নিচের expression-গুলোর result অনুমান করো এবং যাচাই করো।

```python
print(True and True)
print(True and False)
print(True or False)
print(False or False)
print(not True)
print(not False)
```

তারপর নিজের মতো করে আরও পাঁচটি logical expression তৈরি করো।

### Exercise 26: Membership and Identity

নিচের code-এর output পরীক্ষা করো।

```python
numbers = [10, 20, 30]

print(20 in numbers)
print(40 in numbers)
print(10 not in numbers)
```

এরপর `is` ও `==`-এর পার্থক্য সম্পর্কে একটি ছোট note লেখো।

## 7. Level 5 — Input and Output

### Exercise 27: Personal Information Form

User-এর কাছ থেকে নিচের তথ্যগুলো নাও:

- Name
- Age
- Department
- University

তারপর একটি সুন্দর formatted output দেখাও।

Example:

```text
Enter name: Masum
Enter age: 22
Enter department: CSE
Enter university: NUB

--- Student Information ---
Name: Masum
Age: 22
Department: CSE
University: NUB
```

### Exercise 28: Simple Bill Calculator

User-এর কাছ থেকে product price এবং quantity input নাও।

Formula:

\[
\text{Total}=\text{Price}\times\text{Quantity}
\]

Output-এ product price, quantity এবং total bill দেখাও।

### Exercise 29: Currency Conversion

একটি program লেখো, যা বাংলাদেশি টাকা (BDT) input নিয়ে একটি user-provided exchange rate অনুযায়ী অন্য currency-তে convert করবে।

Formula:

\[
\text{Converted Amount}=\text{BDT Amount}\times\text{Exchange Rate}
\]

এই exercise-এ বাস্তব exchange rate প্রয়োজন নেই; user-এর দেওয়া rate ব্যবহার করো।

### Exercise 30: Formatted CGPA

User-এর কাছ থেকে CGPA input নাও এবং দুই decimal place পর্যন্ত দেখাও।

Example:

```text
Enter CGPA: 3.9567
CGPA: 3.96
```

## 8. Level 6 — Debugging Practice

প্রতিটি exercise-এ প্রথমে error বা bug শনাক্ত করো। এরপর code ঠিক করে execute করো।

### Exercise 31: Fix Syntax Error

```python
print("Welcome to Python"
```

### Exercise 32: Fix Variable Name Error

```python
student_name = "Masum"

print(student_nam)
```

### Exercise 33: Fix Type Error

```python
age = 22

print("Age: " + age)
```

### Exercise 34: Fix Logical Error

```python
length = 10
width = 5

area = length + width

print("Area:", area)
```

### Exercise 35: Fix Input Calculation

```python
a = input("Enter first number: ")
b = input("Enter second number: ")

print("Sum:", a + b)
```

User `10` এবং `20` দিলে expected result `30`। Code-টি সংশোধন করো।

### Exercise 36: Handle Division by Zero

দুটি number input নিয়ে প্রথম number-কে দ্বিতীয় number দিয়ে ভাগ করো।

দ্বিতীয় number `0` হলে division না করে উপযুক্ত message দেখাও।

### Exercise 37: Handle Invalid Integer Input

User-এর কাছ থেকে integer input নাও।

- Valid integer হলে number-এর square দেখাও।
- Invalid input হলে friendly error message দেখাও।

Hint: `try-except` ব্যবহার করো।

## 9. Level 7 — Clean Code Practice

### Exercise 38: Improve Readability

নিচের code-টিকে clean ও readable করে rewrite করো।

```python
n="Masum"
a=22
d="CSE"
print("Name:"+n+",Age:"+str(a)+",Department:"+d)
```

Requirements:

- Meaningful variable names ব্যবহার করো।
- Proper spacing রাখো।
- f-string ব্যবহার করো।

### Exercise 39: Create a Reusable Function

দুটি number-এর sum বের করার জন্য একটি function তৈরি করো।

Function-এর নাম হবে:

```python
calculate_sum()
```

দুটি number parameter হিসেবে নেবে এবং sum return করবে।

### Exercise 40: Separate Calculation and Output

তিনটি marks input নিয়ে average বের করো।

Requirements:

- `calculate_average()` নামে একটি function থাকবে।
- Function average return করবে।
- Main program result output হিসেবে দেখাবে।

### Exercise 41: Use Constants

একটি program লেখো, যেখানে:

```python
MAX_MARKS = 100
```

ব্যবহার করে obtained marks-এর percentage হিসাব করা হবে।

### Exercise 42: Improve Duplicate Code

একই calculation একাধিকবার না লিখে একটি function ব্যবহার করে তিনটি product-এর total price হিসাব করো।

## 10. Level 8 — Mini Projects

এই project-গুলো Chapter 02-এর concepts ব্যবহার করে তৈরি করা যাবে। Advanced topic জানার প্রয়োজন নেই।

### Mini Project 1: Student Information System

**Requirements:**

- Student-এর নাম, বয়স ও department input নিতে হবে।
- তিনটি subject-এর marks নিতে হবে।
- Average হিসাব করতে হবে।
- Percentage হিসাব করতে হবে।
- f-string ব্যবহার করে formatted report দেখাতে হবে।

**Expected output-এর উদাহরণ:**

```text
===== Student Report =====
Name: Masum
Age: 22
Department: CSE
Average Marks: 85.00
Percentage: 85.00%
```

এখানে percentage হিসাবের জন্য total marks 300 ধরে নাও, কারণ তিনটি subject-এর প্রতিটির সর্বোচ্চ marks 100।

### Mini Project 2: Simple Shopping Bill

**Requirements:**

- Product name input নিতে হবে।
- Unit price এবং quantity input নিতে হবে।
- Subtotal হিসাব করতে হবে।
- Discount percentage input নিতে হবে।
- Discount amount ও final total হিসাব করতে হবে।

Formula:

\[
\text{Subtotal}=\text{Unit Price}\times\text{Quantity}
\]

\[
\text{Discount Amount}=\frac{\text{Subtotal}\times\text{Discount Rate}}{100}
\]

\[
\text{Final Total}=\text{Subtotal}-\text{Discount Amount}
\]

### Mini Project 3: Personal Expense Calculator

**Requirements:**

- Food expense input নিতে হবে।
- Transport expense input নিতে হবে।
- Study expense input নিতে হবে।
- Total expense হিসাব করতে হবে।
- Budget input নিতে হবে।
- Budget থেকে কত টাকা বাকি আছে তা দেখাতে হবে।

Formula:

\[
\text{Total Expense}=\text{Food}+\text{Transport}+\text{Study}
\]

\[
\text{Remaining Budget}=\text{Budget}-\text{Total Expense}
\]

### Mini Project 4: Basic Calculator

**Requirements:**

- দুটি number input নিতে হবে।
- একটি arithmetic operator input নিতে হবে।
- `+`, `-`, `*`, `/` support করতে হবে।
- Invalid operator handle করতে হবে।
- Division by zero check করতে হবে।
- Output readable হতে হবে।

### Mini Project 5: Marks and Grade Report

**Requirements:**

- তিনটি subject-এর marks input নিতে হবে।
- Average হিসাব করতে হবে।
- একটি নির্দিষ্ট grading rule অনুযায়ী grade নির্ধারণ করতে হবে।
- Student-এর নাম ও final report দেখাতে হবে।

নিজের grading scale আগে define করে নাও। Grade নির্ধারণের জন্য পরবর্তী chapter-এর conditional statements ব্যবহার করা যাবে।

## 11. Challenge Exercises

এই problems একটু বেশি চিন্তা করে solve করার জন্য।

### Challenge 1: Swap Without a Temporary Variable

দুটি variable-এর value temporary variable ছাড়াই swap করো।

Hint: Python-এর multiple assignment ব্যবহার করো।

### Challenge 2: Extract Values from a Sequence

```python
numbers = (10, 20, 30, 40, 50)
```

Unpacking ব্যবহার করে প্রথম, দ্বিতীয় এবং বাকি value-গুলো আলাদা করো।

### Challenge 3: Calculate Time in Seconds

User-এর কাছ থেকে hours, minutes এবং seconds input নাও।

Formula:

\[
\text{Total Seconds}=(h\times3600)+(m\times60)+s
\]

মোট seconds হিসাব করো।

### Challenge 4: Reverse the Order of Assignment

একটি statement ব্যবহার করে নিচের variable-গুলোর value ঘুরিয়ে দাও।

```python
a = 10
b = 20
c = 30
```

Expected values:

```text
a = 30
b = 10
c = 20
```

### Challenge 5: Predict the Output

নিচের code-এর output execute করার আগে অনুমান করো।

```python
x = 10
y = x
x = 20

print(x)
print(y)
```

এরপর ব্যাখ্যা করো, `x` পরিবর্তন হওয়ার পর `y` কেন একই value ধরে রেখেছে।

## 12. Self-Assessment Checklist

Practice শেষ হলে নিচের checklist ব্যবহার করো।

- [ ] আমি `print()` ব্যবহার করে output দেখাতে পারি।
- [ ] আমি `input()` দিয়ে user input নিতে পারি।
- [ ] আমি বুঝি যে `input()` string return করে।
- [ ] আমি `int()` ও `float()` ব্যবহার করে conversion করতে পারি।
- [ ] আমি variable তৈরি ও reassignment করতে পারি।
- [ ] আমি multiple assignment ও unpacking বুঝি।
- [ ] আমি basic operators ও expressions ব্যবহার করতে পারি।
- [ ] আমি operator precedence-এর basic rules বুঝি।
- [ ] আমি syntax, runtime এবং logical error আলাদা করতে পারি।
- [ ] আমি error message পড়ে debugging শুরু করতে পারি।
- [ ] আমি meaningful variable name ও proper indentation ব্যবহার করি।
- [ ] আমি simple function ব্যবহার করে code reuse করতে পারি।
- [ ] আমি basic input validation ও exception handling করতে পারি।
- [ ] আমি কমপক্ষে একটি mini project নিজে তৈরি করতে পারি।

## 13. Practice Progress Tracker

প্রতিটি exercise শেষ হলে status চিহ্নিত করো।

| Status | Meaning |
|---|---|
| Not Started | এখনো শুরু করিনি |
| In Progress | চেষ্টা করছি |
| Completed | নিজে solve করেছি |
| Needs Review | solve করেছি, কিন্তু আবার practice প্রয়োজন |

নিজের progress একটি আলাদা `progress.md` ফাইলে রাখতে পারো। এতে কোন topic ভালোভাবে শিখেছ এবং কোন topic-এ আরও practice প্রয়োজন, তা সহজে বোঝা যাবে।

## 14. Chapter Review

এই chapter-এর practice exercises-এর মাধ্যমে তুমি Python-এর মৌলিক programming concepts পুনরায় ব্যবহার করবে।

সব exercise একদিনে শেষ করা বাধ্যতামূলক নয়। প্রতিদিন কয়েকটি problem solve করো এবং যেগুলোতে আটকে যাও, সেগুলোর concept আবার পড়ে চেষ্টা করো।

**Practice-এর মূল লক্ষ্য:** শুধু code চালানো নয়, বরং code কেন কাজ করে এবং কীভাবে কাজ করে তা বোঝা।

## 15. Next Topic

পরবর্তী ফাইল: [`23_Chapter_Review_and_Self_Assessment.md`](23_Chapter_Review_and_Self_Assessment.md)

সেখানে Python Fundamentals chapter-এর key concepts, important differences, revision questions এবং final self-assessment থাকবে।