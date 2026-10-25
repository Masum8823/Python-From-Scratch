# 01. Introduction to Python Programming

## 1. Programming কী?

**Programming** হলো computer-কে নির্দিষ্ট কোনো কাজ করার জন্য ধাপে ধাপে instruction দেওয়ার প্রক্রিয়া।

Computer নিজে থেকে আমাদের মনের কথা বুঝতে পারে না। তাকে কী করতে হবে, কীভাবে করতে হবে এবং কোন শর্তে করতে হবে, তা instructions-এর মাধ্যমে জানাতে হয়।

**Example:**

ধরো, তুমি computer-কে দুটি সংখ্যা যোগ করতে বলতে চাও।

কাজটি করার ধাপগুলো হবে:

1. প্রথম সংখ্যাটি গ্রহণ করা।
2. দ্বিতীয় সংখ্যাটি গ্রহণ করা।
3. দুটি সংখ্যা যোগ করা।
4. ফলাফল দেখানো।

এই ধাপগুলোকে কোনো programming language ব্যবহার করে লিখলে computer সেগুলো অনুসরণ করে কাজটি করতে পারে।

### সহজ উদাহরণ

```python
number1 = 10
number2 = 20

result = number1 + number2

print(result)
```

Output:

```text
30
```

এখানে আমরা Python ব্যবহার করে computer-কে দুটি সংখ্যা যোগ করতে বলেছি।

## 2. Programming Language কী?

**Programming Language** হলো এমন একটি ভাষা, যার সাহায্যে আমরা computer-কে instructions দিতে পারি।

মানুষের ভাষা, যেমন বাংলা বা ইংরেজি, computer সরাসরি সাধারণভাবে বুঝতে পারে না। তাই computer program লেখার জন্য নির্দিষ্ট rules ও syntax-সহ programming language ব্যবহার করা হয়।

### কয়েকটি জনপ্রিয় Programming Language

| Language | সাধারণ ব্যবহার |
|---|---|
| Python | AI, Machine Learning, Automation, Web Development |
| C | Operating Systems, Embedded Systems |
| C++ | Competitive Programming, Games, System Software |
| Java | Enterprise Applications, Android Development |
| JavaScript | Interactive Websites, Web Applications |
| PHP | Server-side Web Development |

প্রতিটি programming language-এর নিজস্ব syntax, rules এবং ব্যবহারের ক্ষেত্র রয়েছে।

## 3. Python কী?

**Python** হলো একটি high-level, general-purpose programming language, যা সহজ ও readable syntax-এর জন্য পরিচিত।

Python ব্যবহার করে ছোট script থেকে শুরু করে বড় software application পর্যন্ত তৈরি করা যায়।

Python-এর কিছু গুরুত্বপূর্ণ বৈশিষ্ট্য:

- **Easy to Read:** এর syntax অনেক ক্ষেত্রে সাধারণ ইংরেজির মতো সহজবোধ্য।
- **High-Level Language:** programmer-কে computer-এর hardware-level details নিয়ে তুলনামূলকভাবে কম কাজ করতে হয়।
- **General-Purpose:** বিভিন্ন ধরনের কাজে ব্যবহার করা যায়।
- **Interpreted:** Python code সাধারণত Python interpreter-এর মাধ্যমে execute করা হয়।
- **Dynamically Typed:** variable তৈরি করার সময় সাধারণত data type আলাদাভাবে ঘোষণা করতে হয় না।
- **Large Standard Library:** অনেক প্রয়োজনীয় কাজের জন্য Python-এ built-in modules ও tools রয়েছে।
- **Cross-Platform:** উপযুক্ত Python implementation ও dependencies থাকলে Windows, macOS এবং Linux-এ চালানো যায়।

### Python-এর একটি সহজ উদাহরণ

```python
print("Hello, Python!")
```

Output:

```text
Hello, Python!
```

এই একটি লাইন দিয়েই আমরা screen-এ একটি message দেখাতে পারি।

## 4. Python কেন শেখা উচিত?

Python শেখার কয়েকটি গুরুত্বপূর্ণ কারণ রয়েছে।

### 4.1 সহজ Syntax

