# 01. Introduction to Built-in Data Structures in Python

## 1. What Are Built-in Data Structures?

Python-এ **Built-in Data Structures** হলো এমন কিছু বিশেষ data type, যেগুলোর মাধ্যমে আমরা একসাথে একাধিক value সংরক্ষণ এবং পরিচালনা করতে পারি।

সাধারণ variable-এ আমরা সাধারণত একটি value রাখি। কিন্তু Built-in Data Structures ব্যবহার করে একটি variable-এর মধ্যে অনেকগুলো value রাখা যায়।

**Example:**

```python
# Using separate variables

student1 = "Masum"
student2 = "Rahim"
student3 = "Karim"

print(student1)
print(student2)
print(student3)
```

**Output:**

```text
Masum
Rahim
Karim
```

এখানে তিনজন শিক্ষার্থীর নাম রাখার জন্য আমাদের তিনটি আলাদা variable ব্যবহার করতে হয়েছে।

কিন্তু List ব্যবহার করলে একই কাজ আরও সহজে করা যায়।

```python
students = ["Masum", "Rahim", "Karim"]

print(students)
```

**Output:**

```text
['Masum', 'Rahim', 'Karim']
```

এখানে একটি variable-এর মধ্যেই তিনজন শিক্ষার্থীর নাম রাখা হয়েছে।

এটাই Built-in Data Structures ব্যবহারের একটি গুরুত্বপূর্ণ সুবিধা।

---

## 2. Why Do We Need Built-in Data Structures?

একটি program-এ অনেক সময় অনেকগুলো data নিয়ে কাজ করতে হয়।

যেমন:

- অনেকগুলো শিক্ষার্থীর নাম সংরক্ষণ করা।
- একজন শিক্ষার্থীর বিভিন্ন তথ্য রাখা।
- একটি shopping cart-এ অনেকগুলো product রাখা।
- কোনো data থেকে duplicate value বাদ দেওয়া।
- একজন শিক্ষার্থীর ID এবং name একসাথে সংরক্ষণ করা।

প্রতিটি value-এর জন্য আলাদা variable তৈরি করলে program পরিচালনা করা কঠিন হয়ে যায়।

Built-in Data Structures ব্যবহার করলে data সহজে organize, access এবং manage করা যায়।

**Example:**

```python
# Without a List

subject1 = "Python"
subject2 = "Java"
subject3 = "C++"

# With a List

subjects = ["Python", "Java", "C++"]

print(subjects)
```

**Output:**

```text
['Python', 'Java', 'C++']
```

একটি List ব্যবহার করে আমরা সহজেই একাধিক subject সংরক্ষণ করতে পারছি।

---

## 3. Types of Built-in Data Structures in Python

Python-এ প্রধান চারটি Built-in Data Structures রয়েছে।

1. List
2. Tuple
3. Set
4. Dictionary

প্রতিটি Data Structure-এর নিজস্ব বৈশিষ্ট্য এবং ব্যবহার রয়েছে।

### 3.1 List

**List** হলো এমন একটি Data Structure, যেখানে একাধিক value একটি variable-এর মধ্যে রাখা যায়।

- List তৈরি করতে Square Brackets `[]` ব্যবহার করা হয়।
- List Ordered, অর্থাৎ value-গুলোর অবস্থান বা position থাকে।
- List-এর value পরিবর্তন করা যায় (Mutable)।
- Duplicate value রাখা যায়।

**Example:**

```python
fruits = ["Apple", "Banana", "Mango"]

print(fruits)
```

**Output:**

```text
['Apple', 'Banana', 'Mango']
```

### 3.2 Tuple

**Tuple** হলো এমন একটি Data Structure, যেখানে একাধিক value একসাথে রাখা যায়।

- Tuple তৈরি করতে Parentheses `()` ব্যবহার করা হয়।
- Tuple Ordered।
- Tuple-এর value পরিবর্তন করা যায় না (Immutable)।
- Duplicate value রাখা যায়।

**Example:**

```python
colors = ("Red", "Green", "Blue")

print(colors)
```

**Output:**

```text
('Red', 'Green', 'Blue')
```

### 3.3 Set

**Set** হলো এমন একটি Data Structure, যেখানে unique value সংরক্ষণ করা হয়।

- Set তৈরি করতে Curly Braces `{}` ব্যবহার করা হয়।
- Set Unordered, তাই এর value-গুলোর নির্দিষ্ট positional order নেই।
- Duplicate value রাখা যায় না।
- Set Mutable, অর্থাৎ এর value যোগ বা বাদ দেওয়া যায়।

**Example:**

```python
numbers = {10, 20, 30, 20, 10}

print(numbers)
```

**Output (order may vary):**

```text
{10, 20, 30}
```

এখানে `10` এবং `20` একাধিকবার দেওয়া হলেও Set প্রতিটি unique value একবারই রাখে।

### 3.4 Dictionary

**Dictionary** হলো এমন একটি Data Structure, যেখানে data Key-Value Pair আকারে সংরক্ষণ করা হয়।

- Dictionary তৈরি করতে Curly Braces `{}` ব্যবহার করা হয়।
- প্রতিটি item একটি Key এবং একটি Value নিয়ে গঠিত।
- Key unique হতে হয়।
- Dictionary Mutable, অর্থাৎ এর data পরিবর্তন করা যায়।
- Python 3.7 এবং পরবর্তী version-এ insertion order বজায় থাকে।

**Example:**

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}

