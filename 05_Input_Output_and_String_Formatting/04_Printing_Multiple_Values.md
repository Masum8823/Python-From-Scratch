# 04. Printing Multiple Values

## 1. Introduction

Python-এ একটি `print()` function ব্যবহার করে একাধিক value একসঙ্গে দেখানো যায়। যেমন, নাম, বয়স, department এবং CGPA আলাদা আলাদা `print()` statement না লিখেও একই লাইনে দেখানো সম্ভব।

### Example

```python
name = "Masum"
age = 22
department = "CSE"

print(name, age, department)
```

Output:

```text
Masum 22 CSE
```

এখানে একটি `print()` statement-এর মাধ্যমে তিনটি value দেখানো হয়েছে।

এই পদ্ধতি code ছোট রাখতে এবং একাধিক value একসঙ্গে দেখাতে সাহায্য করে।

## 2. Using Commas to Print Multiple Values

একাধিক value print করতে value-গুলোর মধ্যে comma ব্যবহার করা হয়।

### Example 1: Printing Two Values

```python
print("Hello", "Python")
```

Output:

```text
Hello Python
```

### Example 2: Printing Three Values

```python
print("Python", "Java", "C++")
```

Output:

```text
Python Java C++
```

### Example 3: Printing More Values

```python
print("Masum", 22, "CSE", 3.95)
```

Output:

```text
Masum 22 CSE 3.95
```

এখানে string, integer এবং float একসঙ্গে print করা হয়েছে।

**মনে রাখবে:** একাধিক value-এর মধ্যে comma দিলে `print()` default separator হিসেবে একটি space ব্যবহার করে।

## 3. Printing Multiple Variables

Variable-এর value একসঙ্গে print করা খুবই সাধারণ একটি কাজ।

### Example

```python
name = "Masum"
age = 22
cgpa = 3.95

print(name, age, cgpa)
```

Output:

```text
Masum 22 3.95
```

### Example: Student Information

```python
name = "Rahim"
department = "CSE"
university = "NUB"

print("Name:", name, "Department:", department, "University:", university)
```

Output:

```text
Name: Rahim Department: CSE University: NUB
```

এই output সঠিক হলেও অনেক বড় message-এর ক্ষেত্রে পড়তে কিছুটা অসুবিধা হতে পারে। তখন একাধিক line অথবা custom separator ব্যবহার করা যায়।

## 4. Printing Text and Variables Together

একাধিক value print করার সময় text এবং variable একসঙ্গে ব্যবহার করা যায়।

### Example 1

```python
name = "Masum"
print("My name is", name)
```

Output:

```text
My name is Masum
```

### Example 2

```python
product = "Laptop"
price = 55000

print("Product:", product, "Price:", price)
```

Output:

```text
Product: Laptop Price: 55000
```

### Example 3: Result Information

```python
name = "Masum"
marks = 85
grade = "A"

print("Student:", name, "Marks:", marks, "Grade:", grade)
```

Output:

```text
Student: Masum Marks: 85 Grade: A
```

এভাবে একাধিক value-কে meaningful message-এর মধ্যে দেখানো যায়।

## 5. Printing Multiple Values with Calculations

`print()`-এর মধ্যে calculation-এর result-ও অন্যান্য value-এর সঙ্গে দেখানো যায়।

### Example 1: Addition

```python
a = 10
b = 20

print("First number:", a, "Second number:", b, "Sum:", a + b)
```

Output:

```text
First number: 10 Second number: 20 Sum: 30
```

### Example 2: Shopping Bill

```python
price = 100
quantity = 4
total = price * quantity

print("Price:", price, "Quantity:", quantity, "Total:", total)
```

Output:

```text
Price: 100 Quantity: 4 Total: 400
```

### Example 3: Average Marks

```python
mark1 = 80
mark2 = 90
mark3 = 70

average = (mark1 + mark2 + mark3) / 3

print("Marks:", mark1, mark2, mark3, "Average:", average)
```

Output:

```text
Marks: 80 90 70 Average: 80.0
```

এখানে একাধিক variable এবং একটি calculation-এর result একই statement-এ দেখানো হয়েছে।

## 6. Understanding the Default Separator

একাধিক object print করার সময় Python default হিসেবে তাদের মাঝখানে একটি space দেয়।

### Example

```python
print("A", "B", "C")
```

Output:

```text
A B C
```

এই আচরণটি `sep` parameter-এর কারণে ঘটে।

নিচের code-টিও একই output তৈরি করবে:

```python
print("A", "B", "C", sep=" ")
```

