
# 43. String Methods for Searching and Checking

## 1. Introduction

Python-এ String-এর মধ্যে কোনো নির্দিষ্ট character বা word খোঁজা এবং String-এর শুরু বা শেষ পরীক্ষা করার জন্য বিভিন্ন String Method রয়েছে।

এই কাজের জন্য গুরুত্বপূর্ণ কিছু method হলো:

- `find()` - কোনো character বা word খুঁজে বের করে।
- `index()` - কোনো character বা word-এর position বের করে।
- `count()` - কোনো character বা word কতবার আছে তা গণনা করে।
- `startswith()` - String নির্দিষ্ট কিছু দিয়ে শুরু হয়েছে কি না পরীক্ষা করে।
- `endswith()` - String নির্দিষ্ট কিছু দিয়ে শেষ হয়েছে কি না পরীক্ষা করে।
- `rfind()` - ডান দিক থেকে খোঁজা শুরু করে।
- `rindex()` - ডান দিক থেকে খুঁজে position বের করে।

এছাড়াও `in` এবং `not in` operator দিয়ে String-এর মধ্যে কোনো word আছে কি না পরীক্ষা করা যায়।

---

## 2. Using `find()` Method

`find()` method ব্যবহার করে কোনো String-এর মধ্যে নির্দিষ্ট character বা word খুঁজে বের করা যায়।

এটি খুঁজে পাওয়া প্রথম occurrence-এর index return করে।

**Syntax:**

```python
string.find(value, start, end)
```

এখানে:

- `value` = যে character বা word খুঁজতে চাই।
- `start` = কোথা থেকে খোঁজা শুরু হবে (optional)।
- `end` = কোথায় খোঁজা শেষ হবে (optional)।

উদাহরণ:

```python
text = "I love Python"

result = text.find("Python")

print(result)
```

**Output:**

```text
7
```

এখানে `"Python"` word-টি index `7` থেকে শুরু হয়েছে।

আরেকটি উদাহরণ:

```python
text = "Hello Python"

print(text.find("H"))
print(text.find("o"))
print(text.find("Python"))
```

**Output:**

```text
0
4
6
```

### When the Value is Not Found

যদি খুঁজতে চাওয়া character বা word String-এর মধ্যে না থাকে, তাহলে `find()` `-1` return করে।

```python
text = "Hello Python"

result = text.find("Java")

print(result)
```

**Output:**

```text
-1
```

### Using Start and End Parameters

`find()` method-এর মাধ্যমে নির্দিষ্ট range-এর মধ্যেও search করা যায়।

```python
text = "Python Programming"

print(text.find("o", 5))
print(text.find("o", 0, 5))
```

**Output:**

```text
4
4
```

প্রথম ক্ষেত্রে index `5` থেকে search শুরু হয়েছে। কিন্তু `"Python"`-এর `o` index `4`-এ থাকায় এটি পাওয়া যায়নি। তাই সঠিক output হবে `-1`।

সংশোধিত code:

```python
text = "Python Programming"

print(text.find("o", 5))
print(text.find("o", 0, 5))
```

**Output:**

```text
12
4
```

**মনে রাখবে:** `find()` কোনো value না পেলে error দেয় না, বরং `-1` return করে।

---

## 3. Using `index()` Method

`index()` method-ও String-এর মধ্যে নির্দিষ্ট character বা word-এর position খুঁজে বের করে।

এটি প্রথম occurrence-এর index return করে।

**Syntax:**

```python
string.index(value, start, end)
```

উদাহরণ:

```python
text = "Hello Python"

result = text.index("Python")

print(result)
```

**Output:**

```text
6
```

আরেকটি উদাহরণ:

```python
text = "Python Programming"

print(text.index("P"))
print(text.index("o"))
print(text.index("Programming"))
```

**Output:**

```text
0
4
7
```

### When the Value is Not Found

`index()` এবং `find()`-এর মধ্যে গুরুত্বপূর্ণ পার্থক্য রয়েছে।

যদি `index()` কোনো value খুঁজে না পায়, তাহলে এটি `ValueError` দেয়।

```python
text = "Hello Python"

print(text.index("Java"))
```

**Output:**

```text
ValueError: substring not found
```

### Difference Between `find()` and `index()`

| `find()` | `index()` |
|---|---|
| Position return করে | Position return করে |
| না পেলে `-1` দেয় | না পেলে `ValueError` দেয় |
| Error দেয় না | Error দিতে পারে |

