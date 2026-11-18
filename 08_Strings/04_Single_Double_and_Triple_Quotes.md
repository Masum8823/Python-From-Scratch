# 04. Single, Double and Triple Quotes in Python

## 1. Introduction

Python-এ String তৈরি করার জন্য তিন ধরনের quotation marks ব্যবহার করা যায়:

1. Single Quotes (`' '`)
2. Double Quotes (`" "`)
3. Triple Quotes (`''' '''` অথবা `""" """`)

তিন ধরনের quotation marks দিয়েই String তৈরি করা যায়। তবে String-এর মধ্যে quotation marks ব্যবহার করা এবং multiline text লেখার ক্ষেত্রে এদের ব্যবহার আলাদা হতে পারে।

উদাহরণ:

```python
text1 = 'Hello Python'
text2 = "Hello Python"
text3 = """Hello Python"""

print(text1)
print(text2)
print(text3)
```

**Output:**

```text
Hello Python
Hello Python
Hello Python
```

তিনটি ক্ষেত্রেই একই String তৈরি হয়েছে।

## 2. Single Quotes (' ')

Single Quotes ব্যবহার করে সাধারণ String তৈরি করা যায়।

**Syntax:**

```python
variable = 'string'
```

উদাহরণ:

```python
name = 'Masum'
country = 'Bangladesh'
language = 'Python'

print(name)
print(country)
print(language)
```

**Output:**

```text
Masum
Bangladesh
Python
```

Single Quotes সাধারণত ছোট text বা String লেখার জন্য ব্যবহার করা হয়।

## 3. Double Quotes (" ")

Double Quotes ব্যবহার করেও সাধারণ String তৈরি করা যায়।

**Syntax:**

```python
variable = "string"
```

উদাহরণ:

```python
name = "Masum"
message = "Welcome to Python"
university = "Northern University Bangladesh"

print(name)
print(message)
print(university)
```

**Output:**

```text
Masum
Welcome to Python
Northern University Bangladesh
```

Single Quotes এবং Double Quotes-এর মধ্যে String তৈরির ক্ষেত্রে কোনো কার্যকর পার্থক্য নেই।

## 4. Single Quotes vs Double Quotes

| বিষয় | Single Quotes | Double Quotes |
|---|---|---|
| Syntax | `'Hello'` | `"Hello"` |
| String তৈরি | সম্ভব | সম্ভব |
| সাধারণ text | ব্যবহার করা যায় | ব্যবহার করা যায় |
| Apostrophe | Escape প্রয়োজন হতে পারে | সহজে ব্যবহার করা যায় |
| Double quotation mark | সহজে ব্যবহার করা যায় | Escape প্রয়োজন হতে পারে |

উদাহরণ:

```python
text1 = "I'm learning Python."
text2 = 'He said, "Hello!"'

print(text1)
print(text2)
```

**Output:**

```text
I'm learning Python.
He said, "Hello!"
```

এখানে:

- প্রথম String-এ apostrophe (`'`) আছে, তাই Double Quotes ব্যবহার করা হয়েছে।
- দ্বিতীয় String-এ Double Quotation Mark (`"`) আছে, তাই Single Quotes ব্যবহার করা হয়েছে।

এভাবে লিখলে অতিরিক্ত escape character ব্যবহার করতে হয় না।

## 5. Using Quotes Inside Strings

কখনো String-এর ভেতরে quotation marks ব্যবহার করার প্রয়োজন হতে পারে।

এক্ষেত্রে দুটি উপায় রয়েছে:

