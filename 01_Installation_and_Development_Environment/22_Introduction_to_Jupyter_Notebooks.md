# 22. Introduction to Jupyter Notebooks

## 1. Introduction

Python code লেখার জন্য আমরা সাধারণত `.py` file ব্যবহার করি। কিন্তু কিছু কাজের ক্ষেত্রে code-এর ছোট ছোট অংশ আলাদাভাবে run করা, সঙ্গে সঙ্গে output দেখা এবং code-এর পাশে explanation লেখা দরকার হয়।

এই ধরনের কাজের জন্য **Jupyter Notebook** খুবই জনপ্রিয় একটি tool।

Jupyter Notebook বিশেষভাবে উপকারী:

- Python শেখার সময়।
- Data Analysis করার সময়।
- Machine Learning ও Artificial Intelligence নিয়ে কাজ করার সময়।
- Data visualization ও graph তৈরির সময়।
- Experiment এবং research করার সময়।
- Code-এর সঙ্গে explanation ও output সংরক্ষণ করতে।

এই topic-এ আমরা শিখব:

1. Jupyter Notebook কী।
2. Notebook, Cell ও Kernel কী।
3. `.ipynb` file কীভাবে কাজ করে।
4. Jupyter Notebook install ও run করা।
5. VS Code-এ Notebook ব্যবহার করা।
6. Code Cell ও Markdown Cell ব্যবহার করা।
7. Cell execute ও kernel manage করা।
8. Common error সমাধান করা।

---

## 2. What Is Jupyter Notebook?

Jupyter Notebook হলো একটি interactive computing environment, যেখানে code, text, mathematical expression, table, visualization এবং output একসঙ্গে রাখা যায়।

Python শেখার ক্ষেত্রে এটি একটি notebook document-এর মতো কাজ করে।

ধরা যাক, তুমি নিচের code লিখলে:

```python
print("Hello, Python!")
```

Code execute করার পর output একই notebook-এর মধ্যে দেখা যাবে:

```text
Hello, Python!
```

এরপর নতুন cell-এ আরেকটি code লিখে run করতে পারবে। আগের cell-এর code আবার run করার প্রয়োজন হবে না, যদি আগের output বা variable state পরিবর্তন করার দরকার না থাকে।

### Why Is It Called a Notebook?

একটি সাধারণ notebook-এ যেমন লেখা, হিসাব ও ব্যাখ্যা একসঙ্গে রাখা যায়, Jupyter Notebook-এও code, explanation এবং result একসঙ্গে রাখা যায়।

উদাহরণ:

- একটি cell-এ Python code।
- পরের cell-এ সেই code-এর explanation।
- অন্য cell-এ calculation।
- আরেকটি cell-এ graph।

এভাবে learning ও experimentation সহজ হয়।

---

## 3. What Is an `.ipynb` File?

Jupyter Notebook file-এর extension হলো:

```text
.ipynb
```

উদাহরণ:

```text
PythonPractice.ipynb
DataAnalysis.ipynb
MachineLearning.ipynb
```

`.ipynb` হলো একটি notebook document format, যা JSON-ভিত্তিক structure ব্যবহার করে।

একটি notebook file-এ থাকতে পারে:

- Code cell।
- Markdown cell।
- Cell-এর execution order সম্পর্কিত তথ্য।
- সংরক্ষিত output।
- Notebook metadata।
- Graph বা অন্য rich output-এর data।

### `.py` vs `.ipynb`

| Feature | `.py` File | `.ipynb` File |
|---|---|---|
| Format | Python source code | Notebook document |
| Code execution | সাধারণত script হিসেবে | Cell-by-cell |
| Markdown explanation | সাধারণত comment বা আলাদা file | আলাদা Markdown cell |
| Output | সাধারণত Terminal বা application-এ | Cell-এর নিচে দেখানো যায় |
| Graph ও rich output | আলাদাভাবে দেখতে হতে পারে | Notebook-এর মধ্যে দেখা যায় |
| Best use | Script, application, reusable code | Learning, analysis, experimentation |

