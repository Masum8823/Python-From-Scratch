# 09. Numeric Type Operations and Limitations

## 1. Introduction to Python Numeric Types

Python-এ প্রধান তিনটি built-in numeric data type হলো:

1. `int` — পূর্ণসংখ্যার জন্য।
2. `float` — floating-point বা decimal value-এর জন্য।
3. `complex` — real এবং imaginary অংশবিশিষ্ট সংখ্যার জন্য।

Example:

```python
a = 10
b = 3.14
c = 2 + 3j

print(type(a))
print(type(b))
print(type(c))
```

Output:

```text
<class 'int'>
<class 'float'>
<class 'complex'>
```

প্রতিটি type-এর নিজস্ব বৈশিষ্ট্য এবং ব্যবহারের ক্ষেত্র রয়েছে।

## 2. Comparing Numeric Types

| Feature | `int` | `float` | `complex` |
|---|---|---|---|
| Purpose | পূর্ণসংখ্যা | Decimal ও fractional value | Real ও imaginary অংশবিশিষ্ট সংখ্যা |
| Example | `10` | `10.5` | `2 + 3j` |
| Decimal part | থাকে না | থাকতে পারে | Real ও imaginary অংশে থাকতে পারে |
| Precision | Integer value নির্ভুলভাবে সংরক্ষণ করা যায়, resource সীমা সাপেক্ষে | অনেক value আনুমানিকভাবে সংরক্ষিত হয় | Real ও imaginary অংশ সাধারণত floating-point precision অনুসরণ করে |
| Ordering comparison | সমর্থিত | সমর্থিত | `<` ও `>` সমর্থিত নয় |
| Common use | Count, index, quantity | Measurement, average, scientific calculation | Complex mathematics, engineering calculations |

Example:

```python
a = 10
b = 10.0
c = 10 + 0j

print(a == b)
print(b == c)
print(type(a), type(b), type(c))
```

Output:

```text
True
True
<class 'int'> <class 'float'> <class 'complex'>
```

এখানে তিনটি numeric value সমান হলেও তাদের type আলাদা।

## 3. Arithmetic Operations Across Numeric Types

Python-এ বিভিন্ন numeric type একসঙ্গে arithmetic operation-এ ব্যবহার করা যায়।

### 3.1 Integer with Integer

```python
a = 10
b = 3

result = a + b

print(result)
print(type(result))
```

Output:

```text
13
<class 'int'>
```

দুটি integer যোগ করলে সাধারণত integer result পাওয়া যায়।

### 3.2 Integer with Float

```python
a = 10
b = 2.5

result = a + b

print(result)
print(type(result))
```

Output:

```text
12.5
<class 'float'>
```

এখানে mixed-type arithmetic-এর কারণে result `float` হয়েছে।

### 3.3 Integer with Complex

```python
a = 10
b = 2 + 3j

result = a + b

print(result)
print(type(result))
```

Output:

```text
(12+3j)
<class 'complex'>
```

Integer এবং complex number-এর arithmetic result এখানে complex হয়েছে।

### 3.4 Float with Complex

```python
a = 2.5
b = 1 + 2j

result = a + b

print(result)
print(type(result))
```

Output:

```text
(3.5+2j)
<class 'complex'>
```

এখানে result `complex` type-এর।

## 4. Type Promotion in Python

**Type Promotion** বলতে arithmetic operation-এর সময় numeric value-কে উপযুক্ত numeric type-এ নিয়ে গিয়ে operation সম্পন্ন করার প্রক্রিয়াকে বোঝানো হয়।

সাধারণ mixed-type arithmetic-এ Python-এর প্রচলিত numeric promotion order:

`int → float → complex`

উদাহরণ:

```python
print(type(5 + 2))
print(type(5 + 2.0))
print(type(5 + 2j))
print(type(2.0 + 2j))
```

Output:

```text
<class 'int'>
<class 'float'>
<class 'complex'>
<class 'complex'>
```

