# 16. String Concatenation and Repetition

## 1. Introduction

Python-এ string নিয়ে কাজ করার সময় দুটি গুরুত্বপূর্ণ operation হলো:

1. **String Concatenation:** একাধিক string একসঙ্গে যুক্ত করা।
2. **String Repetition:** একটি string-কে নির্দিষ্ট সংখ্যক বার পুনরাবৃত্তি করা।

এই কাজগুলো করার জন্য Python-এ `+` এবং `*` operator ব্যবহার করা যায়।

Example:

```python
first = "Hello"
second = "Python"

print(first + second)
print(first * 3)
```

Output:

```text
HelloPython
HelloHelloHello
```

এখানে `+` দুটি string যুক্ত করেছে এবং `*` একই string তিনবার পুনরাবৃত্তি করেছে।

## 2. What Is String Concatenation?

**String concatenation** হলো দুটি বা তার বেশি string-কে একত্র করে একটি নতুন string তৈরি করা।

Python-এ string concatenation-এর জন্য `+` operator ব্যবহার করা হয়।

### Syntax

```python
string1 + string2
```

### Example 1: Joining Two Strings

```python
first = "Hello"
second = "World"

result = first + second

print(result)
```

Output:

```text
HelloWorld
```

এখানে দুটি string যুক্ত হয়েছে। Python নিজে থেকে কোনো space যোগ করেনি।

### Example 2: Adding a Space

```python
first = "Hello"
second = "World"

result = first + " " + second

print(result)
```

Output:

```text
Hello World
```

এখানে `" "` একটি space-যুক্ত string। এটি মাঝখানে বসানোর কারণে শব্দ দুটি আলাদা হয়েছে।

### Example 3: Joining Multiple Strings

```python
first = "Python"
second = "is"
third = "easy"

result = first + " " + second + " " + third

print(result)
```

Output:

```text
Python is easy
```

একাধিক string একই expression-এ `+` ব্যবহার করে যুক্ত করা যায়।

## 3. Concatenating String Variables

String variable ব্যবহার করেও concatenation করা যায়।

```python
name = "Masum"
department = "CSE"
university = "NUB"

profile = name + " studies " + department + " at " + university

print(profile)
```

Output:

```text
Masum studies CSE at NUB
```

এখানে variable-এর value-গুলো যুক্ত করে একটি সম্পূর্ণ sentence তৈরি করা হয়েছে।

### Important Point

Concatenation সাধারণত নতুন string তৈরি করে। এটি মূল string variable-এর value পরিবর্তন করে না।

```python
a = "Hello"
b = "World"

result = a + " " + b

print(a)
print(b)
print(result)
```

Output:

```text
Hello
World
Hello World
```

এখানে `a` এবং `b` আগের মতোই রয়েছে। নতুন combined string `result`-এ রাখা হয়েছে।

## 4. Concatenation with the `+=` Operator

`+=` হলো augmented assignment operator। String-এর ক্ষেত্রে এটি আগের string-এর সঙ্গে নতুন string যুক্ত করে variable-এ ফলাফল assign করতে পারে।

### Example

```python
message = "Hello"

message += " "
message += "Python"

print(message)
```

Output:

```text
Hello Python
```

এখানে:

1. `message`-এ `"Hello"` রাখা হয়েছে।
2. `message += " "` দিয়ে একটি space যোগ হয়েছে।
3. `message += "Python"` দিয়ে `"Python"` যোগ হয়েছে।

ফলাফল `message` variable-এ assign হয়েছে।

আরেকটি উদাহরণ:

```python
text = "I"
text += " love"
text += " Python"

print(text)
```

Output:

```text
I love Python
```

**মনে রাখবে:** Python string immutable। `+=` ব্যবহার করলেও মূল string object পরিবর্তিত হয় না; variable নতুন string-এর দিকে reference করতে পারে।

## 5. Concatenating Strings with User Input

