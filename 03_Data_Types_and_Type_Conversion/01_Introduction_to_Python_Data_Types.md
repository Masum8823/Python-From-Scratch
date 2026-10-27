# 01. Introduction to Python Data Types

## 1. What Is a Data Type?

**Data Type** হলো কোনো value কী ধরনের data প্রকাশ করে, তা নির্ধারণ করার একটি উপায়।

Python-এ বিভিন্ন ধরনের data নিয়ে কাজ করা হয়। যেমন:

```python
name = "Masum"
age = 22
cgpa = 3.95
is_student = True
```

এখানে:

- `"Masum"` হলো text বা `str` type।
- `22` হলো integer বা `int` type।
- `3.95` হলো floating-point বা `float` type।
- `True` হলো Boolean বা `bool` type।

অর্থাৎ, সব value একই ধরনের নয়। Python প্রতিটি value-এর type অনুযায়ী সেটিকে পরিচালনা করে।

## 2. Why Do We Need Data Types?

Data Types জানার মাধ্যমে আমরা বুঝতে পারি কোনো value-এর সঙ্গে কী ধরনের operation করা যায়।

উদাহরণ:

```python
a = 10
b = 5

print(a + b)
```

Output:

```text
15
```

এখানে `a` এবং `b` দুটি integer। তাই `+` operator তাদের যোগ করেছে।

এবার দেখি:

```python
a = "10"
b = "5"

print(a + b)
```

Output:

```text
105
```

এখানে দুটি value-ই string। তাই `+` operator তাদের যোগ না করে পাশাপাশি যুক্ত করেছে।

আরেকটি example:

```python
age = 22
name = "Masum"

print(age + name)
```

এই code চালালে `TypeError` হবে, কারণ Python সাধারণভাবে integer ও string-কে সরাসরি যোগ করতে পারে না।

এ থেকে বোঝা যায়, **একই operator ভিন্ন data type-এর ওপর ভিন্নভাবে কাজ করতে পারে।**

Data Types জানা প্রয়োজন:

1. সঠিক calculation করার জন্য।
2. Input ও output সঠিকভাবে পরিচালনা করার জন্য।
3. Type-related errors এড়ানোর জন্য।
4. উপযুক্ত data structure নির্বাচন করার জন্য।
5. Program-কে আরও reliable ও readable করার জন্য।

## 3. How Does Python Handle Data Types?

Python-এ প্রতিটি value একটি object, এবং object-এর নিজস্ব type থাকে।

```python
x = 100
y = "Python"

print(type(x))
print(type(y))
```

Output:

```text
<class 'int'>
<class 'str'>
```

এখানে `type()` একটি built-in function, যা কোনো object-এর type সম্পর্কে তথ্য দেয়।

- `x` যে object-কে নির্দেশ করছে, সেটির type হলো `int`।
- `y` যে object-কে নির্দেশ করছে, সেটির type হলো `str`।

`<class 'int'>` output-এর অর্থ হলো object-টি Python-এর `int` class-এর instance।

**মনে রাখবে:** `type()` নিজে value-এর type পরিবর্তন করে না; শুধু type সম্পর্কে তথ্য দেয়।

## 4. Introduction to Python's Built-in Data Types

Python-এ অনেক built-in data type রয়েছে। এই chapter-এ আমরা সেগুলো বিস্তারিতভাবে শিখব।

### 4.1 Numeric Types

সংখ্যাসংক্রান্ত data-এর জন্য ব্যবহার করা হয়।

| Type | Example | Description |
|---|---|---|
| `int` | `25` | পূর্ণসংখ্যা |
| `float` | `3.14` | Floating-point number |
| `complex` | `2 + 3j` | Complex number |

Example:

```python
age = 25
price = 99.50
number = 2 + 3j

print(type(age))
print(type(price))
print(type(number))
```

Output:

```text
<class 'int'>
<class 'float'>
<class 'complex'>
```

### 4.2 Text Type

Text বা character sequence সংরক্ষণের জন্য `str` ব্যবহার করা হয়।

```python
name = "Masum"
language = 'Python'

print(type(name))
print(type(language))
```

Output:

```text
<class 'str'>
<class 'str'>
```

Python-এ single quote এবং double quote—দুটিই ব্যবহার করে string লেখা যায়।

### 4.3 Boolean Type

কোনো logical condition সত্য নাকি মিথ্যা, তা প্রকাশ করতে `bool` ব্যবহার করা হয়।

এর দুটি value:

- `True`
- `False`

Example:

```python
is_student = True
is_graduated = False

print(type(is_student))
print(type(is_graduated))
```

Output:

```text
<class 'bool'>
<class 'bool'>
```

Python-এ `True` এবং `False`-এর প্রথম অক্ষর capital হবে।

### 4.4 NoneType

