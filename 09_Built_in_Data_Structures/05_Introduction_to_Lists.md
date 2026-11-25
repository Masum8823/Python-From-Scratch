# 05. Introduction to Lists in Python

## 1. What is a List in Python?

**List** হলো Python-এর একটি Built-in Data Structure, যার মাধ্যমে একটি variable-এর মধ্যে একাধিক value সংরক্ষণ করা যায়।

List-এ বিভিন্ন ধরনের data রাখা যায়। যেমন: Integer, Float, String এবং Boolean।

List তৈরি করতে **Square Brackets `[]`** ব্যবহার করা হয়।

**Example:**

```python
students = ["Masum", "Rahim", "Karim"]

print(students)
```

**Output:**

```text
['Masum', 'Rahim', 'Karim']
```

এখানে `students` হলো একটি List variable এবং এর মধ্যে তিনটি student-এর নাম সংরক্ষণ করা হয়েছে।

---

## 2. Why Do We Use Lists?

একটি program-এ অনেকগুলো related value নিয়ে কাজ করতে হলে List ব্যবহার করা খুবই সুবিধাজনক।

List ব্যবহারের কয়েকটি কারণ:

1. একসাথে অনেকগুলো value সংরক্ষণ করা যায়।
2. একটি variable দিয়ে অনেকগুলো value manage করা যায়।
3. Index ব্যবহার করে নির্দিষ্ট value access করা যায়।
4. প্রয়োজন অনুযায়ী value পরিবর্তন করা যায়।
5. নতুন value যোগ এবং পুরোনো value বাদ দেওয়া যায়।
6. একই value একাধিকবার রাখা যায়।

**Example:**

```python
marks = [80, 85, 90, 75, 95]

print(marks)
```

**Output:**

```text
[80, 85, 90, 75, 95]
```

এখানে পাঁচটি marks একটি List-এর মধ্যে রাখা হয়েছে।

---

## 3. Creating a List

Python-এ Square Brackets `[]` ব্যবহার করে List তৈরি করা হয়।

**Syntax:**

```python
list_name = [item1, item2, item3]
```

এখানে:

- `list_name` হলো List-এর নাম।
- `item1`, `item2`, `item3` হলো List-এর value।
- প্রতিটি item কমা `,` দিয়ে আলাদা করা হয়।

**Example:**

```python
fruits = ["Apple", "Banana", "Mango"]

print(fruits)
```

**Output:**

```text
['Apple', 'Banana', 'Mango']
```

---

## 4. Creating Different Types of Lists

Python List-এ বিভিন্ন ধরনের data রাখা যায়।

### 4.1 List of Strings

String value দিয়ে List তৈরি করা যায়।

```python
names = ["Masum", "Rahim", "Karim"]

print(names)
```

**Output:**

```text
['Masum', 'Rahim', 'Karim']
```

### 4.2 List of Integers

Integer value দিয়েও List তৈরি করা যায়।

```python
numbers = [10, 20, 30, 40, 50]

print(numbers)
```

**Output:**

```text
[10, 20, 30, 40, 50]
```

### 4.3 List of Floats

Float value দিয়ে List তৈরি করা যায়।

```python
prices = [10.5, 20.75, 30.25]

print(prices)
```

**Output:**

```text
[10.5, 20.75, 30.25]
```

### 4.4 List of Booleans

Boolean value দিয়েও List তৈরি করা যায়।

```python
results = [True, False, True]

print(results)
```

**Output:**

```text
[True, False, True]
```

### 4.5 Mixed Data Types in a List

একটি List-এর মধ্যে একাধিক ধরনের data রাখা যায়।

```python
data = ["Masum", 22, 3.95, True]

print(data)
```

**Output:**

```text
['Masum', 22, 3.95, True]
```

এখানে:

- `"Masum"` হলো String।
- `22` হলো Integer।
- `3.95` হলো Float।
- `True` হলো Boolean।

অর্থাৎ, Python List-এ different data types একসাথে রাখা সম্ভব।

---

## 5. Creating an Empty List

কোনো item ছাড়াই Empty List তৈরি করা যায়।

**Example 1: Using Square Brackets**

```python
students = []

print(students)
```

**Output:**

```text
[]
```

**Example 2: Using list() Function**

