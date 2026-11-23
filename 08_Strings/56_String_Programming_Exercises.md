# 56. String Programming Exercises in Python

## 1. Introduction

এই file-এ Python String ব্যবহার করে বিভিন্ন programming problem solve করা হবে।

প্রতিটি problem-এর সাথে থাকবে:

- Problem Description
- Python Code
- Output
- Explanation

প্রথমে নিজে problem solve করার চেষ্টা করবে। এরপর solution দেখে নিজের code মিলিয়ে নেবে।

---

## 2. Basic String Programming Exercises

### Exercise 1: Print Each Character of a String

**Problem:** একটি string-এর প্রতিটি character আলাদাভাবে print করো।

**Code:**

```python
text = "Python"

for char in text:
    print(char)
```

**Output:**

```text
P
y
t
h
o
n
```

**Explanation:**

- `for` loop string-এর প্রতিটি character access করে।
- `print()` প্রতিটি character আলাদা line-এ দেখায়।

### Exercise 2: Count the Total Characters

**Problem:** একটি string-এ মোট কতটি character আছে তা বের করো।

**Code:**

```python
text = "Programming"

count = len(text)

print("Total Characters:", count)
```

**Output:**

```text
Total Characters: 11
```

**Explanation:**

`len()` function string-এর মোট character সংখ্যা বের করে। Space থাকলেও সেটি character হিসেবে গণনা হয়।

### Exercise 3: Count Vowels in a String

**Problem:** একটি string-এ কয়টি vowel আছে তা বের করো।

**Code:**

```python
text = "education"
count = 0

for char in text:
    if char in "aeiou":
        count += 1

print("Total Vowels:", count)
```

**Output:**

```text
Total Vowels: 5
```

**Explanation:**

- প্রতিটি character পরীক্ষা করা হয়েছে।
- Character vowel হলে `count` এক বাড়ানো হয়েছে।
- শেষে মোট vowel সংখ্যা print করা হয়েছে।

### Exercise 4: Count Consonants in a String

**Problem:** একটি string-এ কয়টি consonant আছে তা বের করো।

**Code:**

```python
text = "education"
count = 0

for char in text:
    if char.isalpha() and char not in "aeiou":
        count += 1

print("Total Consonants:", count)
```

**Output:**

```text
Total Consonants: 4
```

**Explanation:**

- `isalpha()` পরীক্ষা করে character alphabet কি না।
- Character alphabet হলে এবং vowel না হলে সেটি consonant হিসেবে গণনা করা হয়েছে।
- এখানে uppercase vowel থাকলেও সঠিকভাবে গণনার জন্য `text.lower()` ব্যবহার করা যেতে পারে।

### Exercise 5: Convert a String into Uppercase

**Problem:** একটি string-এর সব character uppercase করো।

**Code:**

```python
text = "hello python"

result = text.upper()

print(result)
```

**Output:**

```text
HELLO PYTHON
```

**Explanation:**

`upper()` সব lowercase letter-কে uppercase করে।

### Exercise 6: Convert a String into Lowercase

**Problem:** একটি string-এর সব character lowercase করো।

**Code:**

```python
text = "HELLO PYTHON"

result = text.lower()

print(result)
```

**Output:**

```text
hello python
```

**Explanation:**

`lower()` সব uppercase letter-কে lowercase করে।

### Exercise 7: Reverse a String

**Problem:** একটি string reverse করো।

**Code:**

```python
text = "Python"

result = text[::-1]

print(result)
```

**Output:**

```text
nohtyP
```

**Explanation:**

`[::-1]` ব্যবহার করে string-এর character-গুলো উল্টো order-এ পাওয়া যায়।

### Exercise 8: Check Whether a Character Exists

**Problem:** একটি নির্দিষ্ট character string-এর মধ্যে আছে কি না পরীক্ষা করো।

**Code:**

```python
text = "Programming"

if "g" in text:
    print("Character Found")
else:
    print("Character Not Found")
```

**Output:**

```text
Character Found
```

**Explanation:**

`in` operator string-এর মধ্যে নির্দিষ্ট character বা substring আছে কি না পরীক্ষা করে।

