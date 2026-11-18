# 01. Introduction to Strings in Python

## 1. String কী?

Python-এ **String হলো text বা character-এর একটি sequence**। কোনো নাম, বাক্য, message, address কিংবা অন্য যেকোনো text সংরক্ষণ করার জন্য string ব্যবহার করা হয়।

উদাহরণ:

```python
name = "Masum"
country = "Bangladesh"
message = "I am learning Python."
```

এখানে `name`, `country` এবং `message` ভেরিয়েবলে string রাখা হয়েছে।

- `"Masum"` একটি string।
- `"Bangladesh"` একটি string।
- `"I am learning Python."` একটি string।

String-এর মধ্যে অক্ষর, সংখ্যা, space এবং বিভিন্ন symbol থাকতে পারে।

```python
name = "Masum"
age_text = "22"
password = "abc123@"
message = "Hello, World!"
```

এখানে সবগুলো value-ই string, কারণ এগুলো quotation marks-এর মধ্যে লেখা হয়েছে।

**মনে রাখবে:** String-এর মধ্যে সংখ্যা থাকলেও সেটি string হতে পারে। যেমন `"22"` একটি string, কিন্তু `22` একটি integer।

## 2. বাস্তব জীবনে String-এর ব্যবহার

আমরা প্রতিদিন বিভিন্ন ধরনের text নিয়ে কাজ করি। Python-এ সেগুলো string দিয়ে সংরক্ষণ করা যায়।

| ব্যবহার | উদাহরণ |
|---|---|
| নাম | `"Abdulla"` |
| বিশ্ববিদ্যালয়ের নাম | `"Northern University Bangladesh"` |
| ইমেইল | `"student@example.com"` |
| মোবাইল নম্বর | `"01712345678"` |
| বার্তা | `"Welcome to Python"` |
| পাসওয়ার্ডের text | `"abc@123"` |
| ঠিকানা | `"Dhaka, Bangladesh"` |

মোবাইল নম্বর string হিসেবে রাখা অনেক সময় সুবিধাজনক, কারণ এর শুরুতে `0` থাকতে পারে এবং সাধারণত এটি দিয়ে গাণিতিক হিসাব করা হয় না।

## 3. Python-এ String কীভাবে লিখতে হয়?

String তৈরি করার সবচেয়ে সাধারণ উপায় হলো text-কে quotation marks-এর মধ্যে লেখা।

```python
print("Hello, Python!")
print('Welcome to Python')
```

**Output:**

```text
Hello, Python!
Welcome to Python
```

Python-এ single quotation (`' '`) এবং double quotation (`" "`)—দুটিই ব্যবহার করা যায়।

```python
name = "Masum"
country = 'Bangladesh'

print(name)
print(country)
```

**Output:**

```text
Masum
Bangladesh
```

দুই ক্ষেত্রেই Python string তৈরি করেছে।

## 4. Character কী?

**Character হলো string-এর একটি একক উপাদান**, যেমন একটি অক্ষর, সংখ্যা, space অথবা symbol।

উদাহরণ:

```python
word = "Python"
```

এই string-এর character-গুলো হলো:

```text
P  y  t  h  o  n
```

প্রতিটি অক্ষর আলাদাভাবে একটি character।

আরেকটি উদাহরণ:

```python
text = "A1@ B"
```

এখানে character-গুলো হলো:

- `A` — অক্ষর
- `1` — সংখ্যা হিসেবে লেখা character
- `@` — symbol
- ` ` — space
- `B` — অক্ষর

Python-এ আলাদা `char` data type নেই। একটি character-ও আসলে string।

```python
letter = "A"
print(type(letter))
```

**Output:**

```text
<class 'str'>
```

এখানে `str` হলো Python-এর string data type।

## 5. Sequence বলতে কী বোঝায়?

Sequence হলো এমন একটি collection, যেখানে উপাদানগুলো একটি নির্দিষ্ট ক্রমে থাকে।

String একটি sequence, কারণ এর character-গুলোর অবস্থান নির্দিষ্ট থাকে।