User-এর কাছ থেকে পাওয়া string-গুলোও যুক্ত করা যায়।

### Example 1: Joining First and Last Name

```python
first_name = input("Enter your first name: ")
last_name = input("Enter your last name: ")

full_name = first_name + " " + last_name

print("Full name:", full_name)
```

Sample Interaction:

```text
Enter your first name: Abdulla
Enter your last name: Masum
Full name: Abdulla Masum
```

### Example 2: Creating a Greeting

```python
name = input("Enter your name: ")

message = "Welcome, " + name + "!"

print(message)
```

Sample Interaction:

```text
Enter your name: Masum
Welcome, Masum!
```

এখানে fixed text এবং user input একসঙ্গে যুক্ত হয়েছে।

## 6. Concatenating Strings with Numbers

একটি common mistake হলো string-এর সঙ্গে সরাসরি integer বা float যোগ করার চেষ্টা করা।

### Incorrect Example

```python
age = 22

print("My age is " + age)
```

এখানে `TypeError` হবে, কারণ `"My age is "` একটি string, কিন্তু `age` একটি integer।

Python `+` operator ব্যবহার করে স্বয়ংক্রিয়ভাবে integer-কে string-এ convert করে না।

### Solution 1: Use `str()`

```python
age = 22

print("My age is " + str(age))
```

Output:

```text
My age is 22
```

`str(age)` integer-কে string-এ convert করেছে।

### Solution 2: Use a Comma in `print()`

```python
age = 22

print("My age is", age)
```

Output:

```text
My age is 22
```

এখানে `print()`-এর default separator একটি space। তাই আলাদাভাবে `str()` ব্যবহার করতে হয়নি।

### Solution 3: Use an f-string

```python
age = 22

print(f"My age is {age}")
```

Output:

```text
My age is 22
```

f-string ব্যবহার করে string-এর মধ্যে variable-এর value সহজে দেখানো যায়।

**Best Practice:** সাধারণ output তৈরির জন্য f-string প্রায়ই সবচেয়ে readable পদ্ধতি। তবে concatenation শেখার জন্য `+` operator-এর ব্যবহার বোঝা জরুরি।

## 7. What Is String Repetition?

**String repetition** হলো একটি string-কে নির্দিষ্ট সংখ্যক বার পুনরাবৃত্তি করে একটি নতুন string তৈরি করা।

Python-এ string repetition-এর জন্য `*` operator ব্যবহার করা হয়।

### Syntax

```python
string * number
```

### Example 1: Repeating a String

```python
text = "Python "

result = text * 3

print(result)
```

Output:

```text
Python Python Python
```

এখানে `"Python "` string-টি তিনবার পুনরাবৃত্তি হয়েছে।

### Example 2: Repeating a Symbol

```python
print("*" * 10)
```

Output:

```text
**********
```

এখানে `*` symbol-টি দশবার print করার মতো একটি string তৈরি করেছে।

### Example 3: Repeating a Word

```python
word = "Hi!"

print(word * 4)
```

Output:

```text
Hi!Hi!Hi!Hi!
```

এখানে string-এর মধ্যে space নেই। তাই পুনরাবৃত্তির মাঝেও space নেই।

Space-সহ ফলাফল চাইলে:

```python
word = "Hi! "

print(word * 4)
```

Output:

```text
Hi! Hi! Hi! Hi!
```

## 8. String Repetition with Variables

Repetition-এর সংখ্যা variable-এ রাখা যায়।

```python
symbol = "-"
count = 20

line = symbol * count

print(line)
```

Output:

```text
--------------------
```

এখানে `count`-এর value 20 হওয়ায় hyphen বিশবার পুনরাবৃত্তি হয়েছে।

আরেকটি উদাহরণ:

```python
message = "Welcome! "
times = 3

print(message * times)
```

Output:

```text
Welcome! Welcome! Welcome!
```