দুটোই Python শেখা ও ব্যবহার করার জন্য উপকারী। কাজের ধরন অনুযায়ী সঠিক format বেছে নিতে হয়।

---

## 4. What Is a Cell?

Notebook-এর content ছোট ছোট section-এ ভাগ করা থাকে। প্রতিটি section-কে **Cell** বলা হয়।

প্রধানত দুটি cell type বেশি ব্যবহার করা হয়:

1. Code Cell
2. Markdown Cell

### 4.1 Code Cell

Code Cell-এ Python code লেখা ও execute করা যায়।

উদাহরণ:

```python
x = 10
y = 20

print(x + y)
```

Output:

```text
30
```

### 4.2 Markdown Cell

Markdown Cell-এ explanation, heading, list, link, table ও formatted text লেখা যায়।

উদাহরণ:

```markdown
# Python Variables

Variable হলো একটি নাম, যার মাধ্যমে কোনো value-কে reference করা যায়।

- `name`
- `age`
- `price`
```

Cell render করার পর এটি formatted text হিসেবে দেখা যাবে।

### Why Use Both Cell Types?

Code Cell calculation ও programming-এর জন্য ব্যবহৃত হয়।

Markdown Cell code-এর উদ্দেশ্য ও result ব্যাখ্যা করতে সাহায্য করে।

দুটো একসঙ্গে ব্যবহার করলে notebook পড়া ও বোঝা সহজ হয়।

---

## 5. What Is a Kernel?

**Kernel** হলো সেই process, যা notebook-এর code execute করে এবং execution state ধরে রাখে।

Python Notebook-এর ক্ষেত্রে Python kernel code চালায়।

### Example

প্রথম Code Cell-এ:

```python
name = "Masum"
```

Cell execute করার পরে `name` variable kernel-এর memory-তে থাকে।

এখন দ্বিতীয় Code Cell-এ:

```python
print(name)
```

Output:

```text
Masum
```

দ্বিতীয় cell প্রথম cell-এ তৈরি করা variable ব্যবহার করতে পারছে, কারণ একই kernel-এর state বজায় রয়েছে।

### Important Concept

Notebook-এর cell আলাদাভাবে execute করা গেলেও তাদের variable ও state সাধারণত একই kernel-এর মধ্যে share হয়।

তাই cell-এর execution order গুরুত্বপূর্ণ।

### What Happens If the Kernel Restarts?

Kernel restart হলে সাধারণত memory-তে থাকা variable ও runtime state মুছে যায়।

কিন্তু notebook file-এর code ও সংরক্ষিত output সাধারণত file-এ থেকে যায়।

Restart-এর পরে variable ব্যবহার করতে হলে সংশ্লিষ্ট cell-গুলো আবার execute করতে হবে।

---

## 6. Installing Jupyter Notebook

Jupyter Notebook ব্যবহার করার একটি পদ্ধতি হলো `pip` দিয়ে install করা।

তবে package install করার আগে একটি project-specific virtual environment তৈরি করা ভালো।

### Step 1: Create a Project Folder

Terminal-এ:

```bash
mkdir JupyterPractice
cd JupyterPractice
```

### Step 2: Create a Virtual Environment

Windows:

```powershell
py -m venv .venv
```

macOS/Linux:

```bash
python3 -m venv .venv
```

তোমার system-এ যে Python command সঠিকভাবে কাজ করে, সেটি ব্যবহার করো।

### Step 3: Activate the Environment

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

Windows Command Prompt:

```bat
.venv\Scripts\activate.bat
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### Step 4: Install Jupyter Notebook

```bash
python -m pip install notebook
```

Installation সম্পন্ন হওয়ার জন্য অপেক্ষা করো।

### Step 5: Verify the Installation

```bash
python -m pip show notebook
```

Package-এর details দেখা গেলে installation যাচাই করা যাবে।

**মনে রাখবে:** Jupyter-এর একাধিক interface ও package আছে। এখানে আমরা classic Jupyter Notebook interface-এর introductory workflow শিখছি।

---

## 7. Running Jupyter Notebook

Jupyter install করার পরে project folder-এর Terminal-এ চালাও:

```bash
python -m notebook
```

সাধারণত Jupyter একটি local server চালু করবে এবং browser-এ notebook interface খোলার চেষ্টা করবে।

Browser স্বয়ংক্রিয়ভাবে না খুললে Terminal-এর output-এ দেওয়া local URL ব্যবহার করা যায়।

URL-টি সাধারণত `localhost` বা `127.0.0.1` দিয়ে শুরু হয় এবং এতে port ও access token থাকতে পারে।

**সতর্কতা:** Terminal-এ দেখানো access token-সহ URL অন্য কাউকে share করো না।

### Creating a New Notebook

Jupyter interface-এর version অনুযায়ী menu কিছুটা আলাদা হতে পারে।

সাধারণভাবে:

1. Project directory-এর file browser দেখো।
2. New Notebook তৈরি করার option নির্বাচন করো।
3. Python kernel নির্বাচন করতে বললে উপযুক্ত kernel নির্বাচন করো।
4. Notebook-টি অর্থপূর্ণ নামে save করো।

উদাহরণ:

```text
PythonBasics.ipynb
```

### Stopping Jupyter Notebook

কাজ শেষ হলে notebook server বন্ধ করতে পারো।

সাধারণভাবে server চালু থাকা Terminal-এ `Ctrl + C` চাপো এবং prompt অনুযায়ী shutdown নিশ্চিত করো।

Browser tab বন্ধ করলেই server সব সময় বন্ধ হয় না।

---

## 8. Using Jupyter Notebook in VS Code

তুমি যদি VS Code ব্যবহার করো, তাহলে সেখান থেকেও Jupyter Notebook তৈরি ও execute করতে পারো।

### Step 1: Install the Required Extensions

VS Code-এর Extensions panel খুলে install করো:

- Python extension by Microsoft।
- Jupyter extension by Microsoft।

Extension install করার সময় publisher ও extension-এর নাম যাচাই করো।

### Step 2: Open Your Project Folder

VS Code-এ `JupyterPractice` folder open করো।

### Step 3: Create a Notebook

Explorer panel থেকে নতুন file তৈরি করো:

```text
PythonBasics.ipynb
```

অথবা VS Code-এর command ও notebook interface ব্যবহার করে নতুন Jupyter Notebook তৈরি করো।

### Step 4: Select the Kernel

Notebook-এর kernel selector থেকে project-এর `.venv`-এর Python environment নির্বাচন করো।

যদি environment list-এ না থাকে, তাহলে আগে environment তৈরি ও activate করে দেখো এবং VS Code-এ Python interpreter নির্বাচন করো।

প্রয়োজনে সেই environment-এ notebook-এর জন্য প্রয়োজনীয় package install করতে হতে পারে।

### Step 5: Write and Run Code

প্রথম Code Cell-এ লেখো:

```python
print("Hello from Jupyter Notebook!")
```

Cell-এর Run button ব্যবহার করে execute করো।

Output cell-এর নিচে দেখা যাবে।

**Best practice:** Notebook-এর kernel যেন project-এর সঠিক Python environment ব্যবহার করে, তা যাচাই করো।

---

## 9. Writing Your First Notebook

এখন একটি ছোট notebook তৈরি করি।

File name:

```text
PythonBasics.ipynb
```

### Cell 1: Markdown Cell

Cell type Markdown নির্বাচন করে লেখো:

```markdown
# My First Python Notebook

এই notebook-এ আমি Python-এর basic operations অনুশীলন করব।
```

Cell execute করলে formatted heading ও text দেখা যাবে।

### Cell 2: Code Cell

```python
print("Hello, Python!")
```

Output:

```text
Hello, Python!
```

### Cell 3: Code Cell

```python
x = 15
y = 25

