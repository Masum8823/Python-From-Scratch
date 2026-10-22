# 07. Python Version and Interpreter

## 1. Introduction

Python install করার পরে শুধু version check করলেই হবে না; Python version এবং interpreter কীভাবে কাজ করে, সেটাও বুঝতে হবে।

**Python Version** হলো Python programming language-এর নির্দিষ্ট release বা সংস্করণ।

**Python Interpreter** হলো সেই software component, যা Python code execute করে।

এই topic শেষে আমরা শিখব:

- Python version কী।
- Python 2 ও Python 3-এর পার্থক্য।
- Version number কীভাবে বুঝতে হয়।
- Python interpreter কীভাবে কাজ করে।
- একই computer-এ একাধিক Python version থাকলে কী হয়।
- সঠিক interpreter কীভাবে নির্বাচন করতে হয়।
- Python version ও executable path কীভাবে পরীক্ষা করতে হয়।

---

## 2. What Is a Python Version?

Python programming language সময়ের সঙ্গে উন্নত হয়। নতুন feature যোগ করা, bug fix করা এবং security-related সমস্যা সমাধানের জন্য নতুন version release করা হয়।

প্রতিটি release-এর একটি নির্দিষ্ট version number থাকে।

উদাহরণ:

```text
Python 3.10.0
Python 3.11.0
Python 3.12.0
Python 3.13.0
```

এগুলো Python 3-এর বিভিন্ন release-এর উদাহরণ।

সব version একই সময়ে নতুন নয় এবং সব version সমান সময় ধরে supported থাকে না। তাই নতুন project শুরু করার সময় supported version নির্বাচন করা গুরুত্বপূর্ণ।

### Why Do Python Versions Matter?

Python version গুরুত্বপূর্ণ, কারণ:

- নতুন version-এ নতুন feature থাকতে পারে।
- কিছু পুরোনো feature পরিবর্তিত বা সরিয়ে ফেলা হতে পারে।
- কিছু package নির্দিষ্ট Python version চায়।
- Project-এর code এক version-এ কাজ করলেও অন্য version-এ পরিবর্তন প্রয়োজন হতে পারে।
- Security support ও bug fixes version অনুযায়ী আলাদা হয়।

তাই কোনো tutorial বা project অনুসরণ করার সময় Python version requirement যাচাই করা উচিত।

---

## 3. Understanding Python Version Numbers

Python-এর version number সাধারণত এভাবে দেখা যায়:

```text
3.13.2
```

এখানে version number-এর অংশগুলো হলো:

| Part | Example | Meaning |
|---|---|---|
| Major version | `3` | প্রধান version generation |
| Minor version | `13` | নতুন feature ও language changes-সহ release series |
| Patch version | `2` | Bug fixes ও অন্যান্য maintenance changes |

এই format-কে `MAJOR.MINOR.PATCH` বলা হয়।

### Example 1: Python 3.13.2

- `3` হলো major version।
- `13` হলো minor version।
- `2` হলো patch version।

### Example 2: Python 3.12.8 and Python 3.12.9

এই দুটি একই minor release series-এর অন্তর্ভুক্ত, কিন্তু patch version আলাদা।

সাধারণত patch release-এ bug fixes ও maintenance changes থাকে।

### Important Note

Version number যত বড়, সেটি প্রতিটি project-এর জন্য তত ভালো—এমন নয়।

কোনো project-এর dependency যদি নির্দিষ্ট version range সমর্থন করে, তাহলে সেই compatibility অনুসরণ করতে হবে।

---

## 4. Python 2 vs Python 3

Python-এর ইতিহাসে Python 2 এবং Python 3 দুটি গুরুত্বপূর্ণ major version।

### Python 2

Python 2 একটি পুরোনো major version series। এর official support 2020 সালে শেষ হয়েছে।

নতুন সাধারণ project-এর জন্য Python 2 ব্যবহার করা উচিত নয়।

### Python 3

