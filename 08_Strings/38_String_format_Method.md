
# 38. String format() Method in Python

## 1. Introduction to format() Method

Python-এর `format()` method ব্যবহার করে String-এর মধ্যে বিভিন্ন Value বসিয়ে সুন্দরভাবে Output তৈরি করা যায়।

এটি String Formatting-এর একটি গুরুত্বপূর্ণ পদ্ধতি।

`format()` method ব্যবহার করে আমরা:

- String-এর মধ্যে Variable-এর Value বসাতে পারি।
- একাধিক Value একটি String-এর মধ্যে ব্যবহার করতে পারি।
- Positional Arguments ব্যবহার করতে পারি।
- Keyword Arguments ব্যবহার করতে পারি।
- একই Value একাধিকবার ব্যবহার করতে পারি।
- Number Formatting করতে পারি।
- String-এর Alignment এবং Padding নির্ধারণ করতে পারি।

### Example

```python
name = "Masum"

message = "Hello, {}".format(name)

print(message)
```

**Output:**

```text
Hello, Masum
```

এখানে:

- `{}` হলো Placeholder।
- `format(name)` এর মাধ্যমে `name` Variable-এর Value Placeholder-এ বসানো হয়েছে।
- Final Output একটি String তৈরি করেছে।

**মনে রাখবে:** `format()` method একটি নতুন Formatted String Return করে।

---

## 2. Basic Syntax of format() Method

### Syntax

```python
"string {}".format(value)
```

এখানে:

- `string` হলো মূল Text।
- `{}` হলো Placeholder।
- `format()` এর ভিতরের Value Placeholder-এ বসে।

### Example

```python
name = "Rahim"
age = 22

message = "My name is {} and I am {} years old.".format(name, age)

print(message)
```

**Output:**

```text
My name is Rahim and I am 22 years old.
```

এখানে প্রথম `{}`-তে `name` এবং দ্বিতীয় `{}`-তে `age`-এর Value বসেছে।

---

## 3. Using Multiple Placeholders

একটি String-এর মধ্যে একাধিক Placeholder ব্যবহার করা যায়।

`format()` method-এর মধ্যে একাধিক Value দিলে সেগুলো Placeholder-এ ক্রমানুসারে বসে।

### Example

```python
name = "Masum"
age = 23
city = "Dhaka"

message = "My name is {}, I am {} years old and I live in {}.".format(name, age, city)

print(message)
```

**Output:**

```text
My name is Masum, I am 23 years old and I live in Dhaka.
```

এখানে:

- প্রথম `{}` → `Masum`
- দ্বিতীয় `{}` → `23`
- তৃতীয় `{}` → `Dhaka`

**মনে রাখবে:** Placeholder এবং Value-এর সংখ্যা সমান থাকলে Code সহজে বোঝা যায়।

---

## 4. Positional Arguments in format()

`format()` method-এ Value-এর Position বা Index ব্যবহার করে Placeholder-এ Value বসানো যায়।

একে Positional Formatting বলা হয়।

Python-এ Position Index `0` থেকে শুরু হয়।

### Syntax

```python
"{0} {1} {2}".format(value1, value2, value3)
```

### Example

```python
name = "Masum"
age = 23
city = "Dhaka"

message = "Name: {0}, Age: {1}, City: {2}".format(name, age, city)

print(message)
```

**Output:**

```text
Name: Masum, Age: 23, City: Dhaka
```

এখানে:

- `{0}` → প্রথম Value।
- `{1}` → দ্বিতীয় Value।
- `{2}` → তৃতীয় Value।

### Example 2: Changing the Order

Position Index ব্যবহার করে Value-এর Order পরিবর্তন করা যায়।

```python
name = "Masum"
age = 23

print("Age: {1}, Name: {0}".format(name, age))
```

**Output:**

```text
Age: 23, Name: Masum
```

এখানে `{1}` দ্বিতীয় Value এবং `{0}` প্রথম Value নির্দেশ করছে।

### Example 3: Reusing the Same Value

একই Position একাধিকবার ব্যবহার করা যায়।

