
# 23. String Iteration with for Loops in Python

## 1. Introduction to String Iteration

Python-এ String-এর প্রতিটি character একে একে access করার পদ্ধতিকে **String Iteration** বলা হয়।

একটি String-এর প্রতিটি character-এর উপর কাজ করার জন্য `for` loop ব্যবহার করা যায়।

উদাহরণ:

```python
name = "Masum"

for char in name:
    print(char)
```

**Output:**

```text
M
a
s
u
m
```

এখানে `for` loop String-এর প্রতিটি character একে একে `char` variable-এ রাখে এবং print করে।

## 2. Syntax of String Iteration

**Syntax:**

```python
for variable in string:
    # Code to execute
```

**Explanation:**

- `for` হলো loop শুরু করার keyword।
- `variable` প্রতিবার একটি character গ্রহণ করে।
- `string` হলো যে String-এর উপর loop চালানো হবে।
- প্রতিটি iteration-এ loop পরবর্তী character-এ যায়।

## 3. Iterating Through a String

একটি String-এর প্রতিটি character আলাদাভাবে print করার জন্য `for` loop ব্যবহার করা যায়।

**Example 1:**

```python
text = "Python"

for char in text:
    print(char)
```

**Output:**

```text
P
y
t
h
o
n
```

**Example 2:**

```python
word = "Hello"

for letter in word:
    print("Character:", letter)
```

**Output:**

```text
Character: H
Character: e
Character: l
Character: l
Character: o
```

এখানে `letter` variable প্রতিবার একটি করে character গ্রহণ করছে।

## 4. Iterating Through a String Without a New Line

সাধারণভাবে `print()` প্রতিটি output-এর পরে নতুন line তৈরি করে।

একই line-এ সব character print করতে `end` parameter ব্যবহার করা যায়।

**Example:**

```python
text = "Python"

for char in text:
    print(char, end=" ")
```

**Output:**

```text
P y t h o n
```

এখানে `end=" "` প্রতিটি character-এর পরে একটি space যোগ করে।

## 5. Accessing Characters Using Their Index

`for` loop-এর সঙ্গে `range()` এবং `len()` ব্যবহার করে String-এর প্রতিটি character-এর index access করা যায়।

**Example:**

```python
text = "Python"

for i in range(len(text)):
    print(i, text[i])
```

**Output:**

```text
0 P
1 y
2 t
3 h
4 o
5 n
```

**Explanation:**

- `len(text)` String-এর মোট character সংখ্যা দেয়।
- `range(len(text))` 0 থেকে শেষ index পর্যন্ত সংখ্যা তৈরি করে।
- `text[i]` নির্দিষ্ট index-এর character access করে।

এখানে `i` হলো index, আর `text[i]` হলো সেই index-এর character।

## 6. Using enumerate() with String

Python-এর `enumerate()` function ব্যবহার করে একই সঙ্গে character এবং তার index পাওয়া যায়।

**Example:**

```python
text = "Python"

for index, char in enumerate(text):
    print(index, char)
```

**Output:**

```text
0 P
1 y
2 t
3 h
4 o
5 n
```

**Explanation:**

- `enumerate(text)` প্রতিটি character-এর সঙ্গে তার index প্রদান করে।
- `index` variable character-এর position রাখে।
- `char` variable character-টি রাখে।

`enumerate()` ব্যবহার করলে আলাদাভাবে `range()` এবং `len()` লেখার প্রয়োজন হয় না।

## 7. Counting Characters Using for Loop

`for` loop ব্যবহার করে একটি String-এর মোট character সংখ্যা গণনা করা যায়।

**Example:**

```python
text = "Python Programming"

count = 0

for char in text:
    count += 1

print("Total characters:", count)
```

**Output:**

```text
Total characters: 18
```

**Explanation:**

- প্রথমে `count = 0` নেওয়া হয়েছে।
- প্রতিটি character-এর জন্য `count` এক করে বাড়ানো হয়েছে।
- শেষে মোট character সংখ্যা print করা হয়েছে।

এখানে space-ও একটি character হিসেবে গণনা হয়েছে।

## 8. Counting Vowels Using for Loop

একটি String-এর মধ্যে কতগুলো vowel আছে তা `for` loop দিয়ে গণনা করা যায়।

**Example:**

