# 04. Types of Loops in Python

## 1. Introduction

Python-এ একই কাজ বারবার করার জন্য প্রধানত দুই ধরনের loop ব্যবহার করা হয়:

1. `for` loop
2. `while` loop

দুটোর উদ্দেশ্যই repetition করা, তবে কাজ করার পদ্ধতি আলাদা।

- `for` loop সাধারণত কোনো iterable-এর item একটির পর একটি process করে।
- `while` loop একটি condition `True` থাকা পর্যন্ত code execute করে।

এই পার্থক্য বোঝা গুরুত্বপূর্ণ, কারণ সঠিক loop বেছে নিলে code সহজে লেখা ও বোঝা যায়।

## 2. The `for` Loop

### Definition

A `for` loop executes a block of code for each item in an iterable.

সহজ ভাষায়, কোনো iterable-এর প্রতিটি item-এর জন্য `for` loop তার body execute করে।

Iterable-এর উদাহরণ:

- List
- Tuple
- String
- Set
- Dictionary
- `range()` object

### Syntax

```python
for variable in iterable:
    # Code to execute
```

এখানে:

- `for` হলো loop keyword।
- `variable` প্রতিটি iteration-এ বর্তমান item-এর value পায়।
- `in` iterable থেকে item নেওয়ার জন্য ব্যবহৃত হয়।
- `iterable` হলো যে object থেকে একটির পর একটি item পাওয়া যায়।
- Indented code হলো loop body।

### Example 1: Using `range()`

```python
for number in range(1, 6):
    print(number)
```

Output:

```text
1
2
3
4
5
```

এখানে পাঁচটি iteration হয়েছে।

### Example 2: Using a List

```python
subjects = ["Python", "Java", "C++"]

for subject in subjects:
    print(subject)
```

Output:

```text
Python
Java
C++
```

List-এর প্রতিটি item একবার করে process হয়েছে।

### Example 3: Using a String

```python
for character in "Python":
    print(character)
```

Output:

```text
P
y
t
h
o
n
```

String-এর প্রতিটি character একবার করে print হয়েছে।

## 3. The `while` Loop

### Definition

A `while` loop repeatedly executes a block of code as long as its condition is `True`.

সহজ ভাষায়, `while` loop-এর condition `True` থাকা পর্যন্ত loop চলতে থাকে।

### Syntax

```python
while condition:
    # Code to execute
```

এখানে:

- `while` হলো loop keyword।
- `condition` থেকে `True` বা `False` পাওয়া যায়।
- Condition `True` হলে loop body execute হয়।
- Condition `False` হলে loop body execute না করে loop শেষ হয়।

### Example 1: Counting Numbers

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

Output:

```text
1
2
3
4
5
```

এখানে `count <= 5` condition সত্য থাকা পর্যন্ত loop চলেছে। প্রতিবার `count` এক করে বাড়ানো হয়েছে।

### Example 2: Repeating a Message

```python
count = 0

while count < 3:
    print("Hello")
    count += 1
```

Output:

```text
Hello
Hello
Hello
```

Message-টি তিনবার print হয়েছে।

### Important Note

`while` loop-এ condition এবং variable update সঠিকভাবে পরিচালনা করতে হবে। নইলে loop অনির্দিষ্টকাল চলতে পারে, যাকে **infinite loop** বলা হয়।

## 4. Main Differences Between `for` and `while`

| বিষয় | `for` loop | `while` loop |
|---|---|---|
| কাজের পদ্ধতি | Iterable-এর item ধরে এগোয় | Condition পরীক্ষা করে |
| সাধারণ ব্যবহার | List-এর item process বা নির্দিষ্ট range | Condition পূরণ হওয়া পর্যন্ত কাজ |
| Iteration-এর সংখ্যা | Iterable-এর item সংখ্যার সমান হতে পারে, যদি মাঝপথে বন্ধ না হয় | আগে থেকে নির্দিষ্ট নাও থাকতে পারে |
| Variable update | Iterable থেকে পরবর্তী item পাওয়া যায় | প্রয়োজন অনুযায়ী variable update করতে হয় |
| Infinite loop-এর ঝুঁকি | সাধারণত finite iterable শেষ হলে শেষ হয় | Condition কখনো `False` না হলে চলতে পারে |
| উদাহরণ | প্রতিটি student-এর নাম print | Valid input না পাওয়া পর্যন্ত input নেওয়া |