```python
name = "Masum"

message = "{0} is learning Python. {0} loves programming.".format(name)

print(message)
```

**Output:**

```text
Masum is learning Python. Masum loves programming.
```

এখানে `{0}` দুইবার ব্যবহার করা হয়েছে।

---

## 5. Automatic Positional Formatting

Placeholder-এর মধ্যে Index না লিখলেও Python স্বয়ংক্রিয়ভাবে Value-এর Position নির্ধারণ করতে পারে।

### Example

```python
name = "Masum"
age = 23
city = "Dhaka"

message = "Name: {}, Age: {}, City: {}".format(name, age, city)

print(message)
```

**Output:**

```text
Name: Masum, Age: 23, City: Dhaka
```

এখানে Python স্বয়ংক্রিয়ভাবে:

- প্রথম `{}` → Index 0
- দ্বিতীয় `{}` → Index 1
- তৃতীয় `{}` → Index 2

ব্যবহার করেছে।

**Important:** Automatic Numbering এবং Manual Numbering একই Format String-এ মিশিয়ে ব্যবহার করা যায় না।

### Wrong Example

```python
name = "Masum"
age = 23

print("Name: {}, Age: {1}".format(name, age))
```

**Output:**

```text
ValueError: cannot switch from automatic field numbering to manual field specification
```

**মনে রাখবে:** একটি Format String-এ হয় Automatic Numbering, নয়তো Manual Numbering ব্যবহার করবে।

---

## 6. Keyword Arguments in format()

`format()` method-এ Value-এর Position-এর পরিবর্তে নাম ব্যবহার করেও Placeholder পূরণ করা যায়।

একে Keyword Argument Formatting বলা হয়।

### Syntax

```python
"{name} {age}".format(name=value1, age=value2)
```

### Example

```python
message = "My name is {name} and I am {age} years old.".format(
    name="Masum",
    age=23
)

print(message)
```

**Output:**

```text
My name is Masum and I am 23 years old.
```

এখানে:

- `{name}` → `name="Masum"`
- `{age}` → `age=23`

### Example 2: Changing the Argument Order

Keyword Arguments ব্যবহার করলে Value-এর Order পরিবর্তন হলেও সমস্যা হয় না।

```python
message = "Name: {name}, Age: {age}".format(
    age=23,
    name="Masum"
)

print(message)
```

**Output:**

```text
Name: Masum, Age: 23
```

এখানে Argument-এর Order পরিবর্তন হলেও Placeholder-এর নাম অনুযায়ী Value বসেছে।

---

## 7. Mixing Positional and Keyword Arguments

একই `format()` method-এ Positional এবং Keyword Arguments একসঙ্গে ব্যবহার করা যায়।

তবে Positional Arguments আগে দিতে হয় এবং Keyword Arguments পরে দিতে হয়।

### Example

```python
message = "Name: {}, Age: {age}".format(
    "Masum",
    age=23
)

print(message)
```

**Output:**

```text
Name: Masum, Age: 23
```

এখানে:

- `{}` → Positional Argument।
- `{age}` → Keyword Argument।

**Important Rule:** Positional Argument-এর পরে Keyword Argument দিতে হয়।

---

## 8. Formatting Numbers with format()

`format()` method ব্যবহার করে Number-কে নির্দিষ্ট Decimal Places-এ Display করা যায়।

### Example 1: Two Decimal Places

```python
price = 125.5678

print("Price: {:.2f}".format(price))
```

**Output:**

```text
Price: 125.57
```

এখানে:

- `:` Formatting শুরু করে।
- `.2f` Decimal-এর পরে দুইটি Digit দেখায়।

### Example 2: Three Decimal Places

```python
number = 12.345678

print("{:.3f}".format(number))
```

**Output:**

```text
12.346
```

### Example 3: No Decimal Places

```python
number = 45.89

print("{:.0f}".format(number))
```

**Output:**

```text
46
```

এখানে Decimal-এর পরে কোনো Digit দেখানো হয়নি।

**মনে রাখবে:** Number Formatting করার সময় প্রয়োজন অনুযায়ী Rounding করা হয়।

