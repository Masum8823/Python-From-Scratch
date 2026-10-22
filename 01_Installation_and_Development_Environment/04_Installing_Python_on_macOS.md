# 04. Installing Python on macOS

## 1. Introduction

**macOS** হলো Apple-এর Mac computer-এর operating system। macOS-এ Python programming, web development, automation, data analysis এবং machine learning-এর মতো কাজ করা যায়।

Windows-এর মতো macOS-এও Python install করার আগে operating system version এবং processor architecture সম্পর্কে ধারণা থাকা দরকার।

এই topic শেষে আমরা শিখব:

- macOS version ও processor architecture চেক করতে।
- Official source থেকে Python download করতে।
- Python install করতে।
- Terminal-এ Python version যাচাই করতে।
- `python3` এবং `pip` ব্যবহার করতে।
- Installation-related সাধারণ সমস্যা সমাধান করতে।

---

## 2. Check Your macOS Version

Python install করার আগে নিজের Mac-এর operating system version জেনে নেওয়া ভালো।

### Steps

1. Screen-এর উপরের বাম পাশে Apple menu-তে click করো।
2. **About This Mac** নির্বাচন করো।
3. macOS-এর নাম ও version দেখো।
4. Processor বা chip-এর তথ্যও লক্ষ্য করো।

macOS-এর version অনুযায়ী supported Python release-এর availability আলাদা হতে পারে। তাই installer download করার আগে official documentation-এ compatibility যাচাই করবে।

---

## 3. Understand Intel and Apple Silicon Macs

Mac computer-এ প্রধানত দুই ধরনের processor architecture দেখা যায়।

### A. Intel Mac

পুরোনো অনেক Mac computer-এ Intel processor ব্যবহার করা হয়েছে।

এই ধরনের Mac-এর জন্য compatible Intel বা x86-64 installer নির্বাচন করতে হয়, যদি সেই installer সংশ্লিষ্ট Python release-এর জন্য available থাকে।

### B. Apple Silicon Mac

Apple-এর নিজস্ব chip-ভিত্তিক Mac-গুলো Apple Silicon ব্যবহার করে। এর উদাহরণ হলো M1, M2, M3 এবং পরবর্তী M-series chip।

Apple Silicon-এর native architecture সাধারণত `arm64` হিসেবে পরিচিত।

এই ধরনের Mac-এর জন্য compatible Apple Silicon বা ARM64 installer নির্বাচন করা উচিত, যদি সেটি available থাকে।

### How to Check the Architecture

Terminal খুলে নিচের command চালাও:

```bash
uname -m
```

সাধারণ output:

```text
x86_64
```

এটি সাধারণত Intel architecture নির্দেশ করে।

অথবা:

```text
arm64
```

এটি Apple Silicon architecture নির্দেশ করে।

**Important:** Rosetta-এর মতো compatibility layer-এর অধীনে চলা Terminal application-এ architecture command-এর output ভিন্ন হতে পারে। সন্দেহ হলে **About This Mac**-এ processor বা chip-এর তথ্যও যাচাই করো।

---

## 4. Download Python from the Official Website

Python download করার জন্য official website ব্যবহার করো।

Official website: https://www.python.org/downloads/macos/

### Steps

1. Browser খুলে official Python download page-এ যাও।
2. macOS-এর জন্য available supported stable Python release নির্বাচন করো।
3. নিজের Mac-এর architecture-এর সঙ্গে compatible installer খুঁজে বের করো।
4. Download করার আগে installer-এর description ও system requirements পড়ো।

### Which Version Should You Choose?

সাধারণ beginner-level learning-এর জন্য supported stable Python 3 release উপযুক্ত।

তবে:

- পুরোনো unsupported release এড়িয়ে চলো।
- Existing project-এর version requirement থাকলে সেটি অনুসরণ করো।
- সব package সর্বশেষ Python version-এ সঙ্গে সঙ্গে compatible হবে, এমন ধরে নিয়ো না।
- Download page-এ তোমার architecture-এর জন্য installer না থাকলে official installation instructions অনুসরণ করো।

