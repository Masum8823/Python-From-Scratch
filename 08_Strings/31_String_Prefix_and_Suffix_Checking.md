
# 31. String Prefix and Suffix Checking in Python

## 1. Introduction to Prefix and Suffix Checking

Python-এ কোনো String নির্দিষ্ট কোনো Text দিয়ে শুরু হয়েছে কি না অথবা শেষ হয়েছে কি না তা পরীক্ষা করার জন্য `startswith()` এবং `endswith()` method ব্যবহার করা হয়।

- **Prefix:** কোনো String-এর শুরুর অংশ।
- **Suffix:** কোনো String-এর শেষের অংশ।

**Example:**

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

- `startswith("Python")` পরীক্ষা করেছে String-টি `"Python"` দিয়ে শুরু হয়েছে কি না।
- `endswith("Programming")` পরীক্ষা করেছে String-টি `"Programming"` দিয়ে শেষ হয়েছে কি না।
- দুটি Condition-ই সত্য হওয়ায় Output `True` এসেছে।

## 2. startswith() Method

কোনো String নির্দিষ্ট Text দিয়ে শুরু হয়েছে কি না তা পরীক্ষা করতে `startswith()` method ব্যবহার করা হয়।

**Syntax:**

```python
string.startswith(prefix)
```

**Explanation:**

| Part | Description |
|---|---|
| `string` | যে String পরীক্ষা করা হবে |
| `startswith()` | শুরুতে নির্দিষ্ট Text আছে কি না পরীক্ষা করে |
| `prefix` | যে Text দিয়ে শুরু হওয়ার কথা |

**Example:**

```python
text = "Hello Python"

result = text.startswith("Hello")

print(result)
```

**Output:**

```text
True
```

**Explanation:**

String-টি `"Hello"` দিয়ে শুরু হয়েছে। তাই `True` Return করেছে।

## 3. Checking Different Prefixes

একই String-এর জন্য বিভিন্ন Prefix পরীক্ষা করা যায়।

**Example:**

```python
text = "Python Programming"

print(text.startswith("Python"))
print(text.startswith("Program"))
print(text.startswith("Java"))
```

**Output:**

```text
True
False
False
```

**Explanation:**

- `"Python"` দিয়ে শুরু হয়েছে, তাই `True`।
- `"Program"` String-এর মধ্যে থাকলেও শুরুতে নেই, তাই `False`।
- `"Java"` String-এর শুরুতে নেই, তাই `False`।

**Important Note:** `startswith()` পুরো String-এর শুরু থেকে পরীক্ষা করে। মাঝখানে কোনো Text থাকলে `True` Return করে না।

## 4. endswith() Method

কোনো String নির্দিষ্ট Text দিয়ে শেষ হয়েছে কি না তা পরীক্ষা করতে `endswith()` method ব্যবহার করা হয়।

**Syntax:**

```python
string.endswith(suffix)
```

**Explanation:**

| Part | Description |
|---|---|
| `string` | যে String পরীক্ষা করা হবে |
| `endswith()` | শেষে নির্দিষ্ট Text আছে কি না পরীক্ষা করে |
| `suffix` | যে Text দিয়ে শেষ হওয়ার কথা |

**Example:**

```python
text = "I love Python"

result = text.endswith("Python")

print(result)
```

**Output:**

```text
True
```

**Explanation:**

String-টি `"Python"` দিয়ে শেষ হয়েছে। তাই `True` Return করেছে।

## 5. Checking Different Suffixes

একই String-এর জন্য বিভিন্ন Suffix পরীক্ষা করা যায়।

**Example:**

```python
filename = "notes.txt"

print(filename.endswith(".txt"))
print(filename.endswith(".pdf"))
print(filename.endswith("notes"))
```

**Output:**

```text
True
False
False
```

**Explanation:**

- `.txt` দিয়ে শেষ হয়েছে, তাই `True`।
- `.pdf` দিয়ে শেষ হয়নি, তাই `False`।
- `notes` শুরুতে আছে, শেষে নেই। তাই `False`।

## 6. Case-Sensitive Checking

