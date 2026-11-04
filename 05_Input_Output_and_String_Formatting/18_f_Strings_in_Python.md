# 18. f-Strings in Python

## 1. Introduction to f-Strings

**f-string** হলো Python-এর একটি string formatting method, যার মাধ্যমে string-এর মধ্যে সরাসরি variable, expression এবং function call-এর result দেখানো যায়।

f-string ব্যবহার করতে string-এর শুরুতে `f` অথবা `F` লিখতে হয়।

### Example

```python
name = "Masum"
age = 22

print(f"My name is {name}.")
print(f"I am {age} years old.")
```

Output:

```text
My name is Masum.
I am 22 years old.
```

এখানে `{name}`-এর জায়গায় `"Masum"` এবং `{age}`-এর জায়গায় `22` বসেছে।

### Why Are f-Strings Important?

f-string ব্যবহার করলে:

1. Variable-এর value সহজে string-এর মধ্যে দেখানো যায়।
2. আলাদাভাবে `str()` ব্যবহার করার প্রয়োজন সাধারণত হয় না।
3. Arithmetic expression-এর result সরাসরি দেখানো যায়।
4. Decimal places, percentage ও alignment নিয়ন্ত্রণ করা যায়।
5. Code আরও পরিষ্কার ও readable হয়।

Python 3.6 থেকে f-string ব্যবহার করা যায়।

## 2. Basic Syntax of f-Strings

### Syntax

```python
f"Text {expression}"
```

এখানে:

- `f` বোঝায় এটি একটি formatted string।
- `{}`-এর মধ্যে variable বা expression লেখা হয়।
- Curly braces-এর মধ্যে থাকা expression evaluate হয়।
- Result string-এর মধ্যে বসে।

### Example 1: Variable

```python
name = "Python"

print(f"Welcome to {name}")
```

Output:

```text
Welcome to Python
```

### Example 2: Multiple Variables

```python
name = "Masum"
department = "CSE"
university = "NUB"

print(f"{name} studies {department} at {university}.")
```

Output:

```text
Masum studies CSE at NUB.
```

### Example 3: Uppercase `F`

```python
name = "Masum"

print(F"Hello, {name}!")
```

Output:

```text
Hello, Masum!
```

`f` ও `F`—দুটিই একইভাবে কাজ করে।

## 3. Using Variables Inside f-Strings

f-string-এর মধ্যে বিভিন্ন data type-এর variable ব্যবহার করা যায়।

### Example

```python
name = "Masum"
age = 22
cgpa = 3.95
is_student = True

print(f"Name: {name}")
print(f"Age: {age}")
print(f"CGPA: {cgpa}")
print(f"Student: {is_student}")
```

Output:

```text
Name: Masum
Age: 22
CGPA: 3.95
Student: True
```

এখানে string, integer, float ও boolean variable ব্যবহার করা হয়েছে।

f-string সাধারণত variable-এর value-কে string representation-এ দেখায়। তাই integer বা float-কে আলাদাভাবে `str()` দিয়ে convert করতে হয় না।

## 4. Using Expressions Inside f-Strings

f-string-এর `{}`-এর মধ্যে শুধু variable নয়, arithmetic expression-ও লেখা যায়।

### Example 1: Addition

```python
a = 10
b = 20

print(f"Sum: {a + b}")
```

Output:

```text
Sum: 30
```

### Example 2: Multiplication

```python
price = 100
quantity = 3

print(f"Total price: {price * quantity}")
```

Output:

```text
Total price: 300
```

### Example 3: Multiple Operations

```python
a = 10
b = 3

print(f"Sum: {a + b}")
print(f"Difference: {a - b}")
print(f"Product: {a * b}")
print(f"Division: {a / b}")
```

Output:

```text
Sum: 13
Difference: 7
Product: 30
Division: 3.3333333333333335
```

এখানে প্রতিটি expression evaluate করে তার result দেখানো হয়েছে।

**মনে রাখবে:** Expression-এর মধ্যে division by zero-এর মতো error ঘটতে পারে। f-string ব্যবহার করলেই এই ধরনের error এড়ানো যায় না।

## 5. Using Functions Inside f-Strings

f-string-এর মধ্যে function call করেও result দেখানো যায়।

### Example 1: `len()`

```python
name = "Masum"

print(f"Name length: {len(name)}")
```

Output:

```text
Name length: 5
```

### Example 2: `upper()`

