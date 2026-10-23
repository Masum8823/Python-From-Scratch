# 14. Creating and Running Your First Python File

## 1. Introduction

Python শেখার প্রথম practical step হলো নিজের হাতে একটি Python program লেখা এবং সেটি run করা।

Python code সাধারণত `.py` extension-যুক্ত file-এ লেখা হয়। এই file-কে Python source file বলা হয়।

উদাহরণ:

```text
main.py
hello.py
practice.py
```

এই topic-এ আমরা শিখব:

- Python file কী এবং কেন `.py` extension ব্যবহার করা হয়।
- VS Code-এ Python file তৈরি করা।
- প্রথম Python program লেখা।
- Code save করা ও run করা।
- Terminal থেকে Python file চালানো।
- Output ও error বোঝা।
- Common mistakes সমাধান করা।

---

## 2. What Is a Python File?

একটি Python file হলো এমন একটি text file, যেখানে Python programming language-এর code লেখা থাকে।

উদাহরণ:

```python
print("Hello, World!")
```

এই code-টি `hello.py` নামে save করা যেতে পারে।

Python interpreter file-এর code পড়ে এবং তা execute করে।

### Understanding the File Extension

```text
hello.py
```

এখানে:

- `hello` হলো file name।
- `.py` হলো file extension।

`.py` extension দেখে বোঝা যায় যে এটি সাধারণত একটি Python source file।

অন্যদিকে:

- `.txt` — সাধারণ text file।
- `.md` — Markdown document।
- `.html` — HTML document।
- `.json` — JSON data file।

Python code-কে `.txt` file-এ লিখে রাখলেই সেটি স্বয়ংক্রিয়ভাবে সাধারণ Python source file হয়ে যায় না। Python program চালানোর সময় সঠিক file name ও extension ব্যবহার করা উচিত।

---

## 3. Creating Your First Python File in VS Code

আমরা আগের topic-এ তৈরি করা `first_python_project` folder ব্যবহার করব।

Project structure:

```text
first_python_project/
├── README.md
└── main.py
```

### Step 1: Open the Project Folder

VS Code চালু করে:

1. `File` menu-তে যাও।
2. `Open Folder` নির্বাচন করো।
3. `first_python_project` folder নির্বাচন করো।

VS Code-এর Explorer-এ project folder দেখা যাবে।

### Step 2: Create a Python File

Explorer থেকে `New File` নির্বাচন করো।

File name দাও:

```text
main.py
```

### Step 3: Write Your First Program

`main.py` file-এর মধ্যে লেখো:

```python
print("Hello, World!")
```

### Step 4: Save the File

Keyboard shortcut ব্যবহার করো:

- Windows/Linux: `Ctrl + S`
- macOS: `Cmd + S`

এখন তোমার প্রথম Python file তৈরি হয়েছে।

---

## 4. Understanding Your First Python Program

আমাদের code:

```python
print("Hello, World!")
```

এই code-টি অংশে ভাগ করে বুঝি।

### `print()`

`print()` হলো Python-এর একটি built-in function। এটি সাধারণত screen বা standard output-এ কোনো value প্রদর্শন করতে ব্যবহার করা হয়।

উদাহরণ:

```python
print("Hello")
print(100)
print(10 + 20)
```

Output:

```text
Hello
100
30
```

### Parentheses `()`

`print()`-এর parentheses-এর মধ্যে যে value বা expression দেওয়া হয়, সেটি function-এর argument হিসেবে কাজ করে।

উদাহরণ:

```python
print("Python")
```

এখানে `"Python"` হলো `print()` function-এর argument।

### Quotation Marks

Text বা string বোঝানোর জন্য quotation marks ব্যবহার করা হয়।

উদাহরণ:

```python
print("Hello")
print('Python')
```

Double quotes এবং single quotes—দুটিই string লেখার জন্য ব্যবহার করা যায়।

### Why Does the Code Work?

Python code-টি execute হলে:

1. Python `print()` function-টি শনাক্ত করে।
2. `"Hello, World!"` string-টি argument হিসেবে গ্রহণ করে।
3. String-টি output-এ প্রদর্শন করে।

Output:

```text
Hello, World!
```

---

## 5. Running a Python File in VS Code

Python file run করার কয়েকটি উপায় রয়েছে।

### Method 1: Run Button

1. `main.py` file open করো।
2. VS Code-এর উপরের ডানদিকে Python-এর Run button বা `Run Python File` option খুঁজে বের করো।
3. সেটিতে click করো।
4. নিচের Terminal panel-এ output দেখো।

Expected output:

```text
Hello, World!
```

এই পদ্ধতিতে VS Code সাধারণত selected Python interpreter ব্যবহার করে file চালায়।

### Method 2: Using the Terminal

VS Code-এ Terminal open করো।

Menu:

