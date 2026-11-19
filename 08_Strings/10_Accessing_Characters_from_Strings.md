
# 10. Accessing Characters from Strings

## 1. Introduction

Python-এ String-এর নির্দিষ্ট position থেকে character access করার জন্য Indexing ব্যবহার করা হয়।

আমরা আগের topics-এ শিখেছি:

- Positive Indexing: `0` থেকে শুরু হয়।
- Negative Indexing: `-1` থেকে শুরু হয়।

এই topic-এ বিভিন্নভাবে character access করা এবং সেগুলো বাস্তব প্রোগ্রামে ব্যবহার করা শিখব।

## 2. Accessing a Single Character

String-এর নির্দিষ্ট index ব্যবহার করে একটি character access করা যায়।

```python
text = "PROGRAMMING"

print(text[0])
print(text[3])
print(text[6])
```

**Output:**

```text
P
G
M
```

এখানে:
- `text[0]` = P
- `text[3]` = G
- `text[6]` = M

## 3. Accessing Multiple Characters Individually

একাধিক character access করতে একাধিক Indexing expression ব্যবহার করা যায়।

```python
text = "PYTHON"

first = text[0]
second = text[1]
third = text[2]

print(first)
print(second)
print(third)
```

**Output:**

```text
P
Y
T
```

এখানে প্রতিটি character আলাদাভাবে variable-এ রাখা হয়েছে।

## 4. Accessing First, Middle and Last Characters

String থেকে প্রথম, মাঝের এবং শেষ character বের করা যায়।

```python
text = "PYTHON"

first = text[0]
middle = text[len(text) // 2]
last = text[-1]

print("First:", first)
print("Middle:", middle)
print("Last:", last)
```

**Output:**

```text
First: P
Middle: H
Last: N
```

**ব্যাখ্যা:**

- `text[0]` প্রথম character।
- `len(text) // 2` দিয়ে মাঝের position বের করা হয়েছে।
- `text[-1]` শেষ character।

মনে রাখবে, String-এর character সংখ্যা জোড় হলে এই formula মাঝের ডানদিকের character return করবে।

## 5. Accessing Characters Using Variables

Index একটি variable-এর মধ্যেও রাখা যায়।

```python
text = "PYTHON"

index = 2

print(text[index])
```

**Output:**

```text
T
```

এখানে `index` variable-এর value `2`, তাই `text[2]` access করা হয়েছে।

## 6. Accessing Characters Using User Input

User-এর কাছ থেকে একটি String এবং একটি index নিয়ে নির্দিষ্ট character বের করা যায়।

```python
text = input("Enter a word: ")
index = int(input("Enter an index: "))

if 0 <= index < len(text):
    print("Character:", text[index])
else:
    print("Invalid index!")
```

**Sample Input:**

```text
Enter a word: Python
Enter an index: 2
```

**Output:**

```text
Character: t
```

এখানে condition দিয়ে যাচাই করা হয়েছে index-টি String-এর valid positive index কি না।

## 7. Accessing Characters with Negative Index

Negative Index ব্যবহার করেও একইভাবে character access করা যায়।

```python
text = "PROGRAMMING"

print(text[-1])
print(text[-3])
print(text[-5])
```

**Output:**

```text
G
I
M
```

এখানে:
- `text[-1]` = শেষ character।
- `text[-3]` = তৃতীয় শেষ character।
- `text[-5]` = পঞ্চম শেষ character।

## 8. Accessing Characters Using a for Loop

`for` loop ব্যবহার করে String-এর প্রতিটি character একে একে access করা যায়।

```python
text = "PYTHON"

for character in text:
    print(character)
```

**Output:**

```text
P
Y
T
H
O
N
```

এখানে `for` loop String-এর প্রতিটি character একে একে `character` variable-এ রাখে।

## 9. Accessing Characters Using Index and for Loop

`range()` এবং `len()` ব্যবহার করে index-এর মাধ্যমে প্রতিটি character access করা যায়।

```python
text = "PYTHON"

for i in range(len(text)):
    print(i, text[i])
```

**Output:**

```text
0 P
1 Y
2 T
3 H
4 O
5 N
```

এখানে:
- `len(text)` String-এর মোট character সংখ্যা দেয়।
- `range(len(text))` valid positive index তৈরি করে।
- `text[i]` দিয়ে সেই index-এর character access করা হয়।

## 10. Accessing Characters in Reverse Order

Negative Index ব্যবহার করে String-এর character শেষ থেকে শুরু পর্যন্ত access করা যায়।

```python
text = "PYTHON"

for i in range(-1, -len(text) - 1, -1):
    print(text[i])
```

**Output:**

```text
N
O
H
T
Y
P
```

