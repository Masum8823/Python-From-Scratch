# 30. Choosing the Right Data Type in Python

## 1. Introduction

Python-এ Data Type নির্ধারণ করে কোনো Variable কী ধরনের Value রাখবে এবং সেই Value-এর ওপর কী ধরনের Operation করা যাবে।

সঠিক Data Type নির্বাচন করলে:

- Code সহজে বোঝা যায়।
- Data সঠিকভাবে সংরক্ষণ করা যায়।
- প্রয়োজনীয় Operation সহজে করা যায়।
- Common Error কমানো যায়।
- Program আরও maintainable হয়।

Example:

```python
student_name = "Masum"
student_age = 22
student_cgpa = 3.95
is_enrolled = True
```

এখানে প্রতিটি Variable-এর জন্য তার Value অনুযায়ী Data Type ব্যবহার করা হয়েছে।

## 2. Choosing a Numeric Data Type

Number নিয়ে কাজ করার সময় প্রয়োজন অনুযায়ী `int`, `float` অথবা `complex` নির্বাচন করতে হয়।

### 2.1 Integer (`int`)

পূর্ণসংখ্যা সংরক্ষণ করতে `int` ব্যবহার করা হয়।

Examples:

```python
age = 22
total_students = 50
semester = 9
```

**কখন ব্যবহার করবে:**

- বয়সের বছর
- Student count
- Product quantity
- পরীক্ষার প্রাপ্ত পূর্ণ নম্বর
- Loop counter

```python
total_students = 45
new_students = 5

print(total_students + new_students)
```

Output:

```text
50
```

**মনে রাখবে:** কোনো Quantity গণনা করতে হলে `int` সাধারণত উপযুক্ত। তবে বাস্তব পরিস্থিতিতে fractional value প্রয়োজন হলে অন্য Type বিবেচনা করতে হবে।

### 2.2 Float (`float`)

Decimal বা ভগ্নাংশযুক্ত Number সংরক্ষণ করতে `float` ব্যবহার করা হয়।

Examples:

```python
cgpa = 3.95
temperature = 36.5
height = 5.8
```

**কখন ব্যবহার করবে:**

- CGPA
- Temperature
- Measurement
- Percentage বা decimal result
- সাধারণ বৈজ্ঞানিক গণনা

```python
marks = 85.5
bonus = 2.5

print(marks + bonus)
```

Output:

```text
88.0
```

**সতর্কতা:** `float` সব Decimal value নিখুঁতভাবে সংরক্ষণ করতে পারে না। Financial calculation-এ নির্ভুল decimal arithmetic প্রয়োজন হলে `decimal.Decimal` বিবেচনা করো।

### 2.3 Complex (`complex`)

বাস্তব ও কাল্পনিক অংশযুক্ত Number-এর জন্য `complex` ব্যবহার করা হয়।

```python
number = 3 + 4j

print(number)
print(number.real)
print(number.imag)
```

Output:

```text
(3+4j)
3.0
4.0
```

**কখন ব্যবহার করবে:** Scientific computing, engineering এবং complex-number mathematics-এ।

সাধারণ Student Management System বা দৈনন্দিন Application-এ সাধারণত `int` ও `float` বেশি প্রয়োজন হয়।

## 3. Choosing Between String and Numeric Types

কোনো Value দেখতে Number-এর মতো হলেও সেটি সবসময় Numeric Type হওয়া উচিত নয়।

Example:

```python
student_id = "2026001"
student_age = 22
```

এখানে `student_id` String হিসেবে রাখা হয়েছে, কারণ ID সাধারণত পরিচয় নির্দেশ করে; এটি দিয়ে Arithmetic করা হয় না।

অন্যদিকে `student_age` একটি Number, কারণ এর ওপর গণনা করা যেতে পারে।

### Comparison

