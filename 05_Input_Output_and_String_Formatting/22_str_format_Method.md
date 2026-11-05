# 22. The `str.format()` Method in Python

## 1. Introduction to `str.format()`

Python-এ string-এর মধ্যে variable বা value বসানোর একটি পদ্ধতি হলো `.format()` method।

f-string শেখার আগে এই method ব্যবহার করে string formatting করা হতো। এখনো অনেক পুরোনো codebase, tutorial এবং project-এ `.format()` দেখতে পাওয়া যায়।

### Example

```python
name = "Masum"
age = 22

message = "My name is {} and I am {} years old.".format(name, age)

print(message)
```

Output:

```text
My name is Masum and I am 22 years old.
```

এখানে `{}` হলো placeholder। `.format(name, age)`-এর value-গুলো placeholder-এর জায়গায় বসেছে।

**মনে রাখবে:** `.format()` original string পরিবর্তন করে না; এটি একটি নতুন formatted string return করে।

## 2. Basic Syntax

### Syntax

```python
"string {}".format(value)
```

এখানে:

- String-এর `{}` হলো placeholder।
- `.format()` method-এ value দেওয়া হয়।
- Placeholder-এর জায়গায় value বসিয়ে নতুন string তৈরি হয়।

### Example

```python
name = "Python"

print("I am learning {}.".format(name))
```

Output:

```text
I am learning Python.
```

### Multiple Placeholders

```python
name = "Masum"
department = "CSE"
university = "NUB"

print("My name is {}. I study {} at {}.".format(
    name, department, university
))
```

Output:

```text
My name is Masum. I study CSE at NUB.
```

প্রতিটি placeholder-এর জন্য `.format()`-এ উপযুক্ত value দেওয়া হয়েছে।

## 3. Automatic Positional Ordering

যখন placeholder-এর মধ্যে কোনো index দেওয়া হয় না, তখন `.format()` value-গুলোকে ক্রমানুসারে বসায়।

### Example

```python
print("{} {} {}".format("Python", "is", "easy"))
```

Output:

```text
Python is easy
```

এখানে:

- প্রথম `{}` → `"Python"`
- দ্বিতীয় `{}` → `"is"`
- তৃতীয় `{}` → `"easy"`

### Another Example

```python
name = "Ritu"
marks = 95

print("Student: {}, Marks: {}".format(name, marks))
```

Output:

```text
Student: Ritu, Marks: 95
```

এই পদ্ধতিকে automatic positional formatting বলা যায়।

## 4. Using Positional Indexes

Placeholder-এর মধ্যে index দিয়ে নির্দিষ্ট argument নির্বাচন করা যায়।

Index শুরু হয় `0` থেকে।

### Example

```python
print("{0} is learning Python.".format("Masum"))
```

Output:

```text
Masum is learning Python.
```

এখানে `0` প্রথম argument-এর index।

### Multiple Arguments

```python
print("{0} studies {1} at {2}.".format(
    "Masum", "CSE", "NUB"
))
```

Output:

```text
Masum studies CSE at NUB.
```

এখানে:

- `{0}` → `"Masum"`
- `{1}` → `"CSE"`
- `{2}` → `"NUB"`

### Reusing an Argument

একই argument একাধিকবার ব্যবহার করা যায়।

```python
name = "Masum"

print("{0} is a student. {0} is learning Python.".format(name))
```

Output:

```text
Masum is a student. Masum is learning Python.
```

এখানে `{0}` দুইবার ব্যবহার করা হয়েছে, কিন্তু argument একবারই দিতে হয়েছে।

## 5. Changing the Order of Values

Index ব্যবহার করে argument-এর মূল order পরিবর্তন করে output দেখানো যায়।

### Example

```python
print("{1} {0}".format("Hello", "World"))
```

Output:

```text
World Hello
```

কারণ:

- `{1}` দ্বিতীয় argument `"World"` নেয়।
- `{0}` প্রথম argument `"Hello"` নেয়।

### Practical Example

```python
first_name = "Abdulla"
last_name = "Masum"

print("{1} {0}".format(first_name, last_name))
```

Output:

```text
Masum Abdulla
```

এখানে value-গুলো মূল order-এর বিপরীতে দেখানো হয়েছে।

## 6. Named Arguments

`.format()`-এ argument-এর নাম ব্যবহার করা যায়। এতে code আরও পরিষ্কার হতে পারে।

### Example

```python
print("Name: {name}, Age: {age}".format(
    name="Masum",
    age=22
))
```

