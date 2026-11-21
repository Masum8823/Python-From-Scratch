
# 29. Splitting Strings with split() in Python

## 1. Introduction to split() Method

Python-এ একটি String-কে একাধিক ছোট অংশে ভাগ করার জন্য `split()` method ব্যবহার করা হয়।

এই method একটি String-কে নির্দিষ্ট separator অনুযায়ী ভাগ করে এবং প্রতিটি অংশকে একটি List-এর মধ্যে রাখে।

**Example:**

```python
text = "I love Python"

result = text.split()

print(result)
```

**Output:**

```text
['I', 'love', 'Python']
```

**Explanation:**

- `split()` String-টিকে আলাদা আলাদা Word-এ ভাগ করেছে।
- প্রতিটি Word List-এর একটি Element হিসেবে সংরক্ষিত হয়েছে।
- এখানে কোনো separator দেওয়া হয়নি, তাই default whitespace অনুযায়ী String ভাগ হয়েছে।

## 2. Syntax of split() Method

**Syntax:**

```python
string.split(separator, maxsplit)
```

**Parameters:**

| Parameter | Description |
|---|---|
| `separator` | যে character বা text অনুযায়ী String ভাগ হবে (optional) |
| `maxsplit` | সর্বোচ্চ কতবার split হবে (optional) |

দুটি parameter-ই optional।

## 3. Splitting a String by Spaces

কোনো separator না দিলে `split()` সাধারণ whitespace অনুযায়ী String ভাগ করে।

**Example 1:**

```python
text = "Python is easy"

result = text.split()

print(result)
```

**Output:**

```text
['Python', 'is', 'easy']
```

**Example 2:**

```python
text = "I love learning Python programming"

words = text.split()

print(words)
```

**Output:**

```text
['I', 'love', 'learning', 'Python', 'programming']
```

**Explanation:**

Default `split()` এক বা একাধিক consecutive whitespace-কে separator হিসেবে বিবেচনা করে।

শুরুতে বা শেষে whitespace থাকলেও সাধারণত empty element তৈরি হয় না।

## 4. Splitting a String Using a Specific Separator

`split()` method-এর মধ্যে নির্দিষ্ট separator দেওয়া যায়।

**Example 1: Splitting by Comma**

```python
text = "Apple,Banana,Mango"

result = text.split(",")

print(result)
```

**Output:**

```text
['Apple', 'Banana', 'Mango']
```

**Example 2: Splitting by Hyphen**

```python
text = "Python-is-easy"

result = text.split("-")

print(result)
```

**Output:**

```text
['Python', 'is', 'easy']
```

**Example 3: Splitting by Slash**

```python
text = "2026/11/18"

result = text.split("/")

print(result)
```

**Output:**

```text
['2026', '11', '18']
```

**Explanation:**

- `","` দিলে comma অনুযায়ী ভাগ হয়।
- `"-"` দিলে hyphen অনুযায়ী ভাগ হয়।
- `"/"` দিলে slash অনুযায়ী ভাগ হয়।

## 5. Using maxsplit Parameter

`maxsplit` parameter ব্যবহার করে সর্বোচ্চ কতবার String split হবে তা নির্ধারণ করা যায়।

**Example 1:**

```python
text = "Python is easy to learn"

result = text.split(" ", 1)

print(result)
```

**Output:**

```text
['Python', 'is easy to learn']
```

এখানে `maxsplit=1` দেওয়ায় প্রথম space-এর পর একবার split হয়েছে।

**Example 2:**

```python
text = "Python is easy to learn"

result = text.split(" ", 2)

print(result)
```

**Output:**

```text
['Python', 'is', 'easy to learn']
```

এখানে সর্বোচ্চ দুইবার split হয়েছে।

**Example 3:**

```python
text = "Apple,Banana,Mango,Orange"

result = text.split(",", 2)

print(result)
```

**Output:**

```text
['Apple', 'Banana', 'Mango,Orange']
```

