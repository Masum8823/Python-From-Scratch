# 21. Explicit Type Conversion in Python

## 1. What Is Explicit Type Conversion?

**Explicit Type Conversion** হলো এমন একটি process, যেখানে Programmer নিজে conversion function ব্যবহার করে একটি value-কে অন্য data type-এ রূপান্তর করে।

একে Type Casting-ও বলা হয়।

Python-এ সাধারণত নিচের built-in function-গুলো ব্যবহার করা হয়:

- `int()`
- `float()`
- `str()`
- `bool()`
- `list()`
- `tuple()`
- `set()`
- `dict()`
- `bytes()`
- `bytearray()`

Example:

```python
number = "100"

result = int(number)

print(result)
print(type(result))
```

Output:

```text
100
<class 'int'>
```

এখানে `"100"` একটি String ছিল। Programmer `int()` ব্যবহার করে এটিকে Integer-এ রূপান্তর করেছে।

এটাই Explicit Type Conversion।

## 2. Why Do We Need Explicit Type Conversion?

Explicit Type Conversion বিভিন্ন কাজে প্রয়োজন হয়।

### 2.1 Converting User Input into Numbers

`input()` function String return করে। তাই mathematical operation-এর জন্য প্রয়োজন অনুযায়ী Integer বা Float-এ conversion করতে হয়।

```python
age = int(input("Enter your age: "))

print(age + 1)
```

Input:

```text
20
```

Output:

```text
21
```

### 2.2 Converting Numbers into Strings

Number-এর সঙ্গে text যুক্ত করতে বা text হিসেবে সংরক্ষণ করতে `str()` ব্যবহার করা যায়।

```python
age = 20

message = "My age is " + str(age)

print(message)
```

Output:

```text
My age is 20
```

### 2.3 Converting Between Collections

একটি List-কে Tuple বা Set-এ রূপান্তর করা যায়।

```python
numbers = [1, 2, 2, 3]

print(tuple(numbers))
print(set(numbers))
```

Output-এর একটি সম্ভাব্য রূপ:

```text
(1, 2, 2, 3)
{1, 2, 3}
```

Tuple-এ duplicate value থাকে, কিন্তু Set duplicate element বাদ দেয়।

## 3. Using `int()` for Integer Conversion

`int()` function উপযুক্ত value-কে Integer-এ রূপান্তর করে।

```python
print(int("25"))
print(int(7.9))
print(int(True))
```

Output:

```text
25
7
1
```

এখানে:

- `"25"` String থেকে Integer হয়েছে।
- `7.9` থেকে decimal অংশ বাদ গেছে।
- `True` Integer value `1` হয়েছে।

`int()` সাধারণ rounding করে না। এটি Float-এর fractional অংশ বাদ দেয়।

### Invalid Conversion

```python
number = int("hello")
```

এটি `ValueError` তৈরি করবে, কারণ `"hello"` valid Integer representation নয়।

**বিস্তারিত আলোচনা:** `22_Converting_to_int.md` ফাইলে থাকবে।

## 4. Using `float()` for Floating-Point Conversion

`float()` উপযুক্ত numeric value-কে Floating-Point number-এ রূপান্তর করে।

```python
print(float("12.5"))
print(float(10))
print(float(True))
```

Output:

```text
12.5
10.0
1.0
```

এখানে Integer `10`-ও Float `10.0` হয়েছে।

### Invalid Conversion

```python
number = float("Python")
```

এটি `ValueError` তৈরি করবে।

**বিস্তারিত আলোচনা:** `23_Converting_to_float.md` ফাইলে থাকবে।

## 5. Using `str()` for String Conversion

`str()` function বিভিন্ন ধরনের value-কে String representation-এ রূপান্তর করে।

```python
print(str(100))
print(str(12.5))
print(str(True))
print(str(None))
```

Output:

```text
100
12.5
True
None
```

এখানে output দেখতে আগের value-এর মতো হলেও প্রতিটি result হলো String।

Example:

```python
number = 100
text = str(number)

print(type(number))
print(type(text))
```

Output:

```text
<class 'int'>
<class 'str'>
```

**মনে রাখবে:** `str(100)` হলো `"100"`। এটি Integer `100` নয়।

**বিস্তারিত আলোচনা:** `24_Converting_to_str.md` ফাইলে থাকবে।

## 6. Using `bool()` for Boolean Conversion

`bool()` function কোনো value-এর truth value নির্ধারণ করে `True` অথবা `False` return করে।

```python
print(bool(1))
print(bool(0))
print(bool(""))
print(bool("Python"))
```

Output:

```text
True
False
False
True
```

সাধারণ নিয়ম:

- Zero numeric value → `False`
- Empty String → `False`
- Empty Collection → `False`
- `None` → `False`
- Non-zero number → `True`
- Non-empty String → `True`
- Non-empty Collection → `True`

বিশেষভাবে মনে রাখবে, `"False"` একটি non-empty String। তাই:

```python
print(bool("False"))
```

Output:

```text
True
```

কারণ `bool()` String-এর ভেতরের শব্দের অর্থ দেখে না; String empty কি না, সেটি দেখে।

**বিস্তারিত আলোচনা:** `25_Converting_to_bool.md` ফাইলে থাকবে।

## 7. Converting Between Collection Types

Python-এ একটি collection-কে অন্য collection type-এ রূপান্তর করা যায়।

### 7.1 `list()`

Iterable থেকে List তৈরি করে।

```python
result = list((10, 20, 30))

print(result)
```

Output:

```text
[10, 20, 30]
```

### 7.2 `tuple()`

Iterable থেকে Tuple তৈরি করে।

```python
result = tuple([10, 20, 30])

print(result)
```

Output:

```text
(10, 20, 30)
```

### 7.3 `set()`

Iterable থেকে Set তৈরি করে এবং duplicate element বাদ দেয়।

```python
result = set([1, 2, 2, 3])

print(result)
```

Output-এর একটি সম্ভাব্য রূপ:

```text
{1, 2, 3}
```

Set-এর element order নির্ভরযোগ্যভাবে ধরে নেওয়া উচিত নয়।

### 7.4 `dict()`

উপযুক্ত key-value pair থেকে Dictionary তৈরি করা যায়।

```python
result = dict([("name", "Masum"), ("age", 22)])

print(result)
```

Output:

```text
{'name': 'Masum', 'age': 22}
```

এখানে প্রতিটি pair-এর প্রথম value হলো key এবং দ্বিতীয় value হলো value।

Invalid structure দিলে `dict()` error তৈরি করতে পারে।

**বিস্তারিত আলোচনা:** `26_Converting_Between_Collection_Types.md` ফাইলে থাকবে।

## 8. Explicit Conversion and Data Loss

কিছু conversion-এর ফলে original data-এর তথ্য হারিয়ে যেতে পারে।

### Example 1: Float to Integer

```python
number = 9.8

result = int(number)

print(result)
```

Output:

```text
9
```

Decimal অংশ বাদ গেছে।

### Example 2: List to Set

```python
numbers = [1, 2, 2, 3, 3]

result = set(numbers)

print(result)
```

Output-এর একটি সম্ভাব্য রূপ:

```text
{1, 2, 3}
```

Duplicate value বাদ গেছে।

### Example 3: Integer to String

```python
number = 100

result = str(number)

print(result)
```

Output:

```text
100
```

এখানে সংখ্যাটি String হয়েছে। এর ফলে mathematical operation-এর আচরণ পরিবর্তিত হতে পারে।

```python
number = 100
text = str(number)

print(text + "20")
```

Output:

```text
10020
```

এখানে `+` দুটি String যুক্ত করেছে, arithmetic addition করেনি।

## 9. Explicit Conversion May Fail

Explicit Conversion করলেই যে conversion সফল হবে, এমন নয়।

### 9.1 `ValueError`

যখন value-এর format নির্দিষ্ট conversion-এর জন্য উপযুক্ত নয়, তখন সাধারণত `ValueError` হতে পারে।

```python
number = int("hello")
```

### 9.2 `TypeError`

যখন function-এ এমন type দেওয়া হয় যা ওই operation-এর জন্য গ্রহণযোগ্য নয়, তখন `TypeError` হতে পারে।

```python
number = int(None)
```

### 9.3 `OverflowError`

কিছু numeric conversion-এ value represent করা সম্ভব না হলে `OverflowError` হতে পারে। উদাহরণস্বরূপ, অত্যন্ত বড় finite Float তৈরি করার চেষ্টা কিছু ক্ষেত্রে এই error দিতে পারে।

Error-এর ধরন নির্ভর করে কোন conversion করা হচ্ছে এবং কী input দেওয়া হচ্ছে তার ওপর।

## 10. Explicit Conversion vs Implicit Conversion

| Feature | Explicit Conversion | Implicit Conversion |
|---|---|---|
| Conversion করে | Programmer | Python |
| Function ব্যবহার | সাধারণত ব্যবহার করা হয় | সরাসরি conversion function লাগে না |
| Example | `int("10")` | `10 + 2.5` |
| Control | Programmer-এর হাতে | Python-এর operation rules অনুযায়ী |
| Invalid operation | Error হতে পারে | Incompatible operation-এ error হতে পারে |

Example:

```python
# Explicit Conversion
a = int("10")

# Implicit Numeric Promotion
b = 10 + 2.5

print(a, type(a))
print(b, type(b))
```

