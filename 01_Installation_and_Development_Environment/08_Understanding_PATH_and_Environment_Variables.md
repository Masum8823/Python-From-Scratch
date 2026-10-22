# 08. Understanding PATH and Environment Variables

## 1. Introduction

Python install করার পর আমরা Terminal বা Command Prompt-এ নিচের command চালাতে পারি:

```bash
python --version
```

কিন্তু কখনো কখনো এই command চালালে error আসে:

```text
'python' is not recognized as an internal or external command
```

অথবা:

```text
python: command not found
```

এ ধরনের error-এর একটি সাধারণ কারণ হলো `PATH` configuration সঠিক না থাকা।

এই topic-এ আমরা শিখব:

- Environment Variable কী।
- `PATH` কী এবং কেন দরকার।
- Operating System কীভাবে command খুঁজে পায়।
- Python-এর installation path কীভাবে পরীক্ষা করতে হয়।
- Windows, macOS ও Linux-এ `PATH` কীভাবে কাজ করে।
- `python` command কাজ না করলে কীভাবে সমস্যা সমাধান করতে হয়।

---

## 2. What Is an Environment Variable?

**Environment Variable** হলো Operating System-এ সংরক্ষিত একটি named value, যা program ও command-line tools-এর configuration information বহন করে।

সহজভাবে, environment variable-কে computer-এর configuration information রাখার একটি উপায় হিসেবে ভাবতে পারো।

উদাহরণ:

```text
PATH
HOME
USER
TEMP
```

এগুলো বিভিন্ন operating system-এ দেখা যেতে পারে। তবে সব variable সব operating system-এ একইভাবে থাকে না।

### Example

ধরা যাক, একটি environment variable-এর নাম:

```text
APP_MODE
```

এর value হতে পারে:

```text
development
```

তাহলে কোনো application `APP_MODE`-এর value পড়ে বুঝতে পারে যে সেটি development mode-এ চলছে কি না।

Python development-এর ক্ষেত্রে সবচেয়ে গুরুত্বপূর্ণ environment variable-গুলোর একটি হলো `PATH`।

### Why Are Environment Variables Useful?

Environment variables ব্যবহার করে:

- Program-এর configuration নির্ধারণ করা যায়।
- Command-line tools খুঁজে পাওয়া সহজ হয়।
- Temporary file-এর location নির্ধারণ করা যায়।
- বিভিন্ন application-এর environment আলাদা রাখা যায়।
- কিছু application-এর behavior configuration করা যায়।

---

## 3. What Is PATH?

`PATH` হলো একটি environment variable, যেখানে Operating System command-line থেকে চালানোর জন্য executable program খোঁজার directory-গুলোর তালিকা রাখে।

ধরা যাক, তোমার computer-এ Python install করা আছে এই directory-তে:

```text
C:\Users\YourName\AppData\Local\Programs\Python\Python313\
```

এই directory-তে যদি `python.exe` থাকে, তাহলে `PATH`-এ directory-টি থাকলে Windows সাধারণত `python` command-এর মাধ্যমে executable-টি খুঁজে পেতে পারে।

এখানে `YourName` শুধু উদাহরণ; তোমার computer-এ actual user folder-এর নাম আলাদা হবে।

### Simple Example

ধরা যাক, তোমার computer-এ দুটি program আছে:

```text
C:\Tools\Python\
C:\Tools\Git\
```

এই directory-গুলো `PATH`-এ থাকলে command line থেকে সংশ্লিষ্ট executable-গুলো চালানো সহজ হয়।

```powershell
python --version
```

```powershell
git --version
```

তবে command কাজ করার জন্য executable-এর নাম, installation এবং configuration-ও সঠিক হতে হবে।

### Important Concept

`PATH` সাধারণত executable file-এর তালিকা নয়; এটি executable খোঁজার জন্য directory-গুলোর তালিকা।

উদাহরণস্বরূপ:

