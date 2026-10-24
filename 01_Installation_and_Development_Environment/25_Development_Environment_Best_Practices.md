# 25. Development Environment Best Practices

## 1. Introduction

Python install করে code run করতে পারলেই একটি ভালো development environment তৈরি হয়ে যায় না। Project-এর file গুছিয়ে রাখা, সঠিক Python interpreter ব্যবহার করা, package manage করা, code-এর backup রাখা এবং security বজায় রাখাও গুরুত্বপূর্ণ।

**Development Environment Best Practices** হলো এমন কিছু নিয়ম ও অভ্যাস, যা Python project-কে organized, reliable, secure এবং maintainable রাখতে সাহায্য করে।

এই topic-এ আমরা শিখব:

1. Project folder কীভাবে organize করতে হয়।
2. Virtual environment কেন ব্যবহার করতে হয়।
3. Package ও dependency কীভাবে manage করতে হয়।
4. File ও variable-এর naming convention।
5. `.gitignore` ও Git ব্যবহার।
6. Secret ও sensitive information নিরাপদ রাখা।
7. Code formatting ও documentation।
8. নিয়মিত project maintenance করা।

---

## 2. Keep Each Project in a Separate Folder

প্রতিটি Python project-এর জন্য আলাদা folder তৈরি করা ভালো।

উদাহরণ:

```text
PythonProjects/
├── calculator/
│   ├── main.py
│   └── README.md
├── student_management/
│   ├── main.py
│   └── README.md
└── data_analysis/
    ├── main.py
    └── README.md
```

### Why Is This Important?

- এক project-এর file অন্য project-এর সঙ্গে মিশে যায় না।
- প্রতিটি project আলাদাভাবে manage করা যায়।
- Dependency ও configuration আলাদা রাখা সহজ হয়।
- Git দিয়ে project-এর history manage করা সুবিধাজনক হয়।

### Best Practices

- Project-এর জন্য অর্থপূর্ণ folder name ব্যবহার করো।
- সব project এক folder-এ গুছিয়ে রাখো।
- অপ্রয়োজনীয় nested folder এড়িয়ে চলো।
- Project-এর root directory কোথায়, তা পরিষ্কার রাখো।

---

## 3. Use a Virtual Environment for Each Project

**Virtual Environment** হলো একটি isolated Python environment, যেখানে নির্দিষ্ট project-এর Python interpreter ও installed packages manage করা যায়।

ধরা যাক:

- Project A-এর জন্য `requests`-এর একটি version দরকার।
- Project B-এর জন্য অন্য version দরকার।

আলাদা virtual environment ব্যবহার করলে দুই project-এর dependency আলাদাভাবে manage করা সহজ হয়।

### Create a Virtual Environment

Project folder-এ terminal খুলে চালাও:

```bash
python -m venv .venv
```

এখানে:

- `python` হলো Python interpreter-এর command।
- `-m venv` Python-এর `venv` module চালায়।
- `.venv` হলো environment-এর folder name।

### Activate on Windows PowerShell

```powershell
.\.venv\Scripts\Activate.ps1
```

### Activate on Windows Command Prompt

```cmd
.venv\Scripts\activate.bat
```

### Activate on macOS or Linux

```bash
source .venv/bin/activate
```

### Verify the Environment

```python
import sys

print(sys.executable)
```

Path-এ `.venv` দেখা গেলে সাধারণত project-এর virtual environment ব্যবহার হচ্ছে।

### Best Practices

- প্রতিটি project-এর জন্য আলাদা virtual environment রাখো।
- VS Code-এ সঠিক interpreter select করো।
- Virtual environment folder GitHub-এ commit কোরো না।
- Project-এর dependency আলাদাভাবে document করো।

---

## 4. Keep Project Dependencies Organized

**Dependency** হলো এমন package বা library, যা project-এর কাজ সম্পন্ন করতে প্রয়োজন হয়।

উদাহরণ:

```bash
python -m pip install requests
```

এই command `requests` package install করে।

### Why Manage Dependencies?

- অন্য computer-এ project setup করা সহজ হয়।
- Project-এর প্রয়োজনীয় package জানা যায়।
- Package version-এর conflict শনাক্ত করা সহজ হয়।
- Team-এর অন্য developer-রাও একই ধরনের environment তৈরি করতে পারে।

