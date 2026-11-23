

# 51. String Comprehensions and Generator Expressions in Python

## 1. Introduction

Python-এ String-এর প্রতিটি Character নিয়ে কাজ করে নতুন List বা String তৈরি করা যায়।

এই কাজ সহজে করার জন্য আমরা ব্যবহার করতে পারি:

1. List Comprehension
2. Generator Expression
3. `join()` Method

**Example:**

একটি String থেকে প্রতিটি Character আলাদা করে একটি List তৈরি করা।

```python
text = "Python"

characters = [char for char in text]

print(characters)
```

**Output:**

```text
['P', 'y', 't', 'h', 'o', 'n']
```

এখানে `for char in text` দিয়ে String-এর প্রতিটি Character নেওয়া হয়েছে এবং List তৈরি করা হয়েছে।

**Important:** Python-এ আলাদা কোনো built-in String Comprehension Syntax নেই। তবে List Comprehension এবং `join()` ব্যবহার করে String Processing খুব সহজে করা যায়।

---

## 2. List Comprehension with Strings

List Comprehension ব্যবহার করে একটি String-এর প্রতিটি Character নিয়ে নতুন List তৈরি করা যায়।

**Syntax:**

```python
new_list = [expression for item in iterable]
```

**Example:**

```python
text = "Masum"

characters = [char for char in text]

print(characters)
```

**Output:**

```text
['M', 'a', 's', 'u', 'm']
```

**Explanation:**

- `for char in text` String-এর প্রতিটি Character নেয়।
- `char` প্রতিটি Character-কে নির্দেশ করে।
- `[char for char in text]` একটি নতুন List তৈরি করে।

---

## 3. Converting Characters into Uppercase

List Comprehension ব্যবহার করে String-এর সব Character Uppercase করা যায়।

**Example:**

```python
text = "python"

result = [char.upper() for char in text]

print(result)
```

**Output:**

```text
['P', 'Y', 'T', 'H', 'O', 'N']
```

**Explanation:**

- Loop দিয়ে প্রতিটি Character নেওয়া হয়।
- `upper()` Character-টিকে Uppercase করে।
- সব Character একটি নতুন List-এ জমা হয়।

---

## 4. Extracting Vowels Using List Comprehension

List Comprehension-এর সাথে `if` ব্যবহার করে String থেকে শুধু Vowels বের করা যায়।

**Example:**

```python
text = "programming"

vowels = [char for char in text if char in "aeiou"]

print(vowels)
```

**Output:**

```text
['o', 'a', 'i']
```

**Explanation:**

1. `for char in text` প্রতিটি Character পরীক্ষা করে।
2. `if char in "aeiou"` দেখে Character-টি Vowel কি না।
3. Vowel হলে সেটি List-এ যোগ হয়।

**Important:** এখানে শুধু ছোট হাতের Vowel পরীক্ষা করা হয়েছে। বড় হাতের Vowel-ও ধরতে চাইলে `text.lower()` ব্যবহার করা যায়।

```python
text = "Python Programming"

vowels = [char for char in text.lower() if char in "aeiou"]

print(vowels)
```

**Output:**

```text
['o', 'o', 'a', 'i']
```

---

## 5. Extracting Consonants Using List Comprehension

Vowel বাদ দিয়ে বাকি Alphabet Character বের করতে List Comprehension ব্যবহার করা যায়।

**Example:**

```python
text = "python"

consonants = [
    char for char in text
    if char not in "aeiou"
]

print(consonants)
```

**Output:**

```text
['p', 'y', 't', 'h', 'n']
```

**Explanation:**

- প্রতিটি Character পরীক্ষা করা হয়।
- `if char not in "aeiou"` দিয়ে Vowel বাদ দেওয়া হয়।
- বাকি Character-গুলো নতুন List-এ রাখা হয়।

**Note:** এই Example-এ ধরে নেওয়া হয়েছে String-এ শুধু ছোট হাতের Alphabet আছে।

---

## 6. Extracting Digits from a String

