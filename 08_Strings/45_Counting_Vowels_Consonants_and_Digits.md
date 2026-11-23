
# 45. String Methods for Removing Whitespace in Python

## 1. Introduction

Python-এ String-এর শুরুতে বা শেষে থাকা unwanted whitespace remove করার জন্য কিছু built-in method রয়েছে।

Whitespace বলতে বোঝায়:

- Space
- Tab (`\t`)
- Newline (`\n`)

Python-এ whitespace remove করার জন্য প্রধানত তিনটি method ব্যবহার করা হয়:

1. `strip()`
2. `lstrip()`
3. `rstrip()`

উদাহরণ:

```python
text = "   Hello Python   "

print(text.strip())
```

**Output:**

```text
Hello Python
```

এখানে `strip()` String-এর শুরু এবং শেষের whitespace remove করেছে।

---

## 2. strip() Method

`strip()` method String-এর শুরু এবং শেষ থেকে whitespace remove করে।

মাঝখানে থাকা whitespace remove করে না।

**Example:**

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

- শুরুতে থাকা space remove হয়েছে।
- শেষে থাকা space remove হয়েছে।
- `Hello` এবং `Python`-এর মাঝের space আগের মতোই রয়েছে।

### Another Example

```python
text = "\n\tHello Python\t\n"

print(text.strip())
```

**Output:**

```text
Hello Python
```

এখানে শুরু এবং শেষের newline, tab ও space remove হয়েছে।

---

## 3. lstrip() Method

`lstrip()` method String-এর বাম পাশ বা শুরু থেকে whitespace remove করে।

ডান পাশের whitespace remove করে না।

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

- বাম পাশের space remove হয়েছে।
- ডান পাশের space আগের মতো রয়েছে।

এখানে `l` দ্বারা Left বোঝানো হয়েছে।

---

## 4. rstrip() Method

`rstrip()` method String-এর ডান পাশ বা শেষ থেকে whitespace remove করে।

বাম পাশের whitespace remove করে না।

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

- বাম পাশের space আগের মতো রয়েছে।
- ডান পাশের space remove হয়েছে।

এখানে `r` দ্বারা Right বোঝানো হয়েছে।

---

## 5. Difference Between strip(), lstrip() and rstrip()

| Method | কাজ |
|---|---|
| `strip()` | দুই পাশ থেকে whitespace remove করে |
| `lstrip()` | বাম পাশ থেকে whitespace remove করে |
| `rstrip()` | ডান পাশ থেকে whitespace remove করে |

সহজভাবে মনে রাখবে:

```text
strip()  = Both sides
lstrip() = Left side
rstrip() = Right side
```

**Example:**

```python
text = "   Python   "

print("[" + text.strip() + "]")
print("[" + text.lstrip() + "]")
print("[" + text.rstrip() + "]")
```

**Output:**

```text
[Python]
[Python   ]
[   Python]
```

এখানে `[]` ব্যবহার করা হয়েছে যাতে কোন পাশে space রয়েছে তা সহজে বোঝা যায়।

---

## 6. Removing Specific Characters with strip()

`strip()` শুধু whitespace remove করে না। চাইলে এর মধ্যে নির্দিষ্ট character-ও দেওয়া যায়।

**Syntax:**

```python
string.strip(chars)
```

এখানে `chars` হলো যেসব character String-এর দুই পাশ থেকে remove করতে চাই।

**Example:**

```python
text = "###Python###"

print(text.strip("#"))
```

**Output:**

```text
Python
```

এখানে `#` দুই পাশ থেকে remove হয়েছে।

### Important Example

```python
text = "xxPythonxx"

print(text.strip("x"))
```

**Output:**

```text
Python
```

এখানে শুরু এবং শেষের `x` remove হয়েছে।

### Multiple Characters

```python
text = "###Python***"

print(text.strip("#*"))
```

**Output:**

```text
Python
```

এখানে `#` এবং `*` দুই পাশ থেকেই remove হয়েছে।

**Important:**

`strip("#*")` পুরো `"#*"` substring খুঁজে remove করে না। এটি দুই পাশ থেকে `#` অথবা `*` character remove করে যতক্ষণ পর্যন্ত ওই character পাওয়া যায়।

---

## 7. Using lstrip() with Specific Characters

`lstrip()`-এর মধ্যেও নির্দিষ্ট character দেওয়া যায়।

এটি শুধু বাম পাশ থেকে সেই character remove করে।

**Example:**

```python
text = "###Python###"

print(text.lstrip("#"))
```

**Output:**

```text
Python###
```

এখানে শুধু বাম পাশের `#` remove হয়েছে।

### Another Example

```python
text = "xxxHello"

print(text.lstrip("x"))
```

**Output:**

```text
Hello
```

---

## 8. Using rstrip() with Specific Characters

`rstrip()`-এর মধ্যেও নির্দিষ্ট character দেওয়া যায়।

এটি শুধু ডান পাশ থেকে সেই character remove করে।

**Example:**

```python
text = "###Python###"

print(text.rstrip("#"))
```

**Output:**

```text
###Python
```

এখানে শুধু ডান পাশের `#` remove হয়েছে।

---

## 9. Important: strip() Original String Change করে না

Python-এর String হলো immutable। অর্থাৎ String তৈরি হওয়ার পর তার original value সরাসরি পরিবর্তন করা যায় না।

`strip()`, `lstrip()` এবং `rstrip()` নতুন String return করে।

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

