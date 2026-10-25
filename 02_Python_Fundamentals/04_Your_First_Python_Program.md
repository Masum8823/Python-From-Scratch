# 04. Your First Python Program

## 1. Introduction

Python শেখার সবচেয়ে ভালো উপায় হলো নিজে code লেখা এবং সেটি run করে দেখা।

আমাদের প্রথম program হবে খুব সহজ। এটি screen-এ একটি message দেখাবে।

```python
print("Hello, World!")
```

Output:

```text
Hello, World!
```

এটি একটি সাধারণ introductory program। এর মাধ্যমে আমরা Python code লেখা, quotation marks ব্যবহার, `print()` function এবং output দেখার প্রাথমিক ধারণা পাব।

## 2. What Is "Hello, World!"?

**Hello, World!** হলো programming শেখার সময় ব্যবহৃত একটি প্রচলিত প্রথম program-এর উদাহরণ।

নতুন programming language শেখার সময় অনেকেই প্রথমে এমন একটি program লেখেন, যা screen-এ `Hello, World!` message দেখায়।

এর উদ্দেশ্য হলো:

- Code লেখার পদ্ধতি শেখা।
- Program file তৈরি করা।
- Program execute করা।
- Output সঠিকভাবে দেখা।
- Development environment কাজ করছে কি না যাচাই করা।

এই ছোট program সফলভাবে run করতে পারলে বোঝা যায়, Python-এর basic execution process কাজ করছে।

## 3. Creating Your First Python File

প্রথমে একটি Python file তৈরি করতে হবে।

### Step 1: VS Code Open করো

তোমার computer-এ Visual Studio Code চালু করো।

### Step 2: Project Folder Open করো

একটি folder তৈরি করো, যেমন:

```text
Python_Practice
```

এরপর VS Code থেকে **File → Open Folder** নির্বাচন করে folder-টি open করো।

### Step 3: নতুন File তৈরি করো

VS Code Explorer থেকে New File নির্বাচন করে file-এর নাম দাও:

```text
hello.py
```

এখানে `.py` হলো Python source file-এর extension।

### Step 4: Code লেখো

`hello.py` file-এর মধ্যে লেখো:

```python
print("Hello, World!")
```

### Step 5: File Save করো

`Ctrl + S` চাপ দিয়ে file save করো।

এখন তোমার project structure হবে:

```text
Python_Practice/
└── hello.py
```

**মনে রাখবে:** File-এর নাম `hello.py.txt` হয়ে গেলে সেটি সাধারণত ভুল extension। File-এর প্রকৃত নাম `hello.py` কি না যাচাই করবে।

## 4. Understanding the First Program

এবার code-এর প্রতিটি অংশ বুঝে নিই।

```python
print("Hello, World!")
```

### 4.1 `print`

`print` হলো Python-এর একটি built-in function, যা output দেখাতে ব্যবহৃত হয়।

```python
print("Python")
```

Output:

```text
Python
```

### 4.2 Parentheses `()`

Function call করার সময় parentheses ব্যবহার করা হয়।

```python
print("Hello")
```

এখানে `print()` হলো function call।

### 4.3 Quotation Marks

Text বা string বোঝানোর জন্য quotation marks ব্যবহার করা হয়।

```python
print("Hello, World!")
```

এখানে `"Hello, World!"` হলো একটি string।

Single quotation marks-ও ব্যবহার করা যায়:

```python
print('Hello, World!')
```

দুটি উদাহরণই একই output দেবে।

### 4.4 Text বা String

String হলো text data-এর একটি type।

উদাহরণ:

```python
print("My name is Masum")
print("I am learning Python")
```

Output:

```text
My name is Masum
I am learning Python
```

এই program-এ দুটি string output হিসেবে দেখানো হয়েছে।

## 5. Running the Program in VS Code

VS Code-এ Python file চালানোর একাধিক উপায় রয়েছে।

### Method 1: Run Python File

1. `hello.py` file open করো।
2. Editor-এর উপরের Run Python File button নির্বাচন করো, যদি সেটি available থাকে।
3. Terminal-এ output দেখো।

Expected output:

```text
Hello, World!
```

এই পদ্ধতিতে Python extension এবং উপযুক্ত interpreter configure করা থাকা প্রয়োজন হতে পারে।

### Method 2: Using the Terminal

VS Code-এর Terminal open করো।

সাধারণভাবে:

- Windows/Linux: `Ctrl + ``
- macOS: `Control + ``

