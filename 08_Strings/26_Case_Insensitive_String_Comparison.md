
# 26. Case-Insensitive String Comparison in Python

## 1. Introduction to Case-Insensitive Comparison

Python-এ সাধারণ String Comparison করার সময় uppercase এবং lowercase letters-কে আলাদা হিসেবে বিবেচনা করা হয়।

যেমন:

```python
text1 = "Python"
text2 = "PYTHON"

print(text1 == text2)
```

**Output:**

```text
False
```

**Explanation:**

এখানে দুটি String-এর text একই হলেও তাদের letter case আলাদা। তাই Python তাদের সমান মনে করে না।

কিন্তু অনেক সময় আমরা চাই uppercase এবং lowercase-এর পার্থক্য বিবেচনা না করেই দুটি String compare করতে।

এই পদ্ধতিকে **Case-Insensitive String Comparison** বলা হয়।

## 2. Using lower() for Case-Insensitive Comparison

`lower()` method ব্যবহার করে দুটি String-কে lowercase করে compare করা যায়।

**Syntax:**

```python
string1.lower() == string2.lower()
```

**Example:**

```python
text1 = "Python"
text2 = "PYTHON"

if text1.lower() == text2.lower():
    print("Strings are equal")
else:
    print("Strings are different")
```

**Output:**

```text
Strings are equal
```

**Explanation:**

- `text1.lower()` প্রথম String-কে lowercase করে।
- `text2.lower()` দ্বিতীয় String-কে lowercase করে।
- এরপর দুটি String compare করা হয়।
- তাদের text একই হলে `True` পাওয়া যায়।

## 3. Using upper() for Case-Insensitive Comparison

`upper()` method ব্যবহার করেও একই কাজ করা যায়।

এক্ষেত্রে দুটি String-কে uppercase করে compare করা হয়।

**Example:**

```python
text1 = "Hello"
text2 = "HELLO"

if text1.upper() == text2.upper():
    print("Strings are equal")
else:
    print("Strings are different")
```

**Output:**

```text
Strings are equal
```

**Explanation:**

দুটি String-কে uppercase করার পর compare করা হয়েছে। তাই letter case আলাদা হলেও তাদের সমান হিসেবে পাওয়া গেছে।

## 4. Comparing Strings with Different Cases

নিচের উদাহরণগুলো লক্ষ্য করো।

**Example 1:**

```python
text1 = "Python"
text2 = "python"

print(text1.lower() == text2.lower())
```

**Output:**

```text
True
```

**Example 2:**

```python
text1 = "HELLO"
text2 = "hello"

print(text1.lower() == text2.lower())
```

**Output:**

```text
True
```

**Example 3:**

```python
text1 = "Python"
text2 = "Java"

print(text1.lower() == text2.lower())
```

**Output:**

```text
False
```

**Explanation:**

প্রথম দুটি ক্ষেত্রে letter case আলাদা হলেও text একই। তাই `True` পাওয়া যায়।

তৃতীয় ক্ষেত্রে text আলাদা হওয়ায় `False` পাওয়া যায়।

## 5. Case-Insensitive Comparison with User Input

User-এর কাছ থেকে পাওয়া input compare করার সময় Case-Insensitive Comparison ব্যবহার করা যায়।

**Example:**

```python
password = "Python123"

user_input = input("Enter password: ")

if user_input.lower() == password.lower():
    print("Password matched")
else:
    print("Password not matched")
```

**Input:**

```text
PYTHON123
```

**Output:**

```text
Password matched
```

**Explanation:**

এখানে user uppercase বা lowercase যেভাবেই input দিক না কেন, comparison করার আগে দুটি String lowercase করা হচ্ছে।

**Note:** এটি শুধু Case-Insensitive Comparison বোঝানোর উদাহরণ। বাস্তব password comparison সাধারণত case-sensitive হওয়া উচিত।

## 6. Using casefold() for Case-Insensitive Comparison

Python-এ `casefold()` নামে আরেকটি String method রয়েছে।

এটি Case-Insensitive Comparison-এর জন্য বিশেষভাবে তৈরি করা হয়েছে।

**Syntax:**

```python
string.casefold()
```