print("Sum:", x + y)
```

Output:

```text
Sum: 40
```

### Cell 4: Markdown Cell

```markdown
## Explanation

- `x` variable-এ `15` রাখা হয়েছে।
- `y` variable-এ `25` রাখা হয়েছে।
- `x + y` দিয়ে দুটি value যোগ করা হয়েছে।
```

এভাবে code ও explanation একসঙ্গে সাজানো যায়।

---

## 10. Executing Cells

Notebook-এ cell execute করার একাধিক উপায় আছে।

VS Code ও Jupyter interface-এ keyboard shortcut বা Run button ব্যবহার করা যায়।

### Common Keyboard Shortcuts

| Shortcut | Common Purpose |
|---|---|
| `Shift + Enter` | বর্তমান cell execute করে এবং সাধারণত পরের cell-এ যায় |
| `Ctrl + Enter` | বর্তমান cell execute করে |
| `Esc` | Command mode-এ যেতে সাহায্য করে |
| `Enter` | Edit mode-এ যেতে সাহায্য করে |

macOS-এ কিছু shortcut-এর ক্ষেত্রে `Cmd` ব্যবহৃত হতে পারে। Interface ও keymap অনুযায়ী shortcut ভিন্ন হতে পারে।

### Example

প্রথম cell:

```python
a = 5
```

দ্বিতীয় cell:

```python
b = 10
```

তৃতীয় cell:

```python
print(a + b)
```

Output:

```text
15
```

তিনটি cell সঠিক execution state-এ চালালে output পাওয়া যাবে।

### What If You Run Cells Out of Order?

ধরা যাক, তুমি প্রথমে তৃতীয় cell চালালে:

```python
print(a + b)
```

কিন্তু `a` ও `b` এখনো define করা হয়নি।

তাহলে `NameError` হতে পারে।

সমাধান:

1. প্রয়োজনীয় variable তৈরি করা cell execute করো।
2. তারপর dependent cell execute করো।
3. প্রয়োজনে kernel restart করে সব cell উপর থেকে নিচে আবার চালাও।

---

## 11. Cell Execution Order

Notebook-এর cell-এর অবস্থান এবং execution order সব সময় এক নয়।

প্রতিটি code cell execute হওয়ার সময় kernel-এর state পরিবর্তিত হতে পারে।

### Example

প্রথম cell:

```python
value = 10
```

দ্বিতীয় cell:

```python
value = 20
```

তৃতীয় cell:

```python
print(value)
```

যদি প্রথম, দ্বিতীয় ও তৃতীয় cell এই ক্রমে execute করো, output হবে:

```text
20
```

কারণ দ্বিতীয় cell variable-এর value পরিবর্তন করেছে।

এখন যদি প্রথম cell আবার execute করো, `value`-এর value আবার `10` হবে।

### Best Practice

- Cell-এর execution order খেয়াল রাখো।
- অপ্রয়োজনীয় state dependency কমাও।
- গুরুত্বপূর্ণ calculation-এর আগে প্রয়োজনীয় cell execute হয়েছে কি না যাচাই করো।
- Notebook share করার আগে fresh kernel-এ সব cell উপর থেকে নিচে execute করে দেখো।

VS Code ও Jupyter-এ Restart Kernel এবং Run All ধরনের option থাকতে পারে। এগুলো ব্যবহার করে notebook-এর execution reproducible কি না যাচাই করা যায়।

---

## 12. Using Markdown Cells

Markdown Cell-এ code execute হয় না। বরং text-কে সুন্দরভাবে format করা যায়।

### Heading

```markdown
# Main Heading

## Subheading

### Smaller Heading
```

### Bold and Italic

```markdown
**Bold text**