1. বাইরের ও ভেতরের quotation marks আলাদা রাখা।
2. Escape Character (`\`) ব্যবহার করা।

### Method 1: Using Different Quotes

```python
message1 = "It's a beautiful day."
message2 = 'He said, "Python is easy."'

print(message1)
print(message2)
```

**Output:**

```text
It's a beautiful day.
He said, "Python is easy."
```

এটি String-এর মধ্যে quotation marks ব্যবহারের সহজ পদ্ধতি।

### Method 2: Using Escape Characters

একই ধরনের quotation marks ব্যবহার করতে চাইলে backslash (`\`) দিয়ে escape করতে হয়।

```python
message1 = 'It\'s a beautiful day.'
message2 = "He said, \"Hello!\""

print(message1)
print(message2)
```

**Output:**

```text
It's a beautiful day.
He said, "Hello!"
```

এখানে:

- `\'` একটি single quotation mark তৈরি করেছে।
- `\"` একটি double quotation mark তৈরি করেছে।

## 6. Triple Single Quotes (''' ''')

Triple Single Quotes দিয়ে String তৈরি করা যায়।

**Syntax:**

```python
variable = '''string'''
```

উদাহরণ:

```python
message = '''Welcome to Python Programming'''

print(message)
```

**Output:**

```text
Welcome to Python Programming
```

Triple Single Quotes দিয়ে multiline String-ও তৈরি করা যায়।

```python
message = '''Hello Masum,
Welcome to Python.
Keep learning!'''

print(message)
```

**Output:**

```text
Hello Masum,
Welcome to Python.
Keep learning!
```

## 7. Triple Double Quotes (""" """)

Triple Double Quotes দিয়েও String তৈরি করা যায়।

**Syntax:**

```python
variable = """string"""
```

উদাহরণ:

```python
message = """Python is a programming language."""

print(message)
```

**Output:**

```text
Python is a programming language.
```

Multiline String:

```python
message = """Hello Masum,
Welcome to Python.
Happy Coding!"""

print(message)
```

**Output:**

```text
Hello Masum,
Welcome to Python.
Happy Coding!
```

Triple Single Quotes এবং Triple Double Quotes—দুটিই multiline String তৈরিতে সমানভাবে কাজ করে।

## 8. Single-Line vs Multiline Strings

| বিষয় | Single-Line String | Multiline String |
|---|---|---|
| সাধারণ ব্যবহার | একটি লাইনের text | একাধিক লাইনের text |
| Quotes | Single বা Double | Triple Single বা Triple Double |
| Example | `"Hello Python"` | `"""Hello Python"""` |

উদাহরণ:

**Single-Line String:**

```python
message = "Hello Python"
print(message)
```

**Multiline String:**

```python
message = """Hello Python
Welcome to Programming
Keep Practicing"""

print(message)
```

## 9. Triple Quotes and Line Breaks

Triple Quotes-এর মধ্যে Enter চাপলে সেই line break String-এর অংশ হয়ে যায়।

```python
text = """Python
Programming"""

print(text)
print(len(text))
```

**Output:**

```text
Python
Programming
18
```

এখানে:

- `Python` = 6 characters
- Line break (`\n`) = 1 character
- `Programming` = 11 characters

মোট = 18 characters।

অন্যদিকে `\n` ব্যবহার করেও line break তৈরি করা যায়।

```python
text = "Python\nProgramming"

print(text)
```

**Output:**

```text
Python
Programming
```

## 10. Triple Quotes and Docstrings

Python-এ Triple Quotes শুধু multiline String লেখার জন্য নয়, **Docstring** লেখার জন্যও ব্যবহৃত হয়।

Docstring হলো কোনো module, function বা class কী কাজ করে তা সংক্ষেপে ব্যাখ্যা করার documentation।

উদাহরণ:

```python
def greet():
    """Display a welcome message."""
    print("Welcome to Python!")

greet()
```

**Output:**

```text
Welcome to Python!
```

এখানে:

```python
"""Display a welcome message."""
```

এটি function-এর docstring।

Docstring সাধারণত function, class এবং module-এর documentation লেখার জন্য ব্যবহার করা হয়।

## 11. Choosing the Right Quotes

কোন quotation marks ব্যবহার করবে, তা String-এর content এবং readability-এর ওপর নির্ভর করে।

| Situation | Recommended Quotes |
|---|---|
| সাধারণ text | `'Hello'` অথবা `"Hello"` |
| Text-এ apostrophe আছে | `"It's Python"` |
| Text-এ double quote আছে | `'He said "Hello"'` |
| Multiline text | `"""..."""` |
| Function documentation | `"""..."""` |

Python-এর PEP 8 style guide অনুযায়ী Single ও Double Quotes-এর মধ্যে একটিকে বাধ্যতামূলক করা হয়নি। তবে একটি project-এ একই style ধারাবাহিকভাবে ব্যবহার করা ভালো।

## 12. Common Mistakes

### Mistake 1: Opening এবং Closing Quotes আলাদা হওয়া

ভুল:

```python
name = "Masum'
```

এখানে opening ও closing quotation marks আলাদা।

ফলে `SyntaxError` হবে।

সঠিক:

```python
name = "Masum"
```

### Mistake 2: String-এর মধ্যে Apostrophe ব্যবহার করা

ভুল:

```python
message = 'I'm learning Python'
```

এখানে apostrophe-এর কারণে String ভুলভাবে শেষ হয়ে যায়।

সঠিক:

```python
message = "I'm learning Python"
```

অথবা:

```python
message = 'I\'m learning Python'
```

### Mistake 3: Multiline String-এ সাধারণ Quotes ব্যবহার করা

ভুল:

```python
message = "Hello
Python"
```

সাধারণ quotation marks দিয়ে এভাবে সরাসরি multiline String তৈরি করা যায় না।

সঠিক:

```python
message = """Hello
Python"""
```

### Mistake 4: Triple Quotes সঠিকভাবে বন্ধ না করা

ভুল:

```python
message = """Hello Python
```

এখানে closing triple quotes নেই। ফলে `SyntaxError` হবে।

সঠিক:

```python
message = """Hello Python"""
```

### Mistake 5: Escape Character ভুলে যাওয়া

ভুল:

```python
message = "He said "Hello""
```

সঠিক:

```python
message = "He said \"Hello\""
```

**Output:**

```text
He said "Hello"
```

## 13. Practice Exercises

নিজে code লিখে সমাধান করার চেষ্টা করো।

1. Single Quotes দিয়ে নিজের নামের String তৈরি করো।
2. Double Quotes দিয়ে একটি welcome message তৈরি করো।
3. `"I'm learning Python"` সঠিকভাবে লিখো।
4. `'He said, "Hello!"'` String তৈরি করো।
5. Escape Character ব্যবহার করে Double Quotes-এর মধ্যে text লেখো।
6. Triple Single Quotes দিয়ে তিন লাইনের String তৈরি করো।
7. Triple Double Quotes দিয়ে multiline String তৈরি করো।
8. একটি function তৈরি করে তার মধ্যে Docstring লেখো।
9. Triple Quotes-এর মধ্যে থাকা String-এর length বের করো।
10. একই message Single এবং Double Quotes দিয়ে তৈরি করে compare করো।

## 14. Practice Solutions

### Solution 1

```python
name = 'Masum'
print(name)
```

### Solution 2

```python
message = "Welcome to Python!"
print(message)
```

### Solution 3

```python
message = "I'm learning Python."
print(message)
```

### Solution 4

```python
message = 'He said, "Hello!"'
print(message)
```

### Solution 5

```python
message = "He said, \"Python is easy.\""
print(message)
```

**Output:**

```text
He said, "Python is easy."
```

### Solution 6

```python
message = '''Hello!
I am learning Python.
Happy Coding!'''

print(message)
```

### Solution 7

```python
message = """Python is easy.
Python is powerful.
Python is popular."""

print(message)
```

### Solution 8

```python
def welcome():
    """Display a welcome message."""
    print("Welcome!")

welcome()
```

### Solution 9

```python
text = """Hello
Python"""

print(len(text))
```

**Output:**

```text
12
```

### Solution 10

```python
text1 = 'Python'
text2 = "Python"

print(text1 == text2)
```

**Output:**

```text
True
```

## 15. Chapter Summary

- Python-এ Single, Double এবং Triple Quotes দিয়ে String তৈরি করা যায়।
- Single ও Double Quotes সাধারণ String-এর জন্য ব্যবহার করা হয়।
- Triple Single ও Triple Double Quotes multiline String তৈরি করতে পারে।
- String-এর মধ্যে quotation marks ব্যবহার করতে ভিন্ন quotation marks অথবা escape character ব্যবহার করা যায়।
- `\'` single quote এবং `\"` double quote escape করে।
- Triple Quotes দিয়ে Docstring লেখা যায়।
- একটি project-এ consistent quotation style ব্যবহার করা ভালো।

## 16. Self-Assessment Checklist

- [ ] Single Quotes দিয়ে String তৈরি করতে পারি।
- [ ] Double Quotes দিয়ে String তৈরি করতে পারি।
- [ ] Triple Quotes ব্যবহার করতে পারি।
- [ ] Single ও Double Quotes-এর পার্থক্য বুঝি।
- [ ] String-এর মধ্যে quotation marks ব্যবহার করতে পারি।
- [ ] Multiline String তৈরি করতে পারি।
- [ ] Docstring কী তা বুঝি।
- [ ] Common quotation-related errors সমাধান করতে পারি।

## 17. Next Topic

পরবর্তী file: `05_Strings_with_Quotes_and_Escape_Characters.md`

এখানে String-এর মধ্যে quotation marks, backslash এবং special characters ব্যবহারের নিয়ম বিস্তারিত শেখানো হবে।
