# 23. Chapter Review and Self-Assessment

## 1. Chapter Overview

এই chapter-এ আমরা Python programming-এর মৌলিক বিষয়গুলো শিখেছি। এগুলো পরবর্তী chapter-এর conditional statements, loops, functions, data structures এবং advanced Python শেখার ভিত্তি হিসেবে কাজ করবে।

এই chapter-এর প্রধান topics:

1. Introduction to Python Programming
2. Python Syntax and Program Structure
3. First Python Program
4. `print()` and Comments
5. Statements and Expressions
6. Keywords and Identifiers
7. Variables and Assignment
8. Literals and Constants
9. Expressions and Operators
10. Operator Precedence
11. Indentation and Whitespace
12. Basic Input and Output
13. Errors and Debugging
14. Clean and Readable Code
15. Practice Exercises

## 2. Important Concepts Revision

### 2.1 Python Programming

**Programming** হলো computer-কে নির্দিষ্ট কাজ করানোর জন্য instruction লেখা।

Python একটি high-level, general-purpose programming language। এর syntax তুলনামূলকভাবে সহজ এবং এটি automation, web development, data analysis, machine learning-সহ বিভিন্ন ক্ষেত্রে ব্যবহৃত হয়।

### 2.2 Syntax

**Syntax** হলো programming language-এ code লেখার নিয়ম।

উদাহরণ:

```python
print("Hello Python")
```

এটি valid Python syntax।

কিন্তু নিচের code-এ closing parenthesis নেই:

```python
print("Hello Python"
```

তাই এটি `SyntaxError` তৈরি করবে।

### 2.3 Variable

Variable হলো একটি নাম, যার মাধ্যমে program-এ কোনো value বা object-কে access করা যায়।

```python
name = "Masum"
age = 22
cgpa = 3.95
```

Python dynamically typed। অর্থাৎ variable-এর type আলাদা করে declaration করার প্রয়োজন হয় না।

### 2.4 Assignment

Assignment operator `=` ব্যবহার করে variable-এ value assign করা হয়।

```python
age = 20
age = 22
```

শেষ assignment-এর পরে `age`-এর value হবে `22`।

### 2.5 Data Types

এই chapter-এ আমরা কয়েকটি common built-in data type ব্যবহার করেছি।

| Data Type | Example |
|---|---|
| `int` | `25` |
| `float` | `3.14` |
| `str` | `"Python"` |
| `bool` | `True` |
| `NoneType` | `None` |
| `list` | `[10, 20, 30]` |
| `tuple` | `(10, 20, 30)` |
| `dict` | `{"name": "Masum"}` |
| `set` | `{10, 20, 30}` |

### 2.6 Input and Output

- `input()` user-এর কাছ থেকে text গ্রহণ করে।
- `print()` output দেখায়।
- `int()` integer conversion করে।
- `float()` floating-point conversion করে।
- `type()` value-এর type দেখায়।

Example:

```python
age = int(input("Enter your age: "))

print(f"Your age is {age}.")
```

### 2.7 Errors and Debugging

প্রধান তিন ধরনের সমস্যা:

| Type | Explanation |
|---|---|
| Syntax Error | Code-এর syntax সঠিক নয় |
| Runtime Error | Execution-এর সময় exception ঘটে |
| Logical Error | Program চলে, কিন্তু result ভুল হয় |

**Debugging** হলো সমস্যা শনাক্ত করে তার কারণ খুঁজে বের করা এবং ঠিক করার প্রক্রিয়া।

### 2.8 Clean Code

Clean code সহজে পড়া, বোঝা এবং maintain করা যায়।

গুরুত্বপূর্ণ practices:

- Meaningful variable name ব্যবহার করা।
- Proper indentation রাখা।
- Consistent spacing বজায় রাখা।
- প্রয়োজনীয় comment লেখা।
- অপ্রয়োজনীয় code duplication এড়িয়ে চলা।
- Function-এর দায়িত্ব পরিষ্কার রাখা।
- অপ্রয়োজনীয় complexity এড়িয়ে চলা।

## 3. Important Differences

### 3.1 Statement vs Expression

| Statement | Expression |
|---|---|
| একটি instruction বা action প্রকাশ করে | একটি value produce করে |
| উদাহরণ: `x = 10` | উদাহরণ: `5 + 3` |
| সব statement সরাসরি value produce করে না | Expression evaluate করে value পাওয়া যায় |