*Italic text*
```

### Lists

```markdown
- Python
- Java
- C++
```

### Numbered List

```markdown
1. Install Python
2. Create a project
3. Run the code
```

### Links

```markdown
[Python Official Website](https://www.python.org/)
```

### Inline Code

```markdown
Use `print()` to display output.
```

### Code Blocks in Markdown

````markdown
```python
print("Hello")
```
````

Markdown Cell-এ code block দেখানো যায়, কিন্তু সেটি সাধারণত Python Code Cell-এর মতো execute হয় না।

**কখন ব্যবহার করবে?** Notebook-এ theory, learning objectives, formula explanation, experiment description এবং conclusion লেখার জন্য Markdown Cell ব্যবহার করতে পারো।

---

## 13. Displaying Output

Notebook শুধু plain text output দেখানোর মধ্যেই সীমাবদ্ধ নয়।

এটি বিভিন্ন ধরনের rich output দেখাতে পারে।

### 13.1 Text Output

```python
print("Python is easy to practice.")
```

### 13.2 Calculation Output

```python
10 + 20
```

অনেক notebook interface-এ শেষ expression-এর result স্বয়ংক্রিয়ভাবে দেখানো হয়।

Output:

```text
30
```

### 13.3 Multiple Outputs

```python
print("First output")
print("Second output")
```

Output:

```text
First output
Second output
```

### 13.4 Data Visualization

Data visualization library ব্যবহার করে graph বা chart তৈরি করে notebook-এ দেখানো যায়।

উদাহরণ:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y = [2, 4, 6, 8]

plt.plot(x, y)
plt.title("Simple Line Graph")
plt.xlabel("X")
plt.ylabel("Y")
plt.show()
```

এই example চালানোর আগে environment-এ `matplotlib` install করা থাকতে হবে:

```bash
python -m pip install matplotlib
```

এই ধরনের visualization Data Analysis ও Machine Learning-এর সময় বিশেষভাবে কাজে লাগে।

---

## 14. Understanding Notebook State

Notebook-এর kernel variables, imported modules এবং runtime objects memory-তে ধরে রাখতে পারে।

উদাহরণ:

```python
student_name = "Masum"
student_id = 101
```

অন্য cell-এ:

```python
print(student_name)
print(student_id)
```

Output:

```text
Masum
101
```

দ্বিতীয় cell আগের cell-এর variable ব্যবহার করছে।

### What Is a Stale Output?

Cell-এর code পরিবর্তন করার পর সেটি আবার execute না করলে আগের output notebook-এ থেকে যেতে পারে।

এতে code এবং displayed output-এর মধ্যে অসামঞ্জস্য তৈরি হতে পারে।

### How to Avoid It

- Code পরিবর্তন করার পরে cell আবার execute করো।
- Notebook save করো।
- গুরুত্বপূর্ণ notebook fresh kernel-এ পুনরায় চালাও।
- Share করার আগে output যাচাই করো।

### Restarting the Kernel

Kernel restart করলে runtime state সাধারণত মুছে যায়।

এরপর code-এর ওপর থেকে নিচে পুনরায় execute করে notebook-এর ফলাফল যাচাই করা যায়।

---

## 15. Saving and Sharing Notebooks

Notebook save করলে সাধারণত `.ipynb` file তৈরি হয়।

উদাহরণ:

```text
JupyterPractice/
├── .venv/
├── PythonBasics.ipynb
└── README.md
```

Notebook-এর মধ্যে code, Markdown এবং saved output থাকতে পারে।

### Before Sharing a Notebook

1. File save করো।
2. Code-এর execution order যাচাই করো।
3. Fresh kernel-এ সব cell চালিয়ে দেখো।
4. অপ্রয়োজনীয় বা sensitive output সরিয়ে দাও।
5. API key, password বা personal information প্রকাশ পেয়েছে কি না দেখো।
6. প্রয়োজনীয় package-এর তালিকা document করো।

### Should `.venv` Be Shared?

সাধারণত `.venv` repository-তে upload না করে dependency file ও setup instructions share করো।

Notebook-এ ব্যবহার করা package-গুলোর dependency অন্য developer-কে জানানো জরুরি।

### Important Security Note

Notebook file-এ saved output, local path, personal information বা sensitive data থাকতে পারে। Share করার আগে file-টি review করো।

---

## 16. Jupyter Notebook vs Python Script

কোন পরিস্থিতিতে Notebook এবং কোন পরিস্থিতিতে `.py` file ব্যবহার করবে, তা বোঝা দরকার।

| Situation | Recommended Format |
|---|---|
| Python-এর basic শেখা | Notebook অথবা `.py` |
| Code experiment করা | Notebook |
| Data Analysis | Notebook প্রায়ই উপযোগী |
| Machine Learning experiment | Notebook প্রায়ই উপযোগী |
| বড় application তৈরি | `.py` ও package structure |
| Reusable application logic | `.py` module |
| Automated script | সাধারণত `.py` |
| Theory ও result একসঙ্গে রাখা | Notebook |

এটি কোনো কঠোর নিয়ম নয়। বাস্তব project-এ Notebook ও `.py` file একসঙ্গেও ব্যবহার করা হয়।

---

## 17. Common Errors and Solutions

### Error 1: `ModuleNotFoundError`

উদাহরণ:

```python
import matplotlib
```

Error:

```text
ModuleNotFoundError: No module named 'matplotlib'
```

**কারণ:**

- Package install করা নেই।
- ভুল environment selected আছে।
- Notebook-এর kernel অন্য Python interpreter ব্যবহার করছে।

**সমাধান:**

প্রথমে Notebook-এর kernel যাচাই করো।

প্রয়োজনে সেই environment-এর Terminal-এ:

```bash
python -m pip install matplotlib
```

তারপর cell আবার execute করো।

### Error 2: Kernel Not Found

**কারণ:**

- Python environment মুছে ফেলা হয়েছে।
- VS Code environment শনাক্ত করতে পারছে না।
- উপযুক্ত Jupyter kernel উপলভ্য নেই।

**সমাধান:**

1. Python installation যাচাই করো।
2. Project-এর virtual environment তৈরি বা activate করো।
3. VS Code-এ সঠিক interpreter নির্বাচন করো।
4. Notebook-এর kernel selector থেকে উপযুক্ত kernel নির্বাচন করো।

### Error 3: `NameError`

উদাহরণ:

```python
print(total)
```

কিন্তু `total` variable define করা হয়নি।

**সমাধান:** যে cell-এ variable তৈরি করা হয়েছে, সেটি execute করো অথবা variable-টি সঠিকভাবে define করো।

### Error 4: Jupyter Command Not Found

**কারণ:**

- Jupyter install করা নেই।
- ভুল environment active আছে।
- Command সঠিকভাবে resolve হচ্ছে না।

**সমাধান:**

```bash
python -m pip show notebook
```

প্রয়োজন হলে সঠিক environment-এ:

```bash
python -m pip install notebook
```

তারপর:

```bash
python -m notebook
```

### Error 5: Notebook Opens but Code Does Not Run

**সম্ভাব্য কারণ:**

- Kernel চালু হয়নি।
- Kernel busy আছে।
- Python environment-এ সমস্যা আছে।
- Code-এ error হয়েছে।

**সমাধান:**

- Kernel status পরীক্ষা করো।
- Error message পড়ো।
- প্রয়োজনে kernel restart করো।
- সঠিক interpreter নির্বাচন করে আবার চেষ্টা করো।

### Error 6: Changes Are Not Saved

**কারণ:** Notebook file save হয়নি।

**সমাধান:** Save command ব্যবহার করো এবং file-এর saved status যাচাই করো।

---

## 18. Best Practices

1. Notebook-এর অর্থপূর্ণ নাম দাও।
2. Code ও explanation আলাদা cell-এ রাখো।
3. প্রতিটি cell-এর কাজ পরিষ্কার রাখো।
4. অপ্রয়োজনীয় variable ও state dependency কমাও।
5. গুরুত্বপূর্ণ notebook fresh kernel-এ execute করে যাচাই করো।
6. সঠিক Python kernel নির্বাচন করো।
7. Notebook নিয়মিত save করো।
8. Sensitive information notebook-এ রেখে share করো না।
9. `.venv` repository-তে upload না করে dependency file রাখো।
10. বড় project-এর reusable code `.py` module-এ organize করো।
11. Notebook-এ ব্যবহৃত external package document করো।
12. Code পরিবর্তন করার পরে output আবার execute করে যাচাই করো।

---

## 19. Practical Exercises

### Exercise 1: Create a Notebook

`PythonBasics.ipynb` নামে একটি notebook তৈরি করো।

### Exercise 2: Create a Markdown Cell

একটি heading এবং Python সম্পর্কে ছোট explanation লেখো।

### Exercise 3: Run a Code Cell

```python
print("My first Jupyter Notebook")
```

### Exercise 4: Use Variables

```python
name = "Masum"
age = 22

print(name)
print(age)
```

এখানে `age`-এর value নিজের প্রয়োজন অনুযায়ী পরিবর্তন করতে পারো।

### Exercise 5: Use Multiple Cells

প্রথম cell:

```python
x = 100
```

দ্বিতীয় cell:

```python
y = 200
```

তৃতীয় cell:

```python
print(x + y)
```

Output যাচাই করো।

### Exercise 6: Practice Execution Order

প্রথমে এমন একটি cell চালাও, যেখানে একটি variable define করা হয়নি। Error পর্যবেক্ষণ করো।

তারপর variable define করে cell-টি আবার চালাও।

### Exercise 7: Use Markdown Formatting

Markdown Cell-এ heading, bold text, list এবং inline code লেখো।

### Exercise 8: Install and Use a Package

Virtual environment-এ `requests` install করো:

```bash
python -m pip install requests
```

Notebook-এর Code Cell-এ লেখো:

```python
import requests

print(requests.__version__)
```

### Exercise 9: Restart the Kernel

একটি variable তৈরি করো, kernel restart করো এবং variable আবার ব্যবহার করার চেষ্টা করো।

কেন error হয়েছে, তা ব্যাখ্যা করো।

### Exercise 10: Save and Review

Notebook save করো। সব cell উপর থেকে নিচে execute করে দেখো এবং অপ্রয়োজনীয় output থাকলে পরিষ্কার করো।

---

## 20. Quick Revision

| Term | Meaning |
|---|---|
| Jupyter Notebook | Code, text ও output একসঙ্গে রাখার interactive environment |
| `.ipynb` | Notebook file extension |
| Cell | Notebook-এর একটি পৃথক content section |
| Code Cell | Python code লেখা ও execute করার cell |
| Markdown Cell | Formatted explanation লেখার cell |
| Kernel | Notebook code execute করে ও runtime state ধরে রাখে |
| `Shift + Enter` | সাধারণত cell execute করে পরের cell-এ যায় |
| `python -m notebook` | Installed Notebook package চালু করে |
| Restart Kernel | Runtime state reset করে |
| `requirements.txt` | Project dependency document করে |

---

## 21. Chapter Connection

এই topic-এ আমরা Jupyter Notebook, `.ipynb` file, Code Cell, Markdown Cell, Kernel এবং VS Code-এ Notebook ব্যবহার করার প্রাথমিক পদ্ধতি শিখেছি।

এখন তুমি একটি notebook তৈরি করে Python code execute করতে, output দেখতে এবং code-এর সঙ্গে explanation সংরক্ষণ করতে পারবে।

**Next Topic:** [23. Setting Up Git and GitHub](23_Setting_Up_Git_and_GitHub.md)

পরবর্তী topic-এ আমরা Git ও GitHub-এর পরিচিতি, installation, configuration এবং Python project-এর version control setup করা শিখব।