---

## 9. Thousands Separator with format()

বড় Number সহজে পড়ার জন্য Comma ব্যবহার করা যায়।

### Example 1: Integer

```python
number = 1000000

print("{:,}".format(number))
```

**Output:**

```text
1,000,000
```

### Example 2: Float

```python
number = 1234567.89

print("{:,.2f}".format(number))
```

**Output:**

```text
1,234,567.89
```

এখানে:

- `,` → Thousands Separator যোগ করে।
- `.2f` → Decimal-এর পরে দুইটি Digit দেখায়।

---

## 10. Formatting Percentage with format()

Decimal Value-কে Percentage হিসেবে Display করতে `%` ব্যবহার করা যায়।

### Example 1

```python
result = 0.85

print("Result: {:.2%}".format(result))
```

**Output:**

```text
Result: 85.00%
```

### Example 2

```python
marks = 0.7568

print("Percentage: {:.1%}".format(marks))
```

**Output:**

```text
Percentage: 75.7%
```

**Important:** Percentage Formatting নিজেই Number-কে `100` দিয়ে গুণ করে `%` যোগ করে।

---

## 11. String Alignment with format()

`format()` method ব্যবহার করে String বা Number-কে নির্দিষ্ট Width-এর মধ্যে সাজানো যায়।

তিন ধরনের Alignment ব্যবহার করা হয়:

- `<` → Left Alignment
- `>` → Right Alignment
- `^` → Center Alignment

### Example 1: Left Alignment

```python
name = "Python"

print("{:<15}".format(name))
```

**Output:**

```text
Python
```

এখানে Text বাম পাশে থাকে এবং ডান পাশে Space যোগ হয়।

### Example 2: Right Alignment

```python
name = "Python"

print("{:>15}".format(name))
```

**Output:**

```text
         Python
```

এখানে Text ডান পাশে থাকে এবং বাম পাশে Space যোগ হয়।

### Example 3: Center Alignment

```python
name = "Python"

print("{:^15}".format(name))
```

**Output:**

```text
    Python
```

এখানে Text মাঝখানে থাকে।

### Alignment Summary

| Symbol | কাজ |
|---|---|
| `<` | Left Alignment |
| `>` | Right Alignment |
| `^` | Center Alignment |

---

## 12. Custom Fill Characters

Alignment-এর পাশাপাশি Padding Character-ও নির্ধারণ করা যায়।

### Example 1: Using *

```python
name = "Python"

print("{:*<12}".format(name))
print("{:*>12}".format(name))
print("{:*^12}".format(name))
```

**Output:**

```text
Python******
******Python
***Python***
```

এখানে:

- `*<12` → ডান পাশে `*` যোগ করে।
- `*>12` → বাম পাশে `*` যোগ করে।
- `*^12` → দুই পাশে `*` যোগ করে Center Alignment করে।

### Example 2: Using Zero

```python
number = 42

print("{:0>5}".format(number))
```

**Output:**

```text
00042
```

এখানে Number-এর বাম পাশে Zero যোগ করে মোট Width 5 করা হয়েছে।

---

## 13. Formatting Positive and Negative Signs

Number-এর আগে Positive অথবা Negative Sign দেখানোর জন্য `+` এবং `-` ব্যবহার করা যায়।

### Example 1: Always Show Sign

```python
a = 25
b = -25

print("{:+}".format(a))
print("{:+}".format(b))
```

**Output:**

```text
+25
-25
```

এখানে `+` ব্যবহার করায় Positive এবং Negative উভয় Number-এর Sign দেখানো হয়েছে।

### Example 2: Show Negative Sign Only

```python
a = 25
b = -25

print("{:-}".format(a))
print("{:-}".format(b))
```

**Output:**

```text
25
-25
```

এখানে Positive Number-এর আগে কোনো Sign দেখানো হয়নি।

---

## 14. Formatting Scientific Notation

বড় বা ছোট Number-কে Scientific Notation-এ Display করতে `e` ব্যবহার করা যায়।

### Example 1