এখানে প্রথম দুটি comma-তে split হয়েছে। বাকি অংশ একই Element হিসেবে রয়েছে।

## 6. Difference Between split() and split(" ")

এই দুটি ব্যবহার দেখতে কাছাকাছি হলেও তাদের মধ্যে গুরুত্বপূর্ণ পার্থক্য রয়েছে।

### Example 1: Using split()

```python
text = "  Python   is   easy  "

print(text.split())
```

**Output:**

```text
['Python', 'is', 'easy']
```

### Example 2: Using split(" ")

```python
text = "  Python   is   easy  "

print(text.split(" "))
```

**Output:**

```text
['', '', 'Python', '', '', 'is', '', '', 'easy', '', '']
```

**Explanation:**

- `split()` এক বা একাধিক consecutive whitespace-কে একটি separator হিসেবে বিবেচনা করে।
- `split(" ")` শুধু একটি নির্দিষ্ট space character দিয়ে split করে।
- `split(" ")` ব্যবহার করলে consecutive space এবং শুরু বা শেষের space-এর কারণে empty String তৈরি হতে পারে।

**Important:** সাধারণ Word Splitting-এর জন্য `split()` ব্যবহার করা বেশি সুবিধাজনক।

## 7. Splitting a String into Individual Characters

একটি String-এর প্রতিটি character আলাদা Element হিসেবে পাওয়ার জন্য `split()` সরাসরি ব্যবহার করা যায় না।

কারণ `split()` separator অনুযায়ী String ভাগ করে, character অনুযায়ী নয়।

**Example:**

```python
text = "Python"

result = list(text)

print(result)
```

**Output:**

```text
['P', 'y', 't', 'h', 'o', 'n']
```

**Explanation:**

এখানে `list()` function ব্যবহার করে String-এর প্রতিটি character আলাদা Element হিসেবে List-এ রাখা হয়েছে।

## 8. Splitting an Empty String

Default `split()` ব্যবহার করে Empty String split করলে Empty List পাওয়া যায়।

**Example 1:**

```python
text = ""

result = text.split()

print(result)
```

**Output:**

```text
[]
```

**Example 2:**

```python
text = ""

result = text.split(",")

print(result)
```

**Output:**

```text
['']
```

**Explanation:**

- `split()` কোনো separator ছাড়া Empty String-এর জন্য Empty List return করে।
- কিন্তু নির্দিষ্ট separator দিলে Empty String একটি Element হিসেবে পাওয়া যায়।

## 9. Splitting a String with Multiple Consecutive Separators

নির্দিষ্ট separator বারবার থাকলে `split()` মাঝখানে Empty String তৈরি করতে পারে।

**Example:**

```python
text = "Apple,,Banana,Mango"

result = text.split(",")

print(result)
```

**Output:**

```text
['Apple', '', 'Banana', 'Mango']
```

**Explanation:**

Apple এবং Banana-এর মাঝখানে দুটি comma রয়েছে।

তাই Python-এর `split()` সেখানে একটি Empty String তৈরি করেছে।

## 10. Splitting a String Using Newline

Newline character (`\n`) ব্যবহার করেও String ভাগ করা যায়।

**Example:**

```python
text = "Hello\nPython\nProgramming"

result = text.split("\n")

print(result)
```

**Output:**

```text
['Hello', 'Python', 'Programming']
```

**Explanation:**

এখানে প্রতিটি newline character অনুযায়ী String ভাগ হয়েছে।

## 11. split() Returns a List

`split()` method সবসময় একটি List return করে।

এই List-এর প্রতিটি Element হলো String-এর একটি অংশ।

**Example:**

```python
text = "Python is powerful"

result = text.split()

print(result)
print(type(result))
```

**Output:**

```text
['Python', 'is', 'powerful']
<class 'list'>
```

**Explanation:**

