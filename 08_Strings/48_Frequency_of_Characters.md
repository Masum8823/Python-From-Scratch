# 48. Frequency of Characters in Python

## 1. Introduction

Python-এ কোনো String-এর মধ্যে প্রতিটি character কতবার এসেছে, তা গণনা করাকে **Character Frequency** বলে।

ধরো, আমাদের একটি String আছে:

```python
text = "banana"
```

এখানে:

- `b` এসেছে 1 বার।
- `a` এসেছে 3 বার।
- `n` এসেছে 2 বার।

এগুলোই হলো প্রতিটি character-এর frequency।

Python-এ Loop, `count()` method এবং Dictionary ব্যবহার করে সহজেই character frequency বের করা যায়।

এই topic-এ আমরা শিখব:

- Character Frequency কী।
- `count()` method দিয়ে frequency বের করা।
- Loop ব্যবহার করে frequency গণনা করা।
- Dictionary ব্যবহার করে frequency সংরক্ষণ করা।
- Duplicate character এবং character frequency-এর পার্থক্য।
- সবচেয়ে বেশি ও সবচেয়ে কম ব্যবহৃত character খুঁজে বের করা।
- User input থেকে character frequency বের করা।

---

## 2. What is Character Frequency?

একটি String-এর মধ্যে কোনো character মোট কতবার এসেছে, সেই সংখ্যাকে Character Frequency বলে।

**Example:**

```python
text = "programming"
```

**Frequency Table:**

| Character | Frequency |
|---|---:|
| p | 1 |
| r | 2 |
| o | 1 |
| g | 2 |
| a | 1 |
| m | 2 |
| i | 1 |
| n | 1 |

এখানে `r`, `g` এবং `m`-এর frequency হলো 2।

অন্যদিকে, `p`, `o`, `a`, `i` এবং `n`-এর frequency হলো 1।

**Important:**

- Frequency 1 হলে character একবার এসেছে।
- Frequency 2 হলে character দুইবার এসেছে।
- Frequency 3 হলে character তিনবার এসেছে।

---

## 3. Finding Character Frequency Using count()

Python-এর `count()` method ব্যবহার করে কোনো character কতবার এসেছে তা জানা যায়।

**Syntax:**

```python
string.count(character)
```

**Example:**

```python
text = "banana"

print(text.count("a"))
print(text.count("b"))
print(text.count("n"))
```

**Output:**

```text
3
1
2
```

**Explanation:**

- `a` মোট 3 বার এসেছে।
- `b` মোট 1 বার এসেছে।
- `n` মোট 2 বার এসেছে।

### Another Example

```python
text = "programming"

print("Frequency of r:", text.count("r"))
print("Frequency of m:", text.count("m"))
```

**Output:**

```text
Frequency of r: 2
Frequency of m: 2
```

**Important:**

`count()` একটি নির্দিষ্ট character-এর frequency বের করে। পুরো String-এর প্রতিটি character-এর frequency বের করতে Loop ব্যবহার করা সুবিধাজনক।

---

## 4. Finding Frequency of Every Character Using a Loop

`for` loop ব্যবহার করে String-এর প্রতিটি character-এর frequency বের করা যায়।

**Example:**

```python
text = "banana"

for char in text:
    print(char, "=", text.count(char))
```

**Output:**

```text
b = 1
a = 3
n = 2
a = 3
n = 2
a = 3
```

**Explanation:**

1. `for` loop String-এর প্রতিটি character-এর ওপর কাজ করছে।
2. `count(char)` দিয়ে character-এর frequency বের করা হচ্ছে।
3. `print()` দিয়ে character এবং তার frequency দেখানো হচ্ছে।

**Problem:**

এখানে একই character একাধিকবার print হচ্ছে।

এই সমস্যা সমাধানের জন্য আমরা `checked` variable ব্যবহার করতে পারি।

---

## 5. Printing Each Character Frequency Only Once

