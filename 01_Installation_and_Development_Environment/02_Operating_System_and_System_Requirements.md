# 02. Operating System and System Requirements

## 1. Introduction

Python install করার আগে নিজের computer-এর operating system এবং system configuration সম্পর্কে basic ধারণা থাকা দরকার।

কারণ operating system অনুযায়ী Python install করার পদ্ধতি, terminal command এবং কিছু configuration আলাদা হতে পারে।

এই topic-এ আমরা শিখব:

- Operating System (OS) কী।
- Windows, macOS ও Linux-এর পার্থক্য।
- 32-bit ও 64-bit architecture কী।
- System requirements বলতে কী বোঝায়।
- নিজের computer-এর system information কীভাবে দেখা যায়।
- Python installation-এর আগে কী কী যাচাই করতে হবে।

---

## 2. What Is an Operating System?

**Operating System (OS)** হলো system software, যা computer-এর hardware ও software-এর বিভিন্ন কাজ পরিচালনা করে।

এটি user এবং computer hardware-এর মধ্যে কাজ করার একটি environment তৈরি করে।

প্রধান operating system-এর উদাহরণ:

- Microsoft Windows
- Apple macOS
- Linux

Operating system-এর সাহায্যে আমরা file manage করতে পারি, application চালাতে পারি এবং বিভিন্ন development tool ব্যবহার করতে পারি।

### Examples of Operating Systems

| Operating System | সাধারণ ব্যবহার |
|---|---|
| Windows | Personal computer, education ও office work |
| macOS | Apple Mac computers |
| Linux | Development, servers ও বিভিন্ন computing environment |

Python এই তিনটি operating system-এই ব্যবহার করা যায়। তবে installation-এর পদ্ধতি ও কিছু command আলাদা হতে পারে।

---

## 3. Windows Operating System

**Windows** হলো Microsoft-এর তৈরি একটি widely used operating system।

অনেক শিক্ষার্থী ও developer Windows computer-এ Python শেখেন।

Windows-এর কিছু পরিচিত version:

- Windows 10
- Windows 11

### Why Is Windows Common for Python Development?

- VS Code-এর মতো editor ব্যবহার করা যায়।
- Python-এর official installer ব্যবহার করা যায়।
- Command Prompt ও PowerShell-এর মাধ্যমে command চালানো যায়।
- Programming, web development, data analysis ও automation করা যায়।

### Important Windows Tools

| Tool | কাজ |
|---|---|
| Settings | Computer-এর system information ও configuration দেখা |
| File Explorer | File ও folder manage করা |
| Command Prompt | Command চালানো |
| PowerShell | Command ও scripting-এর কাজ করা |
| Windows Terminal | বিভিন্ন command-line shell ব্যবহার করা |

Windows-এ Python install করার বিস্তারিত পদ্ধতি পরবর্তী installation topic-এ আলোচনা করা হবে।

---

## 4. macOS Operating System

**macOS** হলো Apple-এর Mac computer-এর operating system।

macOS-এও Python programming, web development, data analysis এবং automation করা যায়।

### Common Tools in macOS

| Tool | কাজ |
|---|---|
| System Settings | Computer-এর settings ও information দেখা |
| Finder | File ও folder manage করা |
| Terminal | Command চালানো |
| VS Code | Code লেখা ও edit করা |

macOS-এ terminal ব্যবহার করে Python-এর version পরীক্ষা করা যায়।

```bash
python3 --version
```

Command সফল হলে installed Python version দেখাবে।

তবে command-এর নাম ও ফলাফল computer-এর configuration অনুযায়ী ভিন্ন হতে পারে।

---

## 5. Linux Operating System

**Linux** একটি open-source operating system kernel। সাধারণ ব্যবহারে Ubuntu, Debian ও Fedora-এর মতো Linux-based operating system-কে Linux distribution বলা হয়।

Linux programming ও server development-এ ব্যাপকভাবে ব্যবহৃত হয়।

### Examples of Linux Distributions

- Ubuntu
- Debian
- Fedora
- Linux Mint

### Common Linux Tools

| Tool | কাজ |
|---|---|
| Terminal | Command চালানো |
| File Manager | File ও folder manage করা |
| Package Manager | System software install ও update করা |
| VS Code | Code লেখা ও edit করা |

