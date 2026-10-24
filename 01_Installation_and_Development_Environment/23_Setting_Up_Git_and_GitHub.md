# 23. Setting Up Git and GitHub

## 1. Introduction

Software development-এ শুধু code লিখতে পারলেই হয় না। Code-এর পরিবর্তন সংরক্ষণ করা, আগের version-এ ফিরে যাওয়া, project backup রাখা এবং অন্য developer-এর সঙ্গে কাজ করাও গুরুত্বপূর্ণ।

এই কাজগুলো সহজ করার জন্য **Git** এবং **GitHub** ব্যবহার করা হয়।

এই topic-এ আমরা শিখব:

1. Git কী এবং কেন ব্যবহার করা হয়।
2. Git ও GitHub-এর পার্থক্য।
3. Git install করা।
4. Git installation যাচাই করা।
5. Git username ও email configure করা।
6. Git repository তৈরি করা।
7. Python project-এ Git ব্যবহার করা।
8. GitHub account ও repository তৈরি করা।
9. Local repository-কে GitHub-এর সঙ্গে connect করা।
10. Common Git errors সমাধান করা।

---

## 2. What Is Git?

**Git হলো একটি Distributed Version Control System (DVCS)।**

সহজ ভাষায়, Git এমন একটি tool, যা project-এর file-এ কী পরিবর্তন হয়েছে, কখন পরিবর্তন হয়েছে এবং কে পরিবর্তন করেছে—এসবের history সংরক্ষণ করতে সাহায্য করে।

ধরা যাক, তুমি একটি Python calculator তৈরি করছ।

প্রথমে তোমার code:

```python
def add(a, b):
    return a + b

print(add(10, 20))
```

পরে তুমি multiplication-এর feature যোগ করলে:

```python
def add(a, b):
    return a + b

def multiply(a, b):
    return a * b

print(add(10, 20))
print(multiply(10, 20))
```

Git ব্যবহার করলে এই পরিবর্তনগুলো আলাদা commit হিসেবে সংরক্ষণ করতে পারবে।

প্রয়োজনে আগের version-এর code দেখতে পারবে বা আগের কোনো অবস্থায় ফিরে যাওয়ার ব্যবস্থা করতে পারবে।

### Why Use Git?

- Code-এর পরিবর্তনের history রাখা।
- আগের version-এর সঙ্গে তুলনা করা।
- ভুল পরিবর্তন থেকে recovery করা।
- একাধিক developer-এর সঙ্গে কাজ করা।
- Project-এর বিভিন্ন branch-এ আলাদাভাবে কাজ করা।
- GitHub-এর মতো remote service-এ project publish করা।

**মনে রাখবে:** Git ব্যবহার করার জন্য GitHub account থাকা বাধ্যতামূলক নয়। Git নিজের computer-এ localভাবেও কাজ করে।

---

## 3. What Is GitHub?

**GitHub হলো Git repository host ও manage করার একটি online platform।**

GitHub-এ project-এর repository online-এ রাখা যায়। এছাড়া project documentation, issue tracking, collaboration এবং code review-এর মতো কাজ করা যায়।

উদাহরণ:

```text
Local Computer
      |
      | Git
      v
Local Repository
      |
      | Push
      v
GitHub Repository
```

তুমি computer-এ code লিখে Git দিয়ে commit করতে পারবে। এরপর internet connection থাকলে GitHub repository-তে সেই commit push করতে পারবে।

### What Can You Do with GitHub?

- Python project online-এ সংরক্ষণ করা।
- Public portfolio তৈরি করা।
- Project-এর README প্রকাশ করা।
- অন্যদের project দেখা ও শেখা।
- Team-এর সঙ্গে collaboration করা।
- Open-source project-এ অবদান রাখা।
- Project-এর issue ও pull request manage করা।

### Git vs GitHub