`startswith()` এবং `endswith()` Case-Sensitive।

অর্থাৎ, Uppercase এবং Lowercase Character আলাদাভাবে বিবেচনা করা হয়।

**Example:**

```python
text = "Python Programming"

print(text.startswith("Python"))
print(text.startswith("python"))

print(text.endswith("Programming"))
print(text.endswith("programming"))
```

**Output:**

```text
True
False
True
False
```

**Explanation:**

- `"Python"` এবং `"python"` এক নয়।
- `"Programming"` এবং `"programming"` এক নয়।
- তাই Case পরিবর্তন করলে Result `False` হতে পারে।

## 7. Case-Insensitive Prefix and Suffix Checking

Case-Sensitive সমস্যা এড়াতে `lower()` অথবা `upper()` ব্যবহার করা যায়।

**Example:**

```python
text = "Python Programming"

result = text.lower().startswith("python")

print(result)
```

**Output:**

```text
True
```

**Explanation:**

- `lower()` পুরো String-কে Lowercase করেছে।
- এরপর `startswith()` দিয়ে Prefix পরীক্ষা করা হয়েছে।
- তাই Uppercase বা Lowercase-এর পার্থক্য থাকেনি।

**Another Example:**

```python
filename = "Document.PDF"

result = filename.lower().endswith(".pdf")

print(result)
```

**Output:**

```text
True
```

## 8. Using start and end Parameters

`startswith()` এবং `endswith()` method-এ নির্দিষ্ট Index থেকে পরীক্ষা করার জন্য `start` এবং `end` Parameter ব্যবহার করা যায়।

**Syntax:**

```python
string.startswith(prefix, start, end)

string.endswith(suffix, start, end)
```

| Parameter | Description |
|---|---|
| `prefix` / `suffix` | যে Text পরীক্ষা করা হবে |
| `start` | যে Index থেকে পরীক্ষা শুরু হবে |
| `end` | যে Index পর্যন্ত পরীক্ষা হবে |

**Example with startswith():**

```python
text = "Hello Python"

print(text.startswith("Python", 6))
```

**Output:**

```text
True
```

**Explanation:**

- `"Python"` শুরু হয়েছে Index `6` থেকে।
- তাই Index `6` থেকে পরীক্ষা করলে `True` পাওয়া যায়।

**Example with endswith():**

```python
text = "Hello Python"

print(text.endswith("Hello", 0, 5))
```

**Output:**

```text
True
```

**Explanation:**

- এখানে Index `0` থেকে `5` পর্যন্ত অংশ পরীক্ষা করা হয়েছে।
- এই অংশ হলো `"Hello"`।
- তাই Result `True`।

**Important Note:** `end` Index অন্তর্ভুক্ত হয় না।

## 9. Checking Multiple Prefixes Using Tuple

একটি String একাধিক Prefix-এর যেকোনো একটি দিয়ে শুরু হয়েছে কি না তা পরীক্ষা করতে Tuple ব্যবহার করা যায়।

**Example:**

```python
filename = "report.pdf"

result = filename.startswith(("report", "document", "notes"))

print(result)
```

**Output:**

```text
True
```

**Explanation:**

- Tuple-এর মধ্যে তিনটি Prefix রয়েছে।
- String-টি `"report"` দিয়ে শুরু হয়েছে।
- তাই Result `True`।

**Another Example:**

```python
text = "Python Programming"

print(text.startswith(("Java", "C++", "Python")))
```

**Output:**

```text
True
```

**Note:** Tuple-এর যেকোনো একটি Prefix Match করলেই `True` Return করবে।

## 10. Checking Multiple Suffixes Using Tuple

একটি String একাধিক Suffix-এর যেকোনো একটি দিয়ে শেষ হয়েছে কি না তা পরীক্ষা করতে Tuple ব্যবহার করা যায়।

**Example:**

```python
filename = "photo.png"

result = filename.endswith((".jpg", ".png", ".gif"))

print(result)
```

**Output:**

```text
True
```

**Explanation:**

- Tuple-এর মধ্যে তিনটি File Extension রয়েছে।
- `"photo.png"` এর শেষে `.png` রয়েছে।
- তাই Result `True`।

