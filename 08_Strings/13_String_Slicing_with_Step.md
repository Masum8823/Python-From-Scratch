# String Slicing with Step

## 1. What is Step in String Slicing?

Python String Slicing-এ `step` ব্যবহার করে নির্ধারণ করা যায় কত ঘর পরপর character সংগ্রহ করা হবে।

সহজভাবে, `step` বলে দেয় একটি character নেওয়ার পর পরবর্তী কোন character নেওয়া হবে।

উদাহরণ:

```python
text = "ABCDEFG"

print(text[0:7:2])
```

**Output:**

```text
ACEG
```

এখানে Python প্রথমে index `0` থেকে শুরু করেছে। এরপর প্রতি 2 ঘর পরপর character নিয়েছে।

তাই পাওয়া গেছে:

- Index 0 → A
- Index 2 → C
- Index 4 → E
- Index 6 → G

অর্থাৎ, `step` ব্যবহার করে মাঝখানের কিছু character বাদ দিয়ে প্রয়োজনীয় character নেওয়া যায়।

## 2. Syntax of Slicing with Step

String Slicing with Step-এর syntax:

```python
string[start:stop:step]
```

এখানে তিনটি অংশ রয়েছে:

| Part | Description |
|---|---|
| `start` | কোন index থেকে slicing শুরু হবে। |
| `stop` | কোন index-এর আগে slicing শেষ হবে। |
| `step` | কত ঘর পরপর character নেওয়া হবে। |

**Example:**

```python
text = "PythonProgramming"

result = text[0:10:2]

print(result)
```

**Output:**

```text
PtoPo
```

**ব্যাখ্যা:**

- `start = 0` → index 0 থেকে শুরু।
- `stop = 10` → index 10 নেওয়া হবে না।
- `step = 2` → প্রতি 2 index পরপর character নেওয়া হবে।

মনে রাখবে, `start` এবং `stop` না দিলেও `step` ব্যবহার করা যায়।

## 3. Default Step Value

Python String Slicing-এ `step` না দিলে এর default value হয় `1`।

অর্থাৎ, Python প্রতিটি character এক ঘর পরপর সংগ্রহ করে।

**Example:**

```python
text = "PYTHON"

print(text[0:6])
print(text[0:6:1])
```

**Output:**

```text
PYTHON
PYTHON
```

দুটি code-এর output একই।

কারণ:

```python
text[0:6]
```

এবং

```python
text[0:6:1]
```

একইভাবে কাজ করে।

## 4. Positive Step in String Slicing

যখন `step`-এর মান positive হয়, তখন Python বাম থেকে ডান দিকে character সংগ্রহ করে।

Positive Step-এর কিছু উদাহরণ:

```python
text = "ABCDEFGHIJ"

print(text[::1])
print(text[::2])
print(text[::3])
print(text[::4])
```

**Output:**

```text
ABCDEFGHIJ
ACEGI
ADGJ
AEI
```

**ব্যাখ্যা:**

| Code | Explanation | Output |
|---|---|---|
| `text[::1]` | প্রতিটি character নেয়। | `ABCDEFGHIJ` |
| `text[::2]` | প্রতি 2 index পরপর নেয়। | `ACEGI` |
| `text[::3]` | প্রতি 3 index পরপর নেয়। | `ADGJ` |
| `text[::4]` | প্রতি 4 index পরপর নেয়। | `AEI` |

এখানে start এবং stop দেওয়া হয়নি। তাই Python পুরো string-এর ওপর slicing করেছে।

## 5. Negative Step in String Slicing

যখন `step`-এর মান negative হয়, তখন Python ডান থেকে বাম দিকে character সংগ্রহ করে।

অর্থাৎ, string-এর শেষ দিক থেকে উল্টোভাবে character নেওয়া হয়।

**Example:**

```python
text = "PYTHON"

print(text[::-1])
```

**Output:**

```text
NOHTYP
```

**ব্যাখ্যা:**

এখানে:

- `start` দেওয়া হয়নি।
- `stop` দেওয়া হয়নি।
- `step = -1`

তাই Python string-এর শেষ character থেকে শুরু করে এক ঘর করে বাম দিকে এগিয়েছে।

আরও একটি Example:

```python
text = "ABCDEFGHIJ"

print(text[::-2])
```

**Output:**

```text
JHFDB
```

এখানে Python শেষ character `J` থেকে শুরু করে প্রতি 2 index পরপর বাম দিকে character নিয়েছে।

## 6. Difference Between Positive and Negative Step

Positive এবং Negative Step-এর মধ্যে পার্থক্য:

| Positive Step | Negative Step |
|---|---|
| বাম থেকে ডানে যায়। | ডান থেকে বামে যায়। |
| সাধারণত `1, 2, 3` ব্যবহার করা হয়। | সাধারণত `-1, -2, -3` ব্যবহার করা হয়। |
| সামনে থেকে character নেয়। | পেছন থেকে character নেয়। |
| `text[::1]` পুরো string দেয়। | `text[::-1]` reverse string দেয়। |

**Example:**

```python
text = "PYTHON"

print(text[::1])
print(text[::-1])
```

**Output:**

