

# 52. Regular Expressions Introduction in Python

## 1. Introduction

**Regular Expression (RegEx)** হলো Text-এর মধ্যে নির্দিষ্ট Pattern খুঁজে বের করার একটি পদ্ধতি।

Python-এ Regular Expression ব্যবহার করে আমরা:

- কোনো Text খুঁজে বের করতে পারি।
- নির্দিষ্ট Pattern Match করতে পারি।
- String থেকে Number খুঁজে বের করতে পারি।
- Email বা Phone Number-এর মতো Pattern খুঁজতে পারি।
- Text-এর মধ্যে নির্দিষ্ট Word খুঁজে বের করতে পারি।

Python-এ Regular Expression ব্যবহার করার জন্য `re` Module রয়েছে।

**Example:**

```python
import re

text = "I am learning Python"

result = re.search("Python", text)

print(result)
```

**Output:**

```text
<re.Match object; span=(15, 21), match='Python'>
```

**Explanation:**

- `import re` দিয়ে Regular Expression Module Import করা হয়েছে।
- `re.search()` দিয়ে Text-এর মধ্যে `Python` খোঁজা হয়েছে।
- Pattern পাওয়া যাওয়ায় একটি Match Object Return হয়েছে।

---

## 2. Importing the re Module

Python-এ Regular Expression ব্যবহার করার আগে `re` Module Import করতে হয়।

**Syntax:**

```python
import re
```

**Example:**

```python
import re

text = "Hello Python"

result = re.search("Hello", text)

if result:
    print("Pattern Found")
else:
    print("Pattern Not Found")
```

**Output:**

```text
Pattern Found
```

**Explanation:**

- `re` হলো Python-এর Built-in Module।
- `import re` দিয়ে Module-টি ব্যবহার করার জন্য প্রস্তুত করা হয়।
- এরপর `re`-এর বিভিন্ন Function ব্যবহার করা যায়।

---

## 3. Basic Regular Expression Patterns

RegEx-এ কিছু Special Character ব্যবহার করে বিভিন্ন Pattern তৈরি করা যায়।

| Pattern | কাজ |
|---|---|
| `.` | Newline ছাড়া যেকোনো একটি Character Match করে |
| `^` | String-এর শুরু নির্দেশ করে |
| `$` | String-এর শেষ নির্দেশ করে |
| `*` | আগের Character 0 বা তার বেশি বার Match করে |
| `+` | আগের Character 1 বা তার বেশি বার Match করে |
| `?` | আগের Character 0 বা 1 বার Match করে |
| `[]` | নির্দিষ্ট Character-এর মধ্যে যেকোনো একটি Match করে |
| `\d` | যেকোনো Digit Match করে |
| `\w` | Letter, Digit বা Underscore Match করে |
| `\s` | Whitespace Match করে |

**Example:**

```python
import re

text = "My age is 22"

result = re.findall(r"\d", text)

print(result)
```

**Output:**

```text
['2', '2']
```

**Explanation:**

- `\d` যেকোনো Digit খুঁজে বের করে।
- `findall()` সব Match খুঁজে List আকারে Return করে।
- তাই `2` এবং `2` পাওয়া গেছে।

**Important:** RegEx Pattern লেখার সময় সাধারণত `r"pattern"` ব্যবহার করা হয়। একে Raw String বলা হয়। এতে Backslash-সহ Pattern লেখা সহজ হয়।

---

## 4. Using re.search()

`re.search()` পুরো String-এর মধ্যে কোনো Pattern খুঁজে বের করে।

প্রথম Match পাওয়া গেলে সেটি Return করে।

**Syntax:**

```python
re.search(pattern, string)
```

**Example:**

```python
import re

text = "I love Python programming"

result = re.search("Python", text)

if result:
    print("Pattern Found")
else:
    print("Pattern Not Found")
```

**Output:**

```text
Pattern Found
```

**Explanation:**

- `search()` পুরো String-এ Pattern খোঁজে।
- Pattern পাওয়া গেলে Match Object Return করে।
- না পাওয়া গেলে `None` Return করে।

**Another Example:**

```python
import re

text = "I love Python"

result = re.search("Java", text)

print(result)
```

**Output:**

```text
None
```

কারণ String-এর মধ্যে `Java` নেই।

---

## 5. Using re.findall()

`re.findall()` String-এর মধ্যে Pattern-এর সব Match খুঁজে বের করে এবং List আকারে Return করে।

**Syntax:**

```python
re.findall(pattern, string)
```

**Example:**

