
# 24. String Iteration with while Loops in Python

## 1. Introduction to String Iteration with while Loop

Python-এ `while` loop ব্যবহার করেও String-এর প্রতিটি character একে একে access করা যায়।

`for` loop সরাসরি প্রতিটি character access করে। অন্যদিকে, `while` loop ব্যবহার করার সময় আমাদের নিজে থেকে index তৈরি এবং update করতে হয়।

**Example:**

```python
text = "Python"

i = 0

while i < len(text):
    print(text[i])
    i += 1
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

**Explanation:**

- `i = 0` দিয়ে প্রথম index থেকে শুরু করা হয়েছে।
- `i < len(text)` condition পরীক্ষা করে।
- `text[i]` দিয়ে বর্তমান index-এর character পাওয়া যায়।
- `i += 1` দিয়ে পরবর্তী index-এ যাওয়া হয়।

এভাবে String-এর প্রতিটি character একে একে print হয়।

## 2. Syntax of String Iteration with while Loop

**Syntax:**

```python
i = 0

while i < len(string):
    # Access character using index
    i += 1
```

**Explanation:**

- `i = 0` প্রথম index নির্দেশ করে।
- `while` condition সত্য থাকা পর্যন্ত loop চলে।
- `string[i]` বর্তমান character access করে।
- `i += 1` index এক করে বাড়ায়।

## 3. Printing Each Character Using while Loop

একটি String-এর প্রতিটি character আলাদাভাবে print করা যায়।

**Example:**

```python
text = "Hello"

i = 0

while i < len(text):
    print(text[i])
    i += 1
```

**Output:**

```text
H
e
l
l
o
```

**Explanation:**

প্রতিবার loop চলার সময় `i`-এর মান এক করে বাড়ে। তাই প্রতিবার পরবর্তী character print হয়।

## 4. Printing Characters in the Same Line

`print()` function-এর `end` parameter ব্যবহার করে সব character একই line-এ print করা যায়।

**Example:**

```python
text = "Python"

i = 0

while i < len(text):
    print(text[i], end=" ")
    i += 1
```

**Output:**

```text
P y t h o n
```

এখানে `end=" "` প্রতিটি character-এর পরে একটি space যোগ করে।

## 5. Printing Characters with Their Index

`while` loop ব্যবহার করে প্রতিটি character-এর index এবং character একসঙ্গে print করা যায়।

**Example:**

```python
text = "Python"

i = 0

while i < len(text):
    print(i, text[i])
    i += 1
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

- `i` বর্তমান index নির্দেশ করে।
- `text[i]` সেই index-এর character প্রদান করে।
- `i += 1` পরবর্তী index-এ নিয়ে যায়।

## 6. Counting Total Characters Using while Loop

`while` loop ব্যবহার করে String-এর মোট character সংখ্যা গণনা করা যায়।

**Example:**

```python
text = "Python Programming"

i = 0
count = 0

while i < len(text):
    count += 1
    i += 1

print("Total characters:", count)
```

**Output:**

```text
Total characters: 18
```

**Explanation:**

- `count = 0` দিয়ে counting শুরু হয়েছে।
- প্রতিটি character-এর জন্য `count` এক করে বাড়ে।
- `i` পরবর্তী index-এ যায়।
- শেষে মোট character সংখ্যা পাওয়া যায়।

এখানে space-ও একটি character হিসেবে গণনা হয়েছে।

## 7. Counting Vowels Using while Loop

একটি String-এর মধ্যে কতগুলো vowel আছে তা `while` loop দিয়ে গণনা করা যায়।

**Example:**

```python
text = "Education"

i = 0
count = 0

while i < len(text):
    if text[i] in "aeiouAEIOU":
        count += 1

    i += 1

print("Total vowels:", count)
```

**Output:**

```text
Total vowels: 5
```

**Explanation:**

- `text[i]` দিয়ে বর্তমান character নেওয়া হয়েছে।
- `if` condition দিয়ে character-টি vowel কি না পরীক্ষা করা হয়েছে।
- vowel হলে `count` এক করে বাড়ে।
- প্রতিবার `i` এক করে বাড়ানো হয়েছে।

## 8. Counting Digits Using while Loop

String-এর মধ্যে কতগুলো digit আছে তা গণনা করা যায়।

**Example:**

```python
text = "CSE4355AI2026"

i = 0
count = 0

while i < len(text):
    if text[i].isdigit():
        count += 1

    i += 1

print("Total digits:", count)
```

**Output:**

```text
Total digits: 8
```

**Explanation:**

`isdigit()` method পরীক্ষা করে character-টি digit কি না। Digit হলে `count` এক করে বাড়ে।