| Feature | Git | GitHub |
|---|---|---|
| Type | Version control tool | Online development platform |
| Main purpose | Code changes track করা | Repository host ও collaborate করা |
| Local use | হ্যাঁ | Website-এর মূল service online-ভিত্তিক |
| History | Local repository-তে রাখে | Hosted repository-তেও commit history থাকে |
| Account | Git ব্যবহার করতে account লাগে না | GitHub account সাধারণত নিজের repository manage করার জন্য ব্যবহৃত হয় |
| Internet | Local Git operation-এর জন্য দরকার হয় না | Online service ব্যবহার করতে সাধারণত দরকার হয় |

**সহজভাবে মনে রাখো:** Git হলো version control tool, আর GitHub হলো Git repository রাখার ও share করার একটি platform।

---

## 4. Important Git Terminology

Git ব্যবহার করার আগে কয়েকটি term বোঝা দরকার।

### 4.1 Repository

Repository বা `repo` হলো project-এর file এবং তাদের version history manage করার Git structure।

দুই ধরনের repository নিয়ে বেশি কাজ করবে:

- **Local Repository:** তোমার computer-এ থাকে।
- **Remote Repository:** GitHub-এর মতো server-এ থাকে।

### 4.2 Working Directory

যে folder-এ তুমি project-এর file তৈরি ও edit করো, সেটিই Git-এর working directory।

উদাহরণ:

```text
Python-Basic-to-Pro/
├── README.md
├── main.py
└── practice.py
```

### 4.3 Staging Area

Commit করার আগে কোন পরিবর্তনগুলো পরবর্তী commit-এ থাকবে, তা নির্বাচন করার জায়গা হলো staging area।

```bash
git add main.py
```

এই command `main.py`-এর বর্তমান পরিবর্তন staging area-তে যোগ করে।

### 4.4 Commit

Commit হলো নির্বাচিত পরিবর্তনগুলোর একটি recorded snapshot, যার সঙ্গে একটি message থাকে।

```bash
git commit -m "Add Python main file"
```

### 4.5 Branch

Branch ব্যবহার করে মূল development line থেকে আলাদা একটি line of development তৈরি করা যায়।

```bash
git branch
```

### 4.6 Remote

Remote হলো local repository-র সঙ্গে সম্পর্কিত একটি remote repository-এর reference।

সাধারণত GitHub repository-কে `origin` নামে remote হিসেবে যোগ করা হয়।

### 4.7 Push

Local commit remote repository-তে পাঠানোকে push বলে।

```bash
git push
```

### 4.8 Pull

Remote repository থেকে পরিবর্তন এনে local branch update করতে `git pull` ব্যবহার করা হয়।

```bash
git pull
```

### 4.9 Clone

কোনো remote repository-র local copy তৈরি করতে `git clone` ব্যবহার করা হয়।

```bash
git clone <repository-url>
```

### 4.10 `.gitignore`

কোন file বা folder Git tracking-এ নেওয়া হবে না, তা নির্ধারণ করতে `.gitignore` file ব্যবহার করা হয়।

উদাহরণ:

```gitignore
.venv/
__pycache__/
.env
```

`.gitignore` সাধারণত untracked file-কে tracking-এ নেওয়া থেকে বিরত রাখে। ইতিমধ্যে tracked হয়ে যাওয়া file-কে এটি নিজে থেকে untrack করে না।

---

## 5. Installing Git on Windows

Windows-এ Git install করার জন্য official website ব্যবহার করো।

Website: https://git-scm.com/

### Step 1: Download Git

1. Browser-এ official Git website খোলো।
2. Windows-এর জন্য download option নির্বাচন করো।
3. Installer download করো।

### Step 2: Run the Installer

Downloaded installer open করো।

Installer-এর বিভিন্ন configuration option থাকবে। নতুন user হিসেবে সাধারণত default option-গুলো রাখা যায়।

বিশেষভাবে:

- Git-এর command line tools উপলভ্য আছে কি না নিশ্চিত করো।
- Editor configuration-এর option এলে নিজের পছন্দ অনুযায়ী নির্বাচন করতে পারো।
- Default branch name হিসেবে `main` নির্বাচন করার option থাকলে সেটি বেছে নিতে পারো।

Installer-এর version অনুযায়ী option-এর নাম কিছুটা আলাদা হতে পারে।

### Step 3: Complete Installation

Installer-এর instruction অনুসরণ করে installation শেষ করো।

### Step 4: Open Terminal

VS Code terminal, PowerShell অথবা Git Bash খুলে লেখো:

```bash
git --version
```

উদাহরণ output:

```text
git version 2.x.x
```

তোমার computer-এ version number আলাদা হতে পারে।

Version দেখা গেলে Git command শনাক্ত করা যাচ্ছে।

---

## 6. Installing Git on macOS

macOS-এ Git install করার একাধিক পদ্ধতি রয়েছে।

### Method 1: Check Whether Git Is Available

Terminal খুলে লেখো:

```bash
git --version
```

Git উপলভ্য না থাকলে macOS developer command-line tools install করার prompt দেখাতে পারে।

### Method 2: Install Command Line Tools

Terminal-এ:

```bash
xcode-select --install
```

Prompt এলে instruction অনুসরণ করো।

### Method 3: Use Homebrew

যদি Homebrew আগে থেকেই install করা থাকে, তাহলে:

```bash
brew install git
```

### Verify Installation

```bash
git --version
```

Git-এর version দেখা গেলে installation যাচাই করা যাবে।

---

## 7. Installing Git on Linux

Linux distribution অনুযায়ী installation command আলাদা হতে পারে।

### Ubuntu / Debian

```bash
sudo apt update
sudo apt install git
```

### Fedora

```bash
sudo dnf install git
```

### Arch Linux

```bash
sudo pacman -S git
```

### Verify Installation

```bash
git --version
```

**সতর্কতা:** Linux-এ system package manager ব্যবহার করে package install করার সময় command ও permission সম্পর্কে নিশ্চিত হও। অপ্রয়োজনীয়ভাবে `sudo` ব্যবহার কোরো না।

---

## 8. Configuring Git Username and Email

Git commit তৈরি করার সময় author information সংরক্ষণ করা হয়। এজন্য username ও email configure করা গুরুত্বপূর্ণ।

### Configure Username

```bash
git config --global user.name "Your Name"
```

উদাহরণ:

```bash
git config --global user.name "Masum"
```

### Configure Email

```bash
git config --global user.email "your-email@example.com"
```

এখানে নিজের সঠিক email address ব্যবহার করবে। চাইলে GitHub-এর provided `noreply` email ব্যবহার করতে পারো, যদি privacy বজায় রাখতে চাও।

### What Does `--global` Mean?

`--global` ব্যবহার করলে configuration সাধারণত তোমার user account-এর অধীনে থাকা সব Git repository-তে প্রযোজ্য হয়।

একটি নির্দিষ্ট repository-র জন্য আলাদা identity সেট করতে চাইলে সেই repository-র folder-এ গিয়ে `--local` ব্যবহার করা যায়।

উদাহরণ:

```bash
git config --local user.name "Project Name"
```

### Verify Configuration

```bash
git config --global user.name
git config --global user.email
```

সব Git configuration দেখতে:

```bash
git config --list
```

**মনে রাখবে:** Commit-এর author email আর GitHub-এ authenticate করার account এক জিনিস নয়। Git configuration নিজে থেকে GitHub-এ login করায় না।

---

## 9. Understanding Git Configuration Levels

Git configuration সাধারণত কয়েকটি level-এ থাকতে পারে।

| Level | Meaning |
|---|---|
| System | পুরো system-এর জন্য প্রযোজ্য configuration |
| Global | নির্দিষ্ট operating-system user-এর জন্য configuration |
| Local | নির্দিষ্ট repository-র configuration |