```python
number = 1234567

print("{:e}".format(number))
```

**Output:**

```text
1.234567e+06
```

### Example 2: Two Decimal Places

```python
number = 1234567

print("{:.2e}".format(number))
```

**Output:**

```text
1.23e+06
```

এখানে `.2e` Scientific Notation-এ Decimal-এর পরে দুইটি Digit দেখিয়েছে।

---

## 15. Accessing Dictionary Values in format()

Dictionary-এর Value-ও `format()` method ব্যবহার করে String-এর মধ্যে বসানো যায়।

এক্ষেত্রে Placeholder-এর মধ্যে Dictionary Key ব্যবহার করা যায়।

### Example

```python
student = {
    "name": "Masum",
    "age": 23,
    "department": "CSE"
}

message = "Name: {s[name]}, Age: {s[age]}, Department: {s[department]}".format(s=student)

print(message)
```

**Output:**

```text
Name: Masum, Age: 23, Department: CSE
```

এখানে:

- `{s[name]}` → Dictionary-এর `name` Value।
- `{s[age]}` → Dictionary-এর `age` Value।
- `{s[department]}` → Dictionary-এর `department` Value।

এখানে `s` হলো `format()` method-এ দেওয়া Keyword Argument।

---

## 16. Using format() with Lists

List-এর Element-ও Index ব্যবহার করে `format()` method-এর মধ্যে Access করা যায়।

### Example

```python
subjects = ["Python", "Java", "C++"]

message = "First: {0[0]}, Second: {0[1]}, Third: {0[2]}".format(subjects)

print(message)
```

**Output:**

```text
First: Python, Second: Java, Third: C++
```

এখানে:

- `{0[0]}` → প্রথম Element।
- `{0[1]}` → দ্বিতীয় Element।
- `{0[2]}` → তৃতীয় Element।

---

## 17. Using Curly Braces inside Strings

String-এর মধ্যে সরাসরি Curly Braces `{}` Display করতে চাইলে Double Curly Braces ব্যবহার করতে হয়।

### Example

```python
name = "Masum"

message = "Hello {{name}}. Welcome to Python!".format(name=name)

print(message)
```

**Output:**

```text
Hello {name}. Welcome to Python!
```

এখানে:

- `{{` → একটি `{` Display করে।
- `}}` → একটি `}` Display করে।

**মনে রাখবে:** `{{` এবং `}}` ব্যবহার করলে Curly Braces সাধারণ Text হিসেবে Display হয়।

---

## 18. Practical Example: Student Information

```python
name = "Masum"
department = "CSE"
semester = 9
cgpa = 3.95

print("Student Information")
print("---------------------------")
print("Name: {}".format(name))
print("Department: {}".format(department))
print("Semester: {}".format(semester))
print("CGPA: {:.2f}".format(cgpa))
```

**Output:**

```text
Student Information
---------------------------
Name: Masum
Department: CSE
Semester: 9
CGPA: 3.95
```

এখানে `format()` method ব্যবহার করে Student-এর Information Display করা হয়েছে।

---

## 19. Practical Example: Product Price List

```python
products = [
    ("Keyboard", 1250.567),
    ("Mouse", 750.5),
    ("Monitor", 12500.999)
]

print("{:<15} {:>12}".format("Product", "Price"))
print("-" * 27)

for name, price in products:
    print("{:<15} {:>12,.2f}".format(name, price))
```

**Output:**

```text
Product                Price
---------------------------
Keyboard            1,250.57
Mouse                 750.50
Monitor            12,501.00
```

এখানে:

- `{:<15}` → Product Name-কে Left Alignment করেছে।
- `{:>12,.2f}` → Price-কে Right Alignment করেছে।
- `,` → Thousands Separator যোগ করেছে।
- `.2f` → দুই Decimal Places দেখিয়েছে।

---

## 20. Practical Example: Simple Result Calculator

```python
name = "Masum"
total_marks = 450
full_marks = 500

percentage = (total_marks / full_marks) * 100

print("Student: {}".format(name))
print("Total Marks: {}".format(total_marks))
print("Full Marks: {}".format(full_marks))
print("Percentage: {:.2f}%".format(percentage))
```

