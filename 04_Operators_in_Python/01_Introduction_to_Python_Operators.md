# 01. Introduction to Python Operators

## 1. What Is an Operator?

Python-এ **Operator** হলো একটি Symbol বা Keyword, যা এক বা একাধিক Value-এর ওপর নির্দিষ্ট Operation সম্পন্ন করে।

Operator ব্যবহার করে আমরা যোগ, বিয়োগ, তুলনা, শর্ত যাচাই এবং আরও অনেক ধরনের কাজ করতে পারি।

Example:

```python
a = 10
b = 5

print(a + b)
```

Output:

```text
15
```

এখানে `+` হলো একটি Operator, যা `a` এবং `b`-এর Value যোগ করেছে।

## 2. Why Do We Need Operators?

Programming-এ বিভিন্ন ধরনের Calculation এবং Decision নেওয়ার জন্য Operators প্রয়োজন হয়।

Operators ব্যবহার করে আমরা:

1. Mathematical Calculation করতে পারি।
2. দুটি Value তুলনা করতে পারি।
3. একাধিক Condition যাচাই করতে পারি।
4. Variable-এর Value Update করতে পারি।
5. কোনো Value Collection-এর মধ্যে আছে কি না পরীক্ষা করতে পারি।
6. Object Identity যাচাই করতে পারি।
7. Binary Data-এর ওপর Bit-Level Operation করতে পারি।

Example:

```python
price = 500
discount = 50

final_price = price - discount

print(final_price)
```

Output:

```text
450
```

এখানে `-` Operator ব্যবহার করে Discount বাদ দেওয়া হয়েছে।

## 3. Basic Components of an Operation

একটি সাধারণ Operation-এর তিনটি গুরুত্বপূর্ণ অংশ রয়েছে।

- **Operator:** যে Operation সম্পন্ন করে।
- **Operand:** যে Value বা Object-এর ওপর Operation করা হয়।
- **Expression:** Operator এবং Operand ব্যবহার করে তৈরি হওয়া একটি Code Fragment, যা Evaluate করলে একটি Value পাওয়া যায়।

Example:

```python
result = 10 + 5
```

এখানে:

| Component | Value |
|---|---|
| Left Operand | `10` |
| Operator | `+` |
| Right Operand | `5` |
| Expression | `10 + 5` |
| Result | `15` |

**মনে রাখবে:** `result = 10 + 5` একটি Assignment Statement, আর `10 + 5` হলো Expression।

## 4. Types of Operators in Python

Python-এ Operators-কে তাদের কাজ অনুযায়ী কয়েকটি প্রধান Category-তে ভাগ করা হয়।

| Category | Main Purpose | Examples |
|---|---|---|
| Arithmetic Operators | Mathematical Calculation | `+`, `-`, `*`, `/` |
| Comparison Operators | দুটি Value তুলনা করা | `==`, `!=`, `>`, `<` |
| Logical Operators | Logical Condition যাচাই করা | `and`, `or`, `not` |
| Assignment Operators | Variable-এ Value Assign বা Update করা | `=`, `+=`, `-=` |
| Identity Operators | Object একই কি না যাচাই করা | `is`, `is not` |
| Membership Operators | কোনো Element আছে কি না যাচাই করা | `in`, `not in` |
| Bitwise Operators | Integer-এর Binary Bits নিয়ে কাজ করা | `&`, `|`, `^`, `~` |

এই Chapter-এ প্রতিটি Category আলাদাভাবে বিস্তারিত শেখা হবে।

## 5. Arithmetic Operators

Arithmetic Operators ব্যবহার করে Mathematical Calculation করা হয়।

```python
a = 10
b = 3

print(a + b)
print(a - b)
print(a * b)
print(a / b)
```

Output:

```text
13
7
30
3.3333333333333335
```

এখানে:

- `+` → Addition
- `-` → Subtraction
- `*` → Multiplication
- `/` → Division

Floor Division, Modulo এবং Exponentiation-সহ বাকি Arithmetic Operators পরবর্তী Topics-এ বিস্তারিত আলোচনা করা হবে।

## 6. Comparison Operators

Comparison Operators দুটি Value তুলনা করে এবং সাধারণত `True` অথবা `False` Return করে।

```python
a = 10
b = 5

print(a > b)
print(a < b)
print(a == b)
print(a != b)
```

Output:

```text
True
False
False
True
```

এখানে:

- `>` → Greater Than
- `<` → Less Than
- `==` → Equal To
- `!=` → Not Equal To

**Important:** `=` এবং `==` এক নয়। `=` Assignment-এর জন্য, আর `==` Equality Comparison-এর জন্য ব্যবহৃত হয়।

## 7. Logical Operators

Logical Operators ব্যবহার করে এক বা একাধিক Condition Combine বা Reverse করা যায়।

Python-এর তিনটি প্রধান Logical Operator হলো:

- `and`
- `or`
- `not`

Example:

```python
age = 22
has_id = True

print(age >= 18 and has_id)
```

Output:

```text
True
```

এখানে দুটি Condition-ই `True`, তাই `and` Expression-এর Result `True`।

## 8. Assignment Operators

Assignment Operators Variable-এ Value Assign বা বিদ্যমান Value Update করতে সাহায্য করে।

Example:

```python
number = 10
number += 5

print(number)
```

Output:

```text
15
```

এখানে `+=` হলো Augmented Assignment Operator। এটি বিদ্যমান Value-এর সঙ্গে `5` যোগ করে Variable-টি Update করেছে।

## 9. Identity Operators

Identity Operators পরীক্ষা করে দুটি Reference একই Object-কে নির্দেশ করছে কি না।

