# Finding Substrings with find() and index() in Python

## 1. Introduction to find() and index()

Python-এ কোনো String-এর মধ্যে নির্দিষ্ট Character বা Substring কোথায় রয়েছে, তা খুঁজে বের করার জন্য `find()` এবং `index()` method ব্যবহার করা হয়।

এই দুটি Method প্রায় একই ধরনের কাজ করে।

এরা কোনো Substring খুঁজে পেলে তার প্রথম অবস্থানের Index Number return করে।

তবে Substring খুঁজে না পেলে এদের Result আলাদা হয়:

- `find()` → `-1` return করে।
- `index()` → `ValueError` তৈরি করে।

## 2. Finding Substrings Using find()

Python-এর `find()` method ব্যবহার করে কোনো String-এর মধ্যে নির্দিষ্ট Character বা Substring খুঁজে বের করা যায়।

এটি Substring-এর প্রথম অবস্থানের Index Number return করে।

**Syntax:**

```python
string.find(substring)
```

এখানে:

- `string` → যে String-এর মধ্যে খুঁজব।
- `substring` → যে Character বা Text খুঁজতে চাই।

**Example:**

```python
text = "I love Python Programming"

result = text.find("Python")

print(result)
```

**Output:**

```text
7
```

**ব্যাখ্যা:**

এখানে `"Python"` শব্দটি `text` String-এর ৭ নম্বর Index থেকে শুরু হয়েছে।

তাই `find()` method `7` return করেছে।

## 3. Finding a Single Character Using find()

শুধু সম্পূর্ণ Word নয়, কোনো একটি Character-এর Index-ও খুঁজে বের করা যায়।

**Example:**

```python
text = "Python"

print(text.find("P"))
print(text.find("y"))
print(text.find("n"))
```

**Output:**

```text
0
1
5
```

এখানে:

- `"P"`-এর Index হলো `0`।
- `"y"`-এর Index হলো `1`।
- `"n"`-এর Index হলো `5`।

## 4. What Happens When find() Cannot Find a Substring?

যদি `find()` method কোনো Substring খুঁজে না পায়, তাহলে এটি Error না দিয়ে `-1` return করে।

**Example:**

```python
text = "I love Python"

result = text.find("Java")

print(result)
```

**Output:**

```text
-1
```

**ব্যাখ্যা:**

এখানে `"Java"` String-এর মধ্যে নেই।

তাই `find()` method `-1` return করেছে।

**Important:**

`-1` অর্থ Substring-টি পাওয়া যায়নি।

## 5. Finding the First Occurrence of a Substring

একটি String-এর মধ্যে একই Character বা Substring একাধিকবার থাকতে পারে।

`find()` method সবসময় প্রথম Occurrence-এর Index return করে।

**Example:**

```python
text = "banana"

result = text.find("a")

print(result)
```

**Output:**

```text
1
```

**ব্যাখ্যা:**

`"banana"` String-এর মধ্যে `"a"` তিনবার রয়েছে।

তাদের Index হলো:

- প্রথম `"a"` → Index `1`
- দ্বিতীয় `"a"` → Index `3`
- তৃতীয় `"a"` → Index `5`

`find()` প্রথম `"a"`-এর Index `1` return করেছে।

## 6. Using Start and End Parameters in find()

`find()` method-এর মাধ্যমে নির্দিষ্ট Index থেকে শুরু করে Substring খোঁজা যায়।

এক্ষেত্রে `start` এবং `end` parameter ব্যবহার করা হয়।

**Syntax:**

```python
string.find(substring, start, end)
```

এখানে:

- `substring` → যে Text খুঁজব।
- `start` → কোন Index থেকে Search শুরু হবে।
- `end` → কোন Index পর্যন্ত Search হবে (End Index অন্তর্ভুক্ত নয়)।

**Example 1: Using Start**

```python
text = "banana"

result = text.find("a", 2)

print(result)
```

**Output:**

```text
3
```

**ব্যাখ্যা:**

এখানে Index `2` থেকে Search শুরু হয়েছে।

প্রথম `"a"` পাওয়া গেছে Index `3`-এ।

তাই Result `3` হয়েছে।

