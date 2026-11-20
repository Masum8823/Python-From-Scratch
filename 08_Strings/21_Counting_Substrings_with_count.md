
# 21. Counting Substrings with count() in Python

## 1. Introduction to count()

Python-এ কোনো String-এর মধ্যে নির্দিষ্ট Character বা Substring কতবার রয়েছে, তা গণনা করার জন্য `count()` method ব্যবহার করা হয়।

এটি নির্দিষ্ট Character বা Substring-এর মোট Occurrence সংখ্যা return করে।

**Example:**

```python
text = "banana"

result = text.count("a")

print(result)
```

**Output:**

```text
3
```

**ব্যাখ্যা:**

এখানে `"banana"` String-এর মধ্যে `"a"` মোট ৩ বার রয়েছে।

তাই `count()` method `3` return করেছে।

## 2. Syntax of count()

**Syntax:**

```python
string.count(substring)
```

এখানে:

- `string` → যে String-এর মধ্যে Search করব।
- `substring` → যে Character বা Text গণনা করতে চাই।

`count()` method একটি Integer Number return করে।

## 3. Counting a Single Character

কোনো String-এর মধ্যে একটি নির্দিষ্ট Character কতবার রয়েছে, তা `count()` দিয়ে গণনা করা যায়।

**Example:**

```python
text = "programming"

print(text.count("m"))
print(text.count("g"))
print(text.count("r"))
```

**Output:**

```text
2
2
2
```

**ব্যাখ্যা:**

এখানে:

- `"m"` রয়েছে ২ বার।
- `"g"` রয়েছে ২ বার।
- `"r"` রয়েছে ২ বার।

তাই প্রতিটি Character-এর মোট সংখ্যা return হয়েছে।

## 4. Counting a Substring

শুধু একটি Character নয়, একাধিক Character-এর Substring কতবার রয়েছে, সেটিও গণনা করা যায়।

**Example:**

```python
text = "Python is easy. Python is powerful."

print(text.count("Python"))
print(text.count("is"))
print(text.count("o"))
```

**Output:**

```text
2
2
3
```

**ব্যাখ্যা:**

- `"Python"` রয়েছে ২ বার।
- `"is"` রয়েছে ২ বার।
- `"o"` রয়েছে ৩ বার।

## 5. What Happens When a Substring Is Not Found?

যদি কোনো Substring String-এর মধ্যে না থাকে, তাহলে `count()` method `0` return করে।

এটি কোনো Error তৈরি করে না।

**Example:**

```python
text = "I love Python"

result = text.count("Java")

print(result)
```

**Output:**

```text
0
```

**ব্যাখ্যা:**

এখানে `"Java"` String-এর মধ্যে নেই।

তাই `count()` method `0` return করেছে।

**Important:**

`0` অর্থ Substring-টি String-এর মধ্যে পাওয়া যায়নি।

## 6. Counting Multiple Occurrences

একটি String-এর মধ্যে একই Character বা Substring একাধিকবার থাকতে পারে।

`count()` method সবগুলো Non-Overlapping Occurrence গণনা করে।

**Example:**

```python
text = "banana"

print(text.count("a"))
print(text.count("na"))
print(text.count("ana"))
```

**Output:**

```text
3
2
1
```

**ব্যাখ্যা:**

`"banana"` String-এর মধ্যে:

- `"a"` রয়েছে ৩ বার।
- `"na"` রয়েছে ২ বার।
- `"ana"` রয়েছে ১ বার।

এখানে `count()` Overlapping Substring আলাদাভাবে গণনা করে না।

**Example:**

```python
text = "banana"

print(text.count("ana"))
```

**Output:**

```text
1
```

এখানে `"ana"` দুটি Overlapping Position-এ পাওয়া যেতে পারে। কিন্তু `count()` শুধু Non-Overlapping Occurrence গণনা করে।

তাই Result `1` হয়েছে।

## 7. Using Start Parameter in count()

`count()` method-এর মাধ্যমে String-এর নির্দিষ্ট Index থেকে Substring গণনা করা যায়।

এক্ষেত্রে `start` parameter ব্যবহার করা হয়।

**Syntax:**

```python
string.count(substring, start)
```

এখানে:

- `substring` → যে Text গণনা করব।
- `start` → কোন Index থেকে গণনা শুরু হবে।

**Example:**

