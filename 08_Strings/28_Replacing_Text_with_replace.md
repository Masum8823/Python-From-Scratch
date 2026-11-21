
# 28. Replacing Text with replace() in Python

## 1. Introduction to replace() Method

Python-এ String-এর কোনো নির্দিষ্ট character বা word পরিবর্তন করার জন্য `replace()` method ব্যবহার করা হয়।

এটি একটি String-এর মধ্যে নির্দিষ্ট text খুঁজে তার পরিবর্তে অন্য text বসায়।

**Example:**

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

- `"Java"` হলো যে text পরিবর্তন করতে চাই।
- `"Python"` হলো নতুন text।
- `replace()` পুরোনো text-এর পরিবর্তে নতুন text বসিয়েছে।

## 2. Syntax of replace() Method

**Syntax:**

```python
string.replace(old, new, count)
```

**Parameters:**

| Parameter | Description |
|---|---|
| `old` | যে text পরিবর্তন করতে চাই |
| `new` | যে নতুন text বসাতে চাই |
| `count` | সর্বোচ্চ কতবার replace হবে (optional) |

`old` এবং `new` দেওয়া বাধ্যতামূলক। `count` দেওয়া optional।

## 3. Replacing a Character

`replace()` ব্যবহার করে String-এর একটি নির্দিষ্ট character পরিবর্তন করা যায়।

**Example:**

```python
text = "Hello"

result = text.replace("l", "x")

print(result)
```

**Output:**

```text
Hexxo
```

**Explanation:**

এখানে `"l"` character-এর প্রতিটি occurrence `"x"` দিয়ে replace হয়েছে।

## 4. Replacing a Word

একটি String-এর নির্দিষ্ট word অন্য word দিয়ে পরিবর্তন করা যায়।

**Example:**

```python
text = "I love Java"

result = text.replace("Java", "Python")

print(result)
```

**Output:**

```text
I love Python
```

**Another Example:**

```python
sentence = "Python is easy. Java is easy."

result = sentence.replace("easy", "powerful")

print(result)
```

**Output:**

```text
Python is powerful. Java is powerful.
```

এখানে `"easy"` যেখানে পাওয়া গেছে, সব জায়গায় `"powerful"` বসেছে।

## 5. Replacing Multiple Occurrences

সাধারণভাবে `replace()` একটি String-এর মধ্যে পাওয়া সব matching occurrence replace করে।

**Example:**

```python
text = "apple apple apple"

result = text.replace("apple", "mango")

print(result)
```

**Output:**

```text
mango mango mango
```

**Explanation:**

এখানে `"apple"` তিনবার ছিল। তাই তিনটি occurrence-ই `"mango"` দিয়ে replace হয়েছে।

## 6. Using the count Parameter

`replace()` method-এর `count` parameter ব্যবহার করে কতবার replace হবে তা নির্ধারণ করা যায়।

**Example 1:**

```python
text = "apple apple apple"

result = text.replace("apple", "mango", 1)

print(result)
```

**Output:**

```text
mango apple apple
```

এখানে `count=1` দেওয়ায় শুধু প্রথম occurrence replace হয়েছে।

**Example 2:**

```python
text = "apple apple apple"

result = text.replace("apple", "mango", 2)

print(result)
```

**Output:**

```text
mango mango apple
```

এখানে সর্বোচ্চ দুইবার replace হয়েছে।

**Example 3:**

```python
text = "apple apple apple"

result = text.replace("apple", "mango", 3)

print(result)
```

**Output:**

```text
mango mango mango
```

এখানে তিনটি occurrence-ই replace হয়েছে।

## 7. Removing Characters Using replace()

`replace()` method-এর `new` parameter হিসেবে empty String (`""`) দিলে নির্দিষ্ট character remove করা যায়।

**Example 1: Removing a Character**

```python
text = "Hello World"

result = text.replace("l", "")

print(result)
```

**Output:**

```text
Heo Word
```

**Explanation:**

এখানে String-এর সব `"l"` character remove হয়েছে।

**Example 2: Removing Spaces**

```python
text = "Python Programming"

result = text.replace(" ", "")

print(result)
```

**Output:**

```text
PythonProgramming
```

