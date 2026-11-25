# 06. Creating Lists in Python

## 1. Introduction

Python-এ List তৈরি করার জন্য সাধারণত Square Brackets `[]` ব্যবহার করা হয়।

একটি List-এর মধ্যে এক বা একাধিক value রাখা যায়। এমনকি বিভিন্ন data type-এর value-ও একই List-এ রাখা সম্ভব।

**Example:**

```python
students = ["Masum", "Rahim", "Karim"]

print(students)
```

**Output:**

```text
['Masum', 'Rahim', 'Karim']
```

এই topic-এ আমরা Python-এ List তৈরি করার বিভিন্ন পদ্ধতি শিখব।

---

## 2. Creating a List Using Square Brackets

List তৈরি করার সবচেয়ে সহজ এবং সাধারণ পদ্ধতি হলো Square Brackets `[]` ব্যবহার করা।

**Syntax:**

```python
list_name = [item1, item2, item3]
```

এখানে:

- `list_name` হলো List-এর নাম।
- Square Brackets `[]` List তৈরি করে।
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

## 3. Creating a List with Different Data Types

Python List-এর মধ্যে বিভিন্ন ধরনের data একসাথে রাখা যায়।

### 3.1 List of Strings

```python
names = ["Masum", "Rahim", "Karim"]

print(names)
```

**Output:**

```text
['Masum', 'Rahim', 'Karim']
```

### 3.2 List of Integers

```python
numbers = [10, 20, 30, 40, 50]

print(numbers)
```

**Output:**

```text
[10, 20, 30, 40, 50]
```

### 3.3 List of Floats

```python
prices = [10.5, 20.75, 30.25]

print(prices)
```

**Output:**

```text
[10.5, 20.75, 30.25]
```

### 3.4 List of Booleans

```python
results = [True, False, True]

print(results)
```

**Output:**

```text
[True, False, True]
```

### 3.5 Mixed Data Types

```python
data = ["Masum", 22, 3.95, True]

print(data)
```

**Output:**

```text
['Masum', 22, 3.95, True]
```

এখানে String, Integer, Float এবং Boolean একই List-এ রাখা হয়েছে।

---

## 4. Creating an Empty List

কখনো কখনো শুরুতে কোনো value ছাড়াই List তৈরি করার প্রয়োজন হয়।

এ ধরনের List-কে **Empty List** বলা হয়।

Python-এ Empty List তৈরি করার দুটি সাধারণ পদ্ধতি রয়েছে।

### Method 1: Using Empty Square Brackets

```python
students = []

print(students)
```

**Output:**

```text
[]
```

### Method 2: Using the list() Function

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

## 5. Creating a List Using the list() Constructor

Python-এর `list()` হলো একটি Built-in Constructor, যা ব্যবহার করে List তৈরি করা যায়।

এটি কোনো Iterable Object-এর item-গুলো নিয়ে একটি নতুন List তৈরি করে।

Iterable হলো এমন object, যার item-গুলোর ওপর একে একে loop চালানো যায়।

### Example 1: Converting a Tuple into a List

```python
numbers = (10, 20, 30)

my_list = list(numbers)

print(my_list)
```

**Output:**

```text
[10, 20, 30]
```

এখানে Tuple-কে List-এ convert করা হয়েছে।

### Example 2: Converting a String into a List

```python
text = "Python"

letters = list(text)

print(letters)
```

**Output:**

```text
['P', 'y', 't', 'h', 'o', 'n']
```

এখানে String-এর প্রতিটি character আলাদা List item হিসেবে সংরক্ষণ করা হয়েছে।

### Example 3: Converting a Set into a List

```python
numbers = {10, 20, 30}

my_list = list(numbers)

print(my_list)
```

**Possible Output:**

```text
[10, 20, 30]
```

Set-এর নির্দিষ্ট positional order নেই। তাই List-এ item-গুলোর order নির্দিষ্টভাবে ধরে নেওয়া যাবে না।

