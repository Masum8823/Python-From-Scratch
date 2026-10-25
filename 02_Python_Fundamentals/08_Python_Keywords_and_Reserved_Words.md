# 08. Python Keywords and Reserved Words

## 1. Introduction to Python Keywords

**Keywords** হলো Python-এর কিছু নির্দিষ্ট শব্দ, যেগুলোর নিজস্ব বিশেষ অর্থ ও কাজ রয়েছে। Python language-এর syntax এবং program-এর structure তৈরি করতে এগুলো ব্যবহৃত হয়।

উদাহরণ:

```python
if age >= 18:
    print("Adult")
else:
    print("Minor")
```

এখানে `if` এবং `else` হলো Python keywords।

এগুলো condition অনুযায়ী program-এর কোন অংশ execute হবে, তা নির্ধারণ করে।

Python keywords-এর নিজস্ব অর্থ থাকায় এগুলোকে সাধারণ variable name, function name বা class name হিসেবে ব্যবহার করা যায় না।

## 2. Why Are Keywords Important?

Python keywords গুরুত্বপূর্ণ, কারণ এগুলো language-এর basic structure তৈরি করে।

Keywords ব্যবহার করে আমরা:

- Condition পরীক্ষা করতে পারি।
- Loop চালাতে পারি।
- Function ও class তৈরি করতে পারি।
- Module import করতে পারি।
- Exception handle করতে পারি।
- Logical operations করতে পারি।
- Function থেকে value return করতে পারি।

উদাহরণ:

```python
def check_age(age):
    if age >= 18:
        return "Adult"
    else:
        return "Minor"

print(check_age(20))
```

Output:

```text
Adult
```

এখানে `def`, `if`, `return` এবং `else` keywords।

## 3. Python Keywords List

Python-এর keyword list version অনুযায়ী পরিবর্তিত হতে পারে। নিচে Python 3-এর বহুল ব্যবহৃত এবং আধুনিক versions-এ থাকা standard keywords-এর তালিকা দেওয়া হলো।

| Keyword | কাজ |
|---|---|
| `False` | Boolean false value |
| `None` | কোনো value নেই বা অনুপস্থিত বোঝায় |
| `True` | Boolean true value |
| `and` | Logical AND operation |
| `as` | Alias নির্ধারণ বা exception binding |
| `assert` | কোনো condition সত্য কি না যাচাই |
| `async` | Asynchronous function বা context তৈরি |
| `await` | Awaitable operation-এর ফলের জন্য অপেক্ষা |
| `break` | Loop বন্ধ করে বের হওয়া |
| `class` | Class তৈরি করা |
| `continue` | Loop-এর বর্তমান iteration বাদ দিয়ে পরেরটিতে যাওয়া |
| `def` | Function তৈরি করা |
| `del` | Reference বা container-এর item মুছে ফেলা |
| `elif` | অতিরিক্ত condition পরীক্ষা |
| `else` | বিকল্প block নির্ধারণ |
| `except` | Exception handle করা |
| `finally` | Exception handling-এর শেষে cleanup block চালানো |
| `for` | Sequence বা iterable-এর ওপর iteration |
| `from` | Module থেকে নির্দিষ্ট item import করা |
| `global` | Function-এর ভেতর থেকে global variable-কে refer করা |
| `if` | Condition পরীক্ষা করা |
| `import` | Module import করা |
| `in` | Membership পরীক্ষা বা loop-এ iteration |
| `is` | Object identity পরীক্ষা |
| `lambda` | ছোট anonymous function তৈরি |
| `nonlocal` | Enclosing function scope-এর variable ব্যবহার করা |
| `not` | Logical NOT operation |
| `or` | Logical OR operation |
| `pass` | কোনো কাজ না করে placeholder হিসেবে থাকা |
| `raise` | Exception তৈরি বা raise করা |
| `return` | Function থেকে value ফেরত দেওয়া |
| `try` | Exception handling শুরু করা |
| `while` | Condition সত্য থাকা পর্যন্ত loop চালানো |
| `with` | Context manager ব্যবহার করা |
| `yield` | Generator থেকে value produce করা |

**Note:** Python version অনুযায়ী keyword list যাচাই করার সবচেয়ে নির্ভরযোগ্য উপায় হলো Python-এর `keyword` module ব্যবহার করা।

## 4. Types of Keywords

বিষয়টি সহজে বোঝার জন্য keywords-গুলোকে কাজ অনুযায়ী কয়েকটি group-এ ভাগ করা যায়। এই grouping শেখার সুবিধার জন্য; Python-এর আনুষ্ঠানিক classification নয়।

