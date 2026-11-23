

# 50. Extracting Information from Strings in Python

## 1. Introduction

Python-এ অনেক সময় একটি String থেকে নির্দিষ্ট কিছু Information বের করার প্রয়োজন হয়। এই কাজকে **Extracting Information from Strings** বলা হয়।

উদাহরণ:

- Email Address থেকে Username বের করা।
- Email Address থেকে Domain Name বের করা।
- String থেকে Number বের করা।
- Text থেকে নির্দিষ্ট Word বের করা।
- কোনো Record থেকে আলাদা আলাদা Information বের করা।

এই কাজগুলো করার জন্য আমরা `split()`, `find()`, Indexing, Slicing এবং Loop ব্যবহার করতে পারি।

---

## 2. Extracting Username from an Email

একটি Email Address থেকে `@` চিহ্নের আগের অংশ বের করে Username পাওয়া যায়।

**Example:**

```python
email = "masum@gmail.com"

username = email.split("@")[0]

print(username)
```

**Output:**

```text
masum
```

**Explanation:**

1. `split("@")` Email-টিকে `@` চিহ্ন দিয়ে ভাগ করে।
2. ফলে একটি List তৈরি হয়: `["masum", "gmail.com"]`
3. `[0]` দিয়ে প্রথম অংশটি নেওয়া হয়।
4. তাই Username পাওয়া যায়।

---

## 3. Extracting Domain Name from an Email

Email Address থেকে `@` চিহ্নের পরের অংশ বের করে Domain Name পাওয়া যায়।

**Example:**

```python
email = "masum@gmail.com"

domain = email.split("@")[1]

print(domain)
```

**Output:**

```text
gmail.com
```

**Explanation:**

- `split("@")` Email-টিকে দুই ভাগে ভাগ করে।
- `[1]` দিয়ে দ্বিতীয় অংশটি নেওয়া হয়।
- তাই `gmail.com` পাওয়া যায়।

**Another Example:**

```python
email = "student@yahoo.com"

parts = email.split("@")

print("Username:", parts[0])
print("Domain:", parts[1])
```

**Output:**

```text
Username: student
Domain: yahoo.com
```

---

## 4. Extracting Information Using split()

`split()` ব্যবহার করে একটি String থেকে আলাদা আলাদা Information বের করা যায়।

**Example:**

```python
student = "Masum CSE 3.95"

parts = student.split()

print("Name:", parts[0])
print("Department:", parts[1])
print("CGPA:", parts[2])
```

**Output:**

```text
Name: Masum
Department: CSE
CGPA: 3.95
```

**Explanation:**

`split()` সাধারণত Space অনুযায়ী String-কে ভাগ করে একটি List তৈরি করে।

এখানে:

- `parts[0]` = Masum
- `parts[1]` = CSE
- `parts[2]` = 3.95

---

## 5. Extracting Numbers from a String

একটি String-এর মধ্যে Text এবং Number একসাথে থাকতে পারে। Loop এবং `isdigit()` ব্যবহার করে সেখান থেকে Number বের করা যায়।

**Example:**

```python
text = "My age is 22"

numbers = ""

for char in text:
    if char.isdigit():
        numbers += char

print(numbers)
```

**Output:**

```text
22
```

**Explanation:**

1. Loop দিয়ে String-এর প্রতিটি Character পরীক্ষা করা হয়।
2. `isdigit()` চেক করে Character-টি Digit কি না।
3. Digit হলে সেটি `numbers` String-এর সাথে যোগ হয়।
4. শেষে শুধু Number পাওয়া যায়।

**Another Example:**

```python
text = "Room 205, Floor 3"

numbers = ""

for char in text:
    if char.isdigit():
        numbers += char

print(numbers)
```

**Output:**

```text
2053
```

**Important:** এই পদ্ধতিতে সব Digit একসাথে যুক্ত হয়। আলাদা আলাদা Number প্রয়োজন হলে অতিরিক্ত Logic ব্যবহার করতে হবে।

---

## 6. Extracting First and Last Words

`split()` ব্যবহার করে কোনো Sentence-এর প্রথম এবং শেষ Word বের করা যায়।

**Example:**

```python
sentence = "Python is easy to learn"

words = sentence.split()

first_word = words[0]
last_word = words[-1]

print("First Word:", first_word)
print("Last Word:", last_word)
```

**Output:**

```text
First Word: Python
Last Word: learn
```

**Explanation:**

- `words[0]` প্রথম Word বের করে।
- `words[-1]` শেষ Word বের করে।

---

## 7. Extracting a Specific Part Using Slicing

String Slicing ব্যবহার করে কোনো String-এর নির্দিষ্ট অংশ বের করা যায়।

**Syntax:**

