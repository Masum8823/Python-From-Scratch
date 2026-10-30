# 29. Type Compatibility and Common Errors

## 1. Introduction

Python-এ বিভিন্ন Data Type-এর value নিয়ে কাজ করার সময় সব Operation সব Type-এর জন্য কাজ করে না। কোনো Operation-এর জন্য উপযুক্ত Data Type না থাকলে Python Error দিতে পারে।

**Type Compatibility:** দুটি বা একাধিক Data Type কোনো নির্দিষ্ট Operation-এর সঙ্গে সঠিকভাবে কাজ করতে পারলে তাদের সেই Operation-এর জন্য compatible বলা যায়।

Example:

```python
a = 10
b = 5

print(a + b)
```

Output:

```text
15
```

এখানে দুটি Integer যোগ করা যায়।

কিন্তু:

```python
age = 22
message = "My age is "

print(message + age)
```

এখানে `str` এবং `int` সরাসরি `+` দিয়ে concatenate করা যায় না। ফলে `TypeError` হবে।

সঠিকভাবে লিখতে পারি:

```python
age = 22
message = "My age is "

print(message + str(age))
```

Output:

```text
My age is 22
```

## 2. Compatible and Incompatible Operations

কোনো Operation-এর compatibility নির্ভর করে ব্যবহৃত Data Type এবং Operation-এর ওপর।

| Operation | Example | Result |
|---|---|---|
| Integer addition | `10 + 5` | `15` |
| Float addition | `2.5 + 1.5` | `4.0` |
| String concatenation | `"Py" + "thon"` | `"Python"` |
| List concatenation | `[1, 2] + [3]` | `[1, 2, 3]` |
| String and Integer addition | `"Age: " + 20` | `TypeError` |
| List and Integer addition | `[1, 2] + 3` | `TypeError` |
| Integer and String multiplication | `3 * "Hi"` | `"HiHiHi"` |

মনে রাখবে, একই Operator বিভিন্ন Data Type-এর জন্য ভিন্নভাবে কাজ করতে পারে।

## 3. Common Type Compatibility Rules

### 3.1 Numeric Types

Python সাধারণত Integer ও Float-এর মতো Numeric Type-এর মধ্যে Arithmetic Operation সমর্থন করে।

```python
a = 10
b = 2.5

print(a + b)
print(a * b)
```

Output:

```text
12.5
25.0
```

Integer এবং Float একসঙ্গে ব্যবহার করলে অনেক Arithmetic Operation-এর ক্ষেত্রে Integer value Float-এ promote হয়।

তবে সব Numeric Operation-এর আচরণ এক নয়। যেমন, `/` Division সাধারণত Float result দেয়।

```python
print(10 / 2)
print(10 // 3)
```

Output:

```text
5.0
3
```

### 3.2 String Operations

String-এর সঙ্গে String concatenate করা যায়।

```python
first = "Hello"
second = "Python"

print(first + " " + second)
```

Output:

```text
Hello Python
```

String-এর সঙ্গে Integer সরাসরি concatenate করা যায় না।

```python
age = 22

# print("Age: " + age)  # TypeError
print("Age: " + str(age))
```

Output:

```text
Age: 22
```

আরও সহজভাবে String Formatting ব্যবহার করা যায়:

```python
age = 22

print(f"Age: {age}")
```

Output:

```text
Age: 22
```

### 3.3 List Operations

দুটি List concatenate করা যায়।

```python
a = [1, 2]
b = [3, 4]

print(a + b)
```

Output:

```text
[1, 2, 3, 4]
```

কিন্তু List-এর সঙ্গে Integer সরাসরি `+` ব্যবহার করা যায় না।

```python
numbers = [1, 2, 3]

# print(numbers + 4)  # TypeError
```

একটি element যোগ করতে `append()` ব্যবহার করো।

```python
numbers = [1, 2, 3]
numbers.append(4)

print(numbers)
```

Output:

```text
[1, 2, 3, 4]
```

### 3.4 Dictionary Operations

