# 01. Introduction to Loops and Iteration

## 1. Introduction

Programming-এ অনেক সময় একই কাজ বারবার করতে হয়। যেমন, ১ থেকে ১০ পর্যন্ত সংখ্যা print করা, কোনো student-এর marks হিসাব করা অথবা একটি list-এর সব item দেখানো।

প্রতিবার একই code আলাদাভাবে লিখলে program বড় হয়ে যায় এবং ভুল হওয়ার সম্ভাবনাও বাড়ে। এই সমস্যা সমাধানের জন্য Python-এ **Loop** ব্যবহার করা হয়।

Loop-এর সাহায্যে নির্দিষ্ট condition পূরণ হওয়া পর্যন্ত অথবা কোনো sequence-এর সব item শেষ না হওয়া পর্যন্ত একই code বারবার execute করা যায়।

## 2. What Is a Loop?

**Definition:** A loop is a programming structure that executes a block of code repeatedly.

সহজ ভাষায়, Loop হলো এমন একটি programming structure, যার মাধ্যমে একই code বারবার চালানো যায়।

### Example: Without a Loop

```python
print(1)
print(2)
print(3)
print(4)
print(5)
```

**Output:**

```text
1
2
3
4
5
```

এখানে পাঁচটি সংখ্যা print করার জন্য পাঁচটি `print()` statement লিখতে হয়েছে।

### Example: With a Loop

```python
for number in range(1, 6):
    print(number)
```

**Output:**

```text
1
2
3
4
5
```

এখানে মাত্র দুইটি code line ব্যবহার করে একই output পাওয়া গেছে।

**মূল কথা:** একই কাজ বারবার করার প্রয়োজন হলে loop code-কে ছোট, পরিষ্কার ও maintain করা সহজ করে।

## 3. What Is Iteration?

**Definition:** An iteration is one complete execution of a loop's body.

সহজভাবে, একটি loop একবার তার ভেতরের code execute করলে সেটিকে একটি **Iteration** বলা হয়।

উপরের উদাহরণে:

```python
for number in range(1, 6):
    print(number)
```

Loop-টি মোট পাঁচবার execute হয়।

| Iteration | `number`-এর value | Output |
|---:|---:|---:|
| 1st | 1 | 1 |
| 2nd | 2 | 2 |
| 3rd | 3 | 3 |
| 4th | 4 | 4 |
| 5th | 5 | 5 |

অর্থাৎ, এই loop-এ মোট ৫টি iteration হয়েছে।

**মনে রাখবে:**

- **Loop:** বারবার code execute করার structure।
- **Iteration:** সেই loop-এর একবারের execution।

## 4. Why Do We Need Loops?

Loop ব্যবহার করার কয়েকটি গুরুত্বপূর্ণ কারণ নিচে দেওয়া হলো।

### 4.1 Repeating Tasks

একই কাজ বারবার করার জন্য loop ব্যবহার করা হয়।

```python
for i in range(3):
    print("Hello")
```

Output:

```text
Hello
Hello
Hello
```

এখানে `Hello` তিনবার print হয়েছে।

### 4.2 Reducing Repeated Code

১০০টি সংখ্যা print করতে ১০০টি `print()` statement লেখার প্রয়োজন নেই।

```python
for i in range(1, 101):
    print(i)
```

এই loop ১ থেকে ১০০ পর্যন্ত সংখ্যা print করবে।

### 4.3 Processing Multiple Values

একটি list-এর প্রতিটি item নিয়ে কাজ করতে loop ব্যবহার করা যায়।

```python
students = ["Masum", "Ritu", "Mahin"]

for student in students:
    print(student)
```

Output:

```text
Masum
Ritu
Mahin
```

### 4.4 Performing Calculations

Loop দিয়ে অনেকগুলো সংখ্যার যোগফল বের করা যায়।

```python
total = 0

for number in range(1, 6):
    total = total + number

print(total)
```

Output:

```text
15
```

এখানে \(1+2+3+4+5=15\) হিসাব করা হয়েছে।

### 4.5 Automating Repetitive Work

Loop ব্যবহার করে একই ধরনের কাজ স্বয়ংক্রিয়ভাবে করা যায়। যেমন:

- অনেকগুলো student-এর marks process করা।
- একটি list-এর সব number পরীক্ষা করা।
- একাধিক file-এর নাম নিয়ে কাজ করা।
- বিভিন্ন input-এর জন্য একই calculation করা।

## 5. Types of Loops in Python

Python-এ সাধারণত দুটি প্রধান loop ব্যবহার করা হয়।

### 5.1 `for` Loop

`for` loop ব্যবহার করে কোনো sequence বা iterable-এর item একটির পর একটি process করা যায়।

```python
for i in range(1, 4):
    print(i)
```

Output:

```text
1
2
3
```

এখানে `range(1, 4)` থেকে `1`, `2` ও `3` পাওয়া যায়। Stop value `4` অন্তর্ভুক্ত হয় না।

**কখন ব্যবহার করব?**

- নির্দিষ্ট সংখ্যক বার কাজ করতে।
- List, tuple বা string-এর item নিয়ে কাজ করতে।
- কোনো iterable-এর প্রতিটি item process করতে।

### 5.2 `while` Loop

`while` loop একটি condition `True` থাকা পর্যন্ত code execute করে।

```python
count = 1

while count <= 3:
    print(count)
    count = count + 1
```

Output:

```text
1
2
3
```

এখানে `count <= 3` condition `True` থাকা অবস্থায় loop চলেছে। প্রতিবার `count` এক করে বাড়ানো হয়েছে।

**কখন ব্যবহার করব?**

