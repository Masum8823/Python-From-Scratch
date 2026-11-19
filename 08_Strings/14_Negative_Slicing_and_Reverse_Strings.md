# Negative Slicing and Reverse Strings

## 1. What is Negative Slicing?

Python String Slicing-এ Negative Index ব্যবহার করে string-এর শেষ দিক থেকে character নির্বাচন করাকে Negative Slicing বলা হয়।

Negative Slicing-এর মাধ্যমে string-এর নির্দিষ্ট অংশ শেষ দিক থেকে সংগ্রহ করা যায়।

Python-এ Negative Indexing শুরু হয় `-1` থেকে।

**Example:**

```python
text = "PYTHON"

print(text[-4:-1])
```

**Output:**

```text
THO
```

**ব্যাখ্যা:**

এখানে:

- `-4` → T থেকে slicing শুরু।
- `-1` → শেষ character N নেওয়া হবে না।
- তাই output হয়েছে `THO`।

মনে রাখবে, Negative Slicing-এও stop index অন্তর্ভুক্ত হয় না।

---

## 2. Negative Indexing in Strings

Negative Slicing বোঝার আগে Negative Indexing মনে রাখা প্রয়োজন।

একটি string-এর character-গুলোর negative index হয়:

```text
Character:    P    Y    T    H    O    N
Positive:     0    1    2    3    4    5
Negative:    -6   -5   -4   -3   -2   -1
```

এখানে:

- `-1` → N
- `-2` → O
- `-3` → H
- `-4` → T
- `-5` → Y
- `-6` → P

**Example:**

```python
text = "PYTHON"

print(text[-1])
print(text[-3])
print(text[-6])
```

**Output:**

```text
N
H
P
```

---

## 3. Negative Slicing with Start and Stop

Negative Index ব্যবহার করে string-এর নির্দিষ্ট অংশ সংগ্রহ করা যায়।

**Syntax:**

```python
string[start:stop]
```

**Example 1:**

```python
text = "PROGRAMMING"

print(text[-5:-1])
```

**Output:**

```text
MMIN
```

**ব্যাখ্যা:**

- `start = -5` → M থেকে শুরু।
- `stop = -1` → শেষ character নেওয়া হবে না।
- তাই output হয়েছে `MMIN`।

**Example 2:**

```python
text = "PROGRAMMING"

print(text[-8:-3])
```

**Output:**

```text
GRAMM
```

এখানে index `-8` থেকে শুরু করে `-3`-এর আগ পর্যন্ত character নেওয়া হয়েছে।

---

## 4. Negative Slicing with Step

Negative Indexing-এর সঙ্গে Positive Step ব্যবহার করা যায়।

**Example:**

```python
text = "ABCDEFGHIJ"

print(text[-9:-1:2])
```

**Output:**

```text
BDFH
```

**ব্যাখ্যা:**

- `start = -9` → B থেকে শুরু।
- `stop = -1` → J নেওয়া হবে না।
- `step = 2` → প্রতি 2 index পরপর character নেওয়া হবে।

তাই output হয়েছে `BDFH`।

---

## 5. Negative Step in Slicing

Negative Step ব্যবহার করলে Python ডান থেকে বাম দিকে character সংগ্রহ করে।

এক্ষেত্রে সাধারণত start index-এর অবস্থান stop index-এর চেয়ে ডান দিকে হতে হয়।

**Example:**

```python
text = "PYTHON"

print(text[5:1:-1])
```

**Output:**

```text
NOHT
```

**ব্যাখ্যা:**

- `start = 5` → N থেকে শুরু।
- `stop = 1` → index 1 নেওয়া হবে না।
- `step = -1` → এক ঘর করে বাম দিকে যাবে।

তাই character নেওয়া হয়েছে N, O, H এবং T।

---

## 6. Negative Slicing with Negative Start and Stop

Start এবং stop দুটিই negative হতে পারে। পাশাপাশি negative step-ও ব্যবহার করা যায়।

**Example:**

```python
text = "ABCDEFGHIJ"

print(text[-1:-6:-1])
```

