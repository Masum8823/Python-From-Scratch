
# 44. String Methods for Checking Character Types in Python

## 1. Introduction

Python-এ String-এর মধ্যে থাকা character বা text-এর ধরন পরীক্ষা করার জন্য কিছু built-in method রয়েছে।

এই method-গুলো ব্যবহার করে আমরা জানতে পারি:

- String-এ শুধু alphabet আছে কি না।
- String-এ শুধু digit আছে কি না।
- String-এ uppercase বা lowercase letter আছে কি না।
- String-এ শুধু space আছে কি না।
- String-টি title case-এ আছে কি না।

এই method-গুলো সাধারণত `True` অথবা `False` return করে।

উদাহরণ:

```python
name = "Masum"

print(name.isalpha())
```

**Output:**
```text
True
```

কারণ `Masum`-এ শুধু alphabet রয়েছে।

---

## 2. isalpha() Method

`isalpha()` method পরীক্ষা করে String-এ শুধু alphabetic character আছে কি না।

- শুধু alphabet থাকলে `True` return করে।
- Space, number বা special character থাকলে `False` return করে।
- Empty String হলে `False` return করে।

**Example:**

```python
text1 = "Python"
text2 = "Python123"
text3 = "Hello World"
text4 = "বাংলা"

print(text1.isalpha())
print(text2.isalpha())
print(text3.isalpha())
print(text4.isalpha())
```

**Output:**
```text
True
False
False
True
```

**Explanation:**

- `Python`-এ শুধু alphabet আছে।
- `Python123`-এ number আছে।
- `Hello World`-এ space আছে।
- `বাংলা`-এর সব character alphabetic।

---

## 3. isdigit() Method

`isdigit()` method পরীক্ষা করে String-এর সব character digit কি না।

- সব character digit হলে `True` return করে।
- Alphabet, space বা special character থাকলে `False` return করে।
- Empty String হলে `False` return করে।

**Example:**

```python
number1 = "12345"
number2 = "123abc"
number3 = "12.5"
number4 = "2026"

print(number1.isdigit())
print(number2.isdigit())
print(number3.isdigit())
print(number4.isdigit())
```

**Output:**
```text
True
False
False
True
```

**Important:**

`isdigit()` শুধু `0` থেকে `9` পর্যন্ত সীমাবদ্ধ নয়। কিছু Unicode digit character-ও এটি গ্রহণ করে।

---

## 4. isdecimal() Method

`isdecimal()` method পরীক্ষা করে String-এর সব character decimal digit কি না।

এটি `isdigit()`-এর তুলনায় কিছুটা বেশি সীমিত।

**Example:**

```python
text1 = "12345"
text2 = "12.5"
text3 = "²"

print(text1.isdecimal())
print(text2.isdecimal())
print(text3.isdecimal())
```

**Output:**
```text
True
False
False
```

**Explanation:**

- `12345` decimal digit দিয়ে তৈরি।
- `12.5`-এ decimal point আছে।
- `²` একটি superscript digit, কিন্তু decimal digit নয়।

---

## 5. isnumeric() Method

`isnumeric()` method পরীক্ষা করে String-এর সব character numeric কি না।

এটি `isdecimal()` এবং `isdigit()`-এর চেয়ে বেশি ধরনের numeric character গ্রহণ করে।

**Example:**

```python
text1 = "12345"
text2 = "²"
text3 = "½"
text4 = "Python"

print(text1.isnumeric())
print(text2.isnumeric())
print(text3.isnumeric())
print(text4.isnumeric())
```

**Output:**
```text
True
True
True
False
```

**Explanation:**

- `12345` সাধারণ numeric character।
- `²` superscript number।
- `½` fraction character।
- `Python`-এ কোনো numeric character নেই।

### Difference Between Three Methods

| Method | কী পরীক্ষা করে |
|---|---|
| `isdecimal()` | Decimal digit |
| `isdigit()` | Decimal digit এবং কিছু অতিরিক্ত digit |
| `isnumeric()` | সবচেয়ে বেশি ধরনের numeric character |

সহজভাবে মনে রাখবে:

```text
isdecimal() ⊆ isdigit() ⊆ isnumeric()
```

---

## 6. isalnum() Method

`isalnum()` method পরীক্ষা করে String-এ শুধু alphabet এবং number আছে কি না।

- Alphabet থাকলে `True`।
- Number থাকলে `True`।
- Alphabet ও number একসাথে থাকলেও `True`।
- Space বা special character থাকলে `False`।
- Empty String হলে `False`।

**Example:**

```python
text1 = "Python123"
text2 = "Python"
text3 = "12345"
text4 = "Hello World"
text5 = "Python@123"

print(text1.isalnum())
print(text2.isalnum())
print(text3.isalnum())
print(text4.isalnum())
print(text5.isalnum())
```

**Output:**
```text
True
True
True
False
False
```

---

## 7. islower() Method

`islower()` method পরীক্ষা করে String-এর সব cased letter lowercase কি না।