**Example:**

```python
text1 = "Python"
text2 = "PYTHON"

print(text1.casefold() == text2.casefold())
```

**Output:**

```text
True
```

**Explanation:**

- `casefold()` String-এর case এমনভাবে পরিবর্তন করে যাতে case-insensitive comparison করা সহজ হয়।
- এটি `lower()`-এর তুলনায় কিছু Unicode character-এর ক্ষেত্রে বেশি কার্যকর।
- সাধারণ English text comparison-এর জন্য `lower()` এবং `casefold()` উভয়ই ব্যবহার করা যায়।

## 7. Difference Between lower() and casefold()

দুটি method দেখতে কাছাকাছি হলেও তাদের মধ্যে কিছু পার্থক্য রয়েছে।

| lower() | casefold() |
|---|---|
| String lowercase করে | Case-insensitive comparison-এর জন্য case পরিবর্তন করে |
| সাধারণ text-এর জন্য useful | Unicode text comparison-এর জন্য বেশি suitable |
| কিছু Unicode character-এর ক্ষেত্রে আলাদা ফল দিতে পারে | আরও aggressive case conversion করে |

**Example:**

```python
text = "Straße"

print(text.lower())
print(text.casefold())
```

**Output:**

```text
straße
strasse
```

**Explanation:**

এখানে `casefold()` German character `ß`-কে `ss`-এ রূপান্তর করেছে।

তাই সাধারণ English text-এর জন্য `lower()` যথেষ্ট হলেও Unicode text-এর ক্ষেত্রে `casefold()` বেশি উপযোগী হতে পারে।

## 8. Checking Whether Two Names Are Equal

Case-Insensitive Comparison ব্যবহার করে দুটি নাম compare করা যায়।

**Example:**

```python
name1 = "Masum"
name2 = "MASUM"

if name1.casefold() == name2.casefold():
    print("Same name")
else:
    print("Different names")
```

**Output:**

```text
Same name
```

**Explanation:**

দুটি নামের letter case আলাদা হলেও text একই। তাই `casefold()` ব্যবহার করে তাদের সমান পাওয়া গেছে।

## 9. Case-Insensitive Searching

একটি String-এর মধ্যে নির্দিষ্ট word খোঁজার সময়ও Case-Insensitive Comparison ব্যবহার করা যায়।

**Example:**

```python
text = "Python is easy to learn"
target = "PYTHON"

if target.lower() in text.lower():
    print("Word found")
else:
    print("Word not found")
```

**Output:**

```text
Word found
```

**Explanation:**

- `text.lower()` পুরো sentence-কে lowercase করে।
- `target.lower()` search করার word-টিকেও lowercase করে।
- এরপর `in` operator দিয়ে word-টি আছে কি না পরীক্ষা করা হয়।

## 10. Common Mistakes in Case-Insensitive Comparison

### Mistake 1: Comparing Strings Directly

**Incorrect Code:**

```python
text1 = "Python"
text2 = "PYTHON"

print(text1 == text2)
```

**Output:**

```text
False
```

**Why?**

Python uppercase এবং lowercase letters-কে আলাদা হিসেবে বিবেচনা করে।

**Correct Code:**

```python
text1 = "Python"
text2 = "PYTHON"

print(text1.lower() == text2.lower())
```

**Output:**

```text
True
```

### Mistake 2: Forgetting Parentheses

**Incorrect Code:**

```python
text1 = "Hello"
text2 = "HELLO"

print(text1.lower == text2.lower)
```

**Output:**

```text
False
```

**Why?**

এখানে `lower` method call করা হয়নি। Method call করার জন্য `()` ব্যবহার করতে হয়।

**Correct Code:**

```python
text1 = "Hello"
text2 = "HELLO"

print(text1.lower() == text2.lower())
```

**Output:**

```text
True
```

### Mistake 3: Converting Only One String

**Incorrect Code:**

```python
text1 = "Python"
text2 = "PYTHON"

print(text1.lower() == text2)
```

**Output:**

```text
False
```

**Why?**

প্রথম String lowercase করা হয়েছে, কিন্তু দ্বিতীয় String uppercase অবস্থায় রয়েছে।