**Output:**

```text
Student: Masum
Total Marks: 450
Full Marks: 500
Percentage: 90.00%
```

এখানে Student-এর Total Marks থেকে Percentage বের করে সুন্দরভাবে Display করা হয়েছে।

---

## 21. format() vs f-String

Python-এ `format()` method এবং f-String উভয়ই String Formatting-এর জন্য ব্যবহার করা হয়।

তবে এদের লেখার পদ্ধতিতে পার্থক্য রয়েছে।

### Example 1: Using format()

```python
name = "Masum"
age = 23

print("My name is {} and I am {} years old.".format(name, age))
```

**Output:**

```text
My name is Masum and I am 23 years old.
```

### Example 2: Using f-String

```python
name = "Masum"
age = 23

print(f"My name is {name} and I am {age} years old.")
```

**Output:**

```text
My name is Masum and I am 23 years old.
```

### Main Differences

| format() Method | f-String |
|---|---|
| `.format()` ব্যবহার করতে হয়। | String-এর আগে `f` দিতে হয়। |
| Placeholder-এর মধ্যে Index বা Name ব্যবহার করা যায়। | সরাসরি Variable Name ব্যবহার করা যায়। |
| Value আলাদাভাবে দিতে হয়। | Expression সরাসরি লেখা যায়। |
| তুলনামূলকভাবে বেশি Code লিখতে হয়। | সাধারণত কম Code লিখতে হয়। |

**মনে রাখবে:** Python 3.6 থেকে f-String পাওয়া যায়। আধুনিক Python Code-এ সাধারণত f-String বেশি ব্যবহার করা হয়। তবে `format()` method জানা গুরুত্বপূর্ণ, কারণ অনেক পুরোনো Code এবং Library-তে এটি দেখা যায়।

---

## 22. Important Format Specifiers

| Format Specifier | কাজ |
|---|---|
| `{}` | Automatic Placeholder |
| `{0}` | Positional Placeholder |
| `{name}` | Keyword Placeholder |
| `{:.2f}` | দুই Decimal Places |
| `{:.3f}` | তিন Decimal Places |
| `{:,.2f}` | Comma এবং দুই Decimal Places |
| `{:.2%}` | Percentage |
| `{:>10}` | Right Alignment |
| `{:<10}` | Left Alignment |
| `{:^10}` | Center Alignment |
| `{:0>5}` | Zero Padding |
| `{:+}` | Positive এবং Negative Sign |
| `{:e}` | Scientific Notation |

---

## 23. Important Rules to Remember

1. `format()` হলো Python-এর একটি String Method।
2. `{}` হলো Placeholder।
3. `format()` method-এর মাধ্যমে Placeholder-এ Value বসানো হয়।
4. Positional Index `0` থেকে শুরু হয়।
5. Positional Arguments ব্যবহার করে Value-এর Order পরিবর্তন করা যায়।
6. Keyword Arguments ব্যবহার করে নামের মাধ্যমে Value বসানো যায়।
7. Automatic এবং Manual Numbering একই Format String-এ মিশিয়ে ব্যবহার করা যায় না।
8. Positional Argument-এর পরে Keyword Argument দিতে হয়।
9. একই Placeholder একাধিকবার ব্যবহার করা যায়।
10. `.2f` Decimal-এর পরে দুইটি Digit দেখায়।
11. `,` Thousands Separator যোগ করে।
12. `%` Decimal Value-কে Percentage-এ রূপান্তর করে।
13. `<`, `>` এবং `^` Alignment নির্ধারণ করে।
14. `{{` এবং `}}` ব্যবহার করে Curly Braces Display করা যায়।
15. `format()` method একটি নতুন Formatted String Return করে।
16. `format()` method Original Variable-এর Value পরিবর্তন করে না।
17. Number Formatting-এর Output একটি String হয়।

---

## 24. Common Mistakes and Debugging

### Mistake 1: Missing Argument

```python
name = "Masum"
age = 23

print("Name: {}, Age: {}".format(name))
```