Output:

```text
Name: Masum, Age: 22
```

এখানে:

- `{name}` → `name="Masum"`
- `{age}` → `age=22`

### Using Variables

```python
student_name = "Ritu"
student_marks = 95

message = "Student: {name}, Marks: {marks}".format(
    name=student_name,
    marks=student_marks
)

print(message)
```

Output:

```text
Student: Ritu, Marks: 95
```

Variable-এর নাম এবং placeholder-এর নাম একই হওয়া বাধ্যতামূলক নয়। `.format()`-এ কোন value কোন keyword-এর সঙ্গে যুক্ত, সেটিই গুরুত্বপূর্ণ।

## 7. Mixing Positional and Named Arguments

Positional ও named argument একই format string-এ ব্যবহার করা যায়। তবে positional argument আগে এবং named argument পরে দিতে হবে।

### Example

```python
message = "Name: {0}, Department: {department}".format(
    "Masum",
    department="CSE"
)

print(message)
```

Output:

```text
Name: Masum, Department: CSE
```

এখানে:

- `{0}` positional argument ব্যবহার করেছে।
- `{department}` named argument ব্যবহার করেছে।

**গুরুত্বপূর্ণ:** Positional placeholder ব্যবহার করলে argument-এর order ঠিক রাখতে হবে। Python-এর নিয়ম অনুযায়ী positional argument-এর পরে keyword argument দিতে হয়।

## 8. Using Empty Braces and Explicit Indexes

একই format string-এ automatic placeholder এবং numbered placeholder একসঙ্গে ব্যবহার করা যায় না।

### Correct: Automatic Fields

```python
print("{} {}".format("Python", "Programming"))
```

Output:

```text
Python Programming
```

### Correct: Numbered Fields

```python
print("{0} {1}".format("Python", "Programming"))
```

Output:

```text
Python Programming
```

### Incorrect: Mixing Automatic and Manual Numbering

```python
# print("{} {0}".format("Python", "Programming"))
```

এটি চালালে `ValueError` হবে, কারণ automatic field numbering এবং explicit positional numbering মিশিয়ে ব্যবহার করা হয়েছে।

**মনে রাখবে:** একটি format string-এ automatic numbering অথবা explicit positional numbering ব্যবহার করো। Named field আলাদাভাবে positional field-এর সঙ্গে ব্যবহার করা যায়।

## 9. Formatting Integers

`.format()` দিয়ে integer-এর representation নিয়ন্ত্রণ করা যায়।

### Example 1: Basic Integer

```python
number = 12345

print("Number: {}".format(number))
```

Output:

```text
Number: 12345
```

### Example 2: Integer Format

```python
number = 42

print("{:d}".format(number))
```

Output:

```text
42
```

এখানে `d` decimal integer format নির্দেশ করে।

### Example 3: Zero Padding

```python
number = 42

print("{:05d}".format(number))
```

Output:

```text
00042
```

এখানে `05d` integer-কে minimum width 5-এ zero padding দিয়ে দেখায়।

## 10. Formatting Floating-Point Numbers

Float number-কে নির্দিষ্ট decimal places-এ দেখানো যায়।

### Example 1: Two Decimal Places

```python
price = 123.45678

print("{:.2f}".format(price))
```

Output:

```text
123.46
```

### Example 2: One Decimal Place

```python
number = 12.3456

print("{:.1f}".format(number))
```

Output:

```text
12.3
```

### Example 3: Three Decimal Places

```python
number = 12.3456

print("{:.3f}".format(number))
```

Output:

```text
12.346
```

এখানে `.nf` ব্যবহার করে decimal point-এর পর `n`টি digit দেখানো যায়।

## 11. Thousand Separators

বড় number পড়তে সুবিধা করার জন্য comma separator ব্যবহার করা যায়।

### Example 1: Integer

```python
population = 1250000

print("{:,}".format(population))
```

Output:

```text
1,250,000
```

### Example 2: Float

```python
amount = 1234567.891

print("{:,.2f}".format(amount))
```

Output:

```text
1,234,567.89
```

এখানে:

- `,` thousand grouping করে।
- `.2f` দুই decimal places দেখায়।

## 12. Percentage Formatting

Percentage দেখানোর জন্য `%` format type ব্যবহার করা হয়।

### Example

```python
score = 0.875

print("{:.2%}".format(score))
```

Output:

```text
87.50%
```

এখানে `0.875`-কে 100 দিয়ে গুণ করে percentage হিসেবে দেখানো হয়েছে।

