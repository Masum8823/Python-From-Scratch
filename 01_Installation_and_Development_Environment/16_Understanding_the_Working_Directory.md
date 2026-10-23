# 16. Understanding the Working Directory

## 1. Introduction

Python program চালানোর সময় অনেক ক্ষেত্রে Python-কে জানতে হয় কোনো file বা folder কোথায় রয়েছে।

যেমন:

- কোন folder থেকে Python program চালানো হচ্ছে?
- Python কীভাবে একটি file খুঁজে পায়?
- `data.txt` এবং `folder/data.txt`-এর মধ্যে পার্থক্য কী?
- `FileNotFoundError` কেন হয়?
- Absolute path ও relative path কী?

এই প্রশ্নগুলোর উত্তর বুঝতে হলে প্রথমে **Working Directory** সম্পর্কে জানতে হবে।

এই topic-এ আমরা শিখব:

1. Working Directory কী।
2. Current Working Directory (CWD) কী।
3. Absolute Path ও Relative Path।
4. Terminal থেকে directory পরিবর্তন করা।
5. Python code দিয়ে working directory দেখা।
6. File path-সংক্রান্ত সাধারণ সমস্যা সমাধান করা।

---

## 2. What Is a Directory?

Directory হলো file এবং অন্যান্য directory রাখার একটি স্থান। সাধারণভাবে একে folder-ও বলা হয়।

উদাহরণ:

```text
Python_Project/
├── main.py
├── README.md
├── data.txt
└── practice/
    └── exercise.py
```

এখানে:

- `Python_Project` হলো মূল folder।
- `main.py` হলো একটি Python file।
- `README.md` হলো একটি Markdown file।
- `data.txt` হলো একটি text file।
- `practice` হলো একটি subfolder।
- `exercise.py` হলো `practice` folder-এর ভেতরে থাকা Python file।

Directory-গুলো একটি hierarchy বা কাঠামো তৈরি করে।

### Why Are Directories Important?

Directory ব্যবহার করে আমরা:

- Project-এর file গুছিয়ে রাখতে পারি।
- Source code ও data আলাদা রাখতে পারি।
- বড় project সহজে পরিচালনা করতে পারি।
- নির্দিষ্ট file-এর location খুঁজে পেতে পারি।

---

## 3. What Is the Working Directory?

**Working Directory** হলো কোনো program বা command বর্তমানে যে directory-কে তার current location হিসেবে ব্যবহার করছে।

Python program file খোঁজার সময় অনেক ক্ষেত্রে relative path এই directory-এর ভিত্তিতে ব্যাখ্যা করা হয়।

উদাহরণ:

```text
C:\Users\Student\Python_Project\
├── main.py
└── data.txt
```

ধরা যাক, Terminal-এর current working directory হলো:

```text
C:\Users\Student\Python_Project
```

এখন তুমি চালালে:

```powershell
python main.py
```

Python এই directory-এর মধ্যে `main.py` খুঁজতে পারে।

আবার, `main.py`-তে যদি থাকে:

```python
file = open("data.txt", "r")
```

তাহলে `data.txt`-এর relative path সাধারণভাবে current working directory-এর ভিত্তিতে resolve হবে।

**গুরুত্বপূর্ণ:** Python source file কোথায় আছে এবং program-এর current working directory কোথায় আছে—এ দুটি আলাদা বিষয় হতে পারে।

এই পার্থক্যটি ভালোভাবে বুঝে রাখবে।

---

## 4. What Is the Current Working Directory (CWD)?

CWD-এর পূর্ণরূপ হলো **Current Working Directory**।

এটি হলো বর্তমানে ব্যবহৃত working directory।

### Checking CWD in Windows PowerShell

Terminal-এ চালাও:

```powershell
Get-Location
```

উদাহরণ output:

```text
Path
----
C:\Users\Student\Python_Project
```

### Checking CWD in macOS or Linux

Terminal-এ চালাও:

```bash
pwd
```

উদাহরণ output:

```text
/home/student/Python_Project
```

এখানে `pwd`-এর পূর্ণরূপ হলো `Print Working Directory`।

### Why Should You Check CWD?

ধরা যাক, তোমার `data.txt` file আছে `Python_Project` folder-এ।

কিন্তু Terminal-এর current working directory হলো অন্য একটি folder।

তাহলে:

```python
open("data.txt", "r")
```

চালানোর সময় Python file-টি খুঁজে নাও পেতে পারে।