```python
name = "Masum"

print(f"Uppercase name: {name.upper()}")
```

Output:

```text
Uppercase name: MASUM
```

### Example 3: `round()`

```python
number = 3.14159265

print(f"Rounded value: {round(number, 2)}")
```

Output:

```text
Rounded value: 3.14
```

এখানে `round(number, 2)` function call-এর result f-string-এ বসেছে।

### Important Note

`round()` এবং formatting specification একই বিষয় নয়।

```python
number = 3.5

print(f"{round(number, 2)}")
print(f"{number:.2f}")
```

Output:

```text
3.5
3.50
```

প্রথম ক্ষেত্রে `round()` result হিসেবে numeric value দেয়, যা `3.5` হিসেবে দেখানো হয়েছে। দ্বিতীয় ক্ষেত্রে `.2f` output-এ ঠিক দুইটি decimal place দেখায়।

## 6. Using Conditional Expressions in f-Strings

f-string-এর মধ্যে conditional expression ব্যবহার করা যায়।

### Example

```python
marks = 75

print(f"Result: {'Pass' if marks >= 40 else 'Fail'}")
```

Output:

```text
Result: Pass
```

এখানে:

```python
'Pass' if marks >= 40 else 'Fail'
```

একটি conditional expression।

- `marks >= 40` সত্য হলে `"Pass"` result হবে।
- অন্যথায় `"Fail"` result হবে।

### Another Example

```python
number = 7

print(f"{'Even' if number % 2 == 0 else 'Odd'}")
```

Output:

```text
Odd
```

এ ধরনের ছোট expression f-string-এর মধ্যে ব্যবহার করা যায়। তবে খুব জটিল logic হলে আগে variable-এ result হিসাব করে নেওয়া ভালো।

## 7. Formatting Decimal Places

f-string-এর গুরুত্বপূর্ণ ব্যবহার হলো floating-point number-কে নির্দিষ্ট decimal places-এ দেখানো।

### Syntax

```python
f"{number:.2f}"
```

এখানে:

- `:` formatting specification শুরু করে।
- `.2` দশমিকের পর দুই ঘর নির্দেশ করে।
- `f` fixed-point number format নির্দেশ করে।

### Example 1: Two Decimal Places

```python
price = 125.6789

print(f"{price:.2f}")
```

Output:

```text
125.68
```

### Example 2: One Decimal Place

```python
number = 12.3456

print(f"{number:.1f}")
```

Output:

```text
12.3
```

### Example 3: Three Decimal Places

```python
number = 12.34567

print(f"{number:.3f}")
```

Output:

```text
12.346
```

Formatting-এর সময় প্রয়োজন অনুযায়ী rounding হয়।

### Example 4: Always Show Two Decimal Places

```python
a = 10.0
b = 3.0

result = a / b

print(f"Result: {result:.2f}")
```

Output:

```text
Result: 3.33
```

`.2f` ব্যবহার করলে result-এর decimal অংশে দুইটি ঘর দেখা যাবে।

**গুরুত্বপূর্ণ:** `.2f` output-এর format নিয়ন্ত্রণ করে; এটি মূল variable-এর data type পরিবর্তন করে না।

## 8. Formatting Percentages

Percentage দেখানোর জন্য `%` formatting type ব্যবহার করা যায়।

### Example

```python
score = 0.8567

print(f"Score: {score:.2%}")
```

Output:

```text
Score: 85.67%
```

এখানে:

- `score = 0.8567`
- `.2%` value-কে 100 দিয়ে গুণ করে percentage হিসেবে দেখায়।
- `.2` দশমিকের পর দুই ঘর দেখায়।

### Another Example

```python
attendance = 0.925

print(f"Attendance: {attendance:.1%}")
```

Output:

```text
Attendance: 92.5%
```

### Common Mistake

```python
score = 85.67

print(f"{score:.2%}")
```

Output:

```text
8567.00%
```

কারণ percentage formatting নিজেই value-কে 100 দিয়ে গুণ করে।

যদি `score` ইতোমধ্যে percentage value হয়, তাহলে সরাসরি `%` formatting ব্যবহার না করে সাধারণ numeric formatting দিয়ে `%` character যোগ করা যেতে পারে:

```python
score = 85.67

print(f"{score:.2f}%")
```

Output:

```text
85.67%
```

## 9. Formatting Integers and Large Numbers

