# 15. Running Python Code in Different Ways

## 1. Introduction

Python code লেখার পর সেটি execute করতে হয়, যাতে program-এর output পাওয়া যায়।

Python code চালানোর একাধিক পদ্ধতি রয়েছে। যেমন:

1. VS Code-এর Run Button ব্যবহার করে।
2. Terminal বা Command Line ব্যবহার করে।
3. Python REPL-এ সরাসরি code লিখে।
4. `python -c` command ব্যবহার করে।
5. অন্য Python file থেকে একটি Python module চালিয়ে।

প্রতিটি পদ্ধতির আলাদা ব্যবহার রয়েছে। ছোট code পরীক্ষা করার জন্য একটি পদ্ধতি সুবিধাজনক, আবার বড় project চালানোর জন্য অন্য পদ্ধতি বেশি কার্যকর।

এই topic-এর লক্ষ্য হলো প্রতিটি পদ্ধতি বোঝা এবং সঠিক পরিস্থিতিতে সঠিক পদ্ধতি ব্যবহার করতে শেখা।

---

## 2. Method 1: Running Python Code Using the VS Code Run Button

VS Code ব্যবহার করে Python program চালানোর এটি একটি সহজ পদ্ধতি।

### Step 1: Open a Python File

VS Code-এ তোমার project folder open করো।

এরপর `main.py` file তৈরি করো বা আগে তৈরি করা file open করো।

### Step 2: Write Python Code

```python
print("Hello, Python!")
print("I am learning Python.")
print(10 + 20)
```

### Step 3: Save the File

Windows/Linux-এ `Ctrl + S` এবং macOS-এ `Cmd + S` চাপো।

### Step 4: Run the Program

VS Code-এর উপরের ডানদিকে `Run Python File` button-এ click করো।

প্রয়োজন অনুযায়ী VS Code Python interpreter নির্বাচন করতে বলতে পারে।

### Expected Output

```text
Hello, Python!
I am learning Python.
30
```

Output সাধারণত VS Code-এর Terminal panel-এ দেখা যাবে।

### Advantages

- Beginner-দের জন্য সহজ।
- আলাদাভাবে command লিখতে হয় না।
- Code ও output একই application-এ দেখা যায়।
- ছোট ও মাঝারি program practice করার জন্য সুবিধাজনক।

### Limitations

- VS Code ও প্রয়োজনীয় Python extension configure করা থাকতে হয়।
- কোন interpreter ব্যবহার হচ্ছে, তা খেয়াল রাখা দরকার।
- Terminal-এর working directory ও project configuration না বুঝলে কিছু সমস্যা হতে পারে।

**কখন ব্যবহার করবে?**

শুরুতে Python শেখার সময় এবং প্রতিদিনের coding practice-এ এই পদ্ধতি ব্যবহার করতে পারো।

---

## 3. Method 2: Running Python Code Through the Terminal

Terminal ব্যবহার করে Python file চালানো একটি গুরুত্বপূর্ণ skill। বাস্তব project, automation, debugging এবং deployment-এর সময় এই পদ্ধতি অনেক কাজে লাগে।

### Step 1: Open the Terminal

VS Code-এ যাও:

`Terminal > New Terminal`

Terminal সাধারণত নিচের দিকে open হবে।

### Step 2: Check the Current Directory

Windows PowerShell-এ:

```powershell
Get-Location
```

macOS/Linux-এ:

```bash
pwd
```

এই command-গুলো Terminal-এর বর্তমান working directory দেখায়।

যদি তুমি `main.py`-এর project folder-এ থাকো, তাহলে সরাসরি file চালাতে পারবে।

### Step 3: Run the Python File

Windows-এ:

```powershell
python main.py
```

যদি `python` command কাজ না করে, তাহলে চেষ্টা করো:

```powershell
py main.py
```

macOS/Linux-এ:

```bash
python3 main.py
```

কোন command কাজ করবে, তা তোমার operating system এবং Python installation-এর configuration-এর ওপর নির্ভর করে।

### Step 4: Check the Output

