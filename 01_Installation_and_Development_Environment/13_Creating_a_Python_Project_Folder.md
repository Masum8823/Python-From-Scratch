# 13. Creating a Python Project Folder

## 1. Introduction

Python শেখার সময় আমরা অনেকগুলো program, practice file, notes এবং project তৈরি করব। এগুলো এলোমেলোভাবে computer-এ রাখলে পরে খুঁজে পাওয়া ও manage করা কঠিন হয়ে যায়।

এই সমস্যা সমাধানের জন্য প্রতিটি project-এর জন্য আলাদা folder তৈরি করা ভালো।

**Python Project Folder** হলো এমন একটি directory, যেখানে একটি Python project-এর code, configuration, documentation এবং প্রয়োজনীয় file রাখা হয়।

এই topic-এ আমরা শিখব:

- Python project folder কী।
- Project folder কেন প্রয়োজন।
- Folder ও file-এর নাম কীভাবে নির্বাচন করতে হয়।
- Windows, macOS ও Linux-এ project folder তৈরি করা।
- VS Code-এ project folder open করা।
- একটি beginner-friendly project structure তৈরি করা।
- Project organize করার best practices।

---

## 2. What Is a Python Project?

Python ব্যবহার করে কোনো নির্দিষ্ট কাজ সম্পন্ন করার জন্য তৈরি করা code ও সংশ্লিষ্ট file-গুলোর সমষ্টিকে সাধারণভাবে Python project বলা হয়।

উদাহরণ:

- Calculator
- Student Management System
- Expense Tracker
- To-Do List Application
- Data Analysis Project
- Web Application

একটি ছোট Python project-এ শুধু একটি `.py` file থাকতে পারে। বড় project-এ একাধিক folder, module, test, configuration file এবং documentation থাকতে পারে।

### Example

একটি সাধারণ Calculator project-এর structure হতে পারে:

```text
Calculator/
├── main.py
├── calculator.py
└── README.md
```

এখানে:

- `main.py` — program চালানোর entry point হতে পারে।
- `calculator.py` — calculation-related function রাখা যেতে পারে।
- `README.md` — project-এর পরিচিতি ও ব্যবহারবিধি লেখা যেতে পারে।

এটি একটি simple example। Project-এর ধরন অনুযায়ী structure পরিবর্তিত হতে পারে।

---

## 3. Why Do We Need a Project Folder?

প্রতিটি project-এর জন্য আলাদা folder রাখার অনেক সুবিধা রয়েছে।

### 3.1 Organization

Project-এর code, notes ও configuration এক জায়গায় রাখা যায়।

### 3.2 Easy Navigation

VS Code-এ পুরো project folder open করে সহজে file খুঁজে পাওয়া যায়।

### 3.3 Dependency Management

প্রতিটি project-এর জন্য আলাদা virtual environment ও dependency file রাখা যায়।

### 3.4 Debugging

কোন file কোথায় রয়েছে, তা বোঝা সহজ হয়।

### 3.5 Git and GitHub Integration

Project folder-কে Git repository হিসেবে manage করা যায় এবং পরে GitHub-এ publish করা যায়।

### 3.6 Future Expansion

Project বড় হলে নতুন folder ও file যোগ করে structure উন্নত করা যায়।

**মনে রাখবে:** শুরু থেকেই project organize করার অভ্যাস তৈরি করলে বড় project manage করা অনেক সহজ হয়।

---

## 4. Choosing a Project Location

প্রথমে ঠিক করতে হবে computer-এর কোথায় Python project-গুলো রাখবে।

উদাহরণস্বরূপ, Windows-এ:

```text
C:\Users\YourName\Documents\Python_Projects\
```

অথবা:

```text
D:\Python_Projects\
```

macOS-এ:

```text
/Users/YourName/Documents/Python_Projects/
```

Linux-এ:

```text
/home/yourname/Python_Projects/
```

এগুলো উদাহরণ। তোমার computer-এর user name, drive ও directory আলাদা হতে পারে।

### Recommended Approach

একটি নির্দিষ্ট parent folder তৈরি করো:

```text
Python_Projects/
```

তারপর প্রতিটি project-এর জন্য এর মধ্যে আলাদা folder তৈরি করো।

যেমন:

```text
Python_Projects/
├── Hello_World/
├── Calculator/
├── Number_Guessing_Game/
└── Student_Management/
```

এভাবে project-গুলো আলাদা ও organized থাকবে।

### Important Advice

- System folder-এর মধ্যে অপ্রয়োজনীয় project রাখবে না।
- এমন location নির্বাচন করবে, যেখানে তোমার file তৈরি ও edit করার permission আছে।
- Project-এর নাম সহজ ও অর্থপূর্ণ রাখবে।
- Cloud-synced folder ব্যবহার করলে synchronization conflict হতে পারে কি না খেয়াল রাখবে।

---

## 5. Naming Rules for Project Folders

Folder ও file-এর নাম নির্বাচন করার সময় কিছু নিয়ম অনুসরণ করা ভালো।

### Recommended Naming Style

Python project folder-এর জন্য lowercase letters ও underscores ব্যবহার করা সুবিধাজনক।

উদাহরণ:

```text
python_practice
student_management
expense_tracker
data_analysis_project
```

### Avoid Confusing Names

এ ধরনের নাম এড়িয়ে চলা ভালো:

```text
New Folder
My Project Final Final
Python Project 2 New
test123
```

এগুলো technically সব সময় ভুল নয়, কিন্তু project বড় হলে নাম দেখে উদ্দেশ্য বোঝা কঠিন হতে পারে।

### General Rules

1. Project-এর নাম অর্থপূর্ণ রাখো।
2. সম্ভব হলে lowercase ব্যবহার করো।
3. শব্দ আলাদা করতে underscore (`_`) ব্যবহার করতে পারো।
4. অপ্রয়োজনীয় punctuation এড়িয়ে চলো।
5. File ও folder-এর নামের spelling ঠিক রাখো।
6. একই project-এর জন্য বারবার নতুন folder তৈরি না করে existing project update করো।

Python identifier-এর naming rules এবং file system-এর naming rules এক নয়। তাই file বা folder-এর নাম দেওয়ার সময় operating system-এর নিয়মও বিবেচনা করতে হবে।

---

## 6. Creating a Project Folder on Windows

Windows-এ File Explorer অথবা Terminal—দুইভাবেই project folder তৈরি করা যায়।

### Method 1: Using File Explorer

1. File Explorer open করো।
2. Documents অথবা নিজের পছন্দের location-এ যাও।
3. New Folder তৈরি করো।
4. Folder-এর নাম দাও:

```text
Python_Projects
```

5. Folder-এর মধ্যে আরেকটি folder তৈরি করো:

```text
first_python_project
```

এখন project-এর location হবে এমন:

```text
Python_Projects/
└── first_python_project/
```

### Method 2: Using PowerShell

PowerShell খুলে নিজের পছন্দের parent directory-তে যাও।

উদাহরণ:

```powershell
cd $HOME\Documents
```

এরপর parent folder তৈরি করো:

```powershell
mkdir Python_Projects
```

Project folder-এ প্রবেশ করো:

```powershell
cd Python_Projects
```

তারপর project তৈরি করো:

```powershell
mkdir first_python_project
```

Project folder-এ প্রবেশ করো:

```powershell
cd first_python_project
```

বর্তমান location পরীক্ষা করো:

```powershell
Get-Location
```

এখানে `$HOME` সাধারণত Windows-এ তোমার user home directory নির্দেশ করে।

যদি folder আগে থেকেই থাকে, তাহলে আবার তৈরি করার পরিবর্তে সেটিতে প্রবেশ করো।

---

## 7. Creating a Project Folder on macOS and Linux

macOS ও Linux-এ Terminal ব্যবহার করে folder তৈরি করা যায়।

### Step 1: Go to Your Home Directory

```bash
cd ~
```

`~` সাধারণত বর্তমান user-এর home directory নির্দেশ করে।

### Step 2: Create the Parent Folder

```bash
mkdir -p Python_Projects
```

`-p` ব্যবহার করলে প্রয়োজনীয় parent directory তৈরি করা যায় এবং directory আগে থেকে থাকলেও command সাধারণত error দেয় না।

### Step 3: Enter the Parent Folder

```bash
cd Python_Projects
```

### Step 4: Create the Project Folder

```bash
mkdir first_python_project
```

