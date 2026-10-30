# 07. Arithmetic Operator Examples and Edge Cases

## 1. Introduction

Python-এ Arithmetic Operators দিয়ে যোগ, বিয়োগ, গুণ, ভাগ, ভাগশেষ এবং Power নির্ণয় করা যায়। তবে কিছু ক্ষেত্রে Result আমাদের প্রত্যাশার থেকে আলাদা হতে পারে।

এ ধরনের বিশেষ পরিস্থিতিকে **Edge Case** বলা হয়।

উদাহরণ:

```python
print(10 / 3)
print(0.1 + 0.2)
print(-7 // 2)
```

Output:

```text
3.3333333333333335
0.30000000000000004
-4
```

এখানে:

- Division-এর Result-এ অনেক Decimal Digit দেখা যাচ্ছে।
- `0.1 + 0.2`-এর Result ঠিক `0.3` নয়।
- Negative Number-এর Floor Division Result `-4` হয়েছে।

এই ফাইলে আমরা এসব বিষয় বুঝব।

## 2. Integer Arithmetic

Python-এর Integer দিয়ে সাধারণ Arithmetic Calculation করা যায়।

```python
a = 20
b = 6

print(a + b)
print(a - b)
print(a * b)
print(a // b)
print(a % b)
print(a ** 2)
```

Output:

```text
26
14
120
3
2
400
```

Python-এর Integer-এর নির্দিষ্ট 32-bit বা 64-bit সীমা নেই। Memory-এর প্রাপ্যতা ও Python-এর বাস্তব সীমাবদ্ধতা অনুযায়ী Integer অনেক বড় হতে পারে।

Example:

```python
number = 2 ** 100

print(number)
```

Output:

```text
1267650600228229401496703205376
```

এত বড় Integer-ও Python হিসাব করতে পারে।

তবে খুব বড় Integer নিয়ে Calculation করলে বেশি Memory ও Processing Time লাগতে পারে।

## 3. Floating-Point Precision

Python-এ `float` সাধারণত Binary Floating-Point Representation ব্যবহার করে।

কিছু Decimal Number-কে Binary-তে ঠিকভাবে প্রকাশ করা যায় না। ফলে Calculation-এর সময় সামান্য Precision Difference দেখা দিতে পারে।

Example:

```python
print(0.1 + 0.2)
print(0.1 + 0.2 == 0.3)
```

Output:

```text
0.30000000000000004
False
```

কেন এমন হয়?

`0.1` এবং `0.2`-এর মতো কিছু Decimal Value Binary Floating-Point-এ সম্পূর্ণ নির্ভুলভাবে সংরক্ষণ করা যায় না। ফলে যোগ করার সময় খুব ছোট Difference তৈরি হয়।

### 3.1 Comparing Float Values Safely

Floating-Point Result সরাসরি `==` দিয়ে তুলনা করলে কিছু ক্ষেত্রে ভুল সিদ্ধান্ত হতে পারে।

এর পরিবর্তে `math.isclose()` ব্যবহার করা যায়।

```python
import math

a = 0.1 + 0.2
b = 0.3

print(math.isclose(a, b))
```

Output:

```text
True
```

`math.isclose()` দুটি Number নির্দিষ্ট Tolerance-এর মধ্যে যথেষ্ট কাছাকাছি কি না পরীক্ষা করে।

### 3.2 Using `round()`

Result-কে নির্দিষ্ট Decimal Place পর্যন্ত Round করা যায়।

```python
result = 0.1 + 0.2

print(round(result, 2))
```

Output:

```text
0.3
```

এখানে `round(result, 2)` Result-কে দুইটি Decimal Place পর্যন্ত Round করেছে।

**মনে রাখবে:** `round()` Display বা সাধারণ Calculation-এর জন্য উপকারী হলেও এটি সব Floating-Point Precision Problem দূর করে না।

## 4. Division by Zero

কোনো Number-কে Zero দিয়ে ভাগ করা যায় না।

Python-এ নিচের তিনটি Operation-ই Error তৈরি করে:

```python
print(10 / 0)
print(10 // 0)
print(10 % 0)
```

প্রথম Operation-এই `ZeroDivisionError` হবে। তাই সাধারণভাবে পরের দুটি Line Execute হবে না।

### 4.1 Handling Division by Zero

Division করার আগে Denominator পরীক্ষা করা যায়।

```python
a = 10
b = 0

if b != 0:
    print(a / b)
else:
    print("Cannot divide by zero.")
```

Output:

```text
Cannot divide by zero.
```

