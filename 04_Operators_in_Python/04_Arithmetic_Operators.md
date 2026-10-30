# 04. Arithmetic Operators in Python

## 1. Introduction to Arithmetic Operators

Arithmetic Operators হলো Python-এর এমন Operators, যেগুলো ব্যবহার করে Mathematical Calculation করা হয়।

যেমন:

- Addition
- Subtraction
- Multiplication
- Division
- Floor Division
- Modulo
- Exponentiation

Example:

```python
a = 10
b = 3

print(a + b)
print(a - b)
print(a * b)
```

Output:

```text
13
7
30
```

এখানে `+`, `-` এবং `*` হলো Arithmetic Operators।

## 2. List of Arithmetic Operators

Python-এর প্রধান Arithmetic Operators:

| Operator | Name | কাজ |
|---|---|---|
| `+` | Addition | যোগ করা |
| `-` | Subtraction | বিয়োগ করা |
| `*` | Multiplication | গুণ করা |
| `/` | Division | ভাগ করা |
| `//` | Floor Division | ভাগফলকে নিচের পূর্ণসংখ্যার দিকে নেওয়া |
| `%` | Modulo | ভাগশেষ নির্ণয় করা |
| `**` | Exponentiation | Power বা ঘাত নির্ণয় করা |

এখন প্রতিটি Operator আলাদাভাবে দেখা যাক।

## 3. Addition Operator (`+`)

Addition Operator দুটি Number যোগ করতে ব্যবহার করা হয়।

Syntax:

```python
result = a + b
```

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

### Practical Example

একজন Student দুটি পরীক্ষায় যথাক্রমে 35 এবং 40 Marks পেয়েছে।

```python
midterm_marks = 35
final_marks = 40

total_marks = midterm_marks + final_marks

print("Total Marks:", total_marks)
```

Output:

```text
Total Marks: 75
```

### Addition with Strings

Python-এ `+` Operator দিয়ে দুটি String যুক্ত করা যায়। একে **String Concatenation** বলে।

```python
first_name = "Abdulla"
last_name = "Masum"

full_name = first_name + " " + last_name

print(full_name)
```

Output:

```text
Abdulla Masum
```

**মনে রাখবে:** String এবং Integer সরাসরি `+` দিয়ে যোগ করা যায় না।

```python
print("Age: " + 22)
```

এখানে `TypeError` হবে।

সঠিকভাবে:

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

## 4. Subtraction Operator (`-`)

Subtraction Operator একটি Number থেকে অন্য Number বিয়োগ করতে ব্যবহার করা হয়।

Syntax:

```python
result = a - b
```

Example:

```python
a = 50
b = 20

print(a - b)
```

Output:

```text
30
```

### Practical Example

একটি Product-এর Price 1000 টাকা এবং Discount 150 টাকা।

```python
price = 1000
discount = 150

final_price = price - discount

print("Final Price:", final_price)
```

Output:

```text
Final Price: 850
```

### Unary Minus

`-` Operator একটি Number-এর Sign পরিবর্তন করতেও ব্যবহার করা হয়।

```python
number = 10

print(-number)
```

Output:

```text
-10
```

এখানে `-number` একটি Unary Operation।

## 5. Multiplication Operator (`*`)

Multiplication Operator দুটি Number গুণ করতে ব্যবহার করা হয়।

Syntax:

```python
result = a * b
```

Example:

```python
a = 10
b = 5

print(a * b)
```

Output:

```text
50
```

### Practical Example

একটি Notebook-এর দাম 80 টাকা। 5টি Notebook-এর মোট দাম:

```python
price = 80
quantity = 5

total_price = price * quantity

print("Total Price:", total_price)
```

Output:

```text
Total Price: 400
```

### Multiplication with Strings

String-এর সঙ্গে Integer ব্যবহার করে String Repeat করা যায়।

```python
print("Python " * 3)
```

Output:

