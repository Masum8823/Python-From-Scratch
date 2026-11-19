# Common String Indexing and Slicing Mistakes

## 1. Introduction

Python-এ String Indexing এবং Slicing ব্যবহার করে string-এর নির্দিষ্ট character অথবা অংশ সংগ্রহ করা যায়।

তবে এগুলো ব্যবহার করার সময় কিছু সাধারণ ভুল হতে পারে। যেমন:

- ভুল index ব্যবহার করা।
- String-এর সীমার বাইরে character access করা।
- Slicing-এর stop index ভুল বোঝা।
- ভুল direction-এ slicing করা।
- Step-এর ভুল মান ব্যবহার করা।

এই topic-এ আমরা এসব ভুলের কারণ, output এবং সমাধান শিখব।

## 2. Accessing an Invalid Index

String-এর মধ্যে যতগুলো character আছে, তার বাইরের কোনো index সরাসরি access করার চেষ্টা করলে `IndexError` হয়।

**Example:**

```python
text = "Python"

print(text[10])
```

**Output:**

```text
IndexError: string index out of range
```

**ব্যাখ্যা:**

এখানে `"Python"` string-এ মোট 6টি character রয়েছে।

তাই valid positive index হলো `0` থেকে `5`।

কিন্তু এখানে index `10` access করার চেষ্টা করা হয়েছে, যা string-এর মধ্যে নেই।

**Correct Code:**

```python
text = "Python"

print(text[5])
```

**Output:**

```text
n
```

**মনে রাখবে:** Direct indexing-এর ক্ষেত্রে valid index ব্যবহার করতে হবে।

## 3. Confusing Positive and Negative Indexing

Positive এবং Negative Indexing-এর পার্থক্য বুঝতে না পারলে ভুল character পাওয়া যেতে পারে।

**Example:**

```python
text = "Python"

print(text[1])
print(text[-1])
```

**Output:**

```text
y
n
```

**ব্যাখ্যা:**

- `text[1]` → দ্বিতীয় character।
- `text[-1]` → শেষ character।

Positive Index বাম দিক থেকে এবং Negative Index ডান দিক থেকে শুরু হয়।

**Correct Index Table:**

| Character | P | y | t | h | o | n |
|---|---|---|---|---|---|---|
| Positive Index | 0 | 1 | 2 | 3 | 4 | 5 |
| Negative Index | -6 | -5 | -4 | -3 | -2 | -1 |

## 4. Forgetting That Stop Index Is Excluded

String Slicing-এর সবচেয়ে সাধারণ ভুলগুলোর একটি হলো stop index-কে output-এর মধ্যে অন্তর্ভুক্ত মনে করা।

কিন্তু Python Slicing-এ stop index সবসময় বাদ থাকে।

**Example:**

```python
text = "Python"

print(text[0:3])
```

**Output:**

```text
Pyt
```

**ব্যাখ্যা:**

এখানে:

- Start = 0
- Stop = 3

তাই index 0, 1 এবং 2 নেওয়া হয়েছে।

Index 3-এর character `h` নেওয়া হয়নি।

**মনে রাখবে:**

```python
string[start:stop]
```

এখানে start অন্তর্ভুক্ত হয়, কিন্তু stop অন্তর্ভুক্ত হয় না।

## 5. Confusing Indexing with Slicing

Indexing এবং Slicing একই কাজ করে না।

Indexing একটি character ফেরত দেয়, আর Slicing একটি string ফেরত দেয়।

**Example:**

```python
text = "Python"

print(text[2])
print(text[2:3])
```

**Output:**

```text
t
t
```

দুটি output দেখতে একই হলেও তাদের data type আলাদা।

```python
text = "Python"

print(type(text[2]))
print(type(text[2:3]))
```

**Output:**

```text
<class 'str'>
<class 'str'>
```

Python-এ একটি character-ও আসলে একটি string।

তবে পার্থক্য হলো:

- `text[2]` → একটি character access করে।
- `text[2:3]` → একটি character-সম্বলিত নতুন string তৈরি করে।

## 6. Using the Wrong Slicing Direction