এভাবে variable ব্যবহার করে repetition-এর সংখ্যা সহজে নিয়ন্ত্রণ করা যায়।

## 9. Repeating a String Zero or Negative Times

String repetition-এর ক্ষেত্রে repetition count শূন্য বা negative হলে সাধারণত empty string পাওয়া যায়।

### Example 1: Zero

```python
text = "Python"

print(text * 0)
```

Output:

```text

```

এখানে output-এ কোনো character নেই, কারণ string-টি শূন্যবার পুনরাবৃত্তি হয়েছে।

### Example 2: Negative Number

```python
text = "Python"

print(text * -3)
```

Output:

```text

```

Negative repetition count-এর ক্ষেত্রেও ফলাফল empty string।

### Example 3: Positive Number

```python
text = "A"

print(text * 5)
```

Output:

```text
AAAAA
```

সুতরাং:

- Positive count: string পুনরাবৃত্তি হবে।
- Zero count: empty string।
- Negative count: empty string।

## 10. Concatenation vs Repetition

| বিষয় | Concatenation (`+`) | Repetition (`*`) |
|---|---|---|
| কাজ | String যুক্ত করে | String বারবার পুনরাবৃত্তি করে |
| সাধারণ ব্যবহার | একাধিক text একত্র করা | একই text বারবার তৈরি করা |
| Example | `"Hi" + "Bye"` | `"Hi" * 3` |
| Output | `HiBye` | `HiHiHi` |

### Combined Example

```python
word = "Hi"

result = word + " " + word * 3

print(result)
```

Output:

```text
Hi HiHiHi
```

প্রথমে `word + " "` দিয়ে `"Hi "` তৈরি হয়েছে। এরপর `word * 3` দিয়ে `"HiHiHi"` তৈরি হয়েছে। সবশেষে দুটি অংশ যুক্ত হয়েছে।

## 11. Operator Precedence with Strings

একই expression-এ `+` ও `*` থাকলে multiplication-এর precedence addition-এর চেয়ে বেশি।

### Example

```python
print("A" + "B" * 3)
```

Output:

```text
ABBB
```

এখানে প্রথমে `"B" * 3` হিসাব হয়, যার ফল `"BBB"`। তারপর `"A"` যুক্ত হয়ে `"ABBB"` তৈরি হয়।

### Another Example

```python
print(("A" + "B") * 3)
```

Output:

```text
ABABAB
```

এখানে parentheses-এর কারণে আগে `"A" + "B"` হিসাব হয়েছে। এরপর `"AB"` তিনবার পুনরাবৃত্তি হয়েছে।

**মনে রাখবে:** Parentheses ব্যবহার করলে expression-এর কোন অংশ আগে হিসাব হবে, তা স্পষ্ট করা যায়।

## 12. Repetition with Empty Strings

Empty string হলো এমন string, যার মধ্যে কোনো character নেই।

```python
text = ""

print(text * 5)
print("Hello" + text)
```

Output:

```text

Hello
```

এখানে:

- `text * 5` empty string-ই থাকে।
- `"Hello" + text`-এর ফল `"Hello"`।

Empty string concatenation-এ কোনো নতুন visible character যোগ করে না।

## 13. Practical Programs

### Program 1: Full Name Generator

```python
first_name = input("Enter first name: ")
last_name = input("Enter last name: ")

full_name = first_name + " " + last_name

print("Full name:", full_name)
```

### Program 2: Simple Banner

```python
title = "PYTHON PROGRAMMING"

print("=" * 30)
print(title)
print("=" * 30)
```

Output:

```text
==============================
PYTHON PROGRAMMING
==============================
```

এখানে `=` string-টি 30 বার পুনরাবৃত্তি করে banner তৈরি করা হয়েছে।

### Program 3: Repeat a User's Message

```python
message = input("Enter a message: ")
times = int(input("How many times? "))

print((message + " ") * times)
```

Sample Interaction:

```text
Enter a message: Hello
How many times? 3
Hello Hello Hello 
```

