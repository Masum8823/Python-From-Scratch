# 24. Common Installation Errors and Solutions

## 1. Introduction

Python শেখার সময় installation ও development environment নিয়ে বিভিন্ন সমস্যা হতে পারে। যেমন, Python install করার পরও terminal-এ Python command কাজ না করা, VS Code-এ interpreter খুঁজে না পাওয়া, package install করতে error হওয়া ইত্যাদি।

এই সমস্যাগুলো বেশিরভাগ সময় সঠিক configuration, interpreter selection অথবা environment ঠিক করার মাধ্যমে সমাধান করা যায়।

এই topic-এ আমরা শিখব:

1. Python command কাজ না করলে কী করতে হবে।
2. PATH ও environment variable-এর সমস্যা সমাধান।
3. Python interpreter খুঁজে না পেলে কী করতে হবে।
4. `pip`-এর error সমাধান।
5. Virtual environment-এর সমস্যা সমাধান।
6. VS Code ও Jupyter Notebook-এর সাধারণ সমস্যা।
7. Python script run করার সময় হওয়া error শনাক্ত করা।
8. সমস্যা সমাধানের সঠিক পদ্ধতি।

---

## 2. Problem: Python Is Not Recognized

Windows-এ নিচের মতো error দেখা যেতে পারে:

```text
'python' is not recognized as an internal or external command
```

এটির অর্থ হলো terminal `python` নামে executable command খুঁজে পাচ্ছে না।

### Possible Causes

- Python install করা নেই।
- Python-এর installation directory PATH-এ নেই।
- Installation-এর পরে terminal restart করা হয়নি।
- একাধিক Python installation থাকায় command resolution-এ সমস্যা হচ্ছে।

### Solution 1: Check Python Installation

PowerShell বা VS Code terminal-এ চালাও:

```powershell
python --version
```

এরপর চেষ্টা করো:

```powershell
py --version
```

যদি `py` কাজ করে কিন্তু `python` কাজ না করে, তাহলে Python Launcher উপলভ্য আছে, কিন্তু `python` command-এর configuration আলাদা হতে পারে।

### Solution 2: Check the Installation

Python install করা আছে কি না যাচাই করো। প্রয়োজন হলে official website থেকে installer download করে installation সম্পন্ন করো।

Official website:

https://www.python.org/downloads/

### Solution 3: Check PATH

Python-এর executable directory PATH-এ আছে কি না যাচাই করো।

PATH-এর বিস্তারিত ধারণা এই chapter-এর `08_Understanding_PATH_and_Environment_Variables.md` ফাইলে রয়েছে।

### Solution 4: Restart the Terminal

Installation বা PATH পরিবর্তনের পরে পুরোনো terminal বন্ধ করে নতুন terminal খোলো।

তারপর:

```powershell
python --version
```

চালাও।

**মনে রাখবে:** Python install করার পরও command কাজ না করলে সঙ্গে সঙ্গে আবার install কোরো না। আগে installation, PATH এবং terminal configuration যাচাই করো।

---

## 3. Problem: Python Opens the Microsoft Store

Windows-এ `python` command চালালে কখনো Microsoft Store খুলতে পারে।

### Possible Causes

Windows-এর App Execution Aliases-এর কারণে এমন হতে পারে। এটি সব সময় Python install করা নেই—এমন প্রমাণ নয়।

### Solution

প্রথমে পরীক্ষা করো:

```powershell
py --version
```

এটি কাজ করলে আপাতত `py` ব্যবহার করে Python চালাতে পারো।

সমস্যা থাকলে:

1. Windows Settings খোলো।
2. Apps-এর অধীনে Advanced app settings খুঁজে বের করো।
3. App execution aliases-এ যাও।
4. Python-এর alias configuration যাচাই করো।
5. প্রয়োজন অনুযায়ী alias ঠিক করো এবং নিশ্চিত হও যে আসল Python installation সঠিকভাবে configured আছে।

Windows version অনুযায়ী Settings-এর নাম বা অবস্থান সামান্য আলাদা হতে পারে।

এরপর নতুন terminal খুলে আবার পরীক্ষা করো।

---

