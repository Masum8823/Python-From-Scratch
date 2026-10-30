# 05. Floor Division and Modulo in Python

## 1. Introduction

Python-এ Division-সম্পর্কিত দুটি গুরুত্বপূর্ণ Operator হলো:

- `//` — Floor Division
- `%` — Modulo

Floor Division দিয়ে ভাগফলকে নিচের পূর্ণসংখ্যার দিকে নেওয়া হয়। অন্যদিকে, Modulo দিয়ে ভাগশেষ নির্ণয় করা হয়।

Example:

```python
print(17 // 5)
print(17 % 5)
```

Output:

```text
3
2
```

কারণ:

\[
17 = (5 \times 3) + 2
\]

এখানে:

- Quotient বা ভাগফল = `3`
- Remainder বা ভাগশেষ = `2`

## 2. Understanding Floor Division (`//`)

Floor Division দুটি Number ভাগ করে Result-কে নিচের পূর্ণসংখ্যার দিকে নিয়ে যায়।

Syntax:

```python
result = a // b
```

Example:

```python
print(17 // 5)
print(20 // 4)
print(25 // 6)
```

Output:

```text
3
5
4
```

ব্যাখ্যা:

| Expression | Division Result | Floor Division |
|---|---:|---:|
| `17 // 5` | `3.4` | `3` |
| `20 // 4` | `5.0` | `5` |
| `25 // 6` | `4.166...` | `4` |

এখানে `//` Result-এর চেয়ে ছোট বা সমান সবচেয়ে কাছের পূর্ণসংখ্যার দিকে যায়।

## 3. Floor Division with Negative Numbers

Negative Number-এর ক্ষেত্রে Floor Division বিশেষভাবে গুরুত্বপূর্ণ।

Python-এ Floor Division Zero-এর দিকে নয়, বরং Negative Infinity-এর দিকে Floor করে।

Example:

```python
print(-17 // 5)
print(17 // -5)
print(-17 // -5)
```

Output:

```text
-4
-4
3
```

কেন এমন হয়?

প্রথম Expression:

\[
-17 \div 5 = -3.4
\]

`-3.4`-এর চেয়ে ছোট পূর্ণসংখ্যা হলো `-4`।

তাই:

```python
print(-17 // 5)
```

Output:

```text
-4
```

দ্বিতীয় Expression:

\[
17 \div (-5) = -3.4
\]

এখানেও Floor Value হলো `-4`।

তৃতীয় Expression:

\[
-17 \div (-5) = 3.4
\]

এখানে Floor Value হলো `3`।

**মনে রাখবে:** Negative Result হলে `//` সাধারণত প্রচলিতভাবে শুধু দশমিক বাদ দেওয়ার মতো কাজ করে না; এটি নিচের পূর্ণসংখ্যার দিকে যায়।

## 4. Understanding Modulo (`%`)

Modulo Operator ভাগশেষ নির্ণয় করে।

Syntax:

```python
remainder = a % b
```

Example:

```python
print(17 % 5)
print(20 % 4)
print(25 % 6)
```

Output:

```text
2
0
1
```

ব্যাখ্যা:

- `17 % 5` → ভাগশেষ `2`
- `20 % 4` → ভাগশেষ `0`
- `25 % 6` → ভাগশেষ `1`

কোনো Number অন্য Number দিয়ে সম্পূর্ণ বিভাজ্য হলে Modulo Result `0` হয়।

## 5. Modulo with Negative Numbers

Python-এ Modulo-এর Result-এর Sign Divisor বা ভাগকের Sign-এর সঙ্গে সম্পর্কিত।

Example:

```python
print(-17 % 5)
print(17 % -5)
print(-17 % -5)
```

Output:

```text
3
-3
-2
```

এগুলো কীভাবে পাওয়া যায়?

### Case 1: `-17 % 5`

```python
print(-17 // 5)
print(-17 % 5)
```

Output:

```text
-4
3
```

সম্পর্কটি হলো:

\[
-17 = (5 \times -4) + 3
\]