এখানে message-এর শেষে একটি space যোগ করে পুরো string-টি পুনরাবৃত্তি করা হয়েছে। ফলে শেষেও একটি অতিরিক্ত space থাকে।

### Program 4: Create a Simple Box Top

```python
width = 20

print("+" + "-" * width + "+")
print("|" + " " * width + "|")
print("+" + "-" * width + "+")
```

Output:

```text
+--------------------+
|                    |
+--------------------+
```

এখানে string repetition ব্যবহার করে একটি সাধারণ box-এর মতো output তৈরি হয়েছে।

### Program 5: Build a Sentence

```python
subject = "Python"
verb = "is"
description = "powerful"

sentence = subject + " " + verb + " " + description + "."

print(sentence)
```

Output:

```text
Python is powerful.
```

এই example-এ একাধিক string যুক্ত করে একটি sentence তৈরি করা হয়েছে।

## 14. Common Errors and Mistakes

### Mistake 1: Forgetting Spaces

```python
print("Hello" + "World")
```

Output:

```text
HelloWorld
```

দুটি শব্দের মধ্যে space প্রয়োজন হলে আলাদাভাবে `" "` যোগ করতে হবে।

```python
print("Hello" + " " + "World")
```

Output:

```text
Hello World
```

### Mistake 2: Mixing String and Integer

```python
age = 20

print("Age: " + age)
```

এখানে `TypeError` হবে।

Solution:

```python
print("Age: " + str(age))
```

অথবা:

```python
print(f"Age: {age}")
```

### Mistake 3: Repeating a String with a Float

```python
print("Hi" * 2.5)
```

এখানে `TypeError` হবে, কারণ string repetition-এর count integer হতে হয়।

Solution:

```python
print("Hi" * 2)
```

Output:

```text
HiHi
```

### Mistake 4: Expecting `*` to Multiply Text and Number

```python
print("5" * 3)
```

Output:

```text
555
```

এটি numeric multiplication নয়; string repetition।

Numeric multiplication চাইলে:

```python
print(int("5") * 3)
```

Output:

```text
15
```

### Mistake 5: Expecting Original String to Change

```python
text = "Python"

text + " Programming"

print(text)
```

Output:

```text
Python
```

কারণ concatenation-এর ফলাফল variable-এ assign করা হয়নি।

Solution:

```python
text = text + " Programming"

print(text)
```

Output:

```text
Python Programming
```

## 15. Practice Exercises

### Exercise 1: Basic Concatenation

দুটি variable-এ `"Hello"` এবং `"Python"` রাখো। `+` operator ব্যবহার করে যুক্ত করো।

### Exercise 2: Add Spaces

`"My"`, `"name"` এবং `"Masum"` যুক্ত করে `My name is Masum` sentence তৈরি করো।

### Exercise 3: User Input

User-এর first name এবং last name input নিয়ে full name print করো।

### Exercise 4: String Repetition

`"Python"` string-টি পাঁচবার পুনরাবৃত্তি করো।

### Exercise 5: Symbol Line

`-` symbol ব্যবহার করে 40-character-এর একটি line তৈরি করো।

### Exercise 6: Predict the Output

```python
print("A" + "B" * 2)
print(("A" + "B") * 2)
```

### Exercise 7: String and Integer

```python
age = 21
```

`str()` ব্যবহার করে নিচের output তৈরি করো:

```text
I am 21 years old.
```

### Exercise 8: Repetition Count

নিচের code-এর output কী হবে?

```python
print("Hi" * 0)
print("Hi" * -2)
print("Hi" * 3)
```

### Exercise 9: Simple Banner

`=` symbol ব্যবহার করে একটি title-এর উপরে ও নিচে 25-character-এর line তৈরি করো।

### Exercise 10: Challenge

