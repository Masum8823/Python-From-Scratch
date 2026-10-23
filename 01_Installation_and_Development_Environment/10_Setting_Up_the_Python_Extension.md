# 10. Setting Up the Python Extension

## 1. Introduction

VS Code একটি code editor। কিন্তু Python programming-এর জন্য এর সুবিধাগুলো ভালোভাবে ব্যবহার করতে হলে আমাদের Python Extension install ও configure করতে হয়।

**Python Extension** হলো VS Code-এর একটি extension, যা Python code লেখা, run, debug এবং manage করতে সাহায্য করে।

এটি তৈরি করেছে Microsoft।

Official Extension:

https://marketplace.visualstudio.com/items?itemName=ms-python.python

এই topic-এ আমরা শিখব:

- Extension কী এবং কেন দরকার।
- Python Extension কীভাবে install করতে হয়।
- Extension-এর গুরুত্বপূর্ণ features।
- Python Interpreter-এর সঙ্গে extension কীভাবে কাজ করে।
- Code completion, linting এবং debugging-এর প্রাথমিক ধারণা।
- Extension-সংক্রান্ত সাধারণ সমস্যার সমাধান।

---

## 2. What Is a VS Code Extension?

**Extension** হলো VS Code-এ অতিরিক্ত functionality যোগ করার একটি software component।

VS Code-এর মূল editor দিয়ে code লেখা যায়। কিন্তু বিভিন্ন programming language-এর জন্য বিশেষ সুবিধা যোগ করতে extensions ব্যবহার করা হয়।

উদাহরণ:

| Extension | Main Purpose |
|---|---|
| Python | Python development-এর জন্য প্রধান সুবিধাগুলো |
| Pylance | Python code intelligence ও type information |
| Jupyter | Jupyter Notebook ব্যবহারের সুবিধা |
| Prettier | বিভিন্ন supported language-এর code formatting |
| Git-related extensions | Git workflow-তে অতিরিক্ত সুবিধা |

সব extension install করা বাধ্যতামূলক নয়। Python শেখার শুরুতে প্রয়োজনীয় extension দিয়ে শুরু করাই ভালো।

---

## 3. Why Do We Need the Python Extension?

Python Extension ছাড়াও একটি সাধারণ text editor-এ Python code লেখা সম্ভব। কিন্তু VS Code-এর সঙ্গে Python Extension ব্যবহার করলে coding experience আরও উন্নত হয়।

প্রধান সুবিধাগুলো হলো:

1. Python file সহজে শনাক্ত করা।
2. Python interpreter নির্বাচন করতে সাহায্য করা।
3. Code completion পাওয়া।
4. Syntax ও সম্ভাব্য coding problem সম্পর্কে information পাওয়া।
5. Python program run করার সুবিধা।
6. Debugging tools ব্যবহার করা।
7. Testing ও environment-related workflow-তে সহায়তা করা।

মনে রাখবে, সব feature extension install করলেই প্রতিটি project-এ স্বয়ংক্রিয়ভাবে একইভাবে কাজ করবে না। কিছু feature-এর জন্য সঠিক interpreter, configuration অথবা অতিরিক্ত tool প্রয়োজন হতে পারে।

---

## 4. Installing the Python Extension

### Step 1: Open VS Code

প্রথমে VS Code চালু করো।

### Step 2: Open Extensions

VS Code-এর বাম পাশের Activity Bar থেকে Extensions icon নির্বাচন করো।

অথবা keyboard shortcut ব্যবহার করো:

- Windows/Linux: `Ctrl + Shift + X`
- macOS: `Cmd + Shift + X`

### Step 3: Search for Python

Extensions search box-এ লিখো:

```text
Python
```

### Step 4: Select the Correct Extension

Microsoft-এর তৈরি **Python** extension নির্বাচন করো।

Extension-এর publisher এবং নাম যাচাই করে নেবে, যাতে ভুল extension install না করো।

### Step 5: Install

`Install` button-এ click করো।

Installation সম্পন্ন হলে extension সাধারণত ব্যবহারের জন্য প্রস্তুত হয়ে যায়।

Official documentation:

https://code.visualstudio.com/docs/languages/python

---

## 5. Python Extension vs Python Interpreter