**মনে রাখবে:**

- `find()` = Not found হলে `-1`
- `index()` = Not found হলে `ValueError`

---

## 4. Using `count()` Method

`count()` method ব্যবহার করে কোনো character বা word String-এর মধ্যে কতবার আছে তা গণনা করা যায়।

**Syntax:**

```python
string.count(value, start, end)
```

এখানে `start` এবং `end` optional parameter।

উদাহরণ:

```python
text = "banana"

result = text.count("a")

print(result)
```

**Output:**

```text
3
```

কারণ `"banana"`-তে `a` মোট ৩ বার আছে।

আরেকটি উদাহরণ:

```python
text = "Python Programming"

print(text.count("P"))
print(text.count("o"))
print(text.count("Python"))
```

**Output:**

```text
2
2
1
```

### Counting a Word

```python
text = "Python is easy. Python is powerful."

print(text.count("Python"))
print(text.count("is"))
```

**Output:**

```text
2
2
```

### When the Value is Not Found

যদি কোনো character বা word না থাকে, তাহলে `count()` `0` return করে।

```python
text = "Hello Python"

print(text.count("Java"))
```

**Output:**

```text
0
```

**মনে রাখবে:** `count()` একটি value কতবার আছে তা গণনা করে।

---

## 5. Using `startswith()` Method

`startswith()` method পরীক্ষা করে কোনো String নির্দিষ্ট character বা word দিয়ে শুরু হয়েছে কি না।

এটি Boolean value return করে।

- শুরু হলে `True`।
- শুরু না হলে `False`।

**Syntax:**

```python
string.startswith(prefix, start, end)
```

উদাহরণ:

```python
text = "Python Programming"

print(text.startswith("Python"))
print(text.startswith("Java"))
```

**Output:**

```text
True
False
```

### Checking the First Character

```python
text = "Bangladesh"

print(text.startswith("B"))
print(text.startswith("b"))
```

**Output:**

```text
True
False
```

এখানে Python case-sensitive। তাই uppercase `B` এবং lowercase `b` আলাদা।

### Using Start and End Parameters

```python
text = "Hello Python"

print(text.startswith("Python", 6))
print(text.startswith("Hello", 0, 5))
```

**Output:**

```text
True
True
```

**মনে রাখবে:** `startswith()` String-এর শুরু পরীক্ষা করে এবং `True` অথবা `False` return করে।

---

## 6. Using `endswith()` Method

`endswith()` method পরীক্ষা করে কোনো String নির্দিষ্ট character বা word দিয়ে শেষ হয়েছে কি না।

এটিও Boolean value return করে।

**Syntax:**

```python
string.endswith(suffix, start, end)
```

উদাহরণ:

```python
text = "Python Programming"

print(text.endswith("Programming"))
print(text.endswith("Python"))
```

**Output:**

```text
True
False
```

### Checking File Extensions

File-এর extension পরীক্ষা করার জন্য `endswith()` ব্যবহার করা যায়।

```python
filename = "notes.pdf"

print(filename.endswith(".pdf"))
print(filename.endswith(".txt"))
```

**Output:**

```text
True
False
```

আরেকটি উদাহরণ:

```python
filename = "python.py"

if filename.endswith(".py"):
    print("Python File")
else:
    print("Not a Python File")
```

**Output:**

```text
Python File
```

**মনে রাখবে:** `endswith()` String-এর শেষ অংশ পরীক্ষা করে।

---

## 7. Using `rfind()` Method

`rfind()` method `find()`-এর মতোই কাজ করে। তবে এটি ডান দিক থেকে search শুরু করে।

এটি সর্বশেষ occurrence-এর index return করে।

**Syntax:**

```python
string.rfind(value, start, end)
```

উদাহরণ:

```python
text = "Python Programming"

result = text.rfind("o")

print(result)
```

**Output:**

```text
9
```

এখানে `"o"` একাধিকবার থাকলেও `rfind()` সর্বশেষ `"o"`-এর index return করেছে।

আরেকটি উদাহরণ:

```python
text = "banana"

print(text.find("a"))
print(text.rfind("a"))
```

**Output:**

```text
1
5
```

### When the Value is Not Found

```python
text = "Hello Python"

print(text.rfind("Java"))
```

**Output:**

```text
-1
```

**মনে রাখবে:**

