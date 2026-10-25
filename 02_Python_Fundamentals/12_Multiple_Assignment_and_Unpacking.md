# 12. Multiple Assignment and Unpacking in Python

## 1. Introduction

Python-এ **Multiple Assignment** হলো এক statement-এ একাধিক variable-এ value assign করা। আর **Unpacking** হলো কোনো iterable-এর item-গুলোকে আলাদা variable-এ assign করা।

উদাহরণ:

```python
# Multiple assignment
name, age = "Masum", 22

print(name)
print(age)
```

Output:

```text
Masum
22
```

এখানে এক statement-এ দুটি variable-এ value assign হয়েছে।

এবার একটি list থেকে value নেওয়া যাক:

```python
student = ["Masum", 22]

name, age = student

print(name)
print(age)
```

Output:

```text
Masum
22
```

এখানে list-এর item-গুলো `name` ও `age` variable-এ আলাদা হয়েছে। এটিই unpacking।

এই topic-এ আমরা শিখব:

- Multiple assignment
- Tuple unpacking
- List ও string unpacking
- Variable swapping
- Starred unpacking
- Nested unpacking
- `*` দিয়ে iterable unpacking
- `**` দিয়ে dictionary unpacking
- Common errors ও practical applications

## 2. Multiple Assignment

একটি statement-এ একাধিক variable-এ আলাদা value assign করা যায়।

### 2.1 Basic Multiple Assignment

```python
name, age, department = "Masum", 22, "CSE"

print(name)
print(age)
print(department)
```

Output:

```text
Masum
22
CSE
```

এখানে:

- `name` পেয়েছে `"Masum"`
- `age` পেয়েছে `22`
- `department` পেয়েছে `"CSE"`

সাধারণত বাম পাশের target এবং ডান পাশের value-এর সংখ্যা সমান হতে হয়।

### 2.2 Assigning Values of Different Data Types

একই statement-এ ভিন্ন data type-এর value assign করা যায়।

```python
student_name, marks, is_passed = "Masum", 85, True

print(student_name)
print(marks)
print(is_passed)
```

Output:

```text
Masum
85
True
```

Python dynamically typed language হওয়ায় এখানে string, integer ও Boolean value একসঙ্গে assign করতে কোনো সমস্যা নেই।

### 2.3 Multiple Assignment with Expressions

ডান পাশে expression-ও ব্যবহার করা যায়।

```python
a, b, c = 10 + 5, 20 * 2, 30 - 10

print(a)
print(b)
print(c)
```

Output:

```text
15
40
20
```

Python প্রথমে ডান পাশের expression-গুলো evaluate করে, তারপর ফলাফলগুলো বাম পাশের target-এ assign করে।

### 2.4 Assigning Values to Existing Variables

আগে থেকে থাকা variable-এও multiple assignment করা যায়।

```python
a = 100
b = 200

a, b = 10, 20

print(a)
print(b)
```

Output:

```text
10
20
```

নতুন assignment-এর কারণে `a` ও `b`-এর আগের binding পরিবর্তিত হয়েছে।

## 3. Chained Assignment

একই object একাধিক variable name-এর সঙ্গে bind করতে chained assignment ব্যবহার করা হয়।

```python
a = b = c = 50

print(a)
print(b)
print(c)
```

Output:

```text
50
50
50
```

এখানে তিনটি variable name-ই একই integer object `50`-কে refer করে।

### Multiple Assignment vs Chained Assignment

| Multiple Assignment | Chained Assignment |
|---|---|
| `a, b = 10, 20` | `a = b = 10` |
| আলাদা value assign করে | একই object-এর সঙ্গে একাধিক নাম bind করে |
| `a` ও `b` ভিন্ন value পায় | `a` ও `b` একই value/object refer করে |

**Mutable object-এর ক্ষেত্রে সতর্কতা:**

```python
a = b = []

a.append(10)

print(a)
print(b)
```

Output:

```text
[10]
[10]
```

কারণ `a` ও `b` একই list object-কে refer করছে।

আলাদা list চাইলে:

```python
a = []
b = []
```

এভাবে আলাদাভাবে তৈরি করতে হবে।

## 4. Tuple Unpacking

Tuple unpacking হলো tuple-এর item-গুলোকে আলাদা variable-এ assign করা।

```python
student = ("Masum", 22, "CSE")

name, age, department = student

print(name)
print(age)
print(department)
```