তাই file নিয়ে কাজ করার আগে current working directory জানা খুব গুরুত্বপূর্ণ।

---

## 5. Understanding Absolute Paths

**Absolute Path** হলো কোনো file বা directory-এর সম্পূর্ণ location, যা একটি নির্দিষ্ট root বা filesystem location থেকে নির্ধারিত হয়।

### Windows Example

```text
C:\Users\Student\Python_Project\main.py
```

এখানে সম্পূর্ণ path দেওয়া হয়েছে।

### macOS Example

```text
/Users/student/Python_Project/main.py
```

### Linux Example

```text
/home/student/Python_Project/main.py
```

### Why Use an Absolute Path?

Absolute path ব্যবহার করলে file-এর location স্পষ্টভাবে উল্লেখ করা যায়।

উদাহরণ:

```python
file = open(
    r"C:\Users\Student\Python_Project\data.txt",
    "r"
)
```

এখানে Windows-এর একটি absolute path ব্যবহার করা হয়েছে।

`r` prefix-টি raw string তৈরি করে, যা Windows path-এর backslash নিয়ে কাজ সহজ করতে পারে।

অন্যভাবে forward slash-ও ব্যবহার করা যায়:

```python
file = open(
    "C:/Users/Student/Python_Project/data.txt",
    "r"
)
```

এই উদাহরণে `data.txt` file-টি বাস্তবে ওই location-এ থাকতে হবে।

### Advantages

- File-এর নির্দিষ্ট location পরিষ্কার থাকে।
- Current working directory-এর ওপর নির্ভরতা কমে।
- নির্দিষ্ট environment-এ file খুঁজে পাওয়া সহজ হতে পারে।

### Limitations

- অন্য computer-এ একই path নাও থাকতে পারে।
- Username বা folder পরিবর্তিত হলে path ভুল হয়ে যেতে পারে।
- অন্য operating system-এ path-এর format ভিন্ন হতে পারে।

তাই project-এর ভেতরের file-এর জন্য relative path বা `pathlib` ব্যবহার করা অনেক ক্ষেত্রে বেশি সুবিধাজনক।

---

## 6. Understanding Relative Paths

**Relative Path** হলো current working directory-এর মতো একটি নির্দিষ্ট starting location-এর তুলনায় লেখা path।

উদাহরণ:

```text
Python_Project/
├── main.py
├── data.txt
└── files/
    └── notes.txt
```

ধরা যাক, CWD হলো `Python_Project`।

এখন নিচের path-গুলো দেখো:

| Relative Path | Meaning |
|---|---|
| `main.py` | বর্তমান working directory-এর `main.py` |
| `data.txt` | বর্তমান working directory-এর `data.txt` |
| `files/notes.txt` | `files` folder-এর ভেতরের `notes.txt` |
| `files/data.csv` | `files` folder-এর ভেতরের `data.csv` |

উদাহরণ:

```python
open("data.txt", "r")
```

এখানে `data.txt` একটি relative path।

আবার:

```python
open("files/notes.txt", "r")
```

এখানে `files/notes.txt` একটি relative path।

### Important Point

Relative path সব সময় Python file-এর folder থেকে শুরু হয় না। সাধারণভাবে এটি process-এর current working directory-এর ভিত্তিতে resolve হয়।

এই কারণেই একই Python file ভিন্ন directory থেকে চালালে relative path-সংক্রান্ত ফলাফল আলাদা হতে পারে।

---

## 7. Understanding `.` and `..` in Paths

Relative path-এ `.` এবং `..` বিশেষভাবে ব্যবহৃত হয়।

### `.` — Current Directory

`.` বর্তমান directory বোঝাতে ব্যবহৃত হয়।

উদাহরণ:

```text
./data.txt
```

সাধারণভাবে এটি current working directory-এর `data.txt`-কে নির্দেশ করে।

### `..` — Parent Directory

`..` বর্তমান directory-এর parent বা উপরের directory বোঝায়।

উদাহরণ:

```text
Python_Project/
├── data.txt
└── practice/
    └── main.py
```

যদি working directory হয় `practice`, তাহলে:

```text
../data.txt
```

parent directory-এর `data.txt`-কে নির্দেশ করে।

একইভাবে:

```text
../../data.txt
```

দুটি directory level উপরে গিয়ে `data.txt` খোঁজার অর্থ হতে পারে।

তবে path-এর সঠিক অর্থ নির্ভর করে current working directory ও directory structure-এর ওপর।

---

## 8. Changing the Working Directory in the Terminal

