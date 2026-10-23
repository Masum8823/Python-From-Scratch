# 17. Using the Python REPL

## 1. Introduction

Python শেখার সময় প্রতিটি ছোট code পরীক্ষা করার জন্য আলাদা `.py` file তৈরি করা সব সময় প্রয়োজন হয় না। অনেক সময় সরাসরি Python interpreter-এ code লিখে সঙ্গে সঙ্গে result দেখা যায়।

এই interactive environment-কে বলা হয় **Python REPL**।

REPL ব্যবহার করে তুমি:

- ছোট Python statement পরীক্ষা করতে পারবে।
- Mathematical calculation করতে পারবে।
- Variable তৈরি ও ব্যবহার করতে পারবে।
- String ও data type পরীক্ষা করতে পারবে।
- Function-এর result দেখতে পারবে।
- নতুন Python concept দ্রুত practice করতে পারবে।

এই topic-এর লক্ষ্য হলো Python REPL কীভাবে ব্যবহার করতে হয়, তা ভালোভাবে শেখা।

---

## 2. What Is Python REPL?

REPL-এর পূর্ণরূপ হলো:

**Read-Eval-Print Loop**

এর চারটি অংশ রয়েছে:

| Part | Meaning | কাজ |
|---|---|---|
| Read | Input পড়া | তোমার লেখা code গ্রহণ করে |
| Eval | Evaluate | Code বা expression evaluate করে |
| Print | Result প্রদর্শন | Expression-এর result দেখায় |
| Loop | পুনরাবৃত্তি | পরবর্তী input-এর জন্য অপেক্ষা করে |

সহজভাবে বললে, REPL-এ তুমি code লেখো, Python সেটি process করে এবং result দেখায়। এরপর তুমি আবার নতুন code লিখতে পারো।

### Example

REPL-এ লিখো:

```python
10 + 20
```

Result:

```text
30
```

এবার লিখো:

```python
5 * 6
```

Result:

```text
30
```

এখানে প্রতিটি expression আলাদাভাবে evaluate করা হয়েছে।

---

## 3. How to Open the Python REPL

Python REPL চালু করতে প্রথমে Terminal বা Command Prompt open করতে হবে।

### Windows

PowerShell বা VS Code Terminal-এ লেখো:

```powershell
python
```

যদি command কাজ না করে, চেষ্টা করো:

```powershell
py
```

### macOS and Linux

Terminal-এ লেখো:

```bash
python3
```

Python interpreter সঠিকভাবে চালু হলে সাধারণত নিচের মতো prompt দেখা যাবে:

```text
>>>
```

এই `>>>` চিহ্নটি Python interactive prompt।

এখন তুমি সরাসরি Python code লিখতে পারবে।

### Example

```python
>>> print("Hello, Python!")
Hello, Python!
```

এখানে:

- `>>>` হলো REPL prompt।
- `print("Hello, Python!")` হলো তোমার input।
- `Hello, Python!` হলো output।

**মনে রাখবে:** `>>>` prompt নিজে code-এর অংশ নয়। এটি Python interpreter input নেওয়ার জন্য দেখায়।

---

## 4. Writing Your First REPL Commands

REPL চালু করার পর ছোট expression দিয়ে শুরু করো।

### Example 1: Addition

```python
>>> 10 + 20
30
```

### Example 2: Subtraction

```python
>>> 50 - 15
35
```

### Example 3: Multiplication

```python
>>> 6 * 7
42
```

### Example 4: Division

```python
>>> 100 / 4
25.0
```

Python-এ সাধারণ `/` division operator-এর result এখানে `25.0` হিসেবে দেখানো হয়েছে।

### Example 5: Print Function

```python
>>> print("Learning Python")
Learning Python
```

এখানে `print()` function text-টি output-এ দেখিয়েছে।

### Important Difference

REPL-এ সরাসরি expression লিখলে তার result সাধারণত প্রদর্শিত হয়:

```python
>>> 10 + 20
30
```

কিন্তু `.py` file-এ শুধু নিচের code লিখলে result সাধারণভাবে নিজে থেকে output-এ দেখা যাবে না:

```python
10 + 20
```

File-এ result দেখতে চাইলে লিখতে পারো:

```python
print(10 + 20)
```

**মূল পার্থক্য:** REPL expression-এর result দেখাতে পারে, কিন্তু সাধারণ Python script-এ result দেখানোর জন্য প্রায়ই `print()` ব্যবহার করতে হয়।

---

## 5. Using Variables in the REPL

Variable হলো একটি নাম, যার মাধ্যমে কোনো value-কে reference করা যায়।

REPL-এ variable তৈরি করে সঙ্গে সঙ্গে ব্যবহার করা যায়।

### Example

```python
>>> name = "Masum"
>>> name
'Masum'
```

এখানে:

- `name` হলো variable-এর নাম।
- `"Masum"` হলো value।
- `name` লিখলে REPL value-টি প্রদর্শন করে।

### Working with Numbers

```python
>>> age = 22
>>> age
22
```

এবার:

```python
>>> age + 5
27
```

Python `age`-এর value-এর সঙ্গে `5` যোগ করেছে।

### Updating a Variable

```python
>>> score = 80
>>> score
80
```

এবার:

```python
>>> score = 95
>>> score
95
```

Variable-এ নতুন value assign করায় এখন `score`-এর value `95`।

### Using Multiple Variables

```python
>>> first_number = 10
>>> second_number = 20
>>> first_number + second_number
30
```

REPL-এ variable ব্যবহার করলে ছোট calculation ও logic দ্রুত পরীক্ষা করা যায়।

---

## 6. Understanding the Underscore Variable `_`

Python-এর standard interactive interpreter-এ `_` অনেক সময় সর্বশেষ সফলভাবে প্রদর্শিত expression-এর result ধরে রাখে।

উদাহরণ:

```python
>>> 10 + 20
30
>>> _
30
```

আবার:

```python
>>> _ * 2
60
```

এখানে `_` সর্বশেষ expression result `30` ব্যবহার করেছে।

**সতর্কতা:** এটি Python-এর standard REPL-এর একটি সুবিধা। অন্য interactive environment-এ এর আচরণ আলাদা হতে পারে। নিজের code-এ `_`-কে সাধারণ variable হিসেবেও ব্যবহার করা যায়, তাই এর অর্থ সব পরিস্থিতিতে একই নয়।

---

## 7. Working with Strings in the REPL

String হলো text উপস্থাপনের জন্য ব্যবহৃত data type।

REPL-এ string তৈরি ও পরীক্ষা করা খুব সহজ।

### Example 1: Create a String

```python
>>> message = "Hello, Python"
>>> message
'Hello, Python'
```

### Example 2: Join Strings

```python
>>> first_name = "Abdulla"
>>> last_name = "Masum"
>>> first_name + " " + last_name
'Abdulla Masum'
```

এখানে `+` operator দুটি string এবং একটি space যুক্ত করেছে।

### Example 3: Check String Length

```python
>>> len("Python")
6
```

`len()` হলো built-in function, যা এখানে string-এর character সংখ্যা return করেছে।

### Example 4: Convert to Uppercase

```python
>>> "python".upper()
'PYTHON'
```

`.upper()` string-এর অক্ষরগুলো uppercase করে একটি নতুন string return করে।

String নিয়ে আরও বিস্তারিত আমরা পরবর্তী chapter-এ শিখব।

---

## 8. Checking Data Types in the REPL

Python-এ value-এর data type জানার জন্য `type()` function ব্যবহার করা যায়।

### Example

```python
>>> type(100)
<class 'int'>
```

এখানে `int` হলো integer data type।

আরও কিছু উদাহরণ:

```python
>>> type(3.14)
<class 'float'>
```

```python
>>> type("Hello")
<class 'str'>
```

```python
>>> type(True)
<class 'bool'>
```

এখানে:

| Value | Data Type |
|---|---|
| `100` | `int` |
| `3.14` | `float` |
| `"Hello"` | `str` |
| `True` | `bool` |

REPL-এ `type()` ব্যবহার করে নতুন কোনো value-এর data type দ্রুত পরীক্ষা করতে পারবে।

---

## 9. Using Built-in Functions

Python-এর অনেক built-in function REPL-এ সরাসরি ব্যবহার করা যায়।

### Example 1: `len()`

```python
>>> len("Programming")
11
```

### Example 2: `max()`

```python
>>> max(10, 25, 15)
25
```

### Example 3: `min()`

```python
>>> min(10, 25, 15)
10
```

### Example 4: `sum()`

```python
>>> sum([10, 20, 30])
60
```

### Example 5: `round()`

```python
>>> round(3.14159, 2)
3.14
```

এখানে `round()` সংখ্যাটিকে দুই decimal place পর্যন্ত round করেছে।

এগুলো REPL-এ পরীক্ষা করে built-in function-এর behavior বোঝা সহজ।

---

## 10. Using Multiline Code in the REPL

কিছু Python statement একাধিক line নিয়ে গঠিত হয়।

যেমন:

- `if` statement
- `for` loop
- `while` loop
- Function definition
- Class definition

REPL-এ এই ধরনের code লেখার সময় continuation prompt দেখা যেতে পারে:

```text
...
```

এটি বোঝায় যে Python আরও input আশা করছে।

### Example: An `if` Statement

```python
>>> age = 20
>>> if age >= 18:
...     print("Adult")
...
Adult
```

এখানে:

1. `age = 20` variable তৈরি করেছে।
2. `if age >= 18:` condition পরীক্ষা করছে।
3. পরের line-এ indentation দিয়ে block-এর code লেখা হয়েছে।
4. অতিরিক্ত blank line দিয়ে block শেষ করা হয়েছে।
5. Condition সত্য হওয়ায় `Adult` output এসেছে।

### Example: A `for` Loop

```python
>>> for number in range(3):
...     print(number)
...
0
1
2
```

এই উদাহরণে loop-এর বিস্তারিত এখনই মুখস্থ করার প্রয়োজন নেই। আপাতত বুঝবে, REPL-এ multiline block-ও লেখা যায়।

---

## 11. Handling Errors in the REPL

Code-এ ভুল হলে Python error message দেখায়।

### Example 1: NameError

```python
>>> print(username)
```

যদি `username` নামে কোনো variable আগে তৈরি করা না থাকে, তাহলে `NameError` হতে পারে।

উদাহরণ:

```text
NameError: name 'username' is not defined
```

সমাধান:

```python
>>> username = "Masum"
>>> print(username)
Masum
```

### Example 2: SyntaxError

ভুল code:

```python
>>> print("Hello"
```

এখানে closing parenthesis অনুপস্থিত। তাই `SyntaxError` হতে পারে।

সঠিক code:

```python
>>> print("Hello")
Hello
```

### Example 3: TypeError

```python
>>> "Age: " + 22
```

এখানে string-এর সঙ্গে integer সরাসরি `+` দিয়ে যোগ করতে গেলে `TypeError` হতে পারে।

সঠিক পদ্ধতি:

```python
>>> "Age: " + str(22)
'Age: 22'
```

এখানে `str()` integer-কে string-এ রূপান্তর করেছে।

**মনে রাখবে:** REPL-এ error হওয়া মানে session নষ্ট হয়ে গেছে, এমন নয়। বেশিরভাগ ক্ষেত্রে পরবর্তী input দিয়ে আবার কাজ করা যায়।

---

## 12. The Difference Between REPL and Python Files

REPL ও `.py` file—দুটিই Python code চালানোর জন্য ব্যবহার করা হয়, কিন্তু ব্যবহারের ধরন আলাদা।

| Feature | Python REPL | Python File |
|---|---|---|
| Code লেখা | সরাসরি prompt-এ | Editor-এ file-এর মধ্যে |
| Result দেখা | Expression-এর result সাধারণত সঙ্গে সঙ্গে দেখা যায় | Output দেখতে প্রায়ই `print()` দরকার |
| Code সংরক্ষণ | সাধারণত আলাদাভাবে save হয় না | `.py` file-এ save করা যায় |
| ছোট পরীক্ষা | খুব সুবিধাজনক | File তৈরি করতে হয় |
| বড় program | পরিচালনা করা অসুবিধাজনক | বেশি উপযোগী |
| বারবার চালানো | Input পুনরায় দিতে হতে পারে | File আবার run করা যায় |
| Multiline code | সম্ভব | সহজে manage করা যায় |

### Example: REPL

```python
>>> 10 + 20
30
```

### Example: Python File

`main.py`:

```python
10 + 20
```

সাধারণ script হিসেবে চালালে result নিজে থেকে display হবে না।

কিন্তু:

```python
print(10 + 20)
```

Output:

```text
30
```

তাই ছোট experiment-এর জন্য REPL এবং সংরক্ষণযোগ্য program-এর জন্য Python file ব্যবহার করতে পারো।

---

## 13. Exiting the Python REPL

REPL-এর কাজ শেষ হলে interactive session থেকে বের হওয়া যায়।

### Method 1: Using `exit()`

```python
>>> exit()
```

### Method 2: Using `quit()`

```python
>>> quit()
```

এগুলো interactive session থেকে বের হওয়ার সহজ উপায়।

### Method 3: Keyboard Shortcut

- Windows-এর কিছু console-এ `Ctrl + Z`, তারপর `Enter`।
- macOS/Linux Terminal-এ সাধারণত `Ctrl + D`।

তুমি যদি VS Code Terminal-এ থাকো, REPL থেকে বের হওয়ার পরে আবার সাধারণ shell prompt দেখতে পাবে।

উদাহরণ:

```text
>>> exit()
PS C:\Users\Student\Python_Project>
```

এখন তুমি আবার Terminal command চালাতে পারবে।

---

## 14. Common REPL Problems and Solutions

