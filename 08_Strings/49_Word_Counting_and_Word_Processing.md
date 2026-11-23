# 49. Word Counting and Word Processing in Python

## 1. Introduction

Python-এ কোনো String-এর মধ্যে মোট কতটি word আছে, কোন word কতবার এসেছে এবং নির্দিষ্ট word খুঁজে বের করার মতো কাজগুলোকে **Word Processing** বলে।

ধরো, আমাদের একটি String আছে:

```python
text = "I love Python and I love programming"
```

এখানে মোট 7টি word রয়েছে।

এছাড়া:
- `I` এসেছে 2 বার।
- `love` এসেছে 2 বার।
- `Python` এসেছে 1 বার।
- `and` এসেছে 1 বার।
- `programming` এসেছে 1 বার।

Python-এ `split()`, `len()`, Loop এবং Dictionary ব্যবহার করে সহজেই Word Processing করা যায়।

এই topic-এ আমরা শিখব:

- Word Counting কী।
- String-এর মোট word সংখ্যা গণনা করা।
- `split()` দিয়ে word আলাদা করা।
- প্রতিটি word-এর frequency গণনা করা।
- Duplicate words খুঁজে বের করা।
- Unique words খুঁজে বের করা।
- সবচেয়ে বেশি ব্যবহৃত word খুঁজে বের করা।
- User input থেকে word processing করা।
- Sentence-এর word এবং character গণনা করা।

---

## 2. What is Word Counting?

কোনো String বা Sentence-এর মধ্যে মোট কতটি word রয়েছে, তা গণনা করাকে Word Counting বলে।

**Example:**

```python
text = "I am learning Python"
```

এখানে মোট 4টি word রয়েছে।

**Output:**

```text
Total words: 4
```

Python-এ Word Counting করার জন্য সাধারণত `split()` এবং `len()` ব্যবহার করা হয়।

---

## 3. Splitting a String into Words

Python-এর `split()` method ব্যবহার করে একটি String-কে একাধিক word-এ ভাগ করা যায়।

**Syntax:**

```python
string.split()
```

এটি String-কে ভাগ করে একটি List return করে।

**Example:**

```python
text = "I love Python"

words = text.split()

print(words)
```

**Output:**

```text
['I', 'love', 'Python']
```

**Explanation:**

1. `text.split()` String-টিকে আলাদা আলাদা word-এ ভাগ করেছে।
2. প্রতিটি word List-এর একটি element হিসেবে সংরক্ষিত হয়েছে।
3. `words` variable-এ তৈরি হওয়া List সংরক্ষণ করা হয়েছে।

**Important:**

`split()` ব্যবহার করলে মূল String পরিবর্তন হয় না। এটি একটি নতুন List return করে।

---

## 4. Counting Total Words Using len()

`len()` function ব্যবহার করে একটি List-এর মোট element সংখ্যা বের করা যায়।

যেহেতু `split()` String-কে List-এ পরিণত করে, তাই `len()` দিয়ে মোট word গণনা করা যায়।

**Example:**

```python
text = "I love Python programming"

words = text.split()

total = len(words)

print("Total words:", total)
```

**Output:**

```text
Total words: 4
```

**Explanation:**

- `split()` Sentence-টিকে List-এ ভাগ করেছে।
- `len(words)` List-এর মোট element গণনা করেছে।
- প্রতিটি element একটি word নির্দেশ করছে।

তাই মোট word সংখ্যা 4।

---

## 5. Counting Words Directly Using split() and len()

`split()` এবং `len()` একসাথেও ব্যবহার করা যায়।

**Example:**

```python
text = "Python is easy to learn"

print("Total words:", len(text.split()))
```

**Output:**

```text
Total words: 5
```

**Explanation:**

1. `text.split()` Sentence-টিকে List-এ ভাগ করেছে।
2. `len()` List-এর মোট word সংখ্যা বের করেছে।
3. Result সরাসরি print হয়েছে।

এটি Word Counting করার সবচেয়ে সহজ পদ্ধতি।

---

## 6. Finding Each Word Separately Using a Loop

`for` loop ব্যবহার করে Sentence-এর প্রতিটি word আলাদাভাবে print করা যায়।

**Example:**

