# 08. Formatting Output with `print()`

## 1. Introduction

Python-এ শুধু output দেখালেই হয় না, অনেক সময় output-কে সুন্দরভাবে সাজিয়ে দেখানোও প্রয়োজন হয়।

যেমন, একটি student-এর নাম, department, marks এবং result দেখাতে চাইলে তথ্যগুলো এমনভাবে সাজানো যায়:

```python
print("Student Information")
print("Name: Masum")
print("Department: CSE")
print("Marks: 90")
print("Result: Passed")
```

Output:

```text
Student Information
Name: Masum
Department: CSE
Marks: 90
Result: Passed
```

এখানে প্রতিটি তথ্য আলাদা লাইনে দেখানো হয়েছে। ফলে output সহজে পড়া যায়।

**Output Formatting** হলো output-কে এমনভাবে সাজানো, যাতে তথ্য পরিষ্কার, সুন্দর এবং সহজে বোঝা যায়।

## 2. Printing Labels and Values

কোনো value-এর আগে label দিলে output বুঝতে সুবিধা হয়।

### Example 1: Without Labels

```python
name = "Masum"
age = 22
department = "CSE"

print(name)
print(age)
print(department)
```

Output:

```text
Masum
22
CSE
```

এখানে value-গুলো দেখা যাচ্ছে, কিন্তু কোন value কী বোঝাচ্ছে তা স্পষ্ট নয়।

### Example 2: With Labels

```python
name = "Masum"
age = 22
department = "CSE"

print("Name:", name)
print("Age:", age)
print("Department:", department)
```

Output:

```text
Name: Masum
Age: 22
Department: CSE
```

এখানে label থাকার কারণে তথ্যগুলো সহজে বোঝা যাচ্ছে।

**মনে রাখবে:** `print()`-এ comma দিয়ে একাধিক value দিলে default separator হিসেবে একটি space ব্যবহৃত হয়।

## 3. Formatting Output with Multiple Values

একটি `print()` statement-এ একাধিক value দেখানো যায়।

### Example

```python
name = "Masum"
department = "CSE"
university = "NUB"

print("Name:", name, "Department:", department)
print("University:", university)
```

Output:

```text
Name: Masum Department: CSE
University: NUB
```

এখানে comma দিয়ে আলাদা করা value-গুলো default space দিয়ে যুক্ত হয়েছে।

### Another Example

```python
a = 10
b = 20

print("First Number:", a, "Second Number:", b)
print("Sum:", a + b)
```

Output:

```text
First Number: 10 Second Number: 20
Sum: 30
```

এভাবে text, variable এবং expression একসঙ্গে দেখানো যায়।

## 4. Using `sep` to Format Output

`sep` parameter ব্যবহার করে একাধিক object-এর মাঝখানে কী থাকবে তা নির্ধারণ করা যায়।

### Example 1: Hyphen Separator

```python
print("2026", "10", "16", sep="-")
```

Output:

```text
2026-10-16
```

### Example 2: Colon Separator

```python
print("Hours", "Minutes", "Seconds", sep=":")
```

Output:

```text
Hours:Minutes:Seconds
```

### Example 3: Vertical Bar Separator

```python
print("ID", "Name", "Marks", sep=" | ")
```

Output:

```text
ID | Name | Marks
```

`sep` ব্যবহার করলে output-এর বিভিন্ন অংশের মাঝে নির্দিষ্ট separator রাখা যায়।

## 5. Using `end` to Format Output

`end` parameter ব্যবহার করে output-এর শেষে কী থাকবে তা নির্ধারণ করা যায়।

### Example 1: Same-Line Output

```python
print("Python", end=" ")
print("Programming")
```

Output:

```text
Python Programming
```

### Example 2: Arrow Separator

```python
print("Start", end=" -> ")
print("Process", end=" -> ")
print("End")
```

Output:

```text
Start -> Process -> End
```

