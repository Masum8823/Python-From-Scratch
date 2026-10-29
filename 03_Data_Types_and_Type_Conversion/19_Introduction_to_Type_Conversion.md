# 19. Introduction to Type Conversion in Python

## 1. What Is Type Conversion?

**Type Conversion** হলো একটি value-কে এক data type থেকে অন্য data type-এ রূপান্তর করার প্রক্রিয়া।

Python-এ বিভিন্ন data type রয়েছে, যেমন:

- `int` — Integer number
- `float` — Decimal number
- `str` — Text
- `bool` — Boolean value
- `list` — Ordered collection
- `tuple` — Immutable ordered collection
- `set` — Unique elements-এর collection

কখনো একটি data type-এর value অন্য data type-এর প্রয়োজন হয়। তখন Type Conversion ব্যবহার করা হয়।

Example:

```python
number = "100"

print(number)
print(type(number))
```

Output:

```text
100
<class 'str'>
```

এখানে `"100"` দেখতে number-এর মতো হলেও এটি একটি String।

এটিকে Integer-এ রূপান্তর করা যায়:

```python
number = "100"

converted_number = int(number)

print(converted_number)
print(type(converted_number))
```

Output:

```text
100
<class 'int'>
```

এখানে `int()` String থেকে Integer তৈরি করেছে।

**মনে রাখবে:** কোনো value দেখতে number-এর মতো হলেই সেটি Numeric data type হয়ে যায় না।

## 2. Why Do We Need Type Conversion?

Python program-এ Type Conversion বিভিন্ন কারণে প্রয়োজন হয়।

### 2.1 Performing Mathematical Operations

User-এর কাছ থেকে input নিলে Python সাধারণত সেটিকে String হিসেবে গ্রহণ করে।

```python
a = input("Enter first number: ")
b = input("Enter second number: ")

print(a + b)
```

Input:

```text
10
20
```

Output:

```text
1020
```

কেন `30` আসেনি?

কারণ `input()` দুটি String return করেছে। String-এর ক্ষেত্রে `+` concatenation করে।

Integer-এ রূপান্তর করলে:

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print(a + b)
```

Input:

```text
10
20
```

Output:

```text
30
```

এখানে `int()` input-কে Integer-এ রূপান্তর করেছে।

### 2.2 Converting Numbers into Text

কখনো একটি number-এর সঙ্গে text যুক্ত করতে হয়।

```python
age = 22

message = "My age is " + str(age)

print(message)
```

Output:

```text
My age is 22
```

এখানে `str()` Integer-কে String-এ রূপান্তর করেছে।

### 2.3 Processing Different Data Formats

Data file, API, database বা user input থেকে এলে প্রয়োজন অনুযায়ী data type পরিবর্তন করতে হতে পারে।

```python
price = "250.50"

price = float(price)

print(price * 2)
```

Output:

```text
501.0
```

এখানে String-কে Float-এ রূপান্তর করে multiplication করা হয়েছে।

### 2.4 Working with Collections

একটি collection-কে অন্য collection type-এ রূপান্তর করাও প্রয়োজন হতে পারে।

```python
numbers = [1, 2, 3]

result = tuple(numbers)