```python
text = "I love Python programming"

words = text.split()

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

**Explanation:**

1. `split()` Sentence-টিকে List-এ ভাগ করেছে।
2. `for` loop List-এর প্রতিটি word-এর ওপর কাজ করছে।
3. `print(word)` প্রতিটি word আলাদাভাবে দেখাচ্ছে।

---

## 7. Counting the Frequency of Each Word

Character Frequency-এর মতো Word Frequency-ও বের করা যায়।

অর্থাৎ, Sentence-এর মধ্যে প্রতিটি word কতবার এসেছে তা গণনা করা।

এক্ষেত্রে Dictionary ব্যবহার করা সুবিধাজনক।

**Example:**

```python
text = "I love Python and I love programming"

words = text.split()

frequency = {}

for word in words:
    if word in frequency:
        frequency[word] += 1
    else:
        frequency[word] = 1

print(frequency)
```

**Output:**

```text
{'I': 2, 'love': 2, 'Python': 1, 'and': 1, 'programming': 1}
```

**Explanation:**

1. `split()` Sentence-টিকে List-এ ভাগ করেছে।
2. `frequency = {}` দিয়ে একটি empty Dictionary তৈরি হয়েছে।
3. Loop প্রতিটি word পরীক্ষা করছে।
4. Word আগে Dictionary-তে থাকলে frequency 1 বাড়ছে।
5. Word আগে না থাকলে frequency 1 নির্ধারণ হচ্ছে।
6. শেষে প্রতিটি word-এর frequency Dictionary-তে সংরক্ষিত হচ্ছে।

---

## 8. Displaying Each Word with Its Frequency

Dictionary ব্যবহার করে প্রতিটি word এবং তার frequency আলাদাভাবে print করা যায়।

**Example:**

```python
text = "I love Python and I love programming"

words = text.split()

frequency = {}

for word in words:
    if word in frequency:
        frequency[word] += 1
    else:
        frequency[word] = 1

for word, count in frequency.items():
    print(word, "=", count)
```

**Output:**

```text
I = 2
love = 2
Python = 1
and = 1
programming = 1
```

**Explanation:**

- `frequency.items()` Dictionary-এর Key এবং Value একসাথে দেয়।
- `word` হলো Dictionary-এর Key।
- `count` হলো সেই word-এর frequency।
- Loop প্রতিটি word-এর frequency print করছে।

**Important:**

এখানে Word হলো Key এবং Frequency হলো Value।

---

## 9. Finding Duplicate Words

কোনো Sentence-এর মধ্যে একই word একাধিকবার থাকলে তাকে Duplicate Word বলে।

**Example:**

```python
text = "Python is easy and Python is powerful"

words = text.split()

checked = ""

for word in words:
    if words.count(word) > 1 and word not in checked:
        print(word)
        checked += word + " "
```

**Output:**

```text
Python
is
```

**Explanation:**

1. `split()` Sentence-টিকে List-এ ভাগ করেছে।
2. `words.count(word)` দিয়ে word কতবার এসেছে তা গণনা হচ্ছে।
3. `words.count(word) > 1` দিয়ে duplicate word শনাক্ত হচ্ছে।
4. `word not in checked` দিয়ে একই word বারবার print হওয়া বন্ধ হচ্ছে।
5. `checked += word + " "` দিয়ে word-টি সংরক্ষণ হচ্ছে।

---

## 10. Finding Unique Words

কোনো Sentence-এর মধ্যে যে word মাত্র একবার এসেছে তাকে Unique Word বলা যায়।

**Example:**

```python
text = "Python is easy and Python is powerful"

words = text.split()

for word in words:
    if words.count(word) == 1:
        print(word)
```

**Output:**

```text
easy
and
powerful
```

**Explanation:**

- `words.count(word)` word-এর frequency বের করে।
- `== 1` দিয়ে পরীক্ষা করা হয় word-টি মাত্র একবার এসেছে কি না।
- শর্ত পূরণ হলে word print হয়।

**Important:**

এখানে কোনো word একাধিকবার থাকলে সেটি Unique Word হিসেবে print হবে না।

---

## 11. Finding the Most Frequent Word

কোনো Sentence-এর মধ্যে সবচেয়ে বেশি ব্যবহৃত word খুঁজে বের করতে Dictionary এবং `max()` ব্যবহার করা যায়।

**Example:**

```python
text = "I love Python and I love programming"

words = text.split()

frequency = {}

for word in words:
    if word in frequency:
        frequency[word] += 1
    else:
        frequency[word] = 1

most_frequent = max(frequency, key=frequency.get)