### Use `requirements.txt`

Project-এর dependency list সংরক্ষণের জন্য `requirements.txt` ব্যবহার করা যায়।

উদাহরণ:

```text
requests==2.32.3
```

এটি একটি উদাহরণ version pin। নিজের project-এর জন্য উপযুক্ত version নির্বাচন করবে।

Package install করতে:

```bash
python -m pip install -r requirements.txt
```

### Generate a Requirements File

Virtual environment-এ project-এর dependency install করার পর:

```bash
python -m pip freeze > requirements.txt
```

`pip freeze` environment-এ থাকা installed distribution ও version-এর তালিকা তৈরি করে।

**সতর্কতা:** `pip freeze` সব সময় শুধু project-এর direct dependency দেখায় না; transitive dependency-ও থাকতে পারে। বড় project-এ dependency management-এর আরও উন্নত পদ্ধতি প্রয়োজন হতে পারে।

### Best Practices

- Project-এর dependency file repository-তে রাখো।
- অপ্রয়োজনীয় package install কোরো না।
- Package install করার আগে সঠিক environment active আছে কি না যাচাই করো।
- Dependency পরিবর্তন করলে requirements file update করো।
- গুরুত্বপূর্ণ project-এ package version ও compatibility যাচাই করো।

---

## 5. Follow Python Naming Conventions

সঠিক naming convention code-কে readable ও understandable করে।

Python community-তে naming convention-এর জন্য PEP 8 গুরুত্বপূর্ণ reference।

### 5.1 Variable Names

সাধারণত `snake_case` ব্যবহার করা হয়।

সঠিক:

```python
student_name = "Masum"
total_marks = 450
is_active = True
```

এড়িয়ে চলো:

```python
studentName = "Masum"
TotalMarks = 450
```

### 5.2 Function Names

Function-এর নামও সাধারণত `snake_case` হয়।

```python
def calculate_total():
    pass

def display_result():
    pass
```

### 5.3 Class Names

Class-এর জন্য সাধারণত `PascalCase` ব্যবহার করা হয়।

```python
class StudentRecord:
    pass

class BankAccount:
    pass
```

### 5.4 Constants

Module-level constant-এর জন্য সাধারণত uppercase letters ও underscores ব্যবহার করা হয়।

```python
MAX_RETRIES = 3
PI = 3.14159
DEFAULT_TIMEOUT = 30
```

### 5.5 File Names

Python module-এর জন্য সাধারণত lowercase filename ব্যবহার করা হয়।

উদাহরণ:

```text
main.py
student_record.py
file_handler.py
```

### Important Rules

- অর্থপূর্ণ নাম ব্যবহার করো।
- অপ্রয়োজনীয় abbreviation এড়িয়ে চলো।
- Python-এর reserved keyword variable name হিসেবে ব্যবহার কোরো না।
- Variable ও function-এর নাম দেখে যেন তাদের কাজ বোঝা যায়।

---

## 6. Keep the Project Structure Clean

Project বড় হওয়ার সঙ্গে সঙ্গে সব code একটি file-এ রাখা কঠিন হয়ে যায়। তাই প্রয়োজন অনুযায়ী file ও folder ভাগ করে রাখো।

### Simple Project Structure

```text
my_python_project/
├── README.md
├── requirements.txt
├── .gitignore
├── .env.example
├── main.py
├── src/
│   └── helpers.py
├── tests/
│   └── test_helpers.py
└── data/
```

এটি একটি example structure। সব project-এ প্রতিটি file বা folder থাকা বাধ্যতামূলক নয়।

### Purpose of Each File

| File/Folder | Purpose |
|---|---|
| `README.md` | Project পরিচিতি ও ব্যবহারবিধি |
| `requirements.txt` | Dependency list |
| `.gitignore` | নির্দিষ্ট file Git tracking থেকে বাদ রাখা |
| `.env.example` | প্রয়োজনীয় environment variable-এর নামের নমুনা |
| `main.py` | Program-এর entry point হতে পারে |
| `src/` | Application source code |
| `tests/` | Automated test |
| `data/` | Project-এর data file |

### Best Practices