List Comprehension ব্যবহার করে String থেকে সব Digit বের করা যায়।

**Example:**

```python
text = "Room 205, Floor 3"

numbers = [char for char in text if char.isdigit()]

print(numbers)
```

**Output:**

```text
['2', '0', '5', '3']
```

**Explanation:**

- `isdigit()` পরীক্ষা করে Character-টি Digit কি না।
- Digit হলে সেটি List-এ যোগ হয়।
- ফলে শুধু Digit-গুলো পাওয়া যায়।

---

## 7. Filtering Uppercase Characters

String থেকে শুধু Uppercase Character বের করা যায়।

**Example:**

```python
text = "PyTHon ProGRam"

uppercase = [char for char in text if char.isupper()]

print(uppercase)
```

**Output:**

```text
['P', 'T', 'H', 'G', 'R']
```

**Explanation:**

`isupper()` পরীক্ষা করে কোনো Character বড় হাতের Letter কি না।

---

## 8. Creating a New String Using join()

List Comprehension দিয়ে Character-এর List তৈরি করার পর `join()` ব্যবহার করে আবার String তৈরি করা যায়।

**Example:**

```python
text = "python"

characters = [char.upper() for char in text]

result = "".join(characters)

print(result)
```

**Output:**

```text
PYTHON
```

**Explanation:**

1. List Comprehension প্রতিটি Character Uppercase করে।
2. `characters` List তৈরি হয়।
3. `"".join(characters)` List-এর সব Character একসাথে যুক্ত করে।
4. নতুন String পাওয়া যায়।

**Important:**

- `"".join()` Character-গুলোর মাঝে কোনো Space দেয় না।
- `" ".join()` Character-গুলোর মাঝে Space দেয়।

**Example:**

```python
words = ["Python", "is", "easy"]

result = " ".join(words)

print(result)
```

**Output:**

```text
Python is easy
```

---

## 9. Reversing a String Using List Comprehension

List Comprehension দিয়ে String-এর Character Reverse Order-এ নেওয়া যায়।

**Example:**

```python
text = "Python"

characters = [char for char in text[::-1]]

result = "".join(characters)

print(result)
```

**Output:**

```text
nohtyP
```

**Explanation:**

- `text[::-1]` String-টিকে Reverse করে।
- List Comprehension Character-গুলো List-এ রাখে।
- `join()` Character-গুলো যুক্ত করে নতুন String তৈরি করে।

**Note:** শুধু String Reverse করার জন্য `text[::-1]` ব্যবহার করাই সহজ।

---

## 10. Using if-else in List Comprehension

List Comprehension-এ `if-else` ব্যবহার করে Condition অনুযায়ী Character পরিবর্তন করা যায়।

**Syntax:**

```python
new_list = [value_if_true if condition else value_if_false for item in iterable]
```

**Example:**

```python
text = "python"

result = [
    char.upper() if char in "aeiou" else char
    for char in text
]

print(result)
```

**Output:**

```text
['p', 'Y', 't', 'h', 'O', 'n']
```

**Explanation:**

- Character Vowel হলে Uppercase হবে।
- Vowel না হলে আগের মতোই থাকবে।
- সব Character নিয়ে নতুন List তৈরি হবে।

---

## 11. Introduction to Generator Expression

Generator Expression হলো Python-এর একটি সংক্ষিপ্ত পদ্ধতি, যার মাধ্যমে একবারে সব Value তৈরি না করে প্রয়োজন অনুযায়ী একটি করে Value পাওয়া যায়।

এটি দেখতে List Comprehension-এর মতো, তবে এখানে Square Bracket `[]`-এর পরিবর্তে Parentheses `()` ব্যবহার করা হয়।

**Syntax:**

```python
generator = (expression for item in iterable)
```

**Example:**

```python
text = "Python"

characters = (char for char in text)

print(characters)
```

**Output:**

```text
<generator object <genexpr> at ...>
```

**Explanation:**

