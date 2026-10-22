# 03. Installing Python on Windows

## 1. Introduction

Python programming শুরু করার আগে computer-এ Python install করতে হবে।

এই topic-এ আমরা Windows operating system-এ Python download, install এবং configure করার পদ্ধতি শিখব।

এই topic শেষে আমরা পারব:

- Official website থেকে Python download করতে।
- সঠিক Python installer নির্বাচন করতে।
- Windows-এ Python install করতে।
- `Add Python to PATH` option-এর কাজ বুঝতে।
- Python installation verify করতে।
- Installation-related সাধারণ সমস্যাগুলো সমাধান করতে।

---

## 2. Download Python from the Official Website

Python download করার জন্য official website ব্যবহার করা সবচেয়ে নিরাপদ পদ্ধতি।

Official website: https://www.python.org/downloads/windows/

এই website-এ Windows-এর জন্য available Python release ও installer পাওয়া যায়।

### Step 1: Open the Website

1. Browser খুলে official Python download page-এ যাও।
2. Windows-এর জন্য available stable Python release খুঁজে বের করো।
3. নিজের operating system-এর সঙ্গে compatible installer নির্বাচন করো।

### Step 2: Choose the Correct Version

সাধারণভাবে নতুন project শুরু করার সময় একটি supported, stable Python 3 release ব্যবহার করা ভালো।

Python-এর একাধিক version থাকতে পারে। সব version-এর feature, compatibility ও support period এক নয়।

তাই:

- Supported stable release নির্বাচন করো।
- পুরোনো tutorial অনুসরণ করলে tutorial-এর version requirement যাচাই করো।
- কোনো project নির্দিষ্ট Python version চাইলে সেই requirement অনুসরণ করো।
- অপ্রয়োজনীয়ভাবে পুরোনো বা unsupported version install কোরো না।

**Important:** সর্বশেষ version সব third-party package-এর সঙ্গে সঙ্গে compatible হবে—এমন নিশ্চয়তা নেই। Project-এর compatibility গুরুত্বপূর্ণ।

---

## 3. Understanding Python Installers

Windows-এর জন্য Python-এর বিভিন্ন installer বা installation option পাওয়া যেতে পারে। কোন installer পাওয়া যাচ্ছে, তা Python release অনুযায়ী পরিবর্তিত হতে পারে।

সাধারণ installer type-এর উদাহরণ:

| Installer Type | ব্যবহার |
|---|---|
| 64-bit installer | Compatible 64-bit Windows system-এর জন্য |
| 32-bit installer | Compatible 32-bit Windows system-এর জন্য, যদি সংশ্লিষ্ট release-এ available থাকে |
| Embeddable package | বিশেষ application-এর মধ্যে Python embed করার মতো নির্দিষ্ট use case-এর জন্য |
| Install manager বা নতুন installation option | সংশ্লিষ্ট release-এর official instructions অনুযায়ী Python manage করার জন্য |

### Which One Should a Beginner Choose?

সাধারণ Windows computer-এ beginner হিসেবে official website-এ দেওয়া **recommended standard installation option** নির্বাচন করো।

যদি traditional installer ব্যবহার করো, তাহলে নিজের Windows architecture-এর সঙ্গে compatible installer বেছে নাও।

শুধু file-এর নাম দেখে অনুমান না করে download page-এর description পড়বে।

---

## 4. Run the Python Installer

Installer download হয়ে গেলে সেটি সাধারণত Downloads folder-এ পাওয়া যাবে।

### Step 1: Open the Installer

1. Downloads folder খোলো।
2. Download করা Python installer-এ double-click করো।
3. Installer window খুললে সেখানে থাকা options ভালোভাবে দেখো।

Windows security prompt এলে installer-এর publisher এবং source যাচাই করো।

### Step 2: Understand the Installation Options

Traditional Python installer-এ কিছু গুরুত্বপূর্ণ option থাকতে পারে।

#### A. Install Now

এই option সাধারণত recommended default settings ব্যবহার করে Python install করার সহজ উপায়।

