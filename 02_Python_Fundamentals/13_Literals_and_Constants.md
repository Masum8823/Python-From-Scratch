# 13. Literals and Constants in Python

## 1. Introduction

Python-এ program লেখার সময় আমরা বিভিন্ন value ব্যবহার করি। যেমন: `10`, `3.14`, `"Python"`, `True` এবং `None`।

এই value-গুলো সরাসরি code-এর মধ্যে লিখলে সেগুলোকে **Literals** বলা হয়।

অন্যদিকে, program-এর মধ্যে এমন কিছু value থাকে যেগুলো পরিবর্তন করার প্রয়োজন হয় না বা করা উচিত নয়। এগুলোকে **Constants** হিসেবে ব্যবহার করা হয়।

উদাহরণ:

```python
age = 22
name = "Masum"
PI = 3.14159
is_student = True
```

এখানে:

- `22` হলো integer literal।
- `"Masum"` হলো string literal।
- `3.14159` হলো floating-point literal।
- `True` হলো Boolean literal।
- `PI` হলো constant হিসেবে ব্যবহৃত একটি variable name।

এই topic-এ আমরা শিখব:

- Literal কী
- Literal-এর বিভিন্ন ধরন
- Numeric, string ও Boolean literals
- `None` literal
- Collection literals
- Constants ও naming conventions
- Common mistakes এবং practical examples

## 2. What Is a Literal?

**Literal** হলো এমন একটি value, যা সরাসরি source code-এর মধ্যে লেখা হয়।

উদাহরণ:

```python
x = 100
name = "Python"
price = 99.50
is_valid = True
```

এখানে `100`, `"Python"`, `99.50` এবং `True` হলো literals।

### More Examples

```python
print(25)
print(3.14)
print("Hello World")
print(False)
print(None)
```

Output:

```text
25
3.14
Hello World
False
None
```

### Literal vs Variable

Literal এবং variable এক জিনিস নয়।

```python
age = 22
print(age)
```

এখানে:

- `22` হলো literal।
- `age` হলো variable name।
- `age = 22` হলো assignment statement।

Literal হলো সরাসরি লেখা value, আর variable name হলো সেই object-কে refer করার জন্য ব্যবহৃত নাম।

## 3. Types of Literals in Python

Python-এ বিভিন্ন ধরনের literal রয়েছে।

| Literal Type | Example | Description |
|---|---|---|
| Integer | `100` | পূর্ণসংখ্যা |
| Float | `3.14` | দশমিক বা floating-point number |
| Complex | `2 + 3j` | Complex number |
| String | `"Python"` | Text data |
| Boolean | `True`, `False` | সত্য বা মিথ্যা বোঝায় |
| None | `None` | কোনো value নেই বা অনুপস্থিত বোঝায় |
| List | `[1, 2, 3]` | Ordered, mutable collection |
| Tuple | `(1, 2, 3)` | Ordered, immutable collection |
| Dictionary | `{"name": "Masum"}` | Key-value collection |
| Set | `{1, 2, 3}` | Unique elements-এর collection |

এখন প্রতিটি গুরুত্বপূর্ণ literal বিস্তারিতভাবে দেখি।

## 4. Numeric Literals

Numeric literals হলো code-এর মধ্যে সরাসরি লেখা numeric value।

Python-এ প্রধান numeric literal তিন ধরনের:

1. Integer literals
2. Floating-point literals
3. Complex literals

### 4.1 Integer Literals

Integer literal হলো পূর্ণসংখ্যার value।

উদাহরণ:

```python
age = 22
marks = 85
temperature = -5

print(age)
print(marks)
print(temperature)
```

Output:

```text
22
85
-5
```

Integer-এর মধ্যে decimal point থাকে না।

### Integer Literals in Different Number Systems

Python-এ integer-কে বিভিন্ন number system-এ লেখা যায়।

| Number System | Prefix | Example | Decimal Value |
|---|---|---|---:|
| Decimal | নেই | `100` | 100 |
| Binary | `0b` | `0b1010` | 10 |
| Octal | `0o` | `0o12` | 10 |
| Hexadecimal | `0x` | `0xA` | 10 |

উদাহরণ:

```python
print(100)
print(0b1010)
print(0o12)
print(0xA)
```

Output:

```text
100
10
10
10
```

এখানে চারটি literal ভিন্ন notation-এ লেখা হলেও তাদের numeric value একই নয় সব ক্ষেত্রে—এই উদাহরণে সবগুলোর value যথাক্রমে `100`, `10`, `10` ও `10`।