### Exercise 9: Count a Specific Character

**Problem:** একটি নির্দিষ্ট character কতবার আছে তা বের করো।

**Code:**

```python
text = "banana"

count = text.count("a")

print("Character Count:", count)
```

**Output:**

```text
Character Count: 3
```

**Explanation:**

`count()` method নির্দিষ্ট character-এর মোট occurrence গণনা করে।

### Exercise 10: Remove Spaces from a String

**Problem:** একটি string থেকে সব space remove করো।

**Code:**

```python
text = "I love Python"

result = text.replace(" ", "")

print(result)
```

**Output:**

```text
IlovePython
```

**Explanation:**

`replace(" ", "")` সব space-কে empty string দিয়ে replace করে।

---

## 3. Intermediate String Programming Exercises

### Exercise 11: Check Palindrome String

**Problem:** একটি string palindrome কি না পরীক্ষা করো।

**Code:**

```python
text = "madam"

if text == text[::-1]:
    print("Palindrome")
else:
    print("Not Palindrome")
```

**Output:**

```text
Palindrome
```

**Explanation:**

Palindrome হলো এমন একটি word যা সামনে এবং পেছন থেকে একইভাবে পড়া যায়।

উদাহরণ: `madam`, `level`, `radar`।

### Exercise 12: Count Words in a String

**Problem:** একটি sentence-এ মোট কতটি word আছে তা বের করো।

**Code:**

```python
text = "Python is easy to learn"

words = text.split()

print("Total Words:", len(words))
```

**Output:**

```text
Total Words: 5
```

**Explanation:**

- `split()` sentence-কে word অনুযায়ী list-এ ভাগ করে।
- `len()` মোট word সংখ্যা বের করে।

### Exercise 13: Find the First Character

**Problem:** একটি string-এর প্রথম character বের করো।

**Code:**

```python
text = "Programming"

print("First Character:", text[0])
```

**Output:**

```text
First Character: P
```

**Explanation:**

String-এর প্রথম character-এর index হলো `0`।

### Exercise 14: Find the Last Character

**Problem:** একটি string-এর শেষ character বের করো।

**Code:**

```python
text = "Programming"

print("Last Character:", text[-1])
```

**Output:**

```text
Last Character: g
```

**Explanation:**

Negative indexing-এ `-1` হলো শেষ character।

### Exercise 15: Replace a Word in a Sentence

**Problem:** একটি sentence-এর নির্দিষ্ট word পরিবর্তন করো।

**Code:**

```python
text = "I like Java"

result = text.replace("Java", "Python")

print(result)
```

**Output:**

```text
I like Python
```

**Explanation:**

`replace()` পুরোনো word-এর পরিবর্তে নতুন word বসায় এবং নতুন string return করে।

### Exercise 16: Remove Duplicate Characters

**Problem:** একটি string থেকে duplicate character remove করো।

**Code:**

```python
text = "programming"
result = ""

for char in text:
    if char not in result:
        result += char

print(result)
```

**Output:**

```text
progamin
```

**Explanation:**

- প্রতিটি character পরীক্ষা করা হয়েছে।
- Character আগে থেকে `result`-এ থাকলে সেটি যোগ করা হয়নি।
- ফলে প্রথম occurrence রেখে duplicate character বাদ দেওয়া হয়েছে।

### Exercise 17: Find Duplicate Characters

**Problem:** একটি string-এর duplicate character খুঁজে বের করো।

**Code:**

```python
text = "programming"
duplicates = ""

for char in text:
    if text.count(char) > 1 and char not in duplicates:
        duplicates += char

print(duplicates)
```

**Output:**

```text
rgm
```

**Explanation:**

- `count(char)` character-এর occurrence সংখ্যা বের করে।
- Count 1-এর বেশি হলে character duplicate।
- `char not in duplicates` একই duplicate character বারবার print হওয়া আটকায়।

### Exercise 18: Find the Frequency of Each Character

**Problem:** একটি string-এর প্রতিটি character কতবার আছে তা বের করো।

**Code:**

