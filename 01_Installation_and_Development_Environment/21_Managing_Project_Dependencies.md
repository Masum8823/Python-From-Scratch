# 21. Managing Project Dependencies

## 1. Introduction

Python project তৈরি করার সময় শুধু নিজের লেখা code-ই ব্যবহার করা হয় না। অনেক সময় অন্য developer-দের তৈরি package ও external tool ব্যবহার করতে হয়।

এই package বা tool-গুলোর ওপর project নির্ভর করলে সেগুলোকে **Dependencies** বলা হয়।

যেমন, একটি data analysis project-এ `pandas` ও `numpy` ব্যবহার করা হতে পারে। একটি web application-এ `flask` ব্যবহার করা হতে পারে।

কিন্তু project-এর dependency সঠিকভাবে manage না করলে বিভিন্ন সমস্যা দেখা দিতে পারে:

- অন্য কম্পিউটারে project চালানো যায় না।
- Package-এর version আলাদা হওয়ায় program-এর আচরণ বদলে যায়।
- দুটি package-এর মধ্যে conflict হয়।
- অপ্রয়োজনীয় package project-কে জটিল করে তোলে।
- পুরোনো project পরে আবার চালানো কঠিন হয়।

এই সমস্যাগুলো কমানোর জন্য dependency management শেখা জরুরি।

এই topic-এ আমরা শিখব:

1. Project dependency কী।
2. Direct ও transitive dependency-এর পার্থক্য।
3. Dependency version কীভাবে manage করতে হয়।
4. `requirements.txt` ব্যবহার।
5. `pip freeze`-এর সুবিধা ও সীমাবদ্ধতা।
6. Dependency conflict সমাধান।
7. Clean environment-এ project setup।
8. Dependency management-এর best practices।

---

## 2. What Is a Project Dependency?

Dependency হলো এমন কোনো package, library, tool বা software, যার ওপর project-এর কোনো অংশ নির্ভর করে।

উদাহরণ:

```python
import requests

response = requests.get("https://example.com", timeout=10)

print(response.status_code)
```

এখানে `requests` package ছাড়া এই code সাধারণভাবে কাজ করবে না।

তাই `requests` হলো project-এর একটি direct dependency।

### Common Types of Dependencies

| Type | Meaning | Example |
|---|---|---|
| Direct dependency | Project সরাসরি ব্যবহার করে | `requests` |
| Transitive dependency | অন্য dependency-এর প্রয়োজনে লাগে | `requests`-এর ব্যবহৃত কোনো dependency |
| Development dependency | Development বা testing-এ কাজে লাগে | `pytest` |
| Optional dependency | নির্দিষ্ট feature-এর জন্য প্রয়োজন | কোনো অতিরিক্ত export feature-এর package |
| System dependency | Operating system বা system-level software | কোনো native library বা external executable |

সব project-এ এই প্রতিটি category থাকবে, এমন নয়।

---

## 3. Direct Dependencies

Direct dependency হলো সেই package, যা project-এর code সরাসরি import করে অথবা যার functionality সরাসরি ব্যবহার করে।

উদাহরণ:

```python
import requests
import pandas
```

এখানে project সরাসরি `requests` এবং `pandas` ব্যবহার করছে।

তাই এগুলো project-এর direct dependency।

### Why Should Direct Dependencies Be Documented?

ধরা যাক, অন্য একজন developer তোমার project GitHub থেকে clone করেছে।

সে যদি জানে না কোন package install করতে হবে, তাহলে code চালানোর সময় এমন error পেতে পারে:

```text
ModuleNotFoundError: No module named 'requests'
```

Direct dependency document করা থাকলে project setup সহজ হয়।

উদাহরণ `requirements.txt`:

```text
requests
pandas
```

এখানে project-এর দুটি direct dependency লেখা হয়েছে।

**Best practice:** Project-এর জন্য তুমি সরাসরি যে external package ব্যবহার করো, সেগুলো স্পষ্টভাবে document করো।

---

## 4. Transitive Dependencies

Transitive dependency হলো এমন package, যা project সরাসরি ব্যবহার না করলেও অন্য কোনো dependency-এর কাজ করার জন্য প্রয়োজন হয়।

ধরা যাক:

```text
Your Project
    |
    v
Package A
    |
    v
Package B
```

এখানে:

- Your Project সরাসরি `Package A` ব্যবহার করে।
- `Package A` কাজ করার জন্য `Package B` ব্যবহার করে।
- তাই `Package B` হলো transitive dependency।