দুটি Identity Operator হলো:

- `is`
- `is not`

Example:

```python
a = [1, 2, 3]
b = a

print(a is b)
```

Output:

```text
True
```

কারণ `a` এবং `b` একই List Object-কে Reference করছে।

Identity এবং Equality-এর পার্থক্য পরবর্তী Topics-এ বিস্তারিত শেখা হবে।

## 10. Membership Operators

Membership Operators কোনো Collection-এর মধ্যে নির্দিষ্ট Value আছে কি না পরীক্ষা করে।

দুটি Membership Operator হলো:

- `in`
- `not in`

Example:

```python
fruits = ["Apple", "Mango", "Banana"]

print("Mango" in fruits)
print("Orange" not in fruits)
```

Output:

```text
True
True
```

## 11. Bitwise Operators

Bitwise Operators Integer-এর Binary Representation-এর Bits নিয়ে কাজ করে।

Example:

```python
a = 5
b = 3

print(a & b)
```

Output:

```text
1
```

Binary Representation:

```text
5 = 101
3 = 011
    ---
AND 001 = 1
```

Bitwise Operators শুরুতে কিছুটা কঠিন মনে হতে পারে। তাই এগুলো শেখার আগে Binary Number-এর Basic ধারণা পরিষ্কার করা হবে।

## 12. Operators Can Have Different Numbers of Operands

কোনো Operator কতটি Operand নিয়ে কাজ করে, তার ভিত্তিতেও Operators-কে ভাগ করা যায়।

### 12.1 Unary Operator

একটি Operand-এর ওপর কাজ করে।

Example:

```python
number = 10

print(-number)
print(not True)
```

Output:

```text
-10
False
```

এখানে `-` এবং `not` Unary Operator হিসেবে ব্যবহৃত হয়েছে।

### 12.2 Binary Operator

দুটি Operand-এর ওপর কাজ করে।

Example:

```python
print(10 + 5)
print(10 > 5)
```

Output:

```text
15
True
```

এখানে `+` এবং `>` Binary Operator হিসেবে কাজ করছে।

### 12.3 Conditional Expression

Python-এ Conditional Expression ব্যবহার করে একটি Condition অনুযায়ী দুটি Value-এর মধ্যে একটি নির্বাচন করা যায়।

```python
age = 20

status = "Adult" if age >= 18 else "Minor"

print(status)
```

Output:

```text
Adult
```

এটি সাধারণত Ternary Expression নামে পরিচিত। এর বিস্তারিত পরবর্তী Advanced Topic-এ আলোচনা করা হবে।

## 13. Important Rules to Remember

1. Operator একটি Operation সম্পন্ন করে।
2. Operand হলো যে Value বা Object-এর ওপর Operation করা হয়।
3. Expression Evaluate করলে একটি Result পাওয়া যায়।
4. Arithmetic Operators Calculation করে।
5. Comparison Operators সাধারণত `True` বা `False` Return করে।
6. Logical Operators Condition Combine বা Reverse করে।
7. Assignment Operator হিসেবে `=` ব্যবহৃত হয়।
8. `==` Value Equality পরীক্ষা করে।
9. `is` Object Identity পরীক্ষা করে।
10. `in` Membership পরীক্ষা করে।
11. Operator-এর কাজ বুঝতে Operand-এর Data Type জানা গুরুত্বপূর্ণ।
12. একটি Expression-এ একাধিক Operator থাকলে Precedence ও Associativity Result নির্ধারণে ভূমিকা রাখে।

## 14. Practice Exercises

### Basic Questions

1. Operator কী?
2. Operand কী?
3. Expression বলতে কী বোঝায়?
4. Python-এ Operators কেন ব্যবহার করা হয়?
5. Arithmetic ও Comparison Operators-এর পার্থক্য কী?
6. `=` এবং `==`-এর পার্থক্য কী?
7. Identity ও Membership Operators-এর কাজ কী?
8. Unary এবং Binary Operator-এর পার্থক্য কী?

### Code Practice

**Exercise 1:** দুটি Number যোগ করে Result Print করো।

**Exercise 2:** দুটি Number-এর মধ্যে কোনটি বড়, তা Comparison Operator দিয়ে পরীক্ষা করো।

**Exercise 3:** একটি Student-এর Marks `80` এবং Pass Mark `40` ধরে Student Pass করেছে কি না পরীক্ষা করো।

**Exercise 4:** একটি List-এ `"Python"` আছে কি না Membership Operator দিয়ে পরীক্ষা করো।

**Exercise 5:** একটি Variable-এর Value `10` থেকে `20`-এ Augmented Assignment Operator দিয়ে Update করো।

### Output Prediction

প্রথমে নিজে Output অনুমান করো।

**Question 1**

```python
a = 8
b = 2

print(a + b * 3)
```

**Question 2**

```python
x = 10

print(x > 5)
print(x == 10)
```

**Question 3**

```python
numbers = [10, 20, 30]

print(20 in numbers)
print(40 in numbers)
```

## 15. Chapter Summary

Python Operators হলো Programming-এর অন্যতম মৌলিক অংশ। এগুলো ব্যবহার করে Mathematical Calculation, Comparison, Logical Decision, Assignment, Object Identity এবং Membership Testing করা যায়।

এই Topic-এ Operators-এর পরিচয় ও প্রধান Category শেখা হয়েছে। পরবর্তী Topic-এ Operands এবং Expressions আরও বিস্তারিতভাবে আলোচনা করা হবে।

**Next Topic:** `02_Operands_and_Expressions.md`