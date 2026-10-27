# 14. List Data Type in Python

## 1. What Is a List?

Python-এ **List হলো একটি built-in data type, যা একটি variable-এর মধ্যে একাধিক item বা value সংরক্ষণ করতে পারে।**

List তৈরি করতে square brackets `[]` ব্যবহার করা হয়। একাধিক item comma `,` দিয়ে আলাদা করা হয়।

Example:

```python
students = ["Masum", "Ritu", "Tusher"]

print(students)
print(type(students))
```

Output:

```text
['Masum', 'Ritu', 'Tusher']
<class 'list'>
```

এখানে `students` একটি List, যেখানে তিনটি String সংরক্ষিত আছে।

একটি List-এর মধ্যে বিভিন্ন data type-এর value-ও রাখা যায়।

```python
data = ["Masum", 22, 3.95, True]

print(data)
```

Output:

```text
['Masum', 22, 3.95, True]
```

এখানে String, Integer, Float এবং Boolean একসঙ্গে রয়েছে।

**মনে রাখবে:** List হলো একটি collection type। এটি একাধিক value-কে একটি variable-এর মাধ্যমে পরিচালনা করতে সাহায্য করে।

## 2. Creating a List

Python-এ বিভিন্ন উপায়ে List তৈরি করা যায়।

### 2.1 Empty List

কোনো item ছাড়া List তৈরি করতে `[]` ব্যবহার করা হয়।

```python
numbers = []

print(numbers)
print(type(numbers))
```

Output:

```text
[]
<class 'list'>
```

Empty List-এ পরে item যোগ করা যায়।

### 2.2 List with Multiple Items

```python
numbers = [10, 20, 30, 40, 50]

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

### 2.3 List with Different Data Types

```python
student = ["Masum", 22, 3.95, True]

print(student)
```

Output:

```text
['Masum', 22, 3.95, True]
```

### 2.4 List with Duplicate Values

List-এ একই value একাধিকবার রাখা যায়।

```python
numbers = [10, 20, 10, 30, 20]

print(numbers)
```

Output:

```text
[10, 20, 10, 30, 20]
```

### 2.5 Nested List

একটি List-এর মধ্যে আরেকটি List রাখা হলে তাকে **Nested List** বলা হয়।

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matrix)
```

Output:

```text
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

Nested List matrix, table এবং grouped data সংরক্ষণে কাজে লাগে।

## 3. Important Characteristics of Lists

Python List-এর কয়েকটি গুরুত্বপূর্ণ বৈশিষ্ট্য রয়েছে।

| Feature | Explanation |
|---|---|
| Ordered | Item-গুলোর নির্দিষ্ট position থাকে |
| Mutable | List তৈরি হওয়ার পর item পরিবর্তন করা যায় |
| Allows duplicates | একই value একাধিকবার থাকতে পারে |
| Allows mixed types | বিভিন্ন data type-এর value রাখা যায় |
| Indexed | Index ব্যবহার করে item access করা যায় |
| Dynamic size | Item যোগ বা বাদ দেওয়া যায় |

Example:

```python
items = ["Apple", "Banana", "Apple"]

print(items)
```

Output:

```text
['Apple', 'Banana', 'Apple']
```

এখানে duplicate value রয়েছে, এবং item-গুলোর position গুরুত্বপূর্ণ।

## 4. Accessing List Items with Indexing

List-এর নির্দিষ্ট item access করতে indexing ব্যবহার করা হয়।

Python-এ positive indexing `0` থেকে শুরু হয়।

Example:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print(fruits[0])
print(fruits[1])
print(fruits[2])
print(fruits[3])
```

Output:

```text
Apple
Banana
Mango
Orange
```

Index `0` প্রথম item নির্দেশ করে, index `1` দ্বিতীয় item নির্দেশ করে, এভাবে চলতে থাকে।

### Negative Indexing

Negative indexing List-এর শেষ দিক থেকে item access করতে সাহায্য করে।

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print(fruits[-1])
print(fruits[-2])
print(fruits[-3])
```

Output:

```text
Orange
Mango
Banana
```

**মনে রাখবে:**

- `0` হলো প্রথম item-এর index।
- `-1` হলো শেষ item-এর index।
- List-এর valid index-এর বাইরে access করলে `IndexError` হয়।

## 5. Finding the Length of a List

`len()` function List-এ মোট কতটি item আছে, তা return করে।

```python
fruits = ["Apple", "Banana", "Mango"]