**Output:**

```text
IndexError: Replacement index 1 out of range for positional args tuple
```

**সমস্যা:** দুটি Placeholder থাকলেও একটি Value দেওয়া হয়েছে।

**Correct Code:**

```python
name = "Masum"
age = 23

print("Name: {}, Age: {}".format(name, age))
```

**Output:**

```text
Name: Masum, Age: 23
```

### Mistake 2: Using Wrong Position Index

```python
name = "Masum"

print("Name: {1}".format(name))
```

**Output:**

```text
IndexError: Replacement index 1 out of range for positional args tuple
```

**সমস্যা:** এখানে শুধু একটি Value আছে, যার Index হলো `0`।

**Correct Code:**

```python
name = "Masum"

print("Name: {0}".format(name))
```

**Output:**

```text
Name: Masum
```

### Mistake 3: Using an Undefined Keyword

```python
print("Name: {name}".format(age=23))
```

**Output:**

```text
KeyError: 'name'
```

**সমস্যা:** Placeholder-এ `name` চাওয়া হয়েছে, কিন্তু `format()`-এ `name` দেওয়া হয়নি।

**Correct Code:**

```python
print("Name: {name}".format(name="Masum"))
```

**Output:**

```text
Name: Masum
```

### Mistake 4: Mixing Automatic and Manual Numbering

```python
print("{} {}".format("Python", "Java"))
print("{0} {}".format("Python", "Java"))
```

**সমস্যা:** দ্বিতীয় String-এ Automatic এবং Manual Numbering একসঙ্গে ব্যবহার করা হয়েছে।

**Correct Code:**

```python
print("{} {}".format("Python", "Java"))
print("{0} {1}".format("Python", "Java"))
```

**Output:**

```text
Python Java
Python Java
```

### Mistake 5: Forgetting Percentage Conversion

```python
result = 0.85

print("{:.2f}".format(result))
print("{:.2%}".format(result))
```

**Output:**

```text
0.85
85.00%
```

**মনে রাখবে:** Percentage দেখানোর জন্য `%` ব্যবহার করতে হবে। শুধু `.2f` ব্যবহার করলে Percentage তৈরি হবে না।

---

## 25. Practice Exercises

### Exercise 1: Basic Formatting

নিচের Variable ব্যবহার করে একটি Sentence তৈরি করো।

```python
name = "Masum"
```

**Expected Output:**

```text
Hello, Masum!
```

### Exercise 2: Multiple Placeholders

দুটি Variable ব্যবহার করে Name এবং Age Display করো।

```python
name = "Rahim"
age = 22
```

**Expected Output:**

```text
My name is Rahim and I am 22 years old.
```

### Exercise 3: Positional Arguments

Position Index ব্যবহার করে নিচের Output তৈরি করো।

```python
a = "Python"
b = "Programming"
```

**Expected Output:**

```text
Programming with Python
```

### Exercise 4: Keyword Arguments

Keyword Arguments ব্যবহার করে নিচের Output তৈরি করো।

```python
name = "Masum"
department = "CSE"
```

**Expected Output:**

```text
Name: Masum, Department: CSE
```

### Exercise 5: Decimal Formatting

Number-টিকে দুই Decimal Places-এ Display করো।

```python
number = 45.6789
```

**Expected Output:**

```text
45.68
```

### Exercise 6: Thousands Separator

Number-এ Comma যোগ করো।

```python
number = 5000000
```

**Expected Output:**

```text
5,000,000
```

### Exercise 7: Percentage Formatting

নিচের Value-কে Percentage হিসেবে Display করো।

```python
result = 0.8567
```

**Expected Output:**

```text
85.67%
```

### Exercise 8: String Alignment

নিচের Text-কে 15 Width-এর মধ্যে Center Alignment করো।

```python
name = "Python"
```

**Expected Output:**

```text
    Python
```

### Exercise 9: Zero Padding

Number-টিকে পাঁচটি Character Width-এর মধ্যে Zero Padding দিয়ে Display করো।

```python
number = 25
```

**Expected Output:**