## 9. Reversing a String Using while Loop

`while` loop ব্যবহার করে একটি String উল্টোভাবে তৈরি করা যায়।

**Example:**

```python
text = "Python"

i = len(text) - 1
reverse = ""

while i >= 0:
    reverse += text[i]
    i -= 1

print(reverse)
```

**Output:**

```text
nohtyP
```

**Explanation:**

- `len(text) - 1` দিয়ে শেষ index নেওয়া হয়েছে।
- `text[i]` দিয়ে বর্তমান character access করা হয়েছে।
- `reverse += text[i]` দিয়ে character নতুন String-এ যোগ হয়েছে।
- `i -= 1` দিয়ে আগের index-এ যাওয়া হয়েছে।

এভাবে শেষ থেকে প্রথম character পর্যন্ত access করে String reverse করা হয়েছে।

## 10. Searching for a Character Using while Loop

একটি String-এর মধ্যে নির্দিষ্ট character আছে কি না তা খুঁজে বের করা যায়।

**Example:**

```python
text = "Programming"
target = "g"

i = 0
found = False

while i < len(text):
    if text[i] == target:
        found = True
        break

    i += 1

if found:
    print("Character found!")
else:
    print("Character not found!")
```

**Output:**

```text
Character found!
```

**Explanation:**

- `found = False` দিয়ে শুরু করা হয়েছে।
- প্রতিটি character-এর সঙ্গে `target` তুলনা করা হয়েছে।
- character পাওয়া গেলে `found = True` হয়।
- `break` ব্যবহার করে loop বন্ধ করা হয়েছে।

এখানে প্রথম matching character পাওয়া গেলেই search বন্ধ হয়ে যায়।

## 11. Creating a New String Using while Loop

`while` loop ব্যবহার করে একটি String-এর character দিয়ে নতুন String তৈরি করা যায়।

**Example:**

```python
text = "Hello"

i = 0
result = ""

while i < len(text):
    result += text[i]
    i += 1

print(result)
```

**Output:**

```text
Hello
```

**Explanation:**

প্রতিটি iteration-এ বর্তমান character `result`-এর সঙ্গে যোগ করা হয়েছে। শেষে নতুন String তৈরি হয়েছে।

মনে রাখতে হবে, Python-এর String immutable। তাই এখানে মূল String পরিবর্তন হচ্ছে না।

## 12. Iterating Through an Empty String

Empty String-এর উপর `while` loop চালালে loop-এর ভিতরের code execute হয় না।

**Example:**

```python
text = ""

i = 0

while i < len(text):
    print(text[i])
    i += 1

print("Loop finished")
```

**Output:**

```text
Loop finished
```

**Explanation:**

Empty String-এর length `0`। তাই প্রথম condition `0 < 0` মিথ্যা হয় এবং loop শুরুই হয় না।

## 13. Difference Between for and while Loop in String Iteration

String iteration-এর জন্য `for` এবং `while` উভয় loop ব্যবহার করা যায়।

| for Loop | while Loop |
|---|---|
| সরাসরি character access করে | Index ব্যবহার করে character access করে |
| Index নিজে থেকে update করার প্রয়োজন নেই | Index নিজে থেকে update করতে হয় |
| Syntax সহজ | তুলনামূলক বেশি code লিখতে হয় |
| সাধারণ iteration-এর জন্য useful | Condition-based iteration-এর জন্য useful |

**Example 1: for Loop**

```python
text = "Python"

for char in text:
    print(char)
```

**Example 2: while Loop**

```python
text = "Python"

i = 0

while i < len(text):
    print(text[i])
    i += 1
```

**Output of Both:**

```text
P
y
t
h
o
n
```

সাধারণত শুধু প্রতিটি character access করতে `for` loop সহজ। তবে index এবং condition নিয়ন্ত্রণ করার প্রয়োজন হলে `while` loop ব্যবহার করা যায়।

## 14. Common Mistakes in String Iteration with while Loop

### Mistake 1: Forgetting to Update the Index

**Incorrect Code:**

```python
text = "Python"

i = 0

while i < len(text):
    print(text[i])
```

**Problem:** Infinite Loop

**Why?**

এখানে `i`-এর মান বাড়ানো হয়নি। তাই condition সবসময় True থাকে এবং loop চলতেই থাকে।

**Correct Code:**

```python
text = "Python"

i = 0

while i < len(text):
    print(text[i])
    i += 1
```

### Mistake 2: Using an Incorrect Condition

**Incorrect Code:**

```python
text = "Python"

i = 0

while i <= len(text):
    print(text[i])
    i += 1
```