### Example 3: Printing a Result

```python
print("Calculation", end=": ")
print(10 + 20)
```

Output:

```text
Calculation: 30
```

এখানে `end=": "` প্রথম output-এর শেষে colon এবং space যোগ করেছে।

## 6. Using Newlines for Readable Output

`\n` ব্যবহার করে একটি string-এর মধ্যে নতুন লাইন তৈরি করা যায়।

### Example

```python
print("Student Information\nName: Masum\nDepartment: CSE\nMarks: 90")
```

Output:

```text
Student Information
Name: Masum
Department: CSE
Marks: 90
```

একই কাজ একাধিক `print()` দিয়েও করা যায়:

```python
print("Student Information")
print("Name: Masum")
print("Department: CSE")
print("Marks: 90")
```

দুটি পদ্ধতির output একই। কোনটি ব্যবহার করবে, তা code-এর readability এবং প্রয়োজনের ওপর নির্ভর করে।

## 7. Creating Headings and Separators

Output-এর heading ও section আলাদা করে দেখালে তথ্য আরও পরিষ্কার হয়।

### Example 1: Using Hyphens

```python
print("STUDENT INFORMATION")
print("-------------------")
print("Name: Masum")
print("Department: CSE")
```

Output:

```text
STUDENT INFORMATION
-------------------
Name: Masum
Department: CSE
```

### Example 2: Using Equal Signs

```python
print("====================")
print("  RESULT SUMMARY")
print("====================")
print("Marks: 90")
print("Result: Passed")
```

Output:

```text
====================
  RESULT SUMMARY
====================
Marks: 90
Result: Passed
```

এ ধরনের separator report বা console output-এ ব্যবহার করা যায়।

## 8. Using `\t` to Align Simple Output

`\t` হলো horizontal tab escape sequence। এটি তথ্যের মাঝে tab দিয়ে কিছুটা জায়গা তৈরি করে।

### Example

```python
print("Name\tMarks")
print("Masum\t90")
print("Rahim\t85")
print("Karim\t88")
```

Output-এর ধারণা:

```text
Name    Marks
Masum   90
Rahim   85
Karim   88
```

বাস্তবে tab-এর প্রস্থ terminal অনুযায়ী পরিবর্তিত হতে পারে। তাই `\t` সব ধরনের table-এ নিখুঁত alignment নিশ্চিত করে না।

### When to Use `\t`

- সাধারণ text output সাজাতে।
- দুটি value-এর মাঝে জায়গা রাখতে।
- ছোট ও সাধারণ table দেখাতে।

আরও নির্ভুল alignment প্রয়োজন হলে f-string-এর width formatting ব্যবহার করা যায়, যা পরবর্তী topic-এ বিস্তারিত শিখব।

## 9. Formatting Output with Arithmetic Expressions

`print()`-এর মধ্যে arithmetic expression ব্যবহার করে হিসাবের ফল সরাসরি দেখানো যায়।

### Example 1: Addition

```python
a = 10
b = 20

print("First Number:", a)
print("Second Number:", b)
print("Sum:", a + b)
```

Output:

```text
First Number: 10
Second Number: 20
Sum: 30
```

### Example 2: Average Marks

```python
math_marks = 80
english_marks = 90
python_marks = 100

total = math_marks + english_marks + python_marks
average = total / 3

print("Total Marks:", total)
print("Average Marks:", average)
```

Output:

```text
Total Marks: 270
Average Marks: 90.0
```

এখানে `print()`-এর মধ্যে variable ও calculated result দেখানো হয়েছে।

## 10. Formatting Numeric Output with `round()`

Floating-point result অনেক সময় decimal-এর পরে অনেকগুলো digit দেখাতে পারে। `round()` ব্যবহার করে সংখ্যাকে নির্দিষ্ট decimal places পর্যন্ত round করা যায়।

### Example

```python
price = 125.6789

print("Original Price:", price)
print("Rounded Price:", round(price, 2))
```

