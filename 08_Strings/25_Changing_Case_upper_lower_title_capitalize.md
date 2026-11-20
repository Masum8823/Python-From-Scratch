
# 25. Changing Case in Python (upper, lower, title, capitalize)

## 1. Introduction to Changing Case

Python-এ String-এর English letters-এর case পরিবর্তন করার জন্য কিছু built-in methods রয়েছে।

যেমন:

- Uppercase: সব Letter বড় হাতের করা।
- Lowercase: সব Letter ছোট হাতের করা।
- Title Case: প্রতিটি Word-এর প্রথম Letter বড় হাতের করা।
- Capitalize: পুরো String-এর প্রথম Character বড় হাতের করা।

Python-এ এই কাজগুলোর জন্য প্রধানত চারটি method ব্যবহার করা হয়:

1. `upper()`
2. `lower()`
3. `title()`
4. `capitalize()`

## 2. upper() Method

`upper()` method একটি String-এর সব lowercase English letter-কে uppercase করে।

**Syntax:**

```python
string.upper()
```

**Example 1:**

```python
text = "Hello Python"

result = text.upper()

print(result)
```

**Output:**

```text
HELLO PYTHON
```

**Example 2:**

```python
name = "Masum"

print(name.upper())
```

**Output:**

```text
MASUM
```

**Explanation:**

- `upper()` সব lowercase English letter-কে uppercase করে।
- আগে থেকেই uppercase letter থাকলে সেটি uppercase-ই থাকে।
- Number, space এবং punctuation পরিবর্তন হয় না।

## 3. lower() Method

`lower()` method একটি String-এর সব uppercase English letter-কে lowercase করে।

**Syntax:**

```python
string.lower()
```

**Example 1:**

```python
text = "HELLO PYTHON"

result = text.lower()

print(result)
```

**Output:**

```text
hello python
```

**Example 2:**

```python
name = "MaSuM"

print(name.lower())
```

**Output:**

```text
masum
```

**Explanation:**

- `lower()` সব uppercase English letter-কে lowercase করে।
- আগে থেকেই lowercase letter থাকলে সেটি lowercase-ই থাকে।
- Number এবং special character পরিবর্তন হয় না।

## 4. title() Method

`title()` method একটি String-এর প্রতিটি Word-এর প্রথম Character-কে uppercase করে এবং বাকি অক্ষরগুলো lowercase করে।

**Syntax:**

```python
string.title()
```

**Example 1:**

```python
text = "hello python programming"

result = text.title()

print(result)
```

**Output:**

```text
Hello Python Programming
```

**Example 2:**

```python
name = "md abdulla al masum"

print(name.title())
```

**Output:**

```text
Md Abdulla Al Masum
```

**Explanation:**

- প্রতিটি Word-এর প্রথম Character uppercase হয়।
- Word-এর বাকি English letters lowercase হয়।
- Word সাধারণত space বা punctuation-এর মতো character দিয়ে আলাদা হয়।

**Example 3:**

```python
text = "PYTHON IS FUN"

print(text.title())
```

**Output:**

```text
Python Is Fun
```

## 5. capitalize() Method

`capitalize()` method একটি String-এর প্রথম Character uppercase করে এবং বাকি অক্ষরগুলো lowercase করে।

**Syntax:**

```python
string.capitalize()
```

**Example 1:**

```python
text = "hello python programming"

result = text.capitalize()

print(result)
```

**Output:**

```text
Hello python programming
```

**Example 2:**

```python
text = "PYTHON PROGRAMMING"

print(text.capitalize())
```

**Output:**

```text
Python programming
```

**Explanation:**

- শুধু String-এর প্রথম Character uppercase হয়।
- বাকি English letters lowercase হয়ে যায়।
- প্রতিটি Word-এর প্রথম Letter uppercase হয় না।

## 6. Difference Between upper(), lower(), title() and capitalize()

এই চারটি method-এর কাজ আলাদা।

| Method | কাজ | Example Output |
|---|---|---|
| `upper()` | সব Letter uppercase করে | `HELLO WORLD` |
| `lower()` | সব Letter lowercase করে | `hello world` |
| `title()` | প্রতিটি Word-এর প্রথম Letter uppercase করে | `Hello World` |
| `capitalize()` | শুধু পুরো String-এর প্রথম Character uppercase করে | `Hello world` |

**Example:**

```python
text = "hello python"

print(text.upper())
print(text.lower())
print(text.title())
print(text.capitalize())
```

**Output:**

```text
HELLO PYTHON
hello python
Hello Python
Hello python
```

## 7. Changing Case Does Not Modify the Original String

Python-এর String immutable। তাই `upper()`, `lower()`, `title()` এবং `capitalize()` মূল String পরিবর্তন করে না।

এগুলো পরিবর্তিত String-এর একটি নতুন value return করে।

**Example:**

```python
text = "hello python"

text.upper()

print(text)
```

**Output:**

```text
hello python
```

**Explanation:**

এখানে `upper()` ব্যবহার করা হলেও তার return value সংরক্ষণ করা হয়নি। তাই `text` আগের মতোই রয়েছে।

**Correct Example:**

```python
text = "hello python"

text = text.upper()

print(text)
```

**Output:**

```text
HELLO PYTHON
```

এখানে নতুন String-টি আবার `text` variable-এ assign করা হয়েছে।

## 8. Using Case Methods with User Input

User-এর কাছ থেকে পাওয়া text-এর case পরিবর্তন করতেও এই methods ব্যবহার করা যায়।