**Correct Code:**

```python
text1 = "Python"
text2 = "PYTHON"

print(text1.lower() == text2.lower())
```

**Output:**

```text
True
```

## 11. Practical Examples

### Example 1: Checking a Username

```python
correct_username = "Masum"

entered_username = input("Enter username: ")

if entered_username.casefold() == correct_username.casefold():
    print("Username matched")
else:
    print("Username not matched")
```

**Input:**

```text
MASUM
```

**Output:**

```text
Username matched
```

### Example 2: Checking a Word in a Sentence

```python
sentence = "I Love Python Programming"
word = "python"

if word.casefold() in sentence.casefold():
    print("Word exists")
else:
    print("Word does not exist")
```

**Output:**

```text
Word exists
```

### Example 3: Comparing Two Email Texts

```python
email1 = "Masum@gmail.com"
email2 = "MASUM@GMAIL.COM"

if email1.casefold() == email2.casefold():
    print("Emails are equal")
else:
    print("Emails are different")
```

**Output:**

```text
Emails are equal
```

**Note:** এটি সাধারণ text comparison-এর উদাহরণ। বাস্তবে email address-এর local part এবং domain-এর case-handling নিয়ম এক নয়; তাই সব ক্ষেত্রে পুরো email-কে case-insensitive ধরে নেওয়া উচিত নয়।

## 12. Important Rules to Remember

1. Python-এর সাধারণ String Comparison case-sensitive।
2. `"Python"` এবং `"PYTHON"` সরাসরি compare করলে `False` পাওয়া যায়।
3. Case-Insensitive Comparison-এর জন্য `lower()` ব্যবহার করা যায়।
4. `upper()` ব্যবহার করেও case-insensitive comparison করা যায়।
5. `casefold()` বিশেষভাবে case-insensitive comparison-এর জন্য তৈরি।
6. Unicode text comparison-এর ক্ষেত্রে `casefold()` বেশি কার্যকর হতে পারে।
7. Comparison করার আগে উভয় String-এর case একইভাবে পরিবর্তন করতে হবে।
8. `lower()`, `upper()` এবং `casefold()` মূল String পরিবর্তন করে না।
9. `()` ছাড়া method call হয় না।
10. Password comparison সাধারণত case-sensitive রাখা উচিত।

## 13. Practice Problems

### Problem 1: Compare Two Strings

```python
text1 = "Python"
text2 = "PYTHON"

# Compare both strings without considering case
```

**Expected Output:**

```text
True
```

### Problem 2: Compare Two Names

```python
name1 = "Masum"
name2 = "masum"

# Check whether both names are equal without considering case
```

**Expected Output:**

```text
Names are equal
```

### Problem 3: Search for a Word

```python
sentence = "Python is a powerful language"
word = "PYTHON"

# Search for the word without considering case
```

**Expected Output:**

```text
Word found
```

### Problem 4: Compare Different Strings

```python
text1 = "Python"
text2 = "Java"

# Compare both strings without considering case
```

**Expected Output:**

```text
False
```

### Problem 5: Use casefold()

```python
text1 = "Straße"
text2 = "STRASSE"

# Compare both strings using casefold()
```

**Expected Output:**

```text
True
```

### Problem 6: Username Comparison

```python
correct_username = "Masum"
entered_username = "MASUM"

# Check whether the username matches without considering case
```

**Expected Output:**

```text
Username matched
```

## 14. Chapter Summary

এই Topic-এ আমরা Case-Insensitive String Comparison সম্পর্কে শিখেছি।

আমরা শিখেছি:

- Case-Sensitive এবং Case-Insensitive Comparison
- `lower()` দিয়ে String comparison
- `upper()` দিয়ে String comparison
- `casefold()` method
- `lower()` এবং `casefold()`-এর পার্থক্য
- Case-Insensitive Searching
- Practical examples এবং common mistakes

**Next Topic:**

`27_Removing_Whitespace_with_strip_methods.md`

পরবর্তী Topic-এ আমরা `strip()`, `lstrip()` এবং `rstrip()` ব্যবহার করে String-এর অপ্রয়োজনীয় whitespace remove করা শিখব।
