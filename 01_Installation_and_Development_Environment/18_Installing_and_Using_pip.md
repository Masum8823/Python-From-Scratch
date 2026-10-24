# 18. Installing and Using pip

## 1. Introduction

Python দিয়ে বিভিন্ন ধরনের কাজ করা যায়। কিন্তু সব functionality নিজে থেকে তৈরি করার প্রয়োজন নেই। অন্য developer-দের তৈরি package ব্যবহার করে সহজে নতুন feature যোগ করা যায়।

যেমন:

- `requests` — HTTP request পাঠাতে।
- `numpy` — Numerical calculation করতে।
- `pandas` — Data analysis করতে।
- `matplotlib` — Graph ও chart তৈরি করতে।
- `flask` — Web application তৈরি করতে।

এই package-গুলো install ও manage করার জন্য Python ecosystem-এ বহুল ব্যবহৃত একটি tool হলো **pip**।

এই topic-এ আমরা শিখব:

1. Package ও library কী।
2. `pip` কীভাবে কাজ করে।
3. `pip` installation যাচাই করা।
4. Package install, update ও uninstall করা।
5. নির্দিষ্ট version install করা।
6. Installed package-এর তালিকা দেখা।
7. `requirements.txt` ব্যবহার করা।
8. Common installation error সমাধান করা।

---

## 2. What Is a Package?

Package হলো Python code-এর একটি সংগঠিত collection, যা নির্দিষ্ট functionality প্রদান করে।

উদাহরণ হিসেবে, কোনো package HTTP request পাঠানো, data analysis করা অথবা image process করার সুবিধা দিতে পারে।

### Example

ধরা যাক, তুমি একটি program তৈরি করতে চাও, যা Internet থেকে কোনো website-এর response সংগ্রহ করবে।

নিজে সব networking logic তৈরি না করে `requests` package ব্যবহার করতে পারো।

```python
import requests

response = requests.get("https://example.com", timeout=10)

print(response.status_code)
```

এই উদাহরণে `requests` package ব্যবহার করা হয়েছে।

Package install করা না থাকলে `ModuleNotFoundError` হতে পারে। সে ক্ষেত্রে উপযুক্ত Python environment-এ package install করতে হবে।

### Package vs Module vs Library

এই শব্দগুলো কাছাকাছি অর্থে ব্যবহৃত হলেও এদের মধ্যে পার্থক্য রয়েছে।

| Term | Meaning |
|---|---|
| Module | সাধারণত একটি Python file, যেখানে code থাকে |
| Package | সম্পর্কিত Python module সংগঠিত করার একটি উপায় |
| Library | নির্দিষ্ট কাজের জন্য ব্যবহৃত code বা functionality-এর collection |
| Dependency | কোনো project-এর কাজ করার জন্য প্রয়োজনীয় external package বা software |

Python ecosystem-এ একটি library এক বা একাধিক package ও module নিয়ে গঠিত হতে পারে।

---

## 3. What Is pip?

`pip` হলো Python package install ও manage করার একটি বহুল ব্যবহৃত package installer।

এটি Python Package Index (PyPI) থেকে package install করতে পারে। তবে উপযুক্ত configuration থাকলে অন্য package index বা local source থেকেও package install করা সম্ভব।

### Main Uses of pip

- Package install করা।
- Installed package update করা।
- Package uninstall করা।
- Installed package-এর তালিকা দেখা।
- Package-এর নির্দিষ্ট version install করা।
- Project-এর dependency list তৈরি করা।

### Example

```bash
python -m pip --version
```

Windows-এ `python` command কাজ না করলে:

```powershell
py -m pip --version
```

macOS/Linux-এ:

```bash
python3 -m pip --version
```

Output-এর উদাহরণ:

```text
pip 25.0 from ... (python 3.x)
```

তোমার system-এ pip-এর version ও path আলাদা হতে পারে।

### Why Use `python -m pip`?

শুধু `pip` command ব্যবহার করলেও package install করা যায়। তবে:

```bash
python -m pip
```

পদ্ধতিতে `pip`-কে নির্দিষ্ট `python` interpreter-এর মাধ্যমে চালানো হয়।

এর ফলে কোন Python installation-এর জন্য package manage করা হচ্ছে, তা নিয়ন্ত্রণ করা সহজ হয়।

