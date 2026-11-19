
# 11. String Slicing Basics in Python

## 1. Introduction to String Slicing

Python-এ একটি String থেকে নির্দিষ্ট অংশ বা একাধিক character বের করার পদ্ধতিকে **String Slicing** বলা হয়।

Indexing দিয়ে একটি character access করা যায়, কিন্তু Slicing দিয়ে একসঙ্গে একাধিক character বের করা যায়।

উদাহরণ:

```python
text = "PYTHON"

print(text[0:3])
```

**Output:**

```text
PYT
```

এখানে `text[0:3]` দিয়ে index `0` থেকে `2` পর্যন্ত character নেওয়া হয়েছে।

## 2. Syntax of String Slicing

String Slicing-এর basic syntax:

```python
string[start:stop]
```

এখানে:

- `string` = যে String থেকে অংশ বের করতে চাই।
- `start` = যেখান থেকে Slicing শুরু হবে।
- `stop` = যে index-এর আগে Slicing শেষ হবে।

**Important:** Stop index অন্তর্ভুক্ত হয় না। অর্থাৎ, Stop-এর আগের index পর্যন্ত character নেওয়া হয়।

## 3. Basic Slicing Examples

```python
text = "PROGRAMMING"

print(text[0:4])
print(text[4:8])
print(text[0:7])
```

**Output:**

```text
PROG
RAMM
PROGRAM
```

ব্যাখ্যা:

- `text[0:4]` = index 0, 1, 2, 3
- `text[4:8]` = index 4, 5, 6, 7
- `text[0:7]` = index 0 থেকে 6

প্রতিটি ক্ষেত্রে Stop index বাদ দেওয়া হয়েছে।

## 4. Slicing with Positive Index

Positive Index ব্যবহার করে String-এর যেকোনো অংশ বের করা যায়।

```python
text = "PYTHON"

print(text[1:4])
print(text[2:5])
print(text[0:6])
```

**Output:**

```text
YTH
THO
PYTHON
```

## 5. Slicing Without Start Index

Start index না দিলে Python স্বয়ংক্রিয়ভাবে String-এর শুরু থেকে Slicing শুরু করে।

```python
text = "PYTHON"

print(text[:3])
print(text[:5])
```

**Output:**

```text
PYT
PYTHO
```

এখানে:

- `text[:3]` = শুরু থেকে index 2 পর্যন্ত।
- `text[:5]` = শুরু থেকে index 4 পর্যন্ত।

## 6. Slicing Without Stop Index

Stop index না দিলে Python String-এর শেষ পর্যন্ত Slicing করে।

```python
text = "PYTHON"

print(text[2:])
print(text[4:])
```

**Output:**

```text
THON
ON
```

এখানে:

- `text[2:]` = index 2 থেকে শেষ পর্যন্ত।
- `text[4:]` = index 4 থেকে শেষ পর্যন্ত।

## 7. Slicing Without Start and Stop

Start এবং Stop—দুটিই না দিলে সম্পূর্ণ String-এর একটি copy পাওয়া যায়।

```python
text = "PYTHON"

print(text[:])
```

**Output:**

```text
PYTHON
```

এখানে `text[:]` দিয়ে সম্পূর্ণ String নেওয়া হয়েছে।

## 8. Slicing with len()

`len()` ব্যবহার করে String-এর শেষ পর্যন্ত Slicing করা যায়।

```python
text = "PROGRAMMING"

print(text[0:len(text)])
```

**Output:**

```text
PROGRAMMING
```

এখানে `len(text)` String-এর মোট character সংখ্যা return করে।

## 9. Slicing with Negative Index

Negative Index ব্যবহার করেও String-এর নির্দিষ্ট অংশ বের করা যায়।

```python
text = "PYTHON"

print(text[-4:-1])
print(text[-5:-2])
```

**Output:**

```text
THO
YTH
```

ব্যাখ্যা:

- `text[-4:-1]` = index `-4` থেকে `-2` পর্যন্ত।
- `text[-5:-2]` = index `-5` থেকে `-3` পর্যন্ত।

এখানেও Stop index অন্তর্ভুক্ত হয় না।

## 10. Combining Positive and Negative Index

Slicing-এ Positive এবং Negative Index একসঙ্গে ব্যবহার করা যায়।

```python
text = "PYTHON"

print(text[1:-1])
print(text[0:-2])
```

**Output:**

```text
YTHO
PYTH
```

এখানে:

- `text[1:-1]` = প্রথম character বাদ দিয়ে শেষ character-এর আগ পর্যন্ত।
- `text[0:-2]` = শুরু থেকে শেষের দুইটি character বাদ দিয়ে।

## 11. Slicing Does Not Modify the Original String

String Slicing মূল String পরিবর্তন করে না। এটি একটি নতুন String তৈরি করে।

```python
text = "PYTHON"

result = text[0:3]

print("Original:", text)
print("Sliced:", result)
```

