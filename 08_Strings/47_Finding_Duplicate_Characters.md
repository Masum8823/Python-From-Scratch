# 47. Finding Duplicate Characters in Python

## 1. Introduction

Python-এ String-এর মধ্যে কোনো character একাধিকবার আছে কি না, তা খুঁজে বের করাকে **Finding Duplicate Characters** বলে।

ধরো, আমাদের একটি String আছে:

```python
text = "programming"
```

এখানে:

- `r` দুইবার এসেছে।
- `g` দুইবার এসেছে।
- `m` দুইবার এসেছে।

তাই এই String-এর duplicate characters হলো `r`, `g` এবং `m`।

Python-এ Loop এবং Conditional Statement ব্যবহার করে সহজেই duplicate character খুঁজে বের করা যায়।

এই topic-এ আমরা শিখব:

- Duplicate character কী।
- String-এর মধ্যে duplicate character খুঁজে বের করা।
- `count()` method ব্যবহার করে duplicate খোঁজা।
- Nested loop ব্যবহার করে duplicate খোঁজা।
- একই character বারবার print হওয়া বন্ধ করা।
- Duplicate character-এর সংখ্যা নির্ণয় করা।
- User input থেকে duplicate character খুঁজে বের করা।

---

## 2. What is a Duplicate Character?

কোনো String-এর মধ্যে একই character একাধিকবার থাকলে তাকে Duplicate Character বলে।

**Example:**

```python
text = "banana"
```

এখানে:

| Character | Occurrences |
|---|---:|
| b | 1 |
| a | 3 |
| n | 2 |

সুতরাং, duplicate characters হলো:

```text
a
n
```

**Important:**

- একটি character একবার থাকলে সেটি duplicate নয়।
- একটি character দুইবার বা তার বেশি থাকলে সেটি duplicate।
- Duplicate character খুঁজে বের করার সময় uppercase এবং lowercase আলাদা character হিসেবে বিবেচিত হয়।

---

## 3. Finding Duplicate Characters Using count()

Python-এর `count()` method ব্যবহার করে কোনো character String-এর মধ্যে কতবার এসেছে তা জানা যায়।

**Syntax:**

```python
string.count(character)
```

এটি নির্দিষ্ট character-এর মোট occurrence সংখ্যা return করে।

**Example:**

```python
text = "programming"

print(text.count("r"))
print(text.count("m"))
print(text.count("a"))
```

**Output:**

```text
2
2
1
```

**Explanation:**

- `r` দুইবার এসেছে।
- `m` দুইবার এসেছে।
- `a` একবার এসেছে।

যদি `count()` এর result `1`-এর বেশি হয়, তাহলে character-টি duplicate।

### Another Example

```python
text = "banana"

for char in text:
    if text.count(char) > 1:
        print(char)
```

**Output:**

```text
a
n
a
n
a
```

**Explanation:**

এখানে:

1. `for` loop String-এর প্রতিটি character-এর ওপর কাজ করছে।
2. `count(char)` দিয়ে character-টি কতবার এসেছে তা পরীক্ষা করা হচ্ছে।
3. `count(char) > 1` হলে character-টি print হচ্ছে।

**Important:**

এখানে একই duplicate character একাধিকবার print হচ্ছে। কারণ Loop প্রতিবার character-টি পেলে আবার সেটি পরীক্ষা করছে।

পরবর্তী example-এ আমরা এই সমস্যার সমাধান করব।

---

## 4. Printing Each Duplicate Character Only Once

একই duplicate character বারবার print না করে প্রতিটি duplicate character একবার করে print করতে চাইলে আমরা একটি `checked` variable ব্যবহার করতে পারি।

**Example:**

```python
text = "programming"

checked = ""

for char in text:
    if text.count(char) > 1 and char not in checked:
        print(char)
        checked += char
```

**Output:**

```text
r
g
m
```

**Explanation:**

1. `checked = ""` দিয়ে একটি empty String তৈরি করা হয়েছে।
2. `for` loop প্রতিটি character পরীক্ষা করছে।
3. `count(char) > 1` দিয়ে duplicate character খুঁজে বের করা হচ্ছে।
4. `char not in checked` দিয়ে দেখা হচ্ছে character-টি আগে print হয়েছে কি না।
5. Character আগে print না হয়ে থাকলে সেটি print হচ্ছে।
6. `checked += char` দিয়ে character-টি checked String-এ যোগ হচ্ছে।

এভাবে প্রতিটি duplicate character মাত্র একবার print হয়।

**Important:**

`checked` String-এর কাজ হলো আগে কোন কোন character পরীক্ষা করে print করা হয়েছে তা মনে রাখা।

---

## 5. Finding Duplicate Characters Using Nested Loops