| Problem | Possible Cause | Solution |
|---|---|---|
| `>>>` দেখা যাচ্ছে না | REPL চালু হয়নি | `python`, `py` বা `python3` চালাও |
| `SyntaxError` | Code-এর syntax ভুল | Parentheses, quotes ও syntax যাচাই করো |
| `NameError` | Variable বা name সংজ্ঞায়িত নেই | আগে variable তৈরি করো বা সঠিক নাম ব্যবহার করো |
| `IndentationError` | Block-এর indentation ভুল | সঠিক indentation ব্যবহার করো |
| `...` prompt-এ আটকে আছ | Multiline statement শেষ হয়নি | Block সম্পূর্ণ করো; প্রয়োজনে `Ctrl + C` চাপো |
| `exit()` কাজ করছে না | REPL-এর বাইরে আছ বা command অন্যভাবে লেখা হয়েছে | Prompt যাচাই করো |
| Variable পাওয়া যাচ্ছে না | নতুন session শুরু হয়েছে বা variable তৈরি করা হয়নি | Variable আবার তৈরি করো |

### Useful Tip

REPL-এ একবারে খুব বেশি code লেখার পরিবর্তে ছোট ছোট expression দিয়ে পরীক্ষা করো। এতে ভুল খুঁজে বের করা সহজ হয়।

---

## 15. Practical Exercises

### Exercise 1: Basic Calculation

REPL চালু করে নিচের expression-গুলো পরীক্ষা করো:

```python
10 + 20
50 - 15
6 * 7
100 / 4
```

প্রতিটি result আগে অনুমান করো, তারপর যাচাই করো।

### Exercise 2: Create Variables

```python
name = "Masum"
age = 22
```

এরপর আলাদাভাবে লেখো:

```python
name
age
```

নিজের তৈরি variable-এর value দেখো।

### Exercise 3: Check Data Types

```python
type(100)
type(3.14)
type("Python")
type(False)
```

প্রতিটি value-এর data type শনাক্ত করো।

### Exercise 4: Use Built-in Functions

```python
len("Python")
max(10, 20, 30)
min(10, 20, 30)
sum([5, 10, 15])
```

প্রতিটি function কী result দেয়, তা বোঝার চেষ্টা করো।

### Exercise 5: Test String Operations

```python
"Hello" + " " + "World"
"python".upper()
len("Programming")
```

Output নিজে অনুমান করে যাচাই করো।

### Exercise 6: Fix the Error

নিচের code-এ সমস্যা কী?

```python
>>> total = 100
>>> print(totla)
```

সঠিক variable name ব্যবহার করে error ঠিক করো।

### Exercise 7: REPL vs File

প্রথমে REPL-এ চালাও:

```python
10 + 20
```

তারপর `main.py` file-এ একই code লিখে run করো। এরপর `print(10 + 20)` লিখে আবার run করো।

দুই পদ্ধতির পার্থক্য নিজের ভাষায় ব্যাখ্যা করো।

---

## 16. Best Practices

1. REPL ব্যবহার করে ছোট expression পরীক্ষা করো।
2. নতুন function বা method শেখার সময় REPL-এ experiment করো।
3. Variable-এর value ও data type যাচাই করতে REPL ব্যবহার করো।
4. বড় program-এর জন্য `.py` file ব্যবহার করো।
5. Error message পড়ে ভুলের কারণ বোঝার চেষ্টা করো।
6. Multiline block লেখার সময় indentation ঠিক রাখো।
7. গুরুত্বপূর্ণ code REPL-এ লিখে রেখে না দিয়ে Python file-এ save করো।
8. REPL-এর `>>>` ও `...` prompt-কে code-এর অংশ মনে কোরো না।
9. Interactive session বন্ধ করলে variable-এর state সাধারণত হারিয়ে যায়—এটি মনে রাখো।
10. নিজের code ছোট ছোট অংশে পরীক্ষা করার অভ্যাস গড়ে তোলো।

---

## 17. Quick Revision

| Question | Answer |
|---|---|
| REPL-এর পূর্ণরূপ কী? | Read-Eval-Print Loop |
| REPL কী? | Python-এর interactive environment |
| `>>>` কী নির্দেশ করে? | নতুন input-এর জন্য Python prompt |
| `...` কী নির্দেশ করে? | সাধারণত multiline input চলমান আছে |
| REPL-এ `10 + 20` লিখলে কী হয়? | সাধারণত `30` প্রদর্শিত হয় |
| `type()` কী করে? | কোনো object-এর type জানায় |
| `len()` কী করে? | কোনো object-এর length জানায় |
| `exit()` কী করে? | REPL থেকে বের হয় |
| REPL-এর প্রধান সুবিধা কী? | দ্রুত code পরীক্ষা করা |
| বড় program কোথায় রাখা ভালো? | `.py` source file-এ |

---

## 18. Chapter Connection

এই topic-এ আমরা Python REPL চালু করা, expression পরীক্ষা, variable ব্যবহার, data type যাচাই, multiline code লেখা এবং interactive session থেকে বের হওয়া শিখেছি।

এখন তুমি ছোট Python code দ্রুত পরীক্ষা করতে পারবে এবং REPL ও Python file-এর পার্থক্য বুঝতে পারবে।

**Next Topic:** [18. Installing and Using pip](18_Installing_and_Using_pip.md)