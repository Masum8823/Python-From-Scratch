# 22. Iterating Over Strings

## 1. Introduction

Python-এ **string** হলো character-এর একটি sequence। `for` loop ব্যবহার করে string-এর প্রতিটি character একে একে access করা যায়।

উদাহরণ:

```python
word = "Python"

for character in word:
    print(character)
```

Output:

```text
P
y
t
h
o
n
```

এখানে প্রতিটি iteration-এ `character` variable string-এর পরবর্তী character-এর value পায়।

**মনে রাখবে:** Python-এ string হলো immutable sequence। অর্থাৎ string তৈরি হওয়ার পর তার character সরাসরি পরিবর্তন করা যায় না, তবে নতুন string তৈরি করা যায়।

## 2. Basic Syntax

```python
for character in string:
    statement
```

এখানে:

- `for` loop শুরু করে।
- `character` প্রতিটি iteration-এ একটি character-এর value পায়।
- `string` হলো যে string-এর ওপর loop চালানো হবে।
- `statement` প্রতিটি character-এর জন্য execute হয়।

উদাহরণ:

```python
text = "Hello"

for character in text:
    print(character)
```

Output:

```text
H
e
l
l
o
```

## 3. Understanding Each Iteration

নিচের code-টি দেখো:

```python
word = "Cat"

for character in word:
    print(character)
```

Dry run:

| Iteration | `character` | Output |
|---|---|---|
| 1 | `'C'` | C |
| 2 | `'a'` | a |
| 3 | `'t'` | t |

String-এ তিনটি character থাকায় loop তিনবার execute হয়।

তবে মনে রাখবে, string-এর মধ্যে space, digit ও punctuation থাকলেও সেগুলো character হিসেবে process হয়।

## 4. Iterating Over a String with Spaces

```python
sentence = "Hello World"

for character in sentence:
    print(character)
```

Output:

```text
H
e
l
l
o
 
W
o
r
l
d
```

`Hello` এবং `World`-এর মাঝখানের space-টিও একটি character। তাই loop সেটিও process করে।

Space আলাদাভাবে শনাক্ত করতে পারো:

```python
sentence = "Hi Bro"

for character in sentence:
    if character == " ":
        print("Space found")
    else:
        print(character)
```

Output:

```text
H
i
Space found
B
r
o
```

## 5. Counting Characters in a String

String-এর character সংখ্যা বের করার সহজ উপায় হলো `len()`। তবে loop দিয়েও count করা যায়।

```python
word = "Python"
count = 0

for character in word:
    count += 1

print("Total characters:", count)
```

Output:

```text
Total characters: 6
```

### How It Works

- শুরুতে `count = 0`।
- প্রতিটি character-এর জন্য `count` এক বাড়ে।
- সব character process হওয়ার পর `count` মোট character সংখ্যা নির্দেশ করে।

**নোট:** `len(word)` সরাসরি string-এর length দেয়। এখানে loop ব্যবহার করা হচ্ছে counting-এর পদ্ধতি শেখার জন্য।

## 6. Counting Vowels

English-এর সাধারণ vowel হলো `a`, `e`, `i`, `o`, `u`। String-এর মধ্যে কতটি vowel আছে, তা loop দিয়ে বের করা যায়।

```python
word = "Education"
count = 0

for character in word.lower():
    if character in "aeiou":
        count += 1

print("Vowel count:", count)
```

Output:

```text
Vowel count: 5
```

### Explanation

1. `word.lower()` string-কে lowercase করে।
2. প্রতিটি character পরীক্ষা করা হয়।
3. Character `aeiou`-এর মধ্যে থাকলে `count` এক বাড়ে।
4. Loop শেষে মোট vowel count পাওয়া যায়।

`lower()` মূল string পরিবর্তন করে না; এটি lowercase-এ একটি নতুন string return করে।

## 7. Counting Consonants

Consonant count করার সময় সাধারণত alphabetic character-গুলোর মধ্যে vowel ছাড়া বাকিগুলো count করা হয়।

```python
word = "Python Programming"
count = 0

for character in word.lower():
    if character.isalpha() and character not in "aeiou":
        count += 1

print("Consonant count:", count)
```

Output:

```text
Consonant count: 14
```

### এখানে `isalpha()` কেন ব্যবহার হয়েছে?