Keyboard shortcut কাজ না করলে menu থেকে **Terminal → New Terminal** নির্বাচন করো।

এরপর project folder-এর terminal-এ নিচের command চালাও:

Windows:

```powershell
python hello.py
```

macOS/Linux-এ অনেক ক্ষেত্রে:

```bash
python3 hello.py
```

কিছু Windows environment-এ `py hello.py` command-ও কাজ করতে পারে।

Output:

```text
Hello, World!
```

যদি `python` বা `python3` command কাজ না করে, তাহলে Python installation এবং interpreter configuration যাচাই করো।

## 6. Writing Multiple Print Statements

একটি program-এ একাধিক `print()` statement লেখা যায়।

```python
print("Hello, World!")
print("Welcome to Python")
print("Programming is interesting")
```

Output:

```text
Hello, World!
Welcome to Python
Programming is interesting
```

সাধারণভাবে প্রতিটি `print()` call-এর output নতুন লাইনে দেখা যায়।

### নিজের মতো করে পরিবর্তন করো

```python
print("My name is Masum")
print("I study CSE")
print("I am learning Python programming")
```

এখানে message-গুলো পরিবর্তন করে program আবার run করো।

## 7. Printing Numbers

`print()` শুধু text নয়, numbers-ও output হিসেবে দেখাতে পারে।

```python
print(10)
print(25)
print(100)
```

Output:

```text
10
25
100
```

এখানে সংখ্যাগুলো quotation marks-এর মধ্যে নেই। তাই এগুলো string নয়, integer values।

### Text ও Number-এর পার্থক্য

```python
print(100)
print("100")
```

Output:

```text
100
100
```

দেখতে output একই হলেও data দুটির type আলাদা:

- `100` হলো integer literal।
- `"100"` হলো string literal।

এই পার্থক্য পরবর্তী data types chapter-এ বিস্তারিতভাবে শিখব।

## 8. Performing Simple Calculations

Python ব্যবহার করে calculation-ও করা যায়।

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

| Operator | কাজ |
|---|---|
| `+` | Addition |
| `-` | Subtraction |
| `*` | Multiplication |
| `/` | Division |

Python expression evaluate করে তার result `print()`-এর মাধ্যমে দেখাচ্ছে।

**লক্ষ্য করো:** `/` ব্যবহার করে division করলে সাধারণত result floating-point number হয়। তাই `10 / 5`-এর output `2` না হয়ে `2.0` হয়েছে।

## 9. Using Variables in Your First Program

এবার variable ব্যবহার করে program-টি একটু উন্নত করি।

```python
name = "Masum"

print(name)
```

Output:

```text
Masum
```

এখানে `name` variable-এর মধ্যে `"Masum"` string রাখা হয়েছে।

### একাধিক Variable

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

এই program-এ প্রতিটি variable-এ আলাদা তথ্য রাখা হয়েছে এবং `print()` দিয়ে সেগুলো output হিসেবে দেখানো হয়েছে।

## 10. Using Comments in Your First Program

Code-এর উদ্দেশ্য বোঝানোর জন্য comment ব্যবহার করা যায়।

```python
# Display a greeting message
print("Hello, World!")
```

Output:

```text
Hello, World!
```

এখানে `#` দিয়ে comment শুরু হয়েছে।

Python comment-টিকে সাধারণ executable statement হিসেবে চালায় না। তবে comment code বুঝতে ও maintain করতে সাহায্য করে।

## 11. Understanding Program Execution

যখন আমরা `hello.py` run করি, তখন সাধারণভাবে নিচের কাজগুলো ঘটে:

1. Python command বা editor program চালানোর নির্দেশ দেয়।
2. Python interpreter source file process করে।
3. Program-এর instructions execute হয়।
4. `print()` function output দেখায়।

সহজভাবে:

```text
hello.py
   |
   v
Python Interpreter
   |
   v
Execute print()
   |
   v
Hello, World!
```

এটি একটি simplified diagram। Python-এর অভ্যন্তরীণ execution process implementation অনুযায়ী আরও বিস্তারিত।

## 12. Common Errors and Solutions

প্রথম program লেখার সময় কিছু সাধারণ ভুল হতে পারে।

### Error 1: Missing Quotation Mark

ভুল code:

```python
print("Hello, World!)
```

সমস্যা: String-এর quotation mark সঠিকভাবে বন্ধ করা হয়নি।

সঠিক code:

```python
print("Hello, World!")
```

