# 05. Print Function and Output

## 1. Introduction

Python-এ **`print()` function** ব্যবহার করে screen বা terminal-এ text, numbers, variables এবং expression-এর result দেখানো হয়।

Programming শেখার সময় output দেখা খুব গুরুত্বপূর্ণ। কারণ এর মাধ্যমে আমরা বুঝতে পারি program কী ফলাফল দিচ্ছে।

উদাহরণ:

```python
print("Hello, Python!")
```

Output:

```text
Hello, Python!
```

এখানে `print()` function-এর মাধ্যমে একটি message দেখানো হয়েছে।

## 2. Basic Syntax of `print()`

`print()` function-এর সাধারণ syntax:

```python
print(*objects, sep=' ', end='\n', file=None, flush=False)
```

এখানে:

| Parameter | কাজ |
|---|---|
| `objects` | যেসব value বা object print করতে চাই |
| `sep` | একাধিক object-এর মাঝখানে কী থাকবে |
| `end` | output-এর শেষে কী যোগ হবে |
| `file` | কোন output stream-এ লেখা হবে |
| `flush` | output buffer সঙ্গে সঙ্গে flush করা হবে কি না |

Beginner হিসেবে প্রথমে `objects`, `sep` এবং `end` ভালোভাবে শেখা গুরুত্বপূর্ণ। `file` ও `flush` পরে প্রয়োজন অনুযায়ী ব্যবহার করা যাবে।

## 3. Printing Text

Text output দেখাতে string ব্যবহার করা হয়।

উদাহরণ:

```python
print("Hello World")
print("I am learning Python")
print('Python is interesting')
```

Output:

```text
Hello World
I am learning Python
Python is interesting
```

String লেখার জন্য single quotation marks `' '` অথবা double quotation marks `" "` ব্যবহার করা যায়।

### Important Rules

- Opening quotation mark এবং closing quotation mark মিলতে হবে।
- String-এর ভেতরে থাকা text output-এ দেখানো হবে।
- Quotation marks নিজেরা সাধারণত output-এ দেখা যায় না।

উদাহরণ:

```python
print("Python")
```

Output:

```text
Python
```

## 4. Printing Numbers

`print()` দিয়ে integer এবং floating-point number দেখানো যায়।

```python
print(10)
print(25)
print(3.14)
print(-5)
```

Output:

```text
10
25
3.14
-5
```

এখানে সংখ্যাগুলো quotation marks-এর বাইরে লেখা হয়েছে। তাই এগুলো number literal।

### Number ও String-এর পার্থক্য

```python
print(100)
print("100")
```

Output:

```text
100
100
```

Output দেখতে একই হলেও:

- `100` একটি integer value।
- `"100"` একটি string value।

এই পার্থক্য calculation ও data processing-এর সময় গুরুত্বপূর্ণ।

## 5. Printing Variables

Variable-এর মধ্যে থাকা value দেখাতেও `print()` ব্যবহার করা যায়।

```python
name = "Masum"
age = 22

print(name)
print(age)
```

Output:

```text
Masum
22
```

এখানে `print(name)` লিখলে variable-এর নাম `name` দেখানো হয় না; বরং variable-এর মধ্যে থাকা value দেখানো হয়।

### Multiple Variables

```python
name = "Masum"
department = "CSE"
university = "Northern University Bangladesh"

print(name)
print(department)
print(university)
```

Output:

```text
Masum
CSE
Northern University Bangladesh
```

## 6. Printing Multiple Values

একটি `print()` function-এর মধ্যে comma দিয়ে একাধিক value দেওয়া যায়।

```python
name = "Masum"
age = 22

print(name, age)
```

Output:

```text
Masum 22
```

এখানে `print()` function দুটি value print করেছে এবং default separator হিসেবে একটি space ব্যবহার করেছে।

আরেকটি উদাহরণ:

```python
print("Python", "Java", "C++")
```