একই character বারবার print না করে প্রতিটি character-এর frequency একবার করে দেখাতে `checked` variable ব্যবহার করা যায়।

**Example:**

```python
text = "banana"

checked = ""

for char in text:
    if char not in checked:
        print(char, "=", text.count(char))
        checked += char
```

**Output:**

```text
b = 1
a = 3
n = 2
```

**Explanation:**

1. `checked = ""` দিয়ে একটি empty String তৈরি করা হয়েছে।
2. Loop প্রতিটি character পরীক্ষা করছে।
3. `char not in checked` দিয়ে দেখা হচ্ছে character-টি আগে এসেছে কি না।
4. আগে না এসে থাকলে character এবং তার frequency print হচ্ছে।
5. `checked += char` দিয়ে character-টি checked String-এ যোগ করা হচ্ছে।

এভাবে প্রতিটি আলাদা character-এর frequency একবার করে print হয়।

---

## 6. Finding Character Frequency Using a Dictionary

Python-এর Dictionary ব্যবহার করে character frequency বের করা যায়।

Dictionary-তে data Key-Value pair আকারে সংরক্ষণ করা হয়।

এখানে:

- Key = Character
- Value = Character-এর Frequency

**Example:**

```python
text = "banana"

frequency = {}

for char in text:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

print(frequency)
```

**Output:**

```text
{'b': 1, 'a': 3, 'n': 2}
```

**Explanation:**

1. `frequency = {}` দিয়ে একটি empty Dictionary তৈরি করা হয়েছে।
2. Loop প্রতিটি character পরীক্ষা করছে।
3. Character আগে Dictionary-তে থাকলে তার frequency 1 বাড়ানো হচ্ছে।
4. Character আগে না থাকলে তার frequency 1 নির্ধারণ করা হচ্ছে।
5. শেষে Dictionary-তে প্রতিটি character-এর frequency সংরক্ষিত হচ্ছে।

**Important:**

এই পদ্ধতিতে `checked` variable ব্যবহার করতে হয় না। Dictionary নিজেই প্রতিটি আলাদা character-এর frequency সংরক্ষণ করে।

---

## 7. Displaying Dictionary Frequency Separately

Dictionary থেকে প্রতিটি character এবং তার frequency আলাদাভাবে print করা যায়।

**Example:**

```python
text = "programming"

frequency = {}

for char in text:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

for char, count in frequency.items():
    print(char, "=", count)
```

**Output:**

```text
p = 1
r = 2
o = 1
g = 2
a = 1
m = 2
i = 1
n = 1
```

**Explanation:**

- `frequency.items()` Dictionary-এর Key এবং Value একসাথে দেয়।
- `char` প্রতিটি character নির্দেশ করে।
- `count` সেই character-এর frequency নির্দেশ করে।
- `print()` দিয়ে প্রতিটি character-এর frequency দেখানো হচ্ছে।

**Important:**

`items()` ব্যবহার করে Dictionary-এর Key এবং Value একসাথে পাওয়া যায়।

---

## 8. Finding Frequency of Characters from User Input

এবার User-এর কাছ থেকে একটি String input নিয়ে প্রতিটি character-এর frequency বের করব।

**Example:**

```python
text = input("Enter a string: ")

frequency = {}

for char in text:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

for char, count in frequency.items():
    print(char, "=", count)
```

**Example Input:**

```text
programming
```

**Output:**

```text
p = 1
r = 2
o = 1
g = 2
a = 1
m = 2
i = 1
n = 1
```

**Explanation:**

User-এর দেওয়া String থেকে প্রতিটি character-এর frequency গণনা করে Dictionary-তে সংরক্ষণ করা হচ্ছে।

এরপর Loop ব্যবহার করে character এবং frequency print করা হচ্ছে।

---

## 9. Finding the Most Frequent Character

কোনো String-এর মধ্যে সবচেয়ে বেশি বার কোন character এসেছে, তা বের করা যায়।