Output:

```text
A B C
```

এখানে `sep=" "` স্পষ্টভাবে বলা হয়েছে যে প্রতিটি object-এর মাঝখানে একটি space থাকবে।

**গুরুত্বপূর্ণ:** `sep`-এর default value হলো একটি space (`' '`)।

## 7. Changing the Separator with `sep`

`sep` ব্যবহার করে একাধিক value-এর মাঝখানে space-এর পরিবর্তে অন্য character বা text বসানো যায়।

### Example 1: Hyphen Separator

```python
print("2026", "10", "16", sep="-")
```

Output:

```text
2026-10-16
```

### Example 2: Comma Separator

```python
print("Apple", "Banana", "Mango", sep=", ")
```

Output:

```text
Apple, Banana, Mango
```

### Example 3: Vertical Bar Separator

```python
print("Python", "Java", "C++", sep=" | ")
```

Output:

```text
Python | Java | C++
```

### Example 4: No Separator

```python
print("Py", "thon", sep="")
```

Output:

```text
Python
```

### Example 5: Custom Text as Separator

```python
print("Masum", "CSE", "NUB", sep=" -> ")
```

Output:

```text
Masum -> CSE -> NUB
```

এখানে `sep`-এর মধ্যে দেওয়া সম্পূর্ণ text প্রতিটি adjacent object-এর মাঝখানে বসেছে।

## 8. Printing Values on Separate Lines

একাধিক value-কে আলাদা লাইনে দেখানোর জন্য একাধিক `print()` statement ব্যবহার করা যায়।

### Example 1: Separate Statements

```python
print("Name: Masum")
print("Department: CSE")
print("University: NUB")
```

Output:

```text
Name: Masum
Department: CSE
University: NUB
```

### Example 2: Using One `print()` with Newline Characters

```python
print("Name: Masum\nDepartment: CSE\nUniversity: NUB")
```

Output:

```text
Name: Masum
Department: CSE
University: NUB
```

এখানে `\n` একটি newline তৈরি করেছে।

এই দুই পদ্ধতির output একই রকম হতে পারে, তবে code লেখার উদ্দেশ্য অনুযায়ী পদ্ধতি বেছে নেওয়া উচিত।

## 9. Printing Multiple Values on the Same Line

একটি `print()` statement-এর মধ্যেই comma দিয়ে একাধিক value দিলে সাধারণত একই লাইনে output দেখা যায়।

```python
print("One", "Two", "Three")
```

Output:

```text
One Two Three
```

একাধিক `print()` statement ব্যবহার করেও একই লাইনে output দেখানো যায়। সে ক্ষেত্রে `end` parameter ব্যবহার করা হয়।

```python
print("One", end=" ")
print("Two", end=" ")
print("Three")
```

Output:

```text
One Two Three
```

**পার্থক্য:**

- একই `print()`-এ একাধিক value: comma দিয়ে আলাদা করা হয়।
- একাধিক `print()`-কে একই লাইনে রাখতে: প্রয়োজন অনুযায়ী `end` ব্যবহার করা হয়।

`end` নিয়ে বিস্তারিত আলোচনা হবে `06_end_Parameter_in_print.md` ফাইলে।

## 10. Mixing Different Data Types

একটি `print()` statement-এ বিভিন্ন data type-এর value একসঙ্গে দেখানো যায়।

### Example

```python
name = "Masum"
age = 22
height = 5.8
is_student = True

print(name, age, height, is_student)
```

Output:

```text
Masum 22 5.8 True
```

এখানে চারটি আলাদা data type-এর value দেখানো হয়েছে:

| Variable | Data type | Value |
|---|---|---|
| `name` | `str` | `"Masum"` |
| `age` | `int` | `22` |
| `height` | `float` | `5.8` |
| `is_student` | `bool` | `True` |

Comma দিয়ে আলাদা object print করার জন্য তাদের একই data type হওয়া প্রয়োজন নেই।

## 11. Comma vs Plus Operator

একাধিক value print করার ক্ষেত্রে comma এবং `+` এক জিনিস নয়।

### Example 1: Using Comma

```python
age = 22

print("Age:", age)
```

Output:

```text
Age: 22
```

এখানে string ও integer আলাদা object হিসেবে দেওয়া হয়েছে। `print()` তাদের মাঝখানে default space দিয়েছে।

### Example 2: Using Plus with Strings

```python
first = "Hello"
second = "Python"

print(first + second)
```

Output:

```text
HelloPython
```