### Practical Example

```python
obtained = 425
total = 500

percentage = obtained / total

print("Percentage: {:.2%}".format(percentage))
```

Output:

```text
Percentage: 85.00%
```

**সতর্কতা:** যদি `score = 85` হয়, তাহলে `"{:.2%}".format(score)` output হবে `8500.00%`। Percentage format ব্যবহার করার আগে value-টি ratio কি না, তা নিশ্চিত হও।

## 13. Field Width and Alignment

`.format()`-এও field width এবং alignment ব্যবহার করা যায়।

### Example

```python
name = "Python"

print("|{:<10}|".format(name))
print("|{:>10}|".format(name))
print("|{:^10}|".format(name))
```

Output:

```text
|Python    |
|    Python|
|  Python  |
```

এখানে:

- `<10` → left alignment
- `>10` → right alignment
- `^10` → center alignment

### Custom Padding

```python
name = "Masum"

print("{:*<10}".format(name))
print("{:*>10}".format(name))
print("{:*^10}".format(name))
```

Output:

```text
Masum*****
*****Masum
**Masum***
```

Padding-এর নিয়ম f-string-এর format specification-এর মতোই।

## 14. Formatting Values in a Table

`.format()` দিয়ে সুন্দর table তৈরি করা যায়।

### Example

```python
print("{:<15}{:>8}".format("Name", "Marks"))
print("-" * 23)

print("{:<15}{:>8}".format("Masum", 85))
print("{:<15}{:>8}".format("Ritu", 100))
print("{:<15}{:>8}".format("Abdullah", 92))
```

Output:

```text
Name              Marks
-----------------------
Masum                 85
Ritu                 100
Abdullah              92
```

প্রতিটি column-এর জন্য একই width ব্যবহার করা হয়েছে, তাই table-এর output পরিষ্কার হয়েছে।

## 15. Accessing List Elements

`.format()`-এর placeholder থেকে list বা tuple-এর element access করা যায়।

### Example: List

```python
student = ["Masum", "CSE", 3.95]

print("Name: {0[0]}".format(student))
print("Department: {0[1]}".format(student))
print("CGPA: {0[2]}".format(student))
```

Output:

```text
Name: Masum
Department: CSE
CGPA: 3.95
```

এখানে `{0[0]}` মানে প্রথম argument-এর প্রথম element।

### Example: Tuple

```python
student = ("Ritu", 95)

print("Name: {0[0]}, Marks: {0[1]}".format(student))
```

Output:

```text
Name: Ritu, Marks: 95
```

এ ধরনের indexing পুরোনো format string-এ দেখা যেতে পারে। সাধারণ beginner code-এ variable-কে আলাদা করে রাখা বা f-string ব্যবহার করাও সহজ বিকল্প।

## 16. Accessing Dictionary Values

Dictionary-এর value-ও `.format()` দিয়ে access করা যায়।

### Example

```python
student = {
    "name": "Masum",
    "department": "CSE",
    "cgpa": 3.95
}

print("Name: {0[name]}".format(student))
print("Department: {0[department]}".format(student))
print("CGPA: {0[cgpa]}".format(student))
```

Output:

```text
Name: Masum
Department: CSE
CGPA: 3.95
```

এখানে `{0[name]}` প্রথম argument dictionary-এর `name` key-এর value নেয়।

## 17. Escaping Curly Braces

Format string-এর মধ্যে সত্যিকারের `{` বা `}` character দেখাতে চাইলে double braces ব্যবহার করতে হয়।

### Example

```python
print("Use {{}} to represent curly braces.")
```

Output:

```text
Use {} to represent curly braces.
```

### Example with a Value

```python
name = "Masum"

print("{{Name: {}}}".format(name))
```

Output:

```text
{Name: Masum}
```

এখানে:

- `{{` একটি literal `{` দেখায়।
- `{}` value বসানোর placeholder।
- `}}` একটি literal `}` দেখায়।

## 18. Formatting Dates and Other Objects

`.format()` বিভিন্ন object-এর string representation বসাতে পারে। Date বা time format করতে হলে `datetime` module-এর `strftime()` method-ও প্রচলিত।

### Example: Date Object

```python
from datetime import date

today = date(2026, 10, 16)

print("Date: {}".format(today))
```

Output:

```text
Date: 2026-10-16
```

### Using `strftime()`

```python
from datetime import date

today = date(2026, 10, 16)

print(today.strftime("%d-%m-%Y"))
```

