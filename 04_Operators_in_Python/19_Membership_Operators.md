# 19. Membership Operators in Python

## 1. Introduction to Membership Operators

Python-এ **Membership Operators** ব্যবহার করে কোনো Element একটি Collection-এর মধ্যে আছে কি না পরীক্ষা করা হয়।

Python-এ দুটি Membership Operator রয়েছে:

| Operator | অর্থ |
|---|---|
| `in` | কোনো Element-এর উপস্থিতি পরীক্ষা করে |
| `not in` | কোনো Element-এর অনুপস্থিতি পরীক্ষা করে |

এই Operator-গুলো Result হিসেবে `True` অথবা `False` Return করে।

### Example

```python
numbers = [10, 20, 30, 40]

print(20 in numbers)
print(50 in numbers)
```

Output:

```text
True
False
```

ব্যাখ্যা:

- `20` List-এর মধ্যে আছে, তাই Result `True`।
- `50` List-এর মধ্যে নেই, তাই Result `False`।

**মনে রাখবে:** `in` মানে আছে কি না এবং `not in` মানে নেই কি না।

---

## 2. The `in` Operator

`in` Operator পরীক্ষা করে কোনো Element একটি Collection-এর মধ্যে রয়েছে কি না।

### Example 1: List

```python
fruits = ["apple", "banana", "mango"]

print("apple" in fruits)
print("orange" in fruits)
```

Output:

```text
True
False
```

### Example 2: Tuple

```python
numbers = (10, 20, 30)

print(20 in numbers)
print(40 in numbers)
```

Output:

```text
True
False
```

### Example 3: Set

```python
colors = {"red", "green", "blue"}

print("green" in colors)
print("yellow" in colors)
```

Output:

```text
True
False
```

### Example 4: String

```python
text = "Hello Python"

print("Python" in text)
print("Java" in text)
```

Output:

```text
True
False
```

String-এর ক্ষেত্রে `in` পরীক্ষা করে একটি Substring অন্য String-এর মধ্যে আছে কি না।

---

## 3. The `not in` Operator

`not in` Operator পরীক্ষা করে কোনো Element একটি Collection-এর মধ্যে নেই কি না।

### Example 1: List

```python
numbers = [10, 20, 30]

print(40 not in numbers)
print(20 not in numbers)
```

Output:

```text
True
False
```

ব্যাখ্যা:

- `40` List-এ নেই, তাই `40 not in numbers` হলো `True`।
- `20` List-এ আছে, তাই `20 not in numbers` হলো `False`।

### Example 2: String

```python
text = "Python Programming"

print("Java" not in text)
print("Python" not in text)
```

Output:

```text
True
False
```

### Example 3: Tuple

```python
subjects = ("CSE", "EEE", "BBA")

print("MIS" not in subjects)
print("CSE" not in subjects)
```

Output:

```text
True
False
```

---

## 4. Membership Operators with Strings

String-এর ক্ষেত্রে Membership Operator দিয়ে কোনো Character বা Substring খুঁজে দেখা যায়।

### Example 1: Checking a Character

```python
text = "Python"

print("P" in text)
print("p" in text)
```

Output:

```text
True
False
```

Python Case-Sensitive। তাই বড় হাতের `P` এবং ছোট হাতের `p` আলাদা Character।

### Example 2: Checking a Substring

```python
text = "I am learning Python"

print("learning" in text)
print("Java" in text)
```

Output:

```text
True
False
```

### Example 3: Empty String

```python
text = "Python"

print("" in text)
print("" not in text)
```

Output:

```text
True
False
```

Python-এ Empty String `""` যেকোনো String-এর মধ্যে পাওয়া যায়।

### Example 4: Case Sensitivity

```python
text = "Hello World"

print("Hello" in text)
print("hello" in text)
```

Output:

```text
True
False
```

দ্বিতীয় Result `False`, কারণ `"hello"` এবং `"Hello"`-এর Case আলাদা।

Case-Insensitive Search প্রয়োজন হলে:

```python
text = "Hello World"

print("hello".lower() in text.lower())
```

Output:

```text
True
```

এখানে উভয় String-কে ছোট হাতের অক্ষরে রূপান্তর করে পরীক্ষা করা হয়েছে।

