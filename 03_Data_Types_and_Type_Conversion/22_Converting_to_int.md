# 22. Converting to `int()` in Python

## 1. Introduction to `int()`

Python-এ `int()` হলো একটি built-in function, যা উপযুক্ত value-কে Integer-এ রূপান্তর করে।

Integer হলো এমন পূর্ণসংখ্যা, যার কোনো fractional বা decimal অংশ নেই। যেমন: `10`, `-5`, `0`, `250`।

Example:

```python
number = int("100")

print(number)
print(type(number))
```

Output:

```text
100
<class 'int'>
```

এখানে `"100"` ছিল String। `int()` এটিকে Integer `100`-এ রূপান্তর করেছে।

## 2. Syntax of `int()`

`int()` function-এর সাধারণ syntax:

```python
int(value)
```

এখানে `value` হলো যে value-টিকে Integer-এ রূপান্তর করতে চাই।

String-এর ক্ষেত্রে base উল্লেখ করা যায়:

```python
int(string, base)
```

এখানে:

- `string` হলো যে String-টিকে Integer-এ রূপান্তর করা হবে।
- `base` হলো কোন number system অনুযায়ী String-টিকে পড়তে হবে।

`base`-এর বিস্তারিত ব্যবহার এই ফাইলের পরের অংশে রয়েছে।

## 3. Converting String to Integer

যদি String-এ valid Integer representation থাকে, তাহলে `int()` সেটিকে Integer-এ রূপান্তর করতে পারে।

Example:

```python
a = int("25")
b = int("-10")
c = int("0")

print(a)
print(b)
print(c)
```

Output:

```text
25
-10
0
```

এখানে positive, negative এবং zero—তিন ধরনের Integer representation-ই convert হয়েছে।

### 3.1 String with Leading Zeros

```python
number = int("007")

print(number)
print(type(number))
```

Output:

```text
7
<class 'int'>
```

Integer value-এ leading zeros সংরক্ষিত থাকে না।

যদি `"007"`-এর মতো formatting সংরক্ষণ করতে চাও, তাহলে value-টিকে String হিসেবেই রাখতে হবে।

### 3.2 String with Surrounding Spaces

`int()` String-এর শুরু ও শেষের whitespace উপেক্ষা করতে পারে।

```python
number = int("  123  ")

print(number)
```

Output:

```text
123
```

তবে মাঝখানে অপ্রত্যাশিত whitespace থাকলে conversion ব্যর্থ হতে পারে।

```python
number = int("12 3")
```

এটি `ValueError` তৈরি করবে।

## 4. Converting Float to Integer

`int()` Float-কে Integer-এ রূপান্তর করার সময় decimal বা fractional অংশ বাদ দেয়।

এটি **truncation toward zero** নামে পরিচিত।

Example:

```python
print(int(12.9))
print(int(12.1))
print(int(-12.9))
print(int(-12.1))
```

Output:

```text
12
12
-12
-12
```

লক্ষ্য করো, negative সংখ্যার ক্ষেত্রেও value শূন্যের দিকে truncation করা হয়েছে।

### 4.1 `int()` Does Not Round

অনেক beginner মনে করে `int(12.9)` করলে `13` পাওয়া যাবে। কিন্তু এটি সঠিক নয়।

```python
print(int(12.9))
print(round(12.9))
```

Output:

```text
12
13
```

এখানে:

- `int()` fractional অংশ বাদ দেয়।
- `round()` rounding করে।

আরও একটি বিষয়: Python-এর `round()` সাধারণত ঠিক মাঝামাঝি অবস্থায় nearest even number-এর নিয়ম অনুসরণ করে।

```python
print(round(2.5))
print(round(3.5))
```

Output:

```text
2
4
```

তাই rounding প্রয়োজন হলে `int()`-এর পরিবর্তে উপযুক্ত rounding method ব্যবহার করতে হবে।

## 5. Converting Boolean to Integer

Python-এ `bool` হলো `int`-এর subclass।

তাই:

- `True`-কে `1` হিসেবে convert করা যায়।
- `False`-কে `0` হিসেবে convert করা যায়।

Example:

```python
print(int(True))
print(int(False))
```

Output:

```text
1
0
```

এটি Boolean value-কে numeric representation-এ রূপান্তর করার একটি উদাহরণ।

## 6. Converting Other Numeric Values

`int()`-এর আচরণ source data type-এর ওপর নির্ভর করে।

### 6.1 Integer to Integer

```python
number = int(50)

print(number)
```

Output:

```text
50
```

Value আগে থেকেই Integer হলে সেটির Integer value-ই পাওয়া যায়।

### 6.2 Float to Integer

```python
number = int(7.99)

print(number)
```

Output:

```text
7
```

Fractional অংশ বাদ গেছে।

### 6.3 Complex to Integer

```python
number = int(3 + 2j)
```

এটি `TypeError` তৈরি করবে।

Python সরাসরি Complex number-কে Integer-এ convert করে না। যদি বাস্তব অংশ প্রয়োজন হয়, তাহলে `.real` ব্যবহার করা যায়:

```python
number = int((3 + 2j).real)

print(number)
```

Output:

```text
3
```

এখানে Complex number-এর imaginary অংশ ইচ্ছাকৃতভাবে বাদ দেওয়া হয়েছে। তাই এই পদ্ধতি ব্যবহার করার আগে নিশ্চিত হতে হবে যে imaginary অংশ উপেক্ষা করা গ্রহণযোগ্য।

## 7. Using `int()` with Different Number Systems

Python-এ Integer বিভিন্ন number system-এ প্রকাশ করা যায়:

- Decimal — Base 10
- Binary — Base 2
- Octal — Base 8
- Hexadecimal — Base 16

`int()`-এর `base` parameter ব্যবহার করে এই number system-গুলোর String-কে Integer-এ convert করা যায়।

### 7.1 Binary to Integer

Binary number-এ `0` এবং `1` ব্যবহার করা হয়।

```python
number = int("1010", 2)

print(number)
```

Output:

```text
10
```

এখানে `"1010"`-কে Binary হিসেবে পড়া হয়েছে। এর Decimal value হলো `10`।

### 7.2 Octal to Integer

Octal number-এ `0` থেকে `7` পর্যন্ত digit থাকে।

```python
number = int("17", 8)

print(number)
```

Output:

```text
15
```

কারণ:

\[
1 \times 8^1 + 7 \times 8^0 = 15
\]

### 7.3 Hexadecimal to Integer

Hexadecimal-এ `0–9` এবং `A–F` ব্যবহার করা হয়।

```python
number = int("FF", 16)

print(number)
```

Output:

```text
255
```

এখানে `F`-এর value `15`।

### 7.4 Decimal to Integer

Decimal হলো সাধারণ Base 10 number system।

```python
number = int("125", 10)

print(number)
```

Output:

```text
125
```

### 7.5 Number System Conversion Summary

| Expression | Result | Explanation |
|---|---:|---|
| `int("1010", 2)` | `10` | Binary to Decimal |
| `int("17", 8)` | `15` | Octal to Decimal |
| `int("FF", 16)` | `255` | Hexadecimal to Decimal |
| `int("125", 10)` | `125` | Decimal to Integer |

**Important:** `base` parameter ব্যবহার করলে প্রথম argument অবশ্যই String হতে হবে।

Incorrect:

```python
int(1010, 2)
```

এটি `TypeError` তৈরি করবে।

Correct:

```python
int("1010", 2)
```

## 8. Valid Base Values

`int(string, base)`-এর ক্ষেত্রে `base` সাধারণত `2` থেকে `36`-এর মধ্যে হতে পারে। এছাড়া `base=0` ব্যবহার করে কিছু recognized prefix থেকে base নির্ধারণ করানো যায়।

উদাহরণ:

```python
print(int("101", 2))
print(int("17", 8))
print(int("25", 10))
print(int("1A", 16))
```

Output:

```text
5
15
25
26
```

### Using `base=0`

