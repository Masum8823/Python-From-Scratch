# 57. Chapter Review and Self-Assessment in Python

## 1. Introduction

এই file-এ আমরা Python-এর **Chapter 08: Strings**-এর সম্পূর্ণ বিষয়গুলো review করব।

আগের file-গুলোতে আমরা String-এর basic concepts থেকে শুরু করে advanced string operations, built-in methods এবং বিভিন্ন programming problem সমাধান করা শিখেছি।

এই review-এর মাধ্যমে আমরা যাচাই করব:

- String তৈরি এবং ব্যবহার করতে পারি কি না।
- Indexing ও slicing বুঝি কি না।
- বিভিন্ন string methods ব্যবহার করতে পারি কি না।
- String formatting করতে পারি কি না।
- String-এর মাধ্যমে programming problems solve করতে পারি কি না।

এই file-এর মূল উদ্দেশ্য হলো পুরো chapter-এর গুরুত্বপূর্ণ বিষয়গুলো আবার মনে করা এবং নিজের programming skill যাচাই করা।

---

## 2. Complete Chapter Review

### 2.1 String Fundamentals

**String কী?**

String হলো এক বা একাধিক character-এর sequence। Python-এ text সংরক্ষণের জন্য string ব্যবহার করা হয়।

**Example:**

```python
name = "Masum"
message = 'I am learning Python.'

print(name)
print(message)
```

**Output:**

```text
Masum
I am learning Python.
```

**Important Points:**

- String single quotes (`' '`) দিয়ে তৈরি করা যায়।
- String double quotes (`" "`) দিয়েও তৈরি করা যায়।
- Multiline string-এর জন্য triple quotes ব্যবহার করা যায়।
- Python string immutable।

### 2.2 String Length

`len()` function দিয়ে একটি string-এর মোট character সংখ্যা বের করা যায়।

**Example:**

```python
text = "Python"

print(len(text))
```

**Output:**

```text
6
```

মনে রাখবে, space-ও character হিসেবে গণনা হয়।

### 2.3 String Indexing

Indexing ব্যবহার করে string-এর নির্দিষ্ট character access করা যায়।

**Example:**

```python
text = "Python"

print(text[0])
print(text[2])
print(text[-1])
```

**Output:**

```text
P
t
n
```

**Important Points:**

- Positive indexing `0` থেকে শুরু হয়।
- Negative indexing `-1` থেকে শুরু হয়।
- `-1` হলো শেষ character-এর index।

### 2.4 String Slicing

Slicing ব্যবহার করে string-এর একটি নির্দিষ্ট অংশ বের করা যায়।

**Syntax:**

```python
string[start:stop:step]
```

**Example:**

```python
text = "Python"

print(text[0:3])
print(text[2:5])
print(text[::-1])
```

**Output:**

```text
Pyt
tho
nohtyP
```

**Important Points:**

- `start` থেকে slicing শুরু হয়।
- `stop` index অন্তর্ভুক্ত হয় না।
- `step` character-এর ব্যবধান নির্ধারণ করে।
- `[::-1]` দিয়ে string reverse করা যায়।

### 2.5 String Immutability

Python string immutable। অর্থাৎ string তৈরি হওয়ার পরে তার character সরাসরি পরিবর্তন করা যায় না।

**Example:**

```python
text = "Python"

text[0] = "J"
```

**Output:**

```text
TypeError
```

তবে নতুন string তৈরি করে পরিবর্তিত result পাওয়া যায়।

**Example:**

```python
text = "Python"

new_text = "J" + text[1:]

print(new_text)
```

**Output:**

```text
Jython
```

### 2.6 String Concatenation and Repetition

**Concatenation:** `+` operator দিয়ে দুটি string যুক্ত করা হয়।

```python
first = "Hello"
second = "Python"

print(first + " " + second)
```

**Output:**

```text
Hello Python
```