---

## 5. Membership Operators with Lists

List-এর মধ্যে কোনো Element আছে কি না পরীক্ষা করার জন্য `in` এবং `not in` বহুল ব্যবহৃত হয়।

### Example 1: Checking a Number

```python
numbers = [5, 10, 15, 20]

if 10 in numbers:
    print("Number found.")
```

Output:

```text
Number found.
```

### Example 2: Checking a Name

```python
students = ["Masum", "Ritu", "Rahim"]

name = "Ritu"

if name in students:
    print("Student exists.")
else:
    print("Student not found.")
```

Output:

```text
Student exists.
```

### Example 3: Preventing Duplicate Entries

```python
students = ["Masum", "Ritu"]

new_student = "Ritu"

if new_student not in students:
    students.append(new_student)

print(students)
```

Output:

```text
['Masum', 'Ritu']
```

এখানে `"Ritu"` আগে থেকেই List-এ আছে। তাই নতুন করে যোগ করা হয়নি।

**ব্যবহার:** Student List, Shopping Cart, Registration System এবং অন্যান্য Program-এ Membership Operator কাজে লাগে।

---

## 6. Membership Operators with Tuples

Tuple-এর ক্ষেত্রেও `in` এবং `not in` ব্যবহার করা যায়।

### Example

```python
days = ("Saturday", "Sunday", "Monday")

print("Sunday" in days)
print("Friday" not in days)
```

Output:

```text
True
True
```

Tuple-এর Element খুঁজে দেখতে Membership Operator ব্যবহার করা সহজ ও কার্যকর।

---

## 7. Membership Operators with Sets

Set-এর মধ্যে কোনো Element আছে কি না পরীক্ষা করতে Membership Operator ব্যবহার করা যায়।

### Example

```python
numbers = {10, 20, 30, 40}

print(20 in numbers)
print(50 not in numbers)
```

Output:

```text
True
True
```

Set-এর Membership Check সাধারণত গড়ে \(O(1)\) সময় নিতে পারে।

অন্যদিকে List-এ Element খুঁজতে সাধারণত \(O(n)\) সময় লাগতে পারে, যেখানে \(n\) হলো Element-এর সংখ্যা।

এই জটিলতা গড়পড়তা পরিস্থিতির জন্য; নির্দিষ্ট পরিস্থিতিতে Performance ভিন্ন হতে পারে।

---

## 8. Membership Operators with Dictionaries

Dictionary-এর ক্ষেত্রে Membership Operator ব্যবহার করলে সাধারণত **Key** পরীক্ষা করা হয়, Value নয়।

এটি খুব গুরুত্বপূর্ণ একটি নিয়ম।

### Example 1: Checking a Key

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}

print("name" in student)
print("age" in student)
print("department" in student)
```

Output:

```text
True
True
False
```

### Example 2: Checking a Value

```python
student = {
    "name": "Masum",
    "age": 22
}

print("Masum" in student)
print("Masum" in student.values())
```

Output:

```text
False
True
```

ব্যাখ্যা:

- `"Masum" in student` Dictionary-এর Key খোঁজে।
- `"Masum" in student.values()` Dictionary-এর Value খোঁজে।

### Example 3: Checking a Specific Key

```python
student = {
    "name": "Masum",
    "age": 22
}

if "age" in student:
    print("Age:", student["age"])
```

Output:

```text
Age: 22
```

Key আছে কি না পরীক্ষা করার পর Value Access করলে Missing Key-সংক্রান্ত Error এড়ানো যায়।

---

## 9. Membership Operators with Dictionary Keys and Values

Dictionary-তে Key, Value এবং Key-Value Pair পরীক্ষা করার পদ্ধতি আলাদা।

```python
student = {
    "name": "Masum",
    "age": 22
}

print("name" in student.keys())
print(22 in student.values())
print(("age", 22) in student.items())
```

Output:

```text
True
True
True
```

ব্যাখ্যা:

- `student.keys()` Key-গুলোর Collection দেয়।
- `student.values()` Value-গুলোর Collection দেয়।
- `student.items()` Key-Value Pair দেয়।

সাধারণ Key Check-এর জন্য শুধু `in student` লিখলেই হয়। আলাদাভাবে `.keys()` ব্যবহার করা বাধ্যতামূলক নয়।

---

## 10. Membership Operators in Conditional Statements

`if` Statement-এর সঙ্গে Membership Operator ব্যবহার করে নির্দিষ্ট Condition অনুযায়ী কাজ করা যায়।

### Example 1: Login Role Check

```python
allowed_roles = ["admin", "teacher", "student"]

