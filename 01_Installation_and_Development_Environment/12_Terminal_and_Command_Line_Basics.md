# 12. Terminal and Command Line Basics

## 1. Introduction

Computer ব্যবহার করার সময় আমরা সাধারণত mouse দিয়ে বিভিন্ন application open করি, folder তৈরি করি এবং file manage করি। কিন্তু এসব কাজ keyboard দিয়ে command লিখেও করা যায়।

এই পদ্ধতিকে বলা হয় **Command-Line Interface (CLI)** ব্যবহার করা।

Python development-এ Terminal খুব গুরুত্বপূর্ণ, কারণ এর মাধ্যমে আমরা:

- Python program run করতে পারি।
- Project folder তৈরি ও manage করতে পারি।
- Python package install করতে পারি।
- Virtual environment তৈরি ও activate করতে পারি।
- Git command চালাতে পারি।
- Program-এর error ও output দেখতে পারি।

এই topic-এ আমরা Terminal-এর basic ধারণা থেকে শুরু করে প্রয়োজনীয় command-গুলো শিখব।

---

## 2. What Is a Terminal?

**Terminal** হলো এমন একটি interface, যার মাধ্যমে command লিখে computer-এর সঙ্গে কাজ করা যায়।

উদাহরণস্বরূপ, Terminal-এ নিচের command লিখলে Python version দেখা যায়:

```bash
python --version
```

তোমার operating system অনুযায়ী `python3` বা Windows-এর `py` command-ও ব্যবহার করতে হতে পারে।

Terminal-এর মাধ্যমে mouse ব্যবহার না করেও অনেক কাজ করা যায়।

### Examples of Terminals

| Operating System | Common Terminal |
|---|---|
| Windows | Windows Terminal, Command Prompt, PowerShell |
| macOS | Terminal |
| Linux | Terminal emulator |

VS Code-এর মধ্যেও Integrated Terminal রয়েছে। ফলে code editor থেকে বের না হয়েই command চালানো যায়।

---

## 3. What Is a Command-Line Interface (CLI)?

**Command-Line Interface (CLI)** হলো এমন একটি interface, যেখানে text command লিখে computer বা software-কে নির্দেশ দেওয়া হয়।

উদাহরণ:

```bash
mkdir Python_Practice
```

এই command বর্তমান directory-তে `Python_Practice` নামে একটি folder তৈরি করার চেষ্টা করবে।

অন্যদিকে, **Graphical User Interface (GUI)**-তে সাধারণত button, icon, menu ও mouse ব্যবহার করা হয়।

### CLI vs GUI

| CLI | GUI |
|---|---|
| Text command ব্যবহার করা হয় | Visual elements ব্যবহার করা হয় |
| অনেক কাজ দ্রুত করা যায় | Beginner-এর জন্য অনেক কাজ সহজে বোঝা যায় |
| Command ও syntax মনে রাখতে হয় | Menu ও button ব্যবহার করা যায় |
| Automation-এর জন্য কার্যকর | Visual interaction-এর জন্য সুবিধাজনক |

Python development-এ CLI ও GUI—দুটিই কাজে লাগে।

---

## 4. What Is a Shell?

**Shell** হলো এমন একটি program, যা command গ্রহণ করে এবং সেগুলো কীভাবে execute হবে তা পরিচালনা করে।

সহজভাবে:

- Terminal হলো command ব্যবহারের interface।
- Shell হলো command interpret ও execute করার environment।
- Command হলো computer-কে দেওয়া নির্দেশ।

উদাহরণ:

Windows-এ:

- Command Prompt (`cmd`)
- PowerShell

macOS/Linux-এ:

- Bash
- Zsh
- অন্যান্য supported shell

একই command সব shell-এ একইভাবে কাজ করবে, এমন নয়।

যেমন, Windows PowerShell-এ environment variable দেখানোর command:

```powershell
$env:Path
```

Windows Command Prompt-এ:

```cmd
echo %PATH%
```

macOS/Linux-এর shell-এ:

```bash
echo "$PATH"
```

তাই command ব্যবহার করার সময় কোন shell ব্যবহার করছ, তা জানা জরুরি।

---

## 5. Opening the Terminal in VS Code

VS Code-এর Integrated Terminal ব্যবহার করা Python শেখার জন্য সুবিধাজনক।

### Method 1: Menu

VS Code-এর menu থেকে:

`Terminal > New Terminal`

নির্বাচন করো।

### Method 2: Keyboard Shortcut

অনেক VS Code configuration-এ নিচের shortcut ব্যবহার করে Integrated Terminal খোলা যায়:

- Windows/Linux: `Ctrl + `` 
- macOS: `Control + ``

এখানে `` ` `` হলো backtick key। Keyboard layout অনুযায়ী shortcut ভিন্ন হতে পারে।

### What Will You See?

Terminal খুললে command prompt দেখতে পাবে।

উদাহরণ:

```powershell
PS C:\Users\YourName\Python_Practice>
```

অথবা:

```bash
yourname@computer:~/Python_Practice$
```

এগুলো শুধু উদাহরণ। তোমার computer-এ username, directory ও prompt আলাদা হবে।

Prompt-এর পরে command লিখে Enter চাপলে command execute হয়।

---

## 6. Understanding the Current Working Directory

**Current Working Directory** হলো সেই directory, যেটিকে command-line program-এর বর্তমান working location হিসেবে ব্যবহার করা হচ্ছে।

ধরা যাক, তোমার project structure:

```text
Python_Practice/
├── main.py
└── practice.py
```

Terminal যদি `Python_Practice` folder-এর মধ্যে থাকে, তাহলে নিচের command চালানো সহজ হবে:

```bash
python main.py
```

কিন্তু Terminal অন্য directory-তে থাকলে file খুঁজে পেতে সমস্যা হতে পারে।

### Check the Current Directory

Windows PowerShell:

```powershell
Get-Location
```

Windows Command Prompt:

```cmd
cd
```

macOS/Linux:

```bash
pwd
```

`pwd`-এর অর্থ হলো **Print Working Directory**।

### Why Is It Important?

Current working directory বুঝতে পারলে:

- সঠিক file run করা যায়।
- File path-এর error কম হয়।
- Project-এর file manage করা সহজ হয়।
- Relative path সঠিকভাবে ব্যবহার করা যায়।

---

## 7. Understanding Absolute and Relative Paths

File বা folder-এর location বোঝাতে path ব্যবহার করা হয়।

Path প্রধানত দুই ধরনের।

### 7.1 Absolute Path

**Absolute Path** একটি নির্দিষ্ট root location থেকে file বা folder-এর সম্পূর্ণ location নির্দেশ করে।

Windows example:

```text
C:\Users\YourName\Python_Practice\main.py
```

macOS/Linux example:

```text
/home/yourname/Python_Practice/main.py
```

এগুলো illustrative example; তোমার actual path আলাদা হতে পারে।

### 7.2 Relative Path

**Relative Path** বর্তমান working directory-এর তুলনায় file বা folder-এর location নির্দেশ করে।

ধরা যাক:

```text
Python_Practice/
├── main.py
└── notes/
    └── lesson.md