```python
word = "PYTHON"
```

এখানে character-গুলোর ক্রম হলো:

```text
P → Y → T → H → O → N
```

ক্রম পরিবর্তন করলে string-ও পরিবর্তিত হয়।

```python
print("PYTHON")
print("NOHTYP")
```

**Output:**

```text
PYTHON
NOHTYP
```

দুটি string-এ একই character থাকলেও তাদের ক্রম আলাদা।

এই sequence ধারণা পরবর্তী সময়ে **indexing, slicing এবং string iteration** বুঝতে কাজে লাগবে।

## 6. String এবং Number-এর পার্থক্য

একই দেখতে হলেও string ও number-এর data type আলাদা হতে পারে।

```python
a = 25
b = "25"

print(type(a))
print(type(b))
```

**Output:**

```text
<class 'int'>
<class 'str'>
```

এখানে:

- `25` হলো integer।
- `"25"` হলো string।

এদের operation-ও আলাদা।

```python
print(25 + 5)
print("25" + "5")
```

**Output:**

```text
30
255
```

প্রথম ক্ষেত্রে যোগ হয়েছে। দ্বিতীয় ক্ষেত্রে string দুটি পাশাপাশি যুক্ত হয়েছে। এই প্রক্রিয়াকে **string concatenation** বলা হয়।

String-এর সঙ্গে integer সরাসরি যোগ করা যায় না:

```python
age = 22

print("My age is " + age)
```

এটি `TypeError` তৈরি করবে। কারণ string-এর সঙ্গে integer সরাসরি concatenate করা যায় না।

সঠিক উপায়:

```python
age = 22

print("My age is " + str(age))
```

**Output:**

```text
My age is 22
```

এখানে `str(age)` integer-কে string-এ রূপান্তর করেছে।

## 7. String-এর Length

String-এর মধ্যে মোট কতটি character আছে, তা জানার জন্য `len()` function ব্যবহার করা হয়।

```python
word = "Python"

print(len(word))
```

**Output:**

```text
6
```

`"Python"`-এ ৬টি character আছে, তাই output `6`।

Space-ও character হিসেবে গণনা হয়।

```python
message = "Hi Python"

print(len(message))
```

**Output:**

```text
9
```

এখানে `Hi`-এর ২টি character, একটি space এবং `Python`-এর ৬টি character রয়েছে। মোট \(2+1+6=9\)।

## 8. String-এর মধ্যে Space ও Symbol

String-এ শুধু alphabet থাকতে হবে, এমন কোনো নিয়ম নেই।

```python
text1 = "Hello World"
text2 = "Python123"
text3 = "Price: 500 Tk"
text4 = "user@gmail.com"

print(text1)
print(text2)
print(text3)
print(text4)
```

**Output:**

```text
Hello World
Python123
Price: 500 Tk
user@gmail.com
```

String-এর মধ্যে space, digit, punctuation এবং symbol থাকতে পারে।

## 9. Empty String কী?

যে string-এর মধ্যে কোনো character নেই, তাকে **empty string** বলা হয়।

```python
text = ""

print(text)
print(len(text))
print(type(text))
```

**Output:**

```text

0
<class 'str'>
```

প্রথম লাইনে empty string print হওয়ায় কোনো দৃশ্যমান text দেখা যায় না। এর length `0`, কিন্তু এর data type এখনও `str`।

Empty string এবং string-এর মধ্যে space এক নয়।

```python
print(len(""))
print(len(" "))
```

**Output:**

```text
0
1
```

প্রথম string খালি। দ্বিতীয় string-এ একটি space আছে।

## 10. Common Mistakes

### Mistake 1: Quotation marks না দেওয়া

ভুল:

```python
name = Masum
```

যদি `Masum` নামে কোনো variable আগে থেকে তৈরি না থাকে, তাহলে `NameError` হবে।

সঠিক:

```python
name = "Masum"
```

### Mistake 2: String ও Integer-কে একই মনে করা