অথবা `try-except` ব্যবহার করা যায়।

```python
a = 10
b = 0

try:
    print(a / b)
except ZeroDivisionError:
    print("Cannot divide by zero.")
```

Output:

```text
Cannot divide by zero.
```

কোনো Calculation-এ Denominator Zero হতে পারে—এমন পরিস্থিতিতে Error Handling গুরুত্বপূর্ণ।

## 5. Negative Number Edge Cases

Negative Number নিয়ে `//` এবং `%` ব্যবহার করলে Python-এর Floor Division Rule মনে রাখতে হবে।

### 5.1 Floor Division

```python
print(7 // 2)
print(-7 // 2)
print(7 // -2)
print(-7 // -2)
```

Output:

```text
3
-4
-4
3
```

`-7 / 2` হলো `-3.5`। Floor Division নিচের পূর্ণসংখ্যা `-4` দেয়।

### 5.2 Modulo

```python
print(7 % 2)
print(-7 % 2)
print(7 % -2)
print(-7 % -2)
```

Output:

```text
1
1
-1
-1
```

Python-এ Modulo-এর Result সাধারণত Divisor-এর Sign অনুসরণ করে।

### 5.3 Quotient-Remainder Relationship

যদি `b` শূন্য না হয়, তাহলে:

\[
a = (a // b) \times b + (a \% b)
\]

Example:

```python
a = -7
b = 2

print(a // b)
print(a % b)
print((a // b) * b + (a % b))
```

Output:

```text
-4
1
-7
```

এই সম্পর্কটি Positive ও Negative—উভয় ধরনের Integer-এর ক্ষেত্রে গুরুত্বপূর্ণ।

## 6. Arithmetic with Different Numeric Types

Python-এ Integer এবং Float একসঙ্গে ব্যবহার করা যায়।

```python
a = 10
b = 2.5

print(a + b)
print(a * b)
print(a / b)
```

Output:

```text
12.5
25.0
4.0
```

এখানে Float-এর সঙ্গে Calculation করার ফলে Result-ও Float হয়েছে।

### 6.1 Incompatible Types

কিছু Data Type-এর মধ্যে Arithmetic Operation সরাসরি করা যায় না।

```python
number = 10
text = "5"

print(number + text)
```

এখানে `TypeError` হবে, কারণ Integer ও String সরাসরি যোগ করা যায় না।

সঠিকভাবে:

```python
number = 10
text = "5"

print(number + int(text))
```

Output:

```text
15
```

তবে সব String-কে Integer-এ Convert করা যায় না।

```python
print(int("hello"))
```

এখানে `ValueError` হবে।

## 7. Exponentiation Edge Cases

Exponentiation-এরও কিছু গুরুত্বপূর্ণ Edge Case রয়েছে।

### 7.1 Zero Exponent

```python
print(5 ** 0)
print(0 ** 0)
```

Output:

```text
1
1
```

Python-এ `0 ** 0`-এর Result `1`।

### 7.2 Negative Exponent

```python
print(2 ** -1)
print(2 ** -3)
```

Output:

```text
0.5
0.125
```

Negative Exponent-এর ক্ষেত্রে Result সাধারণত Reciprocal-এর Power হয়।

### 7.3 Zero with Negative Exponent

```python
print(0 ** -1)
```

এখানে `ZeroDivisionError` হবে।

### 7.4 Large Exponents

```python
number = 2 ** 100

print(number)
```

Python বড় Integer হিসাব করতে পারে। তবে অত্যন্ত বড় Power হিসাব করলে প্রচুর Memory ও Processing Time লাগতে পারে।

### 7.5 Negative Base and Fractional Exponent

```python
print((-1) ** 0.5)
```

Python একটি Complex Result দেয়, যা প্রায় `1j`-এর সমান।

Floating-Point Approximation-এর কারণে Result-এ খুব ছোট Real Part দেখা যেতে পারে।

Negative Base-এর Fractional Power সবসময় Real Number হয় না।

## 8. Operator Precedence in Arithmetic Expressions

একটি Expression-এ একাধিক Operator থাকলে Python নির্দিষ্ট Precedence অনুসরণ করে।

সাধারণ Arithmetic Expression-এ গুরুত্বপূর্ণ ক্রম:

1. Parentheses: `()`
2. Exponentiation: `**`
3. Unary Plus ও Minus: `+x`, `-x`
4. Multiplication, Division, Floor Division, Modulo: `*`, `/`, `//`, `%`
5. Addition ও Subtraction: `+`, `-`

এখানে `**` এবং Unary Operators-এর মধ্যে একটি বিশেষ নিয়ম আছে, তাই Negative Base-এর Power নির্ণয়ে Parentheses ব্যবহার করা ভালো।

Example:

```python
print(2 + 3 * 4)
print((2 + 3) * 4)
print(2 ** 3 * 2)
```

Output:

```text
14
20
16
```

ব্যাখ্যা:

- `2 + 3 * 4` → `2 + 12` → `14`
- `(2 + 3) * 4` → `5 * 4` → `20`
- `2 ** 3 * 2` → `8 * 2` → `16`

**Best Practice:** Expression জটিল হলে Parentheses ব্যবহার করো, যাতে Code সহজে বোঝা যায়।

## 9. Integer Division vs True Division

Python-এ `/` এবং `//`-এর কাজ আলাদা।

```python
print(8 / 4)
print(8 // 4)
```

Output:

```text
2.0
2
```

`/` হলো True Division, যা এখানে Float Result দিয়েছে।

`//` হলো Floor Division, যা এখানে Integer Result দিয়েছে।

### Practical Example

```python
total_marks = 85
subjects = 4

average = total_marks / subjects

print(average)
```

Output:

```text
21.25
```

Average হিসাব করতে সাধারণত `/` ব্যবহার করা হয়, কারণ Fractional Result প্রয়োজন হতে পারে।

## 10. Arithmetic Expressions in Real Programs

### 10.1 Shopping Bill

```python
price = 120
quantity = 3
discount = 50

total = price * quantity
final_price = total - discount

print("Total:", total)
print("Final Price:", final_price)
```

Output:

```text
Total: 360
Final Price: 310
```

### 10.2 Average Calculation

```python
mark1 = 80
mark2 = 75
mark3 = 90

average = (mark1 + mark2 + mark3) / 3

print("Average:", average)
```

Output:

```text
Average: 81.66666666666667
```

### 10.3 Time Conversion

মোট Seconds থেকে Minutes এবং Remaining Seconds বের করা:

```python
total_seconds = 367

minutes = total_seconds // 60
seconds = total_seconds % 60

print("Minutes:", minutes)
print("Seconds:", seconds)
```

Output:

```text
Minutes: 6
Seconds: 7
```

### 10.4 Compound Growth

```python
principal = 1000
rate = 0.05
periods = 3

amount = principal * (1 + rate) ** periods

print(round(amount, 2))
```

Output:

```text
1157.63
```

এখানে Compound Growth-এর সাধারণ Formula ব্যবহার করা হয়েছে।

## 11. Overflow and Very Large Numbers

Python-এর Integer Fixed-Size Integer নয়। তাই সাধারণ Integer Calculation-এ C বা Java-এর মতো নির্দিষ্ট Integer Width-এর কারণে একইভাবে Overflow হয় না।

Example:

```python
number = 10 ** 100

print(number)
```

Python বিশাল Integer হিসাব করতে পারে, যতক্ষণ প্রয়োজনীয় Resource ও Implementation Limits-এর মধ্যে থাকে।

তবে Float-এর Range সীমিত।

```python
number = 10.0 ** 1000

print(number)
```

এই Calculation-এ সাধারণত `OverflowError` হবে, কারণ Result Float-এর জন্য অত্যন্ত বড়।

**মনে রাখবে:**

- Integer অনেক বড় হতে পারে।
- Float-এর Range ও Precision সীমিত।
- অত্যন্ত বড় Calculation-এ Memory, Time এবং Numeric Limit বিবেচনা করতে হয়।

## 12. Floating-Point Values in Financial Calculations

সাধারণ Float দিয়ে টাকা বা Decimal Amount হিসাব করলে Precision সমস্যা দেখা দিতে পারে।

Example:

```python
price = 0.1
quantity = 3

total = price * quantity

print(total)
```

Output সাধারণত:

```text
0.30000000000000004
```

সাধারণ প্রদর্শনের জন্য:

```python
print(f"{total:.2f}")
```

Output:

```text
0.30
```

কিন্তু শুধু Display Round করলেই সব আর্থিক Calculation নির্ভুল হয়ে যায় না।

Decimal Arithmetic প্রয়োজন হলে `decimal.Decimal` ব্যবহার করা যেতে পারে।

```python
from decimal import Decimal

price = Decimal("0.10")
quantity = 3

total = price * quantity

print(total)
```

Output:

```text
0.30
```

`Decimal` ব্যবহার করার সময় Decimal Value-কে String থেকে তৈরি করা ভালো, যাতে শুরুতেই Binary Float-এর Approximation যুক্ত না হয়।

## 13. Common Mistakes

### Mistake 1: Using `^` Instead of `**`

```python
print(2 ^ 3)
print(2 ** 3)
```

Output:

```text
1
8
```

`^` হলো Bitwise XOR; `**` হলো Exponentiation।

### Mistake 2: Assuming Float Comparison Is Always Exact

```python
print(0.1 + 0.2 == 0.3)
```

Output:

```text
False
```

প্রয়োজনে `math.isclose()` ব্যবহার করো।

### Mistake 3: Forgetting Parentheses

```python
print(-3 ** 2)
print((-3) ** 2)
```

Output:

```text
-9
9
```

### Mistake 4: Dividing by Zero

`/`, `//` এবং `%`—কোনো ক্ষেত্রেই Divisor Zero হতে পারে না।

### Mistake 5: Assuming Integer and Float Behave Identically

Integer-এর Precision এবং Float-এর Precision এক নয়। বিশেষ করে Decimal Calculation-এ পার্থক্য দেখা দিতে পারে।

### Mistake 6: Assuming Python Integers Always Overflow at 32 Bits

Python Integer-এর Fixed 32-bit Limit নেই। তবে Memory ও Implementation Limits রয়েছে।

## 14. Practice Exercises

### Basic Level

1. `15 + 25 * 2`-এর Result বের করো।
2. `(-5) ** 2` এবং `-5 ** 2` তুলনা করো।
3. `17 // 4` এবং `17 % 4` Calculate করো।
4. `0.1 + 0.2 == 0.3` কেন `False` হয়, ব্যাখ্যা করো।
5. `2 ** 10` Calculate করো।

### Intermediate Level

6. 53 জন Student-কে প্রতি Group-এ 6 জন করে ভাগ করলে পূর্ণ Group এবং বাকি Student-এর সংখ্যা বের করো।
7. 245 Seconds-কে Minutes ও Remaining Seconds-এ রূপান্তর করো।
8. তিনটি Marks-এর Average Calculate করো।
9. `math.isclose()` দিয়ে দুটি Float কাছাকাছি কি না পরীক্ষা করো।
10. `Decimal` ব্যবহার করে `0.10`-এর তিনটি Item-এর Total Price বের করো।

### Output Prediction

```python
print(10 / 4)
print(10 // 4)
print(10 % 4)

print(-10 // 4)
print(-10 % 4)

print(0.1 + 0.2 == 0.3)
print(2 ** 3 ** 2)
```

### Solution

```text
2.5
2
2
-3
2
False
512
```

## 15. Chapter Summary

- Edge Case হলো এমন বিশেষ পরিস্থিতি, যেখানে Result বা Program Behaviour বুঝে নেওয়া জরুরি।
- Python Integer অনেক বড় Number ধারণ করতে পারে, তবে Resource সীমাবদ্ধতা রয়েছে।
- Float-এর Precision সীমিত; তাই কিছু Decimal Calculation-এ সামান্য Difference দেখা যায়।
- Float তুলনায় প্রয়োজনে `math.isclose()` ব্যবহার করা যায়।
- `/`, `//` ও `%`-এ Zero Divisor ব্যবহার করলে `ZeroDivisionError` হয়।
- Negative Number-এর Floor Division ও Modulo-এর নিয়ম গুরুত্বপূর্ণ।
- `Decimal` আর্থিক হিসাবের মতো ক্ষেত্রে উপকারী হতে পারে।
- Parentheses Expression-কে পরিষ্কার ও নির্ভুলভাবে বোঝাতে সাহায্য করে।
- Integer এবং Float-এর Numeric Behaviour এক নয়।

## 16. Self-Assessment Checklist

- [ ] Integer এবং Float-এর পার্থক্য বুঝি।
- [ ] Floating-Point Precision সমস্যা ব্যাখ্যা করতে পারি।
- [ ] `math.isclose()` ব্যবহার করতে পারি।
- [ ] Division by Zero সামলাতে পারি।
- [ ] Negative Number-এর `//` ও `%` বুঝি।
- [ ] Operator Precedence অনুযায়ী Expression Evaluate করতে পারি।
- [ ] Python Integer এবং Float-এর সীমাবদ্ধতা বুঝি।
- [ ] প্রয়োজন অনুযায়ী `Decimal` ব্যবহার করতে পারি।
- [ ] Arithmetic Operators দিয়ে বাস্তব Problem Solve করতে পারি।

**Next Topic:** `08_Comparison_Operators.md`