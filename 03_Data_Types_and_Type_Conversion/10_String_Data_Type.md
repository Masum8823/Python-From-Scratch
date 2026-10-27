# 10. String Data Type in Python

## 1. What Is a String?

Python-এ **String (`str`) হলো এক বা একাধিক character-এর sequence**, যা text সংরক্ষণ করতে ব্যবহার করা হয়।

String-এর মধ্যে letter, number, symbol, space এবং special character থাকতে পারে।

Example:

```python
name = "Masum"
message = "Hello, Python!"
number_text = "12345"
symbol = "@#$%"
```

এখানে সবগুলোই String, কারণ এগুলো quotation marks-এর মধ্যে লেখা হয়েছে।

String-এর data type পরীক্ষা করা যায় `type()` দিয়ে।

```python
name = "Masum"

print(type(name))
```

Output:

```text
<class 'str'>
```

**মনে রাখবে:** `"123"` একটি String, কিন্তু `123` একটি Integer।

```python
print(type("123"))
print(type(123))
```

Output:

```text
<class 'str'>
<class 'int'>
```

## 2. Creating Strings in Python

Python-এ সাধারণত তিনভাবে String তৈরি করা যায়।

### 2.1 Single Quotes

Single quotation marks ব্যবহার করে String তৈরি করা যায়।

```python
name = 'Masum'
print(name)
```

Output:

```text
Masum
```

### 2.2 Double Quotes

Double quotation marks ব্যবহার করেও String তৈরি করা যায়।

```python
message = "Hello, World!"
print(message)
```

Output:

```text
Hello, World!
```

Single quotes এবং double quotes—দুটিই সাধারণ String তৈরির জন্য সমানভাবে ব্যবহার করা যায়।

### 2.3 Triple Quotes

Triple single quotes অথবা triple double quotes ব্যবহার করে একাধিক লাইনের String তৈরি করা যায়।

```python
message = """Hello,
Welcome to Python.
Happy Learning!"""

print(message)
```

Output:

```text
Hello,
Welcome to Python.
Happy Learning!
```

Triple quotes সাধারণত multiline String এবং documentation-এর জন্য ব্যবহৃত হয়।

## 3. Using Quotes Inside a String

String-এর মধ্যে quotation marks রাখতে হলে সঠিকভাবে quote নির্বাচন করতে হবে অথবা escape character ব্যবহার করতে হবে।

### Example 1: Single Quotes Inside Double Quotes

```python
message = "It's a beautiful day."
print(message)
```

Output:

```text
It's a beautiful day.
```

### Example 2: Double Quotes Inside Single Quotes

```python
message = 'He said, "Hello!"'
print(message)
```

Output:

```text
He said, "Hello!"
```

### Example 3: Using Escape Character

একই ধরনের quotation mark-এর মধ্যে সেই quotation mark ব্যবহার করতে চাইলে `\` ব্যবহার করা যায়।

```python
message = "He said, \"Hello!\""
print(message)
```

Output:

```text
He said, "Hello!"
```

এখানে `\"` quotation mark-টিকে String-এর অংশ হিসেবে প্রকাশ করে।

## 4. The `str()` Function

`str()` হলো একটি built-in function, যা কোনো value-কে তার String representation-এ রূপান্তর করে।

Example:

```python
age = 22
price = 99.5
active = True

print(str(age))
print(str(price))
print(str(active))
```

Output:

```text
22
99.5
True
```

এখন type পরীক্ষা করি:

```python
age = 22
text = str(age)

print(type(age))
print(type(text))
```

Output:

```text
<class 'int'>
<class 'str'>
```

এখানে `age`-এর original value পরিবর্তন হয়নি। `str(age)` থেকে পাওয়া String-টি `text` variable-এ রাখা হয়েছে।

**মনে রাখবে:** `str()` কোনো value-কে String-এ রূপান্তর করে; কিন্তু `int()` বা `float()`-এর মতো numeric conversion করার চেষ্টা করে না।

```python
print(str(123))
print(type(str(123)))
```

Output:

```text
123
<class 'str'>
```

## 5. Strings and Variables

String-কে variable-এর মধ্যে সংরক্ষণ করা যায় এবং পরে সেই variable ব্যবহার করা যায়।