Python-এর code সাধারণত পড়া ও বোঝা সহজ।

```python
age = 22

if age >= 18:
    print("Adult")
```

এখানে `if` ব্যবহার করে একটি condition পরীক্ষা করা হয়েছে। Condition সত্য হলে message-টি print হবে।

### 4.2 বিভিন্ন ক্ষেত্রে ব্যবহার

Python-এর ব্যবহার শুধু একটি নির্দিষ্ট ক্ষেত্রের মধ্যে সীমাবদ্ধ নয়।

- **Artificial Intelligence (AI):** Intelligent systems তৈরি করা।
- **Machine Learning (ML):** Data থেকে pattern শেখার model তৈরি করা।
- **Data Analysis:** Data বিশ্লেষণ ও ফলাফল বের করা।
- **Web Development:** Website ও web application-এর backend তৈরি করা।
- **Automation:** Repetitive কাজ স্বয়ংক্রিয়ভাবে সম্পন্ন করা।
- **Scientific Computing:** Scientific ও mathematical calculations করা।
- **Cybersecurity:** অনুমোদিত security testing ও analysis-এর বিভিন্ন কাজে ব্যবহার করা।

### 4.3 বড় Community ও Library

Python-এর বিশাল developer community রয়েছে। বিভিন্ন সমস্যার সমাধান, documentation এবং third-party packages পাওয়া যায়।

উদাহরণ:

- `NumPy` — Numerical Computing
- `Pandas` — Data Analysis
- `Matplotlib` — Data Visualization
- `Django` — Web Development
- `Scikit-learn` — Machine Learning

এই libraries ব্যবহার করে অনেক কাজ তুলনামূলকভাবে কম code লিখে করা যায়।

## 5. Python কোথায় ব্যবহার করা হয়?

| ক্ষেত্র | ব্যবহার |
|---|---|
| AI ও Machine Learning | Prediction, classification এবং intelligent applications |
| Data Science | Data cleaning, analysis ও visualization |
| Web Development | Website ও web application-এর backend |
| Automation | File management, report generation ও repetitive tasks |
| Education | Programming-এর fundamentals শেখা |
| Scientific Computing | Numerical calculations ও research |
| Software Development | বিভিন্ন ধরনের applications ও tools তৈরি |

**মনে রাখবে:** সব কাজের জন্য Python সেরা পছন্দ নয়। কোন language উপযুক্ত হবে, তা project-এর requirements, performance এবং platform-এর ওপর নির্ভর করে।

## 6. Program, Code ও Source Code কী?

এই তিনটি term programming শেখার শুরুতে বোঝা গুরুত্বপূর্ণ।

### 6.1 Code

**Code** হলো programming language ব্যবহার করে লেখা instructions।

উদাহরণ:

```python
print("I am learning Python")
```

এখানে `print("I am learning Python")` হলো code।

### 6.2 Source Code

**Source Code** হলো programmer-এর লেখা original program instructions।

আমরা যখন Python code একটি `.py` file-এ লিখি, তখন সেই file-এ source code থাকে।

উদাহরণ:

```text
hello.py
```

`hello.py` file-এর ভেতরে থাকতে পারে:

```python
print("Hello World")
```

এখানে `hello.py` হলো একটি Python source file।

### 6.3 Program

**Program** হলো নির্দিষ্ট কাজ সম্পন্ন করার জন্য তৈরি instructions-এর সমষ্টি।

উদাহরণস্বরূপ, একটি calculator program যোগ, বিয়োগ, গুণ এবং ভাগ করতে পারে।

সহজভাবে:

- **Code:** লেখা instructions।
- **Source Code:** programmer-এর লেখা original instructions।
- **Program:** নির্দিষ্ট কাজ করার জন্য তৈরি সম্পূর্ণ instructions।

বাস্তবে এই শব্দগুলো অনেক সময় কাছাকাছি অর্থেও ব্যবহার করা হয়।

## 7. Python Interpreter কী?

**Python Interpreter** হলো এমন একটি software, যা Python code execute করতে সাহায্য করে।

