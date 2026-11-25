# 04. List, Tuple, Set and Dictionary Comparison

## 1. Introduction

Python-এর চারটি প্রধান Built-in Data Structures হলো:

1. List
2. Tuple
3. Set
4. Dictionary

এই চারটি Data Structure-এর কাজ কিছুটা একই রকম হলেও এদের বৈশিষ্ট্য আলাদা।

সবগুলোতেই একাধিক data সংরক্ষণ করা যায়। কিন্তু data কীভাবে রাখা হবে, পরিবর্তন করা যাবে কি না এবং কীভাবে access করা যাবে—এসব বিষয়ে পার্থক্য রয়েছে।

এই topic-এ আমরা চারটি Data Structure-এর মধ্যে পার্থক্যগুলো বিস্তারিতভাবে শিখব।

---

## 2. Basic Syntax Comparison

প্রথমে চারটি Data Structure-এর basic syntax দেখে নিই।

### 2.1 List

List তৈরি করতে Square Brackets `[]` ব্যবহার করা হয়।

```python
students = ["Masum", "Rahim", "Karim"]

print(students)
```

**Output:**

```text
['Masum', 'Rahim', 'Karim']
```

### 2.2 Tuple

Tuple তৈরি করতে Parentheses `()` ব্যবহার করা হয়।

```python
students = ("Masum", "Rahim", "Karim")

print(students)
```

**Output:**

```text
('Masum', 'Rahim', 'Karim')
```

### 2.3 Set

Set তৈরি করতে Curly Braces `{}` ব্যবহার করা হয়।

```python
students = {"Masum", "Rahim", "Karim"}

print(students)
```

**Output (order may vary):**

```text
{'Masum', 'Rahim', 'Karim'}
```

### 2.4 Dictionary

Dictionary তৈরি করতে Curly Braces `{}` ব্যবহার করা হয়। এখানে প্রতিটি item Key-Value Pair আকারে থাকে।

```python
student = {
    "name": "Masum",
    "age": 22
}

print(student)
```

**Output:**

```text
{'name': 'Masum', 'age': 22}
```

---

## 3. Main Differences Between Four Data Structures

নিচের table-এ চারটি Data Structure-এর গুরুত্বপূর্ণ পার্থক্যগুলো দেখানো হয়েছে।

| Feature | List | Tuple | Set | Dictionary |
|---|---|---|---|---|
| Syntax | `[]` | `()` | `{}` | `{key: value}` |
| Ordered | Yes | Yes | No | Yes |
| Mutable | Yes | No | Yes | Yes |
| Duplicate Items | Yes | Yes | No | Keys: No |
| Indexing | Yes | Yes | No | Key-based access |
| Data Storage | Values | Values | Unique values | Key-Value Pairs |

**Important Notes:**

- List এবং Tuple-এ duplicate value রাখা যায়।
- Set-এ duplicate value রাখা যায় না।
- Dictionary-এর Key unique হতে হয়।
- Dictionary-এর Value duplicate হতে পারে।
- Python 3.7+ থেকে Dictionary insertion order বজায় রাখে।

---

## 4. Ordered vs Unordered

Ordered এবং Unordered হলো Data Structure-এর গুরুত্বপূর্ণ দুটি বৈশিষ্ট্য।

### 4.1 Ordered

Ordered Data Structure-এ item-গুলোর নির্দিষ্ট position থাকে।

List এবং Tuple Ordered।

**Example:**

```python
numbers = [10, 20, 30]

print(numbers[0])
print(numbers[1])
```

**Output:**

```text
10
20
```

এখানে প্রতিটি item-এর নির্দিষ্ট index রয়েছে।

### 4.2 Unordered

Unordered Data Structure-এ item-গুলোর নির্দিষ্ট positional order-এর ওপর নির্ভর করা যায় না।

Set হলো Unordered Data Structure।

**Example:**

```python
numbers = {10, 20, 30}

print(numbers)
```

**Output (order may vary):**

```text
{10, 20, 30}
```

Set-এর item index দিয়ে access করা যায় না।

**Remember:**

- List = Ordered
- Tuple = Ordered
- Set = Unordered
- Dictionary = Insertion ordered (Python 3.7+)

---

## 5. Mutable vs Immutable

Mutable এবং Immutable-এর পার্থক্য বোঝা খুবই গুরুত্বপূর্ণ।

### 5.1 Mutable

Mutable মানে হলো কোনো Data Structure তৈরি করার পর তার item পরিবর্তন করা যায়।

List, Set এবং Dictionary Mutable।

**Example:**

```python
numbers = [10, 20, 30]

numbers[0] = 50

print(numbers)
```

**Output:**

```text
[50, 20, 30]
```

এখানে List-এর প্রথম item পরিবর্তন করা হয়েছে।

### 5.2 Immutable

Immutable মানে হলো কোনো object তৈরি হওয়ার পর তার মূল content পরিবর্তন করা যায় না।

Tuple Immutable।

**Example:**

```python
numbers = (10, 20, 30)

numbers[0] = 50
```

**Output:**

```text
TypeError
```

