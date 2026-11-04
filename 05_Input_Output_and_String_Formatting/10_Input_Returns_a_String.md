# 10. `input()` Returns a String

## 1. Introduction

Python-এর `input()` function ব্যবহার করে user-এর কাছ থেকে তথ্য নেওয়া যায়। কিন্তু এর একটি গুরুত্বপূর্ণ বৈশিষ্ট্য হলো, **`input()` সবসময় user-এর দেওয়া input-কে string হিসেবে return করে।**

User text, number বা অন্য কোনো character লিখুক না কেন, `input()`-এর return value হবে string।

### Example

```python
age = input("Enter your age: ")

print(age)
print(type(age))
```

Sample Interaction:

```text
Enter your age: 22
22
<class 'str'>
```

এখানে user `22` লিখেছে। দেখতে এটি একটি সংখ্যা মনে হলেও Python এটিকে string `"22"` হিসেবে গ্রহণ করেছে।

`type()` function দিয়ে আমরা কোনো value-এর data type পরীক্ষা করতে পারি।

**মনে রাখবে:** `input()` থেকে পাওয়া value integer বা float হিসেবে ব্যবহার করতে চাইলে প্রয়োজন অনুযায়ী type conversion করতে হবে।

## 2. What Is a String?

String হলো এক বা একাধিক character-এর সমষ্টি, যা text হিসেবে ব্যবহৃত হয়।

Python-এ string সাধারণত single quotation mark (`' '`) অথবা double quotation mark (`" "`) দিয়ে লেখা হয়।

### Example

```python
name = "Masum"
city = "Dhaka"
message = "Hello Python"
```

এখানে `name`, `city` এবং `message`-এর value-গুলো string।

String-এর মধ্যে letter, digit, space এবং special character থাকতে পারে।

```python
text1 = "Hello"
text2 = "123"
text3 = "Python 3.14"
```

এখানে তিনটি value-ই string, কারণ এগুলো quotation mark-এর মধ্যে লেখা হয়েছে।

তবে `input()` থেকে পাওয়া value-কে Python স্বয়ংক্রিয়ভাবে string হিসেবে return করে; user quotation mark লিখেছে কি না, তার ওপর এটি নির্ভর করে না।

## 3. Why Does `input()` Return a String?

`input()` function user-এর keyboard input গ্রহণ করে text হিসেবে return করে। এটি নিজে থেকে নির্ধারণ করে না যে user-এর লেখা text integer, float, নাকি অন্য কোনো data type হিসেবে ব্যবহার করা হবে।

### Example

```python
number = input("Enter a number: ")

print(number)
print(type(number))
```

Sample Interaction:

```text
Enter a number: 100
100
<class 'str'>
```

এখানে `100` string হিসেবে সংরক্ষিত হয়েছে।

### Another Example

```python
price = input("Enter the price: ")

print(price)
print(type(price))
```

Sample Interaction:

```text
Enter the price: 99.50
99.50
<class 'str'>
```

এখানে `99.50`-ও string, float নয়।

### মূল কারণ

- `input()` user-এর লেখা গ্রহণ করে।
- User-এর লেখা text হিসেবে return হয়।
- Python নিজে থেকে numeric conversion করে না।
- প্রয়োজন অনুযায়ী programmer-কে type conversion করতে হয়।

## 4. Difference Between Numeric Strings and Numbers

দেখতে একই রকম হলেও string এবং number এক জিনিস নয়।

### Example 1: Integer vs String

```python
a = 10
b = "10"

print(type(a))
print(type(b))
```

Output:

```text
<class 'int'>
<class 'str'>
```

এখানে:

- `10` একটি integer।
- `"10"` একটি string।

### Example 2: Float vs String

```python
a = 10.5
b = "10.5"

print(type(a))
print(type(b))
```

Output:

```text
<class 'float'>
<class 'str'>
```

এখানে `10.5` একটি float, কিন্তু `"10.5"` একটি string।

### Comparison Table

| Value | Data type | অর্থ |
|---|---|---|
| `25` | `int` | Integer number |
| `"25"` | `str` | Text হিসেবে 25 |
| `25.5` | `float` | Decimal number |
| `"25.5"` | `str` | Text হিসেবে 25.5 |
| `"Hello"` | `str` | সাধারণ text |

