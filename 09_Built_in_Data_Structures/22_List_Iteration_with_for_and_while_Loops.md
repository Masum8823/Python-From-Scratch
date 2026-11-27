# 22. List Iteration with `for` and `while` Loops

## 1. What Is List Iteration?

Python-এ **List Iteration** বলতে একটি List-এর প্রতিটি element একে একে access করার প্রক্রিয়াকে বোঝায়।

List-এর প্রতিটি element নিয়ে কাজ করার জন্য সাধারণত `for` এবং `while` loop ব্যবহার করা হয়।

**Example:**

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

এখানে `for` loop ব্যবহার করে List-এর প্রতিটি element একে একে print করা হয়েছে।

---

## 2. Iterating Through a List Using `for` Loop

Python-এ `for` loop ব্যবহার করে খুব সহজেই একটি List-এর প্রতিটি element access করা যায়।

**Syntax:**

```python
for variable in list_name:
    # Code to execute
```

এখানে:

- `variable` প্রতিবার List-এর একটি element গ্রহণ করে।
- `list_name` হলো যে List-এর উপর loop চালানো হবে।
- List-এর প্রতিটি element-এর জন্য loop একবার করে execute হয়।

**Example:**

```python
fruits = ["Apple", "Banana", "Mango"]

for fruit in fruits:
    print(fruit)
```

**Output:**

```text
Apple
Banana
Mango
```

এখানে:

1. প্রথম iteration-এ `fruit = "Apple"`।
2. দ্বিতীয় iteration-এ `fruit = "Banana"`।
3. তৃতীয় iteration-এ `fruit = "Mango"`।

এভাবে List-এর সব element একে একে access করা হয়েছে।

---

## 3. Iterating Through a List Using `while` Loop

`while` loop ব্যবহার করেও একটি List-এর প্রতিটি element access করা যায়।

এক্ষেত্রে List-এর index ব্যবহার করতে হয়।

**Syntax:**

```python
i = 0

while i < len(list_name):
    print(list_name[i])
    i += 1
```

এখানে:

- `i = 0` দিয়ে প্রথম index থেকে শুরু করা হয়েছে।
- `len()` List-এর মোট element সংখ্যা বের করে।
- `list_name[i]` দিয়ে বর্তমান index-এর element access করা হয়।
- `i += 1` দিয়ে পরবর্তী index-এ যাওয়া হয়।

**Example:**

```python
numbers = [10, 20, 30, 40]

i = 0

while i < len(numbers):
    print(numbers[i])
    i += 1
```

**Output:**

```text
10
20
30
40
```

এখানে `while` loop ব্যবহার করে List-এর প্রতিটি element print করা হয়েছে।

---

## 4. Iterating Through a List Using `range()` and `len()`

`range()` এবং `len()` একসাথে ব্যবহার করেও List-এর প্রতিটি element access করা যায়।

**Syntax:**

```python
for i in range(len(list_name)):
    print(list_name[i])
```

এখানে:

- `len()` List-এর মোট element সংখ্যা বের করে।
- `range()` প্রয়োজনীয় index তৈরি করে।
- `list_name[i]` দিয়ে প্রতিটি element access করা হয়।

**Example:**

```python
subjects = ["Python", "Java", "C++"]

for i in range(len(subjects)):
    print(subjects[i])
```

**Output:**

```text
Python
Java
C++
```

এখানে `range(len(subjects))` থেকে `0, 1, 2` index পাওয়া যায়।

এরপর সেই index ব্যবহার করে List-এর element print করা হয়েছে।

---

## 5. Iterating Through a List Using `enumerate()`

Python-এর built-in `enumerate()` function ব্যবহার করে একই সাথে List-এর index এবং element পাওয়া যায়।

**Syntax:**

```python
for index, value in enumerate(list_name):
    print(index, value)
```

এখানে:

- `index` প্রতিটি element-এর position নির্দেশ করে।
- `value` প্রতিটি element-এর value নির্দেশ করে।

**Example:**

```python
fruits = ["Apple", "Banana", "Mango"]

for index, fruit in enumerate(fruits):
    print(index, fruit)
```

**Output:**

```text
0 Apple
1 Banana
2 Mango
```

এখানে প্রতিটি iteration-এ index এবং corresponding element পাওয়া যাচ্ছে।