```python
import re

text = "Python is easy. Python is powerful."

result = re.findall("Python", text)

print(result)
```

**Output:**

```text
['Python', 'Python']
```

**Explanation:**

- `findall()` পুরো String পরীক্ষা করে।
- যতগুলো Match পাওয়া যায়, সবগুলো List-এ রাখে।
- কোনো Match না থাকলে Empty List `[]` Return করে।

**Another Example:**

```python
import re

text = "My numbers are 10, 20 and 30"

result = re.findall(r"\d+", text)

print(result)
```

**Output:**

```text
['10', '20', '30']
```

এখানে `\d+` এক বা একাধিক Digit একসাথে Match করে।

---

## 6. Using re.match()

`re.match()` String-এর একদম শুরু থেকে Pattern Match করার চেষ্টা করে।

**Syntax:**

```python
re.match(pattern, string)
```

**Example:**

```python
import re

text = "Python is easy"

result = re.match("Python", text)

if result:
    print("Pattern Matched")
else:
    print("Pattern Not Matched")
```

**Output:**

```text
Pattern Matched
```

**Explanation:**

- `match()` String-এর শুরু থেকে পরীক্ষা করে।
- শুরুতেই Pattern পাওয়া গেলে Match Object Return করে।
- শুরুতে Pattern না থাকলে `None` Return করে।

**Another Example:**

```python
import re

text = "I love Python"

result = re.match("Python", text)

print(result)
```

**Output:**

```text
None
```

কারণ String-এর শুরুতে `Python` নেই।

---

## 7. Difference Between search(), match() and findall()

এই তিনটি Function-এর কাজ আলাদা।

| Function | কাজ |
|---|---|
| `re.search()` | পুরো String-এ প্রথম Match খোঁজে |
| `re.match()` | শুধু String-এর শুরু থেকে Match করে |
| `re.findall()` | সব Match List আকারে Return করে |

**Example:**

```python
import re

text = "I love Python. Python is easy."

print(re.search("Python", text))
print(re.match("Python", text))
print(re.findall("Python", text))
```

**Output:**

```text
<re.Match object; span=(7, 13), match='Python'>
None
['Python', 'Python']
```

**মনে রাখার সহজ উপায়:**

- `search()` = প্রথম Match খোঁজে।
- `match()` = শুরু থেকে Match করে।
- `findall()` = সব Match খুঁজে List দেয়।

---

## 8. Using Character Sets []

Square Bracket `[]` ব্যবহার করে নির্দিষ্ট কিছু Character-এর মধ্যে যেকোনো একটি Match করা যায়।

**Example:**

```python
import re

text = "cat bat rat"

result = re.findall("[cbr]at", text)

print(result)
```

**Output:**

```text
['cat', 'bat', 'rat']
```

**Explanation:**

- `[cbr]` অর্থ c, b অথবা r-এর যেকোনো একটি।
- `at`-এর সাথে মিলিয়ে Pattern তৈরি হয়।
- তাই `cat`, `bat` এবং `rat` Match হয়েছে।

**Another Example:**

```python
import re

text = "apple banana orange"

result = re.findall("[aeiou]", text)

print(result)
```

**Output:**

```text
['a', 'a', 'a', 'a', 'o', 'a', 'e']
```

এখানে `[aeiou]` যেকোনো একটি Vowel Match করে।

---

## 9. Using Special Character Classes

RegEx-এ কিছু গুরুত্বপূর্ণ Character Class রয়েছে।

| Pattern | কাজ |
|---|---|
| `\d` | Digit Match করে |
| `\D` | Non-digit Character Match করে |
| `\w` | Letter, Digit বা Underscore Match করে |
| `\W` | এগুলো ছাড়া অন্য Character Match করে |
| `\s` | Whitespace Match করে |
| `\S` | Non-whitespace Character Match করে |

**Example 1: Extracting Digits**

```python
import re

text = "Room 205"

result = re.findall(r"\d", text)

print(result)
```

**Output:**

```text
['2', '0', '5']
```

**Example 2: Extracting Non-Digit Characters**

```python
import re

text = "ABC123"

result = re.findall(r"\D", text)

print(result)
```

**Output:**

```text
['A', 'B', 'C']
```

**Example 3: Extracting Words**

```python
import re

text = "Hello Python 123"

result = re.findall(r"\w+", text)

print(result)
```

**Output:**

```text
['Hello', 'Python', '123']
```

---

## 10. Using Quantifiers

Quantifier ব্যবহার করে কোনো Character বা Pattern কতবার Match করবে তা নির্ধারণ করা যায়।