Python 3 হলো বর্তমানে ব্যবহৃত modern Python language series।

নতুন project, programming শেখা এবং সাধারণ development-এর জন্য supported Python 3 release ব্যবহার করা উচিত।

### Key Differences

| Feature | Python 2 | Python 3 |
|---|---|---|
| Current use | Legacy projects | Modern development |
| Official support | 2020 সালে শেষ | Minor release অনুযায়ী support চলতে থাকে |
| Print syntax | `print "Hello"` | `print("Hello")` |
| Text handling | Unicode ও byte handling-এর আচরণ আলাদা | Text handling আরও সুসংগত |
| New projects | সাধারণত ব্যবহার করা উচিত নয় | Recommended choice |

### Example: Print Statement

Python 2-এর পুরোনো syntax:

```python
print "Hello, World!"
```

Python 3-এর syntax:

```python
print("Hello, World!")
```

এই repository-তে আমরা **Python 3** ব্যবহার করব।

---

## 5. What Is a Python Interpreter?

**Python Interpreter** হলো এমন software, যা Python program পড়ে এবং execute করে।

আমরা যখন Python code লিখি, তখন interpreter সেই code চালিয়ে output তৈরি করে অথবা program-এর কাজ সম্পন্ন করে।

উদাহরণ:

```python
print("Hello, Python!")
```

Output:

```text
Hello, Python!
```

এখানে Python interpreter `print()` statement execute করে text output দেখায়।

### Why Is the Interpreter Important?

Interpreter ছাড়া সাধারণভাবে Python source code সরাসরি execute করা যায় না।

Interpreter-এর সাহায্যে আমরা:

- Python statements চালাতে পারি।
- `.py` file execute করতে পারি।
- Interactive mode-এ code পরীক্ষা করতে পারি।
- Program-এর error শনাক্ত করতে পারি।
- Python standard library ও installed packages ব্যবহার করতে পারি।

### Python Source Code and Interpreter

সহজভাবে workflow-টি এমন:

```text
Python Source Code
        |
        v
Python Interpreter
        |
        v
Program Execution
        |
        v
Output or Result
```

এটি একটি simplified view। CPython-এর মতো implementation সাধারণত source code-কে bytecode-এ compile করে এবং virtual machine-এর মাধ্যমে execute করে।

---

## 6. How Does Python Execute Code?

Python-এর execution process বুঝতে একটি সাধারণ program দেখি।

```python
a = 10
b = 20

result = a + b

print(result)
```

Output:

```text
30
```

### Step-by-Step Execution

**Step 1:** Interpreter প্রথম statement execute করে।

```python
a = 10
```

Variable `a`-তে integer value `10` রাখা হয়।

**Step 2:** দ্বিতীয় statement execute হয়।

```python
b = 20
```

Variable `b`-তে `20` রাখা হয়।

**Step 3:** Addition operation হয়।

```python
result = a + b
```

`a` এবং `b`-এর value যোগ করে `result`-এ রাখা হয়।

**Step 4:** Output দেখানো হয়।

```python
print(result)
```

Output:

```text
30
```

এই উদাহরণে interpreter Python statements execute করে program-এর result তৈরি করেছে।

---

## 7. What Is CPython?

Python-এর একাধিক implementation রয়েছে। এর মধ্যে **CPython** হলো সবচেয়ে প্রচলিত implementation।

CPython C programming language ব্যবহার করে তৈরি Python implementation।

সাধারণভাবে python.org থেকে প্রচলিত Python installer ব্যবহার করলে CPython পাওয়া যায়।

### Other Python Implementations

| Implementation | Description |
|---|---|
| CPython | Python-এর standard ও বহুল ব্যবহৃত implementation |
| PyPy | Just-in-time compilation ব্যবহার করে performance উন্নত করতে পারে |
| Jython | JVM-ভিত্তিক Python implementation; Python 3 compatibility ও version support-এর সীমাবদ্ধতা আছে |
| IronPython | .NET ecosystem-এর জন্য Python implementation |

