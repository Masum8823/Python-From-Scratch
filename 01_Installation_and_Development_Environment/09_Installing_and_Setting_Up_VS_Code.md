# 09. Installing and Setting Up VS Code

## 1. Introduction

**Visual Studio Code (VS Code)** হলো একটি জনপ্রিয়, lightweight code editor, যা দিয়ে Python-সহ বিভিন্ন programming language-এর code লেখা, run, debug এবং manage করা যায়।

Python শেখার জন্য VS Code একটি ভালো choice, কারণ এতে রয়েছে:

- Code writing ও syntax highlighting
- Code completion
- Error detection-এর সুবিধা
- Integrated Terminal
- Debugging tools
- Extensions-এর মাধ্যমে অতিরিক্ত functionality
- Git ও GitHub integration

এই topic-এ আমরা শিখব কীভাবে VS Code install করতে হয় এবং Python programming-এর জন্য প্রস্তুত করতে হয়।

---

## 2. What Is VS Code?

VS Code হলো Microsoft-এর তৈরি একটি source-code editor।

এটি সাধারণ text editor-এর মতো হলেও programming-এর জন্য বিশেষ কিছু সুবিধা দেয়।

উদাহরণস্বরূপ, সাধারণ text editor-এ Python code লিখলে শুধু text দেখা যায়। কিন্তু VS Code-এ Python extension ব্যবহার করলে code completion, debugging এবং interpreter selection-এর মতো সুবিধা পাওয়া যায়।

### VS Code vs Python

এখানে একটি গুরুত্বপূর্ণ পার্থক্য বুঝতে হবে।

| Python | VS Code |
|---|---|
| একটি programming language | একটি code editor |
| Python interpreter code execute করে | Code লেখা, manage ও debug করতে সাহায্য করে |
| Program চালানোর জন্য Python runtime দরকার | Python code edit করার জন্য VS Code ব্যবহার করা যায় |
| `python main.py` দিয়ে program চালানো যায় | VS Code Terminal থেকেও command চালানো যায় |

**মনে রাখবে:** VS Code install করলেই Python automatically install হয়ে যায় না। Python এবং VS Code আলাদাভাবে install করতে হতে পারে।

---

## 3. System Requirements

VS Code install করার আগে নিজের computer-এর operating system ও system requirements যাচাই করো।

VS Code সাধারণত এই operating system-গুলোতে ব্যবহার করা যায়:

- Windows
- macOS
- Linux

Python শেখার জন্য high-end computer বাধ্যতামূলক নয়। Basic Python programming সাধারণ computer-এও করা যায়।

তবে বড় Machine Learning model, data processing বা heavy project-এর জন্য বেশি RAM ও processing power প্রয়োজন হতে পারে।

VS Code-এর latest system requirements জানতে official documentation দেখো:

