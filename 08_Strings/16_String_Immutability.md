# String Immutability

## 1. What is String Immutability?

Python-এ String হলো একটি **Immutable Data Type**।

Immutable বলতে বোঝায়, কোনো object তৈরি হওয়ার পরে তার original value সরাসরি পরিবর্তন করা যায় না।

অর্থাৎ, একটি string তৈরি করার পরে এর কোনো character সরাসরি পরিবর্তন, যোগ বা মুছে ফেলা যায় না।

**Example:**

```python
text = "Python"

text[0] = "J"

print(text)
```

**Output:**

```text
TypeError: 'str' object does not support item assignment
```

**ব্যাখ্যা:**

এখানে `"Python"` string-এর প্রথম character `P` পরিবর্তন করে `J` করার চেষ্টা করা হয়েছে।

কিন্তু Python String immutable হওয়ায় সরাসরি character পরিবর্তন করা যায় না।

তাই Python `TypeError` দেখিয়েছে।

## 2. Understanding Immutable Strings

String immutable হওয়ার অর্থ হলো, original string-এর character পরিবর্তন করা যায় না।

তবে আমরা চাইলে নতুন string তৈরি করতে পারি।

**Example:**

```python
text = "Python"

text = "Jython"

print(text)
```

**Output:**

```text
Jython
```

**ব্যাখ্যা:**

এখানে কোনো error হয়নি।

কারণ আমরা আগের string-এর character পরিবর্তন করিনি। বরং `"Jython"` নামে একটি নতুন string তৈরি করে `text` variable-এ assign করেছি।

অর্থাৎ, variable-কে নতুন string-এর সঙ্গে যুক্ত করা হয়েছে।

**Important:** Immutable হওয়া মানে variable-এ নতুন value assign করা যাবে না, এমন নয়। এর অর্থ হলো existing string object-কে সরাসরি পরিবর্তন করা যায় না।

## 3. Difference Between Mutable and Immutable

Python-এ Data Type-গুলোকে সাধারণভাবে Mutable এবং Immutable হিসেবে ভাগ করা যায়।

| Mutable | Immutable |
|---|---|
| Object তৈরি হওয়ার পরে পরিবর্তন করা যায়। | Object তৈরি হওয়ার পরে পরিবর্তন করা যায় না। |
| Existing object পরিবর্তন করা সম্ভব। | পরিবর্তনের জন্য নতুন object তৈরি করতে হয়। |
| Example: `list`, `dict`, `set` | Example: `str`, `int`, `float`, `tuple` |

**Example of Mutable:**

```python
numbers = [10, 20, 30]

numbers[0] = 100

print(numbers)
```

**Output:**

```text
[100, 20, 30]
```

এখানে List-এর প্রথম element সরাসরি পরিবর্তন করা গেছে। কারণ List হলো Mutable।

**Example of Immutable:**

```python
text = "Python"

text[0] = "J"

print(text)
```

**Output:**

```text
TypeError: 'str' object does not support item assignment
```

এখানে String-এর প্রথম character সরাসরি পরিবর্তন করা যায়নি। কারণ String হলো Immutable।

## 4. How to Modify a String?

String immutable হলেও বিভিন্ন পদ্ধতি ব্যবহার করে নতুন string তৈরি করা যায়।

### Method 1: Using String Concatenation

`+` operator ব্যবহার করে নতুন string তৈরি করা যায়।

**Example:**

```python
text = "Python"

text = "J" + text[1:]

print(text)
```

**Output:**

```text
Jython
```

**ব্যাখ্যা:**

- `"J"` একটি নতুন character।
- `text[1:]` দিয়ে `"ython"` সংগ্রহ করা হয়েছে।
- `+` operator দিয়ে দুটি অংশ যুক্ত করা হয়েছে।
- নতুন string `text` variable-এ সংরক্ষণ করা হয়েছে।

### Method 2: Using replace()

`replace()` method ব্যবহার করে string-এর নির্দিষ্ট text পরিবর্তন করে নতুন string তৈরি করা যায়।

**Example:**

```python
text = "I like Java"

new_text = text.replace("Java", "Python")

print(new_text)
```

