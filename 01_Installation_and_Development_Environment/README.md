# Chapter 01: Installation & Development Environment

## 1. Chapter Overview

Python শেখার আগে নিজের computer-এ একটি working development environment তৈরি করা জরুরি। Development environment হলো এমন একটি setup, যেখানে code লেখা, execute করা, output দেখা, error খুঁজে বের করা এবং project পরিচালনা করা যায়।

এই chapter-এ একদম শুরু থেকে Python installation, VS Code setup, terminal ব্যবহার, প্রথম Python program execute করা, package install করা এবং virtual environment পরিচালনা করা শেখানো হবে।

এই chapter পড়ার জন্য আগে থেকে programming জানা বাধ্যতামূলক নয়।

## 2. Learning Objectives

এই chapter শেষ করার পরে তুমি পারবে:

- Python development environment-এর প্রধান অংশগুলো বুঝতে।
- নিজের operating system অনুযায়ী Python install করতে।
- Python installation ও version যাচাই করতে।
- VS Code-এ Python development setup করতে।
- সঠিক Python interpreter নির্বাচন করতে।
- Terminal থেকে Python program execute করতে।
- Python REPL ব্যবহার করতে।
- `pip` দিয়ে package install করতে।
- Virtual environment তৈরি ও পরিচালনা করতে।
- Project dependencies-এর basic management করতে।
- Common installation ও configuration error-এর সমাধান করতে।

## 3. Complete Table of Contents

### Part 1: Understanding the Environment

1. [Introduction to Python Environment](01_Introduction_to_Python_Environment.md)
2. [Operating System and System Requirements](02_Operating_System_and_System_Requirements.md)

### Part 2: Installing Python

3. [Installing Python on Windows](03_Installing_Python_on_Windows.md)
4. [Installing Python on macOS](04_Installing_Python_on_macOS.md)
5. [Installing Python on Linux](05_Installing_Python_on_Linux.md)
6. [Verifying Python Installation](06_Verifying_Python_Installation.md)
7. [Python Version and Interpreter](07_Python_Version_and_Interpreter.md)
8. [Understanding PATH and Environment Variables](08_Understanding_PATH_and_Environment_Variables.md)

### Part 3: Setting Up the Code Editor

9. [Installing and Setting Up VS Code](09_Installing_and_Setting_Up_VS_Code.md)
10. [Setting Up the Python Extension](10_Setting_Up_the_Python_Extension.md)
11. [Selecting the Python Interpreter](11_Selecting_the_Python_Interpreter.md)

### Part 4: Terminal and First Program

12. [Terminal and Command Line Basics](12_Terminal_and_Command_Line_Basics.md)
13. [Creating a Python Project Folder](13_Creating_a_Python_Project_Folder.md)
14. [Creating and Running Your First Python File](14_Creating_and_Running_Your_First_Python_File.md)
15. [Running Python Code in Different Ways](15_Running_Python_Code_in_Different_Ways.md)
16. [Understanding the Working Directory](16_Understanding_the_Working_Directory.md)
17. [Using the Python REPL](17_Using_the_Python_REPL.md)

### Part 5: Packages and Virtual Environments

18. [Installing and Using pip](18_Installing_and_Using_pip.md)
19. [Creating and Managing Virtual Environments](19_Creating_and_Managing_Virtual_Environments.md)
20. [Installing Packages in a Virtual Environment](20_Installing_Packages_in_a_Virtual_Environment.md)
21. [Managing Project Dependencies](21_Managing_Project_Dependencies.md)

### Part 6: Additional Development Tools

22. [Introduction to Jupyter Notebooks](22_Introduction_to_Jupyter_Notebooks.md)
23. [Setting Up Git and GitHub](23_Setting_Up_Git_and_GitHub.md)

### Part 7: Troubleshooting and Best Practices

24. [Common Installation Errors and Solutions](24_Common_Installation_Errors_and_Solutions.md)
25. [Development Environment Best Practices](25_Development_Environment_Best_Practices.md)
---

## 4. Recommended Learning Order

এই chapter-এর topic-গুলো নিচের ক্রমে পড়লে শেখা সহজ হবে।

