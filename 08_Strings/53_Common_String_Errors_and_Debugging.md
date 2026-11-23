

# 53. Common String Errors and Debugging in Python

## 1. Introduction

Python-এ String নিয়ে কাজ করার সময় বিভিন্ন ধরনের Error হতে পারে।

যেমন:

- ভুল Index ব্যবহার করা।
- String-এর সাথে Number যোগ করা।
- ভুল Method ব্যবহার করা।
- String-এর মধ্যে থাকা Character পরিবর্তন করার চেষ্টা করা।
- ভুল Data Type ব্যবহার করা।

এই Error-গুলো খুঁজে বের করে সমাধান করার প্রক্রিয়াকে **Debugging** বলা হয়।

এই Topic-এ আমরা Python-এর Common String Errors এবং সেগুলো কীভাবে Fix করতে হয় তা শিখব।

---

## 2. IndexError in Strings

String-এর মধ্যে নেই এমন কোনো Index Access করতে চাইলে `IndexError` হয়।

**Example:**

```python
text = "Python"

print(text[10])
```

**Error:**

```text
IndexError: string index out of range
```

**কারণ:**

`Python` String-এর Index হলো 0 থেকে 5 পর্যন্ত। কিন্তু এখানে Index 10 Access করার চেষ্টা করা হয়েছে।

**Correct Way:**

```python
text = "Python"

print(text[5])
```

**Output:**

```text
n
```

**Important:**

String-এর Length বের করতে `len()` ব্যবহার করা যায়।

```python
text = "Python"

print(len(text))
```

**Output:**

```text
6
```

সাধারণভাবে Valid Index হলো `0` থেকে `len(text) - 1` পর্যন্ত।

---

## 3. TypeError in Strings

ভিন্ন Data Type-এর Value সরাসরি একসাথে যোগ করতে গেলে অনেক সময় `TypeError` হয়।

**Example:**

```python
age = 22

message = "My age is " + age

print(message)
```

**Error:**

```text
TypeError: can only concatenate str (not "int") to str
```

**কারণ:**

এখানে String-এর সাথে Integer যোগ করার চেষ্টা করা হয়েছে।

**Correct Way 1: Using str()**

```python
age = 22

message = "My age is " + str(age)

print(message)
```

**Output:**

```text
My age is 22
```

**Correct Way 2: Using f-string**

```python
age = 22

print(f"My age is {age}")
```

**Output:**

```text
My age is 22
```

---

## 4. AttributeError in Strings

কোনো Object-এর মধ্যে নেই এমন Method বা Attribute ব্যবহার করতে গেলে `AttributeError` হতে পারে।

**Example:**

```python
text = "Python"

print(text.uppercase())
```

**Error:**

```text
AttributeError: 'str' object has no attribute 'uppercase'
```

**কারণ:**

Python String-এর মধ্যে `uppercase()` নামে কোনো Method নেই।

**Correct Way:**

```python
text = "Python"

print(text.upper())
```

**Output:**

```text
PYTHON
```

**Important:**

কিছু Common String Method:

| Method | কাজ |
|---|---|
| `upper()` | সব Letter বড় হাতের করে |
| `lower()` | সব Letter ছোট হাতের করে |
| `title()` | প্রতিটি Word-এর প্রথম Letter বড় করে |
| `strip()` | শুরু ও শেষের Extra Space সরায় |
| `replace()` | Text পরিবর্তন করে |
| `split()` | String-কে ভাগ করে |
| `find()` | নির্দিষ্ট Text-এর Position খুঁজে |

---

## 5. ValueError in Strings

কোনো String-কে ভুল Format-এ Convert করতে গেলে `ValueError` হতে পারে।

**Example:**

```python
text = "Hello"

number = int(text)

print(number)
```

**Error:**

```text
ValueError: invalid literal for int() with base 10: 'Hello'
```

**কারণ:**

`int()` ব্যবহার করে Number-এ Convert করতে হলে String-এর মধ্যে Valid Integer থাকতে হবে।

**Correct Way:**

```python
text = "123"

number = int(text)

print(number)
```

**Output:**

```text
123
```

**Another Example:**

```python
text = "12.5"

number = float(text)

print(number)
```

**Output:**

```text
12.5
```

---

## 6. String Immutability Error

Python-এর String হলো **Immutable**। অর্থাৎ String তৈরি হওয়ার পর এর কোনো Character সরাসরি পরিবর্তন করা যায় না।

**Example:**

```python
text = "Python"

text[0] = "J"

print(text)
```

**Error:**