আমরা Python code লিখলেই computer স্বয়ংক্রিয়ভাবে সেটি বুঝে ফেলে না। Code execute করার জন্য Python runtime environment প্রয়োজন হয়।

CPython-এর মতো প্রচলিত Python implementation-এ source code সাধারণত bytecode-এ রূপান্তরিত হয় এবং Python Virtual Machine সেটি execute করে। তবে implementation অনুযায়ী অভ্যন্তরীণ প্রক্রিয়া ভিন্ন হতে পারে।

### Execution-এর সহজ ধারণা

```text
Python Source Code
        |
        v
Python Interpreter
        |
        v
Code Execution
        |
        v
Output
```

উদাহরণ:

```python
print("Learning Python")
```

Output:

```text
Learning Python
```

এখানে Python interpreter code-টি execute করতে সাহায্য করে এবং output হিসেবে message-টি দেখায়।

## 8. Python Code কীভাবে কাজ করে?

একটি সাধারণ Python program চালানোর প্রক্রিয়া ধাপে ধাপে বোঝা যাক।

ধরো, `main.py` নামে একটি file-এ নিচের code রয়েছে:

```python
first_number = 5
second_number = 7

total = first_number + second_number

print(total)
```

### Step 1: Code লেখা

প্রথমে programmer Python syntax ব্যবহার করে instructions লেখে।

### Step 2: Code সংরক্ষণ

Code-টি `main.py` নামে একটি file-এ save করা হয়।

### Step 3: Program চালানো

Terminal অথবা VS Code-এর Run option ব্যবহার করে program চালানো হয়।

### Step 4: Code Execute হওয়া

Python interpreter program-এর instructions execute করে।

### Step 5: Output পাওয়া

Output হবে:

```text
12
```

এভাবে আমরা Python code লিখে বিভিন্ন ধরনের কাজ সম্পন্ন করতে পারি।

## 9. Python-এর সুবিধা ও সীমাবদ্ধতা

### Advantages of Python

1. **Easy to Learn:** নতুনদের জন্য syntax তুলনামূলকভাবে সহজ।
2. **Readable Code:** Code পড়া ও maintain করা সুবিধাজনক।
3. **Versatile:** বিভিন্ন ধরনের application তৈরি করা যায়।
4. **Rich Libraries:** অনেক ready-made tools ও libraries পাওয়া যায়।
5. **Cross-Platform:** বিভিন্ন operating system-এ ব্যবহার করা যায়।
6. **Rapid Development:** অনেক project তুলনামূলকভাবে দ্রুত তৈরি করা সম্ভব।

### Limitations of Python

1. **Performance:** কিছু CPU-intensive task-এ compiled language-এর তুলনায় ধীর হতে পারে।
2. **Memory Usage:** কিছু workload-এ বেশি memory প্রয়োজন হতে পারে।
3. **Mobile Development:** Native mobile application তৈরির প্রধান পছন্দ হিসেবে Python সাধারণত ব্যবহৃত হয় না।
4. **Runtime Errors:** কিছু error program চালানোর সময় প্রকাশ পেতে পারে।
5. **Deployment Requirements:** অন্য computer-এ program চালাতে Python runtime, dependencies বা packaging-এর প্রয়োজন হতে পারে।

তবে সঠিক tool, library ও architecture নির্বাচন করলে Python দিয়ে অনেক শক্তিশালী application তৈরি করা সম্ভব।

## 10. Python এবং অন্য Programming Language-এর মধ্যে পার্থক্য

Python, C, C++ ও Java—সবগুলোই programming language, কিন্তু তাদের syntax, execution model এবং ব্যবহারের ক্ষেত্র এক নয়।

| বিষয় | Python | C/C++ |
|---|---|---|
| Syntax | তুলনামূলকভাবে সহজ ও concise | তুলনামূলকভাবে বেশি low-level control থাকতে পারে |
| Typing | Dynamically typed | C/C++ সাধারণত statically typed |
| Memory Management | সাধারণত automatic memory management | Memory management-এর ওপর বেশি control পাওয়া যায় |
| Development Speed | অনেক ক্ষেত্রে দ্রুত development সম্ভব | Project অনুযায়ী development time ভিন্ন হতে পারে |
| Performance | কিছু task-এ ধীর হতে পারে | অনেক performance-critical task-এ উপযুক্ত |
| Common Uses | AI, data analysis, automation, backend | Systems programming, embedded systems, performance-critical software |