## 4. Problem: `python` and `python3` Behave Differently

বিভিন্ন operating system-এ Python command-এর নাম আলাদা হতে পারে।

উদাহরণ:

```bash
python --version
```

অথবা:

```bash
python3 --version
```

Windows-এ Python Launcher থাকলে:

```powershell
py --version
```

### Why Does This Happen?

একটি computer-এ একাধিক Python version থাকতে পারে। Operating system ও installation configuration অনুযায়ী আলাদা command আলাদা executable নির্দেশ করতে পারে।

### Solution

যে command কাজ করছে, সেটির version এবং executable path যাচাই করো।

Python চালিয়ে:

```python
import sys

print(sys.version)
print(sys.executable)
```

এতে বর্তমানে চলমান interpreter-এর version এবং executable path দেখা যাবে।

Virtual environment ব্যবহার করলে সেই environment-এর interpreter সঠিকভাবে নির্বাচন করা হয়েছে কি না নিশ্চিত হও।

---

## 5. Problem: Python Version Is Different from Expected

ধরা যাক, তুমি Python-এর একটি নতুন version install করেছ। কিন্তু terminal-এ পুরোনো version দেখা যাচ্ছে।

### Possible Causes

- একাধিক Python version install করা আছে।
- PATH-এ অন্য installation আগে রয়েছে।
- VS Code অন্য interpreter ব্যবহার করছে।
- Virtual environment অন্য Python version দিয়ে তৈরি হয়েছে।

### Solution 1: Check the Version

```bash
python --version
```

Windows-এ:

```powershell
py --list
```

এই command-এর output-এ install করা Python version-গুলোর তালিকা পাওয়া যেতে পারে। উপলভ্য Python Launcher version অনুযায়ী আচরণ কিছুটা ভিন্ন হতে পারে।

### Solution 2: Check the Executable

```python
import sys

print(sys.executable)
print(sys.version)
```

### Solution 3: Select the Correct Interpreter

VS Code-এ:

1. `Ctrl + Shift + P` চাপো।
2. `Python: Select Interpreter` নির্বাচন করো।
3. সঠিক Python installation বা virtual environment নির্বাচন করো।

### Important

একাধিক Python version install থাকা নিজে থেকে কোনো সমস্যা নয়। সমস্যা হয় যখন project-এর জন্য ভুল interpreter ব্যবহার করা হয়।

---

## 6. Problem: VS Code Cannot Find the Python Interpreter

VS Code-এ নিচের মতো message দেখা যেতে পারে:

```text
No Python interpreter selected
```

অথবা Python extension interpreter খুঁজে পায় না।

### Possible Causes

- Python install করা নেই।
- VS Code-এর Python extension install করা নেই।
- সঠিক interpreter select করা হয়নি।
- Virtual environment তৈরি করা হয়নি অথবা শনাক্ত হচ্ছে না।
- VS Code পুরোনো configuration ব্যবহার করছে।

### Solution 1: Verify Python Installation

Terminal-এ:

```bash
python --version
```

প্রয়োজন হলে:

```bash
python3 --version
```

Windows-এ:

```powershell
py --version
```

### Solution 2: Install the Python Extension

VS Code-এর Extensions panel খুলে Microsoft-এর Python extension install করো।

### Solution 3: Select an Interpreter

1. `Ctrl + Shift + P` চাপো।
2. `Python: Select Interpreter` লিখে নির্বাচন করো।
3. Project-এর জন্য সঠিক interpreter বেছে নাও।

### Solution 4: Open the Correct Project Folder

VS Code-এ শুধু একটি file না খুলে project-এর মূল folder খোলার চেষ্টা করো।

এতে project-specific virtual environment ও configuration শনাক্ত করা সহজ হতে পারে।

### Solution 5: Reload VS Code

প্রয়োজন হলে Command Palette থেকে `Developer: Reload Window` নির্বাচন করো।

তারপর interpreter আবার নির্বাচন করো।

---

## 7. Problem: VS Code Run Button Does Not Work

Python file-এর Run button চাপলে code execute না হলে কয়েকটি বিষয় পরীক্ষা করতে হবে।

### Solution

**Step 1: Save the File**