**Example 2: Using Start and End**

```python
text = "banana"

result = text.find("a", 2, 5)

print(result)
```

**Output:**

```text
3
```

এখানে Index `2` থেকে Index `5`-এর আগ পর্যন্ত Search করা হয়েছে।

তাই Index `3`-এ থাকা প্রথম `"a"` পাওয়া গেছে।

## 7. Finding Substrings Using index()

Python-এর `index()` method-ও কোনো String-এর মধ্যে নির্দিষ্ট Character বা Substring খুঁজে বের করতে ব্যবহার করা হয়।

এটি Substring-এর প্রথম অবস্থানের Index Number return করে।

**Syntax:**

```python
string.index(substring)
```

**Example:**

```python
text = "I love Python Programming"

result = text.index("Python")

print(result)
```

**Output:**

```text
7
```

এখানে `"Python"` শব্দটি Index `7` থেকে শুরু হয়েছে।

তাই `index()` method `7` return করেছে।

## 8. What Happens When index() Cannot Find a Substring?

`index()` method কোনো Substring খুঁজে না পেলে `ValueError` তৈরি করে।

**Example:**

```python
text = "I love Python"

result = text.index("Java")

print(result)
```

**Output:**

```text
ValueError: substring not found
```

**ব্যাখ্যা:**

এখানে `"Java"` String-এর মধ্যে নেই।

তাই `index()` method `ValueError` তৈরি করেছে।

অন্যদিকে `find()` একই পরিস্থিতিতে `-1` return করত।

## 9. Using Start and End Parameters in index()

`index()` method-এর মধ্যেও `start` এবং `end` parameter ব্যবহার করা যায়।

**Syntax:**

```python
string.index(substring, start, end)
```

**Example 1: Using Start**

```python
text = "banana"

result = text.index("a", 2)

print(result)
```

**Output:**

```text
3
```

এখানে Index `2` থেকে Search শুরু হয়েছে।

তাই প্রথম `"a"` পাওয়া গেছে Index `3`-এ।

**Example 2: Using Start and End**

```python
text = "banana"

result = text.index("a", 2, 5)

print(result)
```

**Output:**

```text
3
```

এখানে Index `2` থেকে `5`-এর আগ পর্যন্ত Search করা হয়েছে।

## 10. Difference Between find() and index()

`find()` এবং `index()` প্রায় একই কাজ করলেও Substring না পেলে এদের আচরণ আলাদা।

| find() | index() |
|---|---|
| Substring-এর Index return করে। | Substring-এর Index return করে। |
| Substring না পেলে `-1` return করে। | Substring না পেলে `ValueError` তৈরি করে। |
| Error তৈরি করে না। | Error তৈরি করে। |
| `text.find("Java")` | `text.index("Java")` |

**Example:**

```python
text = "I love Python"

print(text.find("Java"))
```

**Output:**

```text
-1
```

অন্যদিকে:

```python
text = "I love Python"

print(text.index("Java"))
```

**Output:**

```text
ValueError: substring not found
```

## 11. Finding Substrings with if-else

`find()` method-এর Result ব্যবহার করে কোনো Substring আছে কি না পরীক্ষা করা যায়।

যেহেতু Substring না পেলে `-1` return করে, তাই `-1` দিয়ে Condition Check করা যায়।

**Example:**

```python
text = "I love Python Programming"

position = text.find("Python")

if position != -1:
    print("Word found at index:", position)
else:
    print("Word not found.")
```

**Output:**

```text
Word found at index: 7
```

**ব্যাখ্যা:**

- প্রথমে `find()` দিয়ে `"Python"` খোঁজা হয়েছে।
- Substring পাওয়া গেলে তার Index return করেছে।
- `position != -1` Condition True হয়েছে।
- তাই `if` block execute হয়েছে।

## 12. Using find() with User Input

`input()` ব্যবহার করে User-এর কাছ থেকে কোনো Word নিয়ে সেটি String-এর মধ্যে কোথায় রয়েছে তা বের করা যায়।

**Example:**

```python
text = "I am learning Python Programming"

word = input("Enter a word to search: ")

position = text.find(word)

if position != -1:
    print("Word found at index:", position)
else:
    print("Word not found.")
```