role = "teacher"

if role in allowed_roles:
    print("Access allowed.")
else:
    print("Access denied.")
```

Output:

```text
Access allowed.
```

### Example 2: Checking a Course

```python
courses = ["Python", "AI", "MIS"]

course = "AI"

if course not in courses:
    print("Course not found.")
else:
    print("Course available.")
```

Output:

```text
Course available.
```

### Example 3: Checking User Input

```python
answer = "yes"

if answer.lower() in ("yes", "y"):
    print("Confirmed.")
else:
    print("Not confirmed.")
```

Output:

```text
Confirmed.
```

এখানে `lower()` ব্যবহার করায় `"YES"`-এর মতো Input-ও গ্রহণ করা সম্ভব হবে।

---

## 11. Membership Operators with Numbers and Types

Membership Operator দিয়ে কোনো Number একটি List বা Set-এর মধ্যে আছে কি না পরীক্ষা করা যায়। তবে Data Type ও Value-এর সামঞ্জস্য খেয়াল রাখতে হবে।

### Example 1

```python
numbers = [10, 20, 30]

print(10 in numbers)
print("10" in numbers)
```

Output:

```text
True
False
```

ব্যাখ্যা:

- `10` হলো Integer।
- `"10"` হলো String।
- Integer `10` এবং String `"10"` একই Value Type নয়; তাই দ্বিতীয় Check False।

### Example 2: Boolean and Integer

```python
numbers = [1, 2, 3]

print(True in numbers)
```

Output:

```text
True
```

Python-এ `bool` হলো `int`-এর একটি Subclass এবং `True` সংখ্যাগতভাবে `1`-এর সমান। তাই এই Membership Check `True` হয়।

এই ধরনের আচরণ মাথায় রাখবে, বিশেষ করে যখন Collection-এর Element-এর Data Type গুরুত্বপূর্ণ।

---

## 12. Membership Operators with `range()`

`range()` দিয়ে তৈরি Number Sequence-এর মধ্যে কোনো Integer আছে কি না, তা `in` দিয়ে পরীক্ষা করা যায়।

### Example 1

```python
numbers = range(1, 6)

print(3 in numbers)
print(6 in numbers)
```

Output:

```text
True
False
```

`range(1, 6)` হলো `1, 2, 3, 4, 5`। এখানে `6` অন্তর্ভুক্ত নয়।

### Example 2: Even Numbers

```python
even_numbers = range(2, 11, 2)

print(6 in even_numbers)
print(7 in even_numbers)
```

Output:

```text
True
False
```

এখানে Sequence-টি হলো `2, 4, 6, 8, 10`।

Integer-এর ক্ষেত্রে `range`-এ Membership Check সাধারণত খুব দ্রুত করা যায়, এমনকি Range বড় হলেও।

---

## 13. Common Mistakes

### Mistake 1: Checking a Dictionary Value as a Key

ভুল ধারণা:

```python
student = {"name": "Masum"}

print("Masum" in student)
```

Output:

```text
False
```

কারণ `"Masum"` Value, Key নয়।

সঠিক:

```python
print("Masum" in student.values())
```

Output:

```text
True
```

### Mistake 2: Ignoring Case Sensitivity

```python
text = "Python"

print("python" in text)
```

Output:

```text
False
```

সঠিক:

```python
print("python".lower() in text.lower())
```

Output:

```text
True
```

### Mistake 3: Confusing `in` and `not in`

```python
numbers = [1, 2, 3]

print(2 in numbers)
print(2 not in numbers)
```

Output:

```text
True
False
```

একটি Element থাকলে `in` True এবং `not in` False হয়।

### Mistake 4: Searching for an Entire Element in a String

```python
text = "Python Programming"