```text
C:\Tools\Python\
C:\Tools\Git\
```

এগুলো directory-এর path।

সাধারণত `python.exe` বা `git.exe`-এর সম্পূর্ণ file path সরাসরি `PATH`-এ যোগ করার প্রয়োজন হয় না; executable যে directory-তে রয়েছে, সেই directory যোগ করা হয়।

---

## 4. How Does PATH Work?

আমরা যখন Terminal-এ কোনো command লিখি, তখন Operating System বা command interpreter নির্ধারিত নিয়ম অনুযায়ী সেই command-এর executable খুঁজে বের করার চেষ্টা করে।

যেমন:

```bash
python --version
```

এখানে `python` হলো command, আর `--version` হলো version information দেখানোর option।

### Simplified Workflow

```text
User enters: python --version
              |
              v
Command interpreter looks for "python"
              |
              v
Searches available command locations
              |
              v
Finds the Python executable
              |
              v
Python starts and displays its version
```

যদি executable খুঁজে পাওয়া না যায়, তাহলে command not found ধরনের error আসতে পারে।

এই diagram-টি সহজভাবে ধারণা বোঝানোর জন্য। বাস্তবে command খোঁজার নিয়ম operating system, shell, aliases এবং command configuration অনুযায়ী কিছুটা আলাদা হতে পারে।

---

## 5. PATH on Windows

Windows-এ `PATH` environment variable-এ সাধারণত semicolon (`;`) দিয়ে একাধিক directory আলাদা করা হয়।

উদাহরণ:

```text
C:\Windows\System32;C:\Tools\Python;C:\Tools\Git
```

এখানে তিনটি directory রয়েছে:

1. `C:\Windows\System32`
2. `C:\Tools\Python`
3. `C:\Tools\Git`

এটি একটি simplified example; তোমার computer-এর actual `PATH`-এ আরও অনেক directory থাকতে পারে।

### Check PATH in Command Prompt

Command Prompt-এ চালাও:

```cmd
echo %PATH%
```

এটি `PATH` variable-এর value দেখাবে।

### Check PATH in PowerShell

PowerShell-এ চালাও:

```powershell
$env:Path
```

এটিও `PATH`-এর value দেখাবে।

### Check Python Location

Command Prompt বা PowerShell-এ চালাও:

```powershell
where python
```

এটি command search path-এ পাওয়া `python` executable-এর location দেখাতে পারে।

Python Launcher install করা থাকলে সেটিও পরীক্ষা করতে পারো:

```powershell
where py
```

**মনে রাখবে:** `where python` কোনো result না দেখালে এর অর্থ হতে পারে command search path-এ `python` পাওয়া যাচ্ছে না। তবে Python একেবারেই install করা নেই—এটি নিশ্চিতভাবে প্রমাণ হয় না।

---

## 6. PATH on macOS and Linux

macOS ও Linux-এ `PATH` variable-এ সাধারণত colon (`:`) দিয়ে directory-গুলো আলাদা করা হয়।

উদাহরণ:

```text
/usr/local/bin:/usr/bin:/bin
```

এটি একটি illustrative example। তোমার system-এর `PATH` আলাদা হতে পারে।

### Check PATH

Terminal-এ চালাও:

```bash
echo "$PATH"
```

### Find Python 3

```bash
which python3
```

কিছু system-এ `command -v` ব্যবহার করেও command-এর location বা resolution পরীক্ষা করা যায়:

```bash
command -v python3
```

### Example Output

```text
/usr/bin/python3
```

এই output শুধু উদাহরণ। তোমার computer-এ Python অন্য directory-তে থাকতে পারে।

### Important Note

macOS ও Linux-এ system-managed Python থাকতে পারে। System tool-এর জন্য ব্যবহৃত Python অপ্রয়োজনীয়ভাবে সরিয়ে ফেলা বা পরিবর্তন করা উচিত নয়।

