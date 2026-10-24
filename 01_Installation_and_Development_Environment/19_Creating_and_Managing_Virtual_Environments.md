# 19. Creating and Managing Virtual Environments

## 1. Introduction

Python দিয়ে একাধিক project তৈরি করলে প্রতিটি project-এর আলাদা আলাদা package এবং package version প্রয়োজন হতে পারে।

ধরা যাক, তুমি দুটি project তৈরি করেছ:

- `Project_A`
- `Project_B`

`Project_A`-এর জন্য একটি package-এর পুরোনো version দরকার, কিন্তু `Project_B`-এর জন্য নতুন version দরকার।

যদি উভয় project একই Python environment ব্যবহার করে, তাহলে dependency conflict হতে পারে।

এই সমস্যা সমাধানের একটি গুরুত্বপূর্ণ উপায় হলো **Virtual Environment** ব্যবহার করা।

এই topic-এ আমরা শিখব:

1. Virtual environment কী এবং কেন ব্যবহার করা হয়।
2. `venv` module কীভাবে কাজ করে।
3. Virtual environment তৈরি করা।
4. Windows, macOS ও Linux-এ activate করা।
5. Virtual environment deactivate করা।
6. VS Code-এ virtual environment ব্যবহার করা।
7. Package install ও manage করা।
8. Environment-related error সমাধান করা।

---

## 2. What Is a Virtual Environment?

Virtual environment হলো একটি নির্দিষ্ট Python project-এর জন্য আলাদা environment, যেখানে project-এর নিজস্ব package এবং dependency manage করা যায়।

এটি project-এর package-গুলোকে অন্য project-এর package থেকে আলাদা রাখতে সাহায্য করে।

Python-এর standard library-তে `venv` নামে একটি module রয়েছে, যা দিয়ে virtual environment তৈরি করা যায়।

### Example

ধরা যাক, তোমার কম্পিউটারে দুটি project রয়েছে:

```text
Python_Projects/
├── Project_A/
│   ├── .venv/
│   └── main.py
│
└── Project_B/
    ├── .venv/
    └── main.py
```

এখানে প্রতিটি project-এর নিজস্ব `.venv` রয়েছে।

- `Project_A`-এর package তার environment-এ install হবে।
- `Project_B`-এর package তার environment-এ install হবে।
- একটি project-এর package পরিবর্তন করলে অন্য project সাধারণত প্রভাবিত হবে না।

এভাবে dependency management সহজ হয়।

### Important Concept

Virtual environment তৈরি করলেই প্রতিটি project-এর জন্য সম্পূর্ণ নতুন Python installation download হয় না।

সাধারণত এটি একটি নির্দিষ্ট Python installation-কে ভিত্তি করে আলাদা environment তৈরি করে এবং project-specific package রাখার ব্যবস্থা করে।

---

## 3. Why Do We Need Virtual Environments?

Virtual environment ব্যবহার করার কয়েকটি গুরুত্বপূর্ণ কারণ রয়েছে।

### 3.1 Avoiding Dependency Conflicts

ধরা যাক:

```text
Project_A → Package X version 1
Project_B → Package X version 2
```

দুটি project-এর জন্য আলাদা environment ব্যবহার করলে তাদের package version আলাদাভাবে manage করা যায়।

### 3.2 Keeping Projects Independent

একটি project-এর জন্য নতুন package install করলে অন্য project-এর package list অপ্রয়োজনীয়ভাবে পরিবর্তিত হয় না।

### 3.3 Easier Project Setup

Project-এর dependency list সংরক্ষণ করে অন্য কম্পিউটারেও কাছাকাছি environment পুনরায় তৈরি করা যায়।

### 3.4 Cleaner Python Installation

প্রতিটি project-এর package global Python installation-এ install করার প্রয়োজন কমে যায়।

### 3.5 Better Development Practice

বাস্তব software development-এ project-এর dependency আলাদা করে manage করা একটি সাধারণ ও গুরুত্বপূর্ণ অভ্যাস।

