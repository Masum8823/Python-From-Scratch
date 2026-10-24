# 20. Installing Packages in a Virtual Environment

## 1. Introduction

আগের topic-এ আমরা শিখেছি কীভাবে virtual environment তৈরি, activate এবং deactivate করতে হয়।

এখন শিখব কীভাবে সেই environment-এর মধ্যে Python package install ও manage করতে হয়।

ধরা যাক, তুমি একটি Python project তৈরি করেছ, যেখানে `requests` package ব্যবহার করতে হবে। Package-টি global Python installation-এ install না করে project-এর virtual environment-এ install করাই ভালো।

এই topic-এ আমরা শিখব:

1. সঠিক virtual environment নির্বাচন করা।
2. Environment activate করা।
3. Package install ও verify করা।
4. নির্দিষ্ট version install করা।
5. Package update ও uninstall করা।
6. `requirements.txt` তৈরি ও ব্যবহার করা।
7. Dependency conflict ও installation error সমাধান করা।
8. একটি সম্পূর্ণ practical workflow তৈরি করা।

---

## 2. Understanding the Workflow

একটি Python project-এ package ব্যবহারের সাধারণ workflow হলো:

```text
Create Project Folder
        |
        v
Create Virtual Environment
        |
        v
Activate Environment
        |
        v
Install Required Packages
        |
        v
Verify Installation
        |
        v
Write and Run Python Code
        |
        v
Save Dependencies
```

এই ধাপগুলো অনুসরণ করলে package management অনেক বেশি organized হয়।

### Example Project Structure

```text
MyPythonProject/
├── .venv/
├── main.py
├── requirements.txt
├── .gitignore
└── README.md
```

এখানে:

- `.venv/` — project-এর virtual environment।
- `main.py` — মূল Python program।
- `requirements.txt` — external dependency list।
- `.gitignore` — Git-এ কোন file track করা হবে না, তা নির্ধারণ করে।
- `README.md` — project-এর পরিচিতি ও নির্দেশনা।

---

## 3. Step 1: Open the Project Folder

প্রথমে তোমার project folder তৈরি করো অথবা আগে থেকে থাকা project folder open করো।

উদাহরণ:

```bash
mkdir MyPythonProject
cd MyPythonProject
```

এরপর VS Code-এ folder-টি open করো।

VS Code-এর Terminal খুলতে:

`Terminal > New Terminal`

Terminal যেন project-এর root folder-এ থাকে, তা নিশ্চিত করো।

Project root হলো সেই প্রধান folder, যেখানে project-এর মূল file ও configuration থাকে।

---

## 4. Step 2: Create a Virtual Environment

Project folder-এর Terminal-এ চালাও:

```bash
python -m venv .venv
```

Windows-এ `python` command কাজ না করলে:

```powershell
py -m venv .venv
```

macOS/Linux-এ প্রয়োজনে:

```bash
python3 -m venv .venv
```

Command সফল হলে project folder-এর মধ্যে `.venv` directory তৈরি হবে।

### Verify the Environment Folder

Project structure এমন হতে পারে:

```text
MyPythonProject/
├── .venv/
└──
```

`.venv` folder-এর মধ্যে environment-এর প্রয়োজনীয় file তৈরি হবে।

**মনে রাখবে:** একই project-এ environment আগে থেকেই তৈরি থাকলে সাধারণত প্রতিবার নতুন করে তৈরি করতে হয় না।

---

## 5. Step 3: Activate the Virtual Environment

Package install করার আগে environment activate করো।

### Windows PowerShell

```powershell
.\.venv\Scripts\Activate.ps1
```

### Windows Command Prompt

```bat
.venv\Scripts\activate.bat
```

### macOS/Linux

```bash
source .venv/bin/activate
```

Activation সফল হলে Terminal prompt-এ সাধারণত `(.venv)` দেখা যায়।

উদাহরণ:

```text
(.venv) C:\Projects\MyPythonProject>
```

Prompt-এর format system ও shell অনুযায়ী ভিন্ন হতে পারে।

### Verify the Active Interpreter

```bash
python -c "import sys; print(sys.executable)"
```

Output-এ `.venv`-এর ভেতরের Python executable-এর path থাকা উচিত।

এটি যাচাই করা গুরুত্বপূর্ণ, কারণ ভুল interpreter ব্যবহার করলে package ভুল environment-এ install হতে পারে।

---

## 6. Step 4: Install a Package

এখন environment active থাকা অবস্থায় `requests` package install করো।

```bash
python -m pip install requests
```

এই command-এর অংশগুলো:

- `python` — active Python interpreter।
- `-m pip` — ওই interpreter-এর মাধ্যমে pip চালায়।
- `install` — package install করার নির্দেশ।
- `requests` — package-এর নাম।

Installation সম্পন্ন হলে সাধারণত success message দেখা যাবে।

### Why Install Inside the Virtual Environment?

Environment active থাকলে `python -m pip` সাধারণত সেই environment-এর package installer ব্যবহার করে।

ফলে package-টি project-এর environment-এ install হয়।

এতে অন্য project-এর dependency অপ্রয়োজনীয়ভাবে পরিবর্তিত হওয়ার ঝুঁকি কমে।

---

## 7. Step 5: Verify the Installed Package

Package install করার পর যাচাই করা উচিত যে সেটি সঠিক environment-এ install হয়েছে কি না।

### Method 1: Use `pip show`

```bash
python -m pip show requests
```

এখানে সাধারণত দেখা যাবে:

- Name
- Version
- Summary
- Location
- Dependencies-এর তথ্য

`Location` field-এ package-এর installation directory দেখা যায়।

Directory-টি `.venv`-এর সঙ্গে সম্পর্কিত কি না যাচাই করো।

### Method 2: Use `pip list`

```bash
python -m pip list
```

এটি active environment-এ install করা package-এর তালিকা দেখায়।

### Method 3: Import the Package

একটি Python file তৈরি করো:

`main.py`

```python
import requests

print("Requests version:", requests.__version__)
```

Program চালাও:

```bash
python main.py
```

Package সঠিকভাবে install করা থাকলে তার version print হবে।

### Method 4: Check the Python Executable

```bash
python -c "import sys; print(sys.executable)"
```

এটি program কোন Python interpreter ব্যবহার করছে, তা দেখায়।

**Best practice:** শুধু installation success message-এর ওপর নির্ভর না করে package-এর location ও import দুটোই যাচাই করো।

---

## 8. Installing Multiple Packages

একটি project-এ একাধিক package প্রয়োজন হতে পারে।

উদাহরণ:

```bash
python -m pip install requests numpy pandas
```

এই command তিনটি package install করার চেষ্টা করবে।

| Package | Common Use |
|---|---|
| `requests` | HTTP request পাঠানো |
| `numpy` | Numerical calculation |
| `pandas` | Data analysis |

এই package-গুলো একই virtual environment-এ install হবে।

### Verify All Packages

```bash
python -m pip list
```

অথবা একটি নির্দিষ্ট package-এর জন্য:

```bash
python -m pip show numpy
```

একাধিক package install করার পর project-এর code ও tests চালিয়ে compatibility যাচাই করো।

---

## 9. Installing a Specific Version

কখনো project-এর জন্য নির্দিষ্ট package version প্রয়োজন হয়।

এক্ষেত্রে version specifier ব্যবহার করা যায়।

### Example

```bash
python -m pip install requests==2.32.3
```

এখানে `==` নির্দিষ্ট version নির্দেশ করে।

এই version-টি উদাহরণ হিসেবে দেওয়া হয়েছে। তোমার project-এর সঙ্গে compatibility যাচাই করে version নির্বাচন করবে।

### Common Version Specifiers