```text
Python Python Python
```

এখানে String তিনবার Repeat হয়েছে।

**Note:** Negative বা Zero Repetition Count দিলে String-এর Result Empty হতে পারে।

```python
print("Python" * 0)
```

Output:

```text
```

## 6. Division Operator (`/`)

Division Operator একটি Number-কে অন্য Number দিয়ে ভাগ করে।

Syntax:

```python
result = a / b
```

Example:

```python
a = 10
b = 2

print(a / b)
```

Output:

```text
5.0
```

**Important:** Python-এ দুটি Integer ভাগ করলেও `/` Operator সাধারণত `float` Result দেয়।

```python
print(10 / 3)
```

Output:

```text
3.3333333333333335
```

### Practical Example

একটি Amount চারজনের মধ্যে সমানভাবে ভাগ করা হবে।

```python
total_amount = 1000
people = 4

share = total_amount / people

print("Each Person Gets:", share)
```

Output:

```text
Each Person Gets: 250.0
```

### Division by Zero

কোনো Number-কে Zero দিয়ে ভাগ করা যায় না।

```python
print(10 / 0)
```

এখানে `ZeroDivisionError` হবে।

Zero দিয়ে ভাগ করার আগে প্রয়োজন অনুযায়ী Denominator পরীক্ষা করা উচিত।

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

## 7. Floor Division Operator (`//`)

Floor Division Operator ভাগ করার পর Result-কে নিচের পূর্ণসংখ্যার দিকে নিয়ে যায়।

Syntax:

```python
result = a // b
```

Example:

```python
print(10 // 3)
```

Output:

```text
3
```

কারণ:

\[
10 \div 3 = 3.333\ldots
\]

Floor Division Result:

\[
10 // 3 = 3
\]

### Important: Floor Means Toward Negative Infinity

Floor Division সবসময় Zero-এর দিকে Round করে না। এটি Result-এর চেয়ে ছোট বা সমান সবচেয়ে কাছের Integer-এর দিকে যায়।

Example:

```python
print(10 // 3)
print(-10 // 3)
```

Output:

```text
3
-4
```

কারণ:

\[
-10 \div 3 = -3.333\ldots
\]

এই মানের চেয়ে ছোট পূর্ণসংখ্যা হলো `-4`।

**মনে রাখবে:** `int(-10 / 3)` করলে `-3` পাওয়া যাবে, কিন্তু `-10 // 3` করলে `-4` পাওয়া যাবে।

### Floor Division with Float

```python
print(10.0 // 3)
```

Output:

```text
3.0
```

Operand-এর Type অনুযায়ী Floor Division-এর Result `float`-ও হতে পারে।

### Practical Example

একটি ক্লাসে 23 জন Student আছে। প্রতি Bench-এ 4 জন বসতে পারে।

পূর্ণ Bench কয়টি হবে?

```python
students = 23
capacity = 4

full_benches = students // capacity

print("Full Benches:", full_benches)
```

Output:

```text
Full Benches: 5
```

এখানে 5টি পূর্ণ Bench হবে, আর 3 জন Student বাকি থাকবে।

## 8. Modulo Operator (`%`)

Modulo Operator Division-এর Remainder বা ভাগশেষ নির্ণয় করতে ব্যবহার করা হয়।

Syntax:

```python
remainder = a % b
```

Example:

```python
print(10 % 3)
```

Output:

```text
1
```

কারণ:

\[
10 = (3 \times 3) + 1
\]

তাই Remainder হলো `1`।

### Practical Example: Even or Odd

কোনো Integer জোড় না বিজোড়, তা পরীক্ষা করতে `%` ব্যবহার করা যায়।

```python
number = 10

if number % 2 == 0:
    print("Even Number")
else:
    print("Odd Number")
```

Output:

```text
Even Number
```

কারণ Even Number-কে 2 দিয়ে ভাগ করলে Remainder `0` হয়।