বাস্তবে একটি package-এর একাধিক transitive dependency থাকতে পারে।

### Why Are Transitive Dependencies Important?

কারণ এগুলোও project-এর installation, compatibility ও security-কে প্রভাবিত করতে পারে।

যেমন:

- Transitive dependency-এর version পরিবর্তিত হতে পারে।
- Dependency update-এর ফলে breaking change আসতে পারে।
- কোনো dependency-তে security vulnerability থাকতে পারে।

তাই শুধু direct dependency দেখলেই সব dependency-related সমস্যা বোঝা যায় না।

### Important Distinction

`requirements.txt`-এ সরাসরি package-এর নাম লেখা এবং `pip freeze` দিয়ে সব installed package-এর তালিকা তৈরি করা এক বিষয় নয়।

`pip freeze` সাধারণত বর্তমান environment-এর installed distribution-গুলোর version দেখায়। এতে direct ও transitive—দুই ধরনের dependency-ই থাকতে পারে।

---

## 5. Why Does Dependency Management Matter?

Dependency management-এর কয়েকটি গুরুত্বপূর্ণ উদ্দেশ্য রয়েছে।

### 5.1 Reproducibility

অন্য কম্পিউটারেও একই বা কাছাকাছি dependency configuration তৈরি করতে সাহায্য করে।

### 5.2 Compatibility

একটি package অন্য package-এর সঙ্গে compatible কি না, তা নিয়ন্ত্রণ ও যাচাই করতে সাহায্য করে।

### 5.3 Maintainability

Project-এর dependency সম্পর্কে পরিষ্কার ধারণা থাকলে ভবিষ্যতে update করা সহজ হয়।

### 5.4 Collaboration

Team-এর সবাই একই dependency setup অনুসরণ করতে পারে।

### 5.5 Security

Package update, vulnerability review এবং অপ্রয়োজনীয় dependency বাদ দেওয়া সহজ হয়।

### 5.6 Troubleshooting

কোন version ব্যবহার করা হচ্ছে তা জানা থাকলে installation ও runtime problem-এর কারণ খুঁজে বের করা সহজ হয়।

---

## 6. Understanding Package Versions

একটি package-এর একাধিক version থাকতে পারে।

উদাহরণ:

```text
requests 2.30.0
requests 2.31.0
requests 2.32.0
```

এগুলো একই package-এর ভিন্ন version-এর উদাহরণ।

Version পরিবর্তনের সঙ্গে নতুন feature, bug fix, security fix অথবা incompatible change আসতে পারে।

### Common Versioning Pattern

অনেক Python package version এ ধরনের format অনুসরণ করে:

```text
MAJOR.MINOR.PATCH
```

উদাহরণ:

```text
2.32.3
```

সাধারণভাবে:

- `MAJOR` — বড় পরিবর্তনের version component।
- `MINOR` — নতুন feature যোগ করার version component।
- `PATCH` — ছোট bug fix-এর version component।

তবে সব package একই versioning policy অনুসরণ করে না। Version বোঝার জন্য সংশ্লিষ্ট package-এর documentation দেখা উচিত।

### Important Operators

| Operator | Meaning |
|---|---|
| `==` | নির্দিষ্ট version |
| `>=` | নির্দিষ্ট version বা তার চেয়ে নতুন |
| `<=` | নির্দিষ্ট version বা তার চেয়ে পুরোনো |
| `<` | নির্দিষ্ট version-এর চেয়ে পুরোনো |
| `>` | নির্দিষ্ট version-এর চেয়ে নতুন |
| `!=` | নির্দিষ্ট version বাদ দেওয়া |
| `~=` | Compatible release specification |

উদাহরণ:

```text
requests==2.32.3
```

এখানে নির্দিষ্ট version চাওয়া হয়েছে।

অন্যদিকে:

```text
requests>=2.30
```

এখানে `2.30` বা তার চেয়ে নতুন উপযুক্ত version চাওয়া হয়েছে।

আরও একটি উদাহরণ:

```text
requests>=2.30,<3.0
```

এখানে version-কে `2.30` বা তার চেয়ে নতুন এবং `3.0`-এর চেয়ে পুরোনো সীমার মধ্যে রাখা হয়েছে।

Version specifier কীভাবে কাজ করে, তা নির্ভুলভাবে বুঝতে Python Packaging-এর version specification documentation দেখা যায়:

https://packaging.python.org/en/latest/specifications/version-specifiers/

