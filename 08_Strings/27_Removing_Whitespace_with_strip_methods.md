
# 27. Removing Whitespace with strip() Methods in Python

## 1. Introduction to Whitespace

Python-এ Whitespace বলতে এমন character বোঝায়, যা text-এর মধ্যে ফাঁকা জায়গা বা line break তৈরি করে।

সাধারণ Whitespace-এর উদাহরণ:

- Space (`" "`)
- Tab (`"\t"`)
- Newline (`"\n"`)

অনেক সময় User Input বা কোনো Text-এর শুরুতে কিংবা শেষে অপ্রয়োজনীয় whitespace থাকে।

এগুলো remove করার জন্য Python-এ তিনটি গুরুত্বপূর্ণ method রয়েছে:

1. `strip()`
2. `lstrip()`
3. `rstrip()`

## 2. strip() Method

`strip()` method একটি String-এর শুরু এবং শেষের whitespace remove করে।

তবে String-এর মাঝখানের whitespace remove করে না।

**Syntax:**

```python
string.strip()
```

**Example 1:**

```python
text = "   Hello Python   "

result = text.strip()

print(result)
```

**Output:**

```text
Hello Python
```

**Explanation:**

- String-এর শুরুতে থাকা whitespace remove হয়েছে।
- String-এর শেষে থাকা whitespace remove হয়েছে।
- মাঝখানের space অপরিবর্তিত রয়েছে।

**Example 2:**

```python
text = "   Python Programming   "

print(text.strip())
```

**Output:**

```text
Python Programming
```

## 3. lstrip() Method

`lstrip()` method একটি String-এর বাম পাশের অর্থাৎ শুরুর whitespace remove করে।

এটি ডান পাশের whitespace remove করে না।

**Syntax:**

```python
string.lstrip()
```

**Example:**

```python
text = "   Hello Python   "

result = text.lstrip()

print(result)
```

**Output:**

```text
Hello Python   
```

**Explanation:**

- String-এর শুরুর whitespace remove হয়েছে।
- String-এর শেষের whitespace রয়ে গেছে।
- মাঝখানের whitespace পরিবর্তন হয়নি।

## 4. rstrip() Method

`rstrip()` method একটি String-এর ডান পাশের অর্থাৎ শেষের whitespace remove করে।

এটি বাম পাশের whitespace remove করে না।

**Syntax:**

```python
string.rstrip()
```

**Example:**

```python
text = "   Hello Python   "

result = text.rstrip()

print(result)
```

**Output:**

```text
   Hello Python
```

**Explanation:**

- String-এর শেষের whitespace remove হয়েছে।
- String-এর শুরুর whitespace রয়ে গেছে।
- মাঝখানের whitespace পরিবর্তন হয়নি।

## 5. Difference Between strip(), lstrip() and rstrip()

এই তিনটি method-এর কাজ আলাদা।

| Method | কাজ |
|---|---|
| `strip()` | শুরু এবং শেষের whitespace remove করে |
| `lstrip()` | শুধু শুরুর whitespace remove করে |
| `rstrip()` | শুধু শেষের whitespace remove করে |

**Example:**

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

## 6. Removing Specific Characters with strip()

`strip()` method-এর মধ্যে নির্দিষ্ট character দিলে String-এর শুরু এবং শেষ থেকে সেই character-গুলো remove করা যায়।

**Syntax:**

```python
string.strip(chars)
```

এখানে `chars` হলো যে character-গুলো String-এর দুই পাশ থেকে remove করতে চাই।

**Example 1:**

```python
text = "###Python###"

result = text.strip("#")

print(result)
```

**Output:**

```text
Python
```

**Explanation:**

এখানে `#` character String-এর শুরু এবং শেষ থেকে remove হয়েছে।

**Example 2:**

```python
text = "xxxHello Worldxxx"

print(text.strip("x"))
```

**Output:**

```text
Hello World
```

এখানে শুধু দুই পাশের `x` character remove হয়েছে।

## 7. Removing Specific Characters with lstrip()

`lstrip()` ব্যবহার করে String-এর শুরু থেকে নির্দিষ্ট character remove করা যায়।

**Example:**

```python
text = "###Python###"

result = text.lstrip("#")

print(result)
```

**Output:**

```text
Python###
```

**Explanation:**

এখানে শুধু String-এর বাম পাশের `#` character remove হয়েছে।

## 8. Removing Specific Characters with rstrip()

`rstrip()` ব্যবহার করে String-এর শেষ থেকে নির্দিষ্ট character remove করা যায়।

**Example:**

```python
text = "###Python###"

result = text.rstrip("#")

print(result)
```