```python
text = "Education"

count = 0

for char in text:
    if char in "aeiouAEIOU":
        count += 1

print("Total vowels:", count)
```

**Output:**

```text
Total vowels: 5
```

**Explanation:**

- `for` loop প্রতিটি character পরীক্ষা করে।
- `if char in "aeiouAEIOU"` চেক করে character-টি vowel কি না।
- vowel হলে `count` এক করে বাড়ে।

## 9. Finding a Specific Character

একটি String-এর মধ্যে নির্দিষ্ট কোনো character আছে কি না, তা `for` loop দিয়ে পরীক্ষা করা যায়।

**Example:**

```python
text = "Programming"
target = "g"

for char in text:
    if char == target:
        print("Character found!")
```

**Output:**

```text
Character found!
Character found!
```

**Explanation:**

এখানে `"Programming"` String-এর মধ্যে `g` দুইবার আছে। তাই message-টি দুইবার print হয়েছে।

## 10. Creating a New String Using for Loop

`for` loop ব্যবহার করে একটি String-এর character দিয়ে নতুন String তৈরি করা যায়।

**Example:**

```python
text = "Python"
result = ""

for char in text:
    result += char

print(result)
```

**Output:**

```text
Python
```

**Explanation:**

- প্রথমে একটি empty String নেওয়া হয়েছে।
- প্রতিটি character `result`-এর সঙ্গে যোগ করা হয়েছে।
- শেষে নতুন String-টি print করা হয়েছে।

মনে রাখতে হবে, Python-এর String immutable। তাই এখানে পুরোনো String পরিবর্তন হচ্ছে না; প্রতিবার নতুন String তৈরি হচ্ছে।

## 11. Reversing a String Using for Loop

`for` loop ব্যবহার করে একটি String উল্টোভাবে তৈরি করা যায়।

**Example:**

```python
text = "Python"
reverse = ""

for char in text:
    reverse = char + reverse

print(reverse)
```

**Output:**

```text
nohtyP
```

**Explanation:**

প্রতিটি নতুন character-কে `reverse` String-এর শুরুতে যোগ করা হচ্ছে। ফলে শেষ পর্যন্ত String-টি উল্টো হয়ে যায়।

## 12. Iterating Through an Empty String

একটি Empty String-এর উপর `for` loop চালালে কোনো iteration হয় না।

**Example:**

```python
text = ""

for char in text:
    print(char)

print("Loop finished")
```

**Output:**

```text
Loop finished
```

**Explanation:**

Empty String-এর মধ্যে কোনো character নেই। তাই loop-এর ভিতরের code একবারও execute হয় না।

## 13. Difference Between Direct Iteration and Index-Based Iteration

String-এর উপর `for` loop চালানোর দুটি সাধারণ পদ্ধতি রয়েছে।

| Direct Iteration | Index-Based Iteration |
|---|---|
| সরাসরি character পাওয়া যায় | Index ব্যবহার করে character পাওয়া যায় |
| `for char in text` | `for i in range(len(text))` |
| সহজ এবং readable | Index প্রয়োজন হলে useful |

**Example 1: Direct Iteration**

```python
text = "ABC"

for char in text:
    print(char)
```

**Example 2: Index-Based Iteration**

```python
text = "ABC"

for i in range(len(text)):
    print(text[i])
```

**Output of Both:**

```text
A
B
C
```

সাধারণভাবে শুধু character নিয়ে কাজ করতে হলে Direct Iteration ব্যবহার করা ভালো। আর index প্রয়োজন হলে Index-Based Iteration বা `enumerate()` ব্যবহার করা যায়।

## 14. Common Mistakes in String Iteration

### Mistake 1: Treating Character as an Index

**Incorrect Code:**

```python
text = "Python"

for char in text:
    print(text[char])
```

**Error:** `TypeError`

**Why?**

এখানে `char` একটি character, কিন্তু String indexing-এর জন্য integer index প্রয়োজন।

**Correct Code:**

```python
text = "Python"

for char in text:
    print(char)
```

### Mistake 2: Incorrect Indentation

**Incorrect Code:**

```python
text = "Python"

for char in text:
print(char)
```

**Error:** `IndentationError`

**Correct Code:**

```python
text = "Python"

for char in text:
    print(char)
```

### Mistake 3: Using an Incorrect Range

**Incorrect Code:**