- ছোট project-এ অপ্রয়োজনীয় folder তৈরি কোরো না।
- বড় project-এ related code আলাদা module-এ রাখো।
- Temporary file ও generated output source code থেকে আলাদা রাখো।
- Folder-এর নাম দেখে যেন উদ্দেশ্য বোঝা যায়।

---

## 7. Use `.gitignore` Properly

Git repository-তে সব file track করা প্রয়োজন হয় না।

উদাহরণস্বরূপ:

- Virtual environment।
- Python bytecode cache।
- Secret-containing `.env` file।
- Editor-specific temporary file।

এসব বাদ রাখতে `.gitignore` ব্যবহার করা হয়।

### Example `.gitignore`

```gitignore
# Virtual environments
.venv/
venv/

# Python cache
__pycache__/
*.py[cod]

# Environment variables and secrets
.env

# Test and coverage output
.pytest_cache/
.coverage
htmlcov/

# Editor settings (optional)
.vscode/
```

এই example-এর কিছু entry project-এর প্রয়োজন অনুযায়ী পরিবর্তন করা যেতে পারে। যেমন, team-এর জন্য share করা দরকার হলে `.vscode/` বাদ না দিয়ে নির্দিষ্ট ব্যক্তিগত settings-কে ignore করা যেতে পারে।

### Important

`.gitignore` সাধারণত untracked file-কে Git tracking থেকে বাদ রাখতে সাহায্য করে।

কোনো file আগে থেকেই tracked হয়ে গেলে শুধু `.gitignore`-এ নাম যোগ করলেই tracking বন্ধ হয় না। সেক্ষেত্রে প্রয়োজন অনুযায়ী:

```bash
git rm --cached FILENAME
```

ব্যবহার করা যায়। `FILENAME`-এর জায়গায় নির্দিষ্ট file-এর path বসাবে।

এই command সাধারণত Git-এর index থেকে file সরায়, কিন্তু local file রেখে দেয়।

---

## 8. Never Store Secrets in Source Code

Password, API key, access token বা database credential সরাসরি source code-এ লেখা নিরাপদ নয়।

### Bad Practice

```python
API_KEY = "my-secret-api-key"
```

এভাবে লিখলে code repository-তে প্রকাশিত হওয়ার সঙ্গে সঙ্গে secret-ও প্রকাশ হয়ে যেতে পারে।

### Better Approach

Environment variable থেকে value নেওয়া যায়।

```python
import os

api_key = os.getenv("API_KEY")

if not api_key:
    raise RuntimeError("API_KEY is not configured")
```

এখানে Python `API_KEY` নামে environment variable খুঁজবে।

Environment variable-এর value operating system বা development environment-এর মাধ্যমে configure করতে হবে।

### `.env` File

কিছু project-এ environment variable manage করতে `.env` file ব্যবহার করা হয়।

উদাহরণ:

```text
API_KEY=your_api_key_here
```

এটি শুধু placeholder example। এখানে বাস্তব secret লিখে public repository-তে commit কোরো না।

`.env` file সাধারণত `.gitignore`-এ রাখা উচিত।

### `.env.example`

Team-এর অন্য সদস্যদের configuration বোঝাতে secret ছাড়া একটি example file রাখা যায়।

```text
API_KEY=
DATABASE_URL=
```

### Important Security Rules

- Real secret source code-এ hardcode কোরো না।
- `.env` file public repository-তে commit কোরো না।
- Secret ভুল করে publish হলে সেটি revoke বা rotate করো।
- Public repository-তে sensitive data আছে কি না push করার আগে যাচাই করো।

---

## 9. Write Readable and Maintainable Code

Code শুধু computer-এর জন্য নয়; অন্য developer-দেরও code বুঝতে হয়।

### Use Meaningful Names

খারাপ:

```python
x = 500
y = 200
z = x - y
```

ভালো:

```python
total_income = 500
total_expense = 200
remaining_balance = total_income - total_expense
```

দ্বিতীয় উদাহরণে variable-এর উদ্দেশ্য সহজে বোঝা যায়।

### Keep Functions Focused

একটি function-এ অপ্রয়োজনীয়ভাবে অনেক কাজ না রেখে নির্দিষ্ট কাজের জন্য function তৈরি করো।

```python
def calculate_area(length, width):
    return length * width


def display_area(area):
    print(f"Area: {area}")
```