```python
students = list()

print(students)
```

**Output:**

```text
[]
```

দুটি পদ্ধতিতেই Empty List তৈরি হয়।

---

## 6. List Allows Duplicate Values

Python List-এ একই value একাধিকবার রাখা যায়।

**Example:**

```python
numbers = [10, 20, 10, 30, 20]

print(numbers)
```

**Output:**

```text
[10, 20, 10, 30, 20]
```

এখানে `10` এবং `20` একাধিকবার রয়েছে। List এগুলো বাদ দেয় না।

---

## 7. List Is Ordered

Python List হলো একটি **Ordered Data Structure**।

এর অর্থ হলো, List-এর প্রতিটি item-এর একটি নির্দিষ্ট position থাকে এবং item-গুলো যে ক্রমে রাখা হয়, সেই ক্রম বজায় থাকে।

**Example:**

```python
fruits = ["Apple", "Banana", "Mango"]

print(fruits)
```

**Output:**

```text
['Apple', 'Banana', 'Mango']
```

এখানে:

- Apple প্রথম position-এ রয়েছে।
- Banana দ্বিতীয় position-এ রয়েছে।
- Mango তৃতীয় position-এ রয়েছে।

List-এর item access করার জন্য এই position-গুলো ব্যবহার করা যায়।

---

## 8. List Is Mutable

Python List হলো একটি **Mutable Data Structure**।

Mutable অর্থ হলো, List তৈরি হওয়ার পর এর item পরিবর্তন করা যায়।

**Example:**

```python
fruits = ["Apple", "Banana", "Mango"]

fruits[1] = "Orange"

print(fruits)
```

**Output:**

```text
['Apple', 'Orange', 'Mango']
```

এখানে:

- প্রথমে List-এর দ্বিতীয় item ছিল `"Banana"`।
- পরে সেটি পরিবর্তন করে `"Orange"` করা হয়েছে।
- তাই নতুন List-এ `"Orange"` দেখা যাচ্ছে।

---

## 9. Checking the Type of a List

Python-এর `type()` function ব্যবহার করে কোনো variable-এর data type জানা যায়।

**Example:**

```python
students = ["Masum", "Rahim", "Karim"]

print(type(students))
```

**Output:**

```text
<class 'list'>
```

এখানে Python দেখাচ্ছে যে `students` একটি List।

---

## 10. Checking the Number of Items in a List

Python-এর `len()` function ব্যবহার করে List-এর মোট item সংখ্যা বের করা যায়।

**Example:**

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print(len(fruits))
```

**Output:**

```text
4
```

এখানে List-এর মধ্যে মোট চারটি item রয়েছে।

**Important:** `len()` প্রতিটি item গণনা করে। Duplicate item থাকলেও সেটি গণনায় অন্তর্ভুক্ত হয়।

**Example:**

```python
numbers = [10, 20, 10, 30]

print(len(numbers))
```

**Output:**

```text
4
```

---

## 11. Real-Life Example of a List

ধরো, তুমি তোমার university-এর কয়েকটি course-এর নাম একটি variable-এ রাখতে চাও।

**Example:**

```python
courses = [
    "Python",
    "Data Structure",
    "Database",
    "Artificial Intelligence"
]

print(courses)
print(len(courses))
```

**Output:**

```text
['Python', 'Data Structure', 'Database', 'Artificial Intelligence']
4
```

এখানে একটি List-এর মধ্যে চারটি course-এর নাম রাখা হয়েছে।

---

## 12. Important Points to Remember

1. List হলো Python-এর একটি Built-in Data Structure।
2. List তৈরি করতে Square Brackets `[]` ব্যবহার করা হয়।
3. List-এর মধ্যে একাধিক value রাখা যায়।
4. List-এ বিভিন্ন data type রাখা যায়।
5. List Ordered।
6. List Mutable।
7. List-এ Duplicate Value রাখা যায়।
8. Empty List তৈরি করতে `[]` অথবা `list()` ব্যবহার করা যায়।
9. `type()` function দিয়ে List-এর type জানা যায়।
10. `len()` function দিয়ে List-এর item সংখ্যা জানা যায়।

---

## 13. Common Beginner Mistakes

### Mistake 1: List তৈরি করতে ভুল Brackets ব্যবহার করা

```python
numbers = (10, 20, 30)

