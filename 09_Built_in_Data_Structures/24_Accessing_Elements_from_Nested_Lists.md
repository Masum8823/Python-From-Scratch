# 24. Accessing Elements from Nested Lists

## 1. Introduction to Accessing Elements from Nested Lists

Nested List-এর ভিতরে থাকা নির্দিষ্ট element access করার জন্য একাধিক index ব্যবহার করতে হয়।

সাধারণ List-এ একটি index ব্যবহার করে element access করা হয়। কিন্তু Nested List-এর ক্ষেত্রে প্রথমে outer List-এর index এবং পরে inner List-এর index ব্যবহার করতে হয়।

**Syntax:**

```python
list_name[outer_index][inner_index]
```

এখানে:

- `outer_index` নির্দিষ্ট inner List নির্বাচন করে।
- `inner_index` সেই inner List-এর নির্দিষ্ট element নির্বাচন করে।

**Example:**

```python
numbers = [
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
]

print(numbers[0][1])
```

**Output:**

```text
20
```

এখানে:

- `numbers[0]` হলো `[10, 20, 30]`।
- `numbers[0][1]` হলো `20`।

---

## 2. Accessing Inner Lists Using Outer Index

Nested List-এর outer index ব্যবহার করে সম্পূর্ণ একটি inner List access করা যায়।

**Example:**

```python
numbers = [
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
]

print(numbers[0])
print(numbers[1])
print(numbers[2])
```

**Output:**

```text
[10, 20, 30]
[40, 50, 60]
[70, 80, 90]
```

এখানে:

- `numbers[0]` প্রথম inner List return করে।
- `numbers[1]` দ্বিতীয় inner List return করে।
- `numbers[2]` তৃতীয় inner List return করে।

---

## 3. Accessing Individual Elements from Nested Lists

একাধিক index ব্যবহার করে Nested List-এর নির্দিষ্ট element access করা যায়।

**Example:**

```python
numbers = [
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
]

print(numbers[0][0])
print(numbers[1][1])
print(numbers[2][2])
```

**Output:**

```text
10
50
90
```

এখানে:

- `numbers[0][0]` প্রথম Row-এর প্রথম element।
- `numbers[1][1]` দ্বিতীয় Row-এর দ্বিতীয় element।
- `numbers[2][2]` তৃতীয় Row-এর তৃতীয় element।

---

## 4. Accessing Elements Using Negative Indexing

Negative Indexing ব্যবহার করেও Nested List-এর element access করা যায়।

Python-এ negative index `-1` থেকে শুরু হয়।

**Example 1: Accessing the Last Inner List**

```python
numbers = [
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
]

print(numbers[-1])
```

**Output:**

```text
[70, 80, 90]
```

এখানে `numbers[-1]` শেষ inner List return করে।

**Example 2: Accessing the Last Element**

```python
numbers = [
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
]

print(numbers[0][-1])
print(numbers[-1][-1])
```

**Output:**

```text
30
90
```

এখানে:

- `numbers[0][-1]` প্রথম inner List-এর শেষ element।
- `numbers[-1][-1]` শেষ inner List-এর শেষ element।

---

## 5. Accessing Elements from a 2D List

Two-Dimensional List বা 2D List-এ Row এবং Column অনুযায়ী element access করা যায়।

**Example:**

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matrix[0][2])
print(matrix[1][0])
print(matrix[2][1])
```

**Output:**

```text
3
4
8
```

এখানে:

- `matrix[0][2]` প্রথম Row-এর তৃতীয় Column।
- `matrix[1][0]` দ্বিতীয় Row-এর প্রথম Column।
- `matrix[2][1]` তৃতীয় Row-এর দ্বিতীয় Column।

**Remember:**

```python
matrix[row_index][column_index]
```

---

## 6. Accessing Elements from a 3D List

Three-Dimensional List-এ element access করতে তিনটি index ব্যবহার করতে হয়।

**Syntax:**

```python
list_name[index1][index2][index3]
```

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

print(data[0][0][1])
print(data[1][0][0])
print(data[1][1][1])
```