Linux-এ অনেক ক্ষেত্রে Python আগে থেকেই থাকে। কিন্তু আগে থেকে থাকা Python-এর version, configuration এবং development-এর জন্য সেটি উপযুক্ত কি না, তা যাচাই করা দরকার।

Version পরীক্ষা করার জন্য:

```bash
python3 --version
```

**Important:** System-এর নিজস্ব tools-এর জন্য ব্যবহৃত Python version পরিবর্তন করা বা system Python সরিয়ে ফেলা উচিত নয়। Project অনুযায়ী আলাদা virtual environment ব্যবহার করা নিরাপদ পদ্ধতি।

---

## 6. Difference Between Windows, macOS and Linux

| Feature | Windows | macOS | Linux |
|---|---|---|---|
| Developed by / Origin | Microsoft | Apple | Linux kernel ও বিভিন্ন community/organization-এর ecosystem |
| Common command-line tools | PowerShell, CMD | Terminal | Terminal |
| Python support | আছে | আছে | আছে |
| Official Python installation options | Official installer ও অন্যান্য পদ্ধতি | Official installer ও অন্যান্য পদ্ধতি | Distribution package manager ও অন্যান্য পদ্ধতি |
| Common use | Personal computing, development | Personal computing, development | Development, servers, computing |
| Command differences | কিছু command আলাদা | কিছু command আলাদা | কিছু command আলাদা |

### Which Operating System Is Best for Learning Python?

Python শেখার জন্য কোনো একটি operating system বাধ্যতামূলকভাবে সেরা নয়।

- Windows-এ Python শেখা যায়।
- macOS-এ Python শেখা যায়।
- Linux-এ Python শেখা যায়।

তোমার কাছে যে computer আছে, সেটি দিয়েই শুরু করা সম্ভব।

---

## 7. What Are System Requirements?

**System Requirements** বলতে কোনো software install ও ব্যবহার করার জন্য প্রয়োজনীয় hardware এবং software-এর শর্তগুলোকে বোঝায়।

Python-এর ক্ষেত্রে system requirements-এর মধ্যে থাকতে পারে:

- Supported operating system
- Processor architecture
- Available storage
- Required permissions
- Compatible Python version

Python-এর exact requirements version ও operating system অনুযায়ী পরিবর্তিত হতে পারে।

সাধারণ beginner-level Python programming-এর জন্য খুব powerful computer প্রয়োজন হয় না।

তবে machine learning, deep learning বা বড় dataset নিয়ে কাজ করলে অতিরিক্ত RAM, storage এবং কখনো কখনো GPU প্রয়োজন হতে পারে।

### Basic Requirement Checklist

| Requirement | কেন গুরুত্বপূর্ণ |
|---|---|
| Supported OS | Installer ও Python version compatible কি না বুঝতে |
| Processor architecture | উপযুক্ত installer নির্বাচন করতে |
| Available storage | Python ও development tools install করতে |
| User permission | Installation ও configuration সম্পন্ন করতে |
| Internet connection | Installer বা package download করতে |
| Code editor | Code লেখা ও manage করতে |

---

## 8. What Is 32-bit and 64-bit Architecture?

Computer architecture-এর একটি গুরুত্বপূর্ণ বিষয় হলো 32-bit ও 64-bit architecture।

সহজভাবে, এগুলো processor এবং operating system-এর data handling ও addressing capability-এর সঙ্গে সম্পর্কিত।

Python-এর installer নির্বাচন করার সময় architecture গুরুত্বপূর্ণ হতে পারে।

### 32-bit Architecture

32-bit system-এ 32-bit architecture-এর জন্য তৈরি software চালানোর compatibility সীমাবদ্ধতা থাকতে পারে। কিছু modern software বা Python version-এর জন্য 32-bit support আর উপলভ্য নয়।

### 64-bit Architecture

64-bit system সাধারণত বেশি memory address করতে পারে এবং বর্তমানে personal computer-এ ব্যাপকভাবে ব্যবহৃত হয়।

64-bit operating system-এর জন্য উপযুক্ত 64-bit Python installer নির্বাচন করা সাধারণত সঠিক পদ্ধতি।

### Important Difference

**64-bit processor** এবং **64-bit operating system** একই বিষয় নয়।

একটি computer-এর processor 64-bit হলেও সেটিতে 32-bit operating system install করা থাকতে পারে।

