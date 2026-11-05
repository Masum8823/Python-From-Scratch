# 27. Chapter Practice and Self-Assessment

## 1. Chapter Overview

এই chapter-এ আমরা Python-এর Input, Output এবং String Formatting নিয়ে কাজ করেছি।

এই final practice file-এর উদ্দেশ্য হলো আগের topics কতটা বুঝতে পেরেছ, তা যাচাই করা।

এই ফাইলে থাকবে:

1. Quick revision
2. Important syntax
3. Output prediction
4. Find the error
5. Fill in the blanks
6. Programming exercises
7. Mini project
8. Answer key
9. Final self-assessment checklist

**Practice rule:** প্রথমে নিজে উত্তর দেওয়ার চেষ্টা করবে। তারপর Answer Key-এর সঙ্গে মিলিয়ে দেখবে।

---

## 2. Quick Revision

| Topic | কী কাজে লাগে | Example |
|---|---|---|
| `input()` | User-এর কাছ থেকে input নিতে | `name = input()` |
| `print()` | Output দেখাতে | `print("Hello")` |
| `int()` | Integer conversion | `int("25")` |
| `float()` | Floating-point conversion | `float("3.5")` |
| `str()` | String conversion | `str(100)` |
| `split()` | String-কে ভাগ করতে | `"10 20".split()` |
| `sep` | Output-এর object-গুলোর মাঝে separator দিতে | `print(1, 2, sep="-")` |
| `end` | `print()`-এর শেষে কী থাকবে নির্ধারণ করতে | `print("Hi", end="!")` |
| f-string | String-এর মধ্যে value বসাতে | `f"Age: {age}"` |
| `:.2f` | দুই decimal places দেখাতে | `f"{3.14159:.2f}"` |
| `:,.2f` | Comma ও দুই decimal places | `f"{1234.5:,.2f}"` |
| `:.2%` | Ratio-কে percentage হিসেবে দেখাতে | `f"{0.85:.2%}"` |
| `try-except` | নির্দিষ্ট error handle করতে | `try: ... except ValueError: ...` |
| `while` | শর্ত অনুযায়ী বারবার কাজ করতে | `while True:` |

## 3. Important Syntax Revision

### 3.1 Basic Input and Output

```python
name = input("Enter your name: ")
print(f"Hello, {name}!")
```

### 3.2 Numeric Input

```python
age = int(input("Enter age: "))
price = float(input("Enter price: "))
```

মনে রাখবে: `input()` string return করে। Numeric calculation করতে প্রয়োজন অনুযায়ী conversion করতে হয়।

### 3.3 Multiple Inputs

```python
a, b = map(int, input("Enter two numbers: ").split())

print(a + b)
```

Input:

```text
10 20
```

Output:

```text
30
```

### 3.4 Custom Separator

```python
print("Python", "Java", "C++", sep=" | ")
```

Output:

```text
Python | Java | C++
```

### 3.5 Custom Ending

```python
print("Hello", end=" ")
print("World")
```

Output:

```text
Hello World
```

### 3.6 Number Formatting

```python
price = 12500.5
percentage = 0.875

print(f"Price: Tk {price:,.2f}")
print(f"Percentage: {percentage:.2%}")
```

Output:

```text
Price: Tk 12,500.50
Percentage: 87.50%
```

---

## 4. Output Prediction Exercises

প্রতিটি code-এর output নিজে বের করো।

### Question 1

```python
print("Python", "Programming")
```

### Question 2

```python
print("A", "B", "C", sep="-")
```

### Question 3

```python
print("Hello", end=" ")
print("Python")
```

### Question 4

```python
a = "10"
b = "20"

print(a + b)
```

### Question 5

```python
a = 10
b = 20

print(a + b)
print(str(a) + str(b))
```

### Question 6

```python
print(f"{25 / 4:.2f}")
```

### Question 7

```python
print(f"{0.756:.1%}")
```

### Question 8

```python
print(f"{1234567:,.2f}")
```

### Question 9

```python
numbers = input().split()
print(numbers)
```

Input:

```text
10 20 30
```

### Question 10

```python
a, b, c = map(int, input().split())
print(a + b + c)
```

Input:

```text
5 10 15
```

### Question 11

```python
print("Hi\nPython")
```

### Question 12

```python
print("A", "B", sep="", end="!")
```

### Question 13

```python
value = int("25")
print(value * 2)
```

### Question 14

```python
print("Python" * 3)
```

### Question 15

```python
marks = 425
total = 500

percentage = marks / total
print(f"{percentage:.2%}")
```

---

## 5. Find the Error