এখানে calculation ও display-এর কাজ আলাদা রাখা হয়েছে।

### Avoid Unnecessary Repetition

একই logic বারবার লিখতে হলে সেটিকে function-এ রাখা যায়।

### Keep Code Simple

- অপ্রয়োজনীয় complexity এড়িয়ে চলো।
- Code-এর উদ্দেশ্য পরিষ্কার রাখো।
- শুধু ছোট code-কে বড় দেখানোর জন্য অতিরিক্ত abstraction তৈরি কোরো না।
- নতুন feature যোগ করার সময় আগের code যেন অকারণে ভেঙে না যায়, তা যাচাই করো।

---

## 10. Follow PEP 8 and Use a Formatter

**PEP 8** হলো Python code style-এর একটি গুরুত্বপূর্ণ guideline।

এতে naming convention, indentation, line length, import organization এবং whitespace-এর মতো বিষয় নিয়ে নির্দেশনা রয়েছে।

### Example

সাধারণত:

```python
def calculate_sum(first_number, second_number):
    return first_number + second_number
```

এভাবে readable নাম ও consistent spacing ব্যবহার করা ভালো।

### Use a Code Formatter

Formatter code-এর formatting স্বয়ংক্রিয়ভাবে ঠিক করতে সাহায্য করে।

একটি জনপ্রিয় formatter হলো `Black`।

Install করতে:

```bash
python -m pip install black
```

একটি file format করতে:

```bash
python -m black main.py
```

পুরো project-এর Python file format করার আগে formatter-এর behavior সম্পর্কে ধারণা নাও।

### Use a Linter

Linter code-এর সম্ভাব্য style issue, ভুল pattern বা কিছু programming problem শনাক্ত করতে সাহায্য করে।

উদাহরণ হিসেবে `Ruff` ব্যবহার করা যায়।

Install করতে:

```bash
python -m pip install ruff
```

Code check করতে:

```bash
python -m ruff check .
```

### Formatter vs Linter

| Tool | Main Purpose |
|---|---|
| Formatter | Code-এর formatting consistent করা |
| Linter | Code-এর বিভিন্ন issue ও rule violation শনাক্ত করা |

সব project-এ একই tool বাধ্যতামূলক নয়। Project-এর আকার ও প্রয়োজন অনুযায়ী tool নির্বাচন করো।

---

## 11. Use Comments and Docstrings Properly

Comment ও docstring code বুঝতে সাহায্য করে, কিন্তু অপ্রয়োজনীয় explanation code-কে cluttered করতে পারে।

### Comment

Comment কোনো code-এর উদ্দেশ্য বা বিশেষ decision বোঝাতে ব্যবহার করা যায়।

```python
# Calculate the final price after applying a discount.
final_price = price - discount
```

### Docstring

Docstring function, class বা module-এর কাজ document করতে ব্যবহৃত হয়।

```python
def calculate_area(length, width):
    """Return the area of a rectangle."""
    return length * width
```

### Best Practices

- Code কেন লেখা হয়েছে তা ব্যাখ্যা করার জন্য comment ব্যবহার করো।
- সহজে বোঝা যায় এমন code-এর প্রতিটি line-এ comment দেওয়ার দরকার নেই।
- Function ও class-এর জন্য প্রয়োজন অনুযায়ী docstring লেখো।
- Code পরিবর্তন করলে পুরোনো বা ভুল comment update করো।

---

## 12. Keep a Useful README File

`README.md` হলো project-এর পরিচিতি ও নির্দেশনার প্রধান file।

একটি ভালো README-তে সাধারণত থাকে:

1. Project title।
2. Project-এর উদ্দেশ্য।
3. Features।
4. Requirements।
5. Installation instructions।
6. Run করার নিয়ম।
7. Usage example।
8. Project structure, প্রয়োজন হলে।
9. Contribution instructions, প্রয়োজন হলে।
10. License, প্রয়োজন অনুযায়ী।

### Example README

```markdown
# Python Calculator

A simple calculator built with Python.

## Features

- Addition
- Subtraction
- Multiplication
- Division

## Requirements

- Python 3

## Run

```bash
python main.py
```
```

README-এর example command project-এর actual file ও environment-এর সঙ্গে মিলিয়ে লিখবে।

### Why Is README Important?