print(len(fruits))
```

Output:

```text
3
```

Empty List-এর length হলো `0`।

```python
numbers = []

print(len(numbers))
```

Output:

```text
0
```

Nested List-এর ক্ষেত্রে `len()` শুধু outer List-এর item গণনা করে।

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6]
]

print(len(matrix))
print(len(matrix[0]))
```

Output:

```text
2
3
```

এখানে outer List-এ দুটি nested List আছে। প্রথম nested List-এ তিনটি item রয়েছে।

## 6. List Slicing

**Slicing** ব্যবহার করে List-এর নির্দিষ্ট অংশ বের করা যায়।

Syntax:

```python
list[start:stop:step]
```

- `start`: যে index থেকে শুরু হবে।
- `stop`: যে index পর্যন্ত যাবে, তবে সেই index-এর item অন্তর্ভুক্ত হবে না।
- `step`: কত ঘর পরপর item নেওয়া হবে।

### 6.1 Basic Slicing

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[0:3])
print(numbers[1:4])
```

Output:

```text
[10, 20, 30]
[20, 30, 40]
```

### 6.2 Omitting Start and Stop

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[:3])
print(numbers[2:])
print(numbers[:])
```

Output:

```text
[10, 20, 30]
[30, 40, 50]
[10, 20, 30, 40, 50]
```

### 6.3 Slicing with Step

```python
numbers = [10, 20, 30, 40, 50, 60]

print(numbers[::2])
print(numbers[1::2])
print(numbers[::-1])
```

Output:

```text
[10, 30, 50]
[20, 40, 60]
[60, 50, 40, 30, 20, 10]
```

`numbers[::-1]` দিয়ে List-এর item-গুলো উল্টো ক্রমে পাওয়া যায়।

**গুরুত্বপূর্ণ:** Slicing সাধারণত একটি নতুন List return করে। তাই slice-এর item পরিবর্তন করলে original List-এর সংশ্লিষ্ট item সরাসরি পরিবর্তিত হয় না।

## 7. Modifying List Items

Python List হলো **mutable**। অর্থাৎ List তৈরি হওয়ার পরও তার item পরিবর্তন করা যায়।

Example:

```python
fruits = ["Apple", "Banana", "Mango"]

fruits[1] = "Orange"

print(fruits)
```

Output:

```text
['Apple', 'Orange', 'Mango']
```

এখানে index `1`-এর item পরিবর্তন করা হয়েছে।

একাধিক item একসঙ্গে slicing assignment দিয়েও পরিবর্তন করা যায়।

```python
numbers = [10, 20, 30, 40]

numbers[1:3] = [200, 300]

print(numbers)
```

Output:

```text
[10, 200, 300, 40]
```

এখানে index `1` থেকে `2` পর্যন্ত item-গুলোর জায়গায় নতুন value বসেছে।

## 8. Adding Items to a List

List-এ নতুন item যোগ করার জন্য কয়েকটি গুরুত্বপূর্ণ method রয়েছে।

### 8.1 `append()`

`append()` List-এর শেষে একটি item যোগ করে।

```python
fruits = ["Apple", "Banana"]

fruits.append("Mango")

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango']
```

একটি List-কে `append()` করলে সেটি একটি item হিসেবে যুক্ত হয়।

```python
numbers = [10, 20]

numbers.append([30, 40])

print(numbers)
```

Output:

```text
[10, 20, [30, 40]]
```

এখানে `[30, 40]` একটি nested List হিসেবে যুক্ত হয়েছে।

### 8.2 `extend()`

`extend()` অন্য একটি iterable-এর item-গুলো বর্তমান List-এর শেষে যোগ করে।

```python
numbers = [10, 20]

numbers.extend([30, 40])

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

`append()` এবং `extend()`-এর পার্থক্য মনে রাখবে:

```python
a = [1, 2]
a.append([3, 4])

b = [1, 2]
b.extend([3, 4])

print(a)
print(b)
```

Output:

```text
[1, 2, [3, 4]]
[1, 2, 3, 4]
```

### 8.3 `insert()`

`insert()` নির্দিষ্ট index-এ item যোগ করে।

Syntax:

```python
list.insert(index, item)
```

Example:

```python
fruits = ["Apple", "Mango"]