---

## 4. What Is `venv`?

`venv` হলো Python-এর standard library-তে থাকা একটি module, যা virtual environment তৈরি করতে ব্যবহৃত হয়।

সাধারণভাবে এটি আলাদাভাবে `pip` দিয়ে install করতে হয় না।

### Creating a Virtual Environment

প্রথমে project folder-এর Terminal-এ যাও:

```bash
cd MyPythonProject
```

তারপর চালাও:

```bash
python -m venv .venv
```

এখানে:

- `python` হলো Python interpreter চালানোর command।
- `-m` একটি Python module-কে script হিসেবে চালায়।
- `venv` হলো virtual environment তৈরির module।
- `.venv` হলো environment-এর directory name।

Windows-এ প্রয়োজনে `python`-এর পরিবর্তে `py` ব্যবহার করতে পারো:

```powershell
py -m venv .venv
```

macOS/Linux-এ প্রয়োজনে:

```bash
python3 -m venv .venv
```

Command সফল হলে project folder-এর মধ্যে `.venv` directory তৈরি হবে।

**মনে রাখবে:** `.venv` কোনো বিশেষ Python keyword নয়। এটি একটি প্রচলিত folder name। চাইলে অন্য নামও ব্যবহার করা যায়, যেমন `venv`।

---

## 5. Understanding the `.venv` Folder

Virtual environment তৈরি করার পর project-এর structure এমন হতে পারে:

```text
MyPythonProject/
├── .venv/
├── main.py
├── requirements.txt
└── README.md
```

`.venv` folder-এর মধ্যে environment পরিচালনার জন্য প্রয়োজনীয় file ও directory থাকে।

Operating system অনুযায়ী এর structure কিছুটা আলাদা হতে পারে।

Windows-এ সাধারণত:

```text
.venv/
├── Include/
├── Lib/
│   └── site-packages/
├── Scripts/
└── pyvenv.cfg
```

macOS/Linux-এ সাধারণত:

```text
.venv/
├── bin/
├── include/
├── lib/
│   └── pythonX.Y/
│       └── site-packages/
└── pyvenv.cfg
```

এখানে:

- `Scripts/` বা `bin/`-এ environment-এর executable ও activation script থাকে।
- `site-packages/`-এ environment-এর installed package থাকে।
- `pyvenv.cfg`-এ environment configuration-সংক্রান্ত তথ্য থাকে।

`pythonX.Y` শুধু version-dependent directory বোঝানোর জন্য ব্যবহার করা হয়েছে; এটি কোনো literal folder name নয়।

### Important Rule

`.venv` folder-এর ভেতরের file সাধারণত নিজে হাতে edit বা delete করার দরকার হয় না।

Environment নষ্ট হলে অনেক ক্ষেত্রে সেটি পুনরায় তৈরি করাই সহজ সমাধান।

---

## 6. Activating a Virtual Environment on Windows

Virtual environment তৈরি করার পর সেটি activate করতে হবে।

ধরা যাক, তোমার project folder-এর নাম `MyPythonProject` এবং environment-এর নাম `.venv`।

### Step 1: Open the Project Folder

VS Code-এ `MyPythonProject` folder open করো।

### Step 2: Open the Terminal

VS Code menu থেকে:

`Terminal > New Terminal`

### Step 3: Activate in PowerShell

```powershell
.\.venv\Scripts\Activate.ps1
```

Activation সফল হলে Terminal prompt-এর শুরুতে সাধারণত এমন দেখা যায়:

```text
(.venv) PS C:\...\MyPythonProject>
```

এখানে `(.venv)` বোঝায় যে virtual environment active হয়েছে।

### Step 4: Verify the Environment

```powershell
python --version
```

তারপর:

```powershell
python -c "import sys; print(sys.executable)"
```

দ্বিতীয় command-টি Python executable-এর path দেখাবে।