### Underscores in Numeric Literals

বড় সংখ্যা সহজে পড়ার জন্য digit-এর মাঝে underscore ব্যবহার করা যায়।

```python
population = 10_000_000

print(population)
```

Output:

```text
10000000
```

Underscore শুধু readability বাড়ায়; এটি numeric value পরিবর্তন করে না।

### 4.2 Floating-Point Literals

Floating-point literal সাধারণত decimal point-সহ সংখ্যা প্রকাশ করে।

উদাহরণ:

```python
price = 99.50
cgpa = 3.95
temperature = -2.5

print(price)
print(cgpa)
print(temperature)
```

Output:

```text
99.5
3.95
-2.5
```

Python-এর floating-point representation-এর কারণে কিছু decimal value-তে সামান্য precision difference দেখা যেতে পারে।

উদাহরণ:

```python
print(0.1 + 0.2)
```

Output:

```text
0.30000000000000004
```

এটি floating-point representation-এর একটি পরিচিত বৈশিষ্ট্য।

### Scientific Notation

বড় বা ছোট floating-point number scientific notation-এ লেখা যায়।

```python
large_number = 1.5e3
small_number = 2.5e-3

print(large_number)
print(small_number)
```

Output:

```text
1500.0
0.0025
```

এখানে:

- `1.5e3` অর্থ \(1.5 \times 10^3\)।
- `2.5e-3` অর্থ \(2.5 \times 10^{-3}\)।

### 4.3 Complex Literals

Complex number-এ real এবং imaginary অংশ থাকে। Python-এ imaginary অংশ প্রকাশ করতে `j` ব্যবহার করা হয়।

উদাহরণ:

```python
number = 2 + 3j

print(number)
print(type(number))
```

Output:

```text
(2+3j)
<class 'complex'>
```

এখানে:

- Real part হলো `2`।
- Imaginary part হলো `3j`।

Complex number সাধারণ arithmetic ও scientific computing-এ কাজে লাগে।

## 5. String Literals

String literal হলো quotation marks-এর মধ্যে লেখা text।

Python-এ single quotes, double quotes এবং triple quotes ব্যবহার করা যায়।

### 5.1 Single Quotes

```python
name = 'Masum'

print(name)
```

Output:

```text
Masum
```

### 5.2 Double Quotes

```python
language = "Python"

print(language)
```

Output:

```text
Python
```

Single quotes এবং double quotes—দুটিই সাধারণ string literal তৈরিতে ব্যবহার করা যায়।

### 5.3 Triple-Quoted Strings

একাধিক লাইনের text লেখার জন্য triple quotes ব্যবহার করা যায়।

```python
message = """Welcome to Python.
We are learning literals.
This is a multiline string."""

print(message)
```

Output:

```text
Welcome to Python.
We are learning literals.
This is a multiline string.
```

Triple quotes হলো `'''` অথবা `"""`।

**মনে রাখবে:** Triple-quoted string নিজে থেকেই comment নয়। এটি একটি string literal। Function বা class-এর শুরুতে নির্দিষ্টভাবে ব্যবহার করা হলে এটি docstring হিসেবেও কাজ করতে পারে।

### 5.4 Escape Sequences in String Literals

String-এর মধ্যে বিশেষ character প্রকাশ করতে escape sequence ব্যবহার করা যায়।

| Escape Sequence | Meaning |
|---|---|
| `\n` | New line |
| `\t` | Horizontal tab |
| `\\` | Backslash |
| `\'` | Single quote |
| `\"` | Double quote |

উদাহরণ:

```python
print("Hello\nPython")
print("Name:\tMasum")
print("It's a Python string")
```

Output:

```text
Hello
Python
Name:   Masum
It's a Python string
```

### 5.5 Raw String Literals

Raw string-এর আগে `r` বা `R` লেখা হয়। এতে সাধারণ escape sequence-গুলোকে escape sequence হিসেবে interpret করা হয় না।

```python
path = r"C:\new_folder\test"

print(path)
```

Output:

```text
C:\new_folder\test
```

এটি Windows file path এবং regular expression-এর মতো ক্ষেত্রে উপকারী হতে পারে।

তবে raw string-এরও কিছু syntax rule আছে। যেমন, একটি raw string সাধারণত একটিমাত্র trailing backslash দিয়ে শেষ করা যায় না।

