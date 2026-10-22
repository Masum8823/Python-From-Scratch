# 05. Installing Python on Linux

## 1. Introduction

**Linux** হলো একটি open-source operating system kernel, যার ওপর ভিত্তি করে Ubuntu, Debian ও Fedora-এর মতো বিভিন্ন Linux distribution তৈরি হয়েছে।

Linux-এ Python programming, web development, automation, data analysis এবং server-side development করা যায়।

অনেক Linux distribution-এ Python আগে থেকেই install করা থাকে। তাই নতুন করে install করার আগে বর্তমান Python version পরীক্ষা করা গুরুত্বপূর্ণ।

এই topic শেষে আমরা শিখব:

- Linux distribution কী।
- আগে থেকে Python install আছে কি না যাচাই করতে।
- Ubuntu ও Debian-এ Python ব্যবহার করতে।
- Fedora-তে Python install করতে।
- Package manager-এর কাজ বুঝতে।
- `pip` ও virtual environment ব্যবহার করতে।
- System Python পরিবর্তন করার ঝুঁকি বুঝতে।

---

## 2. What Is a Linux Distribution?

একটি Linux distribution হলো Linux kernel এবং অন্যান্য software, utilities ও package management tools-এর সমন্বয়ে তৈরি operating system।

### Common Linux Distributions

| Distribution | সাধারণ বৈশিষ্ট্য |
|---|---|
| Ubuntu | Beginner-friendly এবং বহুল ব্যবহৃত |
| Debian | Stability ও reliability-এর জন্য পরিচিত |
| Fedora | আধুনিক software ও development tools সরবরাহ করে |
| Linux Mint | Desktop ব্যবহারকারীদের মধ্যে জনপ্রিয় |
| Arch Linux | Advanced users-দের কাছে পরিচিত |

সব distribution-এ software install করার পদ্ধতি একই নয়।

উদাহরণস্বরূপ:

- Ubuntu ও Debian-এ সাধারণত `apt` ব্যবহার করা হয়।
- Fedora-তে সাধারণত `dnf` ব্যবহার করা হয়।

তাই command চালানোর আগে নিজের Linux distribution শনাক্ত করা উচিত।

---

## 3. Check Your Linux Distribution

প্রথমে নিজের Linux distribution-এর নাম ও version জানতে হবে।

Terminal খুলে নিচের command চালাও:

```bash
cat /etc/os-release
```

Output-এ distribution-এর নাম, version এবং অন্যান্য তথ্য দেখা যেতে পারে।

উদাহরণস্বরূপ, Ubuntu system-এ `NAME` এবং `VERSION` field-এ Ubuntu-সংক্রান্ত তথ্য থাকবে।

Architecture পরীক্ষা করতে:

```bash
uname -m
```

সাধারণ output:

```text
x86_64
```

অথবা:

```text
aarch64
```

এই output-গুলো সাধারণত যথাক্রমে 64-bit x86 এবং 64-bit ARM architecture নির্দেশ করে।

এই তথ্যগুলো জেনে রাখলে সঠিক software package ও installation method নির্বাচন করা সহজ হয়।

---

## 4. Check Whether Python Is Already Installed

Linux-এ Python install করার আগে প্রথমেই পরীক্ষা করো এটি আগে থেকে আছে কি না।

Terminal-এ চালাও:

```bash
python3 --version
```

Output এমন হতে পারে:

```text
Python 3.x.y
```

এখানে `3.x.y` example format। প্রকৃত version তোমার system অনুযায়ী আলাদা হবে।

Python executable-এর location দেখতে:

```bash
which python3
```

এই command Terminal যে `python3` executable ব্যবহার করছে, তার path দেখাতে পারে।

### Why Should You Check First?

আগে থেকে Python install থাকলে নতুন করে install করার প্রয়োজন নাও হতে পারে।

বিশেষ করে Linux system-এর কিছু tools Python-এর ওপর নির্ভর করতে পারে। তাই আগে থেকে থাকা Python সরিয়ে ফেলা বা system version পরিবর্তন করা উচিত নয়।

**Important:** System-এ Python থাকা মানেই প্রতিটি project-এর জন্য আলাদা Python version বা package configuration ব্যবহার করতে হবে না—এমন নয়। Project-এর প্রয়োজন অনুযায়ী আলাদা environment তৈরি করা যায়।

---

## 5. Installing Python on Ubuntu and Debian

Ubuntu ও Debian-এ software install ও manage করার জন্য সাধারণত `apt` package manager ব্যবহার করা হয়।

প্রথমে নিশ্চিত হও যে তুমি Ubuntu/Debian বা compatible distribution ব্যবহার করছ।

### Step 1: Update the Package Information

Terminal-এ চালাও:

```bash
sudo apt update
```

এই command configured software repositories থেকে package information update করে।