```python
string[start:stop]
```

**Example:**

```python
text = "Python Programming"

result = text[0:6]

print(result)
```

**Output:**

```text
Python
```

**Explanation:**

- `0` হলো Starting Index।
- `6` হলো Ending Index, কিন্তু এটি অন্তর্ভুক্ত হবে না।
- তাই Index 0 থেকে 5 পর্যন্ত Character পাওয়া যায়।

**Another Example:**

```python
phone = "01712345678"

code = phone[0:3]
number = phone[3:]

print("Code:", code)
print("Number:", number)
```

**Output:**

```text
Code: 017
Number: 12345678
```

---

## 8. Extracting Text Using find()

`find()` Method ব্যবহার করে কোনো Character বা Word-এর Position বের করা যায়। এরপর Slicing ব্যবহার করে প্রয়োজনীয় অংশ Extract করা যায়।

**Example:**

```python
text = "Name: Masum"

position = text.find(":")

name = text[position + 2:]

print(name)
```

**Output:**

```text
Masum
```

**Explanation:**

1. `find(":")` Colon-এর Position বের করে।
2. `position + 2` দিয়ে Colon এবং পরের Space বাদ দেওয়া হয়।
3. Slicing দিয়ে বাকি অংশ নেওয়া হয়।

**Important:** কোনো Text খুঁজে না পেলে `find()` `-1` Return করে।

---

## 9. Extracting File Name and Extension

একটি File Name থেকে মূল নাম এবং Extension আলাদা করা যায়।

**Example:**

```python
filename = "python_notes.pdf"

parts = filename.split(".")

name = parts[0]
extension = parts[1]

print("File Name:", name)
print("Extension:", extension)
```

**Output:**

```text
File Name: python_notes
Extension: pdf
```

**Explanation:**

- `split(".")` Dot অনুযায়ী String ভাগ করে।
- `[0]` দিয়ে File Name পাওয়া যায়।
- `[1]` দিয়ে Extension পাওয়া যায়।

**Note:** এই Example-টি একটি সাধারণ File Name-এর জন্য। একাধিক Dot থাকলে বা Folder Path থাকলে আরও সতর্কভাবে কাজ করতে হবে।

---

## 10. Extracting Multiple Information from a String

একটি String-এর মধ্যে থাকা একাধিক Information আলাদা করে বের করা যায়।

**Example:**

```python
student = "Masum, CSE, 3.95"

parts = student.split(",")

name = parts[0].strip()
department = parts[1].strip()
cgpa = parts[2].strip()

print("Name:", name)
print("Department:", department)
print("CGPA:", cgpa)
```

**Output:**

```text
Name: Masum
Department: CSE
CGPA: 3.95
```

**Explanation:**

- `split(",")` Comma অনুযায়ী String ভাগ করে।
- `strip()` প্রতিটি অংশের শুরু ও শেষের অতিরিক্ত Space সরিয়ে দেয়।
- আলাদা Variable-এ Information রাখা হয়।

---

## 11. Extracting Information from User Input

User-এর কাছ থেকে Information নিয়ে সেখান থেকে নির্দিষ্ট অংশ বের করা যায়।

**Example:**

```python
email = input("Enter your email: ")

parts = email.split("@")

if len(parts) == 2:
    print("Username:", parts[0])
    print("Domain:", parts[1])
else:
    print("Invalid email format")
```

**Sample Input:**

```text
Enter your email: masum@gmail.com
```

**Output:**

```text
Username: masum
Domain: gmail.com
```

**Explanation:**

- `input()` দিয়ে Email নেওয়া হয়।
- `split("@")` দিয়ে Email ভাগ করা হয়।
- `len(parts) == 2` দিয়ে দুইটি অংশ আছে কি না পরীক্ষা করা হয়।
- সঠিক Format হলে Username এবং Domain দেখানো হয়।

**Note:** এটি শুধু Basic Format Checking। সম্পূর্ণ Email Validation নয়।

---

## 12. Practical Example: Extracting Information from a URL

একটি সাধারণ URL থেকে Domain Name বের করা যায়।

**Example:**

```python
url = "https://www.google.com/search"

domain = url.split("/")[2]

print(domain)
```

**Output:**

```text
www.google.com
```

**Explanation:**

- `split("/")` URL-টিকে Slash অনুযায়ী ভাগ করে।
- `[2]` দিয়ে Domain অংশটি পাওয়া যায়।

**Note:** এটি একটি সাধারণ URL-এর Example। সব ধরনের URL-এর জন্য এই পদ্ধতি নির্ভরযোগ্য নয়।

---

## 13. Common Mistakes

### Mistake 1: Wrong Index ব্যবহার করা

```python
email = "masum@gmail.com"

print(email.split("@")[2])
```