তাই ভাগশেষ `3`।

### Case 2: `17 % -5`

```python
print(17 // -5)
print(17 % -5)
```

Output:

```text
-4
-3
```

কারণ:

\[
17 = (-5 \times -4) + (-3)
\]

তাই ভাগশেষ `-3`।

### Case 3: `-17 % -5`

```python
print(-17 // -5)
print(-17 % -5)
```

Output:

```text
3
-2
```

কারণ:

\[
-17 = (-5 \times 3) + (-2)
\]

তাই ভাগশেষ `-2`।

**গুরুত্বপূর্ণ নিয়ম:** Python-এর Modulo Result সাধারণত Divisor-এর Sign অনুসরণ করে। এটি সবসময় Positive হবে—এমন নয়।

## 6. The Relationship Between `//` and `%`

Python-এ Floor Division এবং Modulo-এর মধ্যে একটি গুরুত্বপূর্ণ সম্পর্ক রয়েছে।

\[
a = (a // b) \times b + (a \% b)
\]

এখানে:

- `a` = Dividend বা ভাজ্য
- `b` = Divisor বা ভাজক
- `a // b` = Floor Quotient বা পূর্ণ ভাগফল
- `a % b` = Remainder বা ভাগশেষ

এই সম্পর্কটি `b` শূন্য না হলে প্রযোজ্য।

### Example 1: Positive Numbers

```python
a = 17
b = 5

quotient = a // b
remainder = a % b

print(quotient)
print(remainder)
print(quotient * b + remainder)
```

Output:

```text
3
2
17
```

কারণ:

\[
(3 \times 5) + 2 = 17
\]

### Example 2: Negative Dividend

```python
a = -17
b = 5

quotient = a // b
remainder = a % b

print(quotient)
print(remainder)
print(quotient * b + remainder)
```

Output:

```text
-4
3
-17
```

কারণ:

\[
(-4 \times 5) + 3 = -17
\]

### Example 3: Negative Divisor

```python
a = 17
b = -5

quotient = a // b
remainder = a % b

print(quotient)
print(remainder)
print(quotient * b + remainder)
```

Output:

```text
-4
-3
17
```

কারণ:

\[
(-4 \times -5) + (-3) = 17
\]

## 7. Difference Between `/`, `//`, and `%`

| Operator | কাজ | Example | Result |
|---|---|---|---:|
| `/` | সাধারণ Division | `17 / 5` | `3.4` |
| `//` | Floor Division | `17 // 5` | `3` |
| `%` | Remainder | `17 % 5` | `2` |

আরও একটি Example:

```python
a = 17
b = 5

print(a / b)
print(a // b)
print(a % b)
```

Output:

```text
3.4
3
2
```

## 8. Integer and Float Behaviour

Floor Division ও Modulo Integer এবং Float—দুই ধরনের Number-এর সঙ্গে ব্যবহার করা যায়।

### Floor Division with Float

```python
print(17.0 // 5)
print(17 // 5.0)
```

Output:

```text
3.0
3.0
```

Operand-এর মধ্যে Float থাকলে Result-ও Float হতে পারে।

### Modulo with Float

```python
print(17.5 % 5)
print(10.5 % 2)
```

Output:

```text
2.5
0.5
```

Modulo শুধু Integer-এর জন্য নয়; Float-এর ক্ষেত্রেও ব্যবহার করা যায়।

তবে Floating-Point Number-এর সীমিত Precision-এর কারণে কিছু Result-এ ছোটখাটো Decimal Difference দেখা যেতে পারে।

## 9. Practical Use of Floor Division

### 9.1 Finding Complete Groups

ধরা যাক, 29 জন Student-কে প্রতি Group-এ 4 জন করে ভাগ করতে হবে।

```python
students = 29
group_size = 4

complete_groups = students // group_size

print("Complete Groups:", complete_groups)
```

Output:

```text
Complete Groups: 7
```

অর্থাৎ, 7টি পূর্ণ Group তৈরি হবে।

### 9.2 Converting Seconds into Minutes

```python
total_seconds = 185

minutes = total_seconds // 60

print("Minutes:", minutes)
```

Output:

```text
Minutes: 3
```

এখানে শুধু পূর্ণ মিনিট গণনা করা হয়েছে।

### 9.3 Finding the Number of Pages

প্রতি Page-এ 10টি প্রশ্ন রাখা যাবে। মোট প্রশ্ন 47টি হলে অন্তত কতটি পূর্ণ Page ব্যবহার করা যাবে?

```python
questions = 47
questions_per_page = 10

full_pages = questions // questions_per_page

print("Full Pages:", full_pages)
```

Output:

```text
Full Pages: 4
```

এখানে 4টি Page পূর্ণ হবে। বাকি 7টি প্রশ্নের জন্য আরেকটি Page প্রয়োজন হতে পারে।

## 10. Practical Use of Modulo

### 10.1 Checking Even and Odd Numbers

```python
number = 15

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

Output:

```text
Odd
```

যদি `number % 2 == 0` হয়, তাহলে Number-টি Even। অন্যথায় Odd।

### 10.2 Checking Divisibility

```python
number = 45

if number % 5 == 0:
    print("Divisible by 5")
else:
    print("Not divisible by 5")
```

Output:

```text
Divisible by 5
```

### 10.3 Extracting the Last Digit

কোনো Positive Integer-এর শেষ Digit বের করতে `% 10` ব্যবহার করা যায়।

```python
number = 5837

last_digit = number % 10

print(last_digit)
```

Output:

```text
7
```

কারণ, 5837-কে 10 দিয়ে ভাগ করলে ভাগশেষ `7`।

### 10.4 Extracting the Last Two Digits

```python
number = 45837

last_two_digits = number % 100

print(last_two_digits)
```

Output:

```text
37
```

### 10.5 Repeating a Cycle

ধরা যাক, 7 দিনের একটি Cycle-এর মধ্যে Day Index নির্ধারণ করতে হবে।

```python
day_index = 10

print(day_index % 7)
```

Output:

```text
3
```

Modulo বিভিন্ন ধরনের Repeating Cycle বা Circular Index হিসাব করতে কাজে লাগে। তবে Day Number `1` থেকে `7` হিসেবে দেখাতে চাইলে আলাদা Mapping প্রয়োজন হতে পারে।

## 11. Combining `//` and `%`

একটি Number-কে ভাগফল এবং ভাগশেষে ভাগ করতে দুটি Operator একসঙ্গে ব্যবহার করা যায়।

Example:

```python
number = 47
divisor = 10

quotient = number // divisor
remainder = number % divisor

print("Quotient:", quotient)
print("Remainder:", remainder)
```

Output:

```text
Quotient: 4
Remainder: 7
```

### Practical Challenge: Converting Seconds

মোট Seconds-কে Minutes ও Remaining Seconds-এ রূপান্তর করা যাক।

```python
total_seconds = 185

minutes = total_seconds // 60
seconds = total_seconds % 60

print("Minutes:", minutes)
print("Seconds:", seconds)
```

Output:

```text
Minutes: 3
Seconds: 5
```

কারণ, 185 Seconds হলো 3 Minutes এবং 5 Seconds।

### Practical Challenge: Counting Notes

ধরা যাক, 575 টাকা থেকে 100 টাকার সর্বোচ্চ কতটি Note নেওয়া যাবে এবং কত টাকা বাকি থাকবে।

```python
amount = 575

notes = amount // 100
remaining = amount % 100

print("100 Taka Notes:", notes)
print("Remaining Amount:", remaining)
```

Output:

```text
100 Taka Notes: 5
Remaining Amount: 75
```

## 12. Common Mistakes and Pitfalls

### Mistake 1: Thinking `//` Always Removes Decimal Digits

```python
print(-7 // 2)
```

Output:

```text
-4
```

এটি `-3` নয়, কারণ Floor Division নিচের পূর্ণসংখ্যার দিকে যায়।

### Mistake 2: Assuming Modulo Is Always Positive

```python
print(7 % -3)
```

Output:

```text
-2
```

Divisor Negative হলে Modulo Result-ও Negative হতে পারে।

### Mistake 3: Forgetting the Relationship

```python
a = 23
b = 4

print((a // b) * b + (a % b))
```

Output:

```text
23
```

`//` এবং `%`-এর Result দিয়ে মূল Dividend পুনরুদ্ধার করা যায়।

### Mistake 4: Using Zero as the Divisor

```python
print(10 // 0)
print(10 % 0)
```

এই Operations-এ `ZeroDivisionError` হবে। প্রথম Error ঘটলে সাধারণভাবে দ্বিতীয় Line-এ পৌঁছানো হবে না।

### Mistake 5: Confusing Modulo with Percentage

Python-এ `%` Operator সাধারণভাবে Remainder নির্ণয় করে। এটি নিজে থেকে Percentage Calculate করে না।

উদাহরণস্বরূপ, 200-এর 15% বের করতে:

```python
amount = 200
percentage = 15

result = amount * percentage / 100

print(result)
```

Output:

```text
30.0
```

## 13. Practice Exercises

### Basic Level

1. `19 // 4` এবং `19 % 4`-এর Result বের করো।
2. `30 // 7` এবং `30 % 7` Calculate করো।
3. `-19 // 4` এবং `-19 % 4`-এর Result বের করো।
4. `19 // -4` এবং `19 % -4` Calculate করো।
5. `-19 // -4` এবং `-19 % -4` Calculate করো।

### Intermediate Level

6. একটি Number 2 দিয়ে Divisible কি না পরীক্ষা করো।
7. একটি Number-এর শেষ Digit বের করো।
8. মোট Seconds-কে Minutes ও Remaining Seconds-এ রূপান্তর করো।
9. 53 জন Student-কে প্রতি Group-এ 6 জন করে ভাগ করলে পূর্ণ Group এবং বাকি Student-এর সংখ্যা বের করো।
10. একটি Amount-কে 100 টাকার Note এবং অবশিষ্ট টাকায় ভাগ করো।

### Output Prediction

নিচের Code-এর Output আগে নিজে বের করার চেষ্টা করো।

```python
print(23 // 5)
print(23 % 5)

print(-23 // 5)
print(-23 % 5)

print(23 // -5)
print(23 % -5)
```

### Solution

```text
4
3
-5
2
-5
-2
```

## 14. Chapter Summary

- `//` হলো Floor Division Operator।
- `%` হলো Modulo বা Remainder Operator।
- Floor Division Result-কে নিচের পূর্ণসংখ্যার দিকে নিয়ে যায়।
- Negative Number-এর ক্ষেত্রেও Floor Division-এর নিয়ম একইভাবে প্রযোজ্য।
- Python-এ Modulo Result সাধারণত Divisor-এর Sign অনুসরণ করে।
- `a = (a // b) * b + (a % b)` হলো Quotient-Remainder Relationship।
- `//` এবং `%` দিয়ে Group Counting, Even/Odd Checking, Digit Extraction ও Time Conversion করা যায়।
- Divisor শূন্য হলে `ZeroDivisionError` হয়।

## 15. Self-Assessment Checklist

- [ ] Floor Division এবং Modulo-এর পার্থক্য বুঝি।
- [ ] Positive Number-এর ভাগফল ও ভাগশেষ বের করতে পারি।
- [ ] Negative Number-এর ক্ষেত্রে Result ব্যাখ্যা করতে পারি।
- [ ] Quotient-Remainder Relationship ব্যবহার করতে পারি।
- [ ] `%` দিয়ে Even/Odd এবং Divisibility পরীক্ষা করতে পারি।
- [ ] `//` ও `%` দিয়ে Seconds Conversion করতে পারি।
- [ ] Zero Division-এর Error শনাক্ত করতে পারি।

**Next Topic:** `06_Exponentiation_Operator.md`