```python
first_name = "Abdulla"
last_name = "Masum"

print(first_name)
print(last_name)
```

Output:

```text
Abdulla
Masum
```

একাধিক String variable ব্যবহার করে নতুন String তৈরি করা যায়।

```python
first_name = "Abdulla"
last_name = "Masum"

full_name = first_name + " " + last_name

print(full_name)
```

Output:

```text
Abdulla Masum
```

এখানে `" "` একটি space-যুক্ত String। এটি ব্যবহার না করলে দুটি নামের মাঝে space থাকবে না।

## 6. String Length with `len()`

`len()` function একটি String-এ মোট কতটি character আছে, তা গণনা করে।

এখানে space এবং punctuation-ও character হিসেবে গণনা হয়।

Example:

```python
text = "Python"

print(len(text))
```

Output:

```text
6
```

Space-সহ উদাহরণ:

```python
text = "Hello World"

print(len(text))
```

Output:

```text
11
```

কারণ `Hello`-তে ৫টি character, space ১টি এবং `World`-এ ৫টি character রয়েছে।

Empty String-এর length হলো `0`।

```python
text = ""

print(len(text))
```

Output:

```text
0
```

## 7. String Indexing

**Indexing** ব্যবহার করে String-এর নির্দিষ্ট position-এর character পাওয়া যায়।

Python-এ indexing `0` থেকে শুরু হয়।

Example:

```python
text = "Python"

print(text[0])
print(text[1])
print(text[2])
```

Output:

```text
P
y
t
```

String `"Python"`-এর index:

| Character | P | y | t | h | o | n |
|---|---:|---:|---:|---:|---:|---:|
| Positive index | 0 | 1 | 2 | 3 | 4 | 5 |
| Negative index | -6 | -5 | -4 | -3 | -2 | -1 |

### Negative Indexing

Negative indexing ব্যবহার করে String-এর শেষ দিক থেকে character পাওয়া যায়।

```python
text = "Python"

print(text[-1])
print(text[-2])
print(text[-6])
```

Output:

```text
n
o
P
```

**মনে রাখবে:**

- প্রথম character-এর index হলো `0`।
- শেষ character-এর negative index হলো `-1`।
- String-এর valid index-এর বাইরে access করলে `IndexError` হয়।

Example:

```python
text = "Python"

print(text[10])
```

এটি `IndexError` তৈরি করবে, কারণ index `10`-এ কোনো character নেই।

## 8. String Slicing

**Slicing** ব্যবহার করে String-এর একটি অংশ বের করা যায়।

Syntax:

```python
string[start:stop:step]
```

এখানে:

- `start`: যে index থেকে শুরু হবে।
- `stop`: যে index পর্যন্ত যাবে, তবে `stop` index-এর character অন্তর্ভুক্ত হবে না।
- `step`: কত ঘর পরপর character নেওয়া হবে।

### 8.1 Basic Slicing

```python
text = "Python"

print(text[0:3])
print(text[2:5])
```

Output:

```text
Pyt
tho
```

`text[0:3]`-এ index `0`, `1` এবং `2` নেওয়া হয়েছে। Index `3` নেওয়া হয়নি।

### 8.2 Omitting Start and Stop

```python
text = "Python"

print(text[:3])
print(text[3:])
print(text[:])
```

Output:

```text
Pyt
hon
Python
```

- `text[:3]` শুরু থেকে index `3`-এর আগ পর্যন্ত নেয়।
- `text[3:]` index `3` থেকে শেষ পর্যন্ত নেয়।
- `text[:]` সম্পূর্ণ String-এর সমান একটি নতুন String তৈরি করে।

### 8.3 Slicing with Negative Index

```python
text = "Python"

print(text[-3:])
print(text[:-2])
```

Output:

```text
hon
Pyth
```

### 8.4 Slicing with Step

```python
text = "Python"

print(text[::2])
print(text[::-1])
```

Output:

```text
Pto
nohtyP
```

`text[::2]` প্রতি দুই ঘর পরপর character নেয়। আর `text[::-1]` String-কে উল্টো ক্রমে প্রকাশ করে।

**Important:** Slicing-এ `stop` index-এর বাইরে গেলেও সাধারণত `IndexError` হয় না। Python যতটুকু valid অংশ আছে, ততটুকু নেয়।