**Example 3: Removing a Word**

```python
text = "I love Java Programming"

result = text.replace("Java ", "")

print(result)
```

**Output:**

```text
I love Programming
```

## 8. Replacing Spaces with Underscores

একটি String-এর space-গুলো underscore (`_`) দিয়ে replace করা যায়।

**Example:**

```python
text = "Python Programming Language"

result = text.replace(" ", "_")

print(result)
```

**Output:**

```text
Python_Programming_Language
```

এটি file name বা text formatting-এর ক্ষেত্রে কাজে লাগতে পারে।

## 9. Case-Sensitive Behavior of replace()

Python-এর `replace()` method case-sensitive।

অর্থাৎ uppercase এবং lowercase character-কে আলাদা হিসেবে বিবেচনা করে।

**Example:**

```python
text = "Python python PYTHON"

result = text.replace("python", "Java")

print(result)
```

**Output:**

```text
Python Java PYTHON
```

**Explanation:**

এখানে শুধু lowercase `"python"` replace হয়েছে।

কারণ `"Python"` এবং `"PYTHON"`-এর letter case আলাদা।

## 10. Replacing Text in a String with No Match

যদি `old` text String-এর মধ্যে না থাকে, তাহলে `replace()` কোনো পরিবর্তন করে না।

**Example:**

```python
text = "Hello Python"

result = text.replace("Java", "C++")

print(result)
```

**Output:**

```text
Hello Python
```

**Explanation:**

এখানে `"Java"` String-এর মধ্যে নেই। তাই Original text অপরিবর্তিত রয়েছে।

## 11. Replacing an Empty String

`replace()` method-এ `old` হিসেবে empty String (`""`) দেওয়া যায়।

এক্ষেত্রে Python প্রতিটি character-এর মাঝখানে এবং String-এর শুরু ও শেষে নতুন text বসায়।

**Example:**

```python
text = "ABC"

result = text.replace("", "-")

print(result)
```

**Output:**

```text
-A-B-C-
```

**Explanation:**

Empty String-এর position-গুলোতে `-` যোগ হয়েছে।

## 12. replace() Does Not Modify the Original String

Python-এর String immutable। তাই `replace()` method মূল String পরিবর্তন করে না।

এটি একটি নতুন String return করে।

**Example:**

```python
text = "I like Java"

text.replace("Java", "Python")

print(text)
```

**Output:**

```text
I like Java
```

**Explanation:**

এখানে `replace()` ব্যবহার করা হলেও return value সংরক্ষণ করা হয়নি।

তাই Original String আগের মতোই রয়েছে।

**Correct Example:**

```python
text = "I like Java"

text = text.replace("Java", "Python")

print(text)
```

**Output:**

```text
I like Python
```

## 13. Practical Examples

### Example 1: Correcting a Word

```python
sentence = "I love programing"

result = sentence.replace("programing", "programming")

print(result)
```

**Output:**

```text
I love programming
```

### Example 2: Replacing Dashes with Spaces

```python
text = "Python-is-easy-to-learn"

result = text.replace("-", " ")

print(result)
```

**Output:**

```text
Python is easy to learn
```

### Example 3: Removing Special Characters

```python
text = "Hello@Python!"

result = text.replace("@", "").replace("!", "")

print(result)
```

**Output:**

```text
HelloPython
```

**Explanation:**

এখানে একাধিক `replace()` method chain করে `@` এবং `!` remove করা হয়েছে।

### Example 4: Replacing Only the First Occurrence

```python
text = "Python is easy. Python is popular."

result = text.replace("Python", "Java", 1)

print(result)
```

**Output:**

```text
Java is easy. Python is popular.
```

### Example 5: Formatting a Phone Number

```python
phone = "01712345678"

result = phone.replace("017", "+88017", 1)

print(result)
```

**Output:**

```text
+8801712345678
```

## 14. Common Mistakes in replace() Method

### Mistake 1: Forgetting Parentheses

**Incorrect Code:**

```python
text = "Hello"

print(text.replace)
```

**Why?**

এখানে `replace()` method call করা হয়নি। শুধু method-এর reference নেওয়া হয়েছে।

**Correct Code:**

