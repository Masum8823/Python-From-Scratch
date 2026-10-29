# 23. Converting to `float()` in Python

## 1. Introduction to `float()`

Python-এ `float()` হলো একটি built-in function, যা উপযুক্ত value-কে Floating-Point number-এ রূপান্তর করে।

**Float** হলো এমন একটি numeric data type, যা decimal বা fractional value প্রকাশ করতে ব্যবহার করা হয়।

Examples:

```python
a = 10.5
b = 3.14
c = -7.25

print(type(a))
print(type(b))
print(type(c))
```

Output:

```text
<class 'float'>
<class 'float'>
<class 'float'>
```

এখানে সবগুলো value-এর type হলো `float`।

## 2. Syntax of `float()`

`float()` function-এর সাধারণ syntax:

```python
float(value)
```

এখানে `value` হলো যে value-টিকে Float-এ রূপান্তর করতে চাই।

Example:

```python
number = float("25.5")

print(number)
print(type(number))
```

Output:

```text
25.5
<class 'float'>
```

এখানে String `"25.5"` Float `25.5`-এ রূপান্তরিত হয়েছে।

## 3. Converting String to Float

যদি String-এ valid numeric representation থাকে, তাহলে `float()` সেটিকে Float-এ convert করতে পারে।

### 3.1 Positive Number

```python
number = float("12.5")

print(number)
```

Output:

```text
12.5
```

### 3.2 Negative Number

```python
number = float("-8.75")

print(number)
```

Output:

```text
-8.75
```

### 3.3 Integer-Looking String

```python
number = float("100")

print(number)
print(type(number))
```

Output:

```text
100.0
<class 'float'>
```

এখানে String-এ decimal point না থাকলেও result Float হয়েছে।

### 3.4 String with Surrounding Spaces

```python
number = float("  15.75  ")

print(number)
```

Output:

```text
15.75
```

String-এর শুরু ও শেষের whitespace গ্রহণযোগ্য।

তবে String-এর মধ্যে অপ্রত্যাশিত whitespace থাকলে conversion ব্যর্থ হতে পারে।

```python
number = float("15 .75")
```

এটি `ValueError` তৈরি করবে।

## 4. Converting Integer to Float

Integer-কে Float-এ রূপান্তর করতে `float()` ব্যবহার করা যায়।

```python
a = float(10)
b = float(-5)
c = float(0)

print(a)
print(b)
print(c)
```

Output:

```text
10.0
-5.0
0.0
```

এখানে Integer value-গুলো Float হয়েছে।

**মনে রাখবে:** `10` এবং `10.0` সংখ্যাগতভাবে সমান হলেও তাদের data type আলাদা।

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

## 5. Converting Boolean to Float

Python-এ `bool` হলো `int`-এর subclass। তাই Boolean value-কে Float-এ convert করা যায়।

```python
print(float(True))
print(float(False))
```

Output:

```text
1.0
0.0
```

এখানে:

- `True` → `1.0`
- `False` → `0.0`

## 6. Converting Other Numeric Values

### 6.1 Float to Float

```python
number = float(5.75)

print(number)
```

Output:

```text
5.75
```

### 6.2 Complex to Float

Python সরাসরি Complex number-কে Float-এ convert করে না।

```python
number = float(3 + 2j)
```

এটি `TypeError` তৈরি করবে।

যদি Complex number-এর বাস্তব অংশ প্রয়োজন হয়, তাহলে `.real` ব্যবহার করা যায়:

```python
number = float((3 + 2j).real)

print(number)
```

Output:

```text
3.0
```

এখানে imaginary অংশ ইচ্ছাকৃতভাবে বাদ দেওয়া হয়েছে। এই পদ্ধতি ব্যবহার করার আগে নিশ্চিত হও যে imaginary অংশ উপেক্ষা করা গ্রহণযোগ্য।

## 7. Converting User Input to Float

Python-এর `input()` function সব সময় String return করে। Decimal input নিয়ে calculation করতে `float()` ব্যবহার করা যায়।

```python
price = float(input("Enter product price: "))

print(price)
print(type(price))
```

Input:

```text
125.75
```

Output:

```text
125.75
<class 'float'>
```

### 7.1 Calculating the Average

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))
c = float(input("Enter third number: "))

average = (a + b + c) / 3

print("Average:", average)
```

Input:

```text
10
20
30
```

Output:

```text
Average: 20.0
```

এখানে Float conversion-এর কারণে decimal input-ও গ্রহণ করা যায়।

### 7.2 Handling Invalid Input

User যদি valid numeric value না দেয়, তাহলে `float()` `ValueError` তৈরি করতে পারে।

```python
text = input("Enter a decimal number: ")

try:
    number = float(text)
    print("Number:", number)