নিজস্ব project-এর জন্য virtual environment ব্যবহার করা সাধারণত নিরাপদ ও সুবিধাজনক।

---

## 7. Python Installation Path

Python install করার সময় executable সাধারণত একটি নির্দিষ্ট directory-তে থাকে।

### Example: Windows

```text
C:\Users\YourName\AppData\Local\Programs\Python\Python313\
```

এই directory-তে থাকতে পারে:

```text
python.exe
pythonw.exe
Lib\
Scripts\
```

এগুলো installation-এর উদাহরণ। Python version ও installation options অনুযায়ী directory structure আলাদা হতে পারে।

### Example: macOS or Linux

Python executable থাকতে পারে এমন কিছু location:

```text
/usr/bin/python3
/usr/local/bin/python3
```

কিন্তু এগুলো সব system-এর জন্য universal location নয়।

কোনো package manager বা custom installation অন্য directory ব্যবহার করতে পারে।

### Find the Active Python Executable

সবচেয়ে নির্ভরযোগ্য উপায়গুলোর একটি হলো Python চালিয়ে `sys.executable` পরীক্ষা করা।

```python
import sys

print(sys.executable)
```

এটি বর্তমানে চলমান Python interpreter-এর executable path দেখায়।

Command-line থেকে চালানো যায়:

```bash
python -c "import sys; print(sys.executable)"
```

যদি তোমার system-এ `python` command ব্যবহার করা হয়।

macOS বা Linux-এ প্রয়োজন হলে:

```bash
python3 -c "import sys; print(sys.executable)"
```

---

## 8. How to Add Python to PATH on Windows

Python installer-এ অনেক সময় `Add python.exe to PATH` বা `Add Python to environment variables`-এর মতো option থাকে। Installer-এর version অনুযায়ী wording আলাদা হতে পারে।

Install করার সময় সঠিক option নির্বাচন করলে Python command-line থেকে ব্যবহার করা সহজ হয়।

### Method 1: Use the Python Installer

1. Python-এর official installer চালাও।
2. Installer-এ `Add Python to PATH` বা সংশ্লিষ্ট option থাকলে সেটি নির্বাচন করো।
3. Installation সম্পন্ন করো।
4. নতুন Command Prompt বা PowerShell window খোলো।
5. Version পরীক্ষা করো।

```powershell
python --version
```

তারপর:

```powershell
python -m pip --version
```

এই command-গুলো সঠিক version-এর Python ও pip ব্যবহৃত হচ্ছে কি না যাচাই করতে সাহায্য করে।

### Method 2: Modify PATH Manually

যদি Python install করা থাকে কিন্তু command কাজ না করে, তাহলে `PATH` configuration পরীক্ষা করতে হবে।

Windows-এ:

1. Start menu-তে `Edit environment variables for your account` search করো।
2. সংশ্লিষ্ট settings খোলো।
3. `Environment Variables` নির্বাচন করো, যদি আলাদা window-তে option থাকে।
4. User variables-এর `Path` নির্বাচন করো।
5. `Edit` চাপো।
6. Python-এর সঠিক installation directory প্রয়োজন হলে যোগ করো।
7. Python-এর `Scripts` directory দরকার হলে সেটিও যোগ করো।
8. Settings save করো।
9. নতুন Terminal বা Command Prompt খুলে command পরীক্ষা করো।

উদাহরণস্বরূপ, directory দুটির format এমন হতে পারে:

```text
C:\Users\YourName\AppData\Local\Programs\Python\Python313\
C:\Users\YourName\AppData\Local\Programs\Python\Python313\Scripts\
```

**সতর্কতা:** নিজের computer-এর প্রকৃত installation location যাচাই না করে এই example path কপি করে যোগ কোরো না।