- `find()` প্রথম occurrence খুঁজে।
- `rfind()` সর্বশেষ occurrence খুঁজে।
- না পেলে `rfind()`-ও `-1` return করে।

---

## 8. Using `rindex()` Method

`rindex()` method `index()`-এর মতো কাজ করে। তবে এটি ডান দিক থেকে search করে সর্বশেষ occurrence-এর index return করে।

**Syntax:**

```python
string.rindex(value, start, end)
```

উদাহরণ:

```python
text = "banana"

result = text.rindex("a")

print(result)
```

**Output:**

```text
5
```

এখানে সর্বশেষ `"a"`-এর index হলো `5`।

আরেকটি উদাহরণ:

```python
text = "Python Programming"

print(text.index("o"))
print(text.rindex("o"))
```

**Output:**

```text
4
9
```

### When the Value is Not Found

`rindex()` কোনো value খুঁজে না পেলে `ValueError` দেয়।

```python
text = "Hello Python"

print(text.rindex("Java"))
```

**Output:**

```text
ValueError: substring not found
```

**মনে রাখবে:**

- `index()` প্রথম occurrence খুঁজে।
- `rindex()` সর্বশেষ occurrence খুঁজে।
- না পেলে দুটোই `ValueError` দেয়।

---

## 9. Using `in` Operator

`in` operator ব্যবহার করে কোনো character বা word String-এর মধ্যে আছে কি না পরীক্ষা করা যায়।

এটি Boolean value return করে।

উদাহরণ:

```python
text = "I love Python"

print("Python" in text)
print("Java" in text)
```

**Output:**

```text
True
False
```

এখানে:

- `"Python"` String-এর মধ্যে আছে, তাই `True`।
- `"Java"` নেই, তাই `False`।

আরেকটি উদাহরণ:

```python
text = "Bangladesh"

if "land" in text:
    print("Found")
else:
    print("Not Found")
```

**Output:**

```text
Found
```

**মনে রাখবে:** `in` operator দিয়ে String-এর মধ্যে কোনো value আছে কি না সহজেই পরীক্ষা করা যায়।

---

## 10. Using `not in` Operator

`not in` operator পরীক্ষা করে কোনো character বা word String-এর মধ্যে নেই কি না।

- না থাকলে `True`।
- থাকলে `False`।

উদাহরণ:

```python
text = "Python Programming"

print("Java" not in text)
print("Python" not in text)
```

**Output:**

```text
True
False
```

আরেকটি উদাহরণ:

```python
email = "masum@gmail.com"

if "@" not in email:
    print("Invalid Email")
else:
    print("Email contains @")
```

**Output:**

```text
Email contains @
```

**মনে রাখবে:** `not in` হলো `in`-এর বিপরীত।

---

## 11. Difference Between Searching Methods

Python-এর গুরুত্বপূর্ণ String searching method-গুলোর পার্থক্য:

| Method | কাজ | Value না পেলে |
|---|---|---|
| `find()` | প্রথম occurrence খোঁজে | `-1` |
| `index()` | প্রথম occurrence খোঁজে | `ValueError` |
| `rfind()` | শেষ occurrence খোঁজে | `-1` |
| `rindex()` | শেষ occurrence খোঁজে | `ValueError` |
| `count()` | মোট occurrence গণনা করে | `0` |

উদাহরণ:

```python
text = "banana"

print(text.find("a"))
print(text.index("a"))
print(text.rfind("a"))
print(text.rindex("a"))
print(text.count("a"))
```

**Output:**

```text
1
1
5
5
3
```

---

## 12. Difference Between `startswith()` and `endswith()`

এই দুটি method String-এর নির্দিষ্ট অংশ পরীক্ষা করার জন্য ব্যবহৃত হয়।

| `startswith()` | `endswith()` |
|---|---|
| String-এর শুরু পরীক্ষা করে | String-এর শেষ পরীক্ষা করে |
| Prefix check করে | Suffix check করে |
| `True` অথবা `False` দেয় | `True` অথবা `False` দেয় |

উদাহরণ:

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

---

## 13. Case-Sensitive Searching

Python-এর String searching method-গুলো case-sensitive।

অর্থাৎ uppercase এবং lowercase character আলাদা হিসেবে বিবেচিত হয়।

উদাহরণ:

```python
text = "Python"

print(text.find("P"))
print(text.find("p"))
print("PYTHON" in text)
```

**Output:**

```text
0
-1
False
```