- সব letter lowercase হলে `True`।
- কোনো uppercase letter থাকলে `False`।
- কোনো cased letter না থাকলে `False`।

**Example:**

```python
text1 = "python"
text2 = "Python"
text3 = "python123"
text4 = "12345"

print(text1.islower())
print(text2.islower())
print(text3.islower())
print(text4.islower())
```

**Output:**
```text
True
False
True
False
```

**Explanation:**

`python123`-এ সব letter lowercase। তাই এটি `True` return করে।

কিন্তু `12345`-এ কোনো letter নেই। তাই এটি `False` return করে।

---

## 8. isupper() Method

`isupper()` method পরীক্ষা করে String-এর সব cased letter uppercase কি না।

- সব letter uppercase হলে `True`।
- কোনো lowercase letter থাকলে `False`।
- কোনো cased letter না থাকলে `False`।

**Example:**

```python
text1 = "PYTHON"
text2 = "Python"
text3 = "PYTHON123"
text4 = "12345"

print(text1.isupper())
print(text2.isupper())
print(text3.isupper())
print(text4.isupper())
```

**Output:**
```text
True
False
True
False
```

---

## 9. istitle() Method

`istitle()` method পরীক্ষা করে String-টি title case-এ আছে কি না।

Title case-এ প্রতিটি word-এর প্রথম cased letter uppercase এবং পরবর্তী cased letter lowercase থাকে।

**Example:**

```python
text1 = "Hello World"
text2 = "hello world"
text3 = "Hello world"
text4 = "Python Programming"

print(text1.istitle())
print(text2.istitle())
print(text3.istitle())
print(text4.istitle())
```

**Output:**
```text
True
False
False
True
```

**Explanation:**

- `Hello World` title case-এ আছে।
- `hello world` lowercase দিয়ে শুরু।
- `Hello world`-এ দ্বিতীয় word-এর প্রথম letter lowercase।
- `Python Programming` title case-এ আছে।

---

## 10. isspace() Method

`isspace()` method পরীক্ষা করে String-এর সব character whitespace কি না।

Whitespace-এর উদাহরণ:

- Space
- Tab (`\t`)
- Newline (`\n`)

**Example:**

```python
text1 = "   "
text2 = "\t"
text3 = "\n"
text4 = "Hello World"
text5 = ""

print(text1.isspace())
print(text2.isspace())
print(text3.isspace())
print(text4.isspace())
print(text5.isspace())
```

**Output:**
```text
True
True
True
False
False
```

**Important:**

Empty String-এর ক্ষেত্রে `isspace()` `False` return করে।

---

## 11. isascii() Method

`isascii()` method পরীক্ষা করে String-এর সব character ASCII character কি না।

ASCII character-এর উদাহরণ:

- English alphabet
- English digit
- সাধারণ English punctuation
- ASCII whitespace

**Example:**

```python
text1 = "Python123"
text2 = "Hello!"
text3 = "বাংলা"
text4 = "2026"

print(text1.isascii())
print(text2.isascii())
print(text3.isascii())
print(text4.isascii())
```

**Output:**
```text
True
True
False
True
```

**Explanation:**

বাংলা character ASCII-এর অন্তর্ভুক্ত নয়। তাই `"বাংলা".isascii()` False return করে।

---

## 12. isprintable() Method

`isprintable()` method পরীক্ষা করে String-এর সব character print করা যায় কি না।

সাধারণ alphabet, number, punctuation এবং space printable character।

কিন্তু newline এবং tab-এর মতো control character printable নয়।

**Example:**

```python
text1 = "Hello World"
text2 = "Python123"
text3 = "Hello\nWorld"
text4 = "Python\tProgramming"

print(text1.isprintable())
print(text2.isprintable())
print(text3.isprintable())
print(text4.isprintable())
```

**Output:**
```text
True
True
False
False
```

---

## 13. Empty String-এর ক্ষেত্রে Important Rule

Empty String হলো এমন String যার মধ্যে কোনো character নেই।

```python
text = ""

print(text.isalpha())
print(text.isdigit())
print(text.isalnum())
print(text.islower())
print(text.isupper())
print(text.isspace())
print(text.isascii())
print(text.isprintable())
```

**Output:**
```text
False
False
False
False
False
False
True
True
```

**মনে রাখবে:**

- অধিকাংশ `is...()` method Empty String-এর জন্য `False` return করে।
- `isascii()` এবং `isprintable()` Empty String-এর জন্য `True` return করে।

---

## 14. Difference Between Common Checking Methods

| Method | কাজ |
|---|---|
| `isalpha()` | শুধু alphabet পরীক্ষা করে |
| `isdigit()` | Digit পরীক্ষা করে |
| `isdecimal()` | Decimal digit পরীক্ষা করে |
| `isnumeric()` | Numeric character পরীক্ষা করে |
| `isalnum()` | Alphabet অথবা number পরীক্ষা করে |
| `islower()` | Lowercase letter পরীক্ষা করে |
| `isupper()` | Uppercase letter পরীক্ষা করে |
| `istitle()` | Title case পরীক্ষা করে |
| `isspace()` | Whitespace পরীক্ষা করে |
| `isascii()` | ASCII character পরীক্ষা করে |
| `isprintable()` | Printable character পরীক্ষা করে |