**Output:**

```text
###Python
```

**Explanation:**

এখানে শুধু String-এর ডান পাশের `#` character remove হয়েছে।

## 9. Important Note About the chars Parameter

`strip(chars)`-এর মধ্যে একাধিক character দিলে Python সেগুলোকে একটি নির্দিষ্ট substring হিসেবে বিবেচনা করে না।

বরং প্রতিটি character-কে আলাদাভাবে remove করার জন্য ব্যবহার করে।

**Example:**

```python
text = "xyPythonxy"

print(text.strip("xy"))
```

**Output:**

```text
Python
```

**Explanation:**

এখানে `"xy"` দেওয়ার অর্থ শুধু `"xy"` substring remove করা নয়।

Python String-এর শুরু এবং শেষ থেকে `x` অথবা `y` character remove করে।

**Another Example:**

```python
text = "abcPythoncba"

print(text.strip("abc"))
```

**Output:**

```text
Python
```

এখানে শুরু এবং শেষ থেকে `a`, `b` অথবা `c` character remove হয়েছে।

**Important:** `strip()` মাঝখানের character remove করে না।

## 10. Removing Newline and Tab Characters

`strip()` method ব্যবহার করে String-এর শুরু এবং শেষের newline ও tab character-ও remove করা যায়।

**Example 1: Removing Newline**

```python
text = "\nHello Python\n"

result = text.strip()

print(result)
```

**Output:**

```text
Hello Python
```

**Example 2: Removing Tab**

```python
text = "\tPython Programming\t"

result = text.strip()

print(result)
```

**Output:**

```text
Python Programming
```

**Explanation:**

- `\n` হলো Newline character।
- `\t` হলো Tab character।
- `strip()` শুরু এবং শেষের এই whitespace-গুলো remove করে।

## 11. Using strip() with User Input

User-এর কাছ থেকে Input নেওয়ার সময় অনেক ক্ষেত্রে শুরু বা শেষে অতিরিক্ত space থাকতে পারে।

`strip()` ব্যবহার করে সেগুলো remove করা যায়।

**Example:**

```python
name = input("Enter your name: ")

name = name.strip()

print("Welcome", name)
```

**Input:**

```text
   Masum   
```

**Output:**

```text
Welcome Masum
```

**Explanation:**

User-এর Input-এর শুরু এবং শেষের অতিরিক্ত whitespace remove করা হয়েছে।

## 12. strip() Does Not Modify the Original String

Python-এর String immutable। তাই `strip()`, `lstrip()` এবং `rstrip()` মূল String পরিবর্তন করে না।

এগুলো নতুন String return করে।

**Example:**

```python
text = "   Python   "

text.strip()

print(text)
```

**Output:**

```text
   Python   
```

**Explanation:**

এখানে `strip()` method ব্যবহার করা হলেও তার return value সংরক্ষণ করা হয়নি।

তাই Original String আগের মতোই রয়েছে।

**Correct Example:**

```python
text = "   Python   "

text = text.strip()

print(text)
```

**Output:**

```text
Python
```

এখানে পরিবর্তিত String আবার `text` variable-এ assign করা হয়েছে।

## 13. Difference Between strip() and replace()

`strip()` এবং `replace()` উভয়ই String থেকে কিছু character remove করতে ব্যবহার করা যায়। তবে তাদের কাজ আলাদা।

| strip() | replace() |
|---|---|
| String-এর শুরু ও শেষ থেকে character remove করতে পারে | String-এর যেকোনো জায়গায় নির্দিষ্ট text replace করতে পারে |
| মাঝখানের character remove করে না | মাঝখানের text-ও replace করতে পারে |
| নির্দিষ্ট character set গ্রহণ করে | নির্দিষ্ট substring গ্রহণ করে |

**Example 1: Using strip()**

```python
text = "###Python###"

print(text.strip("#"))
```

**Output:**

```text
Python
```

**Example 2: Using replace()**

```python
text = "Py#th#on"

print(text.replace("#", ""))
```

**Output:**

```text
Python
```

**Explanation:**

- `strip()` শুধু String-এর দুই পাশ থেকে character remove করেছে।
- `replace()` String-এর মাঝখান থেকেও `#` remove করেছে।

## 14. Common Mistakes in strip() Methods

### Mistake 1: Expecting strip() to Remove Middle Whitespace

**Incorrect Expectation:**

```python
text = "Hello   Python"

print(text.strip())
```

**Output:**

```text
Hello   Python
```

**Why?**

`strip()` শুধু শুরু এবং শেষের whitespace remove করে। মাঝখানের whitespace remove করে না।