ধরা যাক, `main.py`-তে রয়েছে:

```python
print("Running Python from Terminal")
print(25 + 25)
```

Output:

```text
Running Python from Terminal
50
```

### Why Is This Method Important?

Terminal থেকে code চালানোর মাধ্যমে তুমি শিখবে:

- Python executable ব্যবহার করা।
- File path বোঝা।
- Working directory পরিচালনা করা।
- Command-line arguments ব্যবহার করা।
- Error message দেখা।
- Project-এর বিভিন্ন script execute করা।

এই দক্ষতাগুলো পরবর্তীতে automation, web development, testing এবং deployment-এ কাজে লাগবে।

---

## 4. Method 3: Running Python Code Using the Python REPL

REPL হলো `Read-Eval-Print Loop`-এর সংক্ষিপ্ত রূপ।

এটি এমন একটি interactive environment, যেখানে তুমি একটি Python statement লিখে সঙ্গে সঙ্গে তার ফলাফল দেখতে পারো।

REPL-এর চারটি ধাপ:

| Step | Meaning |
|---|---|
| Read | তোমার লেখা code পড়ে |
| Eval | Code evaluate বা execute করে |
| Print | ফলাফল প্রদর্শন করে |
| Loop | পরবর্তী input-এর জন্য অপেক্ষা করে |

### Step 1: Open the Terminal

VS Code-এর Terminal open করো।

### Step 2: Start the Python Interpreter

Windows-এ:

```powershell
python
```

অথবা:

```powershell
py
```

macOS/Linux-এ:

```bash
python3
```

যদি Python REPL সফলভাবে open হয়, তাহলে সাধারণত এমন prompt দেখতে পাবে:

```text
>>>
```

এই `>>>` হলো Python interactive prompt।

### Step 3: Write Code Directly

REPL-এ লেখো:

```python
print("Hello")
```

Output:

```text
Hello
```

এবার লেখো:

```python
10 + 20
```

Output:

```text
30
```

এখানে `print()` ব্যবহার না করেও expression-এর result দেখা যায়, কারণ REPL সাধারণত expression-এর ফলাফল প্রদর্শন করে।

### Step 4: Create and Use Variables

```python
name = "Masum"
```

এরপর:

```python
name
```

Output:

```text
'Masum'
```

এবার:

```python
age = 22
age + 5
```

Output:

```text
27
```

এখানে variable-এর বিস্তারিত আমরা পরবর্তী chapter-এ শিখব। আপাতত বুঝবে, REPL-এ একটি statement লেখার পর পরবর্তী statement লিখে পরীক্ষা করা যায়।

### Step 5: Exit the REPL

REPL থেকে বের হতে লিখতে পারো:

```python
exit()
```

অথবা Windows/Linux/macOS-এর অনেক Terminal-এ `Ctrl + D` কাজ করে। Windows-এর কিছু console-এ `Ctrl + Z`, এরপর Enter ব্যবহার করা যায়।

**মনে রাখবে:** REPL-এ লেখা code সাধারণত স্বয়ংক্রিয়ভাবে `.py` file-এ save হয় না। স্থায়ীভাবে রাখতে চাইলে code file-এ লিখে save করবে।

### Advantages

- দ্রুত ছোট code পরীক্ষা করা যায়।
- Calculation যাচাই করা যায়।
- Function ও data structure পরীক্ষা করা যায়।
- সম্পূর্ণ file তৈরি না করেই experiment করা যায়।

### Limitations

- বড় program লেখা ও manage করা অসুবিধাজনক।
- Session শেষ হলে সাধারণত interactive session-এর state হারিয়ে যায়।
- Code-এর স্থায়ী record রাখতে আলাদা file-এ save করতে হয়।

**কখন ব্যবহার করবে?**

ছোট calculation, expression, function এবং নতুন Python feature পরীক্ষা করার জন্য REPL খুব উপকারী।

---

## 5. Method 4: Running a Single Command with `python -c`

কখনো কোনো `.py` file তৈরি না করেই একটি ছোট Python command execute করার প্রয়োজন হতে পারে।

