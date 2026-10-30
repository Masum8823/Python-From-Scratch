# 31. Data Types Best Practices in Python

## 1. Introduction

Python-এ সঠিক Data Type নির্বাচন করা যেমন গুরুত্বপূর্ণ, তেমনি সেগুলো সঠিকভাবে ব্যবহার করাও জরুরি।

**Best Practices** হলো এমন কিছু নিয়ম ও পদ্ধতি, যেগুলো অনুসরণ করলে Code আরও readable, maintainable এবং reliable হয়।

Data Types ব্যবহারের প্রধান লক্ষ্য:

- সঠিক Data Type নির্বাচন করা।
- অপ্রয়োজনীয় Type Conversion এড়িয়ে চলা।
- Unexpected Error কমানো।
- Code সহজে বোঝা ও পরিবর্তন করা।
- Data-এর অর্থ পরিষ্কার রাখা।

## 2. Choose the Right Data Type

সবসময় Data-এর প্রকৃতি অনুযায়ী Data Type নির্বাচন করো।

Example:

```python
student_name = "Masum"
student_age = 22
student_cgpa = 3.95
is_enrolled = True
```

এখানে:

- `student_name` হলো `str`।
- `student_age` হলো `int`।
- `student_cgpa` হলো `float`।
- `is_enrolled` হলো `bool`।

ভুল Data Type নির্বাচন করলে Code বোঝা এবং সঠিকভাবে ব্যবহার করা কঠিন হতে পারে।

Example:

```python
student_age = "22"
```

যদি Age নিয়ে Arithmetic করতে হয়, তাহলে Integer রাখা বেশি সুবিধাজনক।

```python
student_age = 22

print(student_age + 1)
```

Output:

```text
23
```

তবে কোনো Number-এর মতো দেখতে Value আসলে Identifier হলে String ব্যবহার করাই যুক্তিযুক্ত।

## 3. Use Meaningful Variable Names

Variable-এর নাম এমন হওয়া উচিত, যাতে বোঝা যায় সেটিতে কী ধরনের Data রাখা হয়েছে।

Bad Practice:

```python
a = "Masum"
b = 3.95
c = True
```

Better Practice:

```python
student_name = "Masum"
student_cgpa = 3.95
is_enrolled = True
```

Meaningful Variable Name Code পড়তে এবং Debugging করতে সাহায্য করে।

Python-এর সাধারণ Naming Convention অনুযায়ী Variable ও Function-এর নাম `snake_case`-এ লেখা হয়।

Example:

```python
total_marks = 450
student_count = 50
average_marks = 90.0
```

## 4. Understand Mutable and Immutable Objects

Mutable এবং Immutable Object-এর পার্থক্য পরিষ্কারভাবে বুঝতে হবে।

Mutable Types:

- `list`
- `dict`
- `set`
- `bytearray`

Immutable Types:

- `int`
- `float`
- `complex`
- `bool`
- `str`
- `bytes`
- `frozenset`

Tuple সাধারণত Immutable, তবে এর মধ্যে Mutable Object থাকলে সেই Object পরিবর্তন করা যায়।

Example:

```python
numbers = [10, 20, 30]
numbers.append(40)

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

List পরিবর্তনযোগ্য বলে এখানে নতুন Element যোগ করা গেছে।

**Best Practice:** কোনো Object পরিবর্তন করা প্রয়োজন কি না, তা বিবেচনা করে Collection নির্বাচন করো।

## 5. Avoid Unnecessary Type Conversion

একই Value বারবার Convert করার প্রয়োজন নেই। প্রয়োজন হলে একবার Convert করে Result ব্যবহার করো।

Bad Practice:

```python
value = "100"

print(int(value) + 10)
print(int(value) + 20)
print(int(value) + 30)
```

Better Practice:

```python
value = "100"
number = int(value)

print(number + 10)
print(number + 20)
print(number + 30)
```

এতে Code পড়তে সহজ হয় এবং Conversion-এর কাজ বারবার করতে হয় না।

তবে Input-এর Value পরিবর্তনশীল হলে Conversion-এর আগে Invalid Input-এর সম্ভাবনা বিবেচনা করতে হবে।

## 6. Validate User Input

`input()` Function সবসময় String Return করে। তাই User Input দিয়ে Numeric Calculation করতে হলে প্রয়োজন অনুযায়ী Convert করতে হয়।

Example:

```python
age = int(input("Enter your age: "))