এখানে Tuple-এর item পরিবর্তন করার চেষ্টা করায় error হয়েছে।

**Remember:**

- List = Mutable
- Tuple = Immutable
- Set = Mutable
- Dictionary = Mutable

---

## 6. Duplicate Values

Duplicate value মানে একই value একাধিকবার থাকা।

### 6.1 List Allows Duplicates

```python
numbers = [10, 20, 10, 30, 20]

print(numbers)
```

**Output:**

```text
[10, 20, 10, 30, 20]
```

List duplicate value রাখে।

### 6.2 Tuple Allows Duplicates

```python
numbers = (10, 20, 10, 30, 20)

print(numbers)
```

**Output:**

```text
(10, 20, 10, 30, 20)
```

Tuple-ও duplicate value রাখে।

### 6.3 Set Does Not Allow Duplicates

```python
numbers = {10, 20, 10, 30, 20}

print(numbers)
```

**Output (order may vary):**

```text
{10, 20, 30}
```

Set duplicate value বাদ দেয়।

### 6.4 Dictionary Keys Must Be Unique

```python
student = {
    "name": "Masum",
    "age": 22,
    "name": "Rahim"
}

print(student)
```

**Output:**

```text
{'name': 'Rahim', 'age': 22}
```

Dictionary-তে একই Key একাধিকবার দিলে শেষের Value আগের Value-কে replace করে।

তবে Dictionary-এর Value duplicate হতে পারে।

```python
students = {
    "student1": "Masum",
    "student2": "Masum"
}

print(students)
```

**Output:**

```text
{'student1': 'Masum', 'student2': 'Masum'}
```

---

## 7. Indexing and Accessing

চারটি Data Structure-এ data access করার পদ্ধতি এক নয়।

### List: Indexing

```python
fruits = ["Apple", "Banana", "Mango"]

print(fruits[1])
```

**Output:**

```text
Banana
```

### Tuple: Indexing

```python
colors = ("Red", "Green", "Blue")

print(colors[2])
```

**Output:**

```text
Blue
```

### Set: No Indexing

```python
numbers = {10, 20, 30}

print(numbers[0])
```

**Output:**

```text
TypeError
```

Set indexing support করে না।

### Dictionary: Key-Based Access

```python
student = {
    "name": "Masum",
    "age": 22
}

print(student["name"])
```

**Output:**

```text
Masum
```

Dictionary-তে Key ব্যবহার করে Value access করা হয়।

---

## 8. When Should We Use Each Data Structure?

কোন Data Structure ব্যবহার করব, তা আমাদের কাজের ওপর নির্ভর করে।

| Situation | Suitable Data Structure | Reason |
|---|---|---|
| অনেকগুলো student name রাখতে হবে | List | Multiple values রাখা যায় |
| Fixed data রাখতে হবে | Tuple | Item পরিবর্তন করা যায় না |
| Duplicate বাদ দিতে হবে | Set | Unique values রাখে |
| Student information রাখতে হবে | Dictionary | Key-Value Pair ব্যবহার করে |
| Shopping cart তৈরি করতে হবে | List | Product যোগ বা বাদ দেওয়া যায় |
| Unique ID রাখতে হবে | Set | Duplicate ID বাদ দেওয়া যায় |

### Example 1: Student Names Using List

```python
students = ["Masum", "Rahim", "Karim"]

print(students)
```

**Output:**

```text
['Masum', 'Rahim', 'Karim']
```

### Example 2: Fixed Coordinate Using Tuple

```python
coordinate = (10, 20)

print(coordinate)
```

**Output:**

```text
(10, 20)
```

### Example 3: Unique Numbers Using Set

```python
numbers = {10, 20, 10, 30}

print(numbers)
```

**Output (order may vary):**

```text
{10, 20, 30}
```

### Example 4: Student Information Using Dictionary

```python
student = {
    "name": "Masum",
    "department": "CSE",
    "semester": 9
}

print(student["name"])
```

**Output:**

```text
Masum
```

---

## 9. Mixed Data Structures

Python-এ প্রয়োজন অনুযায়ী একটি Data Structure-এর মধ্যে অন্য Data Structure রাখা যায়।

**Example: List Inside Dictionary**

```python
student = {
    "name": "Masum",
    "subjects": ["Python", "Java", "C++"]
}

print(student["subjects"])
```

**Output:**

```text
['Python', 'Java', 'C++']
```

এখানে Dictionary-এর `"subjects"` Key-এর Value হিসেবে একটি List রাখা হয়েছে।

এভাবে বিভিন্ন Data Structure একসাথে ব্যবহার করে complex data manage করা যায়।

---

## 10. Important Points to Remember

1. List তৈরি করতে `[]` ব্যবহার করা হয়।
2. Tuple তৈরি করতে `()` ব্যবহার করা হয়।
3. Set তৈরি করতে `{}` ব্যবহার করা হয়।
4. Dictionary-তে `{key: value}` format ব্যবহার করা হয়।
5. List, Tuple এবং Dictionary Ordered।
6. Set Unordered।
7. List, Set এবং Dictionary Mutable।
8. Tuple Immutable।
9. List এবং Tuple duplicate value রাখতে পারে।
10. Set duplicate value রাখে না।
11. Dictionary-এর Key unique হতে হয়।
12. Dictionary-এর Value duplicate হতে পারে।
13. List এবং Tuple index দিয়ে access করা যায়।
14. Set indexing support করে না।
15. Dictionary Key ব্যবহার করে Value access করে।