---

## 7. Pinning Package Versions

Package version pinning মানে dependency-এর জন্য নির্দিষ্ট version উল্লেখ করা।

উদাহরণ:

```text
requests==2.32.3
```

এখানে `requests`-এর জন্য নির্দিষ্ট version pin করা হয়েছে।

### Advantages of Version Pinning

- কোন version ব্যবহার করা হবে, তা স্পষ্ট হয়।
- Environment পুনরায় তৈরি করার সময় version variation কমে।
- Compatibility সমস্যা debug করা সহজ হয়।
- Team-এর সদস্যরা একই version ব্যবহার করতে পারে।

### Disadvantages

- Pinned version পুরোনো হয়ে যেতে পারে।
- Security update পেতে version পরিবর্তন করতে হতে পারে।
- নতুন Python version বা platform-এ package compatible নাও হতে পারে।
- অনেক dependency pin করলে maintenance-এর কাজ বাড়তে পারে।

### Should Every Project Pin Every Package?

সব project-এর জন্য একই policy উপযুক্ত নয়।

Learning project-এ সাধারণ dependency specification যথেষ্ট হতে পারে। কিন্তু production application, deployment বা reproducible research-এর জন্য version pinning এবং dependency validation আরও গুরুত্বপূর্ণ।

**মনে রাখবে:** Version pinning dependency management-এর একটি অংশ। এটি একাই সম্পূর্ণ reproducibility বা security নিশ্চিত করে না।

---

## 8. Managing Dependencies with `requirements.txt`

`requirements.txt` হলো dependency list রাখার একটি বহুল ব্যবহৃত পদ্ধতি।

### Example Project Structure

```text
StudentManagement/
├── .venv/
├── main.py
├── requirements.txt
├── .gitignore
└── README.md
```

### Example `requirements.txt`

```text
requests==2.32.3
pandas>=2.0
```

এখানে:

- `requests`-এর একটি নির্দিষ্ট version চাওয়া হয়েছে।
- `pandas`-এর একটি minimum version নির্ধারণ করা হয়েছে।

এই version-গুলো উদাহরণ। বাস্তব project-এ Python version, platform এবং dependency compatibility যাচাই করে নির্বাচন করতে হবে।

### Installing the Dependencies

Virtual environment activate করার পর চালাও:

```bash
python -m pip install -r requirements.txt
```

pip file পড়ে dependency-গুলো install করার চেষ্টা করবে।

### Why Use a Separate File?

যদি package-এর তালিকা code-এর মধ্যে বা আলাদা আলাদা command হিসেবে document করা হয়, তাহলে project setup অসংগঠিত হয়ে যেতে পারে।

`requirements.txt` সব dependency specification একটি জায়গায় রাখতে সাহায্য করে।

---

## 9. Direct Dependency List vs `pip freeze`

এটি খুব গুরুত্বপূর্ণ পার্থক্য।

### Method 1: Manually Maintain Direct Dependencies

উদাহরণ `requirements.txt`:

```text
requests
pandas
```

এখানে project-এর সরাসরি ব্যবহৃত package-গুলো লেখা হয়েছে।

**সুবিধা:**

- Dependency list সহজে বোঝা যায়।
- অপ্রয়োজনীয় package কম থাকে।
- Project-এর intended dependency স্পষ্ট থাকে।

**সীমাবদ্ধতা:**

- Version specification না থাকলে install-এর সময় ভিন্ন version পাওয়া যেতে পারে।
- Transitive dependency-এর exact version সরাসরি এখানে উল্লেখ করা হয়নি।

### Method 2: Use `pip freeze`

Command:

```bash
python -m pip freeze > requirements.txt
```

এটি বর্তমান environment-এর installed package ও version-এর তালিকা file-এ লেখে।

উদাহরণ:

```text
requests==2.x
urllib3==2.x
certifi==202x.x
```

এখানে version-গুলো illustrative placeholder।

**সুবিধা:**

- Environment-এর package version সংরক্ষণ করতে সাহায্য করে।
- একই ধরনের environment পুনরায় তৈরি করার সুবিধা দেয়।
- Debugging ও deployment-এর সময় সহায়ক হতে পারে।

**সীমাবদ্ধতা:**

- অপ্রয়োজনীয় package তালিকায় চলে আসতে পারে।
- Direct ও transitive dependency আলাদা করে দেখায় না।
- এটি নিজে থেকে Python version, operating system বা system-level dependency সম্পূর্ণভাবে document করে না।