**Sample Input 1:**

```text
Enter a word to search: Python
```

**Output 1:**

```text
Word found at index: 13
```

**Sample Input 2:**

```text
Enter a word to search: Java
```

**Output 2:**

```text
Word not found.
```

এখানে User-এর দেওয়া Word খুঁজে তার প্রথম অবস্থানের Index দেখানো হয়েছে।

## 13. Finding the Last Occurrence Using rfind()

Python-এ `rfind()` method ব্যবহার করে কোনো Substring-এর শেষ Occurrence-এর Index খুঁজে বের করা যায়।

এটি `find()`-এর মতো কাজ করে, তবে Search করার সময় ডান দিক থেকে খোঁজে।

**Syntax:**

```python
string.rfind(substring)
```

**Example:**

```python
text = "banana"

result = text.rfind("a")

print(result)
```

**Output:**

```text
5
```

**ব্যাখ্যা:**

`"banana"` String-এর মধ্যে `"a"` তিনবার রয়েছে।

তাদের Index হলো `1`, `3` এবং `5`।

`rfind()` শেষ `"a"`-এর Index `5` return করেছে।

**Example 2:**

```python
text = "Python Programming Python"

print(text.find("Python"))
print(text.rfind("Python"))
```

**Output:**

```text
0
20
```

এখানে:

- `find()` প্রথম `"Python"`-এর Index `0` return করেছে।
- `rfind()` শেষ `"Python"`-এর Index `20` return করেছে।

**Important:**

`rfind()` Substring না পেলে `-1` return করে।

## 14. Common Mistakes in find() and index()

### Mistake 1: Confusing find() with index()

**Example:**

```python
text = "Python"

print(text.find("Java"))
```

**Output:**

```text
-1
```

অনেকে মনে করতে পারে `find()` Substring না পেলে Error তৈরি করবে। কিন্তু এটি `-1` return করে।

### Mistake 2: Using index() Without Checking

**Incorrect Code:**

```python
text = "Python"

position = text.index("Java")

print(position)
```

**Error:**

```text
ValueError: substring not found
```

**Solution:**

যদি নিশ্চিত না হও যে Substring রয়েছে কি না, তাহলে আগে `find()` ব্যবহার করে পরীক্ষা করা যায়।

```python
text = "Python"

position = text.find("Java")

if position != -1:
    print(position)
else:
    print("Substring not found.")
```

**Output:**

```text
Substring not found.
```

### Mistake 3: Forgetting Case Sensitivity

**Example:**

```python
text = "I Love Python"

print(text.find("python"))
```

**Output:**

```text
-1
```

এখানে `"python"` এবং `"Python"` আলাদা হওয়ায় Substring পাওয়া যায়নি।

**Solution:**

```python
text = "I Love Python"

print(text.lower().find("python"))
```

**Output:**

```text
7
```

### Mistake 4: Using an Incorrect Start Index

**Example:**

```python
text = "banana"

print(text.find("a", 4))
```

**Output:**

```text
5
```

এখানে Index `4` থেকে Search শুরু হয়েছে। তাই Index `1` এবং `3`-এর `"a"` বিবেচনা করা হয়নি।

## 15. Practical Examples

### Example 1: Finding a Word in a Sentence

```python
sentence = "Python is easy to learn"

position = sentence.find("easy")

print("Position:", position)
```

**Output:**

```text
Position: 10
```

### Example 2: Finding the Position of @ in an Email

```python
email = "masum@gmail.com"

position = email.find("@")

print("Position of @:", position)
```

**Output:**

```text
Position of @: 5
```

এখানে Email-এর মধ্যে `"@"` Character-এর Index খুঁজে বের করা হয়েছে।

### Example 3: Finding the First and Last Occurrence

```python
text = "programming"

print("First occurrence:", text.find("m"))
print("Last occurrence:", text.rfind("m"))
```

**Output:**

```text
First occurrence: 6
Last occurrence: 7
```

### Example 4: Searching for a Word with User Input

