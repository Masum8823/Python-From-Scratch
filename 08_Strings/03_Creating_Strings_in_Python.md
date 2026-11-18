# 03. Creating Strings in Python

## 1. Introduction

Python-এ String তৈরি করা খুবই সহজ। কোনো text-কে quotation marks-এর মধ্যে লিখলেই Python সেটিকে String হিসেবে চিনতে পারে।

উদাহরণ:

```python
name = "Masum"
```

এখানে `"Masum"` একটি String এবং `name` হলো variable, যেখানে String-টি সংরক্ষণ করা হয়েছে।

Python-এ String তৈরির জন্য প্রধানত তিন ধরনের quotation marks ব্যবহার করা যায়:

1. Single Quotes (`' '`)
2. Double Quotes (`" "`)
3. Triple Quotes (`''' '''` অথবা `""" """`)

## 2. Creating a String with Single Quotes

Single quotation marks ব্যবহার করে String তৈরি করা যায়।

```python
name = 'Masum'
country = 'Bangladesh'

print(name)
print(country)
```

**Output:**

```text
Masum
Bangladesh
```

এখানে `'Masum'` এবং `'Bangladesh'` দুটি String।

## 3. Creating a String with Double Quotes

Double quotation marks ব্যবহার করেও String তৈরি করা যায়।

```python
name = "Masum"
message = "Welcome to Python"

print(name)
print(message)
```

**Output:**

```text
Masum
Welcome to Python
```

Single ও double quotes—দুটিই String তৈরির জন্য সমানভাবে কাজ করে।

```python
a = 'Python'
b = "Python"

print(a)
print(b)
print(a == b)
```

**Output:**

```text
Python
Python
True
```

এখানে দুটি String-এর value একই, তাই comparison-এর ফলাফল `True`।

## 4. Creating a String with Triple Quotes

Triple quotes ব্যবহার করে String তৈরি করা যায়। এটি বিশেষ করে multiline text লেখার জন্য সুবিধাজনক।

Python-এ দুই ধরনের triple quotes রয়েছে:

- Triple Single Quotes: `''' '''`
- Triple Double Quotes: `""" """`

উদাহরণ:

```python
message = """Welcome to Python Programming."""

print(message)
```

**Output:**

```text
Welcome to Python Programming.
```

এখানে একটি সাধারণ String তৈরি হয়েছে।

## 5. Creating Multiline Strings

Triple quotes ব্যবহার করে একাধিক লাইনে String লেখা যায়।

```python
message = """Hello Masum,
Welcome to Python.
Keep learning every day."""

print(message)
```

**Output:**

```text
Hello Masum,
Welcome to Python.
Keep learning every day.
```

এখানে String-এর মধ্যে line break সংরক্ষিত রয়েছে।

এ ধরনের String ব্যবহার করা যায়:

- Long messages
- Documentation
- Descriptions
- Multiline text
- SQL query বা অন্যান্য formatted text

## 6. Choosing Between Single and Double Quotes

Single ও double quotes-এর মধ্যে Python-এর দৃষ্টিতে কোনো কার্যকর পার্থক্য নেই।

তবে String-এর মধ্যে quotation mark থাকলে উপযুক্ত quotation mark বেছে নেওয়া সুবিধাজনক।

উদাহরণ:

```python
message1 = "I'm learning Python."
message2 = 'He said, "Hello!"'

print(message1)
print(message2)
```

**Output:**

```text
I'm learning Python.
He said, "Hello!"
```

প্রথম String-এ apostrophe আছে, তাই double quotes ব্যবহার করা হয়েছে।

দ্বিতীয় String-এ double quotation mark আছে, তাই single quotes ব্যবহার করা হয়েছে।

## 7. Creating an Empty String

যে String-এর মধ্যে কোনো character থাকে না, তাকে Empty String বলে।

Empty String তৈরি করার দুটি উপায়:

```python
text1 = ""
text2 = ''

print(text1)
print(text2)

print(len(text1))
print(len(text2))
```

**Output:**

```text


0
0
```

দুটি String-ই empty, তাই তাদের length `0`।

Empty String ব্যবহার করা হয়:

- Initially empty variable তৈরি করতে।
- User input সংগ্রহ করতে।
- Loop-এর মধ্যে text জমা করতে।
- Text processing করতে।

উদাহরণ:

```python
message = ""

message = message + "Hello"
message = message + " Python"

print(message)
```

**Output:**

```text
Hello Python
```

## 8. Creating Strings Using Variables

String সরাসরি variable-এ রাখা যায়।

```python
name = "Masum"
university = "NUB"
department = "CSE"

print(name)
print(university)
print(department)
```

**Output:**

```text
Masum
NUB
CSE
```

একটি String variable-এর value অন্য variable-এও রাখা যায়।

```python
first_name = "Abdulla"
second_name = first_name

print(second_name)
```

**Output:**

```text
Abdulla
```

এখানে `second_name`-এ `first_name`-এর String value রাখা হয়েছে।

## 9. Creating Strings Using the str() Function

`str()` function ব্যবহার করে অন্যান্য data type থেকে String তৈরি করা যায়।

উদাহরণ:

```python
age = 22
price = 250.50
is_student = True

age_text = str(age)
price_text = str(price)
status_text = str(is_student)

print(age_text)
print(price_text)
print(status_text)
```

**Output:**

```text
22
250.5
True
```

এখন এই variable-গুলোর data type পরীক্ষা করি:

```python
print(type(age_text))
print(type(price_text))
print(type(status_text))
```

**Output:**

```text
<class 'str'>
<class 'str'>
<class 'str'>
```

সবগুলো value এখন String।

## 10. Creating Strings with User Input

`input()` function ব্যবহার করে user-এর কাছ থেকে String নেওয়া যায়।

```python
name = input("Enter your name: ")

print("Welcome,", name)
```

**Sample Input:**

```text
Enter your name: Masum
```

**Output:**

```text
Welcome, Masum
```

`input()` সাধারণত user-এর দেওয়া value-কে String হিসেবে return করে।

```python
number = input("Enter a number: ")

print(type(number))
```

User যদি `100` লেখে, Output হবে:

```text
<class 'str'>
```

## 11. Creating Strings with Escape Characters