### Which Method Is Better?

Project-এর উদ্দেশ্য অনুযায়ী সিদ্ধান্ত নিতে হবে।

| Situation | Suggested Approach |
|---|---|
| ছোট learning project | সহজ `requirements.txt` |
| Team project | Review করা dependency file ও version policy |
| Environment পুনরায় তৈরি করা | Versioned dependency list |
| Production deployment | Tested ও appropriately pinned dependencies |
| Complex application | প্রয়োজনে dedicated dependency/lock-file tooling |

---

## 10. Using `pip freeze` Correctly

ধরা যাক, তুমি `DataAnalysis` project-এর জন্য একটি virtual environment তৈরি করেছ।

Environment activate করার পর:

```bash
python -m pip install pandas numpy
```

এরপর package list তৈরি করো:

```bash
python -m pip freeze
```

Output Terminal-এ দেখা যাবে।

File-এ সংরক্ষণ করতে:

```bash
python -m pip freeze > requirements.txt
```

### Important: Check the Active Environment First

এই command চালানোর আগে যাচাই করো:

```bash
python -c "import sys; print(sys.executable)"
```

যদি ভুল environment active থাকে, তাহলে অন্য environment-এর package list `requirements.txt`-এ চলে আসতে পারে।

### Does `pip freeze` Install Packages?

না।

```bash
python -m pip freeze
```

বর্তমান environment-এর installed distribution-গুলোর তালিকা দেখায়।

অন্যদিকে:

```bash
python -m pip install -r requirements.txt
```

File থেকে dependency install করার চেষ্টা করে।

দুটি command-এর কাজ আলাদা।

---

## 11. Development Dependencies

কিছু package application চালানোর জন্য প্রয়োজন হয়, আবার কিছু package development ও testing-এর সময় কাজে লাগে।

উদাহরণ:

- `pytest` — test চালাতে।
- `ruff` — linting ও code quality checking-এর জন্য।
- `black` — code formatting-এর জন্য।

এই package-গুলোকে অনেক project-এ development dependencies হিসেবে manage করা হয়।

### Example

একটি project-এর জন্য:

```text
Runtime dependencies:
requests

Development dependencies:
pytest
ruff
```

এটি একটি conceptual example।

### Why Separate Them?

- Production environment-এ অপ্রয়োজনীয় tool install করা কমানো যায়।
- Project-এর purpose পরিষ্কার থাকে।
- Development ও deployment setup আলাদা রাখা যায়।

### Simple Approach

Beginner project-এ চাইলে দুটি file ব্যবহার করতে পারো:

`requirements.txt`

```text
requests
```

`requirements-dev.txt`

```text
-r requirements.txt
pytest
ruff
```

Development environment setup করতে:

```bash
python -m pip install -r requirements-dev.txt
```

এখানে `-r requirements.txt` দিয়ে মূল dependency file-টিও পড়তে বলা হয়েছে।

এটি একটি সহজ convention; সব project-এর জন্য একটিই বাধ্যতামূলক format নয়।

---

## 12. Understanding Dependency Conflicts

Dependency conflict ঘটে যখন একাধিক package-এর requirements পরস্পরের সঙ্গে মেলে না।

ধরা যাক:

```text
Package A requires Library X < 2.0
Package B requires Library X >= 2.0
```

এখানে একই environment-এ দুইটি requirement একসঙ্গে পূরণ করা সম্ভব নয়।

### Common Causes

1. Package-এর incompatible version।
2. Python version-এর সঙ্গে incompatibility।
3. পুরোনো dependency।
4. একাধিক package-এর conflicting requirements।
5. Environment-এ আগের installation থেকে রয়ে যাওয়া package।

### How to Investigate

প্রথমে active Python interpreter যাচাই করো:

```bash
python -c "import sys; print(sys.executable)"
```

Installed package list দেখো:

```bash
python -m pip list
```

Dependency consistency পরীক্ষা করো:

```bash
python -m pip check
```

তারপর error message এবং সংশ্লিষ্ট package-এর documentation পড়ো।

### Possible Solutions

- Compatible package version নির্বাচন করা।
- Package-এর updated version ব্যবহার করা, যদি সেটি conflict সমাধান করে।
- Clean virtual environment তৈরি করা।
- Project-এর dependency specification review করা।
- প্রয়োজন হলে application code বা architecture পরিবর্তন করা।