**মনে রাখবে:** কোনো value-এর মধ্যে digit থাকলেই সেটি number হয় না। তার data type-ও দেখতে হবে।

## 5. Understanding `type()` with User Input

`type()` function দিয়ে কোনো value-এর data type পরীক্ষা করা যায়।

### Example

```python
name = input("Enter your name: ")
age = input("Enter your age: ")
marks = input("Enter your marks: ")

print(type(name))
print(type(age))
print(type(marks))
```

Sample Interaction:

```text
Enter your name: Masum
Enter your age: 22
Enter your marks: 85.5
<class 'str'>
<class 'str'>
<class 'str'>
```

এখানে তিনটি input-ই string।

- `name`-এ text দেওয়া হয়েছে।
- `age`-এ integer-এর মতো দেখতে text দেওয়া হয়েছে।
- `marks`-এ decimal number-এর মতো দেখতে text দেওয়া হয়েছে।

তবুও সবগুলো `str`।

## 6. What Happens When We Add Two Inputs?

এটি এই topic-এর সবচেয়ে গুরুত্বপূর্ণ অংশগুলোর একটি।

ধরা যাক, আমরা user-এর কাছ থেকে দুটি সংখ্যা নিলাম এবং তাদের যোগ করলাম।

### Example: Addition Without Type Conversion

```python
a = input("Enter the first number: ")
b = input("Enter the second number: ")

result = a + b

print("Result:", result)
```

Sample Interaction:

```text
Enter the first number: 10
Enter the second number: 20
Result: 1020
```

অনেকে এখানে `30` আশা করে। কিন্তু output এসেছে `1020`।

### কেন এমন হলো?

কারণ `a` এবং `b` integer নয়, string।

Python-এ দুটি string-এর মধ্যে `+` operator ব্যবহার করলে string concatenation হয়। অর্থাৎ, দুটি string পাশাপাশি যুক্ত হয়।

```python
a = "10"
b = "20"

print(a + b)
```

Output:

```text
1020
```

এখানে `"10"` এবং `"20"` যুক্ত হয়ে `"1020"` হয়েছে।

### সঠিকভাবে যোগ করার উপায়

```python
a = int(input("Enter the first number: "))
b = int(input("Enter the second number: "))

result = a + b

print("Result:", result)
```

Sample Interaction:

```text
Enter the first number: 10
Enter the second number: 20
Result: 30
```

এখানে `int()` ব্যবহার করে input-কে integer-এ convert করা হয়েছে।

`int()` এবং অন্যান্য type conversion পদ্ধতি পরবর্তী topic-এ বিস্তারিত শিখব।

## 7. String Concatenation vs Numeric Addition

একই `+` operator data type অনুযায়ী ভিন্ন কাজ করতে পারে।

### Example 1: String Concatenation

```python
a = "5"
b = "3"

print(a + b)
```

Output:

```text
53
```

এখানে string দুটি যুক্ত হয়েছে।

### Example 2: Numeric Addition

```python
a = 5
b = 3

print(a + b)
```

Output:

```text
8
```

এখানে integer দুটি যোগ হয়েছে।

### Example 3: Mixing String and Integer

```python
a = "5"
b = 3

print(a + b)
```

Output:

```text
TypeError
```

আরও নির্দিষ্টভাবে, Python সাধারণত `TypeError: can only concatenate str (not "int") to str`-এর মতো error দেখাবে।

কারণ Python string-এর সঙ্গে integer-কে সরাসরি `+` দিয়ে concatenate করতে দেয় না।

### Summary

| Expression | Result | কারণ |
|---|---|---|
| `"5" + "3"` | `"53"` | String concatenation |
| `5 + 3` | `8` | Numeric addition |
| `"5" + 3` | `TypeError` | Incompatible types for `+` |

## 8. Converting User Input into an Integer

যখন user-এর কাছ থেকে পূর্ণসংখ্যা নিতে হয়, তখন `int()` ব্যবহার করা যায়।

### Example

```python
age = int(input("Enter your age: "))

print(age)
print(type(age))
```

Sample Interaction:

```text
Enter your age: 22
22
<class 'int'>
```

এখানে কাজের ধাপগুলো হলো:

1. `input()` user-এর লেখা গ্রহণ করে।
2. `input()` string return করে।
3. `int()` সেই string-কে integer-এ convert করে।
4. Converted value `age` variable-এ সংরক্ষিত হয়।

