# 02. Overview of Built-in Data Types

## 1. Introduction

Python-এ বিভিন্ন ধরনের data সংরক্ষণ ও পরিচালনার জন্য built-in data types রয়েছে।

উদাহরণস্বরূপ:

```python
name = "Masum"
age = 22
cgpa = 3.95
is_student = True
skills = ["Python", "C++", "SQL"]
```

এখানে প্রতিটি variable-এর value আলাদা ধরনের data প্রকাশ করে।

- `name` একটি string।
- `age` একটি integer।
- `cgpa` একটি float।
- `is_student` একটি Boolean।
- `skills` একটি list।

সঠিক data type নির্বাচন করলে data নিয়ে কাজ করা সহজ হয় এবং অপ্রয়োজনীয় error এড়ানো যায়।

## 2. Categories of Python Built-in Data Types

Python-এর built-in data types-কে কয়েকটি প্রধান category-তে ভাগ করা যায়।

| Category | Data Types | Main Purpose |
|---|---|---|
| Numeric | `int`, `float`, `complex` | সংখ্যা ও calculation |
| Text | `str` | Text সংরক্ষণ |
| Boolean | `bool` | `True` বা `False` প্রকাশ |
| None | `NoneType` | Value অনুপস্থিত বোঝানো |
| Sequence | `list`, `tuple`, `range` | Ordered values সংরক্ষণ |
| Mapping | `dict` | Key-value pairs সংরক্ষণ |
| Set | `set`, `frozenset` | Unique elements সংরক্ষণ |
| Binary | `bytes`, `bytearray`, `memoryview` | Binary data নিয়ে কাজ |

এই chapter-এ আমরা গুরুত্বপূর্ণ data types-গুলোর বৈশিষ্ট্য, ব্যবহার এবং পার্থক্য শিখব।

## 3. Numeric Data Types

Numeric data types সংখ্যাসংক্রান্ত data এবং mathematical operations-এর জন্য ব্যবহৃত হয়।

### 3.1 Integer — `int`

পূর্ণসংখ্যা সংরক্ষণ করতে `int` ব্যবহার করা হয়।

```python
age = 22
marks = 85
temperature = -5

print(type(age))
```

Output:

```text
<class 'int'>
```

Python-এর integer-এর নির্দিষ্ট fixed maximum value নেই; তবে ব্যবহারিক সীমা available memory দ্বারা প্রভাবিত হয়।

**Use cases:** বয়স, শিক্ষার্থীর সংখ্যা, পূর্ণসংখ্যার marks এবং counting।

### 3.2 Floating-Point — `float`

Decimal বা floating-point number সংরক্ষণ করতে `float` ব্যবহার করা হয়।

```python
cgpa = 3.95
price = 99.50
temperature = -2.5

print(type(cgpa))
```

Output:

```text
<class 'float'>
```

**Use cases:** CGPA, price, measurement এবং decimal calculation।

মনে রাখবে, `float` অনেক decimal value-কে binary floating-point representation-এ আনুমানিকভাবে সংরক্ষণ করে। তাই কিছু calculation-এ ছোট precision difference দেখা যেতে পারে।

### 3.3 Complex — `complex`

Complex number-এর real ও imaginary অংশ থাকে।

```python
number = 2 + 3j

print(number)
print(type(number))
```

Output:

```text
(2+3j)
<class 'complex'>
```

এখানে `2` হলো real part এবং `3j` হলো imaginary part।

**Use cases:** Scientific computing, engineering এবং complex-number mathematics।

## 4. Text Data Type

### String — `str`

Text বা character sequence সংরক্ষণ করতে `str` ব্যবহার করা হয়।

```python
name = "Masum"
university = "Northern University Bangladesh"
message = 'Welcome to Python'

print(type(name))
```

Output:

```text
<class 'str'>
```

String single quote অথবা double quote দিয়ে লেখা যায়।

String-এর গুরুত্বপূর্ণ বৈশিষ্ট্য:

- Text সংরক্ষণ করে।
- Ordered character sequence।
- Immutable; তৈরি হওয়ার পরে string-এর character সরাসরি পরিবর্তন করা যায় না।
- Indexing ও slicing সমর্থন করে।

Example:

```python
language = "Python"

print(language[0])
print(language[1:4])
```

Output:

```text
P
yth
```

**Use cases:** নাম, ঠিকানা, email, message এবং user input।

## 5. Boolean Data Type

### Boolean — `bool`

Boolean data type logical truth প্রকাশ করে।

এর দুটি value:

- `True`
- `False`

Example:

```python
is_student = True
is_graduated = False

print(type(is_student))
```

Output:

```text
<class 'bool'>
```