শুধু error message না পড়ে package version এলোমেলোভাবে পরিবর্তন করা উচিত নয়।

---

## 13. Recreating an Environment on Another Computer

ধরা যাক, তোমার project GitHub-এ আছে এবং তুমি অন্য computer-এ project-টি চালাতে চাও।

Project-এর `.venv` folder সাধারণত GitHub-এ upload করা হয় না। তাই নতুন computer-এ environment তৈরি করতে হবে।

### Step 1: Get the Project

Git ব্যবহার করলে:

```bash
git clone YOUR_REPOSITORY_URL
```

এখানে `YOUR_REPOSITORY_URL`-এর পরিবর্তে তোমার repository URL ব্যবহার করবে।

অথবা repository থেকে project download করতে পারো।

### Step 2: Enter the Project Folder

```bash
cd YourProject
```

### Step 3: Create a Virtual Environment

```bash
python -m venv .venv
```

প্রয়োজনে `python`-এর পরিবর্তে `py` বা `python3` ব্যবহার করো।

### Step 4: Activate It

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### Step 5: Install Dependencies

```bash
python -m pip install -r requirements.txt
```

### Step 6: Run the Project

```bash
python main.py
```

Project-এর entry-point file যদি `main.py` না হয়, তাহলে সঠিক file চালাবে।

### Important Limitations

একই `requirements.txt` ব্যবহার করলেও সব computer-এ environment পুরোপুরি identical হবে, এমন নিশ্চয়তা নেই।

কারণ:

- Python version আলাদা হতে পারে।
- Operating system আলাদা হতে পারে।
- কিছু package platform-specific হতে পারে।
- System-level dependency ভিন্ন হতে পারে।
- Package index বা installation source পরিবর্তিত হতে পারে।

তাই project-এর documentation-এ supported Python version এবং setup instruction উল্লেখ করা ভালো।

---

## 14. Understanding Lock Files

`requirements.txt` dependency specification রাখার একটি পদ্ধতি। তবে বড় project-এ আরও নির্দিষ্ট dependency resolution ও reproducibility প্রয়োজন হতে পারে।

এক্ষেত্রে কিছু tool lock file তৈরি করে।

Lock file সাধারণত resolved dependency graph-এর নির্দিষ্ট version এবং প্রয়োজনীয় metadata সংরক্ষণ করে।

### Why Use a Lock File?

- Dependency version আরও নির্দিষ্টভাবে সংরক্ষণ করতে।
- Environment পুনরায় তৈরি করার consistency বাড়াতে।
- Team-এর মধ্যে dependency resolution-এর পার্থক্য কমাতে।

### Common Tools

Python ecosystem-এ dependency management-এর জন্য বিভিন্ন tool রয়েছে, যেমন:

- `pip` — package installation ও management।
- `pip-tools` — dependency specification থেকে pinned requirements তৈরি করতে।
- Poetry — project metadata ও dependency management।
- uv — Python project ও dependency management-এর জন্য আধুনিক tool।

এই tool-গুলোর workflow ও configuration আলাদা।

**Beginner guideline:** প্রথমে `pip`, `venv` এবং `requirements.txt` ভালোভাবে শেখো। তারপর project-এর complexity অনুযায়ী lock-file tooling শেখা শুরু করো।

---

## 15. Security and Dependency Maintenance

Dependency management শুধু package install করার বিষয় নয়। Security ও maintenance-ও এর অংশ।

### 15.1 Use Trusted Sources

Official package documentation ও পরিচিত package index ব্যবহার করো।

### 15.2 Verify Package Names

একটি অক্ষরের ভুলেও ভিন্ন package install হয়ে যেতে পারে।

### 15.3 Review Updates

Package update করার আগে changelog, release notes এবং compatibility information দেখো।

### 15.4 Check Vulnerabilities

Dependency-তে পরিচিত vulnerability আছে কি না, তা উপযুক্ত security advisory বা scanning tool দিয়ে যাচাই করা যায়।

### 15.5 Remove Unused Dependencies

যে package আর ব্যবহার হচ্ছে না, তা project থেকে সরিয়ে ফেলো।

### 15.6 Test After Updates

Dependency update করার পরে program এবং relevant tests চালাও।

### 15.7 Avoid Blind Installation

শুধু কোনো tutorial-এ command দেখেছ বলে অজানা package install করো না। Package-এর purpose ও source যাচাই করো।

---

## 16. Common Mistakes

### Mistake 1: Installing Packages Globally

