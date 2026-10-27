# 07. Floating-Point Type (`float`)

## 1. What Is a Floating-Point Number?

Python-এ **Float (`float`)** হলো একটি built-in numeric data type, যা দশমিক বা fractional value প্রকাশ করতে ব্যবহৃত হয়।

যেসব সংখ্যায় decimal বা ভগ্নাংশের অংশ থাকতে পারে, সেগুলো প্রকাশ করতে `float` ব্যবহার করা হয়।

Examples:

```python
price = 99.50
cgpa = 3.95
temperature = 36.6
height = 5.8
```

এখানে সবগুলো value `float` type-এর।

```python
print(type(99.50))
print(type(3.95))
print(type(36.6))
```

Output:

```text
<class 'float'>
<class 'float'>
<class 'float'>
```

**মনে রাখবে:** কোনো সংখ্যার শেষে `.0` থাকলেও সেটি float হতে পারে।

```python
a = 10
b = 10.0

print(type(a))
print(type(b))
```

Output:

```text
<class 'int'>
<class 'float'>
```

এখানে `10` হলো integer, আর `10.0` হলো float।

## 2. Creating Float Variables

Python-এ float variable তৈরি করতে decimal value assign করা যায়।

```python
price = 250.75
cgpa = 3.95
temperature = -2.5
```

Python নিজে থেকেই value-এর type নির্ধারণ করে।

```python
number = 12.5

print(number)
print(type(number))
```

Output:

```text
12.5
<class 'float'>
```

এখানে আলাদাভাবে float declare করার প্রয়োজন হয়নি।

Float-এর মান positive, negative অথবা zero হতে পারে।

```python
a = 5.5
b = -5.5
c = 0.0

print(a)
print(b)
print(c)
```

Output:

```text
5.5
-5.5
0.0
```

## 3. Integer vs Float

`int` এবং `float`—দুটিই numeric data type, তবে এদের ব্যবহার ও আচরণে কিছু পার্থক্য রয়েছে।

| Integer (`int`) | Floating-point (`float`) |
|---|---|
| পূর্ণসংখ্যা প্রকাশ করে | Fractional value-সহ সংখ্যা প্রকাশ করতে পারে |
| Example: `10` | Example: `10.5` |
| সাধারণ integer arithmetic-এ নির্ভুল পূর্ণসংখ্যার ফল পাওয়া যায়, resource সীমা সাপেক্ষে | অনেক decimal value binary format-এ আনুমানিকভাবে সংরক্ষিত হয় |
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

Numeric value সমান হলেও তাদের type আলাদা।

## 4. Float Arithmetic Operations

Float-এর ওপর সাধারণ arithmetic operations করা যায়।

### 4.1 Addition

```python
a = 10.5
b = 2.5

print(a + b)
```

Output:

```text
13.0
```

### 4.2 Subtraction

```python
a = 10.5
b = 2.5

print(a - b)
```

Output:

```text
8.0
```

### 4.3 Multiplication

```python
a = 2.5
b = 4.0

print(a * b)
```

Output:

```text
10.0
```

### 4.4 Division

```python
a = 10
b = 4

print(a / b)
```

Output:

```text
2.5
```

সাধারণ division-এর result float হয়, এমনকি দুটি operand-ই integer হলেও।

### 4.5 Floor Division

```python
print(7.0 // 2.0)
```

Output:

```text
3.0
```

Floor division decimal অংশ বাদ দেওয়ার মতো দেখালেও প্রকৃতপক্ষে নিচের পূর্ণসংখ্যার দিকে floor নির্ধারণ করে। Float operand ব্যবহার করলে result-ও float হতে পারে।

### 4.6 Modulus

```python
print(7.5 % 2.0)
```

Output:

```text
1.5
```

Modulus ভাগশেষ নির্ণয় করে।

### 4.7 Exponentiation

```python
print(2.5 ** 2)
```

Output:

```text
6.25
```

### Arithmetic Summary

| Operator | Example | Result |
|---|---|---:|
| `+` | `2.5 + 1.5` | `4.0` |
| `-` | `5.5 - 2.0` | `3.5` |
| `*` | `2.5 * 2` | `5.0` |
| `/` | `5 / 2` | `2.5` |
| `//` | `7.0 // 2.0` | `3.0` |
| `%` | `7.5 % 2.0` | `1.5` |
| `**` | `2.0 ** 3` | `8.0` |

## 5. Floating-Point Precision

এটি Python-এর `float`-এর সবচেয়ে গুরুত্বপূর্ণ বিষয়গুলোর একটি।