Output:

```text
16-10-2026
```

এখানে `.format()` date object-এর default string representation দেখিয়েছে, আর `strftime()` নির্দিষ্ট date format তৈরি করেছে।

## 19. Common Errors

### Error 1: Missing Argument

```python
# print("Name: {}, Age: {}".format("Masum"))
```

এখানে দুটি placeholder আছে, কিন্তু argument দেওয়া হয়েছে একটি। তাই `IndexError` হবে।

Correct version:

```python
print("Name: {}, Age: {}".format("Masum", 22))
```

### Error 2: Invalid Index

```python
# print("{2}".format("A", "B"))
```

এখানে শুধু দুটি argument আছে, যাদের index `0` ও `1`; তাই index `2` ব্যবহার করলে `IndexError` হবে।

### Error 3: Missing Named Argument

```python
# print("{name}".format(age=22))
```

এখানে `name` নামে কোনো argument দেওয়া হয়নি। তাই `KeyError` হবে।

Correct version:

```python
print("{name}".format(name="Masum"))
```

### Error 4: Incorrect Format Type

```python
# print("{:d}".format(12.5))
```

এখানে `d` integer format, কিন্তু value float। তাই `ValueError` হবে।

Correct version:

```python
print("{:.1f}".format(12.5))
```

Output:

```text
12.5
```

### Error 5: Incorrect Braces

```python
# print("{".format())
```

Format string-এ একক `{` placeholder শুরু করে, কিন্তু এটি সম্পূর্ণ নয়। তাই `ValueError` হতে পারে।

Literal brace দেখাতে `{{` বা `}}` ব্যবহার করো।

## 20. `.format()` vs f-Strings

দুই পদ্ধতিই string formatting করতে পারে।

### Using `.format()`

```python
name = "Masum"
age = 22

print("Name: {}, Age: {}".format(name, age))
```

### Using f-Strings

```python
name = "Masum"
age = 22

print(f"Name: {name}, Age: {age}")
```

দুটির output:

```text
Name: Masum, Age: 22
```

| Feature | `.format()` | f-string |
|---|---|---|
| Basic syntax | `"{}".format(value)` | `f"{value}"` |
| Variable ব্যবহার | Argument দিতে হয় | Variable সরাসরি লেখা যায় |
| Expression | Placeholder-এ সরাসরি সাধারণ expression লেখা যায় না; আগে argument তৈরি করতে হয় | `{}`-এর মধ্যে expression লেখা যায় |
| Named values | `{name}` এবং keyword argument | `{name}` এবং local variable |
| Readability | অনেক placeholder হলে তুলনামূলক দীর্ঘ হতে পারে | সাধারণত সহজ ও সংক্ষিপ্ত |
| Python version | Python 2.6+ এবং Python 3-এ পাওয়া যায় | Python 3.6+ |

**Recommendation:** নতুন Python code লেখার সময় সাধারণত f-string ব্যবহার করো। তবে `.format()` বোঝা জরুরি, কারণ বিদ্যমান code-এ এটি দেখতে পাবে।

## 21. Practical Program: Student Result Card

```python
name = "Masum"
obtained = 425
total = 500

percentage = obtained / total

print("=" * 35)
print("{:^35}".format("STUDENT RESULT CARD"))
print("=" * 35)
print("{:<15} {}".format("Name:", name))
print("{:<15} {}/{}".format("Marks:", obtained, total))
print("{:<15} {:.2%}".format("Percentage:", percentage))
print("=" * 35)
```

Output:

```text
===================================
         STUDENT RESULT CARD
===================================
Name:           Masum
Marks:          425/500
Percentage:     85.00%
===================================
```

এখানে `.format()` ব্যবহার করে heading, labels এবং percentage সাজানো হয়েছে।

## 22. Practice Exercises

### Exercise 1: Basic Formatting

`name = "Masum"` এবং `age = 22` ব্যবহার করে `.format()` দিয়ে sentence তৈরি করো।

### Exercise 2: Positional Index

দুটি value `"Python"` ও `"Programming"` দিয়ে output তৈরি করো:

```text
Programming with Python
```

### Exercise 3: Named Arguments

`name`, `department` এবং `university` named argument ব্যবহার করে student introduction তৈরি করো।

### Exercise 4: Decimal Formatting

`price = 1234.5678`-কে দুই decimal places-এ দেখাও।

### Exercise 5: Percentage

