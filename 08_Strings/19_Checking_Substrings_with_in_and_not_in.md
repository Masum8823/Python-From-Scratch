# Checking Substrings with in and not in in Python

## 1. What is a Substring?

একটি String-এর মধ্যে থাকা ছোট String বা character-এর অংশকে **Substring** বলা হয়।

সহজভাবে, একটি String-এর ভেতরে থাকা অন্য কোনো String বা Character হলো Substring।

**Example:**

```python
text = "I love Python Programming"
```

এখানে:

- `"Python"` একটি Substring।
- `"love"` একটি Substring।
- `"Programming"` একটি Substring।
- `"Java"` এই String-এর Substring নয়।

Python-এ কোনো String-এর মধ্যে নির্দিষ্ট Substring আছে কি না পরীক্ষা করার জন্য `in` এবং `not in` operator ব্যবহার করা হয়।

## 2. Checking Substrings Using in Operator

Python-এ `in` operator ব্যবহার করে কোনো String-এর মধ্যে নির্দিষ্ট Character বা Substring আছে কি না পরীক্ষা করা যায়।

যদি Substring পাওয়া যায়, তাহলে `True` return করে। অন্যথায় `False` return করে।

**Syntax:**

```python
substring in string
```

এখানে:

- `substring` → যে Text খুঁজতে চাই।
- `string` → যে String-এর মধ্যে খুঁজব।

**Example:**

```python
text = "I love Python"

result = "Python" in text

print(result)
```

**Output:**

```text
True
```

**ব্যাখ্যা:**

এখানে `"Python"` String-টি `text`-এর মধ্যে রয়েছে।

তাই `in` operator `True` return করেছে।

## 3. Checking a Character Using in Operator

শুধু সম্পূর্ণ Word নয়, কোনো একটি Character আছে কি না তাও পরীক্ষা করা যায়।

**Example:**

```python
text = "Python"

print("P" in text)
print("y" in text)
print("z" in text)
```

**Output:**

```text
True
True
False
```

এখানে:

- `"P"` String-এর মধ্যে রয়েছে।
- `"y"` String-এর মধ্যে রয়েছে।
- `"z"` String-এর মধ্যে নেই।

তাই শেষের Result `False` হয়েছে।

## 4. Checking Multiple Substrings

একই String-এর মধ্যে একাধিক Substring পরীক্ষা করা যায়।

**Example:**

```python
text = "I am learning Python Programming"

print("Python" in text)
print("learning" in text)
print("Java" in text)
print("Programming" in text)
```

**Output:**

```text
True
True
False
True
```

এখানে প্রতিটি Substring আলাদাভাবে পরীক্ষা করা হয়েছে।

যে Substring পাওয়া গেছে তার জন্য `True` এবং যেটি পাওয়া যায়নি তার জন্য `False` এসেছে।

## 5. Checking Substrings Using not in Operator

Python-এ `not in` operator ব্যবহার করে কোনো Substring একটি String-এর মধ্যে নেই কি না পরীক্ষা করা যায়।

যদি Substring পাওয়া না যায়, তাহলে `True` return করে। অন্যথায় `False` return করে।

**Syntax:**

```python
substring not in string
```

**Example:**

```python
text = "I love Python"

result = "Java" not in text

print(result)
```

**Output:**

```text
True
```

**ব্যাখ্যা:**

এখানে `"Java"` String-টি `text`-এর মধ্যে নেই।

তাই `not in` operator `True` return করেছে।

## 6. Difference Between in and not in

`in` এবং `not in` দুটিই String-এর মধ্যে Substring খুঁজতে ব্যবহার করা হয়। তবে এদের Result বিপরীত।

| in Operator | not in Operator |
|---|---|
| Substring আছে কি না পরীক্ষা করে। | Substring নেই কি না পরীক্ষা করে। |
| পাওয়া গেলে `True` দেয়। | না পাওয়া গেলে `True` দেয়। |
| না পাওয়া গেলে `False` দেয়। | পাওয়া গেলে `False` দেয়। |
| `"Python" in text` | `"Python" not in text` |