print(result)
print(type(result))
```

Output:

```text
(1, 2, 3)
<class 'tuple'>
```

এখানে `list`-কে `tuple`-এ রূপান্তর করা হয়েছে।

## 3. Main Types of Type Conversion

Python-এ Type Conversion প্রধানত দুই ধরনের:

1. Implicit Type Conversion
2. Explicit Type Conversion

<text weight="medium">Implicit Type Conversion</text>

Python নিজে প্রয়োজন অনুযায়ী একটি compatible data type থেকে অন্য data type-এ conversion করে।

<text weight="medium">Explicit Type Conversion</text>

Programmer নিজে `int()`, `float()`, `str()`-এর মতো function ব্যবহার করে conversion করে।

এই দুই ধরনের conversion পরবর্তী ফাইলগুলোতে বিস্তারিত আলোচনা করা হবে।

## 4. Common Type Conversion Functions

Python-এ বহুল ব্যবহৃত কিছু conversion function নিচে দেওয়া হলো।

| Function | কাজ | Example | Result |
|---|---|---|---|
| `int()` | Integer-এ রূপান্তর | `int("25")` | `25` |
| `float()` | Float-এ রূপান্তর | `float("3.5")` | `3.5` |
| `str()` | String-এ রূপান্তর | `str(100)` | `"100"` |
| `bool()` | Boolean-এ রূপান্তর | `bool(1)` | `True` |
| `list()` | List তৈরি | `list((1, 2))` | `[1, 2]` |
| `tuple()` | Tuple তৈরি | `tuple([1, 2])` | `(1, 2)` |
| `set()` | Set তৈরি | `set([1, 1, 2])` | `{1, 2}` |
| `dict()` | Dictionary তৈরি | `dict([("a", 1)])` | `{'a': 1}` |
| `bytes()` | Bytes তৈরি | `bytes([65, 66])` | `b'AB'` |

**Important:** সব value-কে সব data type-এ সফলভাবে রূপান্তর করা যায় না।

যেমন:

```python
print(int("hello"))
```

এটি `ValueError` তৈরি করবে, কারণ `"hello"` একটি valid Integer representation নয়।

## 5. Conversion Does Not Always Change the Original Variable

Type Conversion করলে নতুন value তৈরি হতে পারে। Conversion-এর result original variable-এ assign না করলে original value পরিবর্তিত হয় না।

Example:

```python
number = "100"

int(number)

print(number)
print(type(number))
```

Output:

```text
100
<class 'str'>
```

এখানে `int(number)` conversion করলেও result variable-এ রাখা হয়নি। তাই `number` এখনও String।

সঠিক পদ্ধতি:

```python
number = "100"

number = int(number)

print(number)
print(type(number))
```

Output:

```text
100
<class 'int'>
```

এখানে conversion-এর result আবার `number`-এ assign করা হয়েছে।

অথবা আলাদা variable ব্যবহার করা যায়:

```python
text = "100"

number = int(text)

print(type(text))
print(type(number))
```

Output:

```text
<class 'str'>
<class 'int'>
```

এভাবে original String-টিও সংরক্ষিত থাকে।

## 6. Type Conversion and Data Loss

কিছু conversion-এর সময় original value-এর নির্দিষ্ট তথ্য হারিয়ে যেতে পারে।

### Example 1: Float to Integer

```python
number = 12.9

result = int(number)

print(result)
```

Output:

```text
12
```

এখানে decimal অংশ বাদ পড়েছে। `int()` সাধারণত Float-এর fractional অংশ বাদ দেয়; এটি সাধারণ rounding নয়।

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

এখানে duplicate value বাদ গেছে। Set-এর element order-এর ওপর নির্ভর করা উচিত নয়।

### Example 3: String to Integer

```python
number = int("007")

print(number)
```

Output:

```text
7
```

এখানে String-এর leading zeros আর থাকে না, কারণ Integer value হিসেবে `007` এবং `7` একই সংখ্যা।

**মনে রাখবে:** Type Conversion করার আগে ভাববে, original data-এর কোনো অংশ হারিয়ে যাবে কি না।

## 7. Type Conversion and User Input

`input()` function সব সময় String return করে। তাই input-এর data type অনুযায়ী conversion করতে হয়।

### Integer Input

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

### Float Input

```python
price = float(input("Enter product price: "))

print(price)
```

Input:

```text
99.5
```

Output:

```text
99.5
```

### String Input

```python
name = input("Enter your name: ")

print(name)
print(type(name))
```

এখানে আলাদা conversion প্রয়োজন নেই, কারণ `input()` ইতিমধ্যেই String return করে।

**সতর্কতা:** User যদি Integer চাওয়া হলে `hello` লেখে, তাহলে `int()` ব্যবহার করে সরাসরি conversion করলে `ValueError` হবে। এমন input handle করার পদ্ধতি আমরা Exception Handling অধ্যায়ে শিখব।

## 8. Common Beginner Mistakes

### Mistake 1: Assuming `input()` Returns a Number

```python
number = input("Enter a number: ")

