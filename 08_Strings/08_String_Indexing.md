
# 08. String Indexing in Python

## 1. Introduction to String Indexing

Python-এ String-এর প্রতিটি character-এর একটি নির্দিষ্ট position বা index থাকে। এই index ব্যবহার করে String থেকে নির্দিষ্ট character access করা যায়।

এই পদ্ধতিকে **String Indexing** বলা হয়।

Python-এ String Indexing শুরু হয় `0` থেকে, `1` থেকে নয়।

উদাহরণ:

```python
text = "PYTHON"
```

এখানে প্রতিটি character-এর index:

| Character | P | Y | T | H | O | N |
|---|---|---|---|---|---|---|
| Index | 0 | 1 | 2 | 3 | 4 | 5 |

অর্থাৎ:
- `P`-এর index হলো `0`।
- `Y`-এর index হলো `1`।
- `T`-এর index হলো `2`।
- `H`-এর index হলো `3`।
- `O`-এর index হলো `4`।
- `N`-এর index হলো `5`।

## 2. Syntax of String Indexing

String থেকে নির্দিষ্ট character access করার Syntax:

```python
string[index]
```

এখানে:
- `string` হলো যে String থেকে character নিতে চাই।
- `index` হলো character-এর position।

## 3. Accessing Characters Using Index

```python
text = "PYTHON"

print(text[0])
print(text[1])
print(text[2])
print(text[3])
```

**Output:**

```text
P
Y
T
H
```

**ব্যাখ্যা:**

- `text[0]` প্রথম character return করে।
- `text[1]` দ্বিতীয় character return করে।
- `text[2]` তৃতীয় character return করে।
- `text[3]` চতুর্থ character return করে।

## 4. Accessing the First and Last Character

String Indexing ব্যবহার করে সহজেই প্রথম ও শেষ character access করা যায়।

```python
name = "Masum"

print("First character:", name[0])
print("Last character:", name[4])
```

**Output:**

```text
First character: M
Last character: m
```

এখানে `Masum` String-এর প্রথম character-এর index `0` এবং শেষ character-এর index `4`।

তবে String-এর length পরিবর্তিত হলে শেষ index-ও পরিবর্তিত হবে।

## 5. Using len() with String Indexing

`len()` function ব্যবহার করে String-এর length বের করা যায়। Length থেকে `1` বাদ দিলে শেষ character-এর index পাওয়া যায়।

**Formula:**

```python
len(string) - 1
```

উদাহরণ:

```python
name = "Python"

last_index = len(name) - 1

print(name[last_index])
```

**Output:**

```text
n
```

এখানে:
- String-এর length = 6
- Last index = 6 - 1 = 5
- `name[5]` = `n`

## 6. String Indexing with User Input

User-এর কাছ থেকে একটি Word নিয়ে তার প্রথম character access করা যায়।

```python
word = input("Enter a word: ")

print("First character:", word[0])
```

**Sample Input:**

```text
Python
```

**Output:**

```text
Enter a word: Python
First character: P
```

**Important:** User যদি Empty String দেয়, তাহলে `word[0]` ব্যবহার করলে `IndexError` হবে। তাই প্রয়োজন অনুযায়ী আগে String খালি কি না যাচাই করতে হবে।

```python
word = input("Enter a word: ")

if len(word) > 0:
    print("First character:", word[0])
else:
    print("The string is empty.")
```

## 7. IndexError in String Indexing

String-এর মধ্যে যতগুলো character আছে, তার বাইরে কোনো positive index access করতে গেলে `IndexError` হয়।

উদাহরণ:

```python
text = "PYTHON"

print(text[6])
```

**Output:**

```text
IndexError: string index out of range
```

**কেন Error হয়েছে?**

`PYTHON` String-এর index হলো `0` থেকে `5` পর্যন্ত। এখানে `text[6]` দিয়ে এমন একটি position access করার চেষ্টা করা হয়েছে, যা String-এর মধ্যে নেই।