```python
text = "hello"
frequency = {}

for char in text:
    frequency[char] = frequency.get(char, 0) + 1

print(frequency)
```

**Output:**

```text
{'h': 1, 'e': 1, 'l': 2, 'o': 1}
```

**Explanation:**

- একটি empty dictionary তৈরি করা হয়েছে।
- `get()` আগের count বের করে।
- প্রতিবার character পাওয়া গেলে count এক বাড়ে।

### Exercise 19: Check Whether Two Strings Are Equal

**Problem:** দুটি string একই কি না পরীক্ষা করো।

**Code:**

```python
text1 = "Python"
text2 = "Python"

if text1 == text2:
    print("Strings are Equal")
else:
    print("Strings are Not Equal")
```

**Output:**

```text
Strings are Equal
```

**Explanation:**

`==` operator দুটি string-এর value তুলনা করে।

### Exercise 20: Capitalize the First Letter

**Problem:** একটি string-এর প্রথম character uppercase করো।

**Code:**

```python
text = "python programming"

result = text.capitalize()

print(result)
```

**Output:**

```text
Python programming
```

**Explanation:**

`capitalize()` string-এর প্রথম character uppercase করে এবং বাকি অক্ষরগুলো lowercase করে।

---

## 4. Advanced String Programming Exercises

### Exercise 21: Check Anagram Strings

**Problem:** দুটি string anagram কি না পরীক্ষা করো।

**Code:**

```python
text1 = "listen"
text2 = "silent"

if sorted(text1) == sorted(text2):
    print("Anagram")
else:
    print("Not Anagram")
```

**Output:**

```text
Anagram
```

**Explanation:**

Anagram হলো দুটি word যেখানে একই character একই সংখ্যায় থাকে, তবে order আলাদা হতে পারে।

- `sorted()` character-গুলোকে সাজিয়ে list তৈরি করে।
- দুটি sorted list একই হলে string দুটি anagram।

### Exercise 22: Find the Longest Word

**Problem:** একটি sentence থেকে সবচেয়ে বড় word বের করো।

**Code:**

```python
text = "Python is a powerful language"

words = text.split()
longest = ""

for word in words:
    if len(word) > len(longest):
        longest = word

print("Longest Word:", longest)
```

**Output:**

```text
Longest Word: powerful
```

**Explanation:**

- `split()` sentence-কে word-এ ভাগ করে।
- প্রতিটি word-এর length পরীক্ষা করা হয়।
- সবচেয়ে বেশি length-এর word `longest` variable-এ রাখা হয়।

### Exercise 23: Find the Shortest Word

**Problem:** একটি sentence থেকে সবচেয়ে ছোট word বের করো।

**Code:**

```python
text = "Python is a powerful language"

words = text.split()
shortest = words[0]

for word in words:
    if len(word) < len(shortest):
        shortest = word

print("Shortest Word:", shortest)
```

**Output:**

```text
Shortest Word: a
```

**Explanation:**

- প্রথম word-কে initial shortest হিসেবে নেওয়া হয়েছে।
- পরবর্তী word-এর length ছোট হলে সেটি update করা হয়েছে।
- শেষে সবচেয়ে ছোট word পাওয়া যায়।

### Exercise 24: Reverse Each Word in a Sentence

**Problem:** একটি sentence-এর প্রতিটি word reverse করো।

**Code:**

```python
text = "I love Python"

words = text.split()

result = []

for word in words:
    result.append(word[::-1])

print(" ".join(result))
```

**Output:**

```text
I evol nohtyP
```

**Explanation:**

- `split()` sentence-কে word-এ ভাগ করে।
- `[::-1]` প্রতিটি word reverse করে।
- `join()` reverse করা word-গুলোকে একত্র করে।

### Exercise 25: Find the Most Frequent Character

**Problem:** একটি string-এ সবচেয়ে বেশি ব্যবহৃত character বের করো।

**Code:**

```python
text = "programming"

most_frequent = ""

for char in text:
    if text.count(char) > text.count(most_frequent):
        most_frequent = char

print("Most Frequent Character:", most_frequent)
```

