# 02. Operands and Expressions in Python

## 1. Introduction

Python-এ Operators নিয়ে কাজ করার আগে দুটি গুরুত্বপূর্ণ Concept বুঝতে হবে:

- **Operand:** যে Value বা Object-এর ওপর Operator কাজ করে।
- **Expression:** Code-এর এমন একটি অংশ, যা Evaluate করলে একটি Value পাওয়া যায়।

Example:

```python
result = 10 + 5
```

এখানে:

- `10` হলো Left Operand।
- `+` হলো Operator।
- `5` হলো Right Operand।
- `10 + 5` হলো Expression।
- `15` হলো Expression-এর Result।
- `result = 10 + 5` হলো Assignment Statement।

## 2. What Is an Operand?

Operand হলো কোনো Operation-এ ব্যবহৃত Value, Variable বা Expression।

Example:

```python
a = 10
b = 20

result = a + b
print(result)
```

Output:

```text
30
```

এখানে `a` এবং `b` হলো `+` Operator-এর Operand।

তাদের বর্তমান Value হলো `10` এবং `20`।

### 2.1 Types of Operands

Operand হিসেবে বিভিন্ন ধরনের Value ব্যবহার করা যায়।

**1. Numeric Values**

```python
result = 10 + 20
```

এখানে `10` এবং `20` Operand।

**2. Variables**

```python
a = 10
b = 5

result = a - b
```

এখানে `a` এবং `b` Operand।

**3. String Values**

```python
result = "Hello" + " Python"
print(result)
```

Output:

```text
Hello Python
```

এখানে দুটি String হলো Operand।

**4. Expressions**

```python
result = (10 + 5) * 2
print(result)
```

Output:

```text
30
```

এখানে `(10 + 5)`-এর Result `15`, যা পরবর্তী Multiplication-এর Operand হিসেবে ব্যবহৃত হয়েছে।

## 3. Left Operand and Right Operand

Binary Operator-এর ক্ষেত্রে সাধারণত দুটি Operand থাকে।

```python
result = 10 - 4
```

এখানে:

- `10` হলো Left Operand।
- `4` হলো Right Operand।
- `-` হলো Binary Operator।

**মনে রাখবে:** সব Operator-এর দুটি Operand থাকে না। Unary Operator একটি Operand নিয়ে কাজ করে।

Example:

```python
number = 10

print(-number)
```

Output:

```text
-10
```

এখানে Unary `-` Operator একটি Operand-এর ওপর কাজ করছে।

## 4. What Is an Expression?

Expression হলো এমন একটি Combination of Values, Variables, Operators, এবং Function Calls, যা Evaluate করে একটি Value পাওয়া যায়।

Examples:

```python
10 + 5
```

```python
age >= 18
```

```python
price * quantity
```

```python
len("Python")
```

প্রতিটি Expression Evaluate করলে একটি Result পাওয়া যায়।

Example:

```python
a = 10
b = 5

print(a + b)
print(a > b)
print(len("Python"))
```

Output:

```text
15
True
6
```

এখানে Expression-গুলো ভিন্ন ধরনের Result দিয়েছে।

- `a + b` → Integer Result
- `a > b` → Boolean Result
- `len("Python")` → Integer Result

## 5. Types of Expressions

Python-এ বিভিন্ন ধরনের Expression রয়েছে।

### 5.1 Arithmetic Expression

Mathematical Calculation করে।

```python
result = 10 + 5 * 2
print(result)
```

Output:

```text
20
```

এখানে Multiplication আগে হয়েছে, কারণ `*`-এর Precedence `+`-এর চেয়ে বেশি।

### 5.2 Comparison Expression

দুটি Value তুলনা করে।

```python
age = 22

result = age >= 18
print(result)
```

Output:

```text
True
```

Comparison Expression সাধারণত `True` অথবা `False` Return করে।

### 5.3 Logical Expression

এক বা একাধিক Condition Combine করে।

```python
age = 22
has_id = True

result = age >= 18 and has_id
print(result)
```

Output:

```text
True
```

### 5.4 String Expression

String Concatenation বা Repetition-এর মতো Operation করতে পারে।

```python
name = "Python"

print(name + " Programming")
print(name * 2)
```

Output:

```text
Python Programming
PythonPython
```

### 5.5 Conditional Expression

