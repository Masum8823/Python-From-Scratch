# 06. Verifying Python Installation

## 1. Introduction

Python install করার পর এটি সঠিকভাবে কাজ করছে কি না, তা পরীক্ষা করা জরুরি। এই প্রক্রিয়াকে **Verifying Python Installation** বলা হয়।

Python install হলেও কখনো command কাজ না করা, ভুল version চালু হওয়া অথবা `pip` খুঁজে না পাওয়ার মতো সমস্যা হতে পারে।

এই topic শেষে আমরা শিখব:

- Python version পরীক্ষা করতে।
- Python interpreter সঠিকভাবে কাজ করছে কি না যাচাই করতে।
- Python executable-এর location দেখতে।
- `pip` কাজ করছে কি না পরীক্ষা করতে।
- একটি ছোট Python program execute করতে।
- Installation-related সমস্যা শনাক্ত করতে।

---

## 2. Open the Terminal

Python verification-এর জন্য একটি command-line tool ব্যবহার করতে হবে।

| Operating System | Terminal Tool |
|---|---|
| Windows | Command Prompt, PowerShell বা Windows Terminal |
| macOS | Terminal |
| Linux | Terminal |

Windows-এ Start Menu থেকে `PowerShell` search করে খুলতে পারো।

macOS-এ Spotlight Search-এ `Terminal` লিখে খুলতে পারো।

Linux-এ application menu থেকে Terminal খুলতে পারো।

**Important:** Command লেখার পরে `Enter` চাপবে। Command-এর output দেখে বুঝতে হবে সেটি সফল হয়েছে কি না।

---

## 3. Check the Python Version

প্রথমে Python version পরীক্ষা করব।

### Windows

```powershell
python --version
```

যদি `python` command কাজ না করে এবং Python Launcher install করা থাকে, তাহলে:

```powershell
py --version
```

### macOS and Linux

```bash
python3 --version
```

### Example Output

```text
Python 3.x.y
```

এখানে `3.x.y` একটি example format। তোমার computer-এ প্রকৃত version number আলাদা হবে।

### Why Is This Command Important?

এই command থেকে জানা যায়:

- Python command চালানো যাচ্ছে কি না।
- কোন Python version চালু হচ্ছে।
- Installation-এর প্রাথমিক verification সফল হয়েছে কি না।

Version output দেখা গেলে বুঝবে যে সংশ্লিষ্ট command-এর মাধ্যমে Python চালানো যাচ্ছে।

তবে শুধু version দেখা মানেই development environment-এর সব configuration ঠিক আছে—এমন নয়।

---

## 4. Check the Python Interpreter

**Python Interpreter** হলো সেই software component, যা Python code execute করে।

Interpreter সঠিকভাবে কাজ করছে কি না, তা পরীক্ষা করার জন্য সরাসরি একটি Python statement চালানো যায়।

### Windows

```powershell
python -c "print('Python is working!')"
```

যদি `python` command কাজ না করে, চেষ্টা করো:

```powershell
py -c "print('Python is working!')"
```

### macOS and Linux

```bash
python3 -c "print('Python is working!')"
```

### Expected Output

```text
Python is working!
```

### Understanding the Command

| Part | Meaning |
|---|---|
| `python` বা `python3` | Python interpreter চালায় |
| `-c` | Command line থেকে সরাসরি Python code execute করে |
| `print()` | Output দেখায় |
| Text inside quotes | যে text output-এ দেখানো হবে |

এই test সফল হলে interpreter একটি সাধারণ Python statement execute করতে পারছে।

---

## 5. Check the Python Executable Location

একটি computer-এ একাধিক Python installation থাকতে পারে। তাই কোন executable চালু হচ্ছে, সেটি জানা গুরুত্বপূর্ণ।

### Windows

PowerShell বা Command Prompt-এ চালাও:

```powershell
where python
```

Python Launcher install থাকলে:

```powershell
where py
```

এগুলো command search path-এ পাওয়া সংশ্লিষ্ট executable-এর location দেখাতে পারে।

**Note:** `where python` কোনো path না দেখালে Python অবশ্যই install করা নেই—এমন নয়। Python অন্য location-এ install থাকতে পারে, অথবা command search path-এ configure করা না থাকতে পারে।

