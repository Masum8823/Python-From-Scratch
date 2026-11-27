# 23. Nested Lists in Python

## 1. What Is a Nested List?

Python-এ **Nested List** হলো এমন একটি List, যার ভিতরে এক বা একাধিক List থাকে।

অর্থাৎ, একটি List-এর মধ্যে অন্য List সংরক্ষণ করাকে Nested List বলে।

**Example:**

```python
numbers = [
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
]

print(numbers)
```

**Output:**

```text
[[10, 20, 30], [40, 50, 60], [70, 80, 90]]
```

এখানে `numbers` একটি Nested List, কারণ এর ভিতরে তিনটি আলাদা List রয়েছে।

---

## 2. Creating a Nested List

সাধারণ List-এর মতোই square brackets `[]` ব্যবহার করে Nested List তৈরি করা হয়।

**Syntax:**

```python
nested_list = [
    [element1, element2],
    [element3, element4]
]
```

**Example:**

```python
students = [
    ["Masum", 3.95],
    ["Rahim", 3.75],
    ["Karim", 3.80]
]

print(students)
```

**Output:**

```text
[['Masum', 3.95], ['Rahim', 3.75], ['Karim', 3.8]]
```

এখানে প্রতিটি inner List-এ একজন student-এর name এবং CGPA রাখা হয়েছে।

### Nested List with Different Data Types

Nested List-এর ভিতরে বিভিন্ন ধরনের data রাখা যায়।

**Example:**

```python
student = [
    ["Masum", "CSE"],
    [23, 3.95],
    [True, "NUB"]
]

print(student)
```

**Output:**

```text
[['Masum', 'CSE'], [23, 3.95], [True, 'NUB']]
```

এখানে String, Integer, Float এবং Boolean data ব্যবহার করা হয়েছে।

---

## 3. Types of Nested Lists

Nested List বিভিন্নভাবে তৈরি করা যায়।

### 3.1 Two-Dimensional List (2D List)

যে Nested List-এ একটি List-এর ভিতরে একাধিক List থাকে, তাকে সাধারণত Two-Dimensional List বলে।

এটি অনেকটা Table বা Matrix-এর মতো কাজ করে।

**Example:**

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matrix)
```

**Output:**

```text
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

এখানে:

- মোট 3টি Row রয়েছে।
- প্রতিটি Row-তে 3টি Column রয়েছে।

### 3.2 Three-Dimensional List (3D List)

যে List-এর ভিতরে একাধিক 2D List থাকে, তাকে Three-Dimensional List বলা হয়।

**Example:**

```python
data = [
    [
        [1, 2],
        [3, 4]
    ],
    [
        [5, 6],
        [7, 8]
    ]
]

print(data)
```

**Output:**

```text
[[[1, 2], [3, 4]], [[5, 6], [7, 8]]]
```

এখানে একটি List-এর ভিতরে দুটি 2D List রয়েছে।

---

## 4. Nested List as a Table

Nested List ব্যবহার করে সহজেই Table-এর মতো data সংরক্ষণ করা যায়।

**Example:**

```python
students = [
    ["Name", "Age", "CGPA"],
    ["Masum", 23, 3.95],
    ["Rahim", 22, 3.75],
    ["Karim", 24, 3.80]
]

for row in students:
    print(row)
```

**Output:**

```text
['Name', 'Age', 'CGPA']
['Masum', 23, 3.95]
['Rahim', 22, 3.75]
['Karim', 24, 3.8]
```

এখানে প্রতিটি inner List একটি Row হিসেবে কাজ করছে।

---

## 5. Creating an Empty Nested List

প্রথমে একটি empty List তৈরি করে পরে তার মধ্যে অন্য List যোগ করা যায়।

**Example:**

```python
students = []

students.append(["Masum", 3.95])
students.append(["Rahim", 3.75])
students.append(["Karim", 3.80])

print(students)
```

**Output:**

```text
[['Masum', 3.95], ['Rahim', 3.75], ['Karim', 3.8]]
```

এখানে `append()` ব্যবহার করে প্রতিটি inner List মূল List-এর মধ্যে যোগ করা হয়েছে।

### Adding a List Using `append()` and `extend()`

`append()` এবং `extend()` Nested List-এর ক্ষেত্রে ভিন্নভাবে কাজ করে।

**Example 1: Using `append()`**

```python
numbers = [[10, 20]]

numbers.append([30, 40])

print(numbers)
```

**Output:**

```text
[[10, 20], [30, 40]]
```

এখানে সম্পূর্ণ `[30, 40]` List-টি একটি single element হিসেবে যোগ হয়েছে।

**Example 2: Using `extend()`**

```python
numbers = [[10, 20]]

numbers.extend([30, 40])

print(numbers)
```

**Output:**

```text
[[10, 20], 30, 40]
```

এখানে `extend()` দ্বিতীয় List-এর element-গুলো আলাদাভাবে মূল List-এ যোগ করেছে।