**Output:**

```text
2
5
8
```

এখানে প্রতিটি index একটি নির্দিষ্ট nested level-এর element নির্বাচন করে।

---

## 7. Modifying Elements in a Nested List

Nested List-এর element access করে তার value পরিবর্তন করা যায়।

**Example:**

```python
numbers = [
    [10, 20, 30],
    [40, 50, 60]
]

numbers[0][1] = 200

print(numbers)
```

**Output:**

```text
[[10, 200, 30], [40, 50, 60]]
```

এখানে `numbers[0][1]`-এর পুরোনো value `20` পরিবর্তন করে `200` করা হয়েছে।

### Modifying Multiple Elements

**Example:**

```python
numbers = [
    [10, 20],
    [30, 40]
]

numbers[0][0] = 100
numbers[1][1] = 400

print(numbers)
```

**Output:**

```text
[[100, 20], [30, 400]]
```

এখানে দুটি আলাদা inner List-এর element পরিবর্তন করা হয়েছে।

---

## 8. Accessing Nested List Elements Using Variables

Index সরাসরি ব্যবহার না করে variable দিয়েও Nested List-এর element access করা যায়।

**Example:**

```python
numbers = [
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
]

row = 1
column = 2

print(numbers[row][column])
```

**Output:**

```text
60
```

এখানে:

- `row = 1` দ্বিতীয় Row নির্বাচন করে।
- `column = 2` তৃতীয় Column নির্বাচন করে।
- `numbers[row][column]` থেকে `60` পাওয়া যায়।

---

## 9. Accessing Elements Using Slicing

Nested List-এর inner List থেকে একাধিক element access করতে List Slicing ব্যবহার করা যায়।

**Example 1: Slicing an Inner List**

```python
numbers = [
    [10, 20, 30, 40, 50],
    [60, 70, 80, 90, 100]
]

print(numbers[0][1:4])
```

**Output:**

```text
[20, 30, 40]
```

এখানে প্রথম inner List-এর index `1` থেকে `3` পর্যন্ত element পাওয়া গেছে।

**Example 2: Accessing Multiple Inner Lists**

```python
numbers = [
    [10, 20],
    [30, 40],
    [50, 60],
    [70, 80]
]

print(numbers[0:2])
```

**Output:**

```text
[[10, 20], [30, 40]]
```

এখানে outer List-এর প্রথম দুটি inner List পাওয়া গেছে।

**Important:** `numbers[0:2]` outer List থেকে slicing করে, আর `numbers[0][1:4]` প্রথম inner List থেকে slicing করে।

---

## 10. Accessing Nested List Elements Using Loops

Nested List-এর সব element access করার জন্য nested `for` loop ব্যবহার করা যায়।

**Example:**

```python
numbers = [
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
]

for row in numbers:
    for number in row:
        print(number)
```

**Output:**

```text
10
20
30
40
50
60
70
80
90
```

এখানে:

- Outer loop প্রতিটি inner List access করে।
- Inner loop প্রতিটি inner List-এর element access করে।

### Accessing Elements with Index Using Nested Loops

**Example:**

```python
numbers = [
    [10, 20],
    [30, 40]
]

for i in range(len(numbers)):
    for j in range(len(numbers[i])):
        print(numbers[i][j])
```

**Output:**

```text
10
20
30
40
```

এখানে:

- `i` outer List-এর index নির্দেশ করে।
- `j` প্রতিটি inner List-এর index নির্দেশ করে।
- `numbers[i][j]` নির্দিষ্ট element access করে।

---

## 11. Accessing Row and Column Separately

2D List-এর নির্দিষ্ট Row বা Column access করা যায়।

### 11.1 Accessing a Specific Row

**Example:**

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matrix[1])
```

**Output:**

```text
[4, 5, 6]
```

এখানে দ্বিতীয় Row access করা হয়েছে।

### 11.2 Accessing a Specific Column

একটি নির্দিষ্ট Column-এর সব element access করতে loop ব্যবহার করা যায়।

**Example:**

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

for row in matrix:
    print(row[1])
```