`Terminal > New Terminal`

এরপর নিশ্চিত হও যে Terminal-এর current working directory তোমার project folder।

Windows-এ:

```powershell
python main.py
```

যদি `python` command কাজ না করে, তাহলে চেষ্টা করতে পারো:

```powershell
py main.py
```

macOS/Linux-এ:

```bash
python3 main.py
```

কোন command কাজ করবে, তা তোমার system-এর Python installation-এর ওপর নির্ভর করে।

### Expected Output

```text
Hello, World!
```

Terminal-এ এই output দেখা গেলে program-টি সফলভাবে run হয়েছে।

---

## 6. Writing Multiple Statements

একটি Python file-এ একাধিক statement লেখা যায়।

উদাহরণ:

```python
print("My name is Masum.")
print("I am learning Python.")
print("This is my first Python program.")
```

Output:

```text
My name is Masum.
I am learning Python.
This is my first Python program.
```

সাধারণভাবে প্রতিটি `print()` statement আলাদা output line তৈরি করে।

### Statement কী?

Python interpreter যে instruction-গুলো execute করে, সেগুলোকে সাধারণভাবে statement বলা হয়।

উদাহরণ:

```python
print("Hello")
print("Welcome")
```

এখানে দুটি expression statement রয়েছে।

এই পর্যায়ে মনে রাখবে, Python file-এ একাধিক instruction ধারাবাহিকভাবে লেখা যায় এবং program সেগুলো execute করে।

---

## 7. Printing Different Types of Values

`print()` শুধু text নয়, বিভিন্ন ধরনের value-ও display করতে পারে।

### 7.1 Printing Text

```python
print("Learning Python")
```

Output:

```text
Learning Python
```

### 7.2 Printing Integers

```python
print(10)
print(500)
print(-25)
```

Output:

```text
10
500
-25
```

### 7.3 Printing Decimal Numbers

```python
print(3.14)
print(99.5)
```

Output:

```text
3.14
99.5
```

### 7.4 Printing Boolean Values

```python
print(True)
print(False)
```

Output:

```text
True
False
```

Python-এ `True` ও `False` হলো Boolean values। এগুলো লেখার সময় প্রথম অক্ষর capital হবে।

### 7.5 Printing Calculations

```python
print(10 + 20)
print(50 - 15)
print(6 * 7)
```

Output:

```text
30
35
42
```

এখানে Python calculation করে ফলাফল output-এ দেখায়।

---

## 8. Printing Multiple Values Together

একটি `print()` function ব্যবহার করেও একাধিক value প্রদর্শন করা যায়।

উদাহরণ:

```python
print("Age:", 22)
print("Score:", 95)
print("Total:", 50 + 40)
```

Output:

```text
Age: 22
Score: 95
Total: 90
```

`print()`-এর মধ্যে একাধিক argument দিলে Python সাধারণত সেগুলোর মাঝে একটি space দিয়ে output প্রদর্শন করে।

### Example

```python
print("Python", "is", "easy")
```

Output:

```text
Python is easy
```

এটি নিচের code-এর মতো একই ধরনের output দেয়:

```python
print("Python is easy")
```

তবে প্রথম উদাহরণে তিনটি আলাদা string argument ব্যবহার করা হয়েছে, আর দ্বিতীয় উদাহরণে একটি string ব্যবহার করা হয়েছে।

---

## 9. Understanding Comments

Comment হলো code-এর মধ্যে লেখা এমন text, যা Python সাধারণত program execute করার সময় instruction হিসেবে চালায় না।

Python-এ single-line comment লিখতে `#` ব্যবহার করা হয়।

উদাহরণ:

```python
# This is my first Python program

print("Hello, World!")
```

Output:

```text
Hello, World!
```

Comment output-এ প্রদর্শিত হয়নি।

### Why Do We Use Comments?

- Code-এর উদ্দেশ্য ব্যাখ্যা করতে।
- গুরুত্বপূর্ণ logic সম্পর্কে note রাখতে।
- অন্য developer-কে code বুঝতে সাহায্য করতে।
- Program-এর নির্দিষ্ট অংশ সম্পর্কে reminder রাখতে।

### Another Example

```python
# Display a welcome message
print("Welcome to Python")

# Display a number
print(100)
```

Comments code পড়তে সাহায্য করে, তবে সহজ code-এ অপ্রয়োজনীয় comment না লেখাই ভালো।

---

## 10. Understanding Case Sensitivity

Python case-sensitive language। অর্থাৎ, uppercase ও lowercase অক্ষরকে আলাদা হিসেবে বিবেচনা করা হয়।

উদাহরণ:

```python
print("Hello")
```

এটি সঠিক।

কিন্তু:

```python
Print("Hello")
```