| Quantifier | কাজ |
|---|---|
| `*` | 0 বা তার বেশি বার |
| `+` | 1 বা তার বেশি বার |
| `?` | 0 বা 1 বার |
| `{n}` | ঠিক n বার |
| `{n,}` | কমপক্ষে n বার |
| `{n,m}` | n থেকে m বার |

**Example 1: Using `+`**

```python
import re

text = "My age is 25"

result = re.findall(r"\d+", text)

print(result)
```

**Output:**

```text
['25']
```

এখানে `+` এক বা একাধিক Digit একসাথে Match করেছে।

**Example 2: Using `{3}`**

```python
import re

text = "123 45 6789"

result = re.findall(r"\d{3}", text)

print(result)
```

**Output:**

```text
['123', '678']
```

এখানে ঠিক তিনটি Digit-এর Group Match হয়েছে।

**Example 3: Using `*`**

```python
import re

text = "ab abb abbb"

result = re.findall(r"ab*", text)

print(result)
```

**Output:**

```text
['ab', 'abb', 'abbb']
```

এখানে `b*` শূন্য বা তার বেশি `b` Match করেছে।

---

## 11. Using ^ and $ Symbols

`^` এবং `$` দিয়ে String-এর শুরু ও শেষ নির্দেশ করা হয়।

- `^` = String-এর শুরু।
- `$` = String-এর শেষ।

**Example 1: Checking the Beginning**

```python
import re

text = "Python is easy"

result = re.search(r"^Python", text)

if result:
    print("Starts with Python")
else:
    print("Does not start with Python")
```

**Output:**

```text
Starts with Python
```

**Example 2: Checking the Ending**

```python
import re

text = "I love Python"

result = re.search(r"Python$", text)

if result:
    print("Ends with Python")
else:
    print("Does not end with Python")
```

**Output:**

```text
Ends with Python
```

---

## 12. Extracting Phone Numbers Using RegEx

একটি String থেকে Phone Number-এর মতো Pattern Extract করা যায়।

**Example:**

```python
import re

text = "Contact: 01712345678"

result = re.findall(r"\d{11}", text)

print(result)
```

**Output:**

```text
['01712345678']
```

**Explanation:**

- `\d` যেকোনো Digit Match করে।
- `{11}` ঠিক ১১টি Digit Match করে।
- `findall()` সব Match খুঁজে List Return করে।

**Note:** এটি শুধু ১১ Digit-এর Sequence খুঁজে। এটি কোনো Phone Number-এর পূর্ণ Validation নয়।

---

## 13. Extracting Email-like Patterns Using RegEx

RegEx দিয়ে সাধারণ Email-এর মতো Pattern খুঁজে বের করা যায়।

**Example:**

```python
import re

text = "Contact me at masum@gmail.com"

pattern = r"\w+@\w+\.\w+"

result = re.findall(pattern, text)

print(result)
```

**Output:**

```text
['masum@gmail.com']
```

**Explanation:**

- `\w+` এক বা একাধিক Word Character Match করে।
- `@` Email-এর @ চিহ্ন Match করে।
- `\.` একটি সাধারণ Dot Match করে।
- শেষের `\w+` Domain-এর শেষ অংশ Match করে।

**Important:** এটি একটি Basic Pattern। সব ধরনের Valid Email Address সঠিকভাবে শনাক্ত করতে পারে না।

---

## 14. Common Mistakes

### Mistake 1: re Module Import না করা

**Wrong:**

```python
text = "Hello Python"

result = re.findall("Python", text)
```

**Error:**

```text
NameError: name 're' is not defined
```

**Correct:**

```python
import re

text = "Hello Python"

result = re.findall("Python", text)

print(result)
```

**Output:**

```text
['Python']
```

### Mistake 2: match() এবং search() এক মনে করা

```python
import re

text = "I love Python"

print(re.match("Python", text))
print(re.search("Python", text))
```

**Output:**

```text
None
<re.Match object; span=(7, 13), match='Python'>
```

**কারণ:**

- `match()` শুধু শুরু থেকে পরীক্ষা করে।
- `search()` পুরো String-এ খোঁজে।

### Mistake 3: findall() এর Result List হিসেবে না বোঝা

```python
import re

text = "I have 10 books"

result = re.findall(r"\d+", text)

print(result)
```

**Output:**

```text
['10']
```

**মনে রাখবে:** `findall()` Match পাওয়া গেলেও List Return করে, তাই Result-এর Data Type List।

### Mistake 4: Special Character Escape না করা