### Another Example: Student Marks

```python
marks = int(input("Enter your marks: "))

print("Your marks are:", marks)
```

Sample Interaction:

```text
Enter your marks: 85
Your marks are: 85
```

এখানে user-এর input integer হিসেবে ব্যবহার করা হয়েছে।

**সতর্কতা:** User যদি `abc` বা `85.5` লেখে, তাহলে সরাসরি `int()` ব্যবহার করলে `ValueError` হতে পারে। Valid input নিশ্চিত করার বিষয়টি পরবর্তী topic-এ আলোচনা করা হবে।

## 9. Converting User Input into a Float

Decimal number গ্রহণ করতে `float()` ব্যবহার করা হয়।

### Example

```python
price = float(input("Enter the price: "))

print(price)
print(type(price))
```

Sample Interaction:

```text
Enter the price: 99.50
99.5
<class 'float'>
```

এখানে input-কে float-এ convert করা হয়েছে।

Python সংখ্যাটি `99.5` হিসেবে দেখিয়েছে। কারণ numeric value হিসেবে `99.50` এবং `99.5` সমান।

### Another Example: Average Marks

```python
marks1 = float(input("Enter first marks: "))
marks2 = float(input("Enter second marks: "))

average = (marks1 + marks2) / 2

print("Average:", average)
```

Sample Interaction:

```text
Enter first marks: 80
Enter second marks: 90
Average: 85.0
```

এখানে input-গুলো float-এ convert করা হয়েছে, তাই arithmetic addition সঠিকভাবে হয়েছে।

## 10. Why Type Conversion Is Necessary

Type conversion হলো একটি value-কে অন্য data type-এ পরিবর্তন করা।

User input নিয়ে calculation করতে চাইলে অনেক সময় type conversion প্রয়োজন হয়।

### Example: Incorrect Calculation

```python
length = input("Enter length: ")
width = input("Enter width: ")

area = length * width

print("Area:", area)
```

এখানে `length` এবং `width` string। তাই string-এর সঙ্গে string-এর multiplication করার এই expression-এ `TypeError` হবে।

### Correct Program

```python
length = float(input("Enter length: "))
width = float(input("Enter width: "))

area = length * width

print("Area:", area)
```

Sample Interaction:

```text
Enter length: 5
Enter width: 3
Area: 15.0
```

এখানে দুটি input float-এ convert হয়েছে। ফলে গুণের কাজ সঠিকভাবে সম্পন্ন হয়েছে।

### কখন কোনটি ব্যবহার করবে?

- পূর্ণসংখ্যার জন্য: `int()`
- Decimal number-এর জন্য: `float()`
- Text হিসেবে রাখতে চাইলে: `input()`-এর return value সরাসরি ব্যবহার করা যায়।

## 11. When Should Input Remain a String?

সব input-কে number-এ convert করার প্রয়োজন নেই। অনেক তথ্য text হিসেবেই রাখা উচিত।

### Example 1: Name

```python
name = input("Enter your name: ")
```

এখানে নাম string হওয়াই স্বাভাবিক।

### Example 2: Student ID

```python
student_id = input("Enter your student ID: ")
```

Student ID-তে শুরুতে zero থাকতে পারে। যেমন `00125`। Integer-এ convert করলে শুরুতে থাকা zero হারিয়ে যেতে পারে।

```python
student_id = input("Enter your student ID: ")

print(student_id)
print(type(student_id))
```

Sample Interaction:

```text
Enter your student ID: 00125
00125
<class 'str'>
```

এখানে ID string হিসেবে রাখা হয়েছে, তাই শুরুতে থাকা zero অক্ষুণ্ণ রয়েছে।

### Example 3: Phone Number

```python
phone = input("Enter your phone number: ")
```

Phone number সাধারণত arithmetic করার জন্য নয়। তাই এটিকে string হিসেবে রাখাই উপযুক্ত।

### মূল নিয়ম

**যে input দিয়ে calculation করতে হবে, প্রয়োজন অনুযায়ী সেটিকে numeric type-এ convert করো। আর পরিচয় বা text হিসেবে ব্যবহৃত তথ্য string হিসেবেই রাখো।**

## 12. Common Mistakes

### Mistake 1: `input()`-এর Return Type ভুলে যাওয়া

```python
age = input("Enter your age: ")

print(type(age))
```