কোনো value অনুপস্থিত বা এখনো নির্ধারণ করা হয়নি—এমন অবস্থা বোঝাতে `None` ব্যবহার করা হয়।

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

`None` এবং `0` একই নয়। একইভাবে `None` এবং empty string `""`-ও এক নয়।

### 4.5 Collection Types

একাধিক value একসঙ্গে সংরক্ষণ করতে collection types ব্যবহার করা হয়।

| Type | Example | Main Property |
|---|---|---|
| `list` | `[10, 20, 30]` | Ordered, mutable |
| `tuple` | `(10, 20, 30)` | Ordered, immutable |
| `set` | `{10, 20, 30}` | Unique elements |
| `dict` | `{"name": "Masum"}` | Key-value pairs |

Example:

```python
marks = [80, 85, 90]
coordinates = (10, 20)
unique_numbers = {1, 2, 3}
student = {"name": "Masum", "age": 22}

print(type(marks))
print(type(coordinates))
print(type(unique_numbers))
print(type(student))
```

Output:

```text
<class 'list'>
<class 'tuple'>
<class 'set'>
<class 'dict'>
```

এই collection types-গুলোর বিস্তারিত properties পরবর্তী file-গুলোতে শেখা হবে।

### 4.6 Binary Types

Binary data নিয়ে কাজ করার জন্য Python-এ `bytes` এবং `bytearray` রয়েছে।

```python
data = bytes([65, 66, 67])
mutable_data = bytearray([65, 66, 67])

print(type(data))
print(type(mutable_data))
```

Output:

```text
<class 'bytes'>
<class 'bytearray'>
```

এগুলো সাধারণ text string-এর মতো নয়। Binary file, network communication এবং অন্যান্য low-level data processing-এ এগুলো কাজে লাগে।

## 5. Data Type and Variable: What Is the Difference?

Variable এবং Data Type এক বিষয় নয়।

- **Variable:** যে নামের মাধ্যমে কোনো object-কে access করা হয়।
- **Data Type:** সেই object কোন ধরনের, তা নির্দেশ করে।

Example:

```python
value = 100

print(value)
print(type(value))
```

Output:

```text
100
<class 'int'>
```

এখানে `value` হলো variable name, আর `int` হলো object-এর type।

একই variable-এ পরবর্তীতে অন্য type-এর object assign করা যায়।

```python
value = 100
print(type(value))

value = "Python"
print(type(value))
```

Output:

```text
<class 'int'>
<class 'str'>
```

এটি সম্ভব, কারণ Python dynamically typed language। Dynamic typing-এর বিস্তারিত ব্যাখ্যা থাকবে `03_Dynamic_Typing_in_Python.md` ফাইলে।

## 6. How to Check a Data Type

Python-এ data type যাচাই করার দুটি গুরুত্বপূর্ণ উপায় হলো `type()` এবং `isinstance()`।

### Using `type()`

```python
age = 22

print(type(age))
```

Output:

```text
<class 'int'>
```

### Using `isinstance()`

```python
age = 22

print(isinstance(age, int))
print(isinstance(age, str))
```

Output:

```text
True
False
```

`isinstance()` যাচাই করে object-টি নির্দিষ্ট class বা type-এর instance কি না।

সাধারণ type checking-এর জন্য `isinstance()` অনেক ক্ষেত্রে বেশি উপযোগী, বিশেষ করে inheritance থাকলে।

## 7. Same-Looking Values Can Have Different Types

দেখতে একই রকম হলেও value-এর type আলাদা হতে পারে।

```python
a = 100
b = "100"

print(a)
print(b)

print(type(a))
print(type(b))
```

Output:

```text
100
100
<class 'int'>
<class 'str'>
```

এখানে:

- `100` হলো integer।
- `"100"` হলো string।

তাদের display একই রকম দেখালেও তাদের type এবং behavior আলাদা।

আরেকটি example:

```python
x = 5
y = 5.0

print(type(x))
print(type(y))

print(x == y)
```

Output:

```text
<class 'int'>
<class 'float'>
True
```

এখানে `x` ও `y`-এর type আলাদা, কিন্তু numeric value সমান হওয়ায় `x == y` ফলাফল `True`।

**মনে রাখবে:** Value সমান হওয়া এবং Data Type একই হওয়া এক বিষয় নয়।

## 8. Introduction to Type Conversion

একটি data type-এর value-কে অন্য data type-এ পরিবর্তন করাকে **Type Conversion** বলা হয়।

Example:

```python
age = "22"

age = int(age)

print(age)
print(type(age))
```

Output:

```text
22
<class 'int'>
```

এখানে `"22"` string থেকে `22` integer-এ convert হয়েছে।

Type conversion প্রধানত দুই ধরনের:

1. **Implicit Type Conversion:** Python স্বয়ংক্রিয়ভাবে type conversion করে।
2. **Explicit Type Conversion:** Programmer `int()`, `float()`, `str()` ইত্যাদি ব্যবহার করে conversion করে।