```python
print(int("0b1010", 0))
print(int("0o17", 0))
print(int("0xFF", 0))
```

Output:

```text
10
15
255
```

এখানে prefix-গুলো হলো:

- `0b` — Binary
- `0o` — Octal
- `0x` — Hexadecimal

`base=0`-এর ক্ষেত্রে String-এর prefix ও formatting valid হতে হবে। এটি যেকোনো String-এর base নিজে থেকে অনুমান করতে পারে না।

## 9. Converting User Input to Integer

`input()` সব সময় String return করে। তাই Integer input প্রয়োজন হলে `int()` ব্যবহার করা যায়।

```python
age = int(input("Enter your age: "))

print(age)
print(type(age))
```

Input:

```text
22
```

Output:

```text
22
<class 'int'>
```

### 9.1 Addition of Two User Inputs

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print("Sum:", a + b)
```

Input:

```text
10
20
```

Output:

```text
Sum: 30
```

### 9.2 Handling Invalid Input

User সব সময় valid Integer দেবে—এমন নিশ্চয়তা নেই।

```python
text = input("Enter an integer: ")

try:
    number = int(text)
    print("Number:", number)
except ValueError:
    print("Invalid integer input.")
```

Input:

```text
hello
```

Output:

```text
Invalid integer input.
```

এখানে `try` এবং `except` invalid input-এর কারণে program বন্ধ হয়ে যাওয়া থেকে রক্ষা করে।

Exception Handling অধ্যায়ে এই বিষয়টি বিস্তারিত শেখা হবে।

## 10. Common Errors with `int()`

### 10.1 `ValueError`

যখন String-টি valid Integer representation নয়, তখন `ValueError` হতে পারে।

```python
int("hello")
```

কারণ `"hello"`-কে Integer হিসেবে পড়া যায় না।

### 10.2 Decimal String

```python
int("12.5")
```

এটি `ValueError` তৈরি করবে।

কারণ `"12.5"` একটি decimal String, Integer String নয়।

Correct:

```python
print(int(float("12.5")))
```

Output:

```text
12
```

প্রথমে String-কে Float এবং পরে Integer-এ convert করা হয়েছে।

### 10.3 Invalid Base

```python
int("102", 2)
```

এটি `ValueError` তৈরি করবে, কারণ Binary number-এ `2` digit ব্যবহার করা যায় না।

### 10.4 Invalid Base Range

```python
int("10", 1)
```

এটি `ValueError` তৈরি করবে, কারণ `base=1` valid নয়।

### 10.5 Passing `None`

```python
int(None)
```

এটি `TypeError` তৈরি করবে। কারণ `None` সরাসরি Integer-এ convert করার উপযুক্ত value নয়।

## 11. `int()` vs `float()` vs `round()`

এই তিনটি function-এর পার্থক্য বুঝতে হবে।

| Expression | Result | Reason |
|---|---:|---|
| `int(8.9)` | `8` | Fractional অংশ বাদ |
| `float(8)` | `8.0` | Float-এ conversion |
| `round(8.9)` | `9` | Nearest integer-এ rounding |
| `int(-8.9)` | `-8` | শূন্যের দিকে truncation |
| `round(2.5)` | `2` | Nearest even rule |
| `round(3.5)` | `4` | Nearest even rule |

কোন function ব্যবহার করবে, তা নির্ভর করবে তোমার প্রয়োজনের ওপর।

- Decimal অংশ বাদ দিতে → `int()`
- Floating-point number পেতে → `float()`
- Rounding করতে → `round()`

## 12. Practical Examples

### Example 1: Age Next Year

```python
age = int(input("Enter your age: "))

next_year_age = age + 1

print("Next year, you will be", next_year_age)
```

### Example 2: Convert Binary to Decimal

```python
binary = input("Enter a binary number: ")

decimal = int(binary, 2)

print("Decimal value:", decimal)
```

Input:

```text
1101
```

Output:

```text
Decimal value: 13
```

এই example-এ user-এর input valid Binary String হতে হবে।

### Example 3: Calculate Total Items

```python
apples = int(input("Enter number of apples: "))
oranges = int(input("Enter number of oranges: "))