**Repetition:** `*` operator দিয়ে string একাধিকবার repeat করা যায়।

```python
text = "Hi "

print(text * 3)
```

**Output:**

```text
Hi Hi Hi
```

### 2.7 Checking and Finding Substrings

`in` operator দিয়ে string-এর মধ্যে কোনো character বা substring আছে কি না পরীক্ষা করা যায়।

```python
text = "I love Python"

print("Python" in text)
print("Java" not in text)
```

**Output:**

```text
True
True
```

`find()` এবং `index()` method দিয়ে substring-এর অবস্থান খুঁজে পাওয়া যায়।

```python
text = "Programming"

print(text.find("gram"))
print(text.index("gram"))
```

**Output:**

```text
3
3
```

**Important Difference:**

- `find()` substring না পেলে `-1` return করে।
- `index()` substring না পেলে `ValueError` দেয়।

### 2.8 Important String Methods

| Method | কাজ |
|---|---|
| `upper()` | সব letter uppercase করে |
| `lower()` | সব letter lowercase করে |
| `title()` | প্রতিটি word-এর প্রথম letter uppercase করে |
| `capitalize()` | প্রথম character uppercase করে |
| `strip()` | দুই পাশের whitespace সরায় |
| `replace()` | নির্দিষ্ট text পরিবর্তন করে |
| `split()` | String-কে list-এ ভাগ করে |
| `join()` | String-এর iterable elements যুক্ত করে |
| `count()` | নির্দিষ্ট substring গণনা করে |
| `find()` | Substring-এর index খুঁজে |
| `startswith()` | নির্দিষ্ট text দিয়ে শুরু হয়েছে কি না পরীক্ষা করে |
| `endswith()` | নির্দিষ্ট text দিয়ে শেষ হয়েছে কি না পরীক্ষা করে |
| `isalpha()` | সব character alphabet কি না পরীক্ষা করে |
| `isdigit()` | সব character digit কি না পরীক্ষা করে |
| `isalnum()` | সব character alphabet বা digit কি না পরীক্ষা করে |

### 2.9 String Formatting

f-string ব্যবহার করে string-এর মধ্যে variable-এর value সহজে বসানো যায়।

**Example:**

```python
name = "Masum"
age = 22

print(f"My name is {name} and I am {age} years old.")
```

**Output:**

```text
My name is Masum and I am 22 years old.
```

### 2.10 Escape Sequences and Raw Strings

Escape sequence বিশেষ character প্রকাশ করতে ব্যবহৃত হয়।

| Escape Sequence | কাজ |
|---|---|
| `\n` | New line |
| `\t` | Tab space |
| `\\` | Backslash |
| `\'` | Single quote |
| `\"` | Double quote |

**Example:**

```python
print("Hello\nPython")
print("Hello\tPython")
```

**Output:**

```text
Hello
Python
Hello    Python
```

Raw string তৈরি করতে `r` ব্যবহার করা হয়।

```python
text = r"C:\new\test"

print(text)
```

**Output:**

```text
C:\new\test
```

### 2.11 Unicode and Bytes

Python 3-এর string Unicode text সংরক্ষণ করে।

- `str` হলো text data type।
- `bytes` হলো byte data type।
- Encoding text-কে bytes-এ রূপান্তর করে।
- Decoding bytes-কে text-এ রূপান্তর করে।

**Example:**

```python
text = "Hello"

data = text.encode("utf-8")

print(data)
print(data.decode("utf-8"))
```

**Output:**

```text
b'Hello'
Hello
```

---

## 3. Important String Rules

পরীক্ষা এবং programming-এর জন্য নিচের rules-গুলো মনে রাখবে।