**Example:**

```python
text = "I love Python"

print("Python" in text)
print("Python" not in text)
```

**Output:**

```text
True
False
```

এখানে `"Python"` String-এর মধ্যে রয়েছে।

তাই `in` এর Result `True` এবং `not in` এর Result `False` হয়েছে।

## 7. Case Sensitivity in Substring Checking

Python-এ `in` এবং `not in` operator Case-Sensitive।

অর্থাৎ, Uppercase এবং Lowercase Character-কে আলাদা হিসেবে বিবেচনা করা হয়।

**Example:**

```python
text = "I Love Python"

print("Python" in text)
print("python" in text)
print("PYTHON" in text)
```

**Output:**

```text
True
False
False
```

**ব্যাখ্যা:**

এখানে:

- `"Python"` এবং `"python"` এক নয়।
- `"PYTHON"` এবং `"Python"` এক নয়।

কারণ Python-এ Capital এবং Small Letter আলাদা Character হিসেবে বিবেচিত হয়।

**Solution: Using lower()**

Case-Sensitive সমস্যা এড়াতে উভয় String-কে `lower()` ব্যবহার করে Lowercase করা যায়।

```python
text = "I Love Python"

print("python" in text.lower())
```

**Output:**

```text
True
```

এখানে `text.lower()` পুরো String-কে Lowercase করেছে। তাই `"python"` খুঁজে পাওয়া গেছে।

## 8. Using in Operator with if-else

`in` এবং `not in` operator Conditional Statement-এর সঙ্গেও ব্যবহার করা যায়।

এর মাধ্যমে কোনো String-এর মধ্যে নির্দিষ্ট Word আছে কি না পরীক্ষা করে সিদ্ধান্ত নেওয়া যায়।

**Example:**

```python
text = "I love Python Programming"

if "Python" in text:
    print("Python is available.")
else:
    print("Python is not available.")
```

**Output:**

```text
Python is available.
```

**ব্যাখ্যা:**

- প্রথমে `"Python"` String-এর মধ্যে আছে কি না পরীক্ষা করা হয়েছে।
- Substring পাওয়া যাওয়ায় Condition `True` হয়েছে।
- তাই `if` block-এর Statement execute হয়েছে।

## 9. Checking Substrings with User Input

`input()` ব্যবহার করে User-এর কাছ থেকে কোনো Word নিয়ে সেটি একটি String-এর মধ্যে আছে কি না পরীক্ষা করা যায়।

**Example:**

```python
text = "I am learning Python Programming"

word = input("Enter a word to search: ")

if word in text:
    print("Word found!")
else:
    print("Word not found!")
```

**Sample Input 1:**

```text
Enter a word to search: Python
```

**Output 1:**

```text
Word found!
```

**Sample Input 2:**

```text
Enter a word to search: Java
```

**Output 2:**

```text
Word not found!
```

এখানে User-এর দেওয়া Word `in` operator দিয়ে মূল String-এর মধ্যে পরীক্ষা করা হয়েছে।

## 10. Checking Substrings in a Case-Insensitive Way

আগেই জেনেছি, Python-এর `in` operator Case-Sensitive।

তবে `lower()` বা `upper()` ব্যবহার করে Case-Insensitive Checking করা যায়।

**Example:**

```python
text = "I Love Python Programming"

word = input("Enter a word: ")

if word.lower() in text.lower():
    print("Word found!")
else:
    print("Word not found!")
```

**Sample Input:**

```text
Enter a word: python
```

**Output:**

```text
Word found!
```

**ব্যাখ্যা:**

- `word.lower()` User-এর Input-কে Lowercase করেছে।
- `text.lower()` মূল String-কে Lowercase করেছে।
- এরপর `in` operator দিয়ে দুটি String-এর মধ্যে Search করা হয়েছে।

