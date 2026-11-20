# String Repetition in Python

## 1. What is String Repetition?

Python-এ কোনো String-কে একাধিকবার পুনরাবৃত্তি করে একটি নতুন String তৈরি করাকে **String Repetition** বলা হয়।

String Repetition করার জন্য Python-এ `*` (Multiplication) operator ব্যবহার করা হয়।

সহজভাবে, একটি String-কে নির্দিষ্ট সংখ্যক বার repeat করাই হলো String Repetition।

**Example:**

```python
text = "Python "

result = text * 3

print(result)
```

**Output:**

```text
Python Python Python
```

**ব্যাখ্যা:**

এখানে:

- `text` একটি String variable।
- `* 3` ব্যবহার করে String-টিকে ৩ বার repeat করা হয়েছে।
- ফলে একটি নতুন String তৈরি হয়েছে।

## 2. String Repetition Using * Operator

Python-এ `*` operator ব্যবহার করে একটি String-কে নির্দিষ্ট সংখ্যক বার repeat করা যায়।

**Syntax:**

```python
string * number
```

এখানে:

- `string` → যে String-টি repeat করতে চাই।
- `number` → String-টি কতবার repeat হবে।

**Example:**

```python
text = "Hello"

result = text * 3

print(result)
```

**Output:**

```text
HelloHelloHello
```

এখানে `"Hello"` String-টি ৩ বার repeat হয়েছে।

## 3. Adding Spaces During String Repetition

String-এর মধ্যে space থাকলে repetition-এর সময় সেই space-ও repeat হয়।

**Example 1:**

```python
text = "Hello "

result = text * 3

print(result)
```

**Output:**

```text
Hello Hello Hello
```

এখানে `"Hello "` String-এর শেষে একটি space রয়েছে। তাই প্রতিবার repeat হওয়ার পর একটি space পাওয়া যাচ্ছে।

**Example 2:**

```python
text = "Python"

result = (text + " ") * 3

print(result)
```

**Output:**

```text
Python Python Python
```

এখানে প্রথমে `"Python"`-এর সঙ্গে একটি space যুক্ত করা হয়েছে। এরপর পুরো String-টি ৩ বার repeat করা হয়েছে।

## 4. Repeating Strings with Different Numbers

String-এর সঙ্গে বিভিন্ন Integer ব্যবহার করে বিভিন্ন সংখ্যক বার repetition করা যায়।

**Example:**

```python
text = "Hi "

print(text * 1)
print(text * 2)
print(text * 3)
print(text * 4)
```

**Output:**

```text
Hi
Hi Hi
Hi Hi Hi
Hi Hi Hi Hi
```

এখানে Integer-এর মান অনুযায়ী String-এর repetition হয়েছে।

## 5. Repeating Strings Using Variables

String এবং repetition number উভয়ই Variable-এর মধ্যে রাখা যায়।

**Example:**

```python
text = "Python "
count = 4

result = text * count

print(result)
```

**Output:**

```text
Python Python Python Python
```

**ব্যাখ্যা:**

- `text`-এ `"Python "` সংরক্ষণ করা হয়েছে।
- `count`-এ repetition-এর সংখ্যা `4` রাখা হয়েছে।
- `text * count` ব্যবহার করে String-টি ৪ বার repeat করা হয়েছে।

## 6. String Repetition with User Input

`input()` ব্যবহার করে User-এর কাছ থেকে String এবং repetition number নেওয়া যায়।

**Example:**

```python
text = input("Enter a word: ")
count = int(input("How many times to repeat? "))

result = text * count

print("Result:", result)
```

**Sample Input:**

```text
Enter a word: Python
How many times to repeat? 3
```

**Output:**

```text
Result: PythonPythonPython
```

**ব্যাখ্যা:**

- `input()` ব্যবহার করে একটি Word নেওয়া হয়েছে।
- দ্বিতীয় `input()` থেকে repetition number নেওয়া হয়েছে।
- `int()` ব্যবহার করে সংখ্যাটিকে Integer-এ convert করা হয়েছে।
- এরপর `*` operator দিয়ে String repeat করা হয়েছে।

## 7. String Repetition with Zero and Negative Numbers

String Repetition করার সময় Zero এবং Negative Number ব্যবহার করলে কী হয়, তা জানা গুরুত্বপূর্ণ।

**Example 1: Repetition with Zero**

```python
text = "Python"

result = text * 0

print(result)
```

**Output:**

```text

```

এখানে কোনো Output দেখা যাবে না, কারণ String-টি ০ বার repeat হয়েছে। ফলে একটি Empty String তৈরি হয়েছে।

**Example 2: Repetition with Negative Number**

```python
text = "Python"

result = text * -3

print(result)
```

**Output:**

```text

```

এখানেও কোনো Output দেখা যাবে না।