Dictionary-তে key ব্যবহার করে value access করা হয়।

```python
student = {
    "name": "Masum",
    "age": 22
}

print(student["name"])
```

Output:

```text
Masum
```

Dictionary-তে অনুপস্থিত key ব্যবহার করলে সাধারণত `KeyError` হয়।

```python
student = {"name": "Masum"}

# print(student["cgpa"])  # KeyError
print(student.get("cgpa"))
```

Output:

```text
None
```

`get()` ব্যবহার করলে key না থাকলে default হিসেবে `None` পাওয়া যায়। চাইলে নিজের default value-ও দিতে পারো।

```python
print(student.get("cgpa", 0.0))
```

Output:

```text
0.0
```

## 4. TypeError

`TypeError` ঘটে যখন কোনো Operation বা Function-এর জন্য উপযুক্ত Type-এর object দেওয়া হয় না।

Example:

```python
number = 10
text = "20"

# print(number + text)  # TypeError
```

সঠিক উপায়:

```python
number = 10
text = "20"

print(number + int(text))
```

Output:

```text
30
```

আরেকটি Example:

```python
numbers = [10, 20, 30]

# numbers.append()  # TypeError: argument missing
numbers.append(40)

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

**সমাধান:** Error message পড়ো, Operation কী ধরনের argument চায় তা বুঝে উপযুক্ত Type ব্যবহার করো।

## 5. ValueError

`ValueError` ঘটে যখন সঠিক ধরনের object দেওয়া হলেও তার value নির্দিষ্ট Operation-এর জন্য গ্রহণযোগ্য নয়।

Example:

```python
number = int("hello")
```

এখানে `"hello"` একটি String। কিন্তু এটি বৈধ Integer representation নয়। তাই `ValueError` হবে।

সঠিক Example:

```python
number = int("123")

print(number)
```

Output:

```text
123
```

User Input-এর ক্ষেত্রেও এমন Error হতে পারে।

```python
user_input = "abc"

try:
    age = int(user_input)
    print(age)
except ValueError:
    print("Please enter a valid integer.")
```

Output:

```text
Please enter a valid integer.
```

**TypeError এবং ValueError-এর পার্থক্য:**

- `TypeError`: Operation-এর জন্য উপযুক্ত Type নেই।
- `ValueError`: Type গ্রহণযোগ্য, কিন্তু Value গ্রহণযোগ্য নয়।

## 6. IndexError

List, Tuple বা String-এর বৈধ Index-এর বাইরে কোনো Position access করলে `IndexError` হয়।

```python
numbers = [10, 20, 30]

# print(numbers[5])  # IndexError
print(numbers[2])
```

Output:

```text
30
```

List-এর Length পরীক্ষা করে নিরাপদে access করা যায়।

```python
numbers = [10, 20, 30]
index = 2

if 0 <= index < len(numbers):
    print(numbers[index])
else:
    print("Invalid index.")
```

Output:

```text
30
```

মনে রাখবে, Python-এর Index `0` থেকে শুরু হয়। তিনটি element-এর Index হলো `0`, `1` এবং `2`।

## 7. KeyError

Dictionary-তে নেই এমন Key সরাসরি access করলে `KeyError` হয়।

```python
student = {
    "name": "Masum",
    "department": "CSE"
}

# print(student["cgpa"])  # KeyError
```

সমাধান:

```python
student = {
    "name": "Masum",
    "department": "CSE"
}

if "cgpa" in student:
    print(student["cgpa"])
else:
    print("CGPA is not available.")
```

Output:

```text
CGPA is not available.
```

অথবা `get()` ব্যবহার করা যায়।

```python
print(student.get("cgpa", "Not available"))
```

Output:

```text
Not available
```

## 8. AttributeError

কোনো Object-এর মধ্যে নেই এমন Attribute বা Method ব্যবহার করলে `AttributeError` হতে পারে।

Example:

```python
number = 10

# number.append(20)  # AttributeError
```

Integer-এর `append()` Method নেই। `append()` List-এর মতো Mutable Sequence-এ ব্যবহৃত হয়।

সঠিক Example:

```python
numbers = [10, 20]
numbers.append(30)