Output:

```text
Python Java C++
```

এভাবে একাধিক value একসঙ্গে দেখানো যায়।

## 7. Understanding the `sep` Parameter

`sep`-এর পূর্ণরূপ **separator**। এটি একাধিক object print করার সময় তাদের মাঝখানে কী থাকবে, তা নির্ধারণ করে।

Default separator হলো একটি space: `' '`।

### Example 1: Default Separator

```python
print("Python", "Java", "C++")
```

Output:

```text
Python Java C++
```

### Example 2: Using a Hyphen

```python
print("Python", "Java", "C++", sep="-")
```

Output:

```text
Python-Java-C++
```

### Example 3: Using a Comma

```python
print("Dhaka", "Bangladesh", sep=", ")
```

Output:

```text
Dhaka, Bangladesh
```

### Example 4: Using an Empty Separator

```python
print("Hello", "World", sep="")
```

Output:

```text
HelloWorld
```

এখানে object-গুলোর মাঝে কোনো separator নেই।

### Example 5: Using a Symbol

```python
print(10, 20, 30, sep=" | ")
```

Output:

```text
10 | 20 | 30
```

**মনে রাখবে:** `sep` শুধু একই `print()` call-এর একাধিক object-এর মাঝখানে separator নিয়ন্ত্রণ করে। এটি string-এর ভেতরের space পরিবর্তন করে না।

## 8. Understanding the `end` Parameter

`end` parameter নির্ধারণ করে `print()` function-এর output-এর শেষে কী যোগ হবে।

এর default value হলো newline character `'\n'`। অর্থাৎ, প্রতিটি `print()` call-এর পর সাধারণত পরবর্তী output নতুন লাইনে শুরু হয়।

### Example 1: Default `end`

```python
print("Hello")
print("World")
```

Output:

```text
Hello
World
```

### Example 2: Using an Empty `end`

```python
print("Hello", end="")
print("World")
```

Output:

```text
HelloWorld
```

প্রথম `print()`-এর শেষে newline যোগ হয়নি। তাই দ্বিতীয় message একই লাইনে এসেছে।

### Example 3: Using a Space

```python
print("Hello", end=" ")
print("World")
```

Output:

```text
Hello World
```

### Example 4: Using a Hyphen

```python
print("Python", end="-")
print("Programming")
```

Output:

```text
Python-Programming
```

### Example 5: Using a Newline Explicitly

```python
print("First", end="\n")
print("Second")
```

Output:

```text
First
Second
```

এখানে `end="\n"` ব্যবহার করা হয়েছে। এটি `print()`-এর default behavior-এর সমান।

**মনে রাখবে:** `sep` object-গুলোর মাঝখানে কাজ করে, আর `end` output-এর শেষে কাজ করে।

## 9. Difference Between `sep` and `end`

| বিষয় | `sep` | `end` |
|---|---|---|
| পূর্ণরূপ | Separator | Ending value |
| কাজ | Object-গুলোর মাঝখানে text বসায় | Output-এর শেষে text যোগ করে |
| Default value | `' '` | `'\n'` |
| ব্যবহার | `print(1, 2, sep="-")` | `print(1, end="!")` |

একটি উদাহরণে দুটোই দেখি:

```python
print("A", "B", "C", sep="-", end="!")
```

Output:

```text
A-B-C!
```

এখানে:

- `sep="-"` object-গুলোর মাঝে hyphen দিয়েছে।
- `end="!"` output-এর শেষে exclamation mark দিয়েছে।

আরেকটি উদাহরণ:

```python
print("A", "B", sep=":", end=" ")
print("C")
```

Output:

```text
A:B C
```

প্রথম call-এর output শেষে space রয়েছে, তাই দ্বিতীয় call-এর `C` একই লাইনে এসেছে।

## 10. Printing Mathematical Expressions

`print()`-এর মধ্যে mathematical expression লিখলে Python আগে expression evaluate করে, তারপর result দেখায়।

