# 24. Iterating Over Sets and Dictionaries

## 1. Introduction

Python-এ `for` loop ব্যবহার করে শুধু list ও tuple নয়, **set এবং dictionary**-এর item নিয়েও কাজ করা যায়।

- **Set:** Unique item রাখে; duplicate item রাখে না।
- **Dictionary:** Key-value pair আকারে data রাখে।

উদাহরণ:

```python
numbers = {10, 20, 30}

student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}
```

Set-এ প্রতিটি item একবার করে পাওয়া যায়। Dictionary-তে সরাসরি loop চালালে সাধারণত key-গুলো পাওয়া যায়।

## 2. Iterating Over a Set

Set-এর ওপর `for` loop চালালে set-এর item-গুলো একে একে পাওয়া যায়।

**Syntax:**

```python
for item in set_name:
    print(item)
```

**Example:**

```python
fruits = {"Apple", "Mango", "Banana"}

for fruit in fruits:
    print(fruit)
```

সম্ভাব্য output:

```text
Apple
Banana
Mango
```

**Important:** Set-এর iteration order নির্দিষ্ট নয়। তাই output-এর item-এর order উপরের উদাহরণের মতোই হবে—এমন নিশ্চয়তা নেই।

## 3. Understanding Duplicate Items in Sets

Set duplicate item রাখে না।

```python
numbers = {10, 20, 10, 30, 20}

for number in numbers:
    print(number)
```

সম্ভাব্য output:

```text
10
20
30
```

এখানে `10` এবং `20` একাধিকবার দেওয়া হলেও set-এ প্রতিটি unique value একবার করে থাকে।

মনে রাখবে, set-এ duplicate বাদ পড়ে; কিন্তু iteration-এর order-কে sorting-এর মতো ধরে নেওয়া যাবে না।

## 4. Performing Calculations on Set Items

Set-এর প্রতিটি item নিয়ে calculation করা যায়।

```python
numbers = {2, 4, 6, 8}

total = 0

for number in numbers:
    total += number

print("Total:", total)
```

**Output:**

```text
Total: 20
```

Set-এর item-এর order যাই হোক, এই উদাহরণে সব সংখ্যার যোগফল একই থাকবে।

### Counting items that satisfy a condition

```python
numbers = {1, 2, 3, 4, 5, 6, 7, 8}

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

এখানে even number চারটি: `2`, `4`, `6` এবং `8`।

## 5. Iterating Over a Dictionary

Dictionary key-value pair আকারে data সংরক্ষণ করে।

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}
```

Dictionary-এর ওপর সরাসরি `for` loop চালালে **key** পাওয়া যায়।

```python
for key in student:
    print(key)
```

**Output:**

```text
name
age
department
```

এখানে `key` variable প্রতিবার একটি dictionary key গ্রহণ করে।

আরও স্পষ্টভাবে লিখতে চাইলে:

```python
for key in student.keys():
    print(key)
```

এখানেও key-গুলোই পাওয়া যাবে।

## 6. Accessing Values Using Dictionary Keys

Dictionary-এর key ব্যবহার করে তার corresponding value পাওয়া যায়।

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}

for key in student:
    print(student[key])
```

**Output:**

```text
Masum
22
CSE
```

এখানে:

- প্রথমে একটি key পাওয়া যায়।
- `student[key]` দিয়ে ওই key-এর value access করা হয়।
- তারপর পরবর্তী key নিয়ে একই কাজ করা হয়।

এই পদ্ধতিতে key এবং value দুটো নিয়েই কাজ করা যায়, যদিও আরও সহজ একটি পদ্ধতি আছে।

## 7. Using the keys() Method

`keys()` method dictionary-এর সব key-এর একটি view দেয়।

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}

for key in student.keys():
    print(key)
```

**Output:**

```text
name
age
department
```

**কখন ব্যবহার করবে?**

যখন dictionary-এর key-গুলো নিয়ে কাজ করতে হবে, তখন `keys()` ব্যবহার করতে পারো।

মনে রাখবে, `student.keys()` একটি `dict_keys` view দেয়; এটি নিজে list নয়।

List দরকার হলে:

```python
keys_list = list(student.keys())

print(keys_list)
```

**Output:**

```text
['name', 'age', 'department']
```

## 8. Using the values() Method

`values()` method dictionary-এর সব value-এর একটি view দেয়।

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}

for value in student.values():
    print(value)
```

**Output:**

```text
Masum
22
CSE
```

### Example: Calculating total marks

```python
marks = {
    "Python": 85,
    "Database": 90,
    "AI": 88
}