total = apples + oranges

print("Total fruits:", total)
```

### Example 4: Convert Float Input to Integer

```python
price = float(input("Enter a price: "))

whole_number = int(price)

print("Original price:", price)
print("Integer part:", whole_number)
```

Input:

```text
125.75
```

Output:

```text
Original price: 125.75
Integer part: 125
```

এখানে Integer conversion-এর কারণে fractional অংশ বাদ গেছে।

## 13. Practice Exercises

### Exercise 1: Basic Conversion

নিচের String-গুলোকে Integer-এ convert করো:

```python
a = "100"
b = "-50"
c = "0"
```

প্রতিটি result-এর type পরীক্ষা করো।

### Exercise 2: Float Conversion

নিচের expression-গুলোর output অনুমান করো:

```python
print(int(9.99))
print(int(-9.99))
print(int(0.75))
print(int(-0.75))
```

### Exercise 3: Boolean Conversion

```python
print(int(True))
print(int(False))
```

Output ব্যাখ্যা করো।

### Exercise 4: Binary to Decimal

নিচের Binary String-গুলোকে Decimal Integer-এ convert করো:

```python
print(int("101", 2))
print(int("1111", 2))
print(int("10000", 2))
```

### Exercise 5: Hexadecimal to Decimal

```python
print(int("A", 16))
print(int("10", 16))
print(int("FF", 16))
```

### Exercise 6: Identify Errors

নিচের প্রতিটি expression কেন error তৈরি করে, তা ব্যাখ্যা করো:

```python
int("Python")
int("12.5")
int("102", 2)
int(None)
```

### Exercise 7: User Input Calculator

User-এর কাছ থেকে দুটি Integer নিয়ে নিচের তথ্য দেখাও:

- Sum
- Difference
- Product
- Division

Division-এর ক্ষেত্রে zero দিয়ে ভাগ করার সম্ভাবনা বিবেচনা করো।

### Exercise 8: Number System Converter

একটি program তৈরি করো, যেখানে user একটি Binary String দেবে এবং program সেটিকে Decimal Integer-এ convert করে দেখাবে।

### Exercise 9: Truncation vs Rounding

`12.7`, `12.3`, `-12.7` এবং `-12.3`-এর জন্য `int()` ও `round()`-এর result তুলনা করো।

### Exercise 10: Mini Project — Multi-Base Converter

একটি program তৈরি করো, যেখানে user একটি valid number String এবং তার base দেবে। Program-টি সেই number-কে Decimal Integer-এ convert করবে।

Base হিসেবে `2`, `8`, `10` অথবা `16` support করো।

## 14. Key Takeaways

- `int()` উপযুক্ত value-কে Integer-এ convert করে।
- Float থেকে Integer conversion করলে fractional অংশ শূন্যের দিকে truncation হয়।
- `int()` সাধারণ rounding করে না।
- `True` Integer `1` এবং `False` Integer `0`-এ convert হয়।
- `int(string, base)` দিয়ে Binary, Octal ও Hexadecimal String-কে Integer-এ convert করা যায়।
- `base` সাধারণত `2` থেকে `36`-এর মধ্যে হতে পারে; `0`-ও বিশেষভাবে ব্যবহার করা যায়।
- Invalid String বা invalid base দিলে `ValueError` হতে পারে।
- `None`-এর মতো unsupported input দিলে `TypeError` হতে পারে।
- `input()` থেকে পাওয়া String-কে Integer করতে `int()` ব্যবহার করা হয়।
- Conversion করার সময় data loss হচ্ছে কি না, তা বুঝে নেওয়া জরুরি।

## 15. Next Topic

পরবর্তী ফাইল:

**`23_Converting_to_float.md`**

সেখানে `float()` function-এর syntax, String ও Integer থেকে Float conversion, scientific notation, `inf`, `nan`, floating-point precision এবং common errors বিস্তারিতভাবে শেখা হবে।