print(numbers)
```

Output:

```text
[10, 20, 30]
```

**সমাধান:** Object-এর Type যাচাই করো এবং সেই Type-এর জন্য উপযুক্ত Method ব্যবহার করো।

## 9. ZeroDivisionError

কোনো Number-কে শূন্য দিয়ে Divide করলে `ZeroDivisionError` হয়।

```python
# print(10 / 0)  # ZeroDivisionError
```

সমাধান:

```python
number = 10
divisor = 0

if divisor != 0:
    print(number / divisor)
else:
    print("Cannot divide by zero.")
```

Output:

```text
Cannot divide by zero.
```

## 10. Type Checking Before an Operation

কোনো Operation করার আগে প্রয়োজন অনুযায়ী Type পরীক্ষা করা যায়।

### Using `isinstance()`

```python
value = 100

if isinstance(value, int):
    print(value + 10)
else:
    print("An integer is required.")
```

Output:

```text
110
```

তবে `bool` হলো `int`-এর একটি Subclass। তাই `isinstance(True, int)`-এর ফল `True`।

যদি Boolean-কে বাদ দিয়ে শুধু Integer গ্রহণ করতে চাও:

```python
value = True

if type(value) is int:
    print("Integer")
else:
    print("Not an exact integer type")
```

Output:

```text
Not an exact integer type
```

সাধারণ ক্ষেত্রে `isinstance()` বেশি উপযোগী। `type(value) is int` শুধু তখন ব্যবহার করো যখন exact type পরীক্ষা করা প্রয়োজন।

## 11. Type Conversion to Solve Compatibility Problems

অনেক Type Compatibility Problem সঠিক Type Conversion-এর মাধ্যমে সমাধান করা যায়।

### Example 1: String to Integer

```python
a = "10"
b = "20"

result = int(a) + int(b)

print(result)
```

Output:

```text
30
```

### Example 2: Integer to String

```python
age = 22

message = "Age: " + str(age)

print(message)
```

Output:

```text
Age: 22
```

### Example 3: String to Float

```python
price = "125.50"

total = float(price) + 10

print(total)
```

Output:

```text
135.5
```

**সতর্কতা:** সব String সফলভাবে Number-এ convert করা যায় না। User Input convert করার আগে invalid value-এর সম্ভাবনা বিবেচনা করো।

## 12. Common Mistakes and Their Solutions

| Mistake | Problem | Solution |
|---|---|---|
| String ও Integer যোগ করা | `TypeError` | `str()` বা `int()` ব্যবহার |
| Invalid String-কে Integer করা | `ValueError` | Value যাচাই বা `try-except` |
| List-এর বাইরে Index access | `IndexError` | Index ও `len()` পরীক্ষা |
| Missing Dictionary Key access | `KeyError` | `get()` বা key membership check |
| ভুল Object Method ব্যবহার | `AttributeError` | সঠিক Type-এর Method ব্যবহার |
| Zero দিয়ে Division | `ZeroDivisionError` | Divisor পরীক্ষা |
| Number-এর বদলে String নিয়ে Arithmetic | ভুল Result বা Error | প্রয়োজনমতো Conversion |

## 13. General Error-Handling Pattern

যে Operation-এ নির্দিষ্ট Error হওয়ার সম্ভাবনা আছে, সেটি `try-except` দিয়ে handle করা যায়।

```python
user_input = input("Enter a number: ")

try:
    number = int(user_input)
    result = number * 2
except ValueError:
    print("Invalid input. Please enter an integer.")
else:
    print("Result:", result)