total = 0

for mark in marks.values():
    total += mark

print("Total marks:", total)
```

**Output:**

```text
Total marks: 263
```

এখানে শুধু marks-এর value নেওয়া হয়েছে। Subject-এর key প্রয়োজন হয়নি।

### Example: Finding the average

```python
marks = {
    "Python": 85,
    "Database": 90,
    "AI": 88
}

total = 0

for mark in marks.values():
    total += mark

if marks:
    average = total / len(marks)
    print("Average:", average)
else:
    print("No marks available.")
```

**Output:**

```text
Average: 87.66666666666667
```

`if marks:` দিয়ে dictionary খালি কি না পরীক্ষা করা হয়েছে। Empty dictionary হলে division করা হবে না।

## 9. Using the items() Method

`items()` method dictionary-এর key এবং value একসঙ্গে দেয়।

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}

for key, value in student.items():
    print(key, ":", value)
```

**Output:**

```text
name : Masum
age : 22
department : CSE
```

এখানে:

- `key` dictionary-এর key গ্রহণ করে।
- `value` সংশ্লিষ্ট value গ্রহণ করে।
- `items()` প্রতিটি key-value pair দেয়, যা দুটি variable-এ unpack করা হয়েছে।

Dictionary নিয়ে কাজ করার ক্ষেত্রে এটি সবচেয়ে কার্যকর পদ্ধতিগুলোর একটি।

## 10. Comparing keys(), values(), and items()

| Method | কী পাওয়া যায় | ব্যবহার |
|---|---|---|
| `keys()` | সব key | Key নিয়ে কাজ |
| `values()` | সব value | Value নিয়ে calculation |
| `items()` | Key ও value pair | দুটো নিয়েই কাজ |

একই dictionary দিয়ে পার্থক্য দেখো:

```python
student = {
    "name": "Masum",
    "age": 22
}

for key in student.keys():
    print(key)

for value in student.values():
    print(value)

for key, value in student.items():
    print(key, value)
```

**Output:**

```text
name
age
Masum
22
name Masum
age 22
```

## 11. Searching in a Dictionary

Loop ব্যবহার করে dictionary-এর মধ্যে নির্দিষ্ট value বা key খুঁজে বের করা যায়।

### Example: Finding a specific subject

```python
marks = {
    "Python": 85,
    "Database": 90,
    "AI": 88
}

target = "Database"

for subject, mark in marks.items():
    if subject == target:
        print(subject, "marks:", mark)
```

**Output:**

```text
Database marks: 90
```

### Example: Checking whether a key exists

কোনো key আছে কি না যাচাই করার জন্য সরাসরি `in` ব্যবহার করা যায়।

```python
student = {
    "name": "Masum",
    "age": 22
}

if "age" in student:
    print("Age is available.")
else:
    print("Age is not available.")
```

**Output:**

```text
Age is available.
```

`"age" in student` dictionary-এর key পরীক্ষা করে, value নয়।

Value পরীক্ষা করতে চাইলে:

```python
if 22 in student.values():
    print("The value exists.")
```

**Output:**

```text
The value exists.
```

## 12. Counting Dictionary Values Based on a Condition

Dictionary-এর value-গুলো কোনো condition পূরণ করে কি না, তা গোনা যায়।

### Example: Counting passing students

```python
marks = {
    "Masum": 85,
    "Ritu": 35,
    "Mahin": 70,
    "Tusher": 25
}

count = 0

for mark in marks.values():
    if mark >= 40:
        count += 1

print("Passed students:", count)
```

**Output:**

```text
Passed students: 2
```

এখানে `40` বা তার বেশি marks পাওয়া দুজনকে pass হিসেবে গণনা করা হয়েছে।

### Example: Printing students who passed

```python
marks = {
    "Masum": 85,
    "Ritu": 35,
    "Mahin": 70,
    "Tusher": 25
}

for name, mark in marks.items():
    if mark >= 40:
        print(name, mark)
```

**Output:**

```text
Masum 85
Mahin 70
```

এখানে `items()` ব্যবহার করে নাম ও marks দুটোই পাওয়া হয়েছে।

## 13. Creating a New Dictionary Using a Loop

Loop ব্যবহার করে নতুন dictionary তৈরি করা যায়।

### Example: Squaring numbers

```python
numbers = [1, 2, 3, 4]

squares = {}

for number in numbers:
    squares[number] = number ** 2

print(squares)
```

**Output:**

```text
{1: 1, 2: 4, 3: 9, 4: 16}
```

