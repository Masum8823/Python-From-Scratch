
# 35. Raw Strings in Python

## 1. Introduction to Raw Strings

Python-এ সাধারণ String-এর মধ্যে Backslash (`\`) দিয়ে শুরু হওয়া কিছু character Escape Sequence হিসেবে কাজ করে।

কিন্তু অনেক সময় আমরা চাই Backslash-কে Escape Sequence হিসেবে ব্যবহার না করে সাধারণ character হিসেবে রাখতে।

এই কাজের জন্য Python-এ **Raw String** ব্যবহার করা হয়।

Raw String তৈরি করতে String-এর শুরুতে ছোট হাতের `r` অথবা বড় হাতের `R` ব্যবহার করতে হয়।

### Example

```python
normal_string = "Hello\nWorld"
raw_string = r"Hello\nWorld"

print(normal_string)
print(raw_string)
```

**Output:**

```text
Hello
World
Hello\nWorld
```

**ব্যাখ্যা:**

- Normal String-এ `\n` নতুন line তৈরি করেছে।
- Raw String-এ `\n` সাধারণ text হিসেবে রয়েছে।

---

## 2. Syntax of Raw Strings

Raw String লেখার নিয়ম:

```python
r"string"
```

অথবা

```python
R"string"
```

### Example

```python
text1 = r"Python\nProgramming"
text2 = R"Hello\tWorld"

print(text1)
print(text2)
```

**Output:**

```text
Python\nProgramming
Hello\tWorld
```

এখানে `r` এবং `R` উভয়ই Raw String তৈরি করে।

---

## 3. Difference Between Normal String and Raw String

Normal String এবং Raw String-এর মধ্যে পার্থক্য নিচের উদাহরণে দেখা যায়।

### Example

```python
normal = "Python\nProgramming"
raw = r"Python\nProgramming"

print(normal)
print(raw)
```

**Output:**

```text
Python
Programming
Python\nProgramming
```

| Normal String | Raw String |
|---|---|
| Escape Sequence কাজ করে | Escape Sequence সাধারণত কাজ করে না |
| `\n` নতুন line তৈরি করে | `\n` সাধারণ text হিসেবে থাকে |
| সাধারণ text সংরক্ষণে ব্যবহৃত হয় | Backslash-সহ text সংরক্ষণে সুবিধা দেয় |

---

## 4. Raw Strings with File Paths

Windows File Path-এর মধ্যে Backslash (`\`) ব্যবহার করা হয়।

কিন্তু Python-এ কিছু Backslash combination Escape Sequence হিসেবে কাজ করতে পারে।

Raw String ব্যবহার করে এই সমস্যা সহজে এড়ানো যায়।

### Example 1: Normal String

```python
path = "C:\\Users\\Masum\\Documents"

print(path)
```

**Output:**

```text
C:\Users\Masum\Documents
```

### Example 2: Raw String

```python
path = r"C:\Users\Masum\Documents"

print(path)
```

**Output:**

```text
C:\Users\Masum\Documents
```

দুই ক্ষেত্রেই একই Output পাওয়া যায়।

তবে Raw String ব্যবহার করলে প্রতিটি Backslash আলাদাভাবে লিখতে হয় না।

---

## 5. Raw Strings with Escape Sequences

Raw String-এর মধ্যে সাধারণ Escape Sequence যেমন `\n`, `\t`, `\\` সাধারণত তাদের literal form-এ থাকে।

### Example

```python
text = r"Hello\nWorld\tPython\\"

print(text)
```

**Output:**

```text
Hello\nWorld\tPython\\
```

এখানে:

- `\n` New Line তৈরি করেনি।
- `\t` Tab Space তৈরি করেনি।
- `\\` একটি Backslash-এ রূপান্তরিত হয়নি।

সবগুলোই সাধারণ text হিসেবে রয়েছে।

---

## 6. Raw Strings with Regular Expressions

Regular Expression বা Regex-এ Backslash (`\`) অনেক বেশি ব্যবহৃত হয়।

যেমন:

- `\d` = Digit
- `\w` = Word Character
- `\s` = Whitespace

Regex লেখার সময় Raw String ব্যবহার করলে Backslash নিয়ে কাজ করা সহজ হয়।

### Example

```python
import re

text = "My age is 22"

pattern = r"\d+"

result = re.findall(pattern, text)

print(result)
```

**Output:**

```text
['22']
```

**ব্যাখ্যা:**

- `r"\d+"` একটি Raw String।
- `\d` যেকোনো Digit খুঁজে বের করে।
- `+` এক বা একাধিক Digit নির্দেশ করে।
- `re.findall()` text-এর মধ্যে matching value খুঁজে বের করে।

এখানে Raw String ব্যবহার করায় Regex pattern সহজে লেখা যায়।

---

## 7. Raw String Does Not Disable Every Special Character

Raw String-এর ক্ষেত্রে একটি গুরুত্বপূর্ণ বিষয় মনে রাখতে হবে।

Raw String-এ Backslash-এর Escape Sequence processing বন্ধ থাকে, কিন্তু এটি Python-এর String-এর সব নিয়ম বাতিল করে না।

বিশেষ করে Quote-এর আগে Backslash থাকলে সেটি Quote-কে String-এর অংশ হিসেবে রাখতে পারে।

### Example

```python
text = r"Python\n\"Programming"

print(text)
```

**Output:**

```text
Python\n\"Programming
```

এখানে `\"` একটি literal backslash এবং quote হিসেবে রয়েছে।

**Important:** Raw String-এর শেষেও একক Backslash (`\`) রাখা যায় না।

---

## 8. Important Limitation of Raw Strings

Python-এর Raw String-এর শেষে সরাসরি একটি Backslash রাখা যায় না।

### Incorrect Example

```python
path = r"C:\Users\Masum\"
```

**Output:**

```text
SyntaxError
```

**কারণ:**

Raw String-এর শেষের Backslash closing quote-কে Escape করে ফেলে। ফলে String সঠিকভাবে শেষ হয় না।

### Correct Example 1: Using Double Backslash

```python
path = r"C:\Users\Masum" + "\\"

print(path)
```

**Output:**

```text
C:\Users\Masum\
```

### Correct Example 2: Using Normal String

```python
path = "C:\\Users\\Masum\\"

print(path)
```

**Output:**

```text
C:\Users\Masum\
```

---

## 9. Practical Example: Windows File Path

```python
file_path = r"C:\Users\Masum\Desktop\Python\notes.txt"

print("File Path:", file_path)
```

**Output:**

```text
File Path: C:\Users\Masum\Desktop\Python\notes.txt
```

এখানে Raw String ব্যবহার করে Windows File Path সহজে লেখা হয়েছে।

---

## 10. Important Rules

1. Raw String তৈরি করতে `r` অথবা `R` ব্যবহার করতে হয়।
2. Raw String-এ সাধারণ Escape Sequence processing হয় না।
3. `r"\n"` সাধারণত `\n` হিসেবেই থাকে।
4. Windows File Path লেখার ক্ষেত্রে Raw String সুবিধাজনক।
5. Regular Expression লেখার ক্ষেত্রে Raw String অনেক বেশি ব্যবহৃত হয়।
6. Raw String-এর শেষে সরাসরি একটি Backslash রাখা যায় না।
7. Raw String-এর মধ্যেও Quote-এর নিয়ম মেনে চলতে হয়।
8. Raw String এবং Normal String উভয়ই Python-এর String।
9. Raw String ব্যবহার করলেও Python-এর String-এর অন্যান্য নিয়ম পরিবর্তন হয় না।

---

## 11. Common Mistakes

### Mistake 1: Forgetting the r Prefix

```python
text = "Hello\nWorld"

print(text)
```

**Output:**

```text
Hello
World
```

**কারণ:** এখানে `r` ব্যবহার করা হয়নি। তাই `\n` New Line তৈরি করেছে।

**Correct Code:**

```python
text = r"Hello\nWorld"

print(text)
```

**Output:**

```text
Hello\nWorld
```

### Mistake 2: Ending a Raw String with a Single Backslash

```python
path = r"C:\Python\"
```

**Output:**

```text
SyntaxError
```

**কারণ:** Raw String-এর শেষে সরাসরি একটি Backslash রাখা যায় না।

**Correct Code:**

```python
path = r"C:\Python" + "\\"

print(path)
```

**Output:**

```text
C:\Python\
```

### Mistake 3: Thinking Raw Strings Remove Backslashes

```python
text = r"Python\nWorld"

print(text)
```

**Output:**

```text
Python\nWorld
```

**কারণ:** Raw String Backslash সরিয়ে দেয় না। বরং Backslash-সহ text-কে সাধারণভাবে রাখে।

---

## 12. Practice Exercises

### Exercise 1: Basic Raw String

একটি Raw String তৈরি করে নিচের Output দেখাও।

**Expected Output:**

```text
Hello\nPython
```

### Exercise 2: File Path

Raw String ব্যবহার করে নিচের File Path সংরক্ষণ করো।

**Expected Output:**

```text
C:\Users\Masum\Desktop\Python
```

### Exercise 3: Multiple Escape Sequences

নিচের Code-এর Output Predict করো।

```python
text = r"Hello\nWorld\tPython"

print(text)
```

**Expected Output:**

```text
Hello\nWorld\tPython
```

### Exercise 4: Regex Pattern

Raw String ব্যবহার করে একটি Regex Pattern তৈরি করো, যা String-এর মধ্যে থাকা Digit খুঁজে বের করবে।

**Input:**

```python
text = "My ID is 12345"
```

**Expected Output:**

```text
['12345']
```

### Exercise 5: Predict the Output

```python
text1 = "Python\nProgramming"
text2 = r"Python\nProgramming"

print(text1)
print(text2)
print(len(text2))
```

**Expected Output:**

```text
Python
Programming
Python\nProgramming
19
```

---

## 13. Chapter Summary

এই topic-এ আমরা Python-এর Raw String সম্পর্কে শিখেছি।

| বিষয় | Description |
|---|---|
| Raw String | Backslash-সহ text সাধারণভাবে রাখে |
| `r` | Raw String তৈরি করে |
| `R` | Raw String তৈরি করে |
| File Path | Windows Path লেখার ক্ষেত্রে সুবিধাজনক |
| Regex | Regex Pattern লেখার ক্ষেত্রে সুবিধাজনক |
| Limitation | শেষে সরাসরি একটি Backslash রাখা যায় না |

**মনে রাখবে:**

- Normal String: `"\n"` → New Line
- Raw String: `r"\n"` → সাধারণ `\n` text

---

## 14. Self-Assessment Checklist

- [ ] Raw String কী বুঝতে পেরেছি।
- [ ] `r` এবং `R` ব্যবহার করতে পারি।
- [ ] Normal String ও Raw String-এর পার্থক্য বুঝতে পেরেছি।
- [ ] Raw String-এর মধ্যে Escape Sequence কীভাবে কাজ করে বুঝতে পেরেছি।
- [ ] File Path-এর ক্ষেত্রে Raw String ব্যবহার করতে পারি।
- [ ] Regex-এর ক্ষেত্রে Raw String-এর ব্যবহার বুঝতে পেরেছি।
- [ ] Raw String-এর limitation বুঝতে পেরেছি।
- [ ] Raw String-এর Output predict করতে পারি।

---

## 15. Next Topic

পরবর্তী topic:

**36. String Formatting with f-Strings in Python**

এখানে আমরা f-String কী, কীভাবে String-এর মধ্যে Variable ব্যবহার করতে হয় এবং Dynamic String তৈরি করতে হয়, তা শিখব।
