# 09. Identifiers and Naming Rules in Python

## 1. Introduction to Identifiers

**Identifier** হলো Python program-এর কোনো variable, function, class, module বা অন্য named object-কে চিহ্নিত করার জন্য দেওয়া নাম।

সহজভাবে বললে, code-এর মধ্যে কোনো কিছুর নাম দেওয়ার জন্য আমরা identifier ব্যবহার করি।

উদাহরণ:

```python
student_name = "Masum"
age = 22

def calculate_total():
    return 100

class Student:
    pass
```

এখানে:

- `student_name` — variable identifier
- `age` — variable identifier
- `calculate_total` — function identifier
- `Student` — class identifier

Identifier ব্যবহার করার ফলে program-এর বিভিন্ন অংশকে সহজে চেনা ও ব্যবহার করা যায়।

## 2. Why Are Identifiers Important?

ভালো identifier ব্যবহার করলে code পড়া, বোঝা, debug করা এবং maintain করা সহজ হয়।

উদাহরণ:

```python
a = 85
b = 90
c = (a + b) / 2

print(c)
```

Output:

```text
87.5
```

Code-টি কাজ করছে, কিন্তু `a`, `b` এবং `c` কী বোঝাচ্ছে, তা নাম দেখে পরিষ্কার নয়।

আরও ভালোভাবে লেখা যায়:

```python
math_marks = 85
english_marks = 90

average_marks = (math_marks + english_marks) / 2

print(average_marks)
```

Output:

```text
87.5
```

এখানে variable-গুলোর নাম দেখেই বোঝা যায় কোন variable-এ কী রাখা হয়েছে।

**মূল কথা:** Identifier শুধু নাম নয়; এটি code-এর অর্থ ও উদ্দেশ্য বোঝাতেও সাহায্য করে।

## 3. Rules for Naming Identifiers

Python-এ identifier তৈরি করার জন্য কিছু নির্দিষ্ট নিয়ম রয়েছে।

### Rule 1: An Identifier Can Contain Letters

ইংরেজি uppercase ও lowercase letters ব্যবহার করা যায়।

```python
name = "Masum"
Name = "Ritu"
studentName = "Rahim"
```

এগুলো সব valid identifiers।

### Rule 2: An Identifier Can Contain Digits

Identifier-এর মধ্যে digit `0` থেকে `9` পর্যন্ত ব্যবহার করা যায়, তবে প্রথম character হিসেবে digit ব্যবহার করা যায় না।

Valid:

```python
student1 = "Masum"
marks2026 = 85
section9A = "CSE"
```

Invalid:

```python
1student = "Masum"
2026marks = 85
```

কারণ identifier-এর শুরুতে digit থাকলে Python সেটিকে valid identifier হিসেবে গ্রহণ করে না।

### Rule 3: An Identifier Can Start with an Underscore

Identifier-এর প্রথম character হিসেবে underscore (`_`) ব্যবহার করা যায়।

উদাহরণ:

```python
_student_name = "Masum"
_private_value = 100
_total = 500
```

এগুলো valid identifiers।

Python-এ underscore-এর কিছু বিশেষ convention আছে, যা পরে আলোচনা করা হবে।

### Rule 4: Spaces Are Not Allowed

Identifier-এর মধ্যে space ব্যবহার করা যায় না।

Invalid:

```python
student name = "Masum"
total marks = 85
```

Valid:

```python
student_name = "Masum"
total_marks = 85
```

একাধিক শব্দের মধ্যে space-এর পরিবর্তে সাধারণত underscore ব্যবহার করা হয়।

### Rule 5: Special Characters Are Generally Not Allowed

সাধারণ identifier-এ নিচের মতো special characters ব্যবহার করা যায় না:

- `@`
- `#`
- `$`
- `%`
- `-`
- `!`

Invalid:

```python
student-name = "Masum"
total@marks = 85
user#name = "Masum"
```

Valid:

```python
student_name = "Masum"
total_marks = 85
user_name = "Masum"
```

**Note:** সাধারণ identifier-এর ক্ষেত্রে underscore (`_`) ব্যবহার করা যায়। Unicode letters-ও Python-এর identifier rules অনুযায়ী অনুমোদিত হতে পারে, তবে professional code-এ সাধারণত English letters ব্যবহার করা বেশি প্রচলিত।