Terminal-এ `cd` command ব্যবহার করে working directory পরিবর্তন করা যায়।

`cd`-এর অর্থ হলো `Change Directory`।

### Windows Example

বর্তমান directory দেখো:

```powershell
Get-Location
```

একটি folder-এ প্রবেশ করো:

```powershell
cd practice
```

এক level উপরে যাও:

```powershell
cd ..
```

একটি absolute path-এ যাও:

```powershell
cd C:\Users\Student\Python_Project
```

### macOS/Linux Example

বর্তমান directory দেখো:

```bash
pwd
```

একটি folder-এ প্রবেশ করো:

```bash
cd practice
```

এক level উপরে যাও:

```bash
cd ..
```

একটি absolute path-এ যাও:

```bash
cd /home/student/Python_Project
```

### Going Back to the Previous Directory

কিছু shell-এ `cd -` ব্যবহার করে আগের working directory-তে ফেরা যায়:

```bash
cd -
```

এই command-এর আচরণ shell অনুযায়ী নির্ভর করতে পারে।

---

## 9. Understanding the Difference Between Script Location and CWD

এটি Python-এর একটি গুরুত্বপূর্ণ concept।

ধরা যাক, project structure:

```text
Python_Project/
├── data.txt
└── scripts/
    └── main.py
```

এখন তুমি `Python_Project` folder থেকে চালালে:

```bash
python scripts/main.py
```

এক্ষেত্রে সাধারণত:

- Python script-এর location: `Python_Project/scripts/main.py`
- Current working directory: `Python_Project`

এ দুটি একই নয়।

`main.py`-তে যদি থাকে:

```python
print("Hello from Python")
```

তাহলে code ঠিকমতো চলবে।

কিন্তু যদি থাকে:

```python
file = open("data.txt", "r")
```

তাহলে Python সাধারণভাবে current working directory-এর `data.txt` খুঁজবে। উপরের command-এ সেটি `Python_Project/data.txt`।

অন্যদিকে, তুমি যদি `scripts` folder-এ প্রবেশ করে চালাও:

```bash
python main.py
```

তাহলে CWD হবে `Python_Project/scripts`। একই `open("data.txt", "r")` তখন `scripts/data.txt` খুঁজবে, `Python_Project/data.txt` নয়।

ফলে `FileNotFoundError` হতে পারে।

### Key Lesson

**Script location এবং current working directory এক জিনিস নয়।**

এই বিষয়টি মনে রাখলে অনেক file path error সহজে বুঝতে পারবে।

---

## 10. Checking the Working Directory in Python

Python-এর `os` module ব্যবহার করে current working directory দেখা যায়।

উদাহরণ:

```python
import os

print(os.getcwd())
```

Output তোমার system অনুযায়ী ভিন্ন হবে।

উদাহরণ:

```text
C:\Users\Student\Python_Project
```

এখানে:

- `import os` — `os` module import করে।
- `os.getcwd()` — current working directory-এর path return করে।
- `print()` — path-টি display করে।

### Example with More Information

```python
import os

current_directory = os.getcwd()

print("Current Working Directory:")
print(current_directory)
```

এই code-এর মাধ্যমে working directory একটি variable-এ রেখে পরে ব্যবহার করা যায়।

### Changing CWD from Python

`os.chdir()` ব্যবহার করে Python program-এর current working directory পরিবর্তন করা যায়।

```python
import os

print("Before:", os.getcwd())

os.chdir("..")

print("After:", os.getcwd())
```

এখানে `os.chdir("..")` current working directory-কে parent directory-তে পরিবর্তন করার চেষ্টা করে।

**সতর্কতা:** Python code-এর ভেতরে working directory পরিবর্তন করলে পরবর্তী relative file path-এর অর্থও পরিবর্তিত হয়। তাই অকারণে `os.chdir()` ব্যবহার না করাই ভালো।

---

## 11. Working with Paths Using `pathlib`

Python-এর `pathlib` module file path নিয়ে কাজ করার একটি আধুনিক ও সুবিধাজনক উপায়।

এটি Windows, macOS ও Linux-এর path-এর পার্থক্য সামলাতে সাহায্য করে।

### Example 1: Get the Current Working Directory

```python
from pathlib import Path

current_directory = Path.cwd()

print(current_directory)
```

এখানে `Path.cwd()` বর্তমান working directory-কে একটি `Path` object হিসেবে দেয়।

### Example 2: Create a Relative Path