Beginner-দের জন্য এটি অনেক ক্ষেত্রে উপযুক্ত।

#### B. Customize Installation

এই option ব্যবহার করে installation-এর বিভিন্ন component এবং location-এর মতো settings নির্বাচন করা যায়।

কেন কোনো setting পরিবর্তন করতে হবে, তা না জানলে default configuration অনুসরণ করাই ভালো।

#### C. Add Python to PATH

এই option Python command-কে terminal থেকে সহজে ব্যবহার করার সুযোগ দেয়।

যদি installer-এ এই checkbox থাকে, তাহলে সাধারণ command-line setup-এর জন্য এটি নির্বাচন করা উপকারী।

এ বিষয়ে বিস্তারিত পরবর্তী topic-এ আলোচনা করা হবে।

**Note:** নতুন Python installation manager বা installer interface-এ option-এর নাম ও layout আলাদা হতে পারে। সে ক্ষেত্রে সংশ্লিষ্ট official installation instructions অনুসরণ করবে।

---

## 5. Install Python Using the Default Settings

Beginner হিসেবে installation-এর সময় অপ্রয়োজনীয় settings পরিবর্তন করার দরকার নেই।

Traditional installer ব্যবহার করলে সাধারণ workflow হলো:

1. Installer চালু করো।
2. `Add Python to PATH` option থাকলে সেটি নির্বাচন করো।
3. Recommended installation option নির্বাচন করো।
4. প্রয়োজন হলে Windows security permission দাও।
5. Installation সম্পন্ন হওয়ার জন্য অপেক্ষা করো।
6. সফলভাবে installation সম্পন্ন হয়েছে কি না যাচাই করো।

সব installer-এ একই screen বা button থাকবে না। তাই installer-এর version অনুযায়ী steps কিছুটা আলাদা হতে পারে।

### Installation Location

Python সাধারণত user-specific বা system-level installation location-এ install হতে পারে।

উদাহরণস্বরূপ, installation path দেখতে এমন হতে পারে:

```text
C:\Users\YourUsername\AppData\Local\Programs\Python\Python3XX\
```

এখানে `YourUsername` এবং `Python3XX` example হিসেবে দেখানো হয়েছে। তোমার computer-এ path ও version number আলাদা হতে পারে।

Installation path মুখস্থ করার দরকার নেই। তবে Python কোথায় install হয়েছে, তা জানা থাকলে troubleshooting সহজ হয়।

---

## 6. Understanding the Python Installation Components

Python install করার সময় বা installation-এর পরে বিভিন্ন component দেখতে পারো।

| Component | কাজ |
|---|---|
| Python Interpreter | Python code execute করে |
| Standard Library | Python-এর built-in modules ও utilities সরবরাহ করে |
| `pip` | Python packages install ও manage করতে সাহায্য করে |
| Python Launcher | Windows-এ installed Python version নির্বাচন করে চালাতে সাহায্য করতে পারে |
| IDLE | Python-এর basic interactive development environment |
| Documentation | Python-এর documentation; installer বা installation option অনুযায়ী available হতে পারে |

সব component প্রতিটি installation method-এ একইভাবে উপস্থিত থাকবে না।

### Python Interpreter

Interpreter Python code execute করে। এটি ছাড়া সাধারণভাবে Python program চালানো সম্ভব হবে না।

### pip

`pip` ব্যবহার করে external Python package install করা যায়।

উদাহরণ:

```powershell
python -m pip --version
```

এই command Python-এর সঙ্গে যুক্ত `pip`-এর version পরীক্ষা করতে সাহায্য করে।

### IDLE

IDLE একটি basic environment, যেখানে Python code লেখা এবং interactive mode-এ পরীক্ষা করা যায়।

তবে বড় project-এর জন্য অনেক developer VS Code বা অন্য code editor ব্যবহার করেন।

---

## 7. Verify Python Installation

Python install করার পরে অবশ্যই installation পরীক্ষা করতে হবে।

### Step 1: Open a Terminal