কম্পিউটার অনেক decimal value-কে binary floating-point format-এ সংরক্ষণ করে। কিছু decimal fraction binary-তে সসীমভাবে প্রকাশ করা যায় না। ফলে value-কে কাছাকাছি একটি representable number হিসেবে সংরক্ষণ করা হয়।

এ কারণে কিছু calculation-এ অপ্রত্যাশিত decimal result দেখা যায়।

Example:

```python
print(0.1 + 0.2)
```

Output:

```text
0.30000000000000004
```

আমরা সাধারণত `0.3` আশা করি, কিন্তু floating-point representation-এর কারণে সামান্য পার্থক্য দেখা যায়।

আরেকটি example:

```python
print(0.1 + 0.2 == 0.3)
```

Output:

```text
False
```

কারণ বাম পাশের calculation-এর result এবং `0.3`-এর floating-point representation একদম সমান নয়।

**গুরুত্বপূর্ণ:** এর মানে এই নয় যে Python-এর arithmetic ভুল। এটি binary floating-point representation-এর একটি সীমাবদ্ধতা।

## 6. Comparing Float Values Safely

Floating-point calculation-এর ক্ষেত্রে `==` দিয়ে exact equality check করলে অনেক সময় ভুল সিদ্ধান্ত আসতে পারে।

একটি সাধারণ পদ্ধতি হলো `math.isclose()` ব্যবহার করা।

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

`math.isclose()` দুটি numeric value যথেষ্ট কাছাকাছি কি না পরীক্ষা করে।

প্রয়োজনে tolerance নির্ধারণ করা যায়।

```python
import math

a = 1.000001
b = 1.000002

print(math.isclose(a, b, rel_tol=1e-5))
```

Output:

```text
True
```

এখানে `rel_tol` হলো relative tolerance—দুটি value কতটা কাছাকাছি হলে তাদের প্রায় সমান হিসেবে গ্রহণ করা হবে, তা নির্ধারণ করে।

**মনে রাখবে:** কোন tolerance ব্যবহার করবে, তা problem-এর প্রয়োজনীয় accuracy-এর ওপর নির্ভর করে।

## 7. Rounding Float Values

Python-এ float-এর decimal places সীমিত করে দেখাতে `round()` ব্যবহার করা যায়।

Syntax:

```python
round(number, ndigits)
```

এখানে:

- `number`: যে সংখ্যাটি round করতে চাও।
- `ndigits`: decimal point-এর পর কত ঘর রাখতে চাও।

Example:

```python
number = 3.141592

print(round(number, 2))
print(round(number, 3))
```

Output:

```text
3.14
3.142
```

### Rounding to a Whole Number

```python
print(round(3.6))
print(round(3.2))
```

Output:

```text
4
3
```

তবে Python-এর `round()` tie-এর ক্ষেত্রে **round half to even** নিয়ম অনুসরণ করে।

Example:

```python
print(round(2.5))
print(round(3.5))
```

Output:

```text
2
4
```

যখন value ঠিক মাঝামাঝি অবস্থায় থাকে, তখন কাছের even integer-এর দিকে round করা হয়।

**Note:** `round()`-এর result সবসময় float হবে না। `ndigits` বাদ দিলে integer input-এর ক্ষেত্রে সাধারণত integer result পাওয়া যায়।

## 8. Displaying Float Values with Formatting

কখনো calculation-এর আসল value অপরিবর্তিত রেখে নির্দিষ্ট decimal places-এ দেখাতে হয়।

এক্ষেত্রে f-string ব্যবহার করা যায়।

```python
price = 99.5678

print(f"{price:.2f}")
```

Output:

```text
99.57
```

এখানে `.2f` মানে decimal point-এর পরে দুই ঘর দেখানো।

আরেকটি example:

```python
cgpa = 3.95678

print(f"CGPA: {cgpa:.2f}")
print(f"CGPA: {cgpa:.3f}")
```

Output:

```text
CGPA: 3.96
CGPA: 3.957
```

**পার্থক্য:**

- `round()` একটি rounded numeric value return করে।
- f-string formatting নির্দিষ্ট format-এ value-কে text হিসেবে উপস্থাপন করে।

Example:

```python
number = 3.14159

rounded = round(number, 2)
formatted = f"{number:.2f}"

print(rounded, type(rounded))
print(formatted, type(formatted))
```

Output:

```text
3.14 <class 'float'>
3.14 <class 'str'>
```

এখানে `formatted` একটি string।

## 9. Scientific Notation

খুব বড় অথবা খুব ছোট floating-point number প্রকাশ করতে scientific notation ব্যবহার করা যায়।