User-এর কাছ থেকে একটি word এবং একটি integer নাও। word-টি ওই সংখ্যক বার পুনরাবৃত্তি করো। Integer invalid হলে `ValueError` handle করো এবং negative count গ্রহণ না করে উপযুক্ত message দেখাও।

## 16. Practice Answer Key

### Answer 1

```python
a = "Hello"
b = "Python"

print(a + b)
```

Output:

```text
HelloPython
```

### Answer 2

```python
a = "My"
b = "name"
c = "Masum"

print(a + " " + b + " is " + c)
```

Output:

```text
My name is Masum
```

### Answer 3

```python
first_name = input("Enter first name: ")
last_name = input("Enter last name: ")

print(first_name + " " + last_name)
```

### Answer 4

```python
print("Python" * 5)
```

Output:

```text
PythonPythonPythonPythonPython
```

### Answer 5

```python
print("-" * 40)
```

### Answer 6

Output:

```text
ABB
ABAB
```

### Answer 7

```python
age = 21

print("I am " + str(age) + " years old.")
```

Output:

```text
I am 21 years old.
```

### Answer 8

প্রথম দুটি expression empty string তৈরি করে। তৃতীয়টি `"HiHiHi"` তৈরি করে।

### Answer 9

```python
title = "Python Notes"

print("=" * 25)
print(title)
print("=" * 25)
```

### Answer 10

```python
word = input("Enter a word: ")

try:
    count = int(input("Enter repetition count: "))

    if count < 0:
        print("Count cannot be negative.")
    else:
        print(word * count)

except ValueError:
    print("Please enter a valid integer.")
```

## 17. Best Practices

1. `+` ব্যবহার করে string যুক্ত করার সময় প্রয়োজনীয় space ও punctuation ঠিকভাবে দাও।
2. String-এর সঙ্গে number যুক্ত করতে `str()` অথবা f-string ব্যবহার করো।
3. একই text বারবার তৈরি করতে `*` operator ব্যবহার করো।
4. Repetition count-এর জন্য integer ব্যবহার করো।
5. Complex expression-এ parentheses ব্যবহার করে calculation পরিষ্কার রাখো।
6. Concatenation-এর ফলাফল রাখতে চাইলে variable-এ assign করো।
7. অনেকগুলো value একত্র করার ক্ষেত্রে f-string বা `str.join()`-এর মতো বিকল্পও বিবেচনা করো।

## 18. Self-Assessment Checklist

- [ ] String concatenation কী, তা বুঝি।
- [ ] `+` operator দিয়ে একাধিক string যুক্ত করতে পারি।
- [ ] `+=` দিয়ে string variable-এর value পুনরায় assign করতে পারি।
- [ ] `str()` ব্যবহার করে number-কে string-এ convert করতে পারি।
- [ ] `*` operator দিয়ে string repetition করতে পারি।
- [ ] Zero ও negative repetition count-এর ফলাফল বুঝি।
- [ ] `+` ও `*` একসঙ্গে থাকলে precedence বুঝতে পারি।
- [ ] Common string concatenation error শনাক্ত করতে পারি।

## 19. Chapter Summary

- **Concatenation:** একাধিক string যুক্ত করে একটি string তৈরি করা।
- **Repetition:** একটি string-কে নির্দিষ্ট সংখ্যক বার পুনরাবৃত্তি করা।
- `+` string যুক্ত করে।
- `*` string পুনরাবৃত্তি করে।
- `+=` দিয়ে concatenation-এর ফল variable-এ assign করা যায়।
- String-এর সঙ্গে integer সরাসরি `+` ব্যবহার করা যায় না।
- `str()` বা f-string ব্যবহার করে text ও number একসঙ্গে output করা যায়।
- String immutable; operation-এর ফলাফল নতুন string তৈরি করে।

**Next Topic:** `17_Introduction_to_String_Formatting.md` — এখানে Python-এ variable ও value-কে সুন্দর, পরিষ্কার এবং readable format-এ output দেখানোর পদ্ধতিগুলো শিখব.