Windows-এ নিচের যেকোনো একটি ব্যবহার করতে পারো:

- Command Prompt
- PowerShell
- Windows Terminal

Start Menu থেকে search করে terminal খুলতে পারো।

### Step 2: Check the Python Version

নিচের command চালাও:

```powershell
python --version
```

অথবা:

```powershell
python -V
```

Installation এবং command configuration সঠিক থাকলে output এমন হতে পারে:

```text
Python 3.x.y
```

এখানে `3.x.y` শুধু example format; তোমার installed version অনুযায়ী প্রকৃত সংখ্যাগুলো আলাদা হবে।

### Step 3: Try the Python Launcher

যদি `py` launcher install করা থাকে, তাহলে চালাও:

```powershell
py --version
```

কিছু Windows setup-এ `py` কাজ করতে পারে, যদিও `python` command কাজ করছে না—বা উল্টোটাও হতে পারে।

### Step 4: Check pip

```powershell
python -m pip --version
```

এই command সফল হলে `pip`-এর version এবং সংশ্লিষ্ট installation location দেখাতে পারে।

**Important:** Version command সফল হওয়া মানে Python command ব্যবহার করা যাচ্ছে। তবে development-এর জন্য VS Code, interpreter selection এবং project environment-ও পরে যাচাই করতে হবে।

---

## 8. Run Your First Python Command

Python installation verify করার পরে একটি ছোট command চালিয়ে দেখতে পারো।

Terminal-এ লেখো:

```powershell
python -c "print('Hello, Python!')"
```

Output:

```text
Hello, Python!
```

এই command-এ:

- `python` Python interpreter চালায়।
- `-c` terminal থেকে সরাসরি Python code execute করতে বলে।
- `print()` text output দেখায়।
- `'Hello, Python!'` হলো output হিসেবে দেখানোর text।

যদি `python` command কাজ না করে কিন্তু `py` launcher কাজ করে, তাহলে এই command-টিও চেষ্টা করতে পারো:

```powershell
py -c "print('Hello, Python!')"
```

---

## 9. Common Installation Problems

### Problem 1: `'python' is not recognized`

সম্ভাব্য কারণ:

- Python install হয়নি।
- Python-এর installation directory `PATH`-এ নেই।
- Terminal পুরোনো environment ব্যবহার করছে।
- Windows-এর application execution alias-এর কারণে অন্য command behavior হচ্ছে।

সমাধান:

1. নতুন terminal খুলে আবার চেষ্টা করো।
2. `py --version` চালিয়ে দেখো।
3. Python সঠিকভাবে install হয়েছে কি না যাচাই করো।
4. প্রয়োজনে installer চালিয়ে PATH configuration ঠিক করো।

### Problem 2: Python Opens Microsoft Store

কখনো Windows-এর application execution alias-এর কারণে `python` command Microsoft Store খুলতে পারে।

সমাধান:

1. `py --version` চেষ্টা করো।
2. Python-এর installation যাচাই করো।
3. প্রয়োজনে Windows-এর **Manage app execution aliases** settings পরীক্ষা করো।
4. Python-এর সঠিক executable ও command configuration নিশ্চিত করো।

সমস্যার কারণ নিশ্চিত না হয়ে অপ্রয়োজনীয় settings পরিবর্তন কোরো না।

### Problem 3: Wrong Python Version Appears

Computer-এ একাধিক Python version install থাকলে command অনুযায়ী ভিন্ন version চালু হতে পারে।

যাচাই করো:

```powershell
python --version
```

```powershell
py --list
```

দ্বিতীয় command supported Python launcher-এ installed Python runtime-এর তালিকা দেখাতে পারে। Launcher version অনুযায়ী command-এর availability আলাদা হতে পারে।

### Problem 4: Installation Fails

সম্ভাব্য কারণ:

- Incomplete installer download
- Permission-related problem
- Unsupported operating system
- Conflicting installation settings
- Insufficient disk space

সমাধান:

1. Official source থেকে installer আবার download করো।
2. Windows version ও architecture যাচাই করো।
3. পর্যাপ্ত disk space আছে কি না দেখো।
4. প্রয়োজনে installation log বা error message পরীক্ষা করো।

### Problem 5: pip Command Is Not Recognized

`pip` সরাসরি কাজ না করলেও Python-এর মাধ্যমে এটি চালানো সম্ভব হতে পারে।

চেষ্টা করো:

```powershell
python -m pip --version
```

Package install করার জন্যও সাধারণভাবে নিচের format ব্যবহার করা যায়:

```powershell
python -m pip install package_name
```

এখানে `package_name`-এর জায়গায় প্রকৃত package-এর নাম লিখতে হবে।

---

## 10. Important Installation Best Practices

Python install করার সময় কয়েকটি নিয়ম অনুসরণ করা ভালো:

1. Official Python website বা trusted official installation method ব্যবহার করো।
2. Supported stable Python version নির্বাচন করো।
3. নিজের operating system-এর সঙ্গে compatible installer ব্যবহার করো।
4. Installer-এর options না বুঝে পরিবর্তন কোরো না।
5. Installation শেষে version command চালিয়ে verify করো।
6. Python install করার পর terminal ও VS Code-এ interpreter configuration যাচাই করো।
7. প্রতিটি project-এর জন্য প্রয়োজন হলে আলাদা virtual environment ব্যবহার করো।
8. System-wide configuration অপ্রয়োজনীয়ভাবে পরিবর্তন কোরো না।

---

## 11. Practice Tasks

### Task 1: Download and Install Python

Official website থেকে Windows-এর জন্য উপযুক্ত Python installation option নির্বাচন করো এবং installation সম্পন্ন করো।

Official download page:

https://www.python.org/downloads/windows/

### Task 2: Verify the Installation

নিচের command-গুলো চালিয়ে দেখো:

```powershell
python --version
```

```powershell
py --version
```

```powershell
python -m pip --version
```

সব command প্রতিটি system-এ একইভাবে কাজ করতেই হবে—এমন নয়। কোন command কাজ করছে এবং কোনটি করছে না, তা লিখে রাখো।

### Task 3: Run a Python Command

```powershell
python -c "print('My Python Setup Is Ready')"
```

Output:

```text
My Python Setup Is Ready
```

### Task 4: Answer These Questions

1. Python-এর official download website কোনটি?
2. Python installer কী?
3. `Add Python to PATH` option-এর কাজ কী?
4. Python installation verify করতে কোন command ব্যবহার করা যায়?
5. `pip` কী কাজে লাগে?
6. `python` command কাজ না করলে কোন Windows launcher command চেষ্টা করা যেতে পারে?
7. Installation-এর পরে কেন version check করা জরুরি?

---

## 12. Quick Revision

| Command / Term | Purpose |
|---|---|
| Official Python Website | Python download করার trusted source |
| Installer | Python install করার software |
| `python --version` | Python version পরীক্ষা করা |
| `python -V` | Python version পরীক্ষা করা |
| `py --version` | Windows Python launcher-এর version পরীক্ষা করা |
| `python -m pip --version` | Python-এর সঙ্গে যুক্ত pip পরীক্ষা করা |
| `python -c "..."` | Terminal থেকে সরাসরি Python code চালানো |
| PATH | Terminal থেকে executable খুঁজে পাওয়ার configuration |
| Interpreter | Python code execute করে |

---

## 13. Chapter Connection

এই topic-এ Windows-এ Python download, installation এবং basic verification শিখেছি।

Python install করার পরে terminal-এ command চালাতে পারা গুরুত্বপূর্ণ। তবে command কাজ করার জন্য PATH এবং environment configuration-ও সঠিক হতে হয়।

**Next Topic:** [04. Installing Python on macOS](04_Installing_Python_on_macOS.md)

macOS ব্যবহার না করলেও এই ফাইলটি repository-তে রাখা হবে, যাতে ভবিষ্যতে অন্য operating system-এ কাজ করার সময় reference হিসেবে ব্যবহার করা যায়।