Python-এ `e` বা `E` ব্যবহার করে এটি লেখা হয়।

Example:

```python
a = 1.5e3
b = 2.5e-2

print(a)
print(b)
```

Output:

```text
1500.0
0.025
```

ব্যাখ্যা:

- `1.5e3` অর্থ \(1.5 \times 10^3 = 1500.0\)
- `2.5e-2` অর্থ \(2.5 \times 10^{-2} = 0.025\)

Scientific notation বড় বা ছোট value সহজে লেখার জন্য উপযোগী।

আরেকটি example:

```python
number = 6.02e23

print(number)
print(type(number))
```

Output:

```text
6.02e+23
<class 'float'>
```

## 10. Converting Values to Float

`float()` function দিয়ে উপযুক্ত value-কে float-এ convert করা যায়।

### 10.1 Integer to Float

```python
number = 10

result = float(number)

print(result)
print(type(result))
```

Output:

```text
10.0
<class 'float'>
```

### 10.2 String to Float

```python
number = "12.75"

result = float(number)

print(result)
print(type(result))
```

Output:

```text
12.75
<class 'float'>
```

### 10.3 Integer-Looking String to Float

```python
number = float("25")

print(number)
```

Output:

```text
25.0
```

### 10.4 Invalid String Conversion

```python
number = float("Python")
```

এটি `ValueError` তৈরি করবে, কারণ `"Python"` একটি valid numeric string নয়।

### 10.5 Boolean to Float

```python
print(float(True))
print(float(False))
```

Output:

```text
1.0
0.0
```

Python-এ `True` numeric context-এ `1` এবং `False` numeric context-এ `0` হিসেবে কাজ করে।

## 11. Special Floating-Point Values

Python-এর `float`-এ কয়েকটি special value থাকতে পারে।

### 11.1 Positive Infinity

```python
a = float("inf")

print(a)
print(type(a))
```

Output:

```text
inf
<class 'float'>
```

`inf` positive infinity বোঝায়।

### 11.2 Negative Infinity

```python
a = float("-inf")

print(a)
```

Output:

```text
-inf
```

### 11.3 Not a Number (`NaN`)

`NaN`-এর পূর্ণরূপ **Not a Number**। এটি এমন একটি special floating-point value, যা অনির্ধারিত বা অপ্রতিনিধিত্বযোগ্য numeric result বোঝাতে ব্যবহৃত হয়।

```python
value = float("nan")

print(value)
print(type(value))
```

Output:

```text
nan
<class 'float'>
```

`NaN`-এর একটি গুরুত্বপূর্ণ বৈশিষ্ট্য হলো, এটি নিজের সমান নয়।

```python
value = float("nan")

print(value == value)
```

Output:

```text
False
```

তাই `NaN` check করতে `math.isnan()` ব্যবহার করা উচিত।

```python
import math

value = float("nan")

print(math.isnan(value))
```

Output:

```text
True
```

Infinity এবং `NaN` বিশেষ numeric calculation, scientific computing ও data analysis-এ দেখা যায়।

## 12. Float Limitations

Python-এর সাধারণ `float` সাধারণত IEEE 754 double-precision floating-point format ব্যবহার করে। এর কিছু গুরুত্বপূর্ণ সীমাবদ্ধতা রয়েছে।

### 12.1 Approximate Decimal Representation

কিছু decimal value exactভাবে সংরক্ষণ করা যায় না।

```python
print(0.1 + 0.2)
```

### 12.2 Limited Precision

অনেক বড় বা খুব ছোট সংখ্যা নিয়ে কাজ করার সময় precision হারাতে পারে।

### 12.3 Overflow and Underflow

কিছু calculation-এর result float-এর representable range ছাড়িয়ে যেতে পারে। খুব ছোট value-ও precision-এর কারণে শূন্যের কাছাকাছি বা শূন্য হয়ে যেতে পারে।

### 12.4 Not Ideal for Every Financial Calculation

সাধারণ financial calculation-এ floating-point rounding সমস্যার কারণ হতে পারে। Decimal-based arithmetic প্রয়োজন হলে `decimal.Decimal` বিবেচনা করা যায়।

উদাহরণ:

```python
from decimal import Decimal

a = Decimal("0.1")
b = Decimal("0.2")

print(a + b)
```

Output:

```text
0.3
```

এখানে decimal value-গুলো string থেকে তৈরি করা হয়েছে, যাতে প্রত্যাশিত decimal representation বজায় থাকে।

