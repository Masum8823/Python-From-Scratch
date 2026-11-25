# 03. Types of Built-in Data Structures in Python

## 1. Introduction

Python-এ বিভিন্ন ধরনের Built-in Data Structures রয়েছে। এগুলোর মাধ্যমে আমরা একসাথে একাধিক value সংরক্ষণ এবং পরিচালনা করতে পারি।

Python-এর প্রধান চারটি Built-in Data Structures হলো:

1. List
2. Tuple
3. Set
4. Dictionary

প্রতিটি Data Structure-এর নিজস্ব বৈশিষ্ট্য রয়েছে। তাই কোন Data Structure ব্যবহার করব, তা নির্ভর করে আমাদের কাজের প্রয়োজনের ওপর।

---

## 2. List

**List** হলো Python-এর একটি Built-in Data Structure, যেখানে একাধিক value একটি variable-এর মধ্যে সংরক্ষণ করা যায়।

### Main Characteristics of List

- List তৈরি করতে Square Brackets `[]` ব্যবহার করা হয়।
- List Ordered, অর্থাৎ প্রতিটি value-এর নির্দিষ্ট position থাকে।
- List Mutable, অর্থাৎ এর value পরিবর্তন করা যায়।
- List-এ Duplicate Value রাখা যায়।
- List-এর value index ব্যবহার করে access করা যায়।

### Example:

```python
students = ["Masum", "Rahim", "Karim"]

print(students)
```

**Output:**

```text
['Masum', 'Rahim', 'Karim']
```

### Accessing List Items

```python
fruits = ["Apple", "Banana", "Mango"]

print(fruits[0])
print(fruits[1])
```

**Output:**

```text
Apple
Banana
```

এখানে index `0` দিয়ে প্রথম value এবং index `1` দিয়ে দ্বিতীয় value access করা হয়েছে।

### Modifying List Items

```python
fruits = ["Apple", "Banana", "Mango"]

fruits[1] = "Orange"

print(fruits)
```

**Output:**

```text
['Apple', 'Orange', 'Mango']
```

এখানে `"Banana"` পরিবর্তন করে `"Orange"` করা হয়েছে।

---

## 3. Tuple

**Tuple** হলো Python-এর একটি Built-in Data Structure, যেখানে একাধিক value একসাথে সংরক্ষণ করা যায়। তবে Tuple তৈরি হওয়ার পর এর item পরিবর্তন করা যায় না।

### Main Characteristics of Tuple

- Tuple তৈরি করতে Parentheses `()` ব্যবহার করা হয়।
- Tuple Ordered।
- Tuple Immutable, অর্থাৎ এর item পরিবর্তন করা যায় না।
- Tuple-এ Duplicate Value রাখা যায়।
- Tuple-এর value index ব্যবহার করে access করা যায়।

### Example:

```python
colors = ("Red", "Green", "Blue")

print(colors)
```

**Output:**

```text
('Red', 'Green', 'Blue')
```

### Accessing Tuple Items

```python
colors = ("Red", "Green", "Blue")

print(colors[0])
print(colors[2])
```

**Output:**

```text
Red
Blue
```

### Tuple Is Immutable

```python
numbers = (10, 20, 30)

numbers[0] = 50
```

**Output:**

```text
TypeError
```

এখানে Tuple-এর item পরিবর্তন করার চেষ্টা করা হয়েছে। কিন্তু Tuple Immutable হওয়ায় Python `TypeError` দেখাবে।

---

## 4. Set

**Set** হলো Python-এর একটি Built-in Data Structure, যেখানে unique value সংরক্ষণ করা হয়।

### Main Characteristics of Set

- Set তৈরি করতে Curly Braces `{}` ব্যবহার করা যায়।
- Set Unordered, অর্থাৎ এর item-গুলোর নির্দিষ্ট positional order নেই।
- Set Mutable।
- Set-এ Duplicate Value রাখা যায় না।
- Set-এর item index ব্যবহার করে access করা যায় না।
- Set-এর item অবশ্যই hashable হতে হয়।

### Example:

```python
numbers = {10, 20, 30, 40}

print(numbers)
```

**Output (order may vary):**

```text
{10, 20, 30, 40}
```

### Removing Duplicate Values

```python
numbers = {10, 20, 10, 30, 20}

print(numbers)
```

**Output (order may vary):**

```text
{10, 20, 30}
```

এখানে duplicate value-গুলো Set নিজে থেকেই বাদ দিয়েছে।