এই বিষয়গুলো Chapter-এর Section E-তে বিস্তারিত শেখা হবে।

## 9. Common Beginner Mistakes

### Mistake 1: Number-কে String ভেবে নেওয়া

```python
age = "22"

print(age + 5)
```

এখানে `TypeError` হবে, কারণ `age` একটি string।

সংশোধন:

```python
age = int("22")

print(age + 5)
```

Output:

```text
27
```

### Mistake 2: `type()`-কে Conversion Function মনে করা

```python
age = "22"

print(type(age))
```

এটি string-কে integer-এ convert করবে না। এটি শুধু type দেখাবে।

Conversion করতে হবে:

```python
age = int(age)

print(type(age))
```

### Mistake 3: `None`-কে String মনে করা

```python
result = None

print(type(result))
```

Output:

```text
<class 'NoneType'>
```

`None` একটি বিশেষ Python value; `"None"` একটি string।

### Mistake 4: Boolean Value ভুলভাবে লেখা

```python
is_active = true
```

এটি সাধারণ Python code-এ `NameError` তৈরি করবে, কারণ Boolean literal-এর সঠিক বানান `True`।

সঠিক:

```python
is_active = True
```

### Mistake 5: Empty Collection-এর Type ভুল বোঝা

```python
a = []
b = ()
c = {}
d = set()

print(type(a))
print(type(b))
print(type(c))
print(type(d))
```

Output:

```text
<class 'list'>
<class 'tuple'>
<class 'dict'>
<class 'set'>
```

বিশেষভাবে মনে রাখবে, `{}` একটি empty dictionary; empty set নয়। Empty set তৈরি করতে `set()` ব্যবহার করতে হয়।

## 10. Practice Exercises

### Exercise 1: Identify the Data Types

নিচের প্রতিটি variable-এর type অনুমান করো।

```python
a = 50
b = 5.75
c = "Python"
d = False
e = None
f = [1, 2, 3]
g = (1, 2, 3)
h = {"name": "Masum"}
i = {1, 2, 3}
```

প্রতিটি variable-এর জন্য `type()` ব্যবহার করে উত্তর যাচাই করো।

### Exercise 2: Predict the Output

```python
a = 10
b = "10"
c = 10.0

print(type(a))
print(type(b))
print(type(c))

print(a == c)
```

Code execute করার আগে output লিখে রাখো।

### Exercise 3: Fix the Error

```python
age = input("Enter your age: ")

print(age + 5)
```

Program-টিকে এমনভাবে সংশোধন করো, যাতে user age input দিলে তার সঙ্গে `5` যোগ করে result দেখায়।

### Exercise 4: Type Checking

একটি program লেখো, যেখানে:

1. `name` variable-এ নিজের নাম রাখবে।
2. `age` variable-এ নিজের বয়স রাখবে।
3. `cgpa` variable-এ নিজের CGPA রাখবে।
4. প্রতিটি variable-এর type `type()` দিয়ে দেখাবে।
5. `isinstance()` দিয়ে `age` integer কি না যাচাই করবে।

### Exercise 5: Conversion Practice

নিচের value-গুলো convert করার চেষ্টা করো:

- `"100"` থেকে `int`
- `"3.75"` থেকে `float`
- `250` থেকে `str`
- `0` থেকে `bool`
- `1` থেকে `bool`

প্রতিটি conversion-এর result এবং result-এর type print করো।

## 11. Key Takeaways

- Data Type কোনো value-এর ধরন এবং তার behavior বুঝতে সাহায্য করে।
- Python-এর প্রতিটি value একটি object।
- `type()` দিয়ে object-এর type দেখা যায়।
- `isinstance()` দিয়ে নির্দিষ্ট type বা class-এর instance যাচাই করা যায়।
- Python-এর গুরুত্বপূর্ণ built-in types-এর মধ্যে `int`, `float`, `complex`, `str`, `bool`, `NoneType`, `list`, `tuple`, `set`, `dict`, `bytes` এবং `bytearray` রয়েছে।
- একই রকম দেখতে value-এর type আলাদা হতে পারে।
- Variable-এর নাম এবং তার refer করা object-এর type এক বিষয় নয়।
- Type conversion-এর মাধ্যমে value-কে অন্য type-এ রূপান্তর করা যায়।
- সঠিক data type ব্যবহার করলে program-এর ভুল কমে এবং code বোঝা সহজ হয়।

## 12. Next Topic

পরবর্তী ফাইল:

**`02_Overview_of_Built_in_Data_Types.md`**

সেখানে Python-এর built-in data types-গুলোকে একটি পূর্ণাঙ্গ overview-এর মাধ্যমে তুলনা করা হবে, যাতে কোন data type কখন ব্যবহার করতে হয় তা সহজে বোঝা যায়।