### macOS and Linux

```bash
which python3
```

এই command নির্বাচিত `python3` executable-এর path দেখায়।

### Example Output

```text
/usr/bin/python3
```

অথবা:

```text
/usr/local/bin/python3
```

এগুলো শুধু উদাহরণ। তোমার system-এ path আলাদা হতে পারে।

### Why Is the Location Important?

Executable location জানলে:

- একাধিক Python installation শনাক্ত করা সহজ হয়।
- ভুল Python version চালু হচ্ছে কি না বোঝা যায়।
- VS Code-এ interpreter নির্বাচন করার সময় সাহায্য পাওয়া যায়।
- Command-related সমস্যার কারণ খুঁজে বের করা সহজ হয়।

---

## 6. Check pip Installation

`pip` হলো Python package installer। এটি ব্যবহার করে external Python packages install ও manage করা যায়।

উদাহরণস্বরূপ, কোনো project-এ `requests` বা `numpy` package প্রয়োজন হতে পারে।

### Windows

```powershell
python -m pip --version
```

যদি `python` command কাজ না করে এবং `py` launcher available থাকে:

```powershell
py -m pip --version
```

### macOS and Linux

```bash
python3 -m pip --version
```

### Example Output

```text
pip 25.x from ... (python 3.x)
```

প্রকৃত output-এ pip version, installation location এবং সংশ্লিষ্ট Python version-এর তথ্য থাকতে পারে।

### Why Use `python -m pip`?

সরাসরি `pip` command চালালে সেটি অন্য Python installation-এর সঙ্গে যুক্ত হতে পারে।

অন্যদিকে:

```bash
python3 -m pip --version
```

নির্দিষ্ট `python3` interpreter-এর সঙ্গে যুক্ত `pip` চালায়।

Windows-এ একই ধারণা প্রযোজ্য:

```powershell
python -m pip --version
```

এটি ভুল interpreter-এর অধীনে package install করার ঝুঁকি কমাতে সাহায্য করে।

**Note:** `pip` available না থাকলে error message পড়ে সংশ্লিষ্ট operating system ও Python installation method অনুযায়ী সমাধান করতে হবে। Linux-এর system-managed Python-এ সরাসরি package install না করে virtual environment ব্যবহার করা ভালো।

---

## 7. Check the Python Version from Inside Python

এবার Python interpreter-এর ভেতর থেকে version পরীক্ষা করব।

### Step 1: Open Python Interactive Mode

Windows:

```powershell
python
```

macOS/Linux:

```bash
python3
```

Command সফল হলে Python prompt দেখা যেতে পারে:

```text
>>>
```

এই `>>>` prompt বোঝায় যে তুমি Python interactive mode-এ আছ।

### Step 2: Import the sys Module

```python
import sys
```

`sys` হলো Python-এর standard library-এর একটি module। এটি interpreter ও runtime environment সম্পর্কিত তথ্য দেয়।

### Step 3: Display the Version

```python
print(sys.version)
```

এতে Python-এর version এবং build-related information দেখা যাবে।

আরও সংক্ষিপ্ত version information পেতে:

```python
print(sys.version_info)
```

### Step 4: Exit Python

```python
exit()
```

অথবা সাধারণত `Ctrl + D` ব্যবহার করা যায়; Windows-এর কিছু terminal-এ `Ctrl + Z` চাপার পরে `Enter` ব্যবহার করা যায়।

### Complete Example

```python
import sys

print("Python Version:", sys.version)
print("Version Details:", sys.version_info)
```

এই example-এ interpreter-এর version-related information দেখা যাবে।

---

## 8. Verify Python Using a Script File

Command line থেকে code execute করা একটি প্রাথমিক test। এবার একটি `.py` file তৈরি করে Python program চালাব।

### Step 1: Create a File

একটি folder তৈরি করো:

```text
Python_Practice/
```

তার ভেতরে একটি file তৈরি করো:

```text
verify_python.py
```

### Step 2: Write Python Code

ফাইলের মধ্যে লেখো:

```python
print("Python installation verified successfully!")

name = "Python Learner"
print("Welcome,", name)
```

### Step 3: Save the File

ফাইলটি `verify_python.py` নামেই save করো।