File-এর extension `.py` কি না যাচাই করো।

উদাহরণ:

```text
main.py
```

**Step 2: Select the Interpreter**

`Python: Select Interpreter` ব্যবহার করে সঠিক interpreter নির্বাচন করো।

**Step 3: Check the Terminal**

VS Code-এর Terminal panel খুলে error message দেখো।

**Step 4: Run Manually**

Terminal-এ:

```bash
python main.py
```

Windows-এ `python` কাজ না করলে:

```powershell
py main.py
```

macOS বা Linux-এ প্রয়োজনে:

```bash
python3 main.py
```

**Step 5: Check the Extension**

Microsoft-এর Python extension install ও enabled আছে কি না যাচাই করো।

**মনে রাখবে:** Run button কাজ না করলেও terminal থেকে Python script চালানো সম্ভব হতে পারে। তাই terminal-এ code চালিয়ে সমস্যা VS Code-এর, নাকি Python installation-এর—তা আলাদা করে যাচাই করো।

---

## 8. Problem: `pip` Is Not Recognized

নিচের মতো error দেখা যেতে পারে:

```text
'pip' is not recognized as an internal or external command
```

### Why Does This Happen?

- `pip` command PATH-এ নেই।
- Python installation-এর সঙ্গে `pip` install হয়নি।
- একাধিক Python installation-এর কারণে ভুল `pip` ব্যবহার হচ্ছে।

### Solution 1: Use `python -m pip`

সবচেয়ে নির্ভরযোগ্য পদ্ধতিগুলোর একটি হলো:

```bash
python -m pip --version
```

Windows-এ:

```powershell
py -m pip --version
```

macOS বা Linux-এ:

```bash
python3 -m pip --version
```

এভাবে নির্দিষ্ট interpreter-এর সঙ্গে `pip` ব্যবহার করা যায়।

### Solution 2: Install or Repair pip

যদি interpreter-এ `pip` না থাকে, তাহলে সমর্থিত installation-এ চেষ্টা করতে পারো:

```bash
python -m ensurepip --upgrade
```

Windows-এ প্রয়োজনে:

```powershell
py -m ensurepip --upgrade
```

সব Python distribution-এ `ensurepip` উপলভ্য থাকবে—এমন নিশ্চয়তা নেই। Command কাজ না করলে তোমার installation-এর official documentation অনুসরণ করো।

### Solution 3: Upgrade pip

```bash
python -m pip install --upgrade pip
```

এখানে সঠিক interpreter-এর command ব্যবহার করবে।

---

## 9. Problem: Package Installation Fails

ধরা যাক, তুমি `requests` package install করতে চাও।

```bash
python -m pip install requests
```

কিন্তু installation fail হচ্ছে।

### Possible Causes

- Internet connection নেই।
- ভুল interpreter ব্যবহার হচ্ছে।
- Python version package-এর সঙ্গে compatible নয়।
- Package-এর নাম ভুল লেখা হয়েছে।
- Permission সমস্যা হচ্ছে।
- Package download বা build করার সময় error হচ্ছে।

### Step 1: Check the Package Name

Package-এর সঠিক নাম ব্যবহার করো।

উদাহরণ:

```bash
python -m pip install requests
```

### Step 2: Check Python and pip

```bash
python --version
python -m pip --version
```

এতে বোঝা যাবে কোন Python installation-এর সঙ্গে `pip` কাজ করছে।

### Step 3: Check the Error Message

Error message-এর শেষের অংশ ভালোভাবে পড়ো। সেখানে network, compatibility, permission বা build failure-এর কারণ থাকতে পারে।

### Step 4: Use a Virtual Environment

Project-এর জন্য virtual environment তৈরি ও activate করে package install করো।

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

macOS বা Linux:

```bash
source .venv/bin/activate
```

তারপর:

```bash
python -m pip install requests
```

### Step 5: Avoid Random Fixes

Error না বুঝে একের পর এক command চালিয়ো না। বিশেষ করে অজানা website থেকে package download বা security বন্ধ করার নির্দেশ অনুসরণ কোরো না।

---

## 10. Problem: Permission Denied During Package Installation