### Starting Index with `enumerate()`

সাধারণত `enumerate()` index গণনা `0` থেকে শুরু করে।

তবে `start` parameter ব্যবহার করে অন্য সংখ্যা থেকেও শুরু করা যায়।

**Example:**

```python
fruits = ["Apple", "Banana", "Mango"]

for index, fruit in enumerate(fruits, start=1):
    print(index, fruit)
```

**Output:**

```text
1 Apple
2 Banana
3 Mango
```

এখানে `start=1` দেওয়ার কারণে index গণনা `1` থেকে শুরু হয়েছে।

---

## 6. Iterating Through a List Using `reversed()`

Python-এর `reversed()` function ব্যবহার করে List-এর element-গুলো reverse order-এ iterate করা যায়।

**Example:**

```python
numbers = [10, 20, 30, 40]

for number in reversed(numbers):
    print(number)
```

**Output:**

```text
40
30
20
10
```

এখানে Original List পরিবর্তন না করেই শেষ থেকে প্রথম element পর্যন্ত access করা হয়েছে।

---

## 7. Using Conditions Inside List Iteration

List iteration করার সময় `if` condition ব্যবহার করে নির্দিষ্ট element নির্বাচন করা যায়।

**Example:**

```python
numbers = [10, 15, 20, 25, 30]

for number in numbers:
    if number % 2 == 0:
        print(number)
```

**Output:**

```text
10
20
30
```

এখানে:

- `number % 2 == 0` দিয়ে Even Number পরীক্ষা করা হয়েছে।
- Condition True হলে সংখ্যাটি print হয়েছে।
- তাই শুধু Even Number-গুলো পাওয়া গেছে।

**Another Example:**

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

for fruit in fruits:
    if fruit == "Mango":
        print("Mango found!")
```

**Output:**

```text
Mango found!
```

এখানে শুধু `"Mango"` পাওয়া গেলে message print হয়েছে।

---

## 8. Using `break` and `continue` During List Iteration

List iteration করার সময় `break` এবং `continue` ব্যবহার করা যায়।

### 8.1 Using `break`

`break` statement ব্যবহার করলে loop সম্পূর্ণভাবে বন্ধ হয়ে যায়।

**Example:**

```python
numbers = [10, 20, 30, 40, 50]

for number in numbers:
    if number == 30:
        break

    print(number)
```

**Output:**

```text
10
20
```

এখানে `30` পাওয়ার পর loop বন্ধ হয়ে গেছে।

### 8.2 Using `continue`

`continue` statement ব্যবহার করলে বর্তমান iteration বাদ দিয়ে পরবর্তী iteration শুরু হয়।

**Example:**

```python
numbers = [10, 20, 30, 40, 50]

for number in numbers:
    if number == 30:
        continue

    print(number)