## 9. String Concatenation

**Concatenation** হলো একাধিক String যুক্ত করে একটি String তৈরি করা।

Python-এ `+` operator ব্যবহার করে String concatenation করা যায়।

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

আরেকটি উদাহরণ:

```python
a = "Py"
b = "thon"

print(a + b)
```

Output:

```text
Python
```

**সতর্কতা:** String-এর সঙ্গে Integer সরাসরি `+` ব্যবহার করলে `TypeError` হয়।

```python
age = 22

print("Age: " + age)
```

সঠিক উপায়:

```python
age = 22

print("Age: " + str(age))
```

Output:

```text
Age: 22
```

আধুনিক Python-এ String-এর সঙ্গে variable যুক্ত করার জন্য f-string-ও ব্যবহার করা যায়; এটি পরবর্তী String formatting topic-এ বিস্তারিত শেখা হবে।

## 10. String Repetition

`*` operator ব্যবহার করে একটি String একাধিকবার repeat করা যায়।

```python
text = "Hi! "

print(text * 3)
```

Output:

```text
Hi! Hi! Hi!
```

আরেকটি উদাহরণ:

```python
line = "-" * 10

print(line)
```

Output:

```text
----------
```

তবে String repetition-এর জন্য integer multiplier ব্যবহার করতে হয়।

```python
print("Python" * 2)
```

Output:

```text
PythonPython
```

## 11. Checking Membership with `in` and `not in`

`in` operator পরীক্ষা করে কোনো character বা substring একটি String-এর মধ্যে আছে কি না।

`not in` পরীক্ষা করে সেটি নেই কি না।

Example:

```python
text = "Python Programming"

print("Python" in text)
print("Java" in text)
print("Java" not in text)
```

Output:

```text
True
False
True
```

Membership checking case-sensitive।

```python
text = "Python"

print("Py" in text)
print("py" in text)
```

Output:

```text
True
False
```

এখানে `"Py"` এবং `"py"` আলাদা, কারণ `P` ও `p`-এর case আলাদা।

## 12. String Immutability

Python-এর String হলো **immutable** data type।

Immutability মানে String তৈরি হওয়ার পর তার নির্দিষ্ট character-কে সরাসরি পরিবর্তন করা যায় না।

Example:

```python
text = "Python"

text[0] = "J"
```

এই code চালালে `TypeError` হবে।

কারণ `text[0]`-এর character সরাসরি পরিবর্তন করা যায় না।

### How to Create a Modified String

পরিবর্তিত String তৈরি করতে নতুন String বানাতে হয়।

```python
text = "Python"

new_text = "J" + text[1:]

print(new_text)
print(text)
```

Output:

```text
Jython
Python
```

এখানে `new_text`-এ নতুন String তৈরি হয়েছে। Original `text` অপরিবর্তিত রয়েছে।

### Reassignment Is Allowed

String immutable হলেও variable-কে নতুন String assign করা যায়।

```python
text = "Python"
text = "Java"

print(text)
```

Output:

```text
Java
```

এখানে String-এর character পরিবর্তন করা হয়নি; variable-টিকে নতুন String-এর সঙ্গে bind করা হয়েছে।

## 13. Comparing Strings

Python-এ `==` operator ব্যবহার করে দুটি String সমান কি না পরীক্ষা করা যায়।

```python
a = "Python"
b = "Python"
c = "Java"

print(a == b)
print(a == c)
```

Output:

```text
True
False
```

String comparison case-sensitive।

```python
print("Python" == "python")
```

Output:

```text
False
```

String-এর মধ্যে `!=`, `<`, `>`-এর মতো comparison operator-ও ব্যবহার করা যায়। Ordering comparison Unicode code point-এর ক্রম অনুসারে হয়; এটি সব ক্ষেত্রে মানুষের dictionary ordering-এর সঙ্গে এক হবে, এমন নয়।

```python
print("apple" < "banana")
```

Output:

```text
True
```

## 14. Common String Mistakes

### Mistake 1: Forgetting That Indexing Starts at Zero

```python
text = "Python"

print(text[1])
```

Output:

```text
y
```

এখানে প্রথম character পাওয়ার জন্য `text[0]` ব্যবহার করতে হবে।

### Mistake 2: Using an Invalid Index