এটি অত্যন্ত গুরুত্বপূর্ণ একটি পার্থক্য।

**Python Extension এবং Python Interpreter এক জিনিস নয়।**

| Python Extension | Python Interpreter |
|---|---|
| VS Code-এর functionality বাড়ায় | Python code execute করে |
| Code completion ও debugging-এ সাহায্য করে | Program চালায় |
| VS Code-এর মধ্যে install হয় | Operating system বা environment-এ install থাকে |
| Code লেখা ও development workflow উন্নত করে | Python instructions execute করে |

উদাহরণ:

```python
print("Hello, Python!")
```

এই code execute করার জন্য Python interpreter দরকার।

Python Extension editor-এ code লেখা ও run করার workflow সহজ করে, কিন্তু এটি নিজে Python interpreter-এর বিকল্প নয়।

**মনে রাখার কৌশল:**

- Extension = Coding assistant ও editor integration
- Interpreter = Python code execution engine

---

## 6. Selecting the Python Interpreter

একটি computer-এ একাধিক Python installation থাকতে পারে। আবার প্রতিটি project-এর জন্য আলাদা virtual environment-ও থাকতে পারে।

তাই VS Code-এ সঠিক interpreter নির্বাচন করা গুরুত্বপূর্ণ।

### Step 1: Open the Command Palette

Windows/Linux:

```text
Ctrl + Shift + P
```

macOS:

```text
Cmd + Shift + P
```

### Step 2: Search for the Command

লিখো:

```text
Python: Select Interpreter
```

### Step 3: Select an Interpreter

VS Code যে interpreter-গুলো খুঁজে পায়, সেগুলোর তালিকা দেখাতে পারে।

যেমন:

```text
Python 3.x
Python 3.x (.venv)
```

এগুলো শুধু উদাহরণ। তোমার computer-এ version ও path আলাদা হতে পারে।

Project-এর জন্য সঠিক interpreter নির্বাচন করো।

### Step 4: Verify the Interpreter

Project-এর মধ্যে একটি Python file তৈরি করে নিচের code চালাও:

```python
import sys

print("Python Version:", sys.version)
print("Interpreter Path:", sys.executable)
```

`sys.executable` বর্তমান program চালানোর জন্য ব্যবহৃত interpreter-এর path দেখায়।

### Why Is Interpreter Selection Important?

ধরা যাক, তোমার computer-এ দুটি Python environment আছে:

```text
Python Environment A
Python Environment B
```

একটি environment-এ `requests` package install করা আছে, কিন্তু অন্যটিতে নেই।

VS Code যদি দ্বিতীয় environment ব্যবহার করে, তাহলে প্রথম environment-এ package install থাকা সত্ত্বেও import error হতে পারে।

এ কারণে project অনুযায়ী সঠিক interpreter নির্বাচন করা দরকার।

---

## 7. Understanding IntelliSense

**IntelliSense** হলো VS Code-এর code intelligence feature, যা coding করার সময় suggestion, completion এবং information দিতে পারে।

Python development-এ এটি variable, function, class, module ও তাদের members সম্পর্কে suggestion দিতে সাহায্য করে।

উদাহরণ:

```python
message = "Hello Python"

message.
```

Dot (`.`) দেওয়ার পর editor string-এর বিভিন্ন method-এর suggestion দেখাতে পারে।

যেমন:

```python
message.upper()
message.lower()
message.title()
```

এগুলো Python-এর string method।

IntelliSense-এর suggestion গ্রহণ করলে code লেখার সময় কমতে পারে এবং available method সম্পর্কে ধারণা পাওয়া যায়।

### Important Note

Suggestion সব সময় সঠিক code তৈরি করে দেবে—এমন নয়। Suggestion গ্রহণ করার আগে সেটি কী করছে তা বোঝার চেষ্টা করবে।

---

## 8. Understanding Pylance

**Pylance** হলো VS Code-এর জন্য একটি Python language-support extension, যা code intelligence, type information এবং বিভিন্ন সম্ভাব্য problem শনাক্ত করতে সাহায্য করে।

এটি Python Extension-এর সঙ্গে সাধারণত ব্যবহৃত হয়।

Pylance-এর সুবিধার মধ্যে রয়েছে:

- Intelligent code completion
- Function ও variable-এর information
- Type information
- Code navigation
- সম্ভাব্য coding problem-এর diagnostics

Pylance install না থাকলে VS Code-এর configuration অনুযায়ী এটি install করার recommendation দেখা যেতে পারে।

### Example

```python
def add(a: int, b: int) -> int:
    return a + b
```

এই function-এর ক্ষেত্রে Pylance `a`, `b` এবং return value-এর type information দেখাতে পারে।

এখানে:

- `a: int` — `a`-এর intended type integer।
- `b: int` — `b`-এর intended type integer।
- `-> int` — function-এর intended return type integer।

Python-এর type hints সম্পর্কে বিস্তারিত পরে শেখা হবে।

---

## 9. Running Python Code with the Extension

Python Extension install করার পরে VS Code থেকে Python file run করার সুবিধা ব্যবহার করা যায়।

ধরা যাক, project-এ `main.py` আছে।

```python
name = "Masum"

print("Hello,", name)
```

### Method 1: Run Python File

1. `main.py` open করো।
2. সঠিক Python interpreter নির্বাচন করো।
3. Editor-এর `Run Python File` option ব্যবহার করো।
4. Output Terminal-এ দেখো।

Expected output:

```text
Hello, Masum
```

### Method 2: Use the Terminal

VS Code-এর Terminal খোলো।

Windows:

```powershell
python main.py
```

macOS/Linux:

```bash
python3 main.py
```

তোমার system-এ `python` বা `python3`—কোন command কাজ করে, তা installation-এর ওপর নির্ভর করে।

Terminal থেকে command চালানো শেখা গুরুত্বপূর্ণ, কারণ এটি VS Code-এর বাইরেও Python program run করতে সাহায্য করে।

---

## 10. Understanding Syntax Highlighting

**Syntax Highlighting** হলো code-এর বিভিন্ন অংশকে আলাদা visual style-এ দেখানোর সুবিধা।

উদাহরণ:

```python
def greet(name):
    message = "Hello, " + name
    print(message)

greet("Python")
```

Editor-এ function name, string, keyword এবং variable আলাদাভাবে highlight হতে পারে।

এতে code পড়তে সুবিধা হয়।

তবে syntax highlighting কোনো program সঠিকভাবে কাজ করবে কি না, তা নিশ্চিত করে না। Code দেখতে সুন্দর হলেও logical error থাকতে পারে।

---

## 11. Understanding Linting and Diagnostics

Code লেখার সময় সম্ভাব্য problem শনাক্ত করার প্রক্রিয়াকে সাধারণভাবে **Linting** বলা হয়।

কিছু diagnostics editor-এ সরাসরি দেখা যায়, আবার কিছু diagnostics-এর জন্য নির্দিষ্ট tool ও configuration প্রয়োজন হয়।

উদাহরণ:

```python
print("Hello Python"
```

এখানে closing parenthesis নেই।

Python syntax অনুযায়ী code-টি সঠিক নয়। Editor বা language tool সমস্যাটি highlight করতে পারে।

আরেকটি উদাহরণ:

```python
total = 10
print(totle)
```

এখানে `totle` এবং `total` আলাদা নাম। Code-এ `totle` নামে কোনো variable define করা হয়নি, তাই program চালালে `NameError` হতে পারে।

Editor এই ধরনের কিছু সমস্যা শনাক্ত করতে সাহায্য করতে পারে, তবে সব error আগেই শনাক্ত করতে পারে না।

**মনে রাখবে:** Diagnostics হলো সাহায্যকারী signal; final verification-এর জন্য code run ও test করতে হয়।

---

## 12. Debugging Support

Debugging হলো program-এর error বা unexpected behavior খুঁজে বের করার প্রক্রিয়া।

Python Extension ও VS Code-এর debugging support ব্যবহার করে program-এর execution step-by-step পরীক্ষা করা যায়।

উদাহরণ:

```python
x = 10
y = 5

result = x + y

print(result)
```

Debugging করার সময় তুমি পরীক্ষা করতে পারবে:

- কোন line execute হচ্ছে।
- Variable-এর বর্তমান value কী।
- Program-এর execution কোথায় পৌঁছেছে।
- কোন line-এর পরে unexpected behavior হচ্ছে।

