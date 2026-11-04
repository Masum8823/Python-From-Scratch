# 21. String Alignment, Width and Padding

## 1. Introduction

Python-এ output শুধু সঠিক হলেই হয় না; সেটি সুন্দর ও সহজে পড়ার উপযোগী হওয়াও গুরুত্বপূর্ণ।

ধরো, আমরা কয়েকজন student-এর নাম ও marks দেখাতে চাই।

```python
print("Name: Masum")
print("Name: Ritu")
print("Name: Abdullah")
```

Output:

```text
Name: Masum
Name: Ritu
Name: Abdullah
```

এখানে output ঠিক আছে। তবে নির্দিষ্ট column-এ data সাজাতে চাইলে alignment ও width ব্যবহার করা যায়।

Python-এর f-string formatting দিয়ে আমরা:

- Text বামে, ডানে বা মাঝখানে সাজাতে পারি।
- নির্দিষ্ট width-এর field তৈরি করতে পারি।
- ফাঁকা জায়গায় space বা অন্য character বসাতে পারি।
- Number-কে একই column-এ সাজাতে পারি।
- Table ও report-এর output সুন্দর করতে পারি।

## 2. What Is Alignment?

**Alignment** হলো নির্দিষ্ট জায়গার মধ্যে text বা number কীভাবে সাজানো হবে, তা নির্ধারণ করা।

Python-এ প্রধান তিনটি alignment option রয়েছে:

| Symbol | Meaning |
|---|---|
| `<` | Left alignment |
| `>` | Right alignment |
| `^` | Center alignment |

### Example

```python
name = "Python"

print(f"|{name:<12}|")
print(f"|{name:>12}|")
print(f"|{name:^12}|")
```

Output:

```text
|Python      |
|      Python|
|   Python   |
```

এখানে `12` হলো field width।

- `<12` text-কে বাম দিকে সাজায়।
- `>12` text-কে ডান দিকে সাজায়।
- `^12` text-কে মাঝখানে সাজায়।

দুই পাশে `|` ব্যবহার করা হয়েছে, যাতে space-গুলো স্পষ্ট দেখা যায়।

## 3. Understanding Field Width

**Field width** হলো formatted value-এর জন্য নির্ধারিত ন্যূনতম character width।

### Example

```python
name = "Masum"

print(f"|{name:5}|")
print(f"|{name:10}|")
print(f"|{name:15}|")
```

Output:

```text
|Masum|
|Masum     |
|Masum          |
```

এখানে width বাড়ার সঙ্গে সঙ্গে ডান পাশে space বেড়েছে।

### Important Rule

Field width হলো minimum width, maximum width নয়।

```python
name = "Abdullah"

print(f"|{name:5}|")
```

Output:

```text
|Abdullah|
```

`Abdullah`-এর length 5-এর বেশি হওয়ায় Python text-টিকে ছোট করে দেয়নি।

**মনে রাখবে:** Field width নির্ধারণ করলেই text truncate হয় না।

## 4. Left Alignment

Left alignment-এর জন্য `<` ব্যবহার করা হয়।

### Example

```python
name = "Masum"

print(f"|{name:<10}|")
```

Output:

```text
|Masum     |
```

Text বাম দিকে থাকে এবং বাকি জায়গা ডান পাশে space দিয়ে পূরণ হয়।

### Multiple Values

```python
print(f"|{'Masum':<10}|")
print(f"|{'Ritu':<10}|")
print(f"|{'Abdullah':<10}|")
```

Output:

```text
|Masum     |
|Ritu      |
|Abdullah  |
```

একই width ব্যবহার করায় প্রতিটি value একই জায়গা থেকে শুরু হয়েছে।

## 5. Right Alignment

Right alignment-এর জন্য `>` ব্যবহার করা হয়।

### Example

```python
name = "Masum"

print(f"|{name:>10}|")
```

Output:

```text
|     Masum|
```

এখানে text ডান দিকে থাকে এবং space বাম পাশে যোগ হয়।

### Aligning Numbers

```python
marks1 = 85
marks2 = 100
marks3 = 7

print(f"|{marks1:>5}|")
print(f"|{marks2:>5}|")
print(f"|{marks3:>5}|")
```

Output:

```text
|   85|
|  100|
|    7|
```

Number-কে ডান দিকে সাজালে marks বা quantity-এর column পড়তে সুবিধা হয়।

## 6. Center Alignment

Center alignment-এর জন্য `^` ব্যবহার করা হয়।

### Example

```python
title = "Python"

print(f"|{title:^12}|")
```

Output:

```text
|   Python   |
```