**Best practice:** Beginner হিসেবে `python -m pip` ব্যবহার করার অভ্যাস গড়ে তোলো। Windows-এ প্রয়োজনে `py -m pip` এবং macOS/Linux-এ `python3 -m pip` ব্যবহার করতে পারো।

---

## 4. Checking Whether pip Is Installed

Package install করার আগে pip কাজ করছে কি না যাচাই করো।

### Windows

```powershell
python -m pip --version
```

অথবা:

```powershell
py -m pip --version
```

### macOS/Linux

```bash
python3 -m pip --version
```

যদি pip-এর version ও location দেখা যায়, তাহলে command সফল হয়েছে।

### What If pip Is Not Available?

যদি এমন error পাও:

```text
No module named pip
```

তাহলে সংশ্লিষ্ট Python installation-এ pip অনুপস্থিত থাকতে পারে।

কিছু Python installation-এ `ensurepip` module ব্যবহার করে pip bootstrap করা যায়:

```bash
python -m ensurepip --upgrade
```

Windows-এ প্রয়োজনে:

```powershell
py -m ensurepip --upgrade
```

macOS/Linux-এ সংশ্লিষ্ট interpreter-এর জন্য:

```bash
python3 -m ensurepip --upgrade
```

তবে সব Python distribution-এ `ensurepip` উপলভ্য থাকে না। Linux-এর কিছু distribution-এ package manager দিয়ে pip install করতে হয়।

**সতর্কতা:** Operating system-এর system-managed Python installation-এ package install করার সময় distribution-এর নির্দেশনা অনুসরণ করো। সাধারণ project-এর জন্য virtual environment ব্যবহার করা বেশি নিরাপদ।

---

## 5. Installing Your First Package

এখন একটি package install করা শিখি।

আমরা `requests` package ব্যবহার করব।

### Step 1: Open the Terminal

VS Code-এ তোমার project folder open করো।

এরপর:

`Terminal > New Terminal`

### Step 2: Check the Python Interpreter

Windows:

```powershell
python --version
```

অথবা:

```powershell
py --version
```

macOS/Linux:

```bash
python3 --version
```

### Step 3: Install the Package

Windows:

```powershell
python -m pip install requests
```

প্রয়োজনে:

```powershell
py -m pip install requests
```

macOS/Linux:

```bash
python3 -m pip install requests
```

Installation সম্পন্ন হলে সাধারণত success message দেখা যাবে।

### Step 4: Verify the Installation

```bash
python -m pip show requests
```

Windows-এ `python` command-এর পরিবর্তে `py` এবং macOS/Linux-এ `python3` ব্যবহার করতে পারো।

এই command package-এর name, version, location এবং অন্যান্য metadata দেখায়।

### Step 5: Test the Package

একটি `test_requests.py` file তৈরি করো:

```python
import requests

print(requests.__version__)
```

File-টি run করো:

```bash
python test_requests.py
```

যদি package সঠিক interpreter-এ install করা থাকে, তাহলে version দেখা যাবে।

**মনে রাখবে:** Package install সফল হলেও অন্য Python interpreter বা virtual environment থেকে চালালে package পাওয়া নাও যেতে পারে।

---

## 6. Installing Multiple Packages

একটি project-এ একাধিক package দরকার হতে পারে।

যেমন:

```bash
python -m pip install requests numpy pandas
```

এখানে তিনটি package install করার চেষ্টা করা হবে:

- `requests`
- `numpy`
- `pandas`

Windows-এ প্রয়োজনে:

```powershell
py -m pip install requests numpy pandas
```

macOS/Linux-এ:

```bash
python3 -m pip install requests numpy pandas
```

একসঙ্গে একাধিক package install করা যায়।

তবে বড় project-এর ক্ষেত্রে package-গুলো virtual environment-এর মধ্যে install করা উচিত। Virtual environment আমরা পরবর্তী topic-এ বিস্তারিত শিখব।

---

## 7. Installing a Specific Package Version

কোনো project-এর জন্য package-এর নির্দিষ্ট version প্রয়োজন হতে পারে।

এক্ষেত্রে version specifier ব্যবহার করা যায়।

### Example

```bash
python -m pip install requests==2.32.3
```