Condition অনুযায়ী দুটি Value-এর মধ্যে একটি নির্বাচন করে।

```python
age = 20

status = "Adult" if age >= 18 else "Minor"

print(status)
```

Output:

```text
Adult
```

### 5.6 Function Call Expression

Function Call থেকেও একটি Value পাওয়া যেতে পারে।

```python
result = len("Programming")

print(result)
```

Output:

```text
11
```

## 6. What Is Expression Evaluation?

**Expression Evaluation** হলো Expression-এর Result নির্ণয় করার প্রক্রিয়া।

Example:

```python
result = 10 + 5 * 2
```

Python প্রথমে Precedence অনুযায়ী `5 * 2` Evaluate করে।

```text
5 * 2 = 10
10 + 10 = 20
```

তাই:

```python
print(result)
```

Output:

```text
20
```

Expression-এ একাধিক Operator থাকলে তাদের Precedence এবং Associativity Evaluation-এর Order নির্ধারণে সাহায্য করে।

## 7. Expressions and Data Types

Expression-এর Result-এর Data Type নির্ভর করে ব্যবহৃত Operand এবং Operator-এর ওপর।

Example:

```python
print(10 + 5)
print(10 / 5)
print(10 > 5)
print("Py" + "thon")
```

Output:

```text
15
2.0
True
Python
```

Result-এর Type পরীক্ষা করা যাক:

```python
print(type(10 + 5))
print(type(10 / 5))
print(type(10 > 5))
print(type("Py" + "thon"))
```

Output:

```text
<class 'int'>
<class 'float'>
<class 'bool'>
<class 'str'>
```

এখানে:

- Integer Addition-এর Result `int`।
- `/` দিয়ে Division-এর Result `float`।
- Comparison-এর Result `bool`।
- String Concatenation-এর Result `str`।

**Important:** `/` Operator দিয়ে দুটি Integer Divide করলেও Python সাধারণত `float` Result দেয়।

## 8. Expression vs Statement

Expression এবং Statement এক জিনিস নয়।

### Expression

Evaluate করলে একটি Value পাওয়া যায়।

```python
10 + 5
```

```python
age >= 18
```

### Statement

Python-কে কোনো কাজ করার নির্দেশ দেয়।

```python
age = 22
```

```python
print("Hello")
```

```python
if age >= 18:
    print("Adult")
```

এখানে Assignment এবং `if` Statement রয়েছে।

### Expression Inside a Statement

একটি Statement-এর মধ্যে Expression থাকতে পারে।

```python
total = 10 + 5
```

এখানে:

- `10 + 5` হলো Expression।
- `total = 10 + 5` হলো Assignment Statement।

| Expression | Statement |
|---|---|
| একটি Value নির্ণয় করে | একটি Instruction প্রকাশ করে |
| `10 + 5` | `total = 15` |
| `age > 18` | `print("Hello")` |
| `len("Python")` | `if age > 18:` |

কিছু Python Statement-এর মধ্যে Expression থাকে, আবার কিছু Expression সরাসরি Expression Statement হিসেবে লেখা যায়।

## 9. Operator and Operand Compatibility

সব Operator সব ধরনের Operand-এর সঙ্গে কাজ করতে পারে না।

### 9.1 Valid Operation

```python
print(10 + 20)
```

Output:

```text
30
```

### 9.2 String Concatenation

```python
print("Hello" + " World")
```

Output:

```text
Hello World
```

### 9.3 Invalid Operation

```python
print("Age: " + 22)
```

এখানে `TypeError` হবে, কারণ String এবং Integer সরাসরি `+` দিয়ে Concatenate করা যায় না।

সঠিক উপায়:

```python
print("Age: " + str(22))
```

Output:

```text
Age: 22
```

অথবা:

```python
print(f"Age: {22}")
```

Output:

```text
Age: 22
```

Operator ব্যবহারের আগে Operand-এর Data Type এবং সেই Operation-এর নিয়ম বুঝতে হবে।

## 10. Expressions with Variables

Variable ব্যবহার করে Expression তৈরি করা যায়।

```python
price = 100
quantity = 3
discount = 50

total = price * quantity - discount

print(total)
```

Output:

```text
250
```

Evaluation:

```text
100 * 3 - 50
= 300 - 50
= 250
```

এই ধরনের Expression বাস্তব Problem যেমন Shopping Bill, Marks Calculation এবং Budget হিসাব করতে কাজে লাগে।

