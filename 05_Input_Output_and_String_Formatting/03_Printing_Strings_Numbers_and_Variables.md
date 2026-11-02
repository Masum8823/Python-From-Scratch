# 03. Printing Strings, Numbers, and Variables

## 1. Introduction

Python-এ `print()` function ব্যবহার করে বিভিন্ন ধরনের data screen-এ দেখানো যায়। এর মধ্যে সবচেয়ে বেশি ব্যবহৃত তিনটি হলো:

1. **String:** Text বা লেখা।
2. **Number:** Numeric value, যেমন integer ও float।
3. **Variable:** কোনো value সংরক্ষণ করে রাখার জন্য ব্যবহৃত নাম।

উদাহরণ:

```python
print("Hello Python")
print(100)

name = "Masum"
print(name)
```

Output:

```text
Hello Python
100
Masum
```

এই topic-এ আমরা শিখব কীভাবে এই তিন ধরনের data আলাদাভাবে এবং একসঙ্গে print করতে হয়।

## 2. Printing Strings

**String** হলো text data, যেমন নাম, ঠিকানা, message বা কোনো sentence।

Python-এ string লেখার জন্য সাধারণত single quotation marks (`' '`) অথবা double quotation marks (`" "`) ব্যবহার করা হয়।

### Example 1: Printing a Simple String

```python
print("Hello, World!")
```

Output:

```text
Hello, World!
```

এখানে `"Hello, World!"` একটি string।

### Example 2: Using Single Quotes

```python
print('I am learning Python.')
```

Output:

```text
I am learning Python.
```

Single quotes এবং double quotes—দুটিই সাধারণ string লেখার জন্য ব্যবহার করা যায়।

### Example 3: Printing Multiple Strings

```python
print("Python", "is", "easy")
```

Output:

```text
Python is easy
```

একটি `print()` statement-এ একাধিক string comma দিয়ে দিলে Python default separator হিসেবে একটি space ব্যবহার করে।

### Example 4: Printing a String with Punctuation

```python
print("My name is Masum.")
print("I study CSE!")
```

Output:

```text
My name is Masum.
I study CSE!
```

String-এর মধ্যে punctuation, space এবং সাধারণ text লেখা যায়।

## 3. Printing Numbers

Python-এ `print()` দিয়ে সরাসরি number দেখানো যায়। Number লেখার সময় সাধারণত quotation marks ব্যবহার করা হয় না।

### Example 1: Integer

```python
print(10)
print(250)
print(-15)
```

Output:

```text
10
250
-15
```

Integer হলো পূর্ণসংখ্যা, যেমন `10`, `250` এবং `-15`।

### Example 2: Float

```python
print(3.14)
print(9.5)
print(-2.75)
```

Output:

```text
3.14
9.5
-2.75
```

Float ব্যবহার করে দশমিক সংখ্যাও প্রকাশ করা যায়।

### Example 3: Printing Arithmetic Results

```python
print(10 + 5)
print(20 - 8)
print(6 * 4)
print(20 / 5)
```

Output:

```text
15
12
24
4.0
```

এখানে Python প্রথমে calculation করে, তারপর result print করে।

**মনে রাখবে:** Python 3-এ `/` operator ব্যবহার করলে division-এর result সাধারণত float হয়। তাই `20 / 5`-এর output `4.0`।

## 4. Printing Variables

**Variable** হলো একটি নাম, যার মাধ্যমে কোনো value-কে reference করা যায়।

উদাহরণ:

```python
name = "Masum"
age = 22
cgpa = 3.95
```

এখানে:

- `name` একটি variable, যার value `"Masum"`।
- `age` একটি variable, যার value `22`।
- `cgpa` একটি variable, যার value `3.95`।

Variable-এর value print করতে variable-এর নাম সরাসরি `print()`-এর মধ্যে লিখতে হয়।

### Example

```python
name = "Masum"
age = 22
cgpa = 3.95

print(name)
print(age)
print(cgpa)
```

Output:

```text
Masum
22
3.95
```

Python variable-এর বর্তমান value দেখায়।

## 5. Variable Name vs String Literal

এই বিষয়টি beginner-দের জন্য খুবই গুরুত্বপূর্ণ।

### Example

```python
name = "Masum"

print(name)
print("name")
print("Masum")
```

Output:

```text
Masum
name
Masum
```

ব্যাখ্যা:

| Code | কী দেখাবে |
|---|---|
| `print(name)` | Variable `name`-এর value |
| `print("name")` | `name` শব্দটি |
| `print("Masum")` | `Masum` text-টি |

