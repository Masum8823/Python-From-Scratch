
# 46. String Methods for Changing Case in Python

## 1. Introduction

Python-এ String-এর letter-গুলোকে Uppercase বা Lowercase করার জন্য কিছু built-in method রয়েছে।

এই method-গুলো ব্যবহার করে আমরা:

- সব letter বড় হাতের করতে পারি।
- সব letter ছোট হাতের করতে পারি।
- প্রথম letter বড় হাতের করতে পারি।
- প্রতিটি word-এর প্রথম letter বড় হাতের করতে পারি।
- Uppercase-কে Lowercase এবং Lowercase-কে Uppercase করতে পারি।

এই topic-এর গুরুত্বপূর্ণ method-গুলো হলো:

1. `upper()`
2. `lower()`
3. `capitalize()`
4. `title()`
5. `swapcase()`

---

## 2. upper() Method

`upper()` method String-এর সব lowercase letter-কে uppercase letter-এ পরিবর্তন করে।

**Example:**

```python
text = "Hello Python"

result = text.upper()

print(result)
```

**Output:**

```text
HELLO PYTHON
```

**Explanation:**

- `Hello` হয়ে গেছে `HELLO`।
- `Python` হয়ে গেছে `PYTHON`।
- সব letter uppercase হয়েছে।

### Another Example

```python
name = "masum"

print(name.upper())
```

**Output:**

```text
MASUM
```

**Important:**

`upper()` কোনো number বা special character পরিবর্তন করে না।

```python
text = "python123@"

print(text.upper())
```

**Output:**

```text
PYTHON123@
```

---

## 3. lower() Method

`lower()` method String-এর সব uppercase letter-কে lowercase letter-এ পরিবর্তন করে।

**Example:**

```python
text = "HELLO PYTHON"

result = text.lower()

print(result)
```

**Output:**

```text
hello python
```

### Another Example

```python
name = "MASUM"

print(name.lower())
```

**Output:**

```text
masum
```

**Explanation:**

String-এর সব uppercase letter lowercase হয়ে গেছে।

---

## 4. capitalize() Method

`capitalize()` method String-এর প্রথম character-কে uppercase করে এবং বাকি সব cased letter-কে lowercase করে।

**Example:**

```python
text = "hello python"

result = text.capitalize()

print(result)
```

**Output:**

```text
Hello python
```

**Explanation:**

- প্রথম letter `h` থেকে `H` হয়েছে।
- বাকি letter-গুলো lowercase হয়েছে।

### Important Example

```python
text = "hELLO PYTHON"

print(text.capitalize())
```

**Output:**

```text
Hello python
```

দেখো, শুধু প্রথম letter uppercase হয়েছে। বাকি সব letter lowercase হয়েছে।

### Another Example

```python
text = "python programming language"

print(text.capitalize())
```

**Output:**

```text
Python programming language
```

**Important:**

`capitalize()` শুধু String-এর প্রথম character নিয়ে কাজ করে। প্রতিটি word-এর প্রথম letter uppercase করে না।

---

## 5. title() Method

`title()` method String-এর প্রতিটি word-এর প্রথম cased letter-কে uppercase করে এবং সেই word-এর বাকি cased letter-গুলো lowercase করে।

**Example:**

```python
text = "hello python programming"

result = text.title()

print(result)
```

**Output:**

```text
Hello Python Programming
```

**Explanation:**

- `hello` হয়েছে `Hello`।
- `python` হয়েছে `Python`।
- `programming` হয়েছে `Programming`।

### Another Example

```python
text = "i am learning python"

print(text.title())
```

**Output:**

```text
I Am Learning Python
```

**Important:**

`title()` প্রতিটি word-এর প্রথম letter uppercase করে। তবে apostrophe-এর মতো punctuation থাকলে কিছু ক্ষেত্রে অপ্রত্যাশিত ফল আসতে পারে।

**Example:**

```python
text = "they're learning python"

print(text.title())
```

**Output:**

```text
They'Re Learning Python
```