সাধারণ beginner workflow-এ `--global` দিয়ে username ও email configure করাই যথেষ্ট।

### Example

```bash
git config --global init.defaultBranch main
```

এই configuration নতুন repository তৈরি করার সময় default branch name `main` করতে সাহায্য করে।

বর্তমান repository-র branch name দেখতে:

```bash
git branch --show-current
```

পুরোনো repository-তে branch name ভিন্ন হতে পারে।

---

## 10. Creating a GitHub Account

GitHub-এ repository host করতে account তৈরি করতে পারো।

Official website:

https://github.com/

### Steps

1. GitHub website খোলো।
2. Sign up option নির্বাচন করো।
3. Email address ও প্রয়োজনীয় তথ্য দিয়ে account তৈরি করো।
4. Verification-এর instruction অনুসরণ করো।
5. Account-এ sign in করো।

### Choose a Professional Username

GitHub username portfolio ও project link-এর অংশ হতে পারে।

তাই username নির্বাচন করার সময়:

- সহজে মনে রাখা যায় এমন নাম বেছে নাও।
- অপ্রয়োজনীয় symbol এড়িয়ে চলো।
- Professional ও consistent নাম রাখার চেষ্টা করো।

### Public and Private Repositories

- **Public Repository:** সাধারণত অন্যরা দেখতে পারে।
- **Private Repository:** Access অনুমোদিত ব্যক্তিদের মধ্যে সীমাবদ্ধ থাকে।

Public repository-তে password, API key, private information বা অন্য কোনো secret প্রকাশ কোরো না।

---

## 11. Creating a Local Python Project

এবার Git ব্যবহার করার জন্য একটি sample Python project তৈরি করি।

### Step 1: Create a Folder

Terminal-এ:

```bash
mkdir GitPythonPractice
cd GitPythonPractice
```

### Step 2: Open the Folder in VS Code

```bash
code .
```

যদি `code` command কাজ না করে, তাহলে VS Code-এর Open Folder option ব্যবহার করো।

### Step 3: Create `main.py`

```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Python"))
```

Output:

```text
Hello, Python!
```

### Step 4: Create `README.md`

```markdown
# Git Python Practice

This repository contains basic Python practice code.

## Topics

- Python functions
- Git basics
- Version control
```

### Step 5: Create `.gitignore`

```gitignore
.venv/
__pycache__/
*.pyc
.env
```

এই sample `.gitignore` Python virtual environment, bytecode cache এবং `.env` file-কে সাধারণভাবে Git tracking থেকে বাদ দিতে সাহায্য করবে।

---

## 12. Initializing a Git Repository

Project folder-এর Terminal-এ নিশ্চিত হও যে তুমি সঠিক folder-এ আছ।

তারপর:

```bash
git init
```

এই command folder-এ Git repository initialize করে।

সাধারণত project-এর মধ্যে `.git` নামে একটি hidden directory তৈরি হয়।

এই directory-তে Git-এর repository metadata ও history রাখা হয়।

### Check Repository Status

```bash
git status
```

Git project-এর file-এর অবস্থা দেখাবে।

### Set the Branch Name

যদি repository-র branch name `main` করতে চাও:

```bash
git branch -M main
```

এই command বর্তমান branch-কে `main` নামে rename করে।

### Important

`git init` শুধু local repository তৈরি করে। এটি নিজে থেকে GitHub-এ repository তৈরি করে না।

---

## 13. Understanding the Git Workflow

Git-এর সাধারণ workflow:

```text
Working Directory
       |
       | git add
       v
Staging Area
       |
       | git commit
       v
Local Repository
       |
       | git push
       v
Remote Repository
```

### Step 1: Check Status

```bash
git status
```

কোন file নতুন, কোন file modified এবং কোন file staged হয়েছে—তা দেখা যায়।

### Step 2: Add Files to the Staging Area

সব উপযুক্ত file stage করতে:

```bash
git add .
```

শুধু একটি file stage করতে:

```bash
git add main.py
```

**সতর্কতা:** `git add .` ব্যবহার করার আগে `git status` দেখে নাও। ভুল করে password, secret বা বড় অপ্রয়োজনীয় file stage কোরো না।

### Step 3: Create a Commit

```bash
git commit -m "Add initial Python practice files"
```

Commit message-এ পরিবর্তনের উদ্দেশ্য পরিষ্কারভাবে লেখো।

### Step 4: Check History

```bash
git log --oneline
```

Commit history সংক্ষিপ্তভাবে দেখা যাবে।

### Step 5: Check Status Again

```bash
git status
```

সব পরিবর্তন commit হয়ে থাকলে working tree clean থাকার কথা।

---

## 14. Writing Good Commit Messages

Commit message দেখে যেন বোঝা যায় কী পরিবর্তন করা হয়েছে।

### Good Examples

```text
Add Python project README
Create initial Python script
Add string practice examples
Fix variable naming
Update installation instructions
```

### Poor Examples

```text
update
changes
final
new code
done
```

এ ধরনের message পরিবর্তনের উদ্দেশ্য পরিষ্কার করে না।

### Commit Message Best Practices

1. ছোট ও অর্থপূর্ণ message লেখো।
2. একটি commit-এ সম্পর্কিত পরিবর্তন রাখো।
3. অপ্রয়োজনীয় file commit কোরো না।
4. Commit করার আগে code যাচাই করো।
5. বড় কাজকে ছোট, অর্থপূর্ণ commit-এ ভাগ করো।

---

## 15. Creating a GitHub Repository

এখন local project-এর জন্য GitHub-এ remote repository তৈরি করব।

### Step 1: Open GitHub

https://github.com/

Account-এ sign in করো।

### Step 2: Create a New Repository

New repository option নির্বাচন করো।

### Step 3: Enter Repository Details

উদাহরণ:

```text
Repository name: GitPythonPractice
Description: Basic Python and Git practice
Visibility: Public or Private
```

### Step 4: Choose Repository Initialization Options

যদি local project-এ আগে থেকেই `README.md` তৈরি করে commit করে থাকো, তাহলে GitHub-এ নতুন repository তৈরির সময় আবার README, license বা `.gitignore` initialize না করাই সহজ হতে পারে।

এতে local ও remote history আলাদাভাবে তৈরি হওয়ার কারণে সম্ভাব্য initial conflict এড়ানো যায়।

### Step 5: Create the Repository

Repository তৈরি করার পর GitHub-এর page-এ remote repository URL দেখতে পাবে।

HTTPS URL-এর format সাধারণত:

```text
https://github.com/USERNAME/REPOSITORY.git
```

এখানে `USERNAME` ও `REPOSITORY`-এর জায়গায় নিজের account এবং repository-র তথ্য থাকবে।

**গুরুত্বপূর্ণ:** উপরের URL শুধু example format। নিজের repository page থেকে সঠিক URL copy করবে।

---

## 16. Connecting the Local Repository to GitHub

Local project folder-এর Terminal-এ নিচের command চালাও।

### Step 1: Add a Remote

```bash
git remote add origin https://github.com/USERNAME/GitPythonPractice.git
```

এখানে নিজের actual repository URL বসাবে।

`origin` হলো remote-এর একটি প্রচলিত নাম। চাইলে অন্য নামও ব্যবহার করা যায়।

### Step 2: Verify the Remote

```bash
git remote -v
```

Remote repository-র fetch ও push URL দেখা যাবে।

### Step 3: Push the Local Branch

```bash
git push -u origin main
```

এই command `main` branch-কে `origin` remote-এ push করে এবং পরবর্তী push-এর জন্য upstream tracking সেট করে।

যদি branch-এর নাম `main` না হয়, তাহলে নিজের বর্তমান branch name ব্যবহার করবে।

### Step 4: Verify on GitHub

Browser-এ GitHub repository page refresh করো।