| Specifier | Meaning |
|---|---|
| `==2.32.3` | নির্দিষ্ট version |
| `>=2.30` | অন্তত 2.30 version |
| `<3.0` | 3.0-এর চেয়ে পুরোনো version |
| `!=2.31.0` | 2.31.0 বাদে অন্য version |

উদাহরণ:

```bash
python -m pip install "requests>=2.30,<3.0"
```

এখানে package version-কে একটি নির্দিষ্ট range-এর মধ্যে সীমাবদ্ধ করা হয়েছে।

**গুরুত্বপূর্ণ:** Version range অনুমোদিত হলেও প্রতিবার একই package version install হবে, এমন নিশ্চয়তা নেই।

---

## 10. Upgrading a Package

Package-এর নতুন version install করতে:

```bash
python -m pip install --upgrade requests
```

এই command active environment-এ `requests`-এর উপযুক্ত নতুন version install করার চেষ্টা করবে।

### Check the New Version

```bash
python -m pip show requests
```

Output-এর `Version` field দেখো।

### Should You Upgrade Every Package?

সব package অন্ধভাবে update করা উচিত নয়।

কারণ:

- নতুন version-এ breaking changes থাকতে পারে।
- অন্য dependency-এর সঙ্গে conflict হতে পারে।
- Project-এর code পুরোনো version-এর ওপর নির্ভর করতে পারে।

Update করার পরে relevant tests চালিয়ে নিশ্চিত হও যে project ঠিকভাবে কাজ করছে।

---

## 11. Uninstalling a Package

কোনো package আর প্রয়োজন না হলে:

```bash
python -m pip uninstall requests
```

pip সাধারণত confirmation চাইবে।

Confirmation দিলে package uninstall হবে।

### Verify the Uninstallation

```bash
python -m pip show requests
```

Package-টি আর install না থাকলে সাধারণত package not found ধরনের message দেখা যাবে।

এরপর `requests` import করা code চালালে `ModuleNotFoundError` হতে পারে।

তাই কোনো package uninstall করার আগে নিশ্চিত হও যে project-এর code সেটি ব্যবহার করছে না।

---

## 12. Creating a `requirements.txt` File

`requirements.txt` হলো একটি সাধারণ text file, যেখানে project-এর dependency ও প্রয়োজনে তাদের version specification লেখা থাকে।

Project root-এ file তৈরি করো:

```text
MyPythonProject/
├── .venv/
├── main.py
└── requirements.txt
```

### Example Content

```text
requests
numpy
pandas
```

এখানে তিনটি package-এর নাম লেখা হয়েছে।

### Why Is This File Useful?

- Project-এর dependency document করা যায়।
- নতুন environment setup করা সহজ হয়।
- অন্য developer project-এর প্রয়োজনীয় package জানতে পারে।
- একই project একাধিক computer-এ setup করা সহজ হয়।

তবে শুধু package-এর নাম থাকলে installation-এর সময় উপযুক্ত version ভিন্ন হতে পারে।

---

## 13. Installing Packages from `requirements.txt`

ধরা যাক, `requirements.txt`-এ লেখা আছে:

```text
requests
numpy
pandas
```

Environment activate করার পর চালাও:

```bash
python -m pip install -r requirements.txt
```

এখানে:

- `install` package install করে।
- `-r` requirements file পড়তে বলে।
- `requirements.txt` dependency list-এর file।

pip file-টি পড়ে listed package-গুলো install করার চেষ্টা করবে।

### Important

Command চালানোর আগে:

1. সঠিক project folder-এ থাকো।
2. সঠিক virtual environment activate করো।
3. `requirements.txt` file-এর নাম ও location যাচাই করো।
4. Package version ও Python compatibility সম্পর্কে নিশ্চিত হও।

---

## 14. Generating a `requirements.txt` File

Active environment-এর installed package-গুলোর version-সহ তালিকা তৈরি করতে পারো:

```bash
python -m pip freeze > requirements.txt
```

এই command:

1. `pip freeze` দিয়ে installed distribution ও version-এর তালিকা তৈরি করে।
2. `>` দিয়ে output-কে `requirements.txt` file-এ লেখে।
3. File আগে থেকে থাকলে সাধারণত তার আগের content replace করে।

### Example Output

```text
requests==2.x
urllib3==2.x
certifi==202x.x.x
```

এখানে `x`-যুক্ত version-গুলো শুধু illustrative placeholder।

বাস্তবে command চালালে actual installed version লেখা হবে।

### Important Limitation of `pip freeze`

`pip freeze` সাধারণত environment-এর installed package-গুলো version-সহ তালিকাভুক্ত করে। কিন্তু কোন package সরাসরি তোমার project-এর জন্য install করা হয়েছিল আর কোনটি অন্য package-এর dependency হিসেবে এসেছে, তা আলাদা করে চিহ্নিত করে না।

তাই:

- Project-এর dedicated virtual environment ব্যবহার করো।
- Generated file review করো।
- Unnecessary package থাকলে পরিষ্কার করো।
- Production project-এ dependency ও version management আরও পরিকল্পিতভাবে করো।

---

## 15. Understanding Direct and Transitive Dependencies

Dependency সাধারণত দুইভাবে বোঝানো যায়।

### Direct Dependency

যে package তুমি সরাসরি তোমার project-এ ব্যবহার করো।

উদাহরণ:

```python
import requests
```

এখানে `requests` তোমার project-এর direct dependency।

### Transitive Dependency

যে package অন্য একটি dependency-এর কাজ করার জন্য প্রয়োজন হয়।

ধরা যাক:

```text
Your Project
    |
    v
requests
    |
    v
urllib3
```

এখানে `urllib3` হলো `requests`-এর dependency হিসেবে ব্যবহৃত একটি package।

তোমার project সরাসরি `urllib3` import না করলেও `requests`-এর কাজের জন্য এটি প্রয়োজন হতে পারে।

### Why Does This Matter?

Package update বা uninstall করার সময় dependency relationship বুঝতে হয়।

এছাড়া `requirements.txt`-এ কী রাখা উচিত, সেটি ঠিক করতেও এই পার্থক্য গুরুত্বপূর্ণ।

---

## 16. Checking Dependency Compatibility

কোনো environment-এ package-গুলোর declared dependency requirement-এর মধ্যে incompatibility আছে কি না পরীক্ষা করতে:

```bash
python -m pip check
```

সমস্যা না থাকলে সাধারণত এমন output দেখা যায়:

```text
No broken requirements found.
```

কোনো conflict থাকলে pip সংশ্লিষ্ট package ও requirement সম্পর্কে message দিতে পারে।

### Does `pip check` Guarantee That the Project Works?

না।

এটি dependency metadata-এর compatibility পরীক্ষা করে। কিন্তু তোমার program-এর logic, API behavior, runtime error বা সব ধরনের incompatibility পরীক্ষা করে না।

তাই package install বা update করার পরে:

- `pip check` চালাও।
- Program run করো।
- Unit test থাকলে চালাও।
- গুরুত্বপূর্ণ functionality যাচাই করো।

---

## 17. Using the Correct Environment in VS Code

VS Code-এ ভুল interpreter selected থাকলে package install করার পরও program-এ `ModuleNotFoundError` দেখা দিতে পারে।

### Step 1: Select the Interpreter

Command Palette খুলতে:

`Ctrl + Shift + P`

macOS-এ:

`Cmd + Shift + P`

তারপর নির্বাচন করো:

`Python: Select Interpreter`

Project-এর `.venv`-এর interpreter নির্বাচন করো।

### Step 2: Open a New Terminal

VS Code-এর Terminal-এ নতুন session খুললে environment activation ও PATH-এর অবস্থা যাচাই করা সহজ হয়।