তাই শুধু processor architecture নয়, operating system-এর architecture-ও যাচাই করতে হবে।

---

## 9. How to Check System Information in Windows

Windows ব্যবহার করলে কয়েকটি সহজ পদ্ধতিতে নিজের system information দেখা যায়।

### Method 1: Using Settings

1. Start Menu খুলে **Settings**-এ যাও।
2. **System** নির্বাচন করো।
3. **About** section খুঁজে বের করো।
4. নিচের তথ্যগুলো দেখো:
   - Windows edition
   - Windows version
   - Processor
   - Installed RAM
   - System type

System type-এ সাধারণত operating system architecture সম্পর্কে তথ্য পাওয়া যায়।

### Method 2: Using System Information

1. Start Menu খুলে search box-এ `System Information` লিখো।
2. Application-টি open করো।
3. নিচের তথ্যগুলো দেখো:
   - OS Name
   - Version
   - System Type
   - Processor
   - Installed Physical Memory

### Method 3: Using a Terminal

PowerShell বা Command Prompt খুলে নিচের command চালাতে পারো:

```powershell
systeminfo
```

এটি operating system ও computer configuration-এর বিভিন্ন তথ্য দেখায়।

**Note:** সব output এখন মুখস্থ করার দরকার নেই। Python install করার জন্য প্রয়োজনীয় তথ্যগুলো শনাক্ত করতে পারাই মূল লক্ষ্য।

---

## 10. How to Check System Information on macOS

macOS-এ system information দেখার জন্য:

1. Apple menu খোলো।
2. **About This Mac** নির্বাচন করো।
3. macOS version, chip বা processor এবং memory-সংক্রান্ত তথ্য দেখো।

অতিরিক্ত system information-এর জন্য System Information application ব্যবহার করা যায়।

Terminal-এ নিচের command চালিয়ে processor architecture সম্পর্কেও তথ্য পাওয়া যায়:

```bash
uname -m
```

এটি system-এর machine hardware name দেখায়। তবে এই output-কে একাই সব compatibility নির্ধারণের জন্য যথেষ্ট ধরে নেওয়া উচিত নয়।

---

## 11. How to Check System Information on Linux

Linux distribution অনুযায়ী interface আলাদা হতে পারে।

সাধারণভাবে Settings-এর **About** বা **System Information** section থেকে system details দেখা যায়।

Terminal-এ:

```bash
uname -m
```

এটি machine architecture-এর নাম দেখায়।

Operating system-এর বিস্তারিত তথ্য দেখতে অনেক Linux distribution-এ ব্যবহার করা যায়:

```bash
cat /etc/os-release
```

এখানে distribution-এর নাম ও version-সংক্রান্ত তথ্য দেখা যেতে পারে।

Python version পরীক্ষা করতে:

```bash
python3 --version
```

Linux-এ Python install করার আগে distribution-এর package management ও system Python সম্পর্কে ধারণা রাখা গুরুত্বপূর্ণ।

---

## 12. Do You Need a Powerful Computer for Python?

Python-এর basic programming শেখার জন্য সাধারণত high-end computer প্রয়োজন হয় না।

### Basic Python Learning

সাধারণত নিচের কাজগুলোর জন্য modest computer যথেষ্ট:

- Variables ও data types শেখা
- Conditional statements ও loops অনুশীলন
- Functions ও OOP শেখা
- Basic file handling
- ছোট programming projects
- Basic automation scripts

### Advanced Python Tasks

কিছু advanced task-এ বেশি resources প্রয়োজন হতে পারে:

| Task | সম্ভাব্য অতিরিক্ত চাহিদা |
|---|---|
| Large data analysis | বেশি RAM ও storage |
| Machine learning | Dataset ও model অনুযায়ী CPU/RAM |
| Deep learning | বড় model-এর জন্য GPU ও বেশি memory |
| Large-scale applications | Project অনুযায়ী CPU, RAM ও storage |
| Multiple virtual machines | বেশি RAM ও storage |

এই requirements কাজের ধরন, dataset এবং ব্যবহৃত software-এর ওপর নির্ভর করে।

---

## 13. Internet Connection and Permissions

Python install করার জন্য internet connection সব সময় বাধ্যতামূলক নয়। Offline installer থাকলে internet ছাড়াও installation করা সম্ভব হতে পারে।

তবে internet থাকলে সহজে:

- Python installer download করা যায়।
- VS Code ও extension download করা যায়।
- External packages install করা যায়।
- Documentation ও tutorials দেখা যায়।

### Administrator Permission

কিছু installation-এর জন্য administrator permission প্রয়োজন হতে পারে। অন্যদিকে user-specific installation অনেক ক্ষেত্রে administrator permission ছাড়াও করা যায়।

বিশেষ করে shared বা university computer ব্যবহার করলে software install করার অনুমতি আছে কি না, তা আগে যাচাই করা উচিত।

---

## 14. Common Beginner Mistakes

### Mistake 1: Downloading the Wrong Installer

Operating system বা architecture-এর সঙ্গে compatible নয় এমন installer নির্বাচন করলে installation ব্যর্থ হতে পারে।

**Solution:** Download করার আগে নিজের operating system ও architecture যাচাই করো।

### Mistake 2: Assuming Every Computer Has the Same Python Version

বিভিন্ন computer-এ বিভিন্ন Python version থাকতে পারে।

**Solution:** Installation-এর পরে version command ব্যবহার করে যাচাই করো।

### Mistake 3: Assuming a 64-bit Processor Always Means a 64-bit OS

Processor ও operating system-এর architecture আলাদা হতে পারে।

**Solution:** System information থেকে operating system-এর architecture যাচাই করো।

### Mistake 4: Removing the System Python on Linux

System Python সরিয়ে ফেললে operating system-এর কিছু tool ক্ষতিগ্রস্ত হতে পারে।

**Solution:** System Python পরিবর্তন না করে project-specific virtual environment ব্যবহার করো।

### Mistake 5: Thinking a Powerful Computer Is Required

Basic Python programming-এর জন্য সাধারণত powerful GPU বা high-end processor লাগে না।

**Solution:** নিজের বর্তমান computer দিয়েই শুরু করো।

---

## 15. Practice Tasks

### Task 1: Identify Your Operating System

নিজের computer-এ কোন operating system ব্যবহার করছ, তা লিখে রাখো।

উদাহরণ:

```text
Operating System: Windows 11
```

এটি শুধু example। নিজের computer-এর সঠিক তথ্য লিখবে।

### Task 2: Check Your System Information

নিচের তথ্যগুলো সংগ্রহ করো:

- Operating system name
- Operating system version
- Processor
- Installed RAM
- System architecture

### Task 3: Answer These Questions

1. Operating System কী?
2. Windows, macOS ও Linux-এর মধ্যে দুটি পার্থক্য লেখো।
3. System requirements বলতে কী বোঝায়?
4. 32-bit ও 64-bit architecture কেন গুরুত্বপূর্ণ?
5. Python শেখার জন্য high-end computer কি বাধ্যতামূলক?
6. Linux-এ system Python সরিয়ে ফেলা কেন ঝুঁকিপূর্ণ হতে পারে?

### Task 4: Verify Your System

নিজের operating system অনুযায়ী system information দেখার উপযুক্ত method নির্বাচন করো।

এখনো Python install না করা থাকলে সমস্যা নেই। এই topic-এর লক্ষ্য হলো installation-এর আগে নিজের computer সম্পর্কে জানা।

---

## 16. Quick Revision

| Topic | Key Point |
|---|---|
| Operating System | Computer-এর hardware ও software পরিচালনা করে |
| Windows | Microsoft-এর operating system |
| macOS | Apple-এর Mac computer-এর operating system |
| Linux | Open-source kernel-ভিত্তিক operating system ecosystem |
| System Requirements | Software ব্যবহারের জন্য প্রয়োজনীয় শর্ত |
| 32-bit / 64-bit | Software ও system compatibility-এর সঙ্গে সম্পর্কিত |
| System Information | OS, processor, RAM ও architecture-এর তথ্য |
| Python Compatibility | Python version ও operating system অনুযায়ী যাচাই করতে হয় |
| Basic Python | সাধারণত high-end hardware প্রয়োজন হয় না |

---

## 17. Chapter Connection

এই topic-এ operating system ও system requirements সম্পর্কে ধারণা নেওয়া হয়েছে। এখন নিজের computer-এর OS ও architecture জানা থাকলে উপযুক্ত installation method নির্বাচন করা সহজ হবে।

**Next Topic:** [03. Installing Python on Windows](03_Installing_Python_on_Windows.md)