fruits.insert(1, "Banana")

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango']
```

এখানে index `1`-এ `"Banana"` যুক্ত হয়েছে।

## 9. Removing Items from a List

List থেকে item বাদ দেওয়ার জন্য `remove()`, `pop()`, `del` এবং `clear()` ব্যবহার করা যায়।

### 9.1 `remove()`

`remove()` নির্দিষ্ট value-এর প্রথম occurrence বাদ দেয়।

```python
numbers = [10, 20, 30, 20]

numbers.remove(20)

print(numbers)
```

Output:

```text
[10, 30, 20]
```

এখানে প্রথম `20` বাদ গেছে, দ্বিতীয়টি রয়ে গেছে।

Value না থাকলে `remove()` `ValueError` তৈরি করে।

### 9.2 `pop()`

`pop()` নির্দিষ্ট index-এর item বাদ দেয় এবং সেই item return করে।

```python
fruits = ["Apple", "Banana", "Mango"]

removed = fruits.pop(1)

print(removed)
print(fruits)
```

Output:

```text
Banana
['Apple', 'Mango']
```

Index না দিলে `pop()` শেষ item বাদ দেয়।

```python
numbers = [10, 20, 30]

removed = numbers.pop()

print(removed)
print(numbers)
```

Output:

```text
30
[10, 20]
```

Empty List থেকে `pop()` করলে `IndexError` হয়।

### 9.3 `del`

`del` ব্যবহার করে নির্দিষ্ট index অথবা একটি slice বাদ দেওয়া যায়।

```python
numbers = [10, 20, 30, 40]

del numbers[1]

print(numbers)
```

Output:

```text
[10, 30, 40]
```

একাধিক item বাদ দেওয়া:

```python
numbers = [10, 20, 30, 40, 50]

del numbers[1:4]

print(numbers)
```

Output:

```text
[10, 50]
```

### 9.4 `clear()`

`clear()` List-এর সব item বাদ দেয়, কিন্তু List object-টি রেখে দেয়।

```python
numbers = [10, 20, 30]

numbers.clear()

print(numbers)
```

Output:

```text
[]
```

## 10. Checking Whether an Item Exists

`in` এবং `not in` operator ব্যবহার করে List-এর মধ্যে কোনো item আছে কি না পরীক্ষা করা যায়।

```python
fruits = ["Apple", "Banana", "Mango"]

print("Apple" in fruits)
print("Orange" in fruits)
print("Orange" not in fruits)
```

Output:

```text
True
False
True
```

এ ধরনের membership check user input validation এবং data filtering-এ কাজে লাগে।

## 11. Finding the Position of an Item

`index()` method কোনো value-এর প্রথম occurrence-এর index return করে।

```python
fruits = ["Apple", "Banana", "Mango", "Banana"]

print(fruits.index("Banana"))
```

Output:

```text
1
```

এখানে `"Banana"` প্রথম পাওয়া গেছে index `1`-এ।

Value List-এ না থাকলে `index()` `ValueError` তৈরি করে।

আগে membership check করা যায়:

```python
fruits = ["Apple", "Banana", "Mango"]

if "Orange" in fruits:
    print(fruits.index("Orange"))
else:
    print("Item not found.")
```

Output:

```text
Item not found.
```

## 12. Counting Items with `count()`

`count()` method কোনো value List-এ কতবার আছে, তা return করে।

```python
numbers = [10, 20, 10, 30, 10, 40]

print(numbers.count(10))
print(numbers.count(20))
print(numbers.count(50))
```

Output:

```text
3
1
0
```

Value না থাকলে `count()` error না দিয়ে `0` return করে।

## 13. Sorting a List

List-এর item sort করার জন্য `sort()` method অথবা `sorted()` function ব্যবহার করা যায়।

### 13.1 `sort()`

`sort()` original List-কে পরিবর্তন করে।

```python
numbers = [40, 10, 30, 20]

numbers.sort()

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

Descending order:

```python
numbers = [40, 10, 30, 20]

numbers.sort(reverse=True)

print(numbers)
```

Output:

```text
[40, 30, 20, 10]
```

### 13.2 `sorted()`

`sorted()` একটি নতুন sorted List return করে; original List পরিবর্তন করে না।