Beginner হিসেবে এখনই সব implementation শেখার প্রয়োজন নেই।

এই repository-তে সাধারণভাবে CPython ব্যবহার করে Python শেখা হবে, যদি অন্য কোনো implementation স্পষ্টভাবে উল্লেখ না করা হয়।

### Important Difference

**Python language** এবং **Python implementation** একই ধারণা নয়।

Python language-এর syntax ও behavior নির্দিষ্ট করে। CPython বা PyPy-এর মতো implementation সেই language execute করার software সরবরাহ করে।

---

## 8. Python Interpreter vs Code Editor

Beginner-রা অনেক সময় Python interpreter এবং code editor-কে একই জিনিস মনে করেন। আসলে এদের কাজ আলাদা।

| Feature | Python Interpreter | Code Editor |
|---|---|---|
| Main purpose | Python code execute করা | Code লেখা ও edit করা |
| Example | CPython | VS Code |
| Runs Python code | হ্যাঁ | নিজে interpreter নয় |
| Syntax highlighting | মূল কাজ নয় | সাধারণত থাকে |
| Error display | Execution-related errors দেখায় | Editor ও extension অনুযায়ী error information দেখাতে পারে |

### Example

VS Code-এ তুমি লিখতে পারো:

```python
print("Learning Python")
```

কিন্তু code execute করার জন্য VS Code-কে একটি compatible Python interpreter-এর সঙ্গে কাজ করতে হবে।

অর্থাৎ:

- VS Code হলো code editor।
- Python interpreter code execute করে।
- Python extension editor-কে Python development-এর বিভিন্ন feature দিতে সাহায্য করে।

VS Code setup-এর বিস্তারিত আলোচনা পরবর্তী topic-গুলোতে থাকবে।

---

## 9. Check Your Python Version

Python version পরীক্ষা করার জন্য operating system অনুযায়ী command ব্যবহার করতে হবে।

### Windows

```powershell
python --version
```

অথবা:

```powershell
py --version
```

### macOS and Linux

```bash
python3 --version
```

### Example Output

```text
Python 3.12.8
```

এই output example হিসেবে দেখানো হয়েছে। তোমার computer-এ অন্য supported version থাকতে পারে।

### Check the Version Inside Python

Python interactive mode-এ প্রবেশ করার পরে:

```python
import sys

print(sys.version)
```

এটি interpreter-এর version ও build-related information দেখায়।

আরও structured information:

```python
print(sys.version_info)
```

এই information debugging এবং version compatibility পরীক্ষা করার সময় কাজে লাগে।

---

## 10. What Happens When Multiple Python Versions Are Installed?

একটি computer-এ একাধিক Python version install থাকতে পারে।

উদাহরণস্বরূপ:

```text
Python 3.11
Python 3.12
Python 3.13
```

এটি সব সময় সমস্যা নয়। আলাদা project-এর requirement আলাদা হলে একাধিক version দরকার হতে পারে।

### Example Situation

ধরা যাক:

- Project A-এর জন্য Python 3.11 প্রয়োজন।
- Project B-এর জন্য Python 3.12 প্রয়োজন।

এক্ষেত্রে project-এর requirement অনুযায়ী interpreter নির্বাচন করতে হবে।

### What Can Go Wrong?

একাধিক version থাকলে:

- `python` command প্রত্যাশিত version নাও চালাতে পারে।
- এক version-এ install করা package অন্য version-এ available নাও থাকতে পারে।
- VS Code ভুল interpreter ব্যবহার করতে পারে।
- Script-এর behavior project-এর requirement থেকে আলাদা হতে পারে।

এই সমস্যাগুলো এড়াতে Python version, executable path এবং project environment যাচাই করা গুরুত্বপূর্ণ।

---

## 11. Check Available Python Versions on Windows

Windows-এ Python Launcher install থাকলে এটি available Python runtime-এর তালিকা দেখাতে পারে।