---

## 5. Understanding the macOS Installer

Python-এর official macOS download page-এ সংশ্লিষ্ট release-এর installer বা installation instructions দেওয়া থাকে।

সাধারণ installer-এর ক্ষেত্রে file extension `.pkg` হতে পারে।

### Installation Steps

1. Download করা installer file-এ double-click করো।
2. Installer window খুললে Continue নির্বাচন করো।
3. License information পড়ে প্রয়োজনীয় confirmation দাও।
4. Installation location ও অন্যান্য option দেখো।
5. Installer-এর নির্দেশনা অনুসরণ করো।
6. প্রয়োজন হলে Mac-এর password দিয়ে installation অনুমোদন করো।
7. Installation শেষ হওয়া পর্যন্ত অপেক্ষা করো।

Installer-এর interface ও options Python release অনুযায়ী পরিবর্তিত হতে পারে।

### Installation Location

Python-এর installation location installer ও installation method অনুযায়ী আলাদা হতে পারে।

তাই নির্দিষ্ট একটি folder-এই Python install হবে—এমন ধরে নেওয়া উচিত নয়।

Installation শেষ হওয়ার পরে Terminal থেকে Python command চালিয়ে পরীক্ষা করাই সবচেয়ে সহজ প্রথম ধাপ।

---

## 6. What Is Terminal in macOS?

**Terminal** হলো macOS-এর command-line application। এর মাধ্যমে text command লিখে computer-কে বিভিন্ন কাজের নির্দেশ দেওয়া যায়।

Python installation যাচাই, program চালানো এবং package manage করার জন্য Terminal ব্যবহার করা হয়।

### How to Open Terminal

1. `Command + Space` চাপো।
2. Spotlight Search খুললে `Terminal` লিখো।
3. Terminal application নির্বাচন করো।

Terminal-এ command লেখার পরে `Enter` চাপলে সেটি execute হয়।

উদাহরণ:

```bash
python3 --version
```

এই command Python 3-এর version পরীক্ষা করে।

---

## 7. Verify Python Installation

Installation শেষ হলে Python সঠিকভাবে কাজ করছে কি না, তা যাচাই করতে হবে।

### Step 1: Check Python Version

Terminal-এ চালাও:

```bash
python3 --version
```

Output এমন হতে পারে:

```text
Python 3.x.y
```

এখানে `3.x.y` example format। তোমার installed version অনুযায়ী প্রকৃত সংখ্যাগুলো আলাদা হবে।

### Step 2: Check the Python Executable

নিচের command চালাও:

```bash
which python3
```

এটি Terminal যে `python3` executable ব্যবহার করছে, তার path দেখাতে পারে।

একাধিক Python installation থাকলে কোন executable চালু হচ্ছে, তা বুঝতে এই command সাহায্য করে।

### Step 3: Check pip

```bash
python3 -m pip --version
```

এই command Python interpreter-এর সঙ্গে যুক্ত `pip`-এর version এবং location দেখাতে পারে।

যদি `pip` available না থাকে, তাহলে error message পড়ে official Python documentation অনুযায়ী সমাধান করতে হবে।

### Important Note

macOS-এ `python3` command ব্যবহার করা সাধারণত উপযুক্ত। সব system-এ `python` এবং `python3` একই interpreter চালাবে—এমন নয়।

---

## 8. Run Your First Python Command

Python install হওয়ার পরে Terminal থেকে একটি ছোট program চালিয়ে দেখা যাক।

```bash
python3 -c "print('Hello, Python on macOS!')"
```

Output:

```text
Hello, Python on macOS!
```

### Understanding the Command

- `python3` Python interpreter চালায়।
- `-c` সরাসরি command-line থেকে Python code execute করতে বলে।
- `print()` output দেখায়।
- `'Hello, Python on macOS!'` হলো output হিসেবে দেখানোর text।

এই command সফলভাবে execute হলে basic Python command-line execution কাজ করছে বলে বোঝা যায়।

---

## 9. Understanding `pip` on macOS

