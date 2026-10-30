# 32. Data Types Practice Exercises in Python

## 1. Introduction

এই ফাইলে Python Data Types Chapter-এর গুরুত্বপূর্ণ বিষয়গুলো Practice করা হবে।

Practice-এর প্রধান Topics:

- Built-in Data Types
- Type Checking
- Numeric Types
- String, Boolean এবং None
- List, Tuple, Set এবং Dictionary
- Type Conversion
- Mutable and Immutable Objects
- Shallow Copy and Deep Copy
- Type Compatibility
- Common Errors
- Data Type Selection

**Practice Guideline:** প্রথমে নিজে Code লেখার চেষ্টা করবে। এরপর Expected Output-এর সঙ্গে তোমার Output মিলিয়ে দেখবে।

---

## 2. Level 1: Basic Data Types

### Exercise 1: Identify Data Types

নিচের প্রতিটি Value-এর Data Type বের করো।

```python
a = 100
b = 25.5
c = "Python"
d = True
e = None
f = [1, 2, 3]
g = (10, 20)
h = {1, 2, 3}
i = {"name": "Masum"}
j = 2 + 3j

print(type(a))
print(type(b))
print(type(c))
print(type(d))
print(type(e))
print(type(f))
print(type(g))
print(type(h))
print(type(i))
print(type(j))
```

**Task:** প্রতিটি Output কোন Type নির্দেশ করে, তা ব্যাখ্যা করো।

### Exercise 2: Check Data Types

`type()` ব্যবহার করে নিচের Value-গুলোর Type পরীক্ষা করো:

- `50`
- `5.75`
- `"Hello"`
- `False`
- `[10, 20]`

এরপর `isinstance()` ব্যবহার করে একই ধরনের Check করো।

### Exercise 3: Integer and Float

দুটি Number নিয়ে নিচের Operation-গুলো করো:

1. Addition
2. Subtraction
3. Multiplication
4. Division
5. Floor Division
6. Modulus

Example:

```python
a = 17
b = 5

print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a // b)
print(a % b)
```

**Task:** প্রতিটি Output এবং Result-এর Data Type ব্যাখ্যা করো।

### Exercise 4: Boolean Values

নিচের Expression-গুলোর Output অনুমান করো।

```python
print(bool(0))
print(bool(1))
print(bool(""))
print(bool("Python"))
print(bool([]))
print(bool([0]))
print(bool(None))
```

**Task:** কোন Value-গুলো Falsy এবং কোনগুলো Truthy, তা লেখো।

### Exercise 5: None Checking

নিচের Code সম্পূর্ণ করো, যাতে `result`-এর Value `None` কি না পরীক্ষা করা যায়।

```python
result = None

# Write your condition here
```

**Requirement:** `None` হলে `"No result"` এবং অন্যথায় `"Result available"` Print করবে।

---

## 3. Level 2: Type Conversion

### Exercise 6: Convert String to Integer

```python
number = "250"
```

String-টিকে Integer-এ Convert করে `50` যোগ করো।

Expected Output:

```text
300
```

### Exercise 7: Convert Integer to String

```python
age = 22
```

এমন একটি Message তৈরি করো:

```text
My age is 22
```

### Exercise 8: Convert to Float

```python
price = "125.75"
```

String-টিকে Float-এ Convert করে `10` যোগ করো।

Expected Output:

```text
135.75
```

### Exercise 9: Convert to Boolean

নিচের Value-গুলোর জন্য `bool()` ব্যবহার করো:

```python
values = [0, 1, "", "False", [], [0], None]
```

**Important:** `"False"` String-এর Boolean Value কী হবে এবং কেন হবে, ব্যাখ্যা করো।

### Exercise 10: Convert Between Collections

নিচের Code সম্পূর্ণ করো।

```python
numbers = [10, 20, 10, 30, 20, 40]

# Convert the list to a set
# Convert the set to a tuple
# Print both results
```

**Task:** Set-এ Duplicate Value কেন থাকে না, তা ব্যাখ্যা করো।