print(number + 5)
```

এখানে String এবং Integer যোগ করার চেষ্টা করায় `TypeError` হবে।

Correct:

```python
number = int(input("Enter a number: "))

print(number + 5)
```

### Mistake 2: Using `int()` on a Decimal String

```python
number = int("12.5")
```

এটি `ValueError` তৈরি করবে। কারণ `"12.5"` সরাসরি Integer representation নয়।

Correct:

```python
number = int(float("12.5"))

print(number)
```

Output:

```text
12
```

এখানে প্রথমে Float এবং তারপর Integer-এ conversion হয়েছে। Decimal অংশ বাদ গেছে।

### Mistake 3: Forgetting to Store the Result

```python
number = "50"

int(number)

print(type(number))
```

Output:

```text
<class 'str'>
```

Correct:

```python
number = int(number)
```

### Mistake 4: Assuming Every String Can Become a Number

```python
value = int("Python")
```

এটি `ValueError` তৈরি করবে। শুধু উপযুক্ত numeric representation-ই `int()` দিয়ে রূপান্তর করা যায়।

### Mistake 5: Confusing Conversion with Formatting

```python
price = 25.5

print(str(price))
```

এখানে number-টি String-এ রূপান্তর হয়েছে। কিন্তু এটি নির্দিষ্ট decimal places-এ format করা হয়নি।

নির্দিষ্ট format-এর জন্য:

```python
price = 25.5

print(f"{price:.2f}")
```

Output:

```text
25.50
```

এখানে f-string formatting ব্যবহার হয়েছে; `price`-এর original type Float-ই রয়েছে।

## 9. Practice Exercises

### Exercise 1: String to Integer

`"250"` String-কে Integer-এ রূপান্তর করে এর সঙ্গে `50` যোগ করো।

Expected output:

```text
300
```

### Exercise 2: String to Float

`"19.75"`-কে Float-এ রূপান্তর করে এর সঙ্গে `0.25` যোগ করো।

### Exercise 3: Integer to String

`100`-কে String-এ রূপান্তর করো এবং result-এর type পরীক্ষা করো।

### Exercise 4: User Input Conversion

User-এর কাছ থেকে দুটি সংখ্যা নাও এবং তাদের যোগফল print করো।

### Exercise 5: Identify the Error

নিচের code-এ কী সমস্যা আছে ব্যাখ্যা করো:

```python
number = int("hello")
```

### Exercise 6: Float to Integer

`15.99`-কে Integer-এ রূপান্তর করো। Result কেন `16` নয়, তা ব্যাখ্যা করো।

### Exercise 7: List to Set

```python
numbers = [1, 2, 2, 3, 4, 4]
```

এটিকে Set-এ রূপান্তর করে duplicate value-এর কী হয় তা পর্যবেক্ষণ করো।

### Exercise 8: Data Type Checking

```python
value = "123"
```

এই value-কে Integer-এ রূপান্তর করো। Conversion-এর আগে ও পরে `type()` ব্যবহার করে data type তুলনা করো।

## 10. Key Takeaways

- Type Conversion হলো এক data type থেকে অন্য data type-এ রূপান্তর।
- Python-এ প্রধানত Implicit এবং Explicit Type Conversion রয়েছে।
- `int()`, `float()`, `str()` ও `bool()` বহুল ব্যবহৃত conversion function।
- `input()` সব সময় String return করে।
- Conversion-এর result ব্যবহার করতে সেটি variable-এ assign করা যায়।
- কিছু conversion-এর সময় data loss হতে পারে।
- সব value-কে সব data type-এ রূপান্তর করা যায় না।
- Invalid conversion-এর কারণে `ValueError` বা `TypeError` হতে পারে।
- Conversion এবং formatting আলাদা বিষয়।

## 11. Next Topic

পরবর্তী ফাইল:

**`20_Implicit_Type_Conversion.md`**

সেখানে Python কীভাবে নিজে থেকেই compatible numeric type-এর মধ্যে conversion করে এবং Integer ও Float-এর arithmetic operation-এ কী ঘটে, তা বিস্তারিত শেখা হবে।