except ValueError:
    print("Invalid numeric input.")
```

Input:

```text
hello
```

Output:

```text
Invalid numeric input.
```

এখানে `try-except` ব্যবহার করে invalid input handle করা হয়েছে।

## 8. Scientific Notation

Float-কে Scientific Notation ব্যবহার করেও প্রকাশ করা যায়।

Scientific Notation-এ `e` বা `E` দিয়ে 10-এর power বোঝানো হয়।

Examples:

```python
a = float("1.5e2")
b = float("2.5e-3")
c = float("3E4")

print(a)
print(b)
print(c)
```

Output:

```text
150.0
0.0025
30000.0
```

ব্যাখ্যা:

- `1.5e2` = \(1.5 \times 10^2 = 150\)
- `2.5e-3` = \(2.5 \times 10^{-3} = 0.0025\)
- `3E4` = \(3 \times 10^4 = 30000\)

Scientific Notation খুব বড় বা খুব ছোট সংখ্যা প্রকাশ করতে কাজে লাগে।

## 9. Special Float Values: `inf` and `nan`

Python-এর Float type-এ কিছু special value রয়েছে।

### 9.1 Infinity

`float("inf")` positive infinity তৈরি করে।

```python
a = float("inf")
b = float("-inf")

print(a)
print(b)
```

Output:

```text
inf
-inf
```

এগুলো সাধারণ finite number নয়। বিশেষ mathematical result বা বড় numeric range নিয়ে কাজ করার সময় এগুলো দেখা যেতে পারে।

### 9.2 Not a Number (`nan`)

`nan`-এর পূর্ণরূপ হলো **Not a Number**।

```python
number = float("nan")

print(number)
print(number == number)
```

Output:

```text
nan
False
```

এখানে `nan` নিজের সঙ্গেও equal নয়।

তাই `nan` পরীক্ষা করতে equality comparison ব্যবহার না করে `math.isnan()` ব্যবহার করা ভালো।

```python
import math

number = float("nan")

print(math.isnan(number))
```

Output:

```text
True
```

### 9.3 Checking Infinity

```python
import math

number = float("inf")

print(math.isinf(number))
```

Output:

```text
True
```

`math.isnan()` ও `math.isinf()` special Float value শনাক্ত করতে সাহায্য করে।

## 10. Floating-Point Precision

কম্পিউটার অনেক decimal number binary representation-এ একদম নিখুঁতভাবে সংরক্ষণ করতে পারে না।

তাই কিছু Float calculation-এ ছোট precision error দেখা যায়।

Example:

```python
a = 0.1
b = 0.2

print(a + b)
```

Output:

```text
0.30000000000000004
```

আমরা সাধারণত `0.3` আশা করি। কিন্তু binary floating-point representation-এর সীমাবদ্ধতার কারণে result-এ সামান্য পার্থক্য দেখা যায়।

### 10.1 Comparing Floats

Floating-point result-এর equality সব সময় সরাসরি পরীক্ষা করা নিরাপদ নয়।

```python
a = 0.1 + 0.2
b = 0.3

print(a == b)
```

Output:

```text
False
```

ছোট numerical difference গ্রহণযোগ্য হলে `math.isclose()` ব্যবহার করা যায়।

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

`math.isclose()` নির্দিষ্ট tolerance-এর মধ্যে দুটি number-কে কাছাকাছি কি না পরীক্ষা করে।

### 10.2 Formatting Float Output

Float-এর output-এ নির্দিষ্ট decimal places দেখাতে f-string ব্যবহার করা যায়।

```python
price = 125.7564

print(f"{price:.2f}")
```

Output:

```text
125.76
```

এখানে `.2f` দিয়ে দুই decimal places দেখানো হয়েছে।

**Important:** Formatting শুধু প্রদর্শিত text পরিবর্তন করে; original variable-এর data type Float-ই থাকে।

## 11. Float vs Decimal

সাধারণ scientific ও mathematical calculation-এর জন্য `float` উপযোগী।

কিন্তু financial calculation-এ নির্দিষ্ট decimal arithmetic প্রয়োজন হতে পারে। সে ক্ষেত্রে `decimal.Decimal` ব্যবহার করা যায়।

Example:

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

এখানে Decimal value String থেকে তৈরি করা হয়েছে, যাতে নির্দিষ্ট decimal representation ব্যবহার করা যায়।

**মনে রাখবে:** সব ক্ষেত্রে `float` ভুল নয়। প্রয়োজন অনুযায়ী `float` অথবা `Decimal` বেছে নিতে হবে।

## 12. Common Errors with `float()`

### 12.1 Invalid String

```python
number = float("Python")
```

এটি `ValueError` তৈরি করবে, কারণ `"Python"` valid numeric representation নয়।

### 12.2 Comma-Separated Number

```python
number = float("1,000.50")
```

এটি `ValueError` তৈরি করবে।

Python-এর সাধারণ `float()` function হাজারের separator হিসেবে comma গ্রহণ করে না।

### 12.3 Complex Number

```python
number = float(2 + 3j)
```

এটি `TypeError` তৈরি করবে।

### 12.4 Passing `None`

```python
number = float(None)
```

এটিও `TypeError` তৈরি করবে।

### 12.5 Confusing Formatting with Conversion

```python
number = 25.6789