### Breakpoint

Breakpoint হলো code-এর নির্দিষ্ট একটি line-এ execution থামানোর নির্দেশ।

Editor-এর line number-এর পাশে click করে breakpoint set করা যায়।

এরপর Run and Debug workflow দিয়ে program debug করা যায়।

Debugging-এর পূর্ণাঙ্গ আলোচনা পরবর্তী relevant topic-এ করা হবে।

---

## 13. Working with Multiple Python Environments

একই computer-এ বিভিন্ন project-এর জন্য আলাদা Python environment ব্যবহার করা যায়।

উদাহরণ:

```text
Project_A/
├── .venv/
└── main.py

Project_B/
├── .venv/
└── main.py
```

এখানে দুটি project-এর `.venv` আলাদা হতে পারে।

Project A-এর interpreter নির্বাচন করলে Project B-এর interpreter automatically একই হবে—এমন নয়।

### Recommended Workflow

1. Project folder open করো।
2. Project-এর virtual environment তৈরি করো।
3. `Python: Select Interpreter` ব্যবহার করো।
4. Project-specific package install করো।
5. `sys.executable` দিয়ে interpreter যাচাই করো।

Virtual environment তৈরি ও manage করার বিস্তারিত আমরা এই chapter-এর পরবর্তী topic-গুলোতে শিখব।

---

## 14. Common Problems and Solutions

### Problem 1: Python Extension Is Not Working

সম্ভাব্য কারণ:

- Extension install হয়নি।
- Extension disabled রয়েছে।
- VS Code-এর extension host-এ সমস্যা হয়েছে।
- VS Code বা extension update প্রয়োজন।

সমাধান:

1. Extensions view খুলে Python extension-এর status পরীক্ষা করো।
2. প্রয়োজনে extension enable করো।
3. VS Code reload করো।
4. Official documentation-এর troubleshooting নির্দেশনা অনুসরণ করো।

### Problem 2: No Python Interpreter Found

সম্ভাব্য কারণ:

- Python install করা নেই।
- Python executable খুঁজে পাওয়া যাচ্ছে না।
- Interpreter discovery ব্যর্থ হয়েছে।
- Virtual environment মুছে গেছে বা স্থান পরিবর্তন হয়েছে।

সমাধান:

1. Terminal-এ Python version পরীক্ষা করো।
2. Python installation path যাচাই করো।
3. `Python: Select Interpreter` চালাও।
4. প্রয়োজন হলে সঠিক environment তৈরি বা নির্বাচন করো।

Windows:

```powershell
py --version
```

macOS/Linux:

```bash
python3 --version
```

### Problem 3: Import Error

উদাহরণ:

```text
ModuleNotFoundError: No module named 'requests'
```

এর অর্থ বর্তমান interpreter যে module খুঁজছে, সেটি সেখানে পাওয়া যাচ্ছে না।

সমাধান:

1. সঠিক interpreter নির্বাচন করো।
2. Virtual environment সক্রিয় আছে কি না যাচাই করো।
3. প্রয়োজনীয় package install করো।

```bash
python -m pip install requests
```

macOS/Linux-এ প্রয়োজনে:

```bash
python3 -m pip install requests
```

এখানে package-টি যে interpreter ব্যবহার করবে, তার সঙ্গেই install করা গুরুত্বপূর্ণ।

### Problem 4: Code Completion Is Not Working

সম্ভাব্য কারণ:

- Python Extension বা Pylance সক্রিয় নেই।
- Interpreter নির্বাচন করা হয়নি।
- Language server চালু হতে সমস্যা হচ্ছে।
- Project-এর configuration বা indexing সম্পন্ন হয়নি।

সমাধান:

1. Python file open করো।
2. সঠিক interpreter নির্বাচন করো।
3. Python ও Pylance extension-এর status পরীক্ষা করো।
4. VS Code reload করে আবার চেষ্টা করো।

### Problem 5: Run Button Does Not Work

সমাধান:

1. File-টি `.py` extension দিয়ে save করো।
2. Python Extension install আছে কি না দেখো।
3. সঠিক interpreter নির্বাচন করো।
4. Integrated Terminal থেকে সরাসরি program run করে পরীক্ষা করো।

