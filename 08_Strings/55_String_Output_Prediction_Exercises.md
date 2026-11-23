# 55. String Output Prediction Exercises in Python

## 1. Introduction

এই file-এ Python String-এর বিভিন্ন topic থেকে কিছু Output Prediction Exercise দেওয়া হয়েছে।

এখানে code দেখে নিজে output অনুমান করার চেষ্টা করতে হবে। এরপর solution এবং explanation মিলিয়ে দেখতে হবে।

এই practice-এর মাধ্যমে String Indexing, Slicing, Methods, Loop, Condition এবং অন্যান্য বিষয় আরও ভালোভাবে বোঝা যাবে।

---

## 2. Easy Level Exercises

### Exercise 1: String Length

**Code:**

```python
text = "Python"
print(len(text))
```

**Output:**

```text
6
```

**Explanation:**

- `len()` string-এর মোট character সংখ্যা বের করে।
- `"Python"`-এ মোট 6টি character আছে।

### Exercise 2: Positive Indexing

**Code:**

```python
word = "Programming"

print(word[0])
print(word[3])
print(word[6])
```

**Output:**

```text
P
g
m
```

**Explanation:**

String-এর indexing `0` থেকে শুরু হয়।

- `word[0]` = P
- `word[3]` = g
- `word[6]` = m

### Exercise 3: Negative Indexing

**Code:**

```python
name = "Masum"

print(name[-1])
print(name[-2])
print(name[-5])
```

**Output:**

```text
m
u
M
```

**Explanation:**

Negative indexing string-এর শেষ দিক থেকে শুরু হয়।

- `-1` = শেষ character
- `-2` = শেষ থেকে দ্বিতীয় character
- `-5` = প্রথম character

### Exercise 4: String Slicing

**Code:**

```python
text = "Python Programming"

print(text[0:6])
print(text[7:18])
print(text[:6])
```

**Output:**

```text
Python
Programming
Python
```

**Explanation:**

Slicing-এর ক্ষেত্রে starting index অন্তর্ভুক্ত হয়, কিন্তু ending index অন্তর্ভুক্ত হয় না।

### Exercise 5: Reverse a String

**Code:**

```python
word = "Python"

print(word[::-1])
```

**Output:**

```text
nohtyP
```

**Explanation:**

`[::-1]` ব্যবহার করে string-কে উল্টো করা যায়।

### Exercise 6: String Concatenation

**Code:**

```python
first = "Hello"
second = "World"

result = first + " " + second

print(result)
```

**Output:**

```text
Hello World
```

**Explanation:**

`+` operator দিয়ে একাধিক string যুক্ত করা যায়।

### Exercise 7: String Repetition

**Code:**

```python
text = "Hi "

print(text * 3)
```

**Output:**

```text
Hi Hi Hi
```

**Explanation:**

`*` operator দিয়ে string একাধিকবার repeat করা যায়।

### Exercise 8: Uppercase and Lowercase

**Code:**

```python
text = "Python Programming"

print(text.upper())
print(text.lower())
```

**Output:**

```text
PYTHON PROGRAMMING
python programming
```

**Explanation:**

- `upper()` সব character uppercase করে।
- `lower()` সব character lowercase করে।

### Exercise 9: Replace Method

**Code:**

```python
text = "I like Java"

new_text = text.replace("Java", "Python")

print(new_text)
```

**Output:**

```text
I like Python
```

**Explanation:**

`replace()` string-এর নির্দিষ্ট অংশ পরিবর্তন করে নতুন string return করে।

### Exercise 10: Membership Operator

**Code:**

```python
text = "Python Programming"

print("Python" in text)
print("Java" in text)
print("Java" not in text)
```

**Output:**

```text
True
False
True
```

**Explanation:**

- `in` দিয়ে কোনো substring আছে কি না পরীক্ষা করা হয়।
- `not in` দিয়ে substring নেই কি না পরীক্ষা করা হয়।

---

## 3. Medium Level Exercises

### Exercise 11: Strip Method

**Code:**

```python
text = "   Python   "

print(text.strip())
print(text.lstrip())
print(text.rstrip())
```

**Output:**

```text
Python
Python   
   Python
```

**Explanation:**

- `strip()` দুই পাশের whitespace সরায়।
- `lstrip()` বাম পাশের whitespace সরায়।
- `rstrip()` ডান পাশের whitespace সরায়।

### Exercise 12: Split Method

**Code:**

```python
text = "Python,Java,C++"

result = text.split(",")

print(result)
print(result[1])
```

**Output:**

```text
['Python', 'Java', 'C++']
Java
```

**Explanation:**

`split()` string-কে নির্দিষ্ট separator অনুযায়ী list-এ ভাগ করে।

### Exercise 13: Join Method

**Code:**

```python
words = ["I", "love", "Python"]

result = " ".join(words)

print(result)
```

**Output:**

```text
I love Python
```

**Explanation:**

`join()` list-এর string elements-গুলোকে একত্র করে একটি string তৈরি করে।

### Exercise 14: Find and Count

**Code:**