### Case-Insensitive Searching

Case-sensitive সমস্যা এড়াতে `lower()` অথবা `upper()` ব্যবহার করা যায়।

উদাহরণ:

```python
text = "Python Programming"

result = "python" in text.lower()

print(result)
```

**Output:**

```text
True
```

এখানে:

- `lower()` পুরো String-কে lowercase করেছে।
- তারপর `"python"` খোঁজা হয়েছে।

আরেকটি উদাহরণ:

```python
text = "Python Programming"

result = "PYTHON" in text.upper()

print(result)
```

**Output:**

```text
True
```

**মনে রাখবে:** Case-insensitive search করতে দুই পাশের text-কে একই case-এ convert করতে হবে।

---

## 14. Using Multiple Search Methods Together

একটি String-এর মধ্যে বিভিন্ন method একসঙ্গে ব্যবহার করা যায়।

উদাহরণ:

```python
text = "Python is easy and Python is powerful"

print("Position:", text.find("Python"))
print("Count:", text.count("Python"))
print("Starts with Python:", text.startswith("Python"))
print("Ends with powerful:", text.endswith("powerful"))
```

**Output:**

```text
Position: 0
Count: 2
Starts with Python: True
Ends with powerful: True
```

---

## 15. Common Mistakes

### Mistake 1: Thinking `find()` Gives an Error

```python
text = "Hello"

print(text.find("Python"))
```

**Output:**

```text
-1
```

`find()` value না পেলে error দেয় না। এটি `-1` return করে।

### Mistake 2: Forgetting That `index()` Gives an Error

```python
text = "Hello"

print(text.index("Python"))
```

**Output:**

```text
ValueError: substring not found
```

`index()` value না পেলে `ValueError` দেয়।

### Mistake 3: Ignoring Case Sensitivity

```python
text = "Python"

print(text.find("python"))
```

**Output:**

```text
-1
```

কারণ `"Python"` এবং `"python"` এক নয়।

সঠিক পদ্ধতি:

```python
text = "Python"

print(text.lower().find("python"))
```

**Output:**

```text
0
```

### Mistake 4: Confusing `find()` and `rfind()`

```python
text = "banana"

print(text.find("a"))
print(text.rfind("a"))
```

**Output:**

```text
1
5
```

`find()` প্রথম occurrence এবং `rfind()` শেষ occurrence return করে।

### Mistake 5: Confusing `count()` with `find()`

```python
text = "banana"

print(text.find("a"))
print(text.count("a"))
```

**Output:**

```text
1
3
```

`find()` position return করে, আর `count()` মোট সংখ্যা return করে।

---

## 16. Important Rules to Remember

1. `find()` প্রথম occurrence-এর index return করে।
2. `find()` value না পেলে `-1` return করে।
3. `index()` প্রথম occurrence-এর index return করে।
4. `index()` value না পেলে `ValueError` দেয়।
5. `count()` কোনো value কতবার আছে তা গণনা করে।
6. `startswith()` String-এর শুরু পরীক্ষা করে।
7. `endswith()` String-এর শেষ পরীক্ষা করে।
8. `rfind()` সর্বশেষ occurrence-এর index return করে।
9. `rindex()` সর্বশেষ occurrence-এর index return করে।
10. `rfind()` value না পেলে `-1` return করে।
11. `rindex()` value না পেলে `ValueError` দেয়।
12. `in` operator value আছে কি না পরীক্ষা করে।
13. `not in` operator value নেই কি না পরীক্ষা করে।
14. Searching methods সাধারণত case-sensitive।
15. Case-insensitive search করতে `lower()` বা `upper()` ব্যবহার করা যায়।

---

## 17. Practice Exercises

### Practice 1: Find a Word

একটি String-এর মধ্যে `"Python"` word-এর position বের করো।

**Solution:**

```python
text = "I love Python"

print(text.find("Python"))
```

**Output:**

```text
7
```

### Practice 2: Check a Missing Word

String-এর মধ্যে `"Java"` আছে কি না `find()` দিয়ে পরীক্ষা করো।

**Solution:**

```python
text = "I love Python"

print(text.find("Java"))
```

**Output:**

```text
-1
```

### Practice 3: Use `index()`

একটি String-এর মধ্যে `"Programming"` word-এর position বের করো।

**Solution:**

```python
text = "Python Programming"

print(text.index("Programming"))
```

**Output:**