Example:

```python
x = 10
result = x + 5
```

এখানে `x = 10` একটি assignment statement এবং `x + 5` একটি expression।

### 3.2 Variable vs Constant

| Variable | Constant |
|---|---|
| Value পরিবর্তন করা যেতে পারে | Fixed value বোঝাতে ব্যবহার করা হয় |
| `age = 22` | `MAX_MARKS = 100` |
| সাধারণত `snake_case` | Convention অনুযায়ী `UPPER_SNAKE_CASE` |

Python-এ uppercase নাম নিজে থেকে value-কে immutable করে না। এটি একটি naming convention।

### 3.3 `=` vs `==`

| Operator | Purpose | Example |
|---|---|---|
| `=` | Assignment | `age = 20` |
| `==` | Equality comparison | `age == 20` |

`=` variable-এ value assign করে। `==` দুটি value সমান কি না যাচাই করে।

### 3.4 `input()` vs `print()`

| `input()` | `print()` |
|---|---|
| User-এর কাছ থেকে input নেয় | Output দেখায় |
| সাধারণত `str` return করে | Defaultভাবে `None` return করে |
| উদাহরণ: `name = input()` | উদাহরণ: `print(name)` |

### 3.5 `int()` vs `float()`

| `int()` | `float()` |
|---|---|
| Integer value তৈরি করে | Floating-point value তৈরি করে |
| `int("25")` → `25` | `float("2.5")` → `2.5` |
| `int("hello")` করলে `ValueError` হয় | `float("hello")` করলে `ValueError` হয় |

### 3.6 Syntax Error vs Logical Error

| Syntax Error | Logical Error |
|---|---|
| Code-এর syntax নিয়ম ভাঙা হয় | Code-এর logic ভুল হয় |
| Program execute হওয়ার আগেই সাধারণত শনাক্ত হয় | Program চললেও ভুল result দিতে পারে |
| উদাহরণ: bracket বাদ পড়া | উদাহরণ: area বের করতে `+` ব্যবহার করা |

### 3.7 `is` vs `==`

| `is` | `==` |
|---|---|
| দুটি reference একই object নির্দেশ করছে কি না যাচাই করে | দুটি object-এর value সমান কি না যাচাই করে |
| Identity comparison | Equality comparison |

Example:

```python
a = [1, 2]
b = [1, 2]

print(a == b)
print(a is b)
```

Output:

```text
True
False
```

দুটি list-এর content সমান হলেও তারা আলাদা object।

### 3.8 Multiple Assignment vs Unpacking

**Multiple assignment:**

```python
a, b = 10, 20
```

**Unpacking:**

```python
student = ("Masum", 22, "CSE")

name, age, department = student
```

Multiple assignment একাধিক variable-এ একসঙ্গে value assign করতে পারে। Unpacking কোনো iterable-এর element-গুলোকে একাধিক variable-এ ভাগ করে assign করে।

## 4. Important Python Rules

নিচের নিয়মগুলো মনে রাখবে:

1. Python case-sensitive।
2. `name` এবং `Name` আলাদা identifier।
3. Variable name number দিয়ে শুরু হতে পারে না।
4. Variable name-এ space ব্যবহার করা যায় না।
5. Keyword-কে সাধারণ variable name হিসেবে ব্যবহার করা যায় না।
6. Python-এ indentation code block নির্ধারণ করে।
7. সাধারণত indentation level-এ চারটি space ব্যবহার করা হয়।
8. `input()` string return করে।
9. Numeric calculation-এর আগে প্রয়োজন অনুযায়ী type conversion করতে হয়।
10. `=` assignment এবং `==` comparison-এর জন্য ব্যবহৃত হয়।
11. `#` দিয়ে single-line comment লেখা যায়।
12. `print()`-এর default separator হলো space।
13. `print()`-এর default ending হলো newline।
14. `**` exponentiation-এর জন্য ব্যবহৃত হয়।
15. `//` floor division এবং `%` remainder-এর জন্য ব্যবহৃত হয়।
16. `and`, `or`, `not` logical operator।
17. `in` এবং `not in` membership operator।
18. `is` এবং `is not` identity operator।
19. Error message পড়া debugging-এর গুরুত্বপূর্ণ অংশ।
20. Code শুধু সঠিক হলেই নয়, readable হওয়াও গুরুত্বপূর্ণ।