Python-এর `max()` function এবং Dictionary ব্যবহার করে এটি করা সম্ভব।

**Example:**

```python
text = "banana"

frequency = {}

for char in text:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

most_frequent = max(frequency, key=frequency.get)

print("Most frequent character:", most_frequent)
print("Frequency:", frequency[most_frequent])
```

**Output:**

```text
Most frequent character: a
Frequency: 3
```

**Explanation:**

1. প্রথমে Dictionary-তে প্রতিটি character-এর frequency গণনা করা হয়েছে।
2. `max()` function সবচেয়ে বেশি frequency-যুক্ত character খুঁজে বের করছে।
3. `key=frequency.get` দিয়ে Dictionary-এর Value অনুযায়ী comparison করা হচ্ছে।
4. শেষে character এবং তার frequency print হচ্ছে।

**Important:**

যদি একাধিক character-এর সর্বোচ্চ frequency সমান হয়, তাহলে `max()` প্রথম পাওয়া character-টি return করে।

---

## 10. Finding the Least Frequent Character

কোনো String-এর মধ্যে সবচেয়ে কম frequency-যুক্ত character বের করতে `min()` function ব্যবহার করা যায়।

**Example:**

```python
text = "banana"

frequency = {}

for char in text:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

least_frequent = min(frequency, key=frequency.get)

print("Least frequent character:", least_frequent)
print("Frequency:", frequency[least_frequent])
```

**Output:**

```text
Least frequent character: b
Frequency: 1
```

**Explanation:**

- `min()` Dictionary-এর সবচেয়ে ছোট Value খুঁজে বের করে।
- `key=frequency.get` frequency অনুযায়ী comparison করে।
- এরপর character এবং তার frequency print হয়।

**Important:**

একাধিক character-এর frequency সমানভাবে সর্বনিম্ন হলে প্রথম পাওয়া character-টি return হয়।

---

## 11. Case-Insensitive Character Frequency

Python-এ Uppercase এবং Lowercase character আলাদা হিসেবে গণনা করা হয়।

যেমন:

```python
text = "aAaB"

frequency = {}

for char in text:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

print(frequency)
```

**Output:**

```text
{'a': 1, 'A': 2, 'B': 1}
```

এখানে `a` এবং `A` আলাদা Key হিসেবে সংরক্ষিত হয়েছে।

কিন্তু আমরা যদি Uppercase এবং Lowercase-কে একই character হিসেবে গণনা করতে চাই, তাহলে `lower()` ব্যবহার করতে পারি।

**Example:**

```python
text = "aAaB"

text = text.lower()

frequency = {}

for char in text:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

print(frequency)
```

**Output:**

```text
{'a': 3, 'b': 1}
```

**Explanation:**

`lower()` পুরো String-কে lowercase করেছে। তাই `a` এবং `A` একই character হিসেবে গণনা হয়েছে।

---

## 12. Ignoring Spaces While Counting Frequency

অনেক সময় String-এর মধ্যে থাকা space গণনা করতে চাই না।

সেক্ষেত্রে `if char != " "` condition ব্যবহার করা যায়।

**Example:**

```python
text = "I love Python"

frequency = {}

for char in text:
    if char != " ":
        if char in frequency:
            frequency[char] += 1
        else:
            frequency[char] = 1

print(frequency)
```

**Output:**

```text
{'I': 1, 'l': 1, 'o': 2, 'v': 1, 'e': 1, 'P': 1, 'y': 1, 't': 1, 'h': 1, 'n': 1}
```

**Explanation:**

- `char != " "` দিয়ে space বাদ দেওয়া হচ্ছে।
- শুধু non-space character-এর frequency গণনা হচ্ছে।
- Dictionary-তে character এবং frequency সংরক্ষিত হচ্ছে।

**Important:**

এখানে শুধু সাধারণ space বাদ দেওয়া হয়েছে। Tab এবং newline বাদ দিতে চাইলে আলাদা condition ব্যবহার করতে হবে।