`+` দুটি string-কে concatenate করেছে। এখানে মাঝখানে কোনো space যোগ হয়নি।

### Example 3: Adding a Space Manually

```python
first = "Hello"
second = "Python"

print(first + " " + second)
```

Output:

```text
Hello Python
```

### Example 4: String and Integer with Plus

```python
age = 22
print("Age: " + age)
```

এই code-এ `TypeError` হবে, কারণ string-এর সঙ্গে integer সরাসরি `+` দিয়ে concatenate করা যায় না।

সাধারণ সমাধান:

```python
print("Age:", age)
```

Output:

```text
Age: 22
```

**মনে রাখবে:**

- Comma দিয়ে একাধিক object `print()` করা যায়।
- `+` string concatenate করতে পারে অথবা compatible numeric value যোগ করতে পারে।
- `+` ব্যবহার করে string ও integer সরাসরি concatenate করা যায় না।

## 12. Printing Multiple Values with `end`

`end` parameter output-এর শেষে কী থাকবে তা নির্ধারণ করে। এর default value newline (`'\n'`)।

### Example 1

```python
print("A", "B", end="!")
print("C")
```

Output:

```text
A B!C
```

প্রথম `print()`-এ `A` ও `B`-এর মাঝখানে default space রয়েছে। কিন্তু output-এর শেষে newline-এর পরিবর্তে `!` বসেছে।

### Example 2

```python
print("Python", "Java", sep="-", end=" | ")
print("C++", "JavaScript", sep="-")
```

Output:

```text
Python-Java | C++-JavaScript
```

এখানে:
- `sep="-"` প্রতিটি `print()`-এর object-গুলোর মাঝে hyphen বসিয়েছে।
- `end=" | "` প্রথম output-এর শেষে separator text বসিয়েছে।
- দ্বিতীয় `print()`-এর default `end` newline হওয়ায় output শেষে নতুন line শুরু হবে।

## 13. Practical Program: Student Profile

একটি student profile একই লাইনে এবং আলাদা লাইনে কীভাবে print করা যায়, দেখি।

### Version 1: Same Line

```python
name = "Masum"
department = "CSE"
semester = 9
cgpa = 3.95

print(name, department, semester, cgpa)
```

Output:

```text
Masum CSE 9 3.95
```

### Version 2: Custom Separator

```python
name = "Masum"
department = "CSE"
semester = 9
cgpa = 3.95

print(name, department, semester, cgpa, sep=" | ")
```

Output:

```text
Masum | CSE | 9 | 3.95
```

### Version 3: Labelled Output

```python
name = "Masum"
department = "CSE"
semester = 9
cgpa = 3.95

print("Name:", name)
print("Department:", department)
print("Semester:", semester)
print("CGPA:", cgpa)
```

Output:

```text
Name: Masum
Department: CSE
Semester: 9
CGPA: 3.95
```

এই তিনটি version-এর উদ্দেশ্য একই, কিন্তু output-এর format আলাদা।

## 14. Common Beginner Mistakes

### Mistake 1: Comma-এর বদলে space দিয়ে value আলাদা করা

ভুল:

```python
print("Python" "Java")
```

Output:

```text
PythonJava
```

পাশাপাশি থাকা string literal-গুলো Python concatenate করে।

সঠিক:

```python
print("Python", "Java")
```

Output:

```text
Python Java
```

### Mistake 2: `sep` শুধু দুইটি object-এর জন্য কাজ করে মনে করা

```python
print("A", "B", "C", "D", sep="-")
```

Output:

```text
A-B-C-D
```

`sep` সব adjacent object-এর মাঝে প্রয়োগ হয়।

### Mistake 3: `sep`-কে output-এর শুরুতে বা শেষে বসানোর parameter মনে করা

```python
print("A", "B", sep="-")
```

Output:

```text
A-B
```

`sep` শুধু object-গুলোর মাঝখানে বসে। Output-এর শেষে কী থাকবে, তা `end` নির্ধারণ করে।

### Mistake 4: Comma এবং `+`-এর পার্থক্য না বোঝা

```python
print("Total:", 100)
```

এটি কাজ করবে।

কিন্তু:

```python
print("Total: " + 100)
```

এটি `TypeError` তৈরি করবে, কারণ string-এর সঙ্গে integer সরাসরি concatenate করা হচ্ছে।

### Mistake 5: প্রতিটি `print()` একই লাইনে থাকবে মনে করা

```python
print("A")
print("B")
```

Output:

```text
A
B
```

প্রতিটি `print()`-এর default `end` newline। একই লাইনে রাখতে চাইলে `end` পরিবর্তন করতে হবে।