Text-এর দুই পাশে space যোগ করে তাকে মাঝখানে রাখা হয়েছে।

### Practical Example

```python
print("=" * 30)
print(f"{'STUDENT REPORT':^30}")
print("=" * 30)
```

Output:

```text
==============================
        STUDENT REPORT
==============================
```

এভাবে report-এর heading সুন্দরভাবে সাজানো যায়।

**নোট:** Field width-এর মধ্যে space সমানভাবে ভাগ করা না গেলে দুই পাশের space-এর সংখ্যা এক ঘর আলাদা হতে পারে।

## 7. Padding in Python

**Padding** হলো কোনো value-এর পাশে অতিরিক্ত character যোগ করে নির্দিষ্ট width পূরণ করা।

Padding-এর জন্য space ছাড়াও `*`, `-`, `0` বা অন্য character ব্যবহার করা যায়।

### Syntax

```python
f"{value:fill<width}"
```

এখানে:

- `fill` হলো যে character দিয়ে জায়গা পূরণ হবে।
- `<` alignment নির্দেশ করে।
- `width` হলো minimum field width।

### Example

```python
name = "Python"

print(f"{name:*<10}")
print(f"{name:*>10}")
print(f"{name:*^10}")
```

Output:

```text
Python****
****Python
**Python**
```

এখানে:

- `*<10` বাম দিকে text রেখে ডানে `*` যোগ করে।
- `*>10` ডানে text রেখে বামে `*` যোগ করে।
- `*^10` text-কে মাঝখানে রেখে দুই পাশে `*` যোগ করে।

## 8. Custom Padding Characters

Padding-এর জন্য বিভিন্ন character ব্যবহার করা যায়।

### Example

```python
name = "Masum"

print(f"{name:-<10}")
print(f"{name:.>10}")
print(f"{name:_^10}")
```

Output:

```text
Masum-----
.....Masum
__Masum___
```

এখানে:

- `-` দিয়ে dash padding হয়েছে।
- `.` দিয়ে dot padding হয়েছে।
- `_` দিয়ে underscore padding হয়েছে।

### Practical Example: Heading

```python
title = "PYTHON"

print(f"{title:*^20}")
```

Output:

```text
*******PYTHON*******
```

এখানে মোট field width 20।

## 9. Zero Padding for Integers

Integer-এর বাম পাশে zero যোগ করতে `0` ব্যবহার করা যায়।

### Example

```python
number = 42

print(f"{number:05d}")
```

Output:

```text
00042
```

এখানে:

- `0` zero padding নির্দেশ করে।
- `5` minimum width।
- `d` integer format নির্দেশ করে।

### More Examples

```python
number = 7

print(f"{number:03d}")
print(f"{number:05d}")
print(f"{number:08d}")
```

Output:

```text
007
00007
00000007
```

এটি serial number, fixed-width display বা কিছু identifier format করার কাজে লাগতে পারে।

তবে identifier-এর leading zero ডেটার অংশ হলে সেটিকে string হিসেবে সংরক্ষণ করাও ভালো পদ্ধতি।

## 10. Padding Numbers with Signs

Positive বা negative number-এর ক্ষেত্রে sign ও padding একসঙ্গে ব্যবহার করা যায়।

### Example

```python
number = 42

print(f"{number:+06d}")
```

Output:

```text
+00042
```

এখানে `+` sign দেখায় এবং `06d` sign-সহ মোট width 6 পূরণ করতে zero ব্যবহার করে।

### Negative Number

```python
number = -42

print(f"{number:+06d}")
```

Output:

```text
-00042
```

### Decimal Number

```python
price = 45.5

print(f"{price:010.2f}")
```

Output:

```text
0000045.50
```

এখানে width 10 এবং দুই decimal place ব্যবহার করা হয়েছে।

## 11. Formatting Strings and Numbers Together

বাস্তব output-এ সাধারণত text ও number একসঙ্গে থাকে।

### Example

```python
name = "Masum"
marks = 85

print(f"{name:<12}{marks:>5}")
```

Output:

```text
Masum          85
```

এখানে name-এর জন্য 12 width এবং marks-এর জন্য 5 width রাখা হয়েছে।

### Another Example

```python
name = "Ritu"
marks = 100

print(f"{name:<12} | {marks:>5}")
```

Output:

```text
Ritu         |   100
```

এভাবে একাধিক field পাশাপাশি সাজিয়ে table তৈরি করা যায়।

## 12. Creating a Simple Table

একটি table তৈরি করতে column-এর জন্য একই width ব্যবহার করতে হয়।

### Example