- `split()` String-কে List-এ রূপান্তর করেছে।
- List-এর প্রতিটি Element আলাদা String।
- `type()` দিয়ে Result-এর Data Type পরীক্ষা করা হয়েছে।

## 12. Accessing Elements After Splitting

`split()` করার পর পাওয়া List-এর Element Index ব্যবহার করে access করা যায়।

**Example:**

```python
text = "Python is easy"

words = text.split()

print(words[0])
print(words[1])
print(words[2])
```

**Output:**

```text
Python
is
easy
```

**Explanation:**

- `words[0]` প্রথম Word।
- `words[1]` দ্বিতীয় Word।
- `words[2]` তৃতীয় Word।

## 13. Using split() with User Input

User-এর কাছ থেকে একাধিক Word বা Item Input নিয়ে সেগুলো আলাদা করতে `split()` ব্যবহার করা যায়।

**Example 1: Taking Multiple Words**

```python
text = input("Enter some words: ")

words = text.split()

print(words)
```

**Input:**

```text
I love Python
```

**Output:**

```text
['I', 'love', 'Python']
```

**Example 2: Taking Comma-Separated Values**

```python
text = input("Enter three fruits: ")

fruits = text.split(",")

print(fruits)
```

**Input:**

```text
Apple,Banana,Mango
```

**Output:**

```text
['Apple', 'Banana', 'Mango']
```

## 14. Practical Examples

### Example 1: Counting Words in a Sentence

```python
sentence = "Python is easy to learn"

words = sentence.split()

print("Total words:", len(words))
```

**Output:**

```text
Total words: 5
```

**Explanation:**

- `split()` sentence-টিকে Word অনুযায়ী ভাগ করেছে।
- `len()` List-এর মোট Element সংখ্যা গণনা করেছে।
- এভাবেই মোট Word সংখ্যা পাওয়া গেছে।

### Example 2: Extracting Date Information

```python
date = "18-11-2026"

parts = date.split("-")

print("Day:", parts[0])
print("Month:", parts[1])
print("Year:", parts[2])
```

**Output:**

```text
Day: 18
Month: 11
Year: 2026
```

### Example 3: Extracting Email Parts

```python
email = "masum@gmail.com"

parts = email.split("@")

print("Username:", parts[0])
print("Domain:", parts[1])
```

**Output:**

```text
Username: masum
Domain: gmail.com
```

**Note:** এটি একটি সাধারণ example। বাস্তব email address validation-এর জন্য শুধু `split()` যথেষ্ট নয়।

### Example 4: Splitting a Sentence and Printing Each Word

```python
sentence = "I love Python programming"

words = sentence.split()

for word in words:
    print(word)
```

**Output:**

```text
I
love
Python
programming
```

### Example 5: Splitting and Converting Values into Integers

`split()` দিয়ে পাওয়া প্রতিটি Element String হয়। প্রয়োজন হলে সেগুলোকে `int()` দিয়ে Integer-এ convert করা যায়।

```python
numbers = "10 20 30 40"

parts = numbers.split()

result = []

for num in parts:
    result.append(int(num))

print(result)
```

**Output:**

```text
[10, 20, 30, 40]
```

## 15. Common Mistakes in split() Method

### Mistake 1: Using the Wrong Separator

**Incorrect Code:**

```python
text = "Apple,Banana,Mango"

result = text.split("-")

print(result)
```

**Output:**

```text
['Apple,Banana,Mango']
```

**Why?**

String-এর মধ্যে `-` নেই। তাই কোনো split হয়নি।

**Correct Code:**

```python
text = "Apple,Banana,Mango"

result = text.split(",")

print(result)
```

**Output:**

```text
['Apple', 'Banana', 'Mango']
```

### Mistake 2: Expecting split() to Return a String

**Example:**

```python
text = "Hello Python"

result = text.split()

print(type(result))
```

**Output:**

```text
<class 'list'>
```

**Why?**

`split()` একটি List return করে, String নয়।

### Mistake 3: Confusing split() and split(" ")