### Step 5: Enter the Project Folder

```bash
cd first_python_project
```

### Step 6: Verify the Location

```bash
pwd
```

এখন তুমি নিজের project folder-এর মধ্যে আছ কি না যাচাই করতে পারবে।

---

## 8. Opening the Project Folder in VS Code

Project folder তৈরি করার পর সেটিকে VS Code-এ open করতে হবে।

### Method 1: Using the VS Code Menu

1. VS Code চালু করো।
2. `File > Open Folder` নির্বাচন করো।
3. নিজের project folder খুঁজে বের করো।
4. Folder নির্বাচন করে open করো।

এখন VS Code-এর Explorer-এ project-এর file ও folder দেখা যাবে।

### Method 2: Using the Terminal

যদি `code` command configure করা থাকে, তাহলে project folder-এর মধ্যে থেকে চালাও:

```bash
code .
```

এখানে:

- `code` — VS Code command-line launcher।
- `.` — current directory।

এই command বর্তমান folder VS Code-এ open করার চেষ্টা করবে।

`code` command কাজ না করলে menu ব্যবহার করো। এর অর্থ এই নয় যে VS Code install করা নেই; command-line launcher configuration আলাদা হতে পারে।

### Why Open the Entire Folder?

পুরো folder open করলে:

- সব project file একসঙ্গে দেখা যায়।
- Relative path নিয়ে কাজ করা সহজ হয়।
- Project-specific settings ব্যবহার করা যায়।
- Git repository manage করা সুবিধাজনক হয়।
- Terminal-এ project directory ব্যবহার করা সহজ হয়।

---

## 9. Creating Your First Project Structure

এখন আমরা একটি beginner-friendly project structure তৈরি করব।

Project-এর নাম:

```text
first_python_project
```

শুরুতে structure হবে:

```text
first_python_project/
├── README.md
├── main.py
└── practice.py
```

### File 1: `README.md`

এই file-এ project-এর পরিচিতি, উদ্দেশ্য ও run করার পদ্ধতি লেখা হবে।

### File 2: `main.py`

এটি হবে মূল Python file।

### File 3: `practice.py`

এখানে আলাদা practice code রাখা যাবে।

### Why Use Separate Files?

একটি file-এ সব ধরনের code রাখলে ছোট program-এ সমস্যা না হলেও project বড় হলে code manage করা কঠিন হয়।

তাই প্রয়োজন অনুযায়ী আলাদা file ব্যবহার করা ভালো।

তবে শুরুতে প্রতিটি ছোট code-এর জন্য নতুন file তৈরি করারও দরকার নেই। কাজ অনুযায়ী file ভাগ করবে।

---

## 10. Creating Files in VS Code

Project folder open করার পরে VS Code-এর Explorer থেকে file তৈরি করতে পারো।

### Step 1: Create `main.py`

1. Explorer-এর New File option নির্বাচন করো।
2. File name দাও:

```text
main.py
```

3. নিচের code লেখো:

```python
print("Welcome to Python!")
print("This is my first project.")
```

4. `Ctrl + S` চাপো।

macOS-এ `Cmd + S` ব্যবহার করবে।

### Step 2: Create `practice.py`

আরেকটি file তৈরি করো:

```text
practice.py
```

এর মধ্যে লেখো:

```python
print("I am practicing Python.")
print("I will improve step by step.")
```

### Step 3: Create `README.md`

আরেকটি file তৈরি করো:

```text
README.md
```

এর মধ্যে লিখতে পারো:

```markdown
# First Python Project

This is my first Python practice project.

## Files

- `main.py`: Main Python program
- `practice.py`: Practice code

## How to Run

Run the following command in the project directory:

```bash
python main.py
```
```

Windows-এ তোমার system অনুযায়ী `py main.py`-ও ব্যবহার করা যেতে পারে। macOS/Linux-এ প্রয়োজনে `python3 main.py` ব্যবহার করবে।

---

## 11. Running the Project

VS Code-এর Terminal open করো।

প্রথমে নিশ্চিত হও যে Terminal project folder-এ রয়েছে।

Windows PowerShell:

```powershell
Get-Location
```

macOS/Linux:

```bash
pwd
```

তারপর `main.py` run করো।

Windows:

```powershell
python main.py
```