```text
TypeError: 'str' object does not support item assignment
```

**কারণ:**

String-এর কোনো Character সরাসরি পরিবর্তন করা যায় না।

**Correct Way:**

নতুন String তৈরি করে পরিবর্তন করতে হবে।

```python
text = "Python"

text = "J" + text[1:]

print(text)
```

**Output:**

```text
Jython
```

**Explanation:**

- `text[1:]` দিয়ে প্রথম Character বাদে বাকি অংশ নেওয়া হয়েছে।
- `"J"` এবং বাকি অংশ একসাথে যোগ করা হয়েছে।
- একটি নতুন String তৈরি হয়েছে।

---

## 7. NameError in String Variables

কোনো Variable তৈরি করার আগে সেটি ব্যবহার করলে `NameError` হয়।

**Example:**

```python
print(name)
```

**Error:**

```text
NameError: name 'name' is not defined
```

**কারণ:**

এখানে `name` Variable আগে Declare করা হয়নি।

**Correct Way:**

```python
name = "Masum"

print(name)
```

**Output:**

```text
Masum
```

**Important:** Python-এ Variable Name Case-sensitive।

```python
name = "Masum"

print(Name)
```

এখানেও `NameError` হবে। কারণ `name` এবং `Name` দুটি আলাদা Variable।

---

## 8. Common String Method Errors

String Method ব্যবহার করার সময় কিছু সাধারণ ভুল হয়।

### Mistake 1: Wrong Method Name

```python
text = "Python"

print(text.capital())
```

**Error:**

```text
AttributeError: 'str' object has no attribute 'capital'
```

**Correct:**

```python
text = "Python"

print(text.capitalize())
```

**Output:**

```text
Python
```

### Mistake 2: Wrong Number of Arguments

```python
text = "Python"

print(text.replace("P"))
```

**Error:**

```text
TypeError: replace expected at least 2 arguments, got 1
```

**কারণ:** `replace()` Method-এ পুরোনো এবং নতুন Text দিতে হয়।

**Correct:**

```python
text = "Python"

print(text.replace("P", "J"))
```

**Output:**

```text
Jython
```

### Mistake 3: split() Result ভুলভাবে ব্যবহার করা

```python
text = "Python Programming"

words = text.split()

print(words[2])
```

**Error:**

```text
IndexError: list index out of range
```

**কারণ:** `split()` করার পর এখানে মাত্র দুটি Word পাওয়া যায়। কিন্তু `[2]` দিয়ে তৃতীয় Word চাওয়া হয়েছে।

**Correct:**

```python
text = "Python Programming"

words = text.split()

print(words[1])
```

**Output:**

```text
Programming
```

---

## 9. Debugging String Programs

**Debugging** হলো Program-এর Error বা ভুল খুঁজে বের করে ঠিক করার প্রক্রিয়া।

String Program Debug করার জন্য কয়েকটি সহজ পদ্ধতি অনুসরণ করা যায়।

### Step 1: Check Variable Value

`print()` ব্যবহার করে Variable-এর Value পরীক্ষা করা যায়।

```python
text = "Python"

print(text)
```

**Output:**

```text
Python
```

### Step 2: Check Data Type

`type()` দিয়ে Variable-এর Data Type পরীক্ষা করা যায়।

```python
value = 100

print(type(value))
```

**Output:**

```text
<class 'int'>
```

### Step 3: Check String Length

`len()` দিয়ে String-এর Length পরীক্ষা করা যায়।

```python
text = "Python"

print(len(text))
```

**Output:**

```text
6
```

### Step 4: Check Index

String-এর প্রতিটি Character-এর Index দেখতে পারি।

```python
text = "Python"

for index, char in enumerate(text):
    print(index, char)
```

**Output:**

```text
0 P
1 y
2 t
3 h
4 o
5 n
```

### Step 5: Read the Error Message

Python-এর Error Message দেখে সমস্যার কারণ বোঝার চেষ্টা করতে হবে।

যেমন:

```text
IndexError: string index out of range
```

এর অর্থ হলো ভুল Index Access করা হয়েছে।

---

## 10. Using try-except to Handle String Errors

Python-এ `try-except` ব্যবহার করে কিছু Error Handle করা যায়।

**Example:**

```python
text = "Hello"

try:
    number = int(text)
    print(number)

except ValueError:
    print("Invalid number")
```

**Output:**

```text
Invalid number
```

**Explanation:**