### 4.1 Conditional Keywords

| Keyword | কাজ |
|---|---|
| `if` | Condition পরীক্ষা |
| `elif` | অন্য condition পরীক্ষা |
| `else` | বিকল্প block |

উদাহরণ:

```python
marks = 85

if marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
else:
    print("Below A")
```

Output:

```text
A+
```

### 4.2 Loop Control Keywords

| Keyword | কাজ |
|---|---|
| `for` | Iterable-এর ওপর iteration |
| `while` | Condition-ভিত্তিক loop |
| `break` | Loop বন্ধ করা |
| `continue` | বর্তমান iteration বাদ দেওয়া |

উদাহরণ:

```python
for number in range(5):
    if number == 3:
        break
    print(number)
```

Output:

```text
0
1
2
```

### 4.3 Function-Related Keywords

| Keyword | কাজ |
|---|---|
| `def` | Function তৈরি |
| `return` | Value ফেরত দেওয়া |
| `lambda` | Anonymous function তৈরি |
| `yield` | Generator থেকে value দেওয়া |

উদাহরণ:

```python
def add(a, b):
    return a + b

print(add(5, 3))
```

Output:

```text
8
```

### 4.4 Logical Keywords

| Keyword | কাজ |
|---|---|
| `and` | সব condition সত্য হলে `True` |
| `or` | অন্তত একটি condition সত্য হলে `True` |
| `not` | Logical result উল্টে দেয় |

উদাহরণ:

```python
age = 20

print(age >= 18 and age <= 60)
print(age < 18 or age > 60)
print(not age >= 18)
```

Output:

```text
True
False
False
```

### 4.5 Exception Handling Keywords

| Keyword | কাজ |
|---|---|
| `try` | Error হতে পারে এমন code পরীক্ষা |
| `except` | Exception handle করা |
| `finally` | শেষের cleanup block |
| `raise` | Exception raise করা |
| `assert` | Condition যাচাই করা |

উদাহরণ:

```python
try:
    number = int("abc")
except ValueError:
    print("Invalid number")
finally:
    print("Program finished")
```

Output:

```text
Invalid number
Program finished
```

### 4.6 Class and Scope Keywords

| Keyword | কাজ |
|---|---|
| `class` | Class তৈরি |
| `global` | Global variable refer করা |
| `nonlocal` | Enclosing function-এর variable refer করা |
| `del` | Reference বা item মুছে ফেলা |
| `pass` | Empty block-এর placeholder |

### 4.7 Other Important Keywords

| Keyword | কাজ |
|---|---|
| `import` | Module import |
| `from` | নির্দিষ্ট module item import |
| `as` | Alias নির্ধারণ |
| `in` | Membership পরীক্ষা |
| `is` | Object identity পরীক্ষা |
| `with` | Context manager ব্যবহার |
| `async` | Asynchronous definition |
| `await` | Awaitable operation-এর জন্য অপেক্ষা |

## 5. How to Check Python Keywords

Python-এর `keyword` module ব্যবহার করে current interpreter-এর keyword list দেখা যায়।

```python
import keyword

print(keyword.kwlist)
```

এই code বর্তমান Python version-এর standard keywords-এর list দেখাবে।

### Check Whether a Word Is a Keyword

```python
import keyword

print(keyword.iskeyword("if"))
print(keyword.iskeyword("for"))
print(keyword.iskeyword("hello"))
```

Output:

```text
True
True
False
```

এখানে:

- `"if"` একটি keyword।
- `"for"` একটি keyword।
- `"hello"` keyword নয়।

`keyword.iskeyword()` একটি word keyword কি না, তা যাচাই করে।

## 6. What Are Soft Keywords?

কিছু Python শব্দ নির্দিষ্ট context-এ বিশেষ অর্থ বহন করে, কিন্তু সব জায়গায় reserved keyword নয়। এগুলোকে **soft keywords** বলা হয়।

উদাহরণ:

- `match`
- `case`
- `type`
- `_`

কোন শব্দ soft keyword হিসেবে ব্যবহৃত হবে, তা Python version এবং syntax context-এর ওপর নির্ভর করে।

### Example: `match` and `case`

```python
command = "start"

match command:
    case "start":
        print("Starting")
    case "stop":
        print("Stopping")
    case _:
        print("Unknown command")
```

Output:

```text
Starting
```

এখানে `match` এবং `case` pattern matching syntax-এর অংশ। `_` default case হিসেবে কাজ করছে।