`isalpha()` পরীক্ষা করে character-টি alphabetic কি না। এর ফলে space, digit ও punctuation consonant হিসেবে count হয় না।

এই উদাহরণে English text ব্যবহার করা হয়েছে। Unicode-এর অন্যান্য ভাষার alphabetic character-ও `isalpha()` দ্বারা শনাক্ত হতে পারে, তাই এটি শুধু English letter যাচাই করার method নয়।

## 8. Counting Digits in a String

String-এর মধ্যে কতটি digit আছে, তা বের করা যায় `isdigit()` দিয়ে।

```python
text = "Python12345"
count = 0

for character in text:
    if character.isdigit():
        count += 1

print("Digit count:", count)
```

Output:

```text
Digit count: 5
```

এখানে `1`, `2`, `3`, `4`, `5`—এই পাঁচটি character digit।

`isdigit()` কিছু Unicode digit-ও শনাক্ত করে। তাই সব ক্ষেত্রে এটি শুধু ASCII digit `0` থেকে `9`-এর সমতুল্য নয়।

## 9. Counting Spaces

```python
sentence = "Python is easy"
space_count = 0

for character in sentence:
    if character == " ":
        space_count += 1

print("Spaces:", space_count)
```

Output:

```text
Spaces: 2
```

এখানে `Python`, `is` এবং `easy`-এর মাঝে দুটি space রয়েছে।

এই code শুধু সাধারণ space (`" "`) count করে। Tab বা newline-এর মতো whitespace count করতে `character.isspace()` ব্যবহার করা যায়।

## 10. Finding a Character in a String

কোনো character string-এর মধ্যে আছে কি না, তা loop দিয়ে পরীক্ষা করা যায়।

```python
word = "Programming"
target = "g"
found = False

for character in word:
    if character == target:
        found = True
        break

if found:
    print("Character found")
else:
    print("Character not found")
```

Output:

```text
Character found
```

### এখানে কী ঘটেছে?

- `found = False` দিয়ে শুরু করা হয়েছে।
- প্রতিটি character `target`-এর সঙ্গে তুলনা করা হয়েছে।
- মিল পাওয়া গেলে `found = True` হয়।
- `break` loop বন্ধ করে দেয়।
- শেষে `found`-এর value অনুযায়ী message print হয়।

Python-এ `target in word` দিয়েও সরাসরি character বা substring আছে কি না পরীক্ষা করা যায়। এই উদাহরণে loop দিয়ে search করার পদ্ধতি দেখানো হয়েছে।

## 11. Counting a Specific Character

একটি নির্দিষ্ট character কতবার আছে, তা count করতে পারো।

```python
word = "banana"
target = "a"
count = 0

for character in word:
    if character == target:
        count += 1

print("Occurrences:", count)
```

Output:

```text
Occurrences: 3
```

এখানে `"banana"`-তে `a` তিনবার রয়েছে।

Case-insensitive counting চাইলে string ও target—দুটিই lowercase করে নিতে পারো।

```python
word = "BanAna"
target = "a"
count = 0

for character in word.lower():
    if character == target.lower():
        count += 1

print(count)
```

Output:

```text
3
```

## 12. Reversing a String Using a Loop

String-এর character উল্টো ক্রমে সাজাতে loop ব্যবহার করা যায়।

```python
word = "Python"
reversed_word = ""

for character in word:
    reversed_word = character + reversed_word

print(reversed_word)
```

Output:

```text
nohtyP
```

### কীভাবে কাজ করে?

| Character | `reversed_word` |
|---|---|
| `P` | `P` |
| `y` | `yP` |
| `t` | `tyP` |
| `h` | `htyP` |
| `o` | `ohtyP` |
| `n` | `nohtyP` |

প্রতিবার নতুন character-টি বর্তমান string-এর সামনে যোগ করা হয়।

Python-এ `word[::-1]` দিয়েও string reverse করা যায়। এখানে loop দিয়ে logic বোঝানো হয়েছে।

## 13. Building a New String

String immutable হওয়ায় কোনো character সরাসরি বদলানো যায় না। তবে loop ব্যবহার করে নতুন string তৈরি করা যায়।

উদাহরণ: প্রতিটি character uppercase করা।

```python
word = "python"
result = ""

for character in word:
    result += character.upper()

print(result)
```

Output:

```text
PYTHON
```

এখানে প্রতিটি character uppercase করে নতুন string-এ যোগ করা হয়েছে।