| Data | Suitable Type | Reason |
|---|---|---|
| Student name | `str` | Text সংরক্ষণ |
| Student ID | `str` | Identifier, সাধারণত গণনা করা হয় না |
| Age | `int` | পূর্ণসংখ্যা |
| CGPA | `float` | Decimal value |
| Phone number | `str` | Arithmetic প্রয়োজন নেই; leading zero থাকতে পারে |
| Email address | `str` | Text data |
| Product quantity | `int` | Item count |
| Product price | `Decimal` বা উপযুক্ত numeric type | নির্ভুল আর্থিক হিসাবের প্রয়োজন হতে পারে |

Example:

```python
phone_number = "01712345678"

print(phone_number)
```

Phone number-কে Integer হিসেবে রাখলে leading zero হারিয়ে যেতে পারে এবং Number-এর মতো Arithmetic করারও প্রয়োজন নেই।

## 4. Choosing a Text Data Type

Text সংরক্ষণের জন্য `str` ব্যবহার করা হয়।

```python
name = "Masum"
department = "CSE"
university = "Northern University Bangladesh"
```

**কখন ব্যবহার করবে:**

- Name
- Address
- Email
- Course title
- Message
- User input-এর text
- File path

Example:

```python
course_name = "Artificial Intelligence"

print("Course:", course_name)
```

Output:

```text
Course: Artificial Intelligence
```

String immutable হওয়ায় নির্দিষ্ট Character সরাসরি পরিবর্তন করা যায় না। পরিবর্তিত String প্রয়োজন হলে নতুন String তৈরি করতে হয়।

## 5. Choosing a Boolean Data Type

শুধু দুটি Logical State প্রকাশ করতে `bool` ব্যবহার করা হয়: `True` এবং `False`।

Examples:

```python
is_student = True
is_paid = False
is_logged_in = True
```

**কখন ব্যবহার করবে:**

- কোনো Student enrolled কি না
- User logged in কি না
- Payment completed কি না
- Form valid কি না
- কোনো condition সত্য কি না

Example:

```python
is_enrolled = True

if is_enrolled:
    print("Student is enrolled.")
else:
    print("Student is not enrolled.")
```

Output:

```text
Student is enrolled.
```

Boolean ব্যবহার করলে কোনো Condition-এর অর্থ পরিষ্কার থাকে।

## 6. Choosing a List

একাধিক Item-এর Ordered Collection সংরক্ষণ করতে `list` ব্যবহার করা হয়।

List হলো Mutable, তাই এর Element পরিবর্তন, যোগ বা বাদ দেওয়া যায়।

Example:

```python
courses = ["Python", "AI", "MIS"]

courses.append("VLSI")

print(courses)
```

Output:

```text
['Python', 'AI', 'MIS', 'VLSI']
```

**কখন ব্যবহার করবে:**

- Student-এর Course List
- Shopping Cart
- Marks List
- Task List
- Ordered Items
- পরিবর্তনশীল Collection

List-এ Duplicate Value রাখা যায়।

```python
marks = [80, 85, 90, 85]

print(marks)
```

Output:

```text
[80, 85, 90, 85]
```

যদি Item-এর Order গুরুত্বপূর্ণ হয় এবং Collection পরিবর্তন করতে হয়, তাহলে List ভালো পছন্দ।

## 7. Choosing a Tuple

একাধিক Value একসঙ্গে সংরক্ষণ করতে `tuple` ব্যবহার করা হয়, যখন Collection-এর Element Reference-গুলো পরিবর্তন করা উচিত নয়।

Example:

```python
coordinates = (23.8103, 90.4125)

print(coordinates)
```

Output:

```text
(23.8103, 90.4125)
```

**কখন ব্যবহার করবে:**

- Fixed coordinates
- কোনো Function থেকে একাধিক Value Return
- নির্দিষ্ট Record-এর কয়েকটি Value একসঙ্গে রাখা
- পরিবর্তন না করার জন্য নির্ধারিত Sequence

Example:

```python
def get_student():
    return ("Masum", 3.95)

student = get_student()

print(student)
```

Output:

```text
('Masum', 3.95)
```