```python
print(10 + 5)
print(10 - 5)
print(10 * 5)
print(10 / 5)
```

Output:

```text
15
5
50
2.0
```

এখানে:

- `10 + 5` → Addition
- `10 - 5` → Subtraction
- `10 * 5` → Multiplication
- `10 / 5` → Division

### More Examples

```python
print(5 ** 2)
print(10 % 3)
print(10 // 3)
```

Output:

```text
25
1
3
```

এখানে:

- `**` exponentiation বা power হিসাব করে।
- `%` remainder বা ভাগশেষ বের করে।
- `//` floor division করে।

Operators নিয়ে বিস্তারিত আলোচনা হবে `15_Introduction_to_Operators.md` ফাইলে।

## 11. Printing Text and Variables Together

Text ও variable-এর value একসঙ্গে দেখানোর কয়েকটি পদ্ধতি রয়েছে।

### Method 1: Using Commas

```python
name = "Masum"
age = 22

print("Name:", name)
print("Age:", age)
```

Output:

```text
Name: Masum
Age: 22
```

এটি beginner-friendly একটি পদ্ধতি।

### Method 2: Using String Concatenation

String concatenation হলো একাধিক string একসঙ্গে যুক্ত করা।

```python
first_name = "Abdulla"
last_name = "Masum"

full_name = first_name + " " + last_name

print(full_name)
```

Output:

```text
Abdulla Masum
```

এখানে `+` দিয়ে string-গুলো যুক্ত করা হয়েছে।

**সতর্কতা:** সাধারণ string concatenation-এ number সরাসরি string-এর সঙ্গে যোগ করা যায় না।

```python
age = 22

# print("Age: " + age)  # TypeError হবে
print("Age: " + str(age))
```

Output:

```text
Age: 22
```

এখানে `str(age)` number-টিকে string-এ convert করেছে। Type conversion পরে বিস্তারিতভাবে শিখব।

### Method 3: Using an f-string

f-string দিয়ে string-এর মধ্যে variable বা expression-এর value সহজে দেখানো যায়।

```python
name = "Masum"
age = 22

print(f"My name is {name} and I am {age} years old.")
```

Output:

```text
My name is Masum and I am 22 years old.
```

এখানে:

- `f` string-টিকে formatted string হিসেবে চিহ্নিত করে।
- `{name}` variable-এর value বসায়।
- `{age}` variable-এর value বসায়।

f-string ব্যবহার করলে text ও variable একসঙ্গে দেখানো সহজ হয়।

### Using an Expression in an f-string

```python
a = 10
b = 20

print(f"Total: {a + b}")
```

Output:

```text
Total: 30
```

এখানে `{a + b}` expression evaluate করে result বসানো হয়েছে।

## 12. Printing Special Characters

কিছু special character output-এ নির্দিষ্ট কাজ করে। এদের মধ্যে newline ও tab গুরুত্বপূর্ণ।

### 12.1 Newline `\n`

`\n` string-এর মধ্যে নতুন line তৈরি করে।

```python
print("Hello\nWorld")
```

Output:

```text
Hello
World
```

### 12.2 Tab `\t`

`\t` tab-এর মতো spacing তৈরি করে।

```python
print("Name\tAge")
print("Masum\t22")
```

Output:

```text
Name    Age
Masum   22
```

ঠিক কতটা ফাঁকা জায়গা দেখা যাবে, তা terminal বা output viewer-এর ওপর নির্ভর করতে পারে।

### 12.3 Backslash `\\`

String-এর মধ্যে backslash character দেখাতে `\\` ব্যবহার করা যায়।

```python
print("C:\\Users\\Masum")
```

Output:

```text
C:\Users\Masum
```

এগুলোকে escape sequences বলা হয়। প্রয়োজন অনুযায়ী আরও escape sequences ব্যবহার করা যায়।

## 13. Printing an Empty Line