**Output:**

```text
JIHGF
```

**ব্যাখ্যা:**

- `start = -1` → J থেকে শুরু।
- `stop = -6` → E নেওয়া হবে না।
- `step = -1` → এক ঘর করে বাম দিকে যাবে।

তাই output হয়েছে `JIHGF`।

---

## 7. Reversing a String in Python

একটি string-এর character-গুলোকে উল্টো ক্রমে সাজানোকে String Reversing বলা হয়।

Python-এ slicing ব্যবহার করে সহজেই string reverse করা যায়।

এর জন্য `[::-1]` ব্যবহার করা হয়।

**Example:**

```python
text = "Python"

reverse_text = text[::-1]

print(reverse_text)
```

**Output:**

```text
nohtyP
```

**ব্যাখ্যা:**

এখানে:

- `start` দেওয়া হয়নি।
- `stop` দেওয়া হয়নি।
- `step = -1`।

তাই Python শেষ character থেকে শুরু করে প্রথম character পর্যন্ত উল্টোভাবে সংগ্রহ করেছে।

---

## 8. Different Ways to Reverse a String

Python-এ বিভিন্নভাবে string reverse করা যায়।

### Method 1: Using Slicing

```python
text = "PROGRAMMING"

reverse_text = text[::-1]

print(reverse_text)
```

**Output:**

```text
GNIMMARGORP
```

এটি string reverse করার সবচেয়ে সহজ পদ্ধতি।

### Method 2: Using a for Loop

```python
text = "PYTHON"

reverse_text = ""

for char in text:
    reverse_text = char + reverse_text

print(reverse_text)
```

**Output:**

```text
NOHTYP
```

**ব্যাখ্যা:**

- প্রথমে একটি empty string নেওয়া হয়েছে।
- এরপর loop দিয়ে প্রতিটি character সংগ্রহ করা হয়েছে।
- প্রতিবার নতুন character-টি আগের string-এর সামনে যোগ করা হয়েছে।
- ফলে string উল্টো হয়ে গেছে।

### Method 3: Using reversed() Function

Python-এর built-in `reversed()` function ব্যবহার করেও string reverse করা যায়।

```python
text = "PYTHON"

reverse_text = "".join(reversed(text))

print(reverse_text)
```

**Output:**

```text
NOHTYP
```

**ব্যাখ্যা:**

- `reversed(text)` string-এর character-গুলো উল্টো ক্রমে দেয়।
- `join()` character-গুলো একসঙ্গে যুক্ত করে নতুন string তৈরি করে।

মনে রাখবে, `reversed()` সরাসরি string ফেরত দেয় না; এটি একটি reverse iterator ফেরত দেয়।

---

## 9. Extracting a Portion of a String in Reverse

Negative Step ব্যবহার করে string-এর শুধু নির্দিষ্ট অংশ reverse করা যায়।

**Example 1:**

```python
text = "ABCDEFGHIJ"

print(text[7:2:-1])
```

**Output:**

```text
HGFED
```

এখানে index 7 থেকে শুরু করে index 3 পর্যন্ত character উল্টোভাবে নেওয়া হয়েছে।

**Example 2:**

```python
text = "PROGRAMMING"

print(text[8:3:-1])
```

**Output:**

```text
MMARG
```

এখানে index 8 থেকে index 4 পর্যন্ত character reverse করে নেওয়া হয়েছে।

---

## 10. Reversing Words and Sentences

String reverse করা এবং sentence-এর word-এর order reverse করা এক বিষয় নয়।

**Example 1: Reverse the Entire Sentence**

```python
text = "I love Python"

print(text[::-1])
```

**Output:**

```text
nohtyP evol I
```

এখানে পুরো sentence-এর প্রতিটি character উল্টো হয়েছে।

**Example 2: Reverse Word Order**

```python
text = "I love Python"

words = text.split()

reverse_text = " ".join(words[::-1])

print(reverse_text)
```

**Output:**

```text
Python love I
```

এখানে word-এর order উল্টো হয়েছে, কিন্তু প্রতিটি word-এর spelling ঠিক রয়েছে।