**মূল নিয়ম:**

- Variable-এর value print করতে quotation marks ছাড়া variable-এর নাম লেখো।
- সরাসরি text print করতে quotation marks-এর মধ্যে text লেখো।

আরেকটি উদাহরণ:

```python
city = "Dhaka"

print(city)
print("city")
```

Output:

```text
Dhaka
city
```

## 6. Printing Multiple Variables

একটি `print()` statement-এ একাধিক variable-এর value দেখানো যায়।

### Example 1: Two Variables

```python
first_name = "Abdulla"
last_name = "Masum"

print(first_name, last_name)
```

Output:

```text
Abdulla Masum
```

### Example 2: Multiple Variables

```python
name = "Masum"
department = "CSE"
university = "NUB"

print(name, department, university)
```

Output:

```text
Masum CSE NUB
```

Python প্রতিটি object-এর মাঝখানে default হিসেবে একটি space দিয়েছে।

### Example 3: Different Data Types

```python
name = "Masum"
age = 22
cgpa = 3.95
is_student = True

print(name, age, cgpa, is_student)
```

Output:

```text
Masum 22 3.95 True
```

একই `print()` statement-এ string, integer, float এবং boolean value দেখানো যায়।

## 7. Printing Strings and Variables Together

অনেক সময় শুধু variable-এর value দেখানোর বদলে একটি meaningful message দেখাতে হয়।

### Example 1: Comma-Separated Output

```python
name = "Masum"

print("My name is", name)
```

Output:

```text
My name is Masum
```

এখানে text এবং variable-এর value একসঙ্গে দেখানো হয়েছে।

### Example 2: Student Information

```python
name = "Masum"
department = "CSE"
university = "Northern University Bangladesh"

print("Name:", name)
print("Department:", department)
print("University:", university)
```

Output:

```text
Name: Masum
Department: CSE
University: Northern University Bangladesh
```

এই পদ্ধতিতে output পড়তে সহজ হয়।

### Example 3: Number with a Message

```python
marks = 85

print("Your marks are", marks)
```

Output:

```text
Your marks are 85
```

এখানে `marks`-এর value integer হলেও `print()` সহজেই message-এর সঙ্গে দেখাতে পারে।

## 8. Printing Variables with Calculations

Variable-এর value দিয়ে calculation করে result print করা যায়।

### Example 1: Addition

```python
a = 10
b = 20

print("Sum:", a + b)
```

Output:

```text
Sum: 30
```

### Example 2: Multiplication

```python
price = 50
quantity = 4

print("Total price:", price * quantity)
```

Output:

```text
Total price: 200
```

### Example 3: Average

```python
mark1 = 80
mark2 = 90
mark3 = 70

average = (mark1 + mark2 + mark3) / 3

print("Average marks:", average)
```

Output:

```text
Average marks: 80.0
```

এখানে প্রথমে তিনটি marks-এর average হিসাব করা হয়েছে, তারপর result print করা হয়েছে।

## 9. Printing the Same Variable Multiple Times

একই variable একাধিকবার print করা যায়।

```python
language = "Python"

print(language)
print(language)
print(language)
```

Output:

```text
Python
Python
Python
```

একটি variable-এর value যতবার প্রয়োজন, ততবার ব্যবহার করা যায়।

## 10. Printing Updated Variable Values

Variable-এর value পরিবর্তন হলে পরবর্তী `print()`-এ নতুন value দেখা যায়।

```python
score = 50

print(score)

score = 80

print(score)
```

Output:

```text
50
80
```

ব্যাখ্যা:

1. প্রথমে `score`-এর value ছিল `50`।
2. প্রথম `print()` `50` দেখিয়েছে।
3. পরে `score`-এর value `80` করা হয়েছে।
4. দ্বিতীয় `print()` নতুন value `80` দেখিয়েছে।

আগের output নিজে থেকে পরিবর্তন হয় না; নতুন `print()` বর্তমান value দেখায়।

## 11. Printing Without Changing Data Types

`print()` value দেখানোর জন্য ব্যবহৃত হয়। এটি variable-এর data type পরিবর্তন করে না।

### Example

```python
number = 25
text = "25"

print(number)
print(text)

print(type(number))
print(type(text))
```

Output:

```text
25
25
<class 'int'>
<class 'str'>
```

এখানে `number` হলো integer এবং `text` হলো string।

দুটির output দেখতে একই রকম হলেও data type আলাদা।

**মনে রাখবে:** Output একই দেখালেই data type একই হবে—এমন নয়।

## 12. Printing Special Characters Inside Strings