```python
print("10" + "20")
print(10 + 20)
```

Output:

```text
1020
30
```

প্রথম ক্ষেত্রে string concatenate হয়েছে। দ্বিতীয় ক্ষেত্রে integer যোগ হয়েছে।

### Mistake 3: Empty string ও space-কে একই মনে করা

```python
print(len(""))
print(len(" "))
```

Output:

```text
0
1
```

Space একটি character, তাই এর length `1`।

### Mistake 4: Python-এ আলাদা Character Type আছে মনে করা

```python
letter = "A"

print(type(letter))
```

Output:

```text
<class 'str'>
```

Python-এ single character-ও string type-এর।

## 11. Practice Exercises

নিজে code লিখে নিচের প্রশ্নগুলোর উত্তর বের করার চেষ্টা করো।

1. নিজের নাম একটি string variable-এ রাখো এবং print করো।
2. নিজের বিশ্ববিদ্যালয়ের নাম string হিসেবে রাখো।
3. `"Python Programming"` string-এর length বের করো।
4. `"100"` এবং `100`-এর data type পরীক্ষা করো।
5. `"Hello"` ও `"World"` concatenate করো।
6. Empty string এবং একটি space-যুক্ত string-এর length তুলনা করো।
7. `"Python123@!"` string-টি print করো।
8. `25` integer-কে string-এ রূপান্তর করে `"My number is "`-এর সঙ্গে যুক্ত করো।

## 12. Practice Solutions

### Solution 1

```python
name = "Masum"
print(name)
```

Output:

```text
Masum
```

### Solution 2

```python
university = "Northern University Bangladesh"
print(university)
```

### Solution 3

```python
text = "Python Programming"
print(len(text))
```

Output:

```text
18
```

### Solution 4

```python
print(type("100"))
print(type(100))
```

Output:

```text
<class 'str'>
<class 'int'>
```

### Solution 5

```python
print("Hello" + "World")
```

Output:

```text
HelloWorld
```

দুটি শব্দের মাঝে space চাইলে:

```python
print("Hello" + " " + "World")
```

Output:

```text
Hello World
```

### Solution 6

```python
print(len(""))
print(len(" "))
```

Output:

```text
0
1
```

### Solution 7

```python
print("Python123@!")
```

Output:

```text
Python123@!
```

### Solution 8

```python
number = 25
print("My number is " + str(number))
```

Output:

```text
My number is 25
```

## 13. Chapter Summary

- String হলো text বা character-এর sequence।
- Python-এ string-এর data type হলো `str`।
- Single ও double quotes—দুটিই string তৈরিতে ব্যবহার করা যায়।
- Python-এ আলাদা `char` data type নেই।
- String-এর মধ্যে alphabet, digit, space ও symbol থাকতে পারে।
- `len()` দিয়ে string-এর character সংখ্যা জানা যায়।
- Empty string-এর length `0`; একটি space-এর length `1`।
- String ও integer আলাদা data type।
- String concatenate করতে `+` ব্যবহার করা যায়।
- `str()` দিয়ে অন্য data type-কে string-এ রূপান্তর করা যায়।

## 14. Self-Assessment Checklist

- [ ] String কী তা নিজের ভাষায় ব্যাখ্যা করতে পারি।
- [ ] String এবং integer-এর পার্থক্য বুঝি।
- [ ] Character ও sequence-এর ধারণা বুঝি।
- [ ] `str` ও `len()` ব্যবহার করতে পারি।
- [ ] Empty string ও space-এর পার্থক্য বুঝি।
- [ ] String concatenation করতে পারি।
- [ ] সাধারণ string-related error শনাক্ত করতে পারি।

## 15. Next Topic

পরবর্তী file: `02_Why_Strings_Are_Important.md`

এখানে programming-এ string কেন গুরুত্বপূর্ণ, কীভাবে user input, data processing, web applications এবং text-based problem solving-এ string ব্যবহার করা হয়, তা বিস্তারিত শেখানো হবে।