```python
text = "Python"

for i in range(len(text) + 1):
    print(text[i])
```

**Error:** `IndexError`

**Why?**

String-এর শেষ index হলো `len(text) - 1`। কিন্তু এখানে অতিরিক্ত একটি index access করার চেষ্টা করা হয়েছে।

**Correct Code:**

```python
text = "Python"

for i in range(len(text)):
    print(text[i])
```

### Mistake 4: Forgetting Case Sensitivity

**Incorrect Code:**

```python
text = "Apple"
count = 0

for char in text:
    if char in "aeiou":
        count += 1

print(count)
```

**Output:**

```text
2
```

**Why?**

এখানে uppercase `A`-কে lowercase `a` হিসেবে গণনা করা হয়নি।

**Correct Code:**

```python
text = "Apple"
count = 0

for char in text:
    if char.lower() in "aeiou":
        count += 1

print(count)
```

**Output:**

```text
3
```

## 15. Practical Example

### Example 1: Printing Each Character with Its Position

```python
name = "Masum"

for index, char in enumerate(name):
    print(f"Index {index}: {char}")
```

**Output:**

```text
Index 0: M
Index 1: a
Index 2: s
Index 3: u
Index 4: m
```

### Example 2: Counting Digits in a String

```python
text = "Python123"
count = 0

for char in text:
    if char.isdigit():
        count += 1

print("Total digits:", count)
```

**Output:**

```text
Total digits: 3
```

### Example 3: Printing Only Uppercase Characters

```python
text = "PyTHon Programming"

for char in text:
    if char.isupper():
        print(char, end=" ")
```

**Output:**

```text
P T H P
```

## 16. Important Rules to Remember

1. String-এর প্রতিটি character access করতে `for` loop ব্যবহার করা যায়।
2. `for char in text` সরাসরি প্রতিটি character প্রদান করে।
3. প্রতিটি iteration-এ একটি করে character পাওয়া যায়।
4. `range(len(text))` ব্যবহার করে index access করা যায়।
5. `enumerate()` একসঙ্গে index এবং character প্রদান করে।
6. Empty String-এর উপর loop চালালে কোনো iteration হয় না।
7. String immutable, তাই সরাসরি character পরিবর্তন করা যায় না।
8. Python-এ String iteration case-sensitive।
9. `len(text)` মোট character সংখ্যা দেয়।
10. সাধারণত শুধু character প্রয়োজন হলে Direct Iteration সবচেয়ে সহজ।

## 17. Practice Problems

### Problem 1: Print Each Character

```python
text = "Bangladesh"

# Print each character using a for loop
```

**Expected Output:**

```text
B
a
n
g
l
a
d
e
s
h
```

### Problem 2: Count Total Characters

```python
text = "Hello World"

# Count total characters using a for loop
```

**Expected Output:**

```text
11
```

### Problem 3: Count Vowels

```python
text = "Computer Science"

# Count total vowels
```

**Expected Output:**

```text
6
```

### Problem 4: Print Index and Character

```python
text = "Python"

# Print each character with its index
```

**Expected Output:**

```text
0 P
1 y
2 t
3 h
4 o
5 n
```

### Problem 5: Count Digits

```python
text = "CSE4355AI2026"

# Count how many digits are present
```

**Expected Output:**

```text
8
```

### Problem 6: Reverse a String

```python
text = "Python"

# Reverse the String using a for loop
```

**Expected Output:**

```text
nohtyP
```

### Problem 7: Print Only Uppercase Characters

```python
text = "Hello PYTHON"

# Print only uppercase characters
```

**Expected Output:**

```text
H P Y T H O N
```

## 18. Chapter Summary

এই Topic-এ আমরা Python-এর `for` loop ব্যবহার করে String-এর প্রতিটি character নিয়ে কাজ করা শিখেছি।

আমরা শিখেছি:

- String Iteration
- `for` loop দিয়ে character access
- `range()` এবং `len()` দিয়ে index access
- `enumerate()` ব্যবহার
- Character counting
- Vowel এবং digit counting
- String reversing
- Empty String iteration
- Common mistakes এবং তাদের সমাধান

**Next Topic:**

`24_String_Iteration_with_while_Loops.md`

পরবর্তী Topic-এ আমরা Python-এর `while` loop ব্যবহার করে String-এর প্রতিটি character access করা শিখব।