এক্ষেত্রে `-c` option ব্যবহার করা যায়।

### Windows

```powershell
python -c "print('Hello from command line')"
```

অথবা:

```powershell
py -c "print(10 + 20)"
```

### macOS/Linux

```bash
python3 -c "print('Hello from command line')"
```

Output:

```text
Hello from command line
```

দ্বিতীয় command-এর output হবে:

```text
30
```

### Understanding the Command

```powershell
python -c "print(10 + 20)"
```

এখানে:

- `python` হলো Python interpreter চালানোর command।
- `-c` হলো command option, যার মাধ্যমে command-line string হিসেবে দেওয়া Python code execute করা হয়।
- `"print(10 + 20)"` হলো execute করার Python code।

### When Is This Useful?

- দ্রুত একটি calculation পরীক্ষা করতে।
- Python interpreter সঠিকভাবে কাজ করছে কি না দেখতে।
- ছোট automation command চালাতে।
- Script বা command-line workflow পরীক্ষা করতে।

বড় program-এর জন্য `.py` file ব্যবহার করাই বেশি সুবিধাজনক।

---

## 6. Method 5: Running a Python File with a Different Name

Python file-এর নাম সব সময় `main.py` হতে হবে, এমন কোনো নিয়ম নেই।

উদাহরণ:

```text
hello.py
calculator.py
practice.py
student_info.py
```

ধরা যাক, তোমার project folder-এ রয়েছে:

```text
first_python_project/
├── main.py
├── hello.py
└── calculator.py
```

`hello.py`-তে:

```python
print("Hello from hello.py")
```

`calculator.py`-তে:

```python
print(100 + 200)
```

এখন Terminal থেকে চালাও:

```powershell
python hello.py
```

Output:

```text
Hello from hello.py
```

এরপর:

```powershell
python calculator.py
```

Output:

```text
300
```

Windows-এ প্রয়োজন হলে `python`-এর পরিবর্তে `py` ব্যবহার করতে পারো। macOS/Linux-এ সাধারণত `python3` ব্যবহার করা হয়।

**গুরুত্বপূর্ণ:** Command-এ যে file name দেবে, Python সেই file চালানোর চেষ্টা করবে।

---

## 7. Method 6: Running a Python Module with `-m`

Python-এর `-m` option দিয়ে কোনো importable module-কে script হিসেবে চালানো যায়।

উদাহরণ:

```bash
python -m http.server
```

Windows-এ `python` command-এর পরিবর্তে প্রয়োজন হলে `py` ব্যবহার করতে পারো। macOS/Linux-এ সাধারণত:

```bash
python3 -m http.server
```

এই command বর্তমান working directory থেকে একটি সাধারণ HTTP server চালু করে। Default configuration-এ এটি সাধারণত port `8000` ব্যবহার করে।

Browser-এ খোলা যায়:

```text
http://localhost:8000
```

Server বন্ধ করতে Terminal-এ `Ctrl + C` চাপো।

### Why Use `-m`?

- Python standard library-এর module চালাতে।
- কিছু package-এর command-line interface চালাতে।
- নির্দিষ্ট Python interpreter-এর সঙ্গে module execute করতে।

উদাহরণ:

```bash
python -m pip --version
```

এটি নির্বাচিত Python interpreter-এর সঙ্গে সম্পর্কিত `pip`-এর version দেখায়।

**সতর্কতা:** `http.server` মূলত সাধারণ local testing-এর জন্য। এটি production server হিসেবে ব্যবহার করার জন্য তৈরি নয়। অপরিচিত বা sensitive file থাকা directory থেকে server চালানোর সময় সতর্ক থাকবে।

---

## 8. Comparing the Different Methods

| Method | Best Use | Main Advantage |
|---|---|---|
| VS Code Run Button | দৈনন্দিন coding practice | সহজে file run করা যায় |
| Terminal | Project ও script চালানো | Command ও file path-এর ওপর নিয়ন্ত্রণ |
| Python REPL | ছোট code পরীক্ষা | সঙ্গে সঙ্গে result পাওয়া যায় |
| `python -c` | Single command | File ছাড়াই ছোট code execute |
| `python filename.py` | নির্দিষ্ট script চালানো | সরাসরি file execute |
| `python -m module` | Module বা package-এর command চালানো | Python module-কে command হিসেবে execute |