**Output:**

```text
Original: PYTHON
Sliced: PYT
```

এখানে Original String আগের মতোই `PYTHON` রয়েছে।

## 12. Practical Example: Extracting First Name

একটি String থেকে প্রথম কয়েকটি character বের করা যায়।

```python
name = "Abdulla"

first_part = name[0:4]

print(first_part)
```

**Output:**

```text
Abdu
```

এখানে index `0` থেকে `3` পর্যন্ত character নেওয়া হয়েছে।

## 13. Important Rules

1. Slicing দিয়ে String-এর একটি নির্দিষ্ট অংশ বের করা যায়।
2. Basic syntax হলো `string[start:stop]`।
3. Start index অন্তর্ভুক্ত হয়।
4. Stop index অন্তর্ভুক্ত হয় না।
5. Start না দিলে Slicing শুরু থেকে হয়।
6. Stop না দিলে Slicing শেষ পর্যন্ত হয়।
7. `string[:]` দিয়ে সম্পূর্ণ String পাওয়া যায়।
8. Positive ও Negative Index—দুটিই ব্যবহার করা যায়।
9. Slicing মূল String পরিবর্তন করে না।

## 14. Common Mistakes

### Mistake 1: Stop Index-কে অন্তর্ভুক্ত মনে করা

```python
text = "PYTHON"

print(text[0:3])
```

Output:

```text
PYT
```

এখানে `H` আসবে না, কারণ তার index `3`, যা Stop index।

### Mistake 2: Start এবং Stop উল্টো ব্যবহার করা

```python
text = "PYTHON"

print(text[4:2])
```

Output:

```text

```

এখানে Empty String পাওয়া যাবে। কারণ Default positive direction-এ Start index Stop index-এর চেয়ে বড়।

### Mistake 3: Invalid Stop Index নিয়ে বিভ্রান্ত হওয়া

```python
text = "PYTHON"

print(text[0:20])
```

Output:

```text
PYTHON
```

Slicing-এর Stop index String-এর length-এর চেয়ে বড় হলেও সাধারণত `IndexError` হয় না। Python যতটুকু character আছে, ততটুকুই return করে।

## 15. Practice Exercises

### Exercise 1: Basic Slicing

`"PROGRAMMING"` থেকে নিচের অংশগুলো বের করো:

- First 4 characters
- Characters from index 3 to 7
- Last 4 characters

### Exercise 2: Missing Start and Stop

নিচের Code-এর Output Predict করো:

```python
text = "COMPUTER"

print(text[:4])
print(text[3:])
print(text[:])
```

### Exercise 3: Negative Slicing

`"PYTHON"` থেকে Negative Index ব্যবহার করে:

- `THO` বের করো।
- `YTH` বের করো।

### Exercise 4: Extracting Text

একটি String input নাও এবং তার প্রথম তিনটি character print করো। String-এর length 3-এর কম হলেও যেন Error না হয়।

## 16. Practice Solutions

### Solution 1

```python
text = "PROGRAMMING"

print(text[0:4])
print(text[3:8])
print(text[-4:])
```

**Output:**

```text
PROG
GRAMM
MING
```

### Solution 2

**Output:**

```text
COMP
PUTER
COMPUTER
```

### Solution 3

```python
text = "PYTHON"

print(text[-4:-1])
print(text[-5:-2])
```

**Output:**

```text
THO
YTH
```

### Solution 4

```python
text = input("Enter a string: ")

print("First three characters:", text[:3])
```

এখানে String ছোট হলেও Slicing নিরাপদে কাজ করবে।

## 17. Chapter Summary

- String Slicing দিয়ে একাধিক character একসঙ্গে বের করা যায়।
- `string[start:stop]` হলো Basic Syntax।
- Start অন্তর্ভুক্ত হয়, Stop অন্তর্ভুক্ত হয় না।
- Start বা Stop বাদ দেওয়া যায়।
- Positive ও Negative Index ব্যবহার করা যায়।
- Slicing মূল String পরিবর্তন করে না।
- Stop index String-এর length ছাড়িয়ে গেলেও Error হয় না।

## 18. Self-Assessment Checklist

- [ ] String Slicing কী বুঝতে পারি।
- [ ] `string[start:stop]` ব্যবহার করতে পারি।
- [ ] Start ও Stop index-এর কাজ বুঝি।
- [ ] Start ও Stop বাদ দিয়ে Slicing করতে পারি।
- [ ] Negative Index দিয়ে Slicing করতে পারি।
- [ ] Slicing-এর Output Predict করতে পারি।
- [ ] Slicing মূল String পরিবর্তন করে না বুঝি।

## 19. Next Topic

`12_String_Slicing_with_Start_and_Stop.md`

পরবর্তী topic-এ Start ও Stop index ব্যবহার করে String Slicing আরও বিস্তারিতভাবে শিখব এবং বিভিন্ন ধরনের problem solve করব।
