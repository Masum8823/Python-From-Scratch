# 06. Integer Type (`int`)

## 1. What Is an Integer?

Python-এ **Integer (`int`)** হলো এমন একটি built-in data type, যা পূর্ণসংখ্যা প্রকাশ করতে ব্যবহৃত হয়।

যেসব সংখ্যার fractional বা decimal অংশ নেই, সেগুলো সাধারণত integer হিসেবে প্রকাশ করা হয়।

Examples:

```python
age = 22
temperature = -5
score = 100
balance = 0
```

এখানে সবগুলো value integer।

Integer হতে পারে:

- Positive: `10`, `25`, `100`
- Negative: `-5`, `-20`, `-100`
- Zero: `0`

**মনে রাখবে:** `10` একটি integer, কিন্তু `10.0` একটি float।

```python
print(type(10))
print(type(10.0))
```

Output:

```text
<class 'int'>
<class 'float'>
```

## 2. Creating Integer Variables

Integer variable তৈরি করতে সরাসরি পূর্ণসংখ্যা assign করা যায়।

```python
age = 22
semester = 9
marks = 85

print(age)
print(semester)
print(marks)
```

Output:

```text
22
9
85
```

Python-এ variable তৈরি করার সময় আলাদাভাবে `int` declare করতে হয় না।

```python
number = 100

print(number)
print(type(number))
```

Output:

```text
100
<class 'int'>
```

Python নিজেই value-এর type নির্ধারণ করে। এটি Python-এর dynamic typing-এর একটি উদাহরণ।

## 3. Positive, Negative and Zero Integers

Integer-এর sign বা চিহ্ন অনুযায়ী তিনটি সাধারণ অবস্থা রয়েছে।

| Type | Example | Meaning |
|---|---:|---|
| Positive integer | `15` | শূন্যের চেয়ে বড় |
| Negative integer | `-15` | শূন্যের চেয়ে ছোট |
| Zero | `0` | ধনাত্মকও নয়, ঋণাত্মকও নয় |

Example:

```python
positive = 25
negative = -25
zero = 0

print(positive)
print(negative)
print(zero)
```

Output:

```text
25
-25
0
```

Integer ব্যবহার করে age, quantity, student count, marks, item number এবং অন্যান্য পূর্ণসংখ্যাভিত্তিক তথ্য প্রকাশ করা যায়।

## 4. Integer Literals

**Integer literal** হলো source code-এ সরাসরি লেখা integer value।

Example:

```python
a = 100
b = -50
c = 0
d = 1_000_000
```

এখানে `100`, `50`, `0` এবং `1_000_000` হলো integer literals।

Python-এ বড় integer পড়তে সুবিধা করার জন্য underscore ব্যবহার করা যায়।

```python
population = 170_000_000

print(population)
```

Output:

```text
170000000
```

Underscore শুধু readability বাড়ায়। এটি সংখ্যার মান পরিবর্তন করে না।

সঠিক:

```python
number = 1_000_000
```

ভুল:

```python
# number = 1__000
```

Integer literal-এর মধ্যে underscore-এর অবস্থান নির্দিষ্ট নিয়ম মেনে হতে হবে। একাধিক পাশাপাশি underscore ব্যবহার করে literal লেখা যায় না।

## 5. Different Number Systems in Python

Python-এ integer শুধু decimal বা base-10 পদ্ধতিতে নয়, আরও কয়েকটি number system-এ লেখা যায়।

### 5.1 Decimal (Base 10)

এটি আমাদের দৈনন্দিন ব্যবহৃত সাধারণ সংখ্যা পদ্ধতি।

Digits: `0` থেকে `9`

```python
number = 25

print(number)
```

Output:

```text
25
```

### 5.2 Binary (Base 2)

Binary-তে শুধু `0` এবং `1` ব্যবহৃত হয়।

Python-এ binary integer লেখার জন্য `0b` বা `0B` ব্যবহার করা হয়।