প্রতিটি code-এ কী সমস্যা আছে, তা চিহ্নিত করো। তারপর সঠিকভাবে লেখার চেষ্টা করো।

### Question 1: String and Integer

```python
age = 22
print("Age: " + age)
```

### Question 2: Incorrect Conversion

```python
price = int(input("Enter price: "))
```

User যদি `12.50` input দেয়, কী হবে?

### Question 3: Wrong Number of Values

```python
a, b, c = input().split()
```

Input:

```text
10 20
```

### Question 4: Division by Zero

```python
a = 10
b = 0

print(a / b)
```

### Question 5: Incorrect Percentage Formatting

```python
percentage = 85
print(f"{percentage:.2%}")
```

এখানে `percentage` ইতোমধ্যে percent হিসেবে দেওয়া হয়েছে। Output সঠিকভাবে `85.00%` দেখানোর জন্য কী পরিবর্তন করতে হবে?

### Question 6: Invalid Numeric Input

```python
age = int(input("Enter age: "))
```

User যদি `twenty` দেয়, কী ধরনের error হতে পারে?

### Question 7: Missing f-string

```python
name = "Masum"
print("Hello, {name}")
```

### Question 8: Incorrect Separator

```python
a, b = map(int, input().split(","))
```

Input:

```text
10 20
```

### Question 9: Wrong `end` Usage

```python
print("Hello", end=" ")
print("World", end=" ")
print("Python")
```

Output-এ line break কোথায় হবে?

### Question 10: Empty Input

```python
numbers = list(map(int, input().split()))
average = sum(numbers) / len(numbers)
```

User কিছু না লিখে Enter চাপলে কী সমস্যা হতে পারে?

---

## 6. Fill in the Blanks

সঠিক function, operator বা formatting specification দিয়ে ফাঁকা জায়গা পূরণ করো।

### Question 1

```python
age = ______(input("Enter age: "))
```

Age-কে integer হিসেবে নিতে হবে।

### Question 2

```python
print("A", "B", "C", ______="-")
```

Output: `A-B-C`

### Question 3

```python
print("Hello", ______=" ")
```

পরবর্তী `print()` একই line-এ শুরু করতে হবে।

### Question 4

```python
price = 1250.5
print(f"Tk {price:____}")
```

Output: `Tk 1,250.50`

### Question 5

```python
marks = 85
total = 100

percentage = marks / total
print(f"{percentage:____}")
```

Output: `85.00%`

### Question 6

```python
a, b = map(______, input().split())
```

দুটি input-কে integer করতে হবে।

### Question 7

```python
parts = "10 20 30".______()
```

String-কে whitespace অনুযায়ী ভাগ করতে হবে।

### Question 8

```python
print(f"{3.14159:.____f}")
```

Output: `3.14`

### Question 9

```python
try:
    number = int(input())
except ______:
    print("Invalid number")
```

Invalid integer conversion handle করতে হবে।

### Question 10

```python
if divisor ______ 0:
    print(dividend / divisor)
```

Division করার আগে divisor zero নয়, তা যাচাই করতে হবে।

---

## 7. Programming Exercises

এবার নিজে complete program লেখার চেষ্টা করো।

### Exercise 1: Greeting Program

User-এর নাম input নিয়ে নিচের মতো output দেখাও।

```text
Enter your name: Masum
Welcome, Masum!
Welcome to Python Programming.
```

Requirements:
- `input()` ব্যবহার করতে হবে।
- f-string দিয়ে greeting দেখাতে হবে।

### Exercise 2: Two-Number Calculator

দুটি integer input নিয়ে sum, difference, product এবং division দেখাও।

Requirements:
- Division-এর আগে zero check করতে হবে।
- Division result দুই decimal places-এ দেখাতে হবে।

### Exercise 3: Personal Information

Name, age, department এবং university input নিয়ে formatted output তৈরি করো।

Requirements:
- Age integer হিসেবে নিতে হবে।
- Output-এ প্রতিটি তথ্য আলাদা line-এ দেখাতে হবে।

### Exercise 4: Marks and Percentage

Obtained marks ও total marks input নিয়ে percentage বের করো।

Requirements:
- Total marks শূন্যের বেশি হতে হবে।
- Obtained marks negative হতে পারবে না।
- Obtained marks total marks-এর বেশি হতে পারবে না।
- Percentage দুই decimal places-এ দেখাতে হবে।

### Exercise 5: Product Bill

Product name, price এবং quantity input নিয়ে subtotal দেখাও।