ছোট উদাহরণে এটি ঠিক আছে। খুব বড় string বারবার `+=` দিয়ে তৈরি করার পরিবর্তে list-এ অংশগুলো জমা করে `''.join(...)` ব্যবহার করা অনেক ক্ষেত্রে বেশি কার্যকর।

## 14. Removing Spaces from a String

```python
text = "P y t h o n"
result = ""

for character in text:
    if character != " ":
        result += character

print(result)
```

Output:

```text
Python
```

এখানে সাধারণ space বাদ দিয়ে বাকি character-গুলো নতুন string-এ যোগ করা হয়েছে।

যদি শুধু শুরু ও শেষের whitespace বাদ দিতে চাও, তাহলে `strip()` ব্যবহার করা সহজ। আর সব ধরনের whitespace বাদ দেওয়ার প্রয়োজন হলে `isspace()`-ভিত্তিক logic ব্যবহার করা যায়।

## 15. Checking Uppercase and Lowercase Characters

`isupper()` ও `islower()` দিয়ে character uppercase বা lowercase কি না পরীক্ষা করা যায়।

```python
text = "PyThOn"
upper_count = 0
lower_count = 0

for character in text:
    if character.isupper():
        upper_count += 1
    elif character.islower():
        lower_count += 1

print("Uppercase:", upper_count)
print("Lowercase:", lower_count)
```

Output:

```text
Uppercase: 3
Lowercase: 3
```

এখানে `P`, `T`, `O` uppercase এবং `y`, `h`, `n` lowercase।

## 16. Using `enumerate()` with Strings

কোনো character-এর position বা index-সহ access করতে `enumerate()` ব্যবহার করা যায়।

```python
word = "Python"

for index, character in enumerate(word):
    print(index, character)
```

Output:

```text
0 P
1 y
2 t
3 h
4 o
5 n
```

এখানে:

- `index` character-এর position নির্দেশ করে।
- `character` হলো সেই position-এর character।
- Python-এর সাধারণ string indexing `0` থেকে শুরু হয়।

## 17. Common Mistakes

### Mistake 1: Trying to Change a String Character Directly

Incorrect:

```python
word = "Python"
word[0] = "J"
```

এতে `TypeError` হবে, কারণ string immutable।

Correct:

```python
word = "Python"
word = "J" + word[1:]

print(word)
```

Output:

```text
Jython
```

### Mistake 2: Forgetting Case Sensitivity

```python
word = "Apple"

for character in word:
    if character == "a":
        print("Found")
```

এখানে `Found` print হবে না, কারণ `"A"` এবং `"a"` এক নয়।

Case-insensitive comparison:

```python
word = "Apple"

for character in word:
    if character.lower() == "a":
        print("Found")
```

### Mistake 3: Counting Spaces as Consonants

শুধু `character not in "aeiou"` লিখলে space, digit ও punctuation-ও count হতে পারে।

সঠিক condition:

```python
if character.isalpha() and character not in "aeiou":
    count += 1
```

### Mistake 4: Confusing Character and Index

```python
word = "Python"

for character in word:
    print(character)
```

এখানে `character` হলো `P`, `y`, `t` ইত্যাদি। এটি index নয়।

Index দরকার হলে:

```python
for index, character in enumerate(word):
    print(index, character)
```

## 18. Practical Program: Character Statistics

একটি string-এ uppercase, lowercase, digit, whitespace এবং অন্যান্য character count করা যাক।

```python
text = "Python 123!"
uppercase = 0
lowercase = 0
digits = 0
whitespace = 0
others = 0

for character in text:
    if character.isupper():
        uppercase += 1
    elif character.islower():
        lowercase += 1
    elif character.isdigit():
        digits += 1
    elif character.isspace():
        whitespace += 1
    else:
        others += 1

print("Uppercase:", uppercase)
print("Lowercase:", lowercase)
print("Digits:", digits)
print("Whitespace:", whitespace)
print("Others:", others)
```

Output:

```text
Uppercase: 1
Lowercase: 5
Digits: 3
Whitespace: 1
Others: 1
```

এখানে `!` হলো `others`-এর অংশ।

## 19. Dry Run Example

Code:

```python
word = "aba"
count = 0

for character in word:
    if character == "a":
        count += 1

print(count)
```

Dry run:

| Iteration | Character | Condition | Count |
|---|---|---|---:|
| 1 | `a` | True | 1 |
| 2 | `b` | False | 1 |
| 3 | `a` | True | 2 |

Output:

```text
2
```

প্রতিটি iteration-এ character পরীক্ষা করা হয়। শর্ত পূরণ হলেই count বাড়ে।

## 20. Practice Exercises

### Exercise 1

`for` loop দিয়ে `"Computer"` string-এর প্রতিটি character print করো।

### Exercise 2

`"Bangladesh"` string-এ মোট কতটি character আছে, loop ব্যবহার করে বের করো।

### Exercise 3

`"programming"` string-এ vowel count করো।

### Exercise 4

`"Hello123"` string-এ digit count করো।

### Exercise 5

`"banana"` string-এ `a` কতবার আছে, তা বের করো।

### Exercise 6

`"Python"` string reverse করো, slicing ব্যবহার না করে।

### Exercise 7

`"PyThOn"` string-এ uppercase ও lowercase character count করো।

### Exercise 8

`"Masum 123"` string-এর প্রতিটি character-এর index ও value print করো।

### Exercise 9

নিচের code-এর output কী হবে?

```python
text = "abc"

for character in text:
    print(character.upper())
```

### Exercise 10

String immutable বলতে কী বোঝায়?

## 21. Answer Key

### Exercise 1

```python
for character in "Computer":
    print(character)
```

### Exercise 2

```python
word = "Bangladesh"
count = 0

for character in word:
    count += 1

print(count)
```

Output:

```text
10
```

### Exercise 3

```python
word = "programming"
count = 0

for character in word.lower():
    if character in "aeiou":
        count += 1

print(count)
```

Output:

```text
3
```

### Exercise 4

```python
text = "Hello123"
count = 0

for character in text:
    if character.isdigit():
        count += 1

print(count)
```

Output:

```text
3
```

### Exercise 5

```python
word = "banana"
count = 0

for character in word:
    if character == "a":
        count += 1

print(count)
```

Output:

```text
3
```

### Exercise 6

```python
word = "Python"
result = ""

for character in word:
    result = character + result

print(result)
```

Output:

```text
nohtyP
```

### Exercise 7

```python
word = "PyThOn"
upper_count = 0
lower_count = 0

for character in word:
    if character.isupper():
        upper_count += 1
    elif character.islower():
        lower_count += 1

print("Uppercase:", upper_count)
print("Lowercase:", lower_count)
```

Output:

```text
Uppercase: 3
Lowercase: 3
```

### Exercise 8

```python
text = "Masum 123"

for index, character in enumerate(text):
    print(index, character)
```

### Exercise 9

Output:

```text
A
B
C
```

### Exercise 10

String immutable অর্থ হলো তৈরি হওয়ার পর string-এর character সরাসরি পরিবর্তন করা যায় না। পরিবর্তনের প্রয়োজন হলে নতুন string তৈরি করতে হয়।

## 22. Chapter Progress Checklist

- [ ] String-এর ওপর `for` loop চালাতে পারি।
- [ ] Space-সহ প্রতিটি character process করতে পারি।
- [ ] Loop দিয়ে character count করতে পারি।
- [ ] Vowel, consonant ও digit count করতে পারি।
- [ ] নির্দিষ্ট character search করতে পারি।
- [ ] Loop দিয়ে string reverse করতে পারি।
- [ ] `isalpha()`, `isdigit()`, `isupper()` ও `islower()` ব্যবহার করতে পারি।
- [ ] `enumerate()` দিয়ে index ও character একসঙ্গে পেতে পারি।
- [ ] String immutable হওয়ার কারণ বুঝেছি।

## 23. Summary

- `for` loop দিয়ে string-এর character একে একে access করা যায়।
- Space, digit ও punctuation-ও string-এর character।
- `lower()` দিয়ে case-insensitive comparison সহজ হয়।
- `isalpha()`, `isdigit()`, `isupper()` ও `islower()` character পরীক্ষা করতে সাহায্য করে।
- `enumerate()` index ও character একসঙ্গে দেয়।
- String immutable, তাই character সরাসরি পরিবর্তন করা যায় না।
- Loop ব্যবহার করে counting, searching, reversing ও character analysis করা যায়।

**Next Topic:** `23_Iterating_Over_Lists_and_Tuples.md`