`Scripts` directory-তে `pip`-এর মতো command-line tools-এর executable থাকতে পারে। তবে package install করার সময় `python -m pip` ব্যবহার করলে ভুল Python version-এর সঙ্গে pip মিলে যাওয়ার ঝুঁকি কমে।

### Why Open a New Terminal?

Environment variable-এর পরিবর্তন সাধারণত নতুন process বা Terminal window-তে কার্যকর হয়।

তাই `PATH` পরিবর্তনের পর আগের Terminal-এ command পরীক্ষা না করে একটি নতুন Terminal খুলে পরীক্ষা করা ভালো।

---

## 9. Should You Modify PATH on macOS and Linux?

macOS ও Linux-এ অনেক সময় Python install করার পর executable directory আগে থেকেই `PATH`-এ থাকে।

তাই command কাজ করলে আলাদাভাবে `PATH` পরিবর্তন করার দরকার নেই।

### Check First

```bash
command -v python3
```

তারপর:

```bash
python3 --version
```

যদি command সঠিকভাবে কাজ করে, তাহলে সাধারণত অতিরিক্ত configuration প্রয়োজন হয় না।

### If Python Is Installed but Not Found

1. Python-এর installation location যাচাই করো।
2. Executable আছে কি না পরীক্ষা করো।
3. `PATH`-এ সংশ্লিষ্ট directory আছে কি না দেখো।
4. Terminal-এর shell configuration যাচাই করো।
5. প্রয়োজন হলে official installation instructions অনুসরণ করো।

কিছু shell-এ `PATH` configuration `~/.zshrc`, `~/.bashrc` বা সংশ্লিষ্ট configuration file-এ থাকতে পারে। কোন file পরিবর্তন করতে হবে, তা তোমার shell ও operating system-এর ওপর নির্ভর করে।

System-এর existing `PATH` সম্পূর্ণ replace কোরো না। এতে অন্য command কাজ করা বন্ধ করে দিতে পারে।

---

## 10. Other Useful Environment Variables

`PATH` সবচেয়ে গুরুত্বপূর্ণ হলেও Python development-এ আরও কিছু environment variable সম্পর্কে ধারণা রাখা উপকারী।

| Variable | General Purpose |
|---|---|
| `PATH` | Executable খোঁজার directory-এর তালিকা |
| `HOME` | অনেক Unix-like system-এ user-এর home directory |
| `USERPROFILE` | Windows-এ সাধারণত user profile directory |
| `TEMP` | Windows-এ temporary file-এর directory নির্ধারণে ব্যবহৃত হয় |
| `TMP` | Temporary file-এর location নির্ধারণে ব্যবহৃত হতে পারে |
| `PYTHONPATH` | Python-এর module search path-এ অতিরিক্ত location যোগ করতে পারে |

Environment variable-এর availability ও behavior operating system এবং application অনুযায়ী আলাদা হতে পারে।

### What Is PYTHONPATH?

`PYTHONPATH` হলো একটি optional environment variable, যা Python-এর module search path-এ অতিরিক্ত directory যোগ করতে ব্যবহার করা যায়।

সাধারণ beginner project-এর জন্য সাধারণত এটি পরিবর্তন করার প্রয়োজন হয় না।

ভুলভাবে `PYTHONPATH` configure করলে Python ভুল location থেকে module import করতে পারে।

তাই project-specific module ব্যবহারের জন্য আগে সঠিক folder structure ও virtual environment শেখা ভালো।

---

## 11. PATH vs PYTHONPATH

এই দুটি variable-এর কাজ এক নয়।

| Feature | PATH | PYTHONPATH |
|---|---|---|
| Main purpose | Command-line executable খুঁজে পেতে সাহায্য করা | Python module খোঁজার location-এ directory যোগ করা |
| Used by | Operating system বা command interpreter | Python import system |
| Example | `python --version` চালানোর command resolution | `import my_module`-এর জন্য অতিরিক্ত module location |
| Beginner setup | Python command খুঁজে পাওয়ার জন্য গুরুত্বপূর্ণ | সাধারণত পরিবর্তনের প্রয়োজন নেই |