```python
print(f"{'Name':<15}{'Department':<15}{'Marks':>8}")
print("-" * 38)

print(f"{'Masum':<15}{'CSE':<15}{85:>8}")
print(f"{'Ritu':<15}{'CSE':<15}{100:>8}")
print(f"{'Abdullah':<15}{'EEE':<15}{92:>8}")
```

Output:

```text
Name           Department        Marks
--------------------------------------
Masum          CSE                  85
Ritu           CSE                 100
Abdullah       EEE                  92
```

এখানে:

- Name-এর width 15।
- Department-এর width 15।
- Marks-এর width 8।
- Text left-aligned এবং marks right-aligned।

এই পদ্ধতি দিয়ে console-based report তৈরি করা যায়।

## 13. Formatting Decimal Numbers in Columns

Float number-কে একই width ও decimal places-এ দেখালে comparison সহজ হয়।

### Example

```python
students = [
    ("Masum", 3.95),
    ("Ritu", 3.85),
    ("Abdullah", 3.90)
]

print(f"{'Name':<15}{'CGPA':>10}")
print("-" * 25)

for name, cgpa in students:
    print(f"{name:<15}{cgpa:>10.2f}")
```

Output:

```text
Name                 CGPA
-------------------------
Masum                3.95
Ritu                 3.85
Abdullah             3.90
```

এখানে `.2f` দুই decimal places দেখায় এবং `>10` number-কে ডান দিকে সাজায়।

## 14. Using Alignment with Thousand Separators

Comma separator এবং alignment একসঙ্গে ব্যবহার করা যায়।

### Example

```python
amounts = [1250.5, 25000, 987654.321]

print(f"{'Amount':>18}")
print("-" * 18)

for amount in amounts:
    print(f"{amount:>18,.2f}")
```

Output:

```text
            Amount
------------------
          1,250.50
         25,000.00
        987,654.32
```

এখানে `>18,.2f` ব্যবহার করা হয়েছে:

- `>18` right alignment ও minimum width।
- `,` thousand separator।
- `.2f` দুই decimal places।

## 15. Alignment with Different Data Types

String, integer ও float-এর alignment-এর default আচরণ আলাদা হতে পারে।

### Example

```python
name = "Python"
number = 42
price = 19.5

print(f"|{name:10}|")
print(f"|{number:10}|")
print(f"|{price:10.2f}|")
```

Output:

```text
|Python    |
|        42|
|     19.50|
```

সাধারণভাবে:

- String defaultভাবে left-aligned হয়।
- Integer ও float defaultভাবে right-aligned হয়।
- নিজের প্রয়োজন অনুযায়ী `<`, `>` বা `^` ব্যবহার করে alignment স্পষ্ট করে দেওয়া ভালো।

## 16. Dynamic Width

কখনো field width variable দিয়ে নিয়ন্ত্রণ করতে হয়। f-string-এর format specification-এর মধ্যে nested field ব্যবহার করা যায়।

### Example

```python
name = "Masum"
width = 12

print(f"|{name:<{width}}|")
```

Output:

```text
|Masum       |
```

এখানে `{width}`-এর value 12 হওয়ায় name-এর field width 12 হয়েছে।

### Dynamic Number Width

```python
number = 123
width = 8

print(f"|{number:>{width}}|")
```

Output:

```text
|     123|
```

এটি কাজে লাগে যখন user input বা data অনুযায়ী column-এর width পরিবর্তন করতে হয়।

## 17. Dynamic Precision

Decimal places-ও variable দিয়ে নির্ধারণ করা যায়।

### Example

```python
number = 12.345678
precision = 3

print(f"{number:.{precision}f}")
```

Output:

```text
12.346
```

এখানে `precision = 3` হওয়ায় তিন decimal places দেখানো হয়েছে।

### Width and Precision Together

```python
number = 123.456789
width = 12
precision = 2

print(f"|{number:{width}.{precision}f}|")
```

Output:

```text
|      123.46|
```

এখানে width 12 এবং precision 2।

## 18. Text Truncation and Long Strings

Field width নির্ধারণ করলেই text কেটে যায় না।

### Example

```python
name = "AbdullahAlMasum"

print(f"|{name:10}|")
```

Output:

```text
|AbdullahAlMasum|
```

Text-এর length 10-এর বেশি হলেও পুরো text দেখানো হয়েছে।

### Manually Limiting String Length

String-এর একটি অংশ দেখাতে slicing ব্যবহার করা যায়।

```python
name = "AbdullahAlMasum"

print(f"|{name[:10]:<10}|")
```

Output:

```text
|AbdullahAl|
```

এখানে `name[:10]` প্রথম 10টি character নিয়েছে, আর `<10` সেই অংশকে left-align করেছে।

**মনে রাখবে:** Slicing text-এর একটি অংশ নেয়; formatting width নিজে থেকে text truncate করে না।

## 19. Practical Program: Student Marks Table

```python
students = [
    ("Masum", 85),
    ("Ritu", 100),
    ("Abdullah", 92),
    ("Mahin", 78)
]

print("=" * 35)
print(f"{'STUDENT MARKS':^35}")
print("=" * 35)

print(f"{'Name':<18}{'Marks':>8}{'Grade':>9}")
print("-" * 35)

for name, marks in students:
    grade = "A" if marks >= 80 else "B" if marks >= 60 else "C"

    print(f"{name:<18}{marks:>8}{grade:>9}")

print("=" * 35)
```

Output:

```text
===================================
          STUDENT MARKS
===================================
Name                 Marks    Grade
-----------------------------------
Masum                   85        A
Ritu                   100        A
Abdullah                92        A
Mahin                   78        B
===================================
```

এখানে alignment, field width এবং conditional expression একসঙ্গে ব্যবহার করা হয়েছে। Grade নির্ধারণের নিয়মটি শুধু এই example-এর জন্য।

## 20. Practical Program: Product Price Table

```python
products = [
    ("Keyboard", 1250.5, 2),
    ("Mouse", 650, 3),
    ("Monitor", 12500, 1)
]

print("=" * 48)
print(f"{'PRODUCT PRICE LIST':^48}")
print("=" * 48)

print(f"{'Product':<15}{'Price':>12}{'Quantity':>10}{'Total':>11}")
print("-" * 48)

for product, price, quantity in products:
    total = price * quantity

    print(
        f"{product:<15}"
        f"{price:>12,.2f}"
        f"{quantity:>10}"
        f"{total:>11,.2f}"
    )

print("=" * 48)
```

Output:

```text
================================================
              PRODUCT PRICE LIST
================================================
Product               Price  Quantity      Total
------------------------------------------------
Keyboard           1,250.50         2   2,501.00
Mouse                650.00         3   1,950.00
Monitor           12,500.00         1  12,500.00
================================================
```

এখানে প্রতিটি column-এর জন্য নির্দিষ্ট width ব্যবহার করা হয়েছে, যাতে product, price, quantity ও total সুন্দরভাবে সাজানো থাকে।

## 21. Common Mistakes

### Mistake 1: Using Alignment Without Width

```python
name = "Masum"

print(f"{name:<}")
```

এভাবে alignment-এর সঙ্গে কোনো width না দেওয়ায় format specification সঠিক নয়। সাধারণভাবে alignment ব্যবহার করতে width দাও।

```python
print(f"{name:<10}")
```

Output:

```text
Masum     
```

### Mistake 2: Expecting Truncation

```python
name = "Abdullah"

print(f"{name:3}")
```

Output:

```text
Abdullah
```

Width 3 হলেও text ছোট হয় না।

### Mistake 3: Confusing Width and Precision

```python
number = 12.3456

print(f"{number:10.2f}")
```

Output:

```text
     12.35
```

এখানে `10` field width এবং `.2f` decimal precision নির্দেশ করে।

### Mistake 4: Using the Wrong Alignment

```python
number = 42

print(f"|{number:<8}|")
print(f"|{number:>8}|")
```

Output:

```text
|42      |
|      42|
```

Text এবং number-এর alignment প্রয়োজন অনুযায়ী নির্বাচন করতে হবে।

### Mistake 5: Forgetting to Reuse the Same Column Width

প্রতিটি row-তে আলাদা width ব্যবহার করলে table-এর column সোজা নাও থাকতে পারে। Table বানানোর সময় একই column-এর জন্য একই width ব্যবহার করো।

## 22. Practice Exercises

### Exercise 1: Basic Alignment

`"Python"` string-কে 15-character width-এ left, right ও center-align করো।

### Exercise 2: Custom Padding

`"Masum"`-কে 12-character width-এ `*` দিয়ে left, right ও center padding করো।

### Exercise 3: Zero Padding

`number = 73`-কে আট character width-এ zero padding-সহ দেখাও।

### Exercise 4: Number Alignment

`marks = [7, 85, 100, 92]`-এর প্রতিটি number-কে 6-character width-এ right-align করো।

### Exercise 5: Table Creation

তিনজন student-এর name ও marks নিয়ে একটি table তৈরি করো। Name left-aligned এবং marks right-aligned হবে।

