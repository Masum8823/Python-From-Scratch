# 23. Iterating Over Lists and Tuples

## 1. Introduction

Python-এ **List** এবং **Tuple** হলো এমন দুটি data structure, যেখানে একাধিক item রাখা যায়।

- **List:** একাধিক item রাখে এবং পরিবর্তন করা যায়।
- **Tuple:** একাধিক item রাখে, কিন্তু তৈরি করার পর এর item পরিবর্তন করা যায় না।

এই item-গুলোকে একে একে access করে কাজ করার পদ্ধতিকে **Iteration** বলে।

উদাহরণস্বরূপ, একটি list-এ পাঁচটি সংখ্যা আছে। প্রতিটি সংখ্যা আলাদাভাবে print করতে চাইলে বারবার `print()` না লিখে `for` loop ব্যবহার করতে পারি।

```python
numbers = [10, 20, 30, 40, 50]

for number in numbers:
    print(number)
```

**Output:**

```text
10
20
30
40
50
```

এখানে `for` loop list-এর প্রতিটি item একবার করে নিয়েছে এবং print করেছে।

## 2. Iterating Over a List

List-এর ওপর `for` loop চালালে list-এর item-গুলো তাদের সংরক্ষিত order অনুযায়ী একে একে পাওয়া যায়।

**Syntax:**

```python
for variable in list_name:
    # কাজ
```

এখানে:

- `for` loop শুরু করে।
- `variable` প্রতিবার একটি item-এর value গ্রহণ করে।
- `list_name` হলো যে list-এর ওপর loop চলবে।
- Indented block-এর code প্রতিটি item-এর জন্য execute হয়।

**Example:**

```python
fruits = ["Apple", "Mango", "Banana"]

for fruit in fruits:
    print(fruit)
```

**Output:**

```text
Apple
Mango
Banana
```

প্রথম iteration-এ `fruit` হবে `"Apple"`। দ্বিতীয় iteration-এ `"Mango"` এবং তৃতীয় iteration-এ `"Banana"`।

## 3. Dry Run of List Iteration

নিচের code-টি দেখো:

```python
numbers = [5, 10, 15]

for number in numbers:
    print(number * 2)
```

**Dry Run Table:**

| Iteration | `number` | `number * 2` |
|---|---:|---:|
| 1 | 5 | 10 |
| 2 | 10 | 20 |
| 3 | 15 | 30 |

**Output:**

```text
10
20
30
```

মনে রাখবে, loop-এর variable প্রতিটি iteration-এ নতুন item-এর value গ্রহণ করে।

## 4. Performing Calculations on List Items

Loop-এর মাধ্যমে list-এর প্রতিটি item নিয়ে calculation করা যায়।

### Example 1: Finding the sum

```python
numbers = [10, 20, 30, 40]

total = 0

for number in numbers:
    total += number

print("Total:", total)
```

**Output:**

```text
Total: 100
```

এখানে `total` হলো একটি accumulator, যা প্রতিটি সংখ্যার যোগফল জমা রাখে।

### Example 2: Multiplying each item

```python
numbers = [2, 4, 6]

for number in numbers:
    print(number * 3)
```

**Output:**

```text
6
12
18
```

### Example 3: Finding the average

```python
numbers = [10, 20, 30, 40]

total = 0

for number in numbers:
    total += number

if len(numbers) > 0:
    average = total / len(numbers)
    print("Average:", average)
else:
    print("The list is empty.")
```

**Output:**

```text
Average: 25.0
```

এখানে:

- `sum` বা `total` দিয়ে যোগফল বের করা হয়েছে।
- `len(numbers)` দিয়ে মোট item-এর সংখ্যা বের করা হয়েছে।
- যোগফলকে item-এর সংখ্যা দিয়ে ভাগ করে average বের করা হয়েছে।

Empty list হলে zero দিয়ে ভাগ হওয়ার সমস্যা এড়াতে আগে list খালি কি না পরীক্ষা করা হয়েছে।

## 5. Counting Items with a Condition