```python
text = "banana"

result = text.count("a", 2)

print(result)
```

**Output:**

```text
2
```

**ব্যাখ্যা:**

এখানে Index `2` থেকে গণনা শুরু হয়েছে।

Index `2` থেকে String-এর বাকি অংশ হলো `"nana"`।

এই অংশে `"a"` রয়েছে ২ বার।

তাই Result `2` হয়েছে।

## 8. Using Start and End Parameters in count()

`count()` method-এ `start` এবং `end` উভয় parameter ব্যবহার করা যায়।

এর মাধ্যমে String-এর নির্দিষ্ট অংশের মধ্যে Substring গণনা করা সম্ভব।

**Syntax:**

```python
string.count(substring, start, end)
```

এখানে:

- `substring` → যে Text গণনা করব।
- `start` → কোন Index থেকে গণনা শুরু হবে।
- `end` → কোন Index পর্যন্ত গণনা হবে।

**Important:** End Index অন্তর্ভুক্ত হয় না।

**Example:**

```python
text = "banana"

result = text.count("a", 1, 5)

print(result)
```

**Output:**

```text
2
```

**ব্যাখ্যা:**

এখানে Index `1` থেকে Index `5`-এর আগ পর্যন্ত গণনা করা হয়েছে।

এই অংশটি হলো `"anan"`।

এখানে `"a"` রয়েছে ২ বার।

তাই Result `2` হয়েছে।

**Example 2:**

```python
text = "banana"

print(text.count("a", 0, 3))
print(text.count("a", 3, 6))
```

**Output:**

```text
1
2
```

এখানে:

- প্রথম ক্ষেত্রে Index `0` থেকে `3`-এর আগ পর্যন্ত গণনা হয়েছে।
- দ্বিতীয় ক্ষেত্রে Index `3` থেকে `6`-এর আগ পর্যন্ত গণনা হয়েছে।

## 9. Case Sensitivity in count()

Python-এর `count()` method Case-Sensitive।

অর্থাৎ Uppercase এবং Lowercase Character-কে আলাদা হিসেবে বিবেচনা করে।

**Example:**

```python
text = "Python python PYTHON"

print(text.count("Python"))
print(text.count("python"))
print(text.count("PYTHON"))
```

**Output:**

```text
1
1
1
```

**ব্যাখ্যা:**

এখানে `"Python"`, `"python"` এবং `"PYTHON"` আলাদা Text হিসেবে বিবেচিত হয়েছে।

তাই প্রতিটির Count `1` হয়েছে।

**Solution:**

Case-Insensitive Counting করতে চাইলে `lower()` ব্যবহার করা যায়।

```python
text = "Python python PYTHON"

result = text.lower().count("python")

print(result)
```

**Output:**

```text
3
```

এখানে প্রথমে String-কে Lowercase করা হয়েছে।

তারপর `"python"` কতবার রয়েছে তা গণনা করা হয়েছে।

## 10. Counting Substrings with if-else

`count()` method-এর Result ব্যবহার করে কোনো Character বা Substring রয়েছে কি না পরীক্ষা করা যায়।

**Example:**

```python
text = "I love Python Programming"

total = text.count("Python")

if total > 0:
    print("Word found.")
else:
    print("Word not found.")
```

**Output:**

```text
Word found.
```

**ব্যাখ্যা:**

- প্রথমে `count()` দিয়ে `"Python"` গণনা করা হয়েছে।
- Substring পাওয়া যাওয়ায় Result `1` হয়েছে।
- `total > 0` Condition True হয়েছে।
- তাই `if` block execute হয়েছে।

## 11. Using count() with User Input

`input()` ব্যবহার করে User-এর কাছ থেকে কোনো Character বা Word নিয়ে String-এর মধ্যে সেটি কতবার রয়েছে, তা গণনা করা যায়।

**Example:**

```python
text = "I am learning Python Programming"

word = input("Enter a word to count: ")

total = text.count(word)

print("Total occurrences:", total)
```

**Sample Input 1:**

```text
Enter a word to count: Python
```

**Output 1:**

```text
Total occurrences: 1
```

**Sample Input 2:**

```text
Enter a word to count: am
```

**Output 2:**

```text
Total occurrences: 1
```

এখানে User-এর দেওয়া Word String-এর মধ্যে কতবার রয়েছে তা গণনা করা হয়েছে।