**Important:** Nested List-এর মধ্যে নতুন inner List যোগ করতে চাইলে সাধারণত `append()` ব্যবহার করা হয়।

---

## 6. Length of a Nested List

`len()` function ব্যবহার করে Nested List-এর মোট outer element সংখ্যা জানা যায়।

**Example:**

```python
numbers = [
    [10, 20, 30],
    [40, 50],
    [60, 70, 80, 90]
]

print(len(numbers))
```

**Output:**

```text
3
```

এখানে outer List-এর মধ্যে 3টি inner List রয়েছে।

### Finding the Length of an Inner List

Inner List-এর length জানার জন্য তার index ব্যবহার করতে হয়।

**Example:**

```python
numbers = [
    [10, 20, 30],
    [40, 50],
    [60, 70, 80, 90]
]

print(len(numbers[0]))
print(len(numbers[1]))
print(len(numbers[2]))
```

**Output:**

```text
3
2
4
```

এখানে:

- `numbers[0]`-এ 3টি element রয়েছে।
- `numbers[1]`-এ 2টি element রয়েছে।
- `numbers[2]`-এ 4টি element রয়েছে।

---

## 7. Important Characteristics of Nested Lists

Nested List-এর কিছু গুরুত্বপূর্ণ বৈশিষ্ট্য:

1. একটি List-এর ভিতরে একাধিক List রাখা যায়।
2. Inner List-এর মধ্যে বিভিন্ন data type রাখা যায়।
3. Nested List-এর element index ব্যবহার করে access করা যায়।
4. Inner List-এর element পরিবর্তন করা যায়।
5. Nested List-এর মধ্যে নতুন List যোগ করা যায়।
6. Nested List-এর element remove করা যায়।
7. Nested List ব্যবহার করে Table এবং Matrix-এর মতো data সংরক্ষণ করা যায়।

---

## 8. Real-Life Examples of Nested Lists

Nested List বাস্তব জীবনের বিভিন্ন ধরনের data সংরক্ষণে ব্যবহার করা যায়।

### Example 1: Student Information

```python
students = [
    ["Masum", "CSE", 3.95],
    ["Rahim", "EEE", 3.75],
    ["Karim", "BBA", 3.80]
]

print(students)
```

**Output:**

```text
[['Masum', 'CSE', 3.95], ['Rahim', 'EEE', 3.75], ['Karim', 'BBA', 3.8]]
```

### Example 2: Product Information

```python
products = [
    ["Laptop", 75000],
    ["Mobile", 25000],
    ["Keyboard", 1500]
]

print(products)
```

**Output:**

```text
[['Laptop', 75000], ['Mobile', 25000], ['Keyboard', 1500]]
```

### Example 3: Monthly Sales

```python
sales = [
    [100, 150, 200],
    [120, 180, 220],
    [140, 190, 250]
]

print(sales)
```

**Output:**

```text
[[100, 150, 200], [120, 180, 220], [140, 190, 250]]
```

এখানে প্রতিটি inner List একটি আলাদা সময়ের sales data নির্দেশ করতে পারে।

---

## 9. Common Beginner Mistakes

### Mistake 1: Confusing a Nested List with a Normal List

**Normal List:**

```python
numbers = [10, 20, 30]
```

**Nested List:**

```python
numbers = [[10, 20], [30, 40]]
```

প্রথমটি Normal List এবং দ্বিতীয়টি Nested List।

### Mistake 2: Using `append()` and `extend()` Incorrectly

```python
numbers = [[10, 20]]

numbers.append([30, 40])

print(numbers)
```

**Output:**

```text
[[10, 20], [30, 40]]
```

অন্যদিকে:

```python
numbers = [[10, 20]]

numbers.extend([30, 40])

print(numbers)
```

**Output:**

```text
[[10, 20], 30, 40]
```

`append()` সম্পূর্ণ List-কে একটি element হিসেবে যোগ করে, কিন্তু `extend()` তার element-গুলো আলাদাভাবে যোগ করে।

### Mistake 3: Assuming All Inner Lists Have Equal Length

```python
numbers = [
    [10, 20],
    [30, 40, 50],
    [60]
]

print(len(numbers))
```

**Output:**

```text
3
```

প্রতিটি inner List-এর element সংখ্যা সমান হওয়া বাধ্যতামূলক নয়।

### Mistake 4: Forgetting the Nested Structure

```python
numbers = [[10, 20], [30, 40]]

print(numbers[0])
```

**Output:**

```text
[10, 20]
```

এখানে `numbers[0]` একটি সম্পূর্ণ inner List return করে, শুধু একটি number নয়।

---

## 10. Important Points to Remember