print(age)
```

User বৈধ Integer দিলে এটি কাজ করবে। কিন্তু `hello` লিখলে `ValueError` হবে।

আরও নিরাপদ পদ্ধতি:

```python
user_input = input("Enter your age: ")

try:
    age = int(user_input)

    if age >= 0:
        print("Age:", age)
    else:
        print("Age cannot be negative.")

except ValueError:
    print("Please enter a valid integer.")
```

এখানে দুটি বিষয় যাচাই করা হয়েছে:

1. Input Integer-এ Convert করা যাচ্ছে কি না।
2. Age-এর Value গ্রহণযোগ্য কি না।

**মনে রাখবে:** Type Validation এবং Business Rule Validation আলাদা বিষয়। কোনো Value Integer হলেই সেটি সবসময় গ্রহণযোগ্য হবে না।

## 7. Use `isinstance()` for Type Checking

কোনো Object নির্দিষ্ট Type-এর কি না, তা যাচাই করতে `isinstance()` ব্যবহার করা যায়।

Example:

```python
value = 100

if isinstance(value, int):
    print("Integer value")
else:
    print("Not an integer")
```

Output:

```text
Integer value
```

একাধিক গ্রহণযোগ্য Type পরীক্ষা করাও সম্ভব।

```python
value = 3.5

if isinstance(value, (int, float)):
    print("Numeric value")
```

Output:

```text
Numeric value
```

তবে মনে রাখবে, `bool` হলো `int`-এর Subclass। তাই `isinstance(True, int)`-এর ফল `True`।

যদি Boolean বাদ দিয়ে নির্দিষ্ট Numeric Type গ্রহণ করতে চাও, তাহলে Validation আরও স্পষ্টভাবে লিখতে হবে।

## 8. Use `is None` to Check None

`None` কোনো Value অনুপস্থিত বা নির্ধারিত নয়—এমন অবস্থা প্রকাশ করতে ব্যবহৃত হয়।

Best Practice:

```python
result = None

if result is None:
    print("No result available.")
```

Output:

```text
No result available.
```

`None` পরীক্ষা করতে `is None` বা `is not None` ব্যবহার করো।

```python
result = 100

if result is not None:
    print("Result:", result)
```

Output:

```text
Result: 100
```

`None`-কে `0`, `False` বা Empty String-এর সঙ্গে গুলিয়ে ফেলবে না। এগুলো আলাদা Value।

## 9. Use the Right Collection Type

Collection নির্বাচন করার সময় Data-এর Requirement বিবেচনা করো।

| Requirement | Recommended Type |
|---|---|
| Ordered, changeable items | `list` |
| Fixed sequence of items | `tuple` |
| Unique values | `set` |
| Key-value records | `dict` |
| Text | `str` |
| Binary data | `bytes` বা `bytearray` |

Example:

```python
student = {
    "name": "Masum",
    "age": 22,
    "courses": ["Python", "AI", "MIS"]
}
```

এখানে Student-এর Named Information-এর জন্য Dictionary এবং Course Collection-এর জন্য List ব্যবহার করা হয়েছে।

**Best Practice:** শুধু সুবিধার জন্য একটি Type সব জায়গায় ব্যবহার না করে, Data-এর প্রকৃতি অনুযায়ী Type নির্বাচন করো।

## 10. Avoid Modifying Shared Mutable Objects Unexpectedly

একই Mutable Object একাধিক Variable Reference করলে একটি Variable দিয়ে পরিবর্তন অন্য Variable দিয়েও দেখা যেতে পারে।

Example:

```python
first = [10, 20, 30]
second = first

second.append(40)

print(first)
```

Output:

```text
[10, 20, 30, 40]
```

যদি Independent Copy প্রয়োজন হয়:

```python
first = [10, 20, 30]
second = first.copy()

second.append(40)

print(first)
print(second)
```

Output:

```text
[10, 20, 30]
[10, 20, 30, 40]
```

Nested Mutable Objects থাকলে `copy()` যথেষ্ট নাও হতে পারে। সে ক্ষেত্রে প্রয়োজন অনুযায়ী `copy.deepcopy()` ব্যবহার করা যায়।

## 11. Be Careful with Floating-Point Precision

Python-এর `float` Binary Floating-Point Representation ব্যবহার করে। তাই কিছু Decimal Value নিখুঁতভাবে Represent করা যায় না।

Example:

```python
print(0.1 + 0.2)
```

Output সাধারণত:

```text
0.30000000000000004
```

এটি Python-এর Bug নয়; Binary Floating-Point Representation-এর একটি সীমাবদ্ধতা।

### Recommended Approach

যদি Approximate Numeric Result গ্রহণযোগ্য হয়, তাহলে `math.isclose()` ব্যবহার করা যায়।

```python
import math