Requirements:
- Price ও quantity negative হতে পারবে না।
- Bill-এ currency formatting ব্যবহার করতে হবে।
- Subtotal দুই decimal places-এ দেখাতে হবে।

### Exercise 6: Temperature Conversion

Celsius input নিয়ে Fahrenheit-এ convert করো।

Formula:

\[
F=\frac{9}{5}C+32
\]

### Exercise 7: Average Calculator

এক লাইনে তিনটি number input নিয়ে average বের করো।

Example input:

```text
80 90 70
```

Expected output:

```text
Average: 80.00
```

### Exercise 8: Positive Number Validation

User-এর কাছ থেকে positive number নিতে থাকো। Invalid text অথবা non-positive number দিলে আবার input নাও।

Requirements:
- `while` loop ব্যবহার করতে হবে।
- `try-except ValueError` ব্যবহার করতে হবে।
- Valid input পেলে loop বন্ধ করতে হবে।

### Exercise 9: Formatted Receipt

দুটি product-এর নাম, price ও quantity নিয়ে আলাদা subtotal এবং final bill দেখাও।

Requirements:
- f-string ব্যবহার করতে হবে।
- প্রতিটি subtotal দুই decimal places-এ দেখাতে হবে।
- Final bill-এ comma separator ব্যবহার করতে হবে।

### Exercise 10: Student Report

তিনটি subject-এর marks নিয়ে total, average এবং percentage দেখাও।

Requirements:
- প্রতিটি subject-এর marks 0 থেকে 100-এর মধ্যে হতে হবে।
- Total marks হবে 300-এর মধ্যে।
- Average দুই decimal places-এ দেখাতে হবে।
- Percentage `:.2%` ব্যবহার করে দেখাতে হবে।

---

## 8. Answer Key — Output Prediction

### Answer 1

```text
Python Programming
```

Default `sep` হলো একটি space।

### Answer 2

```text
A-B-C
```

### Answer 3

```text
Hello World
```

প্রথম `print()`-এর শেষে newline-এর বদলে space রয়েছে।

### Answer 4

```text
1020
```

দুটি string concatenate হয়েছে।

### Answer 5

```text
30
1020
```

প্রথম line-এ numeric addition, দ্বিতীয় line-এ string concatenation হয়েছে।

### Answer 6

```text
6.25
```

### Answer 7

```text
75.6%
```

### Answer 8

```text
1,234,567.00
```

### Answer 9

```text
['10', '20', '30']
```

`split()` string-এর list তৈরি করেছে।

### Answer 10

```text
30
```

### Answer 11

```text
Hi
Python
```

`\n` newline তৈরি করেছে।

### Answer 12

```text
AB!
```

### Answer 13

```text
50
```

### Answer 14

```text
PythonPythonPython
```

### Answer 15

```text
85.00%
```

---

## 9. Answer Key — Find the Error

### Answer 1

সমস্যা: String-এর সঙ্গে integer সরাসরি `+` দিয়ে concatenate করা যায় না।

Correct code:

```python
age = 22
print(f"Age: {age}")
```

অথবা:

```python
print("Age: " + str(age))
```

### Answer 2

`int("12.50")` দিলে `ValueError` হবে, কারণ string-টি integer text নয়।

Correct code:

```python
price = float(input("Enter price: "))
```

### Answer 3

দুটি value পাওয়া যাচ্ছে, কিন্তু তিনটি variable-এ assign করার চেষ্টা করা হয়েছে। এতে `ValueError` হবে।

Correct code:

```python
a, b = input().split()
```

### Answer 4

`b` শূন্য হওয়ায় `ZeroDivisionError` হবে।

Correct code:

```python
a = 10
b = 0

if b != 0:
    print(a / b)
else:
    print("Cannot divide by zero.")
```

### Answer 5

সঠিক code:

```python
percentage = 85
print(f"{percentage:.2f}%")
```

Output:

```text
85.00%
```

### Answer 6

`int("twenty")` দিলে `ValueError` হবে।

Correct code:

```python
try:
    age = int(input("Enter age: "))
    print(age)
except ValueError:
    print("Please enter a valid integer.")
```

### Answer 7

সঠিক code:

```python
name = "Masum"
print(f"Hello, {name}")
```

### Answer 8

Code-টি comma separator আশা করছে, কিন্তু input-এ space দেওয়া হয়েছে। ফলে পুরো input একটি অংশ হিসেবে থাকবে এবং `int("10 20")`-এ `ValueError` হবে।

Correct code:

```python
a, b = map(int, input().split())
```

### Answer 9

Output:

```text
Hello World Python
```