String-এর মধ্যে কিছু special character ব্যবহার করতে backslash (`\`) ব্যবহার করা হয়।

উদাহরণ:

```python
message = "Hello\nWorld"

print(message)
```

**Output:**

```text
Hello
World
```

এখানে `\n` নতুন line তৈরি করেছে।

আরেকটি উদাহরণ:

```python
message = "Python\tProgramming"

print(message)
```

**Output:**

```text
Python  Programming
```

এখানে `\t` একটি tab space তৈরি করেছে।

Escape characters নিয়ে বিস্তারিত আলোচনা হবে `34_Escape_Sequences_in_Strings.md` file-এ।

## 12. Creating Strings with Different Data

String-এর মধ্যে alphabet, digit, space এবং symbol—সবকিছু রাখা যায়।

```python
text1 = "Python"
text2 = "Python123"
text3 = "Hello World"
text4 = "Price: 500 Tk"
text5 = "Email: masum@example.com"

print(text1)
print(text2)
print(text3)
print(text4)
print(text5)
```

**Output:**

```text
Python
Python123
Hello World
Price: 500 Tk
Email: masum@example.com
```

## 13. Common String Creation Errors

### Mistake 1: Quotation Marks না দেওয়া

ভুল:

```python
name = Masum
```

এখানে Python `Masum`-কে variable হিসেবে খুঁজবে। সেটি আগে define করা না থাকলে `NameError` হবে।

সঠিক:

```python
name = "Masum"
```

### Mistake 2: Opening এবং Closing Quotes আলাদা হওয়া

ভুল:

```python
name = "Masum'
```

এখানে শুরুতে double quote এবং শেষে single quote রয়েছে। ফলে `SyntaxError` হবে।

সঠিক:

```python
name = "Masum"
```

### Mistake 3: String-এর মধ্যে একই ধরনের Quote ব্যবহার করা

ভুল:

```python
message = 'I'm learning Python'
```

এখানে `I'm`-এর apostrophe String-কে আগেই শেষ করে দেয়। ফলে `SyntaxError` হবে।

সঠিক:

```python
message = "I'm learning Python"
```

### Mistake 4: Multiline String-এ সাধারণ Quotes ব্যবহার করা

ভুল:

```python
message = "Hello
Welcome to Python"
```

সাধারণ single বা double quoted String এভাবে সরাসরি একাধিক লাইনে লেখা যায় না।

সঠিক:

```python
message = """Hello
Welcome to Python"""
```

### Mistake 5: String-এর সঙ্গে Number সরাসরি যুক্ত করা

ভুল:

```python
age = 22
message = "Age: " + age
```

এখানে `TypeError` হবে।

সঠিক:

```python
age = 22
message = "Age: " + str(age)

print(message)
```

**Output:**

```text
Age: 22
```

## 14. Practice Exercises

নিজে Python code লিখে সমাধান করার চেষ্টা করো।

1. Single quotes দিয়ে নিজের নামের String তৈরি করো।
2. Double quotes দিয়ে নিজের university-এর নাম রাখো।
3. Triple quotes দিয়ে তিন লাইনের একটি message তৈরি করো।
4. একটি Empty String তৈরি করে তার length বের করো।
5. `str()` ব্যবহার করে `100`-কে String-এ রূপান্তর করো।
6. দুটি String variable তৈরি করে তাদের value print করো।
7. User-এর কাছ থেকে নাম নিয়ে greeting message দেখাও।
8. String-এর মধ্যে `\n` ব্যবহার করে দুটি আলাদা line তৈরি করো।
9. String-এর মধ্যে alphabet, number এবং symbol রাখো।
10. `"I'm learning Python"` সঠিক quotation marks ব্যবহার করে তৈরি করো।

## 15. Practice Solutions

### Solution 1

```python
name = 'Masum'
print(name)
```

### Solution 2

```python
university = "Northern University Bangladesh"
print(university)
```

### Solution 3

```python
message = """Hello!
I am learning Python.
Python is interesting."""

print(message)
```

### Solution 4

```python
text = ""

print(len(text))
```

**Output:**

```text
0
```

### Solution 5

```python
number = str(100)

print(number)
print(type(number))
```

### Solution 6

```python
first_name = "Abdulla"
last_name = "Masum"

print(first_name)
print(last_name)
```

### Solution 7

```python
name = input("Enter your name: ")

print(f"Welcome, {name}!")
```

### Solution 8

```python
message = "Hello\nPython"

print(message)
```

**Output:**

```text
Hello
Python
```

### Solution 9

```python
text = "Python123@!"

print(text)
```

### Solution 10

```python
message = "I'm learning Python."

print(message)
```

## 16. Chapter Summary

- Quotation marks ব্যবহার করে String তৈরি করা হয়।
- Single ও double quotes—দুটিই ব্যবহার করা যায়।
- Triple quotes দিয়ে multiline String তৈরি করা যায়।
- Empty String-এর মধ্যে কোনো character থাকে না।
- Variable-এর মধ্যে String সংরক্ষণ করা যায়।
- `str()` দিয়ে অন্য data type-কে String-এ রূপান্তর করা যায়।
- `input()` user-এর কাছ থেকে String নেয়।
- Escape characters দিয়ে special formatting করা যায়।
- String তৈরির সময় quotation marks সঠিকভাবে ব্যবহার করতে হয়।

## 17. Self-Assessment Checklist

- [ ] Single ও double quotes দিয়ে String তৈরি করতে পারি।
- [ ] Triple quotes ব্যবহার করতে পারি।
- [ ] Multiline String তৈরি করতে পারি।
- [ ] Empty String তৈরি করতে পারি।
- [ ] `str()` function ব্যবহার করতে পারি।
- [ ] User input থেকে String নিতে পারি।
- [ ] Common String creation errors সমাধান করতে পারি।

## 18. Next Topic

পরবর্তী file: `04_Single_Double_and_Triple_Quotes.md`

এখানে Single, Double এবং Triple Quotes-এর ব্যবহার, পার্থক্য, nested quotation marks এবং কখন কোন quotation marks ব্যবহার করা উচিত—এসব বিস্তারিত শেখানো হবে।