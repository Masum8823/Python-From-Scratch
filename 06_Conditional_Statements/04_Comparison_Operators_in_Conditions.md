# 04. Comparison Operators in Conditions

## 1. Introduction

Python-এ দুটি value তুলনা করার জন্য **Comparison Operators** ব্যবহার করা হয়। এই operator-গুলো পরীক্ষা করে একটি value অন্যটির সমান, অসমান, বড় নাকি ছোট।

Comparison-এর result সাধারণত Boolean value হয়:

- `True`
- `False`

Example:

```python
a = 10
b = 5

print(a > b)
print(a < b)
print(a == b)
```

Output:

```text
True
False
False
```

এখানে `a > b` সত্য, তাই result `True`। কিন্তু `a < b` এবং `a == b` মিথ্যা, তাই result `False`।

Comparison Operators conditional statements-এর গুরুত্বপূর্ণ অংশ। এগুলো ব্যবহার করে pass/fail, eligibility, price checking এবং user input validation-এর মতো কাজ করা যায়।

## 2. List of Comparison Operators

Python-এ প্রধান ছয়টি comparison operator রয়েছে।

| Operator | Name | Meaning |
|---|---|---|
| `==` | Equal to | দুটি value সমান কি না |
| `!=` | Not equal to | দুটি value আলাদা কি না |
| `>` | Greater than | বাম পাশের value বড় কি না |
| `<` | Less than | বাম পাশের value ছোট কি না |
| `>=` | Greater than or equal to | বাম পাশের value বড় অথবা সমান কি না |
| `<=` | Less than or equal to | বাম পাশের value ছোট অথবা সমান কি না |

মনে রাখবে, comparison operator সাধারণত value পরিবর্তন করে না; এটি তুলনার result দেয়।

## 3. Equal to Operator (`==`)

`==` operator পরীক্ষা করে দুটি value সমান কি না।

Example:

```python
a = 10
b = 10
c = 20

print(a == b)
print(a == c)
```

Output:

```text
True
False
```

ব্যাখ্যা:

- `a == b` → `10 == 10` → `True`
- `a == c` → `10 == 20` → `False`

### Practical Example: Pass Mark

```python
marks = 40

if marks == 40:
    print("Marks are exactly 40.")
```

Output:

```text
Marks are exactly 40.
```

এখানে condition সত্য, কারণ marks-এর value ঠিক 40।

**Important:** `==` সমান কি না পরীক্ষা করে। এটি variable-এ value assign করে না।

## 4. Not Equal to Operator (`!=`)

`!=` পরীক্ষা করে দুটি value সমান নয় কি না।

Example:

```python
a = 10
b = 20

print(a != b)
print(a != 10)
```

Output:

```text
True
False
```

ব্যাখ্যা:

- `10 != 20` সত্য।
- `10 != 10` মিথ্যা।

### Practical Example: Username Check

```python
username = "masum"

if username != "admin":
    print("Regular user")
```

Output:

```text
Regular user
```

এখানে username `"admin"` নয়, তাই condition সত্য।

## 5. Greater Than Operator (`>`)

`>` operator পরীক্ষা করে বাম পাশের value ডান পাশের value-এর চেয়ে বড় কি না।

Example:

```python
print(10 > 5)
print(5 > 10)
print(5 > 5)
```

Output:

```text
True
False
False
```

খেয়াল করো, দুটি value সমান হলে `>`-এর result `False` হয়।

### Practical Example: Age Check

```python
age = 20

if age > 18:
    print("Age is greater than 18.")
```

Output:

```text
Age is greater than 18.
```

যদি `age = 18` হয়, তাহলে condition মিথ্যা হবে।

**মনে রাখবে:** `>` মানে শুধু বড়; সমান হলে নয়।

## 6. Less Than Operator (`<`)

`<` operator পরীক্ষা করে বাম পাশের value ডান পাশের value-এর চেয়ে ছোট কি না।

Example:

```python
print(3 < 8)
print(8 < 3)
print(5 < 5)
```

Output:

```text
True
False
False
```

### Practical Example: Low Balance

```python
balance = 500

if balance < 1000:
    print("Low balance")
```

Output:

```text
Low balance
```

এখানে balance 1000-এর চেয়ে কম, তাই condition সত্য।

## 7. Greater Than or Equal to (`>=`)

`>=` operator পরীক্ষা করে বাম পাশের value বড় অথবা সমান কি না।

Example:

```python
print(50 >= 40)
print(40 >= 40)
print(30 >= 40)
```

Output:

```text
True
True
False
```