| Step | Topics | Main Goal |
|---|---|---|
| 1 | Topics 01–02 | Development environment বোঝা |
| 2 | Topics 03–08 | Python install ও configure করা |
| 3 | Topics 09–11 | VS Code setup করা |
| 4 | Topics 12–17 | Terminal, REPL ও প্রথম program |
| 5 | Topics 18–21 | `pip`, virtual environment ও dependencies |
| 6 | Topics 22–23 | Jupyter ও Git-এর পরিচিতি |
| 7 | Topics 24–26 | Error সমাধান ও practical assessment |

**গুরুত্বপূর্ণ:** Python install করার পদ্ধতি operating system অনুযায়ী আলাদা। নিজের computer-এ যে operating system ব্যবহার করো, সেই installation guide-টি অনুসরণ করবে। Windows, macOS ও Linux—তিনটির installation guide মুখস্থ করার প্রয়োজন নেই।

## 5. Required Tools

| Tool | Purpose |
|---|---|
| Python 3 | Python code execute করা |
| VS Code অথবা অন্য editor | Code লেখা ও edit করা |
| Terminal | Command execute করা |
| `pip` | Python package install ও manage করা |
| `venv` | Project-specific virtual environment তৈরি করা |
| Git | Code-এর পরিবর্তনের history পরিচালনা করা |
| GitHub | Repository host ও share করা |

শুরুতে Python, একটি code editor এবং terminal থাকলেই basic programming শুরু করা সম্ভব। অন্য tools শেখার সঙ্গে সঙ্গে ব্যবহার করবে।

Official resources:

- Python: https://www.python.org/downloads/
- Python Documentation: https://docs.python.org/3/
- VS Code: https://code.visualstudio.com/
- Git: https://git-scm.com/
- GitHub: https://github.com/

## 6. Practical Learning Method

শুধু installation guide পড়ে chapter শেষ করবে না। নিজের computer-এ প্রতিটি গুরুত্বপূর্ণ step execute করবে।

প্রতিটি topic-এর জন্য এই পদ্ধতি অনুসরণ করো:

1. Topic-এর explanation পড়ো।
2. Command বা code-এর কাজ বোঝো।
3. নিজের computer-এ command execute করো।
4. Expected output-এর সঙ্গে নিজের output তুলনা করো।
5. Error হলে message পড়ে কারণ খুঁজে বের করো।
6. কাজটি নিজে আবার করতে পারছ কি না যাচাই করো।

কোনো command কাজ না করলে error message না বুঝে বারবার random command execute করবে না।

## 7. Common Problems You May Face

এই chapter-এ নিচের সমস্যাগুলো সমাধান করতে শিখবে:

- Python install হয়েছে, কিন্তু terminal command কাজ করছে না।
- একাধিক Python version-এর মধ্যে ভুল version চালু হচ্ছে।
- VS Code Python interpreter খুঁজে পাচ্ছে না।
- Package install করার পরও `ModuleNotFoundError` দেখা যাচ্ছে।
- Virtual environment activate হচ্ছে না।
- Python file-এর path বা working directory ভুল হচ্ছে।
- Terminal-এর command নিজের operating system-এর সঙ্গে মিলছে না।

এসব সমস্যা programming শেখার সময় স্বাভাবিক। Error message পড়ে ধাপে ধাপে কারণ শনাক্ত করাও programming skill-এর অংশ।

## 8. Chapter Completion Checklist

Chapter শেষ করার আগে নিচের checklist সম্পন্ন করো।

- [ ] Python install ও version verify করেছি।
- [ ] VS Code বা নির্বাচিত editor-এ Python code লিখেছি।
- [ ] `main.py` তৈরি করেছি।
- [ ] Terminal থেকে Python program execute করেছি।
- [ ] Python REPL-এ expression পরীক্ষা করেছি।
- [ ] Project-specific virtual environment তৈরি করেছি।
- [ ] Virtual environment activate ও deactivate করেছি।
- [ ] Environment-এর মধ্যে একটি package install করেছি।
- [ ] Dependency list সংরক্ষণের পদ্ধতি বুঝেছি।
- [ ] Common installation error-এর সমাধান অনুশীলন করেছি।

## 9. What Comes Next?

এই chapter শেষ হলে তুমি নিজের computer-এ Python program লেখা ও execute করার জন্য প্রস্তুত থাকবে।

এরপর শুরু হবে **Chapter 02 — Python Fundamentals**, যেখানে Python syntax, statements, comments, indentation, variables, naming rules এবং basic programming structure শেখা হবে।