এখানে `==` দিয়ে নির্দিষ্ট version চাওয়া হয়েছে।

তবে এই উদাহরণটি একটি নির্দিষ্ট version-এর syntax বোঝানোর জন্য। তোমার Python version, platform, package availability এবং project requirements-এর সঙ্গে version-টি সামঞ্জস্যপূর্ণ কি না, তা যাচাই করতে হবে।

### Common Version Specifiers

| Operator | Meaning |
|---|---|
| `==` | নির্দিষ্ট version |
| `>=` | নির্দিষ্ট version বা তার চেয়ে নতুন |
| `<=` | নির্দিষ্ট version বা তার চেয়ে পুরোনো |
| `>` | নির্দিষ্ট version-এর চেয়ে নতুন |
| `<` | নির্দিষ্ট version-এর চেয়ে পুরোনো |
| `!=` | নির্দিষ্ট version বাদ দিয়ে অন্য version |

উদাহরণ:

```bash
python -m pip install "requests>=2.30"
```

এটি `requests`-এর অন্তত `2.30` version চায়।

**গুরুত্বপূর্ণ:** `>=` ব্যবহার করলে সব সময় একই version install হবে না। Reproducible project-এর জন্য dependency version কীভাবে নির্ধারণ করা হচ্ছে, তা গুরুত্বপূর্ণ।

---

## 8. Upgrading a Package

কোনো package-এর নতুন version install করতে `--upgrade` ব্যবহার করা যায়।

উদাহরণ:

```bash
python -m pip install --upgrade requests
```

Windows-এ প্রয়োজনে:

```powershell
py -m pip install --upgrade requests
```

macOS/Linux-এ:

```bash
python3 -m pip install --upgrade requests
```

এটি সংশ্লিষ্ট environment-এ `requests`-এর উপযুক্ত নতুন version install করার চেষ্টা করবে।

### Checking the Installed Version

```bash
python -m pip show requests
```

Output-এ `Version` field দেখতে পারবে।

### Should Every Package Always Be Upgraded?

না।

Package update করার আগে বিবেচনা করো:

- নতুন version project-এর সঙ্গে compatible কি না।
- অন্য dependency-এর সঙ্গে conflict হতে পারে কি না।
- কোনো breaking change রয়েছে কি না।
- Existing code ও test সঠিকভাবে কাজ করছে কি না।

বিশেষ করে production project-এ যাচাই না করে সব dependency update করা উচিত নয়।

---

## 9. Uninstalling a Package

কোনো package আর প্রয়োজন না হলে uninstall করা যায়।

উদাহরণ:

```bash
python -m pip uninstall requests
```

pip সাধারণত confirmation চাইবে।

Confirmation দিলে package uninstall হবে।

### Uninstall Without Confirmation

```bash
python -m pip uninstall -y requests
```

`-y` option confirmation prompt-এ স্বয়ংক্রিয়ভাবে yes দেয়।

এটি automation-এ কাজে লাগতে পারে, তবে সতর্কভাবে ব্যবহার করতে হবে।

### Important Warning

Package uninstall করার আগে নিশ্চিত হও যে:

- সঠিক Python environment selected আছে।
- অন্য project একই environment-এর package ব্যবহার করছে না।
- Package-টি প্রয়োজনীয় dependency কি না।

Virtual environment ব্যবহার করলে একটি project-এর package অন্য project থেকে আলাদা রাখা সহজ হয়।

---

## 10. Listing Installed Packages

কোন Python environment-এ কোন package install করা আছে, তা দেখতে:

```bash
python -m pip list
```

Output-এর উদাহরণ:

```text
Package    Version
---------- -------
pip        25.0
requests   2.x
urllib3    2.x
```

এখানে version-গুলো উদাহরণস্বরূপ দেখানো হয়েছে। বাস্তবে installed version ভিন্ন হতে পারে।

### Why Is `pip list` Useful?

- Installed package দেখতে।
- Package update হয়েছে কি না যাচাই করতে।
- Dependency সম্পর্কে ধারণা পেতে।
- Environment debugging করতে।

### Showing Package Details

```bash
python -m pip show requests
```

এই command একটি package সম্পর্কে আরও বিস্তারিত তথ্য দেয়।

### Checking Dependency Relationships

```bash
python -m pip check
```