### Exercise 11: Handle Conversion Errors

নিচের Code-টি নিরাপদভাবে লেখো।

```python
user_input = "hello"

number = int(user_input)
print(number)
```

**Requirement:** Invalid Integer Input হলে Program যেন Crash না করে; উপযুক্ত Error Message দেখাবে।

---

## 4. Level 3: String and Collection Data Types

### Exercise 12: String Operations

```python
text = "Python Programming"
```

নিচের কাজগুলো করো:

1. String-এর Length বের করো।
2. সব Character Uppercase করো।
3. সব Character Lowercase করো।
4. `"Programming"` অংশটি বের করো।
5. String-টি `"Python"` দিয়ে শুরু হয়েছে কি না পরীক্ষা করো।

### Exercise 13: List Operations

একটি List তৈরি করো:

```python
numbers = [10, 20, 30]
```

নিচের কাজগুলো করো:

1. `40` যোগ করো।
2. প্রথম Element-কে `100` করো।
3. `20` Remove করো।
4. List-এর Length Print করো।

### Exercise 14: Tuple Operations

একটি Tuple তৈরি করো:

```python
student = ("Masum", 22, "CSE")
```

নিচের কাজগুলো করো:

1. Name Print করো।
2. Age Print করো।
3. Department Print করো।
4. Tuple-এর Length বের করো।

**Task:** Tuple-এর Element সরাসরি পরিবর্তন করা যায় কি না, ব্যাখ্যা করো।

### Exercise 15: Set Operations

দুটি Set তৈরি করো:

```python
a = {10, 20, 30, 40}
b = {30, 40, 50, 60}
```

নিচের Operation-গুলো করো:

1. Union
2. Intersection
3. Difference
4. Symmetric Difference

**Hint:** `|`, `&`, `-`, `^` Operator ব্যবহার করতে পারো।

### Exercise 16: Dictionary Operations

নিচের Dictionary ব্যবহার করো:

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}
```

নিচের কাজগুলো করো:

1. Name Access করো।
2. CGPA Key যোগ করো।
3. Age Update করো।
4. Dictionary-এর সব Key Print করো।
5. `get()` দিয়ে অনুপস্থিত Key Access করো।

---

## 5. Level 4: Mutable and Immutable Objects

### Exercise 17: Shared Reference

Output অনুমান করো।

```python
a = [10, 20, 30]
b = a

b.append(40)

print(a)
print(b)
print(a is b)
```

**Task:** কেন `a` এবং `b`-এর Output একই, ব্যাখ্যা করো।

### Exercise 18: Reassignment

Output অনুমান করো।

```python
a = [1, 2, 3]
b = a

a = [4, 5, 6]

print(a)
print(b)
print(a is b)
```

**Task:** Exercise 17-এর সঙ্গে এর পার্থক্য ব্যাখ্যা করো।

### Exercise 19: Shallow Copy

```python
original = [[1, 2], [3, 4]]
copied = original.copy()

copied[0][0] = 100

print(original)
print(copied)
```

**Task:** Original List কেন পরিবর্তিত হয়েছে?

### Exercise 20: Deep Copy

Exercise 19-এর Code-টি `copy.deepcopy()` ব্যবহার করে লেখো।

**Requirement:** Nested List পরিবর্তন করলেও Original যেন অপরিবর্তিত থাকে।

### Exercise 21: Immutable String

```python
first = "Python"
second = first

first = first + " Programming"

print(first)
print(second)
```

**Task:** দুটি Variable-এর Output আলাদা হওয়ার কারণ ব্যাখ্যা করো।

### Exercise 22: Tuple with Mutable Object

```python
data = ([1, 2], [3, 4])

data[0].append(5)

print(data)
```

**Task:** Tuple Immutable হলেও ভিতরের List কীভাবে পরিবর্তিত হলো?

---

## 6. Level 5: Type Compatibility and Errors

### Exercise 23: Find the Error

নিচের Code-এ কী Error হবে, তা শনাক্ত করো।

```python
number = 10
text = "20"