**Output:**

```text
Most Frequent Character: r
```

**Explanation:**

- প্রতিটি character-এর count পরীক্ষা করা হয়েছে।
- যে character-এর count বেশি, সেটি `most_frequent`-এ রাখা হয়েছে।
- এখানে `r`, `g` এবং `m` প্রত্যেকটি 2 বার আছে। Code-টি প্রথম পাওয়া সর্বোচ্চ-frequency character return করে।

### Exercise 26: Check Whether a String Contains Only Digits

**Problem:** একটি string-এর সব character digit কি না পরীক্ষা করো।

**Code:**

```python
text = "12345"

if text.isdigit():
    print("Only Digits")
else:
    print("Not Only Digits")
```

**Output:**

```text
Only Digits
```

**Explanation:**

`isdigit()` string-এর সব character digit হলে `True` return করে।

### Exercise 27: Extract Digits from a String

**Problem:** একটি string থেকে শুধু digit বের করো।

**Code:**

```python
text = "Masum123CSE456"
result = ""

for char in text:
    if char.isdigit():
        result += char

print(result)
```

**Output:**

```text
123456
```

**Explanation:**

- `isdigit()` digit কি না পরীক্ষা করে।
- Digit হলে সেটি result-এর সাথে যুক্ত হয়।

### Exercise 28: Extract Alphabets from a String

**Problem:** একটি string থেকে শুধু alphabet বের করো।

**Code:**

```python
text = "Masum123@CSE"
result = ""

for char in text:
    if char.isalpha():
        result += char

print(result)
```

**Output:**

```text
MasumCSE
```

**Explanation:**

`isalpha()` character alphabet হলে `True` return করে।

### Exercise 29: Check Whether a String Starts and Ends with Specific Text

**Problem:** একটি string নির্দিষ্ট text দিয়ে শুরু এবং শেষ হয়েছে কি না পরীক্ষা করো।

**Code:**

```python
text = "Python Programming"

print(text.startswith("Python"))
print(text.endswith("Programming"))
```

**Output:**

```text
True
True
```

**Explanation:**

- `startswith()` শুরুতে নির্দিষ্ট text আছে কি না পরীক্ষা করে।
- `endswith()` শেষে নির্দিষ্ট text আছে কি না পরীক্ষা করে।

### Exercise 30: Create an Acronym

**Problem:** একটি sentence-এর প্রতিটি word-এর প্রথম letter নিয়ে acronym তৈরি করো।

**Code:**

```python
text = "Northern University Bangladesh"

words = text.split()
result = ""

for word in words:
    result += word[0].upper()

print(result)
```

**Output:**

```text
NUB
```

**Explanation:**

- `split()` sentence-কে word-এ ভাগ করে।
- `word[0]` প্রতিটি word-এর প্রথম character নেয়।
- `upper()` character-কে uppercase করে।

---

## 5. Additional Challenge Problems

নিজের programming skill যাচাই করার জন্য নিচের problem-গুলো নিজে solve করার চেষ্টা করো।

### Challenge 1: Swap First and Last Characters

**Problem:** একটি string-এর প্রথম এবং শেষ character পরিবর্তন করো।

**Expected Example:**

```text
Input: Python
Output: nythoP
```

**Hint:** Slicing ব্যবহার করো।

### Challenge 2: Count Uppercase and Lowercase Letters

**Problem:** একটি string-এ uppercase এবং lowercase letter আলাদাভাবে গণনা করো।

**Expected Example:**

```text
Input: PyThOn
Uppercase: 3
Lowercase: 3
```

**Hint:** `isupper()` এবং `islower()` ব্যবহার করো।

### Challenge 3: Remove All Vowels

**Problem:** একটি string থেকে সব vowel remove করো।

**Expected Example:**

```text
Input: education
Output: dctn
```

**Hint:** `for` loop এবং `not in` ব্যবহার করো।

### Challenge 4: Find the Second Largest Word

**Problem:** একটি sentence থেকে দ্বিতীয় সবচেয়ে বড় word বের করো।

**Expected Example:**

```text
Input: Python is a powerful programming language
Output: programming
```