Package install করার সময় permission-related error দেখা যেতে পারে।

### Possible Causes

- System-level Python directory-তে write permission নেই।
- অন্য user-এর অধীনে package install করার চেষ্টা হচ্ছে।
- Virtual environment activate করা হয়নি।

### Recommended Solution

Project-এর virtual environment ব্যবহার করো।

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

macOS বা Linux:

```bash
source .venv/bin/activate
```

তারপর:

```bash
python -m pip install requests
```

### Important

অপ্রয়োজনীয়ভাবে `sudo pip install ...` ব্যবহার কোরো না। এতে system-managed Python package পরিবর্তিত হয়ে অন্য application-এর সমস্যা হতে পারে।

---

## 11. Problem: Virtual Environment Does Not Activate

Virtual environment তৈরি করার পর activate command কাজ না করলে operating system অনুযায়ী সঠিক command ব্যবহার করো।

### Windows PowerShell

```powershell
.\.venv\Scripts\Activate.ps1
```

### Windows Command Prompt

```cmd
.venv\Scripts\activate.bat
```

### Git Bash on Windows

```bash
source .venv/Scripts/activate
```

### macOS and Linux

```bash
source .venv/bin/activate
```

### Check the Folder Structure

Virtual environment তৈরি হয়ে থাকলে সাধারণত নিচের মতো structure থাকবে:

```text
project/
├── .venv/
│   ├── Scripts/       # Windows
│   └── bin/           # macOS/Linux
└── main.py
```

বাস্তব structure operating system অনুযায়ী আলাদা হবে।

### If Activation Still Fails

1. তুমি সঠিক project folder-এ আছ কি না দেখো।
2. `.venv` folder তৈরি হয়েছে কি না যাচাই করো।
3. সঠিক activation command ব্যবহার করো।
4. প্রয়োজন হলে environment নতুন করে তৈরি করো।

উদাহরণ:

```bash
python -m venv .venv
```

আগের environment-এ গুরুত্বপূর্ণ file থাকলে সেটি মুছে ফেলার আগে যাচাই করো।

---

## 12. Problem: PowerShell Blocks the Activation Script

Windows PowerShell-এ এমন error দেখা যেতে পারে:

```text
running scripts is disabled on this system
```

এটি PowerShell-এর execution policy-এর সঙ্গে সম্পর্কিত হতে পারে।

### Recommended Options

**Option 1: Use Command Prompt**

VS Code-এ Command Prompt terminal নির্বাচন করে চালাও:

```cmd
.venv\Scripts\activate.bat
```

**Option 2: Use PowerShell After Reviewing the Policy**

PowerShell execution policy security-এর একটি অংশ। এটি পরিবর্তন করার আগে policy কীভাবে কাজ করে তা বোঝা দরকার।

ব্যক্তিগত user-এর জন্য policy পরিবর্তনের প্রয়োজন হলে Microsoft-এর official documentation পড়ে অনুমোদিত ও উপযুক্ত scope নির্বাচন করো।

শুধু একটি Python environment activate করার জন্য অযথা system-wide security policy দুর্বল কোরো না।

### Alternative

Activation ছাড়াও virtual environment-এর Python executable সরাসরি ব্যবহার করা যায়।

Windows:

```powershell
.\.venv\Scripts\python.exe main.py
```

macOS বা Linux:

```bash
./.venv/bin/python main.py
```

---

## 13. Problem: VS Code Uses the Wrong Virtual Environment

কখনো virtual environment তৈরি ও activate করার পরও VS Code অন্য Python interpreter ব্যবহার করতে পারে।

### Solution

1. VS Code-এ project folder খোলো।
2. `Ctrl + Shift + P` চাপো।
3. `Python: Select Interpreter` নির্বাচন করো।
4. Project-এর `.venv` interpreter নির্বাচন করো।

সাধারণত path হবে:

Windows:

```text
.venv\Scripts\python.exe
```

macOS বা Linux:

```text
.venv/bin/python
```

### Verify the Interpreter

একটি Python file-এ চালাও:

```python
import sys

print(sys.executable)
```

Output-এ `.venv`-এর Python path দেখা গেলে সাধারণত সঠিক interpreter ব্যবহার হচ্ছে।