- অন্য developer project দ্রুত বুঝতে পারে।
- নিজের project পরে আবার শুরু করা সহজ হয়।
- GitHub portfolio আরও organized হয়।
- Installation ও usage নিয়ে confusion কমে।

---

## 13. Use Git Regularly

Git ব্যবহার করলে project-এর পরিবর্তনের history রাখা যায়।

### Basic Workflow

```bash
git status
git diff
git add .
git commit -m "Describe the changes"
```

Remote repository থাকলে:

```bash
git push
```

### Best Practices

- ছোট কিন্তু অর্থপূর্ণ পরিবর্তন commit করো।
- Commit message পরিষ্কার রাখো।
- Commit করার আগে `git status` দেখো।
- প্রয়োজনে `git diff` দিয়ে পরিবর্তন যাচাই করো।
- অপ্রয়োজনীয় generated file commit কোরো না।
- Secret ও private information commit কোরো না।

### Important

Git backup-এর বিকল্প হিসেবে একমাত্র ব্যবস্থা হওয়া উচিত নয়। Repository-এর গুরুত্বপূর্ণ data-এর জন্য উপযুক্ত backup strategy রাখো।

---

## 14. Keep the Development Environment Reproducible

**Reproducible Environment** হলো এমন environment, যা অন্য computer-এও নির্ভরযোগ্যভাবে পুনরায় তৈরি করা যায়।

ধরা যাক, তুমি একটি project-এ কিছু external package ব্যবহার করেছ।

শুধু source code অন্য computer-এ copy করলে সেই package-গুলো স্বয়ংক্রিয়ভাবে install হবে না।

তাই setup instructions ও dependency list রাখা জরুরি।

### Example Setup Workflow

```bash
# Create a virtual environment
python -m venv .venv
```

এরপর operating system অনুযায়ী environment activate করো।

তারপর:

```bash
python -m pip install -r requirements.txt
```

এবং:

```bash
python main.py
```

### Best Practices

- Dependency list সংরক্ষণ করো।
- Python version-এর প্রয়োজনীয়তা document করো।
- Project setup-এর নির্দেশনা README-তে রাখো।
- Clean environment-এ project run করে পরীক্ষা করো।
- বড় project-এ উপযুক্ত dependency lock বা environment management tool বিবেচনা করো।

`requirements.txt` থাকা মানেই সব operating system ও সব Python version-এ একই ফল পাওয়া নিশ্চিত নয়। কিছু package-এর system-level dependency বা version restriction থাকতে পারে।

---

## 15. Keep Your Tools Updated Carefully

Python, VS Code, extensions এবং packages-এর update bug fix ও নতুন feature দিতে পারে।

তবে update করার আগে compatibility বিবেচনা করা জরুরি।

### Best Practices

- Official source থেকে software download করো।
- গুরুত্বপূর্ণ project-এর dependency update করার আগে পরীক্ষা করো।
- Update-এর পরে tests চালাও।
- অপ্রয়োজনীয় extension install কোরো না।
- অজানা source থেকে executable বা package install করা এড়িয়ে চলো।

### Example

Installed package-এর তথ্য দেখতে:

```bash
python -m pip show requests
```

Package update করার আগে project-এর dependency ও compatibility যাচাই করো।

```bash
python -m pip install --upgrade requests
```

এই command current environment-এ `requests` update করার চেষ্টা করবে। Production বা গুরুত্বপূর্ণ project-এ update করার আগে version constraint ও tests বিবেচনা করো।

---

## 16. Use Testing Before Major Changes

Project-এর behavior সঠিক আছে কি না যাচাই করতে testing গুরুত্বপূর্ণ।

ধরা যাক, একটি function যোগ করেছ:

```python
def add(a, b):
    return a + b
```

সাধারণভাবে:

```python
print(add(2, 3))
```

Output:

```text
5
```

এটি একটি simple manual check।

Project বড় হলে automated test ব্যবহার করা সুবিধাজনক।

### Example with `unittest`

```python
import unittest


def add(a, b):
    return a + b


class TestAddition(unittest.TestCase):
    def test_add_positive_numbers(self):
        self.assertEqual(add(2, 3), 5)


if __name__ == "__main__":
    unittest.main()
```

এই উদাহরণে `unittest` দিয়ে addition function পরীক্ষা করা হয়েছে।