```python
sentence = "I am learning Python Programming"

word = input("Enter a word: ")

position = sentence.find(word)

if position != -1:
    print("Found at index:", position)
else:
    print("Word not found.")
```

**Sample Input:**

```text
Enter a word: Programming
```

**Output:**

```text
Found at index: 18
```

### Example 5: Finding a Character from a Specific Position

```python
text = "banana"

position = text.find("a", 3)

print(position)
```

**Output:**

```text
5
```

এখানে Index `3` থেকে Search শুরু হয়েছে। তাই শেষ `"a"`-এর Index `5` পাওয়া গেছে।

## 16. Important Rules to Remember

1. `find()` এবং `index()` দিয়ে String-এর মধ্যে Substring খুঁজে বের করা যায়।
2. দুটি Method-ই Substring-এর প্রথম Occurrence-এর Index return করে।
3. `find()` Substring না পেলে `-1` return করে।
4. `index()` Substring না পেলে `ValueError` তৈরি করে।
5. `start` parameter দিয়ে Search-এর শুরু নির্ধারণ করা যায়।
6. `end` parameter দিয়ে Search-এর শেষ সীমা নির্ধারণ করা যায়।
7. `end` Index Search-এর মধ্যে অন্তর্ভুক্ত হয় না।
8. `rfind()` দিয়ে শেষ Occurrence-এর Index খুঁজে পাওয়া যায়।
9. `find()` এবং `rfind()` Substring না পেলে `-1` return করে।
10. এই Method-গুলো Case-Sensitive।

## 17. Practice Problems

### Problem 1: Find a Word

নিচের String-এর মধ্যে `"Python"`-এর Index খুঁজে বের করো।

```python
text = "I love Python Programming"
```

**Expected Output:**

```text
7
```

### Problem 2: Find a Character

নিচের String-এর মধ্যে `"a"`-এর প্রথম Index খুঁজে বের করো।

```python
text = "banana"
```

**Expected Output:**

```text
1
```

### Problem 3: Find a Missing Word

নিচের String-এর মধ্যে `"Java"` খুঁজে বের করো।

```python
text = "I love Python"
```

**Expected Output:**

```text
-1
```

### Problem 4: Use index()

নিচের String-এর মধ্যে `"Programming"`-এর Index খুঁজে বের করো।

```python
text = "Python Programming"
```

**Expected Output:**

```text
7
```

### Problem 5: Use rfind()

নিচের String-এর মধ্যে `"a"`-এর শেষ Occurrence-এর Index খুঁজে বের করো।

```python
text = "banana"
```

**Expected Output:**

```text
5
```

### Problem 6: Use Start Parameter

Index `2` থেকে Search শুরু করে `"a"`-এর অবস্থান খুঁজে বের করো।

```python
text = "banana"
```

**Expected Output:**

```text
3
```

### Problem 7: Find a Word with User Input

User-এর কাছ থেকে একটি Word নিয়ে নিচের String-এর মধ্যে সেটির Index খুঁজে বের করো।

```python
text = "I am learning Python Programming"
```

**Sample Input:**

```text
Python
```

**Expected Output:**

```text
13
```

### Problem 8: Predict the Output

```python
text = "banana"

print(text.find("a"))
print(text.find("a", 2))
print(text.rfind("a"))
print(text.find("z"))
```

**Expected Output:**

```text
1
3
5
-1
```

## 18. Summary

- `find()` এবং `index()` Method দিয়ে String-এর মধ্যে Substring খুঁজে বের করা যায়।
- দুটি Method-ই Substring-এর প্রথম অবস্থানের Index return করে।
- `find()` Substring না পেলে `-1` return করে।
- `index()` Substring না পেলে `ValueError` তৈরি করে।
- `start` এবং `end` parameter ব্যবহার করে নির্দিষ্ট অংশে Search করা যায়।
- `rfind()` দিয়ে Substring-এর শেষ Occurrence খুঁজে বের করা যায়।
- `find()` এবং `rfind()` Substring না পেলে `-1` return করে।

`find()` এবং `index()` Python-এর গুরুত্বপূর্ণ String Methods, যা Text Searching, Character Position Finding এবং বিভিন্ন Text Processing-এর কাজে ব্যবহার করা হয়।