### 5.6 F-Strings

F-string-এর আগে `f` বা `F` লেখা হয়। এর মাধ্যমে string-এর মধ্যে variable বা expression-এর value বসানো যায়।

```python
name = "Masum"
age = 22

message = f"My name is {name} and I am {age} years old."

print(message)
```

Output:

```text
My name is Masum and I am 22 years old.
```

এখানে `{name}` এবং `{age}`-এর জায়গায় variable-এর value বসেছে।

F-string-এর বিস্তারিত আলোচনা String Formatting-এর topic-এ করা হবে।

## 6. Boolean Literals

Python-এ দুটি Boolean literal রয়েছে:

- `True`
- `False`

উদাহরণ:

```python
is_student = True
is_graduated = False

print(is_student)
print(is_graduated)
```

Output:

```text
True
False
```

Boolean literal সাধারণত condition, comparison এবং logical operation-এ ব্যবহৃত হয়।

উদাহরণ:

```python
print(10 > 5)
print(10 < 5)
```

Output:

```text
True
False
```

Python-এ `True` এবং `False`-এর প্রথম অক্ষর capital হতে হবে।

ভুল:

```python
# status = true
```

এখানে `true` কোনো built-in Boolean literal নয়। এটি আগে define না করা থাকলে `NameError` হবে।

সঠিক:

```python
status = True
```

## 7. The `None` Literal

`None` হলো Python-এর একটি বিশেষ literal। এটি সাধারণত কোনো value অনুপস্থিত, এখনো নির্ধারিত হয়নি বা কোনো ফলাফল নেই—এমন অবস্থা বোঝাতে ব্যবহৃত হয়।

উদাহরণ:

```python
result = None

print(result)
print(type(result))
```

Output:

```text
None
<class 'NoneType'>
```

এখানে `result`-এর value হলো `None`।

### Checking for `None`

কোনো variable-এর value `None` কি না পরীক্ষা করতে `is None` ব্যবহার করা হয়।

```python
result = None

if result is None:
    print("No result available")
```

Output:

```text
No result available
```

`None` পরীক্ষা করার জন্য সাধারণত `is None` এবং `is not None` ব্যবহার করা উত্তম।

উদাহরণ:

```python
value = 100

if value is not None:
    print("A value is available")
```

Output:

```text
A value is available
```

### `None` Is Not the Same as Zero or an Empty String

নিচের value-গুলো এক নয়:

```python
a = None
b = 0
c = ""
d = False

print(a)
print(b)
print(c)
print(d)
```

Output:

```text
None
0

False
```

পার্থক্য:

- `None` — value অনুপস্থিত বোঝাতে ব্যবহৃত হয়।
- `0` — একটি integer value।
- `""` — empty string।
- `False` — Boolean value।

## 8. Collection Literals

Python-এ সরাসরি collection তৈরির জন্যও literal syntax রয়েছে।

### 8.1 List Literal

List literal square brackets `[]` ব্যবহার করে লেখা হয়।

```python
numbers = [10, 20, 30]

print(numbers)
print(type(numbers))
```

Output:

```text
[10, 20, 30]
<class 'list'>
```

List ordered এবং mutable। অর্থাৎ এর item-এর order থাকে এবং item পরিবর্তন করা যায়।

### 8.2 Tuple Literal

Tuple সাধারণত parentheses `()` ব্যবহার করে লেখা হয়।

```python
student = ("Masum", 22, "CSE")

print(student)
print(type(student))
```

Output:

```text
('Masum', 22, 'CSE')
<class 'tuple'>
```

Comma দিয়ে tuple তৈরি করা হয়। Parentheses সব ক্ষেত্রে বাধ্যতামূলক নয়।

একটি item-এর tuple তৈরি করতে trailing comma প্রয়োজন:

```python
single_item = (10,)

print(type(single_item))
```

Output:

```text
<class 'tuple'>
```

কিন্তু:

```python
not_a_tuple = (10,)

print(not_a_tuple)
```

এটিও এক item-এর tuple। অন্যদিকে `(10)` শুধু integer expression।

### 8.3 Dictionary Literal

Dictionary literal curly braces `{}` এবং key-value pair ব্যবহার করে লেখা হয়।

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}

print(student)
```

Output:

```text
{'name': 'Masum', 'age': 22, 'department': 'CSE'}
```

Dictionary-তে key-এর সঙ্গে value যুক্ত থাকে।

### 8.4 Set Literal

Set literal curly braces ব্যবহার করে লেখা যায়।

```python
numbers = {10, 20, 30}