Commit সফল হলে project-এর file ও commit history দেখতে পাবে।

---

## 17. Authentication: Signing In to GitHub

GitHub-এ push করার সময় authentication প্রয়োজন হতে পারে।

সাধারণ পদ্ধতি:

- Git Credential Manager-এর মাধ্যমে sign in।
- SSH key configure করা।
- HTTPS-এর সঙ্গে Personal Access Token (PAT) ব্যবহার করা, যেখানে উপযুক্ত।

### Important Security Rules

- GitHub account password সাধারণ Git HTTPS password-এর বিকল্প হিসেবে ব্যবহার করা যায় না।
- Personal Access Token কখনো public repository-তে commit কোরো না।
- SSH private key কারও সঙ্গে share কোরো না।
- Authentication information code-এর মধ্যে hardcode কোরো না।
- GitHub-এর official authentication instructions অনুসরণ করো।

Git for Windows-এর installer-এ Git Credential Manager অন্তর্ভুক্ত থাকতে পারে। Setup অনুযায়ী sign-in prompt আসতে পারে।

---

## 18. Making Changes and Pushing Again

GitHub-এ প্রথম commit push করার পরে project-এ নতুন feature যোগ করি।

`main.py` file-এ লেখো:

```python
def greet(name):
    return f"Hello, {name}!"

def add(a, b):
    return a + b

print(greet("Python"))
print(add(10, 20))
```

এবার Terminal-এ:

### Step 1: Check Changes

```bash
git status
```

### Step 2: Review the Difference

```bash
git diff
```

এতে commit না করা tracked-file পরিবর্তনগুলো দেখা যাবে।

### Step 3: Stage the File

```bash
git add main.py
```

### Step 4: Commit

```bash
git commit -m "Add addition function"
```

### Step 5: Push

```bash
git push
```

আগে upstream সেট করা থাকলে সাধারণত শুধু `git push` ব্যবহার করা যায়।

GitHub repository refresh করলে নতুন commit দেখতে পাবে।

---

## 19. Cloning a GitHub Repository

কোনো existing GitHub repository নিজের computer-এ copy করতে `git clone` ব্যবহার করা হয়।

### Command

```bash
git clone https://github.com/USERNAME/REPOSITORY.git
```

তারপর repository folder-এ যাও:

```bash
cd REPOSITORY
```

এই command-এ নিজের actual repository URL ও folder name ব্যবহার করবে।

### When Is Cloning Useful?

- অন্য computer-এ নিজের project নিতে।
- অন্য developer-এর project নিয়ে কাজ করতে।
- Open-source project-এর local copy তৈরি করতে।
- Existing project-এর code study করতে।

Clone করলে সাধারণত project-এর Git history-ও local repository-তে পাওয়া যায়।

---

## 20. Common Git Commands

| Command | Purpose |
|---|---|
| `git --version` | Git version দেখা |
| `git config --list` | Git configuration দেখা |
| `git init` | Local repository initialize করা |
| `git status` | File-এর current status দেখা |
| `git add main.py` | নির্দিষ্ট file stage করা |
| `git add .` | Current directory-এর উপযুক্ত পরিবর্তন stage করা |
| `git commit -m "message"` | Commit তৈরি করা |
| `git log --oneline` | সংক্ষিপ্ত commit history দেখা |
| `git diff` | Unstaged tracked-file changes দেখা |
| `git branch` | Local branch list দেখা |
| `git branch -M main` | Current branch-কে `main` নামে rename করা |
| `git remote -v` | Remote URL দেখা |
| `git push` | Commit remote-এ পাঠানো |
| `git pull` | Remote changes এনে integrate করা |
| `git clone URL` | Remote repository-র local copy তৈরি করা |

এই command-গুলো ভালোভাবে অনুশীলন করলে beginner হিসেবে Git-এর মূল workflow আয়ত্ত করতে পারবে।

---

## 21. Common Git Errors and Solutions