**Example:**

```python
text = "Python   is   easy"

print(text.split())
print(text.split(" "))
```

**Output:**

```text
['Python', 'is', 'easy']
['Python', '', '', 'is', '', '', 'easy']
```

**Why?**

Default `split()` একাধিক consecutive whitespace একসঙ্গে handle করে। কিন্তু `split(" ")` প্রতিটি space অনুযায়ী আলাদা করে split করে।

### Mistake 4: Forgetting That maxsplit Limits Splitting

**Example:**

```python
text = "A-B-C-D"

result = text.split("-", 1)

print(result)
```

**Output:**

```text
['A', 'B-C-D']
```

**Why?**

`maxsplit=1` দেওয়ায় শুধু প্রথম separator-এ split হয়েছে।

## 16. Important Rules to Remember

1. `split()` একটি String-কে একাধিক অংশে ভাগ করে।
2. `split()` একটি List return করে।
3. Default `split()` whitespace অনুযায়ী String ভাগ করে।
4. নির্দিষ্ট separator ব্যবহার করেও String ভাগ করা যায়।
5. `maxsplit` দিয়ে সর্বোচ্চ split-এর সংখ্যা নির্ধারণ করা যায়।
6. Default `split()` একাধিক consecutive whitespace handle করে।
7. `split(" ")` এবং `split()` একভাবে কাজ করে না।
8. নির্দিষ্ট separator একাধিকবার থাকলে Empty String তৈরি হতে পারে।
9. `split()` দিয়ে পাওয়া প্রতিটি Element একটি String।
10. String-এর প্রতিটি character আলাদা করতে `list()` ব্যবহার করা যায়।
11. `split()` Original String পরিবর্তন করে না।
12. Word counting-এর জন্য `len(text.split())` ব্যবহার করা যায়।

## 17. Practice Problems

### Problem 1: Split a Sentence

```python
text = "I love Python programming"

# Split the sentence into words
```

**Expected Output:**

```text
['I', 'love', 'Python', 'programming']
```

### Problem 2: Split Using Comma

```python
text = "Apple,Banana,Mango,Orange"

# Split the String using comma
```

**Expected Output:**

```text
['Apple', 'Banana', 'Mango', 'Orange']
```

### Problem 3: Split Using Hyphen

```python
text = "Python-is-easy"

# Split the String using hyphen
```

**Expected Output:**

```text
['Python', 'is', 'easy']
```

### Problem 4: Use maxsplit

```python
text = "A-B-C-D"

# Split the String only once
```

**Expected Output:**

```text
['A', 'B-C-D']
```

### Problem 5: Count Words

```python
sentence = "Python is a powerful language"

# Count the total number of words
```

**Expected Output:**

```text
5
```

### Problem 6: Extract Email Parts

```python
email = "masum@gmail.com"

# Extract username and domain separately
```

**Expected Output:**

```text
masum
gmail.com
```

### Problem 7: Split and Convert into Integers

```python
numbers = "10 20 30 40"

# Split the numbers and convert them into integers
```

**Expected Output:**

```text
[10, 20, 30, 40]
```

## 18. Chapter Summary

এই Topic-এ আমরা Python-এর `split()` method সম্পর্কে শিখেছি।

আমরা শিখেছি:

- `split()` method এবং এর syntax
- Whitespace অনুযায়ী String splitting
- Specific separator ব্যবহার
- `maxsplit` parameter
- `split()` এবং `split(" ")`-এর পার্থক্য
- Empty String এবং consecutive separator
- Newline দিয়ে String splitting
- `split()` থেকে পাওয়া List-এর Element access
- User Input থেকে একাধিক value নেওয়া
- Practical examples এবং common mistakes

**Next Topic:**

`30_Joining_Strings_with_join.md`

পরবর্তী Topic-এ আমরা Python-এর `join()` method ব্যবহার করে একাধিক String একসঙ্গে যুক্ত করা শিখব।