**Output:**

```text
2
5
8
```

এখানে প্রতিটি Row-এর index `1` অর্থাৎ দ্বিতীয় Column-এর element print করা হয়েছে।

---

## 12. Accessing Elements from Irregular Nested Lists

Nested List-এর সব inner List-এর length সমান হওয়া বাধ্যতামূলক নয়।

এ ধরনের Nested List-এর প্রতিটি element access করতে `len()` ব্যবহার করা সুবিধাজনক।

**Example:**

```python
numbers = [
    [10, 20, 30],
    [40, 50],
    [60, 70, 80, 90]
]

for row in numbers:
    for number in row:
        print(number)
```

**Output:**

```text
10
20
30
40
50
60
70
80
90
```

এখানে প্রতিটি inner List-এর element সংখ্যা আলাদা হলেও loop সঠিকভাবে সব element access করেছে।

---

## 13. Common Beginner Mistakes

### Mistake 1: Using an Incorrect Index

**Incorrect:**

```python
numbers = [[10, 20], [30, 40]]

print(numbers[2][0])
```

**Output:**

```text
IndexError: list index out of range
```

এখানে outer List-এ শুধু index `0` এবং `1` রয়েছে। তাই index `2` ব্যবহার করলে error হবে।

**Correct:**

```python
numbers = [[10, 20], [30, 40]]

print(numbers[1][0])
```

**Output:**

```text
30
```

### Mistake 2: Using Only One Index

```python
numbers = [[10, 20], [30, 40]]

print(numbers[0])
```

**Output:**

```text
[10, 20]
```

এখানে সম্পূর্ণ inner List পাওয়া গেছে, নির্দিষ্ট element নয়।

নির্দিষ্ট element পেতে দুটি index ব্যবহার করতে হবে।

```python
print(numbers[0][1])
```

**Output:**

```text
20
```

### Mistake 3: Confusing Row and Column Index

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matrix[0][2])
```

**Output:**

```text
3
```

এখানে প্রথম index হলো Row এবং দ্বিতীয় index হলো Column।

### Mistake 4: Assuming Every Inner List Has the Same Length

```python
numbers = [[10, 20], [30, 40, 50]]

print(numbers[1][2])
```

**Output:**

```text
50
```

এখানে দ্বিতীয় inner List-এ তিনটি element রয়েছে, তাই index `2` valid।

তবে সব inner List-এর ক্ষেত্রে একই index valid হবে এমন নয়।

---

## 14. Important Points to Remember

1. Nested List-এর element access করতে একাধিক index ব্যবহার করা হয়।
2. `list_name[outer_index]` দিয়ে সম্পূর্ণ inner List পাওয়া যায়।
3. `list_name[outer_index][inner_index]` দিয়ে নির্দিষ্ট element পাওয়া যায়।
4. Python-এর index `0` থেকে শুরু হয়।
5. Negative Indexing ব্যবহার করেও element access করা যায়।
6. 2D List-এ প্রথম index Row এবং দ্বিতীয় index Column নির্দেশ করে।
7. 3D List-এর element access করতে তিনটি index ব্যবহার করা হয়।
8. Nested List-এর element পরিবর্তন করা যায়।
9. Slicing ব্যবহার করে একাধিক element access করা যায়।
10. Nested loop দিয়ে সব element access করা যায়।
11. `len()` ব্যবহার করে outer এবং inner List-এর length জানা যায়।
12. Invalid index ব্যবহার করলে `IndexError` হয়।

---

## 15. Practice Exercises

### Exercise 1

নিচের Nested List-এর প্রথম inner List print করো।

```python
numbers = [[10, 20], [30, 40], [50, 60]]
```

**Solution:**

```python
numbers = [[10, 20], [30, 40], [50, 60]]