```python
from pathlib import Path

file_path = Path("data.txt")

print(file_path)
```

এখানে `file_path` একটি relative path নির্দেশ করে।

### Example 3: Check Whether a File Exists

```python
from pathlib import Path

file_path = Path("data.txt")

if file_path.exists():
    print("File exists")
else:
    print("File does not exist")
```

এখানে `exists()` পরীক্ষা করে নির্দিষ্ট path-এ file বা directory আছে কি না।

### Example 4: Check Whether It Is a File

```python
from pathlib import Path

file_path = Path("data.txt")

if file_path.is_file():
    print("This is a file")
else:
    print("This is not a file")
```

### Example 5: Build a Path

```python
from pathlib import Path

file_path = Path("data") / "notes.txt"

print(file_path)
```

এটি `data/notes.txt`-এর মতো path তৈরি করবে। Operating system অনুযায়ী প্রদর্শিত separator ভিন্ন হতে পারে।

### Why Prefer `pathlib`?

- বিভিন্ন operating system-এ path পরিচালনা সহজ হয়।
- Path-এর অংশ যুক্ত করা যায়।
- File ও directory পরীক্ষা করা যায়।
- Path নিয়ে কাজের code সাধারণত পরিষ্কার হয়।

পরবর্তী file handling chapter-এ `pathlib` আরও বিস্তারিতভাবে ব্যবহার করব।

---

## 12. Understanding Absolute and Relative Paths with `pathlib`

`pathlib` দিয়ে relative path-কে absolute path-এ রূপান্তর করা যায়।

উদাহরণ:

```python
from pathlib import Path

file_path = Path("data.txt")

print("Relative path:", file_path)
print("Absolute path:", file_path.resolve())
```

`resolve()` path-টির absolute form তৈরি করে। Path-এর অস্তিত্ব, symbolic link এবং operating system-এর আচরণের কারণে বিস্তারিত ফলাফল ভিন্ন হতে পারে।

### Checking Whether a Path Is Absolute

```python
from pathlib import Path

path1 = Path("data.txt")
path2 = Path.cwd() / "data.txt"

print(path1.is_absolute())
print(path2.is_absolute())
```

সাধারণভাবে:

- `Path("data.txt")` হলো relative path।
- `Path.cwd() / "data.txt"` হলো absolute path।

### Practical Example

ধরা যাক, বর্তমান working directory:

```text
C:\Users\Student\Python_Project
```

তাহলে:

```python
from pathlib import Path

file_path = Path("data.txt")

print(file_path.resolve())
```

Output হতে পারে:

```text
C:\Users\Student\Python_Project\data.txt
```

এই উদাহরণটি বুঝতে সাহায্য করে কীভাবে relative path-কে absolute path হিসেবে প্রকাশ করা যায়।

---

## 13. Common File Path Errors

### Error 1: `FileNotFoundError`

উদাহরণ:

```python
with open("data.txt", "r", encoding="utf-8") as file:
    content = file.read()

print(content)
```

যদি Python current working directory-তে `data.txt` না পায়, তাহলে `FileNotFoundError` হতে পারে।

সমাধান:

1. File-এর নাম সঠিক কি না যাচাই করো।
2. File সঠিক folder-এ আছে কি না দেখো।
3. `os.getcwd()` দিয়ে current working directory পরীক্ষা করো।
4. প্রয়োজনে সঠিক relative বা absolute path ব্যবহার করো।

### Error 2: Incorrect Windows Path

ভুল বা ঝুঁকিপূর্ণ উদাহরণ:

```python
path = "C:\new_folder\data.txt"
```

এখানে `\n`-এর মতো sequence Python string-এর special escape sequence হিসেবে ব্যাখ্যা হতে পারে।

সঠিক পদ্ধতি:

```python
path = r"C:\new_folder\data.txt"
```

অথবা:

```python
path = "C:/new_folder/data.txt"
```

অথবা:

```python
path = "C:\\new_folder\\data.txt"
```

### Error 3: Wrong Capitalization

কিছু operating system-এ file name-এর uppercase ও lowercase পার্থক্য গুরুত্বপূর্ণ।

যেমন:

```text
data.txt
Data.txt
```

কিছু file system-এ এগুলো আলাদা file হিসেবে বিবেচিত হয়।

তাই file-এর প্রকৃত নামের সঙ্গে code-এর path মিলিয়ে লিখবে।

### Error 4: Wrong Directory