**Hint:** প্রথমে word-গুলোকে length অনুযায়ী সাজানোর কথা ভাবো।

### Challenge 5: Check Palindrome Without Slicing

**Problem:** Slicing ব্যবহার না করে একটি string palindrome কি না পরীক্ষা করো।

**Expected Example:**

```text
Input: madam
Output: Palindrome
```

**Hint:** Loop ব্যবহার করে string-এর দুই পাশের character তুলনা করো।

---

## 6. Important String Methods for Programming

| Method | কাজ |
|---|---|
| `upper()` | সব letter uppercase করে |
| `lower()` | সব letter lowercase করে |
| `capitalize()` | প্রথম letter uppercase করে |
| `title()` | প্রতিটি word-এর প্রথম letter uppercase করে |
| `strip()` | দুই পাশের whitespace সরায় |
| `replace()` | নির্দিষ্ট text পরিবর্তন করে |
| `split()` | String-কে list-এ ভাগ করে |
| `join()` | List-এর string একত্র করে |
| `find()` | নির্দিষ্ট text-এর index খুঁজে |
| `count()` | নির্দিষ্ট text-এর সংখ্যা গণনা করে |
| `startswith()` | শুরুতে নির্দিষ্ট text আছে কি না পরীক্ষা করে |
| `endswith()` | শেষে নির্দিষ্ট text আছে কি না পরীক্ষা করে |
| `isalpha()` | সব character alphabet কি না পরীক্ষা করে |
| `isdigit()` | সব character digit কি না পরীক্ষা করে |
| `isalnum()` | সব character alphabet বা digit কি না পরীক্ষা করে |
| `isupper()` | সব letter uppercase কি না পরীক্ষা করে |
| `islower()` | সব letter lowercase কি না পরীক্ষা করে |

---

## 7. Common Mistakes

1. **IndexError:** String-এর range-এর বাইরে index ব্যবহার করলে error হয়।
2. **Immutability:** String-এর character সরাসরি পরিবর্তন করা যায় না।
3. **Case Sensitivity:** `"Python"` এবং `"python"` এক নয়।
4. **Slicing:** Slicing-এর stop index অন্তর্ভুক্ত হয় না।
5. **Empty String:** `text[0]` ব্যবহার করার আগে string empty কি না খেয়াল রাখতে হবে।
6. **split() and join():** `split()` list return করে, আর `join()` string return করে।
7. **Whitespace:** `len()` space-সহ সব character গণনা করে।

---

## 8. Chapter Summary

এই file-এ আমরা Python String ব্যবহার করে বিভিন্ন programming problem solve করেছি।

গুরুত্বপূর্ণ বিষয়গুলো:

1. Character Counting
2. Vowel and Consonant Counting
3. String Reversing
4. Palindrome Checking
5. Word Counting
6. Duplicate Character Removal
7. Character Frequency
8. Anagram Checking
9. Longest and Shortest Word
10. Digit and Alphabet Extraction
11. String Validation
12. Acronym Creation

---

## 9. Self-Assessment Checklist

- [ ] String-এর প্রতিটি character print করতে পারি।
- [ ] Vowel এবং consonant count করতে পারি।
- [ ] String reverse করতে পারি।
- [ ] Palindrome check করতে পারি।
- [ ] Word count বের করতে পারি।
- [ ] Duplicate character remove করতে পারি।
- [ ] Character frequency বের করতে পারি।
- [ ] Anagram check করতে পারি।
- [ ] Longest এবং shortest word বের করতে পারি।
- [ ] String থেকে digit এবং alphabet আলাদা করতে পারি।
- [ ] String-এর uppercase এবং lowercase count করতে পারি।
- [ ] নিজের মতো করে String programming problem solve করতে পারি।

---

## 10. Next Topic

পরবর্তী file:

**57. Chapter Review and Self-Assessment**

এখানে Chapter 08: Strings-এর সম্পূর্ণ বিষয়গুলো review করা হবে এবং নিজের শেখার অগ্রগতি যাচাই করার জন্য final assessment দেওয়া হবে।