Python-এ Negative Number দিয়ে String repeat করলে Empty String পাওয়া যায়।

**Important:**

- Positive Number → String নির্দিষ্ট সংখ্যক বার repeat হয়।
- Zero → Empty String পাওয়া যায়।
- Negative Number → Empty String পাওয়া যায়।

## 8. String Repetition Using *= Operator

Python-এ `*=` assignment operator ব্যবহার করেও String Repetition করা যায়।

এটি মূলত একটি String-কে নির্দিষ্ট সংখ্যক বার repeat করে Variable-এ নতুন ফলাফল assign করে।

**Example:**

```python
text = "Hello "

text *= 3

print(text)
```

**Output:**

```text
Hello Hello Hello
```

**ব্যাখ্যা:**

নিচের দুটি statement একই ধরনের কাজ করে:

```python
text = text * 3
```

```python
text *= 3
```

দুটিই আগের String-টিকে ৩ বার repeat করে Variable-এ নতুন ফলাফল assign করে।

মনে রাখবে, String immutable। তাই `*=` ব্যবহার করলেও পুরোনো String object পরিবর্তন হয় না; নতুন String তৈরি হয়ে Variable-এ assign হয়।

## 9. Difference Between String Concatenation and String Repetition

String Concatenation এবং String Repetition দুটিই String-এর গুরুত্বপূর্ণ operation। তবে এদের কাজ আলাদা।

| String Concatenation | String Repetition |
|---|---|
| একাধিক String যুক্ত করে। | একটি String বারবার repeat করে। |
| `+` operator ব্যবহার করে। | `*` operator ব্যবহার করে। |
| `str1 + str2` | `str * number` |
| একাধিক String যুক্ত করতে ব্যবহৃত হয়। | একই String একাধিকবার তৈরি করতে ব্যবহৃত হয়। |

**Example:**

```python
# String Concatenation

text1 = "Hello"
text2 = "World"

print(text1 + " " + text2)


# String Repetition

text = "Python "

print(text * 3)
```

**Output:**

```text
Hello World
Python Python Python
```

## 10. String Repetition with Different Data Types

String Repetition করার সময় একটি গুরুত্বপূর্ণ বিষয় মনে রাখতে হবে।

Python-এ `*` operator ব্যবহার করে String-এর সঙ্গে Integer যুক্ত করে Repetition করা যায়।

তবে String-এর সঙ্গে Float বা অন্য String ব্যবহার করে সরাসরি Repetition করা যায় না।

**Incorrect Example 1: Using Float**

```python
text = "Python"

result = text * 2.5

print(result)
```

**Output:**

```text
TypeError: can't multiply sequence by non-int of type 'float'
```

এখানে Float `2.5` ব্যবহার করায় `TypeError` হয়েছে।

**Incorrect Example 2: Using Another String**

```python
text = "Hello"

result = text * "3"

print(result)
```

**Output:**

```text
TypeError: can't multiply sequence by non-int of type 'str'
```

এখানেও `TypeError` হয়েছে, কারণ Repetition-এর জন্য Integer প্রয়োজন।

**Correct Example:**

```python
text = "Python"
count = 3

result = text * count

print(result)
```

**Output:**

```text
PythonPythonPython
```

## 11. Practical Examples

### Example 1: Printing a Line Using Repetition

```python
line = "-" * 20

print(line)
```

**Output:**

```text
--------------------
```

এখানে `"-"` character-টি ২০ বার repeat করে একটি Line তৈরি করা হয়েছে।

### Example 2: Creating a Simple Pattern

```python
print("*" * 5)
print("*" * 10)
print("*" * 15)
```

**Output:**

```text
*****
**********
***************
```

এখানে `*` character ব্যবহার করে বিভিন্ন দৈর্ঘ্যের Pattern তৈরি করা হয়েছে।

### Example 3: Creating a Welcome Message

```python
message = "Welcome! "

result = message * 3

print(result)
```

**Output:**

```text
Welcome! Welcome! Welcome! 
```

এখানে একই Welcome Message তিনবার repeat করা হয়েছে।

### Example 4: Creating a Box Border

```python
border = "=" * 25

print(border)
print("Python Programming")
print(border)
```

**Output:**

```text
=========================
Python Programming
=========================
```

এখানে String Repetition ব্যবহার করে একটি সাধারণ Border তৈরি করা হয়েছে।

### Example 5: Repeating a Word Using User Input

```python
word = input("Enter a word: ")
number = int(input("Enter repetition number: "))

print(word * number)
```

**Sample Input:**

```text
Enter a word: Hello
Enter repetition number: 4
```

**Output:**

```text
HelloHelloHelloHello
```

## 12. Common Mistakes in String Repetition

### Mistake 1: Using Float Instead of Integer

**Incorrect Code:**

```python
text = "Hello"

print(text * 2.5)
```