print(type(numbers))
```

**Output:**

```text
<class 'tuple'>
```

এখানে `()` ব্যবহার করায় এটি List নয়, Tuple তৈরি হয়েছে।

সঠিক List তৈরি করতে:

```python
numbers = [10, 20, 30]

print(type(numbers))
```

**Output:**

```text
<class 'list'>
```

### Mistake 2: String এবং Variable গুলিয়ে ফেলা

```python
numbers = [10, 20, 30]

print("numbers")
```

**Output:**

```text
numbers
```

এখানে `"numbers"` একটি String, তাই List-এর value দেখাবে না।

সঠিকভাবে লিখতে হবে:

```python
numbers = [10, 20, 30]

print(numbers)
```

**Output:**

```text
[10, 20, 30]
```

### Mistake 3: List-এর Item সংখ্যা ভুল গণনা করা

```python
numbers = [10, 20, 10, 30, 20]

print(len(numbers))
```

**Output:**

```text
5
```

Duplicate value থাকলেও `len()` প্রতিটি item গণনা করে।

---

## 14. Practice Exercises

### Exercise 1

Create a List containing five student names.

**Solution:**

```python
students = ["Masum", "Rahim", "Karim", "Hasan", "Sakib"]

print(students)
```

**Output:**

```text
['Masum', 'Rahim', 'Karim', 'Hasan', 'Sakib']
```

### Exercise 2

Create a List containing five integer numbers.

**Solution:**

```python
numbers = [10, 20, 30, 40, 50]

print(numbers)
```

**Output:**

```text
[10, 20, 30, 40, 50]
```

### Exercise 3

Create a List containing different data types.

**Solution:**

```python
data = ["Python", 100, 3.5, True]

print(data)
```

**Output:**

```text
['Python', 100, 3.5, True]
```

### Exercise 4

Create an Empty List.

**Solution:**

```python
my_list = []

print(my_list)
```

**Output:**

```text
[]
```

### Exercise 5

Find the total number of items in the following List.

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]
```

**Solution:**

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print(len(fruits))
```

**Output:**

```text
4
```

### Exercise 6

What will be the output?

```python
numbers = [10, 20, 30]

numbers[0] = 100

print(numbers)
```

**Solution:**

```text
[100, 20, 30]
```

কারণ List Mutable এবং এর item পরিবর্তন করা যায়।

### Exercise 7

What will be the output?

```python
numbers = [10, 20, 10, 30, 20]

print(len(numbers))
```

**Solution:**

```text
5
```

### Exercise 8

Check the data type of the following variable.

```python
colors = ["Red", "Green", "Blue"]
```

**Solution:**

```python
colors = ["Red", "Green", "Blue"]

print(type(colors))
```

**Output:**

```text
<class 'list'>
```

---

## 15. Chapter Summary

এই topic-এ আমরা Python List-এর প্রাথমিক ধারণা শিখেছি।

- List হলো একটি Built-in Data Structure।
- Square Brackets `[]` দিয়ে List তৈরি করা হয়।
- একটি List-এর মধ্যে একাধিক value রাখা যায়।
- List-এ বিভিন্ন data type রাখা যায়।
- List Ordered এবং Mutable।
- List duplicate value support করে।
- `type()` দিয়ে data type এবং `len()` দিয়ে item সংখ্যা জানা যায়।

---

## 16. Self-Assessment Checklist

- [ ] List কী তা বুঝতে পেরেছি।
- [ ] List তৈরি করতে পারি।
- [ ] Different data types দিয়ে List তৈরি করতে পারি।
- [ ] Empty List তৈরি করতে পারি।
- [ ] List-এর duplicate value বুঝতে পেরেছি।
- [ ] List কেন Ordered তা বুঝতে পেরেছি।
- [ ] List কেন Mutable তা বুঝতে পেরেছি।
- [ ] `type()` এবং `len()` function ব্যবহার করতে পারি।
- [ ] Basic List code-এর output বলতে পারি।

---

## 17. Next Topic

**06. Creating Lists in Python**

পরবর্তী topic-এ আমরা Python-এ List তৈরি করার বিভিন্ন পদ্ধতি, Syntax এবং practical examples বিস্তারিতভাবে শিখব।