কোনো argument ছাড়া `print()` call করলে একটি blank line তৈরি হয়।

```python
print("First")
print()
print("Second")
```

Output:

```text
First

Second
```

এখানে দ্বিতীয় `print()` একটি ফাঁকা লাইন তৈরি করেছে।

Program-এর output-কে readable করতে এটি ব্যবহার করা যায়।

### Formatting Sections

```python
print("Student Information")
print("--------------------")
print("Name: Masum")
print("Department: CSE")
```

Output:

```text
Student Information
--------------------
Name: Masum
Department: CSE
```

এভাবে output-কে পরিষ্কারভাবে সাজানো যায়।

## 14. Printing Boolean Values

Python-এ Boolean value দুটি হলো `True` এবং `False`।

```python
print(True)
print(False)
```

Output:

```text
True
False
```

Boolean value সাধারণত condition ও logical operations-এর ফলাফল হিসেবে পাওয়া যায়।

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

এখানে comparison expression-এর result print করা হয়েছে।

## 15. The `file` and `flush` Parameters

`print()` function-এ `file` এবং `flush` নামে আরও দুটি parameter রয়েছে। এগুলো একটু advanced, তবে basic ধারণা জানা ভালো।

### 15.1 `file`

Defaultভাবে `print()` output standard output stream-এ পাঠায়, যা সাধারণত terminal বা console-এ দেখা যায়।

`file` parameter দিয়ে অন্য text stream-এ output পাঠানো যায়।

উদাহরণ:

```python
with open("output.txt", "w", encoding="utf-8") as file:
    print("Hello, Python!", file=file)
```

এই code চালালে `output.txt` file-এ লেখা হবে:

```text
Hello, Python!
```

এখানে `open()` file খুলেছে এবং `file=file` দিয়ে `print()`-কে সেই file stream-এ লিখতে বলা হয়েছে।

File handling নিয়ে বিস্তারিত আলোচনা হবে `13_File_Handling.md` ফাইলে।

### 15.2 `flush`

সাধারণত output buffer-এর মাধ্যমে output পরিচালিত হতে পারে। `flush=True` দিলে `print()` call-এর পর buffer flush করা হয়।

```python
print("Processing...", flush=True)
```

এটি বিশেষ করে কিছু interactive program বা দীর্ঘ সময় চলা process-এ উপকারী হতে পারে। সাধারণ beginner program-এ এটি প্রায়ই প্রয়োজন হয় না।

## 16. Common Mistakes

### Mistake 1: Quotation Marks ভুলে যাওয়া

ভুল:

```python
print(Hello)
```

সঠিক:

```python
print("Hello")
```

Quotation marks ছাড়া `Hello`-কে variable বা identifier হিসেবে বিবেচনা করা হবে।

### Mistake 2: String ও Number যুক্ত করার ভুল পদ্ধতি

ভুল:

```python
age = 22
print("Age: " + age)
```

সঠিক:

```python
age = 22
print("Age:", age)
```

অথবা:

```python
age = 22
print(f"Age: {age}")
```

### Mistake 3: `sep`-এর ভুল ধারণা

```python
print("Hello World", sep="-")
```

Output:

```text
Hello World
```

কেন? কারণ এখানে একটি মাত্র object দেওয়া হয়েছে। `sep` একাধিক object-এর মাঝখানে কাজ করে; একটি string-এর ভেতরের space পরিবর্তন করে না।

সঠিক ব্যবহার:

```python
print("Hello", "World", sep="-")
```

Output:

```text
Hello-World
```

### Mistake 4: `end`-এর কাজ ভুল বোঝা

```python
print("Hello", end=" ")
print("World")
```

Output:

```text
Hello World
```

`end=" "` ব্যবহার করার কারণে প্রথম output-এর পর newline-এর পরিবর্তে একটি space এসেছে।

### Mistake 5: Variable-এর নাম ভুল লেখা