print(number + text)
```

**Task:** Error-এর কারণ এবং সমাধান লেখো।

### Exercise 24: Fix the IndexError

```python
numbers = [10, 20, 30]

print(numbers[5])
```

**Requirement:** বৈধ Index হলে Element Print করবে; অন্যথায় উপযুক্ত Message দেখাবে।

### Exercise 25: Handle KeyError

```python
student = {
    "name": "Masum",
    "department": "CSE"
}

print(student["cgpa"])
```

**Requirement:** Key না থাকলে Program যেন Crash না করে।

### Exercise 26: Handle ZeroDivisionError

দুটি Number নিয়ে Division করার Program লেখো।

**Requirement:** Divisor `0` হলে `"Cannot divide by zero."` দেখাবে।

### Exercise 27: TypeError or ValueError?

প্রতিটি Code-এর ক্ষেত্রে কোন Error হতে পারে তা লেখো।

**A.**

```python
print("Age: " + 22)
```

**B.**

```python
print(int("hello"))
```

**C.**

```python
print([10, 20][5])
```

**D.**

```python
print(10 / 0)
```

**Task:** প্রতিটি Error-এর কারণ ব্যাখ্যা করো।

---

## 7. Level 6: Choosing the Right Data Type

### Exercise 28: Student Information

একটি Student Record তৈরি করো।

তথ্য:

- Name: Masum
- Student ID: `2026001`
- Age: `22`
- CGPA: `3.95`
- Enrolled: `True`
- Courses: Python, AI, MIS

**Task:** প্রতিটি Value-এর জন্য উপযুক্ত Data Type নির্বাচন করো।

### Exercise 29: Remove Duplicates

```python
courses = ["AI", "MIS", "AI", "VLSI", "MIS"]
```

Duplicate বাদ দিয়ে Unique Course Collection তৈরি করো।

**Task:** কেন Set ব্যবহার করা উপযোগী, তা ব্যাখ্যা করো।

### Exercise 30: Phone Number

একটি Phone Number সংরক্ষণ করার জন্য `str` নাকি `int` ব্যবহার করা উচিত?

**Task:** Leading Zero এবং Arithmetic Operation-এর প্রয়োজন বিবেচনা করে উত্তর লেখো।

### Exercise 31: Financial Calculation

`Decimal` ব্যবহার করে `10.25` এবং `1.50` যোগ করো।

**Requirement:** Decimal তৈরি করার সময় String ব্যবহার করো।

### Exercise 32: Missing Value

একটি Variable-এ বর্তমানে কোনো Result নেই—এমন অবস্থা প্রকাশ করো।

**Requirement:** `None` ব্যবহার করো এবং `is None` দিয়ে পরীক্ষা করো।

---

## 8. Level 7: Practical Coding Challenges

### Exercise 33: Simple Marks Calculator

একজন Student-এর তিনটি Subject-এর Marks Input নাও।

Requirements:

1. Marks-গুলো Numeric Type-এ Convert করো।
2. Total Marks বের করো।
3. Average Marks বের করো।
4. Invalid Input Handle করো।

### Exercise 34: Unique Number Collector

একটি List-এ কিছু Duplicate Number থাকবে।

Requirements:

1. List থেকে Unique Number বের করো।
2. Unique Number-গুলো Print করো।
3. মোট কতটি Unique Number আছে, তা দেখাও।

### Exercise 35: Student Record Manager

একটি Dictionary-তে Student-এর তথ্য রাখো।

Requirements:

1. Name
2. Student ID
3. Age
4. CGPA
5. Course List

তারপর Age Update করো, নতুন Course যোগ করো এবং সম্পূর্ণ Record Print করো।

### Exercise 36: Safe Number Converter

`safe_int()` নামে একটি Function লেখো।

Requirements:

1. একটি Value গ্রহণ করবে।
2. Integer-এ Convert করার চেষ্টা করবে।
3. Conversion ব্যর্থ হলে `None` Return করবে।
4. Conversion সফল হলে Integer Return করবে।

Example:

```python
print(safe_int("123"))
print(safe_int("hello"))
```

Expected Output:

```text
123
None
```

**Challenge:** Function-টি এমনভাবে তৈরি করো যেন Boolean Value-কে Integer হিসেবে গ্রহণ না করে।

### Exercise 37: Data Type Analyzer

একটি Function তৈরি করো, যা একটি Value গ্রহণ করে তার Type সম্পর্কে তথ্য দেখাবে।

Example:

```python
analyze_value(100)
analyze_value("Python")
analyze_value([1, 2, 3])
```

Requirements:

- Value Print করবে।
- Type Print করবে।
- Value Mutable নাকি Immutable, সে সম্পর্কে উপযুক্ত ব্যাখ্যা দেবে।

**Hint:** Mutable ও Immutable Type-এর জন্য আলাদা Logic ব্যবহার করো। Custom Object বা জটিল Container-এর ক্ষেত্রে Mutability সবসময় একটি সরল Type Label দিয়ে নির্ধারণ করা যায় না।

---

## 9. Final Challenge: University Student Data

একটি University Student Data Program তৈরি করো।

প্রতিটি Student-এর জন্য সংরক্ষণ করবে:

- Name
- Student ID
- Age
- CGPA
- Enrolled Status
- Registered Courses

Example Structure:

```python
student = {
    "name": "Masum",
    "student_id": "2026001",
    "age": 22,
    "cgpa": 3.95,
    "is_enrolled": True,
    "courses": ["Python", "AI", "MIS"]
}
```

Program-এর Requirements:

1. সঠিক Data Type ব্যবহার করবে।
2. Student-এর Age ও CGPA Validate করবে।
3. Course List-এ নতুন Course যোগ করবে।
4. মোট Course Count দেখাবে।
5. CGPA অনুপস্থিত হলে `None` ব্যবহার করতে পারবে।
6. Invalid Numeric Input Handle করবে।
7. Dictionary-এর তথ্য সুন্দরভাবে Print করবে।

**Bonus Challenge:**

একটি Function তৈরি করো, যা Student Dictionary গ্রহণ করবে এবং Validation সফল হলে Student Record Return করবে। Invalid Data পেলে উপযুক্ত Exception Raise করবে।

---

## 10. Self-Assessment Checklist

Practice শেষ হলে প্রতিটি বিষয় যাচাই করো।

- [ ] Built-in Data Types শনাক্ত করতে পারি।
- [ ] `type()` এবং `isinstance()` ব্যবহার করতে পারি।
- [ ] Integer, Float ও Complex-এর পার্থক্য বুঝি।
- [ ] String, Boolean এবং `None` সঠিকভাবে ব্যবহার করতে পারি।
- [ ] List, Tuple, Set ও Dictionary-এর পার্থক্য বুঝি।
- [ ] Implicit ও Explicit Type Conversion বুঝি।
- [ ] `TypeError` এবং `ValueError`-এর পার্থক্য বুঝি।
- [ ] Mutable ও Immutable Object-এর পার্থক্য বুঝি।
- [ ] `is` এবং `==` সঠিকভাবে ব্যবহার করতে পারি।
- [ ] Shallow Copy ও Deep Copy-এর পার্থক্য বুঝি।
- [ ] প্রয়োজন অনুযায়ী সঠিক Data Type নির্বাচন করতে পারি।
- [ ] `try-except` দিয়ে Common Error Handle করতে পারি।
- [ ] নিজের ছোট Program-এ Data Types ব্যবহার করতে পারি।

যেসব বিষয় এখনও পরিষ্কার নয়, সেগুলোর আগের Notes আবার পড়ে সংশ্লিষ্ট Exercise পুনরায় সমাধান করো।

## 11. Next Topic

পরবর্তী এবং এই Chapter-এর শেষ ফাইল:

**`33_Chapter_Review_and_Self_Assessment.md`**

সেখানে Chapter 03-এর মূল Concept, গুরুত্বপূর্ণ পার্থক্য, Revision Questions এবং Final Self-Assessment একসঙ্গে থাকবে।