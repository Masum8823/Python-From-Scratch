# 07. Accessing List Elements Using Indexing in Python

## 1. Introduction

Python List-এর মধ্যে থাকা প্রতিটি element-কে তার **Index Number** ব্যবহার করে access করা যায়।

Index হলো List-এর প্রতিটি element-এর অবস্থান বোঝানোর একটি number।

Python-এ List Indexing শুরু হয় `0` থেকে, `1` থেকে নয়।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print(fruits[0])
print(fruits[1])
print(fruits[2])
print(fruits[3])
```

**Output:**

```text
Apple
Banana
Mango
Orange
```

এখানে:

- `fruits[0]` → Apple
- `fruits[1]` → Banana
- `fruits[2]` → Mango
- `fruits[3]` → Orange

## 2. Understanding Positive Indexing

Positive Indexing হলো List-এর শুরু থেকে element access করা।

Python-এ প্রথম element-এর index `0`, দ্বিতীয় element-এর index `1`, এভাবে বাড়তে থাকে।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[0])
print(numbers[2])
print(numbers[4])
```

**Output:**

```text
10
30
50
```

**Index Mapping:**

| Element | 10 | 20 | 30 | 40 | 50 |
|---|---|---|---|---|---|
| Index | 0 | 1 | 2 | 3 | 4 |

**মনে রাখবে:**

- প্রথম element-এর index হলো `0`।
- দ্বিতীয় element-এর index হলো `1`।
- শেষ element-এর index হলো `len(list) - 1`।

## 3. Understanding Negative Indexing

Python-এ Negative Indexing ব্যবহার করে List-এর শেষ দিক থেকে element access করা যায়।

Negative Indexing শুরু হয় `-1` থেকে।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print(fruits[-1])
print(fruits[-2])
print(fruits[-3])
print(fruits[-4])
```

**Output:**

```text
Orange
Mango
Banana
Apple
```

**Negative Index Mapping:**

| Element | Apple | Banana | Mango | Orange |
|---|---|---|---|---|
| Positive Index | 0 | 1 | 2 | 3 |
| Negative Index | -4 | -3 | -2 | -1 |

**মনে রাখবে:**

- `-1` → শেষ element
- `-2` → শেষ থেকে দ্বিতীয় element
- `-3` → শেষ থেকে তৃতীয় element

## 4. Accessing the First Element

List-এর প্রথম element access করতে index `0` ব্যবহার করতে হয়।

উদাহরণ:

```python
students = ["Masum", "Rahim", "Karim"]

first_student = students[0]

print(first_student)
```

**Output:**

```text
Masum
```

এখানে `students[0]` ব্যবহার করে প্রথম student-এর নাম পাওয়া গেছে।

## 5. Accessing the Last Element

List-এর শেষ element access করার জন্য `-1` ব্যবহার করা যায়।

উদাহরণ:

```python
colors = ["Red", "Green", "Blue", "Yellow"]

last_color = colors[-1]

print(last_color)
```

**Output:**

```text
Yellow
```

এখানে `colors[-1]` List-এর শেষ element return করেছে।

আরেকটি উপায় হলো `len()` ব্যবহার করা।

```python
colors = ["Red", "Green", "Blue", "Yellow"]

last_color = colors[len(colors) - 1]

print(last_color)
```

**Output:**

```text
Yellow
```

এখানে `len(colors)` List-এর মোট element সংখ্যা return করে।

যেহেতু List-এ 4টি element আছে, তাই শেষ index হলো:

```python
4 - 1 = 3
```

অর্থাৎ `colors[3]` এবং `colors[-1]` একই element return করে।

## 6. Accessing Elements Using Variables

আমরা চাইলে একটি variable-এর মধ্যেও index number রাখতে পারি।

তারপর সেই variable ব্যবহার করে List-এর element access করতে পারি।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

index = 2

print(fruits[index])
```

**Output:**

```text
Mango
```

এখানে:

- `index = 2` মানে index variable-এর value হলো `2`।
- `fruits[index]` আসলে `fruits[2]`-এর মতো কাজ করে।

## 7. Accessing Elements from a List of Different Data Types

একটি List-এর মধ্যে বিভিন্ন ধরনের data থাকলেও Indexing ব্যবহার করে প্রতিটি element access করা যায়।

উদাহরণ:

```python
student = ["Masum", 23, 3.95, True]

print(student[0])
print(student[1])
print(student[2])
print(student[3])
```

**Output:**

```text
Masum
23
3.95
True
```

এখানে List-এর মধ্যে String, Integer, Float এবং Boolean value রয়েছে।

Indexing-এর নিয়ম সব ক্ষেত্রেই একই।

## 8. IndexError in Python

যদি আমরা List-এর মধ্যে থাকা element-এর valid index-এর বাইরে কোনো index ব্যবহার করি, তাহলে Python একটি `IndexError` দেখায়।

উদাহরণ:

```python
numbers = [10, 20, 30]

print(numbers[5])
```