result = 0.1 + 0.2

print(math.isclose(result, 0.3))
```

Output:

```text
True
```

Financial Calculation-এ Exact Decimal Arithmetic প্রয়োজন হলে `decimal.Decimal` বিবেচনা করো।

```python
from decimal import Decimal

price = Decimal("0.1")
tax = Decimal("0.2")

print(price + tax)
```

Output:

```text
0.3
```

## 12. Use Type Hints When Helpful

Type Hints দিয়ে Variable, Function Parameter এবং Return Value-এর প্রত্যাশিত Type প্রকাশ করা যায়।

Example:

```python
student_name: str = "Masum"
student_age: int = 22
student_cgpa: float = 3.95
```

Function-এর ক্ষেত্রেও ব্যবহার করা যায়:

```python
def calculate_total(price: float, quantity: int) -> float:
    return price * quantity
```

এখানে:

- `price: float` → Price-এর প্রত্যাশিত Type।
- `quantity: int` → Quantity-এর প্রত্যাশিত Type।
- `-> float` → Return Value-এর প্রত্যাশিত Type।

সাধারণ Python Execution-এ Type Hints নিজে থেকে Runtime-এ Type Enforce করে না। তবে IDE, Static Type Checker এবং Code Review-এর মাধ্যমে ভুল শনাক্ত করতে সাহায্য করে।

## 13. Avoid Confusing `==` and `is`

`==` Value Equality পরীক্ষা করে, আর `is` Object Identity পরীক্ষা করে।

Example:

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a == b)
print(a is b)
```

Output:

```text
True
False
```

Best Practice:

- Value তুলনা করতে `==` ব্যবহার করো।
- একই Object কি না পরীক্ষা করতে `is` ব্যবহার করো।
- `None` পরীক্ষা করতে `is None` ব্যবহার করো।

Integer বা String-এর মতো Value তুলনা করার সময় অপ্রয়োজনীয়ভাবে `is` ব্যবহার করো না।

## 14. Follow Consistent Coding Style

Code-এ Consistent Naming, Indentation এবং Formatting বজায় রাখো।

Example:

```python
student_name = "Masum"
student_age = 22

if student_age >= 18:
    print(student_name, "is an adult.")
```

Python-এর প্রচলিত Style Guide হলো **PEP 8**। এটি Variable Naming, Indentation এবং Code Formatting-এর মতো বিষয়ে নির্দেশনা দেয়।

কিছু সাধারণ নিয়ম:

- Variable ও Function-এর জন্য `snake_case` ব্যবহার করো।
- Class-এর জন্য সাধারণত `PascalCase` ব্যবহার করো।
- Indentation Consistent রাখো।
- অর্থবহ Variable Name ব্যবহার করো।
- অপ্রয়োজনীয় Conversion ও জটিল Expression এড়িয়ে চলো।

## 15. Common Bad Practices and Better Alternatives

| Bad Practice | Better Practice |
|---|---|
| Phone Number-কে Integer হিসেবে রাখা | String হিসেবে রাখা |
| একই Value বারবার Convert করা | একবার Convert করে Reuse করা |
| সব Data-এর জন্য List ব্যবহার করা | Requirement অনুযায়ী Collection নির্বাচন |
| `None` পরীক্ষা করতে `==` ব্যবহার | `is None` ব্যবহার |
| Shared List-এর Copy না করা | প্রয়োজন অনুযায়ী Shallow বা Deep Copy |
| Float-কে সব Decimal Calculation-এর জন্য উপযুক্ত ভাবা | Precision Requirement বিবেচনা |
| Type Hints-কে Runtime Validation ভাবা | প্রয়োজন হলে আলাদা Validation করা |
| সব Exception একসঙ্গে ধরে ফেলা | নির্দিষ্ট Exception Handle করা |

## 16. Practical Example: Clean Student Record

নিচের Example-এ একাধিক Best Practice একসঙ্গে ব্যবহার করা হয়েছে।