```python
text = "banana"

print(text.find("a"))
print(text.count("a"))
print(text.find("z"))
```

**Output:**

```text
1
3
-1
```

**Explanation:**

- `find()` প্রথম matching character-এর index return করে।
- `count()` character কতবার আছে তা গণনা করে।
- কোনো character না পেলে `find()` `-1` return করে।

### Exercise 15: Loop Through a String

**Code:**

```python
word = "Cat"

for char in word:
    print(char)
```

**Output:**

```text
C
a
t
```

**Explanation:**

`for` loop ব্যবহার করে string-এর প্রতিটি character আলাদাভাবে পাওয়া যায়।

### Exercise 16: Enumerate Function

**Code:**

```python
word = "Cat"

for index, char in enumerate(word):
    print(index, char)
```

**Output:**

```text
0 C
1 a
2 t
```

**Explanation:**

`enumerate()` একসাথে character-এর index এবং character return করে।

### Exercise 17: String Immutability

**Code:**

```python
text = "Python"

text[0] = "J"

print(text)
```

**Output:**

```text
TypeError
```

**Explanation:**

Python string immutable। অর্থাৎ string তৈরি হওয়ার পর তার character সরাসরি পরিবর্তন করা যায় না।

### Exercise 18: String with Conditions

**Code:**

```python
password = "Python123"

if len(password) >= 8:
    print("Valid Password")
else:
    print("Invalid Password")
```

**Output:**

```text
Valid Password
```

**Explanation:**

- `len(password)` = 9
- 9 হলো 8-এর সমান বা বড়।
- তাই `if` block execute হবে।

### Exercise 19: Escape Characters

**Code:**

```python
print("Hello\nWorld")
print("Python\tProgramming")
```

**Output:**

```text
Hello
World
Python    Programming
```

**Explanation:**

- `\n` নতুন line তৈরি করে।
- `\t` tab space তৈরি করে।

### Exercise 20: String Comparison

**Code:**

```python
a = "apple"
b = "banana"

print(a == b)
print(a != b)
print(a < b)
```

**Output:**

```text
False
True
True
```

**Explanation:**

Python string comparison-এ character-এর Unicode value অনুযায়ী তুলনা করা হয়।

---

## 4. Advanced Level Exercises

### Exercise 21: Slicing with Step

**Code:**

```python
text = "Programming"

print(text[0:11:2])
print(text[1:11:2])
```

**Output:**

```text
Pormig
rgamn
```

**Explanation:**

`[start:stop:step]` ব্যবহার করে নির্দিষ্ট interval অনুযায়ী character নেওয়া যায়।

- প্রথম code-এ প্রতি 2 index পরপর character নেওয়া হয়েছে।
- দ্বিতীয় code-এ index 1 থেকে শুরু হয়েছে।

### Exercise 22: Count Vowels

**Code:**

```python
text = "education"
count = 0

for char in text:
    if char in "aeiou":
        count += 1

print(count)
```

**Output:**

```text
5
```

**Explanation:**

- Loop প্রতিটি character পরীক্ষা করে।
- Character vowel হলে `count` এক বাড়ে।
- `"education"`-এ মোট 5টি vowel আছে।

### Exercise 23: Count Characters Using Dictionary

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

- `frequency` একটি empty dictionary।
- `get(char, 0)` character-এর আগের count বের করে।
- প্রতিবার character পাওয়া গেলে count এক বাড়ে।

### Exercise 24: Remove Spaces

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

### Exercise 25: String Comprehension

**Code:**

```python
text = "python"

result = [char.upper() for char in text]

print(result)
```

**Output:**

```text
['P', 'Y', 'T', 'H', 'O', 'N']
```

**Explanation:**

List comprehension ব্যবহার করে string-এর প্রতিটি character uppercase করে নতুন list তৈরি করা হয়েছে।

### Exercise 26: Generator Expression

**Code:**

```python
text = "Python"

result = (char.upper() for char in text)

print(list(result))
```

**Output:**

```text
['P', 'Y', 'T', 'H', 'O', 'N']
```

**Explanation:**

- Generator expression `( )` ব্যবহার করে তৈরি করা হয়।
- এটি একবারে পুরো list তৈরি করে না।
- `list()` দিয়ে generator-এর সব value বের করা হয়েছে।

### Exercise 27: Palindrome Check

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

একটি string সামনে এবং পেছন থেকে একই হলে তাকে palindrome বলা হয়।

### Exercise 28: Word Counting

**Code:**

```python
text = "Python is easy to learn"

words = text.split()

print(len(words))
```

**Output:**

```text
5
```

**Explanation:**

- `split()` string-কে word অনুযায়ী list-এ ভাগ করে।
- `len()` মোট word সংখ্যা বের করে।

### Exercise 29: Remove Duplicate Characters

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

- প্রতিটি character পরীক্ষা করা হয়।
- Character আগে থেকে `result`-এ না থাকলে যোগ করা হয়।
- ফলে duplicate character বাদ পড়ে এবং প্রথম occurrence-এর order বজায় থাকে।

### Exercise 30: Regular Expression

**Code:**