1. String হলো character-এর sequence।
2. String immutable।
3. Indexing `0` থেকে শুরু হয়।
4. Negative indexing `-1` থেকে শুরু হয়।
5. Slicing-এর stop index অন্তর্ভুক্ত হয় না।
6. `len()` string-এর মোট character সংখ্যা বের করে।
7. `+` দিয়ে string concatenate করা যায়।
8. `*` দিয়ে string repeat করা যায়।
9. `in` দিয়ে substring check করা যায়।
10. `split()` একটি list return করে।
11. `join()` একটি string return করে।
12. `replace()` মূল string পরিবর্তন করে না।
13. `find()` না পেলে `-1` return করে।
14. `index()` না পেলে error দেয়।
15. f-string দিয়ে সহজে variable-এর value string-এ বসানো যায়।
16. Python 3 string Unicode support করে।

---

## 4. Output Prediction Exercises

নিচের code-গুলো run করার আগে নিজে output অনুমান করার চেষ্টা করো।

### Question 1

```python
text = "Python"

print(text[0])
print(text[-1])
```

**Answer:**

```text
P
n
```

### Question 2

```python
text = "Programming"

print(text[0:7])
print(text[3:8])
```

**Answer:**

```text
Program
gramm
```

### Question 3

```python
text = "Python"

print(text[::-1])
print(text[::2])
```

**Answer:**

```text
nohtyP
Pto
```

### Question 4

```python
text = "banana"

print(text.count("a"))
print(text.find("n"))
```

**Answer:**

```text
3
2
```

### Question 5

```python
text = "hello python"

print(text.upper())
print(text.title())
```

**Answer:**

```text
HELLO PYTHON
Hello Python
```

### Question 6

```python
text = "I love Python"

words = text.split()

print(words)
print(len(words))
```

**Answer:**

```text
['I', 'love', 'Python']
3
```

### Question 7

```python
text = "Python"

print("Py" in text)
print("Java" not in text)
```

**Answer:**

```text
True
True
```

### Question 8

```python
name = "Masum"

print(name * 2)
```

**Answer:**

```text
MasumMasum
```

### Question 9

```python
text = "  Python  "

print(text.strip())
```

**Answer:**

```text
Python
```

### Question 10

```python
text = "Python"

print(text.replace("P", "J"))
print(text)
```

**Answer:**

```text
Jython
Python
```

**Explanation:** `replace()` একটি নতুন string return করে। তাই original string পরিবর্তিত হয় না।

---

## 5. String Programming Self-Assessment

নিচের problem-গুলো নিজে solve করার চেষ্টা করো।

প্রতিটি problem-এর জন্য প্রথমে নিজে code লিখবে। প্রয়োজন হলে আগের file-গুলোর সাহায্য নিতে পারো।

### Basic Level

**Problem 1: Count Characters**

একটি string-এর মোট character সংখ্যা বের করো।

Expected Example:

```text
Input: Python
Output: 6
```

**Problem 2: Count Vowels**

একটি string-এ মোট কয়টি vowel আছে তা বের করো।

Expected Example:

```text
Input: education
Output: 5
```

**Problem 3: Convert to Uppercase**

একটি string-এর সব letter uppercase করো।

Expected Example:

```text
Input: hello python
Output: HELLO PYTHON
```

**Problem 4: Find the Last Character**

একটি string-এর শেষ character বের করো।

Expected Example:

```text
Input: Programming
Output: g
```

**Problem 5: Remove Spaces**

একটি string থেকে সব space remove করো।

Expected Example:

```text
Input: I love Python
Output: IlovePython
```

### Intermediate Level

**Problem 6: Reverse a String**

একটি string reverse করো।

Expected Example:

```text
Input: Python
Output: nohtyP
```

**Problem 7: Check Palindrome**

একটি word palindrome কি না পরীক্ষা করো।

Expected Example:

```text
Input: madam
Output: Palindrome
```

**Problem 8: Count Words**

একটি sentence-এ মোট কয়টি word আছে তা বের করো।

Expected Example:

```text
Input: Python is easy to learn
Output: 5
```

**Problem 9: Remove Duplicate Characters**