Boolean সাধারণত comparison ও logical condition-এর result হিসেবে পাওয়া যায়।

```python
age = 22

print(age >= 18)
print(age < 18)
```

Output:

```text
True
False
```

**Use cases:** Condition checking, validation এবং decision-making।

## 6. NoneType

### `NoneType` — `None`

কোনো value নেই বা বর্তমানে value অনুপস্থিত—এমন অবস্থা প্রকাশ করতে `None` ব্যবহার করা হয়।

```python
result = None

print(result)
print(type(result))
```

Output:

```text
None
<class 'NoneType'>
```

`None` কোনো number, string বা empty collection নয়।

এটি যাচাই করার প্রচলিত উপায়:

```python
if result is None:
    print("No result available")
```

Output:

```text
No result available
```

**Use cases:** কোনো result এখনো তৈরি হয়নি, optional value অনুপস্থিত, অথবা কোনো function স্পষ্টভাবে value return করছে না—এমন পরিস্থিতি।

## 7. Sequence Data Types

Sequence হলো এমন collection, যেখানে element-গুলোর একটি নির্দিষ্ট order থাকে। Sequence-এর element index দিয়ে access করা যায়।

### 7.1 List — `list`

List-এ একাধিক value সংরক্ষণ করা যায়।

```python
marks = [80, 85, 90]

print(type(marks))
print(marks[0])
```

Output:

```text
<class 'list'>
80
```

List-এর বৈশিষ্ট্য:

- Ordered।
- Mutable।
- Duplicate values থাকতে পারে।
- বিভিন্ন data type-এর value রাখা যায়।

Example:

```python
student = ["Masum", 22, 3.95, True]

student[0] = "Abdulla"

print(student)
```

Output:

```text
['Abdulla', 22, 3.95, True]
```

**Use cases:** Marks, shopping lists, tasks এবং পরিবর্তনযোগ্য collection।

### 7.2 Tuple — `tuple`

Tuple-ও একাধিক value সংরক্ষণ করে, কিন্তু tuple immutable।

```python
coordinates = (10, 20)

print(type(coordinates))
print(coordinates[0])
```

Output:

```text
<class 'tuple'>
10
```

Tuple-এর বৈশিষ্ট্য:

- Ordered।
- Immutable।
- Duplicate values থাকতে পারে।
- Indexing ও slicing সমর্থন করে।

**Use cases:** Coordinates, fixed records এবং এমন value-এর group যা তৈরি হওয়ার পরে পরিবর্তন করার প্রয়োজন নেই।

### 7.3 Range — `range`

`range` সাধারণত integer-এর একটি ধারাবাহিক sequence তৈরি করতে ব্যবহৃত হয়।

```python
numbers = range(1, 6)

print(list(numbers))
print(type(numbers))
```

Output:

```text
[1, 2, 3, 4, 5]
<class 'range'>
```

`range(1, 6)`-এ `1` অন্তর্ভুক্ত হয়, কিন্তু `6` অন্তর্ভুক্ত হয় না।

**Use cases:** নির্দিষ্ট সংখ্যক iteration এবং ধারাবাহিক integer নিয়ে কাজ করা।

## 8. Mapping Data Type

### Dictionary — `dict`

Dictionary data-কে key-value pair আকারে সংরক্ষণ করে।

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}

print(type(student))
print(student["name"])
```

Output:

```text
<class 'dict'>
Masum
```

Dictionary-এর বৈশিষ্ট্য:

- Key-value pair ব্যবহার করে।
- Key unique হতে হয়।
- Value পরিবর্তন করা যায়।
- Dictionary mutable।
- Python 3.7 এবং পরবর্তী version-এ insertion order বজায় থাকে।

**Use cases:** Student records, configuration, API data এবং structured information।

## 9. Set Data Types

Set-এর প্রধান বৈশিষ্ট্য হলো এটি unique elements সংরক্ষণ করে।

### 9.1 Set — `set`

```python
numbers = {10, 20, 20, 30}

print(numbers)
print(type(numbers))
```

Output-এর set-এ প্রতিটি unique value একবার থাকবে:

```text
{10, 20, 30}
<class 'set'>
```

Set-এর বৈশিষ্ট্য:

- Duplicate element থাকে না।
- সাধারণ indexing ব্যবহার করে element access করা যায় না।
- Set mutable।
- Union, intersection এবং difference-এর মতো set operations সমর্থন করে।

**Use cases:** Duplicate বাদ দেওয়া, unique values রাখা এবং common elements খুঁজে বের করা।

### 9.2 Frozen Set — `frozenset`

`frozenset` হলো immutable set।

```python
numbers = frozenset([10, 20, 20, 30])