**Error:**

```text
IndexError: list index out of range
```

**কারণ:** `split("@")` করার পর এখানে মাত্র দুইটি অংশ তৈরি হয়েছে। কিন্তু `[2]` দিয়ে তৃতীয় অংশ চাওয়া হয়েছে।

### Mistake 2: find() এর Result Check না করা

```python
text = "Hello Python"

position = text.find("@")

print(text[position + 1:])
```

**সমস্যা:** `@` না থাকায় `find()` `-1` Return করে। তাই ভুল অংশ পাওয়া যেতে পারে।

**Correct Way:**

```python
text = "Hello Python"

position = text.find("@")

if position != -1:
    print(text[position + 1:])
else:
    print("Character not found")
```

**Output:**

```text
Character not found
```

### Mistake 3: strip() ব্যবহার না করা

```python
student = "Masum, CSE, 3.95"

parts = student.split(",")

print(parts[1])
```

**Output:**

```text
 CSE
```

**সমস্যা:** Comma-এর পর Space থেকে গেছে।

**Correct Way:**

```python
print(parts[1].strip())
```

**Output:**

```text
CSE
```

---

## 14. Practice Exercises

### Exercise 1: Extract Username

একটি Email Address থেকে Username বের করো।

**Solution:**

```python
email = "masum@gmail.com"

username = email.split("@")[0]

print(username)
```

**Output:**

```text
masum
```

### Exercise 2: Extract Domain

একটি Email Address থেকে Domain Name বের করো।

**Solution:**

```python
email = "student@yahoo.com"

domain = email.split("@")[1]

print(domain)
```

**Output:**

```text
yahoo.com
```

### Exercise 3: Extract Numbers

একটি String থেকে সব Digit বের করো।

**Solution:**

```python
text = "I have 25 books and 10 pens"

numbers = ""

for char in text:
    if char.isdigit():
        numbers += char

print(numbers)
```

**Output:**

```text
2510
```

### Exercise 4: Extract First and Last Word

একটি Sentence থেকে প্রথম এবং শেষ Word বের করো।

**Solution:**

```python
sentence = "I love learning Python"

words = sentence.split()

print("First:", words[0])
print("Last:", words[-1])
```

**Output:**

```text
First: I
Last: Python
```

### Exercise 5: Extract File Extension

একটি File Name থেকে Extension বের করো।

**Solution:**

```python
filename = "report.docx"

extension = filename.split(".")[-1]

print(extension)
```

**Output:**

```text
docx
```

---

## 15. Chapter Summary

এই Topic-এ আমরা শিখেছি:

1. String থেকে Username Extract করা।
2. Email থেকে Domain Name বের করা।
3. `split()` দিয়ে String ভাগ করা।
4. `isdigit()` দিয়ে Number Extract করা।
5. `Indexing` এবং `Slicing` দিয়ে নির্দিষ্ট অংশ বের করা।
6. `find()` দিয়ে Character বা Word-এর Position খুঁজে বের করা।
7. File Name এবং Extension আলাদা করা।
8. `strip()` দিয়ে অতিরিক্ত Space সরানো।
9. User Input থেকে Information Extract করা।

### Important Methods

| Method / Technique | কাজ |
|---|---|
| `split()` | String-কে ভাগ করে |
| `find()` | কোনো Text-এর Position খুঁজে |
| `strip()` | শুরু ও শেষের Space সরায় |
| `isdigit()` | Character Digit কি না পরীক্ষা করে |
| Indexing | নির্দিষ্ট Character বের করে |
| Slicing | নির্দিষ্ট অংশ বের করে |

---

## 16. Self-Assessment Checklist

নিচের বিষয়গুলো নিজে করতে পারলে এই Topic ভালোভাবে শেখা হয়েছে:

- [ ] Email থেকে Username বের করতে পারি।
- [ ] Email থেকে Domain বের করতে পারি।
- [ ] `split()` ব্যবহার করতে পারি।
- [ ] String থেকে Number Extract করতে পারি।
- [ ] First এবং Last Word বের করতে পারি।
- [ ] Slicing দিয়ে নির্দিষ্ট অংশ বের করতে পারি।
- [ ] `find()` ব্যবহার করতে পারি।
- [ ] File Extension Extract করতে পারি।
- [ ] User Input থেকে Information বের করতে পারি।

---

## 17. Next Topic

**51. String Comprehensions and Generator Expressions**

পরবর্তী Topic-এ আমরা শিখব:

- List Comprehension-এর মাধ্যমে String Processing।
- String থেকে নতুন List তৈরি করা।
- Generator Expression ব্যবহার করা।
- Comprehension এবং Generator-এর মধ্যে পার্থক্য।
- Practical String Processing Examples।