Output:

```text
Original Price: 125.6789
Rounded Price: 125.68
```

এখানে `round(price, 2)` সংখ্যাটিকে দুই decimal places পর্যন্ত round করেছে।

### Another Example

```python
a = 10
b = 3

result = a / b

print("Result:", result)
print("Rounded Result:", round(result, 2))
```

Output:

```text
Result: 3.3333333333333335
Rounded Result: 3.33
```

**মনে রাখবে:** `round()` সংখ্যার value round করে। এটি সব ক্ষেত্রে নির্দিষ্ট সংখ্যক decimal digit দেখানোর নিশ্চয়তা দেয় না। যেমন `round(5.0, 2)`-এর ফল `5.0` হতে পারে, `5.00` নয়। নির্দিষ্ট decimal format দেখানোর জন্য f-string ব্যবহার করা হয়।

## 11. Formatting Percentages

Percentage দেখাতে কোনো সংখ্যাকে 100 দিয়ে গুণ করে `%` চিহ্ন যোগ করা যায়।

### Example

```python
marks = 85
total_marks = 100

percentage = (marks / total_marks) * 100

print("Percentage:", percentage, "%")
```

Output:

```text
Percentage: 85.0 %
```

এখানে `%` একটি সাধারণ string হিসেবে দেখানো হয়েছে।

### Another Example

```python
completed = 75

print("Course Completed:", completed, "%")
```

Output:

```text
Course Completed: 75 %
```

এটি basic formatting-এর উদাহরণ। পরবর্তী সময়ে f-string ব্যবহার করে percentage আরও সুন্দরভাবে format করা শিখব।

## 12. Formatting Currency Values

টাকার পরিমাণ দেখানোর সময় currency symbol বা currency name ব্যবহার করা যায়।

### Example

```python
price = 1500

print("Price: Tk.", price)
```

Output:

```text
Price: Tk. 1500
```

### Another Example

```python
balance = 2500.50

print("Account Balance: BDT", balance)
```

Output:

```text
Account Balance: BDT 2500.5
```

এখানে সংখ্যাটি `2500.5` হিসেবে দেখানো হয়েছে। যদি সব সময় দুইটি decimal places দেখাতে চাও, তাহলে f-string-এর মতো নির্দিষ্ট formatting technique ব্যবহার করা প্রয়োজন।

## 13. Creating a Simple Report

একাধিক formatting technique ব্যবহার করে একটি সাধারণ report তৈরি করা যায়।

### Example

```python
name = "Masum"
department = "CSE"
marks = 90
result = "Passed"

print("=" * 30)
print("       STUDENT REPORT")
print("=" * 30)
print("Name:", name)
print("Department:", department)
print("Marks:", marks)
print("Result:", result)
print("=" * 30)
```

Output:

```text
==============================
       STUDENT REPORT
==============================
Name: Masum
Department: CSE
Marks: 90
Result: Passed
==============================
```

এখানে `"=" * 30` দিয়ে সমান চিহ্ন ৩০ বার তৈরি করা হয়েছে।

এটি string repetition-এর একটি উদাহরণ। `*` operator দিয়ে string-কে integer সংখ্যক বার repeat করা যায়।

## 14. Common Output Formatting Mistakes

### Mistake 1: String ও Integer সরাসরি `+` দিয়ে যুক্ত করা

ভুল code:

```python
age = 22

print("Age: " + age)
```

এখানে `TypeError` হবে, কারণ string এবং integer-কে এভাবে সরাসরি concatenate করা যায় না।

সঠিক পদ্ধতি:

```python
print("Age:", age)
```

অথবা:

```python
print("Age: " + str(age))
```

Output:

```text
Age: 22
```

### Mistake 2: `sep` ও `end` গুলিয়ে ফেলা

```python
print("A", "B", sep="-", end="!")
```

Output:

```text
A-B!
```