### Step 3: Verify the Interpreter

```bash
python -c "import sys; print(sys.executable)"
```

### Step 4: Verify pip

```bash
python -m pip --version
```

দুটি output-ই সঠিক virtual environment-এর সঙ্গে সম্পর্কিত কি না যাচাই করো।

### Step 5: Test the Package

```bash
python -c "import requests; print(requests.__version__)"
```

এই command সফল হলে নির্বাচিত interpreter-এ `requests` import করা যাচ্ছে।

---

## 18. A Complete Practical Example

এখন একটি ছোট project-এর সম্পূর্ণ workflow অনুশীলন করি।

### Step 1: Create the Folder

```bash
mkdir PackagePractice
cd PackagePractice
```

### Step 2: Create the Environment

Windows:

```powershell
py -m venv .venv
```

macOS/Linux:

```bash
python3 -m venv .venv
```

### Step 3: Activate the Environment

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### Step 4: Install `requests`

```bash
python -m pip install requests
```

### Step 5: Create `main.py`

```python
import requests

print("Requests version:", requests.__version__)

response = requests.get(
    "https://example.com",
    timeout=10
)

print("Status code:", response.status_code)
```

### Step 6: Run the Program

```bash
python main.py
```

প্রথমে package version print হবে। এরপর program Internet-এর মাধ্যমে একটি HTTP request পাঠানোর চেষ্টা করবে।

Request সফল হলে status code দেখা যাবে। Network error বা timeout হলে request ব্যর্থ হতে পারে।

### Step 7: Create `requirements.txt`

```bash
python -m pip freeze > requirements.txt
```

File-টি open করে generated dependency list দেখো।

### Step 8: Check Dependencies

```bash
python -m pip check
```

### Step 9: Deactivate

```bash
deactivate
```

এভাবে তুমি একটি project-এ package install, test এবং dependency record করার basic workflow সম্পন্ন করলে।

---

## 19. Common Errors and Solutions

### Error 1: `ModuleNotFoundError`

**কারণ:** Package সঠিক environment-এ install করা নেই, অথবা program অন্য interpreter ব্যবহার করছে।

**সমাধান:**

```bash
python -c "import sys; print(sys.executable)"
python -m pip show requests
```

Interpreter ও package location যাচাই করো।

### Error 2: `Could not open requirements file`

**কারণ:** `requirements.txt` বর্তমান directory-তে নেই অথবা file-এর নাম ভুল।

**সমাধান:**

```bash
python -m pip install -r requirements.txt
```

Command চালানোর আগে নিশ্চিত হও যে Terminal সঠিক project root-এ আছে এবং file-টি সেখানে রয়েছে।

### Error 3: Dependency Conflict

**কারণ:** দুটি বা একাধিক package পরস্পর incompatible version চাইতে পারে।

**সমাধান:**

- Error message পড়ো।
- Package documentation যাচাই করো।
- Compatible version নির্বাচন করো।
- প্রয়োজনে clean virtual environment তৈরি করো।
- Package install করার পর `pip check` ও project tests চালাও।

### Error 4: Permission Error

**কারণ:** System-managed environment বা protected directory-তে package install করার চেষ্টা।

**সমাধান:** Project-specific virtual environment ব্যবহার করো এবং সেটি active আছে কি না যাচাই করো।

### Error 5: Package Version Does Not Match

**কারণ:** অন্য environment ব্যবহার হচ্ছে অথবা dependency file-এ ভিন্ন version লেখা আছে।

**সমাধান:**

```bash
python -m pip show requests
python -m pip --version
python -c "import sys; print(sys.executable)"
```

প্রতিটি output পরীক্ষা করো।

### Error 6: Installation Fails Because of Python Compatibility

**কারণ:** Package-এর নির্দিষ্ট version তোমার Python version বা operating system support নাও করতে পারে।

**সমাধান:**