**মনে রাখবে:** Soft keyword সব context-এ সাধারণ keyword-এর মতো নিষিদ্ধ নয়। প্রয়োজন হলে current version-এর `keyword.softkwlist` দিয়ে এগুলো দেখা যায়।

```python
import keyword

print(keyword.softkwlist)
```

## 7. What Are Reserved Words?

**Reserved words** বলতে সাধারণত এমন শব্দ বোঝায়, যেগুলো programming language বিশেষ অর্থে সংরক্ষণ করে রেখেছে এবং সাধারণ identifier হিসেবে ব্যবহার করতে দেয় না।

Python-এর standard keywords reserved words-এর অন্তর্ভুক্ত।

উদাহরণ:

```python
if = 10
```

এই code invalid, কারণ `if` একটি keyword।

সঠিক:

```python
if_value = 10
print(if_value)
```

Output:

```text
10
```

এখানে `if_value` valid identifier, কারণ পুরো নামটি `if` keyword-এর সঙ্গে এক নয়।

## 8. Keywords vs Identifiers

**Identifier** হলো variable, function, class বা অন্য কোনো named object-এর জন্য দেওয়া নাম।

উদাহরণ:

```python
student_name = "Masum"
age = 22

def greet():
    print("Hello")
```

এখানে:

- `student_name` — identifier
- `age` — identifier
- `greet` — identifier
- `def` — keyword

### Difference Between Keywords and Identifiers

| Keywords | Identifiers |
|---|---|
| Python-এর predefined special words | Programmer-এর দেওয়া নাম |
| নির্দিষ্ট syntax বা কাজের অর্থ রয়েছে | Variable, function, class ইত্যাদি শনাক্ত করে |
| সাধারণভাবে identifier হিসেবে ব্যবহার করা যায় না | Naming rules মেনে নিজের নাম দেওয়া যায় |
| Example: `if`, `for`, `class` | Example: `age`, `student_name`, `calculate` |

## 9. Why Can't We Use Keywords as Variable Names?

Python keywords-এর নির্দিষ্ট syntax-related অর্থ রয়েছে। এগুলো variable name হিসেবে ব্যবহার করলে Python code-এর অর্থ বুঝতে সমস্যা হবে।

ভুল:

```python
class = "CSE"
```

এখানে `class` একটি keyword, তাই SyntaxError হবে।

সঠিক:

```python
department = "CSE"
print(department)
```

Output:

```text
CSE
```

আরেকটি ভুল উদাহরণ:

```python
for = 10
```

সঠিক:

```python
for_count = 10
print(for_count)
```

Output:

```text
10
```

**Rule:** Keyword-এর সঙ্গে অতিরিক্ত অক্ষর যোগ করে নতুন identifier তৈরি করা যায়, যদি সেটি identifier naming rules মেনে চলে।

## 10. Keywords Are Case-Sensitive

Python case-sensitive। তাই uppercase এবং lowercase অক্ষর আলাদা হিসেবে বিবেচিত হয়।

উদাহরণ:

```python
if True:
    print("Correct")
```

Output:

```text
Correct
```

কিন্তু:

```python
IF True:
    print("Incorrect")
```

এটি invalid, কারণ `IF` Python-এর `if` keyword নয়।

একইভাবে:

- `True` হলো keyword।
- `true` keyword নয়।
- `False` হলো keyword।
- `false` keyword নয়।
- `None` হলো keyword।
- `none` keyword নয়।

তবে `true`, `false` এবং `none` lowercase নামগুলো keyword নয় বলে ব্যবহার করা technically সম্ভব। কিন্তু এগুলো এভাবে variable হিসেবে ব্যবহার না করাই ভালো, কারণ এতে confusion হতে পারে।

## 11. Common Beginner Mistakes

### Mistake 1: Using a Keyword as a Variable

ভুল:

```python
if = 5
```

সঠিক:

```python
if_number = 5
```

### Mistake 2: Using the Wrong Case

ভুল:

```python
If age >= 18:
    print("Adult")
```

সঠিক:

```python
if age >= 18:
    print("Adult")
```

### Mistake 3: Thinking Every Special-Looking Word Is a Keyword

উদাহরণ:

```python
name = "Masum"
print(name)
```

এখানে `name` এবং `print` একই ধরনের identifier নয়। `name` হলো variable name, আর `print` হলো Python-এর built-in function-এর নাম।

`print` standard keyword নয়, যদিও এটি Python-এর গুরুত্বপূর্ণ built-in function।

### Mistake 4: Confusing Keywords with Built-in Functions