### Why Is This Important?

ধরা যাক, তুমি `.venv`-এ `requests` install করেছ। কিন্তু VS Code system Python ব্যবহার করছে।

তাহলে VS Code-এ:

```python
import requests
```

লিখলে `ModuleNotFoundError` দেখা যেতে পারে।

এক্ষেত্রে package আবার install করার আগে interpreter সঠিক কি না যাচাই করো।

---

## 14. Problem: `ModuleNotFoundError`

উদাহরণ:

```text
ModuleNotFoundError: No module named 'requests'
```

এর অর্থ হলো Python যে environment থেকে code চালাচ্ছে, সেখানে `requests` module খুঁজে পাচ্ছে না।

### Solution 1: Identify the Active Interpreter

```python
import sys

print(sys.executable)
```

### Solution 2: Install the Package in That Environment

```bash
python -m pip install requests
```

সঠিক virtual environment বা interpreter-এর command ব্যবহার করো।

### Solution 3: Check the Import Name

কিছু package-এর installation name ও import name আলাদা হতে পারে।

উদাহরণ:

```bash
python -m pip install beautifulsoup4
```

Python code:

```python
from bs4 import BeautifulSoup
```

### Solution 4: Check Local File Names

নিজের project-এ `requests.py`, `random.py` বা `json.py` নামে file থাকলে standard library বা installed package-এর সঙ্গে নামের conflict হতে পারে।

প্রয়োজন হলে file rename করো এবং সংশ্লিষ্ট cache পরিষ্কার করো।

---

## 15. Problem: Jupyter Notebook Cannot Find a Kernel

Jupyter Notebook চালানোর সময় kernel নির্বাচন করতে না পারলে বা Python kernel unavailable দেখালে নিচের বিষয়গুলো যাচাই করো।

### Step 1: Check Jupyter Installation

```bash
python -m pip show jupyter
```

### Step 2: Install Jupyter

প্রয়োজন হলে:

```bash
python -m pip install jupyter
```

### Step 3: Install the IPython Kernel

```bash
python -m pip install ipykernel
```

### Step 4: Register the Environment as a Kernel

```bash
python -m ipykernel install --user --name python-learning --display-name "Python Learning"
```

এই command current interpreter-এর environment-কে Jupyter kernel হিসেবে register করতে সাহায্য করে।

### Step 5: Select the Kernel

Jupyter Notebook বা VS Code-এ kernel selection option থেকে উপযুক্ত Python environment নির্বাচন করো।

### Important

Jupyter server ও notebook kernel আলাদা environment থেকে চলতে পারে। তাই server চালু থাকলেও notebook-এর মধ্যে সব package পাওয়া যাবে—এমন নয়।

---

## 16. Problem: Jupyter Notebook Uses Old Variable Values

Jupyter Notebook-এ কোনো cell একবার run করার পর variable-এর value memory-তে থাকে।

ধরা যাক:

```python
number = 10
```

পরে তুমি cell পরিবর্তন করে লিখলে:

```python
number = 20
```

কিন্তু সেই cell run না করলে notebook-এর memory-তে পুরোনো value থেকে যেতে পারে।

### Solution

- সংশোধিত cell আবার run করো।
- প্রয়োজন হলে `Restart Kernel` ব্যবহার করো।
- Kernel restart করার পরে প্রয়োজনীয় cell-গুলো সঠিক ক্রমে run করো।

**মনে রাখবে:** Notebook-এর cell-এর দৃশ্যমান order ও বাস্তবে execution-এর order সব সময় এক নাও হতে পারে।

---

## 17. Problem: `SyntaxError`

উদাহরণ:

```python
print("Hello"
```

এখানে closing parenthesis নেই।

Python এমন error দেখাতে পারে:

```text
SyntaxError: '(' was never closed
```

### Common Causes

- Closing bracket না থাকা।
- String-এর quotation mark বন্ধ না করা।
- Colon (`:`) বাদ পড়া।
- ভুলভাবে operator বা keyword লেখা।
- ভুল indentation-এর কারণে syntax error হওয়া।

### Correct Example

```python
print("Hello")
```