এখানে `40 >= 40` সত্য, কারণ সমান হলেও condition পূরণ হয়।

### Practical Example: Passing Marks

ধরো, পাস করার জন্য অন্তত 40 নম্বর পেতে হবে।

```python
marks = 40

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

Output:

```text
Pass
```

যদি এখানে `>` ব্যবহার করা হতো, তাহলে ঠিক 40 পাওয়া student-কে Pass দেখাত না।

তাই requirement যদি **at least 40** হয়, তাহলে `>= 40` ব্যবহার করতে হবে।

## 8. Less Than or Equal to (`<=`)

`<=` operator পরীক্ষা করে বাম পাশের value ছোট অথবা সমান কি না।

Example:

```python
print(5 <= 10)
print(10 <= 10)
print(15 <= 10)
```

Output:

```text
True
True
False
```

### Practical Example: Maximum Age

ধরো, একটি program-এ age সর্বোচ্চ 60 হতে পারবে।

```python
age = 60

if age <= 60:
    print("Age is within the limit.")
else:
    print("Age exceeds the limit.")
```

Output:

```text
Age is within the limit.
```

যদি age 61 হয়, তাহলে condition মিথ্যা হবে।

## 9. Difference Between `=` and `==`

Python beginners-দের জন্য এটি খুব গুরুত্বপূর্ণ একটি বিষয়।

| Operator | Purpose | Example |
|---|---|---|
| `=` | Assignment | `age = 18` |
| `==` | Equality comparison | `age == 18` |

### Assignment Example

```python
age = 18
```

এখানে `18` value-টি `age` variable-এ assign করা হয়েছে।

### Comparison Example

```python
age = 18

print(age == 18)
```

Output:

```text
True
```

এখানে পরীক্ষা করা হচ্ছে `age`-এর value 18 কি না।

### Common Error

Incorrect:

```python
age = 18

if age = 18:
    print("Age is 18")
```

এটি `SyntaxError` তৈরি করবে, কারণ `if` condition-এর মধ্যে এভাবে assignment করা যায় না।

Correct:

```python
age = 18

if age == 18:
    print("Age is 18")
```

Output:

```text
Age is 18
```

**মনে রাখার কৌশল:**

- `=` → value রাখা।
- `==` → value তুলনা করা।

## 10. Comparing Variables

Comparison Operators-এর সঙ্গে variable ব্যবহার করা যায়।

```python
a = 15
b = 10

print(a > b)
print(a < b)
print(a != b)
```

Output:

```text
True
False
True
```

Python variable-এর বর্তমান value নিয়ে comparison করে।

### Variable Values Can Change

```python
a = 10
b = 20

print(a < b)

a = 30

print(a < b)
```

Output:

```text
True
False
```

প্রথমে `10 < 20` সত্য ছিল। পরে `a`-এর value 30 হওয়ায় `30 < 20` মিথ্যা হয়েছে।

## 11. Comparing User Input

User-এর input নিয়েও comparison করা যায়। তবে `input()` সাধারণত string return করে।

Example:

```python
age = int(input("Enter your age: "))

print(age >= 18)
```

Sample Input:

```text
Enter your age: 21
```

Output:

```text
True
```

এখানে `int()` ব্যবহার করে input-কে integer-এ convert করা হয়েছে।

### Comparing Text Input

```python
answer = input("Enter yes or no: ")

print(answer == "yes")
```

Input:

```text
yes
```

Output:

```text
True
```

Input:

```text
Yes
```

Output:

```text
False
```

কারণ Python-এর string comparison case-sensitive।

Case-insensitive comparison প্রয়োজন হলে:

```python
answer = input("Enter yes or no: ").strip().lower()