```python
import re

text = "My numbers are 123 and 456"

result = re.findall(r"\d+", text)

print(result)
```

**Output:**

```text
['123', '456']
```

**Explanation:**

- `re.findall()` string থেকে matching অংশগুলো খুঁজে বের করে।
- `\d+` এক বা একাধিক digit খুঁজে বের করে।
- ফলাফল list আকারে পাওয়া যায়।

---

## 5. Common Output Prediction Mistakes

Output prediction করার সময় নিচের বিষয়গুলো মনে রাখতে হবে।

| বিষয় | মনে রাখবে |
|---|---|
| Indexing | Index শুরু হয় 0 থেকে |
| Negative Indexing | শেষ character-এর index -1 |
| Slicing | Stop index অন্তর্ভুক্ত হয় না |
| Step | Step অনুযায়ী character নেওয়া হয় |
| `len()` | মোট character সংখ্যা return করে |
| `find()` | না পেলে -1 return করে |
| `count()` | Matching character-এর সংখ্যা return করে |
| `split()` | List return করে |
| `join()` | String return করে |
| `strip()` | দুই পাশের whitespace সরায় |
| `upper()` | নতুন uppercase string return করে |
| Immutability | String সরাসরি পরিবর্তন করা যায় না |

---

## 6. Practice Exercises (Try Yourself)

নিচের প্রশ্নগুলোর output নিজে বের করার চেষ্টা করো। তারপর solution-এর সাথে মিলিয়ে দেখো।

### Question 1

```python
text = "Computer"

print(text[2])
print(text[-3])
```

### Question 2

```python
text = "ABCDEFG"

print(text[1:6:2])
```

### Question 3

```python
text = "Python"

print(text * 2)
print(text[::-1])
```

### Question 4

```python
text = "Hello Python"

print(text.lower().count("o"))
```

### Question 5

```python
text = "apple"

for char in text:
    if char == "p":
        print("Found")
```

### Question 6

```python
text = "Bangladesh"

print(text.startswith("Bang"))
print(text.endswith("desh"))
```

### Question 7

```python
text = "one two three"

words = text.split()

print(words[-1])
print(len(words))
```

### Question 8

```python
text = "Python"

result = ""

for char in text:
    result = char + result

print(result)
```

---

## 7. Practice Exercise Solutions

### Solution 1

```text
m
t
```

Explanation: `text[2]` হলো `m` এবং `text[-3]` হলো `t`।

### Solution 2

```text
BDF
```

Explanation: Index 1, 3 এবং 5 থেকে character নেওয়া হয়েছে।

### Solution 3

```text
PythonPython
nohtyP
```

Explanation: প্রথম লাইনে string repeat এবং দ্বিতীয় লাইনে reverse করা হয়েছে।

### Solution 4

```text
2
```

Explanation: `"hello python"`-এ `o` মোট 2 বার আছে।

### Solution 5

```text
Found
Found
```

Explanation: `"apple"`-এ `p` দুইবার আছে। তাই দুইবার `Found` print হবে।

### Solution 6

```text
True
True
```

Explanation:

- `startswith()` শুরুতে নির্দিষ্ট text আছে কি না পরীক্ষা করে।
- `endswith()` শেষে নির্দিষ্ট text আছে কি না পরীক্ষা করে।

### Solution 7

```text
three
3
```

Explanation: `split()` তিনটি word-এর list তৈরি করেছে। শেষ word হলো `three`।

### Solution 8

```text
nohtyP
```

Explanation: প্রতিবার নতুন character-কে আগের result-এর সামনে যুক্ত করা হয়েছে। ফলে string reverse হয়েছে।

---

## 8. Chapter Summary

এই file-এ আমরা Python String-এর বিভিন্ন বিষয় থেকে output prediction practice করেছি।

গুরুত্বপূর্ণ বিষয়গুলো:

1. String Indexing and Negative Indexing
2. String Slicing and Reversing
3. String Concatenation and Repetition
4. String Methods
5. Membership Operators
6. Loop and Enumerate
7. String Immutability
8. String Conditions
9. String Comprehension
10. Generator Expressions
11. Palindrome and Character Counting
12. Regular Expressions

---

## 9. Self-Assessment Checklist

নিচের বিষয়গুলো নিজে করতে পারলে এই practice শেষ হয়েছে বলে ধরে নিতে পারো।

- [ ] String-এর output predict করতে পারি।
- [ ] Positive এবং Negative Indexing বুঝি।
- [ ] Slicing-এর output বের করতে পারি।
- [ ] String reverse করতে পারি।
- [ ] String methods-এর output বুঝতে পারি।
- [ ] Loop দিয়ে character বের করতে পারি।
- [ ] String-এর character count করতে পারি।
- [ ] Palindrome check করতে পারি।
- [ ] String comprehension বুঝি।
- [ ] Generator expression বুঝি।
- [ ] Regular Expression-এর basic output বুঝি।

---

## 10. Next Topic

পরবর্তী file:

**56. String Programming Exercises**

এখানে Python String ব্যবহার করে বিভিন্ন programming problem solve করা হবে।