User `22` লিখলেও output:

```text
<class 'str'>
```

প্রয়োজন হলে:

```python
age = int(input("Enter your age: "))
```

### Mistake 2: String-এর মধ্যে Numeric Addition আশা করা

```python
a = input("First number: ")
b = input("Second number: ")

print(a + b)
```

Input:

```text
10
20
```

Output:

```text
1020
```

কারণ এখানে string concatenation হয়েছে।

### Mistake 3: Decimal Input-কে `int()` দিয়ে Convert করা

```python
number = int(input("Enter a number: "))
```

User `12.5` লিখলে `ValueError` হবে। কারণ `"12.5"` সরাসরি integer-এ convert করা যায় না।

Decimal input-এর জন্য:

```python
number = float(input("Enter a number: "))
```

### Mistake 4: String ও Number সরাসরি যোগ করা

```python
age = input("Enter age: ")

print(age + 5)
```

এখানে `TypeError` হবে, কারণ `age` string এবং `5` integer।

সঠিকভাবে:

```python
age = int(input("Enter age: "))

print(age + 5)
```

### Mistake 5: সব input-কে `int()` দিয়ে Convert করা

```python
name = int(input("Enter your name: "))
```

User `Masum` লিখলে `ValueError` হবে।

কারণ `"Masum"` integer নয়।

সঠিক code:

```python
name = input("Enter your name: ")
```

## 13. Practical Programs

### Program 1: Add Two Numbers

```python
a = int(input("Enter the first number: "))
b = int(input("Enter the second number: "))

total = a + b

print("Total:", total)
```

Sample Interaction:

```text
Enter the first number: 15
Enter the second number: 25
Total: 40
```

### Program 2: Calculate Age After Five Years

```python
age = int(input("Enter your current age: "))

future_age = age + 5

print("Your age after five years:", future_age)
```

Sample Interaction:

```text
Enter your current age: 22
Your age after five years: 27
```

### Program 3: Calculate Rectangle Area

```python
length = float(input("Enter length: "))
width = float(input("Enter width: "))

area = length * width

print("Rectangle Area:", area)
```

Sample Interaction:

```text
Enter length: 10
Enter width: 5
Rectangle Area: 50.0
```

### Program 4: Store Student Information

```python
name = input("Enter your name: ")
student_id = input("Enter your student ID: ")
marks = float(input("Enter your marks: "))

print("\n--- Student Information ---")
print("Name:", name)
print("Student ID:", student_id)
print("Marks:", marks)
```

Sample Interaction:

```text
Enter your name: Masum
Enter your student ID: 00125
Enter your marks: 85.5

--- Student Information ---
Name: Masum
Student ID: 00125
Marks: 85.5
```

এখানে name এবং student ID string হিসেবে রাখা হয়েছে, আর marks float হিসেবে নেওয়া হয়েছে।

## 14. Practice Exercises

প্রথমে নিজে সমাধান করো। প্রয়োজন হলে `type()` ব্যবহার করে value-এর data type পরীক্ষা করো।

### Exercise 1: Identify the Type

```python
number = input("Enter a number: ")
print(type(number))
```

User `50` লিখলে কোন data type দেখা যাবে?

### Exercise 2: Predict the Output

```python
a = input("First: ")
b = input("Second: ")

print(a + b)
```

User প্রথমে `12` এবং পরে `8` লিখলে output কী হবে?

### Exercise 3: Fix the Addition

নিচের program-টি এমনভাবে ঠিক করো, যেন `10` এবং `20` input দিলে ফল `30` আসে।

```python
a = input("First number: ")
b = input("Second number: ")

print(a + b)
```

### Exercise 4: Convert to Float

User-এর কাছ থেকে একটি decimal number নাও এবং তার type দেখাও।

### Exercise 5: Identify the Error

```python
price = int(input("Enter price: "))
```

User `25.75` লিখলে কী হবে? কেন?

### Exercise 6: Student ID

User-এর কাছ থেকে `00125` student ID নাও এবং সেটি একইভাবে print করো। শুরুতে থাকা zero যেন না হারায়।

### Exercise 7: Calculate Total Marks

User-এর কাছ থেকে তিনটি পূর্ণসংখ্যার marks নাও এবং total হিসাব করো।

### Exercise 8: Calculate Average

User-এর কাছ থেকে দুটি decimal number নাও এবং তাদের average বের করো।