কারণ `title()` apostrophe-কে word separator হিসেবে বিবেচনা করে।

---

## 6. swapcase() Method

`swapcase()` method String-এর uppercase letter-গুলোকে lowercase এবং lowercase letter-গুলোকে uppercase করে।

সহজভাবে, এটি letter-এর case উল্টে দেয়।

**Example:**

```python
text = "Hello Python"

result = text.swapcase()

print(result)
```

**Output:**

```text
hELLO pYTHON
```

**Explanation:**

- `H` হয়েছে `h`।
- `e` হয়েছে `E`।
- `P` হয়েছে `p`।
- `y` হয়েছে `Y`।

### Another Example

```python
text = "PyThOn"

print(text.swapcase())
```

**Output:**

```text
pYtHoN
```

---

## 7. Difference Between Case Changing Methods

| Method | কাজ |
|---|---|
| `upper()` | সব letter uppercase করে |
| `lower()` | সব letter lowercase করে |
| `capitalize()` | প্রথম character uppercase করে, বাকিগুলো lowercase করে |
| `title()` | প্রতিটি word-এর প্রথম cased letter uppercase করে |
| `swapcase()` | Uppercase ও lowercase অদলবদল করে |

সহজভাবে মনে রাখবে:

```text
upper()      = ALL UPPERCASE
lower()      = all lowercase
capitalize() = First character uppercase
title()      = First Letter Of Each Word
swapcase()   = Reverse the case
```

---

## 8. Combining Case Changing Methods

একাধিক method একসাথে ব্যবহার করা যায়।

**Example:**

```python
text = "hello python"

result = text.upper().replace("PYTHON", "WORLD")

print(result)
```

**Output:**

```text
HELLO WORLD
```

**Explanation:**

প্রথমে `upper()` পুরো String-কে uppercase করেছে। এরপর `replace()` দিয়ে `PYTHON`-এর জায়গায় `WORLD` বসানো হয়েছে।

### Another Example

```python
text = "   hello python   "

result = text.strip().title()

print(result)
```

**Output:**

```text
Hello Python
```

এখানে:

1. `strip()` দুই পাশের whitespace remove করেছে।
2. `title()` প্রতিটি word-এর প্রথম letter uppercase করেছে।

---

## 9. Important: Original String Change হয় না

Python-এর String immutable। তাই `upper()`, `lower()`, `capitalize()`, `title()` এবং `swapcase()` original String পরিবর্তন করে না।

এগুলো নতুন String return করে।

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

কারণ `upper()`-এর result সংরক্ষণ করা হয়নি।

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

---

## 10. Practical Example: Case-Insensitive Comparison

ধরো, user একটি password বা word input দিচ্ছে। আমরা চাই uppercase বা lowercase যেভাবেই লিখুক, তুলনা করার সময় একইভাবে পরীক্ষা করতে।

**Example:**

```python
word = input("Enter a word: ")

if word.lower() == "python":
    print("Correct word")
else:
    print("Wrong word")
```

**Example Input 1:**

```text
PYTHON
```

**Output:**

```text
Correct word
```

**Example Input 2:**

```text
Python
```

**Output:**

```text
Correct word
```

**Example Input 3:**

```text
Java
```

**Output:**

```text
Wrong word
```

**Explanation:**

`lower()` ব্যবহার করার কারণে user uppercase বা lowercase যেভাবেই লিখুক, comparison-এর আগে input lowercase হয়ে যাচ্ছে।

---

## 11. Common Mistakes

### Mistake 1: capitalize() এবং title() একই মনে করা

```python
text = "hello python programming"

print(text.capitalize())
print(text.title())
```

**Output:**

```text
Hello python programming
Hello Python Programming
```

`capitalize()` শুধু String-এর প্রথম character uppercase করে।

`title()` প্রতিটি word-এর প্রথম cased letter uppercase করে।

### Mistake 2: upper() Original String পরিবর্তন করে মনে করা

```python
text = "python"

text.upper()

print(text)
```

**Output:**

```text
python
```