এখানে:

- Original list থেকে একটি সংখ্যা নেওয়া হয়েছে।
- সংখ্যাটিকে key হিসেবে ব্যবহার করা হয়েছে।
- তার square-কে value হিসেবে রাখা হয়েছে।

### Example: Converting values

```python
prices = {
    "Pen": 10,
    "Book": 100,
    "Bag": 500
}

updated_prices = {}

for item, price in prices.items():
    updated_prices[item] = price * 2

print(updated_prices)
```

**Output:**

```text
{'Pen': 20, 'Book': 200, 'Bag': 1000}
```

Original dictionary পরিবর্তন না করে নতুন dictionary তৈরি করা হয়েছে।

## 14. Nested Dictionary Iteration

একটি dictionary-এর value নিজেও dictionary হতে পারে। একে nested dictionary বলা হয়।

```python
students = {
    "S1": {"name": "Masum", "marks": 85},
    "S2": {"name": "Ritu", "marks": 90}
}
```

Nested dictionary-এর ওপর loop চালানো:

```python
for student_id, details in students.items():
    print(student_id, details)
```

**Output:**

```text
S1 {'name': 'Masum', 'marks': 85}
S2 {'name': 'Ritu', 'marks': 90}
```

### Accessing nested values

```python
for student_id, details in students.items():
    print("ID:", student_id)
    print("Name:", details["name"])
    print("Marks:", details["marks"])
```

**Output:**

```text
ID: S1
Name: Masum
Marks: 85
ID: S2
Name: Ritu
Marks: 90
```

এখানে `details` হলো প্রতিটি student-এর inner dictionary।

## 15. Understanding Iteration Order

List ও tuple তাদের সংরক্ষিত order অনুযায়ী iterate হয়। Dictionary-ও insertion order বজায় রাখে—অর্থাৎ key-গুলো যে ক্রমে যোগ করা হয়েছে, সাধারণভাবে iteration-এ সেই ক্রমে পাওয়া যায়।

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}

for key in student:
    print(key)
```

**Output:**

```text
name
age
department
```

অন্যদিকে, set-এর iteration order নির্দিষ্ট নয়। তাই set-এর output-এ একটি নির্দিষ্ট order-এর ওপর নির্ভর করবে না।

## 16. Common Mistakes

### Mistake 1: Expecting dictionary values from a direct loop

ভুল ধারণা:

```python
student = {"name": "Masum", "age": 22}

for item in student:
    print(item)
```

Output:

```text
name
age
```

এখানে value নয়, key পাওয়া যায়।

Values দরকার হলে:

```python
for value in student.values():
    print(value)
```

### Mistake 2: Using a missing key

```python
student = {"name": "Masum"}

print(student["age"])
```

এতে `KeyError` হবে, কারণ `"age"` key নেই।

নিরাপদ বিকল্প:

```python
print(student.get("age", "Not available"))
```

**Output:**

```text
Not available
```

### Mistake 3: Unpacking the wrong number of values

```python
student = {"name": "Masum", "age": 22}

for key, value, extra in student.items():
    print(key, value, extra)
```

এখানে প্রতিটি item-এ দুটি value থাকলেও তিনটি variable নেওয়া হয়েছে। তাই `ValueError` হবে।

সঠিক:

```python
for key, value in student.items():
    print(key, value)
```

### Mistake 4: Assuming set order

```python
numbers = {30, 10, 20}

for number in numbers:
    print(number)
```

এখানে `10, 20, 30` ক্রমেই output আসবে—এমন নিশ্চয়তা নেই। Sorted output চাইলে `sorted(numbers)` ব্যবহার করা যায়।

### Mistake 5: Changing dictionary size during iteration

Dictionary iterate করার সময় নতুন key যোগ করা বা key মুছে ফেলা runtime error ঘটাতে পারে।

ঝুঁকিপূর্ণ পদ্ধতি:

```python
student = {"name": "Masum", "age": 22}

for key in student:
    student["department"] = "CSE"
```

নিরাপদ পদ্ধতি হলো আগে নতুন dictionary তৈরি করা, অথবা প্রয়োজন অনুযায়ী key-গুলোর list তৈরি করে তার ওপর loop চালানো।

## 17. Practice Exercises

### Exercise 1: Iterate over a set

```python
numbers = {10, 20, 30, 40}
```

প্রতিটি item print করো।

### Exercise 2: Calculate set sum

```python
numbers = {2, 4, 6, 8}
```

Loop ব্যবহার করে যোগফল বের করো।

### Exercise 3: Print dictionary keys

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}
```