---

## 15. Practical Example

ধরো, একজন user তার username input দিচ্ছে। আমরা পরীক্ষা করতে চাই username-এ শুধু alphabet এবং number আছে কি না।

```python
username = input("Enter your username: ")

if username.isalnum():
    print("Valid username")
else:
    print("Invalid username")
```

**Example Input 1:**
```text
Masum123
```

**Output:**
```text
Valid username
```

**Example Input 2:**
```text
Masum@123
```

**Output:**
```text
Invalid username
```

কারণ `@` একটি special character।

---

## 16. Common Mistakes

### Mistake 1: isalpha() দিয়ে Space গ্রহণ করা

```python
text = "Hello World"

print(text.isalpha())
```

**Output:**
```text
False
```

কারণ String-এর মধ্যে space রয়েছে।

### Mistake 2: isdigit() দিয়ে Decimal Number পরীক্ষা করা

```python
number = "12.5"

print(number.isdigit())
```

**Output:**
```text
False
```

কারণ `.` digit নয়।

### Mistake 3: islower() দিয়ে শুধু Number পরীক্ষা করা

```python
text = "12345"

print(text.islower())
```

**Output:**
```text
False
```

কারণ String-এ কোনো lowercase letter নেই।

### Mistake 4: isalnum() দিয়ে Special Character গ্রহণ করা

```python
text = "Python@123"

print(text.isalnum())
```

**Output:**
```text
False
```

কারণ `@` একটি special character।

---

## 17. Practice Exercises

### Exercise 1

নিচের code-এর output কী হবে?

```python
text = "Python"

print(text.isalpha())
print(text.isupper())
print(text.islower())
```

**Solution:**

```text
True
False
False
```

### Exercise 2

নিচের code-এর output কী হবে?

```python
text = "Python123"

print(text.isalnum())
print(text.isalpha())
print(text.isdigit())
```

**Solution:**

```text
True
False
False
```

### Exercise 3

নিচের code-এর output কী হবে?

```python
text = "HELLO WORLD"

print(text.isupper())
print(text.istitle())
print(text.isalpha())
```

**Solution:**

```text
True
False
False
```

### Exercise 4

User-এর কাছ থেকে একটি number input নিয়ে পরীক্ষা করো সেটি শুধু digit দিয়ে তৈরি কি না।

**Solution:**

```python
number = input("Enter a number: ")

if number.isdigit():
    print("Only digits")
else:
    print("Contains other characters")
```

**Example Input:**
```text
12345
```

**Output:**
```text
Only digits
```

### Exercise 5

নিচের code-এর output কী হবে?

```python
text = "Hello World"

print(text.isspace())
print(text.isprintable())
print(text.isascii())
```

**Solution:**

```text
False
True
True
```

---

## 18. Chapter Summary

এই topic-এ আমরা Python-এর String Checking Methods শিখেছি।

গুরুত্বপূর্ণ বিষয়গুলো:

1. `isalpha()` শুধু alphabet পরীক্ষা করে।
2. `isdigit()` digit পরীক্ষা করে।
3. `isdecimal()` decimal digit পরীক্ষা করে।
4. `isnumeric()` numeric character পরীক্ষা করে।
5. `isalnum()` alphabet এবং number পরীক্ষা করে।
6. `islower()` lowercase letter পরীক্ষা করে।
7. `isupper()` uppercase letter পরীক্ষা করে।
8. `istitle()` title case পরীক্ষা করে।
9. `isspace()` whitespace পরীক্ষা করে।
10. `isascii()` ASCII character পরীক্ষা করে।
11. `isprintable()` printable character পরীক্ষা করে।

এই method-গুলো সাধারণত `True` অথবা `False` return করে।

---

## 19. Self-Assessment Checklist

নিচের বিষয়গুলো নিজে করতে পারলে এই topic ভালোভাবে শেখা হয়েছে:

- [ ] `isalpha()` ব্যবহার করতে পারি।
- [ ] `isdigit()` এবং `isdecimal()`-এর পার্থক্য বুঝি।
- [ ] `isnumeric()` কী কাজ করে বুঝি।
- [ ] `isalnum()` ব্যবহার করতে পারি।
- [ ] `islower()` এবং `isupper()` ব্যবহার করতে পারি।
- [ ] `istitle()` ব্যবহার করতে পারি।
- [ ] `isspace()` ব্যবহার করতে পারি।
- [ ] `isascii()` এবং `isprintable()` বুঝি।
- [ ] Empty String-এর ক্ষেত্রে method-গুলোর আচরণ বুঝি।

---

## 20. Next Topic

**45. String Methods for Removing Whitespace**

পরবর্তী topic-এ আমরা শিখব:

- `strip()`
- `lstrip()`
- `rstrip()`
- String থেকে unwanted whitespace remove করা।