```python
text = "Hello"

print(text.replace("H", "J"))
```

**Output:**

```text
Jello
```

### Mistake 2: Confusing old and new Parameters

**Example:**

```python
text = "I like Java"

result = text.replace("Python", "Java")

print(result)
```

**Output:**

```text
I like Java
```

**Why?**

এখানে `"Python"` খোঁজা হয়েছে, কিন্তু String-এর মধ্যে সেটি নেই।

**Correct Code:**

```python
text = "I like Java"

result = text.replace("Java", "Python")

print(result)
```

**Output:**

```text
I like Python
```

### Mistake 3: Expecting replace() to Change the Original String

**Incorrect Code:**

```python
text = "Hello Java"

text.replace("Java", "Python")

print(text)
```

**Output:**

```text
Hello Java
```

**Correct Code:**

```python
text = "Hello Java"

text = text.replace("Java", "Python")

print(text)
```

**Output:**

```text
Hello Python
```

### Mistake 4: Ignoring Case Sensitivity

**Example:**

```python
text = "PYTHON"

print(text.replace("python", "Java"))
```

**Output:**

```text
PYTHON
```

**Why?**

`replace()` case-sensitive। তাই lowercase `"python"` এবং uppercase `"PYTHON"` এক নয়।

**Correct Code:**

```python
text = "PYTHON"

print(text.replace("PYTHON", "Java"))
```

**Output:**

```text
Java
```

## 15. Important Rules to Remember

1. `replace()` String-এর নির্দিষ্ট text পরিবর্তন করে।
2. `old` parameter-এ যে text খুঁজতে হবে তা দিতে হয়।
3. `new` parameter-এ নতুন text দিতে হয়।
4. `count` parameter optional।
5. `count` দিয়ে সর্বোচ্চ কতবার replace হবে তা নির্ধারণ করা যায়।
6. `replace()` সাধারণভাবে সব matching occurrence replace করে।
7. `new=""` ব্যবহার করে নির্দিষ্ট text remove করা যায়।
8. `replace()` case-sensitive।
9. `old` text না পাওয়া গেলে String অপরিবর্তিত থাকে।
10. `replace()` নতুন String return করে।
11. Original String পরিবর্তন হয় না।
12. একাধিক `replace()` method chain করা যায়।

## 16. Practice Problems

### Problem 1: Replace a Word

```python
text = "I like Java"

# Replace Java with Python
```

**Expected Output:**

```text
I like Python
```

### Problem 2: Replace a Character

```python
text = "Hello"

# Replace l with x
```

**Expected Output:**

```text
Hexxo
```

### Problem 3: Replace Spaces with Underscores

```python
text = "Python Programming Language"

# Replace spaces with underscores
```

**Expected Output:**

```text
Python_Programming_Language
```

### Problem 4: Remove All Spaces

```python
text = "Learn Python Easily"

# Remove all spaces
```

**Expected Output:**

```text
LearnPythonEasily
```

### Problem 5: Replace Only Once

```python
text = "apple apple apple"

# Replace only the first apple with mango
```

**Expected Output:**

```text
mango apple apple
```

### Problem 6: Replace Dashes

```python
text = "Hello-World-Python"

# Replace all dashes with spaces
```

**Expected Output:**

```text
Hello World Python
```

### Problem 7: Remove Special Characters

```python
text = "Hello@Python!"

# Remove @ and !
```

**Expected Output:**

```text
HelloPython
```

## 17. Chapter Summary

এই Topic-এ আমরা Python-এর `replace()` method সম্পর্কে শিখেছি।

আমরা শিখেছি:

- `replace()` method এবং এর syntax
- Character ও Word replace করা
- Multiple occurrences replace করা
- `count` parameter ব্যবহার
- Empty String দিয়ে text remove করা
- Space এবং special character replace করা
- Case-sensitive behavior
- Original String অপরিবর্তিত থাকা
- Practical examples এবং common mistakes

**Next Topic:**

`29_Splitting_Strings_with_split.md`

পরবর্তী Topic-এ আমরা Python-এর `split()` method ব্যবহার করে একটি String-কে একাধিক অংশে ভাগ করা শিখব।