macOS/Linux:

```bash
python3 main.py
```

প্রয়োজনে নিজের system-এর উপযুক্ত Python command ব্যবহার করবে।

Expected output:

```text
Welcome to Python!
This is my first project.
```

এখন `practice.py` run করো।

Windows:

```powershell
python practice.py
```

macOS/Linux:

```bash
python3 practice.py
```

Expected output:

```text
I am practicing Python.
I will improve step by step.
```

---

## 12. Understanding Project Root

**Project Root** হলো একটি project-এর প্রধান directory, যার মধ্যে project-এর মূল file ও folder থাকে।

উদাহরণ:

```text
first_python_project/
├── README.md
├── main.py
└── practice.py
```

এখানে `first_python_project/` হলো project root।

Project বড় হলে এর মধ্যে subdirectory তৈরি করা যেতে পারে:

```text
first_python_project/
├── README.md
├── src/
├── tests/
└── docs/
```

এখানে:

- `src/` — source code রাখার জন্য ব্যবহৃত হতে পারে।
- `tests/` — test code রাখার জন্য।
- `docs/` — documentation রাখার জন্য।

ছোট beginner project-এর জন্য এতগুলো folder বাধ্যতামূলক নয়। Project-এর প্রয়োজন অনুযায়ী structure তৈরি করবে।

---

## 13. A More Organized Project Structure

একটু বড় project-এর structure এমন হতে পারে:

```text
expense_tracker/
├── README.md
├── main.py
├── requirements.txt
├── .gitignore
├── src/
│   └── expense_tracker.py
├── tests/
│   └── test_expense_tracker.py
└── docs/
    └── usage.md
```

এটি একটি illustrative structure।

| File/Folder | Purpose |
|---|---|
| `README.md` | Project overview ও usage |
| `main.py` | Program চালু করার entry point হতে পারে |
| `requirements.txt` | Project-এর dependency list |
| `.gitignore` | Git-এ কোন file track করা হবে না, তা নির্ধারণ |
| `src/` | Source code |
| `tests/` | Test code |
| `docs/` | অতিরিক্ত documentation |

এই structure-এ ব্যবহৃত প্রতিটি file বা folder সব project-এ থাকা বাধ্যতামূলক নয়।

যেমন, external package ব্যবহার না করলে `requirements.txt` দরকার নাও হতে পারে।

---

## 14. Project Folder vs Virtual Environment

Project folder এবং virtual environment এক জিনিস নয়।

| Project Folder | Virtual Environment |
|---|---|
| পুরো project-এর file রাখে | Project-এর Python environment ও package আলাদা রাখতে সাহায্য করে |
| Code ও documentation থাকে | Python executable এবং installed dependencies থাকতে পারে |
| Project-এর মূল directory | Project folder-এর ভেতরে রাখা একটি environment directory হতে পারে |
| যেমন `my_project/` | যেমন `my_project/.venv/` |

উদাহরণ:

```text
my_project/
├── .venv/
├── main.py
└── README.md
```

এখানে `my_project/` হলো project folder, আর `.venv/` হলো virtual environment-এর directory।

Virtual environment-এর বিস্তারিত পরবর্তী topic-গুলোতে শেখা হবে।

---

## 15. Common Mistakes

### Mistake 1: Keeping All Projects in One Folder

সব project-এর file একই directory-তে রাখলে পরে manage করা কঠিন হতে পারে।

**Solution:** প্রতিটি project-এর জন্য আলাদা folder তৈরি করো।

### Mistake 2: Opening Only a Python File

শুধু একটি file open করলে project-এর অন্যান্য file ও folder manage করা কঠিন হতে পারে।

**Solution:** সাধারণত VS Code-এ পুরো project folder open করো।

### Mistake 3: Running Code from the Wrong Directory

Terminal অন্য directory-তে থাকলে Python file খুঁজে পেতে সমস্যা হতে পারে।

**Solution:** `pwd` বা `Get-Location` দিয়ে বর্তমান directory যাচাই করো।

### Mistake 4: Using Unclear Folder Names

`New Folder 2` বা `Final Project New`-এর মতো নাম project-এর উদ্দেশ্য বোঝায় না।

**Solution:** `calculator`, `expense_tracker` বা `student_management`-এর মতো অর্থপূর্ণ নাম ব্যবহার করো।