```

**Output:**

```text
10
20
40
50
```

এখানে `30` print না করে পরবর্তী element-এ চলে গেছে।

---

## 9. Iterating Through a List and Calculating Sum

List iteration ব্যবহার করে List-এর সব সংখ্যার যোগফল বের করা যায়।

**Example:**

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

এখানে:

- `total = 0` দিয়ে শুরু করা হয়েছে।
- প্রতিটি number `total`-এর সাথে যোগ হয়েছে।
- শেষে মোট যোগফল পাওয়া গেছে।

---

## 10. Iterating Through a Nested List

Nested List-এর element access করার জন্য nested loop ব্যবহার করা যায়।

**Example:**

```python
numbers = [
    [10, 20],
    [30, 40],
    [50, 60]
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
```

এখানে:

- Outer loop প্রতিটি inner List access করে।
- Inner loop সেই List-এর প্রতিটি element access করে।
- এভাবে Nested List-এর সব element print করা হয়েছে।

---

## 11. Difference Between `for` and `while` Loop

List iteration-এর ক্ষেত্রে `for` এবং `while` উভয় loop ব্যবহার করা যায়।

তবে এদের মধ্যে কিছু পার্থক্য রয়েছে।

| Feature | `for` Loop | `while` Loop |
|---|---|---|
| Working | Iterates through elements | Runs while condition is True |
| Index | Not required | Often required |
| Syntax | Simple | Requires initialization and update |
| Usage | Direct List iteration | Condition-based iteration |
| Risk | Less chance of infinite loop | Infinite loop may occur |

**Example:**

```python
numbers = [10, 20, 30]

# Using for loop
for number in numbers:
    print(number)

# Using while loop
i = 0

while i < len(numbers):
    print(numbers[i])
    i += 1
```

**Output:**

```text
10
20
30
10
20
30
```

**Note:** সাধারণ List iteration-এর জন্য `for` loop সহজ এবং সুবিধাজনক। অন্যদিকে নির্দিষ্ট condition অনুযায়ী iteration নিয়ন্ত্রণ করতে `while` loop ব্যবহার করা যায়।

---

## 12. Common Beginner Mistakes

### Mistake 1: Forgetting to Update the Index in `while` Loop

**Incorrect:**

```python
numbers = [10, 20, 30]

i = 0

while i < len(numbers):
    print(numbers[i])
```

এখানে `i`-এর value পরিবর্তন করা হয়নি।

তাই loop বারবার প্রথম element print করবে এবং infinite loop তৈরি হবে।

**Correct:**

```python
numbers = [10, 20, 30]

i = 0

while i < len(numbers):
    print(numbers[i])
    i += 1
```

**Output:**

```text
10
20
30
```

### Mistake 2: Using an Incorrect Index Range

**Incorrect:**

```python
numbers = [10, 20, 30]

for i in range(1, len(numbers)):
    print(numbers[i])
```

**Output:**

```text
20
30
```

এখানে `range(1, len(numbers))` ব্যবহার করার কারণে প্রথম element বাদ পড়েছে।

**Correct:**

```python
numbers = [10, 20, 30]

for i in range(len(numbers)):
    print(numbers[i])
```

**Output:**

```text
10
20
30
```

### Mistake 3: Forgetting That Index Starts from 0

```python
fruits = ["Apple", "Banana", "Mango"]

for i in range(len(fruits)):
    print(i, fruits[i])
```

**Output:**

```text
0 Apple
1 Banana
2 Mango
```

Python List-এর index `0` থেকে শুরু হয়।

### Mistake 4: Modifying a List While Iterating

একই List-এর উপর loop চালানোর সময় সরাসরি element remove করলে কিছু element বাদ পড়ে যেতে পারে।

**Example:**

```python
numbers = [10, 20, 30, 40, 50]

for number in numbers:
    if number == 20 or number == 30:
        numbers.remove(number)

print(numbers)
```

**Output:**

```text
[10, 30, 40, 50]
```

এখানে iteration চলাকালীন List পরিবর্তন করার কারণে `30` remove হয়নি।

**Better Approach:**

```python
numbers = [10, 20, 30, 40, 50]

numbers = [number for number in numbers if number not in [20, 30]]

print(numbers)
```

**Output:**

```text
[10, 40, 50]
```

এখানে নতুন List তৈরি করে প্রয়োজনীয় element রাখা হয়েছে।

---

## 13. Important Points to Remember

1. List Iteration হলো List-এর প্রতিটি element একে একে access করা।
2. `for` loop দিয়ে সহজে List iterate করা যায়।
3. `while` loop দিয়েও List iterate করা যায়।
4. `len()` List-এর মোট element সংখ্যা return করে।
5. `range()` ব্যবহার করে List-এর index তৈরি করা যায়।
6. `enumerate()` একসাথে index এবং element return করে।
7. `enumerate()`-এর `start` parameter দিয়ে starting index নির্ধারণ করা যায়।
8. `reversed()` দিয়ে reverse order-এ iteration করা যায়।
9. `break` loop সম্পূর্ণ বন্ধ করে।
10. `continue` বর্তমান iteration বাদ দেয়।
11. Nested List iterate করতে nested loop ব্যবহার করা যায়।
12. `while` loop-এ index update করতে ভুললে infinite loop হতে পারে।
13. Iteration চলাকালীন একই List modify করা থেকে বিরত থাকা ভালো।

---

## 14. Practice Exercises

### Exercise 1

`for` loop ব্যবহার করে নিচের List-এর সব element print করো।

```python
numbers = [10, 20, 30, 40, 50]
```

**Solution:**

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

### Exercise 2

`while` loop ব্যবহার করে List-এর সব element print করো।

```python
fruits = ["Apple", "Banana", "Mango"]
```

**Solution:**

```python
fruits = ["Apple", "Banana", "Mango"]

i = 0

while i < len(fruits):
    print(fruits[i])
    i += 1
```

**Output:**

```text
Apple
Banana
Mango
```

### Exercise 3

`enumerate()` ব্যবহার করে index এবং element print করো।

```python
subjects = ["Python", "Java", "C++"]
```

**Solution:**

```python
subjects = ["Python", "Java", "C++"]

for index, subject in enumerate(subjects):
    print(index, subject)
```

**Output:**

```text
0 Python
1 Java
2 C++
```

### Exercise 4

List থেকে শুধু Even Number print করো।

```python
numbers = [10, 15, 20, 25, 30, 35]
```

**Solution:**

```python
numbers = [10, 15, 20, 25, 30, 35]

for number in numbers:
    if number % 2 == 0:
        print(number)
```

**Output:**

```text
10
20
30
```

### Exercise 5

List-এর সব element-এর যোগফল বের করো।

```python
numbers = [10, 20, 30, 40, 50]
```

**Solution:**

```python
numbers = [10, 20, 30, 40, 50]

total = 0

for number in numbers:
    total += number

print(total)
```

**Output:**

```text
150
```

### Exercise 6

নিচের List-এর element-গুলো reverse order-এ print করো।

```python
numbers = [10, 20, 30, 40]
```

**Solution:**

```python
numbers = [10, 20, 30, 40]

for number in reversed(numbers):
    print(number)
```

**Output:**

```text
40
30
20
10
```

### Exercise 7

নিচের code-এর output কী হবে?

```python
numbers = [10, 20, 30, 40]

for number in numbers:
    if number == 30:
        break

    print(number)
```

**Solution:**

```text
10
20
```

### Exercise 8

নিচের code-এর output কী হবে?

```python
numbers = [10, 20, 30, 40]

for number in numbers:
    if number == 20:
        continue

    print(number)
```

**Solution:**

```text
10
30
40
```

### Exercise 9

নিচের code-এর output কী হবে?

```python
numbers = [1, 2, 3]

for i in range(len(numbers)):
    print(i, numbers[i])
```

**Solution:**

```text
0 1
1 2
2 3
```

### Exercise 10

Nested List-এর সব element print করো।

```python
numbers = [[10, 20], [30, 40], [50, 60]]
```

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

---

## 15. Chapter Summary

এই topic-এ আমরা Python-এ List Iteration সম্পর্কে শিখেছি।

- `for` loop দিয়ে List-এর প্রতিটি element access করা যায়।
- `while` loop ব্যবহার করেও List iterate করা যায়।
- `range()` এবং `len()` দিয়ে index ব্যবহার করে element access করা যায়।
- `enumerate()` index এবং element একসাথে দেয়।
- `reversed()` reverse order-এ iteration করতে সাহায্য করে।
- `break` এবং `continue` দিয়ে loop control করা যায়।
- Nested loop দিয়ে Nested List iterate করা যায়।

---

## 16. Self-Assessment Checklist

নিজে যাচাই করো:

- [ ] List Iteration কী তা বুঝতে পেরেছি।
- [ ] `for` loop দিয়ে List iterate করতে পারি।
- [ ] `while` loop দিয়ে List iterate করতে পারি।
- [ ] `range()` এবং `len()` ব্যবহার করতে পারি।
- [ ] `enumerate()` ব্যবহার করে index এবং value পেতে পারি।
- [ ] `reversed()` ব্যবহার করে reverse iteration করতে পারি।
- [ ] `break` এবং `continue` ব্যবহার করতে পারি।
- [ ] List iteration-এর সময় condition ব্যবহার করতে পারি।
- [ ] List-এর সব element-এর যোগফল বের করতে পারি।
- [ ] Nested List iterate করতে পারি।
- [ ] Common beginner mistakes বুঝতে পেরেছি।

---

## 17. Next Topic

**23. Nested Lists in Python**

পরবর্তী topic-এ আমরা শিখব Nested List কী, কীভাবে একটি List-এর মধ্যে অন্য List রাখা যায় এবং কীভাবে Multi-dimensional List তৈরি করা যায়।