### Adding Items to a Set

```python
fruits = {"Apple", "Banana"}

fruits.add("Mango")

print(fruits)
```

**Output (order may vary):**

```text
{'Apple', 'Banana', 'Mango'}
```

এখানে `add()` method ব্যবহার করে নতুন item যোগ করা হয়েছে।

---

## 5. Dictionary

**Dictionary** হলো Python-এর একটি Built-in Data Structure, যেখানে data Key-Value Pair আকারে সংরক্ষণ করা হয়।

### Main Characteristics of Dictionary

- Dictionary তৈরি করতে Curly Braces `{}` ব্যবহার করা হয়।
- Data Key-Value Pair আকারে সংরক্ষণ করা হয়।
- প্রতিটি Key unique হতে হয়।
- Value duplicate হতে পারে।
- Dictionary Mutable।
- Dictionary insertion order বজায় রাখে (Python 3.7+)।
- Key hashable হতে হয়।

### Example:

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

### Accessing Dictionary Values

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}

print(student["name"])
print(student["age"])
```

**Output:**

```text
Masum
22
```

এখানে Key ব্যবহার করে Dictionary থেকে Value বের করা হয়েছে।

### Modifying Dictionary Values

```python
student = {
    "name": "Masum",
    "age": 22
}

student["age"] = 23

print(student)
```

**Output:**

```text
{'name': 'Masum', 'age': 23}
```

এখানে `"age"` Key-এর Value পরিবর্তন করা হয়েছে।

---

## 6. Comparison of Four Data Structures

| Feature | List | Tuple | Set | Dictionary |
|---|---|---|---|---|
| Syntax | `[]` | `()` | `{}` | `{key: value}` |
| Ordered | Yes | Yes | No | Yes |
| Mutable | Yes | No | Yes | Yes |
| Duplicate Items | Yes | Yes | No | Keys: No |
| Indexing | Yes | Yes | No | Key-based access |
| Main Purpose | Collection of items | Fixed collection | Unique items | Key-Value pairs |

**Important Notes:**

- Dictionary-এর Value duplicate হতে পারে।
- Set-এর item index দিয়ে access করা যায় না।
- Tuple-এর item পরিবর্তন করা যায় না।
- List-এর item পরিবর্তন করা যায়।

---

## 7. Choosing the Right Data Structure

কোন Data Structure ব্যবহার করব, তা আমাদের প্রয়োজনের ওপর নির্ভর করে।

| Requirement | Suitable Data Structure |
|---|---|
| Multiple values store করতে হবে | List |
| Values পরিবর্তন করা যাবে না | Tuple |
| শুধু unique values রাখতে হবে | Set |
| Key-Value Pair আকারে data রাখতে হবে | Dictionary |

### Example 1: List

একটি shopping cart-এ product-এর নাম রাখতে List ব্যবহার করা যায়।

```python
cart = ["Laptop", "Mouse", "Keyboard"]

print(cart)
```

**Output:**

```text
['Laptop', 'Mouse', 'Keyboard']
```

### Example 2: Tuple

একটি fixed coordinate সংরক্ষণ করতে Tuple ব্যবহার করা যায়।

```python
location = (10, 20)

print(location)
```

**Output:**

```text
(10, 20)
```

### Example 3: Set

একটি collection থেকে unique number রাখতে Set ব্যবহার করা যায়।

```python
numbers = {10, 20, 10, 30}

print(numbers)
```

**Output (order may vary):**

```text
{10, 20, 30}
```

### Example 4: Dictionary

একজন শিক্ষার্থীর বিভিন্ন information সংরক্ষণ করতে Dictionary ব্যবহার করা যায়।

```python
student = {
    "name": "Masum",
    "department": "CSE",
    "semester": 9
}

print(student)
```

**Output:**

```text
{'name': 'Masum', 'department': 'CSE', 'semester': 9}
```

---

## 8. Important Points to Remember

1. Python-এর প্রধান Built-in Data Structures হলো List, Tuple, Set এবং Dictionary।
2. List এবং Tuple Ordered।
3. List Mutable এবং Tuple Immutable।
4. Set শুধু unique items সংরক্ষণ করে।
5. Set-এর item index দিয়ে access করা যায় না।
6. Dictionary Key-Value Pair আকারে data রাখে।
7. Dictionary-এর Key unique হতে হয়।
8. Dictionary-এর Value duplicate হতে পারে।
9. Dictionary Python 3.7+ এ insertion order বজায় রাখে।
10. Set এবং Dictionary-এর Key-এর জন্য hashable value প্রয়োজন।

---

## 9. Common Beginner Mistakes

### Mistake 1: Empty Set তৈরি করতে `{}` ব্যবহার করা

```python
data = {}