Tuple-এর ভিতরে Mutable Object থাকলে সেই Object পরিবর্তনযোগ্য হতে পারে। তাই Tuple-কে সম্পূর্ণ Deeply Immutable ভাবা ঠিক নয়।

## 8. Choosing a Set

Unique Value সংরক্ষণ করতে এবং Set Operations করতে `set` ব্যবহার করা হয়।

Set-এ Duplicate Value রাখা হয় না এবং Element-এর নির্দিষ্ট Position বা Order-এর ওপর নির্ভর করা উচিত নয়।

Example:

```python
courses = {"Python", "AI", "MIS", "AI"}

print(courses)
```

Output-এ `"AI"` একবার থাকবে। Element-এর Order নির্দিষ্ট নয়।

**কখন ব্যবহার করবে:**

- Duplicate বাদ দেওয়া
- Unique Student ID নিয়ে কাজ করা
- Common Item বের করা
- দুটি Collection-এর Difference বের করা
- Membership Testing

Example:

```python
section_a = {"Masum", "Ritu", "Mahin"}
section_b = {"Ritu", "Tusher", "Masum"}

print(section_a & section_b)
```

Output-এ `"Masum"` এবং `"Ritu"` থাকবে, তবে তাদের Order নির্দিষ্ট নয়।

এখানে `&` Set Intersection নির্দেশ করে।

## 9. Choosing a Dictionary

Key-Value Pair আকারে Data সংরক্ষণ করতে `dict` ব্যবহার করা হয়।

Example:

```python
student = {
    "name": "Masum",
    "department": "CSE",
    "cgpa": 3.95
}

print(student["name"])
print(student["cgpa"])
```

Output:

```text
Masum
3.95
```

**কখন ব্যবহার করবে:**

- Student Record
- Product Information
- User Profile
- Configuration Settings
- API Response
- Named attributes-সহ Data

Dictionary ব্যবহার করলে প্রতিটি Value একটি নির্দিষ্ট Key-এর মাধ্যমে Access করা যায়।

Example:

```python
product = {
    "name": "Keyboard",
    "price": 1200,
    "in_stock": True
}

print(product["price"])
```

Output:

```text
1200
```

যখন Data-এর প্রতিটি Value-এর আলাদা পরিচয় প্রয়োজন হয়, তখন Dictionary সাধারণত ভালো পছন্দ।

## 10. Choosing Between List, Tuple, Set and Dictionary

| Requirement | Suitable Type |
|---|---|
| Ordered, changeable Collection | `list` |
| Fixed Sequence of Values | `tuple` |
| Unique Values | `set` |
| Key-Value Data | `dict` |
| Text | `str` |
| True/False State | `bool` |
| Whole-number Count | `int` |
| Decimal Measurement | `float` |
| Precise Decimal Financial Calculation | `decimal.Decimal` |

Example:

```python
student_names = ["Masum", "Ritu", "Tusher"]

student_location = (23.81, 90.41)

unique_departments = {"CSE", "EEE", "BBA"}

student_info = {
    "name": "Masum",
    "cgpa": 3.95
}
```

এখানে প্রতিটি Type ভিন্ন ধরনের Requirement পূরণ করছে।

## 11. Choosing a Type for Financial Data

সাধারণ Decimal Calculation-এর জন্য `float` ব্যবহার করা যায়। তবে Money বা Financial Calculation-এ নির্দিষ্ট Decimal Precision প্রয়োজন হতে পারে।

Python-এর `decimal` Module এ ধরনের কাজে উপযোগী।

```python
from decimal import Decimal

price = Decimal("10.25")
tax = Decimal("1.50")

total = price + tax

print(total)
```

Output:

```text
11.75
```

`Decimal` তৈরি করার সময় String ব্যবহার করা ভালো, কারণ Float থেকে Decimal তৈরি করলে Float-এর Binary Approximation-এর প্রভাব থাকতে পারে।

Example:

```python
from decimal import Decimal

value = Decimal("0.1") + Decimal("0.2")

print(value)
```

Output:

```text
0.3
```

