# 04. Prerequisites

## 1. Introduction

Prerequisites হলো কোনো বিষয় শেখা শুরু করার আগে যে প্রাথমিক জ্ঞান, দক্ষতা বা tools প্রয়োজন হতে পারে।

Python programming শেখার সবচেয়ে ভালো দিক হলো, এটি শুরু করার জন্য আগে থেকে programming জানা বাধ্যতামূলক নয়। একেবারে beginner হয়েও Python শেখা শুরু করা যায়।

তবে computer ব্যবহার, file management এবং basic mathematical reasoning সম্পর্কে ধারণা থাকলে শেখার প্রক্রিয়া সহজ হয়।

এই ফাইলে Python শেখার জন্য প্রয়োজনীয় প্রস্তুতি, beginner হিসেবে কী জানা দরকার এবং কোন বিষয়গুলো পরে শেখা যাবে, তা আলোচনা করা হবে।

---

## 2. Is Previous Programming Knowledge Required?

**না, আগে থেকে কোনো programming language জানা বাধ্যতামূলক নয়।**

Python একটি beginner-friendly programming language। তাই C, C++, Java বা অন্য কোনো language না জানলেও Python শেখা শুরু করতে পারবে।

তবে আগে থেকে programming জানা থাকলে কিছু বিষয় বুঝতে সুবিধা হতে পারে:

- Variables
- Data types
- Conditions
- Loops
- Functions
- Algorithms

এসব ধারণা আগে থেকে জানা না থাকলেও সমস্যা নেই। আমাদের roadmap-এ এগুলো শুরু থেকে ব্যাখ্যা করা হবে।

## 3. Basic Computer Skills

Python শেখার আগে কিছু সাধারণ computer skills থাকা উপকারী।

### 3.1 Using a Computer

তোমার computer-এর সাধারণ কাজগুলো করতে পারা উচিত:

- Applications open এবং close করা
- Keyboard ও mouse ব্যবহার করা
- Text type করা
- Software install করা
- File ও folder তৈরি করা
- File copy, move, rename এবং delete করা

এগুলো programming-এর বিষয় নয়; তবে development environment ব্যবহার করার সময় কাজে লাগবে।

### 3.2 Understanding Files and Folders

Python code সাধারণত `.py` extension-যুক্ত file-এ লেখা হয়।

উদাহরণ:

```text
python-learning/
├── hello.py
├── calculator.py
└── practice/
    └── variables.py
```

এখানে:

- `python-learning/` হলো project folder।
- `hello.py` একটি Python source file।
- `calculator.py` আরেকটি Python source file।
- `practice/` হলো একটি subfolder।
- `variables.py` subfolder-এর ভেতরে রাখা হয়েছে।

File এবং folder-এর পার্থক্য বোঝা গুরুত্বপূর্ণ, কারণ বড় project-এ অনেকগুলো file organize করতে হবে।

### 3.3 File Extensions

File extension দেখে সাধারণত file-এর ধরন বোঝা যায়।

| Extension | Common Use |
|---|---|
| `.py` | Python source code |
| `.md` | Markdown documentation |
| `.txt` | Plain text |
| `.csv` | Tabular data |
| `.json` | Structured data |
| `.pdf` | Document |
| `.xlsx` | Excel spreadsheet |

Python শেখার সময় সবচেয়ে বেশি ব্যবহার হবে `.py` এবং `.md` file।

---

## 4. Basic Mathematics

Python শুরু করার জন্য advanced mathematics জানা বাধ্যতামূলক নয়।

তবে নিচের basic mathematical concepts জানা থাকলে সুবিধা হবে:

- Addition, subtraction, multiplication and division
- Positive and negative numbers
- Fractions and decimals
- Percentages
- Comparison of numbers
- Basic algebra
- Simple equations

উদাহরণ:

\[
x = 10 + 5
\]

Python-এ:

```python
x = 10 + 5
print(x)
```

Output:

```text
15
```

এখানে `10 + 5` একটি arithmetic expression এবং তার result `x` variable-এ রাখা হয়েছে।

### Is Advanced Mathematics Required?

না। Python fundamentals, file handling, automation বা সাধারণ software development শুরু করার জন্য calculus, linear algebra কিংবা advanced statistics আগে থেকে জানা প্রয়োজন নেই।

তবে কিছু specialized field-এর জন্য অতিরিক্ত mathematics লাগতে পারে:

| Field | Useful Mathematical Knowledge |
|---|---|
| Basic Python | Arithmetic and logical reasoning |
| Algorithms | Logic, discrete mathematics and complexity |
| Data Analysis | Statistics and basic probability |
| Machine Learning | Linear algebra, probability, statistics and calculus |
| Scientific Computing | Linear algebra, numerical methods and calculus |
| Computer Graphics | Geometry, vectors and matrices |

এসব বিষয় প্রয়োজন অনুযায়ী সংশ্লিষ্ট chapter বা specialization-এ শেখা যাবে।

---

## 5. Basic English Reading Skills