List-এর কতগুলো item নির্দিষ্ট condition পূরণ করে, তা loop দিয়ে গণনা করা যায়।

### Example: Counting even numbers

```python
numbers = [1, 2, 3, 4, 5, 6, 8]

count = 0

for number in numbers:
    if number % 2 == 0:
        count += 1

print("Even numbers:", count)
```

**Output:**

```text
Even numbers: 4
```

এখানে `number % 2 == 0` দিয়ে even number শনাক্ত করা হয়েছে। Condition সত্য হলে `count` এক বাড়ে।

### Example: Counting numbers greater than 10

```python
numbers = [5, 12, 8, 20, 15, 3]

count = 0

for number in numbers:
    if number > 10:
        count += 1

print(count)
```

**Output:**

```text
3
```

কারণ `12`, `20` এবং `15` হলো 10-এর চেয়ে বড়।

## 6. Accessing List Items Using Index

List-এর item-গুলো index ব্যবহার করেও access করা যায়। Python-এ index শুরু হয় `0` থেকে।

```python
fruits = ["Apple", "Mango", "Banana"]

print(fruits[0])
print(fruits[1])
print(fruits[2])
```

**Output:**

```text
Apple
Mango
Banana
```

Index ব্যবহার করে loop চালানোর একটি পদ্ধতি হলো:

```python
fruits = ["Apple", "Mango", "Banana"]

for i in range(len(fruits)):
    print(fruits[i])
```

**Output:**

```text
Apple
Mango
Banana
```

এখানে:

- `len(fruits)` list-এর item সংখ্যা দেয়।
- `range(len(fruits))` `0` থেকে শেষ index পর্যন্ত সংখ্যা দেয়।
- `fruits[i]` দিয়ে ওই index-এর item পাওয়া যায়।

তবে শুধু item নিয়ে কাজ করতে চাইলে সাধারণত এটি বেশি সহজ:

```python
for fruit in fruits:
    print(fruit)
```

**মনে রাখবে:** শুধু item দরকার হলে সরাসরি `for item in list_name` ব্যবহার করো। Index-ও দরকার হলে `enumerate()` ব্যবহার করতে পারো।

## 7. Using enumerate() to Get Index and Item

`enumerate()` ব্যবহার করলে একই সঙ্গে প্রতিটি item এবং তার index পাওয়া যায়।

```python
fruits = ["Apple", "Mango", "Banana"]

for index, fruit in enumerate(fruits):
    print(index, fruit)
```

**Output:**

```text
0 Apple
1 Mango
2 Banana
```

এখানে `index` হলো item-এর index এবং `fruit` হলো item-এর value।

### Starting the index from 1

কখনো কখনো 0-এর পরিবর্তে 1 থেকে counting দেখাতে হয়।

```python
fruits = ["Apple", "Mango", "Banana"]

for index, fruit in enumerate(fruits, start=1):
    print(index, fruit)
```

**Output:**

```text
1 Apple
2 Mango
3 Banana
```

এটি numbered list বা serial number দেখানোর জন্য কাজে লাগে।

## 8. Iterating Over a Tuple

Tuple-এর ওপরও list-এর মতোই `for` loop চালানো যায়।

**Example:**

```python
colors = ("Red", "Green", "Blue")

for color in colors:
    print(color)
```

**Output:**

```text
Red
Green
Blue
```

List এবং Tuple iteration-এর মূল নিয়ম একই। পার্থক্য হলো, list পরিবর্তন করা যায় কিন্তু tuple-এর item পরিবর্তন করা যায় না।

## 9. Performing Calculations on Tuple Items

Tuple-এর item নিয়েও calculation করা যায়।

```python
numbers = (10, 20, 30, 40)

total = 0

for number in numbers:
    total += number

print(total)
```

**Output:**

```text
100
```

এখানে tuple-এর item পরিবর্তন করা হয়নি। শুধু item-গুলো পড়া হয়েছে এবং তাদের যোগফল `total` variable-এ জমা রাখা হয়েছে।

## 10. Finding Maximum and Minimum Values

Loop ব্যবহার করে list বা tuple-এর সবচেয়ে বড় এবং ছোট value খুঁজে বের করা যায়।