```text
PYTHON
NOHTYP
```

## 7. Using Start, Stop and Step Together

এখন আমরা start, stop এবং step একসঙ্গে ব্যবহার করব।

**Example 1:**

```python
text = "ABCDEFGHIJ"

print(text[1:9:2])
```

**Output:**

```text
BDFH
```

**ব্যাখ্যা:**

- `start = 1` → index 1 থেকে শুরু।
- `stop = 9` → index 9 নেওয়া হবে না।
- `step = 2` → প্রতি 2 index পরপর character নেওয়া হবে।

তাই index 1, 3, 5 এবং 7-এর character পাওয়া যায়।

**Example 2:**

```python
text = "ABCDEFGHIJ"

print(text[0:10:3])
```

**Output:**

```text
ADGJ
```

এখানে index 0, 3, 6 এবং 9-এর character নেওয়া হয়েছে।

## 8. Using Step with Negative Indexing

Negative indexing-এর সঙ্গেও `step` ব্যবহার করা যায়।

**Example:**

```python
text = "PYTHON"

print(text[-1:-7:-2])
```

**Output:**

```text
NHY
```

**ব্যাখ্যা:**

- `start = -1` → শেষ character থেকে শুরু।
- `stop = -7` → index -7 নেওয়া হবে না।
- `step = -2` → প্রতি 2 index পরপর বাম দিকে যাবে।

তাই character নেওয়া হয়েছে:

- Index -1 → N
- Index -3 → H
- Index -5 → Y

ফলে output হয়েছে `NHY`।

## 9. Important Rules of Step

String Slicing-এর ক্ষেত্রে নিচের নিয়মগুলো মনে রাখতে হবে:

1. `step`-এর default value হলো `1`।
2. Positive step হলে বাম থেকে ডানে character নেওয়া হয়।
3. Negative step হলে ডান থেকে বামে character নেওয়া হয়।
4. `step = 2` হলে প্রতি 2 index পরপর character নেওয়া হয়।
5. `step = -1` ব্যবহার করে string reverse করা যায়।
6. `start` এবং `stop` বাদ দেওয়া যায়।
7. `step`-এর মান কখনো `0` হতে পারে না।

**Important Error:**

```python
text = "Python"

print(text[::0])
```

**Output:**

```text
ValueError: slice step cannot be zero
```

কারণ Python-এ slicing-এর step হিসেবে `0` ব্যবহার করা যায় না।

## 10. Common Mistakes

### Mistake 1: Using Step 0

```python
text = "Python"

print(text[::0])
```

এটি ভুল। কারণ step-এর মান কখনো zero হতে পারে না।

### Mistake 2: Wrong Slicing Direction

```python
text = "PYTHON"

print(text[0:5:-1])
```

**Output:**

```text

```

এখানে কোনো character পাওয়া যাবে না।

কারণ negative step ব্যবহার করলে Python ডান থেকে বামে যায়। কিন্তু এখানে start index `0` এবং stop index `5` দেওয়া হয়েছে।

### Mistake 3: Forgetting Stop is Excluded

```python
text = "ABCDEFG"

print(text[0:5:2])
```

**Output:**

```text
ACE
```

এখানে index 5-এর character নেওয়া হয়নি। কারণ slicing-এ stop index সবসময় বাদ থাকে।

## 11. Practice Problems

নিচের সমস্যাগুলো নিজে code লিখে সমাধান করার চেষ্টা করো।

**Problem 1:**

নিচের string থেকে প্রতি 2 index পরপর character বের করো।

```python
text = "ABCDEFGHIJ"
```

Expected Output:

```text
ACEGI
```

**Problem 2:**

নিচের string থেকে প্রতি 3 index পরপর character বের করো।

```python
text = "PROGRAMMING"
```

Expected Output:

```text
PGAI
```

**Problem 3:**

নিচের string-টি slicing ব্যবহার করে reverse করো।

```python
text = "PYTHON"
```

Expected Output:

```text
NOHTYP
```

**Problem 4:**

নিচের string থেকে index 1 থেকে index 9-এর আগ পর্যন্ত প্রতি 2 index পরপর character বের করো।

```python
text = "ABCDEFGHIJ"
```

Expected Output:

```text
BDFH
```

**Problem 5:**

Negative step ব্যবহার করে নিচের string থেকে প্রতি 2 index পরপর character বের করো।

```python
text = "ABCDEFGHIJ"
```

Expected Output:

```text
JHFDB
```

## 12. Summary

- `step` নির্ধারণ করে কত ঘর পরপর character নেওয়া হবে।
- Slicing-এর syntax হলো `string[start:stop:step]`।
- Step-এর default value হলো `1`।
- Positive step বাম থেকে ডানে কাজ করে।
- Negative step ডান থেকে বামে কাজ করে।
- `[::-1]` ব্যবহার করে string reverse করা যায়।
- `step = 0` ব্যবহার করলে `ValueError` হয়।
- Stop index কখনো output-এর অন্তর্ভুক্ত হয় না।

এইভাবে `step` ব্যবহার করে Python String-এর নির্দিষ্ট character সংগ্রহ, character skip এবং string reverse করা যায়।