Output:

```text
Masum
22
CSE
```

এখানে tuple-এর তিনটি item যথাক্রমে তিনটি variable-এ assign হয়েছে।

### 4.1 Direct Tuple Unpacking

আলাদা tuple variable তৈরি না করেও unpacking করা যায়।

```python
name, age, department = ("Masum", 22, "CSE")

print(name)
print(age)
print(department)
```

এটিও একই ফলাফল দেবে।

### 4.2 Parentheses Are Often Optional

Python-এ unpacking করার সময় parentheses সব ক্ষেত্রে প্রয়োজন হয় না।

```python
name, age = "Masum", 22
```

এখানে ডান পাশের comma-separated values একটি tuple হিসেবে বিবেচিত হয় এবং unpacking-এর মাধ্যমে variable-গুলো value পায়।

## 5. List Unpacking

List থেকেও unpacking করা যায়।

```python
numbers = [10, 20, 30]

a, b, c = numbers

print(a)
print(b)
print(c)
```

Output:

```text
10
20
30
```

এখানে list-এর item-গুলো আলাদা variable-এ assign হয়েছে।

List unpacking-এর ক্ষেত্রে list-এর item-এর সংখ্যা এবং target-এর সংখ্যা সাধারণত সমান হতে হয়। Starred unpacking ব্যবহার করলে অতিরিক্ত item সংগ্রহ করা যায়, যা পরের অংশে দেখব।

## 6. String Unpacking

String একটি iterable। তাই এর character-গুলোও unpack করা যায়।

```python
letters = "CAT"

a, b, c = letters

print(a)
print(b)
print(c)
```

Output:

```text
C
A
T
```

প্রতিটি character একটি variable-এ assign হয়েছে।

তবে character-এর সংখ্যা target-এর সংখ্যার সঙ্গে না মিললে সাধারণ unpacking-এ `ValueError` হবে।

উদাহরণ:

```python
# a, b = "CAT"
```

এখানে তিনটি character-এর জন্য দুটি target দেওয়া হয়েছে।

## 7. Variable Swapping with Unpacking

Python-এর একটি সুবিধা হলো temporary variable ছাড়াই দুটি variable-এর value swap করা যায়।

```python
a = 10
b = 20

a, b = b, a

print(a)
print(b)
```

Output:

```text
20
10
```

### কীভাবে কাজ করে?

প্রথমে:

- `a = 10`
- `b = 20`

তারপর:

```python
a, b = b, a
```

ডান পাশের পুরোনো value-গুলো আগে evaluate করা হয়। তারপর:

- `a` পায় `20`
- `b` পায় `10`

এ কারণে একটি value হারিয়ে যায় না।

### Practical Example: Swapping Student Marks

```python
masum_marks = 85
ritu_marks = 90

masum_marks, ritu_marks = ritu_marks, masum_marks

print("Masum:", masum_marks)
print("Ritu:", ritu_marks)
```

Output:

```text
Masum: 90
Ritu: 85
```

## 8. Starred Unpacking with `*`

সাধারণ unpacking-এ item-এর সংখ্যা target-এর সংখ্যার সঙ্গে মিলতে হয়। কিন্তু সব item আলাদা variable-এ রাখার প্রয়োজন না থাকলে `*` ব্যবহার করা যায়।

Starred target বাকি item-গুলোকে একটি **list** হিসেবে সংগ্রহ করে।

### 8.1 Collecting Middle Values

```python
numbers = [10, 20, 30, 40, 50]

first, *middle, last = numbers

print(first)
print(middle)
print(last)
```

Output:

```text
10
[20, 30, 40]
50
```

এখানে:

- `first` প্রথম item পেয়েছে।
- `middle` মাঝের item-গুলো list হিসেবে পেয়েছে।
- `last` শেষ item পেয়েছে।

### 8.2 Collecting Remaining Values

```python
numbers = [10, 20, 30, 40]

first, *remaining = numbers

print(first)
print(remaining)
```

Output:

```text
10
[20, 30, 40]
```

এখানে `first` প্রথম item পেয়েছে এবং বাকি item-গুলো `remaining` list-এ রাখা হয়েছে।

### 8.3 Collecting the First Values

```python
numbers = [10, 20, 30, 40]

*initial, last = numbers

print(initial)
print(last)
```

Output:

```text
[10, 20, 30]
40
```

এখানে `last` শেষ item পেয়েছে এবং বাকি item-গুলো `initial` list-এ রাখা হয়েছে।

### 8.4 Only One Starred Target

একটি unpacking assignment-এ সাধারণত সর্বোচ্চ একটি starred target থাকতে পারে।

সঠিক:

```python
a, *b, c = [1, 2, 3, 4]
```

ভুল:

```python
# a, *b, *c = [1, 2, 3, 4]
```

এক statement-এ দুটি starred target দিলে `SyntaxError` হবে।

### 8.5 Starred Unpacking with a Short List

```python
numbers = [10, 20]

first, *middle, last = numbers

print(first)
print(middle)
print(last)
```

Output:

```text
10
[]
20
```

এখানে `middle` খালি list পেয়েছে। কারণ `first` ও `last`-এর জন্য একটি করে item ব্যবহৃত হয়েছে।

## 9. Nested Unpacking

কোনো nested data structure-এর ভেতরের item-গুলোকে একাধিক variable-এ assign করাকে nested unpacking বলা হয়।

উদাহরণ:

```python
student = ("Masum", (22, "CSE"))

name, (age, department) = student

print(name)
print(age)
print(department)
```

Output:

```text
Masum
22
CSE
```

এখানে:

- বাইরের tuple-এর প্রথম item `name` পেয়েছে।
- দ্বিতীয় item-এর ভেতরের `22` পেয়েছে `age`।
- `"CSE"` পেয়েছে `department`।

### Nested List Example

```python
data = [10, [20, 30]]

first, (second, third) = data

print(first)
print(second)
print(third)
```

Output:

```text
10
20
30
```

Nested unpacking-এর ক্ষেত্রে target-এর structure ডান পাশের data structure-এর সঙ্গে মিলতে হবে।

## 10. Unpacking in a `for` Loop

Iterable-এর প্রতিটি item যদি একাধিক value-এর group হয়, তাহলে loop-এর মধ্যেই unpacking করা যায়।

```python
students = [
    ("Masum", 85),
    ("Ritu", 90),
    ("Tusher", 80)
]

for name, marks in students:
    print(name, marks)
```

Output:

```text
Masum 85
Ritu 90
Tusher 80
```

এখানে প্রতিটি tuple থেকে `name` ও `marks` আলাদা variable-এ assign হয়েছে।

### Practical Use: Processing Student Records

```python
students = [
    ("Masum", 3.95),
    ("Ritu", 3.90),
    ("Tusher", 3.85)
]

for name, cgpa in students:
    print(f"{name} has CGPA {cgpa}")
```

Output:

```text
Masum has CGPA 3.95
Ritu has CGPA 3.9
Tusher has CGPA 3.85
```

এভাবে data processing-এর code সহজ ও readable হয়।

## 11. Iterable Unpacking with `*`

Assignment-এর বাইরে function call-এর সময়ও `*` ব্যবহার করে iterable-এর item-গুলো আলাদা positional argument হিসেবে পাঠানো যায়।

উদাহরণ:

```python
numbers = [10, 20, 30]

print(*numbers)
```

Output:

```text
10 20 30
```

এখানে `*numbers` list-এর item-গুলো `print()`-এ আলাদা argument হিসেবে পাঠিয়েছে।

এটি নিচের মতো:

```python
print(10, 20, 30)
```

### Using `*` with a Function

```python
def add(a, b, c):
    return a + b + c

numbers = [10, 20, 30]

result = add(*numbers)

print(result)
```

Output:

```text
60
```

এখানে list-এর তিনটি item যথাক্রমে `a`, `b` ও `c` parameter-এ পাঠানো হয়েছে।

**মনে রাখবে:** এই ধরনের unpacking function-এর parameter সম্পর্কে বোঝার পর আরও সহজ হবে।

## 12. Dictionary Unpacking with `**`

Function call-এর সময় `**` দিয়ে dictionary-এর key-value pair-গুলোকে keyword argument হিসেবে পাঠানো যায়।

উদাহরণ:

```python
def introduce(name, age):
    print(f"My name is {name} and I am {age} years old.")

student = {
    "name": "Masum",
    "age": 22
}

introduce(**student)
```

Output:

```text
My name is Masum and I am 22 years old.
```

এখানে:

- `"name"` key-এর value `name` parameter-এ গেছে।
- `"age"` key-এর value `age` parameter-এ গেছে।

Dictionary-এর key-গুলো function-এর parameter name-এর সঙ্গে মিলতে হবে এবং প্রয়োজনীয় parameter-এর জন্য উপযুক্ত value দিতে হবে।

### Combining Dictionaries with `**`

Dictionary display-এর মধ্যেও `**` ব্যবহার করা যায়।

```python
first = {"name": "Masum", "age": 22}
second = {"department": "CSE"}

student = {**first, **second}

print(student)
```

Output:

```text
{'name': 'Masum', 'age': 22, 'department': 'CSE'}
```

এখানে দুটি dictionary-এর entry একত্র করা হয়েছে।

যদি একই key একাধিক dictionary-তে থাকে, তাহলে পরের dictionary-এর value আগের value-কে override করবে।

```python
first = {"name": "Masum", "age": 22}
second = {"age": 23}

student = {**first, **second}

print(student)
```

Output:

```text
{'name': 'Masum', 'age': 23}
```

## 13. Unpacking vs Indexing

একটি list বা tuple থেকে নির্দিষ্ট item নেওয়ার দুটি সাধারণ উপায় হলো indexing এবং unpacking।

### Using Indexing

```python
student = ("Masum", 22, "CSE")

name = student[0]
age = student[1]
department = student[2]
```

### Using Unpacking

```python
student = ("Masum", 22, "CSE")

name, age, department = student
```

দুটিই একই data আলাদা variable-এ রাখে।

| Indexing | Unpacking |
|---|---|
| প্রতিটি item-এর index লিখতে হয় | এক statement-এ একাধিক item assign করা যায় |
| নির্দিষ্ট item নেওয়ার জন্য সুবিধাজনক | সব বা একাধিক item আলাদা করতে সুবিধাজনক |
| `name = student[0]` | `name, age, dept = student` |

যখন data structure-এর item-গুলোর সংখ্যা ও ক্রম জানা থাকে, তখন unpacking অনেক বেশি পরিষ্কার হতে পারে।

## 14. Common Errors and Solutions

### Error 1: Too Many Values to Unpack

ভুল:

```python
# a, b = [10, 20, 30]
```

কারণ: দুটি target-এর জন্য তিনটি item রয়েছে।

সমাধান:

```python
a, b, *remaining = [10, 20, 30]

print(a, b, remaining)
```

Output:

```text
10 20 [30]
```

### Error 2: Not Enough Values to Unpack

ভুল:

```python
# a, b, c = [10, 20]
```

কারণ: তিনটি target-এর জন্য দুটি item রয়েছে।

সমাধান:

```python
a, b = [10, 20]
```

অথবা প্রয়োজন অনুযায়ী starred target ব্যবহার করা যায়।

### Error 3: Incorrect Nested Structure

ভুল:

```python
# a, (b, c) = [10, 20, 30]
```

এখানে দ্বিতীয় item-টিকে দুইটি value-তে unpack করার মতো nested structure নেই।

সঠিক:

```python
a, (b, c) = [10, [20, 30]]

print(a, b, c)
```

Output:

```text
10 20 30
```

### Error 4: Wrong Number of Function Arguments

```python
def add(a, b):
    return a + b

numbers = [10, 20, 30]

# add(*numbers)
```

এখানে তিনটি argument পাঠানো হচ্ছে, কিন্তু function দুটি parameter গ্রহণ করে। তাই `TypeError` হবে।

সমাধান:

```python
numbers = [10, 20]

print(add(*numbers))
```

Output:

```text
30
```

## 15. Best Practices

1. **Meaningful variable names ব্যবহার করো।** `name, age, department` ব্যবহার করলে code সহজে বোঝা যায়।
2. **Unpacking-এর structure মিলিয়ে নাও।** ডান পাশের data-এর structure বাম পাশের target-এর সঙ্গে মিলতে হবে।
3. **Starred unpacking ব্যবহার করো যখন item-এর সংখ্যা পরিবর্তিত হতে পারে।** যেমন `first, *remaining = values`।
4. **Nested unpacking বেশি জটিল করো না।** অতিরিক্ত nested structure হলে আলাদা statement ব্যবহার করা সহজ হতে পারে।
5. **Chained assignment-এ mutable object-এর ব্যাপারে সতর্ক থাকো।** `a = b = []` দুটি আলাদা list তৈরি করে না।
6. **Function call-এ `*` ও `**` ব্যবহারের আগে parameter-এর structure বুঝে নাও।**
7. **শুধু code ছোট করার জন্য unpacking ব্যবহার করো না।** Readability সব সময় গুরুত্বপূর্ণ।