- [VS Code Requirements](https://code.visualstudio.com/docs/supporting/requirements)

---

## 4. Downloading VS Code

VS Code download করার জন্য official website ব্যবহার করবে।

**Official website:** https://code.visualstudio.com/

ধাপগুলো:

1. Browser-এ official website খোলো।
2. Download option নির্বাচন করো।
3. নিজের operating system অনুযায়ী installer download করো।
4. Download সম্পন্ন হলে installer চালাও।

Third-party website থেকে installer download না করাই ভালো।

### কেন Official Website ব্যবহার করব?

Official website থেকে download করলে software-এর সঠিক distribution পাওয়ার সম্ভাবনা বেশি থাকে এবং unofficial বা modified installer-এর ঝুঁকি কমে।

---

## 5. Installing VS Code on Windows

Windows computer-এ VS Code install করার জন্য নিচের ধাপগুলো অনুসরণ করো।

### Step 1: Run the Installer

Downloaded installer file-এ double-click করো।

Installer-এর নাম version অনুযায়ী আলাদা হতে পারে।

### Step 2: Accept the Agreement

License agreement পড়ে accept করো এবং `Next` চাপো।

### Step 3: Select Installation Location

প্রয়োজনে installation location নির্বাচন করো।

Beginner হিসেবে সাধারণত default location ব্যবহার করতে পারো।

### Step 4: Select Additional Tasks

Installer-এ কিছু optional setting থাকতে পারে। যেমন:

- Add to PATH
- Add `Open with Code` action
- Register Code as an editor
- Create a desktop icon

তোমার প্রয়োজন অনুযায়ী option নির্বাচন করতে পারো।

`Add to PATH` নির্বাচন করা থাকলে Terminal থেকে `code` command ব্যবহার করা সহজ হতে পারে। Installer-এর option ও wording version অনুযায়ী পরিবর্তিত হতে পারে।

### Step 5: Install

`Install` চাপো এবং installation সম্পন্ন হওয়ার জন্য অপেক্ষা করো।

### Step 6: Launch VS Code

Installation শেষে VS Code চালু করো।

এখন editor-এর main interface দেখতে পাবে।

---

## 6. Installing VS Code on macOS

macOS-এ VS Code install করার সাধারণ পদ্ধতি:

1. Official website থেকে macOS version download করো।
2. Download করা archive খুলে VS Code application বের করো।
3. VS Code application-টি `Applications` folder-এ রাখো।
4. Applications থেকে VS Code চালু করো।

macOS-এর version ও download format অনুযায়ী installation process কিছুটা আলাদা হতে পারে।

### Apple Silicon and Intel

Mac computer-এ Intel processor অথবা Apple Silicon processor থাকতে পারে।

Download করার সময় নিজের Mac-এর processor architecture-এর সঙ্গে সামঞ্জস্যপূর্ণ version নির্বাচন করো।

Processor information দেখতে:

1. Apple menu খোলো।
2. `About This Mac` নির্বাচন করো।
3. Chip বা Processor information দেখো।

---

## 7. Installing VS Code on Linux

Linux-এ installation method distribution অনুযায়ী আলাদা হতে পারে।

উদাহরণ:

- Ubuntu বা Debian-এ `.deb` package ব্যবহার করা যেতে পারে।
- Fedora-তে `.rpm` package ব্যবহার করা যেতে পারে।
- কিছু distribution-এ package manager বা অন্য supported installation method রয়েছে।

Official installation guide:

https://code.visualstudio.com/docs/setup/setup-overview

নিজের Linux distribution অনুযায়ী official নির্দেশনা অনুসরণ করো।

অপরিচিত source থেকে package install করার পরিবর্তে official বা trusted package source ব্যবহার করো।

---

## 8. Understanding the VS Code Interface

VS Code প্রথমবার চালু করলে কয়েকটি গুরুত্বপূর্ণ section দেখতে পাবে।

### 8.1 Activity Bar

সাধারণত interface-এর বাম পাশে থাকে।

এখান থেকে Explorer, Search, Source Control, Run and Debug এবং Extensions-এর মতো view খোলা যায়।

### 8.2 Explorer

Explorer দিয়ে project folder ও file দেখা এবং manage করা যায়।

যেমন:

```text
Python_Project/
├── main.py
├── practice.py
└── README.md
```

### 8.3 Editor

Editor হলো যেখানে code লেখা ও পরিবর্তন করা হয়।

যেমন:

```python
print("Hello, Python!")
```

### 8.4 Terminal

Terminal থেকে Python program run করা, package install করা এবং বিভিন্ন command চালানো যায়।

VS Code-এর menu থেকে:

`Terminal > New Terminal`

### 8.5 Extensions

Extensions-এর মাধ্যমে VS Code-এ নতুন feature যোগ করা যায়।

Python programming-এর জন্য Python extension গুরুত্বপূর্ণ।

### 8.6 Status Bar

Editor-এর নিচের দিকে থাকা Status Bar-এ file type, interpreter information এবং অন্যান্য status দেখা যেতে পারে।

Python file-এর ক্ষেত্রে সঠিক interpreter নির্বাচন করা হয়েছে কি না, সেটি এখানে পরীক্ষা করা যায়।

---

## 9. Opening a Project Folder

Python project-এর জন্য একটি নির্দিষ্ট folder ব্যবহার করা ভালো।

ধরা যাক, তোমার project folder-এর নাম:

```text
Python_Basic_to_Pro/
```

VS Code-এ folder খোলার ধাপ:

1. VS Code চালু করো।
2. `File > Open Folder` নির্বাচন করো।
3. নিজের project folder খুঁজে বের করো।
4. Folder নির্বাচন করে open করো।

এখন Explorer-এ project-এর file ও folder দেখা যাবে।

### Why Open a Folder Instead of a Single File?

Project folder open করলে:

- একসঙ্গে project-এর সব file দেখা যায়।
- Relative file path manage করা সহজ হয়।
- Project-specific settings রাখা যায়।
- Terminal সাধারণত project directory-তে খোলা সহজ হয়।
- Git-এর মতো tool ব্যবহার করা সুবিধাজনক হয়।

তাই শুধু `main.py` file open না করে পুরো project folder open করার অভ্যাস তৈরি করো।

---

## 10. Creating Your First Python File

VS Code-এ project folder open করার পরে:

1. Explorer-এর `New File` option নির্বাচন করো।
2. File name দাও:

```text
main.py
```

3. File-এর মধ্যে নিচের code লেখো:

```python
print("Hello, Python!")
print("I am learning Python using VS Code.")
```

4. `Ctrl + S` চাপো file save করার জন্য।

`.py` হলো Python source file-এর extension।

File save করা গুরুত্বপূর্ণ। Save না করা পরিবর্তন run করার সময় বিভ্রান্তি তৈরি করতে পারে।

---

## 11. Opening the Integrated Terminal

VS Code-এর integrated terminal ব্যবহার করে editor-এর ভেতর থেকেই command চালানো যায়।

Terminal খোলার জন্য:

`Terminal > New Terminal`

Windows-এ সাধারণত PowerShell বা Command Prompt ব্যবহার করা যেতে পারে। macOS ও Linux-এ shell অনুযায়ী terminal চালু হয়।

Terminal-এ project directory-এর path দেখতে পারো।

Windows PowerShell-এ:

```powershell
Get-Location
```

macOS/Linux-এ:

```bash
pwd
```

এগুলো বর্তমান working directory দেখায়।

Python program run করার আগে তুমি সঠিক project directory-তে আছ কি না যাচাই করা ভালো।

---

## 12. Running Python Code from VS Code

Python file run করার একাধিক উপায় রয়েছে।

### Method 1: Run Button

Python extension install করার পরে editor-এর উপরে বা অন্য উপযুক্ত location-এ `Run Python File` button দেখা যেতে পারে।

এটি ব্যবহার করে বর্তমান Python file run করা যায়।

### Method 2: Integrated Terminal

Windows-এ:

```powershell
python main.py
```

macOS/Linux-এ:

```bash
python3 main.py
```

কিছু system-এ `python` command-ও কাজ করতে পারে।

### Expected Output

```text
Hello, Python!
I am learning Python using VS Code.
```

### Method 3: Debugging

VS Code-এর Run and Debug feature ব্যবহার করে breakpoint সেট করে code step-by-step execute করা যায়।

Debugging সম্পর্কে বিস্তারিত পরবর্তী relevant topic-এ শেখা হবে।

**গুরুত্বপূর্ণ:** Run button ব্যবহার করার সময় সঠিক Python interpreter নির্বাচন করা থাকতে হবে।

---

## 13. Essential VS Code Keyboard Shortcuts

Keyboard shortcut ব্যবহার করলে coding দ্রুত করা যায়।

| কাজ | Windows/Linux | macOS |
|---|---|---|
| Save File | `Ctrl + S` | `Cmd + S` |
| Open File | `Ctrl + O` | `Cmd + O` |
| Find | `Ctrl + F` | `Cmd + F` |
| Replace | `Ctrl + H` | `Option + Cmd + F` |
| Toggle Terminal | `Ctrl + `` | `Control + `` |
| Command Palette | `Ctrl + Shift + P` | `Cmd + Shift + P` |
| Toggle Comment | `Ctrl + /` | `Cmd + /` |

Shortcut-এর behavior keyboard layout, operating system এবং VS Code configuration অনুযায়ী কিছুটা ভিন্ন হতে পারে।

### Command Palette

Command Palette হলো VS Code-এর বিভিন্ন command খোঁজা ও চালানোর একটি সুবিধাজনক উপায়।

Windows/Linux:

```text
Ctrl + Shift + P
```

macOS:

```text
Cmd + Shift + P
```

এখানে command-এর নাম লিখে সংশ্লিষ্ট action চালাতে পারো।

---

## 14. Basic VS Code Settings

শুরুতে অনেক setting পরিবর্তন করার প্রয়োজন নেই। প্রথমে editor-এর default setting দিয়ে কাজ শেখো।

তবে কিছু setting সম্পর্কে ধারণা রাখা ভালো।

### 14.1 Font Size

Code ছোট দেখালে font size বাড়াতে পারো।

`Ctrl + ,` বা macOS-এ `Cmd + ,` দিয়ে Settings খোলা যায়।

তারপর `Font Size` search করো।

### 14.2 Word Wrap

একটি লম্বা line editor-এর বাইরে চলে গেলে Word Wrap চালু করতে পারো।

Command Palette থেকে `Toggle Word Wrap` search করো।

### 14.3 Auto Save

Auto Save চালু করলে পরিবর্তন নির্দিষ্ট সময় বা configuration অনুযায়ী automatically save হতে পারে।

তবে beginner হিসেবে `Ctrl + S` বা `Cmd + S` দিয়ে নিজে save করার অভ্যাসও রাখো।

### 14.4 Format on Save

Formatter configure করা থাকলে file save করার সময় code formatting automatically করা যায়।

তবে formatter-এর behavior নির্ভর করে সংশ্লিষ্ট extension ও configuration-এর ওপর। এটি Python extension install করলেই সব ক্ষেত্রে automatically কাজ করবে—এমন নয়।

### Recommended Approach

প্রথমে নিচের বিষয়গুলো ঠিক রাখো:

- Code সহজে পড়া যায় এমন font size।
- সঠিক Python interpreter।
- Project folder খোলা।
- Integrated Terminal ব্যবহার করতে পারা।
- File save করার অভ্যাস।

---

## 15. VS Code vs Visual Studio

এই দুটি software-এর নাম কাছাকাছি হলেও এগুলো এক নয়।

| Feature | VS Code | Visual Studio |
|---|---|---|
| Type | Lightweight source-code editor | Full-featured integrated development environment |
| Installation | তুলনামূলকভাবে lightweight | সাধারণত বড় installation |
| Extensions | ব্যাপক extension ecosystem | Workloads ও extensions |
| Python support | Python extension দিয়ে | Supported configuration ও workload অনুযায়ী |
| Common use | বিভিন্ন language-এর development | বিশেষ করে .NET ও Windows development-এ বহুল ব্যবহৃত |

Python শেখার জন্য VS Code একটি ভালো starting option। তবে কোন editor ব্যবহার করবে, তা নিজের project ও প্রয়োজনের ওপর নির্ভর করে।

---

## 16. Common Problems and Solutions

### Problem 1: VS Code Does Not Open

সম্ভাব্য কারণ:

- Installation incomplete।
- Application file সঠিকভাবে install হয়নি।
- Operating system-এর সঙ্গে version সামঞ্জস্যপূর্ণ নয়।

সমাধান:

1. Installation সম্পন্ন হয়েছে কি না যাচাই করো।
2. Official source থেকে সঠিক version download করো।
3. প্রয়োজন হলে official troubleshooting guide দেখো।

### Problem 2: Python Extension Is Missing

সমাধান:

1. VS Code-এর Extensions view খোলো।
2. Search box-এ `Python` লেখো।
3. Microsoft-এর Python extension নির্বাচন করো।
4. Install করো।

Official extension information:

https://marketplace.visualstudio.com/items?itemName=ms-python.python

### Problem 3: Run Button Does Not Appear

সম্ভাব্য কারণ:

- Python extension install করা নেই।
- Python file open করা হয়নি।
- Editor-এর file type সঠিকভাবে detect হয়নি।

সমাধান:

1. File-এর নাম `main.py` কি না পরীক্ষা করো।
2. Python extension install আছে কি না দেখো।
3. Python interpreter select করো।
4. Command Palette থেকে সংশ্লিষ্ট Python command খুঁজে দেখো।

### Problem 4: `python` Command Does Not Work in Terminal

VS Code-এর terminal-ও system-এর Python installation ও command configuration-এর ওপর নির্ভর করে।

Windows-এ পরীক্ষা করো:

```powershell
python --version
py --version
```

macOS/Linux-এ:

```bash
python3 --version
```

কোনো command কাজ না করলে Python installation ও PATH configuration পরীক্ষা করো। আগের topic-এ আমরা এই বিষয়গুলো বিস্তারিত আলোচনা করেছি।

### Problem 5: Wrong Python Interpreter Is Selected

VS Code একাধিক Python installation বা virtual environment খুঁজে পেতে পারে।

সমাধান:

1. Command Palette খোলো।
2. `Python: Select Interpreter` search করো।
3. নিজের project-এর জন্য সঠিক interpreter নির্বাচন করো।
4. Integrated Terminal-এ version ও executable path যাচাই করো।

### Problem 6: Code Runs but Shows Unexpected Output

সম্ভাব্য কারণ:

- অন্য file run হচ্ছে।
- পরিবর্তন save করা হয়নি।
- অন্য interpreter ব্যবহার হচ্ছে।
- Terminal-এর working directory আলাদা।

সমাধান:

1. File save করো।
2. সঠিক file run করো।
3. `sys.executable` দিয়ে interpreter পরীক্ষা করো।
4. `pwd` অথবা `Get-Location` দিয়ে working directory দেখো।

---

## 17. Recommended Project Structure

VS Code-এ Python project এভাবে সাজাতে পারো:

```text
Python_Basic_to_Pro/
├── README.md
├── main.py
├── practice.py
└── notes/
    └── learning_notes.md
```

এখানে:

- `README.md` — project-এর পরিচিতি।
- `main.py` — মূল Python code।
- `practice.py` — practice code।
- `notes/` — অতিরিক্ত learning notes।

Project বড় হলে topic অনুযায়ী আলাদা folder তৈরি করা যায়।

এখনই অনেক folder তৈরি করার প্রয়োজন নেই। প্রথমে simple structure দিয়ে শুরু করো।

---

## 18. Best Practices

1. সব Python project-এর জন্য পরিষ্কার folder structure রাখো।
2. Python file-এর extension `.py` ব্যবহার করো।
3. Code লেখার পর file save করো।
4. Run করার আগে সঠিক interpreter নির্বাচন করো।
5. Integrated Terminal ব্যবহার করতে শেখো।
6. অপ্রয়োজনীয় extension install কোরো না।
7. শুরুতে খুব বেশি editor setting পরিবর্তন কোরো না।
8. Error এলে error message পড়ার অভ্যাস তৈরি করো।
9. Project-এর সব file এক জায়গায় organize করো।
10. VS Code ও Python-এর installation আলাদা—এটি মনে রাখো।

---

## 19. Practice Tasks

নিচের কাজগুলো নিজে করে দেখো।

### Task 1: Install VS Code

Official website থেকে নিজের operating system-এর উপযুক্ত version install করো।

### Task 2: Open a Project Folder

`Python_Practice` নামে একটি folder তৈরি করে VS Code-এ open করো।

### Task 3: Create a Python File

Folder-এর মধ্যে `main.py` নামে file তৈরি করো।

### Task 4: Write Your First Program

```python
print("Hello, World!")
print("I am learning Python.")
print("VS Code is my code editor.")
```

File save করে run করো।

### Task 5: Use the Integrated Terminal

Terminal খুলে Python version পরীক্ষা করো।

```bash
python --version
```

প্রয়োজন হলে:

```bash
python3 --version
```

Windows-এ `python` কাজ না করলে:

```powershell
py --version
```

### Task 6: Check the Interpreter

```python
import sys

print(sys.version)
print(sys.executable)
```

Output দেখে Python version ও executable path বোঝার চেষ্টা করো।

### Task 7: Practice Keyboard Shortcuts

- File save করো।
- Command Palette খোলো।
- Integrated Terminal খোলো।
- Word Wrap toggle করো।

---

## 20. Chapter Summary

এই topic-এ আমরা শিখেছি:

- VS Code কী এবং কেন ব্যবহার করা হয়।
- Python ও VS Code-এর পার্থক্য।
- Windows, macOS ও Linux-এ VS Code install করার পদ্ধতি।
- VS Code interface-এর গুরুত্বপূর্ণ অংশ।
- Project folder ও Python file তৈরি করা।
- Integrated Terminal ব্যবহার করা।
- Python code run করা।
- Basic keyboard shortcuts ও editor settings।
- Common error-এর সমাধান।

### Final Checklist

- [ ] VS Code install করেছি।
- [ ] Python extension install করেছি।
- [ ] Project folder open করতে পারি।
- [ ] `main.py` তৈরি করতে পারি।
- [ ] Integrated Terminal খুলতে পারি।
- [ ] Python version check করতে পারি।
- [ ] Python program run করতে পারি।
- [ ] সঠিক interpreter নির্বাচন করতে পারি।

সবগুলো কাজ করতে পারলে পরের topic শেখার জন্য তুমি প্রস্তুত।

---

## 21. Next Topic

পরবর্তী topic:

**[10. Setting Up the Python Extension](10_Setting_Up_the_Python_Extension.md)**

এখানে Python extension-এর কাজ, installation, প্রয়োজনীয় features, interpreter detection এবং VS Code-এর সঙ্গে Python-এর integration আরও বিস্তারিতভাবে শিখব।