---

## 6. Creating a List Using the range() Function

Python-এর `range()` function ব্যবহার করে নির্দিষ্ট সংখ্যার sequence তৈরি করা যায়।

এই sequence-কে `list()` দিয়ে List-এ convert করা সম্ভব।

**Example 1:**

```python
numbers = list(range(5))

print(numbers)
```

**Output:**

```text
[0, 1, 2, 3, 4]
```

এখানে:

- `range(5)` তৈরি করে 0 থেকে 4 পর্যন্ত sequence।
- `list()` sequence-টিকে List-এ convert করে।

### Example 2: Starting from a Specific Number

```python
numbers = list(range(1, 6))

print(numbers)
```

**Output:**

```text
[1, 2, 3, 4, 5]
```

এখানে:

- `1` হলো Starting Value।
- `6` হলো Stopping Value।
- Stopping Value অন্তর্ভুক্ত হয় না।

### Example 3: Using Step

```python
numbers = list(range(2, 11, 2))

print(numbers)
```

**Output:**

```text
[2, 4, 6, 8, 10]
```

এখানে:

- `2` হলো Starting Value।
- `11` হলো Stopping Value।
- `2` হলো Step।

প্রতিবার 2 করে বাড়িয়ে নতুন value তৈরি করা হয়েছে।

---

## 7. Creating a List Using List Comprehension

**List Comprehension** হলো Python-এ List তৈরি করার একটি সংক্ষিপ্ত এবং সুন্দর পদ্ধতি।

এটি ব্যবহার করে কম code লিখে নতুন List তৈরি করা যায়।

**Basic Syntax:**

```python
new_list = [expression for item in iterable]
```

এখানে:

- `expression` হলো প্রতিটি item-এর জন্য তৈরি হওয়া value।
- `item` হলো প্রতিবার পাওয়া element।
- `iterable` হলো যে collection থেকে item নেওয়া হবে।

### Example 1: Creating Numbers

```python
numbers = [x for x in range(5)]

print(numbers)
```

**Output:**

```text
[0, 1, 2, 3, 4]
```

### Example 2: Creating Squares

```python
squares = [x * x for x in range(1, 6)]

print(squares)
```

**Output:**

```text
[1, 4, 9, 16, 25]
```

এখানে প্রতিটি সংখ্যাকে নিজের সাথে গুণ করে নতুন List তৈরি করা হয়েছে।

### Example 3: Creating a List with a Condition

```python
numbers = [x for x in range(1, 11) if x % 2 == 0]

print(numbers)
```

**Output:**

```text
[2, 4, 6, 8, 10]
```

এখানে শুধু যেসব সংখ্যা 2 দিয়ে বিভাজ্য, সেগুলো List-এ রাখা হয়েছে।

**Note:** List Comprehension নিয়ে পরবর্তী advanced topic-এ আরও বিস্তারিত আলোচনা করা হবে।

---

## 8. Creating a Nested List

একটি List-এর মধ্যে অন্য List রাখলে তাকে **Nested List** বলা হয়।

**Example:**

```python
students = [
    ["Masum", 22],
    ["Rahim", 23],
    ["Karim", 21]
]

print(students)
```

**Output:**

```text
[['Masum', 22], ['Rahim', 23], ['Karim', 21]]
```

এখানে একটি List-এর মধ্যে আরও তিনটি List রয়েছে।

Nested List ব্যবহার করে related data একসাথে organize করা যায়।

---

## 9. Assigning a List to a Variable

একটি List তৈরি করে সেটিকে variable-এর মধ্যে রাখা হয়।

```python
fruits = ["Apple", "Banana", "Mango"]

print(fruits)
```

**Output:**

```text
['Apple', 'Banana', 'Mango']
```

এখানে `fruits` variable-টি List object-কে refer করছে।

---

## 10. Creating Multiple Lists

একই program-এ প্রয়োজন অনুযায়ী একাধিক List তৈরি করা যায়।

