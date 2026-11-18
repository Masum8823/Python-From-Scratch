# 06. Multiline Strings in Python

## 1. Introduction

Python-এ যখন একটি String-এর মধ্যে একাধিক line-এর text রাখতে হয়, তখন তাকে **Multiline String** বলা হয়।

সাধারণ String সাধারণত একটি লাইনে লেখা হয়। কিন্তু Multiline String ব্যবহার করে একই String-এর মধ্যে একাধিক line লেখা যায়।

উদাহরণ:

```python
message = """Hello Masum,
Welcome to Python.
Keep learning!"""

print(message)
```

**Output:**

```text
Hello Masum,
Welcome to Python.
Keep learning!
```

এখানে একটি String-এর মধ্যে তিনটি line রয়েছে।

## 2. Why Multiline Strings Are Needed

অনেক সময় বড় text বা paragraph সংরক্ষণের প্রয়োজন হয়। প্রতিটি line আলাদা variable-এ না রেখে একটি Multiline String-এ রাখা যায়।

Multiline String ব্যবহার করা হয়:

- Long messages সংরক্ষণ করতে।
- Paragraph বা description লিখতে।
- Documentation তৈরি করতে।
- Email বা notification message তৈরি করতে।
- SQL query সুন্দরভাবে সাজাতে।
- Multiple lines-এর text process করতে।

উদাহরণ:

```python
description = """Python is a programming language.
It is easy to learn.
It is widely used in software development."""

print(description)
```

**Output:**

```text
Python is a programming language.
It is easy to learn.
It is widely used in software development.
```

## 3. Creating Multiline Strings with Triple Double Quotes

Triple Double Quotes (`""" """`) ব্যবহার করে Multiline String তৈরি করা যায়।

**Syntax:**

```python
variable = """First line
Second line
Third line"""
```

উদাহরণ:

```python
message = """Hello!
Welcome to Python.
Happy Coding!"""

print(message)
```

**Output:**

```text
Hello!
Welcome to Python.
Happy Coding!
```

এখানে প্রতিটি line আলাদা লাইনে দেখানো হয়েছে।

## 4. Creating Multiline Strings with Triple Single Quotes

Triple Single Quotes (`''' '''`) ব্যবহার করেও Multiline String তৈরি করা যায়।

উদাহরণ:

```python
message = '''Hello!
Welcome to Python.
Happy Coding!'''

print(message)
```

**Output:**

```text
Hello!
Welcome to Python.
Happy Coding!
```

Triple Single Quotes এবং Triple Double Quotes—দুটিই Multiline String তৈরির জন্য ব্যবহার করা যায়।

## 5. Multiline Strings with Newline Character (\n)

Triple Quotes ছাড়াও `\n` ব্যবহার করে একটি String-এর মধ্যে একাধিক line তৈরি করা যায়।

উদাহরণ:

```python
message = "Hello!\nWelcome to Python.\nHappy Coding!"

print(message)
```

**Output:**

```text
Hello!
Welcome to Python.
Happy Coding!
```

এখানে প্রতিটি `\n` একটি নতুন line তৈরি করেছে।

আরেকটি উদাহরণ:

```python
student_info = "Name: Masum\nDepartment: CSE\nUniversity: NUB"

print(student_info)
```

**Output:**

```text
Name: Masum
Department: CSE
University: NUB
```

## 6. Triple Quotes vs Newline Character

দুই পদ্ধতিতেই Multiline String তৈরি করা যায়। তবে লেখার ধরন আলাদা।

| বিষয় | Triple Quotes | `\n` |
|---|---|---|
| Syntax | `"""..."""` | `\n` |
| ব্যবহার | একাধিক লাইনে text লেখা | String-এর মধ্যে newline তৈরি |
| Readability | বড় text-এর জন্য সহজ | ছোট text-এর জন্য সুবিধাজনক |
| Line break | Enter চাপলে তৈরি হয় | `\n` লিখলে তৈরি হয় |

উদাহরণ:

**Triple Quotes:**

```python
text = """Python
is
easy."""

print(text)
```

**Using `\n`:**

```python
text = "Python\nis\neasy."

print(text)
```

দুই ক্ষেত্রেই Output:

```text
Python
is
easy.
```

## 7. Understanding Line Breaks in Multiline Strings

Multiline String-এর মধ্যে প্রতিটি line break-ও String-এর অংশ হিসেবে সংরক্ষিত হয়।

উদাহরণ:

```python
text = """Python
Programming"""

print(len(text))
```

**Output:**

```text
18
```

কারণ:

- `Python` = 6 characters
- Newline (`\n`) = 1 character
- `Programming` = 11 characters

মোট = 18 characters।

অর্থাৎ, line break-ও String-এর length-এর মধ্যে গণনা হয়।

## 8. Multiline Strings with Variables

Variable-এর মধ্যে Multiline String সংরক্ষণ করে পরে ব্যবহার করা যায়।

```python
name = "Masum"

message = f"""Hello, {name}!
Welcome to Python.
Happy Learning!"""

print(message)
```

**Output:**

```text
Hello, Masum!
Welcome to Python.
Happy Learning!
```

এখানে f-string ব্যবহার করে variable-এর value Multiline String-এর মধ্যে বসানো হয়েছে।

## 9. Multiline Strings in Real-World Applications

বাস্তব programming-এ Multiline String বিভিন্ন কাজে ব্যবহৃত হয়।

### Example 1: Student Information

```python
student = """Name: Masum
Department: CSE
University: NUB
Section: 9A"""

print(student)
```

**Output:**

```text
Name: Masum
Department: CSE
University: NUB
Section: 9A
```

### Example 2: Email Message

```python
email = """Dear Student,

Your registration is successful.

Thank you."""

print(email)
```