## 5. Predict the Output

নিজে code execute করার আগে প্রতিটি output অনুমান করো।

### Question 1

```python
x = 10
y = 20

print(x + y)
print(x * y)
```

### Question 2

```python
x = 10
x = 25

print(x)
```

### Question 3

```python
print(10 + 5 * 2)
print((10 + 5) * 2)
```

### Question 4

```python
print("Python", "Programming", sep="-")
```

### Question 5

```python
print("Hello", end=" ")
print("World")
```

### Question 6

```python
name = "Masum"
age = 22

print(f"{name} is {age} years old.")
```

### Question 7

```python
a = 10
b = a

a = 30

print(a)
print(b)
```

### Question 8

```python
print(bool(0))
print(bool(1))
print(bool(""))
print(bool("False"))
```

### Question 9

```python
numbers = [10, 20, 30]

print(20 in numbers)
print(40 not in numbers)
```

### Question 10

```python
a, b = 5, 10
a, b = b, a

print(a, b)
```

## 6. Find and Fix the Errors

প্রতিটি code-এর সমস্যা শনাক্ত করে সংশোধন করো।

### Problem 1

```python
print("Hello Python"
```

### Problem 2

```python
2name = "Masum"
```

### Problem 3

```python
age = input("Enter your age: ")
print(age + 5)
```

### Problem 4

```python
if age >= 18
    print("Adult")
```

### Problem 5

```python
price = 100
quantity = 3

total = price + quantity

print(total)
```

### Problem 6

```python
name = "Masum"

print(Name)
```

### Problem 7

```python
number = int("hello")

print(number)
```

### Problem 8

```python
a = 10
b = 0

print(a / b)
```

## 7. Short Questions for Revision

প্রতিটি প্রশ্নের উত্তর নিজের ভাষায় লেখার চেষ্টা করো।

1. What is Python?
2. What is programming?
3. What is syntax?
4. What is a variable?
5. What is dynamic typing?
6. What is an identifier?
7. What is a keyword?
8. What is a literal?
9. What is a constant?
10. What is an expression?
11. What is a statement?
12. What is operator precedence?
13. Why is indentation important in Python?
14. What is the difference between `=` and `==`?
15. What does `input()` return?
16. Why do we use `int()` and `float()`?
17. What is the difference between `is` and `==`?
18. What is the difference between `print()` and `input()`?
19. What is debugging?
20. What is a logical error?
21. What is the purpose of comments?
22. What is the DRY principle?
23. What is the KISS principle?
24. What is PEP 8?
25. Why is clean code important?

## 8. Practical Assessment

এবার একটি ছোট program তৈরি করো, যেখানে chapter-এর একাধিক concept একসঙ্গে ব্যবহার করতে হবে।

### Task: Student Performance Calculator

**Requirements:**

1. Student-এর নাম input নাও।
2. তিনটি subject-এর marks input নাও।
3. প্রতিটি marks `float` হিসেবে convert করো।
4. তিনটি marks-এর average হিসাব করো।
5. Total marks-এর ভিত্তিতে percentage হিসাব করো।
6. f-string দিয়ে formatted output দেখাও।
7. Meaningful variable name ব্যবহার করো।
8. প্রয়োজনীয় জায়গায় comment লেখো।
9. Invalid numeric input হলে `ValueError` handle করো।

ধরে নাও, প্রতিটি subject-এর maximum marks 100।

Formula:

\[
\text{Average}=\frac{m_1+m_2+m_3}{3}
\]

\[
\text{Percentage}=\frac{m_1+m_2+m_3}{300}\times100
\]

Sample input:

```text
Enter student name: Masum
Enter first subject marks: 80
Enter second subject marks: 85
Enter third subject marks: 90
```

Expected output:

```text
===== Student Performance =====
Name: Masum
Average: 85.00
Percentage: 85.00%
```

এখানে grade নির্ধারণের প্রয়োজন নেই; সেটি পরবর্তী Conditional Statements chapter-এ practice করা যাবে।

## 9. Self-Assessment Checklist

Chapter 02 শেষ করার পর যাচাই করো, তুমি নিচের কাজগুলো নিজে করতে পারো কি না।

### Fundamentals

- [ ] Python program তৈরি ও execute করতে পারি।
- [ ] Python syntax-এর basic rules বুঝি।
- [ ] `print()` এবং `input()` ব্যবহার করতে পারি।
- [ ] Comments ও literals বুঝি।