1. Nested List হলো একটি List-এর ভিতরে অন্য List।
2. Nested List তৈরি করতে square brackets `[]` ব্যবহার করা হয়।
3. 2D List অনেকটা Table বা Matrix-এর মতো।
4. 3D List-এর মধ্যে একাধিক 2D List থাকতে পারে।
5. `append()` সম্পূর্ণ List-কে একটি element হিসেবে যোগ করে।
6. `extend()` একটি List-এর element-গুলো আলাদাভাবে যোগ করে।
7. `len()` outer List-এর element সংখ্যা return করে।
8. Inner List-এর length জানতেও `len()` ব্যবহার করা যায়।
9. Nested List-এ বিভিন্ন data type রাখা যায়।
10. প্রতিটি inner List-এর length আলাদা হতে পারে।

---

## 11. Practice Exercises

### Exercise 1

নিচের information ব্যবহার করে একটি Nested List তৈরি করো।

- Masum, CSE, 3.95
- Rahim, EEE, 3.75
- Karim, BBA, 3.80

**Solution:**

```python
students = [
    ["Masum", "CSE", 3.95],
    ["Rahim", "EEE", 3.75],
    ["Karim", "BBA", 3.80]
]

print(students)
```

**Output:**

```text
[['Masum', 'CSE', 3.95], ['Rahim', 'EEE', 3.75], ['Karim', 'BBA', 3.8]]
```

### Exercise 2

একটি empty List তৈরি করে `append()` ব্যবহার করে তিনটি inner List যোগ করো।

**Solution:**

```python
students = []

students.append(["Masum", 3.95])
students.append(["Rahim", 3.75])
students.append(["Karim", 3.80])

print(students)
```

**Output:**

```text
[['Masum', 3.95], ['Rahim', 3.75], ['Karim', 3.8]]
```

### Exercise 3

নিচের Nested List-এর outer length বের করো।

```python
numbers = [[10, 20], [30, 40], [50, 60]]
```

**Solution:**

```python
numbers = [[10, 20], [30, 40], [50, 60]]

print(len(numbers))
```

**Output:**

```text
3
```

### Exercise 4

নিচের Nested List-এর প্রতিটি inner List-এর length বের করো।

**Solution:**

```python
numbers = [[10, 20], [30, 40, 50], [60]]

for row in numbers:
    print(len(row))
```

**Output:**

```text
2
3
1
```

### Exercise 5

একটি Nested List তৈরি করো যেখানে তিনটি product-এর name এবং price থাকবে।

**Solution:**

```python
products = [
    ["Laptop", 75000],
    ["Mobile", 25000],
    ["Keyboard", 1500]
]

print(products)
```

**Output:**

```text
[['Laptop', 75000], ['Mobile', 25000], ['Keyboard', 1500]]
```

### Exercise 6

নিচের code-এর output কী হবে?

```python
numbers = [[10, 20], [30, 40]]

print(numbers[0])
print(numbers[1])
```

**Solution:**

```text
[10, 20]
[30, 40]
```

### Exercise 7

নিচের code-এর output কী হবে?

```python
numbers = [[10, 20]]

numbers.append([30, 40])

print(len(numbers))
```

**Solution:**

```text
2
```

### Exercise 8

নিচের code-এর output কী হবে?

```python
numbers = [[10, 20]]

numbers.extend([30, 40])

print(numbers)
```

**Solution:**

```text
[[10, 20], 30, 40]
```

---

## 12. Chapter Summary

এই topic-এ আমরা Python-এর Nested List সম্পর্কে শিখেছি।

- Nested List হলো একটি List-এর ভিতরে অন্য List।
- `[]` ব্যবহার করে Nested List তৈরি করা যায়।
- 2D এবং 3D Nested List তৈরি করা যায়।
- Nested List ব্যবহার করে Table এবং Matrix-এর মতো data সংরক্ষণ করা যায়।
- `append()` এবং `extend()` দিয়ে element যোগ করা যায়।
- `len()` দিয়ে outer এবং inner List-এর length জানা যায়।
- Nested List-এ বিভিন্ন data type রাখা যায়।

---

## 13. Self-Assessment Checklist

নিজে যাচাই করো:

- [ ] Nested List কী তা বুঝতে পেরেছি।
- [ ] Nested List তৈরি করতে পারি।
- [ ] Different data types দিয়ে Nested List তৈরি করতে পারি।
- [ ] 2D List এবং 3D List বুঝতে পেরেছি।
- [ ] Nested List দিয়ে Table তৈরি করতে পারি।
- [ ] Empty Nested List তৈরি করতে পারি।
- [ ] `append()` এবং `extend()`-এর পার্থক্য বুঝতে পেরেছি।
- [ ] Outer List-এর length বের করতে পারি।
- [ ] Inner List-এর length বের করতে পারি।
- [ ] Nested List-এর ব্যবহার বুঝতে পেরেছি।

---

## 14. Next Topic

**24. Accessing Elements from Nested Lists**

পরবর্তী topic-এ আমরা শিখব কীভাবে Nested List-এর ভিতরের element-গুলো index ব্যবহার করে access করতে হয় এবং কীভাবে Row ও Column অনুযায়ী নির্দিষ্ট data বের করতে হয়।