print(f"{number:.2f}")
print(number)
```

Output:

```text
25.68
25.6789
```

প্রথম লাইনে output format করা হয়েছে। দ্বিতীয় লাইনে original Float value দেখানো হয়েছে।

## 13. Practical Examples

### Example 1: Calculate Total Price

```python
price = float(input("Enter price: "))
quantity = int(input("Enter quantity: "))

total = price * quantity

print(f"Total price: {total:.2f}")
```

Input:

```text
12.50
4
```

Output:

```text
Total price: 50.00
```

### Example 2: Calculate Average Marks

```python
mark1 = float(input("Enter first mark: "))
mark2 = float(input("Enter second mark: "))
mark3 = float(input("Enter third mark: "))

average = (mark1 + mark2 + mark3) / 3

print(f"Average marks: {average:.2f}")
```

### Example 3: Convert Scientific Notation

```python
number = float("4.2e3")

print(number)
```

Output:

```text
4200.0
```

### Example 4: Compare Float Values Safely

```python
import math

a = 0.1 + 0.2
b = 0.3

if math.isclose(a, b):
    print("Values are close.")
else:
    print("Values are different.")
```

Output:

```text
Values are close.
```

## 14. Practice Exercises

### Exercise 1: Basic Conversion

নিচের String-গুলোকে Float-এ convert করো:

```python
a = "10"
b = "12.75"
c = "-5.5"
```

প্রতিটি result-এর type পরীক্ষা করো।

### Exercise 2: Integer to Float

`25`, `0` এবং `-10`-কে Float-এ convert করো।

### Exercise 3: Boolean to Float

```python
print(float(True))
print(float(False))
```

Output ব্যাখ্যা করো।

### Exercise 4: Scientific Notation

নিচের expression-গুলোর output অনুমান করো:

```python
print(float("2e3"))
print(float("5e-2"))
print(float("1.25e2"))
```

### Exercise 5: Floating-Point Precision

নিচের code চালাও এবং result ব্যাখ্যা করো:

```python
print(0.1 + 0.2)
print(0.1 + 0.2 == 0.3)
```

এরপর `math.isclose()` ব্যবহার করে তুলনা করো।

### Exercise 6: Invalid Conversion

নিচের কোন expression-গুলো error তৈরি করবে, তা শনাক্ত করো:

```python
float("12.5")
float("hello")
float(None)
float("1e3")
float("1,000")
```

### Exercise 7: Calculate Average

User-এর কাছ থেকে তিনটি decimal number নিয়ে তাদের average বের করো। Result দুই decimal places-এ দেখাও।

### Exercise 8: Float and Decimal

`0.1 + 0.2`-এর Float result এবং `Decimal("0.1") + Decimal("0.2")`-এর result তুলনা করো।

### Exercise 9: Mini Project — Shopping Bill

একটি program তৈরি করো, যেখানে user প্রতিটি পণ্যের unit price এবং quantity দেবে। Program-টি:

1. Price-কে Float-এ convert করবে।
2. Quantity-কে Integer-এ convert করবে।
3. Total cost হিসাব করবে।
4. Total cost দুই decimal places-এ দেখাবে।

## 15. Key Takeaways

- `float()` উপযুক্ত value-কে Floating-Point number-এ convert করে।
- Integer, valid numeric String এবং Boolean value থেকে Float তৈরি করা যায়।
- `float()` Scientific Notation support করে।
- `float("inf")` এবং `float("nan")` special Float value তৈরি করে।
- Binary floating-point representation-এর কারণে precision error দেখা যেতে পারে।
- কাছাকাছি Float value তুলনা করতে `math.isclose()` ব্যবহার করা যায়।
- `math.isnan()` ও `math.isinf()` special value পরীক্ষা করতে সাহায্য করে।
- f-string formatting output-এর appearance পরিবর্তন করে, original value-এর type নয়।
- Financial calculation-এ প্রয়োজন অনুযায়ী `Decimal` বিবেচনা করা যায়।

## 16. Next Topic

পরবর্তী ফাইল:

**`24_Converting_to_str.md`**

সেখানে `str()` function, বিভিন্ন data type থেকে String conversion, object-এর String representation এবং common mistakes বিস্তারিতভাবে শেখা হবে।