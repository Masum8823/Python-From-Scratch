# 02. Understanding Python Syntax

## 1. Python Syntax কী?

**Python Syntax** হলো Python code লেখার নিয়মাবলি। একটি program সঠিকভাবে লেখার জন্য এই নিয়মগুলো অনুসরণ করতে হয়।

যেমন, বাংলা বা ইংরেজি লেখার সময় ভাষার নির্দিষ্ট নিয়ম থাকে, তেমনি Python code লেখারও কিছু নির্দিষ্ট নিয়ম রয়েছে।

**Example:**

```python
print("Hello, Python!")
```

Output:

```text
Hello, Python!
```

এটি একটি valid Python statement, কারণ এখানে `print()` function সঠিকভাবে লেখা হয়েছে।

কিন্তু নিচের code-টি দেখো:

```python
print("Hello, Python!"
```

এখানে শেষের closing parenthesis `)` নেই। তাই Python এই code execute করার সময় syntax error দেখাবে।

**মনে রাখবে:** Python code লেখার সময় syntax rules মেনে চলা অত্যন্ত গুরুত্বপূর্ণ।

## 2. Basic Syntax Rules

Python code লেখার সময় কয়েকটি গুরুত্বপূর্ণ নিয়ম অনুসরণ করতে হয়।

### 2.1 Parentheses সঠিকভাবে ব্যবহার করা

Function call করার সময় parentheses `()` সঠিকভাবে ব্যবহার করতে হয়।

সঠিক:

```python
print("Hello")
```

ভুল:

```python
print("Hello"
```

দ্বিতীয় উদাহরণে closing parenthesis নেই।

### 2.2 String-এর Quotation Marks ব্যবহার করা

String লেখার সময় quotation marks ব্যবহার করতে হয়।

সঠিক:

```python
print("Python")
print('Programming')
```

ভুল:

```python
print(Python)
```

এখানে `Python`-কে quotation marks-এর মধ্যে রাখা হয়নি। Python এটিকে variable বা অন্য কোনো identifier হিসেবে বিবেচনা করার চেষ্টা করবে। আগে থেকে এমন নাম সংজ্ঞায়িত না থাকলে `NameError` হবে।

### 2.3 Colon ব্যবহার করা

`if`, `for`, `while`, `def` এবং `class`-এর মতো কিছু statement-এর শেষে colon `:` ব্যবহার করতে হয়।

উদাহরণ:

```python
if 10 > 5:
    print("10 is greater than 5")
```

Output:

```text
10 is greater than 5
```

ভুল উদাহরণ:

```python
if 10 > 5
    print("10 is greater than 5")
```

এখানে `if` statement-এর শেষে colon নেই। ফলে syntax error হবে।

### 2.4 Operators সঠিকভাবে ব্যবহার করা

Operators ব্যবহার করে calculation বা comparison করা হয়।

সঠিক:

```python
result = 10 + 5
print(result)
```

Output:

```text
15
```

ভুল:

```python
result = 10 +
```

এখানে expression-টি অসম্পূর্ণ, তাই syntax error হবে।

### 2.5 Brackets-এর Matching

যে opening bracket ব্যবহার করবে, তার উপযুক্ত closing bracket থাকতে হবে।

| Opening | Closing |
|---|---|
| `(` | `)` |
| `[` | `]` |
| `{` | `}` |

সঠিক:

```python
numbers = [10, 20, 30]
print(numbers)
```

ভুল:

```python
numbers = [10, 20, 30
```

এখানে closing square bracket `]` নেই।

## 3. Python Case Sensitivity

Python হলো **case-sensitive programming language**। অর্থাৎ, uppercase ও lowercase letters-কে আলাদা হিসেবে বিবেচনা করা হয়।

উদাহরণ:

```python
name = "Masum"
Name = "Ritu"

print(name)
print(Name)
```

Output:

```text
Masum
Ritu
```

এখানে `name` এবং `Name` দুটি আলাদা variable।

### Function-এর ক্ষেত্রেও Case গুরুত্বপূর্ণ

সঠিক:

```python
print("Hello")
```

ভুল:

```python
Print("Hello")
```