Python-এর syntax এবং অধিকাংশ programming documentation ইংরেজিতে লেখা হয়।

তাই সাধারণ ইংরেজি শব্দ পড়তে পারলে শেখা সহজ হবে। তবে advanced English জানা বাধ্যতামূলক নয়।

কিছু গুরুত্বপূর্ণ শব্দ:

| English Term | বাংলা অর্থ |
|---|---|
| Variable | পরিবর্তনশীল মান সংরক্ষণের নাম |
| Value | কোনো data বা expression-এর মান |
| Condition | শর্ত |
| Loop | পুনরাবৃত্তির ব্যবস্থা |
| Function | নির্দিষ্ট কাজের জন্য reusable code block |
| Input | program-এ দেওয়া data |
| Output | program থেকে পাওয়া ফলাফল |
| Error | কোনো সমস্যা বা ত্রুটি |
| Return | function থেকে result ফেরত দেওয়া |
| Import | module বা package-এর functionality ব্যবহার করার ব্যবস্থা |

এই repository-তে মূল explanation বাংলায় থাকবে। ফলে English technical terms-এর সঙ্গে পরিচিত হওয়া ধীরে ধীরে সহজ হবে।

---

## 6. Logical Thinking

Programming-এর একটি গুরুত্বপূর্ণ অংশ হলো logical thinking।

Logical thinking বলতে কোনো problem বিশ্লেষণ করে ধাপে ধাপে solution বের করার দক্ষতাকে বোঝায়।

উদাহরণ: দুটি সংখ্যার মধ্যে বড় সংখ্যা খুঁজে বের করা।

Problem-solving steps:

1. দুটি সংখ্যা input হিসেবে নাও।
2. সংখ্যা দুটি compare করো।
3. প্রথম সংখ্যা বড় হলে সেটি দেখাও।
4. দ্বিতীয় সংখ্যা বড় হলে সেটি দেখাও।
5. দুটি সমান হলে equality দেখাও।

Python-এ:

```python
a = 15
b = 20

if a > b:
    print("a is greater")
elif b > a:
    print("b is greater")
else:
    print("Both are equal")
```

Output:

```text
b is greater
```

এখানে মূল বিষয় Python syntax মুখস্থ করা নয়; বরং problem-টিকে ছোট ছোট logical steps-এ ভাগ করা।

Logical thinking শুরু থেকেই practice-এর মাধ্যমে উন্নত করা যায়। আগে থেকে expert হওয়ার প্রয়োজন নেই।

---

## 7. Required Hardware

Python শেখার জন্য সাধারণ computer বা laptop যথেষ্ট।

### Recommended Setup

- একটি computer বা laptop
- Keyboard এবং mouse বা touchpad
- Software install করার অনুমতি
- পর্যাপ্ত storage space
- Internet connection, বিশেষ করে software installation ও documentation ব্যবহারের জন্য

Python-এর basic programming, problem-solving এবং অধিকাংশ beginner project-এর জন্য high-end computer দরকার হয় না।

### What About RAM and Processor?

সাধারণ Python programming-এর জন্য modest hardware-ও যথেষ্ট হতে পারে। তবে Data Science, Machine Learning, বড় dataset অথবা computationally intensive project-এর ক্ষেত্রে বেশি RAM এবং processing power প্রয়োজন হতে পারে।

---

## 8. Required Software

Python শেখার সময় কয়েকটি software ব্যবহার করা হবে।

### 8.1 Python Interpreter

Python interpreter Python code execute করে।

Python install করার পর terminal থেকে সাধারণত নিচের command ব্যবহার করে version পরীক্ষা করা যায়:

```bash
python --version
```

কিছু system-এ command হতে পারে:

```bash
python3 --version
```

Windows-এ Python Launcher থাকলে এটিও ব্যবহার করা যায়:

```bash
py --version
```

কোন command কাজ করবে তা installation এবং operating system-এর configuration-এর ওপর নির্ভর করে।

### 8.2 Code Editor

Python code লেখার জন্য একটি code editor ব্যবহার করা হবে।

উদাহরণ:

- Visual Studio Code
- PyCharm
- IDLE

এই repository-তে code example চালানো ও project organize করার জন্য Visual Studio Code ব্যবহার করা যেতে পারে।

### 8.3 Terminal or Command Line

Terminal দিয়ে Python script চালানো, package install করা এবং project-related command execute করা যায়।

উদাহরণ:

```bash
python hello.py
```

এই command বর্তমান directory-তে থাকা `hello.py` file execute করার চেষ্টা করবে।

Terminal-এর সব command আগে থেকে জানা বাধ্যতামূলক নয়। প্রয়োজন অনুযায়ী শেখা হবে।

---

## 9. Internet and Documentation Access

Internet connection থাকলে Python শেখা অনেক সহজ হয়।

এটি কাজে লাগবে:

- Python install করতে
- Official documentation পড়তে
- Third-party packages install করতে
- Error messages সম্পর্কে তথ্য খুঁজতে
- Tutorial এবং coding exercises অনুসরণ করতে
- GitHub-এ project সংরক্ষণ করতে