Negative Step ব্যবহার করার সময় start এবং stop-এর অবস্থান ভুল হলে empty string পাওয়া যেতে পারে।

**Incorrect Example:**

```python
text = "Python"

print(text[0:5:-1])
```

**Output:**

```text

```

**ব্যাখ্যা:**

এখানে:

- Start = 0
- Stop = 5
- Step = -1

Negative step বাম দিকে যাওয়ার নির্দেশ দেয়। কিন্তু start index 0 থেকে stop index 5-এর দিকে যাওয়ার চেষ্টা করা হয়েছে।

তাই কোনো character পাওয়া যায়নি।

**Correct Code:**

```python
text = "Python"

print(text[5:0:-1])
```

**Output:**

```text
nohty
```

এখানে negative step-এর direction সঠিকভাবে ব্যবহার করা হয়েছে।

## 7. Using Zero as Step

Slicing-এর step হিসেবে `0` ব্যবহার করা যায় না।

**Incorrect Example:**

```python
text = "Python"

print(text[::0])
```

**Output:**

```text
ValueError: slice step cannot be zero
```

**ব্যাখ্যা:**

Step নির্ধারণ করে কত ঘর পরপর character নেওয়া হবে।

কিন্তু `0` হলে কোনো movement বা অগ্রগতি সম্ভব নয়।

**Correct Code:**

```python
text = "Python"

print(text[::1])
```

**Output:**

```text
Python
```

এখানে step হিসেবে `1` ব্যবহার করা হয়েছে।

## 8. Confusing String Length with Last Index

String-এর length এবং শেষ index এক জিনিস নয়।

**Example:**

```python
text = "Python"

print(len(text))
print(text[5])
```

**Output:**

```text
6
n
```

**ব্যাখ্যা:**

- `len(text)` → মোট character সংখ্যা, অর্থাৎ 6।
- `text[5]` → শেষ character।

কারণ Python-এর indexing শুরু হয় `0` থেকে।

তাই:

```python
last_index = len(text) - 1
```

**Example:**

```python
text = "Python"

print(text[len(text) - 1])
```

**Output:**

```text
n
```

## 9. Thinking Slicing Always Produces an Error for Out-of-Range Indexes

Direct Indexing-এর ক্ষেত্রে invalid index ব্যবহার করলে `IndexError` হয়।

কিন্তু Slicing-এর ক্ষেত্রে start বা stop string-এর সীমার বাইরে গেলেও সাধারণত error হয় না।

**Example:**

```python
text = "Python"

print(text[0:20])
print(text[10:20])
```

**Output:**

```text
Python

```

**ব্যাখ্যা:**

- `text[0:20]` → string-এর শেষ পর্যন্ত character নেয়।
- `text[10:20]` → start index string-এর বাইরে হওয়ায় empty string দেয়।

Slicing-এর ক্ষেত্রে Python প্রয়োজন অনুযায়ী index-কে string-এর সীমার মধ্যে সমন্বয় করে।

## 10. Forgetting String Immutability

Python String immutable। অর্থাৎ string তৈরি হওয়ার পরে এর কোনো character সরাসরি পরিবর্তন করা যায় না।

**Incorrect Example:**

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

এখানে string-এর প্রথম character `P` পরিবর্তন করে `J` করার চেষ্টা করা হয়েছে।

কিন্তু Python string immutable হওয়ায় সরাসরি character পরিবর্তন করা যায় না।

**Correct Code:**

```python
text = "Python"

text = "J" + text[1:]

print(text)
```

**Output:**

```text
Jython
```

এখানে পুরোনো string পরিবর্তন করা হয়নি। বরং নতুন string তৈরি করে variable-এ সংরক্ষণ করা হয়েছে।

## 11. Forgetting to Store Slicing Results

String Slicing মূল string পরিবর্তন করে না। এটি একটি নতুন string ফেরত দেয়।

**Incorrect Example:**

```python
text = "Python"

text[0:3]

print(text)
```

**Output:**

```text
Python
```

**ব্যাখ্যা:**

এখানে slicing-এর ফলাফল কোনো variable-এ সংরক্ষণ করা হয়নি।

**Correct Code:**