Python-এর built-in function-এর নাম `print`, `Print` নয়। তাই `Print()` ব্যবহার করলে আগে থেকে সংজ্ঞায়িত না থাকায় সাধারণত `NameError` হবে।

**মনে রাখবে:** Python-এর built-in names এবং keywords সঠিক capitalization-এ লিখতে হবে।

## 4. Indentation কী?

**Indentation** হলো code-এর শুরুতে space বা tab ব্যবহার করে code-কে ভেতরের দিকে সরিয়ে লেখা।

Python-এ indentation শুধু code সুন্দরভাবে সাজানোর জন্য নয়; এটি program-এর structure নির্ধারণ করতেও ব্যবহৃত হয়।

উদাহরণ:

```python
if 10 > 5:
    print("Condition is true")
```

এখানে `print()` statement-টি `if` block-এর ভেতরে রয়েছে। সাধারণভাবে একটি block-এর জন্য চারটি space ব্যবহার করা হয়।

ভুল উদাহরণ:

```python
if 10 > 5:
print("Condition is true")
```

এখানে `print()`-কে প্রয়োজনীয় indentation দেওয়া হয়নি। তাই `IndentationError` হবে।

### Indentation-এর গুরুত্বপূর্ণ নিয়ম

- সাধারণভাবে প্রতি indentation level-এ চারটি space ব্যবহার করো।
- একই block-এর statements-এ consistent indentation রাখো।
- একই block-এ অপ্রয়োজনে tabs ও spaces মিশিয়ে ব্যবহার করো না।
- `if`, `for`, `while`, `def` ইত্যাদির block সঠিকভাবে indent করো।

উদাহরণ:

```python
age = 20

if age >= 18:
    print("Adult")
    print("Eligible by age")
```

এখানে দুটি `print()` statement একই block-এর অংশ।

## 5. Statements কীভাবে লেখা হয়?

**Statement** হলো Python-এর এমন একটি instruction, যা কোনো কাজ সম্পন্ন করে।

উদাহরণ:

```python
name = "Masum"
age = 22
print(name)
print(age)
```

এখানে প্রতিটি assignment ও function call একটি statement।

### একাধিক Statement

সাধারণত প্রতিটি statement আলাদা লাইনে লেখা হয়।

ভালো পদ্ধতি:

```python
first = 10
second = 20
total = first + second

print(total)
```

Python-এ কিছু ক্ষেত্রে একই লাইনে একাধিক statement লেখা সম্ভব, কিন্তু beginner হিসেবে প্রতিটি statement আলাদা লাইনে লেখাই ভালো।

## 6. Line Break ও Newline

Python-এ সাধারণত একটি logical statement একাধিক physical line-এ ভাগ করা যায় না, যদি না continuation-এর উপযুক্ত নিয়ম ব্যবহার করা হয়।

সাধারণ উদাহরণ:

```python
first_name = "Abdulla"
last_name = "Masum"

print(first_name)
print(last_name)
```

এখানে প্রতিটি statement আলাদা লাইনে রয়েছে।

### Long Expression ভাঙা

Parentheses-এর মধ্যে expression একাধিক লাইনে লেখা যায়।

```python
total = (
    10
    + 20
    + 30
)

print(total)
```

Output:

```text
60
```

এভাবে দীর্ঘ expression পড়তে ও বুঝতে সুবিধা হয়।

## 7. Whitespace-এর ব্যবহার

**Whitespace** বলতে space, tab এবং newline-এর মতো ফাঁকা জায়গা বোঝায়।

Python-এ whitespace-এর ভূমিকা context অনুযায়ী ভিন্ন হয়।

উদাহরণ:

```python
total = 10 + 20
```

এবং

```python
total=10+20
```

দুটিই valid Python code এবং একই ফলাফল দেয়।

তবে readability-এর জন্য operators-এর দুই পাশে space রাখা ভালো।

### String-এর ভেতরে Whitespace

```python
print("Hello World")
print("HelloWorld")
```

Output:

```text
Hello World
HelloWorld
```

String-এর ভেতরের space output-এর অংশ। তাই সেখানে space সরিয়ে দিলে ফলাফল পরিবর্তিত হয়।