তাই Capital বা Small Letter যেভাবেই Input দেওয়া হোক, Substring খুঁজে পাওয়া সম্ভব।

## 11. Checking Whether a String Contains a Specific Character

কোনো String-এর মধ্যে নির্দিষ্ট Character আছে কি না পরীক্ষা করতে `in` এবং `not in` ব্যবহার করা যায়।

**Example:**

```python
email = "masum@gmail.com"

if "@" in email:
    print("Valid email format.")
else:
    print("Invalid email format.")
```

**Output:**

```text
Valid email format.
```

এখানে Email-এর মধ্যে `"@"` Character আছে কি না পরীক্ষা করা হয়েছে।

মনে রাখবে, শুধু `"@"` থাকলেই কোনো Email সম্পূর্ণ Valid প্রমাণিত হয় না। এটি শুধু একটি সাধারণ Character Checking Example।

## 12. Using in and not in with Empty Strings

Python-এ Empty String (`""`) যেকোনো String-এর মধ্যে পাওয়া যায়।

তাই Empty String পরীক্ষা করলে `in` এবং `not in`-এর Result একটু আলাদা হবে।

**Example:**

```python
text = "Python"

print("" in text)
print("" not in text)
```

**Output:**

```text
True
False
```

**ব্যাখ্যা:**

- `"" in text` এর Result `True`।
- `"" not in text` এর Result `False`।

কারণ Empty String প্রতিটি String-এর মধ্যে উপস্থিত হিসেবে বিবেচিত হয়।

## 13. Common Mistakes in Substring Checking

### Mistake 1: Case-Sensitive Checking

**Incorrect Expectation:**

```python
text = "I Love Python"

print("python" in text)
```

**Output:**

```text
False
```

অনেকে মনে করতে পারে `"python"` এবং `"Python"` একই। কিন্তু Python-এ Case-Sensitive Checking হয়।

**Solution:**

```python
text = "I Love Python"

print("python" in text.lower())
```

**Output:**

```text
True
```

### Mistake 2: Confusing in with Assignment Operator

`in` একটি Membership Operator। এটি কোনো Variable-এ Value Assign করে না।

**Incorrect Code:**

```python
text = "Python"

result = "Python" = text
```

**Error:**

```text
SyntaxError
```

**Solution:**

```python
text = "Python"

result = "Python" in text

print(result)
```

**Output:**

```text
True
```

### Mistake 3: Expecting not in to Find a Substring

**Example:**

```python
text = "I love Python"

print("Python" not in text)
```

**Output:**

```text
False
```

এখানে `"Python"` আছে। তাই `not in` এর Result `False` হয়েছে।

মনে রাখবে, `not in` কোনো Substring খুঁজে না পেলে `True` দেয়।

## 14. Practical Examples

### Example 1: Checking Whether a Word Exists

```python
sentence = "Python is easy to learn"

if "easy" in sentence:
    print("The word exists.")
else:
    print("The word does not exist.")
```

**Output:**

```text
The word exists.
```

### Example 2: Checking Whether a Sentence Contains Python

```python
sentence = input("Enter a sentence: ")

if "Python" in sentence:
    print("This sentence contains Python.")
else:
    print("This sentence does not contain Python.")
```

**Sample Input:**

```text
Enter a sentence: I am learning Python
```

**Output:**

```text
This sentence contains Python.
```

### Example 3: Checking a Vowel

```python
letter = input("Enter a letter: ")

if letter.lower() in "aeiou":
    print("It is a vowel.")
else:
    print("It is not a vowel.")
```

**Sample Input:**

```text
Enter a letter: A
```

**Output:**

```text
It is a vowel.
```

এখানে `lower()` ব্যবহার করে Capital Letter-কে Lowercase করা হয়েছে।

### Example 4: Checking Whether a Word is Missing

```python
text = "I am learning Python"

if "Java" not in text:
    print("Java is not present.")
else:
    print("Java is present.")
```

**Output:**

```text
Java is not present.
```

### Example 5: Checking Multiple Words