Conditional statement-এর সঠিক উদাহরণ:

```python
if 10 > 5:
    print("Ten is greater than five")
```

### Solution

1. Error message পড়ো।
2. যে line-এ error দেখাচ্ছে সেটি পরীক্ষা করো।
3. তার আগের line-টিও দেখো, কারণ ভুলটি আগের line-এ থাকতে পারে।
4. Bracket, quotation mark, colon ও indentation যাচাই করো।

---

## 18. Problem: `IndentationError`

Python code-এর block নির্ধারণ করতে indentation ব্যবহার করে।

ভুল উদাহরণ:

```python
if True:
print("Hello")
```

সঠিক উদাহরণ:

```python
if True:
    print("Hello")
```

### Solution

- একই block-এ consistent indentation ব্যবহার করো।
- সাধারণত প্রতি level-এ চারটি space ব্যবহার করা হয়।
- একই block-এ tab ও space মিশিয়ে ব্যবহার করা এড়িয়ে চলো।
- VS Code-এর indentation setting যাচাই করো।

---

## 19. Problem: File Not Found

Error:

```text
FileNotFoundError
```

এর অর্থ Python নির্দিষ্ট path-এ file খুঁজে পায়নি।

### Example

```python
with open("data.txt", "r", encoding="utf-8") as file:
    content = file.read()
```

`data.txt` যদি Python process-এর current working directory-তে না থাকে, তাহলে error হতে পারে।

### Solution 1: Check the Working Directory

```python
import os

print(os.getcwd())
```

### Solution 2: Check Whether the File Exists

```python
from pathlib import Path

file_path = Path("data.txt")

print(file_path.exists())
```

### Solution 3: Use the Correct Path

File-এর সঠিক relative বা absolute path ব্যবহার করো।

```python
from pathlib import Path

file_path = Path("data") / "data.txt"

if file_path.exists():
    print("File found")
else:
    print("File not found")
```

Project-এর file structure বুঝে path নির্ধারণ করো। সব সময় absolute path hardcode করা ভালো practice নয়।

---

## 20. Problem: Port or Network Error While Installing Packages

Package install বা Jupyter চালানোর সময় network-related error দেখা যেতে পারে।

### Possible Causes

- Internet connection নেই।
- Network firewall বা proxy connection বাধা দিচ্ছে।
- Package index server সাময়িকভাবে unavailable।
- Certificate বা TLS configuration সমস্যা হচ্ছে।

### Solution

1. Internet connection যাচাই করো।
2. Error message-এ server, proxy বা certificate-এর তথ্য দেখো।
3. প্রয়োজনে কিছুক্ষণ পরে আবার চেষ্টা করো।
4. প্রতিষ্ঠানের network ব্যবহার করলে তাদের অনুমোদিত proxy configuration অনুসরণ করো।
5. Package-এর official installation instructions যাচাই করো।

Certificate verification বন্ধ করে দেওয়া বা অজানা mirror ব্যবহার করা নিরাপদ সমাধান নয়।

---

## 21. General Troubleshooting Method

Python-সংক্রান্ত সমস্যা হলে নিচের ধাপগুলো অনুসরণ করো।

### Step 1: Read the Full Error Message

Error-এর শেষের অংশে কী সমস্যা হয়েছে তা প্রায়ই উল্লেখ থাকে।

### Step 2: Identify the Environment

```python
import sys

print(sys.version)
print(sys.executable)
```

### Step 3: Check the Working Directory

```python
from pathlib import Path

print(Path.cwd())
```

### Step 4: Check the Package

```bash
python -m pip show PACKAGE_NAME
```

এখানে `PACKAGE_NAME`-এর পরিবর্তে আসল package name ব্যবহার করবে।

### Step 5: Check the Terminal

VS Code-এর Run button-এর পাশাপাশি terminal থেকে code চালিয়ে দেখো।

### Step 6: Change One Thing at a Time

একসঙ্গে অনেক configuration পরিবর্তন কোরো না। একটি পরিবর্তনের পর আবার পরীক্ষা করো।

### Step 7: Consult Official Documentation

প্রয়োজন হলে Python, VS Code, pip, Jupyter বা সংশ্লিষ্ট package-এর official documentation দেখো।