print(numbers)
print(type(numbers))
```

এতে duplicate value বাদ পড়ে এবং তৈরি হওয়ার পরে element যোগ বা বাদ দেওয়া যায় না।

**Use cases:** Immutable set প্রয়োজন হলে এবং উপযুক্ত ক্ষেত্রে dictionary key হিসেবে ব্যবহার করতে।

## 10. Binary Data Types

Binary data types সাধারণ text-এর পরিবর্তে byte-ভিত্তিক data নিয়ে কাজ করে।

### 10.1 Bytes — `bytes`

`bytes` হলো immutable sequence of bytes।

```python
data = bytes([65, 66, 67])

print(data)
print(type(data))
```

Output:

```text
b'ABC'
<class 'bytes'>
```

এখানে byte value `65`, `66` এবং `67` ASCII-compatible representation-এ `A`, `B` এবং `C` হিসেবে দেখা যাচ্ছে।

### 10.2 Bytearray — `bytearray`

`bytearray` হলো mutable sequence of bytes।

```python
data = bytearray([65, 66, 67])

data[0] = 90

print(data)
```

Output:

```text
bytearray(b'ZBC')
```

### 10.3 Memoryview — `memoryview`

`memoryview` অন্য কোনো bytes-like object-এর data copy না করেই তার memory view তৈরি করতে পারে।

```python
data = bytearray(b"Python")
view = memoryview(data)

print(view[0])
```

Output:

```text
80
```

`80` হলো `P`-এর byte value।

এই তিনটি type সাধারণত binary file processing, network communication এবং performance-sensitive কাজের ক্ষেত্রে বেশি গুরুত্বপূর্ণ।

## 11. Mutable vs Immutable Data Types

Data type বোঝার জন্য একটি গুরুত্বপূর্ণ বিষয় হলো **mutability**।

- **Mutable:** Object তৈরি হওয়ার পরে তার content পরিবর্তন করা যায়।
- **Immutable:** Object তৈরি হওয়ার পরে তার content পরিবর্তন করা যায় না।

| Type | Mutable or Immutable |
|---|---|
| `int` | Immutable |
| `float` | Immutable |
| `complex` | Immutable |
| `bool` | Immutable |
| `str` | Immutable |
| `tuple` | Immutable |
| `range` | Immutable |
| `bytes` | Immutable |
| `frozenset` | Immutable |
| `list` | Mutable |
| `dict` | Mutable |
| `set` | Mutable |
| `bytearray` | Mutable |

**Important:** একটি tuple-এর মধ্যে mutable object থাকলে সেই nested object পরিবর্তন করা যেতে পারে। Tuple-এর element reference পরিবর্তন করা যায় না, কিন্তু nested list-এর content পরিবর্তন করা সম্ভব।

Example:

```python
data = ([10, 20], 30)

data[0].append(40)

print(data)
```

Output:

```text
([10, 20, 40], 30)
```

Tuple নিজে immutable হলেও এর মধ্যে থাকা list mutable।

## 12. Comparison of Important Data Types

| Type | Ordered | Mutable | Duplicates | Access Method |
|---|---|---|---|---|
| `str` | Yes | No | Characters may repeat | Index |
| `list` | Yes | Yes | Yes | Index |
| `tuple` | Yes | No | Yes | Index |
| `range` | Yes | No | Depends on range | Index |
| `dict` | Insertion order | Yes | Keys are unique | Key |
| `set` | No guaranteed positional order | Yes | No | Membership |
| `frozenset` | No guaranteed positional order | No | No | Membership |

এই table-টি revision-এর সময় ব্যবহার করতে পারো।

## 13. How to Choose the Right Data Type

কোনো data সংরক্ষণ করার আগে ভাববে, data-টি কীভাবে ব্যবহার করা হবে।

| Requirement | Suitable Type |
|---|---|
| পূর্ণসংখ্যা সংরক্ষণ | `int` |
| Decimal calculation | `float` |
| Text সংরক্ষণ | `str` |
| True/False result | `bool` |
| Value অনুপস্থিত বোঝানো | `None` |
| পরিবর্তনযোগ্য ordered collection | `list` |
| পরিবর্তনযোগ্য নয় এমন sequence | `tuple` |
| Unique values | `set` |
| Key-value information | `dict` |
| Integer sequence তৈরি | `range` |
| Immutable binary data | `bytes` |
| Mutable binary data | `bytearray` |

একই কাজ বিভিন্ন data type দিয়ে কখনো করা সম্ভব হলেও উপযুক্ত type ব্যবহার করলে code আরও পরিষ্কার হয়।

## 14. Common Beginner Mistakes

### Mistake 1: Empty Set তৈরি করতে `{}` ব্যবহার করা

ভুল ধারণা:

```python
data = {}