তুমি যদি ভুল directory থেকে program চালাও, তাহলে relative path দিয়ে file খুঁজে পাওয়া নাও যেতে পারে।

সমাধান:

```python
import os

print(os.getcwd())
```

এরপর file-এর অবস্থানের সঙ্গে current working directory মিলিয়ে দেখো।

---

## 14. Practical Exercises

### Exercise 1: Check CWD

একটি Python file তৈরি করো:

```python
import os

print(os.getcwd())
```

Program চালিয়ে current working directory দেখো।

### Exercise 2: Explore a Path with `pathlib`

```python
from pathlib import Path

current_directory = Path.cwd()

print("Current directory:", current_directory)
print("Is absolute:", current_directory.is_absolute())
```

প্রতিটি line কী করে, নিজের ভাষায় ব্যাখ্যা করো।

### Exercise 3: Create a Folder Structure

এমন একটি project structure তৈরি করো:

```text
Path_Practice/
├── main.py
└── files/
    └── notes.txt
```

`notes.txt`-এ কিছু text লেখো।

### Exercise 4: Check File Existence

`main.py`-তে লেখো:

```python
from pathlib import Path

file_path = Path("files") / "notes.txt"

print(file_path.exists())
```

Program-টি `Path_Practice` folder থেকে চালিয়ে ফলাফল দেখো।

### Exercise 5: Compare Relative and Absolute Paths

```python
from pathlib import Path

relative_path = Path("files") / "notes.txt"
absolute_path = relative_path.resolve()

print("Relative:", relative_path)
print("Absolute:", absolute_path)
```

দুটি path-এর পার্থক্য বোঝার চেষ্টা করো।

### Exercise 6: Fix a File Path Error

`notes.txt`-এর path ভুল লিখে program চালাও। Error message পড়ো এবং path ঠিক করে আবার চালাও।

---

## 15. Best Practices

1. File নিয়ে কাজ করার আগে current working directory বোঝার চেষ্টা করো।
2. Relative path ব্যবহার করার সময় path কোন directory থেকে resolve হচ্ছে, তা যাচাই করো।
3. Project-এর ভেতরের file পরিচালনার জন্য প্রয়োজনে `pathlib` ব্যবহার করো।
4. Absolute path hardcode করার আগে বিবেচনা করো অন্য computer-এ সেটি কাজ করবে কি না।
5. Windows path লেখার সময় backslash-এর escape sequence সম্পর্কে সতর্ক থাকো।
6. File name ও extension সঠিকভাবে লেখো।
7. `FileNotFoundError` হলে প্রথমে file location ও working directory পরীক্ষা করো।
8. অকারণে `os.chdir()` দিয়ে working directory পরিবর্তন কোরো না।
9. Project-এর file ও folder-এর নাম অর্থপূর্ণ রাখো।
10. ছোট practical example দিয়ে path-এর আচরণ যাচাই করো।

---

## 16. Quick Revision

| Term | Meaning |
|---|---|
| Directory | File ও subdirectory রাখার স্থান |
| Working Directory | Program বা command-এর current directory |
| CWD | Current Working Directory |
| Absolute Path | নির্দিষ্ট root বা filesystem location থেকে নির্ধারিত সম্পূর্ণ path |
| Relative Path | নির্দিষ্ট starting directory-এর তুলনায় লেখা path |
| `.` | Current directory নির্দেশ করে |
| `..` | Parent directory নির্দেশ করে |
| `pwd` | macOS/Linux-এ working directory দেখায় |
| `Get-Location` | PowerShell-এ working directory দেখায় |
| `os.getcwd()` | Python-এ current working directory return করে |
| `os.chdir()` | Python process-এর working directory পরিবর্তন করে |
| `Path.cwd()` | `pathlib` দিয়ে current working directory পায় |
| `Path.exists()` | Path-এ কোনো file বা directory আছে কি না পরীক্ষা করে |
| `Path.resolve()` | Path-এর resolved absolute form দেয় |
| `FileNotFoundError` | প্রয়োজনীয় file বা path খুঁজে না পাওয়ার error |

---

## 17. Chapter Connection

এই topic-এ আমরা directory, current working directory, absolute path, relative path এবং Python-এর `os` ও `pathlib` module দিয়ে path পরিচালনার প্রাথমিক ধারণা শিখেছি।

এই বিষয়গুলো পরবর্তী সময়ে file handling, project structure, database, automation এবং web development-এ কাজে লাগবে।

**Next Topic:** [17. Using the Python REPL](17_Using_the_Python_REPL.md)