### Error 1: `git is not recognized`

Windows-এ এমন error দেখা যেতে পারে:

```text
'git' is not recognized as an internal or external command
```

**কারণ:**

- Git install করা নেই।
- Git-এর command-line path environment-এ উপলভ্য নয়।
- Installation-এর পরে Terminal restart করা হয়নি।

**সমাধান:**

1. Git install করা আছে কি না যাচাই করো।
2. নতুন Terminal খুলে `git --version` চালাও।
3. প্রয়োজন হলে installation বা PATH configuration ঠিক করো।

### Error 2: `Author identity unknown`

**কারণ:** Git username ও email configure করা হয়নি।

**সমাধান:**

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

এরপর commit আবার তৈরি করো।

### Error 3: `remote origin already exists`

**কারণ:** Repository-তে `origin` নামে remote আগেই যোগ করা হয়েছে।

**সমাধান:**

```bash
git remote -v
```

বর্তমান URL সঠিক হলে আবার remote যোগ করার দরকার নেই।

URL পরিবর্তন করতে:

```bash
git remote set-url origin YOUR_REPOSITORY_URL
```

এখানে actual repository URL বসাবে।

### Error 4: `src refspec main does not match any`

**সম্ভাব্য কারণ:**

- এখনো কোনো commit তৈরি করা হয়নি।
- Local branch-এর নাম `main` নয়।
- Push করার জন্য branch নেই।

**সমাধান:**

```bash
git status
git branch
git log --oneline
```

প্রয়োজনীয় file stage ও commit করো। তারপর actual branch name ব্যবহার করে push করো।

### Error 5: `Authentication failed`

**সম্ভাব্য কারণ:**

- Authentication সঠিকভাবে সম্পন্ন হয়নি।
- Credential পুরোনো বা invalid।
- Repository access permission নেই।

**সমাধান:**

- GitHub account-এ access আছে কি না যাচাই করো।
- Git Credential Manager-এর sign-in flow অনুসরণ করো।
- HTTPS বা SSH authentication configuration যাচাই করো।
- প্রয়োজন হলে GitHub-এর official authentication documentation দেখো।

### Error 6: `rejected` or `fetch first`

**কারণ:** Remote repository-তে এমন commit থাকতে পারে, যা local repository-তে নেই।

**সমাধান:**

প্রথমে remote history ও local changes বুঝে নাও। তারপর উপযুক্ত merge বা rebase workflow ব্যবহার করো।

নতুন local ও remote repository-র history আলাদা হলে সতর্কভাবে conflict resolve করতে হতে পারে।

অন্ধভাবে `git push --force` ব্যবহার কোরো না। এতে remote history হারানোর ঝুঁকি থাকে।

### Error 7: Merge Conflict

একই file-এর একই অংশে ভিন্ন পরিবর্তন হলে conflict হতে পারে।

**সমাধান:**

1. Conflict-যুক্ত file খোলো।
2. Git-এর conflict marker দেখে সঠিক code নির্বাচন করো।
3. Marker সরিয়ে file ঠিক করো।
4. File stage করো।
5. Merge বা rebase workflow অনুযায়ী প্রক্রিয়া সম্পন্ন করো।

Conflict মানেই project নষ্ট হয়ে গেছে—এমন নয়। এটি Git-এর একটি স্বাভাবিক collaboration পরিস্থিতি।

---

## 22. Important Safety Practices

Git ও GitHub ব্যবহার করার সময় কিছু বিষয় অবশ্যই খেয়াল রাখতে হবে।

### Never Commit Secrets

নিচের তথ্যগুলো repository-তে প্রকাশ কোরো না:

- Password।
- API key।
- Access token।
- Private SSH key।
- Database credential।
- ব্যক্তিগত বা গোপন তথ্য।

### Use `.gitignore`

উদাহরণ:

```gitignore
.venv/
__pycache__/
*.pyc
.env
```

### Check Before Committing