### Example

ধরা যাক, `python` command কাজ করছে না।

এক্ষেত্রে প্রথমে `PATH` ও Python installation যাচাই করা উচিত।

কিন্তু Python চালু হচ্ছে, অথচ:

```python
import my_module
```

চালালে `ModuleNotFoundError` হচ্ছে, তাহলে module-এর location, project structure, virtual environment এবং import configuration পরীক্ষা করতে হবে।

`PYTHONPATH` সব import problem-এর সমাধান নয়।

---

## 12. Common PATH Errors and Solutions

### Error 1: `python is not recognized`

Windows-এ এমন error দেখা যেতে পারে:

```text
'python' is not recognized as an internal or external command
```

সম্ভাব্য কারণ:

- Python install করা নেই।
- Python-এর directory `PATH`-এ নেই।
- Terminal পুরোনো environment variable ব্যবহার করছে।
- অন্য কোনো command alias বা launcher configuration সমস্যা করছে।

**সমাধান:**

1. Python install করা আছে কি না যাচাই করো।
2. নতুন Terminal খুলে চেষ্টা করো।
3. Windows-এ চালাও:

```powershell
py --version
```

4. কাজ না হলে installation location ও `PATH` পরীক্ষা করো।

### Error 2: `python: command not found`

এটি macOS বা Linux-এ দেখা যেতে পারে।

**সমাধান:**

```bash
python3 --version
```

অনেক system-এ Python 3 চালানোর command হলো `python3`, `python` নয়।

তবুও command কাজ না করলে Python install করা আছে কি না এবং তার executable location পরীক্ষা করো।

### Error 3: Wrong Python Version Runs

তুমি হয়তো একটি version install করেছ, কিন্তু অন্য version চালু হচ্ছে।

**সমাধান:**

Windows:

```powershell
where python
py --list
```

macOS/Linux:

```bash
command -v python3
```

তারপর active interpreter-এর path পরীক্ষা করো:

```bash
python -c "import sys; print(sys.executable)"
```

প্রয়োজনে `python`-এর বদলে সঠিক `python3` command বা Windows Python Launcher ব্যবহার করো।

### Error 4: `pip` Is Not Recognized

কখনো `pip` command কাজ না করলেও Python সঠিকভাবে কাজ করতে পারে।

**Recommended Solution:**

```bash
python -m pip --version
```

macOS/Linux-এ প্রয়োজন হলে:

```bash
python3 -m pip --version
```

এভাবে `pip`-কে নির্দিষ্ট Python interpreter-এর মাধ্যমে চালানো যায়।

### Error 5: Python Works in One Terminal but Not Another

সম্ভাব্য কারণ:

- Terminal-গুলোর environment আলাদা।
- একটি Terminal virtual environment ব্যবহার করছে।
- Shell configuration আলাদা।
- Environment variable পরিবর্তনের পরে একটি Terminal নতুন করে খোলা হয়নি।

**সমাধান:** দুই Terminal-এ version, executable path এবং environment activation পরীক্ষা করো।

---

## 13. PATH and Virtual Environments

Virtual environment ব্যবহার করলে project-এর জন্য আলাদা Python environment তৈরি হয়।

উদাহরণ:

```text
MyProject/
├── .venv/
├── main.py
└── requirements.txt
```

Virtual environment activate করলে Terminal-এর command resolution এমনভাবে পরিবর্তিত হতে পারে, যাতে project-এর `.venv`-এর Python ও package tools আগে ব্যবহৃত হয়।

### Activate on Windows PowerShell

```powershell
.\.venv\Scripts\Activate.ps1
```

### Activate on Windows Command Prompt

```cmd
.venv\Scripts\activate.bat
```

### Activate on macOS and Linux

```bash
source .venv/bin/activate
```