print(numbers)
print(type(numbers))
```

Set unique elements রাখে। তাই duplicate value থাকলে একটিই রাখা হয়।

```python
numbers = {10, 10, 20, 20, 30}

print(numbers)
```

Output-এর set-এ `10`, `20` ও `30` একবার করে থাকবে। Set-এর item-এর নির্দিষ্ট display order-এর ওপর নির্ভর করা উচিত নয়।

**Important:** `{}` একটি empty dictionary তৈরি করে, empty set নয়।

Empty set তৈরি করতে:

```python
empty_set = set()
```

এটি একটি empty set তৈরি করে, যদিও `set()` literal নয়—এটি built-in constructor-এর call।

## 9. What Is a Constant?

**Constant** হলো এমন একটি নাম, যার value program-এর execution-এর সময় পরিবর্তন না করার উদ্দেশ্যে ব্যবহার করা হয়।

উদাহরণ:

```python
PI = 3.14159
MAX_USERS = 100
UNIVERSITY_NAME = "Northern University Bangladesh"
```

এখানে `PI`, `MAX_USERS` এবং `UNIVERSITY_NAME` constant হিসেবে ব্যবহৃত হয়েছে।

Python-এ `const` নামে কোনো keyword নেই। তাই variable-এর মতো constant-ও assign করা যায় এবং language নিজে থেকে এর value পরিবর্তন নিষিদ্ধ করে না।

অর্থাৎ, Python-এর constants মূলত **convention-based**।

## 10. Naming Convention for Constants

Python-এ constant-এর নাম সাধারণত uppercase letters এবং underscores ব্যবহার করে লেখা হয়।

উদাহরণ:

```python
PI = 3.14159
MAX_MARKS = 100
MIN_AGE = 18
TAX_RATE = 0.15
```

এই naming style-কে `UPPER_SNAKE_CASE` বলা হয়।

### Variable vs Constant Naming

| Type | Naming Convention | Example |
|---|---|---|
| সাধারণ variable | `snake_case` | `student_name` |
| Constant | `UPPER_SNAKE_CASE` | `MAX_MARKS` |
| Class name | `PascalCase` | `StudentRecord` |

এখানে মূল পার্থক্য হলো naming convention। Python constant-এর জন্য আলাদা syntax বাধ্যতামূলক করে না।

## 11. Why Do We Use Constants?

### 11.1 To Avoid Repeated Values

ধরা যাক, কোনো program-এ সর্বোচ্চ marks বারবার ব্যবহার করতে হবে।

Constant ছাড়া:

```python
student1_marks = 85
student2_marks = 90

student1_percentage = student1_marks / 100 * 100
student2_percentage = student2_marks / 100 * 100
```

এখানে `100` বারবার লেখা হয়েছে।

Constant ব্যবহার করে:

```python
MAX_MARKS = 100

student1_marks = 85
student2_marks = 90

student1_percentage = student1_marks / MAX_MARKS * 100
student2_percentage = student2_marks / MAX_MARKS * 100
```

এতে `MAX_MARKS`-এর অর্থ স্পষ্ট হয়।

### 11.2 To Improve Readability

```python
TAX_RATE = 0.15

price = 1000
tax = price * TAX_RATE

print(tax)
```

Output:

```text
150.0
```

`0.15` সরাসরি ব্যবহার করার চেয়ে `TAX_RATE` নামটি value-এর উদ্দেশ্য পরিষ্কার করে।

### 11.3 To Make Maintenance Easier

একই configuration value program-এর বিভিন্ন জায়গায় প্রয়োজন হলে constant ব্যবহার করলে তা maintain করা সহজ হয়।

উদাহরণ:

```python
MAX_LOGIN_ATTEMPTS = 5

print("Maximum attempts:", MAX_LOGIN_ATTEMPTS)
```

ভবিষ্যতে limit পরিবর্তন করতে হলে সংশ্লিষ্ট constant update করা সহজ।

## 12. Constants Are Not Truly Protected in Python

Python-এ uppercase নাম ব্যবহার করা মানেই value অপরিবর্তনীয় নয়।

উদাহরণ:

```python
MAX_USERS = 100
MAX_USERS = 200