দুটো loop দিয়েই অনেক problem solve করা সম্ভব। তবে যে loop দিয়ে logic সবচেয়ে পরিষ্কারভাবে প্রকাশ করা যায়, সেটি বেছে নেওয়া ভালো।

## 5. When Should You Use a `for` Loop?

নিচের পরিস্থিতিতে `for` loop সাধারণত সুবিধাজনক।

### Situation 1: A Known Range of Numbers

```python
for number in range(1, 11):
    print(number)
```

১ থেকে ১০ পর্যন্ত সংখ্যা print হবে।

### Situation 2: Processing a List

```python
marks = [85, 90, 78, 92]

for mark in marks:
    print(mark)
```

প্রতিটি marks-এর value একবার করে process হবে।

### Situation 3: Processing Each Character

```python
word = "Python"

for character in word:
    print(character)
```

প্রতিটি character আলাদাভাবে print হবে।

**Rule of thumb:** কোনো iterable-এর প্রতিটি item নিয়ে কাজ করতে হলে সাধারণত `for` loop দিয়ে শুরু করো।

## 6. When Should You Use a `while` Loop?

নিচের পরিস্থিতিতে `while` loop সুবিধাজনক হতে পারে।

### Situation 1: Repeating Until a Condition Changes

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

Condition সত্য থাকা পর্যন্ত loop চলবে।

### Situation 2: Input Validation

```python
password = ""

while password != "python123":
    password = input("Enter password: ")

print("Correct password")
```

সঠিক password না পাওয়া পর্যন্ত input নেওয়া হবে।

এটি শেখার উদাহরণ; বাস্তব authentication-এর জন্য নিরাপদ password handling প্রয়োজন।

### Situation 3: Menu-Based Programs

```python
choice = ""

while choice != "0":
    print("1. Start")
    print("0. Exit")

    choice = input("Choose an option: ")

print("Program ended")
```

User `0` দিলে loop শেষ হবে।

**Rule of thumb:** কোনো condition পরিবর্তন হওয়া পর্যন্ত কাজ চালিয়ে যেতে হলে `while` loop বিবেচনা করো।

## 7. Can We Solve the Same Problem With Both Loops?

হ্যাঁ, অনেক ক্ষেত্রে একই কাজ `for` এবং `while`—দুইভাবেই করা যায়।

### Using a `for` Loop

```python
for number in range(1, 6):
    print(number)
```

### Using a `while` Loop

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

দুটোর output:

```text
1
2
3
4
5
```

তবে `while` loop-এ `number` update করতে হয়েছে। `for` loop-এ `range()` থেকে পরবর্তী value স্বয়ংক্রিয়ভাবে পাওয়া গেছে।

## 8. Nested Loops

একটি loop-এর ভেতরে আরেকটি loop থাকলে তাকে **Nested Loop** বলে।

```python
for row in range(2):
    for column in range(3):
        print(row, column)
```

Output:

```text
0 0
0 1
0 2
1 0
1 1
1 2
```

এখানে বাইরের loop দুইবার চলে এবং প্রতিবার ভেতরের loop তিনবার চলে। ফলে মোট ছয়বার `print()` execute হয়।

Nested loops আলাদা topic-এ বিস্তারিত শিখব।

## 9. Common Beginner Mistakes

### Mistake 1: `while` Loop-এ Variable Update না করা

ভুল:

```python
count = 1

while count <= 3:
    print(count)
```

এখানে `count` পরিবর্তিত হয় না, তাই loop শেষ হবে না।

সঠিক:

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