---

## 11. Common Beginner Mistakes

### Mistake 1: Empty Set এবং Empty Dictionary গুলিয়ে ফেলা

```python
data = {}

print(type(data))
```

**Output:**

```text
<class 'dict'>
```

`{}` দিয়ে Empty Dictionary তৈরি হয়।

Empty Set তৈরি করতে হবে:

```python
data = set()

print(type(data))
```

**Output:**

```text
<class 'set'>
```

### Mistake 2: Tuple-এর Single Item তৈরি করতে ভুল করা

```python
number = (10)

print(type(number))
```

**Output:**

```text
<class 'int'>
```

এটি Tuple নয়, কারণ এখানে শুধু Parentheses ব্যবহার করা হয়েছে।

Single-item Tuple তৈরি করতে comma দিতে হয়।

```python
number = (10,)

print(type(number))
```

**Output:**

```text
<class 'tuple'>
```

### Mistake 3: Set-এ Index ব্যবহার করা

```python
numbers = {10, 20, 30}

print(numbers[0])
```

**Output:**

```text
TypeError
```

Set indexing support করে না।

### Mistake 4: Dictionary-এর Key Duplicate রাখা যায় মনে করা

```python
student = {
    "name": "Masum",
    "name": "Rahim"
}

print(student["name"])
```

**Output:**

```text
Rahim
```

একই Key একাধিকবার থাকলে শেষের Value কার্যকর হয়।

---

## 12. Practice Exercises

### Exercise 1

Which Data Structure is Mutable?

**Solution:**

```text
List, Set and Dictionary
```

### Exercise 2

Which Data Structure is Immutable?

**Solution:**

```text
Tuple
```

### Exercise 3

Which Data Structure does not allow duplicate values?

**Solution:**

```text
Set
```

### Exercise 4

নিচের code-এর output কী হবে?

```python
numbers = [10, 20, 10, 30]

print(len(numbers))
```

**Solution:**

```text
4
```

কারণ List duplicate value-সহ সব item গণনা করে।

### Exercise 5

নিচের code-এর output কী হবে?

```python
numbers = {10, 20, 10, 30}

print(len(numbers))
```

**Solution:**

```text
3
```

কারণ Set duplicate value রাখে না।

### Exercise 6

নিচের code-এর output কী হবে?

```python
student = {
    "name": "Masum",
    "age": 22
}

student["age"] = 23

print(student["age"])
```

**Solution:**

```text
23
```

### Exercise 7

Single-item Tuple তৈরি করার সঠিক syntax কোনটি?

**Solution:**

```python
number = (10,)
```

### Exercise 8

কোন Data Structure Key-Value Pair আকারে data রাখে?

**Solution:**

```text
Dictionary
```

### Exercise 9

নিচের code-এর output কী হবে?

```python
numbers = (10, 20, 30)

print(numbers[1])
```

**Solution:**

```text
20
```

### Exercise 10

একটি collection থেকে duplicate student ID বাদ দিতে কোন Data Structure ব্যবহার করবে?

**Solution:**

```text
Set
```

---

## 13. Chapter Summary

এই topic-এ আমরা List, Tuple, Set এবং Dictionary-এর মধ্যে পার্থক্য শিখেছি।

| Data Structure | Main Feature |
|---|---|
| List | Ordered and Mutable |
| Tuple | Ordered and Immutable |
| Set | Unordered and Unique Items |
| Dictionary | Key-Value Pairs |

মনে রাখবে, চারটি Data Structure-এর কাজ আলাদা। তাই program-এর প্রয়োজন অনুযায়ী সঠিক Data Structure নির্বাচন করতে হবে।

---

## 14. Self-Assessment Checklist

- [ ] List, Tuple, Set এবং Dictionary-এর syntax জানি।
- [ ] Ordered এবং Unordered বুঝতে পেরেছি।
- [ ] Mutable এবং Immutable বুঝতে পেরেছি।
- [ ] চারটি Data Structure-এর duplicate value rules জানি।
- [ ] Indexing এবং Key-based access-এর পার্থক্য বুঝেছি।
- [ ] Empty Set এবং Empty Dictionary তৈরি করতে পারি।
- [ ] Single-item Tuple তৈরি করতে পারি।
- [ ] প্রয়োজন অনুযায়ী সঠিক Data Structure নির্বাচন করতে পারি।
- [ ] Code দেখে output বলতে পারি।

---

## 15. Next Topic

**05. Introduction to Lists in Python**

পরবর্তী topic থেকে আমরা List নিয়ে বিস্তারিত শেখা শুরু করব। List কী, কীভাবে তৈরি করতে হয় এবং কীভাবে এর মাধ্যমে একাধিক value সংরক্ষণ করতে হয়—এসব বিষয় ধাপে ধাপে শিখব।