ব্যাখ্যা:

- `int + int` → সাধারণত `int`
- `int + float` → `float`
- `int + complex` → `complex`
- `float + complex` → `complex`

**Important:** এটি সাধারণ arithmetic operation-এর একটি ব্যবহারিক নিয়ম। সব operator-এর আচরণ এক নয়। যেমন `/` ব্যবহার করলে দুটি integer-এর division result-ও `float` হয়।

## 5. Division and Floor Division

Python-এ `/` এবং `//`-এর আচরণ আলাদা।

### 5.1 Normal Division (`/`)

```python
a = 10
b = 4

result = a / b

print(result)
print(type(result))
```

Output:

```text
2.5
<class 'float'>
```

সাধারণ division-এর result `float` হয়।

### 5.2 Floor Division (`//`)

```python
print(10 // 4)
print(10.0 // 4)
```

Output:

```text
2
2.0
```

Integer operand ব্যবহার করলে এখানে integer result এবং float operand ব্যবহার করলে float result পাওয়া যায়।

### 5.3 Negative Floor Division

```python
print(-10 // 3)
print(-10 % 3)
```

Output:

```text
-4
2
```

`//` zero-এর দিকে truncate করে না; mathematical floor নির্ধারণ করে। তাই `-10 / 3`-এর result প্রায় `-3.333...` হলেও floor division-এর result `-4`।

## 6. Numeric Comparison

Integer ও float-এর numeric value সরাসরি তুলনা করা যায়।

```python
a = 10
b = 10.0

print(a == b)
print(a < 15.5)
print(b >= 10)
```

Output:

```text
True
True
True
```

তবে numeric equality এবং type equality এক বিষয় নয়।

```python
a = 10
b = 10.0

print(a == b)
print(type(a) == type(b))
```

Output:

```text
True
False
```

কারণ `10` ও `10.0`-এর numeric value সমান, কিন্তু type আলাদা।

Complex number-এর equality পরীক্ষা করা যায়, কিন্তু complex number-এর সঙ্গে `<`, `>` বা `<=`-এর মতো ordering comparison ব্যবহার করা যায় না।

```python
a = 2 + 3j
b = 4 + 5j

print(a == b)
```

Output:

```text
False
```

কিন্তু নিচের operation-টি `TypeError` তৈরি করবে:

```python
print(a < b)
```

Magnitude অনুযায়ী তুলনা করতে চাইলে `abs()` ব্যবহার করা যায়।

```python
print(abs(a) < abs(b))
```

Output:

```text
True
```

এখানে complex number দুটির magnitude তুলনা করা হয়েছে।

## 7. Precision Limitations of Float

Python-এর সাধারণ `float` সাধারণত IEEE 754 double-precision floating-point format ব্যবহার করে।

অনেক decimal value binary floating-point-এ সঠিকভাবে প্রকাশ করা যায় না। ফলে calculation-এর result-এ সামান্য পার্থক্য দেখা দিতে পারে।

Example:

```python
a = 0.1
b = 0.2

print(a + b)
print(a + b == 0.3)
```

Output:

```text
0.30000000000000004
False
```

এটি floating-point representation-এর সীমাবদ্ধতা।

### Solution: `math.isclose()`

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

`math.isclose()` দুটি value নির্ধারিত tolerance-এর মধ্যে কাছাকাছি কি না পরীক্ষা করে।

**Best Practice:** Floating-point value-এর equality পরীক্ষা করার সময় problem-এর accuracy requirement অনুযায়ী `math.isclose()` বা উপযুক্ত tolerance ব্যবহার করো।

## 8. Precision Limitations of Complex Numbers

Python-এর সাধারণ complex number-এর real এবং imaginary অংশ floating-point value দিয়ে প্রকাশিত হয়।

তাই complex arithmetic-এও floating-point precision-এর প্রভাব থাকতে পারে।

Example:

```python
number = 0.1 + 0.2j

print(number.real)
print(number.imag)
```

Output:

```text
0.1
0.2
```

এই সাধারণ উদাহরণে value-গুলো পরিষ্কারভাবে দেখা গেলেও complex arithmetic-এর প্রতিটি result exact হবে, এমন নিশ্চয়তা নেই।

আরেকটি example:

```python
a = 0.1 + 0.2j
b = 0.2 + 0.4j

print(a * 2 == b)
```

এই ধরনের comparison-এর result floating-point representation-এর ওপর নির্ভর করতে পারে। Complex number-এর real ও imaginary অংশ প্রয়োজন অনুযায়ী আলাদাভাবে tolerance দিয়ে যাচাই করা যায়।

## 9. Integer Limitations

Python-এর `int` সাধারণত C বা Java-এর fixed-width integer-এর মতো নির্দিষ্ট 32-bit বা 64-bit range-এ সীমাবদ্ধ নয়।

Example:

```python
number = 2 ** 100

print(number)
print(type(number))
```

Output:

```text
1267650600228229401496703205376
<class 'int'>
```

Python প্রয়োজন অনুযায়ী বড় integer সংরক্ষণ করতে পারে, যতক্ষণ memory এবং implementation-এর সীমা অনুমতি দেয়।

তবে খুব বড় integer নিয়ে calculation করলে বেশি memory ও processing time প্রয়োজন হতে পারে।

## 10. Complex Number Limitations

Complex number ব্যবহার করার সময় কয়েকটি গুরুত্বপূর্ণ সীমাবদ্ধতা মনে রাখতে হবে।

### 10.1 No Direct Ordering Comparison

```python
a = 2 + 3j
b = 4 + 5j

print(a < b)
```

এটি `TypeError` তৈরি করবে।

Complex number-এর magnitude তুলনা করতে চাইলে:

```python
print(abs(a) < abs(b))
```

### 10.2 Cannot Directly Convert to Integer

```python
number = 3 + 4j

print(int(number))
```

এটি `TypeError` তৈরি করবে।

শুধু real part প্রয়োজন হলে:

```python
print(int(number.real))
```

Output:

```text
3
```

তবে এতে imaginary অংশ বাদ পড়ে যায়।

### 10.3 Division by Zero

```python
number = 2 + 3j

print(number / 0)
```

এটি `ZeroDivisionError` তৈরি করবে।

## 11. Division by Zero

Numeric type যেটিই হোক, শূন্য দিয়ে division করলে error হতে পারে।

```python
print(10 / 0)
print(10 // 0)
print(10 % 0)
```

প্রতিটি operation-ই `ZeroDivisionError` তৈরি করবে।

Complex number-এর ক্ষেত্রেও একই নিয়ম প্রযোজ্য।

Safe approach:

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

## 12. Choosing the Right Numeric Type

Problem অনুযায়ী সঠিক numeric type নির্বাচন করা গুরুত্বপূর্ণ।

| Situation | Recommended type | Example |
|---|---|---|
| Student count | `int` | `students = 40` |
| Product quantity | `int` | `quantity = 5` |
| Average marks | `float` | `average = 85.5` |
| Temperature measurement | `float` | `temperature = 36.6` |
| Complex mathematical calculation | `complex` | `z = 2 + 3j` |
| Exact decimal arithmetic for suitable financial tasks | `Decimal` | `Decimal("19.99")` |

**Note:** `Decimal` একটি standard-library numeric type; এটি built-in `int`, `float` ও `complex`-এর মতো built-in numeric type নয়। Financial calculation-এ এটি উপযোগী হতে পারে, তবে rounding policy-ও ঠিক করতে হয়।

## 13. Common Beginner Mistakes

### Mistake 1: Numeric Equality-কে Type Equality মনে করা

```python
print(10 == 10.0)
print(type(10) == type(10.0))
```

Output:

```text
True
False
```

### Mistake 2: Float-এর Exact Result আশা করা