একটি string থেকে duplicate character remove করো।

Expected Example:

```text
Input: programming
Output: progamin
```

**Problem 10: Count Character Frequency**

একটি string-এর প্রতিটি character কতবার আছে তা বের করো।

Expected Example:

```text
Input: hello

Output:
h: 1
e: 1
l: 2
o: 1
```

### Advanced Level

**Problem 11: Check Anagram**

দুটি string anagram কি না পরীক্ষা করো।

Expected Example:

```text
Input:
listen
silent

Output: Anagram
```

**Problem 12: Find the Longest Word**

একটি sentence থেকে সবচেয়ে বড় word বের করো।

Expected Example:

```text
Input: Python is a powerful language

Output: powerful
```

**Problem 13: Extract Digits**

একটি string থেকে শুধু digit বের করো।

Expected Example:

```text
Input: Masum123CSE456

Output: 123456
```

**Problem 14: Remove All Vowels**

একটি string থেকে সব vowel remove করো।

Expected Example:

```text
Input: education

Output: dctn
```

**Problem 15: Create an Acronym**

একটি sentence-এর প্রতিটি word-এর প্রথম letter নিয়ে acronym তৈরি করো।

Expected Example:

```text
Input: Northern University Bangladesh

Output: NUB
```

---

## 6. Common Mistakes in String Programming

1. **IndexError:** String-এর range-এর বাইরে index ব্যবহার করলে error হয়।
2. **Immutability:** String-এর character সরাসরি পরিবর্তন করা যায় না।
3. **Case Sensitivity:** `"Python"` এবং `"python"` এক নয়।
4. **Empty String:** Empty string-এর ক্ষেত্রে `text[0]` ব্যবহার করলে error হয়।
5. **Slicing:** Stop index slicing-এর মধ্যে অন্তর্ভুক্ত হয় না।
6. **split():** এটি list return করে, string নয়।
7. **join():** এটি string return করে।
8. **TypeError:** String-এর সাথে integer সরাসরি concatenate করা যায় না।
9. **Whitespace:** `len()` space-সহ সব character গণনা করে।
10. **Case Handling:** Uppercase এবং lowercase character একসাথে compare করার সময় case normalization প্রয়োজন হতে পারে।

---

## 7. Important Questions for Revision

**Q1. What is a String?**

Answer: String is a sequence of characters used to store text.

**Q2. Is String Mutable or Immutable?**

Answer: String is immutable. Its characters cannot be changed directly.

**Q3. What is String Indexing?**

Answer: Indexing is used to access individual characters from a string.

**Q4. What is String Slicing?**

Answer: Slicing is used to get a specific part of a string.

**Q5. What is Negative Indexing?**

Answer: Negative indexing accesses characters from the end of a string.

**Q6. What is String Concatenation?**

Answer: Joining two or more strings using the `+` operator is called concatenation.

**Q7. What is String Repetition?**

Answer: Repeating a string using the `*` operator is called string repetition.

**Q8. What is the use of `len()`?**

Answer: `len()` returns the total number of characters in a string.

**Q9. What is the difference between `find()` and `index()`?**

Answer: `find()` returns `-1` if the substring is not found, but `index()` raises an error.

**Q10. What is the use of `split()`?**

Answer: `split()` divides a string into a list of words or parts.

**Q11. What is the use of `join()`?**

Answer: `join()` combines string elements into one string.

**Q12. What is an f-string?**

Answer: An f-string is used to insert variable values directly into a string.

**Q13. What is Unicode?**

Answer: Unicode is a standard used to represent characters from different languages.

**Q14. What is the difference between `str` and `bytes`?**

Answer: `str` stores text, while `bytes` stores binary byte data.

**Q15. How can we reverse a string?**

Answer: We can reverse a string using slicing `[::-1]`.

---

## 8. Chapter Summary