```python
def create_student(
    name: str,
    student_id: str,
    age: int,
    cgpa: float
) -> dict:
    if not isinstance(name, str):
        raise TypeError("Name must be a string.")

    if not isinstance(student_id, str):
        raise TypeError("Student ID must be a string.")

    if type(age) is not int:
        raise TypeError("Age must be an integer.")

    if not isinstance(cgpa, (int, float)) or isinstance(cgpa, bool):
        raise TypeError("CGPA must be numeric.")

    if age < 0:
        raise ValueError("Age cannot be negative.")

    if not 0 <= cgpa <= 4.0:
        raise ValueError("CGPA must be between 0 and 4.")

    return {
        "name": name,
        "student_id": student_id,
        "age": age,
        "cgpa": float(cgpa)
    }


student = create_student("Masum", "2026001", 22, 3.95)

print(student)
```

Output:

```text
{'name': 'Masum', 'student_id': '2026001', 'age': 22, 'cgpa': 3.95}
```

এই Example-এ:

1. Meaningful Parameter Name ব্যবহার করা হয়েছে।
2. Type Hints দেওয়া হয়েছে।
3. Input Type যাচাই করা হয়েছে।
4. Invalid Value-এর জন্য `ValueError` ব্যবহার করা হয়েছে।
5. Student Record Dictionary-তে রাখা হয়েছে।

এটি একটি Learning Example। বাস্তব System-এ University-এর প্রকৃত Validation Rules, Database Constraints এবং প্রয়োজনীয় Error Handling আলাদাভাবে নির্ধারণ করতে হবে।

## 17. Practice Exercises

### Exercise 1: Identify the Bad Practice

নিচের Code-এ কী সমস্যা আছে তা চিহ্নিত করো।

```python
a = "Masum"
b = "22"
c = True
```

প্রতিটি Variable-এর জন্য আরও অর্থবহ নাম প্রস্তাব করো।

### Exercise 2: Fix Type Conversion

```python
age = "22"

print(age + 1)
```

Code-টি ঠিক করো, যাতে Output `23` হয়।

### Exercise 3: Safe Input Validation

একটি Program লেখো, যা User-এর কাছ থেকে Integer Input নেবে। Invalid Input দিলে Error Message দেখাবে।

### Exercise 4: Choose the Right Collection

একটি Student Record তৈরি করো, যেখানে থাকবে Name, ID, CGPA এবং Course List। প্রতিটি Field-এর জন্য সঠিক Data Type ব্যবহার করো।

### Exercise 5: Fix Shared Reference

```python
a = [1, 2, 3]
b = a

b.append(4)

print(a)
```

`b`-তে পরিবর্তন করলেও `a` যেন অপরিবর্তিত থাকে, সে অনুযায়ী Code ঠিক করো।

### Exercise 6: Handle Floating-Point Comparison

```python
value = 0.1 + 0.2
```

`value`-কে সরাসরি `0.3`-এর সঙ্গে তুলনা না করে `math.isclose()` ব্যবহার করো।

### Exercise 7: Mini Project — Validated Student Record

একটি Function তৈরি করো, যা Name, Student ID, Age এবং CGPA গ্রহণ করবে।

শর্ত:

- Name এবং Student ID হবে String।
- Age হবে Non-negative Integer।
- CGPA হবে `0` থেকে `4.0`-এর মধ্যে।
- Invalid Type হলে `TypeError`।
- Invalid Value হলে `ValueError`।
- সঠিক Input হলে Dictionary Return করবে।

## 18. Key Takeaways

- Data-এর প্রকৃতি অনুযায়ী সঠিক Type নির্বাচন করো।
- Meaningful Variable Name ব্যবহার করো।
- প্রয়োজন ছাড়া বারবার Type Conversion করো না।
- User Input এবং Data Validate করো।
- Mutable Object-এর Shared Reference সম্পর্কে সচেতন থাকো।
- Floating-Point Precision-এর সীমাবদ্ধতা বোঝো।
- প্রয়োজন অনুযায়ী Type Hints ব্যবহার করো।
- `==` ও `is`-এর সঠিক ব্যবহার নিশ্চিত করো।
- Consistent Coding Style বজায় রাখো।
- Code সহজ, পরিষ্কার এবং Maintainable রাখো।

## 19. Next Topic

পরবর্তী ফাইল:

**`32_Data_Types_Practice_Exercises.md`**

সেখানে Chapter 03-এর Data Types, Type Checking, Type Conversion, Mutability এবং Type Compatibility নিয়ে সমন্বিত Practice Exercises থাকবে।