```text
7
```

### Practice 4: Count Characters

একটি String-এর মধ্যে `"a"` কতবার আছে তা বের করো।

**Solution:**

```python
text = "banana"

print(text.count("a"))
```

**Output:**

```text
3
```

### Practice 5: Check the Starting Word

String `"Python Programming"` কি `"Python"` দিয়ে শুরু হয়েছে?

**Solution:**

```python
text = "Python Programming"

print(text.startswith("Python"))
```

**Output:**

```text
True
```

### Practice 6: Check the Ending Word

String `"Python Programming"` কি `"Programming"` দিয়ে শেষ হয়েছে?

**Solution:**

```python
text = "Python Programming"

print(text.endswith("Programming"))
```

**Output:**

```text
True
```

### Practice 7: Find the Last Occurrence

একটি String-এর মধ্যে `"a"`-এর সর্বশেষ position বের করো।

**Solution:**

```python
text = "banana"

print(text.rfind("a"))
```

**Output:**

```text
5
```

### Practice 8: Use `in` Operator

একটি String-এর মধ্যে `"Python"` আছে কি না পরীক্ষা করো।

**Solution:**

```python
text = "I love Python"

print("Python" in text)
```

**Output:**

```text
True
```

### Practice 9: Use `not in` Operator

একটি String-এর মধ্যে `"Java"` নেই কি না পরীক্ষা করো।

**Solution:**

```python
text = "I love Python"

print("Java" not in text)
```

**Output:**

```text
True
```

### Practice 10: Case-Insensitive Search

String-এর মধ্যে `"python"` খুঁজে বের করো, যেখানে মূল String-এ `"Python"` লেখা আছে।

**Solution:**

```python
text = "I Love Python"

result = "python" in text.lower()

print(result)
```

**Output:**

```text
True
```

### Practice 11: Find and Count Together

একটি String-এর মধ্যে `"o"`-এর প্রথম position এবং মোট সংখ্যা বের করো।

**Solution:**

```python
text = "Python Programming"

print("Position:", text.find("o"))
print("Count:", text.count("o"))
```

**Output:**

```text
Position: 4
Count: 2
```

### Practice 12: Check File Extension

একটি File-এর নাম `.pdf` দিয়ে শেষ হয়েছে কি না পরীক্ষা করো।

**Solution:**

```python
filename = "assignment.pdf"

if filename.endswith(".pdf"):
    print("PDF File")
else:
    print("Other File")
```

**Output:**

```text
PDF File
```

---

## 18. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `find()` দিয়ে character বা word খোঁজা।
- `index()` দিয়ে character বা word-এর position বের করা।
- `count()` দিয়ে occurrence গণনা করা।
- `startswith()` দিয়ে String-এর শুরু পরীক্ষা করা।
- `endswith()` দিয়ে String-এর শেষ পরীক্ষা করা।
- `rfind()` দিয়ে শেষ occurrence খোঁজা।
- `rindex()` দিয়ে শেষ occurrence-এর position বের করা।
- `in` এবং `not in` operator ব্যবহার করা।
- Case-sensitive এবং case-insensitive searching।
- বিভিন্ন Searching Method-এর পার্থক্য।

---

## 19. Self-Assessment Checklist

নিজেকে যাচাই করো:

- [ ] `find()` ব্যবহার করতে পারি।
- [ ] `index()` ব্যবহার করতে পারি।
- [ ] `find()` এবং `index()`-এর পার্থক্য বুঝতে পেরেছি।
- [ ] `count()` দিয়ে occurrence গণনা করতে পারি।
- [ ] `startswith()` ব্যবহার করতে পারি।
- [ ] `endswith()` ব্যবহার করতে পারি।
- [ ] `rfind()` এবং `rindex()` ব্যবহার করতে পারি।
- [ ] `in` এবং `not in` operator ব্যবহার করতে পারি।
- [ ] Case-sensitive searching বুঝতে পেরেছি।
- [ ] Case-insensitive searching করতে পারি।

---

## 20. Next Topic

পরবর্তী topic-এ আমরা শিখব:

**44. String Methods for Checking Character Types**

এখানে String-এর মধ্যে alphabet, digit, lowercase, uppercase এবং অন্যান্য character type পরীক্ষা করার জন্য `isalpha()`, `isdigit()`, `isalnum()`, `islower()`, `isupper()`, `isspace()` ইত্যাদি method শিখব।