## 16. Practice Exercises

### Exercise 1: Multiple Assignment

এক statement-এ নিচের variable-গুলোতে value assign করো:

- `name = "Masum"`
- `age = 22`
- `department = "CSE"`

### Exercise 2: Tuple Unpacking

```python
student = ("Masum", 22, "CSE")
```

Tuple-এর item-গুলোকে `name`, `age` ও `department` variable-এ unpack করো।

### Exercise 3: Variable Swapping

```python
a = 100
b = 200
```

Temporary variable ব্যবহার না করে `a` ও `b`-এর value swap করো।

### Exercise 4: Starred Unpacking

```python
numbers = [10, 20, 30, 40, 50, 60]
```

Unpacking করে প্রথম item `first`, শেষ item `last` এবং মাঝের item-গুলো `middle` variable-এ রাখো।

### Exercise 5: Nested Unpacking

```python
data = ("Python", (3, 14))
```

Unpacking করে `"Python"`, `3` ও `14` আলাদা variable-এ রাখো।

### Exercise 6: Loop Unpacking

```python
students = [
    ("Masum", 85),
    ("Ritu", 90),
    ("Tusher", 80)
]
```

`for` loop এবং unpacking ব্যবহার করে প্রতিটি student-এর নাম ও marks print করো।

### Exercise 7: Function Argument Unpacking

```python
def multiply(a, b, c):
    return a * b * c

numbers = [2, 3, 4]
```

`*` ব্যবহার করে list-এর item-গুলো function-এ পাঠাও এবং result print করো।

### Exercise 8: Dictionary Unpacking

```python
def show_student(name, department):
    print(name, department)

student = {
    "name": "Masum",
    "department": "CSE"
}
```

`**` ব্যবহার করে dictionary-এর value-গুলো function-এ পাঠাও।

## 17. Quick Revision

| Concept | Example | Purpose |
|---|---|---|
| Multiple assignment | `a, b = 10, 20` | এক statement-এ একাধিক value assign করা |
| Chained assignment | `a = b = 10` | একাধিক নামকে একই object-এর সঙ্গে bind করা |
| Tuple unpacking | `a, b = (10, 20)` | Tuple-এর item আলাদা করা |
| List unpacking | `a, b = [10, 20]` | List-এর item আলাদা করা |
| String unpacking | `a, b = "OK"` | Character আলাদা করা |
| Starred unpacking | `a, *b = [1, 2, 3]` | বাকি item-গুলো list হিসেবে সংগ্রহ করা |
| Nested unpacking | `a, (b, c) = (1, (2, 3))` | Nested data structure unpack করা |
| Iterable argument unpacking | `func(*values)` | Item-গুলো positional argument হিসেবে পাঠানো |
| Dictionary argument unpacking | `func(**data)` | Key-value pair keyword argument হিসেবে পাঠানো |

## 18. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Multiple assignment দিয়ে এক statement-এ একাধিক variable-এ value assign করা যায়।
- Chained assignment একাধিক variable name-কে একই object-এর সঙ্গে bind করে।
- Tuple, list ও string থেকে unpacking করা যায়।
- `a, b = b, a` দিয়ে সহজে variable swap করা যায়।
- Starred unpacking-এ `*` বাকি item-গুলোকে list হিসেবে সংগ্রহ করে।
- Nested unpacking nested data structure-এর item-গুলো আলাদা করতে সাহায্য করে।
- `for` loop-এ unpacking ব্যবহার করে grouped data সহজে process করা যায়।
- Function call-এ `*` দিয়ে positional argument এবং `**` দিয়ে keyword argument unpack করা যায়।
- ভুল সংখ্যক item বা ভুল structure থাকলে unpacking error হতে পারে।

## 19. Next Topic

পরবর্তী ফাইল: [`13_Literals_and_Constants.md`](13_Literals_and_Constants.md)

সেখানে Python literals, numeric ও string literals, Boolean ও `None` literal, constants এবং Python-এ constant naming conventions নিয়ে বিস্তারিত আলোচনা করা হবে।