print("Most frequent word:", most_frequent)
print("Frequency:", frequency[most_frequent])
```

**Output:**

```text
Most frequent word: I
Frequency: 2
```

**Explanation:**

1. প্রথমে Dictionary-তে প্রতিটি word-এর frequency গণনা করা হয়েছে।
2. `max()` সবচেয়ে বেশি frequency-যুক্ত word খুঁজে বের করছে।
3. `key=frequency.get` দিয়ে Dictionary-এর Value অনুযায়ী comparison হচ্ছে।
4. শেষে word এবং তার frequency print হচ্ছে।

**Important:**

যদি একাধিক word-এর frequency সমান সর্বোচ্চ হয়, তাহলে `max()` প্রথম পাওয়া word-টি return করে।

---

## 12. Case-Insensitive Word Counting

Python-এ Uppercase এবং Lowercase word আলাদা হিসেবে বিবেচিত হয়।

যেমন:

```python
text = "Python python PYTHON"

words = text.split()

frequency = {}

for word in words:
    if word in frequency:
        frequency[word] += 1
    else:
        frequency[word] = 1

print(frequency)
```

**Output:**

```text
{'Python': 1, 'python': 1, 'PYTHON': 1}
```

কিন্তু আমরা যদি সব word একইভাবে গণনা করতে চাই, তাহলে `lower()` ব্যবহার করতে পারি।

**Example:**

```python
text = "Python python PYTHON"

words = text.lower().split()

frequency = {}

for word in words:
    if word in frequency:
        frequency[word] += 1
    else:
        frequency[word] = 1

print(frequency)
```

**Output:**

```text
{'python': 3}
```

**Explanation:**

- `lower()` সব word-কে lowercase করেছে।
- `split()` Sentence-টিকে List-এ ভাগ করেছে।
- Dictionary একই word-এর frequency গণনা করেছে।

এভাবে Uppercase এবং Lowercase-এর পার্থক্য ছাড়াই Word Counting করা যায়।

---

## 13. Removing Extra Spaces Before Word Counting

একটি Sentence-এর মধ্যে একাধিক space থাকলেও `split()` সাধারণভাবে সঠিকভাবে word আলাদা করতে পারে।

**Example:**

```python
text = "I    love     Python"

words = text.split()

print(words)
print("Total words:", len(words))
```

**Output:**

```text
['I', 'love', 'Python']
Total words: 3
```

**Explanation:**

`split()` কোনো separator উল্লেখ না করলে এক বা একাধিক whitespace-এর ভিত্তিতে String ভাগ করে।

এখানে অতিরিক্ত space-এর কারণে word counting-এ সমস্যা হয়নি।

**Important:**

`split()`-এর ভেতরে কোনো argument না দিলে এটি space, tab এবং newline-এর মতো whitespace ব্যবহার করে word আলাদা করে।

---

## 14. Counting Words and Characters Together

একটি Sentence থেকে মোট word এবং character-এর সংখ্যা একসাথে বের করা যায়।

**Example:**

```python
text = "I love Python"

words = text.split()

total_words = len(words)
total_characters = len(text)

print("Total words:", total_words)
print("Total characters:", total_characters)
```

**Output:**

```text
Total words: 3
Total characters: 13
```

**Explanation:**

- `len(words)` মোট word গণনা করেছে।
- `len(text)` String-এর সব character গণনা করেছে।
- এখানে space-ও character হিসেবে গণনা হয়েছে।

**Important:**

`len(text)` space-সহ সব character গণনা করে।

অন্যদিকে, `len(text.replace(" ", ""))` ব্যবহার করলে সাধারণ space বাদ দিয়ে character গণনা করা যায়।

---

## 15. Word Counting from User Input

এবার User-এর কাছ থেকে একটি Sentence input নিয়ে মোট word সংখ্যা বের করব।

**Example:**

```python
text = input("Enter a sentence: ")

words = text.split()

total = len(words)

print("Total words:", total)
```

**Example Input:**

```text
I am learning Python programming
```

**Output:**

```text
Total words: 5
```

**Explanation:**

User-এর দেওয়া Sentence প্রথমে `split()` দিয়ে List-এ ভাগ হয়েছে।

এরপর `len()` দিয়ে মোট word সংখ্যা বের হয়েছে।

---

## 16. Practical Example: Complete Word Frequency Counter

এবার একটি Complete Program তৈরি করব, যেখানে User একটি Sentence input দেবে এবং Program প্রতিটি word-এর frequency দেখাবে।

**Example:**

```python
text = input("Enter a sentence: ")

words = text.lower().split()

frequency = {}

for word in words:
    if word in frequency:
        frequency[word] += 1
    else:
        frequency[word] = 1