---

## 13. Difference Between Duplicate Characters and Character Frequency

Duplicate Characters এবং Character Frequency একে অপরের সঙ্গে সম্পর্কিত হলেও এদের কাজ আলাদা।

| Duplicate Characters | Character Frequency |
|---|---|
| কোন character একাধিকবার এসেছে তা খুঁজে বের করে | প্রতিটি character কতবার এসেছে তা গণনা করে |
| শুধু duplicate character দেখাতে পারে | সব character-এর frequency দেখাতে পারে |
| `count() > 1` ব্যবহার করা যায় | `count()` বা Dictionary ব্যবহার করা যায় |

**Example:**

```python
text = "banana"
```

**Duplicate Characters:**

```text
a
n
```

**Character Frequency:**

```text
b = 1
a = 3
n = 2
```

সহজভাবে মনে রাখবে:

- Duplicate Characters = কোন character একাধিকবার এসেছে?
- Character Frequency = প্রতিটি character কতবার এসেছে?

---

## 14. Common Mistakes

### Mistake 1: Dictionary-এর Key এবং Value গুলিয়ে ফেলা

```python
frequency = {}

frequency["a"] = 3

print(frequency["a"])
```

**Output:**

```text
3
```

এখানে `"a"` হলো Key এবং `3` হলো Value।

### Mistake 2: Frequency বাড়ানোর সময় ভুল করা

```python
text = "banana"

frequency = {}

for char in text:
    if char in frequency:
        frequency[char] = 1
    else:
        frequency[char] = 1

print(frequency)
```

**Output:**

```text
{'b': 1, 'a': 1, 'n': 1}
```

এটি ভুল। কারণ character আগে থাকলে frequency বাড়ানোর পরিবর্তে আবার 1 সেট করা হচ্ছে।

**Correct Code:**

```python
text = "banana"

frequency = {}

for char in text:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

print(frequency)
```

**Output:**

```text
{'b': 1, 'a': 3, 'n': 2}
```

### Mistake 3: Dictionary-এর items() ব্যবহার না বোঝা

```python
frequency = {"a": 3, "b": 2}

for char, count in frequency.items():
    print(char, count)
```

**Output:**

```text
a 3
b 2
```

`items()` Key এবং Value একসাথে return করে।

### Mistake 4: Uppercase এবং Lowercase একই মনে করা

```python
text = "Aa"

print(text.count("a"))
print(text.count("A"))
```

**Output:**

```text
1
1
```

Python-এ `"a"` এবং `"A"` আলাদা character।

---

## 15. Practice Exercises

### Exercise 1

নিচের String-এর প্রতিটি character-এর frequency বের করো।

```python
text = "apple"
```

**Solution:**

```text
a = 1
p = 2
l = 1
e = 1
```

### Exercise 2

নিচের code-এর output কী হবে?

```python
text = "hello"

print(text.count("l"))
print(text.count("h"))
print(text.count("o"))
```

**Solution:**

```text
2
1
1
```

### Exercise 3

একটি String-এর প্রতিটি character-এর frequency Dictionary-তে সংরক্ষণ করো।

**Solution:**

```python
text = "banana"

frequency = {}

for char in text:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

print(frequency)
```

**Output:**

```text
{'b': 1, 'a': 3, 'n': 2}
```

### Exercise 4

একটি String-এর সবচেয়ে বেশি ব্যবহৃত character খুঁজে বের করো।

**Solution:**

```python
text = "programming"

frequency = {}

for char in text:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

most_frequent = max(frequency, key=frequency.get)

print(most_frequent)
```

**Output:**

```text
r
```

### Exercise 5

একটি String-এর সবচেয়ে কম ব্যবহৃত character খুঁজে বের করো।

**Solution:**

```python
text = "banana"

frequency = {}

for char in text:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

least_frequent = min(frequency, key=frequency.get)

print(least_frequent)
```

**Output:**

```text
b
```

### Exercise 6

