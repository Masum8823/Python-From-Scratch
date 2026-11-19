
# 09. Negative String Indexing in Python

## 1. Introduction to Negative Indexing

Python-এ String-এর character শুধু শুরু থেকে নয়, শেষ দিক থেকেও access করা যায়।

String-এর শেষ দিক থেকে character access করার পদ্ধতিকে **Negative Indexing** বলা হয়।

Positive Indexing `0` থেকে শুরু হয়, আর Negative Indexing `-1` থেকে শুরু হয়।

উদাহরণ:

```python
text = "PYTHON"
```

এখানে Positive এবং Negative Index:

| Character | P | Y | T | H | O | N |
|---|---|---|---|---|---|---|
| Positive Index | 0 | 1 | 2 | 3 | 4 | 5 |
| Negative Index | -6 | -5 | -4 | -3 | -2 | -1 |

**মনে রাখবে:**

- `-1` = Last character
- `-2` = Second last character
- `-3` = Third last character

## 2. Syntax of Negative Indexing

```python
string[negative_index]
```

এখানে Negative Index ব্যবহার করে String-এর শেষ দিক থেকে নির্দিষ্ট character access করা হয়।

## 3. Accessing Characters Using Negative Index

```python
text = "PYTHON"

print(text[-1])
print(text[-2])
print(text[-3])
```

**Output:**

```text
N
O
H
```

**ব্যাখ্যা:**

- `text[-1]` শেষ character `N` return করে।
- `text[-2]` দ্বিতীয় শেষ character `O` return করে।
- `text[-3]` তৃতীয় শেষ character `H` return করে।

## 4. Accessing First and Last Characters

Negative Indexing ব্যবহার করে সহজেই শেষ character বের করা যায়।

```python
name = "Masum"

print("First character:", name[0])
print("Last character:", name[-1])
```

**Output:**

```text
First character: M
Last character: m
```

এখানে:
- `name[0]` প্রথম character।
- `name[-1]` শেষ character।

## 5. Positive vs Negative Indexing

একই character Positive এবং Negative Index—দুইভাবেই access করা যায়।

```python
text = "PYTHON"

print(text[0])
print(text[-6])

print(text[5])
print(text[-1])
```

**Output:**

```text
P
P
N
N
```

এখানে:

- `text[0]` এবং `text[-6]` একই character return করে।
- `text[5]` এবং `text[-1]` একই character return করে।

## 6. Negative Indexing with User Input

User-এর কাছ থেকে একটি Word নিয়ে তার শেষ character বের করা যায়।

```python
word = input("Enter a word: ")

if len(word) > 0:
    print("Last character:", word[-1])
else:
    print("The string is empty.")
```

**Sample Input:**

```text
Python
```

**Output:**

```text
Enter a word: Python
Last character: n
```

## 7. IndexError in Negative Indexing

String-এর বাইরে কোনো Negative Index ব্যবহার করলে `IndexError` হয়।

উদাহরণ:

```python
text = "PYTHON"

print(text[-7])
```

**Output:**

```text
IndexError: string index out of range
```

**কেন Error হয়েছে?**

`PYTHON` String-এর Negative Index হলো `-1` থেকে `-6` পর্যন্ত। এখানে `-7` ব্যবহার করা হয়েছে, যা String-এর বাইরে।

সঠিক:

```python
text = "PYTHON"

print(text[-6])
```

**Output:**

```text
P
```

## 8. Negative Indexing with Empty Strings

Empty String-এ কোনো character নেই। তাই Negative Index ব্যবহার করলেও `IndexError` হবে।

```python
text = ""

print(text[-1])
```

**Output:**

```text
IndexError: string index out of range
```

তাই Negative Indexing করার আগে String খালি কি না যাচাই করা ভালো।

## 9. Important Rules

1. Negative Indexing শেষ দিক থেকে শুরু হয়।
2. শেষ character-এর Negative Index হলো `-1`।
3. দ্বিতীয় শেষ character-এর Negative Index হলো `-2`।
4. Negative Indexing-এ `0` ব্যবহার করা যায়, তবে এটি প্রথম character নির্দেশ করে।
5. Invalid Negative Index ব্যবহার করলে `IndexError` হয়।
6. Positive এবং Negative Indexing দিয়ে একই character access করা যায়।

## 10. Common Mistakes

### Mistake 1: Last Index হিসেবে `-0` ব্যবহার করা

```python
text = "Python"

print(text[-0])
```

**Output:**

```text
P
```

`-0` এবং `0` একই। তাই এটি প্রথম character return করে, শেষ character নয়।

শেষ character পেতে `-1` ব্যবহার করতে হবে।

### Mistake 2: Negative Index-এর Range ভুল বোঝা

```python
text = "Hello"

print(text[-6])
```

এখানে `IndexError` হবে।

কারণ `Hello`-এর Negative Index হলো `-1` থেকে `-5`।

### Mistake 3: Empty String Access করা

```python
text = ""

print(text[-1])
```

এখানেও `IndexError` হবে। কারণ String-এ কোনো character নেই।

## 11. Practice Exercises

### Exercise 1: Character Access

`"PROGRAMMING"` String থেকে নিচের character-গুলো বের করো:

- Last character
- Second last character
- Third last character

### Exercise 2: Positive vs Negative

নিচের Code-এর Output Predict করো:

```python
text = "COMPUTER"

print(text[0])
print(text[-8])
print(text[7])
print(text[-1])
```

### Exercise 3: User Input

User-এর কাছ থেকে একটি Word নিয়ে তার প্রথম এবং শেষ character দেখাও।

### Exercise 4: Last Character Validation

একটি String input নাও। String খালি না হলে তার শেষ character দেখাও। অন্যথায় Empty String message দেখাও।

## 12. Practice Solutions

### Solution 1

```python
text = "PROGRAMMING"

print(text[-1])
print(text[-2])
print(text[-3])
```

**Output:**

```text
G
N
I
```

### Solution 2

**Output:**

```text
C
C
R
R
```

### Solution 3

```python
word = input("Enter a word: ")

if len(word) > 0:
    print("First character:", word[0])
    print("Last character:", word[-1])
else:
    print("The string is empty.")
```

### Solution 4

```python
text = input("Enter a string: ")

if len(text) > 0:
    print("Last character:", text[-1])
else:
    print("Empty string!")
```

## 13. Chapter Summary

- Negative Indexing দিয়ে শেষ দিক থেকে character access করা যায়।
- `-1` হলো শেষ character-এর index।
- `-2` হলো দ্বিতীয় শেষ character-এর index।
- Positive ও Negative Indexing দিয়ে একই character access করা যায়।
- Invalid index ব্যবহার করলে `IndexError` হয়।

## 14. Self-Assessment Checklist

- [ ] Negative Indexing কী বুঝতে পারি।
- [ ] `-1`, `-2`, `-3` ব্যবহার করতে পারি।
- [ ] Positive ও Negative Index-এর পার্থক্য বুঝতে পারি।
- [ ] First ও Last character বের করতে পারি।
- [ ] Negative Index-এর `IndexError` বুঝতে পারি।

## 15. Next Topic

`10_Accessing_Characters_from_Strings.md`

পরবর্তী topic-এ Positive ও Negative Indexing ব্যবহার করে বিভিন্নভাবে String-এর character access করার বিষয়গুলো আরও অনুশীলন করব।