এটি সব installed package upgrade করে না; মূলত available package-এর তথ্য refresh করে।

### Understanding the Command

- `sudo` সাধারণ user-কে নির্দিষ্ট command administrator privileges-এ চালাতে দেয়।
- `apt` হলো package management tool।
- `update` repository-র package information refresh করে।

Password চাইলে নিজের user account-এর password দিতে হতে পারে। Password টাইপ করার সময় Terminal-এ character দেখা না গেলেও সেটি স্বাভাবিক হতে পারে।

### Step 2: Install Python 3

```bash
sudo apt install python3
```

এই command configured repositories থেকে available Python 3 package install করে, যদি সেটি আগে থেকে install না থাকে।

Installation-এর আগে Terminal package list দেখাতে পারে। সেখানে package ও storage information যাচাই করে confirmation দিতে হতে পারে।

### Step 3: Verify the Installation

```bash
python3 --version
```

সফলভাবে install হলে Python version দেখা যাবে।

### Step 4: Check pip Availability

```bash
python3 -m pip --version
```

যদি `pip` available না থাকে, তাহলে পরবর্তী section-এর নির্দেশনা অনুসরণ করো।

**Note:** Ubuntu/Debian-এর release অনুযায়ী available Python version এবং package-এর নাম ভিন্ন হতে পারে।

---

## 6. Installing pip on Ubuntu and Debian

`pip` হলো Python package installer। এটি ব্যবহার করে Python-এর external packages install করা যায়।

কিছু Linux distribution-এ Python ও `pip` আলাদাভাবে install করতে হতে পারে।

Ubuntu/Debian-এ সাধারণত নিচের command ব্যবহার করা যায়:

```bash
sudo apt install python3-pip
```

এরপর যাচাই করো:

```bash
python3 -m pip --version
```

তবে modern Linux distribution-এ system-managed Python environment-এর মধ্যে সরাসরি package install করার ক্ষেত্রে restriction থাকতে পারে।

এই restriction এড়ানোর জন্য system configuration পরিবর্তন না করে virtual environment ব্যবহার করা ভালো।

---

## 7. Installing Python on Fedora

Fedora-তে software install করার জন্য সাধারণত `dnf` package manager ব্যবহার করা হয়।

### Step 1: Check Python

```bash
python3 --version
```

Python আগে থেকেই install থাকলে version দেখা যাবে।

### Step 2: Install Python 3

```bash
sudo dnf install python3
```

এই command configured Fedora repositories থেকে available Python 3 package install করে।

### Step 3: Verify the Installation

```bash
python3 --version
```

### Step 4: Check pip

```bash
python3 -m pip --version
```

যদি `pip` available না থাকে, তাহলে Fedora-র package repository ও documentation অনুযায়ী উপযুক্ত package install করতে হবে।

**Important:** Fedora-এর version অনুযায়ী package availability ও installation details পরিবর্তিত হতে পারে।

---

## 8. What Is a Package Manager?

**Package Manager** হলো software install, update, remove এবং manage করার tool।

Linux-এ package manager ব্যবহার করে operating system-এর software repository থেকে software install করা যায়।

### Examples

| Package Manager | Common Distribution |
|---|---|
| `apt` | Ubuntu, Debian |
| `dnf` | Fedora |
| `pacman` | Arch Linux |

### Why Is a Package Manager Useful?

Package manager-এর সাহায্যে:

- Software install করা যায়।
- Repository-র package information update করা যায়।
- Installed package upgrade করা যায়।
- Package dependencies manage করা যায়।
- Package remove করা যায়।

### Important Difference: OS Packages vs Python Packages

Operating system-এর package manager এবং Python-এর `pip` একই tool নয়।

| Tool | সাধারণ কাজ |
|---|---|
| `apt` | Ubuntu/Debian system packages manage করা |
| `dnf` | Fedora system packages manage করা |
| `pip` | Python packages install ও manage করা |
| `venv` | আলাদা Python project environment তৈরি করা |

সাধারণভাবে operating system-এর Python installation manage করতে distribution-এর package manager ব্যবহার করা হয়। আর project-specific Python dependencies manage করতে virtual environment-এর মধ্যে `pip` ব্যবহার করা ভালো।

---

## 9. Understanding System Python

**System Python** বলতে operating system বা তার tools-এর কাজে ব্যবহৃত Python installation-কে বোঝানো হয়।

Linux distribution-এর কিছু system utility Python-এর ওপর নির্ভর করতে পারে।

তাই নিচের কাজগুলো না করাই ভালো:

- System Python-এর executable সরিয়ে ফেলা।
- System-এর গুরুত্বপূর্ণ Python files মুছে ফেলা।
- Package manager দিয়ে manage করা Python installation-কে অপ্রয়োজনীয়ভাবে overwrite করা।
- System Python-এর ওপর জোর করে incompatible package install করা।