**Correct Solution:**

```python
text = "Hello   Python"

print(text.replace(" ", ""))
```

**Output:**

```text
HelloPython
```

### Mistake 2: Confusing strip() with lstrip()

**Example:**

```python
text = "   Python   "

print(text.lstrip())
```

**Output:**

```text
Python   
```

**Why?**

`lstrip()` শুধু বাম পাশের whitespace remove করে।

দুই পাশের whitespace remove করতে `strip()` ব্যবহার করতে হবে।

### Mistake 3: Expecting strip("abc") to Remove the Exact Substring

**Example:**

```python
text = "abcPythoncba"

print(text.strip("abc"))
```

**Output:**

```text
Python
```

**Why?**

`strip("abc")` পুরো `"abc"` substring খোঁজে না। এটি `a`, `b` এবং `c` character-গুলো দুই পাশ থেকে remove করে।

## 15. Practical Examples

### Example 1: Cleaning User Input

```python
name = "   Masum   "

clean_name = name.strip()

print("Name:", clean_name)
```

**Output:**

```text
Name: Masum
```

### Example 2: Removing Special Characters from Both Sides

```python
text = "***Python***"

clean_text = text.strip("*")

print(clean_text)
```

**Output:**

```text
Python
```

### Example 3: Removing Only Leading Spaces

```python
text = "     Hello World"

clean_text = text.lstrip()

print(clean_text)
```

**Output:**

```text
Hello World
```

### Example 4: Removing Only Trailing Spaces

```python
text = "Hello World     "

clean_text = text.rstrip()

print(clean_text)
```

**Output:**

```text
Hello World
```

### Example 5: Removing Newline Characters from Text

```python
message = "\nWelcome to Python\n"

clean_message = message.strip()

print(clean_message)
```

**Output:**

```text
Welcome to Python
```

## 16. Important Rules to Remember

1. `strip()` String-এর শুরু এবং শেষের whitespace remove করে।
2. `lstrip()` শুধু বাম পাশের whitespace remove করে।
3. `rstrip()` শুধু ডান পাশের whitespace remove করে।
4. এই methods মাঝখানের whitespace remove করে না।
5. `strip(chars)` নির্দিষ্ট character দুই পাশ থেকে remove করতে পারে।
6. `strip(chars)` character-গুলোকে আলাদাভাবে বিবেচনা করে।
7. `strip()` দিয়ে space, tab এবং newline remove করা যায়।
8. এই methods নতুন String return করে।
9. Original String পরিবর্তন হয় না।
10. মাঝখানের নির্দিষ্ট text remove করতে `replace()` ব্যবহার করা যায়।

## 17. Practice Problems

### Problem 1: Remove Both Side Whitespace

```python
text = "   Python Programming   "

# Remove whitespace from both sides
```

**Expected Output:**

```text
Python Programming
```

### Problem 2: Remove Left Whitespace

```python
text = "     Hello Python"

# Remove whitespace from the left side
```

**Expected Output:**

```text
Hello Python
```

### Problem 3: Remove Right Whitespace

```python
text = "Hello Python     "

# Remove whitespace from the right side
```

**Expected Output:**

```text
Hello Python
```

### Problem 4: Remove Special Characters

```python
text = "###Bangladesh###"

# Remove # from both sides
```

**Expected Output:**

```text
Bangladesh
```

### Problem 5: Remove Newline Characters

```python
text = "\nWelcome to Python\n"

# Remove newline characters from both sides
```

**Expected Output:**

```text
Welcome to Python
```

### Problem 6: Remove a Specific Character from Both Sides

```python
text = "xxxHello Worldxxx"

# Remove x from both sides
```

**Expected Output:**

```text
Hello World
```

### Problem 7: Clean User Input

```python
name = "   Masum   "

# Remove unnecessary whitespace
# Print the cleaned name
```

**Expected Output:**

```text
Masum
```

## 18. Chapter Summary

এই Topic-এ আমরা Python-এর whitespace removing methods শিখেছি।

আমরা শিখেছি:

- `strip()` method
- `lstrip()` method
- `rstrip()` method
- তিনটি method-এর মধ্যে পার্থক্য
- Specific characters remove করা
- Newline এবং Tab remove করা
- User Input clean করা
- `strip()` এবং `replace()`-এর পার্থক্য
- Common mistakes এবং তাদের সমাধান

**Next Topic:**

`28_Replacing_Text_with_replace.md`

পরবর্তী Topic-এ আমরা Python-এর `replace()` method ব্যবহার করে String-এর নির্দিষ্ট text পরিবর্তন বা remove করা শিখব।