| Keyword | Built-in Function |
|---|---|
| `if` | `print()` |
| `for` | `len()` |
| `def` | `input()` |
| `class` | `type()` |
| `return` | `range()` |

Keywords language syntax-এর অংশ। Built-in functions Python-এ আগে থেকেই পাওয়া যায়, কিন্তু তারা keyword নয়।

## 12. Practical Examples

### Example 1: Using Conditional Keywords

```python
marks = 75

if marks >= 80:
    grade = "A+"
elif marks >= 70:
    grade = "A"
else:
    grade = "Below A"

print(grade)
```

Output:

```text
A
```

### Example 2: Using Loop Keywords

```python
for number in range(1, 6):
    if number == 4:
        continue
    print(number)
```

Output:

```text
1
2
3
5
```

এখানে `continue` বর্তমান iteration বাদ দিয়ে পরের iteration-এ চলে যায়।

### Example 3: Checking a Keyword

```python
import keyword

word = "while"

if keyword.iskeyword(word):
    print("It is a Python keyword")
else:
    print("It is not a Python keyword")
```

Output:

```text
It is a Python keyword
```

## 13. Practice Exercises

### Exercise 1: Identify the Keywords

নিচের code-এ ব্যবহৃত keywords চিহ্নিত করো।

```python
def check_number(number):
    if number > 0:
        return True
    else:
        return False
```

### Exercise 2: Find the Errors

নিচের code-এ কোন keyword ভুলভাবে ব্যবহার করা হয়েছে?

```python
if = 10
for = 20
class = 30
```

প্রতিটি variable-এর জন্য valid identifier তৈরি করো।

### Exercise 3: Check Keywords Using Python

`keyword` module ব্যবহার করে নিচের শব্দগুলো keyword কি না যাচাই করো:

- `if`
- `while`
- `hello`
- `return`
- `student`

### Exercise 4: Keyword or Identifier?

প্রতিটি শব্দকে keyword বা identifier হিসেবে শ্রেণিবদ্ধ করো:

- `def`
- `student_name`
- `class`
- `calculate_total`
- `return`
- `marks`

### Exercise 5: Keyword or Built-in Function?

নিচের নামগুলো keyword, built-in function নাকি সাধারণ identifier—তা নির্ধারণ করো:

- `if`
- `print`
- `len`
- `for`
- `name`
- `input`
- `class`

### Exercise 6: Explain in Your Own Words

1. Python keyword কী?
2. Keyword-কে variable name হিসেবে ব্যবহার করা যায় না কেন?
3. Keyword এবং identifier-এর পার্থক্য কী?
4. Python keywords কীভাবে check করা যায়?
5. Soft keyword কী?
6. `print()` কি Python keyword?

## 14. Quick Revision

| Concept | Key Point |
|---|---|
| Keyword | Python-এর নির্দিষ্ট অর্থবাহী reserved word |
| Reserved word | সাধারণ identifier হিসেবে ব্যবহার করা যায় না |
| Identifier | Variable, function বা class-এর নাম |
| `keyword.kwlist` | Current interpreter-এর standard keyword list |
| `keyword.iskeyword()` | কোনো শব্দ keyword কি না যাচাই করে |
| Soft keyword | নির্দিষ্ট syntax context-এ special meaning বহন করে |
| Case-sensitive | `if` ও `IF` এক নয় |
| Built-in function | `print()` বা `len()`-এর মতো আগে থেকে পাওয়া function |

## 15. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Python keywords-এর নির্দিষ্ট syntax-related অর্থ রয়েছে।
- `if`, `else`, `for`, `while`, `def`, `class` এবং `return` গুরুত্বপূর্ণ keywords।
- Keywords সাধারণ variable, function বা class name হিসেবে ব্যবহার করা যায় না।
- Programmer নিজের identifier তৈরি করতে পারে, তবে naming rules মেনে চলতে হবে।
- Python-এর `keyword` module দিয়ে keyword list ও keyword status পরীক্ষা করা যায়।
- Soft keywords নির্দিষ্ট context-এ special meaning বহন করে।
- Built-in functions যেমন `print()` এবং `len()` keywords নয়।
- Python case-sensitive হওয়ায় keyword-এর সঠিক spelling ও letter case গুরুত্বপূর্ণ।

## 16. Next Topic

পরবর্তী ফাইল: [`09_Identifiers_and_Naming_Rules.md`](09_Identifiers_and_Naming_Rules.md)

এখানে আমরা identifier কী, variable ও function-এর নাম লেখার নিয়ম, valid এবং invalid identifiers, naming conventions এবং professional code-এ নামকরণের best practices শিখব।