- `(char for char in text)` একটি Generator তৈরি করে।
- এটি সরাসরি List তৈরি করে না।
- প্রয়োজন অনুযায়ী `next()` দিয়ে একবারে একটি Value পাওয়া যায়।

**Note:** Generator-এর Memory Address বা Output-এর নির্দিষ্ট অংশ Python-এর Version ও Environment অনুযায়ী পরিবর্তিত হতে পারে।

---

## 12. Accessing Generator Values Using next()

`next()` Function ব্যবহার করে Generator থেকে একবারে একটি Value নেওয়া যায়।

**Example:**

```python
text = "Python"

characters = (char for char in text)

print(next(characters))
print(next(characters))
print(next(characters))
```

**Output:**

```text
P
y
t
```

**Explanation:**

- প্রথম `next()` প্রথম Character দেয়।
- দ্বিতীয় `next()` দ্বিতীয় Character দেয়।
- তৃতীয় `next()` তৃতীয় Character দেয়।

**Important:** Generator-এর সব Value শেষ হয়ে গেলে আবার `next()` ব্যবহার করলে `StopIteration` Error হয়।

---

## 13. Using Generator Expression with a for Loop

Generator Expression-এর সব Value একটি Loop দিয়ে ব্যবহার করা যায়।

**Example:**

```python
text = "Python"

characters = (char.upper() for char in text)

for char in characters:
    print(char)
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

**Explanation:**

- Generator প্রতিবার একটি করে Uppercase Character তৈরি করে।
- `for` Loop সেই Character গ্রহণ করে।
- সব Character শেষ হলে Loop বন্ধ হয়ে যায়।

---

## 14. List Comprehension vs Generator Expression

List Comprehension এবং Generator Expression-এর মধ্যে কিছু গুরুত্বপূর্ণ পার্থক্য রয়েছে।

| List Comprehension | Generator Expression |
|---|---|
| `[]` ব্যবহার করে | `()` ব্যবহার করে |
| সম্পূর্ণ List তৈরি করে | প্রয়োজন অনুযায়ী Value তৈরি করে |
| সাধারণত বেশি Memory ব্যবহার করে | সাধারণত কম Memory ব্যবহার করে |
| একাধিকবার ব্যবহার করা যায় | একবার শেষ হলে আবার ব্যবহার করা যায় না |
| List Return করে | Generator Object Return করে |

**Example:**

```python
text = "Python"

list_result = [char for char in text]

generator_result = (char for char in text)

print(list_result)
print(next(generator_result))
```

**Output:**

```text
['P', 'y', 't', 'h', 'o', 'n']
P
```

---

## 15. Practical Example: Extracting All Vowels

একটি String থেকে সব Vowel বের করে নতুন String তৈরি করা।

**Example:**

```python
text = "I love Python"

vowels = [char for char in text.lower() if char in "aeiou"]

result = "".join(vowels)

print(result)
```

**Output:**

```text
ioeo
```

**Explanation:**

1. `lower()` সব Character ছোট হাতের করে।
2. List Comprehension শুধু Vowel নির্বাচন করে।
3. `join()` Vowel-গুলো একসাথে যুক্ত করে।
4. একটি নতুন String তৈরি হয়।

---

## 16. Common Mistakes

### Mistake 1: List Comprehension-এর Syntax ভুল করা

**Wrong:**

```python
text = "Python"

result = [for char in text]
```

**Error:** `SyntaxError`

**Correct:**

```python
text = "Python"

result = [char for char in text]

print(result)
```

**Output:**

```text
['P', 'y', 't', 'h', 'o', 'n']
```

### Mistake 2: join() ব্যবহার করার সময় ভুল Separator দেওয়া

```python
characters = ["P", "y", "t", "h", "o", "n"]

result = "-".join(characters)

print(result)
```

**Output:**

```text
P-y-t-h-o-n
```

**Explanation:** `"-".join()` প্রতিটি Character-এর মাঝে Hyphen যোগ করে। কোনো Separator না চাইলে `"".join()` ব্যবহার করতে হবে।

### Mistake 3: Generator-কে List মনে করা

```python
text = "Python"