```python
text = "I love learning Python"

if "Python" in text and "learning" in text:
    print("Both words are present.")
else:
    print("One or both words are missing.")
```

**Output:**

```text
Both words are present.
```

এখানে `and` ব্যবহার করে দুটি Condition একসঙ্গে পরীক্ষা করা হয়েছে।

## 15. Important Rules to Remember

1. Substring হলো একটি String-এর মধ্যে থাকা ছোট String বা Character।
2. `in` operator দিয়ে Substring আছে কি না পরীক্ষা করা যায়।
3. Substring পাওয়া গেলে `in` operator `True` return করে।
4. `not in` operator দিয়ে Substring নেই কি না পরীক্ষা করা যায়।
5. Substring না পাওয়া গেলে `not in` operator `True` return করে।
6. `in` এবং `not in` বিপরীত Result দেয়।
7. Python-এ Substring Checking Case-Sensitive।
8. `lower()` বা `upper()` ব্যবহার করে Case-Insensitive Checking করা যায়।
9. `in` এবং `not in` Conditional Statement-এর সঙ্গে ব্যবহার করা যায়।
10. Empty String `""` যেকোনো String-এর মধ্যে পাওয়া যায়।

## 16. Practice Problems

### Problem 1: Check a Substring

নিচের String-এর মধ্যে `"Python"` আছে কি না পরীক্ষা করো।

```python
text = "I love Python"
```

**Expected Output:**

```text
True
```

### Problem 2: Use not in

নিচের String-এর মধ্যে `"Java"` নেই কি না পরীক্ষা করো।

```python
text = "I am learning Python"
```

**Expected Output:**

```text
True
```

### Problem 3: Check a Character

নিচের String-এর মধ্যে `"@"` Character আছে কি না পরীক্ষা করো।

```python
email = "masum@gmail.com"
```

**Expected Output:**

```text
True
```

### Problem 4: Case-Insensitive Checking

`lower()` ব্যবহার করে নিচের String-এর মধ্যে `"python"` আছে কি না পরীক্ষা করো।

```python
text = "I Love Python Programming"
```

**Expected Output:**

```text
True
```

### Problem 5: Use if-else

একটি String-এর মধ্যে `"Bangladesh"` আছে কি না পরীক্ষা করো। থাকলে `"Word Found"` এবং না থাকলে `"Word Not Found"` print করো।

```python
text = "I live in Bangladesh"
```

**Expected Output:**

```text
Word Found
```

### Problem 6: Take User Input

User-এর কাছ থেকে একটি Word নিয়ে নিচের String-এর মধ্যে সেটি আছে কি না পরীক্ষা করো।

```python
text = "Python is a popular programming language"
```

**Sample Input:**

```text
programming
```

**Expected Output:**

```text
Word found!
```

### Problem 7: Predict the Output

```python
text = "Python Programming"

print("Python" in text)
print("python" in text)
print("Java" not in text)
print("Program" in text)
print("" in text)
```

**Expected Output:**

```text
True
False
True
True
True
```

## 17. Summary

- Substring হলো একটি String-এর মধ্যে থাকা ছোট String বা Character।
- `in` operator দিয়ে কোনো Substring আছে কি না পরীক্ষা করা যায়।
- `not in` operator দিয়ে কোনো Substring নেই কি না পরীক্ষা করা যায়।
- `in` এবং `not in` Boolean Result (`True` বা `False`) return করে।
- Python-এ Substring Checking Case-Sensitive।
- `lower()` এবং `upper()` ব্যবহার করে Case-Insensitive Checking করা যায়।
- Conditional Statement-এর সঙ্গে `in` এবং `not in` ব্যবহার করা যায়।
- Empty String প্রতিটি String-এর মধ্যে পাওয়া যায়।

`in` এবং `not in` Python-এর গুরুত্বপূর্ণ Membership Operator, যা Text Searching, Word Checking এবং বিভিন্ন String Validation-এর কাজে ব্যবহার করা হয়।