print(numbers[0])
```

**Output:**

```text
[10, 20]
```

### Exercise 2

Nested List থেকে `50` access করো।

```python
numbers = [
    [10, 20, 30],
    [40, 50, 60]
]
```

**Solution:**

```python
numbers = [
    [10, 20, 30],
    [40, 50, 60]
]

print(numbers[1][1])
```

**Output:**

```text
50
```

### Exercise 3

Nested List-এর শেষ inner List access করো।

**Solution:**

```python
numbers = [[10, 20], [30, 40], [50, 60]]

print(numbers[-1])
```

**Output:**

```text
[50, 60]
```

### Exercise 4

নিচের Nested List-এর শেষ inner List-এর শেষ element print করো।

**Solution:**

```python
numbers = [[10, 20], [30, 40], [50, 60]]

print(numbers[-1][-1])
```

**Output:**

```text
60
```

### Exercise 5

Nested List-এর একটি element পরিবর্তন করে `200` করো।

**Solution:**

```python
numbers = [[10, 20], [30, 40]]

numbers[0][1] = 200

print(numbers)
```

**Output:**

```text
[[10, 200], [30, 40]]
```

### Exercise 6

নিচের Matrix-এর দ্বিতীয় Row-এর সব element print করো।

**Solution:**

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matrix[1])
```

**Output:**

```text
[4, 5, 6]
```

### Exercise 7

নিচের Matrix-এর তৃতীয় Column-এর সব element print করো।

**Solution:**

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

for row in matrix:
    print(row[2])
```

**Output:**

```text
3
6
9
```

### Exercise 8

Nested List-এর সব element nested loop ব্যবহার করে print করো।

**Solution:**

```python
numbers = [[10, 20], [30, 40], [50, 60]]

for row in numbers:
    for number in row:
        print(number)
```

**Output:**

```text
10
20
30
40
50
60
```

### Exercise 9

নিচের code-এর output কী হবে?

```python
numbers = [
    [10, 20, 30],
    [40, 50, 60]
]

print(numbers[1][-1])
```

**Solution:**

```text
60
```

### Exercise 10

নিচের code-এর output কী হবে?

```python
numbers = [
    [10, 20, 30],
    [40, 50, 60]
]

print(numbers[0][1:3])
```

**Solution:**

```text
[20, 30]
```

---

## 16. Chapter Summary

এই topic-এ আমরা Nested List থেকে element access করা শিখেছি।

- Outer index দিয়ে inner List access করা যায়।
- একাধিক index দিয়ে নির্দিষ্ট element access করা যায়।
- Negative Indexing ব্যবহার করা যায়।
- 2D List-এ Row এবং Column অনুযায়ী element access করা যায়।
- 3D List-এ তিনটি index ব্যবহার করা হয়।
- Nested List-এর element পরিবর্তন করা যায়।
- Slicing ব্যবহার করে একাধিক element access করা যায়।
- Nested loop ব্যবহার করে সব element access করা যায়।

---

## 17. Self-Assessment Checklist

নিজে যাচাই করো:

- [ ] Nested List থেকে inner List access করতে পারি।
- [ ] একাধিক index ব্যবহার করে element access করতে পারি।
- [ ] Negative Indexing ব্যবহার করতে পারি।
- [ ] 2D List থেকে Row এবং Column access করতে পারি।
- [ ] 3D List থেকে element access করতে পারি।
- [ ] Nested List-এর element modify করতে পারি।
- [ ] Nested List-এর উপর slicing ব্যবহার করতে পারি।
- [ ] Nested loop দিয়ে সব element access করতে পারি।
- [ ] নির্দিষ্ট Column-এর সব element বের করতে পারি।
- [ ] `IndexError` কেন হয় তা বুঝতে পেরেছি।

---

## 18. Next Topic

**25. List Comprehension Basics**

পরবর্তী topic-এ আমরা Python-এর List Comprehension শিখব। এর মাধ্যমে কম code ব্যবহার করে নতুন List তৈরি করা যায়।