## 15. Practice Exercises

নিজে code লিখে output অনুমান করো।

### Exercise 1: Multiple Strings

একটি `print()` statement দিয়ে নিচের output তৈরি করো:

```text
Python Java C++
```

### Exercise 2: Multiple Numbers

একটি `print()` statement দিয়ে `10`, `20`, `30` এবং `40` দেখাও।

### Exercise 3: Custom Separator

নিচের output তৈরি করো:

```text
Dhaka-Bangladesh-Asia
```

### Exercise 4: Student Information

`name`, `department` এবং `cgpa` variable ব্যবহার করে একই লাইনে তথ্য দেখাও।

### Exercise 5: Predict the Output

```python
print("A", "B", "C", sep=":")
```

### Exercise 6: Predict the Output

```python
print(10, 20, sep="+", end="=")
print(30)
```

### Exercise 7: Find the Error

```python
age = 22
print("My age is " + age)
```

কেন error হবে? একটি সহজ সমাধান লেখো।

### Exercise 8: Same-Line Output

দুটি `print()` statement ব্যবহার করে নিচের output তৈরি করো:

```text
Hello Python
```

### Exercise 9: Calculation with Multiple Values

`a = 15` এবং `b = 5` ব্যবহার করে নিচের output তৈরি করো:

```text
First: 15 Second: 5 Sum: 20
```

### Exercise 10: Predict the Output

```python
print("Py", "thon", sep="", end="!")
print("3")
```

## 16. Practice Answer Key

### Answer 1

```python
print("Python", "Java", "C++")
```

### Answer 2

```python
print(10, 20, 30, 40)
```

### Answer 3

```python
print("Dhaka", "Bangladesh", "Asia", sep="-")
```

### Answer 4

```python
name = "Masum"
department = "CSE"
cgpa = 3.95

print("Name:", name, "Department:", department, "CGPA:", cgpa)
```

### Answer 5

Output:

```text
A:B:C
```

কারণ `sep=":"` প্রতিটি object-এর মাঝে colon বসায়।

### Answer 6

Output:

```text
10+20=30
```

প্রথম `print()`-এর শেষে `=` বসেছে এবং newline যোগ হয়নি।

### Answer 7

সঠিক সমাধান:

```python
age = 22
print("My age is", age)
```

অথবা:

```python
age = 22
print("My age is " + str(age))
```

দ্বিতীয় পদ্ধতিতে `str()` integer-কে string-এ convert করেছে।

### Answer 8

```python
print("Hello", end=" ")
print("Python")
```

### Answer 9

```python
a = 15
b = 5

print("First:", a, "Second:", b, "Sum:", a + b)
```

### Answer 10

Output:

```text
Python!3
```

প্রথমে `"Py"` এবং `"thon"`-এর মাঝে কোনো separator বসেনি। তারপর `end="!"` ব্যবহারের কারণে `3` একই লাইনে এসেছে।

## 17. Chapter Summary

এই topic থেকে আমরা শিখেছি:

1. একটি `print()` function দিয়ে একাধিক value দেখানো যায়।
2. একাধিক object comma দিয়ে আলাদা করতে হয়।
3. `print()`-এর default separator হলো একটি space।
4. `sep` দিয়ে object-গুলোর মাঝখানের separator পরিবর্তন করা যায়।
5. `end` দিয়ে output-এর শেষ নির্ধারণ করা যায়।
6. String, number, variable এবং calculation-এর result একসঙ্গে print করা যায়।
7. Comma দিয়ে একাধিক object print করা এবং `+` দিয়ে string concatenate করা আলাদা বিষয়।
8. Meaningful output তৈরি করতে text ও variable একসঙ্গে ব্যবহার করা যায়।

## 18. Self-Assessment Checklist

- [ ] একটি `print()`-এ একাধিক value দিতে পারি।
- [ ] Default separator কী, তা বুঝি।
- [ ] `sep` দিয়ে custom separator ব্যবহার করতে পারি।
- [ ] `end` দিয়ে একই লাইনে একাধিক output দেখাতে পারি।
- [ ] String ও number একসঙ্গে print করতে পারি।
- [ ] Comma ও `+`-এর পার্থক্য বুঝি।
- [ ] Output দেখে সহজ error শনাক্ত করতে পারি।

**Next Topic:** `05_sep_Parameter_in_print.md` — এখানে `sep` parameter-এর default value, custom separator, practical use case এবং common mistake আরও বিস্তারিত শিখব।