**Another Example:**

```python
filename = "notes.pdf"

print(filename.endswith((".txt", ".pdf", ".docx")))
```

**Output:**

```text
True
```

## 11. Using startswith() with if-else

`startswith()` ব্যবহার করে Condition তৈরি করা যায়।

**Example:**

```python
name = "Masum"

if name.startswith("M"):
    print("Name starts with M")
else:
    print("Name does not start with M")
```

**Output:**

```text
Name starts with M
```

**Explanation:**

- প্রথমে পরীক্ষা করা হয়েছে Name `M` দিয়ে শুরু হয়েছে কি না।
- Condition সত্য হওয়ায় `if` Block Execute হয়েছে।

## 12. Using endswith() with if-else

`endswith()` ব্যবহার করেও Condition তৈরি করা যায়।

**Example:**

```python
filename = "assignment.pdf"

if filename.endswith(".pdf"):
    print("PDF file detected")
else:
    print("Not a PDF file")
```

**Output:**

```text
PDF file detected
```

**Explanation:**

- File Name-এর শেষে `.pdf` রয়েছে।
- তাই `if` Block Execute হয়েছে।

## 13. Practical Examples

### Example 1: Checking Student Name Prefix

```python
name = "Masum"

if name.startswith("M"):
    print("Name starts with M")
else:
    print("Name does not start with M")
```

**Output:**

```text
Name starts with M
```

### Example 2: Checking File Extension

```python
filename = "python_notes.txt"

if filename.endswith(".txt"):
    print("Text file")
else:
    print("Other file")
```

**Output:**

```text
Text file
```

### Example 3: Checking Website Protocol

```python
website = "https://www.python.org"

if website.startswith("https://"):
    print("Secure website")
else:
    print("Other website")
```

**Output:**

```text
Secure website
```

### Example 4: Checking Image File Extensions

```python
filename = "profile.jpg"

if filename.endswith((".jpg", ".png", ".jpeg")):
    print("Image file")
else:
    print("Not an image file")
```

**Output:**

```text
Image file
```

### Example 5: Checking Email Domain

```python
email = "masum@gmail.com"

if email.endswith("@gmail.com"):
    print("Gmail account")
else:
    print("Other email account")
```

**Output:**

```text
Gmail account
```

## 14. Difference Between startswith() and endswith()

`startswith()` এবং `endswith()` উভয়ই String-এর নির্দিষ্ট অংশ পরীক্ষা করে। তবে তাদের কাজ আলাদা।

| startswith() | endswith() |
|---|---|
| String-এর শুরু পরীক্ষা করে | String-এর শেষ পরীক্ষা করে |
| Prefix Check করে | Suffix Check করে |
| শুরুতে Match খোঁজে | শেষে Match খোঁজে |
| `text.startswith("Py")` | `text.endswith("on")` |

**Example:**

```python
text = "Python"

print(text.startswith("Py"))
print(text.endswith("on"))
```

**Output:**

```text
True
True
```

## 15. Common Mistakes

### Mistake 1: Incorrect Case

**Incorrect Code:**

```python
text = "Python"

print(text.startswith("python"))
```

**Output:**

```text
False
```

**Why?**

`startswith()` Case-Sensitive। তাই `"Python"` এবং `"python"` আলাদা।

**Correct Code:**

```python
text = "Python"

print(text.lower().startswith("python"))
```

**Output:**

```text
True
```

### Mistake 2: Checking Text in the Middle

**Example:**

```python
text = "I love Python"

print(text.startswith("love"))
```

**Output:**

```text
False
```

**Why?**

`"love"` String-এর মধ্যে রয়েছে, কিন্তু শুরুতে নেই।

### Mistake 3: Using Integer Instead of String

**Incorrect Code:**

```python
text = "12345"

print(text.startswith(123))
```

**Output:**

```text
TypeError
```

**Why?**

`startswith()`-এ Prefix হিসেবে String দিতে হয়।

**Correct Code:**

```python
text = "12345"

print(text.startswith("123"))
```

**Output:**