**Important:** কোনো language সব পরিস্থিতিতে অন্য language-এর চেয়ে ভালো নয়। Project-এর উদ্দেশ্য অনুযায়ী language নির্বাচন করা হয়।

## 11. Python শেখার জন্য কী কী প্রয়োজন?

Python শেখা শুরু করতে খুব বেশি কিছু প্রয়োজন হয় না।

সাধারণভাবে প্রয়োজন:

1. একটি computer।
2. Python interpreter।
3. একটি code editor, যেমন VS Code।
4. Code চালানোর জন্য Terminal বা editor-এর Run সুবিধা।
5. নিয়মিত practice করার মানসিকতা।

তোমার computer-এ Python ও VS Code setup করা থাকলে নতুন software install না করেও এই chapter-এর code examples practice করতে পারবে।

## 12. প্রথম Python Program

এখন নিজে একটি সহজ Python program লিখি।

```python
print("My name is Masum")
print("I am learning Python")
print("Python is easy to read")
```

Output:

```text
My name is Masum
I am learning Python
Python is easy to read
```

### Code Explanation

- `print()` হলো Python-এর একটি built-in function।
- Parentheses `()`-এর মধ্যে যে text দেওয়া হয়, সেটি output-এ দেখানো হয়।
- Text লেখার জন্য single quotation mark `' '` অথবা double quotation mark `" "` ব্যবহার করা যায়।
- প্রতিটি `print()` statement আলাদা output line তৈরি করে।

এই program-এ আমরা শুধু text output করেছি। পরবর্তী topics-এ `print()`, variables, data types এবং অন্যান্য fundamentals বিস্তারিতভাবে শিখব।

## 13. Practice Exercises

নিচের কাজগুলো নিজে করে দেখো।

### Exercise 1: Introduction

একটি Python program লেখো, যা তোমার নাম, department এবং university-এর নাম আলাদা লাইনে print করবে।

Expected output-এর উদাহরণ:

```text
Name: Masum
Department: CSE
University: Northern University Bangladesh
```

### Exercise 2: Favourite Subject

তোমার পছন্দের subject-এর নাম print করো।

### Exercise 3: Multiple Messages

তিনটি আলাদা `print()` statement ব্যবহার করে তিনটি message দেখাও।

### Exercise 4: Explain Python

নিজের ভাষায় নিচের প্রশ্নগুলোর উত্তর লেখো:

1. Programming কী?
2. Python কী?
3. Programming language কেন প্রয়োজন?
4. Python interpreter কী?
5. Python-এর তিনটি ব্যবহার লেখো।
6. Source code ও program-এর মধ্যে পার্থক্য কী?

### Exercise 5: Experiment

নিচের code চালাও:

```python
print("Hello")
print("Python")
print("Programming")
```

এরপর message-গুলো পরিবর্তন করে আবার চালাও এবং output পর্যবেক্ষণ করো।

## 14. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Programming হলো computer-কে instructions দেওয়ার প্রক্রিয়া।
- Programming language ব্যবহার করে program লেখা হয়।
- Python একটি high-level, general-purpose programming language।
- Python AI, Machine Learning, Data Analysis, Web Development ও Automation-এ ব্যবহৃত হয়।
- Code হলো programming instructions; source code হলো programmer-এর লেখা original instructions।
- Python interpreter code execute করতে সাহায্য করে।
- Python-এর সুবিধার পাশাপাশি কিছু performance ও deployment-related limitation-ও রয়েছে।
- নিয়মিত code লেখা ও practice করার মাধ্যমে Python programming শেখা যায়।

## 15. Next Topic

পরবর্তী ফাইল: [`02_Understanding_Python_Syntax.md`](02_Understanding_Python_Syntax.md)

এই topic-এ আমরা Python Syntax, syntax rules, valid ও invalid code এবং syntax error সম্পর্কে বিস্তারিত শিখব।