## 12. Counting Characters in a String

`count()` ব্যবহার করে কোনো String-এর মধ্যে নির্দিষ্ট Character-এর সংখ্যা বের করা যায়।

**Example:**

```python
text = "programming"

vowel_a = text.count("a")
vowel_e = text.count("e")
vowel_i = text.count("i")
vowel_o = text.count("o")
vowel_u = text.count("u")

total = vowel_a + vowel_e + vowel_i + vowel_o + vowel_u

print("Total vowels:", total)
```

**Output:**

```text
Total vowels: 3
```

**ব্যাখ্যা:**

এখানে:

- `"a"` রয়েছে ১ বার।
- `"i"` রয়েছে ১ বার।
- `"o"` রয়েছে ১ বার।

সবগুলো যোগ করে মোট Vowel-এর সংখ্যা পাওয়া গেছে `3`।

## 13. Difference Between find() and count()

`find()` এবং `count()` দুটিই String-এর মধ্যে Substring Search করতে ব্যবহার করা হয়।

তবে এদের কাজ আলাদা।

| find() | count() |
|---|---|
| Substring-এর Index return করে। | Substring-এর মোট সংখ্যা return করে। |
| প্রথম Occurrence খুঁজে বের করে। | Non-Overlapping Occurrence গণনা করে। |
| না পেলে `-1` return করে। | না পেলে `0` return করে। |
| `text.find("a")` | `text.count("a")` |

**Example:**

```python
text = "banana"

print(text.find("a"))
print(text.count("a"))
```

**Output:**

```text
1
3
```

এখানে:

- `find()` প্রথম `"a"`-এর Index `1` return করেছে।
- `count()` মোট `"a"`-এর সংখ্যা `3` return করেছে।

## 14. Common Mistakes in count()

### Mistake 1: Confusing count() with find()

**Example:**

```python
text = "banana"

print(text.count("a"))
```

**Output:**

```text
3
```

অনেকে মনে করতে পারে `count()` প্রথম Character-এর Index return করবে।

কিন্তু এটি মোট Occurrence সংখ্যা return করে।

প্রথম Occurrence-এর Index বের করতে `find()` ব্যবহার করতে হয়।

### Mistake 2: Forgetting Case Sensitivity

**Example:**

```python
text = "Python Python"

print(text.count("python"))
```

**Output:**

```text
0
```

এখানে `"python"` এবং `"Python"` আলাদা হওয়ায় Result `0` হয়েছে।

**Solution:**

```python
text = "Python Python"

print(text.lower().count("python"))
```

**Output:**

```text
2
```

### Mistake 3: Counting Overlapping Substrings

**Example:**

```python
text = "banana"

print(text.count("ana"))
```

**Output:**

```text
1
```

অনেকে মনে করতে পারে Result `2` হবে।

কিন্তু `count()` Overlapping Occurrence গণনা করে না।

### Mistake 4: Using an Incorrect Start and End Index

**Example:**

```python
text = "banana"

print(text.count("a", 2, 5))
```

**Output:**

```text
1
```

এখানে Index `2` থেকে `5`-এর আগ পর্যন্ত Search হয়েছে।

এই অংশটি হলো `"nan"`।

এখানে `"a"` রয়েছে মাত্র ১ বার।

## 15. Practical Examples

### Example 1: Count a Specific Character

```python
text = "programming"

print("Total m:", text.count("m"))
```

**Output:**

```text
Total m: 2
```

### Example 2: Count a Word in a Sentence

```python
sentence = "Python is easy. Python is popular."

print("Python count:", sentence.count("Python"))
```

**Output:**

```text
Python count: 2
```

### Example 3: Count a Character in User Input

```python
text = input("Enter a text: ")

character = input("Enter a character: ")

total = text.count(character)

print("Total occurrences:", total)
```

**Sample Input:**

```text
Enter a text: programming
Enter a character: m
```

**Output:**

```text
Total occurrences: 2
```

### Example 4: Count Vowels in a Word

```python
word = "education"

total = (
    word.count("a") +
    word.count("e") +
    word.count("i") +
    word.count("o") +
    word.count("u")
)

print("Total vowels:", total)
```

**Output:**

```text
Total vowels: 5
```

### Example 5: Count a Substring from a Specific Position