এই command installed package-গুলোর declared dependency requirement-এর মধ্যে incompatibility আছে কি না পরীক্ষা করে।

তবে `pip check` সফল হলেই project-এর সব code সঠিকভাবে কাজ করবে, এমন নিশ্চয়তা নেই।

---

## 11. Understanding PyPI

PyPI-এর পূর্ণরূপ হলো **Python Package Index**।

এটি Python package প্রকাশ ও বিতরণের একটি জনপ্রিয় repository।

Website:

https://pypi.org/

PyPI-তে তুমি:

- Package খুঁজতে পারো।
- Documentation ও project link দেখতে পারো।
- Package-এর version history দেখতে পারো।
- Installation command জানতে পারো।
- Python version compatibility সম্পর্কে তথ্য পেতে পারো।

### Example: Searching for a Package

ধরা যাক, তুমি `requests` package সম্পর্কে জানতে চাও।

PyPI-তে খুঁজে দেখতে পারো:

https://pypi.org/project/requests/

সেখানে package-এর description, version, dependencies এবং installation instructions পাওয়া যেতে পারে।

### Security Warning

Internet থেকে যেকোনো package install করা উচিত নয়।

Package install করার আগে:

1. Package-এর নাম সঠিক কি না যাচাই করো।
2. Official documentation দেখো।
3. Project-এর maintenance ও reputation সম্পর্কে খোঁজ নাও।
4. অপ্রয়োজনীয় package install করা এড়িয়ে চলো।
5. অজানা source থেকে code install করার আগে সতর্ক হও।

ভুল নামের package বা malicious package install করলে security risk তৈরি হতে পারে।

---

## 12. Using `requirements.txt`

Python project-এ কোন কোন external package দরকার, তা `requirements.txt` file-এ লেখা যায়।

এটি project-এর dependency list হিসেবে কাজ করে।

### Example Project Structure

```text
MyPythonProject/
├── main.py
├── requirements.txt
└── README.md
```

### Example `requirements.txt`

```text
requests
numpy
pandas
```

প্রতিটি line-এ একটি dependency লেখা হয়েছে।

### Installing Dependencies

Project folder-এর Terminal-এ চালাও:

```bash
python -m pip install -r requirements.txt
```

এখানে:

- `-r` option একটি requirements file পড়তে বলে।
- `requirements.txt` হলো dependency list-এর file name।

Windows-এ প্রয়োজনে `py -m pip` এবং macOS/Linux-এ `python3 -m pip` ব্যবহার করতে পারো।

### Specifying Versions

নির্দিষ্ট version উল্লেখ করাও সম্ভব:

```text
requests==2.32.3
numpy>=1.26
```

এখানে `requests`-এর নির্দিষ্ট version এবং `numpy`-এর একটি minimum version উল্লেখ করা হয়েছে। এগুলো ব্যবহার করার আগে তোমার project-এর compatibility যাচাই করতে হবে।

### Generating a Requirements File

বর্তমান environment-এর installed package list থেকে একটি file তৈরি করতে পারো:

```bash
python -m pip freeze > requirements.txt
```

এটি environment-এ থাকা package ও version-গুলোর তালিকা file-এ লিখে দেয়।

**গুরুত্বপূর্ণ:** `pip freeze` environment-এর সব relevant package project-এর direct dependency হিসেবে আলাদা করে চিহ্নিত করে না। তাই project-এর virtual environment ব্যবহার করা ভালো এবং generated list প্রয়োজনে review করা উচিত।

---

## 13. Understanding Package Dependencies

একটি package কাজ করার জন্য অন্য package-এর ওপর নির্ভর করতে পারে।

এগুলোকে dependency বলা হয়।

উদাহরণ:

```text
Your Project
    |
    v
Package A
    |
    v
Package B
```

এখানে:

- তোমার project `Package A` ব্যবহার করছে।
- `Package A` কাজ করার জন্য `Package B` প্রয়োজন।

সাধারণভাবে pip package install করার সময় তার declared dependencies-ও install করার চেষ্টা করে।

### Why Can Dependency Conflicts Happen?

ধরা যাক:

- Package A একটি dependency-এর পুরোনো version চায়।
- Package B একই dependency-এর নতুন version চায়।

এক্ষেত্রে version conflict হতে পারে।