এখানে `sep` মাঝখানে এবং `end` শেষে কাজ করেছে।

### Mistake 3: `round()` দিয়ে নির্দিষ্ট Decimal Places পাওয়ার চেষ্টা

```python
price = 10.5

print(round(price, 2))
```

Output:

```text
10.5
```

এখানে `10.50` দেখা যাচ্ছে না। কারণ `round()` একটি numeric value ফেরত দেয়, নির্দিষ্ট সংখ্যক decimal places-সহ formatted text নয়।

### Mistake 4: Tab-কে Perfect Alignment-এর নিশ্চয়তা মনে করা

```python
print("Short\t90")
print("LongerName\t85")
```

বিভিন্ন terminal-এ column-এর alignment ভিন্ন হতে পারে। নিখুঁত column alignment প্রয়োজন হলে নির্দিষ্ট width formatting ব্যবহার করা ভালো।

## 15. Practical Programs

### Program 1: Student Information

```python
name = "Masum"
student_id = "1350"
department = "CSE"
university = "NUB"

print("=" * 30)
print("STUDENT INFORMATION")
print("=" * 30)
print("Name:", name)
print("Student ID:", student_id)
print("Department:", department)
print("University:", university)
print("=" * 30)
```

Output:

```text
==============================
STUDENT INFORMATION
==============================
Name: Masum
Student ID: 1350
Department: CSE
University: NUB
==============================
```

### Program 2: Marks Calculation Report

```python
subject1 = 80
subject2 = 90
subject3 = 85

total = subject1 + subject2 + subject3
average = total / 3

print("MARKS REPORT")
print("-" * 20)
print("Subject 1:", subject1)
print("Subject 2:", subject2)
print("Subject 3:", subject3)
print("-" * 20)
print("Total Marks:", total)
print("Average Marks:", round(average, 2))
```

Output:

```text
MARKS REPORT
--------------------
Subject 1: 80
Subject 2: 90
Subject 3: 85
--------------------
Total Marks: 255
Average Marks: 85.0
```

### Program 3: Simple Bill

```python
item = "Notebook"
quantity = 3
price = 50

total = quantity * price

print("=" * 25)
print("       SHOP BILL")
print("=" * 25)
print("Item:", item)
print("Quantity:", quantity)
print("Price per item:", price)
print("Total:", total)
print("=" * 25)
```

Output:

```text
=========================
       SHOP BILL
=========================
Item: Notebook
Quantity: 3
Price per item: 50
Total: 150
=========================
```

## 16. Practice Exercises

নিজে চেষ্টা করো। প্রতিটি program-এর output কেমন হবে, আগে অনুমান করবে।

### Exercise 1: Student Details

নিচের তথ্যগুলো সুন্দরভাবে print করো:

- Name: Masum
- Department: CSE
- University: NUB

প্রতিটি তথ্য আলাদা লাইনে দেখাবে।

### Exercise 2: Using `sep`

নিচের output তৈরি করো:

```text
2026-10-16
```

একটি `print()` statement এবং `sep` ব্যবহার করবে।

### Exercise 3: Using `end`

দুটি `print()` statement ব্যবহার করে নিচের output তৈরি করো:

```text
Python Programming
```

### Exercise 4: Calculate Total

তিনটি subject-এর marks যথাক্রমে `75`, `85` এবং `90`। Total marks সুন্দরভাবে label-সহ দেখাও।

### Exercise 5: Create a Heading

নিচের মতো output তৈরি করো:

```text
====================
   RESULT REPORT
====================
Marks: 90
Result: Passed
```

### Exercise 6: Output Prediction

```python
print("A", "B", "C", sep="-", end="!")
print("D")
```

Output কী হবে?

### Exercise 7: Average Calculation

তিনটি subject-এর marks `80`, `85` এবং `90`। Total এবং average দুই decimal places পর্যন্ত round করে দেখাও।

### Exercise 8: String Repetition