result = (char for char in text)

print(result[0])
```

**Error:**

```text
TypeError: 'generator' object is not subscriptable
```

**কারণ:** Generator সরাসরি Indexing Support করে না।

**Correct:**

```python
text = "Python"

result = (char for char in text)

print(next(result))
```

**Output:**

```text
P
```

### Mistake 4: Generator একবার ব্যবহার করার পর আবার ব্যবহার করা

```python
text = "ABC"

result = (char for char in text)

for char in result:
    print(char)

for char in result:
    print(char)
```

**Output:**

```text
A
B
C
```

**কারণ:** প্রথম Loop-এই Generator-এর সব Value শেষ হয়ে যায়। তাই দ্বিতীয় Loop-এ কিছু পাওয়া যায় না।

---

## 17. Practice Exercises

### Exercise 1: Convert Every Character into Uppercase

**Solution:**

```python
text = "python"

result = [char.upper() for char in text]

print(result)
```

**Output:**

```text
['P', 'Y', 'T', 'H', 'O', 'N']
```

### Exercise 2: Extract All Digits

**Solution:**

```python
text = "I have 25 books"

result = [char for char in text if char.isdigit()]

print(result)
```

**Output:**

```text
['2', '5']
```

### Exercise 3: Extract Only Vowels

**Solution:**

```python
text = "education"

result = [char for char in text if char in "aeiou"]

print(result)
```

**Output:**

```text
['e', 'u', 'a', 'i', 'o']
```

### Exercise 4: Create a New String Using join()

**Solution:**

```python
text = "hello"

result = "".join([char.upper() for char in text])

print(result)
```

**Output:**

```text
HELLO
```

### Exercise 5: Create a Generator and Print Its Values

**Solution:**

```python
text = "ABC"

result = (char for char in text)

for char in result:
    print(char)
```

**Output:**

```text
A
B
C
```

---

## 18. Chapter Summary

এই Topic-এ আমরা শিখেছি:

1. String থেকে List তৈরি করা।
2. List Comprehension ব্যবহার করা।
3. Character Uppercase করা।
4. Vowel এবং Consonant Extract করা।
5. String থেকে Digit বের করা।
6. `join()` দিয়ে নতুন String তৈরি করা।
7. Generator Expression ব্যবহার করা।
8. `next()` দিয়ে Generator থেকে Value নেওয়া।
9. List Comprehension এবং Generator Expression-এর পার্থক্য।

### Important Syntax

| Syntax | কাজ |
|---|---|
| `[char for char in text]` | Character-এর List তৈরি করে |
| `[char for char in text if condition]` | Condition অনুযায়ী Character নেয় |
| `(char for char in text)` | Generator তৈরি করে |
| `next(generator)` | পরবর্তী Value দেয় |
| `"".join(list)` | List-এর Character যুক্ত করে String তৈরি করে |

---

## 19. Self-Assessment Checklist

- [ ] List Comprehension কী বুঝি।
- [ ] String থেকে Character-এর List তৈরি করতে পারি।
- [ ] List Comprehension দিয়ে Vowel Extract করতে পারি।
- [ ] String থেকে Digit বের করতে পারি।
- [ ] `join()` ব্যবহার করে নতুন String তৈরি করতে পারি।
- [ ] Generator Expression তৈরি করতে পারি।
- [ ] `next()` ব্যবহার করতে পারি।
- [ ] List Comprehension ও Generator Expression-এর পার্থক্য বুঝি।

---

## 20. Next Topic

**52. Regular Expressions Introduction in Python**

পরবর্তী Topic-এ আমরা শিখব:

- Regular Expression (RegEx) কী।
- `re` Module-এর Introduction।
- `re.search()` ব্যবহার।
- `re.findall()` ব্যবহার।
- `re.match()` ব্যবহার।
- Pattern দিয়ে Text খুঁজে বের করা।
- Basic Text Matching Examples।