**Example:**

```python
students = ["Masum", "Rahim", "Karim"]

marks = [85, 90, 78]

subjects = ["Python", "Java", "C++"]

print(students)
print(marks)
print(subjects)
```

**Output:**

```text
['Masum', 'Rahim', 'Karim']
[85, 90, 78]
['Python', 'Java', 'C++']
```

এখানে তিনটি আলাদা List তৈরি করা হয়েছে।

প্রতিটি List আলাদা ধরনের information সংরক্ষণ করছে।

---

## 11. Checking the Type of a List

`type()` function ব্যবহার করে কোনো variable-এর data type পরীক্ষা করা যায়।

**Example:**

```python
numbers = [10, 20, 30]

print(type(numbers))
```

**Output:**

```text
<class 'list'>
```

এখানে Python দেখাচ্ছে যে `numbers` একটি List।

---

## 12. Checking the Length of a List

`len()` function ব্যবহার করে List-এর মোট item সংখ্যা বের করা যায়।

**Example:**

```python
fruits = ["Apple", "Banana", "Mango"]

print(len(fruits))
```

**Output:**

```text
3
```

এখানে List-এর মধ্যে মোট তিনটি item রয়েছে।

---

## 13. Important Points to Remember

1. List তৈরি করতে Square Brackets `[]` ব্যবহার করা হয়।
2. `list()` constructor দিয়েও List তৈরি করা যায়।
3. Empty List তৈরি করতে `[]` অথবা `list()` ব্যবহার করা যায়।
4. List-এর মধ্যে বিভিন্ন data type রাখা যায়।
5. `list()` দিয়ে Tuple, String এবং অন্যান্য Iterable থেকে List তৈরি করা যায়।
6. `range()` এবং `list()` একসাথে ব্যবহার করে সংখ্যার List তৈরি করা যায়।
7. List Comprehension দিয়ে সংক্ষিপ্তভাবে নতুন List তৈরি করা যায়।
8. Nested List-এর মধ্যে অন্য List রাখা যায়।
9. `type()` দিয়ে List-এর type পরীক্ষা করা যায়।
10. `len()` দিয়ে List-এর item সংখ্যা বের করা যায়।

---

## 14. Common Beginner Mistakes

### Mistake 1: Empty List এবং Empty Dictionary গুলিয়ে ফেলা

```python
data = {}

print(type(data))
```

**Output:**

```text
<class 'dict'>
```

`{}` দিয়ে Empty Dictionary তৈরি হয়, Empty List নয়।

Empty List তৈরি করতে:

```python
data = []

print(type(data))
```

**Output:**

```text
<class 'list'>
```

### Mistake 2: list() এবং list Variable Name গুলিয়ে ফেলা

```python
numbers = list((10, 20, 30))

print(numbers)
```

**Output:**

```text
[10, 20, 30]
```

এখানে `list()` একটি Built-in Constructor।

তাই `list` নামটি variable হিসেবে ব্যবহার না করাই ভালো।

### Mistake 3: range() সরাসরি List মনে করা

```python
numbers = range(5)

print(numbers)
```

**Output:**

```text
range(0, 5)
```

এটি List নয়, একটি range object।

List তৈরি করতে:

```python
numbers = list(range(5))

print(numbers)
```

**Output:**

```text
[0, 1, 2, 3, 4]
```

### Mistake 4: range() এর Stopping Value অন্তর্ভুক্ত মনে করা

```python
numbers = list(range(1, 5))

print(numbers)
```

**Output:**

```text
[1, 2, 3, 4]
```

এখানে `5` অন্তর্ভুক্ত হয়নি।

### Mistake 5: String থেকে List তৈরি করলে পুরো String একটি Item হবে মনে করা

```python
text = "Python"

letters = list(text)

print(letters)
```

**Output:**

```text
['P', 'y', 't', 'h', 'o', 'n']
```

এখানে প্রতিটি character আলাদা item হয়েছে।

---