এটি সাধারণভাবে `NameError` তৈরি করবে, কারণ built-in function-এর নাম `print`, `Print` নয়।

একইভাবে:

```python
PRINT("Hello")
```

এটিও সঠিক নয়।

তাই Python-এর built-in function ও keyword সঠিকভাবে লিখতে হবে।

---

## 11. Understanding Indentation

Python code-এ indentation গুরুত্বপূর্ণ। Indentation বলতে code-এর শুরুতে থাকা whitespace বোঝায়।

উদাহরণ:

```python
print("First line")
print("Second line")
```

এই code-এ দুটি statement একই level-এ রয়েছে।

কিন্তু নিচের code-টি দেখো:

```python
print("First line")
    print("Second line")
```

দ্বিতীয় লাইনের শুরুতে অপ্রয়োজনীয় indentation থাকায় Python সাধারণত `IndentationError` দেখাবে।

তবে সব indentation ভুল নয়। Conditional statement, loop ও function-এর মতো block-এর মধ্যে indentation প্রয়োজন হয়।

উদাহরণ:

```python
if True:
    print("This line is inside the if block")
```

এখানে indentation সঠিক এবং প্রয়োজনীয়।

**মনে রাখবে:** Indentation-এর বিস্তারিত আমরা conditional statement, loop ও function শেখার সময় শিখব।

---

## 12. Understanding Syntax Errors

Python-এর code লেখার সময় language-এর syntax বা লেখার নিয়ম ভঙ্গ হলে syntax error হতে পারে।

উদাহরণ:

```python
print("Hello"
```

এখানে closing parenthesis `)` অনুপস্থিত।

ফলে Python code-টি parse করতে গিয়ে syntax error দেখাবে।

সঠিক code:

```python
print("Hello")
```

### Another Example

ভুল:

```python
print("Hello)
```

সঠিক:

```python
print("Hello")
```

প্রথম উদাহরণে closing quotation mark অনুপস্থিত।

### Common Syntax Mistakes

- Parentheses বন্ধ না করা।
- Quotation marks বন্ধ না করা।
- ভুলভাবে keyword লেখা।
- অপ্রয়োজনীয় indentation ব্যবহার করা।
- ভুল punctuation ব্যবহার করা।

Error দেখলে পুরো program-কে ভুল মনে না করে error message-এর location ও কারণ বোঝার চেষ্টা করবে।

---

## 13. Understanding the Difference Between Code and Output

Code এবং output এক জিনিস নয়।

উদাহরণ:

```python
print(10 + 20)
```

এখানে:

- **Code:** `print(10 + 20)`
- **Output:** `30`

Python code-টি execute করে calculation-এর ফলাফল output-এ প্রদর্শন করেছে।

আরেকটি উদাহরণ:

```python
print("10 + 20")
```

Output:

```text
10 + 20
```

এখানে quotation marks-এর মধ্যে expression-টি text হিসেবে লেখা হয়েছে। তাই Python যোগ করেনি।

কিন্তু:

```python
print(10 + 20)
```

Output:

```text
30
```

এখানে quotation marks নেই, তাই Python `10 + 20` expression-টি evaluate করেছে।

এই পার্থক্যটি ভালোভাবে বুঝে রাখবে। Python শেখার শুরুতে এটি খুব গুরুত্বপূর্ণ।

---

## 14. Understanding the Execution Flow

একটি Python file run করলে সাধারণভাবে নিচের ধাপগুলো ঘটে:

1. তুমি `.py` file-এ code লেখো।
2. File save করো।
3. Python interpreter দিয়ে file execute করো।
4. Python code পড়ে এবং execute করার চেষ্টা করে।
5. Program-এর output Terminal-এ প্রদর্শিত হয়, অথবা error হলে error message দেখা যায়।

উদাহরণ:

```python
print("Start")
print(10 + 5)
print("End")
```

Output:

```text
Start
15
End
```

সাধারণভাবে এই statement-গুলো ওপর থেকে নিচে execute হয়েছে।

পরবর্তীতে conditional statement, loop, function ও exception handling শেখার পর বুঝবে যে সব code সব সময় সরলভাবে ওপর থেকে নিচে execute হয় না।

---

## 15. Common Problems and Solutions

| Problem | Possible Solution |
|---|---|
| `python` command কাজ করছে না | Python installation ও PATH যাচাই করো; Windows-এ `py` চেষ্টা করো |
| `python3` command কাজ করছে না | Python 3 installation ও command configuration যাচাই করো |
| `can't open file` | File name ও current directory যাচাই করো |
| `SyntaxError` | Code-এর syntax, quotation marks ও parentheses পরীক্ষা করো |
| `IndentationError` | অপ্রয়োজনীয় indentation ঠিক করো |
| Output দেখা যাচ্ছে না | File save করেছ কি না এবং program run হয়েছে কি না যাচাই করো |
| ভুল file run হচ্ছে | Terminal-এর current directory ও file name যাচাই করো |
| VS Code-এ Run option নেই | Python extension ও selected interpreter পরীক্ষা করো |