### Mistake 2: `for` Loop-এর Iterable ভুল বোঝা

```python
for number in range(1, 5):
    print(number)
```

এখানে `5` print হবে না, কারণ `range()`-এর stop value অন্তর্ভুক্ত হয় না।

### Mistake 3: অপ্রয়োজনীয়ভাবে Loop জটিল করা

যদি কোনো list-এর প্রতিটি item print করতে হয়, তাহলে সরাসরি `for` loop ব্যবহার করাই পরিষ্কার।

```python
names = ["Masum", "Ritu", "Mahin"]

for name in names:
    print(name)
```

### Mistake 4: ধরে নেওয়া যে `for` সবসময় নির্দিষ্ট সংখ্যক বার চলে

`for` loop iterable-এর item ধরে চলে। Iterable-এর item সংখ্যা জানা থাকলে iteration-এর সংখ্যা অনুমান করা যায়, কিন্তু `break`-এর মতো control statement থাকলে loop আগেই শেষ হতে পারে।

## 10. Practice Exercises

### Exercise 1

Python-এর প্রধান দুই ধরনের loop-এর নাম লেখো।

### Exercise 2

নিচের code-এর output লেখো:

```python
for i in range(2, 5):
    print(i)
```

### Exercise 3

নিচের code-এর output লেখো:

```python
count = 1

while count < 4:
    print(count)
    count += 1
```

### Exercise 4

একটি list-এর প্রতিটি item print করতে সাধারণত কোন loop ব্যবহার করা সুবিধাজনক?

### Exercise 5

কোনো condition `True` থাকা পর্যন্ত একটি কাজ চালাতে কোন loop ব্যবহার করা যায়?

### Exercise 6

নিচের দুইটি code-এর output কি একই হবে?

```python
for i in range(1, 4):
    print(i)
```

```python
i = 1

while i <= 3:
    print(i)
    i += 1
```

### Exercise 7

নিচের code-এ সমস্যাটি কী?

```python
count = 1

while count <= 5:
    print(count)
    count -= 1
```

## 11. Answer Key

**Exercise 1:** `for` loop এবং `while` loop।

**Exercise 2:**

```text
2
3
4
```

**Exercise 3:**

```text
1
2
3
```

**Exercise 4:** সাধারণত `for` loop।

**Exercise 5:** `while` loop।

**Exercise 6:** হ্যাঁ। দুটি code-ই `1`, `2`, `3` print করবে।

**Exercise 7:** `count` এক করে কমছে। এটি কখনো `5`-এর চেয়ে বড় হবে না, তাই condition সবসময় `True` থাকবে এবং loop চলতেই থাকবে। এখানে `count += 1` ব্যবহার করলে loop স্বাভাবিকভাবে শেষ হবে।

## 12. Chapter Progress Checklist

- [ ] `for` loop-এর basic syntax বুঝেছি।
- [ ] `while` loop-এর basic syntax বুঝেছি।
- [ ] `for` ও `while`-এর পার্থক্য জানি।
- [ ] কোন পরিস্থিতিতে কোন loop ব্যবহার করব, বুঝতে পারি।
- [ ] একই problem দুই ধরনের loop দিয়ে solve করতে পারি।
- [ ] Infinite loop-এর একটি সাধারণ কারণ শনাক্ত করতে পারি।
- [ ] Nested loop-এর প্রাথমিক ধারণা বুঝেছি।

## 13. Summary

- Python-এ প্রধানত `for` ও `while` loop ব্যবহার করা হয়।
- `for` loop iterable-এর প্রতিটি item process করতে সুবিধাজনক।
- `while` loop condition `True` থাকা পর্যন্ত চলে।
- অনেক problem দুই ধরনের loop দিয়েই solve করা যায়।
- `while` loop-এ condition এবং variable update ঠিক রাখতে হয়।
- Nested loop হলো একটি loop-এর ভেতরে আরেকটি loop।

**Next Topic:** `05_Understanding_Loop_Execution_Flow.md`