```python
numbers = [40, 10, 30, 20]

result = sorted(numbers)

print(result)
print(numbers)
```

Output:

```text
[10, 20, 30, 40]
[40, 10, 30, 20]
```

### 13.3 Sorting Strings

```python
names = ["Ritu", "Masum", "Tusher"]

names.sort()

print(names)
```

Output:

```text
['Masum', 'Ritu', 'Tusher']
```

String-এর sorting Unicode ordering অনুসরণ করে। Uppercase এবং lowercase String একসঙ্গে sort করলে case-এর কারণে প্রত্যাশিত ক্রম আলাদা হতে পারে।

Case-insensitive sorting:

```python
names = ["ritu", "Masum", "tusher"]

names.sort(key=str.lower)

print(names)
```

Output:

```text
['Masum', 'ritu', 'tusher']
```

## 14. Reversing a List

`reverse()` original List-এর item-এর ক্রম উল্টে দেয়।

```python
numbers = [10, 20, 30, 40]

numbers.reverse()

print(numbers)
```

Output:

```text
[40, 30, 20, 10]
```

`reverse()` এবং `sort(reverse=True)` এক নয়।

- `reverse()` বর্তমান order উল্টে দেয়।
- `sort(reverse=True)` descending order-এ sort করে।

Example:

```python
numbers = [30, 10, 40, 20]

numbers.reverse()
print(numbers)

numbers.sort(reverse=True)
print(numbers)
```

Output:

```text
[20, 40, 10, 30]
[40, 30, 20, 10]
```

## 15. List Concatenation and Repetition

### 15.1 Concatenation

`+` operator দিয়ে দুটি List যুক্ত করা যায়।

```python
a = [1, 2]
b = [3, 4]

result = a + b

print(result)
```

Output:

```text
[1, 2, 3, 4]
```

এতে original List-গুলো পরিবর্তিত হয় না; নতুন List তৈরি হয়।

### 15.2 Repetition

`*` operator দিয়ে List-এর item repeat করা যায়।

```python
numbers = [1, 2]

print(numbers * 3)
```

Output:

```text
[1, 2, 1, 2, 1, 2]
```

**সতর্কতা:** Nested mutable object repeat করলে একই inner object একাধিক position-এ reference হতে পারে।

```python
matrix = [[0]] * 3

matrix[0][0] = 1

print(matrix)
```

Output:

```text
[[1], [1], [1]]
```

এখানে তিনটি আলাদা inner List তৈরি হয়নি। একই inner List-এর reference তিনবার রাখা হয়েছে।

স্বাধীন inner List তৈরি করতে:

```python
matrix = [[0] for _ in range(3)]

matrix[0][0] = 1

print(matrix)
```

Output:

```text
[[1], [0], [0]]
```

## 16. Copying a List

List mutable হওয়ায় copy করার সময় সতর্ক থাকা দরকার।

### 16.1 Assignment Is Not a Copy

```python
a = [10, 20, 30]
b = a

b[0] = 100

print(a)
print(b)
```

Output:

```text
[100, 20, 30]
[100, 20, 30]
```

এখানে `b = a` নতুন List তৈরি করেনি। `a` এবং `b` একই List object-কে নির্দেশ করছে।

### 16.2 Copy with `copy()`

```python
a = [10, 20, 30]
b = a.copy()

b[0] = 100

print(a)
print(b)
```

Output:

```text
[10, 20, 30]
[100, 20, 30]
```

এখানে `b` একটি shallow copy।

### 16.3 Copy with Slicing

```python
a = [10, 20, 30]
b = a[:]

b[0] = 100

print(a)
print(b)
```

Output:

```text
[10, 20, 30]
[100, 20, 30]
```

এভাবেও একটি shallow copy তৈরি হয়।

**গুরুত্বপূর্ণ:** Nested List-এর মতো nested mutable object থাকলে shallow copy inner object-গুলোকে আলাদাভাবে copy করে না। Deep copy-এর বিষয়টি advanced topic-এ বিস্তারিত শেখা হবে।

## 17. Iterating Through a List

List-এর প্রতিটি item নিয়ে কাজ করতে `for` loop ব্যবহার করা যায়।

```python
fruits = ["Apple", "Banana", "Mango"]

for fruit in fruits:
    print(fruit)
```

Output:

```text
Apple
Banana
Mango
```

Index প্রয়োজন হলে `range()` এবং `len()` ব্যবহার করা যায়।

```python
fruits = ["Apple", "Banana", "Mango"]

for i in range(len(fruits)):
    print(i, fruits[i])
```

Output:

```text
0 Apple
1 Banana
2 Mango
```

আরও সহজভাবে index এবং item একসঙ্গে পেতে `enumerate()` ব্যবহার করা যায়।

```python
fruits = ["Apple", "Banana", "Mango"]

for index, fruit in enumerate(fruits):
    print(index, fruit)
```

Output:

```text
0 Apple
1 Banana
2 Mango
```

## 18. Basic List Operations

কিছু গুরুত্বপূর্ণ operation একসঙ্গে দেখা যাক।

```python
numbers = [10, 20, 30, 40]

print(len(numbers))
print(min(numbers))
print(max(numbers))
print(sum(numbers))
```

Output:

```text
4
10
40
100
```

এখানে:

- `len()` item-এর সংখ্যা দেয়।
- `min()` সবচেয়ে ছোট item দেয়।
- `max()` সবচেয়ে বড় item দেয়।
- `sum()` numeric item-গুলোর যোগফল দেয়।

`sum()` numeric value-এর জন্য ব্যবহার করো। আর `min()` ও `max()` ব্যবহার করার সময় item-গুলো পরস্পরের মধ্যে তুলনাযোগ্য কি না, তা নিশ্চিত করতে হবে।

## 19. Nested List Indexing

Nested List-এর মধ্যে থাকা item access করতে একাধিক index ব্যবহার করা যায়।

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matrix[0])
print(matrix[1][2])
print(matrix[2][0])
```

Output:

```text
[1, 2, 3]
6
7
```

ব্যাখ্যা:

- `matrix[0]` প্রথম nested List return করে।
- `matrix[1][2]` দ্বিতীয় nested List-এর তৃতীয় item return করে।
- `matrix[2][0]` তৃতীয় nested List-এর প্রথম item return করে।

## 20. Common Beginner Mistakes

### Mistake 1: Forgetting That Indexing Starts at Zero

```python
numbers = [10, 20, 30]

print(numbers[1])
```

Output:

```text
20
```

প্রথম item পেতে `numbers[0]` ব্যবহার করতে হবে।

### Mistake 2: Accessing an Invalid Index

```python
numbers = [10, 20, 30]

print(numbers[3])
```

এটি `IndexError` তৈরি করবে, কারণ valid positive index হলো `0`, `1` এবং `2`।

### Mistake 3: Confusing `append()` and `extend()`

```python
a = [1, 2]
a.append([3, 4])

b = [1, 2]
b.extend([3, 4])

print(a)
print(b)
```

Output:

```text
[1, 2, [3, 4]]
[1, 2, 3, 4]
```

### Mistake 4: Expecting `sort()` to Return a Sorted List

```python
numbers = [30, 10, 20]

result = numbers.sort()

print(result)
print(numbers)
```

Output:

```text
None
[10, 20, 30]
```

`sort()` original List পরিবর্তন করে এবং `None` return করে।

নতুন sorted List পেতে `sorted(numbers)` ব্যবহার করো।

### Mistake 5: Confusing Assignment with Copying

```python
a = [1, 2, 3]
b = a
```

এখানে `b` আলাদা List নয়। আলাদা shallow copy চাইলে `a.copy()` বা `a[:]` ব্যবহার করো।

### Mistake 6: Modifying a List While Iterating Over It

Iteration চলাকালে একই List থেকে item বাদ দিলে কিছু item বাদ পড়ে যেতে পারে।

```python
numbers = [1, 2, 3, 4, 5]

for number in numbers:
    if number % 2 == 0:
        numbers.remove(number)

print(numbers)
```

এ ধরনের code অপ্রত্যাশিত result দিতে পারে।

নতুন List তৈরি করে সমাধান করা যায়:

```python
numbers = [1, 2, 3, 4, 5]

result = []

for number in numbers:
    if number % 2 != 0:
        result.append(number)