PowerShell বা Command Prompt-এ চালাও:

```powershell
py --list
```

Launcher version অনুযায়ী option ও output কিছুটা আলাদা হতে পারে।

কোনো নির্দিষ্ট version চালু করার জন্য supported launcher-এ version selector ব্যবহার করা যায়।

উদাহরণ:

```powershell
py -3.12 --version
```

এটি launcher-এর মাধ্যমে Python 3.12 series-এর উপযুক্ত installation চালানোর চেষ্টা করে।

**Note:** এই command কাজ করার জন্য compatible Python 3.12 installation এবং উপযুক্ত launcher থাকা দরকার।

Windows-এ command search path-এ পাওয়া Python executable দেখতে:

```powershell
where python
```

এই command-এর output থেকে বোঝা যেতে পারে কোন কোন location-এ `python` command পাওয়া যাচ্ছে।

---

## 12. Check Python Version and Location on macOS and Linux

macOS ও Linux-এ সাধারণত `python3` command ব্যবহার করা হয়।

### Check Version

```bash
python3 --version
```

### Check Executable Location

```bash
which python3
```

### Check Version from Inside Python

```bash
python3 -c "import sys; print(sys.version)"
```

### Check the Exact Executable Used

```bash
python3 -c "import sys; print(sys.executable)"
```

`sys.executable` বর্তমানে চালু interpreter-এর executable path দেখায়।

এই তথ্য বিশেষভাবে উপকারী, যখন একাধিক Python installation বা virtual environment থাকে।

**Important:** `which` command নির্বাচিত executable-এর location শনাক্ত করতে সাহায্য করে, তবে সব shell configuration-এর ক্ষেত্রে এটি একমাত্র বা চূড়ান্ত diagnostic tool নয়।

---

## 13. How to Select the Correct Python Interpreter

সঠিক interpreter নির্বাচন করার আগে তিনটি বিষয় বিবেচনা করতে হবে:

1. Project-এর required Python version।
2. Python installation-এর location।
3. Project-এর virtual environment।

### Example

ধরা যাক, তোমার project folder-এর নাম:

```text
MyProject/
```

এর ভেতরে একটি virtual environment আছে:

```text
MyProject/
├── .venv/
└── main.py
```

এই project-এর জন্য `.venv`-এর interpreter ব্যবহার করা উচিত।

সাধারণত virtual environment তৈরি করতে:

```bash
python -m venv .venv
```

অথবা operating system অনুযায়ী নির্দিষ্ট Python command ব্যবহার করা যায়।

যেমন:

```bash
python3 -m venv .venv
```

Environment তৈরি হওয়ার পরে সেটি activate করে project চালানো যায়।

### Why Is Interpreter Selection Important?

সঠিক interpreter নির্বাচন করলে:

- Project-এর Python version consistent রাখা যায়।
- Project-specific package ব্যবহার করা যায়।
- অন্য project-এর dependency conflict কমানো যায়।
- VS Code এবং terminal-এর execution environment মিলিয়ে রাখা সহজ হয়।

---

## 14. Python Version and Package Compatibility

সব Python package সব Python version সমর্থন করে না।

কোনো package নতুন Python version-এ install না হলে তার কারণ হতে পারে:

- Package-এর নতুন version এখনও compatible নয়।
- Package-এর নির্দিষ্ট dependency দরকার।
- ব্যবহৃত Python version package-এর supported range-এর বাইরে।
- Operating system বা architecture-এর জন্য compatible package build available নেই।

### What Should You Do?

1. Package-এর official documentation পড়ো।
2. Project-এর `README` ও dependency requirements দেখো।
3. Supported Python version যাচাই করো।
4. প্রয়োজন হলে project-এর জন্য compatible Python version নির্বাচন করো।
5. Project-specific virtual environment ব্যবহার করো।

শুধু package install করার জন্য পুরো system-এর Python version অপ্রয়োজনীয়ভাবে পরিবর্তন কোরো না।

---