**Output:**

```text
I like Python
```

**ব্যাখ্যা:**

এখানে `replace()` Java-এর পরিবর্তে Python বসিয়ে একটি নতুন string ফেরত দিয়েছে।

Original string পরিবর্তন হয়নি।

**Example:**

```python
text = "Hello World"

text.replace("World", "Python")

print(text)
```

**Output:**

```text
Hello World
```

এখানে `replace()`-এর result সংরক্ষণ করা হয়নি। তাই original string-ই পাওয়া গেছে।

সঠিক পদ্ধতি:

```python
text = "Hello World"

text = text.replace("World", "Python")

print(text)
```

**Output:**

```text
Hello Python
```

### Method 3: Using String Slicing

Slicing ব্যবহার করে string-এর নির্দিষ্ট অংশ বাদ দিয়ে নতুন character যুক্ত করা যায়।

**Example:**

```python
text = "Python"

new_text = text[:2] + "XX" + text[4:]

print(new_text)
```

**Output:**

```text
PyXXon
```

**ব্যাখ্যা:**

- `text[:2]` → `"Py"` সংগ্রহ করে।
- `"XX"` → নতুন character যোগ করে।
- `text[4:]` → `"on"` সংগ্রহ করে।
- `+` দিয়ে সব অংশ যুক্ত করে নতুন string তৈরি করা হয়েছে।

## 5. String Methods Do Not Modify the Original String

Python-এর অধিকাংশ String Method original string পরিবর্তন করে না। এগুলো নতুন string ফেরত দেয়।

**Example:**

```python
text = "python"

new_text = text.upper()

print(text)
print(new_text)
```

**Output:**

```text
python
PYTHON
```

**ব্যাখ্যা:**

- `text`-এ original string রয়েছে।
- `upper()` বড় হাতের অক্ষর দিয়ে নতুন string তৈরি করেছে।
- নতুন string `new_text`-এ সংরক্ষণ করা হয়েছে।

তাই original string অপরিবর্তিত রয়েছে।

## 6. Understanding String Immutability with id()

Python-এর `id()` function ব্যবহার করে কোনো object-এর identity জানা যায়।

এটি দিয়ে নতুন string assign করার আগে এবং পরে object identity পর্যবেক্ষণ করা যায়।

**Example:**

```python
text = "Python"

print(id(text))

text = "Java"

print(id(text))
```

**Output:**

```text
(First object ID)
(Second object ID)
```

**ব্যাখ্যা:**

- প্রথমে `text` variable `"Python"` string-কে reference করছে।
- পরে `text`-কে `"Java"` string-এর সঙ্গে assign করা হয়েছে।
- সাধারণভাবে দুটি আলাদা string object-এর identity আলাদা হবে।

`id()`-এর প্রকৃত output Python-এর runtime অনুযায়ী পরিবর্তিত হতে পারে।

**মনে রাখবে:** `id()` কোনো object পরিবর্তন করে না। এটি শুধু object-এর identity সম্পর্কে তথ্য দেয়।

## 7. Why Are Python Strings Immutable?

Python-এ String immutable রাখার কয়েকটি গুরুত্বপূর্ণ সুবিধা রয়েছে।

### 1. Safety

String সরাসরি পরিবর্তন করা যায় না বলে accidental modification-এর ঝুঁকি কমে।

### 2. Reliability

একটি string একবার তৈরি হলে সেটির content সরাসরি পরিবর্তিত হয় না। ফলে program-এর বিভিন্ন অংশে এটি ব্যবহার করা সহজ হয়।

### 3. Dictionary Keys

String immutable হওয়ায় এটি Dictionary-এর key হিসেবে ব্যবহার করা যায়।

**Example:**

```python
student = {
    "name": "Masum",
    "department": "CSE"
}

print(student["name"])
```

**Output:**

```text
Masum
```

এখানে `"name"` এবং `"department"` string key হিসেবে ব্যবহার করা হয়েছে।

### 4. Hashability

Immutable হওয়ায় String hashable। তাই এটি Set-এর element এবং Dictionary-এর key হিসেবে ব্যবহার করা যায়।