খেয়াল রাখবে, ফাইলটি যেন ভুল করে `verify_python.py.txt` হিসেবে save না হয়।

### Step 4: Open a Terminal in the Correct Folder

Terminal-এ সেই folder-এ যেতে হবে, যেখানে `verify_python.py` file-টি রয়েছে।

যদি file-টি `Python_Practice` folder-এ থাকে, তাহলে Windows-এ উদাহরণস্বরূপ:

```powershell
cd Python_Practice
```

এই command শুধু তখনই কাজ করবে, যখন বর্তমান location থেকে `Python_Practice` folder-এ যাওয়া সম্ভব।

macOS ও Linux-এও `cd` command ব্যবহার করে folder পরিবর্তন করা যায়।

### Step 5: Run the File

Windows:

```powershell
python verify_python.py
```

অথবা:

```powershell
py verify_python.py
```

macOS/Linux:

```bash
python3 verify_python.py
```

### Expected Output

```text
Python installation verified successfully!
Welcome, Python Learner
```

এই output দেখালে সংশ্লিষ্ট interpreter দিয়ে একটি Python script execute করা যাচ্ছে।

---

## 9. Check the Python Version Used by Your Script

একই computer-এ একাধিক Python version থাকলে terminal-এর command এবং code editor-এর নির্বাচিত interpreter আলাদা হতে পারে।

এটি যাচাই করতে `verify_python.py` file-এ নিচের code ব্যবহার করতে পারো:

```python
import sys

print("Python Version:", sys.version)
print("Python Executable:", sys.executable)
```

### Understanding the Output

- `sys.version` Python version সম্পর্কে তথ্য দেয়।
- `sys.executable` বর্তমানে code execute করা Python interpreter-এর executable path দেয়।

এই information বিশেষভাবে কাজে লাগে যখন VS Code-এ code চালালে প্রত্যাশিত Python version পাওয়া যায় না।

---

## 10. Common Verification Problems

### Problem 1: `'python' is not recognized`

Windows-এ এই error-এর অর্থ command search করার সময় `python` নামে executable পাওয়া যাচ্ছে না।

সম্ভাব্য কারণ:

- Python install করা নেই।
- Python-এর installation directory PATH-এ নেই।
- Windows application execution alias-এর কারণে অন্য behavior হচ্ছে।
- Terminal configuration update হয়নি।

সমাধান:

1. নতুন terminal খুলে আবার পরীক্ষা করো।
2. `py --version` চালিয়ে দেখো।
3. Python সঠিকভাবে install হয়েছে কি না যাচাই করো।
4. প্রয়োজনে PATH বা application execution alias configuration পরীক্ষা করো।

### Problem 2: `python3: command not found`

macOS বা Linux-এ এই error হলে Python install হয়েছে কি না এবং command search path সঠিক কি না যাচাই করো।

Linux-এ Python install করার আগে নিজের distribution ও package manager শনাক্ত করো।

macOS-এ official installation instructions অনুসরণ করো।

### Problem 3: `No module named pip`

এই error-এর অর্থ সংশ্লিষ্ট Python interpreter-এর অধীনে `pip` module available নয়।

সমাধান:

1. সঠিক interpreter ব্যবহার করছ কি না যাচাই করো।
2. Python installation method অনুযায়ী `pip` availability পরীক্ষা করো।
3. Linux-এ প্রয়োজনে distribution-এর package manager ব্যবহার করো।
4. Project-এর জন্য virtual environment তৈরি করার কথা বিবেচনা করো।

### Problem 4: Wrong Python Version

Version command প্রত্যাশিত version দেখাচ্ছে না—এমন হলে একাধিক installation থাকতে পারে।

Windows-এ:

```powershell
where python
```

```powershell
py --list
```

macOS/Linux-এ:

```bash
which python3
```

প্রয়োজন হলে Python executable-এর path এবং VS Code-এর নির্বাচিত interpreter তুলনা করো।

### Problem 5: Python Works, but the Script Does Not

সম্ভাব্য কারণ:

- ভুল folder-এ terminal খোলা আছে।
- File name বা extension ভুল।
- Command-এ file name ভুল লেখা হয়েছে।
- Code-এর মধ্যে syntax error আছে।