print(answer == "yes")
```

এখন `"YES"`, `"Yes"` বা `"yes"`—সবগুলো input comparison-এ `True` দেবে।

## 12. Comparing Strings

Python-এ string-ও তুলনা করা যায়।

### 12.1 Equality Comparison

```python
print("Python" == "Python")
print("Python" == "python")
```

Output:

```text
True
False
```

এখানে uppercase ও lowercase অক্ষরের পার্থক্য গুরুত্বপূর্ণ।

### 12.2 Lexicographical Comparison

String-এর মধ্যে `<` ও `>` ব্যবহার করলে Python Unicode code point-এর ক্রম অনুযায়ী character-by-character তুলনা করে।

```python
print("apple" < "banana")
print("cat" > "car")
```

Output:

```text
True
True
```

ব্যাখ্যা:

- `"apple"` ও `"banana"`-এর প্রথম অক্ষর `a` ও `b`; `a` আগে, তাই প্রথম comparison সত্য।
- `"cat"` ও `"car"`-এর প্রথম দুটি অক্ষর সমান। তৃতীয় অক্ষরে `t` ও `r` তুলনা করা হয়। `t`-এর code point `r`-এর চেয়ে বড়, তাই দ্বিতীয় comparison সত্য।

String comparison সবসময় মানুষের ভাষার dictionary order বা numeric meaning-এর সঙ্গে মিলে যাবে—এমন নয়।

Example:

```python
print("10" < "2")
```

Output:

```text
True
```

কারণ এখানে সংখ্যা হিসেবে নয়, string হিসেবে তুলনা করা হচ্ছে। `"1"` character, `"2"`-এর আগে আসে।

সংখ্যা হিসেবে তুলনা করতে হলে:

```python
print(int("10") < int("2"))
```

Output:

```text
False
```

## 13. Comparing Different Data Types

সব data type-কে সবসময় সরাসরি তুলনা করা যায় না।

### Number vs Number

```python
print(10 > 5)
```

Output:

```text
True
```

### String vs String

```python
print("apple" == "apple")
```

Output:

```text
True
```

### Number vs Numeric String

```python
print(10 == "10")
```

Output:

```text
False
```

কারণ integer `10` ও string `"10"` আলাদা type এবং equality comparison-এ তারা সমান নয়।

### Unsupported Ordering Comparison

```python
print(10 > "5")
```

Output:

```text
TypeError
```

Python 3-এ সাধারণ integer ও string-এর মধ্যে এভাবে বড়-ছোট তুলনা করা যায় না।

Correct approach:

```python
print(10 > int("5"))
```

Output:

```text
True
```

এখানে `"5"`-কে integer-এ convert করা হয়েছে।

## 14. Comparison Operators in Real-World Conditions

### 14.1 Exam Result

```python
marks = 85

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

Output:

```text
Pass
```

### 14.2 Minimum Purchase

```python
amount = 1500

if amount >= 1000:
    print("Eligible for offer")
else:
    print("Not eligible")
```

Output:

```text
Eligible for offer
```

### 14.3 Maximum Withdrawal

```python
balance = 5000
withdraw = 6000

if withdraw <= balance:
    print("Withdrawal allowed")
else:
    print("Insufficient balance")
```

Output:

```text
Insufficient balance
```

### 14.4 Checking a Specific Value

```python
status = "approved"

if status == "approved":
    print("Application accepted")
```

Output:

```text
Application accepted
```

### 14.5 Checking Whether a Value Is Different

```python
temperature = 25

if temperature != 0:
    print("Temperature is not zero")
```

Output:

```text
Temperature is not zero
```

## 15. Boundary Values: `>` vs `>=`

Condition লেখার সময় boundary value খুব গুরুত্বপূর্ণ।

ধরো, পাস করার জন্য অন্তত 40 নম্বর দরকার।

| Marks | `marks > 40` | `marks >= 40` |
|---:|---|---|
| 39 | `False` | `False` |
| 40 | `False` | `True` |
| 41 | `True` | `True` |

এখান থেকে বোঝা যায়, `>` এবং `>=`-এর পার্থক্য হলো সমান value গ্রহণ করা হচ্ছে কি না।

একইভাবে, সর্বোচ্চ 60 বয়স গ্রহণ করতে হলে `age <= 60` ব্যবহার করতে হবে; শুধু `age < 60` ব্যবহার করলে 60 বাদ পড়ে যাবে।

**Rule:** Requirement-এ “greater than or equal to”, “at least”, “minimum”—এ ধরনের শব্দ থাকলে সাধারণত `>=` প্রয়োজন। “less than or equal to”, “at most”, “maximum”—এ ধরনের শব্দ থাকলে সাধারণত `<=` প্রয়োজন।

## 16. Common Mistakes

### Mistake 1: Using `=` Instead of `==`

Incorrect:

```python
if marks = 40:
    print("Pass")
```

Correct:

```python
if marks == 40:
    print("Marks are exactly 40")
```

### Mistake 2: Choosing the Wrong Boundary Operator

Requirement: 40 বা তার বেশি হলে pass।

Incorrect:

```python
if marks > 40:
    print("Pass")
```

Correct:

```python
if marks >= 40:
    print("Pass")
```

### Mistake 3: Comparing String and Integer Incorrectly

```python
age = input("Enter age: ")

print(age >= 18)
```

এখানে সাধারণ numeric input দিলেও `TypeError` হবে, কারণ `age` string এবং `18` integer।

Correct:

```python
age = int(input("Enter age: "))

print(age >= 18)
```