### Practical Example: Divisibility

একটি Number 5 দিয়ে বিভাজ্য কি না পরীক্ষা:

```python
number = 25

if number % 5 == 0:
    print("Divisible by 5")
else:
    print("Not divisible by 5")
```

Output:

```text
Divisible by 5
```

### Modulo with Negative Numbers

Python-এ Modulo-এর Result-এর Sign Divisor-এর Sign-এর সঙ্গে সম্পর্কিত।

```python
print(10 % 3)
print(-10 % 3)
print(10 % -3)
print(-10 % -3)
```

Output:

```text
1
2
-2
-1
```

Python-এর জন্য সাধারণ সম্পর্কটি হলো:

\[
a = (a // b) \times b + (a \% b)
\]

যেখানে `b` শূন্য নয়।

**Important:** Modulo Operator-এও Divisor Zero হলে `ZeroDivisionError` হবে।

## 9. Exponentiation Operator (`**`)

Exponentiation Operator কোনো Number-এর Power বা ঘাত নির্ণয় করে।

Syntax:

```python
result = base ** exponent
```

Example:

```python
print(2 ** 3)
```

Output:

```text
8
```

কারণ:

\[
2^3 = 2 \times 2 \times 2 = 8
\]

### More Examples

```python
print(5 ** 2)
print(10 ** 3)
print(9 ** 0)
print(16 ** 0.5)
```

Output:

```text
25
1000
1
4.0
```

### Practical Example: Area of a Square

একটি Square-এর প্রতিটি বাহুর দৈর্ঘ্য 5।

```python
side = 5

area = side ** 2

print("Area:", area)
```

Output:

```text
Area: 25
```

### Exponentiation with Negative Numbers

```python
print((-2) ** 2)
print(-2 ** 2)
```

Output:

```text
4
-4
```

দ্বিতীয় Expression-এ Exponentiation-এর Precedence Unary Minus-এর চেয়ে বেশি। তাই `-2 ** 2` হলো `-(2 ** 2)`।

**মনে রাখবে:** Negative Base-এর Square করতে Parentheses ব্যবহার করো: `(-2) ** 2`।

## 10. Arithmetic Operators Together

একটি Expression-এ একাধিক Arithmetic Operator ব্যবহার করা যায়।

```python
result = 10 + 5 * 2 - 8 / 4

print(result)
```

Output:

```text
18.0
```

Evaluation:

1. `5 * 2 = 10`
2. `8 / 4 = 2.0`
3. `10 + 10 - 2.0 = 18.0`

এখানে `*` এবং `/` আগে Evaluate হয়েছে।

Operator Precedence-এর বিস্তারিত আলোচনা পরবর্তী Topics-এ করা হবে।

## 11. Practical Calculator Program

নিচের Program-এ কয়েকটি Arithmetic Operation একসঙ্গে দেখানো হয়েছে।

```python
a = 20
b = 6

print("Addition:", a + b)
print("Subtraction:", a - b)
print("Multiplication:", a * b)
print("Division:", a / b)
print("Floor Division:", a // b)
print("Modulo:", a % b)
print("Exponentiation:", a ** b)
```

Output:

```text
Addition: 26
Subtraction: 14
Multiplication: 120
Division: 3.3333333333333335
Floor Division: 3
Modulo: 2
Exponentiation: 64000000
```

এই Program-এর মাধ্যমে সব প্রধান Arithmetic Operator-এর Result একসঙ্গে দেখা যায়।

## 12. Common Mistakes

### Mistake 1: Confusing `/` and `//`

```python
print(7 / 2)
print(7 // 2)
```

Output:

```text
3.5
3
```

`/` Division করে এবং `//` Floor Division করে।

### Mistake 2: Assuming `%` Always Gives a Positive Result

```python
print(-10 % 3)
```

Output:

```text
2
```

Negative Number-এর ক্ষেত্রে Python-এর Modulo Behaviour মনে রাখতে হবে।

### Mistake 3: Dividing by Zero

```python
print(5 / 0)
```

এখানে `ZeroDivisionError` হবে।

### Mistake 4: Ignoring Operator Precedence

```python
print(2 + 3 * 4)
```

Output:

```text
14
```

Output `20` নয়, কারণ Multiplication আগে হয়।

### Mistake 5: Forgetting Parentheses with Negative Powers

```python
print(-3 ** 2)
print((-3) ** 2)
```

Output:

```text
-9
9
```

## 13. Practice Exercises

### Basic Level

1. `25 + 15`-এর Result বের করো।
2. `100 - 35` Calculate করো।
3. `12 * 8` Calculate করো।
4. `25 / 4` এবং `25 // 4`-এর Result বের করো।
5. `25 % 4`-এর Result বের করো।
6. `3 ** 4` Calculate করো।
7. `-15 // 4` এবং `-15 % 4`-এর Result বের করো।

### Intermediate Level

8. একটি Number Even না Odd নির্ণয় করো।
9. একটি Number 3 এবং 5—উভয় দিয়ে Divisible কি না পরীক্ষা করো।
10. Total Price থেকে Discount বাদ দিয়ে Final Price বের করো।
11. একটি Amount নির্দিষ্ট সংখ্যক মানুষের মধ্যে ভাগ করলে প্রত্যেকে কত পাবে, তা বের করো।
12. একটি Integer-এর শেষ Digit `% 10` ব্যবহার করে বের করো।
13. `2 + 3 * 4 ** 2`-এর Result নির্ণয় করো।
14. `-2 ** 3` এবং `(-2) ** 3` তুলনা করো।

### Practical Challenge

একটি Simple Shopping Bill Program তৈরি করো।

Requirements:

1. একটি Product-এর Unit Price নির্ধারণ করো।
2. Quantity নির্ধারণ করো।
3. `*` দিয়ে Total Price হিসাব করো।
4. Discount Amount বিয়োগ করো।
5. Final Price Print করো।
6. Total Price কয়েকজনের মধ্যে সমানভাবে ভাগ করলে প্রত্যেকের Share বের করো।
7. Division করার আগে Denominator শূন্য কি না পরীক্ষা করো।

## 14. Chapter Summary

- `+` দিয়ে Number যোগ এবং String Concatenation করা যায়।
- `-` দিয়ে Subtraction ও Unary Negation করা যায়।
- `*` দিয়ে Multiplication ও String Repetition করা যায়।
- `/` দিয়ে Division করা হয়; Result সাধারণত `float` হয়।
- `//` Floor Division করে, যা Negative Value-এর ক্ষেত্রেও গুরুত্বপূর্ণ।
- `%` Remainder নির্ণয় করে।
- `**` Exponentiation বা Power হিসাব করে।
- Arithmetic Expression-এর Result নির্ণয়ে Operator Precedence গুরুত্বপূর্ণ।
- Division এবং Modulo-তে Zero Divisor ব্যবহার করা যায় না।

## 15. Self-Assessment Checklist

- [ ] সাতটি প্রধান Arithmetic Operator চিনতে পারি।
- [ ] Addition, Subtraction এবং Multiplication করতে পারি।
- [ ] Division ও Floor Division-এর পার্থক্য বুঝি।
- [ ] Modulo দিয়ে Even/Odd পরীক্ষা করতে পারি।
- [ ] Exponentiation ব্যবহার করতে পারি।
- [ ] Negative Number-এর Floor Division ও Modulo বুঝি।
- [ ] Operator Precedence-এর Basic নিয়ম বুঝি।
- [ ] Division by Zero-এর Error শনাক্ত করতে পারি।
- [ ] Arithmetic Operators দিয়ে ছোট Program তৈরি করতে পারি।

**Next Topic:** `05_Floor_Division_and_Modulo.md`