সব key print করো।

### Exercise 4: Print dictionary values

উপরের dictionary থেকে সব value print করো।

### Exercise 5: Print key-value pairs

`items()` ব্যবহার করে প্রতিটি key এবং value print করো।

### Exercise 6: Calculate total marks

```python
marks = {
    "Python": 80,
    "AI": 90,
    "Database": 85
}
```

Loop ব্যবহার করে মোট marks বের করো।

### Exercise 7: Count passing students

```python
marks = {
    "Masum": 85,
    "Ritu": 35,
    "Mahin": 70,
    "Tusher": 25
}
```

`40` বা তার বেশি marks পাওয়া student-এর সংখ্যা বের করো।

### Exercise 8: Create a squares dictionary

```python
numbers = [2, 3, 4, 5]
```

এমন dictionary তৈরি করো যেখানে প্রতিটি সংখ্যা key এবং তার square value হবে।

### Exercise 9: Access nested dictionary values

```python
students = {
    "S1": {"name": "Masum", "marks": 85},
    "S2": {"name": "Ritu", "marks": 90}
}
```

প্রতিটি student-এর নাম ও marks print করো।

## 18. Practice Answer Key

### Answer 1

```python
numbers = {10, 20, 30, 40}

for number in numbers:
    print(number)
```

Set-এর output order ভিন্ন হতে পারে।

### Answer 2

```python
numbers = {2, 4, 6, 8}

total = 0

for number in numbers:
    total += number

print(total)
```

**Output:** `20`

### Answer 3

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}

for key in student:
    print(key)
```

### Answer 4

```python
for value in student.values():
    print(value)
```

### Answer 5

```python
for key, value in student.items():
    print(key, value)
```

### Answer 6

```python
marks = {
    "Python": 80,
    "AI": 90,
    "Database": 85
}

total = 0

for mark in marks.values():
    total += mark

print(total)
```

**Output:** `255`

### Answer 7

```python
marks = {
    "Masum": 85,
    "Ritu": 35,
    "Mahin": 70,
    "Tusher": 25
}

count = 0

for mark in marks.values():
    if mark >= 40:
        count += 1

print(count)
```

**Output:** `2`

### Answer 8

```python
numbers = [2, 3, 4, 5]

squares = {}

for number in numbers:
    squares[number] = number ** 2

print(squares)
```

**Output:**

```text
{2: 4, 3: 9, 4: 16, 5: 25}
```

### Answer 9

```python
students = {
    "S1": {"name": "Masum", "marks": 85},
    "S2": {"name": "Ritu", "marks": 90}
}

for student_id, details in students.items():
    print(details["name"], details["marks"])
```

**Output:**

```text
Masum 85
Ritu 90
```

## 19. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Set-এর ওপর `for` loop চালানো।
- Set-এ duplicate item না থাকা এবং iteration order নির্দিষ্ট না হওয়া।
- Dictionary-এর ওপর সরাসরি loop চালালে key পাওয়া।
- `keys()`, `values()` এবং `items()`-এর ব্যবহার।
- Dictionary থেকে sum ও count বের করা।
- Loop দিয়ে নতুন dictionary তৈরি করা।
- Nested dictionary থেকে data access করা।
- Iteration-এর সময় dictionary পরিবর্তন করার ঝুঁকি বোঝা।

### Quick Revision Table

| কাজ | Code |
|---|---|
| Set iterate | `for item in my_set:` |
| Dictionary keys | `for key in data.keys():` |
| Dictionary values | `for value in data.values():` |
| Key-value pairs | `for key, value in data.items():` |
| Key আছে কি না | `if key in data:` |
| Safe value lookup | `data.get(key, default)` |
| Set sorted order-এ iterate | `for item in sorted(my_set):` |

## 20. Completion Checklist

- [ ] Set-এর item-গুলো loop দিয়ে access করতে পারি।
- [ ] Dictionary-এর key ও value-এর পার্থক্য বুঝি।
- [ ] `keys()`, `values()` এবং `items()` ব্যবহার করতে পারি।
- [ ] Dictionary-এর value দিয়ে calculation করতে পারি।
- [ ] Condition অনুযায়ী item count করতে পারি।
- [ ] Loop দিয়ে নতুন dictionary তৈরি করতে পারি।
- [ ] Nested dictionary থেকে data access করতে পারি।
- [ ] Set-এর order এবং dictionary-এর insertion order-এর পার্থক্য বুঝি।

**Next Topic:** `25_Introduction_to_the_range_Function.md`