```python
number = 0b1101

print(number)
```

Output:

```text
13
```

কারণ:

\[
(1101)_2 = 1(2^3)+1(2^2)+0(2^1)+1(2^0)=13
\]

### 5.3 Octal (Base 8)

Octal-এ `0` থেকে `7` পর্যন্ত digit ব্যবহার করা হয়।

Python-এ octal integer লেখার জন্য `0o` বা `0O` ব্যবহার করা হয়।

```python
number = 0o17

print(number)
```

Output:

```text
15
```

কারণ:

\[
(17)_8 = 1(8^1)+7(8^0)=15
\]

### 5.4 Hexadecimal (Base 16)

Hexadecimal-এ `0` থেকে `9` এবং `A` থেকে `F` ব্যবহার করা হয়।

Python-এ hexadecimal integer লেখার জন্য `0x` বা `0X` ব্যবহার করা হয়।

```python
number = 0x1F

print(number)
```

Output:

```text
31
```

কারণ:

\[
(1F)_{16} = 1(16^1)+15(16^0)=31
\]

### Number Systems Summary

| Number system | Prefix | Example | Decimal result |
|---|---|---|---:|
| Decimal | None | `25` | 25 |
| Binary | `0b` | `0b1101` | 13 |
| Octal | `0o` | `0o17` | 15 |
| Hexadecimal | `0x` | `0x1F` | 31 |

Python-এ এই সবগুলো representation ব্যবহার করলেও value-গুলো `int` type-এর হয়।

```python
print(type(0b1101))
print(type(0o17))
print(type(0x1F))
```

Output:

```text
<class 'int'>
<class 'int'>
<class 'int'>
```

## 6. Converting Integers to Other Number Systems

Integer-কে binary, octal অথবা hexadecimal string হিসেবে দেখতে Python-এর built-in functions ব্যবহার করা যায়।

### `bin()`

```python
number = 13

print(bin(number))
```

Output:

```text
0b1101
```

### `oct()`

```python
number = 15

print(oct(number))
```

Output:

```text
0o17
```

### `hex()`

```python
number = 31

print(hex(number))
```

Output:

```text
0x1f
```

**Important:** `bin()`, `oct()` এবং `hex()` string return করে।

```python
result = bin(13)

print(type(result))
```

Output:

```text
<class 'str'>
```

এগুলো integer-এর representation তৈরি করে; original integer-কে অন্য data type-এ পরিবর্তন করে না।

## 7. Basic Arithmetic Operations with Integers

Python-এ integer-এর ওপর বিভিন্ন arithmetic operation করা যায়।

### 7.1 Addition (`+`)

দুটি সংখ্যা যোগ করে।

```python
a = 10
b = 5

print(a + b)
```

Output:

```text
15
```

### 7.2 Subtraction (`-`)

একটি সংখ্যা থেকে অন্যটি বিয়োগ করে।

```python
a = 10
b = 5

print(a - b)
```

Output:

```text
5
```

### 7.3 Multiplication (`*`)

দুটি সংখ্যা গুণ করে।

```python
a = 10
b = 5

print(a * b)
```

Output:

```text
50
```

### 7.4 Division (`/`)

সাধারণ division-এর result হলো `float`।

```python
a = 10
b = 2

result = a / b

print(result)
print(type(result))
```

Output:

```text
5.0
<class 'float'>
```

দুটি integer দিয়ে division করলেও `/` operator সাধারণত float result দেয়।

### 7.5 Floor Division (`//`)

Floor division result-কে নিচের পূর্ণসংখ্যার দিকে round করে, অর্থাৎ mathematical floor নির্ধারণ করে।

```python
print(10 // 3)
```

Output:

```text
3
```

Negative number-এর ক্ষেত্রে এটি zero-এর দিকে নয়, নিচের পূর্ণসংখ্যার দিকে যায়।

```python
print(-10 // 3)
```

Output:

```text
-4
```