Activation-এর পরে পরীক্ষা করো:

```bash
python --version
```

এবং:

```bash
python -c "import sys; print(sys.executable)"
```

Virtual environment-এর interpreter path দেখালে বোঝা যায় যে project-specific environment ব্যবহৃত হচ্ছে।

Activation command ও environment-এর location সঠিক হতে হবে। PowerShell execution policy-সংক্রান্ত error হলে নিরাপত্তা-সংক্রান্ত setting অন্ধভাবে পরিবর্তন না করে official guidance অনুসরণ করো।

---

## 14. Best Practices

Python development-এর সময় নিচের অভ্যাসগুলো অনুসরণ করো:

1. Python install করার পরে version যাচাই করো।
2. Command কাজ না করলে আগে installation ও executable path পরীক্ষা করো।
3. Windows, macOS ও Linux-এর command এক নয়—নিজের operating system অনুযায়ী command ব্যবহার করো।
4. Project-এর জন্য virtual environment ব্যবহার করো।
5. Package install করতে সম্ভব হলে `python -m pip` ব্যবহার করো।
6. `PATH` পরিবর্তনের আগে existing value পরীক্ষা করো।
7. সম্পূর্ণ `PATH` replace কোরো না।
8. Linux-এর system-managed Python অপ্রয়োজনীয়ভাবে পরিবর্তন কোরো না।
9. `PYTHONPATH` প্রয়োজন না হলে configure কোরো না।
10. VS Code-এর interpreter এবং Terminal-এর interpreter একই কি না যাচাই করো।

---

## 15. Practice Tasks

### Task 1: Display PATH

Windows PowerShell:

```powershell
$env:Path
```

macOS/Linux:

```bash
echo "$PATH"
```

### Task 2: Find Python

Windows:

```powershell
where python
```

macOS/Linux:

```bash
command -v python3
```

### Task 3: Check the Active Interpreter

```python
import sys

print("Version:", sys.version)
print("Executable:", sys.executable)
```

### Task 4: Check pip

```bash
python -m pip --version
```

প্রয়োজন হলে নিজের operating system অনুযায়ী `python3` ব্যবহার করো।

### Task 5: Explain the Difference

নিজের ভাষায় উত্তর দাও:

1. Environment Variable কী?
2. `PATH` কী কাজে লাগে?
3. `PATH` ও `PYTHONPATH`-এর পার্থক্য কী?
4. `python is not recognized` error কেন হয়?
5. `sys.executable` কীভাবে সাহায্য করে?
6. Virtual environment activate করলে command resolution-এ কী পরিবর্তন হতে পারে?

---

## 16. Quick Revision

| Topic | Key Point |
|---|---|
| Environment Variable | Program ও system-এর configuration information বহন করে |
| PATH | Command-line executable খুঁজে পেতে সাহায্য করে |
| Windows PATH separator | Semicolon (`;`) |
| macOS/Linux PATH separator | Colon (`:`) |
| `echo %PATH%` | Windows Command Prompt-এ PATH দেখায় |
| `$env:Path` | PowerShell-এ PATH দেখায় |
| `echo "$PATH"` | macOS/Linux Terminal-এ PATH দেখায় |
| `sys.executable` | চলমান interpreter-এর executable path |
| PYTHONPATH | Python module search path-এ অতিরিক্ত location যোগ করতে পারে |
| Virtual Environment | Project-specific Python environment তৈরি করে |

---

## 17. Chapter Connection

এই topic-এ আমরা Environment Variable, `PATH`, `PYTHONPATH`, executable location এবং সাধারণ command-line error সমাধান করা শিখেছি।

পরবর্তী topic-এ আমরা Python development-এর জন্য ব্যবহৃত একটি গুরুত্বপূর্ণ code editor install ও configure করব।

**Next Topic:** [09. Installing and Setting Up VS Code](09_Installing_and_Setting_Up_VS_Code.md)