এখানে:
- শুরু হয়েছে `-1` থেকে।
- প্রতিবার index `1` করে কমছে।
- `-len(text) - 1` stop value হিসেবে ব্যবহৃত হয়েছে।
- তাই শেষ character থেকে প্রথম character পর্যন্ত access করা হয়েছে।

## 11. Practical Example: First and Last Character

একটি Word-এর প্রথম ও শেষ character বের করার প্রোগ্রাম:

```python
word = input("Enter a word: ")

if len(word) > 0:
    print("First character:", word[0])
    print("Last character:", word[-1])
else:
    print("The string is empty.")
```

**Sample Input:**

```text
Enter a word: Computer
```

**Output:**

```text
First character: C
Last character: r
```

## 12. Important Rules

1. Positive Indexing `0` থেকে শুরু হয়।
2. Negative Indexing `-1` থেকে শুরু হয়।
3. `string[index]` দিয়ে নির্দিষ্ট character access করা যায়।
4. `len(string)` দিয়ে String-এর length জানা যায়।
5. `for` loop দিয়ে সব character access করা যায়।
6. Invalid index ব্যবহার করলে `IndexError` হয়।
7. Empty String থেকে কোনো character access করা যায় না।

## 13. Common Mistakes

### Mistake 1: Invalid Index ব্যবহার করা

```python
text = "Python"

print(text[6])
```

এখানে `IndexError` হবে। কারণ valid index হলো `0` থেকে `5`।

### Mistake 2: String-এর length-কে Last Index মনে করা

```python
text = "Python"

print(text[len(text)])
```

এখানে `IndexError` হবে।

সঠিক:

```python
print(text[len(text) - 1])
```

অথবা:

```python
print(text[-1])
```

### Mistake 3: Empty String Check না করা

```python
text = ""

print(text[0])
```

এখানে `IndexError` হবে।

সঠিক:

```python
if len(text) > 0:
    print(text[0])
else:
    print("Empty string!")
```

## 14. Practice Exercises

### Exercise 1: Character Access

`"COMPUTER"` String থেকে নিচের character-গুলো বের করো:

- First character
- Fourth character
- Last character
- Second last character

### Exercise 2: First and Last Character

User-এর কাছ থেকে একটি Word নিয়ে প্রথম ও শেষ character দেখাও।

### Exercise 3: Index-Based Iteration

একটি String নিয়ে `for` loop ব্যবহার করে প্রতিটি character-এর index এবং character দেখাও।

### Exercise 4: Reverse Access

একটি String-এর সব character শেষ থেকে শুরু পর্যন্ত `for` loop ব্যবহার করে print করো।

## 15. Practice Solutions

### Solution 1

```python
text = "COMPUTER"

print(text[0])
print(text[3])
print(text[-1])
print(text[-2])
```

**Output:**

```text
C
P
R
E
```

### Solution 2

```python
word = input("Enter a word: ")

if len(word) > 0:
    print("First:", word[0])
    print("Last:", word[-1])
else:
    print("Empty string!")
```

### Solution 3

```python
text = "PYTHON"

for i in range(len(text)):
    print(i, text[i])
```

**Output:**

```text
0 P
1 Y
2 T
3 H
4 O
5 N
```

### Solution 4

```python
text = "PYTHON"

for i in range(-1, -len(text) - 1, -1):
    print(text[i])
```

**Output:**

```text
N
O
H
T
Y
P
```

## 16. Chapter Summary

- Indexing দিয়ে String-এর নির্দিষ্ট character access করা যায়।
- Positive এবং Negative Indexing দুইভাবেই character পাওয়া যায়।
- Variable ব্যবহার করে dynamic index access করা যায়।
- `for` loop দিয়ে প্রতিটি character access করা যায়।
- `range()` ও `len()` ব্যবহার করে index অনুযায়ী iteration করা যায়।
- Reverse order-এও character access করা সম্ভব।

## 17. Self-Assessment Checklist

- [ ] Positive Indexing ব্যবহার করতে পারি।
- [ ] Negative Indexing ব্যবহার করতে পারি।
- [ ] First, Middle এবং Last character বের করতে পারি।
- [ ] Variable ব্যবহার করে character access করতে পারি।
- [ ] `for` loop দিয়ে সব character access করতে পারি।
- [ ] Index অনুযায়ী character print করতে পারি।
- [ ] Reverse order-এ character access করতে পারি।

## 18. Next Topic

`11_String_Slicing_Basics.md`

পরবর্তী topic-এ String Slicing শিখব। এর মাধ্যমে একটি String থেকে একসঙ্গে একাধিক character বা নির্দিষ্ট অংশ বের করা যাবে।