সঠিকভাবে active থাকলে path সাধারণত project-এর `.venv` directory-এর ভেতরের Python executable নির্দেশ করবে।

### Alternative: Windows Command Prompt

যদি তুমি Command Prompt ব্যবহার করো, তাহলে:

```bat
.venv\Scripts\activate.bat
```

PowerShell ও Command Prompt-এর activation command এক নয়।

---

## 7. Activating a Virtual Environment on macOS and Linux

macOS ও Linux-এ virtual environment activate করার সাধারণ command হলো:

```bash
source .venv/bin/activate
```

সফল হলে Terminal prompt-এর শুরুতে সাধারণত দেখা যাবে:

```text
(.venv) user@computer MyPythonProject %
```

Prompt-এর format shell ও system অনুযায়ী আলাদা হতে পারে।

### Verify the Environment

```bash
python --version
```

এরপর:

```bash
python -c "import sys; print(sys.executable)"
```

Python executable-এর path পরীক্ষা করো।

সঠিক environment active থাকলে executable সাধারণত `.venv/bin/` directory-এর ভেতরে থাকবে।

### What If `python` Does Not Work?

কিছু system-এ Python চালানোর command হিসেবে `python3` ব্যবহার করতে হয়।

Environment তৈরি করার সময়:

```bash
python3 -m venv .venv
```

কিন্তু environment activate করার পরে সাধারণত `python` command-ই environment-এর interpreter চালায়।

তাই command-এর নাম অনুমান না করে `sys.executable` দিয়ে যাচাই করাই ভালো।

---

## 8. What Does Activation Actually Do?

Virtual environment activate করলে বর্তমান shell-এর environment পরিবর্তিত হয়, যাতে ওই environment-এর Python executable ও related scripts সহজে ব্যবহার করা যায়।

Activation script সাধারণত:

- PATH-এর শুরুতে virtual environment-এর executable directory যোগ করে।
- Terminal prompt-এ environment-এর নাম দেখাতে পারে।
- কিছু environment-related variable সেট করে।

### Example

Environment activate করার আগে:

```text
C:\Python\python.exe
```

Environment activate করার পরে:

```text
C:\Projects\MyPythonProject\.venv\Scripts\python.exe
```

এগুলো illustrative path; তোমার কম্পিউটারে path ভিন্ন হবে।

### Important

Activation একটি convenience feature।

Virtual environment activate না করেও তার Python executable-এর full path ব্যবহার করে program চালানো যায়।

Windows:

```powershell
.\.venv\Scripts\python.exe main.py
```

macOS/Linux:

```bash
./.venv/bin/python main.py
```

এভাবে নির্দিষ্ট environment-এর interpreter সরাসরি ব্যবহার করা যায়।

---

## 9. Installing Packages Inside a Virtual Environment

এখন environment active থাকা অবস্থায় package install করি।

### Step 1: Activate the Environment

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### Step 2: Install a Package

```bash
python -m pip install requests
```

### Step 3: Verify Installation

```bash
python -m pip show requests
```

### Step 4: Test the Package

`main.py`-তে লেখো:

```python
import requests

print(requests.__version__)
```

Run করো:

```bash
python main.py
```

Package import সফল হলে তার version দেখা যাবে।

### Why Does This Work?

Environment active থাকলে `python -m pip` সাধারণত সেই environment-এর interpreter-এর সঙ্গে যুক্ত pip ব্যবহার করে।

তাই package-টি project-এর `.venv`-এর মধ্যে install হয়, global Python environment-এ নয়।

---

## 10. Deactivating a Virtual Environment

কাজ শেষ হলে virtual environment থেকে বের হতে পারো।

Command:

```bash
deactivate
```

এই command Windows, macOS এবং Linux-এর সাধারণ `venv` activation workflow-তে ব্যবহার করা যায়।

Activation-এর আগে Terminal prompt ছিল:

```text
MyPythonProject>
```

Activation-এর পরে:

```text
(.venv) MyPythonProject>
```

Deactivate করার পরে সাধারণত `(.venv)` prefix আর দেখা যাবে না।

### Does Deactivation Delete the Environment?

না।

`deactivate` শুধু বর্তমান shell-কে virtual environment থেকে বের করে।

`.venv` directory এবং এর মধ্যে install করা package-গুলো থেকে যায়।

পরবর্তীতে আবার activate করে কাজ চালিয়ে যেতে পারো।

---

## 11. Checking Whether the Correct Environment Is Active

কোন Python environment ব্যবহার হচ্ছে, তা নিশ্চিত হওয়া খুব গুরুত্বপূর্ণ।

### Method 1: Check the Python Executable

```bash
python -c "import sys; print(sys.executable)"
```

Output-এর path পরীক্ষা করো।

যদি path `.venv`-এর ভেতরের interpreter নির্দেশ করে, তাহলে সাধারণত সঠিক environment ব্যবহার হচ্ছে।

### Method 2: Check pip

```bash
python -m pip --version
```

Output-এ pip-এর location দেখা যাবে।

Location-টি virtual environment-এর সঙ্গে সম্পর্কিত কি না যাচাই করো।

### Method 3: Check Installed Packages

```bash
python -m pip list
```

Environment অনুযায়ী installed package-এর তালিকা দেখতে পারবে।

### Method 4: Check the Environment Prefix

```bash
python -c "import sys; print(sys.prefix); print(sys.base_prefix)"
```

সাধারণ virtual environment-এ:

- `sys.prefix` active environment-এর location নির্দেশ করে।
- `sys.base_prefix` যে base Python installation থেকে environment তৈরি হয়েছে, তার location নির্দেশ করে।

সাধারণত virtual environment-এ `sys.prefix` এবং `sys.base_prefix` আলাদা হয়।

এই পরীক্ষা environment শনাক্ত করতে সহায়ক।

---

## 12. Selecting the Virtual Environment in VS Code

Virtual environment তৈরি করলেই VS Code সব সময় স্বয়ংক্রিয়ভাবে সঠিক interpreter নির্বাচন করবে, এমন নিশ্চয়তা নেই।

তাই interpreter যাচাই করা জরুরি।

### Step 1: Open the Project

VS Code-এ সেই folder open করো, যেখানে `.venv` আছে।

### Step 2: Open the Command Palette

Keyboard shortcut:

```text
Ctrl + Shift + P
```

macOS-এ:

```text
Cmd + Shift + P
```

### Step 3: Select the Interpreter

Command Palette-এ লিখো:

```text
Python: Select Interpreter
```

তারপর project-এর `.venv`-এর interpreter নির্বাচন করো।

সাধারণত path এমন হবে:

Windows:

```text
.venv\Scripts\python.exe
```

macOS/Linux:

```text
.venv/bin/python
```

### Step 4: Verify

VS Code-এর Terminal-এ চালাও:

```bash
python -c "import sys; print(sys.executable)"
```

Interpreter-এর path যাচাই করো।

**মনে রাখবে:** VS Code-এ interpreter নির্বাচন এবং Terminal-এ environment activation সম্পর্কিত হলেও একেবারে একই বিষয় নয়। Terminal-এর বর্তমান state-ও যাচাই করা দরকার।

---

## 13. Creating a Virtual Environment for a New Project

এখন একটি সম্পূর্ণ workflow দেখি।

ধরা যাক, নতুন project-এর নাম `StudentManagement`।

### Step 1: Create the Project Folder

Terminal-এ:

```bash
mkdir StudentManagement
cd StudentManagement
```

এই command-গুলো বর্তমান directory-এর ভেতরে folder তৈরি করে। Windows, macOS ও Linux-এর সাধারণ terminal-এ এগুলো কাজ করে।

### Step 2: Open the Project in VS Code

```bash
code .
```