**Example:**

```python
names = {"Masum", "Rahim", "Karim"}

print(names)
```

**Output:**

```text
{'Masum', 'Rahim', 'Karim'}
```

Set-এর output-এর order নির্দিষ্ট নয়।

## 8. Important Rules to Remember

1. Python String হলো Immutable Data Type।
2. String-এর character সরাসরি পরিবর্তন করা যায় না।
3. String-এর character সরাসরি যোগ বা delete করা যায় না।
4. `+` operator দিয়ে নতুন string তৈরি করা যায়।
5. `replace()` নতুন string ফেরত দেয়।
6. Slicing ব্যবহার করে নতুন string তৈরি করা যায়।
7. Variable-এ নতুন string assign করা যায়।
8. String hashable হওয়ায় Dictionary key হিসেবে ব্যবহার করা যায়।
9. String-এর methods সাধারণত original string পরিবর্তন করে না।

## 9. Common Mistakes

### Mistake 1: Directly Changing a Character

```python
text = "Python"

text[0] = "J"
```

**Output:**

```text
TypeError: 'str' object does not support item assignment
```

**Solution:**

```python
text = "Python"

text = "J" + text[1:]

print(text)
```

**Output:**

```text
Jython
```

### Mistake 2: Thinking replace() Changes the Original String

```python
text = "Hello World"

text.replace("World", "Python")

print(text)
```

**Output:**

```text
Hello World
```

**Solution:**

```python
text = "Hello World"

text = text.replace("World", "Python")

print(text)
```

**Output:**

```text
Hello Python
```

### Mistake 3: Confusing Variable Reassignment with Object Modification

```python
text = "Python"

text = "Java"

print(text)
```

**Output:**

```text
Java
```

এখানে কোনো immutable rule ভাঙা হয়নি। কারণ `text`-কে নতুন string assign করা হয়েছে, পুরোনো string object পরিবর্তন করা হয়নি।

## 10. Practice Problems

### Problem 1: Fix the Error

নিচের code-এ প্রথম character পরিবর্তন করে `J` করতে হবে।

```python
text = "Python"

text[0] = "J"

print(text)
```

Expected Output:

```text
Jython
```

### Problem 2: Use replace()

নিচের string থেকে `Java` পরিবর্তন করে `Python` করো।

```python
text = "I love Java"
```

Expected Output:

```text
I love Python
```

### Problem 3: Use String Slicing

নিচের string-এর `World` অংশ পরিবর্তন করে `Python` বসাও।

```python
text = "Hello World"
```

Expected Output:

```text
Hello Python
```

### Problem 4: Predict the Output

```python
text = "python"

new_text = text.upper()

print(text)
print(new_text)
```

### Problem 5: Mutable vs Immutable

নিচের দুটি code-এর মধ্যে পার্থক্য ব্যাখ্যা করো।

```python
numbers = [10, 20, 30]

numbers[0] = 100

print(numbers)
```

```python
text = "Python"

text[0] = "J"

print(text)
```

### Problem 6: Predict the Output

```python
text = "Hello"

text = text.replace("Hello", "Python")

text = text + " Programming"

print(text)
```

Expected Output:

```text
Python Programming
```

## 11. Summary

- Immutability অর্থ object তৈরি হওয়ার পরে তার original content সরাসরি পরিবর্তন করা যায় না।
- Python String একটি Immutable Data Type।
- String-এর character সরাসরি পরিবর্তন, যোগ বা delete করা যায় না।
- নতুন string তৈরি করে variable-এ assign করা যায়।
- Concatenation, slicing এবং `replace()` ব্যবহার করে নতুন string তৈরি করা যায়।
- String methods সাধারণত নতুন string ফেরত দেয়।
- String hashable হওয়ায় Dictionary key এবং Set element হিসেবে ব্যবহার করা যায়।
- Mutable এবং Immutable Data Type-এর মূল পার্থক্য হলো existing object পরিবর্তন করা যায় কি না।

এইভাবে Python String Immutability বুঝতে পারলে String-এর বিভিন্ন operation কেন নতুন string তৈরি করে, তা সহজেই বুঝতে পারবে।