**Output:**

```text
IndexError: list index out of range
```

এখানে List-এ মাত্র 3টি element রয়েছে।

Valid index হলো `0`, `1` এবং `2`।

কিন্তু আমরা `numbers[5]` ব্যবহার করেছি। তাই Python error দেখিয়েছে।

**আরেকটি উদাহরণ:**

```python
numbers = [10, 20, 30]

print(numbers[-5])
```

**Output:**

```text
IndexError: list index out of range
```

কারণ List-এর শেষ দিক থেকেও `-5` একটি invalid index।

## 9. Accessing Elements from an Empty List

Empty List-এর মধ্যে কোনো element থাকে না।

তাই Empty List থেকে কোনো index ব্যবহার করে element access করা যায় না।

উদাহরণ:

```python
numbers = []

print(numbers[0])
```

**Output:**

```text
IndexError: list index out of range
```

**মনে রাখবে:** Empty List-এর কোনো valid index নেই।

## 10. Important Rules of List Indexing

1. Python List Indexing শুরু হয় `0` থেকে।
2. Positive Indexing List-এর শুরু থেকে কাজ করে।
3. Negative Indexing List-এর শেষ থেকে কাজ করে।
4. `-1` হলো শেষ element-এর index।
5. `len(list) - 1` ব্যবহার করে শেষ positive index পাওয়া যায়।
6. Invalid index ব্যবহার করলে `IndexError` হয়।
7. Empty List-এর কোনো valid index নেই।
8. Indexing ব্যবহার করে List-এর নির্দিষ্ট একটি element access করা যায়।

## 11. Common Mistakes

### Mistake 1: Starting Index from 1

ভুল:

```python
fruits = ["Apple", "Banana", "Mango"]

print(fruits[1])
```

এখানে অনেকে মনে করতে পারে `fruits[1]` প্রথম element return করবে।

কিন্তু এটি দ্বিতীয় element return করবে।

**Correct:**

```python
print(fruits[0])
```

**Output:**

```text
Apple
```

### Mistake 2: Using an Invalid Index

ভুল:

```python
numbers = [10, 20, 30]

print(numbers[3])
```

কারণ এখানে শেষ valid index হলো `2`।

**Correct:**

```python
print(numbers[2])
```

**Output:**

```text
30
```

### Mistake 3: Confusing Negative Indexing

মনে রাখবে:

- `-1` হলো শেষ element।
- `-2` হলো শেষ থেকে দ্বিতীয় element।

Negative Indexing-এ `-1` থেকে শুরু হয়, `0` থেকে নয়।

## 12. Practice Exercises

### Exercise 1: Predict the Output

নিচের code-এর output কী হবে?

```python
numbers = [5, 10, 15, 20, 25]

print(numbers[0])
print(numbers[3])
print(numbers[-1])
print(numbers[-3])
```

**Solution:**

```text
5
20
25
15
```

### Exercise 2: Access the First and Last Element

একটি List থেকে প্রথম এবং শেষ element print করো।

**Solution:**

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print("First:", fruits[0])
print("Last:", fruits[-1])
```

**Output:**

```text
First: Apple
Last: Orange
```

### Exercise 3: Use a Variable as an Index

নিচের List থেকে index variable ব্যবহার করে `Computer` print করো।

**Solution:**

```python
subjects = ["Python", "Java", "Computer", "Math"]

index = 2

print(subjects[index])
```

**Output:**

```text
Computer
```

### Exercise 4: Find the Last Element Using len()

**Solution:**

```python
numbers = [100, 200, 300, 400, 500]

last_index = len(numbers) - 1

print(numbers[last_index])
```

**Output:**

```text
500
```

## 13. Chapter Summary

এই topic-এ আমরা শিখেছি:

- List Indexing কী।
- Positive Indexing কীভাবে কাজ করে।
- Negative Indexing কীভাবে কাজ করে।
- প্রথম এবং শেষ element access করা।
- Variable ব্যবহার করে element access করা।
- `len()` ব্যবহার করে শেষ index বের করা।
- Invalid index-এর কারণে `IndexError` কেন হয়।
- Empty List থেকে element access করলে কী error হয়।

## 14. Self-Assessment Checklist

নিচের বিষয়গুলো নিজে করতে পারলে এই topic ভালোভাবে শেখা হয়েছে:

- [ ] List-এর প্রথম element access করতে পারি।
- [ ] Positive Indexing বুঝি।
- [ ] Negative Indexing বুঝি।
- [ ] শেষ element access করতে পারি।
- [ ] Variable ব্যবহার করে element access করতে পারি।
- [ ] `len()` দিয়ে শেষ index বের করতে পারি।
- [ ] `IndexError` কেন হয় বুঝতে পারি।

## 15. Next Topic

**08. Modifying List Elements Using Indexing**

পরবর্তী topic-এ আমরা শিখব কীভাবে Indexing ব্যবহার করে List-এর নির্দিষ্ট element পরিবর্তন করা যায়।