সংখ্যার মধ্যে comma দিয়ে হাজারের group দেখাতে `,` ব্যবহার করা যায়।

### Example 1: Integer

```python
population = 1250000

print(f"{population:,}")
```

Output:

```text
1,250,000
```

### Example 2: Decimal Number

```python
price = 1234567.891

print(f"{price:,.2f}")
```

Output:

```text
1,234,567.89
```

এখানে:

- `,` হাজারের group আলাদা করে।
- `.2f` দশমিকের পর দুই ঘর দেখায়।

### Example 3: Negative Number

```python
balance = -12500.5

print(f"{balance:,.2f}")
```

Output:

```text
-12,500.50
```

এই format report, result sheet এবং financial summary-তে কাজে লাগে।

## 10. Formatting Currency Values

f-string দিয়ে currency-এর মতো output তৈরি করা যায়।

### Example

```python
price = 1250.5

print(f"Price: Tk {price:,.2f}")
```

Output:

```text
Price: Tk 1,250.50
```

### Calculating a Total

```python
price = 499.99
quantity = 3

total = price * quantity

print(f"Price per item: Tk {price:,.2f}")
print(f"Quantity: {quantity}")
print(f"Total: Tk {total:,.2f}")
```

Output:

```text
Price per item: Tk 499.99
Quantity: 3
Total: Tk 1,499.97
```

এখানে `Tk` সাধারণ text হিসেবে দেখানো হয়েছে।

**মনে রাখবে:** এই formatting কেবল display-এর জন্য। বাস্তব financial calculation-এ সঠিক decimal arithmetic প্রয়োজন হলে `decimal.Decimal` বিবেচনা করা উচিত।

## 11. Alignment and Field Width

f-string দিয়ে text বা number-কে নির্দিষ্ট width-এর মধ্যে সাজানো যায়।

### Right Alignment

```python
name = "Masum"

print(f"|{name:>10}|")
```

Output:

```text
|     Masum|
```

`>10` মানে মোট 10 character-এর field-এ right alignment।

### Left Alignment

```python
name = "Masum"

print(f"|{name:<10}|")
```

Output:

```text
|Masum     |
```

`<10` মানে left alignment।

### Center Alignment

```python
name = "Masum"

print(f"|{name:^10}|")
```

Output:

```text
|  Masum   |
```

`^10` মানে center alignment।

### Custom Fill Character

```python
name = "Masum"

print(f"{name:*^12}")
```

Output:

```text
***Masum****
```

এখানে `*` হলো fill character, `^` center alignment এবং `12` field width।

**নোট:** Field width হলো minimum width। Value নির্ধারিত width-এর চেয়ে বড় হলে সাধারণত value-টি কেটে ফেলা হয় না।

## 12. Using `=` in f-Strings for Debugging

Python 3.8 থেকে f-string-এ `=` ব্যবহার করে expression-এর নামসহ result দেখানো যায়। একে সাধারণত self-documenting expression বলা হয়।

### Example

```python
a = 10
b = 20

print(f"{a=}")
print(f"{b=}")
print(f"{a + b=}")
```

Output:

```text
a=10
b=20
a + b=30
```

এটি debugging-এর সময় কাজে লাগে, কারণ expression এবং result একসঙ্গে দেখা যায়।

### Another Example

```python
name = "Masum"
marks = 85

print(f"{name=}, {marks=}")
```

Output:

```text
name='Masum', marks=85
```

এখানে string value-এর representation quote-সহ দেখা যায়।

**মনে রাখবে:** `f"{a=}"` হলো debugging-friendly syntax। এটি সাধারণ assignment statement নয়।

## 13. Using Dictionaries and Object Attributes

f-string-এর মধ্যে dictionary access এবং object attribute access করা যায়।

### Example 1: Dictionary

```python
student = {
    "name": "Masum",
    "marks": 85
}

print(f"Name: {student['name']}")
print(f"Marks: {student['marks']}")
```

Output:

```text
Name: Masum
Marks: 85
```

এখানে dictionary-এর key ব্যবহার করে value নেওয়া হয়েছে।

### Example 2: List Indexing

```python
numbers = [10, 20, 30]

print(f"First number: {numbers[0]}")
print(f"Last number: {numbers[-1]}")
```

Output:

```text
First number: 10
Last number: 30
```

### Example 3: Object Attribute

```python
class Student:
    def __init__(self, name):
        self.name = name

student = Student("Masum")

print(f"Student name: {student.name}")
```