কারণ result সংরক্ষণ করা হয়নি।

### Mistake 3: swapcase() সব letter uppercase করে মনে করা

```python
text = "Hello"

print(text.swapcase())
```

**Output:**

```text
hELLO
```

কারণ `swapcase()` uppercase-কে lowercase এবং lowercase-কে uppercase করে।

### Mistake 4: lower() দিয়ে Number পরিবর্তন করার চেষ্টা

```python
text = "PYTHON123"

print(text.lower())
```

**Output:**

```text
python123
```

শুধু letter পরিবর্তন হয়েছে। Number আগের মতোই রয়েছে।

---

## 12. Practice Exercises

### Exercise 1

নিচের code-এর output কী হবে?

```python
text = "hello python"

print(text.upper())
print(text.lower())
```

**Solution:**

```text
HELLO PYTHON
hello python
```

### Exercise 2

নিচের code-এর output কী হবে?

```python
text = "pYTHON pROGRAMMING"

print(text.capitalize())
print(text.title())
```

**Solution:**

```text
Python programming
Python Programming
```

### Exercise 3

নিচের code-এর output কী হবে?

```python
text = "PyThOn"

print(text.swapcase())
```

**Solution:**

```text
pYtHoN
```

### Exercise 4

একটি String-এর সব letter uppercase করে নতুন variable-এ সংরক্ষণ করো।

**Solution:**

```python
text = "python programming"

result = text.upper()

print(result)
```

**Output:**

```text
PYTHON PROGRAMMING
```

### Exercise 5

User-এর কাছ থেকে একটি sentence input নিয়ে সেটিকে Title Case-এ পরিবর্তন করো।

**Solution:**

```python
sentence = input("Enter a sentence: ")

result = sentence.title()

print(result)
```

**Example Input:**

```text
i am learning python
```

**Output:**

```text
I Am Learning Python
```

### Exercise 6

নিচের code-এর output কী হবে?

```python
text = "hello python"

result = text.capitalize().swapcase()

print(result)
```

**Solution:**

```text
hELLO PYTHON
```

**Explanation:**

প্রথমে `capitalize()` result দেয় `Hello python`।

এরপর `swapcase()` result দেয় `hELLO PYTHON`।

---

## 13. Chapter Summary

এই topic-এ আমরা Python-এর String Case Changing Methods শিখেছি।

গুরুত্বপূর্ণ বিষয়গুলো:

1. `upper()` সব letter uppercase করে।
2. `lower()` সব letter lowercase করে।
3. `capitalize()` প্রথম character uppercase করে এবং বাকি cased letter lowercase করে।
4. `title()` প্রতিটি word-এর প্রথম cased letter uppercase করে।
5. `swapcase()` uppercase ও lowercase অদলবদল করে।
6. একাধিক String method একসাথে ব্যবহার করা যায়।
7. এই method-গুলো original String পরিবর্তন করে না।
8. পরিবর্তিত String সংরক্ষণ করতে assignment করতে হয়।

---

## 14. Self-Assessment Checklist

নিচের বিষয়গুলো নিজে করতে পারলে এই topic ভালোভাবে শেখা হয়েছে:

- [ ] `upper()` ব্যবহার করতে পারি।
- [ ] `lower()` ব্যবহার করতে পারি।
- [ ] `capitalize()` ব্যবহার করতে পারি।
- [ ] `title()` ব্যবহার করতে পারি।
- [ ] `swapcase()` ব্যবহার করতে পারি।
- [ ] `capitalize()` এবং `title()`-এর পার্থক্য বুঝি।
- [ ] একাধিক String method একসাথে ব্যবহার করতে পারি।
- [ ] Case-insensitive comparison করতে পারি।
- [ ] String immutable কেন বুঝি।

---

## 15. Next Topic

**47. String Methods for Replacing and Modifying Text**

পরবর্তী topic-এ আমরা শিখব:

- `replace()`
- `maketrans()`
- `translate()`
- String-এর নির্দিষ্ট word বা character পরিবর্তন করা।