User-এর কাছ থেকে একটি String input নিয়ে প্রতিটি character-এর frequency print করো।

**Solution:**

```python
text = input("Enter a string: ")

frequency = {}

for char in text:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

for char, count in frequency.items():
    print(char, "=", count)
```

**Example Input:**

```text
programming
```

**Output:**

```text
p = 1
r = 2
o = 1
g = 2
a = 1
m = 2
i = 1
n = 1
```

### Exercise 7

একটি String-এর character frequency গণনা করো। তবে space বাদ দিতে হবে এবং Uppercase ও Lowercase একই হিসেবে গণনা করতে হবে।

**Solution:**

```python
text = input("Enter a string: ")

text = text.lower()

frequency = {}

for char in text:
    if char != " ":
        if char in frequency:
            frequency[char] += 1
        else:
            frequency[char] = 1

print(frequency)
```

**Example Input:**

```text
Hello World
```

**Output:**

```text
{'h': 1, 'e': 1, 'l': 3, 'o': 2, 'w': 1, 'r': 1, 'd': 1}
```

---

## 16. Chapter Summary

এই topic-এ আমরা Python-এ Character Frequency গণনা করা শিখেছি।

গুরুত্বপূর্ণ বিষয়গুলো:

1. Character Frequency হলো একটি character কতবার এসেছে তার সংখ্যা।
2. `count()` method দিয়ে নির্দিষ্ট character-এর frequency বের করা যায়।
3. `for` loop দিয়ে প্রতিটি character পরীক্ষা করা যায়।
4. `checked` variable ব্যবহার করে প্রতিটি character একবার print করা যায়।
5. Dictionary ব্যবহার করে character এবং frequency সংরক্ষণ করা যায়।
6. `frequency[char] += 1` দিয়ে frequency বাড়ানো যায়।
7. `items()` দিয়ে Dictionary-এর Key এবং Value একসাথে পাওয়া যায়।
8. `max()` দিয়ে সবচেয়ে বেশি frequency-যুক্ত character বের করা যায়।
9. `min()` দিয়ে সবচেয়ে কম frequency-যুক্ত character বের করা যায়।
10. `lower()` ব্যবহার করে case-insensitive frequency গণনা করা যায়।
11. Condition ব্যবহার করে space বাদ দেওয়া যায়।

---

## 17. Self-Assessment Checklist

নিচের বিষয়গুলো নিজে করতে পারলে এই topic ভালোভাবে শেখা হয়েছে:

- [ ] Character Frequency কী বুঝি।
- [ ] `count()` method দিয়ে frequency বের করতে পারি।
- [ ] Loop ব্যবহার করে প্রতিটি character-এর frequency বের করতে পারি।
- [ ] `checked` variable-এর কাজ বুঝি।
- [ ] Dictionary ব্যবহার করে frequency গণনা করতে পারি।
- [ ] Dictionary-এর Key এবং Value বুঝি।
- [ ] `items()` method ব্যবহার করতে পারি।
- [ ] Most Frequent Character খুঁজে বের করতে পারি।
- [ ] Least Frequent Character খুঁজে বের করতে পারি।
- [ ] Uppercase ও Lowercase একসাথে গণনা করতে পারি।
- [ ] Space বাদ দিয়ে frequency গণনা করতে পারি।
- [ ] User input থেকে character frequency বের করতে পারি।

---

## 18. Next Topic

**49. Word Counting and Word Processing in Python**

পরবর্তী topic-এ আমরা শিখব:

- Word Counting কী।
- String-এর মধ্যে মোট কতটি word আছে তা গণনা করা।
- `split()` ব্যবহার করে word আলাদা করা।
- প্রতিটি word-এর frequency গণনা করা।
- সবচেয়ে বেশি ব্যবহৃত word খুঁজে বের করা।
- Duplicate words খুঁজে বের করা।
- User input থেকে word processing করা।
- বাস্তব উদাহরণের মাধ্যমে word counting করা।