**Error:** `IndexError`

**Why?**

String-এর শেষ index হলো `len(text) - 1`। কিন্তু `i <= len(text)` ব্যবহার করায় অতিরিক্ত index access করার চেষ্টা হয়।

**Correct Code:**

```python
text = "Python"

i = 0

while i < len(text):
    print(text[i])
    i += 1
```

### Mistake 3: Starting from the Wrong Index

**Incorrect Code:**

```python
text = "Python"

i = 1

while i < len(text):
    print(text[i])
    i += 1
```

**Output:**

```text
y
t
h
o
n
```

**Why?**

এখানে `i = 1` দিয়ে শুরু করায় প্রথম character `P` বাদ পড়ে গেছে।

**Correct Code:**

```python
text = "Python"

i = 0

while i < len(text):
    print(text[i])
    i += 1
```

### Mistake 4: Incorrectly Updating the Index

**Incorrect Code:**

```python
text = "Python"

i = 0

while i < len(text):
    print(text[i])
    i += 2
```

**Output:**

```text
P
t
o
```

**Why?**

`i += 2` ব্যবহার করায় প্রতিবার একটি character বাদ দিয়ে পরবর্তী character access হচ্ছে।

**Correct Code:**

```python
text = "Python"

i = 0

while i < len(text):
    print(text[i])
    i += 1
```

## 15. Practical Examples

### Example 1: Printing Only Uppercase Characters

```python
text = "Hello PYTHON"

i = 0

while i < len(text):
    if text[i].isupper():
        print(text[i], end=" ")

    i += 1
```

**Output:**

```text
H P Y T H O N
```

### Example 2: Counting a Specific Character

```python
text = "Programming"
target = "m"

i = 0
count = 0

while i < len(text):
    if text[i] == target:
        count += 1

    i += 1

print("Character count:", count)
```

**Output:**

```text
Character count: 2
```

### Example 3: Printing String in Reverse Order

```python
text = "Bangladesh"

i = len(text) - 1

while i >= 0:
    print(text[i], end=" ")
    i -= 1
```

**Output:**

```text
h s e d a l g n a B
```

## 16. Important Rules to Remember

1. `while` loop দিয়েও String-এর প্রতিটি character access করা যায়।
2. সাধারণত `i = 0` দিয়ে iteration শুরু করা হয়।
3. `len(text)` String-এর মোট character সংখ্যা দেয়।
4. `text[i]` নির্দিষ্ট index-এর character access করে।
5. `i += 1` দিয়ে পরবর্তী index-এ যেতে হয়।
6. Index update না করলে Infinite Loop হতে পারে।
7. `i < len(text)` ব্যবহার করলে অতিরিক্ত index access হয় না।
8. Reverse iteration-এর জন্য `i = len(text) - 1` ব্যবহার করা যায়।
9. Empty String-এর উপর loop execute হয় না।
10. String immutable, তাই সরাসরি character পরিবর্তন করা যায় না।

## 17. Practice Problems

### Problem 1: Print Each Character

```python
text = "Bangladesh"

# Print each character using a while loop
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

# Count total characters using a while loop
```

**Expected Output:**

```text
11
```

### Problem 3: Count Vowels

```python
text = "Computer Science"

# Count total vowels using a while loop
```

**Expected Output:**

```text
6
```

### Problem 4: Count Digits

```python
text = "CSE4355AI2026"

# Count total digits using a while loop
```

**Expected Output:**

```text
8
```

### Problem 5: Reverse a String

```python
text = "Python"

# Reverse the String using a while loop
```

**Expected Output:**

```text
nohtyP
```

### Problem 6: Find a Character

```python
text = "Programming"
target = "g"

# Search for the target character
# Print "Found" if it exists
```

**Expected Output:**

```text
Found
```

### Problem 7: Count a Specific Character

```python
text = "Mississippi"
target = "s"

# Count how many times target appears
```

**Expected Output:**

```text
4
```

## 18. Chapter Summary

এই Topic-এ আমরা Python-এর `while` loop ব্যবহার করে String-এর প্রতিটি character নিয়ে কাজ করা শিখেছি।

আমরা শিখেছি:

- String Iteration with `while` Loop
- Index দিয়ে character access
- Character এবং index print করা
- Total character counting
- Vowel এবং digit counting
- Character searching
- String reversing
- Empty String iteration
- Common mistakes এবং তাদের সমাধান

**Next Topic:**

`25_Changing_Case_upper_lower_title_capitalize.md`

পরবর্তী Topic-এ আমরা String-এর uppercase, lowercase, title case এবং capitalize করার পদ্ধতি শিখব।