**Example 1:**

```python
name = input("Enter your name: ")

print(name.upper())
```

**Input:**

```text
masum
```

**Output:**

```text
MASUM
```

**Example 2:**

```python
message = input("Enter a sentence: ")

print(message.title())
```

**Input:**

```text
welcome to python programming
```

**Output:**

```text
Welcome To Python Programming
```

## 9. Practical Examples

### Example 1: Converting a Name to Uppercase

```python
name = "Masum"

formatted_name = name.upper()

print("Name:", formatted_name)
```

**Output:**

```text
Name: MASUM
```

### Example 2: Converting a Sentence to Lowercase

```python
sentence = "PYTHON IS EASY TO LEARN"

print(sentence.lower())
```

**Output:**

```text
python is easy to learn
```

### Example 3: Formatting a Full Name

```python
name = "md abdulla al masum"

print(name.title())
```

**Output:**

```text
Md Abdulla Al Masum
```

### Example 4: Formatting the First Letter of a Sentence

```python
sentence = "pYTHON IS A PROGRAMMING LANGUAGE"

print(sentence.capitalize())
```

**Output:**

```text
Python is a programming language
```

### Example 5: Case-Insensitive Comparison

দুটি String-এর letter case আলাদা হলেও একই text কি না তা পরীক্ষা করতে `lower()` ব্যবহার করা যায়।

```python
text1 = "Python"
text2 = "PYTHON"

if text1.lower() == text2.lower():
    print("Both strings are equal")
else:
    print("Strings are different")
```

**Output:**

```text
Both strings are equal
```

**Explanation:**

দুটি String-কে আগে lowercase করা হয়েছে। এরপর তাদের তুলনা করা হয়েছে।

## 10. Common Mistakes in Case Changing Methods

### Mistake 1: Forgetting Parentheses

**Incorrect Code:**

```python
text = "hello"

print(text.upper)
```

**Output:**

```text
<built-in method upper of str object at ...>
```

**Why?**

এখানে `upper` method-কে call করা হয়নি। শুধু method-এর reference নেওয়া হয়েছে।

**Correct Code:**

```python
text = "hello"

print(text.upper())
```

**Output:**

```text
HELLO
```

### Mistake 2: Expecting the Original String to Change

**Incorrect Code:**

```python
text = "hello"

text.upper()

print(text)
```

**Output:**

```text
hello
```

**Why?**

String immutable এবং `upper()` নতুন String return করে।

**Correct Code:**

```python
text = "hello"

text = text.upper()

print(text)
```

**Output:**

```text
HELLO
```

### Mistake 3: Confusing title() and capitalize()

**Example:**

```python
text = "hello python programming"

print(text.title())
print(text.capitalize())
```

**Output:**

```text
Hello Python Programming
Hello python programming
```

**Explanation:**

- `title()` প্রতিটি Word-এর প্রথম Character uppercase করে।
- `capitalize()` শুধু পুরো String-এর প্রথম Character uppercase করে।

## 11. Important Rules to Remember

1. `upper()` সব English letters uppercase করে।
2. `lower()` সব English letters lowercase করে।
3. `title()` প্রতিটি Word-এর প্রথম Character uppercase করে।
4. `capitalize()` শুধু String-এর প্রথম Character uppercase করে।
5. এই চারটি method নতুন String return করে।
6. Original String পরিবর্তন হয় না।
7. পরিবর্তিত String রাখতে variable-এ assign করতে হয়।
8. Method call করার সময় `()` ব্যবহার করতে হয়।
9. Number এবং সাধারণ punctuation case পরিবর্তন করে না।
10. Python String-এর method ব্যবহার করে text-এর case সহজে পরিবর্তন করা যায়।

## 12. Practice Problems

### Problem 1: Convert to Uppercase

```python
text = "python programming"

# Convert the String to uppercase
```

**Expected Output:**

```text
PYTHON PROGRAMMING
```

### Problem 2: Convert to Lowercase

```python
text = "HELLO BANGLADESH"

# Convert the String to lowercase
```

**Expected Output:**

```text
hello bangladesh
```

### Problem 3: Convert to Title Case

```python
text = "learning python is interesting"

# Convert the String to title case
```

**Expected Output:**

```text
Learning Python Is Interesting
```

### Problem 4: Use capitalize()

```python
text = "WELCOME TO PYTHON"

# Capitalize the String
```

**Expected Output:**

```text
Welcome to python
```

### Problem 5: Format a Name

```python
name = "md abdulla al masum"

# Convert the name into title case
```

**Expected Output:**

```text
Md Abdulla Al Masum
```

### Problem 6: Compare Two Strings

```python
text1 = "Python"
text2 = "PYTHON"

# Compare both strings without considering case
```

**Expected Output:**

```text
Strings are equal
```

## 13. Chapter Summary

এই Topic-এ আমরা Python-এর String case changing methods শিখেছি।

আমরা শিখেছি:

- `upper()` method
- `lower()` method
- `title()` method
- `capitalize()` method
- চারটি method-এর মধ্যে পার্থক্য
- Original String অপরিবর্তিত থাকা
- User Input-এর case পরিবর্তন
- Practical examples এবং common mistakes

**Next Topic:**

`26_Case_Insensitive_String_Comparison.md`

পরবর্তী Topic-এ আমরা Case-Insensitive String Comparison সম্পর্কে বিস্তারিত শিখব।