---

## 22. Common Error Quick Reference

| Error | সম্ভাব্য কারণ | প্রথমে কী করবে |
|---|---|---|
| `python is not recognized` | Python command বা PATH সমস্যা | `py --version` ও PATH যাচাই |
| Microsoft Store opens | App Execution Alias | `py --version` পরীক্ষা |
| `pip is not recognized` | pip command PATH-এ নেই | `python -m pip --version` |
| `ModuleNotFoundError` | ভুল environment বা package অনুপস্থিত | `sys.executable` যাচাই |
| `No Python interpreter selected` | VS Code interpreter select করা নেই | `Python: Select Interpreter` |
| `Permission denied` | Write permission বা environment সমস্যা | Virtual environment ব্যবহার |
| Activation script blocked | PowerShell execution policy | Command Prompt বা উপযুক্ত policy |
| `SyntaxError` | Code-এর syntax ভুল | Error line ও আগের line পরীক্ষা |
| `IndentationError` | Block-এর indentation ভুল | Consistent indentation |
| `FileNotFoundError` | File path ভুল | `Path.cwd()` ও file existence |
| Jupyter kernel unavailable | Kernel বা environment configuration | `ipykernel` ও kernel selection |
| Wrong Python version | একাধিক interpreter | `sys.version` ও `sys.executable` |

---

## 23. Practice Tasks

নিচের কাজগুলো নিজে করে দেখো।

1. Terminal-এ Python version পরীক্ষা করো।
2. `sys.executable` ব্যবহার করে Python-এর path দেখো।
3. ইচ্ছাকৃতভাবে ভুল command দিয়ে error message পড়ো।
4. একটি virtual environment তৈরি ও activate করো।
5. Virtual environment-এ `requests` install করো।
6. VS Code-এ সঠিক interpreter নির্বাচন করো।
7. একটি Python file-এ ইচ্ছাকৃতভাবে closing bracket বাদ দিয়ে `SyntaxError` তৈরি করো, তারপর ঠিক করো।
8. একটি file-এর ভুল path ব্যবহার করে `FileNotFoundError` তৈরি করো, তারপর path ঠিক করো।
9. Jupyter Notebook-এ kernel নির্বাচন করে একটি cell run করো।
10. প্রতিটি সমস্যার কারণ ও সমাধান নিজের ভাষায় লিখে রাখো।

---

## 24. Final Checklist

এই topic শেষ করার পর যাচাই করো:

- [ ] Python command কাজ না করলে কীভাবে পরীক্ষা করতে হয়, জানি।
- [ ] Python version ও executable path দেখতে পারি।
- [ ] PATH-এর সমস্যার প্রাথমিক সমাধান জানি।
- [ ] VS Code-এ interpreter নির্বাচন করতে পারি।
- [ ] `python -m pip` ব্যবহার করতে পারি।
- [ ] Virtual environment তৈরি ও activate করতে পারি।
- [ ] `ModuleNotFoundError`-এর সম্ভাব্য কারণ বুঝি।
- [ ] Jupyter kernel নির্বাচন করতে পারি।
- [ ] Syntax ও indentation error-এর প্রাথমিক সমাধান জানি।
- [ ] File path ও working directory যাচাই করতে পারি।
- [ ] Error message পড়ে ধাপে ধাপে সমস্যা সমাধান করতে পারি।

---

## 25. Chapter Summary

এই topic-এ আমরা Python development environment-এর সাধারণ সমস্যা, সেগুলোর সম্ভাব্য কারণ এবং সমাধানের পদ্ধতি শিখেছি।

সবচেয়ে গুরুত্বপূর্ণ বিষয় হলো—কোনো error দেখলেই Python আবার install করার প্রয়োজন নেই। আগে interpreter, PATH, package, virtual environment, working directory এবং error message যাচাই করতে হবে।

**Next Topic:** [25. Development Environment Best Practices](25_Development_Environment_Best_Practices.md)

পরবর্তী topic-এ একটি পরিষ্কার, নিরাপদ ও maintainable Python development environment কীভাবে বজায় রাখতে হয়, তা শিখব।