Output:

```text
Student name: Masum
```

এখানে `student.name` object-এর attribute access করে।

## 14. Handling Curly Braces in f-Strings

f-string-এ `{}` expression-এর জন্য ব্যবহৃত হয়। কিন্তু কখনো output-এ সত্যিকারের curly brace দেখাতে হতে পারে।

এক্ষেত্রে double curly braces ব্যবহার করা হয়।

### Example 1: Printing Curly Braces

```python
print(f"{{Hello}}")
```

Output:

```text
{Hello}
```

### Example 2: Braces Around a Variable

```python
name = "Masum"

print(f"{{{name}}}")
```

Output:

```text
{Masum}
```

এখানে:

- `{{` একটি literal `{` দেখায়।
- `{name}` variable-এর value দেখায়।
- `}}` একটি literal `}` দেখায়।

### Example 3: JSON-Like Text

```python
name = "Masum"

print(f'{{"name": "{name}"}}')
```

Output:

```text
{"name": "Masum"}
```

এটি শুধু formatted text তৈরি করছে; JSON data তৈরি বা validate করছে না।

## 15. Quotation Marks Inside f-Strings

f-string-এর মধ্যে string literal ব্যবহার করার সময় quotation mark নিয়ে সতর্ক থাকতে হয়।

### Example

```python
name = "Masum"

print(f"Hello, {name.upper()}!")
```

Output:

```text
Hello, MASUM!
```

এটি সাধারণভাবে ব্যবহারযোগ্য।

যদি expression-এর মধ্যে quotation mark থাকে, তাহলে বাইরের string-এর quotation mark-এর সঙ্গে সংঘর্ষ এড়াতে হবে।

### Compatible Example

```python
student = {"name": "Masum"}

print(f"Name: {student['name']}")
```

Output:

```text
Name: Masum
```

### Another Compatible Example

```python
student = {"name": "Masum"}

print(f'Name: {student["name"]}')
```

Output:

```text
Name: Masum
```

Python 3.12 থেকে f-string expression-এর মধ্যে quotation mark ব্যবহারের নিয়ম আরও flexible হয়েছে। তবে বিভিন্ন Python version-এ compatibility বজায় রাখতে expression-এর quotation mark এবং বাইরের string-এর quotation mark আলাদা রাখা ভালো।

## 16. Raw f-Strings

কখনো string-এ backslash-সহ path বা অন্য text রাখতে হয়। সে ক্ষেত্রে `rf` অথবা `fr` prefix ব্যবহার করে raw f-string লেখা যায়।

### Example

```python
folder = "Projects"

path = rf"C:\Users\Masum\{folder}"

print(path)
```

Output:

```text
C:\Users\Masum\Projects
```

এখানে:

- `r` raw string-এর মতো backslash handling করে।
- `f` variable interpolation চালু রাখে।
- `{folder}`-এর value বসে।

Raw f-string-এরও কিছু syntax rule রয়েছে। বিশেষ করে trailing backslash দিয়ে string শেষ করা যায় না, এবং raw prefix backslash-কে সব context-এ special meaning থেকে মুক্ত করে না।

## 17. f-Strings and Debugging

Debugging-এর সময় variable-এর value দ্রুত দেখার জন্য f-string সুবিধাজনক।

### Example

```python
price = 100
quantity = 3
total = price * quantity

print(f"{price=}")
print(f"{quantity=}")
print(f"{total=}")
```

Output:

```text
price=100
quantity=3
total=300
```

এতে calculation ঠিক হচ্ছে কি না দ্রুত বোঝা যায়।

তবে production application-এ structured logging বা Python-এর `logging` module ব্যবহার করা বেশি উপযুক্ত হতে পারে।

## 18. Common f-String Errors

### Error 1: Forgetting the `f` Prefix

```python
name = "Masum"

print("Hello, {name}")
```

Output:

```text
Hello, {name}
```

**কারণ:** String-টি f-string নয়।

সঠিক code:

```python
print(f"Hello, {name}")
```

### Error 2: Missing Closing Brace

```python
name = "Masum"

print(f"Hello, {name")
```

এখানে `SyntaxError` হবে, কারণ expression-এর closing brace নেই।

সঠিক code:

```python
print(f"Hello, {name}")
```

### Error 3: Incorrect Formatting Specification

```python
number = 12.345

print(f"{number:.2f}")
```