---

## 11. Important Rules to Remember

1. Negative Indexing শুরু হয় `-1` থেকে।
2. Negative Slicing-এও stop index অন্তর্ভুক্ত হয় না।
3. Negative Step ব্যবহার করলে ডান থেকে বাম দিকে character নেওয়া হয়।
4. `[::-1]` দিয়ে পুরো string reverse করা যায়।
5. `reversed()` একটি reverse iterator ফেরত দেয়।
6. String reverse করলে original string পরিবর্তন হয় না।
7. String immutable হওয়ায় reverse করার ফলাফল নতুন string হিসেবে সংরক্ষণ করতে হয়।
8. পুরো string reverse করা এবং word-এর order reverse করা আলাদা বিষয়।

---

## 12. Common Mistakes

### Mistake 1: Incorrect Slicing Direction

```python
text = "PYTHON"

print(text[0:5:-1])
```

**Output:**

```text

```

এখানে কোনো character পাওয়া যাবে না।

কারণ negative step দিয়ে ডান থেকে বামে যেতে হয়। কিন্তু start index 0 এবং stop index 5 দেওয়া হয়েছে।

### Mistake 2: Including the Stop Index

```python
text = "PYTHON"

print(text[-1:-4:-1])
```

**Output:**

```text
NOH
```

এখানে `-4` index-এর character T নেওয়া হয়নি।

### Mistake 3: Forgetting to Store the Reversed String

```python
text = "PYTHON"

text[::-1]

print(text)
```

**Output:**

```text
PYTHON
```

এখানে reverse operation-এর ফলাফল সংরক্ষণ করা হয়নি।

সঠিক পদ্ধতি:

```python
text = "PYTHON"

reverse_text = text[::-1]

print(reverse_text)
```

**Output:**

```text
NOHTYP
```

---

## 13. Practice Problems

নিজে চেষ্টা করে সমাধান করো।

### Problem 1: Negative Slicing

নিচের string থেকে শেষের 5টি character বের করো।

```python
text = "PROGRAMMING"
```

Expected Output:

```text
MMING
```

### Problem 2: Reverse a String

Slicing ব্যবহার করে string-টি reverse করো।

```python
text = "COMPUTER"
```

Expected Output:

```text
RETUPMOC
```

### Problem 3: Negative Step

Negative Step ব্যবহার করে নিচের string-এর character-গুলো উল্টোভাবে বের করো।

```python
text = "ABCDEFGHIJ"
```

Expected Output:

```text
JIHGFEDCBA
```

### Problem 4: Reverse a Portion

Index 7 থেকে index 2 পর্যন্ত string-এর অংশ reverse করে বের করো।

```python
text = "ABCDEFGHIJ"
```

Expected Output:

```text
HGFED
```

### Problem 5: Reverse Word Order

নিচের sentence-এর word-এর order reverse করো।

```python
text = "I am learning Python"
```

Expected Output:

```text
Python learning am I
```

### Problem 6: Reverse Using a Loop

Slicing ব্যবহার না করে `for` loop দিয়ে string reverse করো।

```python
text = "BANGLADESH"
```

Expected Output:

```text
HSEDALGNAB
```

---

## 14. Summary

- Negative Slicing ব্যবহার করে negative index দিয়ে string-এর অংশ সংগ্রহ করা যায়।
- Negative Indexing শুরু হয় `-1` থেকে।
- Negative Step ব্যবহার করে ডান থেকে বাম দিকে character নেওয়া যায়।
- `[::-1]` হলো string reverse করার সহজ পদ্ধতি।
- `reversed()` function দিয়েও string reverse করা যায়।
- `split()` এবং `join()` ব্যবহার করে word-এর order reverse করা যায়।
- String immutable হওয়ায় reverse operation মূল string পরিবর্তন করে না।

এইভাবে Python-এ Negative Slicing এবং বিভিন্ন পদ্ধতি ব্যবহার করে সম্পূর্ণ string অথবা string-এর নির্দিষ্ট অংশ reverse করা যায়।