সমাধানের জন্য:

- Compatible package version নির্বাচন করতে হবে।
- Virtual environment ব্যবহার করতে হবে।
- Package documentation ও dependency requirements যাচাই করতে হবে।
- `python -m pip check` দিয়ে installed dependency consistency পরীক্ষা করতে হবে।

শুধু installation সফল হওয়া মানেই application-এর সব dependency ও functionality ঠিক আছে, এমন নয়।

---

## 14. The Relationship Between pip and Virtual Environments

এটি খুব গুরুত্বপূর্ণ একটি বিষয়।

ধরা যাক, তোমার দুটি project রয়েছে:

```text
Project_A/
Project_B/
```

`Project_A`-এর জন্য `requests`-এর একটি version দরকার, আর `Project_B`-এর জন্য অন্য version দরকার হতে পারে।

যদি সব package একই global Python environment-এ install করো, তাহলে version conflict বা dependency management-এর সমস্যা হতে পারে।

Virtual environment প্রতিটি project-এর dependency আলাদা রাখতে সাহায্য করে।

### Example Workflow

প্রথমে project folder-এ যাও:

```bash
cd MyPythonProject
```

Virtual environment তৈরি করো:

```bash
python -m venv .venv
```

এরপর environment activate করো।

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

Windows Command Prompt:

```bat
.venv\Scripts\activate.bat
```

macOS/Linux:

```bash
source .venv/bin/activate
```

এরপর package install করো:

```bash
python -m pip install requests
```

এখন package-টি active virtual environment-এ install হবে।

Virtual environment তৈরি, activate, deactivate ও manage করার বিস্তারিত পরবর্তী topic-এ শিখব।

**Best practice:** সাধারণ Python project-এর package global বা system-managed environment-এ install না করে project-specific virtual environment-এ install করো।

---

## 15. Common pip Errors and Solutions

### Error 1: `No module named pip`

সম্ভাব্য কারণ:

- সংশ্লিষ্ট Python installation-এ pip নেই।
- ভুল interpreter ব্যবহার করা হচ্ছে।

সমাধান:

```bash
python -m ensurepip --upgrade
```

এটি সমর্থিত installation-এ কাজ করতে পারে। অন্য ক্ষেত্রে official Python বা operating system-এর নির্দেশনা অনুসরণ করতে হবে।

### Error 2: `No matching distribution found`

সম্ভাব্য কারণ:

- Package name ভুল।
- চাওয়া version পাওয়া যাচ্ছে না।
- Python version বা platform package-এর সঙ্গে compatible নয়।
- Package index-এ উপযুক্ত distribution নেই।

সমাধান:

1. Package name যাচাই করো।
2. PyPI-তে package ও version খুঁজে দেখো।
3. Python version যাচাই করো।
4. Package-এর supported platform ও installation instructions পড়ো।

### Error 3: `ModuleNotFoundError`

উদাহরণ:

```python
import requests
```

কিন্তু output:

```text
ModuleNotFoundError: No module named 'requests'
```

সম্ভাব্য কারণ:

- Package install করা নেই।
- Package অন্য interpreter-এ install হয়েছে।
- Virtual environment activate করা নেই।

সমাধান:

```bash
python -m pip show requests
```

তারপর নিশ্চিত হও যে package installation এবং program execution একই interpreter ব্যবহার করছে।

### Error 4: Permission Denied

সম্ভাব্য কারণ:

- নির্দিষ্ট directory-তে write permission নেই।
- System-managed Python environment-এ package install করার চেষ্টা হচ্ছে।

সমাধান:

- Virtual environment ব্যবহার করো।
- সঠিক directory ও permission যাচাই করো।
- System Python-এর package management policy অনুসরণ করো।

সাধারণ project-এর ক্ষেত্রে শুধু permission error এড়ানোর জন্য administrator বা root হিসেবে pip চালানো উচিত নয়।

### Error 5: Network Error

সম্ভাব্য কারণ:

- Internet connection নেই।
- Proxy বা firewall বাধা দিচ্ছে।
- Package index সাময়িকভাবে unavailable।

সমাধান:

1. Internet connection যাচাই করো।
2. Official package index ও network access পরীক্ষা করো।
3. Proxy ব্যবহার করলে সঠিক configuration যাচাই করো।
4. পরে আবার চেষ্টা করো।