---

## 15. Recommended Extension Setup

শুরুতে নিচের configuration যথেষ্ট।

| Component | Purpose | Required at the Start? |
|---|---|---|
| VS Code | Code editor | Yes |
| Python | Python development integration | Recommended |
| Python Interpreter | Code execution | Yes |
| Pylance | Code intelligence | Recommended |
| Jupyter | Notebook-based development | Later, when needed |
| Formatter | Consistent code formatting | Can be configured later |

সব extension একসঙ্গে install করার দরকার নেই। প্রথমে Python Extension এবং সঠিক interpreter দিয়ে শুরু করো।

---

## 16. Best Practices

1. Extension install করার সময় publisher যাচাই করো।
2. Project অনুযায়ী সঠিক Python interpreter নির্বাচন করো।
3. Code suggestion অন্ধভাবে গ্রহণ কোরো না।
4. Error highlight দেখলে message পড়ে বোঝার চেষ্টা করো।
5. Code run করার পাশাপাশি output যাচাই করো।
6. Package install করার আগে active environment পরীক্ষা করো।
7. প্রয়োজন ছাড়া অজানা extension install কোরো না।
8. Extension সমস্যা হলে Python installation এবং editor configuration আলাদাভাবে পরীক্ষা করো।
9. VS Code-এর বাইরেও Terminal থেকে Python command চালানো শেখো।

---

## 17. Practice Tasks

### Task 1: Install Python Extension

VS Code-এর Extensions view থেকে Microsoft-এর Python extension install করো।

### Task 2: Select the Interpreter

Command Palette থেকে `Python: Select Interpreter` চালিয়ে সঠিক interpreter নির্বাচন করো।

### Task 3: Check Python Information

`main.py` file-এ লিখো:

```python
import sys

print("Python Version:", sys.version)
print("Executable:", sys.executable)
```

Program run করে output দেখো।

### Task 4: Practice IntelliSense

```python
text = "python programming"

print(text.upper())
print(text.lower())
print(text.title())
```

Code লেখার সময় editor-এর suggestion ব্যবহার করে দেখো।

### Task 5: Identify a Syntax Error

নিচের code-এ কী সমস্যা আছে, খুঁজে বের করো:

```python
name = "Masum"
print("Hello", name
```

তারপর code ঠিক করে run করো।

### Task 6: Understand an Import Error

```python
import requests

print(requests.__version__)
```

যদি `requests` install করা না থাকে, তাহলে error হতে পারে।

Error message পড়ে বুঝে নাও কী অনুপস্থিত। তারপর সঠিক interpreter-এর environment-এ package install করে আবার run করো।

---

## 18. Quick Revision

| Term | Meaning |
|---|---|
| Extension | VS Code-এ অতিরিক্ত functionality যোগ করে |
| Python Extension | Python development workflow-তে সাহায্য করে |
| Interpreter | Python code execute করে |
| IntelliSense | Code suggestion ও completion দেয় |
| Pylance | Python code intelligence ও type information দেয় |
| Syntax Highlighting | Code-এর বিভিন্ন অংশ আলাদা করে দেখায় |
| Linting | সম্ভাব্য coding problem শনাক্ত করতে সাহায্য করে |
| Debugging | Program-এর execution পরীক্ষা করে error খুঁজতে সাহায্য করে |
| Interpreter Selection | কোন Python environment ব্যবহার হবে তা নির্ধারণ করে |
| Import Error | প্রয়োজনীয় module বর্তমান import configuration-এ পাওয়া যাচ্ছে না |

---

## 19. Chapter Connection

এই topic-এ আমরা VS Code-এর Python Extension install ও configure করা, interpreter নির্বাচন করা এবং coding assistance-এর গুরুত্বপূর্ণ সুবিধাগুলো শিখেছি।

পরবর্তী topic-এ আমরা আরও গভীরভাবে শিখব কীভাবে VS Code-এ সঠিক Python Interpreter নির্বাচন করতে হয় এবং একাধিক interpreter বা virtual environment-এর মধ্যে পার্থক্য বুঝতে হয়।

**Next Topic:** [11. Selecting the Python Interpreter](11_Selecting_the_Python_Interpreter.md)