print("Python" in text)
```

Output:

```text
True
```

String-এর ক্ষেত্রে Membership Operator Substring খোঁজে। কিন্তু List-এর ক্ষেত্রে এটি List-এর Element-এর সঙ্গে তুলনা করে।

```python
words = ["Python", "Programming"]

print("Python" in words)
print("Pyt" in words)
```

Output:

```text
True
False
```

`"Pyt"` List-এর কোনো Element নয়, যদিও `"Python"`-এর অংশ।

### Mistake 5: Assuming All Collections Have the Same Performance

List-এ Search সাধারণত Linear Search-এর মতো কাজ করে। Set ও Dictionary-তে Membership Check সাধারণত Hashing-এর কারণে দ্রুত হয়।

তাই অনেক Search করতে হলে উপযুক্ত Data Structure বেছে নেওয়া গুরুত্বপূর্ণ।

---

## 14. Practice Exercises

### Basic Level

1. `[10, 20, 30]` List-এ `20` আছে কি না পরীক্ষা করো।
2. `"Python"` String-এর মধ্যে `"th"` আছে কি না পরীক্ষা করো।
3. `not in` ব্যবহার করে `"Java"` String-এ নেই কি না পরীক্ষা করো।
4. Tuple `("CSE", "EEE", "BBA")`-তে `"CSE"` আছে কি না পরীক্ষা করো।
5. Set `{1, 2, 3}`-তে `4` নেই কি না পরীক্ষা করো।

### Intermediate Level

6. Dictionary-তে `"name"` Key আছে কি না পরীক্ষা করো।
7. Dictionary-এর Value-তে `"Masum"` আছে কি না পরীক্ষা করো।
8. List-এ কোনো Student আগে থেকেই থাকলে তাকে আবার যোগ করা বন্ধ করো।
9. `range(1, 11)`-এ `10` আছে কি না পরীক্ষা করো।
10. Case-Insensitive String Search তৈরি করো।

### Output Prediction

```python
numbers = [10, 20, 30]

print(20 in numbers)
print(40 not in numbers)

text = "Python"

print("py" in text)
print("th" in text)

student = {"name": "Masum", "age": 22}

print("Masum" in student)
print(22 in student.values())
```

### Answers

```text
True
True
False
True
False
True
```

ব্যাখ্যা:

- `20` List-এ আছে।
- `40` List-এ নেই।
- `"py"` String-এ নেই, কারণ String Case-Sensitive।
- `"th"` String-এ আছে।
- `"Masum"` Dictionary-এর Value, Key নয়।
- `22` Dictionary-এর Value হিসেবে আছে।

---

## 15. Chapter Summary

- Membership Operators হলো `in` এবং `not in`।
- `in` পরীক্ষা করে কোনো Element আছে কি না।
- `not in` পরীক্ষা করে কোনো Element নেই কি না।
- List, Tuple, Set, String, Dictionary এবং `range()`-এ এগুলো ব্যবহার করা যায়।
- String-এর ক্ষেত্রে Substring বা Character খোঁজা যায়।
- Dictionary-তে সরাসরি `in` ব্যবহার করলে Key পরীক্ষা করা হয়।
- Dictionary-এর Value পরীক্ষা করতে `.values()` ব্যবহার করা যায়।
- Dictionary-এর Key-Value Pair পরীক্ষা করতে `.items()` ব্যবহার করা যায়।
- Python Case-Sensitive হওয়ায় `"Python"` এবং `"python"` আলাদা।
- List, Set ও Dictionary-তে Membership Check-এর Performance আলাদা হতে পারে।

## 16. Self-Assessment Checklist

- [ ] `in` ও `not in`-এর কাজ বুঝি।
- [ ] String-এর মধ্যে Substring খুঁজতে পারি।
- [ ] List, Tuple এবং Set-এ Membership Check করতে পারি।
- [ ] Dictionary-এর Key ও Value আলাদাভাবে পরীক্ষা করতে পারি।
- [ ] `range()`-এ Membership Check করতে পারি।
- [ ] Case Sensitivity-এর প্রভাব বুঝি।
- [ ] Membership Operator ব্যবহার করে Conditional Program লিখতে পারি।
- [ ] Output Prediction Exercise সমাধান করতে পারি।

**Next Topic:** `20_Identity_vs_Equality.md`