### Error 6: `pip` and `python` Refer to Different Installations

সম্ভাব্য কারণ:

- একাধিক Python installation আছে।
- Terminal-এর PATH configuration ভিন্ন।
- Virtual environment-এর interpreter selected নেই।

সমাধান:

```bash
python --version
python -m pip --version
python -c "import sys; print(sys.executable)"
```

এগুলো থেকে Python version, pip-এর location এবং Python executable সম্পর্কে ধারণা পাবে।

---

## 16. Best Practices

1. Package install করার আগে সঠিক Python interpreter নির্বাচন করো।
2. `python -m pip` ব্যবহার করার অভ্যাস গড়ে তোলো।
3. সাধারণ project-এর জন্য virtual environment ব্যবহার করো।
4. Package-এর official documentation পড়ো।
5. অপ্রয়োজনীয় package install করা এড়িয়ে চলো।
6. Project-এর dependency `requirements.txt`-এ document করো।
7. Update করার আগে compatibility যাচাই করো।
8. Package uninstall করার আগে সেটি অন্য code ব্যবহার করছে কি না দেখো।
9. System-managed Python environment-এ সতর্ক থাকো।
10. Error message পড়ে কারণ বোঝার চেষ্টা করো।
11. Package install করার সময় source ও package name যাচাই করো।
12. Production project-এ dependency version ও testing-এর ওপর গুরুত্ব দাও।

---

## 17. Practical Exercises

### Exercise 1: Check pip

Terminal-এ চালাও:

```bash
python -m pip --version
```

তোমার system-এ প্রয়োজন অনুযায়ী `py` বা `python3` ব্যবহার করো।

### Exercise 2: Install a Package

Virtual environment ব্যবহার করে install করো:

```bash
python -m pip install requests
```

### Exercise 3: Verify Installation

```bash
python -m pip show requests
```

Output-এ package name, version এবং location খুঁজে বের করো।

### Exercise 4: Import the Package

`test_requests.py` তৈরি করো:

```python
import requests

print(requests.__version__)
```

File-টি run করো এবং output যাচাই করো।

### Exercise 5: List Installed Packages

```bash
python -m pip list
```

তোমার environment-এ কোন package install আছে, তা দেখো।

### Exercise 6: Check Dependencies

```bash
python -m pip check
```

কোনো dependency incompatibility report হচ্ছে কি না দেখো।

### Exercise 7: Create a Requirements File

`requirements.txt` তৈরি করো:

```text
requests
```

তারপর চালাও:

```bash
python -m pip install -r requirements.txt
```

### Exercise 8: Explore Package Documentation

PyPI-তে `requests` package-এর page দেখো:

https://pypi.org/project/requests/

Package-এর purpose, installation instructions এবং documentation link খুঁজে বের করো।

---

## 18. Quick Revision

| Term | Meaning |
|---|---|
| `pip` | Python package install ও manage করার tool |
| Package | নির্দিষ্ট functionality প্রদানকারী code collection |
| PyPI | Python Package Index |
| `pip install` | Package install করে |
| `pip install --upgrade` | Package update করার চেষ্টা করে |
| `pip uninstall` | Package uninstall করে |
| `pip list` | Installed package-এর তালিকা দেখায় |
| `pip show` | নির্দিষ্ট package-এর details দেখায় |
| `pip check` | Dependency compatibility পরীক্ষা করে |
| `requirements.txt` | Project dependency list |
| Dependency | Project-এর প্রয়োজনীয় package বা software |
| Virtual Environment | আলাদা Python project environment |
| `python -m pip` | নির্দিষ্ট Python interpreter-এর মাধ্যমে pip চালায় |

---

## 19. Chapter Connection

এই topic-এ আমরা `pip`, Python package, PyPI, package installation, version management, dependency এবং `requirements.txt` সম্পর্কে শিখেছি।

এখন তুমি package install ও manage করার মৌলিক কাজগুলো করতে পারবে।

তবে বাস্তব project-এ package install করার আগে virtual environment ব্যবহার করা গুরুত্বপূর্ণ।

**Next Topic:** [19. Creating and Managing Virtual Environments](19_Creating_and_Managing_Virtual_Environments.md)