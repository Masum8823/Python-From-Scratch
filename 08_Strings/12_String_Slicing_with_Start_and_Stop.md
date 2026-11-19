
# 12. String Slicing with Start and Stop

## 1. Introduction

Python String Slicing-এ `start` এবং `stop` ব্যবহার করে String-এর নির্দিষ্ট অংশ বের করা যায়।

আগের topic-এ আমরা Slicing-এর basic syntax শিখেছি। এবার Start ও Stop index কীভাবে কাজ করে তা বিস্তারিতভাবে বুঝব।

**Syntax:**

```python
string[start:stop]
```

এখানে:

- `start` = যে index থেকে character নেওয়া শুরু হবে।
- `stop` = যে index-এর আগে Slicing শেষ হবে।

**Important Rule:**

Start index অন্তর্ভুক্ত হয়, কিন্তু Stop index অন্তর্ভুক্ত হয় না।

## 2. Understanding Start and Stop

ধরি:

```python
text = "COMPUTER"
```

Index অনুযায়ী String:

| Character | C | O | M | P | U | T | E | R |
|---|---|---|---|---|---|---|---|---|
| Index | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 |

এখন:

```python
print(text[1:5])
```

**Output:**

```text
OMPU
```

ব্যাখ্যা:

- Start = 1
- Stop = 5
- নেওয়া হয়েছে index 1, 2, 3, 4।
- Index 5 নেওয়া হয়নি।

## 3. Extracting Different Parts of a String

একই String থেকে বিভিন্ন Start ও Stop ব্যবহার করে আলাদা অংশ বের করা যায়।

```python
text = "PROGRAMMING"

print(text[0:3])
print(text[3:7])
print(text[7:11])
```

**Output:**

```text
PRO
GRAM
MING
```

ব্যাখ্যা:

- `text[0:3]` = index 0 থেকে 2।
- `text[3:7]` = index 3 থেকে 6।
- `text[7:11]` = index 7 থেকে 10।

## 4. Extracting the First Few Characters

Start index `0` দিলে String-এর শুরু থেকে character নেওয়া যায়।

```python
text = "PYTHON PROGRAMMING"

print(text[0:6])
print(text[0:10])
```

**Output:**

```text
PYTHON
PYTHON PRO
```

এখানে Start index `0` হওয়ায় String-এর শুরু থেকে Slicing করা হয়েছে।

## 5. Extracting Characters from a Specific Position

কোনো নির্দিষ্ট index থেকে String-এর শেষ পর্যন্ত অংশ বের করতে চাইলে Stop index বাদ দেওয়া যায়।

```python
text = "PYTHON PROGRAMMING"

print(text[7:18])
print(text[7:])
```

**Output:**

```text
PROGRAMMING
PROGRAMMING
```

এখানে `text[7:]` index 7 থেকে String-এর শেষ পর্যন্ত সব character return করে।

## 6. Extracting the Last Few Characters

Negative Index ব্যবহার করে String-এর শেষ দিক থেকে নির্দিষ্ট অংশ বের করা যায়।

```python
text = "PROGRAMMING"

print(text[-4:])
print(text[-7:-3])
```

**Output:**

```text
MING
GRAM
```

ব্যাখ্যা:

- `text[-4:]` = শেষ ৪টি character।
- `text[-7:-3]` = index `-7` থেকে `-4` পর্যন্ত।

## 7. Using len() with Start and Stop

`len()` ব্যবহার করে String-এর শেষ index বা length অনুযায়ী Slicing করা যায়।

```python
text = "PROGRAMMING"

print(text[0:len(text)])
print(text[3:len(text)])
```

**Output:**

```text
PROGRAMMING
GRAMMING
```

এখানে `len(text)` হলো `11`।

তাই `text[3:len(text)]` index 3 থেকে শেষ পর্যন্ত character return করে।

## 8. Start and Stop with Negative Index

Positive এবং Negative Index একসঙ্গে ব্যবহার করা যায়।

```python
text = "COMPUTER"

print(text[1:-1])
print(text[-6:-2])
print(text[2:-2])
```

**Output:**

```text
OMPUTE
MPUT
MPUT
```

ব্যাখ্যা:

- `text[1:-1]` = প্রথম ও শেষ character বাদ দিয়ে।
- `text[-6:-2]` = index `-6` থেকে `-3` পর্যন্ত।
- `text[2:-2]` = index 2 থেকে শেষের দুইটি character বাদ দিয়ে।

## 9. Slicing with User Input

User-এর কাছ থেকে String, Start এবং Stop input নিয়ে Slicing করা যায়।

```python
text = input("Enter a string: ")

start = int(input("Enter start index: "))
stop = int(input("Enter stop index: "))

result = text[start:stop]

print("Result:", result)
```