### Useful Debugging Steps

সমস্যা হলে একে একে:

1. File save করো।
2. File name যাচাই করো।
3. Terminal-এর current directory পরীক্ষা করো।
4. Python version command দিয়ে যাচাই করো।
5. Error message-এর শেষ কয়েকটি line পড়ো।
6. Code-এর punctuation ও indentation পরীক্ষা করো।
7. ছোট অংশে code run করে সমস্যা খুঁজে বের করো।

Error message শুধু সমস্যা জানানোর জন্য নয়; এটি debugging শেখারও একটি গুরুত্বপূর্ণ উপায়।

---

## 16. Practical Exercises

### Exercise 1: Print a Welcome Message

`main.py`-তে লেখো:

```python
print("Welcome to Python Programming")
```

Output নিজে যাচাই করো।

### Exercise 2: Print Your Information

নিজের তথ্য ব্যবহার করে তিনটি আলাদা line display করো।

```python
print("Name: Your Name")
print("Department: CSE")
print("University: Your University")
```

`Your Name` ও অন্যান্য placeholder নিজের তথ্য দিয়ে পরিবর্তন করবে।

### Exercise 3: Print Numbers

```python
print(100)
print(200)
print(300)
```

Output কী হবে, আগে অনুমান করো; তারপর run করো।

### Exercise 4: Perform Calculations

```python
print(25 + 15)
print(100 - 40)
print(12 * 5)
print(100 / 4)
```

প্রতিটি expression-এর output নিজে বের করার চেষ্টা করো।

### Exercise 5: Understand Strings

নিচের code দুটির output তুলনা করো:

```python
print(5 + 10)
print("5 + 10")
```

কেন output আলাদা হয়, তা নিজের ভাষায় ব্যাখ্যা করো।

### Exercise 6: Use Comments

```python
# Display a greeting
print("Hello, Python!")

# Display a calculation
print(5 + 5)
```

Comment-সহ code run করে দেখো।

### Exercise 7: Fix the Error

নিচের code-এ কী ভুল রয়েছে?

```python
print("Hello, Python!"
print(10 + 20)
```

Code ঠিক করে আবার run করো।

### Exercise 8: Create a Small Program

এমন একটি Python file তৈরি করো, যেটি কমপক্ষে পাঁচটি `print()` statement ব্যবহার করে তোমার সম্পর্কে কিছু তথ্য প্রদর্শন করবে।

---

## 17. Best Practices

1. Python file-এর নামের শেষে `.py` ব্যবহার করো।
2. Code লেখার পরে file save করো।
3. File-এর নাম অর্থপূর্ণ রাখো, যেমন `main.py` বা `practice.py`।
4. Python-এর built-in function ও keyword সঠিকভাবে লেখো।
5. Error message পড়ে সমস্যা সমাধানের চেষ্টা করো।
6. ছোট program দিয়ে practice শুরু করো।
7. Code ও output-এর পার্থক্য বুঝে রাখো।
8. অপ্রয়োজনীয় indentation এড়িয়ে চলো।
9. একটি project-এর code তার নির্ধারিত project folder-এ রাখো।
10. Code শুধু copy না করে প্রতিটি line বুঝে run করো।

---

## 18. Quick Revision

| Term | Meaning |
|---|---|
| Python File | Python code-সহ source file |
| `.py` | Python source file-এর সাধারণ extension |
| `print()` | Output প্রদর্শনের built-in function |
| Argument | Function-কে দেওয়া input value |
| String | Text উপস্থাপনের data type |
| Comment | Code সম্পর্কে মানুষের জন্য লেখা note |
| Interpreter | Python code execute করার জন্য ব্যবহৃত software |
| Output | Program execute হওয়ার ফলে প্রদর্শিত ফলাফল |
| Syntax Error | Code-এর syntax বা লেখার নিয়মে ভুল |
| Indentation | Code-এর শুরুতে থাকা whitespace |
| Terminal | Command চালানো ও program execute করার interface |

---

## 19. Chapter Connection

এই topic-এ আমরা প্রথম Python file তৈরি করা, code লেখা, file save করা, program run করা এবং output বোঝা শিখেছি।

এখন তুমি VS Code ব্যবহার করে নিজের Python program লিখতে এবং execute করতে পারবে।

পরবর্তী topic-এ আমরা Python code চালানোর বিভিন্ন পদ্ধতি তুলনা করে শিখব—যেমন VS Code-এর Run button, Terminal, Python REPL এবং command-line execution।

**Next Topic:** [15. Running Python Code in Different Ways](15_Running_Python_Code_in_Different_Ways.md)