print(result)
```

Output:

```text
[1, 3, 5]
```

## 21. Practice Exercises

### Exercise 1: Create a List

নিজের পছন্দের পাঁচটি programming language-এর নাম দিয়ে একটি List তৈরি করো। এরপর পুরো List এবং List-এর length print করো।

### Exercise 2: Indexing and Slicing

```python
numbers = [10, 20, 30, 40, 50, 60]
```

নিচের output বের করো:

```python
print(numbers[0])
print(numbers[-1])
print(numbers[1:4])
print(numbers[::2])
print(numbers[::-1])
```

### Exercise 3: Modify List Items

```python
fruits = ["Apple", "Banana", "Mango"]
```

`"Banana"`-কে `"Orange"` দিয়ে replace করো। এরপর updated List print করো।

### Exercise 4: Add and Remove Items

```python
numbers = [10, 20, 30]
```

- `append()` দিয়ে `40` যোগ করো।
- `insert()` দিয়ে index `1`-এ `15` যোগ করো।
- `remove()` দিয়ে `20` বাদ দাও।
- `pop()` দিয়ে শেষ item বাদ দাও।

প্রতিটি operation-এর পর List print করো।

### Exercise 5: Find and Count

```python
numbers = [10, 20, 10, 30, 10, 40]
```

`10` কতবার আছে এবং প্রথম `10`-এর index কত, তা বের করো।

### Exercise 6: Sorting

```python
numbers = [45, 12, 78, 23, 9]
```

প্রথমে ascending এবং পরে descending order-এ sort করো। `sort()` এবং `sorted()`-এর পার্থক্য দেখাও।

### Exercise 7: List Copying

```python
a = [1, 2, 3]
b = a
c = a.copy()
```

`b` এবং `c`-এর প্রথম item পরিবর্তন করে দেখো। Original List-এ কী প্রভাব পড়ে, ব্যাখ্যা করো।

### Exercise 8: Nested List

একটি nested List তৈরি করো, যেখানে তিনটি শিক্ষার্থীর নাম এবং তাদের marks আলাদা nested List-এ থাকবে। তারপর indexing ব্যবহার করে দ্বিতীয় শিক্ষার্থীর marks access করো।

### Exercise 9: List Summary

একটি numeric List তৈরি করো। `len()`, `min()`, `max()` এবং `sum()` ব্যবহার করে item-এর সংখ্যা, সর্বনিম্ন, সর্বোচ্চ এবং মোট যোগফল print করো।

### Exercise 10: Mini Project — Student Marks Manager

একটি List-এ পাঁচজন শিক্ষার্থীর marks রাখো। এরপর:

1. সব marks print করো।
2. মোট শিক্ষার্থীর সংখ্যা বের করো।
3. সর্বোচ্চ ও সর্বনিম্ন marks বের করো।
4. মোট marks এবং average বের করো।
5. Marks ascending order-এ sort করো।
6. একটি নতুন marks value List-এর শেষে যোগ করো।

## 22. Key Takeaways

- List হলো Python-এর ordered ও mutable collection type।
- List তৈরি করতে square brackets `[]` ব্যবহার করা হয়।
- List duplicate item এবং mixed data type support করে।
- Indexing `0` থেকে শুরু হয়; negative indexing শেষ দিক থেকে কাজ করে।
- Slicing দিয়ে List-এর নির্দিষ্ট অংশ নেওয়া যায়।
- `append()` একটি item যোগ করে, আর `extend()` iterable-এর item-গুলো যোগ করে।
- `insert()` নির্দিষ্ট index-এ item যোগ করে।
- `remove()`, `pop()`, `del` এবং `clear()` বিভিন্নভাবে item বাদ দেয়।
- `index()` প্রথম matching item-এর index দেয়; `count()` occurrence গণনা করে।
- `sort()` original List পরিবর্তন করে; `sorted()` নতুন sorted List return করে।
- `reverse()` বর্তমান order উল্টে দেয়।
- `b = a` আলাদা List তৈরি করে না; `a.copy()` shallow copy তৈরি করে।
- Nested List-এর item একাধিক index দিয়ে access করা যায়।
- List iteration-এর সময় একই List পরিবর্তন করলে অপ্রত্যাশিত result হতে পারে।

## 23. Next Topic

পরবর্তী ফাইল:

**`15_Tuple_Data_Type.md`**

সেখানে Python-এর Tuple, immutable collection, tuple packing ও unpacking, indexing এবং List-এর সঙ্গে Tuple-এর পার্থক্য শেখা হবে।