নিচের output তৈরি করো:

```text
**********
Python
**********
```

String repetition ব্যবহার করবে।

### Exercise 9: Currency Display

একটি variable-এ `2500` রাখো এবং নিচের মতো output দেখাও:

```text
Account Balance: BDT 2500
```

### Exercise 10: Create a Simple Report

Name, Department, Marks এবং Result নিয়ে একটি ছোট student report তৈরি করো। Heading এবং separator ব্যবহার করবে।

## 17. Practice Answer Key

### Answer 1

```python
print("Name: Masum")
print("Department: CSE")
print("University: NUB")
```

### Answer 2

```python
print("2026", "10", "16", sep="-")
```

### Answer 3

```python
print("Python", end=" ")
print("Programming")
```

### Answer 4

```python
a = 75
b = 85
c = 90

total = a + b + c

print("Total Marks:", total)
```

Output:

```text
Total Marks: 250
```

### Answer 5

```python
print("=" * 20)
print("   RESULT REPORT")
print("=" * 20)
print("Marks: 90")
print("Result: Passed")
```

### Answer 6

```text
A-B-C!D
```

প্রথম statement-এর শেষে `!` যোগ হয়েছে, কিন্তু newline যোগ হয়নি।

### Answer 7

```python
a = 80
b = 85
c = 90

total = a + b + c
average = total / 3

print("Total:", total)
print("Average:", round(average, 2))
```

Output:

```text
Total: 255
Average: 85.0
```

### Answer 8

```python
print("*" * 10)
print("Python")
print("*" * 10)
```

### Answer 9

```python
balance = 2500

print("Account Balance: BDT", balance)
```

### Answer 10

```python
name = "Masum"
department = "CSE"
marks = 90
result = "Passed"

print("=" * 25)
print("   STUDENT REPORT")
print("=" * 25)
print("Name:", name)
print("Department:", department)
print("Marks:", marks)
print("Result:", result)
print("=" * 25)
```

## 18. Chapter Summary

এই topic-এ আমরা শিখেছি:

1. Output formatting হলো output-কে সুন্দর ও readable করে সাজানো।
2. Label ব্যবহার করলে variable-এর value সহজে বোঝা যায়।
3. `print()`-এ comma দিয়ে একাধিক value দেখানো যায়।
4. `sep` object-গুলোর মাঝখানের separator নির্ধারণ করে।
5. `end` output-এর শেষে কী থাকবে তা নির্ধারণ করে।
6. `\n` এবং `\t` দিয়ে output-এ নতুন লাইন ও tab যোগ করা যায়।
7. String repetition দিয়ে heading ও separator তৈরি করা যায়।
8. Arithmetic expression সরাসরি `print()`-এ দেখানো যায়।
9. `round()` সংখ্যাকে round করে, কিন্তু নির্দিষ্ট সংখ্যক decimal places দেখানোর নিশ্চয়তা দেয় না।
10. আরও নির্ভুল numeric formatting-এর জন্য f-string শেখা প্রয়োজন।

## 19. Self-Assessment Checklist

- [ ] Label ও value একসঙ্গে print করতে পারি।
- [ ] একাধিক value সুন্দরভাবে দেখাতে পারি।
- [ ] `sep` এবং `end` ব্যবহার করতে পারি।
- [ ] `\n` ও `\t` দিয়ে output সাজাতে পারি।
- [ ] Heading ও separator তৈরি করতে পারি।
- [ ] হিসাবের ফল label-সহ দেখাতে পারি।
- [ ] `round()`-এর কাজ ও সীমাবদ্ধতা বুঝি।
- [ ] একটি simple report বা bill তৈরি করতে পারি।

**Next Topic:** `09_Understanding_the_input_Function.md` — এবার আমরা `input()` function শিখব, যার মাধ্যমে user-এর কাছ থেকে keyboard দিয়ে তথ্য নেওয়া যায়।