Output:

```text
10 <class 'int'>
12.5 <class 'float'>
```

## 11. Best Practices for Explicit Conversion

### 11.1 Convert Data at the Right Time

User input নেওয়ার পর প্রয়োজন অনুযায়ী conversion করো।

```python
age_text = input("Enter your age: ")
age = int(age_text)

print(age + 1)
```

### 11.2 Validate Untrusted Input

User-এর input সব সময় সঠিক হবে—এমন ধরে নেওয়া উচিত নয়।

```python
text = input("Enter a whole number: ")

if text.isdigit():
    number = int(text)
    print(number)
else:
    print("Please enter a valid non-negative whole number.")
```

এই উদাহরণটি শুধু non-negative digit-only input গ্রহণ করে। Negative number বা decimal গ্রহণ করার জন্য আলাদা validation দরকার।

### 11.3 Do Not Convert Without a Reason

যে value-এর type পরিবর্তন করার প্রয়োজন নেই, সেটিকে অপ্রয়োজনে convert করার দরকার নেই।

```python
name = input("Enter your name: ")
```

এখানে `input()` ইতিমধ্যেই String return করে। তাই `str(input(...))` সাধারণত প্রয়োজন নেই।

### 11.4 Check Whether Conversion Loses Information

Float-কে Integer-এ বা List-কে Set-এ রূপান্তর করার আগে ফলাফলে তথ্য হারাবে কি না, তা বিবেচনা করো।

## 12. Practice Exercises

### Exercise 1: String to Integer

`"150"`-কে Integer-এ convert করে এর সঙ্গে `50` যোগ করো।

Expected output:

```text
200
```

### Exercise 2: Float to Integer

`19.99`-কে Integer-এ convert করো। কেন result `20` নয়, তা ব্যাখ্যা করো।

### Exercise 3: Number to String

`250`-কে String-এ convert করে এর সঙ্গে `" Tk"` যোগ করো।

Expected output:

```text
250 Tk
```

### Exercise 4: Boolean Conversion

নিচের প্রতিটি expression-এর result অনুমান করো:

```python
print(bool(0))
print(bool(-1))
print(bool(""))
print(bool("0"))
print(bool([]))
print(bool([0]))
```

### Exercise 5: List to Tuple

```python
numbers = [10, 20, 30]
```

এটিকে Tuple-এ convert করো এবং result-এর type পরীক্ষা করো।

### Exercise 6: List to Set

```python
numbers = [1, 1, 2, 3, 3, 4]
```

এটিকে Set-এ convert করো। Duplicate element-এর কী হয় তা ব্যাখ্যা করো।

### Exercise 7: Dictionary Conversion

নিচের pair-গুলো থেকে Dictionary তৈরি করো:

```python
pairs = [("name", "Masum"), ("department", "CSE")]
```

### Exercise 8: Find the Error

```python
number = int("12.5")
```

কেন error হচ্ছে? সঠিকভাবে Float এবং Integer conversion করে দেখাও।

### Exercise 9: Type Comparison

```python
a = 50
b = str(a)
c = float(a)
```

`a`, `b` এবং `c`-এর value ও type print করো।

### Exercise 10: Mini Project — Simple Calculator

একটি program তৈরি করো, যা:

1. User-এর কাছ থেকে দুটি সংখ্যা নেবে।
2. Input-গুলোকে Float-এ convert করবে।
3. যোগফল, বিয়োগফল ও গুণফল দেখাবে।
4. দুই নম্বরটি zero না হলে ভাগফল দেখাবে।
5. প্রতিটি result-এর type পরীক্ষা করবে।

## 13. Key Takeaways

- Explicit Type Conversion-এ Programmer নিজে conversion function ব্যবহার করে।
- `int()`, `float()`, `str()` ও `bool()` সবচেয়ে গুরুত্বপূর্ণ conversion function।
- `list()`, `tuple()`, `set()` ও `dict()` দিয়ে collection conversion করা যায়।
- সব conversion সফল হয় না; invalid input-এ error হতে পারে।
- কিছু conversion-এর ফলে তথ্য হারিয়ে যেতে পারে।
- `str()` দিয়ে number-কে String করলে পরবর্তী `+` operation concatenation করতে পারে।
- User input convert করার আগে validation গুরুত্বপূর্ণ।
- Conversion করার আগে result-এর type এবং সম্ভাব্য data loss বিবেচনা করা উচিত।

## 14. Next Topic

পরবর্তী ফাইল:

**`22_Converting_to_int.md`**

সেখানে `int()` function-এর syntax, supported input, base conversion, Float থেকে Integer conversion, Boolean conversion এবং common errors বিস্তারিতভাবে শেখা হবে।