String-এর মধ্যে quotation marks বা অন্য special character দেখানোর প্রয়োজন হতে পারে।

### Example 1: Apostrophe Inside a String

```python
print("I'm learning Python.")
```

Output:

```text
I'm learning Python.
```

Double quotes-এর মধ্যে apostrophe থাকায় এটি সাধারণভাবে লেখা যায়।

### Example 2: Double Quotes Inside a String

```python
print('He said, "Hello!"')
```

Output:

```text
He said, "Hello!"
```

এখানে বাইরের string single quotes দিয়ে লেখা হয়েছে, তাই ভেতরের double quotes সহজেই ব্যবহার করা গেছে।

### Example 3: Using Escape Characters

```python
print("He said, \"Hello!\"")
```

Output:

```text
He said, "Hello!"
```

এখানে `\"` দিয়ে string-এর ভেতরে double quotation mark দেখানো হয়েছে।

Escape sequence নিয়ে বিস্তারিত আলোচনা হবে `07_Newlines_and_Escape_Sequences.md` ফাইলে।

## 13. Common Beginner Mistakes

### Mistake 1: Variable-এর value-এর বদলে নাম print করা

ভুল উদ্দেশ্য:

```python
name = "Masum"
print("name")
```

Output:

```text
name
```

সঠিক:

```python
print(name)
```

Output:

```text
Masum
```

### Mistake 2: String-এর quotation marks বাদ দেওয়া

ভুল:

```python
print(Hello)
```

এখানে Python `Hello`-কে variable বা identifier হিসেবে বিবেচনা করবে। এটি defined না থাকলে `NameError` হবে।

সঠিক:

```python
print("Hello")
```

### Mistake 3: Text এবং variable-কে সরাসরি পাশাপাশি লেখা

ভুল:

```python
name = "Masum"
print("Hello" name)
```

এটি `SyntaxError` তৈরি করবে।

সঠিক:

```python
print("Hello", name)
```

Output:

```text
Hello Masum
```

### Mistake 4: `+` দিয়ে String ও Number যোগ করা

ভুল:

```python
age = 22
print("Age: " + age)
```

এখানে string ও integer সরাসরি `+` দিয়ে concatenate করা যায় না। সাধারণভাবে `TypeError` হবে।

একটি সহজ সমাধান:

```python
print("Age:", age)
```

Output:

```text
Age: 22
```

String formatting ব্যবহার করেও এই কাজ করা যায়, যা পরের topic-গুলোতে শেখা হবে।

### Mistake 5: Calculation-এর বদলে String print করা

```python
print("10 + 20")
```

Output:

```text
10 + 20
```

এখানে Python calculation করেনি, কারণ expression-টি quotation marks-এর মধ্যে string হিসেবে লেখা হয়েছে।

Calculation করতে:

```python
print(10 + 20)
```

Output:

```text
30
```

## 14. Practical Programs

### Program 1: Personal Information

```python
name = "Masum"
age = 22
department = "CSE"
university = "NUB"

print("Name:", name)
print("Age:", age)
print("Department:", department)
print("University:", university)
```

Output:

```text
Name: Masum
Age: 22
Department: CSE
University: NUB
```

### Program 2: Simple Shopping Bill

```python
product = "Pen"
price = 10
quantity = 5

total = price * quantity

print("Product:", product)
print("Price per item:", price)
print("Quantity:", quantity)
print("Total bill:", total)
```

Output:

```text
Product: Pen
Price per item: 10
Quantity: 5
Total bill: 50
```

### Program 3: Student Marks

```python
name = "Masum"
marks1 = 80
marks2 = 90
marks3 = 85

total = marks1 + marks2 + marks3
average = total / 3

print("Student:", name)
print("Total marks:", total)
print("Average marks:", average)
```

Output:

```text
Student: Masum
Total marks: 255
Average marks: 85.0
```

### Program 4: Rectangle Area

```python
length = 10
width = 5

area = length * width

print("Length:", length)
print("Width:", width)
print("Area:", area)
```

Output:

```text
Length: 10
Width: 5
Area: 50
```

## 15. Practice Exercises

নিজে code লিখে output অনুমান করার চেষ্টা করো।

### Exercise 1: String Output

`print()` ব্যবহার করে নিজের নাম এবং department আলাদা লাইনে দেখাও।

### Exercise 2: Number Output

নিচের value-গুলো print করো:

- `100`
- `25.5`
- `-10`

### Exercise 3: Variable Output

`name`, `age` এবং `department` নামে তিনটি variable তৈরি করে তাদের value দেখাও।

### Exercise 4: Predict the Output