Project-specific package global environment-এ install করলে dependency conflict-এর ঝুঁকি বাড়তে পারে।

**Solution:** Virtual environment ব্যবহার করো।

### Mistake 2: Forgetting to Activate the Environment

তুমি ভেবেছ `.venv` active, কিন্তু আসলে অন্য interpreter ব্যবহার হচ্ছে।

**Solution:**

```bash
python -c "import sys; print(sys.executable)"
```

### Mistake 3: Uploading `.venv` to GitHub

Environment-এর file ও path অন্য system-এ কাজ নাও করতে পারে।

**Solution:** `.venv/`-কে `.gitignore`-এ রাখো এবং dependency file commit করো।

### Mistake 4: Treating `pip freeze` as a Complete Project Specification

`pip freeze` current environment-এর package list দেয়, কিন্তু সব project setup requirement নথিবদ্ধ করে না।

**Solution:** Python version, system requirement এবং setup instruction-ও document করো।

### Mistake 5: Updating All Dependencies Without Testing

নতুন version-এর কারণে code ভেঙে যেতে পারে।

**Solution:** Update করার পরে tests চালাও এবং compatibility যাচাই করো।

### Mistake 6: Keeping Unused Packages

অপ্রয়োজনীয় dependency project-এর complexity বাড়ায়।

**Solution:** Dependency list review করো এবং unused package সরিয়ে ফেলো।

---

## 17. Practical Exercise

এবার একটি ছোট project-এর dependency management অনুশীলন করো।

### Step 1: Create the Project

```bash
mkdir DependencyPractice
cd DependencyPractice
```

### Step 2: Create a Virtual Environment

```bash
python -m venv .venv
```

### Step 3: Activate the Environment

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### Step 4: Install Dependencies

```bash
python -m pip install requests
```

### Step 5: Create `main.py`

```python
import requests

response = requests.get(
    "https://example.com",
    timeout=10
)

print("Status code:", response.status_code)
```

### Step 6: Run the Program

```bash
python main.py
```

### Step 7: Generate a Dependency List

```bash
python -m pip freeze > requirements.txt
```

### Step 8: Inspect the File

`requirements.txt` open করে package ও version-গুলো দেখো।

### Step 9: Check Dependency Compatibility

```bash
python -m pip check
```

### Step 10: Document the Setup

`README.md` file-এ নিচের তথ্যগুলো লেখো:

- Project-এর purpose।
- Supported Python version।
- Virtual environment তৈরির command।
- Environment activate করার command।
- Dependency install করার command।
- Program run করার command।

এভাবে তোমার project শুধু নিজের কম্পিউটারে চালানোর জন্য নয়, অন্য developer-এর জন্যও সহজে setup করার উপযোগী হবে।

---

## 18. Quick Revision

| Concept | Meaning |
|---|---|
| Dependency | Project-এর কাজের জন্য প্রয়োজনীয় package বা software |
| Direct dependency | Project সরাসরি ব্যবহার করে |
| Transitive dependency | অন্য dependency-এর মাধ্যমে প্রয়োজন হয় |
| Version pinning | নির্দিষ্ট dependency version উল্লেখ করা |
| `requirements.txt` | Dependency specification রাখার সাধারণ file |
| `pip freeze` | বর্তমান environment-এর installed distribution ও version দেখায় |
| `pip check` | Declared dependency requirement-এর incompatibility পরীক্ষা করে |
| Development dependency | Development ও testing-এর জন্য প্রয়োজনীয় package |
| Lock file | Resolved dependency version ও metadata সংরক্ষণে ব্যবহৃত file |
| Reproducibility | একই বা কাছাকাছি setup পুনরায় তৈরি করার সক্ষমতা |

---

## 19. Chapter Connection

এই topic-এ আমরা direct ও transitive dependency, version specification, `requirements.txt`, `pip freeze`, dependency conflict এবং project অন্য computer-এ setup করার পদ্ধতি শিখেছি।

এখন তুমি শুধু package install করাই নয়, একটি project-এর dependency কীভাবে document ও maintain করতে হয়, সে সম্পর্কেও ধারণা পেয়েছ।

**Next Topic:** [22. Introduction to Jupyter Notebooks](22_Introduction_to_Jupyter_Notebooks.md)

পরবর্তী topic-এ আমরা Jupyter Notebook কী, কেন ব্যবহার করা হয়, কীভাবে install ও run করতে হয় এবং cell-by-cell Python code execute করতে হয়—এসব শিখব।