**মনে রাখবে:** `Decimal` সব সমস্যার universal solution নয়। এটি ব্যবহার করার আগে precision, rounding এবং performance-এর প্রয়োজন বুঝতে হবে।

## 13. Common Beginner Mistakes

### Mistake 1: Integer এবং Float-এর পার্থক্য না বোঝা

```python
a = 5
b = 5.0

print(type(a))
print(type(b))
```

দুটি value সমান হলেও type আলাদা।

### Mistake 2: Exact Float Comparison করা

```python
print(0.1 + 0.2 == 0.3)
```

Output:

```text
False
```

প্রয়োজন অনুযায়ী `math.isclose()` ব্যবহার করো।

### Mistake 3: `round()`-কে সবসময় সাধারণ Rounding মনে করা

```python
print(round(2.5))
```

Output:

```text
2
```

Python tie-এর ক্ষেত্রে round half to even নিয়ম ব্যবহার করে।

### Mistake 4: Formatted Value-কে Float মনে করা

```python
number = 3.14159
result = f"{number:.2f}"

print(result)
print(type(result))
```

Output:

```text
3.14
<class 'str'>
```

Formatted result string হয়।

### Mistake 5: Invalid String Convert করা

```python
number = float("abc")
```

এটি `ValueError` তৈরি করবে। User input convert করার সময় invalid input handle করতে হবে।

## 14. Practice Exercises

### Exercise 1: Identify the Types

নিচের code-এর output নির্ণয় করো:

```python
a = 10
b = 10.0
c = -3.75
d = 0.0

print(type(a))
print(type(b))
print(type(c))
print(type(d))
```

### Exercise 2: Arithmetic Operations

`a = 12.5` এবং `b = 2.5` ধরে addition, subtraction, multiplication, division এবং floor division-এর result বের করো।

### Exercise 3: Precision Problem

নিচের code চালিয়ে output ব্যাখ্যা করো:

```python
print(0.1 + 0.2)
print(0.1 + 0.2 == 0.3)
```

এরপর `math.isclose()` ব্যবহার করে দুটি value তুলনা করো।

### Exercise 4: Rounding

নিচের expression-গুলোর result নির্ণয় করো:

```python
print(round(3.14159, 2))
print(round(3.14159, 3))
print(round(2.5))
print(round(3.5))
```

### Exercise 5: Scientific Notation

নিচের value-গুলোর decimal representation বের করো:

```python
a = 4.5e3
b = 2.5e-3
c = 6.02e23

print(a)
print(b)
print(c)
```

### Exercise 6: Type Conversion

নিচের value-গুলোকে float-এ convert করো:

- Integer `25`
- String `"15.75"`
- String `"100"`
- Boolean `True`

প্রতিটি converted value-এর type-ও print করো।

### Exercise 7: CGPA Formatter

একটি variable-এ `3.95678` রাখো। তারপর CGPA-টি দুই decimal places-এ print করো।

### Exercise 8: Mini Project — Bill Calculator

একটি program লেখো, যা user-এর কাছ থেকে একটি পণ্যের unit price এবং quantity নেবে। তারপর total bill হিসাব করবে।

Requirements:

1. Unit price-কে float-এ convert করবে।
2. Quantity-কে integer-এ convert করবে।
3. Total bill হিসাব করবে।
4. Bill-টি দুই decimal places-এ দেখাবে।
5. Invalid input হলে কীভাবে error handle করা যায়, তা বিবেচনা করবে।

## 14. Key Takeaways

- `float` decimal ও fractional value প্রকাশ করে।
- `10` হলো `int`, কিন্তু `10.0` হলো `float`।
- Float-এর ওপর সাধারণ arithmetic operations করা যায়।
- Binary floating-point representation-এর কারণে কিছু decimal calculation-এ সামান্য precision error দেখা যায়।
- কাছাকাছি float value তুলনা করতে `math.isclose()` ব্যবহার করা যায়।
- `round()` numeric value round করে; f-string formatting text তৈরি করে।
- Scientific notation-এ `e` বা `E` ব্যবহার করা হয়।
- `float()` উপযুক্ত integer, string এবং Boolean value convert করতে পারে।
- `inf` এবং `nan` special floating-point value।
- Decimal arithmetic-এর নির্দিষ্ট প্রয়োজন থাকলে `decimal.Decimal` ব্যবহার করা যায়।

## 15. Next Topic

পরবর্তী ফাইল:

**`08_Complex_Number_Type.md`**

সেখানে Python-এর complex number, real ও imaginary parts, `j` notation, complex arithmetic এবং `complex` data type-এর ব্যবহার শেখা হবে।