### Error 2: Missing Parenthesis

ভুল code:

```python
print("Hello, World!"
```

সমস্যা: Closing parenthesis `)` নেই।

সঠিক code:

```python
print("Hello, World!")
```

### Error 3: Incorrect Capitalization

ভুল code:

```python
Print("Hello, World!")
```

সমস্যা: Python case-sensitive। `Print` এবং `print` আলাদা নাম।

সঠিক code:

```python
print("Hello, World!")
```

### Error 4: Wrong File Name

যদি terminal-এ `python hello.py` চালানোর পর file পাওয়া যাচ্ছে না বলে error আসে, তাহলে:

1. File-এর নাম যাচাই করো।
2. Terminal-এর current working directory যাচাই করো।
3. File ওই folder-এ আছে কি না দেখো।
4. প্রয়োজনে সঠিক folder-এ গিয়ে command চালাও।

### Error 5: Python Command Not Found

যদি `python` command কাজ না করে:

1. Python installation যাচাই করো।
2. Windows-এ `py --version` চেষ্টা করো।
3. macOS/Linux-এ `python3 --version` চেষ্টা করো।
4. VS Code-এ সঠিক Python interpreter নির্বাচন করা আছে কি না যাচাই করো।

## 13. Practical Exercises

### Exercise 1: Print Your Introduction

একটি program লেখো, যা নিচের তথ্যগুলো আলাদা লাইনে দেখাবে:

- তোমার নাম
- তোমার department
- তোমার university
- তোমার favourite programming language

### Exercise 2: Print Numbers

একটি program লেখো, যা `10`, `20`, `30`, `40` এবং `50` আলাদা লাইনে print করবে।

### Exercise 3: Simple Calculation

একটি program লেখো, যা:

1. `25 + 15` calculate করবে।
2. `25 - 15` calculate করবে।
3. `25 * 15` calculate করবে।
4. `25 / 15` calculate করবে।

প্রতিটি result আলাদাভাবে print করো।

### Exercise 4: Use Variables

নিচের তথ্যগুলো variable-এ রাখো এবং output দেখাও:

```text
Name: Masum
Age: 22
Department: CSE
```

Variable-এর নাম অর্থপূর্ণ রাখবে।

### Exercise 5: Find and Fix Errors

নিচের code-গুলোর ভুল ঠিক করো।

**A.**

```python
print("Hello Python"
```

**B.**

```python
Print("Learning Python")
```

**C.**

```python
print("My first program!)
```

প্রতিটি code ঠিক করার পর run করে দেখো।

### Exercise 6: Build a Mini Program

একটি ছোট program লেখো, যা:

- একটি greeting message print করবে।
- তোমার নাম print করবে।
- দুটি সংখ্যা যোগ করবে।
- যোগফল print করবে।
- একটি comment দিয়ে program-এর উদ্দেশ্য ব্যাখ্যা করবে।

## 14. Self-Assessment Checklist

নিজেকে যাচাই করো:

- [ ] Python file তৈরি করতে পারি।
- [ ] `.py` extension চিনতে পারি।
- [ ] `print()` ব্যবহার করতে পারি।
- [ ] String ও number print করতে পারি।
- [ ] Simple calculation করতে পারি।
- [ ] Variable ব্যবহার করতে পারি।
- [ ] VS Code বা Terminal দিয়ে program run করতে পারি।
- [ ] সাধারণ syntax error খুঁজে ঠিক করতে পারি।

সবগুলোতে টিক দিতে পারলে পরবর্তী topic-এ যাওয়ার জন্য প্রস্তুত।

## 15. Chapter Summary

এই topic-এ আমরা শিখেছি:

- কীভাবে প্রথম Python program লিখতে হয়।
- কীভাবে `hello.py` file তৈরি ও save করতে হয়।
- `print()` function দিয়ে output দেখাতে হয়।
- String, number এবং variables ব্যবহার করতে হয়।
- Simple mathematical calculations করতে হয়।
- VS Code ও Terminal দিয়ে program run করতে হয়।
- সাধারণ syntax ও execution-related errors শনাক্ত করতে হয়।

## 16. Next Topic

পরবর্তী ফাইল: [`05_Print_Function_and_Output.md`](05_Print_Function_and_Output.md)

এখানে আমরা `print()` function-এর ব্যবহার, একাধিক value print করা, `sep`, `end`, output formatting এবং আরও গুরুত্বপূর্ণ বিষয় বিস্তারিতভাবে শিখব।