```

যদি current directory `Python_Practice` হয়, তাহলে `main.py`-এর relative path:

```text
main.py
```

আর `lesson.md`-এর relative path:

```text
notes/lesson.md
```

Windows-এ Python ও command-line tools অনেক ক্ষেত্রে forward slash (`/`) গ্রহণ করতে পারে, যদিও Windows path-এ backslash (`\`) বহুল ব্যবহৃত হয়।

### Important Symbols

| Symbol | Meaning |
|---|---|
| `.` | Current directory |
| `..` | Parent directory |
| `/` | Unix-like system-এ root directory বোঝাতে পারে; path separator হিসেবেও ব্যবহৃত হয় |
| `~` | অনেক Unix-like shell-এ home directory |

উদাহরণ:

```bash
cd ..
```

এই command বর্তমান directory-এর parent directory-তে যাওয়ার নির্দেশ দেয়।

---

## 8. Essential Directory Commands

এখন আমরা folder navigate ও manage করার গুরুত্বপূর্ণ command-গুলো শিখব।

### 8.1 `pwd` — Print Working Directory

macOS/Linux এবং অনেক shell-এ বর্তমান directory দেখায়।

```bash
pwd
```

উদাহরণ output:

```text
/home/yourname/Python_Practice
```

Windows PowerShell-এ একই উদ্দেশ্যে ব্যবহার করতে পারো:

```powershell
Get-Location
```

### 8.2 `cd` — Change Directory

একটি directory থেকে অন্য directory-তে যেতে `cd` ব্যবহার করা হয়।

```bash
cd Python_Practice
```

এটি current directory-এর মধ্যে `Python_Practice` folder থাকলে সেখানে যাবে।

Parent directory-তে যেতে:

```bash
cd ..
```

Windows-এ drive পরিবর্তনের নিয়ম shell অনুযায়ী আলাদা হতে পারে। Command Prompt-এ drive এবং directory একসঙ্গে পরিবর্তনের জন্য `cd /d` ব্যবহার করা যায়।

```cmd
cd /d D:\Projects\Python_Practice
```

### 8.3 `mkdir` — Make Directory

নতুন directory তৈরি করতে `mkdir` ব্যবহার করা হয়।

```bash
mkdir Python_Practice
```

একই নামের folder আগে থেকেই থাকলে error আসতে পারে।

### 8.4 `ls` — List Directory Contents

macOS/Linux-এ file ও folder-এর তালিকা দেখতে:

```bash
ls
```

Hidden file-সহ দেখতে:

```bash
ls -a
```

Windows PowerShell-এ:

```powershell
Get-ChildItem
```

PowerShell-এ `ls` সাধারণত `Get-ChildItem`-এর alias হিসেবেও কাজ করে।

### 8.5 `dir` — List Directory Contents on Windows

Windows Command Prompt-এ:

```cmd
dir
```

এটি বর্তমান directory-এর file ও folder দেখায়।

**মনে রাখবে:** `ls` ও `dir`-এর availability এবং behavior shell অনুযায়ী ভিন্ন হতে পারে।

---

## 9. Creating and Navigating Project Folders

ধরা যাক, তুমি `Python_Practice` নামে একটি project folder তৈরি করতে চাও।

### Step 1: Check Your Current Location

```bash
pwd
```

Windows PowerShell-এ:

```powershell
Get-Location
```

### Step 2: Create the Folder

```bash
mkdir Python_Practice
```

### Step 3: Enter the Folder

```bash
cd Python_Practice
```

### Step 4: Check the Location Again

```bash
pwd
```

এখন তুমি `Python_Practice` folder-এর মধ্যে আছ কি না যাচাই করতে পারবে।

### Step 5: Open the Project in VS Code

যদি VS Code-এর `code` command configure করা থাকে:

```bash
code .
```

এখানে `.` current directory বোঝায়।

এই command বর্তমান folder VS Code-এ open করার চেষ্টা করবে।

যদি `code` command কাজ না করে, তাহলে VS Code-এর `File > Open Folder` ব্যবহার করতে পারো। `code` command-এর setup operating system ও installation configuration-এর ওপর নির্ভর করে।

---

## 10. Creating Files from the Terminal

কিছু command-line tool দিয়ে file তৈরি করা যায়।

### Windows PowerShell

```powershell
New-Item main.py -ItemType File
```

### Windows Command Prompt

```cmd
type nul > main.py
```

### macOS/Linux

```bash
touch main.py
```

এই command-গুলো সাধারণভাবে নতুন empty file তৈরির জন্য ব্যবহৃত হয়। File আগে থেকেই থাকলে behavior command ও shell অনুযায়ী আলাদা হতে পারে।

### Recommended Beginner Method

শুরুতে VS Code-এর Explorer ব্যবহার করে file তৈরি করাও সম্পূর্ণ ঠিক।

যেমন:

1. VS Code-এ project folder open করো।
2. Explorer-এ `New File` নির্বাচন করো।
3. `main.py` নাম দাও।
4. Code লিখে save করো।

Terminal থেকে file তৈরি করা শেখা উপকারী, তবে প্রতিটি কাজ command দিয়ে করতেই হবে এমন নয়।

---

## 11. Running Python Programs from the Terminal

Terminal দিয়ে Python program চালানো একটি গুরুত্বপূর্ণ দক্ষতা।

ধরা যাক, `main.py`-তে রয়েছে:

```python
print("Hello, Python!")
print("I am learning command-line basics.")
```

### Windows

```powershell
python main.py
```

Python Launcher ব্যবহার করা থাকলে:

```powershell
py main.py
```

### macOS/Linux

```bash
python3 main.py
```

কিছু system-এ `python` command-ও কাজ করতে পারে।

### Expected Output

```text
Hello, Python!
I am learning command-line basics.
```

### Important

Command চালানোর আগে নিশ্চিত হও:

- Python install করা আছে।
- সঠিক interpreter ব্যবহার হচ্ছে।
- Terminal সঠিক directory-তে আছে।
- `main.py` file-টি সেখানে রয়েছে।

---

## 12. Understanding Command Arguments

কোনো command-এর পরে অতিরিক্ত information দিলে তাকে সাধারণভাবে argument বলা হয়।

উদাহরণ:

```bash
python main.py
```

এখানে:

- `python` হলো command।
- `main.py` হলো command-এ দেওয়া argument।

আরেকটি উদাহরণ:

```bash
mkdir MyProject
```

এখানে `mkdir` directory তৈরির command, আর `MyProject` হলো যে directory তৈরি করতে বলা হয়েছে তার নাম।

Python program-এর ক্ষেত্রেও argument দেওয়া যায়। যেমন:

```bash
python main.py Masum
```

এখানে `Masum` program-এর কাছে command-line argument হিসেবে পাঠানো হচ্ছে।

Python-এর `sys.argv` এবং `argparse` ব্যবহার করে command-line argument গ্রহণ করার বিস্তারিত পরে শেখা হবে।

---

## 13. Useful Python Commands

Terminal-এ Python-এর সঙ্গে সম্পর্কিত কিছু গুরুত্বপূর্ণ command নিচে দেওয়া হলো।

### Check Python Version

```bash
python --version
```

প্রয়োজনে:

```bash
python3 --version
```

Windows-এ:

```powershell
py --version
```

### Start Python Interactive Mode

```bash
python
```

macOS/Linux-এ প্রয়োজনে:

```bash
python3
```

এতে Python REPL চালু হতে পারে, যেখানে সরাসরি Python statement লেখা যায়।

### Run a Single Line of Python

```bash
python -c "print('Hello, Python!')"
```

macOS/Linux-এ প্রয়োজনে:

```bash
python3 -c "print('Hello, Python!')"
```

### Check pip

```bash
python -m pip --version
```

এই command-গুলো কোন Python interpreter ব্যবহার করছে, তা তোমার system-এর configuration-এর ওপর নির্ভর করে।

---

## 14. Understanding Exit Codes

Command execute হওয়ার পরে process একটি exit code দিতে পারে।

সাধারণভাবে:

- Exit code `0` — সফল execution বোঝায়।
- Non-zero exit code — কোনো সমস্যা বা বিশেষ condition বোঝাতে পারে।

তবে exit code-এর সঠিক অর্থ program অনুযায়ী নির্ধারিত হয়।

### Check Exit Code in PowerShell

```powershell
$LASTEXITCODE
```

### Check Exit Code in Command Prompt

```cmd
echo %ERRORLEVEL%
```

### Check Exit Code in Bash or Similar Shells

```bash
echo $?
```

এগুলো সাধারণত সর্বশেষ external command বা process-এর exit status দেখায়। Shell builtin বা বিশেষ command-এর ক্ষেত্রে behavior ভিন্ন হতে পারে।

Beginner হিসেবে আপাতত এতটুকু জানলেই যথেষ্ট যে command সফল হয়েছে কি না, তা বোঝার একটি উপায় হলো তার exit status পরীক্ষা করা।

---

## 15. Common Terminal Errors

### Error 1: `No such file or directory`

উদাহরণ:

```text
python: can't open file 'main.py'
```

সম্ভাব্য কারণ:

- Terminal সঠিক directory-তে নেই।
- File-এর নাম ভুল।
- File save করা হয়নি।
- File অন্য folder-এ রয়েছে।

সমাধান:

```bash
pwd
```

তারপর file-এর তালিকা দেখো:

```bash
ls
```

Windows PowerShell-এ:

```powershell
Get-Location
Get-ChildItem
```

### Error 2: `Command Not Found`

উদাহরণ:

```text
python: command not found
```

সম্ভাব্য কারণ:

- Python install করা নেই।
- Command-এর নাম ভুল।
- Python executable `PATH`-এ নেই।

সমাধান:

macOS/Linux:

```bash
python3 --version
```

Windows:

```powershell
py --version
```

প্রয়োজনে Python installation ও PATH configuration পরীক্ষা করো।

### Error 3: `Permission Denied`

কোনো file বা directory-তে কাজ করার অনুমতি না থাকলে এই error হতে পারে।

সমাধান:

- সঠিক file ও directory ব্যবহার করো।
- নিজের user directory-তে project রাখো।
- File permission পরীক্ষা করো।
- কারণ না বুঝে সব command administrator বা `sudo` দিয়ে চালিও না।

### Error 4: Wrong Directory

তুমি একটি project folder-এ কাজ করতে চাচ্ছ, কিন্তু Terminal অন্য folder-এ আছে।

সমাধান:

```bash
cd path/to/your/project
```

এখানে `path/to/your/project`-এর পরিবর্তে নিজের প্রকৃত directory path ব্যবহার করবে।

### Error 5: Folder Already Exists

একই নামের folder আগে থেকে থাকলে `mkdir` error দিতে পারে।

সমাধান:

প্রথমে directory list দেখো এবং folder-টি ব্যবহার করা যাবে কি না যাচাই করো।

অপ্রয়োজনীয়ভাবে existing project folder delete কোরো না।

---

## 16. Important Safety Practices

Terminal powerful, কারণ এটি সরাসরি file ও system operation চালাতে পারে।

তাই কিছু নিয়ম মেনে চলবে:

1. Command চালানোর আগে তার কাজ বুঝে নাও।
2. অজানা website থেকে পাওয়া command অন্ধভাবে execute কোরো না।
3. `rm -rf` বা file deletion-এর মতো destructive command সম্পর্কে নিশ্চিত না হয়ে ব্যবহার কোরো না।
4. অপ্রয়োজনীয়ভাবে administrator বা `sudo` permission ব্যবহার কোরো না।
5. Project-এর file ও personal file-এর path যাচাই করো।
6. File overwrite বা delete করতে পারে এমন command চালানোর আগে সতর্ক হও।
7. Terminal-এ password, API key বা secret information প্রকাশ কোরো না।

শুরুতে সাধারণ navigation, directory creation এবং Python execution command-গুলো অনুশীলন করাই যথেষ্ট।

---

## 17. Practice Tasks

### Task 1: Open the Terminal

VS Code-এ Integrated Terminal খোলো।

### Task 2: Check Your Current Directory

Windows PowerShell:

```powershell
Get-Location
```

macOS/Linux:

```bash
pwd
```

### Task 3: Create a Project Folder

```bash
mkdir Python_Practice
```

তারপর folder-এ প্রবেশ করো:

```bash
cd Python_Practice
```

যদি folder আগে থেকেই থাকে, তাহলে নতুন folder তৈরির পরিবর্তে সেটিতে প্রবেশ করো।

### Task 4: Create a Python File

VS Code Explorer দিয়ে `main.py` তৈরি করো।

### Task 5: Write a Program

```python
print("Hello, World!")
print("I can use the terminal.")
```

### Task 6: Run the Program

Windows:

```powershell
python main.py
```

macOS/Linux:

```bash
python3 main.py
```

প্রয়োজন হলে নিজের system-এর উপযুক্ত Python command ব্যবহার করো।

### Task 7: Check the Python Version

```bash
python --version
```

Version না দেখালে operating system অনুযায়ী `python3` বা `py` ব্যবহার করে দেখো।

### Task 8: Open the Folder in VS Code

যদি `code` command configured থাকে:

```bash
code .
```

না থাকলে VS Code-এর `File > Open Folder` ব্যবহার করো।

### Task 9: Explain the Difference

নিজের ভাষায় উত্তর দাও:

1. Terminal কী?
2. CLI ও GUI-এর পার্থক্য কী?
3. Shell কী?
4. `cd` কী কাজে লাগে?
5. `mkdir` কী করে?
6. Current working directory কী?
7. Absolute path ও relative path-এর পার্থক্য কী?
8. Terminal দিয়ে Python program চালানোর সুবিধা কী?

---

## 18. Quick Revision

| Command | Purpose | Common Usage |
|---|---|---|
| `pwd` | Current directory দেখায় | macOS/Linux |
| `cd` | Directory পরিবর্তন করে | সব প্রধান platform-এ |
| `mkdir` | নতুন directory তৈরি করে | সব প্রধান platform-এ |
| `ls` | File ও directory দেখায় | macOS/Linux |
| `dir` | File ও directory দেখায় | Windows Command Prompt |
| `Get-ChildItem` | File ও directory দেখায় | PowerShell |
| `python --version` | Python version দেখায় | Configuration অনুযায়ী |
| `python3 --version` | Python 3 version দেখায় | macOS/Linux-এ সাধারণ |
| `py --version` | Python Launcher-এর version information দেখায় | Windows |
| `python main.py` | Python file execute করে | Python command available হলে |
| `code .` | Current folder VS Code-এ open করে | `code` command configured হলে |

---

## 19. Chapter Connection

এই topic-এ আমরা Terminal, CLI, Shell, working directory, path এবং প্রয়োজনীয় command-line operation শিখেছি।

এখন তুমি Terminal থেকে project folder-এ প্রবেশ করতে, Python file run করতে এবং basic command ব্যবহার করতে পারবে।

পরবর্তী topic-এ আমরা একটি নতুন Python project folder তৈরি করার সঠিক পদ্ধতি শিখব এবং project structure কীভাবে সাজাতে হয় তা বুঝব।

**Next Topic:** [13. Creating a Python Project Folder](13_Creating_a_Python_Project_Folder.md)