এই command কাজ করার জন্য VS Code-এর `code` command PATH-এ available থাকতে হবে।

না থাকলে VS Code থেকে folder-টি manually open করো।

### Step 3: Create the Virtual Environment

Windows:

```powershell
py -m venv .venv
```

macOS/Linux:

```bash
python3 -m venv .venv
```

অথবা system-এ উপযুক্ত `python` command ব্যবহার করো।

### Step 4: Activate the Environment

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### Step 5: Install a Package

```bash
python -m pip install requests
```

### Step 6: Create a Python File

`main.py` তৈরি করো:

```python
import requests

response = requests.get("https://example.com", timeout=10)

print("Status code:", response.status_code)
```

### Step 7: Run the Program

```bash
python main.py
```

Internet connection ও website-এর response পাওয়া গেলে status code দেখা যাবে।

এই উদাহরণে network request করা হয়েছে, তাই Internet বা remote server-এর সমস্যার কারণে request ব্যর্থ হতে পারে।

---

## 14. Managing Multiple Projects

ধরা যাক, তোমার কম্পিউটারে তিনটি project রয়েছে:

```text
Python_Projects/
├── Calculator/
│   ├── .venv/
│   └── main.py
│
├── StudentManagement/
│   ├── .venv/
│   └── main.py
│
└── DataAnalysis/
    ├── .venv/
    └── main.py
```

প্রতিটি project-এর নিজস্ব virtual environment আছে।

এর সুবিধা:

- Dependency আলাদাভাবে manage করা যায়।
- Package version-এর conflict কমে।
- Project-এর requirements আলাদা রাখা যায়।
- নতুন কম্পিউটারে project setup সহজ হয়।

### Important Rule

একটি project-এর `.venv` অন্য project-এর মধ্যে copy করে ব্যবহার করার পরিবর্তে নতুন project-এর জন্য আলাদা environment তৈরি করো।

Virtual environment সাধারণত নির্দিষ্ট path ও base Python installation-এর সঙ্গে সম্পর্কিত। তাই copy করা environment অন্য location-এ কাজ নাও করতে পারে।

---

## 15. Should `.venv` Be Uploaded to GitHub?

সাধারণত `.venv` folder GitHub repository-তে upload করা উচিত নয়।

কারণ:

1. এতে অনেক file থাকে।
2. Folder-এর size বড় হতে পারে।
3. Environment operating system ও path-এর ওপর নির্ভর করতে পারে।
4. অন্য developer-এর কম্পিউটারে একই environment সরাসরি কাজ নাও করতে পারে।

এর পরিবর্তে dependency list commit করো, যেমন:

```text
requirements.txt
```

### Example `.gitignore`

Project root-এ `.gitignore` file তৈরি করো:

```gitignore
.venv/
venv/
__pycache__/
*.py[cod]
```

এতে Git সাধারণত এই pattern-গুলোর সঙ্গে মিলে যাওয়া file ও directory track করবে না।

যদি `.venv` আগে থেকেই Git-এ tracked হয়ে থাকে, তাহলে শুধু `.gitignore` যোগ করলেই tracking বন্ধ হবে না। সে ক্ষেত্রে আলাদাভাবে Git tracking পরিবর্তন করতে হবে।

### Recreating the Environment

অন্য কম্পিউটারে project নেওয়ার পরে:

```bash
python -m venv .venv
```

তারপর environment activate করে:

```bash
python -m pip install -r requirements.txt
```

এভাবে project-এর documented dependencies install করা যায়।

---

## 16. Virtual Environment vs Global Python Environment

| Feature | Global Environment | Virtual Environment |
|---|---|---|
| Scope | নির্দিষ্ট Python installation-এর সঙ্গে যুক্ত | নির্দিষ্ট project বা কাজের জন্য |
| Package isolation | তুলনামূলক কম | বেশি |
| Dependency conflicts | একাধিক project-এর মধ্যে হতে পারে | কমানো সহজ |
| Project-specific package management | কঠিন হতে পারে | সহজ |
| সাধারণ project development | সাধারণত কম উপযুক্ত | সাধারণত বেশি উপযুক্ত |