```text
00025
```

### Exercise 10: Predict the Output

নিচের Code-এর Output নিজে Predict করো।

```python
name = "Masum"
age = 23
marks = 87.567

print("Name: {0}".format(name))
print("Age: {}".format(age))
print("Marks: {:.2f}".format(marks))
print("{0} is {1} years old.".format(name, age))
```

**Expected Output:**

```text
Name: Masum
Age: 23
Marks: 87.57
Masum is 23 years old.
```

### Exercise 11: Predict the Output

```python
number = 12345.678

print("{:.1f}".format(number))
print("{:,.2f}".format(number))
print("{:.2%}".format(number))
print("{:*^15}".format("Python"))
```

**Expected Output:**

```text
12345.7
12,345.68
1234567.80%
****Python*****
```

### Exercise 12: Practical Programming

একটি Student Information Program তৈরি করো, যেখানে `format()` method ব্যবহার করে Student-এর Name, Department, Semester এবং CGPA Display করতে হবে।

**Expected Output:**

```text
Student Information
---------------------------
Name: Masum
Department: CSE
Semester: 9
CGPA: 3.95
```

---

## 26. Chapter Summary

এই Topic-এ আমরা Python-এর `format()` method ব্যবহার করে String Formatting শিখেছি।

| Topic | Description |
|---|---|
| Basic Formatting | `{}` দিয়ে Value বসানো |
| Positional Arguments | Index ব্যবহার করে Value বসানো |
| Keyword Arguments | Name ব্যবহার করে Value বসানো |
| Automatic Numbering | স্বয়ংক্রিয়ভাবে Index নির্ধারণ |
| Number Formatting | Decimal Places নির্ধারণ |
| Thousands Separator | Comma যোগ করা |
| Percentage | Percentage Display করা |
| Alignment | Left, Right এবং Center |
| Custom Padding | নিজের মতো Character যোগ করা |
| Dictionary Formatting | Dictionary থেকে Value নেওয়া |
| List Formatting | List থেকে Element নেওয়া |
| Curly Braces | `{}` সাধারণ Text হিসেবে Display করা |

**মনে রাখবে:**

```python
name = "Masum"
age = 23

message = "My name is {} and I am {} years old.".format(name, age)

print(message)
```

**Output:**

```text
My name is Masum and I am 23 years old.
```

`format()` method-এর মূল কাজ হলো Placeholder-এর জায়গায় নির্দিষ্ট Value বসিয়ে একটি Formatted String তৈরি করা।

---

## 27. Self-Assessment Checklist

- [ ] `format()` method কী বুঝতে পেরেছি।
- [ ] Basic Placeholder `{}` ব্যবহার করতে পারি।
- [ ] Multiple Values Format করতে পারি।
- [ ] Positional Arguments ব্যবহার করতে পারি।
- [ ] Keyword Arguments ব্যবহার করতে পারি।
- [ ] Automatic Numbering বুঝতে পেরেছি।
- [ ] Positional এবং Keyword Arguments একসঙ্গে ব্যবহার করতে পারি।
- [ ] Number Formatting করতে পারি।
- [ ] Decimal Places নির্ধারণ করতে পারি।
- [ ] Thousands Separator ব্যবহার করতে পারি।
- [ ] Percentage Formatting করতে পারি।
- [ ] String Alignment করতে পারি।
- [ ] Custom Padding ব্যবহার করতে পারি।
- [ ] Dictionary এবং List-এর Value Access করতে পারি।
- [ ] Curly Braces Display করতে পারি।
- [ ] Common Errors শনাক্ত ও সমাধান করতে পারি।
- [ ] Practical Programs লিখতে পারি।

---

## 28. Next Topic

পরবর্তী Topic:

**39. Old-Style String Formatting in Python**

পরবর্তী File:

`39_Old_Style_String_Formatting.md`

এখানে আমরা Python-এর পুরোনো String Formatting পদ্ধতি `%` Operator, `%s`, `%d`, `%f`, Width, Precision এবং অন্যান্য Format Specifier ব্যবহার করে শিখব।