1. Python version যাচাই করো।
2. Package-এর official documentation পড়ো।
3. Supported version নির্বাচন করো।
4. প্রয়োজন হলে উপযুক্ত Python version দিয়ে নতুন environment তৈরি করো।

---

## 20. Best Practices

1. প্রতিটি project-এর জন্য আলাদা virtual environment ব্যবহার করো।
2. Package install করার আগে সঠিক environment active আছে কি না যাচাই করো।
3. `python -m pip` ব্যবহার করো।
4. Project-এর dependency `requirements.txt`-এ document করো।
5. `pip freeze` output review না করে অন্ধভাবে commit করো না।
6. Package update করার পরে tests চালাও।
7. `pip check` দিয়ে declared dependency compatibility পরীক্ষা করো।
8. `.venv` GitHub-এ upload না করে `.gitignore`-এ রাখো।
9. Package-এর official documentation ও compatibility requirements পড়ো।
10. অজানা package বা source থেকে installation করার আগে security risk বিবেচনা করো।
11. অন্য computer-এ project চালানোর সময় নতুন virtual environment তৈরি করো।
12. Production project-এ dependency version ও installation process নির্ভরযোগ্যভাবে document করো।

---

## 21. Practical Exercises

### Exercise 1: Create an Environment

`PackagePractice` folder-এ `.venv` তৈরি করো।

### Exercise 2: Activate It

তোমার operating system অনুযায়ী activation command ব্যবহার করো।

### Exercise 3: Install a Package

```bash
python -m pip install requests
```

### Exercise 4: Verify Installation

```bash
python -m pip show requests
```

### Exercise 5: Test Import

```bash
python -c "import requests; print(requests.__version__)"
```

### Exercise 6: List Packages

```bash
python -m pip list
```

### Exercise 7: Generate Requirements

```bash
python -m pip freeze > requirements.txt
```

File-এর content পরীক্ষা করো।

### Exercise 8: Reinstall from Requirements

একটি নতুন virtual environment তৈরি করে সেটি activate করো। তারপর:

```bash
python -m pip install -r requirements.txt
```

Package-গুলো install হচ্ছে কি না যাচাই করো।

### Exercise 9: Check Dependencies

```bash
python -m pip check
```

### Exercise 10: Debug an Environment Problem

`requests` অন্য environment-এ install করা আছে বলে ধরে নাও। সঠিক interpreter নির্বাচন করে package-টি import করার সমস্যা সমাধান করো।

---

## 22. Quick Revision

| Command | Purpose |
|---|---|
| `python -m pip install requests` | Package install করে |
| `python -m pip show requests` | Package details দেখায় |
| `python -m pip list` | Installed package list দেখায় |
| `python -m pip install --upgrade requests` | Package update করার চেষ্টা করে |
| `python -m pip uninstall requests` | Package uninstall করে |
| `python -m pip freeze` | Installed package ও version-এর তালিকা দেখায় |
| `python -m pip freeze > requirements.txt` | তালিকা file-এ সংরক্ষণ করে |
| `python -m pip install -r requirements.txt` | Dependency file থেকে package install করে |
| `python -m pip check` | Declared dependency compatibility পরীক্ষা করে |
| `python -c "import sys; print(sys.executable)"` | Python executable-এর path দেখায় |

---

## 23. Chapter Connection

এই topic-এ আমরা virtual environment-এর মধ্যে package install, verify, update, uninstall এবং dependency management শিখেছি।

এখন তুমি একটি Python project-এর dependency list তৈরি করতে এবং `requirements.txt` থেকে package install করতে পারবে।

**Next Topic:** [21. Managing Project Dependencies](21_Managing_Project_Dependencies.md)

পরবর্তী topic-এ আমরা project dependency কীভাবে পরিকল্পনা করতে হয়, direct ও transitive dependency-এর পার্থক্য, version constraints, dependency consistency এবং project অন্য computer-এ setup করার আরও ভালো পদ্ধতি শিখব।