```

Example Input:

```text
Enter a number: 15
```

Output:

```text
Result: 30
```

Invalid Input দিলে:

```text
Enter a number: hello
Invalid input. Please enter an integer.
```

এখানে:

- `try`: সম্ভাব্য Error-যুক্ত Code।
- `except`: নির্দিষ্ট Error হলে কী করতে হবে।
- `else`: Error না হলে যে Code চলবে।

অপ্রয়োজনীয়ভাবে সব Error ধরার জন্য `except Exception` বা bare `except` ব্যবহার না করে সম্ভব হলে নির্দিষ্ট Exception ধরো।

## 14. Best Practices

1. Operation করার আগে Data Type সম্পর্কে নিশ্চিত হও।
2. Error Message মনোযোগ দিয়ে পড়ো।
3. User Input-এর ক্ষেত্রে Invalid Value-এর সম্ভাবনা বিবেচনা করো।
4. প্রয়োজন অনুযায়ী `int()`, `float()` বা `str()` ব্যবহার করো।
5. List Index ও Dictionary Key access করার সময় সম্ভাব্য Error বিবেচনা করো।
6. নির্দিষ্ট Error ধরতে উপযুক্ত `try-except` ব্যবহার করো।
7. শুধু Error এড়ানোর জন্য Data Type পরিবর্তন না করে সমস্যার মূল কারণ বোঝার চেষ্টা করো।
8. `is` ও `==`-এর পার্থক্য বুঝে ব্যবহার করো।

## 15. Practice Exercises

### Exercise 1: Identify the Error

নিচের Code-এ কী Error হবে তা চিহ্নিত করো।

```python
number = 10
text = "5"

print(number + text)
```

### Exercise 2: Fix the TypeError

Code-টি ঠিক করো যাতে Output `15` হয়।

```python
number = 10
text = "5"

# Fix the code
```

### Exercise 3: Handle ValueError

User Input থেকে Integer নেওয়ার একটি Program লেখো। Invalid Input হলে Error Message দেখাবে।

### Exercise 4: Prevent IndexError

```python
numbers = [10, 20, 30]
index = 5
```

Index বৈধ হলে element print করবে, অন্যথায় `"Invalid index"` দেখাবে।

### Exercise 5: Handle KeyError

```python
student = {
    "name": "Masum",
    "department": "CSE"
}
```

Dictionary থেকে `cgpa` access করো। Key না থাকলে `"CGPA not available"` দেখাও।

### Exercise 6: Prevent ZeroDivisionError

দুটি Number নিয়ে Division করার Program লেখো। Divisor `0` হলে Division করবে না।

### Exercise 7: Debug the Program

```python
numbers = [10, 20, 30]

numbers.append(40)
print(numbers[4])
```

কেন Error হচ্ছে? Code-টি ঠিক করো।

### Exercise 8: Mini Project — Safe Calculator

একটি Simple Calculator তৈরি করো, যা:

1. দুটি Number Input নেবে।
2. Addition, Subtraction ও Multiplication করবে।
3. Division করবে শুধু Divisor শূন্য না হলে।
4. Invalid Numeric Input হলে উপযুক্ত Message দেখাবে।

## 16. Key Takeaways

- Type Compatibility নির্ভর করে Data Type ও Operation-এর ওপর।
- `TypeError` সাধারণত Operation-এর জন্য উপযুক্ত Type না থাকলে হয়।
- `ValueError` হয় যখন Value নির্দিষ্ট Operation-এর জন্য গ্রহণযোগ্য নয়।
- `IndexError` List, Tuple বা String-এর বৈধ Index-এর বাইরে access করলে হয়।
- `KeyError` Dictionary-তে অনুপস্থিত Key access করলে হয়।
- `AttributeError` হয় অনুপস্থিত Attribute বা Method ব্যবহার করলে।
- `ZeroDivisionError` হয় শূন্য দিয়ে Division করলে।
- সঠিক Type Conversion অনেক Compatibility Problem সমাধান করতে পারে।
- `try-except` দিয়ে প্রত্যাশিত Error নিরাপদে handle করা যায়।

## 17. Next Topic

পরবর্তী ফাইল:

**`30_Choosing_the_Right_Data_Type.md`**

সেখানে বিভিন্ন Problem-এর জন্য সঠিক Data Type কীভাবে নির্বাচন করতে হয়, তা Practical Example-এর মাধ্যমে শেখা হবে।