`pip` হলো Python package installer। এটি ব্যবহার করে external Python packages install ও manage করা যায়।

উদাহরণস্বরূপ, কোনো project-এ `requests` package প্রয়োজন হলে নিচের command ব্যবহার করা যায়:

```bash
python3 -m pip install requests
```

তবে package install করার আগে project-এর virtual environment ব্যবহার করা ভালো।

### Why Use `python3 -m pip`?

সরাসরি `pip` command চালালে সেটি অন্য Python installation-এর সঙ্গে যুক্ত থাকতে পারে।

অন্যদিকে:

```bash
python3 -m pip --version
```

নির্দিষ্ট `python3` interpreter-এর সঙ্গে যুক্ত `pip` চালায়।

এতে ভুল Python environment-এ package install করার ঝুঁকি কমে।

---

## 10. Virtual Environments on macOS

একটি Python project-এর package requirements অন্য project থেকে আলাদা হতে পারে।

এই সমস্যা সমাধানের জন্য **virtual environment** ব্যবহার করা হয়।

ধরা যাক, তোমার একটি project-এর জন্য নির্দিষ্ট version-এর package দরকার। অন্য project-এর package version আলাদা হতে পারে।

Virtual environment ব্যবহার করলে project-গুলোর dependencies আলাদা রাখা সহজ হয়।

### Create a Virtual Environment

প্রথমে project folder-এ যাও। তারপর চালাও:

```bash
python3 -m venv .venv
```

এখানে:

- `python3` হলো Python interpreter।
- `-m venv` Python-এর virtual environment module চালায়।
- `.venv` হলো তৈরি হওয়া environment folder-এর নাম।

### Activate the Virtual Environment

```bash
source .venv/bin/activate
```

সফলভাবে activate হলে Terminal prompt-এ সাধারণত `(.venv)` দেখা যায়।

### Install a Package

Environment active থাকা অবস্থায়:

```bash
python -m pip install requests
```

### Deactivate the Environment

```bash
deactivate
```

এতে virtual environment থেকে বের হয়ে আসা যায়।

**Note:** Virtual environment-এর বিস্তারিত আলোচনা Chapter 01-এর `19_Creating_and_Managing_Virtual_Environments.md` ফাইলে থাকবে।

---

## 11. Common Installation Problems

### Problem 1: `python3: command not found`

সম্ভাব্য কারণ:

- Python install হয়নি।
- Python-এর installation location Terminal-এর command search path-এ নেই।
- Installation incomplete হয়েছে।

সমাধান:

1. Installation সফল হয়েছে কি না যাচাই করো।
2. নতুন Terminal window খুলে আবার চেষ্টা করো।
3. `which python3` চালিয়ে দেখো command-এর executable পাওয়া যাচ্ছে কি না।
4. Official installation instructions অনুসরণ করে configuration পরীক্ষা করো।

### Problem 2: Wrong Python Version Appears

একাধিক Python installation থাকলে command অনুযায়ী ভিন্ন version চালু হতে পারে।

যাচাই করো:

```bash
python3 --version
```

```bash
which python3
```

এগুলো version এবং নির্বাচিত executable-এর path সম্পর্কে তথ্য দেয়।

### Problem 3: `pip` Is Not Available

`pip` সরাসরি কাজ না করলে প্রথমে চেষ্টা করো:

```bash
python3 -m pip --version
```

এটিও কাজ না করলে error message অনুযায়ী official Python documentation অনুসরণ করো।

অপরিচিত installation script বা random command চালিয়ে সমস্যা সমাধানের চেষ্টা কোরো না।

### Problem 4: Architecture Mismatch

Intel Mac-এর জন্য তৈরি installer Apple Silicon-এর জন্য native installer-এর সমতুল্য নয়; একইভাবে Apple Silicon installer-ও Intel Mac-এর জন্য নয়।

সমাধান:

1. **About This Mac**-এ processor বা chip যাচাই করো।
2. প্রয়োজনে `uname -m` চালাও।
3. Official download page থেকে compatible installer নির্বাচন করো।

### Problem 5: Permission Error While Installing Packages