```python
text = "banana"

print(text.count("a", 2))
```

**Output:**

```text
2
```

এখানে Index `2` থেকে শেষ পর্যন্ত `"a"` গণনা করা হয়েছে।

## 16. Important Rules to Remember

1. `count()` method দিয়ে কোনো String-এর মধ্যে Character বা Substring-এর সংখ্যা গণনা করা যায়।
2. এটি একটি Integer Number return করে।
3. Substring না পেলে `0` return করে।
4. এটি সব Non-Overlapping Occurrence গণনা করে।
5. `start` parameter দিয়ে Counting-এর শুরু নির্ধারণ করা যায়।
6. `end` parameter দিয়ে Counting-এর শেষ সীমা নির্ধারণ করা যায়।
7. `end` Index গণনার মধ্যে অন্তর্ভুক্ত হয় না।
8. `count()` method Case-Sensitive।
9. Case-Insensitive Counting করতে `lower()` বা `upper()` ব্যবহার করা যায়।
10. `find()` Index return করে, কিন্তু `count()` মোট সংখ্যা return করে।

## 17. Practice Problems

### Problem 1: Count a Character

নিচের String-এর মধ্যে `"a"` কতবার রয়েছে তা গণনা করো।

```python
text = "banana"
```

**Expected Output:**

```text
3
```

### Problem 2: Count a Substring

নিচের String-এর মধ্যে `"Python"` কতবার রয়েছে তা গণনা করো।

```python
text = "Python is easy. Python is powerful."
```

**Expected Output:**

```text
2
```

### Problem 3: Count a Missing Character

নিচের String-এর মধ্যে `"z"` কতবার রয়েছে তা বের করো।

```python
text = "programming"
```

**Expected Output:**

```text
0
```

### Problem 4: Count with Start Parameter

Index `2` থেকে `"a"` কতবার রয়েছে তা গণনা করো।

```python
text = "banana"
```

**Expected Output:**

```text
2
```

### Problem 5: Count with Start and End

Index `1` থেকে `5`-এর আগ পর্যন্ত `"a"` কতবার রয়েছে তা গণনা করো।

```python
text = "banana"
```

**Expected Output:**

```text
2
```

### Problem 6: Case-Insensitive Counting

নিচের String-এ `"python"` মোট কতবার রয়েছে তা Case-Insensitive ভাবে গণনা করো।

```python
text = "Python python PYTHON"
```

**Expected Output:**

```text
3
```

### Problem 7: Count Vowels

নিচের Word-এর মধ্যে মোট Vowel-এর সংখ্যা বের করো।

```python
word = "education"
```

**Expected Output:**

```text
5
```

### Problem 8: Count with User Input

User-এর কাছ থেকে একটি Text এবং একটি Character নিয়ে Character-টি কতবার রয়েছে তা গণনা করো।

**Sample Input:**

```text
Enter a text: programming
Enter a character: m
```

**Expected Output:**

```text
Total occurrences: 2
```

### Problem 9: Predict the Output

```python
text = "banana"

print(text.count("a"))
print(text.count("na"))
print(text.count("ana"))
print(text.count("z"))
```

**Expected Output:**

```text
3
2
1
0
```

### Problem 10: Predict the Output

```python
text = "Python python PYTHON"

print(text.count("Python"))
print(text.lower().count("python"))
print(text.count("python"))
```

**Expected Output:**

```text
1
3
1
```

## 18. Summary

- `count()` method দিয়ে String-এর মধ্যে কোনো Character বা Substring কতবার রয়েছে তা গণনা করা যায়।
- এটি মোট Occurrence সংখ্যা Integer হিসেবে return করে।
- Substring না পেলে `0` return করে।
- এটি Non-Overlapping Occurrence গণনা করে।
- `start` এবং `end` parameter ব্যবহার করে নির্দিষ্ট অংশে Counting করা যায়।
- `count()` method Case-Sensitive।
- `lower()` বা `upper()` ব্যবহার করে Case-Insensitive Counting করা যায়।
- `find()` প্রথম Occurrence-এর Index return করে, কিন্তু `count()` মোট Occurrence সংখ্যা return করে।

`count()` Python-এর একটি গুরুত্বপূর্ণ String Method, যা Character Counting, Word Counting এবং বিভিন্ন Text Processing-এর কাজে ব্যবহার করা হয়।