## 15. Practice Exercises

### Exercise 1

Create a List containing five fruits.

**Solution:**

```python
fruits = ["Apple", "Banana", "Mango", "Orange", "Grapes"]

print(fruits)
```

**Output:**

```text
['Apple', 'Banana', 'Mango', 'Orange', 'Grapes']
```

### Exercise 2

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

### Exercise 3

Create a List using the `list()` constructor.

**Solution:**

```python
numbers = list((10, 20, 30))

print(numbers)
```

**Output:**

```text
[10, 20, 30]
```

### Exercise 4

Create a List containing numbers from 1 to 10 using `range()`.

**Solution:**

```python
numbers = list(range(1, 11))

print(numbers)
```

**Output:**

```text
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

### Exercise 5

Create a List containing even numbers from 2 to 10 using `range()`.

**Solution:**

```python
numbers = list(range(2, 11, 2))

print(numbers)
```

**Output:**

```text
[2, 4, 6, 8, 10]
```

### Exercise 6

Create a List containing the squares of numbers from 1 to 5 using List Comprehension.

**Solution:**

```python
squares = [x * x for x in range(1, 6)]

print(squares)
```

**Output:**

```text
[1, 4, 9, 16, 25]
```

### Exercise 7

Convert the String `"Python"` into a List.

**Solution:**

```python
text = "Python"

letters = list(text)

print(letters)
```

**Output:**

```text
['P', 'y', 't', 'h', 'o', 'n']
```

### Exercise 8

Create a Nested List containing three students' names and ages.

**Solution:**

```python
students = [
    ["Masum", 22],
    ["Rahim", 23],
    ["Karim", 21]
]

print(students)
```

**Output:**

```text
[['Masum', 22], ['Rahim', 23], ['Karim', 21]]
```

### Exercise 9

Find the total number of items in the following List.

```python
numbers = [10, 20, 30, 40, 50]
```

**Solution:**

```python
numbers = [10, 20, 30, 40, 50]

print(len(numbers))
```

**Output:**

```text
5
```

### Exercise 10

What will be the output?

```python
numbers = list(range(1, 8, 2))

print(numbers)
```

**Solution:**

```text
[1, 3, 5, 7]
```

---

## 16. Chapter Summary

এই topic-এ আমরা Python-এ List তৈরি করার বিভিন্ন পদ্ধতি শিখেছি।

- Square Brackets `[]` ব্যবহার করে List তৈরি করা যায়।
- `list()` constructor ব্যবহার করে List তৈরি করা যায়।
- Empty List তৈরি করতে `[]` অথবা `list()` ব্যবহার করা যায়।
- String, Tuple এবং অন্যান্য Iterable থেকে List তৈরি করা যায়।
- `range()` ব্যবহার করে সংখ্যার List তৈরি করা যায়।
- List Comprehension দিয়ে সংক্ষিপ্তভাবে List তৈরি করা যায়।
- Nested List-এর মধ্যে অন্য List রাখা যায়।

---

## 17. Self-Assessment Checklist

- [ ] Square Brackets ব্যবহার করে List তৈরি করতে পারি।
- [ ] Different Data Types দিয়ে List তৈরি করতে পারি।
- [ ] Empty List তৈরি করতে পারি।
- [ ] `list()` constructor ব্যবহার করতে পারি।
- [ ] String থেকে List তৈরি করতে পারি।
- [ ] Tuple থেকে List তৈরি করতে পারি।
- [ ] `range()` ব্যবহার করে List তৈরি করতে পারি।
- [ ] List Comprehension-এর basic syntax বুঝেছি।
- [ ] Nested List তৈরি করতে পারি।
- [ ] `type()` এবং `len()` ব্যবহার করতে পারি।

---

## 18. Next Topic

**07. Accessing List Elements Using Indexing**

পরবর্তী topic-এ আমরা শিখব কীভাবে Index ব্যবহার করে List-এর নির্দিষ্ট item access করতে হয়।