### Which One Should You Use?

শেখার জন্য ছোট program চালাতে global Python ব্যবহার করা যায়।

কিন্তু package-নির্ভর project, assignment, web application, data analysis বা machine learning project তৈরি করলে virtual environment ব্যবহার করার অভ্যাস গড়ে তোলা ভালো।

---

## 17. Common Errors and Their Solutions

### Error 1: `No module named venv`

সম্ভাব্য কারণ:

- Python installation অসম্পূর্ণ।
- Linux distribution-এ `venv`-এর আলাদা system package প্রয়োজন।

সমাধান:

Python installation যাচাই করো। Ubuntu/Debian-এর কিছু installation-এ উপযুক্ত Python version-এর `venv` package install করতে হতে পারে।

উদাহরণ:

```bash
sudo apt install python3-venv
```

এই command কেবল উপযুক্ত Ubuntu/Debian environment-এর জন্য; অন্য distribution-এ package manager ও package name ভিন্ন হতে পারে।

### Error 2: PowerShell Script Execution Is Disabled

Windows PowerShell-এ activation script চালানোর সময় execution policy-সংক্রান্ত error হতে পারে।

সম্ভাব্য বিকল্প:

- VS Code-এ Command Prompt terminal ব্যবহার করো।
- Command Prompt-এ চালাও:

```bat
.venv\Scripts\activate.bat
```

PowerShell-এর execution policy পরিবর্তন করার আগে সেটির প্রভাব বুঝে নাও। অজানা script চালানোর জন্য security restriction অন্ধভাবে disable করো না।

### Error 3: `python` Command Not Found

সম্ভাব্য কারণ:

- Python command PATH-এ নেই।
- Python অন্য command name দিয়ে available।
- Terminal নতুন করে open করতে হবে।

যাচাই করো:

Windows:

```powershell
py --version
```

macOS/Linux:

```bash
python3 --version
```

তারপর উপযুক্ত interpreter দিয়ে environment তৈরি করো।

### Error 4: `ModuleNotFoundError` After Installation

সম্ভাব্য কারণ:

- Package global environment-এ install হয়েছে।
- Program অন্য interpreter ব্যবহার করছে।
- VS Code-এ ভুল interpreter selected আছে।

যাচাই করো:

```bash
python -c "import sys; print(sys.executable)"
python -m pip show requests
```

দুটি command একই environment ব্যবহার করছে কি না পরীক্ষা করো।

### Error 5: `.venv` Folder Exists but Does Not Work

সম্ভাব্য কারণ:

- Environment-এর file পরিবর্তিত বা মুছে গেছে।
- Project অন্য location-এ সরানো হয়েছে।
- Base Python installation পরিবর্তিত হয়েছে।

সমাধান:

প্রয়োজনীয় dependency list সংরক্ষিত থাকলে environment পুনরায় তৈরি করা যেতে পারে। পুরোনো environment মুছে ফেলার আগে নিশ্চিত হও যে সেখানে এমন কোনো একমাত্র copy নেই, যা তোমার দরকার।

### Error 6: Wrong Python Version in Virtual Environment

Virtual environment তৈরি করার সময় যে Python interpreter ব্যবহার করা হয়, environment সাধারণত সেই installation-এর সঙ্গে যুক্ত থাকে।

তাই আগে version যাচাই করো:

```bash
python --version
```

প্রয়োজন হলে উপযুক্ত Python interpreter দিয়ে environment পুনরায় তৈরি করো।

---

## 18. Best Practices