print(student)
```

**Output:**

```text
{'name': 'Masum', 'age': 22, 'department': 'CSE'}
```

এখানে:

- `"name"` হলো Key এবং `"Masum"` হলো Value।
- `"age"` হলো Key এবং `22` হলো Value।
- `"department"` হলো Key এবং `"CSE"` হলো Value।

---

## 4. Quick Comparison of Four Data Structures

| Feature | List | Tuple | Set | Dictionary |
|---|---|---|---|---|
| Symbol | `[]` | `()` | `{}` | `{key: value}` |
| Ordered | Yes | Yes | No | Yes |
| Mutable | Yes | No | Yes | Yes |
| Duplicate Values | Yes | Yes | No | Values can repeat |
| Access | Index | Index | No Index | Key |

**Note:** Dictionary-এর Key unique হতে হয়। তবে Dictionary-এর Value duplicate হতে পারে।

---

## 5. Simple Real-Life Examples

আমাদের দৈনন্দিন জীবনের বিভিন্ন কাজের সাথে এই Data Structures-এর ব্যবহার মিলিয়ে দেখা যায়।

| Data Structure | Real-Life Example |
|---|---|
| List | একটি shopping list |
| Tuple | একটি স্থির coordinate `(10, 20)` |
| Set | Unique student ID-এর collection |
| Dictionary | একজন শিক্ষার্থীর information |

এগুলো শুধু বোঝার জন্য উদাহরণ। বাস্তবে কোন Data Structure ব্যবহার করব, তা নির্ভর করবে আমাদের প্রয়োজনের ওপর।

---

## 6. Important Points to Remember

1. Python-এর প্রধান চারটি Built-in Data Structure হলো List, Tuple, Set এবং Dictionary।
2. List এবং Tuple Ordered।
3. List Mutable, কিন্তু Tuple Immutable।
4. Set-এ Duplicate Value রাখা যায় না।
5. Set-এর value-গুলো positional index দিয়ে access করা যায় না।
6. Dictionary data Key-Value Pair আকারে রাখে।
7. Dictionary-এর Key unique হতে হয়।
8. List, Tuple, Set এবং Dictionary-এর নিজস্ব বৈশিষ্ট্য রয়েছে।

---

## 7. Common Beginner Mistakes

### Mistake 1: List এবং Tuple-এর Brackets গুলিয়ে ফেলা

```python
# List
numbers = [10, 20, 30]

# Tuple
numbers = (10, 20, 30)
```

List-এর জন্য `[]` এবং Tuple-এর জন্য `()` ব্যবহার করতে হয়।

### Mistake 2: Set-এ Duplicate Value থাকবে মনে করা

```python
numbers = {10, 20, 10, 30}

print(numbers)
```

**Output (order may vary):**

```text
{10, 20, 30}
```

Set duplicate value রাখে না।

### Mistake 3: Dictionary-তে Key এবং Value গুলিয়ে ফেলা

```python
student = {
    "name": "Masum",
    "age": 22
}
```

এখানে `"name"` এবং `"age"` হলো Key। অন্যদিকে `"Masum"` এবং `22` হলো Value।

---

## 8. Practice Exercises

### Exercise 1

Python-এর প্রধান চারটি Built-in Data Structures-এর নাম লেখো।

**Solution:**

```text
1. List
2. Tuple
3. Set
4. Dictionary
```

### Exercise 2

নিচের কোন Data Structure-এ Duplicate Value রাখা যায় না?

**Solution:**

```text
Set
```

### Exercise 3

নিচের কোন Data Structure Mutable নয়?

**Solution:**

```text
Tuple
```

### Exercise 4

নিচের code-এর output কী হবে?

```python
numbers = [10, 20, 30]

print(numbers)
```

**Solution:**

```text
[10, 20, 30]
```

### Exercise 5

নিচের code-এ Key এবং Value চিহ্নিত করো।

```python
student = {
    "name": "Masum",
    "age": 22
}
```

**Solution:**

```text
Keys:
"name", "age"

Values:
"Masum", 22
```

---

## 9. Chapter Summary

এই topic-এ আমরা Python-এর Built-in Data Structures সম্পর্কে প্রাথমিক ধারণা পেয়েছি।

- Built-in Data Structures দিয়ে একটি variable-এর মধ্যে একাধিক value রাখা যায়।
- Python-এর প্রধান চারটি Data Structure হলো List, Tuple, Set এবং Dictionary।
- List এবং Tuple index ব্যবহার করে value access করতে দেয়।
- Set unique value সংরক্ষণ করে।
- Dictionary Key-Value Pair আকারে data সংরক্ষণ করে।

পরবর্তী topic-গুলোতে আমরা প্রতিটি Data Structure আলাদাভাবে বিস্তারিত শিখব।

---

## 10. Self-Assessment Checklist

নিজে যাচাই করো:

- [ ] Built-in Data Structures কী তা বুঝতে পেরেছি।
- [ ] কেন Data Structures প্রয়োজন তা বুঝতে পেরেছি।
- [ ] List, Tuple, Set এবং Dictionary-এর নাম জানি।
- [ ] চারটি Data Structure-এর basic syntax বুঝতে পেরেছি।
- [ ] Mutable এবং Immutable-এর basic difference বুঝতে পেরেছি।
- [ ] Key-Value Pair কী তা বুঝতে পেরেছি।
- [ ] Basic code দেখে output বলতে পারি।

---

## 11. Next Topic

**02. Why Data Structures Are Important in Python**

পরবর্তী topic-এ আমরা জানব কেন programming-এ Data Structures ব্যবহার করা গুরুত্বপূর্ণ এবং কীভাবে এগুলো data পরিচালনা সহজ করে।