- কোনো condition পূরণ হওয়া পর্যন্ত কাজ করতে।
- User-এর valid input না পাওয়া পর্যন্ত input নিতে।
- কোনো নির্দিষ্ট event বা state পরিবর্তনের জন্য অপেক্ষা করতে।

`for` ও `while` loop বিস্তারিতভাবে পরবর্তী topic-গুলোতে শিখব।

## 6. How Does a Loop Work?

একটি সাধারণ loop-এর execution flow:

1. Loop শুরু হয়।
2. প্রয়োজন অনুযায়ী sequence থেকে value নেওয়া হয় অথবা condition পরীক্ষা করা হয়।
3. Loop-এর ভেতরের code execute হয়।
4. পরবর্তী iteration-এর জন্য control এগিয়ে যায়।
5. Loop শেষ হওয়ার শর্ত পূরণ হলে execution বন্ধ হয়।

উদাহরণ:

```python
count = 1

while count <= 3:
    print(count)
    count = count + 1

print("Loop finished")
```

Output:

```text
1
2
3
Loop finished
```

এখানে `count`-এর value `1`, `2` ও `3` হওয়ার সময় loop-এর body execute হয়েছে। এরপর `count` হয় `4`; তখন `count <= 3` condition `False` হওয়ায় loop শেষ হয়।

## 7. Important Terms

| Term | সহজ অর্থ |
|---|---|
| Loop | Code বারবার execute করার structure |
| Iteration | Loop-এর একবারের execution |
| Loop body | Loop-এর ভেতরে থাকা code block |
| Condition | যে expression থেকে `True` বা `False` পাওয়া যায় |
| Loop variable | Loop-এর সঙ্গে সম্পর্কিত value ধারণকারী variable |
| Sequence | নির্দিষ্ট ক্রমে থাকা item-গুলোর collection |
| Iterable | যে object-এর item একটির পর একটি পাওয়া যায় |
| Infinite loop | যে loop স্বাভাবিকভাবে শেষ হয় না |

## 8. Common Beginner Mistakes

### Mistake 1: Loop-এর বদলে বারবার একই code লেখা

```python
print("Python")
print("Python")
print("Python")
```

একই কাজ বারবার করতে হলে loop ব্যবহার করা আরও সুবিধাজনক।

### Mistake 2: `for` ও `while`-এর কাজ গুলিয়ে ফেলা

- `for`: সাধারণত iterable-এর item বা নির্দিষ্ট range-এর ওপর কাজ করে।
- `while`: condition `True` থাকা পর্যন্ত কাজ করে।

দুটো loop দিয়েই অনেক ধরনের repetitive task করা যায়; উপযুক্ত loop বেছে নেওয়া গুরুত্বপূর্ণ।

### Mistake 3: `while` loop-এ variable update না করা

```python
count = 1

while count <= 3:
    print(count)
```

এই code-এ `count` কখনো বাড়ছে না। Condition সবসময় `True` থাকায় এটি infinite loop হবে।

সঠিক code:

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

### Mistake 4: `range()`-এর stop value অন্তর্ভুক্ত মনে করা

```python
for i in range(1, 5):
    print(i)
```

Output হবে `1`, `2`, `3`, `4`। এখানে `5` print হবে না।

## 9. Practice Exercises

নিজে চেষ্টা করবে। উত্তর দেখার আগে code-এর output অনুমান করার চেষ্টা করো।

### Exercise 1

Loop বলতে কী বোঝায়?

### Exercise 2

Iteration কী?

### Exercise 3

নিচের code-এর output কী হবে?

```python
for i in range(1, 4):
    print("Python")
```

### Exercise 4

নিচের loop-এ মোট কতটি iteration হবে?

```python
for number in range(2, 7):
    print(number)
```

### Exercise 5

`for` loop ও `while` loop-এর মধ্যে একটি পার্থক্য লেখো।

### Exercise 6

নিচের code-এ কী সমস্যা রয়েছে?

```python
count = 1

while count <= 5:
    print(count)
```

## 10. Answer Key

**Exercise 1:** Loop হলো এমন programming structure, যা code বারবার execute করে।

**Exercise 2:** Loop-এর body একবার সম্পূর্ণ execute হওয়াকে iteration বলে।

**Exercise 3:**

```text
Python
Python
Python
```

মোট ৩ বার print হবে।

**Exercise 4:** মোট ৫টি iteration হবে। `number`-এর value হবে `2`, `3`, `4`, `5`, `6`।

**Exercise 5:** `for` loop সাধারণত iterable-এর item process করে; `while` loop condition `True` থাকা পর্যন্ত চলে।

**Exercise 6:** `count`-এর value পরিবর্তন করা হচ্ছে না। তাই condition সবসময় `True` থাকবে এবং loop শেষ হবে না। `count += 1` যোগ করতে হবে।

## 11. Chapter Progress Checklist

- [ ] Loop কী, বুঝতে পেরেছি।
- [ ] Iteration কী, বুঝতে পেরেছি।
- [ ] Loop কেন প্রয়োজন, ব্যাখ্যা করতে পারি।
- [ ] `for` ও `while` loop-এর basic পার্থক্য জানি।
- [ ] Simple loop-এর output অনুমান করতে পারি।
- [ ] Infinite loop-এর basic কারণ বুঝতে পেরেছি।

## 12. Summary

- Loop দিয়ে একই code বারবার execute করা যায়।
- Loop-এর একবারের execution-কে iteration বলে।
- Python-এ প্রধানত `for` ও `while` loop ব্যবহার করা হয়।
- `for` loop iterable-এর item process করতে সুবিধাজনক।
- `while` loop condition `True` থাকা পর্যন্ত execute হয়।
- Loop-এর condition এবং variable update সঠিক না হলে infinite loop হতে পারে।

**Next Topic:** `02_Why_Loops_Are_Needed.md`