1. প্রতিটি project-এর জন্য আলাদা virtual environment ব্যবহার করো।
2. Environment-এর নাম হিসেবে `.venv` ব্যবহার করতে পারো।
3. Package install করার আগে environment activate করো।
4. `python -m pip` ব্যবহার করে package install করো।
5. `sys.executable` দিয়ে interpreter-এর path যাচাই করো।
6. VS Code-এ সঠিক interpreter নির্বাচন করো।
7. `.venv` GitHub-এ upload না করে `.gitignore`-এ রাখো।
8. Project-এর dependency `requirements.txt`-এ document করো।
9. অন্য project-এর environment copy করে ব্যবহার না করে নতুন environment তৈরি করো।
10. System Python-এর package management policy মেনে চলো।
11. Project অন্য computer-এ নেওয়ার সময় environment পুনরায় তৈরি করো।
12. Environment-এর কাজ শেষ হলে `deactivate` ব্যবহার করতে পারো।

---

## 19. Practical Exercises

### Exercise 1: Create a Project

`VirtualEnvironmentPractice` নামে একটি project folder তৈরি করো।

### Exercise 2: Create a Virtual Environment

```bash
python -m venv .venv
```

প্রয়োজনে `python`-এর পরিবর্তে `py` বা `python3` ব্যবহার করো।

### Exercise 3: Activate the Environment

তোমার operating system অনুযায়ী সঠিক activation command ব্যবহার করো।

### Exercise 4: Verify the Interpreter

```bash
python -c "import sys; print(sys.executable)"
```

Output-এর path পরীক্ষা করো।

### Exercise 5: Install a Package

```bash
python -m pip install requests
```

### Exercise 6: Test the Package

`main.py` তৈরি করো:

```python
import requests

print("Requests version:", requests.__version__)
```

Program-টি run করো।

### Exercise 7: Check Installed Packages

```bash
python -m pip list
```

### Exercise 8: Deactivate the Environment

```bash
deactivate
```

তারপর আবার Python executable-এর path পরীক্ষা করো। আগের environment-এর path এবং নতুন path-এর মধ্যে পার্থক্য আছে কি না দেখো।

### Exercise 9: Practice Reactivation

Environment আবার activate করো এবং `main.py` run করো।

### Exercise 10: Create `.gitignore`

নিচের content দিয়ে `.gitignore` file তৈরি করো:

```gitignore
.venv/
__pycache__/
*.py[cod]
```

এবার বোঝার চেষ্টা করো কোন file ও folder Git-এর tracking থেকে বাদ থাকবে।

---

## 20. Quick Revision

| Term / Command | Purpose |
|---|---|
| Virtual Environment | Project-specific Python environment |
| `venv` | Virtual environment তৈরির standard module |
| `python -m venv .venv` | Environment তৈরি করে |
| `.\.venv\Scripts\Activate.ps1` | Windows PowerShell-এ activate করে |
| `.venv\Scripts\activate.bat` | Windows Command Prompt-এ activate করে |
| `source .venv/bin/activate` | macOS/Linux-এ activate করে |
| `deactivate` | Active environment থেকে বের হয় |
| `sys.executable` | ব্যবহৃত Python executable-এর path দেখায় |
| `sys.prefix` | Active Python environment-এর prefix দেখায় |
| `sys.base_prefix` | Base Python installation-এর prefix দেখায় |
| `.gitignore` | Git-কে নির্দিষ্ট file ও folder ignore করতে বলে |
| `requirements.txt` | Project dependency list সংরক্ষণ করে |

---

## 21. Chapter Connection

এই topic-এ আমরা virtual environment তৈরি, activate, deactivate এবং manage করা শিখেছি।

এখন তুমি একটি Python project-এর জন্য আলাদা environment তৈরি করে সেখানে package install ও ব্যবহার করতে পারবে।

পরবর্তী topic-এ আমরা শিখব কীভাবে virtual environment-এর মধ্যে package install করতে হয়, installed package যাচাই করতে হয় এবং dependency list ব্যবহার করে project setup করতে হয়।

**Next Topic:** [20. Installing Packages in a Virtual Environment](20_Installing_Packages_in_a_Virtual_Environment.md)