```bash
git status
git diff
```

তারপর প্রয়োজনীয় file stage ও commit করো।

### Understand Public Repositories

Public repository-তে প্রকাশিত তথ্য অন্যরা দেখতে বা copy করতে পারে। পরে file delete করলেও Git history-তে sensitive information থেকে যেতে পারে।

ভুল করে secret commit করলে শুধু file delete করাই যথেষ্ট নয়। Secret revoke বা rotate করো এবং প্রয়োজন অনুযায়ী repository history পরিষ্কার করার ব্যবস্থা নাও।

---

## 23. Practical Exercise

এই exercise-এর মাধ্যমে local Git repository থেকে GitHub-এ project publish করার অনুশীলন করো।

### Task 1: Install Git

```bash
git --version
```

### Task 2: Configure Git

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

### Task 3: Create a Project

```bash
mkdir GitPractice
cd GitPractice
```

### Task 4: Create Files

`main.py`:

```python
def square(number):
    return number * number

print(square(5))
```

`README.md`:

```markdown
# Git Practice

This project contains basic Python practice code.
```

`.gitignore`:

```gitignore
__pycache__/
.venv/
.env
```

### Task 5: Initialize Git

```bash
git init
git branch -M main
git status
```

### Task 6: Create the First Commit

```bash
git add .
git commit -m "Create initial Python project"
```

### Task 7: Create a GitHub Repository

GitHub website-এ `GitPractice` নামে repository তৈরি করো।

Local project-এ আগে থেকেই file ও commit থাকলে remote repository-টি empty রাখা সহজ হবে।

### Task 8: Connect the Remote

```bash
git remote add origin YOUR_REPOSITORY_URL
git remote -v
```

### Task 9: Push to GitHub

```bash
git push -u origin main
```

### Task 10: Make Another Commit

`main.py`-এ নতুন function যোগ করো:

```python
def cube(number):
    return number ** 3

print(cube(3))
```

তারপর:

```bash
git add main.py
git commit -m "Add cube function"
git push
```

GitHub repository-তে নতুন পরিবর্তন দেখা যাচ্ছে কি না যাচাই করো।

---

## 24. Quick Revision

| Question | Answer |
|---|---|
| Git কী? | Version Control System |
| GitHub কী? | Git repository host ও collaborate করার platform |
| Repository কী? | Project file ও Git history manage করার structure |
| Staging Area কী? | Commit-এর জন্য নির্বাচিত পরিবর্তনের স্থান |
| Commit কী? | পরিবর্তনের recorded snapshot |
| Branch কী? | আলাদা line of development |
| Remote কী? | Remote repository-র reference |
| `git add` কী করে? | পরিবর্তন staging area-তে যোগ করে |
| `git commit` কী করে? | Local repository-তে commit তৈরি করে |
| `git push` কী করে? | Local commit remote-এ পাঠায় |
| `git pull` কী করে? | Remote changes এনে integrate করে |
| `git clone` কী করে? | Remote repository-র local copy তৈরি করে |
| `.gitignore` কী করে? | নির্দিষ্ট untracked file ও folder tracking থেকে বাদ রাখতে সাহায্য করে |

---

## 25. Chapter Connection

এই topic-এ আমরা Git ও GitHub-এর পার্থক্য, Git installation, configuration, repository initialization, staging, commit, remote connection এবং GitHub-এ project push করা শিখেছি।

এখন তুমি নিজের Python project-এর version history সংরক্ষণ করতে এবং GitHub-এ project publish করার প্রাথমিক workflow অনুসরণ করতে পারবে।

**Next Topic:** [24. Common Installation Errors and Solutions](24_Common_Installation_Errors_and_Solutions.md)

পরবর্তী topic-এ Python installation, PATH, virtual environment, pip, VS Code ও Jupyter-সংক্রান্ত সাধারণ সমস্যাগুলো কীভাবে শনাক্ত ও সমাধান করতে হয়, তা শিখব।