সব output একই line-এ থাকবে। শেষের `print()`-এ default `end="\n"` রয়েছে, তাই এরপর newline হবে।

### Answer 10

Empty input থেকে empty list তৈরি হবে। এরপর `len(numbers)` শূন্য হওয়ায় `ZeroDivisionError` হবে।

Correct code:

```python
numbers = list(map(int, input().split()))

if numbers:
    average = sum(numbers) / len(numbers)
    print(f"Average: {average:.2f}")
else:
    print("Please enter at least one number.")
```

---

## 10. Answer Key — Fill in the Blanks

| Question | Answer |
|---|---|
| 1 | `int` |
| 2 | `sep` |
| 3 | `end` |
| 4 | `,.2f` |
| 5 | `.2%` |
| 6 | `int` |
| 7 | `split` |
| 8 | `2` |
| 9 | `ValueError` |
| 10 | `!=` |

---

## 11. Sample Solutions — Programming Exercises

### Solution 1: Greeting Program

```python
name = input("Enter your name: ")

print(f"Welcome, {name}!")
print("Welcome to Python Programming.")
```

### Solution 2: Two-Number Calculator

```python
a = int(input("Enter first integer: "))
b = int(input("Enter second integer: "))

print(f"Sum: {a + b}")
print(f"Difference: {a - b}")
print(f"Product: {a * b}")

if b != 0:
    print(f"Division: {a / b:.2f}")
else:
    print("Cannot divide by zero.")
```

### Solution 3: Personal Information

```python
name = input("Enter name: ")
age = int(input("Enter age: "))
department = input("Enter department: ")
university = input("Enter university: ")

print("\n--- Personal Information ---")
print(f"Name: {name}")
print(f"Age: {age}")
print(f"Department: {department}")
print(f"University: {university}")
```

### Solution 4: Marks and Percentage

```python
obtained = float(input("Enter obtained marks: "))
total = float(input("Enter total marks: "))

if total > 0 and 0 <= obtained <= total:
    percentage = obtained / total
    print(f"Percentage: {percentage:.2%}")
else:
    print("Invalid marks.")
```

### Solution 5: Product Bill

```python
name = input("Enter product name: ")
price = float(input("Enter unit price: "))
quantity = int(input("Enter quantity: "))

if price >= 0 and quantity >= 0:
    subtotal = price * quantity

    print(f"Product: {name}")
    print(f"Unit Price: Tk {price:,.2f}")
    print(f"Quantity: {quantity}")
    print(f"Subtotal: Tk {subtotal:,.2f}")
else:
    print("Price and quantity cannot be negative.")
```

### Solution 6: Temperature Conversion

```python
celsius = float(input("Enter Celsius: "))

fahrenheit = (celsius * 9 / 5) + 32

print(f"Fahrenheit: {fahrenheit:.2f} F")
```

### Solution 7: Average Calculator

```python
a, b, c = map(float, input("Enter three numbers: ").split())

average = (a + b + c) / 3

print(f"Average: {average:.2f}")
```

### Solution 8: Positive Number Validation

```python
while True:
    try:
        number = float(input("Enter a positive number: "))

        if number > 0:
            print(f"Accepted: {number:g}")
            break

        print("Number must be positive.")

    except ValueError:
        print("Invalid number.")
```

### Solution 9: Formatted Receipt

```python
total_bill = 0

for i in range(2):
    name = input("Enter product name: ")
    price = float(input("Enter unit price: "))
    quantity = int(input("Enter quantity: "))

    if price < 0 or quantity < 0:
        print("Invalid price or quantity.")
        continue

    subtotal = price * quantity
    total_bill += subtotal

    print(f"{name}: Tk {subtotal:,.2f}")

print("-" * 30)
print(f"Final Bill: Tk {total_bill:,.2f}")
```

### Solution 10: Student Report

```python
marks = []

for i in range(3):
    mark = float(input(f"Enter subject {i + 1} marks: "))
    marks.append(mark)

if any(mark < 0 or mark > 100 for mark in marks):
    print("Each mark must be between 0 and 100.")
else:
    total = sum(marks)
    average = total / len(marks)
    percentage = total / 300

    print(f"Total: {total:g}/300")
    print(f"Average: {average:.2f}")
    print(f"Percentage: {percentage:.2%}")
```

**Note:** এই sample solutions-গুলো basic practice-এর জন্য। Real-world program-এ numeric conversion-এর error, empty input এবং business-specific rules প্রয়োজন অনুযায়ী handle করতে হবে।

---

## 12. Mini Project: Student Result Slip

### Project Requirements

একটি program তৈরি করো যা:

1. Student-এর name ও ID নেবে।
2. তিনটি subject-এর marks নেবে।
3. প্রতিটি mark 0–100 range-এর মধ্যে আছে কি না যাচাই করবে।
4. Total, average ও percentage হিসাব করবে।
5. সুন্দরভাবে formatted result slip দেখাবে।

### Sample Solution

```python
name = input("Enter student name: ")
student_id = input("Enter student ID: ")

marks = []

for i in range(3):
    mark = float(input(f"Enter subject {i + 1} marks: "))
    marks.append(mark)

if any(mark < 0 or mark > 100 for mark in marks):
    print("Invalid marks. Each mark must be between 0 and 100.")
else:
    total = sum(marks)
    average = total / len(marks)
    percentage = total / 300

    print("\n" + "=" * 36)
    print(f"{'STUDENT RESULT SLIP':^36}")
    print("=" * 36)
    print(f"{'Name:':<15}{name}")
    print(f"{'Student ID:':<15}{student_id}")
    print("-" * 36)

    for i, mark in enumerate(marks, start=1):
        print(f"{'Subject ' + str(i) + ':':<15}{mark:g}")

    print("-" * 36)
    print(f"{'Total Marks:':<15}{total:g}/300")
    print(f"{'Average:':<15}{average:.2f}")
    print(f"{'Percentage:':<15}{percentage:.2%}")
    print("=" * 36)
```

### Project Extension Tasks

নিজের skill আরও বাড়াতে নিচের features যোগ করার চেষ্টা করো:

- `try-except` দিয়ে invalid marks input handle করা।
- Subject সংখ্যা user-এর কাছ থেকে নেওয়া।
- Result-এর সঙ্গে grade দেখানো।
- একই report-এ date দেখানো।
- Output আরও সুন্দরভাবে align করা।

এই extensions বাধ্যতামূলক নয়; এগুলো নিজের practice-এর জন্য।

---

## 13. Final Self-Assessment

প্রতিটি statement পড়ে নিজের skill যাচাই করো।

### Basic Skills

- [ ] `input()` এবং `print()` ব্যবহার করতে পারি।
- [ ] String ও numeric input-এর পার্থক্য বুঝি।
- [ ] `int()`, `float()` ও `str()` ব্যবহার করতে পারি।
- [ ] একাধিক value print করতে পারি।
- [ ] `sep` ও `end`-এর পার্থক্য বুঝি।

### String Formatting

- [ ] Escape sequence যেমন `\n` ও `\t` বুঝি।
- [ ] f-string ব্যবহার করতে পারি।
- [ ] `.2f` দিয়ে decimal places নিয়ন্ত্রণ করতে পারি।
- [ ] `:,.2f` দিয়ে বড় number format করতে পারি।
- [ ] `.2%` দিয়ে ratio-কে percentage হিসেবে দেখাতে পারি।
- [ ] Alignment ও padding ব্যবহার করতে পারি।

### Validation and Problem Solving

- [ ] `split()` দিয়ে multiple input নিতে পারি।
- [ ] `map()` দিয়ে input conversion করতে পারি।
- [ ] Invalid conversion-এর জন্য `ValueError` handle করতে পারি।
- [ ] Zero division এড়াতে পারি।
- [ ] Input-এর valid range check করতে পারি।
- [ ] ছোট input-output program নিজে তৈরি করতে পারি।

### Practical Programming

- [ ] Calculator তৈরি করতে পারি।
- [ ] Percentage ও average calculator তৈরি করতে পারি।
- [ ] Shopping bill তৈরি করতে পারি।
- [ ] Formatted report তৈরি করতে পারি।
- [ ] Validation-সহ ছোট program তৈরি করতে পারি।

## 14. Final Review

Chapter 05 শেষ করার পর তোমার মূল লক্ষ্য হওয়া উচিত—শুধু syntax মনে রাখা নয়, বরং user input থেকে শুরু করে calculation, validation এবং formatted output পর্যন্ত একটি complete program তৈরি করতে পারা।

নিজে অন্তত তিনটি program কোনো solution না দেখে লিখে দেখো:

1. Calculator
2. Student Result Slip
3. Shopping Receipt

এগুলো স্বাধীনভাবে তৈরি করতে পারলে Chapter 05-এর গুরুত্বপূর্ণ concepts ভালোভাবে practice করা হবে।

**Chapter 05 Complete:** Input, Output and String Formatting.

**Next Chapter:** `06_Conditional_Statements/README.md` — Python-এ decision making, `if`, `elif`, `else`, nested conditions এবং conditional logic শেখা হবে।