### Best Practices

- গুরুত্বপূর্ণ function-এর expected output পরীক্ষা করো।
- Bug fix করার পরে একই bug আবার হচ্ছে কি না যাচাই করো।
- বড় পরিবর্তনের পরে relevant tests চালাও।
- Automated testing-এর পাশাপাশি প্রয়োজন অনুযায়ী manual testing করো।

---

## 17. Organize Imports Properly

Python file-এ import সাধারণত নিচের ক্রমে রাখা সুবিধাজনক:

1. Standard library imports।
2. Third-party package imports।
3. নিজের project-এর imports।

উদাহরণ:

```python
import os
from pathlib import Path

import requests

from helpers import format_result
```

এখানে `os` ও `pathlib` standard library-এর অংশ, `requests` third-party package, আর `helpers` project-এর নিজস্ব module-এর উদাহরণ।

Import order সব project-এ নিজে হাতে manage করা বাধ্যতামূলক নয়; linter বা formatter-এর উপযুক্ত configuration ব্যবহার করা যায়।

### Best Practices

- অপ্রয়োজনীয় import সরিয়ে ফেলো।
- ব্যবহৃত package-এর dependency নিশ্চিত করো।
- Import name ও local file name-এর conflict এড়িয়ে চলো।
- Related import একসঙ্গে রাখো।

---

## 18. Avoid Hardcoding Machine-Specific Paths

একটি নির্দিষ্ট computer-এর path code-এ hardcode করলে অন্য computer-এ project চালাতে সমস্যা হতে পারে।

### Less Portable

```python
file_path = "C:/Users/Example/Desktop/data.txt"
```

এই path শুধু নির্দিষ্ট computer-এর folder structure-এর সঙ্গে মিলতে পারে।

### Better Approach

```python
from pathlib import Path

file_path = Path("data") / "data.txt"
```

এখানে path project-এর working directory-এর সঙ্গে সম্পর্কিত।

Project structure ও working directory অনুযায়ী file path ঠিক করতে হবে।

### Best Practices

- প্রয়োজনে `pathlib` ব্যবহার করো।
- README-তে expected folder structure উল্লেখ করো।
- Absolute path দরকার হলে configuration বা environment variable থেকে নিতে পারো।
- File কোথা থেকে load হচ্ছে তা যাচাই করো।

---

## 19. Maintain a Clean Workspace

Project-এর মধ্যে temporary file, cache, test output এবং অপ্রয়োজনীয় duplicate file জমে গেলে project বুঝতে কঠিন হতে পারে।

### Good Practices

- অপ্রয়োজনীয় file নিয়মিত পরিষ্কার করো।
- Generated output source code থেকে আলাদা রাখো।
- Project-এর file name consistent রাখো।
- একই কাজের একাধিক duplicate version অকারণে রেখো না।
- প্রয়োজনীয় documentation update করো।

### Example

```text
my_project/
├── README.md
├── requirements.txt
├── .gitignore
├── main.py
├── src/
└── tests/
```

এটি একটি সাধারণ structure। Project-এর কাজ অনুযায়ী structure পরিবর্তিত হতে পারে।

---

## 20. Common Bad Practices to Avoid

| Bad Practice | Better Practice |
|---|---|
| সব project-এর package system-wide install করা | Project অনুযায়ী virtual environment ব্যবহার |
| সব code একটি file-এ রাখা | প্রয়োজন অনুযায়ী module-এ ভাগ করা |
| Variable-এর অস্পষ্ট নাম ব্যবহার | অর্থপূর্ণ naming convention |
| Password code-এ লেখা | Secure configuration ও environment variable |
| `.venv` GitHub-এ upload করা | `.gitignore`-এ environment folder রাখা |
| README ছাড়া project publish করা | Setup ও usage document করা |
| Error না পড়ে বারবার command চালানো | Error message বিশ্লেষণ করা |
| অপ্রয়োজনীয় package install করা | শুধু প্রয়োজনীয় dependency রাখা |
| Test না করে বড় পরিবর্তন করা | পরিবর্তনের পরে relevant tests চালানো |
| প্রতিটি update সঙ্গে সঙ্গে install করা | Compatibility যাচাই করে update করা |
| Hardcoded personal path ব্যবহার করা | Portable path ও configuration ব্যবহার |
| সব change এক commit-এ রাখা | অর্থপূর্ণ ছোট commit তৈরি করা |