দেখো, original String পরিবর্তন হয়নি।

পরিবর্তিত String সংরক্ষণ করতে হলে নতুন variable-এ রাখতে হবে অথবা একই variable-এ assign করতে হবে।

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

---

## 10. Practical Example: User Input Cleaning

ধরো, একজন user তার নাম input দিচ্ছে। ভুল করে নামের আগে বা পরে space দিয়ে ফেলেছে।

আমরা `strip()` ব্যবহার করে সেই unwanted space remove করতে পারি।

**Example:**

```python
name = input("Enter your name: ")

name = name.strip()

print("Welcome", name)
```

**Example Input:**

```text
   Masum   
```

**Output:**

```text
Welcome Masum
```

এখানে `strip()` user-এর input-এর শুরু এবং শেষের whitespace remove করেছে।

---

## 11. Practical Example: Removing Specific Symbols

ধরো, একটি String-এর শুরু এবং শেষে `*` রয়েছে। আমরা সেগুলো remove করতে চাই।

**Example:**

```python
text = "***Python Programming***"

result = text.strip("*")

print(result)
```

**Output:**

```text
Python Programming
```

---

## 12. Common Mistakes

### Mistake 1: strip() দিয়ে মাঝখানের Space Remove করার চেষ্টা

```python
text = "Hello Python"

print(text.strip())
```

**Output:**

```text
Hello Python
```

কারণ `strip()` শুধু শুরু এবং শেষের whitespace remove করে।

### Mistake 2: lstrip() দিয়ে দুই পাশের Space Remove করার চেষ্টা

```python
text = "   Python   "

print(text.lstrip())
```

**Output:**

```text
Python   
```

কারণ `lstrip()` শুধু বাম পাশের whitespace remove করে।

### Mistake 3: rstrip() দিয়ে বাম পাশের Space Remove করার চেষ্টা

```python
text = "   Python   "

print(text.rstrip())
```

**Output:**

```text
   Python
```

কারণ `rstrip()` শুধু ডান পাশের whitespace remove করে।

### Mistake 4: strip() ব্যবহার করেও Original String পরিবর্তন হবে মনে করা

```python
text = "   Hello   "

text.strip()

print(text)
```

**Output:**

```text
   Hello   
```

কারণ `strip()` একটি নতুন String return করে। তাই result সংরক্ষণ করতে হবে।

---

## 13. Practice Exercises

### Exercise 1

নিচের code-এর output কী হবে?

```python
text = "   Python   "

print(text.strip())
print(text.lstrip())
print(text.rstrip())
```

**Solution:**

```text
Python
Python   
   Python
```

### Exercise 2

নিচের code-এর output কী হবে?

```python
text = "###Hello###"

print(text.strip("#"))
print(text.lstrip("#"))
print(text.rstrip("#"))
```

**Solution:**

```text
Hello
Hello###
###Hello
```

### Exercise 3

নিচের code-এর output কী হবে?

```python
text = "   Hello Python   "

result = text.strip()

print("[" + result + "]")
```

**Solution:**

```text
[Hello Python]
```

### Exercise 4

User-এর কাছ থেকে একটি নাম input নিয়ে তার শুরু এবং শেষের whitespace remove করো।

**Solution:**

```python
name = input("Enter your name: ")

name = name.strip()

print("Your name is:", name)
```

**Example Input:**

```text
   Abdulla   
```

**Output:**

```text
Your name is: Abdulla
```

### Exercise 5

নিচের code-এর output কী হবে?

```python
text = "xxPythonxx"

print(text.strip("x"))
print(text.lstrip("x"))
print(text.rstrip("x"))
```

**Solution:**

```text
Python
Pythonxx
xxPython
```

---

## 14. Chapter Summary

এই topic-এ আমরা String থেকে whitespace এবং নির্দিষ্ট character remove করা শিখেছি।

গুরুত্বপূর্ণ বিষয়গুলো:

1. `strip()` দুই পাশ থেকে whitespace remove করে।
2. `lstrip()` বাম পাশ থেকে whitespace remove করে।
3. `rstrip()` ডান পাশ থেকে whitespace remove করে।
4. এই method-গুলো দিয়ে নির্দিষ্ট character-ও remove করা যায়।
5. `strip()` মাঝখানের whitespace remove করে না।
6. এই method-গুলো নতুন String return করে।
7. Original String পরিবর্তন করতে result assign করতে হয়।

---

## 15. Self-Assessment Checklist

নিচের বিষয়গুলো নিজে করতে পারলে এই topic ভালোভাবে শেখা হয়েছে:

- [ ] `strip()` ব্যবহার করতে পারি।
- [ ] `lstrip()` ব্যবহার করতে পারি।
- [ ] `rstrip()` ব্যবহার করতে পারি।
- [ ] তিনটি method-এর পার্থক্য বুঝি।
- [ ] নির্দিষ্ট character remove করতে পারি।
- [ ] String-এর মাঝখানের whitespace কেন remove হয় না বুঝি।
- [ ] Original String এবং returned String-এর পার্থক্য বুঝি।
- [ ] User input clean করতে পারি।

---

## 16. Next Topic

**46. String Methods for Changing Case**

পরবর্তী topic-এ আমরা শিখব:

- `upper()`
- `lower()`
- `capitalize()`
- `title()`
- `swapcase()`
- String-এর uppercase এবং lowercase পরিবর্তন করা।