`count()` method ছাড়াও Nested Loop ব্যবহার করে duplicate character খুঁজে বের করা যায়।

Nested Loop হলো একটি Loop-এর ভিতরে আরেকটি Loop।

**Example:**

```python
text = "banana"

for i in range(len(text)):
    for j in range(i + 1, len(text)):
        if text[i] == text[j]:
            print(text[i])
            break
```

**Output:**

```text
a
n
```

**Explanation:**

1. Outer Loop একটি character নির্বাচন করে।
2. Inner Loop তার পরের character-গুলোর সঙ্গে তুলনা করে।
3. `text[i] == text[j]` দিয়ে দুটি character সমান কি না পরীক্ষা করা হয়।
4. Character সমান হলে সেটি duplicate হিসেবে print হয়।
5. `break` ব্যবহার করে Inner Loop বন্ধ করা হয়।

**Important:**

এখানে `j = i + 1` ব্যবহার করা হয়েছে। ফলে একটি character-এর আগের character-গুলোর সঙ্গে আবার তুলনা করতে হয় না।

আর `break` ব্যবহার করার কারণে প্রতিটি duplicate character একবারই print হয়।

---

## 6. Finding Duplicate Characters Using User Input

এবার User-এর কাছ থেকে একটি String input নিয়ে তার duplicate character খুঁজে বের করব।

**Example:**

```python
text = input("Enter a string: ")

checked = ""

for char in text:
    if text.count(char) > 1 and char not in checked:
        print(char)
        checked += char
```

**Example Input:**

```text
programming
```

**Output:**

```text
r
g
m
```

**Explanation:**

User একটি String input দেবে। এরপর Loop প্রতিটি character পরীক্ষা করে duplicate character খুঁজে বের করবে।

`checked` ব্যবহার করার কারণে একই character একাধিকবার print হবে না।

---

## 7. Counting Duplicate Characters

শুধু duplicate character খুঁজে বের করা নয়, মোট কতটি different duplicate character আছে সেটিও গণনা করা যায়।

**Example:**

```python
text = "programming"

checked = ""
total = 0

for char in text:
    if text.count(char) > 1 and char not in checked:
        print(char)
        checked += char
        total += 1

print("Total duplicate characters:", total)
```

**Output:**

```text
r
g
m
Total duplicate characters: 3
```

**Explanation:**

- `checked` duplicate character আগে print হয়েছে কি না তা মনে রাখে।
- `total = 0` দিয়ে counting শুরু হয়েছে।
- প্রতিটি নতুন duplicate character পাওয়া গেলে `total += 1` হচ্ছে।
- শেষে মোট different duplicate character print হচ্ছে।

**Important:**

এখানে `total` শুধু different duplicate character গণনা করে।

অর্থাৎ, কোনো character তিনবার থাকলেও সেটিকে একটি duplicate character হিসেবেই গণনা করা হবে।

---

## 8. Finding Duplicate Characters with Their Frequency

কোনো duplicate character কতবার এসেছে সেটিও `count()` method ব্যবহার করে বের করা যায়।

**Example:**

```python
text = "programming"

checked = ""

for char in text:
    if text.count(char) > 1 and char not in checked:
        print(char, "=", text.count(char))
        checked += char
```

**Output:**

```text
r = 2
g = 2
m = 2
```

**Explanation:**

- `count(char)` character-এর মোট occurrence সংখ্যা বের করে।
- `checked` একই character বারবার print হওয়া বন্ধ করে।
- প্রতিটি duplicate character-এর frequency print হয়।

---

## 9. Case-Sensitive Duplicate Characters

Python-এ Uppercase এবং Lowercase character আলাদা হিসেবে বিবেচিত হয়।

যেমন:

```python
text = "aAabB"

checked = ""

for char in text:
    if text.count(char) > 1 and char not in checked:
        print(char)
        checked += char
```

**Output:**

```text
a
```

**Explanation:**

- `a` মোট দুইবার এসেছে।
- `A` একবার এসেছে।
- `b` একবার এসেছে।
- `B` একবার এসেছে।

তাই শুধু `a` duplicate character।

**Important:**

Python String comparison case-sensitive।

তাই `"a"` এবং `"A"` একই character নয়।

---

## 10. Common Mistakes

### Mistake 1: count() > 0 ব্যবহার করা

```python
text = "banana"

for char in text:
    if text.count(char) > 0:
        print(char)
```

**Output:**

```text
b
a
n
a
n
a
```

এটি ভুলভাবে duplicate খুঁজে বের করছে।

কারণ প্রতিটি character অন্তত একবার হলেও String-এর মধ্যে রয়েছে।

**Correct Condition:**

```python
text.count(char) > 1
```

### Mistake 2: checked ব্যবহার না করা

```python
text = "banana"

for char in text:
    if text.count(char) > 1:
        print(char)
```