```python
print(0.1 + 0.2)
```

Output:

```text
0.30000000000000004
```

### Mistake 3: `//`-কে শুধু Decimal বাদ দেওয়া মনে করা

```python
print(-10 // 3)
```

Output:

```text
-4
```

এটি mathematical floor ব্যবহার করে।

### Mistake 4: Complex Number-কে সরাসরি তুলনা করা

```python
print((2 + 3j) < (4 + 5j))
```

এটি `TypeError` তৈরি করবে।

### Mistake 5: `int()`-কে Rounding Function মনে করা

```python
print(int(5.9))
```

Output:

```text
5
```

`int()` float-এর fractional অংশ truncate করে; nearest integer-এ round করে না।

## 14. Practice Exercises

### Exercise 1: Identify the Resulting Types

```python
print(type(5 + 2))
print(type(5 + 2.0))
print(type(5 + 2j))
print(type(2.0 + 2j))
print(type(10 / 2))
```

প্রতিটি result-এর type লিখো এবং কারণ ব্যাখ্যা করো।

### Exercise 2: Numeric Equality

```python
a = 5
b = 5.0
c = 5 + 0j

print(a == b)
print(b == c)
print(type(a) == type(b))
```

Output অনুমান করো।

### Exercise 3: Float Precision

`0.1 + 0.2 == 0.3` কেন `False` হতে পারে, তা নিজের ভাষায় ব্যাখ্যা করো। এরপর `math.isclose()` ব্যবহার করে পরীক্ষা করো।

### Exercise 4: Floor Division

```python
print(15 // 4)
print(-15 // 4)
print(15 % 4)
print(-15 % 4)
```

Output বের করো এবং negative number-এর ক্ষেত্রে `//` ও `%`-এর আচরণ ব্যাখ্যা করো।

### Exercise 5: Complex Number

একটি complex number `3 + 4j` নিয়ে তার real part, imaginary part, conjugate এবং magnitude print করো।

### Exercise 6: Choose the Right Type

নিচের প্রতিটি সমস্যার জন্য উপযুক্ত numeric type নির্বাচন করো:

1. একটি ক্লাসে শিক্ষার্থীর সংখ্যা।
2. একজন শিক্ষার্থীর average marks।
3. একটি complex mathematical equation।
4. Decimal precision প্রয়োজন এমন একটি financial calculation।

### Exercise 7: Mini Project — Numeric Type Analyzer

একটি program লেখো, যা নিচের values-এর type এবং value print করবে:

```python
values = [10, 3.14, 2 + 3j]
```

এরপর integer ও float-এর numeric equality এবং type equality আলাদাভাবে পরীক্ষা করো।

## 15. Key Takeaways

- Python-এর প্রধান numeric types হলো `int`, `float` ও `complex`।
- সাধারণ mixed-type arithmetic-এ promotion-এর ক্রম `int → float → complex`।
- `/` সাধারণত float result দেয়, আর `//` mathematical floor ব্যবহার করে।
- Numeric equality এবং type equality আলাদা।
- Float ও complex arithmetic-এ floating-point precision-এর সীমাবদ্ধতা থাকতে পারে।
- `math.isclose()` কাছাকাছি floating-point value তুলনা করতে সাহায্য করে।
- Python-এর integer fixed 32-bit বা 64-bit range-এ সীমাবদ্ধ নয়, তবে resource সীমা রয়েছে।
- Complex number-এর `<` ও `>`-এর মতো ordering comparison সরাসরি সমর্থিত নয়।
- Zero দিয়ে division করলে `ZeroDivisionError` হতে পারে।
- Problem অনুযায়ী সঠিক numeric type নির্বাচন করা উচিত।

## 16. Next Topic

পরবর্তী ফাইল:

**`10_String_Data_Type.md`**

সেখানে Python-এর `str` data type, string তৈরি, quotation marks, indexing, immutability এবং string-এর basic operations শেখা হবে।