```python
text = "Python"

result = text[0:3]

print(result)
```

**Output:**

```text
Pyt
```

এখানে slicing-এর ফলাফল `result` variable-এ সংরক্ষণ করা হয়েছে।

## 12. Common Errors and Their Solutions

| Common Mistake | Error / Result | Solution |
|---|---|---|
| Invalid indexing | `IndexError` | Valid index ব্যবহার করা। |
| Wrong slicing direction | Empty string | Step অনুযায়ী start ও stop নির্ধারণ করা। |
| Step = 0 | `ValueError` | Non-zero step ব্যবহার করা। |
| Stop index অন্তর্ভুক্ত মনে করা | Unexpected output | Stop index বাদ থাকে মনে রাখা। |
| String character পরিবর্তন করা | `TypeError` | নতুন string তৈরি করা। |
| Slicing result সংরক্ষণ না করা | Original string পাওয়া যায় | Result variable-এ রাখা। |
| Length-কে last index মনে করা | `IndexError` হতে পারে | `len(string) - 1` ব্যবহার করা। |

## 13. Best Practices for Indexing and Slicing

1. Index ব্যবহার করার আগে string-এর length জেনে নাও।
2. Last character access করতে `text[-1]` ব্যবহার করতে পারো।
3. Slicing-এর ক্ষেত্রে stop index বাদ থাকে মনে রাখবে।
4. Negative step ব্যবহার করলে direction খেয়াল করবে।
5. Step কখনো zero দেবে না।
6. String পরিবর্তন করতে হলে নতুন string তৈরি করবে।
7. Slicing-এর result প্রয়োজন হলে variable-এ সংরক্ষণ করবে।
8. Code run করার আগে indexing এবং slicing-এর output predict করার চেষ্টা করবে।

## 14. Practice Problems

নিচের সমস্যাগুলো নিজে সমাধান করার চেষ্টা করো।

### Problem 1: Find the Last Character

```python
text = "Programming"
```

শেষ character বের করো।

Expected Output:

```text
g
```

### Problem 2: Avoid IndexError

```python
text = "Python"
```

String-এর শেষ valid positive index ব্যবহার করে শেষ character বের করো।

Expected Output:

```text
n
```

### Problem 3: Predict the Output

```python
text = "ABCDEFGHIJ"

print(text[2:7])
print(text[-4:-1])
print(text[::2])
```

### Problem 4: Fix the Error

নিচের code-এ ভুল রয়েছে। ভুলটি সংশোধন করো।

```python
text = "Python"

print(text[::0])
```

### Problem 5: Fix the Slicing Direction

```python
text = "PYTHON"

print(text[0:5:-1])
```

Expected Output:

```text
NOHTY
```

### Problem 6: Fix the Immutability Error

```python
text = "Python"

text[0] = "J"

print(text)
```

Expected Output:

```text
Jython
```

### Problem 7: Find the Difference

```python
text = "Python"

print(text[2])
print(text[2:3])
print(type(text[2]))
print(type(text[2:3]))
```

দুটি slicing operation-এর পার্থক্য ব্যাখ্যা করো।

## 15. Summary

- Invalid index access করলে `IndexError` হয়।
- Negative indexing শেষ character থেকে `-1` দিয়ে শুরু হয়।
- Slicing-এ stop index অন্তর্ভুক্ত হয় না।
- Indexing একটি character access করে, আর slicing একটি string ফেরত দেয়।
- Negative step ব্যবহার করলে সঠিক direction বজায় রাখতে হয়।
- Step হিসেবে `0` ব্যবহার করলে `ValueError` হয়।
- String-এর length এবং last index আলাদা।
- Slicing-এর ক্ষেত্রে out-of-range index সাধারণত error তৈরি করে না।
- Python String immutable হওয়ায় character সরাসরি পরিবর্তন করা যায় না।
- Slicing-এর result সংরক্ষণ করতে নতুন variable ব্যবহার করা উচিত।

এই নিয়মগুলো বুঝতে পারলে Python String Indexing এবং Slicing-এর সাধারণ ভুলগুলো সহজেই শনাক্ত ও সমাধান করতে পারবে।