`obtained = 450` এবং `total = 500` থেকে percentage দুই decimal places-এ দেখাও।

### Exercise 6: Zero Padding

`number = 87`-কে ছয় character width-এ zero padding-সহ দেখাও।

### Exercise 7: Alignment

`"Python"`-কে 12-character width-এ left, right ও center-align করো।

### Exercise 8: Dictionary Formatting

নিচের dictionary থেকে name ও CGPA দেখাও।

```python
student = {"name": "Masum", "cgpa": 3.95}
```

### Exercise 9: Output Prediction

```python
name = "Ritu"
marks = 95

print("{1}: {0}".format(marks, name))
print("{:.2f}".format(12.345))
print("{:05d}".format(42))
```

Output কী হবে?

### Exercise 10: Mini Challenge

একটি product bill তৈরি করো, যাতে product name, unit price, quantity এবং total price থাকবে। `.format()` ব্যবহার করে price ও total দুই decimal places-এ দেখাবে।

## 23. Practice Answer Key

### Answer 1

```python
name = "Masum"
age = 22

print("My name is {} and I am {} years old.".format(name, age))
```

### Answer 2

```python
print("{1} with {0}".format("Python", "Programming"))
```

Output:

```text
Programming with Python
```

### Answer 3

```python
print(
    "Name: {name}, Department: {department}, University: {university}".format(
        name="Masum",
        department="CSE",
        university="NUB"
    )
)
```

### Answer 4

```python
price = 1234.5678

print("{:.2f}".format(price))
```

Output:

```text
1234.57
```

### Answer 5

```python
obtained = 450
total = 500

print("{:.2%}".format(obtained / total))
```

Output:

```text
90.00%
```

### Answer 6

```python
number = 87

print("{:06d}".format(number))
```

Output:

```text
000087
```

### Answer 7

```python
name = "Python"

print("|{:<12}|".format(name))
print("|{:>12}|".format(name))
print("|{:^12}|".format(name))
```

### Answer 8

```python
student = {"name": "Masum", "cgpa": 3.95}

print("Name: {0[name]}".format(student))
print("CGPA: {0[cgpa]}".format(student))
```

### Answer 9

Output:

```text
Ritu: 95
12.35
00042
```

### Answer 10

```python
product = "Keyboard"
unit_price = 1250.5
quantity = 2

total = unit_price * quantity

print("=" * 35)
print("{:^35}".format("PRODUCT BILL"))
print("=" * 35)
print("{:<15} {}".format("Product:", product))
print("{:<15} Tk {:.2f}".format("Unit price:", unit_price))
print("{:<15} {}".format("Quantity:", quantity))
print("{:<15} Tk {:,.2f}".format("Total:", total))
print("=" * 35)
```

## 24. Chapter Summary

- `.format()` হলো string-এর একটি formatting method।
- `{}` placeholder-এর মাধ্যমে value বসানো যায়।
- `{0}`, `{1}` ইত্যাদি positional index নির্দিষ্ট argument নির্বাচন করে।
- `{name}`-এর মতো named field keyword argument ব্যবহার করে।
- `.format()` দিয়ে integer, float, percentage, thousand separator ও zero padding করা যায়।
- `<`, `>` এবং `^` দিয়ে left, right ও center alignment করা যায়।
- `{{` ও `}}` দিয়ে literal curly braces দেখানো যায়।
- List ও dictionary-এর value placeholder থেকে access করা যায়।
- Missing argument, invalid index, missing key এবং ভুল format type থেকে error হতে পারে।
- নতুন Python code-এ f-string সাধারণত বেশি readable, তবে `.format()` বোঝা গুরুত্বপূর্ণ।

## 25. Self-Assessment Checklist

- [ ] `.format()`-এর basic syntax বুঝি।
- [ ] Automatic placeholder ও positional index ব্যবহার করতে পারি।
- [ ] Named argument ব্যবহার করতে পারি।
- [ ] Integer ও float format করতে পারি।
- [ ] Percentage ও thousand separator দেখাতে পারি।
- [ ] Width, alignment ও padding ব্যবহার করতে পারি।
- [ ] List ও dictionary থেকে value access করতে পারি।
- [ ] Curly braces escape করতে পারি।
- [ ] `.format()` এবং f-string-এর পার্থক্য বুঝি।

**Next Topic:** `23_Old_Style_Percent_Formatting.md` — এখানে Python-এর পুরোনো `%` string formatting পদ্ধতি শিখব, যা legacy code-এ এখনো দেখা যায়।