```text
True
```

### Mistake 4: Forgetting the Dot in File Extensions

**Example:**

```python
filename = "notes.txt"

print(filename.endswith("txt"))
print(filename.endswith(".txt"))
```

**Output:**

```text
True
True
```

**Explanation:**

দুটি ক্ষেত্রেই Match হয়েছে। কারণ `endswith()` শুধু শেষের Text পরীক্ষা করে। তবে File Extension যাচাই করার ক্ষেত্রে `.txt` ব্যবহার করা বেশি পরিষ্কার।

## 16. Important Rules to Remember

1. `startswith()` String-এর শুরু পরীক্ষা করে।
2. `endswith()` String-এর শেষ পরীক্ষা করে।
3. উভয় Method Boolean Value (`True` অথবা `False`) Return করে।
4. দুটি Method-ই Case-Sensitive।
5. `lower()` বা `upper()` দিয়ে Case-Insensitive Checking করা যায়।
6. `start` এবং `end` Parameter ব্যবহার করা যায়।
7. `end` Index অন্তর্ভুক্ত হয় না।
8. একাধিক Prefix বা Suffix পরীক্ষা করতে Tuple ব্যবহার করা যায়।
9. Prefix এবং Suffix অবশ্যই String হতে হবে।
10. এই Method-গুলো Original String পরিবর্তন করে না।
11. File Extension, Website Protocol এবং Email Domain পরীক্ষা করতে এগুলো ব্যবহার করা যায়।

## 17. Practice Problems

### Problem 1: Check String Prefix

```python
text = "Python Programming"

# Check whether the string starts with "Python"
```

**Expected Output:**

```text
True
```

### Problem 2: Check String Suffix

```python
text = "I love Python"

# Check whether the string ends with "Python"
```

**Expected Output:**

```text
True
```

### Problem 3: Check File Extension

```python
filename = "assignment.pdf"

# Check whether the file ends with ".pdf"
```

**Expected Output:**

```text
True
```

### Problem 4: Case-Insensitive Checking

```python
text = "HELLO PYTHON"

# Check whether the string starts with "hello" without case sensitivity
```

**Expected Output:**

```text
True
```

### Problem 5: Check Multiple Prefixes

```python
website = "https://example.com"

# Check whether the website starts with "http://" or "https://"
```

**Expected Output:**

```text
True
```

### Problem 6: Check Multiple Suffixes

```python
filename = "photo.png"

# Check whether the file ends with ".jpg", ".png", or ".jpeg"
```

**Expected Output:**

```text
True
```

### Problem 7: Use startswith() with if-else

```python
name = "Masum"

# Print "Valid Name" if the name starts with "M"
# Otherwise, print "Invalid Name"
```

**Expected Output:**

```text
Valid Name
```

### Problem 8: Use endswith() with if-else

```python
email = "student@gmail.com"

# Print "Gmail Account" if the email ends with "@gmail.com"
# Otherwise, print "Other Email"
```

**Expected Output:**

```text
Gmail Account
```

## 18. Chapter Summary

এই Topic-এ আমরা Python-এর `startswith()` এবং `endswith()` method সম্পর্কে শিখেছি।

আমরা শিখেছি:

- Prefix এবং Suffix-এর ধারণা।
- `startswith()` Method ব্যবহার।
- `endswith()` Method ব্যবহার।
- Different Prefix এবং Suffix Checking।
- Case-Sensitive Checking।
- Case-Insensitive Checking।
- `start` এবং `end` Parameter ব্যবহার।
- Tuple দিয়ে Multiple Prefix এবং Suffix Checking।
- if-else-এর সঙ্গে Method দুটি ব্যবহার।
- Practical Examples।
- Common Mistakes এবং Important Rules।

**Next Topic:**

`32_String_Testing_Methods_isalpha_isdigit_etc.md`

পরবর্তী Topic-এ আমরা `isalpha()`, `isdigit()`, `isalnum()`, `isspace()` এবং অন্যান্য String Testing Method ব্যবহার করে String-এর Character-গুলো কী ধরনের তা পরীক্ষা করা শিখব।