সঠিক:

```python
text = "PYTHON"

print(text[5])
```

**Output:**

```text
N
```

## 8. Important Rules of String Indexing

1. Python String Indexing শুরু হয় `0` থেকে।
2. প্রতিটি character-এর একটি নির্দিষ্ট index থাকে।
3. `string[index]` ব্যবহার করে character access করা যায়।
4. `len(string) - 1` দিয়ে শেষ character-এর index পাওয়া যায়।
5. Invalid index ব্যবহার করলে `IndexError` হয়।
6. String-এর Indexing case-sensitive। অর্থাৎ `A` এবং `a` আলাদা character।

## 9. Common Mistakes

### Mistake 1: Indexing 1 থেকে শুরু মনে করা

```python
text = "Python"

print(text[1])
```

Output:

```text
y
```

এখানে `P` নয়, `y` পাওয়া যাবে। কারণ প্রথম character-এর index `0`।

### Mistake 2: Last Index ভুল নির্ধারণ করা

```python
text = "Hello"

print(text[5])
```

এখানে `IndexError` হবে। কারণ শেষ index হলো `4`।

সঠিক:

```python
print(text[4])
```

### Mistake 3: Empty String Access করা

```python
text = ""

print(text[0])
```

এখানে `IndexError` হবে। কারণ Empty String-এ কোনো character নেই।

## 10. Practice Exercises

### Exercise 1: Character Access

`"PROGRAMMING"` String থেকে নিচের character-গুলো বের করো:

- First character
- Third character
- Fifth character
- Last character

### Exercise 2: User Input

User-এর কাছ থেকে একটি নাম নিয়ে তার প্রথম character এবং শেষ character দেখাও।

### Exercise 3: Index Prediction

নিচের Code-এর Output নিজে Predict করো:

```python
text = "COMPUTER"

print(text[0])
print(text[3])
print(text[5])
print(text[7])
```

### Exercise 4: First Character Validation

একটি String input নাও। String খালি না হলে প্রথম character দেখাও। অন্যথায় Empty String message দেখাও।

## 11. Practice Solutions

### Solution 1

```python
text = "PROGRAMMING"

print(text[0])
print(text[2])
print(text[4])
print(text[len(text) - 1])
```

**Output:**

```text
P
O
R
G
```

### Solution 2

```python
name = input("Enter your name: ")

if len(name) > 0:
    print("First character:", name[0])
    print("Last character:", name[len(name) - 1])
else:
    print("The string is empty.")
```

### Solution 3

**Output:**

```text
C
P
T
R
```

### Solution 4

```python
text = input("Enter a string: ")

if len(text) > 0:
    print("First character:", text[0])
else:
    print("Empty string!")
```

## 12. Chapter Summary

- String-এর প্রতিটি character-এর একটি index থাকে।
- Python-এ Indexing `0` থেকে শুরু হয়।
- `string[index]` দিয়ে নির্দিষ্ট character access করা যায়।
- `len(string) - 1` দিয়ে শেষ index পাওয়া যায়।
- Invalid index ব্যবহার করলে `IndexError` হয়।
- Empty String থেকে কোনো character access করা যায় না।

## 13. Self-Assessment Checklist

- [ ] String Indexing কী বুঝতে পারি।
- [ ] Index `0` থেকে শুরু হয় জানি।
- [ ] নির্দিষ্ট index দিয়ে character access করতে পারি।
- [ ] First ও Last character বের করতে পারি।
- [ ] `len()` ব্যবহার করে Last Index বের করতে পারি।
- [ ] `IndexError` কেন হয় বুঝতে পারি।

## 14. Next Topic

`09_Negative_String_Indexing.md`

পরবর্তী topic-এ Negative Indexing শিখব, যার মাধ্যমে String-এর শেষ দিক থেকে character access করা যায়।