Output:

```text
12.35
```

সঠিক format specification-এ colon-এর পরে `.2f` ব্যবহার করা হয়েছে।

### Error 4: Division by Zero

```python
a = 10
b = 0

print(f"Result: {a / b}")
```

এখানে `ZeroDivisionError` হবে। f-string expression-এর arithmetic error স্বয়ংক্রিয়ভাবে handle করে না।

সঠিকভাবে handle করতে:

```python
a = 10
b = 0

if b != 0:
    print(f"Result: {a / b}")
else:
    print("Cannot divide by zero.")
```

### Error 5: Expecting Formatting to Change the Original Value

```python
price = 12.5

formatted_price = f"{price:.2f}"

print(formatted_price)
print(type(formatted_price))
print(type(price))
```

Output:

```text
12.50
<class 'str'>
<class 'float'>
```

`formatted_price` একটি string, কিন্তু `price` এখনো float।

## 19. Practical Programs

### Program 1: Student Result Card

```python
name = "Masum"
marks = 85
total_marks = 100

percentage = marks / total_marks * 100

print("=" * 35)
print("STUDENT RESULT CARD".center(35))
print("=" * 35)
print(f"Name       : {name}")
print(f"Marks      : {marks}/{total_marks}")
print(f"Percentage : {percentage:.2f}%")
print("=" * 35)
```

Output:

```text
===================================
         STUDENT RESULT CARD
===================================
Name       : Masum
Marks      : 85/100
Percentage : 85.00%
===================================
```

### Program 2: Shopping Bill

```python
product = "Keyboard"
price = 1250.5
quantity = 2

total = price * quantity

print("=" * 30)
print("SHOPPING BILL".center(30))
print("=" * 30)
print(f"Product  : {product}")
print(f"Price    : Tk {price:,.2f}")
print(f"Quantity : {quantity}")
print(f"Total    : Tk {total:,.2f}")
print("=" * 30)
```

### Program 3: Simple Profile

```python
name = input("Enter your name: ")
department = input("Enter your department: ")
university = input("Enter your university: ")

print("\n--- Student Profile ---")
print(f"Name       : {name}")
print(f"Department : {department}")
print(f"University : {university}")
```

### Program 4: Calculate Average

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))
c = float(input("Enter third number: "))

average = (a + b + c) / 3

print(f"Average: {average:.2f}")
```

এই program-এ invalid input বা conversion error handle করা হয়নি। বাস্তব application-এ user input validation যোগ করা উচিত।

## 20. Practice Exercises

### Exercise 1: Basic f-String

`name = "Masum"` ব্যবহার করে নিচের output তৈরি করো:

```text
Welcome, Masum!
```

### Exercise 2: Multiple Variables

নিচের variable-গুলো ব্যবহার করে একটি sentence তৈরি করো:

```python
name = "Masum"
department = "CSE"
university = "NUB"
```

### Exercise 3: Arithmetic Expression

`a = 15` এবং `b = 5` দিয়ে f-string ব্যবহার করে sum ও product দেখাও।

### Exercise 4: Decimal Formatting

`price = 1234.5678`-কে দুই decimal place এবং হাজারের separator-সহ দেখাও।

### Exercise 5: Percentage Formatting

`score = 0.92345`-কে দুই decimal place-এ percentage হিসেবে দেখাও।

### Exercise 6: Alignment

`"Python"` string-টিকে 15-character width-এর মধ্যে center-align করো।

### Exercise 7: Curly Braces

f-string ব্যবহার করে নিচের output তৈরি করো:

```text
{Name}
```

এখানে `name = "Masum"`।

### Exercise 8: Debugging Syntax

নিচের code-এর output কী হবে?

```python
a = 10
b = 5

print(f"{a=}")
print(f"{a + b=}")
```

### Exercise 9: Dictionary Formatting

```python
student = {
    "name": "Masum",
    "marks": 90
}
```

f-string ব্যবহার করে name ও marks দেখাও।

### Exercise 10: Challenge

User-এর কাছ থেকে নাম, তিনটি subject-এর marks এবং প্রতিটি subject-এর maximum marks 100 ধরে input নাও। Total ও percentage বের করে f-string দিয়ে report তৈরি করো। Invalid numeric input handle করো এবং marks 0 থেকে 100-এর মধ্যে আছে কি না যাচাই করো।

## 21. Practice Answer Key

### Answer 1

```python
name = "Masum"