### Rule 6: Keywords Cannot Be Used as Identifiers

Python keywords-এর নির্দিষ্ট অর্থ রয়েছে। তাই এগুলোকে সাধারণ identifier হিসেবে ব্যবহার করা যায় না।

Invalid:

```python
if = 10
class = "CSE"
return = 50
```

Valid:

```python
if_value = 10
class_name = "CSE"
return_value = 50
```

### Rule 7: Identifiers Are Case-Sensitive

Python-এ uppercase ও lowercase letters আলাদা হিসেবে বিবেচিত হয়।

```python
name = "Masum"
Name = "Ritu"
NAME = "Rahim"

print(name)
print(Name)
print(NAME)
```

Output:

```text
Masum
Ritu
Rahim
```

এখানে `name`, `Name` এবং `NAME` তিনটি আলাদা identifier।

### Rule 8: Identifiers Cannot Start with a Digit

এটি বিশেষভাবে মনে রাখতে হবে।

Invalid:

```python
9section = "A"
2026year = 2026
```

Valid:

```python
section9 = "A"
year2026 = 2026
```

Digit নামের শুরুতে নয়, পরে ব্যবহার করা যায়।

## 4. Valid and Invalid Identifiers

নিচের table-এ কিছু উদাহরণ দেওয়া হলো।

| Identifier | Valid or Invalid | Reason |
|---|---|---|
| `name` | Valid | Letter দিয়ে শুরু |
| `student_name` | Valid | Underscore ব্যবহার করা হয়েছে |
| `_total` | Valid | Underscore দিয়ে শুরু |
| `marks2026` | Valid | Digit শুরুতে নেই |
| `studentName` | Valid | CamelCase style |
| `student name` | Invalid | Space আছে |
| `2marks` | Invalid | Digit দিয়ে শুরু |
| `student-name` | Invalid | Hyphen আছে |
| `total@marks` | Invalid | Special character আছে |
| `if` | Invalid | Python keyword |
| `class` | Invalid | Python keyword |
| `first_name` | Valid | Underscore দিয়ে শব্দ আলাদা করা হয়েছে |

## 5. Python Naming Conventions

Identifier naming rules এবং naming conventions এক জিনিস নয়।

- **Naming rules:** নামটি syntactically valid কি না নির্ধারণ করে।
- **Naming conventions:** নাম কীভাবে লিখলে code আরও readable ও consistent হবে, তা নির্দেশ করে।

একটি নাম valid হলেও সেটি সবসময় ভালো naming convention অনুসরণ নাও করতে পারে।

উদাহরণ:

```python
StudentName = "Masum"
```

এটি valid identifier। কিন্তু সাধারণ variable-এর জন্য Python-এ `student_name` style বেশি প্রচলিত।

## 6. Snake Case

**Snake case**-এ একাধিক শব্দ lowercase-এ লেখা হয় এবং শব্দগুলোর মধ্যে underscore (`_`) ব্যবহার করা হয়।

উদাহরণ:

```python
student_name = "Masum"
total_marks = 250
average_marks = 83.33
calculate_total = 100
```

Python-এ সাধারণত নিচের ক্ষেত্রে snake case ব্যবহার করা হয়:

- Variable names
- Function names
- Module names

উদাহরণ:

```python
def calculate_average(total_marks, subject_count):
    return total_marks / subject_count

print(calculate_average(270, 3))
```

Output:

```text
90.0
```

## 7. PascalCase

**PascalCase**-এ প্রতিটি শব্দের প্রথম অক্ষর uppercase হয় এবং শব্দগুলোর মধ্যে space বা underscore থাকে না।

উদাহরণ:

```python
Student
BankAccount
UniversityStudent
StudentManagementSystem
```

Python-এ সাধারণত class name লেখার জন্য PascalCase ব্যবহার করা হয়।

উদাহরণ:

```python
class Student:
    def __init__(self, name):
        self.name = name

student = Student("Masum")

print(student.name)
```

Output:

```text
Masum
```

এখানে `Student` হলো class name এবং `student` হলো variable name।

## 8. CamelCase