সমাধান:

1. File-এর নাম যাচাই করো।
2. বর্তমান working directory পরীক্ষা করো।
3. Script-এর path সঠিক কি না দেখো।
4. Error message পড়ে code সংশোধন করো।

---

## 11. Installation Verification Checklist

নিচের checklist ব্যবহার করে নিজের installation পরীক্ষা করো।

- [ ] Terminal খুলতে পারছি।
- [ ] Python version command সফলভাবে execute হচ্ছে।
- [ ] একটি ছোট Python command চালাতে পারছি।
- [ ] Python executable-এর location দেখতে পারছি।
- [ ] `pip` version পরীক্ষা করতে পারছি অথবা কেন available নয় তা বুঝতে পারছি।
- [ ] একটি `.py` file তৈরি করতে পারছি।
- [ ] Terminal থেকে `.py` file execute করতে পারছি।
- [ ] Script-এর মধ্যে `sys.version` ও `sys.executable` ব্যবহার করতে পারছি।

সবগুলো task সফল হলে basic Python installation verification সম্পন্ন হয়েছে।

কোনো একটি task ব্যর্থ হলেও হতাশ হওয়ার দরকার নেই। Error message দেখে সংশ্লিষ্ট configuration ঠিক করতে হবে।

---

## 12. Practice Tasks

### Task 1: Check Python Version

নিজের operating system অনুযায়ী command চালাও।

Windows:

```powershell
python --version
```

macOS/Linux:

```bash
python3 --version
```

### Task 2: Check pip

Windows:

```powershell
python -m pip --version
```

macOS/Linux:

```bash
python3 -m pip --version
```

### Task 3: Run a Python Command

Windows:

```powershell
python -c "print(10 + 20)"
```

macOS/Linux:

```bash
python3 -c "print(10 + 20)"
```

Expected output:

```text
30
```

### Task 4: Create a Verification Script

`system_check.py` নামে একটি file তৈরি করো।

```python
import sys

print("Python Version:", sys.version)
print("Python Executable:", sys.executable)
print("Python is working correctly!")
```

ফাইলটি run করে output দেখো।

### Task 5: Answer These Questions

1. Python installation verify করা কেন জরুরি?
2. `python --version` command কী করে?
3. `sys.version` এবং `sys.executable`-এর কাজ কী?
4. `python -m pip` ব্যবহার করার সুবিধা কী?
5. `python` command কাজ না করলে Windows-এ কোন launcher চেষ্টা করা যেতে পারে?
6. একাধিক Python installation থাকলে কী সমস্যা হতে পারে?
7. Version command সফল হলেও কেন script চালিয়ে পরীক্ষা করা উচিত?

---

## 13. Quick Revision

| Command / Term | Purpose |
|---|---|
| `python --version` | Windows-এ Python version পরীক্ষা করা |
| `python3 --version` | macOS/Linux-এ Python version পরীক্ষা করা |
| `python -c "..."` | Windows-এ সরাসরি Python code execute করা |
| `python3 -c "..."` | macOS/Linux-এ সরাসরি Python code execute করা |
| `where python` | Windows-এ command search path-এ পাওয়া Python executable খোঁজা |
| `which python3` | macOS/Linux-এ নির্বাচিত Python executable-এর path দেখা |
| `python -m pip --version` | Windows-এ সংশ্লিষ্ট interpreter-এর pip পরীক্ষা করা |
| `python3 -m pip --version` | macOS/Linux-এ সংশ্লিষ্ট interpreter-এর pip পরীক্ষা করা |
| `sys.version` | Python version information |
| `sys.executable` | বর্তমানে ব্যবহৃত Python executable-এর path |
| `verify_python.py` | Python script চালানোর verification example |

---

## 14. Chapter Connection

এই topic-এ Python installation-এর পর version, interpreter, executable path, `pip` এবং script execution যাচাই করা শিখেছি।

এখন পরবর্তী ধাপে Python-এর বিভিন্ন version, interpreter এবং একাধিক installation থাকলে সেগুলো কীভাবে কাজ করে, তা আরও বিস্তারিতভাবে বুঝব।

**Next Topic:** [07. Python Version and Interpreter](07_Python_Version_and_Interpreter.md)