### Mistake 5: Creating Too Many Folders Too Early

ছোট project-এ অপ্রয়োজনীয় nested folder তৈরি করলে structure জটিল হতে পারে।

**Solution:** প্রয়োজন অনুযায়ী folder তৈরি করো।

### Mistake 6: Accidentally Creating Duplicate Projects

একই project-এর একাধিক copy থাকলে কোনটি latest, তা নিয়ে বিভ্রান্তি হতে পারে।

**Solution:** Project-এর একটি primary location নির্ধারণ করো এবং সেটি নিয়মিত update করো।

---

## 16. Best Practices

1. সব Python project-এর জন্য একটি নির্দিষ্ট parent directory রাখো।
2. প্রতিটি project-এর জন্য আলাদা folder তৈরি করো।
3. অর্থপূর্ণ ও consistent naming convention ব্যবহার করো।
4. VS Code-এ পুরো project folder open করো।
5. Project root থেকে Terminal command চালানোর অভ্যাস তৈরি করো।
6. Code, documentation ও practice file যথাযথভাবে organize করো।
7. Project বড় হওয়ার আগে অপ্রয়োজনীয় structure তৈরি কোরো না।
8. Project-এর গুরুত্বপূর্ণ file নিয়মিত save করো।
9. Git ব্যবহার করলে `.gitignore` সঠিকভাবে configure করো।
10. Project-এর virtual environment project অনুযায়ী manage করো।

---

## 17. Practice Tasks

### Task 1: Create a Parent Folder

নিজের পছন্দের location-এ `Python_Projects` নামে একটি folder তৈরি করো।

### Task 2: Create a Project Folder

এর মধ্যে তৈরি করো:

```text
first_python_project
```

### Task 3: Open the Project

VS Code-এ `first_python_project` folder open করো।

### Task 4: Create the Files

নিচের structure তৈরি করো:

```text
first_python_project/
├── README.md
├── main.py
└── practice.py
```

### Task 5: Write the Main Program

`main.py`-তে লেখো:

```python
print("My first Python project")
print("Project folders help organize code.")
```

### Task 6: Write the Practice Program

`practice.py`-তে লেখো:

```python
print("Practice makes programming easier.")
```

### Task 7: Run Both Files

Terminal থেকে দুটি file আলাদাভাবে run করো।

### Task 8: Verify the Project Location

Terminal-এর current working directory পরীক্ষা করো এবং project root-এর সঙ্গে মিলিয়ে দেখো।

### Task 9: Explain the Concepts

নিজের ভাষায় উত্তর দাও:

1. Python project folder কী?
2. Project root কী?
3. আলাদা project folder রাখার সুবিধা কী?
4. Project folder ও virtual environment-এর পার্থক্য কী?
5. VS Code-এ পুরো folder open করা কেন সুবিধাজনক?

---

## 18. Quick Revision

| Concept | Key Point |
|---|---|
| Python Project | Code ও related file-এর সমষ্টি |
| Project Folder | Project-এর file ও folder রাখার directory |
| Project Root | Project-এর প্রধান directory |
| `mkdir` | Directory তৈরি করে |
| `cd` | Directory পরিবর্তন করে |
| `pwd` | Current working directory দেখায় |
| `main.py` | Program-এর entry point হতে পারে |
| `README.md` | Project-এর পরিচিতি ও ব্যবহারবিধি |
| `requirements.txt` | Python dependency list রাখতে পারে |
| `.gitignore` | Git-এ ignore করার file ও directory নির্ধারণ করে |
| `.venv/` | Virtual environment-এর directory হতে পারে |

---

## 19. Chapter Connection

এই topic-এ আমরা Python project folder তৈরি করা, naming convention, project root, file organization এবং VS Code-এ পুরো project open করা শিখেছি।

এখন তুমি নিজের একটি organized Python project তৈরি করতে পারবে এবং তার মধ্যে একাধিক Python file রাখতে পারবে।

পরবর্তী topic-এ আমরা প্রথম Python file তৈরি করে সেটি run করব এবং program লেখার প্রাথমিক workflow বুঝব।

**Next Topic:** [14. Creating and Running Your First Python File](14_Creating_and_Running_Your_First_Python_File.md)