```python
x = 10
y = 20

print(x)
print("y")
print(x + y)
```

### Exercise 5: Student Information

নিচের তথ্য variable-এ রেখে সুন্দরভাবে print করো:

- Name: Rahim
- Department: CSE
- Marks: 88

### Exercise 6: Total Price

`price = 120` এবং `quantity = 3` ব্যবহার করে মোট দাম হিসাব করে দেখাও।

### Exercise 7: Find the Error

```python
name = "Masum"
age = 22

print("Name: " name)
print("Age:", age)
```

কোডে ভুল কোথায় এবং কীভাবে ঠিক করবে?

### Exercise 8: Data Type

```python
a = 50
b = "50"

print(a)
print(b)
print(type(a))
print(type(b))
```

Output অনুমান করো।

### Exercise 9: Average Marks

তিনটি subject-এর marks variable-এ রেখে total ও average print করার program লেখো।

### Exercise 10: Debugging

```python
number = 10

print("number")
print("Result:", "number" + 5)
```

কোন statement-এ কী সমস্যা রয়েছে, ব্যাখ্যা করো।

## 16. Practice Answer Key

### Answer 1

```python
print("Masum")
print("CSE")
```

### Answer 2

```python
print(100)
print(25.5)
print(-10)
```

### Answer 3

```python
name = "Masum"
age = 22
department = "CSE"

print(name)
print(age)
print(department)
```

### Answer 4

```text
10
y
30
```

`"y"` quotation marks-এর মধ্যে থাকায় variable-এর value নয়, `y` text-টি print হবে।

### Answer 5

```python
name = "Rahim"
department = "CSE"
marks = 88

print("Name:", name)
print("Department:", department)
print("Marks:", marks)
```

### Answer 6

```python
price = 120
quantity = 3

total = price * quantity

print("Total price:", total)
```

Output:

```text
Total price: 360
```

### Answer 7

ভুল statement:

```python
print("Name: " name)
```

সঠিক:

```python
print("Name:", name)
print("Age:", age)
```

### Answer 8

```text
50
50
<class 'int'>
<class 'str'>
```

`a` integer এবং `b` string।

### Answer 9

```python
mark1 = 70
mark2 = 80
mark3 = 90

total = mark1 + mark2 + mark3
average = total / 3

print("Total:", total)
print("Average:", average)
```

### Answer 10

প্রথম statement:

```python
print("number")
```

এটি variable-এর value নয়, `number` text-টি দেখায়।

দ্বিতীয় statement:

```python
print("Result:", "number" + 5)
```

এখানে string-এর সঙ্গে integer যোগ করার চেষ্টা করা হয়েছে, তাই `TypeError` হবে। সঠিকভাবে লিখতে পারো:

```python
number = 10
print("Result:", number + 5)
```

Output:

```text
Result: 15
```

## 17. Chapter Summary

এই topic থেকে আমরা শিখেছি:

1. `print()` দিয়ে string, number এবং variable-এর value দেখানো যায়।
2. String সাধারণত single বা double quotation marks দিয়ে লেখা হয়।
3. Number সরাসরি print করা যায়।
4. Variable-এর value দেখাতে quotation marks ছাড়া variable-এর নাম লিখতে হয়।
5. একাধিক value comma দিয়ে একসঙ্গে print করা যায়।
6. `print()`-এর মধ্যে calculation-এর expression লেখা যায়।
7. `print()` variable-এর data type পরিবর্তন করে না।
8. String ও number-এর মধ্যে `+` ব্যবহার করার সময় data type সম্পর্কে সতর্ক থাকতে হয়।
9. Meaningful output তৈরির জন্য text-এর সঙ্গে variable ব্যবহার করা যায়।

## 18. Self-Assessment Checklist

- [ ] String এবং number print করতে পারি।
- [ ] Variable-এর value সঠিকভাবে print করতে পারি।
- [ ] Variable name ও string literal-এর পার্থক্য বুঝি।
- [ ] একাধিক variable একই লাইনে দেখাতে পারি।
- [ ] Text-এর সঙ্গে variable-এর value দেখাতে পারি।
- [ ] Calculation-এর result print করতে পারি।
- [ ] String ও number-এর মধ্যে `+` ব্যবহারের নিয়ম বুঝি।
- [ ] Output দেখে সহজ coding error শনাক্ত করতে পারি।

**Next Topic:** `04_Printing_Multiple_Values.md` — এখানে একটি `print()` statement-এ একাধিক value দেখানো এবং সেগুলো কীভাবে সাজানো যায়, তা বিস্তারিত শিখব।