print(MAX_USERS)
```

Output:

```text
200
```

এটি বৈধ Python code। তবে constant হিসেবে ব্যবহার করার উদ্দেশ্য থাকলে এমন reassignment এড়িয়ে চলা উচিত।

### Using `Final` Type Hint

Python-এর `typing` module-এ `Final` ব্যবহার করে বোঝানো যায় যে কোনো নাম পুনরায় assign করা উচিত নয়।

```python
from typing import Final

MAX_USERS: Final[int] = 100
```

এখানে `Final[int]` জানায় যে `MAX_USERS`-কে integer value-এর জন্য final হিসেবে বিবেচনা করা হচ্ছে।

তবে `Final` নিজে runtime-এ reassignment আটকে দেয় না। Type checker-এর মতো development tools এই নিয়মের violation ধরতে সাহায্য করতে পারে।

Basic programming-এর জন্য uppercase naming convention-ই প্রথমে ভালোভাবে শিখে রাখো।

## 13. Built-in Constants

Python-এর কিছু built-in constant রয়েছে।

| Constant | Meaning |
|---|---|
| `True` | Boolean true value |
| `False` | Boolean false value |
| `None` | Absence of a value |
| `NotImplemented` | কোনো operation-এর implementation এই object-এর জন্য সরাসরি দেওয়া হয়নি বোঝাতে ব্যবহৃত হয় |
| `Ellipsis` | `...`-এর built-in object |

উদাহরণ:

```python
print(True)
print(False)
print(None)
print(Ellipsis)
```

Output:

```text
True
False
None
Ellipsis
```

`NotImplemented` সাধারণত advanced operator implementation-এ ব্যবহৃত হয়। Beginner পর্যায়ে `True`, `False` এবং `None` ভালোভাবে বোঝাই সবচেয়ে গুরুত্বপূর্ণ।

## 14. Literal vs Constant vs Variable

এই তিনটি concept-এর পার্থক্য পরিষ্কারভাবে বুঝতে হবে।

```python
MAX_MARKS = 100
student_marks = 85

percentage = student_marks / MAX_MARKS * 100
```

এখানে:

- `100` হলো integer literal।
- `MAX_MARKS` হলো constant হিসেবে ব্যবহৃত নাম।
- `student_marks` হলো variable।
- `percentage` হলো calculation-এর result রাখার variable।

| Concept | Meaning | Example |
|---|---|---|
| Literal | Code-এ সরাসরি লেখা value | `100`, `"Python"` |
| Variable | Object-কে refer করার জন্য ব্যবহৃত নাম | `student_marks` |
| Constant | যে নামের value পরিবর্তন না করার convention অনুসরণ করা হয় | `MAX_MARKS` |

**মনে রাখবে:** Constant-ও Python-এর দৃষ্টিতে একটি নাম, যার binding পরিবর্তন করা সম্ভব। এটি সাধারণ variable থেকে মূলত convention ও intended use-এর মাধ্যমে আলাদা।

## 15. Common Mistakes

### Mistake 1: Writing Boolean Literals in Lowercase

ভুল:

```python
# is_active = true
```

সঠিক:

```python
is_active = True
```

Python-এ `True` এবং `False` case-sensitive।

### Mistake 2: Confusing `None` with `"None"`

```python
a = None
b = "None"

print(type(a))
print(type(b))
```

Output:

```text
<class 'NoneType'>
<class 'str'>
```

`None` একটি বিশেষ literal, কিন্তু `"None"` হলো পাঁচটি character-সহ একটি string।

### Mistake 3: Assuming `{}` Creates an Empty Set

ভুল ধারণা:

```python
empty = {}
```

এটি empty dictionary তৈরি করে।

সঠিক:

```python
empty = set()
```

### Mistake 4: Forgetting the Comma in a Single-Item Tuple

```python
a = (10)
b = (10,)

print(type(a))
print(type(b))
```

Output:

```text
<class 'int'>
<class 'tuple'>
```

একটি item-এর tuple তৈরি করতে comma প্রয়োজন।

### Mistake 5: Assuming Constants Cannot Be Changed

```python
PI = 3.14
PI = 3.14159
```

Python এই reassignment নিষিদ্ধ করে না। Constant convention অনুসারে এমন পরিবর্তন এড়িয়ে চলতে হয়।

## 16. Practical Example

নিচের example-এ literals, constants এবং variables একসঙ্গে ব্যবহার করা হয়েছে।

```python
UNIVERSITY_NAME = "Northern University Bangladesh"
MAX_MARKS = 100
PASS_MARKS = 40