print(type(data))
```

Output:

```text
<class 'dict'>
```

সঠিক উপায়:

```python
data = set()

print(type(data))
```

Output:

```text
<class 'set'>
```

### Mistake 2: List ও Tuple-কে একই মনে করা

```python
a = [10, 20, 30]
b = (10, 20, 30)

a[0] = 100
print(a)
```

List-এর element পরিবর্তন করা যায়। কিন্তু tuple-এর element সরাসরি পরিবর্তন করতে গেলে `TypeError` হবে।

### Mistake 3: Set-এ Duplicate Value থাকবে মনে করা

```python
numbers = {1, 1, 2, 2, 3}

print(numbers)
```

Set শুধু unique elements রাখে। তবে set-এর printed order নির্দিষ্টভাবে ধরে নেওয়া উচিত নয়।

### Mistake 4: `None` এবং `"None"`-কে একই মনে করা

```python
a = None
b = "None"

print(type(a))
print(type(b))
```

Output:

```text
<class 'NoneType'>
<class 'str'>
```

### Mistake 5: Dictionary-এর Key ও Value গুলিয়ে ফেলা

```python
student = {"name": "Masum"}

print(student["name"])
```

এখানে `"name"` হলো key এবং `"Masum"` হলো value।

## 15. Practice Exercises

### Exercise 1: Identify the Types

নিচের প্রতিটি value-এর data type লিখো।

```python
a = 150
b = 15.75
c = 5 + 2j
d = "Python"
e = False
f = None
g = [1, 2, 3]
h = (1, 2, 3)
i = {1, 2, 3}
j = {"name": "Masum"}
k = range(5)
l = bytes([65, 66])
```

### Exercise 2: Choose the Right Type

প্রতিটি requirement-এর জন্য উপযুক্ত data type নির্বাচন করো।

1. একজন শিক্ষার্থীর নাম।
2. একজন শিক্ষার্থীর বয়স।
3. কোনো course-এর marks-এর list।
4. একটি fixed coordinate pair।
5. একটি unique student ID-এর collection।
6. একজন শিক্ষার্থীর বিস্তারিত record।
7. কোনো operation সফল হয়েছে কি না।
8. কোনো result এখনো পাওয়া যায়নি।
9. 1 থেকে 100 পর্যন্ত integer sequence।
10. Binary file-এর data।

### Exercise 3: Mutable or Immutable?

নিচের type-গুলো mutable নাকি immutable, তা লেখো:

- `int`
- `str`
- `list`
- `tuple`
- `dict`
- `set`
- `bytes`
- `bytearray`

### Exercise 4: Predict the Output

```python
numbers = [1, 2, 2, 3]
unique_numbers = set(numbers)

print(len(numbers))
print(len(unique_numbers))
```

### Exercise 5: Create a Student Record

একটি dictionary তৈরি করো, যাতে থাকবে:

- `name`
- `age`
- `department`
- `cgpa`
- `courses`

`courses`-এর value হিসেবে একটি list ব্যবহার করবে। এরপর প্রতিটি key-এর value print করবে।

### Exercise 6: Compare Collection Types

একই তিনটি value ব্যবহার করে একটি list, tuple এবং set তৈরি করো। তারপর:

1. প্রতিটির type দেখাও।
2. প্রতিটির length বের করো।
3. list-এর একটি element পরিবর্তন করো।
4. set-এ duplicate value দিলে কী ঘটে তা পরীক্ষা করো।

## 16. Key Takeaways

- Python-এর built-in data types বিভিন্ন ধরনের data পরিচালনা করে।
- Numeric types হলো `int`, `float` এবং `complex`।
- Text সংরক্ষণ করতে `str` ব্যবহার করা হয়।
- Logical values-এর জন্য `bool` ব্যবহার করা হয়।
- `None` value অনুপস্থিত বোঝায়।
- `list`, `tuple` এবং `range` হলো sequence types।
- `dict` key-value pairs সংরক্ষণ করে।
- `set` ও `frozenset` unique elements রাখে।
- `bytes`, `bytearray` এবং `memoryview` binary data-এর জন্য ব্যবহৃত হয়।
- Mutable object পরিবর্তন করা যায়; immutable object-এর content সরাসরি পরিবর্তন করা যায় না।
- কাজের ধরন অনুযায়ী সঠিক data type নির্বাচন করা গুরুত্বপূর্ণ।

## 17. Next Topic

পরবর্তী ফাইল:

**`03_Dynamic_Typing_in_Python.md`**

সেখানে আমরা শিখব Python-এ variable-এর type আগে থেকে declare না করেও কীভাবে কাজ করা যায়, reassignment-এর সময় কী ঘটে এবং variable ও object-এর মধ্যে সম্পর্ক কী।