```python
text = "Python"

print(text[6])
```

এটি `IndexError` তৈরি করবে, কারণ valid positive index হলো `0` থেকে `5`।

### Mistake 3: Mixing String and Integer

```python
age = 22

print("Age: " + age)
```

এটি `TypeError` তৈরি করবে। প্রয়োজন অনুযায়ী `str(age)` অথবা f-string ব্যবহার করতে হবে।

### Mistake 4: Trying to Modify a String Character

```python
text = "Python"
text[0] = "J"
```

এটি `TypeError` তৈরি করবে, কারণ String immutable।

### Mistake 5: Confusing Number Text with a Number

```python
a = "10"
b = "20"

print(a + b)
```

Output:

```text
1020
```

কারণ `a` এবং `b` String; তাই `+` এখানে concatenation করে।

সংখ্যা হিসেবে যোগ করতে চাইলে:

```python
a = int("10")
b = int("20")

print(a + b)
```

Output:

```text
30
```

### Mistake 6: Forgetting Case Sensitivity

```python
text = "Python"

print("python" in text)
```

Output:

```text
False
```

কারণ membership checking case-sensitive।

## 15. Practice Exercises

### Exercise 1: Create Strings

নিচের value-গুলো দিয়ে String তৈরি করো:

1. নিজের নাম।
2. নিজের university-এর নাম।
3. একটি sentence।
4. একাধিক লাইনের একটি message।

প্রতিটির type `type()` দিয়ে পরীক্ষা করো।

### Exercise 2: String Length

```python
text = "Python Programming"
```

নির্ণয় করো:

1. String-এর মোট length।
2. প্রথম character।
3. শেষ character।
4. প্রথম পাঁচটি character।

### Exercise 3: Indexing and Slicing

```python
text = "Programming"
```

নিচের expression-গুলোর output অনুমান করো:

```python
print(text[0])
print(text[-1])
print(text[0:4])
print(text[3:7])
print(text[::-1])
```

### Exercise 4: Concatenation and Repetition

দুটি variable-এ first name এবং last name রাখো। সেগুলো concatenate করে full name তৈরি করো। এরপর full name তিনবার repeat করো।

### Exercise 5: Membership Checking

```python
text = "Artificial Intelligence"
```

পরীক্ষা করো:

- `"Artificial"` আছে কি না।
- `"intelligence"` আছে কি না।
- `"Python"` নেই কি না।

প্রতিটি ক্ষেত্রে output ব্যাখ্যা করো।

### Exercise 6: Immutability

নিচের code-টি কেন error তৈরি করে তা ব্যাখ্যা করো:

```python
text = "Hello"
text[0] = "Y"
```

তারপর নতুন String তৈরি করে `Yello` output দেখাও।

### Exercise 7: Mini Project — User Profile

একটি ছোট program লেখো, যেখানে:

- User-এর নাম একটি String variable-এ থাকবে।
- University-এর নাম আরেকটি String variable-এ থাকবে।
- নামের length print হবে।
- নামের প্রথম ও শেষ character print হবে।
- নাম এবং university-এর নাম একসঙ্গে print হবে।
- নামের প্রথম তিনটি character slicing করে print হবে।

## 16. Key Takeaways

- String-এর built-in type হলো `str`।
- Single quotes, double quotes এবং triple quotes দিয়ে String তৈরি করা যায়।
- `str()` value-কে String representation-এ রূপান্তর করে।
- `len()` String-এর character count দেয়।
- Indexing `0` থেকে শুরু হয়; negative indexing শেষ দিক থেকে কাজ করে।
- Slicing দিয়ে String-এর নির্দিষ্ট অংশ নেওয়া যায়।
- `+` দিয়ে concatenation এবং `*` দিয়ে repetition করা যায়।
- `in` ও `not in` membership পরীক্ষা করে।
- String immutable; character সরাসরি পরিবর্তন করা যায় না।
- String comparison এবং membership checking case-sensitive।
- String ও Integer আলাদা type; প্রয়োজনে conversion করতে হয়।

## 17. Next Topic

পরবর্তী ফাইল:

**`11_Boolean_Data_Type.md`**

সেখানে `bool`, `True`, `False`, comparison-এর result এবং Boolean value-এর ব্যবহার বিস্তারিতভাবে শেখা হবে।