```python
student_name = "Masum"
print(studentname)
```

এখানে `student_name` এবং `studentname` আলাদা identifier। তাই variable-টি সংজ্ঞায়িত না থাকলে `NameError` হবে।

সঠিক:

```python
student_name = "Masum"
print(student_name)
```

## 17. Practice Exercises

### Exercise 1: Basic Output

একটি program লেখো, যা নিচের message-গুলো আলাদা লাইনে print করবে:

- My name is Masum.
- I study CSE.
- I am learning Python.

### Exercise 2: Multiple Values

একটি `print()` call ব্যবহার করে তোমার নাম, department এবং university-এর নাম দেখাও।

### Exercise 3: Use `sep`

নিচের output তৈরি করো:

```text
2026-10-15
```

Hint: `print()`-এর `sep` parameter ব্যবহার করো।

### Exercise 4: Use `end`

দুটি `print()` call ব্যবহার করে নিচের output তৈরি করো:

```text
Python Programming
```

দুটি word-এর মাঝে একটি space থাকবে এবং output একই লাইনে থাকবে।

### Exercise 5: Mathematical Output

নিচের expression-গুলোর result আলাদা লাইনে print করো:

- `25 + 15`
- `25 - 15`
- `25 * 15`
- `25 / 15`

### Exercise 6: Use an f-string

`name` ও `age` নামে দুটি variable তৈরি করো। এরপর নিচের ধরনের output তৈরি করো:

```text
My name is Masum and I am 22 years old.
```

### Exercise 7: Special Characters

`\n` ও `\t` ব্যবহার করে একটি ছোট student information output তৈরি করো।

### Exercise 8: Mini Report

নিচের তথ্যগুলো ব্যবহার করে সুন্দরভাবে একটি report print করো:

```text
Student Report
Name: Masum
Department: CSE
Marks: 85
```

Output-এর heading ও information আলাদা করে সাজানোর চেষ্টা করো।

## 18. Quick Revision

| বিষয় | Example | কাজ |
|---|---|---|
| Basic output | `print("Hello")` | Text দেখায় |
| Number output | `print(100)` | Number দেখায় |
| Multiple values | `print("Age:", 22)` | একাধিক object দেখায় |
| Separator | `print(1, 2, sep="-")` | মাঝখানে `-` বসায় |
| Ending | `print("Hi", end="!")` | শেষে `!` যোগ করে |
| Newline | `print("A\nB")` | নতুন line তৈরি করে |
| Tab | `print("A\tB")` | Tab spacing তৈরি করে |
| f-string | `print(f"Age: {age}")` | String-এ variable-এর value বসায় |
| Empty line | `print()` | Blank line তৈরি করে |
| File output | `print("Hi", file=file)` | নির্দিষ্ট text stream-এ লেখে |

## 19. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `print()` function output দেখাতে ব্যবহৃত হয়।
- Text, numbers, variables, Boolean values ও expressions print করা যায়।
- একাধিক object-এর মাঝে separator নিয়ন্ত্রণ করতে `sep` ব্যবহার করা হয়।
- Output-এর শেষে কী থাকবে তা নিয়ন্ত্রণ করতে `end` ব্যবহার করা হয়।
- String concatenation এবং f-string দিয়ে text ও variable একসঙ্গে দেখানো যায়।
- `\n` newline এবং `\t` tab তৈরি করে।
- `file` ও `flush` parameter কিছু advanced পরিস্থিতিতে কাজে লাগে।
- সঠিক output formatting program-কে আরও readable করে।

## 20. Next Topic

পরবর্তী ফাইল: [`06_Comments_in_Python.md`](06_Comments_in_Python.md)

এখানে আমরা comments কী, কেন ব্যবহার করা হয়, single-line ও multi-line explanations কীভাবে লেখা যায় এবং readable code-এর জন্য comments ব্যবহারের সঠিক পদ্ধতি শিখব।