**Output:**

```text
Dear Student,

Your registration is successful.

Thank you.
```

### Example 3: SQL Query

```python
query = """SELECT *
FROM students
WHERE department = 'CSE';"""

print(query)
```

**Output:**

```text
SELECT *
FROM students
WHERE department = 'CSE';
```

এখানে SQL query-কে একাধিক লাইনে সাজানো হয়েছে, যাতে পড়তে ও বুঝতে সুবিধা হয়।

## 10. Common Mistakes

### Mistake 1: সাধারণ Quotes দিয়ে সরাসরি Multiline String লেখা

ভুল:

```python
message = "Hello
Welcome to Python"
```

এতে `SyntaxError` হবে।

সঠিক:

```python
message = """Hello
Welcome to Python"""
```

### Mistake 2: Triple Quotes বন্ধ করতে ভুলে যাওয়া

ভুল:

```python
message = """Hello
Welcome to Python
```

এখানে closing triple quotes নেই। ফলে `SyntaxError` হবে।

সঠিক:

```python
message = """Hello
Welcome to Python"""
```

### Mistake 3: String-এর শুরুতে অপ্রয়োজনীয় Newline তৈরি করা

```python
message = """
Hello Python
"""

print(message)
```

Output:

```text


Hello Python

```

এখানে opening triple quotes-এর পরের newline-টিও String-এর অংশ।

সঠিকভাবে শুরুতেই text রাখতে চাইলে:

```python
message = """Hello Python
Welcome to Programming"""
```

### Mistake 4: Triple Quotes-এর মধ্যে Indentation-এর প্রভাব না বোঝা

```python
message = """Hello
    Welcome to Python"""

print(message)
```

Output:

```text
Hello
    Welcome to Python
```

দ্বিতীয় লাইনের চারটি space-ও String-এর অংশ হিসেবে সংরক্ষিত হয়েছে।

### Mistake 5: `\n`-এর পরিবর্তে `/n` ব্যবহার করা

ভুল:

```python
message = "Hello/nPython"
print(message)
```

Output:

```text
Hello/nPython
```

সঠিক:

```python
message = "Hello\nPython"
print(message)
```

Output:

```text
Hello
Python
```

## 11. Practice Exercises

নিজে code লিখে সমাধান করার চেষ্টা করো।

1. Triple Double Quotes দিয়ে তিন লাইনের একটি String তৈরি করো।
2. Triple Single Quotes দিয়ে একটি Multiline String তৈরি করো।
3. `\n` ব্যবহার করে তিন লাইনের message print করো।
4. নিজের নাম, department এবং university নিয়ে Multiline String তৈরি করো।
5. একটি email message Multiline String হিসেবে তৈরি করো।
6. Multiline String-এর length বের করো।
7. f-string ব্যবহার করে variable-সহ Multiline String তৈরি করো।
8. একটি SQL query Multiline String হিসেবে লেখো।
9. একটি String-এ দুটি line break ব্যবহার করো।
10. Triple Quotes ও `\n` ব্যবহার করে একই Output তৈরি করো।

## 12. Practice Solutions

### Solution 1

```python
message = """Hello!
Welcome to Python.
Happy Learning!"""

print(message)
```

### Solution 2

```python
message = '''Python is easy.
Python is powerful.
Python is popular.'''

print(message)
```

### Solution 3

```python
message = "Hello\nWelcome to Python\nHappy Coding!"

print(message)
```

### Solution 4

```python
student = """Name: Masum
Department: CSE
University: NUB"""

print(student)
```

### Solution 5

```python
email = """Dear Student,

Your admission is successful.

Thank you."""

print(email)
```

### Solution 6

```python
text = """Hello
Python"""

print(len(text))
```

**Output:**

```text
12
```

### Solution 7

```python
name = "Masum"
course = "Python"

message = f"""Hello, {name}!
You are learning {course}.
Keep practicing!"""

print(message)
```

### Solution 8

```python
query = """SELECT *
FROM students
WHERE department = 'CSE';"""

print(query)
```

### Solution 9

```python
text = "First line\nSecond line\nThird line"

print(text)
```

### Solution 10

**Using Triple Quotes:**

```python
text1 = """Hello
Python
Programming"""
```

**Using `\n`:**

```python
text2 = "Hello\nPython\nProgramming"
```

দুটির Output একই।

## 13. Chapter Summary

- Multiline String হলো একাধিক line-যুক্ত String।
- Triple Single Quotes ও Triple Double Quotes দিয়ে Multiline String তৈরি করা যায়।
- `\n` ব্যবহার করেও নতুন line তৈরি করা যায়।
- Line break-ও String-এর অংশ এবং `len()`-এ গণনা হয়।
- Multiline String-এর মধ্যে variable বসাতে f-string ব্যবহার করা যায়।
- Email, documentation, SQL query এবং বড় text সংরক্ষণে Multiline String কাজে লাগে।
- Triple Quotes-এর মধ্যে indentation ও extra newline-ও String-এর অংশ হতে পারে।

## 14. Self-Assessment Checklist

- [ ] Multiline String কী বুঝি।
- [ ] Triple Double Quotes ব্যবহার করতে পারি।
- [ ] Triple Single Quotes ব্যবহার করতে পারি।
- [ ] `\n` দিয়ে line break তৈরি করতে পারি।
- [ ] Multiline String-এর length বের করতে পারি।
- [ ] f-string দিয়ে Multiline String তৈরি করতে পারি।
- [ ] Common Multiline String errors সমাধান করতে পারি।

## 15. Next Topic

পরবর্তী file: `07_String_Length_with_len.md`

এখানে `len()` function দিয়ে String-এর length বের করা, space ও special character গণনা এবং common mistakes বিস্তারিত শেখানো হবে।