তবে শুধু `Decimal` ব্যবহার করলেই সব Financial Rule স্বয়ংক্রিয়ভাবে পূরণ হয় না। Currency Precision, Rounding এবং Business Rules-ও ঠিকভাবে নির্ধারণ করতে হয়।

## 12. Choosing a Type for Binary Data

সাধারণ Text-এর জন্য `str` ব্যবহার করা হয়। কিন্তু Binary Data নিয়ে কাজ করতে `bytes` বা `bytearray` প্রয়োজন হতে পারে।

### 12.1 Bytes

`bytes` হলো Immutable Binary Data Type।

```python
data = b"Python"

print(data)
```

Output:

```text
b'Python'
```

**ব্যবহার:**

- Binary File Data
- Encoded Data
- Network Protocol-এর Byte Data

### 12.2 Bytearray

`bytearray` হলো Mutable Binary Data Type।

```python
data = bytearray(b"ABC")

data[0] = 88

print(data)
```

Output:

```text
bytearray(b'XBC')
```

Binary Data পরিবর্তন করতে হলে `bytearray` উপযোগী হতে পারে।

## 13. Choosing None

কোনো Value অনুপস্থিত বা এখনও নির্ধারিত হয়নি—এমন অবস্থা বোঝাতে `None` ব্যবহার করা হয়।

Example:

```python
middle_name = None

if middle_name is None:
    print("Middle name is not provided.")
```

Output:

```text
Middle name is not provided.
```

**কখন ব্যবহার করবে:**

- Optional Value
- Function থেকে কোনো Result না থাকা
- কোনো Data এখনও পাওয়া যায়নি
- কোনো Object তৈরি বা নির্ধারণের অপেক্ষায় আছে

`None` পরীক্ষা করার জন্য সাধারণত `is None` ব্যবহার করা হয়।

```python
result = None

if result is None:
    print("No result available.")
```

Output:

```text
No result available.
```

## 14. Choosing a Data Type Based on Requirements

Data Type নির্বাচন করার আগে কয়েকটি প্রশ্ন করো।

1. Data কি Number, Text, নাকি অন্য কিছু?
2. Data-এর ওপর Arithmetic Operation প্রয়োজন কি?
3. Collection হলে Order গুরুত্বপূর্ণ কি?
4. Duplicate Value অনুমোদিত কি?
5. Data পরিবর্তন করা প্রয়োজন কি?
6. Value-গুলো Key-Value Pair হিসেবে Access করতে হবে কি?
7. নির্ভুল Decimal Calculation প্রয়োজন কি?

Example: একটি Student Management System তৈরি করতে হলে:

```python
student = {
    "student_id": "2026001",
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95,
    "is_active": True,
    "courses": ["AI", "MIS", "VLSI"]
}
```

এখানে:

- `student_id`: `str`, কারণ এটি Identifier।
- `name`: `str`, কারণ এটি Text।
- `age`: `int`, কারণ এটি পূর্ণসংখ্যা।
- `cgpa`: `float`, কারণ এটি Decimal Value।
- `is_active`: `bool`, কারণ এটি Logical State।
- `courses`: `list`, কারণ একাধিক Course Ordered Collection হিসেবে রাখা হয়েছে।

বাস্তব Application-এ Database Schema, Validation Rules এবং Precision Requirement অনুযায়ী এই সিদ্ধান্তগুলো আরও নির্দিষ্ট হতে পারে।

## 15. Common Mistakes

### Mistake 1: Phone Number as Integer

```python
phone = 1712345678
```

এভাবে রাখলে শুরুতে থাকা `0` সংরক্ষিত থাকবে না।

Better:

```python
phone = "01712345678"
```

### Mistake 2: Using a List for Unique Values Only

```python
departments = ["CSE", "EEE", "CSE", "BBA"]
```

শুধু Unique Value দরকার হলে Set ব্যবহার করা যায়:

```python
departments = {"CSE", "EEE", "CSE", "BBA"}

print(departments)
```

Output-এ প্রতিটি Department একবার থাকবে।

### Mistake 3: Using a List for Key-Value Data