## 8. Comments-এর Basic ধারণা

Python-এ comment ব্যবহার করে code সম্পর্কে ব্যাখ্যা লেখা যায়।

Single-line comment-এর জন্য `#` ব্যবহার করা হয়।

```python
# This is a comment
print("Hello Python")
```

Output:

```text
Hello Python
```

Python সাধারণত comment-কে executable instruction হিসেবে বিবেচনা করে না।

একাধিক লাইনের code সম্পর্কে ব্যাখ্যা দিতে প্রয়োজন অনুযায়ী একাধিক `#` ব্যবহার করা যায়।

```python
# Store the user's age
# Then display the age
age = 22
print(age)
```

Comments নিয়ে বিস্তারিত আলোচনা থাকবে `06_Comments_in_Python.md` ফাইলে।

## 9. Valid Code ও Invalid Code

**Valid Code** হলো এমন code, যা Python-এর syntax rules মেনে লেখা হয়েছে।

**Invalid Code** হলো এমন code, যেখানে syntax বা অন্যান্য নিয়মের সমস্যা রয়েছে।

| Valid Code | Invalid Code | কারণ |
|---|---|---|
| `print("Hello")` | `print("Hello"` | Closing parenthesis নেই |
| `if age > 18:` | `if age > 18` | Colon নেই |
| `total = 10 + 20` | `total = 10 +` | Expression অসম্পূর্ণ |
| `numbers = [1, 2, 3]` | `numbers = [1, 2, 3` | Closing bracket নেই |
| `if True:` followed by an indented statement | `if True:` followed by an unindented statement | প্রয়োজনীয় indentation নেই |

**গুরুত্বপূর্ণ:** কোনো code syntax-wise valid হলেই যে সেটি সঠিক ফলাফল দেবে, এমন নয়। Syntax ঠিক থাকলেও logical error থাকতে পারে।

উদাহরণ:

```python
print(10 - 5)
```

Output:

```text
5
```

কিন্তু যদি তোমার উদ্দেশ্য যোগ করা হয়, তাহলে syntax ঠিক থাকলেও logic ভুল:

```python
print(10 - 5)
```

এখানে `+`-এর পরিবর্তে `-` ব্যবহৃত হয়েছে।

## 10. Syntax Error কী?

**SyntaxError** হলো Python code-এর syntax-এ সমস্যা থাকলে পাওয়া error।

উদাহরণ:

```python
print("Hello"
```

এখানে closing parenthesis না থাকায় Python syntax error দেখাবে।

আরেকটি উদাহরণ:

```python
if 10 > 5
    print("True")
```

এখানে `if` statement-এর শেষে colon নেই।

### Syntax Error সমাধান করার উপায়

1. Error message মনোযোগ দিয়ে পড়ো।
2. কোন line-এ error দেখাচ্ছে তা খুঁজে বের করো।
3. Brackets ও quotation marks মিলিয়ে দেখো।
4. Colon এবং indentation পরীক্ষা করো।
5. ভুল ঠিক করে program আবার চালাও।

মনে রাখবে, error message-এ দেখানো line-টি সব সময় সমস্যার সম্পূর্ণ উৎস নাও হতে পারে। কখনো আগের লাইনের ভুলের কারণেও পরের লাইনে error দেখা যায়।

## 11. Python Syntax Error ও Runtime Error-এর পার্থক্য

| বিষয় | Syntax Error | Runtime Error |
|---|---|---|
| কখন ঘটে | Code-এর syntax ভুল হলে | Program execute করার সময় সমস্যা হলে |
| উদাহরণ | Closing bracket নেই | শূন্য দিয়ে ভাগ করা |
| ফলাফল | Program স্বাভাবিকভাবে execute শুরু করতে পারে না | Program চলার সময় error ঘটতে পারে |

উদাহরণ:

**Syntax Error:**

```python
print("Hello"
```

**Runtime Error:**

```python
result = 10 / 0
print(result)
```

দ্বিতীয় উদাহরণে syntax ঠিক আছে, কিন্তু শূন্য দিয়ে ভাগ করা যায় না। তাই `ZeroDivisionError` হবে।