### Finding the maximum value

```python
numbers = [15, 8, 25, 12, 4]

if numbers:
    largest = numbers[0]

    for number in numbers:
        if number > largest:
            largest = number

    print("Maximum:", largest)
else:
    print("The list is empty.")
```

**Output:**

```text
Maximum: 25
```

**কীভাবে কাজ করে?**

1. প্রথম item-কে প্রাথমিক `largest` ধরা হয়েছে।
2. প্রতিটি item-এর সঙ্গে `largest` তুলনা করা হয়েছে।
3. কোনো item বড় হলে `largest` update হয়েছে।
4. Loop শেষে সবচেয়ে বড় value পাওয়া গেছে।

### Finding the minimum value

```python
numbers = [15, 8, 25, 12, 4]

if numbers:
    smallest = numbers[0]

    for number in numbers:
        if number < smallest:
            smallest = number

    print("Minimum:", smallest)
else:
    print("The list is empty.")
```

**Output:**

```text
Minimum: 4
```

**Important:** Empty list-এ `numbers[0]` access করলে `IndexError` হবে। তাই আগে `if numbers:` দিয়ে list খালি কি না পরীক্ষা করা হয়েছে।

Python-এ built-in `max()` এবং `min()` function-ও আছে। তবে loop দিয়ে নিজে বের করার নিয়ম শেখা problem-solving-এর জন্য গুরুত্বপূর্ণ।

## 11. Filtering List Items Using a Loop

কোনো condition পূরণ করা item-গুলো আলাদা list-এ রাখা যায়। এই প্রক্রিয়াকে এখানে filtering বলা হচ্ছে।

### Example: Collecting even numbers

```python
numbers = [1, 2, 3, 4, 5, 6]

even_numbers = []

for number in numbers:
    if number % 2 == 0:
        even_numbers.append(number)

print(even_numbers)
```

**Output:**

```text
[2, 4, 6]
```

এখানে:

- `even_numbers = []` দিয়ে খালি list তৈরি করা হয়েছে।
- Even number পাওয়া গেলে `append()` দিয়ে নতুন list-এ যোগ করা হয়েছে।

### Example: Collecting positive numbers

```python
numbers = [-5, 10, -2, 7, 0, 4]

positive_numbers = []

for number in numbers:
    if number > 0:
        positive_numbers.append(number)

print(positive_numbers)
```

**Output:**

```text
[10, 7, 4]
```

মনে রাখবে, `number > 0` হলে শুধু positive number নেওয়া হয়। Zero positive নয়।

## 12. Iterating Over a List of Strings

String-এর list-এর ওপর loop চালিয়ে প্রতিটি string নিয়ে কাজ করা যায়।

```python
names = ["Masum", "Ritu", "Mahin"]

for name in names:
    print("Hello,", name)
```

**Output:**

```text
Hello, Masum
Hello, Ritu
Hello, Mahin
```

### Finding names with a specific condition

```python
names = ["Masum", "Ritu", "Mahin", "Mitu"]

for name in names:
    if name.startswith("M"):
        print(name)
```

**Output:**

```text
Masum
Mahin
Mitu
```

`startswith("M")` পরীক্ষা করে string-টি `M` দিয়ে শুরু হয়েছে কি না।

## 13. Iterating Over a List of Tuples

একটি list-এর প্রতিটি item নিজেও tuple হতে পারে। একে nested data structure বলা যায়।

```python
students = [
    ("Masum", 90),
    ("Ritu", 85),
    ("Mahin", 88)
]

for student in students:
    print(student)
```

**Output:**

```text
('Masum', 90)
('Ritu', 85)
('Mahin', 88)
```

প্রতিটি `student` এখানে একটি tuple।

### Unpacking tuple items

Tuple-এর ভেতরে থাকা value-গুলো আলাদা variable-এ নেওয়া যায়।

```python
students = [
    ("Masum", 90),
    ("Ritu", 85),
    ("Mahin", 88)
]

for name, marks in students:
    print(name, "scored", marks)
```