Python-এর official documentation:

https://docs.python.org/3/

Python-এর official documentation-এ language reference, tutorial, standard library এবং অন্যান্য গুরুত্বপূর্ণ resource পাওয়া যায়।

Internet সব সময় না থাকলেও offline-এ code লেখা ও অনেক Python program run করা সম্ভব, যদি প্রয়োজনীয় software এবং package আগে থেকে install করা থাকে।

---

## 10. Skills That Are Not Required at the Beginning

Python শেখা শুরু করার আগে নিচের বিষয়গুলো জানা বাধ্যতামূলক নয়।

| Topic | Must Know Before Starting? |
|---|---|
| C or C++ | No |
| Java | No |
| HTML and CSS | No |
| JavaScript | No |
| SQL | No |
| Data Structures and Algorithms | No |
| Object-Oriented Programming | No |
| Linux commands | No |
| Git and GitHub | No |
| Advanced Mathematics | No |
| Machine Learning | No |

এসব বিষয়ের কিছু পরে শেখা হবে। অন্য কিছু specialized development বা career goal অনুযায়ী প্রয়োজন হতে পারে।

---

## 11. Prerequisites for Specialized Fields

Python fundamentals শেখার পরে আলাদা ক্ষেত্র বেছে নেওয়ার সময় কিছু অতিরিক্ত prerequisite কাজে লাগবে।

| Specialization | Useful Prerequisites |
|---|---|
| Web Development | HTML, CSS, HTTP and SQL basics |
| Data Analysis | Basic statistics and spreadsheet concepts |
| Machine Learning | Statistics, probability and linear algebra |
| Scientific Computing | Mathematics and numerical methods |
| Automation | File systems, command-line basics and task logic |
| Networking | Basic networking concepts |
| Backend Development | Databases, HTTP, APIs and software design |

এগুলো Python শুরু করার শর্ত নয়। সংশ্লিষ্ট specialization শেখার সময় প্রয়োজন অনুযায়ী শেখা যাবে।

---

## 12. Beginner Readiness Checklist

Python শেখা শুরু করার আগে নিজের প্রস্তুতি যাচাই করতে পারো।

- [ ] Computer-এ file ও folder তৈরি করতে পারি।
- [ ] Software install করতে পারি বা installation guide অনুসরণ করতে পারি।
- [ ] Text editor ব্যবহার করতে পারি।
- [ ] Basic arithmetic করতে পারি।
- [ ] সাধারণ English technical terms পড়ার চেষ্টা করতে পারি।
- [ ] নতুন কিছু শেখার জন্য নিয়মিত সময় দিতে পারি।
- [ ] Code লিখে ভুল হলে আবার চেষ্টা করতে প্রস্তুত।
- [ ] শুধু notes পড়ে নয়, নিজে code লিখে practice করতে রাজি।

সবগুলো checklist পূরণ না হলেও Python শেখা শুরু করতে পারো। এগুলো readiness যাচাই করার জন্য, বাধ্যতামূলক admission criteria নয়।

---

## 13. What If You Are a Complete Beginner?

যদি তুমি আগে কখনো programming না করে থাকো, তাহলে নিচের পদ্ধতি অনুসরণ করো:

1. প্রথমে Python কী এবং programming কী—তা বোঝো।
2. Python ও code editor install করো।
3. একটি simple `Hello, World!` program run করো।
4. Variables, data types এবং operators শেখো।
5. Input, conditions এবং loops practice করো।
6. ছোট ছোট problem solve করো।
7. ধীরে ধীরে functions এবং data structures শেখো।

প্রথম দিনেই সবকিছু বুঝতে হবে না। প্রতিটি concept শেখার জন্য সময় নেওয়া স্বাভাবিক।

---

## 14. Final Recommendations

Python শেখা শুরু করার জন্য সবচেয়ে গুরুত্বপূর্ণ prerequisite হলো শেখার আগ্রহ, ধৈর্য এবং practice করার মানসিকতা।

Advanced mathematics, আগে থেকে programming knowledge কিংবা expensive hardware না থাকলেও Python fundamentals শেখা সম্ভব।

প্রথমে computer setup ঠিক করো, তারপর roadmap অনুসারে একে একে topic শেখো। কোনো বিষয় বুঝতে অসুবিধা হলে আগের explanation পড়ো এবং code নিজে run করে দেখো।

**Remember:** You do not need to know everything before starting Python. You can learn the required skills step by step.

---

## Next Step

পরবর্তী ফাইল: [05. Learning Methodology](05_Learning_Methodology.md)

সেখানে কীভাবে পড়লে programming ভালোভাবে শেখা যায়, theory ও practice-এর মধ্যে কীভাবে balance রাখতে হয়, কীভাবে ভুল থেকে শিখতে হয় এবং কীভাবে দীর্ঘমেয়াদে শেখা বিষয় মনে রাখতে হয়—এসব আলোচনা করা হবে।