### Variables and Operators

- [ ] Variable তৈরি, assign এবং reassign করতে পারি।
- [ ] Identifier ও keyword-এর পার্থক্য বুঝি।
- [ ] Basic data types শনাক্ত করতে পারি।
- [ ] Type conversion করতে পারি।
- [ ] Arithmetic, comparison ও logical operators ব্যবহার করতে পারি।
- [ ] Operator precedence বুঝতে পারি।
- [ ] Multiple assignment ও unpacking ব্যবহার করতে পারি।

### Debugging and Code Quality

- [ ] Syntax Error, Runtime Error এবং Logical Error আলাদা করতে পারি।
- [ ] Error message পড়ে সমস্যা খুঁজতে পারি।
- [ ] `try-except`-এর basic use বুঝি।
- [ ] Meaningful variable name ও proper indentation ব্যবহার করতে পারি।
- [ ] Simple reusable function লিখতে পারি।

### Practical Skills

- [ ] Input নিয়ে calculation করতে পারি।
- [ ] Formatted output তৈরি করতে পারি।
- [ ] একটি ছোট program নিজে তৈরি করতে পারি।
- [ ] Code-এর output অনুমান করে execute করে যাচাই করতে পারি।

## 10. Recommended Revision Plan

যদি কোনো topic ভালোভাবে বুঝতে না পারো, তাহলে এই পদ্ধতিতে revise করো।

| Day | Revision Task |
|---|---|
| Day 1 | Syntax, variables, identifiers ও assignment |
| Day 2 | Data types, literals ও type conversion |
| Day 3 | Operators, expressions ও precedence |
| Day 4 | Input, output ও formatting |
| Day 5 | Errors, debugging ও clean code |
| Day 6 | Practice exercises ও output prediction |
| Day 7 | Student Performance Calculator তৈরি এবং self-assessment |

এই schedule বাধ্যতামূলক নয়। নিজের সুবিধা অনুযায়ী সময় ভাগ করে নিতে পারো।

## 11. Chapter Completion Criteria

Chapter 02 সম্পন্ন হয়েছে বলে ধরে নেওয়ার আগে:

- [ ] Chapter-এর সব subtopic অন্তত একবার পড়েছি।
- [ ] গুরুত্বপূর্ণ code example নিজে execute করেছি।
- [ ] অধিকাংশ practice exercise নিজে solve করেছি।
- [ ] ভুল code debug করার চেষ্টা করেছি।
- [ ] Student Performance Calculator নিজে তৈরি করেছি।
- [ ] যেসব topic দুর্বল, সেগুলো revise করেছি।

কোনো topic বুঝতে সমস্যা হলে সেটি skip না করে সংশ্লিষ্ট file-এ ফিরে যাও।

## 12. Final Summary

Python Fundamentals হলো Python programming শেখার foundation। এই chapter-এর concepts ভালোভাবে বুঝলে পরবর্তী topic শেখা অনেক সহজ হবে।

সবচেয়ে গুরুত্বপূর্ণ বিষয়গুলো:

- Syntax ও indentation সঠিক রাখা।
- Variable এবং data type বোঝা।
- Input ও output ব্যবহার করা।
- Operators ও expressions দিয়ে calculation করা।
- Type conversion-এর প্রয়োজন বোঝা।
- Error message পড়ে debugging করা।
- Clean ও readable code লেখা।
- নিয়মিত নিজে code লিখে practice করা।

**Final Advice:** শুধু notes পড়লে programming skill তৈরি হবে না। প্রতিটি গুরুত্বপূর্ণ example নিজে টাইপ করো, output অনুমান করো, execute করো এবং নিজের মতো করে পরিবর্তন করে দেখো।

## 13. Next Chapter

পরবর্তী chapter: **03 — Data Types & Type Conversion**

এই chapter-এ Python-এর data types আরও বিস্তারিতভাবে শেখা হবে, যেমন:

- Numeric Types
- Strings
- Boolean Values
- `NoneType`
- Type Checking
- Type Conversion
- Mutable and Immutable Objects
- Type-Related Errors

পরবর্তী chapter-এর প্রথম ফাইল হবে:

[`01_Introduction_to_Python_Data_Types.md`](../03_Data_Types_and_Type_Conversion/01_Introduction_to_Python_Data_Types.md)