**Error:**

```text
TypeError: can't multiply sequence by non-int of type 'float'
```

**Solution:**

```python
text = "Hello"

print(text * 2)
```

**Output:**

```text
HelloHello
```

Repetition-এর জন্য Integer ব্যবহার করতে হবে।

### Mistake 2: Using String Instead of Integer

**Incorrect Code:**

```python
text = "Python"

print(text * "3")
```

**Error:**

```text
TypeError: can't multiply sequence by non-int of type 'str'
```

**Solution:**

```python
text = "Python"
count = 3

print(text * count)
```

**Output:**

```text
PythonPythonPython
```

এখানে `"3"`-এর পরিবর্তে Integer `3` ব্যবহার করা হয়েছে।

### Mistake 3: Forgetting Spaces

**Incorrect Code:**

```python
text = "Hello"

print(text * 3)
```

**Output:**

```text
HelloHelloHello
```

**Solution:**

```python
text = "Hello "

print(text * 3)
```

**Output:**

```text
Hello Hello Hello 
```

String-এর মধ্যে space রাখলে Repetition-এর সময়ও space পাওয়া যায়।

### Mistake 4: Using the Wrong Operator

String Concatenation এবং String Repetition-এর operator এক নয়।

**Example:**

```python
text = "Python"

print(text + "3")
print(text * 3)
```

**Output:**

```text
Python3
PythonPythonPython
```

এখানে `+` দিয়ে String যুক্ত হয়েছে এবং `*` দিয়ে String repeat হয়েছে।

## 13. Important Rules to Remember

1. String Repetition অর্থ একটি String-কে একাধিকবার repeat করা।
2. String Repetition-এর জন্য `*` operator ব্যবহার করা হয়।
3. Repetition-এর জন্য Integer ব্যবহার করতে হয়।
4. `string * number` এবং `number * string` একই ফলাফল দেয়।
5. Zero দিয়ে String repeat করলে Empty String পাওয়া যায়।
6. Negative Number দিয়ে String repeat করলেও Empty String পাওয়া যায়।
7. Float বা String দিয়ে সরাসরি Repetition করা যায় না।
8. `*=` operator দিয়েও String Repetition করা যায়।
9. String-এর মধ্যে থাকা Space-ও Repetition-এর সময় repeat হয়।
10. String immutable হওয়ায় Repetition নতুন String তৈরি করে।

## 14. Practice Problems

### Problem 1: Repeat a String

নিচের String-টি ৩ বার repeat করো।

```python
text = "Python"
```

**Expected Output:**

```text
PythonPythonPython
```

### Problem 2: Repeat with Spaces

নিচের String-টি ৪ বার repeat করো এবং প্রতিটি Word-এর মাঝে একটি Space রাখো।

```python
text = "Hello "
```

**Expected Output:**

```text
Hello Hello Hello Hello 
```

### Problem 3: Use a Variable

একটি String এবং একটি Integer Variable ব্যবহার করে String-টিকে ৫ বার repeat করো।

```python
text = "Hi "
count = 5
```

**Expected Output:**

```text
Hi Hi Hi Hi Hi 
```

### Problem 4: Use *= Operator

নিচের String-টিকে `*=` operator ব্যবহার করে ৩ বার repeat করো।

```python
text = "Python "
```

**Expected Output:**

```text
Python Python Python 
```

### Problem 5: Repetition with Zero

নিচের Code-এর Output কী হবে?

```python
text = "Hello"

print(text * 0)
```

**Expected Output:**

```text

```

### Problem 6: Create a Pattern

String Repetition ব্যবহার করে নিচের Pattern তৈরি করো।

**Expected Output:**

```text
*****
**********
***************
```

### Problem 7: Predict the Output

```python
text = "Hi"

result = text * 2 + " Python " * 2

print(result)
```

**Expected Output:**

```text
HiHi Python  Python 
```

## 15. Summary

- String Repetition হলো একটি String-কে একাধিকবার repeat করা।
- `*` operator দিয়ে String Repetition করা যায়।
- `string * number` ব্যবহার করে String নির্দিষ্ট সংখ্যক বার repeat হয়।
- Repetition-এর জন্য Integer ব্যবহার করতে হয়।
- Zero এবং Negative Number ব্যবহার করলে Empty String পাওয়া যায়।
- Float বা অন্য String দিয়ে সরাসরি Repetition করা যায় না।
- `*=` operator দিয়েও String Repetition করা যায়।
- String-এর মধ্যে থাকা Space-ও repeat হয়।
- String Repetition মূল String পরিবর্তন করে না; নতুন String তৈরি করে।

String Repetition Python-এর একটি গুরুত্বপূর্ণ operation, যা Pattern, Border, Message এবং বিভিন্ন Text Output তৈরি করতে ব্যবহার করা হয়।