**CamelCase**-এ প্রথম শব্দটি lowercase দিয়ে শুরু হয় এবং পরবর্তী শব্দগুলোর প্রথম অক্ষর uppercase হয়।

উদাহরণ:

```python
studentName = "Masum"
totalMarks = 250
averageMarks = 83.33
```

CamelCase Python-এ valid, কিন্তু সাধারণ variable ও function-এর জন্য snake case বেশি প্রচলিত এবং PEP 8 style guide-এর সঙ্গে সামঞ্জস্যপূর্ণ।

অন্য programming language, যেমন Java বা JavaScript-এ camelCase বেশি ব্যবহৃত হয়।

## 9. Naming Conventions at a Glance

| Element | Recommended Style | Example |
|---|---|---|
| Variable | `snake_case` | `student_name` |
| Function | `snake_case` | `calculate_total()` |
| Class | `PascalCase` | `StudentRecord` |
| Module | `snake_case` | `student_data.py` |
| Package | সাধারণত lowercase | `studenttools` |
| Constant | `UPPER_SNAKE_CASE` | `MAX_MARKS` |
| Internal-use name | `_leading_underscore` | `_internal_value` |

এগুলো naming conventions, কঠোর syntax rules নয়। Project-এর context অনুযায়ী consistency বজায় রাখা জরুরি।

## 10. Naming Constants

Python-এ constant-এর জন্য আলাদা কোনো সাধারণ assignment syntax নেই। Convention অনুযায়ী এমন variable-এর নাম `UPPER_SNAKE_CASE`-এ লেখা হয়, যার value program চলাকালে পরিবর্তন করার কথা নয়।

উদাহরণ:

```python
PI = 3.14159
MAX_MARKS = 100
DEFAULT_LANGUAGE = "English"
```

এগুলো convention অনুযায়ী constants।

তবে মনে রাখবে, শুধু uppercase নাম ব্যবহার করলেই Python variable-টিকে immutable বা unchangeable করে দেয় না।

উদাহরণ:

```python
MAX_MARKS = 100
MAX_MARKS = 120

print(MAX_MARKS)
```

Output:

```text
120
```

Python assignment-টি অনুমোদন করে। Constant convention মূলত programmer-কে variable-এর উদ্দেশ্য বোঝাতে সাহায্য করে।

## 11. Meaningful and Descriptive Names

ভালো identifier এমন হওয়া উচিত, যা নাম দেখেই মোটামুটি বোঝা যায় এর কাজ কী।

### Bad Naming

```python
x = 500
y = 10
z = x * y

print(z)
```

এখানে variable-গুলোর উদ্দেশ্য পরিষ্কার নয়।

### Better Naming

```python
product_price = 500
quantity = 10

total_price = product_price * quantity

print(total_price)
```

Output:

```text
5000
```

এখানে variable-এর নাম code-এর logic বুঝতে সাহায্য করছে।

### Avoid Unclear Abbreviations

কম পরিষ্কার:

```python
std_mrk = 85
avg_mrk = 90
```

আরও পরিষ্কার:

```python
student_marks = 85
average_marks = 90
```

তবে `id`, `url` বা প্রচলিত technical abbreviations context অনুযায়ী ব্যবহার করা যেতে পারে।

## 12. Using Underscores in Identifiers

Python-এ underscore-এর কয়েকটি প্রচলিত ব্যবহার রয়েছে।

### 12.1 Leading Underscore

একটি underscore দিয়ে শুরু হওয়া নাম অনেক সময় internal-use identifier বোঝাতে ব্যবহৃত হয়।

```python
_internal_value = 100
```

এটি মূলত একটি convention। সাধারণভাবে `_internal_value`-কে ব্যবহার করতে Python বাধা দেয় না।

### 12.2 Trailing Underscore

কোনো নাম keyword-এর সঙ্গে মিলে গেলে শেষে underscore যোগ করা যায়।

```python
class_ = "CSE"
type_ = "Student"
```

এখানে `class_` valid identifier, কিন্তু `class` নয়।

### 12.3 Double Leading Underscore in Classes

Class-এর ভেতরে double leading underscore ব্যবহার করলে Python name mangling প্রয়োগ করতে পারে।

```python
class Student:
    def __init__(self):
        self.__marks = 85
```