```python
student = ["Masum", 22, 3.95]
```

এখানে কোন Value কী বোঝায়, তা Index দেখে বুঝতে হয়।

Better:

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}
```

### Mistake 4: Using Float for Every Numeric Problem

সাধারণ Calculation-এ Float উপযোগী। কিন্তু Exact Financial Precision প্রয়োজন হলে `Decimal` বিবেচনা করা উচিত।

### Mistake 5: Choosing a Type Without Considering Mutation

যে Collection-এর Content নিয়মিত পরিবর্তন করতে হবে, সেখানে সাধারণত List বা Dictionary ব্যবহার করা সুবিধাজনক। নির্দিষ্ট Sequence-এর Reference পরিবর্তন করা উচিত নয় হলে Tuple বিবেচনা করা যায়।

## 16. Practice Exercises

### Exercise 1: Choose the Correct Type

নিচের প্রতিটি Data-এর জন্য উপযুক্ত Type নির্বাচন করো:

1. Student Name
2. Student ID
3. CGPA
4. Number of Students
5. Payment Completed or Not
6. Unique Course Codes
7. Ordered Assignment List
8. Student Information with Named Fields
9. Fixed Pair of Coordinates
10. Missing Optional Value

### Exercise 2: Build a Student Record

একটি Dictionary তৈরি করো যেখানে থাকবে:

- Name
- Student ID
- Age
- CGPA
- Enrolled Status
- Course List

প্রতিটি Field-এর জন্য উপযুক্ত Data Type ব্যবহার করো।

### Exercise 3: Remove Duplicates

নিচের List থেকে Duplicate Value বাদ দিয়ে Unique Course List তৈরি করো।

```python
courses = ["AI", "MIS", "AI", "VLSI", "MIS"]
```

### Exercise 4: Select the Right Collection

কোন Requirement-এর জন্য List, Tuple, Set অথবা Dictionary ব্যবহার করবে, ব্যাখ্যা করো:

- Items-এর Order রাখতে হবে।
- Duplicate রাখা যাবে না।
- Key দিয়ে Value Access করতে হবে।
- নির্দিষ্ট Sequence রাখা হবে, যার Element Reference পরিবর্তন করা হবে না।

### Exercise 5: Financial Calculation

`Decimal` ব্যবহার করে দুটি Price যোগ করো। Float থেকে Decimal তৈরি না করে String থেকে Decimal তৈরি করো।

### Exercise 6: Mini Project — Course Registration Record

একটি Dictionary তৈরি করো যেখানে থাকবে:

- Student Name
- Student ID
- Registered Courses
- Total Registered Courses
- Registration Status

সঠিক Data Type নির্বাচন করো এবং Course List থেকে Total Registered Courses হিসাব করো।

## 17. Key Takeaways

- Data-এর Nature ও Program-এর Requirement অনুযায়ী Data Type নির্বাচন করতে হয়।
- `int` পূর্ণসংখ্যা, `float` সাধারণ Decimal Value এবং `str` Text-এর জন্য ব্যবহৃত হয়।
- `bool` Logical State প্রকাশ করে।
- `list` Ordered ও Mutable Collection-এর জন্য উপযোগী।
- `tuple` নির্দিষ্ট Sequence-এর জন্য উপযোগী।
- `set` Unique Value-এর জন্য এবং `dict` Key-Value Data-এর জন্য ব্যবহৃত হয়।
- Phone Number ও Identifier সাধারণত String হিসেবে রাখা ভালো।
- Financial Calculation-এ Exact Decimal Precision প্রয়োজন হলে `Decimal` বিবেচনা করা উচিত।
- সঠিক Data Type Code-কে পরিষ্কার, নিরাপদ ও সহজে maintainable করে।

## 18. Next Topic

পরবর্তী ফাইল:

**`31_Data_Types_Best_Practices.md`**

সেখানে Python Data Types ব্যবহারের গুরুত্বপূর্ণ Best Practices, Readability, Type Safety এবং Common Pitfalls নিয়ে আলোচনা করা হবে।