## 11. Nested Expressions

একটি Expression-এর মধ্যে আরেকটি Expression থাকলে তাকে Nested Expression বলা যেতে পারে।

Example:

```python
result = (10 + 5) * (8 - 3)

print(result)
```

Output:

```text
75
```

Evaluation:

```text
(10 + 5) = 15
(8 - 3) = 5
15 * 5 = 75
```

Parentheses ব্যবহার করে Expression-এর Evaluation Order পরিষ্কার করা যায়।

## 12. Common Mistakes

### Mistake 1: Confusing `=` and `==`

```python
age = 20
print(age == 20)
```

Output:

```text
True
```

`=` Assignment করে, আর `==` Equality পরীক্ষা করে।

### Mistake 2: Ignoring Operator Precedence

```python
print(10 + 5 * 2)
```

Output:

```text
20
```

Output `30` নয়, কারণ Multiplication আগে হয়।

### Mistake 3: Mixing Incompatible Types

```python
print("Marks: " + 80)
```

এখানে `TypeError` হবে।

সঠিকভাবে:

```python
print("Marks: " + str(80))
```

### Mistake 4: Assuming Every Expression Returns the Same Type

```python
print(10 + 5)
print(10 > 5)
```

Output:

```text
15
True
```

প্রথমটি Integer এবং দ্বিতীয়টি Boolean Result দেয়।

## 13. Practice Exercises

### Basic Questions

1. Operand কী?
2. Expression কী?
3. Left Operand ও Right Operand কী?
4. Expression Evaluation বলতে কী বোঝায়?
5. Expression এবং Statement-এর পার্থক্য কী?
6. Unary এবং Binary Operator-এর পার্থক্য কী?

### Output Prediction

**Question 1**

```python
a = 10
b = 5

print(a + b * 2)
```

**Question 2**

```python
x = 10

print(x > 5)
print(type(x > 5))
```

**Question 3**

```python
name = "Python"

print(name + "3")
```

**Question 4**

```python
result = (8 + 2) / 5

print(result)
print(type(result))
```

**Question 5**

```python
age = 17

status = "Adult" if age >= 18 else "Minor"

print(status)
```

### Practical Exercises

1. দুটি Number নিয়ে Addition, Subtraction এবং Multiplication-এর Expression লেখো।
2. Product-এর Price ও Quantity ব্যবহার করে Total Price নির্ণয় করো।
3. একজন Student-এর Marks `40` বা তার বেশি কি না পরীক্ষা করো।
4. দুটি Condition ব্যবহার করে Logical Expression লেখো।
5. একটি String এবং Integer ব্যবহার করে সঠিকভাবে Message তৈরি করো।
6. Parentheses ব্যবহার করে একটি Nested Expression তৈরি করো।

## 14. Chapter Summary

- Operand হলো Operator-এর ওপর কাজ করা Value বা Object।
- Expression হলো এমন Code Fragment, যা Evaluate করলে একটি Value পাওয়া যায়।
- Expression Arithmetic, Comparison, Logical, String বা Function Call-ভিত্তিক হতে পারে।
- Expression Evaluation হলো Result নির্ণয়ের প্রক্রিয়া।
- Expression-এর Result-এর Data Type Operation অনুযায়ী পরিবর্তিত হতে পারে।
- Statement Python-কে কোনো Instruction দেয়; একটি Statement-এর মধ্যে Expression থাকতে পারে।
- Operator ব্যবহারের সময় Operand-এর Data Type Compatibility বুঝতে হবে।
- Precedence, Associativity এবং Parentheses Expression-এর Evaluation Order নির্ধারণে গুরুত্বপূর্ণ।

## 15. Self-Assessment Checklist

- [ ] Operand এবং Operator আলাদা করতে পারি।
- [ ] Expression শনাক্ত করতে পারি।
- [ ] Left ও Right Operand বুঝি।
- [ ] Expression-এর Result নির্ণয় করতে পারি।
- [ ] Expression ও Statement-এর পার্থক্য বুঝি।
- [ ] Result-এর Data Type পরীক্ষা করতে পারি।
- [ ] Operator ও Operand-এর Compatibility বুঝি।
- [ ] Nested Expression Evaluate করতে পারি।

**Next Topic:** `03_Overview_of_Python_Operators.md`