এটি class attribute-এর নামকে পরিবর্তিতভাবে সংরক্ষণ করতে সাহায্য করে। এটি সরাসরি security বা absolute privacy নিশ্চিত করে না।

এই বিষয়টি Object-Oriented Programming chapter-এ বিস্তারিত শেখা হবে।

### 12.4 Double Leading and Trailing Underscores

`__init__`, `__str__` এবং `__len__`-এর মতো নাম Python-এর special method বা *dunder methods* হিসেবে পরিচিত।

উদাহরণ:

```python
class Student:
    def __init__(self, name):
        self.name = name
```

সাধারণত নিজের ইচ্ছামতো নতুন dunder name তৈরি না করে Python-এর নির্ধারিত special method-গুলোই ব্যবহার করা উচিত।

## 13. Unicode Identifiers

Python-এ কিছু non-English letters-ও identifier হিসেবে ব্যবহার করা সম্ভব, যদি সেগুলো Python-এর identifier rules মেনে চলে।

উদাহরণ:

```python
café = "Coffee"
print(café)
```

Output:

```text
Coffee
```

তবে team project, open-source project এবং professional code-এ সাধারণত English identifiers ব্যবহার করা সুবিধাজনক। এতে বিভিন্ন keyboard, editor এবং development environment-এ কাজ করা সহজ হয়।

বাংলা বা অন্য ভাষার identifier technically সম্ভব হলেও শেখার শুরুতে English naming convention অনুসরণ করাই ভালো।

## 14. Identifiers and Scope

একই নামের variable বিভিন্ন scope-এ থাকতে পারে। Scope হলো program-এর কোন অংশ থেকে কোনো name ব্যবহার করা যায়, তার পরিসর।

উদাহরণ:

```python
name = "Masum"

def show_name():
    name = "Ritu"
    print(name)

show_name()
print(name)
```

Output:

```text
Ritu
Masum
```

এখানে দুটি `name` identifier ভিন্ন scope-এ ব্যবহৃত হয়েছে।

- Function-এর ভেতরের `name` হলো local variable।
- Function-এর বাইরের `name` হলো global variable।

একই identifier-এর নাম থাকলেও scope-এর কারণে তারা আলাদা binding নির্দেশ করতে পারে।

Local ও global scope-এর বিস্তারিত আলোচনা পরবর্তী Function chapter-এ করা হবে।

## 15. Common Beginner Mistakes

### Mistake 1: Using Spaces

ভুল:

```python
student name = "Masum"
```

সঠিক:

```python
student_name = "Masum"
```

### Mistake 2: Starting with a Digit

ভুল:

```python
1st_student = "Masum"
```

সঠিক:

```python
student_1 = "Masum"
```

### Mistake 3: Using a Keyword

ভুল:

```python
return = 100
```

সঠিক:

```python
return_value = 100
```

### Mistake 4: Confusing Uppercase and Lowercase

```python
student_name = "Masum"
Student_Name = "Ritu"

print(student_name)
print(Student_Name)
```

Output:

```text
Masum
Ritu
```

দুটি আলাদা identifier হওয়ায় দুটি আলাদা value পাওয়া যাচ্ছে।

### Mistake 5: Choosing Meaningless Names

কম পরিষ্কার:

```python
a = 85
b = 90
```

আরও পরিষ্কার:

```python
math_marks = 85
english_marks = 90
```

### Mistake 6: Using Hyphens

ভুল:

```python
total-marks = 100
```

এখানে `-` identifier-এর অংশ নয়; Python এটিকে subtraction operator হিসেবে ব্যাখ্যা করার চেষ্টা করবে।

সঠিক:

```python
total_marks = 100
```

## 16. Practical Examples

### Example 1: Student Information

```python
student_name = "Masum"
student_id = 1350
department_name = "CSE"
total_marks = 450

print("Name:", student_name)
print("ID:", student_id)
print("Department:", department_name)
print("Total Marks:", total_marks)
```

Output:

```text
Name: Masum
ID: 1350
Department: CSE
Total Marks: 450
```

### Example 2: Function with Meaningful Names

```python
def calculate_average(total_marks, subject_count):
    average_marks = total_marks / subject_count
    return average_marks

result = calculate_average(270, 3)

print("Average:", result)
```