student_name = "Masum"
student_marks = 85
is_present = True

percentage = student_marks / MAX_MARKS * 100
is_passed = student_marks >= PASS_MARKS

print("University:", UNIVERSITY_NAME)
print("Student:", student_name)
print("Marks:", student_marks)
print("Percentage:", percentage)
print("Present:", is_present)
print("Passed:", is_passed)
```

Output:

```text
University: Northern University Bangladesh
Student: Masum
Marks: 85
Percentage: 85.0
Present: True
Passed: True
```

এই example-এ:

- `"Northern University Bangladesh"` ও `"Masum"` string literals।
- `100`, `40` ও `85` integer literals।
- `True` Boolean literal।
- `UNIVERSITY_NAME`, `MAX_MARKS` ও `PASS_MARKS` constant হিসেবে ব্যবহৃত।
- `student_name`, `student_marks`, `percentage` ও `is_passed` variables।

## 17. Practice Exercises

### Exercise 1: Identify the Literals

নিচের code-এ কোনগুলো literal, চিহ্নিত করো।

```python
name = "Masum"
age = 22
cgpa = 3.95
is_student = True
result = None
```

### Exercise 2: Numeric Literals

নিচের code-এর output অনুমান করো।

```python
print(0b1010)
print(0o10)
print(0x10)
print(1.5e2)
```

### Exercise 3: String Literals

`\n` এবং `\t` ব্যবহার করে নিচের মতো output তৈরি করো।

```text
Name:
Masum
Department: CSE
```

### Exercise 4: Collection Literals

নিচের প্রতিটি collection-এর data type বের করো।

```python
a = [1, 2, 3]
b = (1, 2, 3)
c = {"name": "Masum"}
d = {1, 2, 3}
e = {}
f = (10,)
```

### Exercise 5: Constants

একটি student marks program তৈরি করো। এতে নিচের constants ব্যবহার করবে:

- `MAX_MARKS = 100`
- `PASS_MARKS = 40`

তারপর student-এর marks, percentage এবং pass/fail status print করবে।

### Exercise 6: `None` Checking

`result = None` নিয়ে `is None` ব্যবহার করে `"No result"` print করো।

### Exercise 7: Naming Convention

নিচের নামগুলো constant naming convention অনুযায়ী লেখো:

- Maximum marks
- Minimum age
- Tax rate
- University name

## 18. Quick Revision

| Topic | Remember |
|---|---|
| Literal | Code-এ সরাসরি লেখা value |
| Integer literal | `100` |
| Float literal | `3.14` |
| Complex literal | `2 + 3j` |
| String literal | `"Python"` |
| Boolean literal | `True`, `False` |
| None literal | `None` |
| List literal | `[1, 2, 3]` |
| Tuple literal | `(1, 2, 3)` |
| Dictionary literal | `{"name": "Masum"}` |
| Set literal | `{1, 2, 3}` |
| Empty set | `set()` |
| Constant convention | `UPPER_SNAKE_CASE` |
| Python constant rule | Uppercase নাম একটি convention; runtime-এ value change আটকায় না |
| `Final` | Type checker-কে final binding সম্পর্কে জানানোর জন্য |

## 19. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Literal হলো source code-এ সরাসরি লেখা value।
- Numeric literals-এর মধ্যে integer, float এবং complex অন্তর্ভুক্ত।
- String literal single, double ও triple quotes দিয়ে লেখা যায়।
- Boolean literals হলো `True` এবং `False`।
- `None` অনুপস্থিত value বোঝাতে ব্যবহৃত হয়।
- List, tuple, dictionary ও set-এর literal syntax রয়েছে।
- Constant হলো এমন নাম, যার value পরিবর্তন না করার convention অনুসরণ করা হয়।
- Python-এ constant-এর জন্য আলাদা `const` keyword নেই।
- `UPPER_SNAKE_CASE` হলো constant-এর প্রচলিত naming convention।
- `Final` type hint ব্যবহার করে type checker-এর সাহায্যে অনিচ্ছাকৃত reassignment শনাক্ত করা যেতে পারে।

## 20. Next Topic

পরবর্তী ফাইল: [`14_Basic_Expressions_in_Python.md`](14_Basic_Expressions_in_Python.md)

সেখানে expression কী, কীভাবে expression evaluate হয়, arithmetic ও comparison expression, logical expression এবং expression-এর result variable-এ রাখার নিয়ম বিস্তারিত আলোচনা করা হবে।