print("\nWord Frequency:")

for word, count in frequency.items():
    print(word, "=", count)
```

**Example Input:**

```text
I love Python and I love programming
```

**Output:**

```text
Word Frequency:
i = 2
love = 2
python = 1
and = 1
programming = 1
```

**Explanation:**

1. User-এর কাছ থেকে Sentence input নেওয়া হয়েছে।
2. `lower()` দিয়ে সব word lowercase করা হয়েছে।
3. `split()` দিয়ে Sentence-টিকে List-এ ভাগ করা হয়েছে।
4. Dictionary দিয়ে প্রতিটি word-এর frequency গণনা করা হয়েছে।
5. `items()` ব্যবহার করে প্রতিটি word এবং frequency print করা হয়েছে।

---

## 17. Common Mistakes

### Mistake 1: split() ছাড়া len() ব্যবহার করা

```python
text = "I love Python"

print(len(text))
```

**Output:**

```text
13
```

এখানে মোট word গণনা হয়নি। বরং space-সহ character গণনা হয়েছে।

**Correct Example:**

```python
text = "I love Python"

print(len(text.split()))
```

**Output:**

```text
3
```

### Mistake 2: split() এবং split(" ") একই মনে করা

```python
text = "I  love  Python"

print(text.split())
print(text.split(" "))
```

**Output:**

```text
['I', 'love', 'Python']
['I', '', 'love', '', 'Python']
```

**Explanation:**

- `split()` একাধিক whitespace একসাথে separator হিসেবে ব্যবহার করে।
- `split(" ")` নির্দিষ্ট একটি space দিয়ে ভাগ করে।
- পাশাপাশি একাধিক space থাকলে `split(" ")` empty String তৈরি করতে পারে।

তাই সাধারণ Word Counting-এর জন্য `split()` ব্যবহার করা ভালো।

### Mistake 3: Dictionary-এর Frequency বাড়ানোর পরিবর্তে আবার 1 সেট করা

```python
text = "apple apple"

frequency = {}

for word in text.split():
    if word in frequency:
        frequency[word] = 1
    else:
        frequency[word] = 1

print(frequency)
```

**Output:**

```text
{'apple': 1}
```

এটি ভুল। কারণ দ্বিতীয়বার `apple` আসার পর frequency বাড়েনি।

**Correct Code:**

```python
text = "apple apple"

frequency = {}

for word in text.split():
    if word in frequency:
        frequency[word] += 1
    else:
        frequency[word] = 1

print(frequency)
```

**Output:**

```text
{'apple': 2}
```

### Mistake 4: Case Sensitivity ভুলে যাওয়া

```python
text = "Python python"

words = text.split()

print(words.count("Python"))
print(words.count("python"))
```

**Output:**

```text
1
1
```

Python-এ `"Python"` এবং `"python"` আলাদা word।

একইভাবে গণনা করতে চাইলে `lower()` ব্যবহার করতে হবে।

---

## 18. Practice Exercises

### Exercise 1

নিচের Sentence-এ মোট কতটি word আছে তা বের করো।

```python
text = "Python is easy to learn"
```

**Solution:**

```python
text = "Python is easy to learn"

print("Total words:", len(text.split()))
```

**Output:**

```text
Total words: 5
```

### Exercise 2

নিচের Sentence-এর প্রতিটি word আলাদাভাবে print করো।

```python
text = "I love programming"
```

**Solution:**

```python
text = "I love programming"

words = text.split()

for word in words:
    print(word)
```

**Output:**

```text
I
love
programming
```

### Exercise 3

নিচের Sentence-এর প্রতিটি word-এর frequency বের করো।

```python
text = "I love Python and I love coding"
```

**Solution:**

```python
text = "I love Python and I love coding"

words = text.split()

frequency = {}

for word in words:
    if word in frequency:
        frequency[word] += 1
    else:
        frequency[word] = 1

print(frequency)
```

**Output:**

```text
{'I': 2, 'love': 2, 'Python': 1, 'and': 1, 'coding': 1}
```

### Exercise 4

একটি Sentence-এর Duplicate Words খুঁজে বের করো।

**Solution:**

```python
text = "Python is easy and Python is powerful"

words = text.split()

checked = ""

for word in words:
    if words.count(word) > 1 and word not in checked:
        print(word)
        checked += word + " "
```

**Output:**

```text
Python
is
```

### Exercise 5

একটি Sentence-এর Unique Words খুঁজে বের করো।

**Solution:**

```python
text = "Python is easy and Python is powerful"