### Which Method Should a Beginner Learn First?

প্রথমে এই ক্রমে practice করো:

1. VS Code Run Button।
2. Terminal থেকে `.py` file চালানো।
3. Python REPL।
4. `python -c` command।
5. `python -m` ব্যবহার।

তবে Terminal থেকে file চালানো শিখতে দেরি করবে না। এটি Python development-এর একটি গুরুত্বপূর্ণ ভিত্তি।

---

## 9. Understanding Working Directory and File Paths

Terminal থেকে Python file চালানোর সময় working directory বোঝা জরুরি।

ধরা যাক, তোমার project structure:

```text
Python_Project/
├── main.py
└── practice/
    └── exercise.py
```

তুমি যদি `Python_Project` folder-এ থাকো, তাহলে চালাতে পারো:

```powershell
python main.py
```

`practice` folder-এর file চালাতে পারো:

```powershell
python practice/exercise.py
```

Windows-এ নিচের backslash path-টিও ব্যবহার করা যায়:

```powershell
python practice\exercise.py
```

যদি Terminal অন্য folder-এ থাকে, তাহলে file-এর path অনুযায়ী command দিতে হবে অথবা আগে সঠিক folder-এ যেতে হবে।

উদাহরণ:

```powershell
cd practice
python exercise.py
```

এখানে `cd` command বর্তমান directory পরিবর্তন করে।

**মনে রাখবে:** Python file কোথায় রয়েছে এবং Terminal বর্তমানে কোথায় রয়েছে—এই দুটি বিষয় একসঙ্গে বিবেচনা করতে হয়।

---

## 10. Common Problems and Solutions

### Problem 1: `python` Is Not Recognized

সম্ভাব্য কারণ:

- Python install করা নেই।
- PATH সঠিকভাবে configure করা হয়নি।
- Terminal পুরোনো configuration ব্যবহার করছে।

সমাধান:

1. Python installation যাচাই করো।
2. Windows-এ `py --version` চেষ্টা করো।
3. Terminal বন্ধ করে আবার open করো।
4. প্রয়োজনে PATH configuration ঠিক করো।

### Problem 2: `No such file or directory`

উদাহরণ:

```text
python: can't open file 'main.py'
```

সম্ভাব্য কারণ:

- তুমি ভুল directory-তে আছ।
- File name ভুল লিখেছ।
- File save করা হয়নি।

সমাধান:

```powershell
Get-Location
```

Windows-এ file list দেখতে:

```powershell
Get-ChildItem
```

macOS/Linux-এ:

```bash
pwd
ls
```

তারপর সঠিক file path ব্যবহার করো।

### Problem 3: The Output Is Different

সম্ভাব্য কারণ:

- তুমি অন্য file চালিয়েছ।
- Code পরিবর্তন করার পর save করোনি।
- Code-এ calculation বা string ভুল রয়েছে।

সমাধান:

- File name যাচাই করো।
- Code save করো।
- সঠিক file পুনরায় run করো।

### Problem 4: VS Code Uses the Wrong Interpreter

সম্ভাব্য কারণ:

- অন্য Python version selected আছে।
- Project-এর virtual environment select করা নেই।

সমাধান:

1. `Python: Select Interpreter` command চালাও।
2. সঠিক interpreter নির্বাচন করো।
3. প্রয়োজনে Terminal নতুন করে open করো।
4. Python executable যাচাই করো।

### Problem 5: The Program Keeps Running

কিছু program শেষ না হয়ে চলতে থাকে, যেমন server বা infinite loop।

সমাধান:

Terminal-এ `Ctrl + C` চাপলে অনেক ক্ষেত্রে চলমান program বন্ধ করা যায়।

---

## 11. Practical Exercises

### Exercise 1: Use the VS Code Run Button