কিছু ক্ষেত্রে system-level Python installation-এ package install করার সময় permission error হতে পারে।

সমাধান:

- Project-এর জন্য virtual environment তৈরি করো।
- Environment activate করো।
- Environment-এর মধ্যে package install করো।

সাধারণ project-এর package install করতে অপ্রয়োজনীয়ভাবে `sudo pip install` ব্যবহার কোরো না।

---

## 12. Best Practices for Python on macOS

1. Official source থেকে Python download করো।
2. Supported Python release ব্যবহার করো।
3. Intel ও Apple Silicon architecture-এর পার্থক্য বুঝে installer নির্বাচন করো।
4. Installation শেষে `python3 --version` চালিয়ে verify করো।
5. `python3 -m pip` ব্যবহার করে সঠিক interpreter-এর package manager চালানোর চেষ্টা করো।
6. প্রতিটি project-এর জন্য virtual environment ব্যবহার করার অভ্যাস গড়ে তোলো।
7. System-managed Python installation অপ্রয়োজনীয়ভাবে পরিবর্তন কোরো না।
8. Package installation-এর আগে project-এর requirements যাচাই করো।
9. Error message মনোযোগ দিয়ে পড়ে সমাধান খুঁজো।

---

## 13. Practice Tasks

### Task 1: Identify Your Mac

নিচের তথ্যগুলো সংগ্রহ করো:

- macOS version
- Processor বা chip
- Architecture

### Task 2: Verify Python

Terminal-এ চালাও:

```bash
python3 --version
```

```bash
which python3
```

```bash
python3 -m pip --version
```

### Task 3: Run a Python Command

```bash
python3 -c "print('My Python Setup Is Ready')"
```

Expected output:

```text
My Python Setup Is Ready
```

### Task 4: Create a Virtual Environment

একটি practice folder তৈরি করে সেখানে চালাও:

```bash
python3 -m venv .venv
```

তারপর activate করো:

```bash
source .venv/bin/activate
```

শেষে deactivate করো:

```bash
deactivate
```

### Task 5: Answer These Questions

1. macOS কী?
2. Intel Mac এবং Apple Silicon Mac-এর পার্থক্য কী?
3. `uname -m` command কী কাজে লাগে?
4. macOS-এ সাধারণত `python3` command কেন ব্যবহার করা হয়?
5. `python3 -m pip` ব্যবহারের সুবিধা কী?
6. Virtual environment কেন দরকার?
7. Package installation-এর সময় `sudo pip install` এড়ানো ভালো কেন?

---

## 14. Quick Revision

| Command / Term | Purpose |
|---|---|
| `python3 --version` | Python version পরীক্ষা করা |
| `which python3` | Terminal-এর নির্বাচিত Python executable-এর path দেখা |
| `uname -m` | Machine architecture-এর নাম দেখা |
| `python3 -m pip --version` | Python-এর সঙ্গে যুক্ত pip পরীক্ষা করা |
| `python3 -c "..."` | Terminal থেকে সরাসরি Python code চালানো |
| `python3 -m venv .venv` | Virtual environment তৈরি করা |
| `source .venv/bin/activate` | Virtual environment activate করা |
| `deactivate` | Virtual environment থেকে বের হওয়া |
| `x86_64` | সাধারণত Intel-compatible 64-bit architecture |
| `arm64` | Apple Silicon-এর মতো ARM64 architecture |

---

## 15. Chapter Connection

এই topic-এ macOS-এ Python install, Terminal ব্যবহার, installation verification এবং virtual environment-এর basic command সম্পর্কে ধারণা নেওয়া হয়েছে।

Python Windows, macOS এবং Linux—তিনটি operating system-এই ব্যবহার করা যায়। তবে installation method ও system configuration আলাদা হতে পারে।

**Next Topic:** [05. Installing Python on Linux](05_Installing_Python_on_Linux.md)

পরের topic-এ Linux distribution অনুযায়ী Python installation, package manager এবং system Python নিরাপদে ব্যবহার করার পদ্ধতি শেখা হবে।