**Output:**

```text
a
n
a
n
a
```

এখানে একই character একাধিকবার print হচ্ছে।

**Correct Example:**

```python
text = "banana"

checked = ""

for char in text:
    if text.count(char) > 1 and char not in checked:
        print(char)
        checked += char
```

**Output:**

```text
a
n
```

### Mistake 3: Uppercase এবং Lowercase একই মনে করা

```python
text = "aAb"

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

## 11. Practice Exercises

### Exercise 1

নিচের String-এ duplicate character কোনগুলো?

```python
text = "banana"
```

**Solution:**

```text
a
n
```

### Exercise 2

নিচের code-এর output কী হবে?

```python
text = "hello"

print(text.count("l"))
print(text.count("o"))
```

**Solution:**

```text
2
1
```

### Exercise 3

একটি String-এর duplicate character খুঁজে বের করো এবং প্রতিটি character একবার করে print করো।

**Solution:**

```python
text = "programming"

checked = ""

for char in text:
    if text.count(char) > 1 and char not in checked:
        print(char)
        checked += char
```

**Output:**

```text
r
g
m
```

### Exercise 4

একটি String-এ মোট কতটি different duplicate character আছে তা গণনা করো।

**Solution:**

```python
text = "mississippi"

checked = ""
total = 0

for char in text:
    if text.count(char) > 1 and char not in checked:
        checked += char
        total += 1

print("Total:", total)
```

**Output:**

```text
Total: 3
```

### Exercise 5

User-এর কাছ থেকে একটি String input নিয়ে duplicate character এবং তাদের frequency print করো।

**Solution:**

```python
text = input("Enter a string: ")

checked = ""

for char in text:
    if text.count(char) > 1 and char not in checked:
        print(char, "=", text.count(char))
        checked += char
```

**Example Input:**

```text
programming
```

**Output:**

```text
r = 2
g = 2
m = 2
```

### Exercise 6

নিচের code-এর output কী হবে?

```python
text = "aabbcc"

checked = ""

for char in text:
    if text.count(char) > 1 and char not in checked:
        print(char)
        checked += char
```

**Solution:**

```text
a
b
c
```

**Explanation:**

প্রতিটি character দুইবার এসেছে। কিন্তু `checked` ব্যবহার করার কারণে প্রতিটি character একবার করে print হয়েছে।

---

## 12. Chapter Summary

এই topic-এ আমরা Python-এ Duplicate Characters খুঁজে বের করা শিখেছি।

গুরুত্বপূর্ণ বিষয়গুলো:

1. একই character একাধিকবার থাকলে তাকে Duplicate Character বলে।
2. `count()` method দিয়ে কোনো character কতবার এসেছে তা জানা যায়।
3. `count(char) > 1` দিয়ে duplicate character শনাক্ত করা যায়।
4. `checked` variable ব্যবহার করে একই character বারবার print হওয়া বন্ধ করা যায়।
5. Nested Loop ব্যবহার করেও duplicate character খুঁজে বের করা যায়।
6. `break` ব্যবহার করে Inner Loop বন্ধ করা যায়।
7. `total += 1` ব্যবহার করে different duplicate character গণনা করা যায়।
8. `count()` দিয়ে duplicate character-এর frequency বের করা যায়।
9. Python-এ Uppercase এবং Lowercase character আলাদা।

---

## 13. Self-Assessment Checklist

নিচের বিষয়গুলো নিজে করতে পারলে এই topic ভালোভাবে শেখা হয়েছে:

- [ ] Duplicate Character কী বুঝি।
- [ ] `count()` method ব্যবহার করতে পারি।
- [ ] String থেকে duplicate character খুঁজে বের করতে পারি।
- [ ] প্রতিটি duplicate character একবার করে print করতে পারি।
- [ ] `checked` variable-এর কাজ বুঝি।
- [ ] Nested Loop ব্যবহার করে duplicate খুঁজতে পারি।
- [ ] Duplicate character-এর frequency বের করতে পারি।
- [ ] Different duplicate character-এর সংখ্যা গণনা করতে পারি।
- [ ] User input থেকে duplicate character খুঁজে বের করতে পারি।
- [ ] Case-sensitive comparison বুঝি।

---

## 14. Next Topic

**48. Frequency of Characters in Python**

পরবর্তী topic-এ আমরা শিখব:

- Character Frequency কী।
- String-এর প্রতিটি character কতবার এসেছে তা গণনা করা।
- `count()` ব্যবহার করে frequency বের করা।
- Loop ব্যবহার করে character frequency গণনা করা।
- প্রতিটি character-এর frequency print করা।
- User input থেকে character frequency বের করা।
- বাস্তব উদাহরণের মাধ্যমে frequency analysis করা।