একটি `main.py` file তৈরি করে লেখো:

```python
print("I am learning Python")
print("I can run Python files")
```

Run Button ব্যবহার করে output দেখো।

### Exercise 2: Run the Same File from Terminal

একই file Terminal থেকে চালাও:

```powershell
python main.py
```

Windows-এ প্রয়োজন হলে `py main.py` ব্যবহার করো।

macOS/Linux-এ সাধারণত:

```bash
python3 main.py
```

দুই পদ্ধতির output তুলনা করো।

### Exercise 3: Use the Python REPL

REPL চালু করে একে একে লেখো:

```python
5 + 10
```

```python
print("Python")
```

```python
100 / 4
```

প্রতিটি result বোঝার চেষ্টা করো।

### Exercise 4: Use `python -c`

চেষ্টা করো:

```powershell
python -c "print(50 + 50)"
```

এর output কী হবে, আগে অনুমান করো।

### Exercise 5: Create Two Python Files

দুটি file তৈরি করো:

`hello.py`

```python
print("Hello")
```

`welcome.py`

```python
print("Welcome to Python")
```

Terminal থেকে আলাদাভাবে দুটি file চালাও।

### Exercise 6: Explore a Module

Terminal-এ চালাও:

```bash
python -m pip --version
```

তোমার system-এ প্রয়োজন হলে `python`-এর পরিবর্তে `py` বা `python3` ব্যবহার করো।

Command-টি কী তথ্য দেখায়, তা বোঝার চেষ্টা করো।

---

## 12. Best Practices

1. ছোট code দ্রুত পরীক্ষা করার জন্য REPL ব্যবহার করো।
2. স্থায়ী program লেখার জন্য `.py` file তৈরি করো।
3. Terminal থেকে file চালানোর অভ্যাস গড়ে তোলো।
4. সঠিক Python interpreter ব্যবহার করো।
5. Command চালানোর আগে current working directory যাচাই করো।
6. File name ও path সঠিকভাবে লেখো।
7. Code পরিবর্তন করার পরে save করতে ভুলবে না।
8. Error message পড়ে সমস্যা সমাধান করো।
9. কোন পদ্ধতিতে code চালাচ্ছ, তা বুঝে ব্যবহার করো।
10. অপ্রয়োজনীয়ভাবে একাধিক Python installation তৈরি কোরো না।

---

## 13. Quick Revision

| Question | Answer |
|---|---|
| VS Code-এ Python file কীভাবে চালাব? | `Run Python File` button দিয়ে |
| Terminal থেকে file কীভাবে চালাব? | `python main.py` বা system অনুযায়ী `py main.py` / `python3 main.py` |
| REPL কী? | Interactive Python environment |
| REPL-এর পূর্ণরূপ কী? | Read-Eval-Print Loop |
| ছোট command file ছাড়া কীভাবে চালাব? | `python -c` ব্যবহার করে |
| `python -m` কী কাজে লাগে? | Python module-কে script বা command হিসেবে চালাতে |
| `cd` কী করে? | Current directory পরিবর্তন করে |
| `Ctrl + C` কী কাজে লাগে? | অনেক ক্ষেত্রে চলমান process বন্ধ করতে |
| Code কোথায় save হয়? | যে file-এ লিখে save করা হয়েছে, সেখানে |

---

## 14. Chapter Connection

এই topic-এ আমরা Python code চালানোর বিভিন্ন পদ্ধতি শিখেছি এবং বুঝেছি কোন পরিস্থিতিতে কোন পদ্ধতি ব্যবহার করা সুবিধাজনক।

এখন তুমি VS Code, Terminal ও Python REPL ব্যবহার করে ছোট program চালাতে পারবে।

পরবর্তী topic-এ আমরা **Working Directory** আরও বিস্তারিতভাবে শিখব—current directory, absolute path, relative path, directory পরিবর্তন এবং file path-সংক্রান্ত সাধারণ সমস্যাগুলো নিয়ে।

**Next Topic:** [16. Understanding the Working Directory](16_Understanding_the_Working_Directory.md)