**Output:**

```text
Masum scored 90
Ritu scored 85
Mahin scored 88
```

এখানে:

- `name` প্রথম value গ্রহণ করে।
- `marks` দ্বিতীয় value গ্রহণ করে।

**সতর্কতা:** প্রতিটি tuple-এ এখানে ঠিক দুটি value থাকতে হবে। Unpacking-এর variable-এর সংখ্যা ও value-এর সংখ্যা না মিললে সাধারণত `ValueError` হবে।

## 14. Using Conditions Inside List and Tuple Loops

Loop-এর ভেতরে `if-else` ব্যবহার করে বিভিন্ন condition অনুযায়ী কাজ করা যায়।

```python
numbers = [10, 15, 20, 25, 30]

for number in numbers:
    if number % 2 == 0:
        print(number, "is even")
    else:
        print(number, "is odd")
```

**Output:**

```text
10 is even
15 is odd
20 is even
25 is odd
30 is even
```

এই পদ্ধতি দিয়ে প্রতিটি item পরীক্ষা করে আলাদা কাজ করা যায়।

## 15. Common Mistakes

### Mistake 1: Confusing an item with its index

ভুল:

```python
fruits = ["Apple", "Mango", "Banana"]

for fruit in fruits:
    print(fruits[fruit])
```

এখানে `fruit` হলো string, কিন্তু `fruits[fruit]`-এ index হিসেবে string ব্যবহার করা হয়েছে। এতে `TypeError` হবে।

সঠিক:

```python
for fruit in fruits:
    print(fruit)
```

### Mistake 2: Using an incorrect index range

ভুল:

```python
numbers = [10, 20, 30]

for i in range(len(numbers) + 1):
    print(numbers[i])
```

শেষ iteration-এ index `3` হবে, কিন্তু valid index হলো `0`, `1`, `2`। ফলে `IndexError` হবে।

সঠিক:

```python
for i in range(len(numbers)):
    print(numbers[i])
```

আরও সহজ:

```python
for number in numbers:
    print(number)
```

### Mistake 3: Modifying a list while iterating over it

Loop চলার সময় একই list থেকে item remove করলে কিছু item বাদ পড়ে যেতে পারে।

উদাহরণ:

```python
numbers = [1, 2, 2, 3, 2]

for number in numbers:
    if number == 2:
        numbers.remove(number)

print(numbers)
```

এভাবে remove করার ফলে সব `2` নির্ভরযোগ্যভাবে বাদ যাবে—এমন নিশ্চয়তা নেই।

নিরাপদ পদ্ধতি:

```python
numbers = [1, 2, 2, 3, 2]

filtered_numbers = []

for number in numbers:
    if number != 2:
        filtered_numbers.append(number)

print(filtered_numbers)
```

**Output:**

```text
[1, 3]
```

### Mistake 4: Trying to change a tuple item

```python
colors = ("Red", "Green", "Blue")
colors[0] = "Yellow"
```

এতে `TypeError` হবে, কারণ tuple-এর item assignment করা যায় না।

Tuple-এর পরিবর্তে পরিবর্তনযোগ্য list দরকার হলে list ব্যবহার করতে পারো।

### Mistake 5: Forgetting to initialize the accumulator

ভুল:

```python
numbers = [10, 20, 30]

for number in numbers:
    total += number
```

`total` আগে তৈরি না করা থাকলে `NameError` হবে।

সঠিক:

```python
total = 0

for number in numbers:
    total += number

print(total)
```

## 16. Practice Exercises

নিজে চেষ্টা করো। তারপর নিচের answer key দিয়ে মিলিয়ে নাও।

### Exercise 1: Print every item

```python
numbers = [3, 6, 9, 12]
```

`for` loop দিয়ে প্রতিটি সংখ্যা print করো।

### Exercise 2: Find the sum

```python
numbers = [5, 10, 15, 20]
```

Loop ব্যবহার করে সব সংখ্যার যোগফল বের করো।

### Exercise 3: Count odd numbers

```python
numbers = [1, 2, 3, 4, 5, 6, 7]
```