কারণ:

\[
\left\lfloor -10/3 \right\rfloor = -4
\]

### 7.6 Modulus (`%`)

Modulus operator ভাগশেষ return করে।

```python
print(10 % 3)
```

Output:

```text
1
```

এটি even/odd check এবং divisibility যাচাই করতে কাজে লাগে।

```python
number = 8

print(number % 2)
```

Output:

```text
0
```

ভাগশেষ `0`, তাই `8` একটি even number।

### 7.7 Exponentiation (`**`)

একটি সংখ্যার power নির্ণয় করে।

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

### Arithmetic Operators Summary

| Operator | Name | Example | Result |
|---|---|---|---:|
| `+` | Addition | `10 + 3` | 13 |
| `-` | Subtraction | `10 - 3` | 7 |
| `*` | Multiplication | `10 * 3` | 30 |
| `/` | Division | `10 / 3` | 3.333... |
| `//` | Floor division | `10 // 3` | 3 |
| `%` | Modulus | `10 % 3` | 1 |
| `**` | Exponentiation | `2 ** 3` | 8 |

## 8. Integer Division and Negative Numbers

Negative integer নিয়ে কাজ করার সময় `//` এবং `%`-এর সম্পর্ক বোঝা গুরুত্বপূর্ণ।

Python-এ সাধারণভাবে নিচের সম্পর্কটি বজায় থাকে, যদি divisor শূন্য না হয়:

\[
a = (a // b)\times b + (a \% b)
\]

Example:

```python
print(-10 // 3)
print(-10 % 3)
```

Output:

```text
-4
2
```

যাচাই:

\[
-10 = (-4 \times 3)+2
\]

তাই Python-এ negative dividend-এর ক্ষেত্রেও modulus result divisor-এর sign অনুযায়ী নির্ধারিত হয়।

এটি অন্য কিছু programming language-এর division behaviour থেকে আলাদা হতে পারে।

## 9. Comparing Integers

Integer-এর মান তুলনা করতে comparison operators ব্যবহার করা হয়।

| Operator | Meaning |
|---|---|
| `==` | সমান |
| `!=` | সমান নয় |
| `>` | বড় |
| `<` | ছোট |
| `>=` | বড় অথবা সমান |
| `<=` | ছোট অথবা সমান |

Example:

```python
a = 10
b = 20

print(a == b)
print(a != b)
print(a < b)
print(a > b)
```

Output:

```text
False
True
True
False
```

Comparison-এর result `bool` type-এর হয়।

```python
result = 10 < 20

print(type(result))
```

Output:

```text
<class 'bool'>
```

## 10. Integer Division by Zero

কোনো integer-কে শূন্য দিয়ে divide করলে Python error দেয়।

```python
a = 10
b = 0

print(a / b)
```

এটি চালালে `ZeroDivisionError` হবে।

একইভাবে:

```python
print(10 // 0)
print(10 % 0)
```

এই operation-গুলোও `ZeroDivisionError` তৈরি করবে।

তাই user-provided divisor ব্যবহার করলে zero-এর বিষয়টি বিবেচনা করতে হবে।

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

## 11. How Large Can a Python Integer Be?

Python-এর `int`-এর সাধারণ integer range C বা Java-এর fixed-width integer types-এর মতো নির্দিষ্ট 32-bit বা 64-bit সীমায় আবদ্ধ নয়।

Python প্রয়োজন অনুযায়ী বড় integer সংরক্ষণ করতে পারে, যতক্ষণ available memory এবং implementation-এর অন্যান্য সীমা তা অনুমোদন করে।

Example:

```python
number = 123456789012345678901234567890

print(number)
print(type(number))
```

Output:

```text
123456789012345678901234567890
<class 'int'>
```

আরও বড় integer নিয়েও arithmetic করা যায়।

```python
number = 2 ** 100

print(number)
```

Output:

```text
1267650600228229401496703205376
```

Python বড় integer-এর জন্য প্রয়োজন অনুযায়ী memory ব্যবহার করে। তবে এর অর্থ এই নয় যে integer-এর আকার অসীম—বাস্তবে memory এবং system resource-এর সীমা রয়েছে।

## 12. Integer and Floating-Point Numbers

Integer এবং float—দুটিই numeric data type, কিন্তু এদের মধ্যে গুরুত্বপূর্ণ পার্থক্য রয়েছে।

| Integer (`int`) | Floating-point (`float`) |
|---|---|
| পূর্ণসংখ্যা প্রকাশ করে | Fractional বা decimal value প্রকাশ করতে পারে |
| Example: `10` | Example: `10.5` |
| সাধারণ integer arithmetic-এ precision loss হয় না, যতক্ষণ resource সীমা অনুমোদন করে | Floating-point representation-এ rounding error হতে পারে |
| `type(10)` হলো `int` | `type(10.0)` হলো `float` |

Example:

```python
a = 10
b = 10.0

print(a == b)
print(type(a))
print(type(b))
```

Output:

```text
True
<class 'int'>
<class 'float'>
```

এখানে `a` এবং `b`-এর numeric value সমান হলেও type আলাদা।

## 13. Integer Conversion Using `int()`

`int()` function ব্যবহার করে উপযুক্ত value-কে integer-এ convert করা যায়।

### Converting a Float

```python
number = int(9.8)

print(number)
```

Output:

```text
9
```

এখানে fractional অংশ বাদ দেওয়া হয়েছে। `int()` সাধারণত float-কে convert করার সময় zero-এর দিকে truncate করে; এটি সবসময় nearest integer-এ round করে না।

```python
print(int(9.8))
print(int(-9.8))
```

Output:

```text
9
-9
```

### Converting a String

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

তবে string-টি integer representation হিসেবে গ্রহণযোগ্য হতে হবে।

```python
print(int("12.5"))
```

এটি `ValueError` দেবে, কারণ `"12.5"` সরাসরি integer literal হিসেবে গ্রহণযোগ্য নয়। আগে float-এ convert করে তারপর integer-এ convert করা যায়, যদি সেটিই প্রয়োজন হয়।

```python
number = int(float("12.5"))

print(number)
```

Output:

```text
12
```

**মনে রাখবে:** `int()` ব্যবহার করলেই যেকোনো value সফলভাবে integer-এ convert হবে না।

## 14. Integer and Boolean Relationship

Python-এ `bool` হলো `int`-এর subclass।

```python
print(isinstance(True, int))
print(isinstance(False, int))
```

Output:

```text
True
True
```

Arithmetic operation-এ:

```python
print(True + 2)
print(False + 2)
```

Output:

```text
3
2
```

কারণ Python-এ `True`-এর numeric value `1` এবং `False`-এর numeric value `0`।

তবে Boolean-এর প্রধান উদ্দেশ্য হলো logical value প্রকাশ করা। তাই সাধারণ program-এ Boolean এবং integer-এর ভূমিকা আলাদা রাখাই ভালো।

## 15. Common Beginner Mistakes

### Mistake 1: Integer এবং Float-কে একই Type মনে করা

```python
a = 10
b = 10.0

print(type(a))
print(type(b))
```

দুটি value দেখতে প্রায় একই হলেও তাদের type আলাদা।

### Mistake 2: `/` এবং `//`-এর পার্থক্য না বোঝা

```python
print(7 / 2)
print(7 // 2)
```

Output:

```text
3.5
3
```

`/` সাধারণ division করে, আর `//` floor division করে।

### Mistake 3: `int()`-কে Rounding Function মনে করা

```python
print(int(4.9))
```

Output:

```text
4
```

এটি `5` নয়। কারণ `int()` fractional অংশ বাদ দেয়; nearest integer-এ round করে না।

### Mistake 4: String-এর সঙ্গে Integer যোগ করা

```python
age = "22"

print(age + 5)
```

এটি `TypeError` দেবে, কারণ string এবং integer সরাসরি এভাবে যোগ করা যায় না।

সংশোধন:

```python
age = int(age)

print(age + 5)
```

Output:

```text
27
```

### Mistake 5: Division by Zero

```python
print(10 / 0)
```

এটি `ZeroDivisionError` তৈরি করবে। Division-এর আগে divisor শূন্য কি না যাচাই করো।

## 16. Practice Exercises

### Exercise 1: Basic Integer

তিনটি variable তৈরি করো:

- `age` — তোমার বয়স
- `semester` — বর্তমান semester
- `marks` — একটি পরীক্ষার নম্বর

প্রতিটি variable-এর value এবং type print করো।

### Exercise 2: Arithmetic Operations

`a = 25` এবং `b = 4` ধরে নিচের operation-গুলোর result বের করো:

- Addition
- Subtraction
- Multiplication
- Division
- Floor division
- Modulus
- Exponentiation

### Exercise 3: Number Systems

নিচের integer literals-গুলোকে decimal value-তে convert করে output লিখো:

```python
print(0b1010)
print(0o20)
print(0x2A)
```

### Exercise 4: Even or Odd

একটি integer even নাকি odd, তা নির্ণয় করার program লেখো। `%` operator ব্যবহার করো।

### Exercise 5: Positive, Negative or Zero

একটি integer নিয়ে পরীক্ষা করো, সেটি positive, negative নাকি zero।

### Exercise 6: Floor Division

নিচের code-এর output অনুমান করো এবং কারণ ব্যাখ্যা করো:

```python
print(10 // 3)
print(-10 // 3)
print(10 % 3)
print(-10 % 3)
```

### Exercise 7: Integer Conversion

নিচের code-এর output নির্ণয় করো:

```python
print(int(7.9))
print(int(-7.9))
print(int("25"))
print(type(int("25")))
```

### Exercise 8: Large Integer

`2 ** 100`-এর value এবং type print করো। Python কীভাবে বড় integer handle করে, নিজের ভাষায় ব্যাখ্যা করো।

### Exercise 9: Input Validation

User-এর কাছ থেকে দুটি integer নাও। তাদের যোগফল print করো। মনে রাখবে, `input()` থেকে পাওয়া value-কে integer-এ convert করতে হবে।

### Exercise 10: Mini Project — Simple Calculator

দুটি integer নিয়ে নিচের result-গুলো print করো:

- Sum
- Difference
- Product
- Floor division
- Remainder

Division-এর ক্ষেত্রে দ্বিতীয় integer শূন্য হলে উপযুক্ত message দেখাও।

## 17. Key Takeaways

- `int` হলো Python-এর built-in integer data type।
- Integer positive, negative অথবা zero হতে পারে।
- Python-এ decimal, binary, octal এবং hexadecimal integer literals ব্যবহার করা যায়।
- বড় integer-এর জন্য Python fixed 32-bit বা 64-bit range ব্যবহার করে না; বাস্তব সীমা memory ও resources-এর ওপর নির্ভর করে।
- `/` সাধারণত float result দেয়, আর `//` floor division করে।
- `%` ভাগশেষ এবং `**` power নির্ণয় করে।
- `int()` float-এর fractional অংশ truncate করে; এটি সাধারণ rounding function নয়।
- `bool` হলো `int`-এর subclass।
- Integer division বা modulus-এর divisor শূন্য হলে `ZeroDivisionError` হতে পারে।
- `input()` থেকে পাওয়া numeric text-কে arithmetic করার আগে উপযুক্ত type-এ convert করতে হয়।

## 18. Next Topic

পরবর্তী ফাইল:

**`07_Floating_Point_Type.md`**

সেখানে `float` data type, decimal numbers, floating-point precision, scientific notation, rounding এবং floating-point calculation-এর সাধারণ সমস্যাগুলো শেখা হবে।