words = text.split()

for word in words:
    if words.count(word) == 1:
        print(word)
```

**Output:**

```text
easy
and
powerful
```

### Exercise 6

একটি Sentence-এর সবচেয়ে বেশি ব্যবহৃত word খুঁজে বের করো।

**Solution:**

```python
text = "I love Python and I love programming"

words = text.split()

frequency = {}

for word in words:
    if word in frequency:
        frequency[word] += 1
    else:
        frequency[word] = 1

most_frequent = max(frequency, key=frequency.get)

print("Most frequent word:", most_frequent)
print("Frequency:", frequency[most_frequent])
```

**Output:**

```text
Most frequent word: I
Frequency: 2
```

### Exercise 7

User-এর কাছ থেকে একটি Sentence input নিয়ে মোট word এবং character সংখ্যা বের করো।

**Solution:**

```python
text = input("Enter a sentence: ")

total_words = len(text.split())
total_characters = len(text)

print("Total words:", total_words)
print("Total characters:", total_characters)
```

**Example Input:**

```text
I love Python
```

**Output:**

```text
Total words: 3
Total characters: 13
```

### Exercise 8

User-এর কাছ থেকে একটি Sentence input নিয়ে প্রতিটি word-এর frequency বের করো। Uppercase এবং Lowercase একই হিসেবে গণনা করতে হবে।

**Solution:**

```python
text = input("Enter a sentence: ")

words = text.lower().split()

frequency = {}

for word in words:
    if word in frequency:
        frequency[word] += 1
    else:
        frequency[word] = 1

for word, count in frequency.items():
    print(word, "=", count)
```

**Example Input:**

```text
Python python JAVA java
```

**Output:**

```text
python = 2
java = 2
```

---

## 19. Chapter Summary

এই topic-এ আমরা Python-এ Word Counting এবং Word Processing শিখেছি।

গুরুত্বপূর্ণ বিষয়গুলো:

1. Word Counting হলো Sentence-এর মোট word সংখ্যা গণনা করা।
2. `split()` দিয়ে String-কে List-এ ভাগ করা যায়।
3. `len(text.split())` দিয়ে মোট word সংখ্যা বের করা যায়।
4. `for` loop দিয়ে প্রতিটি word আলাদাভাবে access করা যায়।
5. Dictionary ব্যবহার করে প্রতিটি word-এর frequency গণনা করা যায়।
6. `words.count(word)` দিয়ে নির্দিষ্ট word-এর frequency বের করা যায়।
7. Duplicate Words হলো একাধিকবার আসা word।
8. Unique Words হলো মাত্র একবার আসা word।
9. `lower()` ব্যবহার করে case-insensitive word counting করা যায়।
10. `max()` দিয়ে সবচেয়ে বেশি ব্যবহৃত word খুঁজে বের করা যায়।
11. `len(text)` দিয়ে space-সহ মোট character সংখ্যা বের করা যায়।

---

## 20. Self-Assessment Checklist

নিচের বিষয়গুলো নিজে করতে পারলে এই topic ভালোভাবে শেখা হয়েছে:

- [ ] Word Counting কী বুঝি।
- [ ] `split()` method ব্যবহার করতে পারি।
- [ ] `len()` দিয়ে মোট word সংখ্যা বের করতে পারি।
- [ ] Loop দিয়ে প্রতিটি word print করতে পারি।
- [ ] Dictionary দিয়ে word frequency গণনা করতে পারি।
- [ ] `items()` ব্যবহার করে word এবং frequency print করতে পারি।
- [ ] Duplicate Words খুঁজে বের করতে পারি।
- [ ] Unique Words খুঁজে বের করতে পারি।
- [ ] Most Frequent Word খুঁজে বের করতে পারি।
- [ ] Case-Insensitive Word Counting করতে পারি।
- [ ] User input থেকে Word Processing করতে পারি।
- [ ] Word এবং Character Counting-এর পার্থক্য বুঝি।

---

## 21. Next Topic

**50. Extracting Information from Strings in Python**

পরবর্তী topic-এ আমরা শিখব:

- String থেকে নির্দিষ্ট Information বের করা।
- Email Address থেকে Username বের করা।
- Email Address থেকে Domain Name বের করা।
- String থেকে Number Extract করা।
- String থেকে নির্দিষ্ট অংশ বের করা।
- `split()` এবং String Indexing ব্যবহার করে Information Extract করা।
- Practical Text Processing Problems সমাধান করা।