কতটি odd number আছে তা বের করো।

### Exercise 4: Print index and item

```python
languages = ["Python", "Java", "C++"]
```

`enumerate()` ব্যবহার করে index এবং item print করো।

### Exercise 5: Filter positive numbers

```python
numbers = [-3, 5, 0, 8, -1, 4]
```

শুধু positive number-গুলো নতুন list-এ রাখো।

### Exercise 6: Find the maximum

```python
numbers = [12, 45, 7, 31, 22]
```

Loop ব্যবহার করে সবচেয়ে বড় সংখ্যা বের করো।

### Exercise 7: Iterate over a tuple

```python
subjects = ("Python", "AI", "Database")
```

প্রতিটি subject print করো।

### Exercise 8: Unpack tuples

```python
students = [("A", 80), ("B", 90), ("C", 85)]
```

প্রতিটি student-এর নাম ও marks print করো।

## 17. Practice Answer Key

### Answer 1

```python
numbers = [3, 6, 9, 12]

for number in numbers:
    print(number)
```

### Answer 2

```python
numbers = [5, 10, 15, 20]

total = 0

for number in numbers:
    total += number

print(total)
```

**Output:** `50`

### Answer 3

```python
numbers = [1, 2, 3, 4, 5, 6, 7]

count = 0

for number in numbers:
    if number % 2 != 0:
        count += 1

print(count)
```

**Output:** `4`

### Answer 4

```python
languages = ["Python", "Java", "C++"]

for index, language in enumerate(languages):
    print(index, language)
```

**Output:**

```text
0 Python
1 Java
2 C++
```

### Answer 5

```python
numbers = [-3, 5, 0, 8, -1, 4]

positive_numbers = []

for number in numbers:
    if number > 0:
        positive_numbers.append(number)

print(positive_numbers)
```

**Output:** `[5, 8, 4]`

### Answer 6

```python
numbers = [12, 45, 7, 31, 22]

largest = numbers[0]

for number in numbers:
    if number > largest:
        largest = number

print(largest)
```

**Output:** `45`

এই উদাহরণে list খালি নয় বলে `numbers[0]` ব্যবহার করা নিরাপদ।

### Answer 7

```python
subjects = ("Python", "AI", "Database")

for subject in subjects:
    print(subject)
```

### Answer 8

```python
students = [("A", 80), ("B", 90), ("C", 85)]

for name, marks in students:
    print(name, marks)
```

**Output:**

```text
A 80
B 90
C 85
```

## 18. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `for` loop দিয়ে list ও tuple-এর প্রতিটি item access করা।
- Loop-এর ভেতরে calculation করা এবং sum ও average বের করা।
- Condition ব্যবহার করে item count ও filter করা।
- Index access এবং `enumerate()` ব্যবহার করা।
- List ও tuple-এর item-এর পার্থক্য বোঝা।
- Nested tuple-এর value unpack করা।
- Empty list, invalid index এবং iteration চলাকালে list পরিবর্তনের মতো common mistake এড়ানো।

### Quick Revision

| কাজ | পদ্ধতি |
|---|---|
| প্রতিটি item access | `for item in items:` |
| Index ও item পাওয়া | `enumerate(items)` |
| Sum বের করা | `total += item` |
| Item count করা | `count += 1` |
| নতুন list-এ item যোগ | `new_list.append(item)` |
| Tuple unpack করা | `for name, marks in students:` |
| Empty list পরীক্ষা | `if items:` |

## 19. Completion Checklist

- [ ] List-এর ওপর `for` loop চালাতে পারি।
- [ ] Tuple-এর ওপর `for` loop চালাতে পারি।
- [ ] Loop দিয়ে sum ও average বের করতে পারি।
- [ ] Condition দিয়ে item count ও filter করতে পারি।
- [ ] `enumerate()` দিয়ে index ও item পেতে পারি।
- [ ] Nested tuple unpack করতে পারি।
- [ ] Common iteration errors বুঝতে পারি।

**Next Topic:** `24_Iterating_Over_Sets_and_Dictionaries.md`