Output:

```text
Average: 90.0
```

### Example 3: Using a Constant

```python
PASS_MARKS = 40

student_marks = 75

if student_marks >= PASS_MARKS:
    print("Pass")
else:
    print("Fail")
```

Output:

```text
Pass
```

এখানে `PASS_MARKS` uppercase naming convention অনুসরণ করছে এবং এর উদ্দেশ্যও পরিষ্কার।

## 17. Practice Exercises

### Exercise 1: Identify Valid Identifiers

নিচের কোনগুলো valid identifier, তা চিহ্নিত করো:

- `student_name`
- `2student`
- `_marks`
- `total-marks`
- `student2`
- `class`
- `StudentName`
- `total_marks_2026`

### Exercise 2: Correct the Invalid Names

নিচের invalid identifier-গুলোকে valid নামে পরিবর্তন করো:

```python
# Invalid examples
# 1name = "Masum"
# student name = "Masum"
# total-marks = 100
# class = "CSE"
```

### Exercise 3: Follow Naming Conventions

নিচের নামগুলোকে Python-এর প্রচলিত naming conventions অনুযায়ী লেখো:

1. Variable: student name
2. Function: calculate total
3. Class: student record
4. Constant: maximum marks
5. Module: student data

### Exercise 4: Improve the Code

নিচের code-টিকে আরও readable করো।

```python
a = 80
b = 90
c = 85
d = (a + b + c) / 3

print(d)
```

Variable-গুলোর meaningful নাম ব্যবহার করো।

### Exercise 5: Find the Output

```python
name = "Masum"
Name = "Ritu"

print(name)
print(Name)
```

Output কী হবে এবং কেন?

### Exercise 6: Explain in Your Own Words

1. Identifier কী?
2. Identifier-এর প্রথম character হিসেবে কী ব্যবহার করা যায়?
3. Identifier-এর মধ্যে space ব্যবহার করা যায় কি?
4. Snake case ও PascalCase-এর পার্থক্য কী?
5. Python-এ constants-এর জন্য কোন naming convention ব্যবহৃত হয়?
6. Underscore দিয়ে শুরু হওয়া নাম কী বোঝাতে পারে?

## 18. Quick Revision

| Rule | Example |
|---|---|
| Letter দিয়ে শুরু হতে পারে | `student` |
| Underscore দিয়ে শুরু হতে পারে | `_student` |
| Digit পরে ব্যবহার করা যায় | `student2` |
| Digit দিয়ে শুরু করা যায় না | `2student` |
| Space ব্যবহার করা যায় না | `student_name` |
| Keyword ব্যবহার করা যায় না | `class_name` |
| Case-sensitive | `name` ও `Name` আলাদা |
| Variable-এর convention | `student_name` |
| Function-এর convention | `calculate_total()` |
| Class-এর convention | `StudentRecord` |
| Constant-এর convention | `MAX_MARKS` |

## 19. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Identifier হলো variable, function, class এবং অন্যান্য named object-এর নাম।
- Identifier letter বা underscore দিয়ে শুরু হতে পারে।
- Identifier-এর মধ্যে digit ব্যবহার করা যায়, তবে শুরুতে নয়।
- সাধারণ identifier-এ space এবং অধিকাংশ special character ব্যবহার করা যায় না।
- Python keywords সাধারণ identifier হিসেবে ব্যবহার করা যায় না।
- Python case-sensitive।
- Variable ও function-এর জন্য snake case এবং class-এর জন্য PascalCase প্রচলিত।
- Constants-এর জন্য সাধারণত `UPPER_SNAKE_CASE` ব্যবহার করা হয়।
- Meaningful identifiers code-কে readable এবং maintainable করে।
- Underscore-এর কিছু প্রচলিত convention রয়েছে, যেগুলোর অর্থ context অনুযায়ী বদলাতে পারে।

## 20. Next Topic

পরবর্তী ফাইল: [`10_Variables_in_Python.md`](10_Variables_in_Python.md)

এখানে আমরা variable কী, variable কীভাবে কাজ করে, value ও object-এর সম্পর্ক, dynamic typing, variable creation এবং practical examples বিস্তারিতভাবে শিখব।