---

## 21. Recommended Workflow for a New Python Project

নতুন Python project শুরু করার সময় নিচের workflow অনুসরণ করতে পারো।

### Step 1: Create a Project Folder

```bash
mkdir my_python_project
cd my_python_project
```

### Step 2: Initialize Git

```bash
git init
```

### Step 3: Create a Virtual Environment

```bash
python -m venv .venv
```

### Step 4: Activate the Environment

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

macOS বা Linux:

```bash
source .venv/bin/activate
```

### Step 5: Create the Initial Files

```text
my_python_project/
├── .venv/
├── .gitignore
├── README.md
└── main.py
```

### Step 6: Add the `.gitignore`

```gitignore
.venv/
__pycache__/
*.py[cod]
.env
```

### Step 7: Write and Run the Code

`main.py`:

```python
def main():
    print("My Python project is ready!")


if __name__ == "__main__":
    main()
```

### Step 8: Install Dependencies When Needed

```bash
python -m pip install PACKAGE_NAME
```

`PACKAGE_NAME`-এর পরিবর্তে প্রয়োজনীয় package-এর নাম ব্যবহার করবে।

### Step 9: Document Dependencies

প্রয়োজন অনুযায়ী `requirements.txt` তৈরি ও update করো।

### Step 10: Commit the Project

```bash
git status
git add .
git commit -m "Create initial project structure"
```

### Step 11: Test and Document

Code run করো, প্রয়োজনীয় test করো এবং README update করো।

### Step 12: Publish to GitHub

GitHub repository তৈরি করে local repository-র সঙ্গে connect করো। তারপর commit push করো।

---

## 22. Final Checklist

নতুন Python project শুরু করার সময় এই checklist ব্যবহার করতে পারো।

- [ ] Project-এর জন্য আলাদা folder তৈরি করেছি।
- [ ] সঠিক Python interpreter নির্বাচন করেছি।
- [ ] Project-এর virtual environment তৈরি করেছি।
- [ ] প্রয়োজনীয় package সঠিক environment-এ install করেছি।
- [ ] Meaningful variable, function ও file name ব্যবহার করেছি।
- [ ] `.gitignore` তৈরি করেছি।
- [ ] Secret ও password source code থেকে দূরে রেখেছি।
- [ ] README-তে project-এর পরিচিতি ও setup instructions লিখেছি।
- [ ] Dependency management-এর ব্যবস্থা রেখেছি।
- [ ] Code-এর formatting ও readability বজায় রেখেছি।
- [ ] প্রয়োজন অনুযায়ী tests লিখেছি ও চালিয়েছি।
- [ ] Git commit করার আগে পরিবর্তন যাচাই করেছি।
- [ ] Project-এর গুরুত্বপূর্ণ data-এর backup strategy বিবেচনা করেছি।

---

## 23. Chapter Summary

এই topic-এ আমরা Python development environment ভালোভাবে maintain করার নিয়ম শিখেছি।

সবচেয়ে গুরুত্বপূর্ণ অভ্যাসগুলো হলো:

1. প্রতিটি project-এর জন্য আলাদা folder ও virtual environment ব্যবহার করা।
2. Dependency ও Python version-এর প্রয়োজনীয়তা document করা।
3. পরিষ্কার naming convention ও project structure বজায় রাখা।
4. `.gitignore` ব্যবহার করে অপ্রয়োজনীয় file বাদ দেওয়া।
5. Password ও API key নিরাপদ রাখা।
6. README, testing এবং Git-এর মাধ্যমে project maintain করা।
7. Error message পড়ে ধাপে ধাপে সমস্যা সমাধান করা।

এই অভ্যাসগুলো শুরু থেকেই অনুসরণ করলে project বড় হওয়ার পরও code manage করা অনেক সহজ হবে।

**Next Step:** [Chapter 01 — Installation & Development Environment](README.md)

এই chapter-এর বাকি topic-গুলো revise করে installation, interpreter, terminal, virtual environment, package management, Jupyter এবং Git-এর basic workflow নিজে practice করো। এরপর Chapter 02 — Python Fundamentals শুরু করার জন্য প্রস্তুত হবে।