```python
import re

text = "file.txt"

result = re.findall(r".", text)

print(result)
```

**Output:**

```text
['f', 'i', 'l', 'e', '.', 't', 'x', 't']
```

**কারণ:** RegEx-এ `.` একটি Special Character। এটি সাধারণ Dot নয়, যেকোনো একটি Character Match করে।

**Correct Way:**

```python
import re

text = "file.txt"

result = re.findall(r"\.", text)

print(result)
```

**Output:**

```text
['.']
```

এখানে `\.` ব্যবহার করে সাধারণ Dot Match করা হয়েছে।

---

## 15. Practice Exercises

### Exercise 1: Find All Digits

একটি String থেকে সব Digit বের করো।

**Solution:**

```python
import re

text = "My marks are 85 and 90"

result = re.findall(r"\d", text)

print(result)
```

**Output:**

```text
['8', '5', '9', '0']
```

### Exercise 2: Find All Numbers

একটি String থেকে সম্পূর্ণ Number বের করো।

**Solution:**

```python
import re

text = "I have 10 books and 25 pens"

result = re.findall(r"\d+", text)

print(result)
```

**Output:**

```text
['10', '25']
```

### Exercise 3: Search for Python

একটি String-এর মধ্যে Python আছে কি না পরীক্ষা করো।

**Solution:**

```python
import re

text = "I am learning Python"

result = re.search("Python", text)

if result:
    print("Found")
else:
    print("Not Found")
```

**Output:**

```text
Found
```

### Exercise 4: Find All Vowels

একটি String থেকে সব Vowel বের করো।

**Solution:**

```python
import re

text = "education"

result = re.findall(r"[aeiou]", text)

print(result)
```

**Output:**

```text
['e', 'u', 'a', 'i', 'o']
```

### Exercise 5: Check String Beginning

একটি String `Hello` দিয়ে শুরু হয়েছে কি না পরীক্ষা করো।

**Solution:**

```python
import re

text = "Hello Python"

result = re.search(r"^Hello", text)

if result:
    print("Starts with Hello")
else:
    print("Does not start with Hello")
```

**Output:**

```text
Starts with Hello
```

---

## 16. Chapter Summary

এই Topic-এ আমরা শিখেছি:

1. Regular Expression কী।
2. Python-এর `re` Module Import করা।
3. Basic RegEx Pattern ব্যবহার করা।
4. `re.search()` ব্যবহার করা।
5. `re.findall()` ব্যবহার করা।
6. `re.match()` ব্যবহার করা।
7. Character Set `[]` ব্যবহার করা।
8. `\d`, `\w`, `\s` ইত্যাদি ব্যবহার করা।
9. Quantifier ব্যবহার করা।
10. `^` এবং `$` দিয়ে String-এর শুরু ও শেষ Match করা।
11. Phone Number এবং Email-এর মতো Pattern খুঁজে বের করা।

### Important Functions and Patterns

| Function / Pattern | কাজ |
|---|---|
| `re.search()` | প্রথম Match খোঁজে |
| `re.match()` | String-এর শুরু থেকে Match করে |
| `re.findall()` | সব Match List আকারে দেয় |
| `\d` | Digit Match করে |
| `\w` | Word Character Match করে |
| `\s` | Whitespace Match করে |
| `+` | এক বা একাধিকবার |
| `*` | শূন্য বা একাধিকবার |
| `^` | String-এর শুরু |
| `$` | String-এর শেষ |

---

## 17. Self-Assessment Checklist

- [ ] Regular Expression কী বুঝি।
- [ ] `re` Module Import করতে পারি।
- [ ] `re.search()` ব্যবহার করতে পারি।
- [ ] `re.findall()` ব্যবহার করতে পারি।
- [ ] `re.match()` ব্যবহার করতে পারি।
- [ ] তিনটি Function-এর পার্থক্য বুঝি।
- [ ] `\d`, `\w` এবং `\s` ব্যবহার করতে পারি।
- [ ] Quantifier ব্যবহার করতে পারি।
- [ ] `^` এবং `$` ব্যবহার করতে পারি।
- [ ] RegEx দিয়ে Number এবং Text Extract করতে পারি।

---

## 18. Next Topic

**53. Common String Errors and Debugging in Python**

পরবর্তী Topic-এ আমরা শিখব:

- String সম্পর্কিত Common Errors।
- `TypeError` এবং `IndexError`।
- `ValueError` এবং `AttributeError`।
- String-এর ভুল Debugging করা।
- Common Programming Mistakes।
- Error এড়ানোর Best Practices।