**Sample Input:**

```text
Enter a string: PYTHON
Enter start index: 1
Enter stop index: 4
```

**Output:**

```text
Result: YTH
```

Python Slicing-এ Start ও Stop index-এর বাইরের সীমা থাকলেও সাধারণত Error হয় না; Python available অংশটুকু return করে।

## 10. Important Rules

1. `start` থেকে character নেওয়া শুরু হয়।
2. `stop` index-এর আগেই Slicing শেষ হয়।
3. Start index অন্তর্ভুক্ত হয়।
4. Stop index অন্তর্ভুক্ত হয় না।
5. Start না দিলে Python শুরু থেকে নেয়।
6. Stop না দিলে Python শেষ পর্যন্ত নেয়।
7. Positive ও Negative Index একসঙ্গে ব্যবহার করা যায়।
8. Slicing-এর Stop index String-এর length ছাড়িয়ে গেলেও সাধারণত `IndexError` হয় না।

## 11. Common Mistakes

### Mistake 1: Stop Index অন্তর্ভুক্ত করা

```python
text = "PYTHON"

print(text[1:4])
```

**Output:**

```text
YTH
```

এখানে `O` আসবে না, কারণ তার index 4।

### Mistake 2: ভুল Start ও Stop দেওয়া

```python
text = "PYTHON"

print(text[4:2])
```

**Output:**

```text

```

এখানে Empty String পাওয়া যাবে। কারণ Default direction-এ Start index Stop index-এর চেয়ে বড়।

### Mistake 3: String Length-কে Last Index মনে করা

```python
text = "PYTHON"

print(text[0:6])
```

এখানে পুরো String পাওয়া যাবে।

মনে রাখবে, Stop index `6` হলেও String-এর শেষ character-এর index `5`।

### Mistake 4: Negative Index ভুল গণনা করা

```python
text = "PYTHON"

print(text[-4:-1])
```

**Output:**

```text
THO
```

Negative Index ডান দিক থেকে গণনা করতে হবে।

## 12. Practice Exercises

### Exercise 1: Basic Slicing

`"COMPUTER"` থেকে নিচের অংশগুলো বের করো:

- First 3 characters
- Characters from index 2 to 5
- Last 3 characters

### Exercise 2: Output Prediction

নিচের Code-এর Output predict করো:

```python
text = "PROGRAMMING"

print(text[0:4])
print(text[4:8])
print(text[-3:])
print(text[2:-2])
```

### Exercise 3: User Input Slicing

একটি String এবং দুটি index input নিয়ে নির্দিষ্ট অংশ print করো।

### Exercise 4: Extracting Name Parts

`"ABDULLA"` String থেকে:

- First 3 characters
- Last 4 characters
- Characters from index 2 to 5

বের করো।

## 13. Practice Solutions

### Solution 1

```python
text = "COMPUTER"

print(text[0:3])
print(text[2:6])
print(text[-3:])
```

**Output:**

```text
COM
MPUT
TER
```

### Solution 2

**Output:**

```text
PROG
RAMM
ING
OGRAMMI
```

### Solution 3

```python
text = input("Enter a string: ")

start = int(input("Enter start index: "))
stop = int(input("Enter stop index: "))

print(text[start:stop])
```

### Solution 4

```python
name = "ABDULLA"

print(name[0:3])
print(name[-4:])
print(name[2:6])
```

**Output:**

```text
ABD
ULLA
DULL
```

## 14. Chapter Summary

- Start index থেকে Slicing শুরু হয়।
- Stop index অন্তর্ভুক্ত হয় না।
- `string[start:stop]` দিয়ে নির্দিষ্ট অংশ বের করা যায়।
- Start ও Stop-এর default value ব্যবহার করা যায়।
- Negative Index দিয়ে শেষ দিক থেকে Slicing করা যায়।
- `len()` ব্যবহার করে Dynamic Slicing করা যায়।

## 15. Self-Assessment Checklist

- [ ] Start ও Stop index-এর কাজ বুঝি।
- [ ] Stop index কেন বাদ যায় বুঝি।
- [ ] নির্দিষ্ট অংশ Slicing করতে পারি।
- [ ] First ও Last characters বের করতে পারি।
- [ ] Negative Index দিয়ে Slicing করতে পারি।
- [ ] User Input দিয়ে Slicing করতে পারি।
- [ ] Slicing-এর Output predict করতে পারি।

## 16. Next Topic

`13_String_Slicing_with_Step.md`

পরবর্তী topic-এ Slicing-এর `step` শিখব। এর মাধ্যমে নির্দিষ্ট ব্যবধানে character নেওয়া এবং String থেকে একাধিক character skip করা যাবে।