## 12. Python Syntax-এর কিছু গুরুত্বপূর্ণ নিয়ম

| Rule | Explanation |
|---|---|
| Case-sensitive | `name` ও `Name` আলাদা |
| Indentation | Code block-এর structure নির্ধারণ করে |
| Colon | কিছু compound statement-এর শেষে প্রয়োজন |
| Matching brackets | Opening ও closing brackets মিলতে হবে |
| Quotation marks | String সঠিকভাবে delimit করতে হবে |
| Assignment | Variable-এ value দেওয়ার জন্য `=` ব্যবহার হয় |
| Comments | `#` দিয়ে single-line comment শুরু হয় |
| Readability | Consistent spacing ও formatting code বোঝা সহজ করে |

## 13. Common Beginner Mistakes

### Mistake 1: Quotation Marks ভুলে যাওয়া

ভুল:

```python
print(Hello)
```

সঠিক:

```python
print("Hello")
```

### Mistake 2: Bracket বন্ধ না করা

ভুল:

```python
print(10 + 20
```

সঠিক:

```python
print(10 + 20)
```

### Mistake 3: Colon ভুলে যাওয়া

ভুল:

```python
if age >= 18
    print("Adult")
```

সঠিক:

```python
if age >= 18:
    print("Adult")
```

### Mistake 4: Indentation না দেওয়া

ভুল:

```python
if True:
print("Hello")
```

সঠিক:

```python
if True:
    print("Hello")
```

### Mistake 5: Capitalization ভুল করা

ভুল:

```python
Print("Hello")
```

সঠিক:

```python
print("Hello")
```

## 14. Practice Exercises

### Exercise 1: Correct the Syntax

নিচের code-গুলোর ভুল খুঁজে ঠিক করো।

**A.**

```python
print("Learning Python"
```

**B.**

```python
if 20 > 10
    print("Twenty is greater")
```

**C.**

```python
Print("Hello World")
```

**D.**

```python
numbers = [10, 20, 30
print(numbers)
```

### Exercise 2: Write Valid Code

একটি program লেখো, যা:

1. তোমার নাম print করবে।
2. তোমার বয়স একটি variable-এ রাখবে।
3. বয়স print করবে।
4. বয়স ১৮ বা তার বেশি হলে `Adult` print করবে।

### Exercise 3: Identify the Error

নিচের code-এ কী সমস্যা আছে?

```python
age = 22

if age >= 18:
print("Adult")
```

Error-এর কারণ ব্যাখ্যা করে সঠিক code লেখো।

### Exercise 4: Experiment with Whitespace

নিচের দুটি code চালিয়ে output তুলনা করো।

```python
print("Python is easy")
```

```python
print("Pythoniseasy")
```

Output কেন আলাদা হয়েছে, তা নিজের ভাষায় লেখো।

### Exercise 5: Explain the Concepts

নিজের ভাষায় উত্তর দাও:

1. Python Syntax কী?
2. Case sensitivity বলতে কী বোঝায়?
3. Indentation কেন গুরুত্বপূর্ণ?
4. SyntaxError কী?
5. Syntax error ও runtime error-এর মধ্যে পার্থক্য কী?
6. Valid code কি সব সময় সঠিক ফলাফল দেয়?

## 15. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Python Syntax হলো Python code লেখার নিয়মাবলি।
- Python case-sensitive, তাই uppercase ও lowercase আলাদা।
- Indentation code block-এর structure নির্ধারণ করে।
- কিছু statement-এর শেষে colon `:` দিতে হয়।
- Parentheses, square brackets এবং quotation marks সঠিকভাবে ব্যবহার করতে হয়।
- Syntax error হলে code-এর syntax ঠিক করতে হয়।
- Syntax ঠিক থাকলেও logic ভুল হতে পারে।
- নিয়মিত practice করলে syntax-related ভুল কমে যায়।

## 16. Next Topic

পরবর্তী ফাইল: [`03_Structure_of_a_Python_Program.md`](03_Structure_of_a_Python_Program.md)

এখানে আমরা একটি Python program-এর structure, code-এর execution order, statements-এর arrangement এবং program কীভাবে সাজাতে হয় তা শিখব।