### What Should You Do Instead?

নিজের project-এর জন্য আলাদা virtual environment তৈরি করো।

এতে system Python অক্ষত থাকে এবং project-specific package আলাদাভাবে manage করা যায়।

এই পদ্ধতি beginner ও professional—উভয় ধরনের Python development-এর জন্য উপকারী।

---

## 10. Creating a Virtual Environment on Linux

Virtual environment একটি project-এর Python packages আলাদা রাখতে সাহায্য করে।

ধরা যাক, তোমার project folder-এর নাম `my_python_project`।

### Step 1: Create a Project Folder

```bash
mkdir my_python_project
```

### Step 2: Enter the Folder

```bash
cd my_python_project
```

### Step 3: Create a Virtual Environment

```bash
python3 -m venv .venv
```

এখানে:

- `python3` হলো Python interpreter।
- `-m venv` Python-এর virtual environment module চালায়।
- `.venv` হলো environment folder-এর নাম।

### Step 4: Activate the Environment

```bash
source .venv/bin/activate
```

Environment activate হলে Terminal prompt-এ সাধারণত `(.venv)` দেখা যায়।

### Step 5: Check Python Version

```bash
python --version
```

Activated environment-এর মধ্যে `python` সাধারণত সেই environment-এর interpreter ব্যবহার করে।

### Step 6: Install a Package

```bash
python -m pip install requests
```

এই command virtual environment-এর মধ্যে `requests` package install করে।

### Step 7: Deactivate the Environment

```bash
deactivate
```

এতে virtual environment থেকে বের হয়ে আসবে।

### What If the `venv` Module Is Missing?

Ubuntu/Debian-এর কিছু installation-এ virtual environment তৈরি করার জন্য অতিরিক্ত package প্রয়োজন হতে পারে।

যদি `ensurepip` বা `venv`-সংক্রান্ত error পাও, তাহলে নিজের distribution ও release অনুযায়ী উপযুক্ত package install করো।

উদাহরণস্বরূপ, Ubuntu/Debian-এ:

```bash
sudo apt install python3-venv
```

এরপর আবার virtual environment তৈরির command চালিয়ে দেখো।

**Note:** Fedora বা অন্য distribution-এ package name ও installation method আলাদা হতে পারে।

---

## 11. Understanding `sudo`

Linux-এ `sudo` ব্যবহার করে নির্দিষ্ট command administrator privileges-এ চালানো যায়।

উদাহরণ:

```bash
sudo apt install python3
```

এখানে system-level package install করার জন্য administrator permission দরকার হতে পারে।

কিন্তু প্রতিটি Python command-এর আগে `sudo` ব্যবহার করতে হয় না।

উদাহরণস্বরূপ:

```bash
python3 --version
```

এখানে `sudo` দরকার নেই।

একইভাবে, virtual environment activate করা বা তার মধ্যে সাধারণ Python program চালানোর জন্যও সাধারণত `sudo` প্রয়োজন হয় না।

### Why Avoid Unnecessary `sudo`?

অপ্রয়োজনীয় administrator privileges ব্যবহার করলে:

- System files পরিবর্তিত হতে পারে।
- File ownership সমস্যা তৈরি হতে পারে।
- ভুল command চালালে system configuration ক্ষতিগ্রস্ত হতে পারে।

তাই `sudo` শুধু প্রয়োজনীয় ও বোঝা command-এর ক্ষেত্রে ব্যবহার করো।

---

## 12. Common Installation Problems

### Problem 1: `python3: command not found`

সম্ভাব্য কারণ:

- Python install করা নেই।
- Python executable command search path-এ নেই।
- Installation incomplete হয়েছে।

সমাধান:

1. Distribution শনাক্ত করো।
2. Python install আছে কি না যাচাই করো।
3. নিজের distribution-এর package manager ব্যবহার করো।
4. প্রয়োজনে installation path ও shell configuration পরীক্ষা করো।

### Problem 2: `pip` Is Not Available

সমাধান:

প্রথমে চেষ্টা করো:

```bash
python3 -m pip --version
```

Ubuntu/Debian-এ প্রয়োজনে:

```bash
sudo apt install python3-pip
```

এরপর project-এর জন্য virtual environment তৈরি করে package install করো।

### Problem 3: `No module named venv`

সম্ভাব্য কারণ হলো virtual environment তৈরির জন্য প্রয়োজনীয় package install করা নেই।

Ubuntu/Debian-এ চেষ্টা করো:

```bash
sudo apt install python3-venv
```

অন্য distribution হলে সংশ্লিষ্ট official documentation অনুসরণ করো।

### Problem 4: `externally-managed-environment`

কিছু modern Linux distribution-এ system-managed Python installation-এর মধ্যে সরাসরি `pip` দিয়ে package install করতে গেলে এই error দেখা যায়।