## 15. Common Mistakes

### Mistake 1: Assuming the Latest Version Is Always Required

সব project সর্বশেষ Python release সমর্থন করবে, এমন নয়।

**Solution:** Project-এর compatibility ও support requirements যাচাই করো।

### Mistake 2: Confusing Python and VS Code

VS Code একটি code editor; এটি নিজে Python interpreter নয়।

**Solution:** VS Code-এ compatible Python interpreter নির্বাচন করো।

### Mistake 3: Installing Packages into the Wrong Version

একটি Python version-এ install করা package অন্য version-এ automatically available নাও হতে পারে।

**Solution:** Project-এর নির্বাচিত interpreter ব্যবহার করে `python -m pip` চালাও।

### Mistake 4: Removing System Python

কিছু Linux system tool system Python-এর ওপর নির্ভর করতে পারে।

**Solution:** System Python অক্ষত রেখে virtual environment ব্যবহার করো।

### Mistake 5: Ignoring the Executable Path

একই computer-এ একাধিক Python installation থাকলে command ভুল installation ব্যবহার করতে পারে।

**Solution:** `sys.executable`, `which python3` বা Windows-এ `where python` ব্যবহার করে path পরীক্ষা করো।

---

## 16. Practice Tasks

### Task 1: Check Your Python Version

নিজের operating system অনুযায়ী version command চালাও।

Windows:

```powershell
python --version
```

macOS/Linux:

```bash
python3 --version
```

### Task 2: Check the Interpreter Path

Windows:

```powershell
where python
```

macOS/Linux:

```bash
which python3
```

### Task 3: Display Version Information

```python
import sys

print("Python Version:", sys.version)
print("Python Executable:", sys.executable)
```

### Task 4: Explain the Version Number

ধরা যাক version হলো:

```text
3.12.4
```

লিখে দেখাও:

- Major version: `3`
- Minor version: `12`
- Patch version: `4`

### Task 5: Answer These Questions

1. Python version কী?
2. Major, minor ও patch version-এর মধ্যে পার্থক্য কী?
3. Python 2 ও Python 3-এর মধ্যে কোনটি নতুন project-এর জন্য উপযুক্ত?
4. Python interpreter-এর কাজ কী?
5. CPython কী?
6. একটি computer-এ একাধিক Python version রাখা যায় কি?
7. `sys.executable` কী তথ্য দেয়?
8. Project-এর জন্য সঠিক interpreter নির্বাচন করা কেন গুরুত্বপূর্ণ?

---

## 17. Quick Revision

| Topic | Key Point |
|---|---|
| Python Version | Python-এর নির্দিষ্ট release বা সংস্করণ |
| Major Version | Version number-এর প্রথম অংশ |
| Minor Version | নতুন feature ও changes-সহ release series |
| Patch Version | Maintenance ও bug-fix release |
| Python 2 | Official support 2020 সালে শেষ হয়েছে |
| Python 3 | Modern Python development-এর জন্য ব্যবহৃত series |
| Interpreter | Python code execute করে |
| CPython | বহুল ব্যবহৃত Python implementation |
| `sys.version` | Interpreter-এর version information |
| `sys.executable` | ব্যবহৃত Python executable-এর path |
| Multiple Versions | আলাদা project requirements-এর জন্য একাধিক version থাকতে পারে |
| Virtual Environment | Project-specific package ও environment আলাদা রাখতে সাহায্য করে |

---

## 18. Chapter Connection

এই topic-এ Python version, interpreter, CPython, multiple installations এবং সঠিক interpreter নির্বাচনের ধারণা শিখেছি।

পরবর্তী topic-এ আমরা এমন একটি গুরুত্বপূর্ণ বিষয় শিখব, যা command line থেকে Python চালানোর সঙ্গে সরাসরি সম্পর্কিত—**PATH এবং Environment Variables**।

**Next Topic:** [08. Understanding PATH and Environment Variables](08_Understanding_PATH_and_Environment_Variables.md)