### Mistake 4: Ignoring Case Sensitivity

```python
answer = "Yes"

print(answer == "yes")
```

Output:

```text
False
```

Case-insensitive comparison প্রয়োজন হলে:

```python
print(answer.lower() == "yes")
```

Output:

```text
True
```

### Mistake 5: Assuming Numeric Strings Are Compared Numerically

```python
print("100" < "20")
```

Output:

```text
True
```

এখানে string comparison হচ্ছে। Numeric comparison প্রয়োজন হলে value-গুলোকে সংখ্যায় convert করতে হবে।

## 17. Practice Exercises

প্রথমে নিজে solve করার চেষ্টা করো।

### Exercise 1: Predict the Output

```python
a = 15
b = 10

print(a > b)
print(a < b)
print(a == b)
print(a != b)
```

### Exercise 2: Boundary Check

```python
marks = 40

print(marks > 40)
print(marks >= 40)
```

Output কী হবে?

### Exercise 3: Minimum Age

User-এর কাছ থেকে age input নাও। বয়স 18 বা তার বেশি কি না, তা print করো।

### Exercise 4: Number Comparison

দুটি integer input নিয়ে প্রথমটি দ্বিতীয়টির চেয়ে ছোট কি না, তা print করো।

### Exercise 5: String Comparison

নিচের code-এর output predict করো:

```python
print("Python" == "python")
print("apple" != "orange")
print("10" < "2")
```

### Exercise 6: Find the Error

```python
age = input("Enter age: ")

if age >= 18:
    print("Eligible")
```

কেন error হবে এবং কীভাবে ঠিক করবে?

### Exercise 7: Maximum Limit

একটি `price` variable-এ 500 রাখো। `price` 500 বা তার কম কি না, তা পরীক্ষা করো।

### Exercise 8: Equality Check

User-এর কাছ থেকে একটি number input নাও। number-টি 100-এর সমান কি না, তা print করো।

## 18. Practice Answer Key

### Answer 1

```text
True
False
False
True
```

### Answer 2

```text
False
True
```

কারণ `40 > 40` মিথ্যা, কিন্তু `40 >= 40` সত্য।

### Answer 3

```python
age = int(input("Enter age: "))

print(age >= 18)
```

### Answer 4

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print(a < b)
```

### Answer 5

```text
False
True
True
```

### Answer 6

`input()` string return করে। তাই string-এর সঙ্গে integer-এর ordering comparison করলে `TypeError` হবে।

Correct code:

```python
age = int(input("Enter age: "))

if age >= 18:
    print("Eligible")
```

### Answer 7

```python
price = 500

print(price <= 500)
```

Output:

```text
True
```

### Answer 8

```python
number = int(input("Enter a number: "))

print(number == 100)
```

## 19. Chapter Summary

- Comparison Operators দুটি value-এর মধ্যে তুলনা করে।
- `==` সমান কি না পরীক্ষা করে।
- `!=` আলাদা কি না পরীক্ষা করে।
- `>` বড় এবং `<` ছোট কি না পরীক্ষা করে।
- `>=` বড় অথবা সমান এবং `<=` ছোট অথবা সমান কি না পরীক্ষা করে।
- `=` assignment-এর জন্য, আর `==` equality comparison-এর জন্য ব্যবহৃত হয়।
- Boundary value ঠিকভাবে handle করতে operator নির্বাচন গুরুত্বপূর্ণ।
- String comparison case-sensitive।
- Numeric string-কে number হিসেবে তুলনা করতে প্রয়োজন অনুযায়ী `int()` বা `float()` ব্যবহার করতে হয়।
- Comparison-এর result সাধারণত `True` অথবা `False` হয়।

## 20. Self-Assessment Checklist

- [ ] ছয়টি comparison operator-এর কাজ ব্যাখ্যা করতে পারি।
- [ ] `=` ও `==`-এর পার্থক্য বুঝি।
- [ ] `>` ও `>=`-এর পার্থক্য বুঝি।
- [ ] `<=` ও `<` সঠিকভাবে ব্যবহার করতে পারি।
- [ ] String ও number comparison-এর পার্থক্য বুঝি।
- [ ] Boundary value নিয়ে condition লিখতে পারি।
- [ ] User input নিয়ে comparison করতে পারি।
- [ ] Comparison-সংক্রান্ত সাধারণ error শনাক্ত করতে পারি।

## 21. Next Topic

পরবর্তী file:

`05_The_if_Statement.md`

সেখানে Python-এর `if` statement-এর syntax, execution flow, indentation এবং practical examples বিস্তারিতভাবে শেখা হবে।