এর অর্থ system Python environment distribution-এর package manager দ্বারা পরিচালিত হচ্ছে।

সমাধান:

1. Project folder তৈরি করো।
2. Virtual environment তৈরি করো।
3. Environment activate করো।
4. Environment-এর মধ্যে package install করো।

উদাহরণ:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install requests
```

System protection bypass করার জন্য অপ্রয়োজনীয়ভাবে `--break-system-packages` ব্যবহার কোরো না।

### Problem 5: Permission Denied

সম্ভাব্য কারণ:

- System-level operation-এর জন্য administrator permission নেই।
- Folder বা file-এর ownership ঠিক নেই।
- Protected location-এ write করার চেষ্টা করা হচ্ছে।

সমাধান:

- Command-টি system-level কাজ কি না যাচাই করো।
- নিজের project folder-এ কাজ করো।
- Project dependencies-এর জন্য virtual environment ব্যবহার করো।
- কারণ না বুঝে file permissions পরিবর্তন কোরো না।

---

## 13. Best Practices for Python on Linux

1. Python install করার আগে `python3 --version` চালাও।
2. নিজের Linux distribution শনাক্ত করো।
3. Distribution-এর supported package manager ব্যবহার করো।
4. System Python সরিয়ে ফেলো না।
5. Project-specific dependencies-এর জন্য virtual environment ব্যবহার করো।
6. Virtual environment-এর মধ্যে `python -m pip` ব্যবহার করো।
7. অপ্রয়োজনীয় `sudo` ব্যবহার কোরো না।
8. System-managed Python-এর protection bypass কোরো না।
9. Error message পড়ে distribution-specific solution খুঁজে বের করো।
10. Installation-এর পরে Python ও `pip`-এর version যাচাই করো।

---

## 14. Practice Tasks

### Task 1: Identify Your Distribution

Terminal-এ চালাও:

```bash
cat /etc/os-release
```

Distribution-এর নাম ও version লিখে রাখো।

### Task 2: Check Python

```bash
python3 --version
```

```bash
which python3
```

### Task 3: Check Architecture

```bash
uname -m
```

### Task 4: Create a Virtual Environment

```bash
mkdir python_practice
cd python_practice
python3 -m venv .venv
source .venv/bin/activate
```

Environment active থাকা অবস্থায়:

```bash
python --version
```

শেষ হলে:

```bash
deactivate
```

### Task 5: Answer These Questions

1. Linux distribution কী?
2. Ubuntu/Debian-এ সাধারণত কোন package manager ব্যবহার করা হয়?
3. Fedora-তে সাধারণত কোন package manager ব্যবহার করা হয়?
4. System Python সরিয়ে ফেলা কেন ঝুঁকিপূর্ণ?
5. `pip` এবং `apt`-এর মধ্যে পার্থক্য কী?
6. `externally-managed-environment` error কেন দেখা দিতে পারে?
7. `sudo` কখন ব্যবহার করা উচিত?
8. Virtual environment কীভাবে system Python-কে অপ্রয়োজনীয় পরিবর্তন থেকে রক্ষা করতে সাহায্য করে?

---

## 15. Quick Revision

| Command / Term | Purpose |
|---|---|
| `cat /etc/os-release` | Linux distribution ও version দেখা |
| `uname -m` | Machine architecture দেখা |
| `python3 --version` | Python version পরীক্ষা করা |
| `which python3` | Python executable-এর path দেখা |
| `sudo apt update` | Ubuntu/Debian package information refresh করা |
| `sudo apt install python3` | Ubuntu/Debian repository থেকে Python install করা |
| `sudo dnf install python3` | Fedora repository থেকে Python install করা |
| `python3 -m venv .venv` | Virtual environment তৈরি করা |
| `source .venv/bin/activate` | Virtual environment activate করা |
| `python -m pip install requests` | Active environment-এ package install করা |
| `deactivate` | Virtual environment থেকে বের হওয়া |
| `sudo` | Administrator privileges-এ command চালানো |

---

## 16. Chapter Connection

এই topic-এ Linux-এ Python installation, package manager, system Python এবং virtual environment সম্পর্কে ধারণা নেওয়া হয়েছে।

Windows, macOS ও Linux—প্রতিটি operating system-এ Python ব্যবহার করা যায়। তবে installation method এবং command আলাদা হতে পারে।

**Next Topic:** [06. Verifying Python Installation](06_Verifying_Python_Installation.md)

পরবর্তী topic-এ তিনটি operating system-এই Python installation কীভাবে যাচাই করতে হয়, interpreter ঠিকভাবে কাজ করছে কি না এবং version ও executable path কীভাবে পরীক্ষা করতে হয়, তা একসঙ্গে শেখা হবে।