### Exercise 6: Dynamic Width

`name = "Masum"` এবং `width = 15` ব্যবহার করে dynamic width-সহ left-aligned output তৈরি করো।

### Exercise 7: Dynamic Precision

`number = 12.345678` এবং `precision = 4` ব্যবহার করে dynamic precision-এ number দেখাও।

### Exercise 8: Long Text

`"AbdullaAlMasum"` string-এর প্রথম 8টি character নিয়ে 10-character width-এ left-align করো।

### Exercise 9: Output Prediction

```python
name = "Python"
number = 42

print(f"|{name:^10}|")
print(f"|{number:06d}|")
print(f"|{number:*^8}|")
```

Output কী হবে?

### Exercise 10: Mini Challenge

কমপক্ষে চারটি product-এর name, price ও quantity নিয়ে একটি price table তৈরি করো। Product name left-aligned, price এবং total right-aligned হবে। Monetary values দুই decimal places ও thousand separator-সহ দেখাবে।

## 23. Practice Answer Key

### Answer 1

```python
name = "Python"

print(f"|{name:<15}|")
print(f"|{name:>15}|")
print(f"|{name:^15}|")
```

### Answer 2

```python
name = "Masum"

print(f"{name:*<12}")
print(f"{name:*>12}")
print(f"{name:*^12}")
```

### Answer 3

```python
number = 73

print(f"{number:08d}")
```

Output:

```text
00000073
```

### Answer 4

```python
marks = [7, 85, 100, 92]

for mark in marks:
    print(f"{mark:>6}")
```

### Answer 5

```python
students = [
    ("Masum", 85),
    ("Ritu", 100),
    ("Mahin", 78)
]

print(f"{'Name':<15}{'Marks':>8}")
print("-" * 23)

for name, marks in students:
    print(f"{name:<15}{marks:>8}")
```

### Answer 6

```python
name = "Masum"
width = 15

print(f"|{name:<{width}}|")
```

### Answer 7

```python
number = 12.345678
precision = 4

print(f"{number:.{precision}f}")
```

Output:

```text
12.3457
```

### Answer 8

```python
name = "AbdullaAlMasum"

print(f"|{name[:8]:<10}|")
```

Output:

```text
|AbdullaA  |
```

### Answer 9

Output:

```text
|  Python  |
|000042|
|***42***|
```

### Answer 10

```python
products = [
    ("Keyboard", 1250.5, 2),
    ("Mouse", 650, 3),
    ("Monitor", 12500, 1),
    ("USB Drive", 850.75, 4)
]

print(f"{'Product':<15}{'Price':>12}{'Quantity':>10}{'Total':>14}")
print("-" * 51)

for name, price, quantity in products:
    total = price * quantity

    print(
        f"{name:<15}"
        f"{price:>12,.2f}"
        f"{quantity:>10}"
        f"{total:>14,.2f}"
    )
```

## 24. Chapter Summary

- Alignment হলো field-এর মধ্যে value সাজানোর পদ্ধতি।
- `<` left alignment, `>` right alignment এবং `^` center alignment নির্দেশ করে।
- Field width হলো formatted value-এর minimum width।
- Padding দিয়ে space বা custom character যোগ করা যায়।
- `0` ব্যবহার করে integer-এর zero padding করা যায়।
- Text, number এবং decimal value-কে একই column-এ সাজানো যায়।
- Dynamic width ও precision ব্যবহার করে variable অনুযায়ী formatting নিয়ন্ত্রণ করা যায়।
- Width নিজে থেকে text truncate করে না; slicing দিয়ে text-এর অংশ নেওয়া যায়।
- একই column-এর জন্য একই width ব্যবহার করলে table আরও readable হয়।

## 25. Self-Assessment Checklist

- [ ] Left, right ও center alignment বুঝি।
- [ ] Field width কী তা ব্যাখ্যা করতে পারি।
- [ ] Custom padding character ব্যবহার করতে পারি।
- [ ] Integer-এর zero padding করতে পারি।
- [ ] Text ও number-এর column সাজাতে পারি।
- [ ] Decimal places ও width একসঙ্গে ব্যবহার করতে পারি।
- [ ] Dynamic width ও precision ব্যবহার করতে পারি।
- [ ] Table ও report তৈরি করতে পারি।
- [ ] Width ও truncation-এর পার্থক্য বুঝি।

**Next Topic:** `22_str_format_Method.md` — এখানে পুরোনো কিন্তু গুরুত্বপূর্ণ `.format()` method-এর syntax, positional arguments, named arguments, indexing এবং formatting rules শিখব।