### Exercise 9: Predict the Output

```python
a = "20"
b = "30"

print(a + b)
print(type(a))
```

Output কী হবে?

### Exercise 10: Challenge Program

User-এর নাম, student ID এবং তিনটি subject-এর marks নাও। এরপর নাম ও ID দেখাও, এবং তিনটি marks-এর total ও average হিসাব করে print করো।

## 15. Practice Answer Key

### Answer 1

```text
<class 'str'>
```

কারণ `input()` string return করে।

### Answer 2

```text
128
```

দুটি input string হিসেবে যুক্ত হয়েছে।

### Answer 3

```python
a = int(input("First number: "))
b = int(input("Second number: "))

print(a + b)
```

Input `10` এবং `20` হলে output হবে `30`।

### Answer 4

```python
number = float(input("Enter a decimal number: "))

print(number)
print(type(number))
```

### Answer 5

`ValueError` হবে, কারণ `"25.75"` সরাসরি `int()` দিয়ে convert করা যায় না।

সঠিক code:

```python
price = float(input("Enter price: "))
```

### Answer 6

```python
student_id = input("Enter student ID: ")

print(student_id)
```

Input `00125` হলে output হবে `00125`।

### Answer 7

```python
a = int(input("Enter first marks: "))
b = int(input("Enter second marks: "))
c = int(input("Enter third marks: "))

total = a + b + c

print("Total Marks:", total)
```

### Answer 8

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

average = (a + b) / 2

print("Average:", average)
```

### Answer 9

```text
2030
<class 'str'>
```

প্রথম output string concatenation-এর ফল।

### Answer 10

```python
name = input("Enter your name: ")
student_id = input("Enter your student ID: ")

marks1 = float(input("Enter first subject marks: "))
marks2 = float(input("Enter second subject marks: "))
marks3 = float(input("Enter third subject marks: "))

total = marks1 + marks2 + marks3
average = total / 3

print("\n--- Student Report ---")
print("Name:", name)
print("Student ID:", student_id)
print("Total Marks:", total)
print("Average Marks:", average)
```

এখানে text-ভিত্তিক তথ্য string হিসেবে রাখা হয়েছে এবং marks calculation-এর জন্য numeric type ব্যবহার করা হয়েছে।

## 16. Chapter Summary

এই topic-এ আমরা শিখেছি:

1. `input()` user-এর দেওয়া value string হিসেবে return করে।
2. `"25"` একটি string, কিন্তু `25` একটি integer।
3. `"10" + "20"` ফল `"1020"` দেয়, কারণ এখানে string concatenation হয়।
4. `10 + 20` ফল `30` দেয়, কারণ এখানে numeric addition হয়।
5. `int()` দিয়ে উপযুক্ত input integer-এ convert করা যায়।
6. `float()` দিয়ে উপযুক্ত input float-এ convert করা যায়।
7. String ও numeric value সরাসরি `+` দিয়ে যোগ করলে `TypeError` হতে পারে।
8. Decimal text-কে সরাসরি `int()` দিয়ে convert করলে `ValueError` হতে পারে।
9. Student ID ও phone number-এর মতো তথ্য সাধারণত string হিসেবে রাখা ভালো।
10. সঠিক data type নির্বাচন করলে calculation ও data handling সহজ হয়।

## 17. Self-Assessment Checklist

- [ ] বুঝি কেন `input()` string return করে।
- [ ] String ও number-এর পার্থক্য বুঝি।
- [ ] `type()` দিয়ে data type পরীক্ষা করতে পারি।
- [ ] String concatenation এবং numeric addition আলাদা করতে পারি।
- [ ] প্রয়োজন অনুযায়ী `int()` ও `float()` ব্যবহার করতে পারি।
- [ ] `TypeError` ও `ValueError`-এর সাধারণ কারণ বুঝি।
- [ ] Student ID-এর মতো তথ্য string হিসেবে রাখতে পারি।
- [ ] User input নিয়ে সাধারণ arithmetic program তৈরি করতে পারি।

**Next Topic:** `11_Type_Conversion_in_User_Input.md` — এখানে আমরা user input-এর data type পরিবর্তন, type conversion কেন প্রয়োজন এবং input-কে সঠিক data type-এ রূপান্তরের মৌলিক নিয়মগুলো আরও গুছিয়ে শিখব।