print(type(data))
```

**Output:**

```text
<class 'dict'>
```

`{}` দিয়ে Empty Dictionary তৈরি হয়, Empty Set নয়।

Empty Set তৈরি করতে `set()` ব্যবহার করতে হয়।

```python
data = set()

print(type(data))
```

**Output:**

```text
<class 'set'>
```

### Mistake 2: Tuple-কে List মনে করে পরিবর্তন করার চেষ্টা করা

```python
numbers = (10, 20, 30)

numbers[1] = 50
```

**Output:**

```text
TypeError
```

কারণ Tuple Immutable।

### Mistake 3: Set-এর Item Index দিয়ে Access করা

```python
numbers = {10, 20, 30}

print(numbers[0])
```

**Output:**

```text
TypeError
```

কারণ Set indexing support করে না।

### Mistake 4: Dictionary-তে Duplicate Key ব্যবহার করা

```python
student = {
    "name": "Masum",
    "name": "Rahim"
}

print(student)
```

**Output:**

```text
{'name': 'Rahim'}
```

একই Key একাধিকবার দিলে পরের Value আগের Value-কে replace করে।

---

## 10. Practice Exercises

### Exercise 1

Python-এর চারটি Built-in Data Structures-এর নাম লেখো।

**Solution:**

1. List
2. Tuple
3. Set
4. Dictionary

### Exercise 2

নিচের কোন Data Structure Immutable?

**Solution:**

```text
Tuple
```

### Exercise 3

নিচের code-এর output কী হবে?

```python
numbers = [10, 20, 30]
numbers[1] = 50

print(numbers)
```

**Solution:**

```text
[10, 50, 30]
```

### Exercise 4

নিচের code-এর output কী হবে?

```python
numbers = {10, 20, 10, 30}

print(len(numbers))
```

**Solution:**

```text
3
```

কারণ Set duplicate value রাখে না।

### Exercise 5

নিচের code-এর output কী হবে?

```python
student = {
    "name": "Masum",
    "age": 22
}

print(student["name"])
```

**Solution:**

```text
Masum
```

### Exercise 6

Empty Set তৈরি করার সঠিক উপায় কোনটি?

**Solution:**

```python
my_set = set()
```

### Exercise 7

নিচের code-এর output কী হবে?

```python
colors = ("Red", "Green", "Blue")

print(colors[1])
```

**Solution:**

```text
Green
```

### Exercise 8

একটি collection থেকে duplicate value বাদ দিতে কোন Data Structure ব্যবহার করবে?

**Solution:**

```text
Set
```

---

## 11. Chapter Summary

এই topic-এ আমরা Python-এর চারটি প্রধান Built-in Data Structures সম্পর্কে জেনেছি।

- **List:** Ordered এবং Mutable collection।
- **Tuple:** Ordered এবং Immutable collection।
- **Set:** Unique items সংরক্ষণ করে এবং indexing support করে না।
- **Dictionary:** Key-Value Pair আকারে data সংরক্ষণ করে।

প্রতিটি Data Structure-এর আলাদা বৈশিষ্ট্য রয়েছে। তাই program-এর প্রয়োজন অনুযায়ী সঠিক Data Structure নির্বাচন করা গুরুত্বপূর্ণ।

---

## 12. Self-Assessment Checklist

- [ ] List-এর basic characteristics বুঝতে পেরেছি।
- [ ] Tuple-এর basic characteristics বুঝতে পেরেছি।
- [ ] Set-এর basic characteristics বুঝতে পেরেছি।
- [ ] Dictionary-এর basic characteristics বুঝতে পেরেছি।
- [ ] চারটি Data Structure-এর পার্থক্য বলতে পারি।
- [ ] কোন কাজে কোন Data Structure ব্যবহার করতে হয় তা বুঝেছি।
- [ ] Basic code দেখে output বলতে পারি।

---

## 13. Next Topic

**04. List, Tuple, Set and Dictionary Comparison**

পরবর্তী topic-এ আমরা চারটি Data Structure-এর মধ্যে পার্থক্যগুলো আরও সুন্দরভাবে table এবং practical example-এর মাধ্যমে শিখব।