- `try` Block-এর মধ্যে যে Code-এ Error হতে পারে সেটি লেখা হয়।
- Error হলে সংশ্লিষ্ট `except` Block কাজ করে।
- এখানে String-টি Integer-এ Convert করা সম্ভব হয়নি।
- তাই `Invalid number` Print হয়েছে।

**Another Example:**

```python
text = "Python"

try:
    print(text[10])

except IndexError:
    print("Invalid index")
```

**Output:**

```text
Invalid index
```

**Important:** `try-except` Error Handle করে, কিন্তু ভুল Logic ঠিক করে না। তাই Error-এর মূল কারণও বুঝতে হবে।

---

## 11. Common String Errors Summary

| Error | কারণ |
|---|---|
| `IndexError` | ভুল Index Access করা |
| `TypeError` | ভুল Data Type ব্যবহার করা |
| `AttributeError` | নেই এমন Method ব্যবহার করা |
| `ValueError` | Invalid Value Convert করা |
| `NameError` | Undefined Variable ব্যবহার করা |
| `SyntaxError` | Python Syntax ভুল লেখা |

---

## 12. Common Mistakes and Their Solutions

| Common Mistake | Solution |
|---|---|
| String-এর ভুল Index ব্যবহার | `len()` দিয়ে Length Check করা |
| String ও Integer সরাসরি যোগ | `str()` বা f-string ব্যবহার |
| ভুল String Method ব্যবহার | সঠিক Method Name Check করা |
| String-এর Character পরিবর্তন | নতুন String তৈরি করা |
| Undefined Variable ব্যবহার | Variable আগে Define করা |
| Invalid Conversion | `int()` বা `float()` ব্যবহারের আগে Value Check করা |
| Error Message উপেক্ষা করা | Error Message পড়ে কারণ বোঝা |

---

## 13. Practice Exercises

### Exercise 1: Fix the IndexError

**Wrong Code:**

```python
text = "Python"

print(text[10])
```

**Correct Solution:**

```python
text = "Python"

print(text[5])
```

**Output:**

```text
n
```

### Exercise 2: Fix the TypeError

**Wrong Code:**

```python
age = 22

print("Age: " + age)
```

**Correct Solution:**

```python
age = 22

print("Age: " + str(age))
```

**Output:**

```text
Age: 22
```

### Exercise 3: Fix the AttributeError

**Wrong Code:**

```python
text = "python"

print(text.uppercase())
```

**Correct Solution:**

```python
text = "python"

print(text.upper())
```

**Output:**

```text
PYTHON
```

### Exercise 4: Fix the ValueError

**Wrong Code:**

```python
text = "Python"

number = int(text)

print(number)
```

**Correct Solution:**

```python
text = "123"

number = int(text)

print(number)
```

**Output:**

```text
123
```

### Exercise 5: Handle Invalid Index

**Solution:**

```python
text = "Python"

try:
    print(text[10])

except IndexError:
    print("Index is not valid")
```

**Output:**

```text
Index is not valid
```

---

## 14. Chapter Summary

এই Topic-এ আমরা শিখেছি:

1. `IndexError` কেন হয়।
2. `TypeError` কেন হয়।
3. `AttributeError` কেন হয়।
4. `ValueError` কেন হয়।
5. `NameError` কেন হয়।
6. String Immutable হওয়ার কারণে কী সমস্যা হয়।
7. String Method-এর Common Errors।
8. `print()`, `type()` এবং `len()` দিয়ে Debugging।
9. `try-except` দিয়ে Error Handle করা।
10. Common Error-এর কারণ ও সমাধান।

---

## 15. Self-Assessment Checklist

- [ ] String-এর `IndexError` বুঝি।
- [ ] `TypeError` কেন হয় জানি।
- [ ] `AttributeError` চিনতে পারি।
- [ ] `ValueError` বুঝি।
- [ ] String Immutable কেন জানি।
- [ ] `NameError` সমাধান করতে পারি।
- [ ] `print()` দিয়ে Debugging করতে পারি।
- [ ] `type()` এবং `len()` ব্যবহার করতে পারি।
- [ ] `try-except` ব্যবহার করতে পারি।
- [ ] Error Message পড়ে সমস্যার কারণ বুঝতে পারি।

---

## 16. Next Topic

**54. String Performance and Best Practices in Python**

পরবর্তী Topic-এ আমরা শিখব:

- String Concatenation-এর Performance।
- `join()` কেন ব্যবহার করা ভালো।
- String Immutability-এর প্রভাব।
- Efficient String Processing।
- Memory এবং Performance-এর Basic ধারণা।
- Clean এবং Readable String Code লেখার নিয়ম।