print(f"Welcome, {name}!")
```

### Answer 2

```python
name = "Masum"
department = "CSE"
university = "NUB"

print(f"{name} studies {department} at {university}.")
```

### Answer 3

```python
a = 15
b = 5

print(f"Sum: {a + b}")
print(f"Product: {a * b}")
```

Output:

```text
Sum: 20
Product: 75
```

### Answer 4

```python
price = 1234.5678

print(f"{price:,.2f}")
```

Output:

```text
1,234.57
```

### Answer 5

```python
score = 0.92345

print(f"{score:.2%}")
```

Output:

```text
92.35%
```

### Answer 6

```python
text = "Python"

print(f"|{text:^15}|")
```

### Answer 7

```python
name = "Masum"

print(f"{{{name}}}")
```

Output:

```text
{Masum}
```

### Answer 8

Output:

```text
a=10
a + b=15
```

### Answer 9

```python
student = {
    "name": "Masum",
    "marks": 90
}

print(f"Name: {student['name']}")
print(f"Marks: {student['marks']}")
```

### Answer 10

```python
name = input("Enter student name: ")

try:
    marks1 = float(input("Enter subject 1 marks: "))
    marks2 = float(input("Enter subject 2 marks: "))
    marks3 = float(input("Enter subject 3 marks: "))

    marks = [marks1, marks2, marks3]

    if not all(0 <= mark <= 100 for mark in marks):
        print("Each mark must be between 0 and 100.")
    else:
        total = sum(marks)
        percentage = total / 300 * 100

        print("=" * 30)
        print("STUDENT REPORT".center(30))
        print("=" * 30)
        print(f"Name       : {name}")
        print(f"Total Marks: {total:.2f}/300")
        print(f"Percentage : {percentage:.2f}%")
        print("=" * 30)

except ValueError:
    print("Please enter valid numeric marks.")
```

## 22. Best Practices

1. সাধারণ formatting-এর জন্য f-string ব্যবহার করতে শেখো।
2. Variable ও expression-এর জন্য `{}` ব্যবহার করো।
3. Decimal places দেখানোর জন্য `.2f`-এর মতো specification ব্যবহার করো।
4. Percentage formatting-এর আগে value ratio নাকি percentage, তা নিশ্চিত হও।
5. Debugging-এর সময় `f"{variable=}"` ব্যবহার করতে পারো।
6. Complex logic f-string-এর মধ্যে না লিখে আগে আলাদা variable-এ হিসাব করো।
7. Formatted output-কে numeric data হিসেবে ব্যবহার করার আগে মনে রাখবে, formatted result সাধারণত string।
8. User input থেকে data নিলে validation ও error handling যোগ করো।

## 23. Chapter Summary

- f-string হলো Python-এর আধুনিক string formatting method।
- String-এর আগে `f` বা `F` লিখতে হয়।
- `{variable}` দিয়ে variable-এর value দেখানো যায়।
- `{a + b}`-এর মতো expression-ও ব্যবহার করা যায়।
- `:.2f` দিয়ে দুই decimal place দেখানো যায়।
- `:.2%` ratio-কে percentage হিসেবে format করে।
- `:,` হাজারের separator দেখায়।
- `<`, `>` ও `^` দিয়ে left, right ও center alignment করা যায়।
- `{{` এবং `}}` দিয়ে literal curly braces দেখানো যায়।
- Python 3.8 থেকে `f"{variable=}"` debugging-এর জন্য ব্যবহার করা যায়।

## 24. Self-Assessment Checklist

- [ ] f-string-এর syntax বুঝি।
- [ ] Variable ও expression f-string-এ ব্যবহার করতে পারি।
- [ ] Function call-এর result দেখাতে পারি।
- [ ] Decimal places ও percentage format করতে পারি।
- [ ] Thousand separator ও alignment ব্যবহার করতে পারি।
- [ ] Curly braces output-এ দেখাতে পারি।
- [ ] Dictionary ও list-এর value f-string-এ ব্যবহার করতে পারি।
- [ ] Common f-string error শনাক্ত করতে পারি।
- [ ] Practical report ও receipt তৈরি করতে পারি।

**Next Topic:** `19_Expressions_and_Functions_in_f_Strings.md` — এখানে f-string-এর মধ্যে expression, function call, conditional expression এবং advanced usage আরও গভীরভাবে শিখব।