এই chapter-এ আমরা Python String-এর basic থেকে advanced পর্যন্ত বিভিন্ন বিষয় শিখেছি।

গুরুত্বপূর্ণ বিষয়গুলো:

1. Introduction to Strings
2. Creating Strings
3. Single, Double and Triple Quotes
4. Escape Characters
5. String Length
6. Positive and Negative Indexing
7. String Slicing
8. String Immutability
9. String Concatenation and Repetition
10. Substring Checking and Searching
11. String Comparison
12. String Iteration
13. Built-in String Methods
14. String Formatting
15. Escape Sequences and Raw Strings
16. Unicode and Encoding
17. Bytes vs Strings
18. Text Parsing and Validation
19. Character Counting and Frequency
20. Palindrome and Anagram Checking
21. Word Processing
22. Regular Expressions
23. String Errors and Debugging
24. String Performance and Best Practices
25. Output Prediction and Programming Exercises

---

## 9. Final Self-Assessment Checklist

Chapter 08 সম্পন্ন করার পর নিচের checklist দিয়ে নিজের প্রস্তুতি যাচাই করো।

### String Fundamentals

- [ ] String কী তা বুঝতে পারি।
- [ ] বিভিন্নভাবে string তৈরি করতে পারি।
- [ ] Single, double এবং triple quotes ব্যবহার করতে পারি।
- [ ] Escape sequences ব্যবহার করতে পারি।
- [ ] `len()` দিয়ে string-এর length বের করতে পারি।

### Indexing and Slicing

- [ ] Positive indexing বুঝি।
- [ ] Negative indexing বুঝি।
- [ ] String slicing করতে পারি।
- [ ] Step ব্যবহার করে slicing করতে পারি।
- [ ] String reverse করতে পারি।
- [ ] String immutability ব্যাখ্যা করতে পারি।

### String Operations

- [ ] Concatenation করতে পারি।
- [ ] String repetition করতে পারি।
- [ ] `in` এবং `not in` ব্যবহার করতে পারি।
- [ ] `find()` এবং `index()` ব্যবহার করতে পারি।
- [ ] String comparison করতে পারি।
- [ ] String iteration করতে পারি।

### String Methods

- [ ] Uppercase এবং lowercase করতে পারি।
- [ ] Whitespace remove করতে পারি।
- [ ] `replace()` ব্যবহার করতে পারি।
- [ ] `split()` এবং `join()` ব্যবহার করতে পারি।
- [ ] String testing methods ব্যবহার করতে পারি।
- [ ] Prefix এবং suffix check করতে পারি।

### Advanced Concepts

- [ ] f-string ব্যবহার করতে পারি।
- [ ] Number formatting করতে পারি।
- [ ] Raw string বুঝি।
- [ ] Unicode এবং encoding-এর basic ধারণা বুঝি।
- [ ] `str` এবং `bytes`-এর পার্থক্য বুঝি।
- [ ] Regular Expressions-এর basic ধারণা বুঝি।

### Problem Solving

- [ ] Vowel এবং consonant count করতে পারি।
- [ ] Palindrome check করতে পারি।
- [ ] Anagram check করতে পারি।
- [ ] Duplicate character খুঁজে বের করতে পারি।
- [ ] Character frequency বের করতে পারি।
- [ ] Longest এবং shortest word বের করতে পারি।
- [ ] String থেকে digit এবং alphabet extract করতে পারি।
- [ ] নিজের মতো করে string programming problems solve করতে পারি।

---

## 10. Chapter Completion

**Chapter 08: Strings in Python — Completed!**

এই chapter-এর মাধ্যমে Python-এর String সম্পর্কে basic থেকে advanced পর্যন্ত গুরুত্বপূর্ণ বিষয়গুলো শেখা এবং practice করা সম্পন্ন হলো।

পরবর্তী chapter-এ Python-এর নতুন একটি topic শুরু করা হবে।

**Keep Practicing and Keep Learning!**