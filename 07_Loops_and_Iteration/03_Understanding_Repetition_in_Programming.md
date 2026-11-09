# 03. Understanding Repetition in Programming

## 1. Introduction

Programming-এ **Repetition** বলতে একই কাজ বা নির্দিষ্ট কিছু instruction বারবার সম্পাদন করাকে বোঝায়।

ধরো, তোমাকে ১ থেকে ৫ পর্যন্ত সংখ্যা print করতে হবে। তুমি চাইলে পাঁচটি `print()` statement লিখতে পারো। কিন্তু সংখ্যার পরিমাণ যদি ১,০০০ হয়, তাহলে এতগুলো statement লেখা বাস্তবসম্মত নয়।

এই ধরনের repetitive কাজ সহজ করার জন্য loop ব্যবহার করা হয়।

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

এখানে একই `print()` statement পাঁচবার execute হয়েছে, কিন্তু code লিখতে হয়েছে একবারই।

## 2. What Is Repetition?

**Definition:** Repetition is the process of executing the same instruction or a group of instructions multiple times.

সহজ ভাষায়, কোনো instruction বা instruction-এর group একাধিকবার execute হওয়াকে repetition বলে।

উদাহরণ:

- একটি message বারবার print করা।
- অনেকগুলো student-এর marks পরীক্ষা করা।
- কয়েকটি number-এর যোগফল বের করা।
- User-এর সঠিক input না পাওয়া পর্যন্ত আবার input নেওয়া।
- একটি multiplication table তৈরি করা।

Repetition programming-এর একটি গুরুত্বপূর্ণ ধারণা, কারণ অনেক real-world problem-এ একই ধরনের কাজ একাধিক data-এর ওপর করতে হয়।

## 3. Repetition Without a Loop

ধরো, `Hello` তিনবার print করতে হবে।

```python
print("Hello")
print("Hello")
print("Hello")
```

Output:

```text
Hello
Hello
Hello
```

এখানে একই statement তিনবার লিখতে হয়েছে।

এই পদ্ধতি অল্প কয়েকবারের কাজের জন্য গ্রহণযোগ্য হতে পারে। কিন্তু repetition-এর সংখ্যা বাড়লে code দীর্ঘ ও maintain করা কঠিন হয়ে যায়।

## 4. Repetition With a Loop

একই কাজ loop দিয়ে করা যায়:

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

এখানে `range(3)` তিনটি value দেয়: `0`, `1` ও `2`। তাই loop-এর body মোট তিনবার execute হয়।

খেয়াল করো, এখানে `i`-এর value ব্যবহার করে message পরিবর্তন করা হয়নি। শুধু তিনবার repetition নিয়ন্ত্রণ করার জন্য variable-টি ব্যবহৃত হয়েছে।

## 5. Types of Repetition

প্রোগ্রামিংয়ের কাজ বোঝার সুবিধার জন্য repetition-কে কয়েকভাবে ভাগ করে দেখা যায়। এগুলো ধারণাগত শ্রেণিবিভাগ; Python-এ মূল loop statement হলো `for` ও `while`।

### 5.1 Fixed-Count Repetition

যখন আগে থেকেই জানা থাকে কাজটি কতবার করতে হবে, তখন তাকে fixed-count repetition বলা যায়।

উদাহরণ: পাঁচবার একটি message print করা।

```python
for i in range(5):
    print("Keep practicing")
```

Output:

```text
Keep practicing
Keep practicing
Keep practicing
Keep practicing
Keep practicing
```

এখানে repetition-এর সংখ্যা আগে থেকেই নির্ধারিত—পাঁচবার।

**ব্যবহার:**

- ১ থেকে ১০০ পর্যন্ত সংখ্যা print করা।
- একটি নির্দিষ্ট multiplication table তৈরি করা।
- নির্দিষ্ট সংখ্যক বার calculation করা।

### 5.2 Condition-Based Repetition

যখন কোনো condition-এর ওপর নির্ভর করে repetition চলতে থাকে, তখন তাকে condition-based repetition বলা যায়।

উদাহরণ:

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

এখানে `count <= 5` condition `True` থাকা পর্যন্ত loop চলেছে।

প্রতিবার `count` এক করে বাড়ছে। `count`-এর value `6` হলে condition `False` হবে এবং loop বন্ধ হবে।

**ব্যবহার:**

- সঠিক input না পাওয়া পর্যন্ত input নেওয়া।
- কোনো নির্দিষ্ট condition পূরণ না হওয়া পর্যন্ত কাজ করা।
- Menu-driven program-এ exit option নির্বাচন না করা পর্যন্ত menu দেখানো।

### 5.3 Data-Based Repetition

যখন কোনো collection বা iterable-এর item-গুলো একটির পর একটি process করা হয়, তখন সেটিকেও repetition-এর একটি সাধারণ ধরন হিসেবে বোঝা যায়।

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

এখানে list-এর প্রতিটি item-এর জন্য loop একবার করে execute হয়েছে।

## 6. Fixed-Count vs Condition-Based Repetition

| বিষয় | Fixed-count repetition | Condition-based repetition |
|---|---|---|
| Repetition-এর সংখ্যা | সাধারণত আগে থেকে জানা | আগে থেকে জানা নাও থাকতে পারে |
| সাধারণ ব্যবহার | নির্দিষ্ট সংখ্যক কাজ | Condition পূরণ হওয়া পর্যন্ত কাজ |
| উপযুক্ত loop | প্রায়ই `for` | প্রায়ই `while` |
| উদাহরণ | ১০ বার message print | Valid input না পাওয়া পর্যন্ত input নেওয়া |

**মনে রাখবে:** `for` ও `while` একে অপরের বিকল্প হিসেবে অনেক problem-এ ব্যবহার করা যায়। কোনটি ভালো হবে, তা problem-এর logic-এর ওপর নির্ভর করে।

## 7. Understanding Repetition Step by Step

নিচের code-টি দেখি:

```python
for number in range(1, 4):
    print(number * 2)
```

Output:

```text
2
4
6
```

এখন execution বুঝি:

| Iteration | `number` | Calculation | Output |
|---:|---:|---|---:|
| 1 | 1 | `1 * 2` | 2 |
| 2 | 2 | `2 * 2` | 4 |
| 3 | 3 | `3 * 2` | 6 |

প্রতিটি iteration-এ একই calculation করা হয়েছে, কিন্তু `number`-এর value পরিবর্তিত হয়েছে।

এটাই repetition-এর মূল ধারণা: একই logic বিভিন্ন value-এর জন্য বারবার execute করা।

## 8. Repetition and Variables

Loop-এর ভেতরে variable ব্যবহার করে প্রতিটি iteration-এ ভিন্ন কাজ করা যায়।

উদাহরণ: ১ থেকে ৫ পর্যন্ত সংখ্যার বর্গ print করা।

```python
for number in range(1, 6):
    square = number * number
    print(square)
```

Output:

```text
1
4
9
16
25
```

এখানে `number` প্রতিটি iteration-এ নতুন value পাচ্ছে এবং সেই value-এর square হিসাব করা হচ্ছে।

## 9. Repetition and Accumulation

কিছু problem-এ শুধু কাজ বারবার করলেই হয় না; প্রতিবারের result জমা রাখতে হয়। এই পদ্ধতিকে **Accumulation** বলা হয়।

উদাহরণ: ১ থেকে ৪ পর্যন্ত সংখ্যার যোগফল।

```python
total = 0

for number in range(1, 5):
    total += number

print("Total:", total)
```

Output:

```text
Total: 10
```

প্রতিটি iteration-এ `number`-কে `total`-এর সঙ্গে যোগ করা হচ্ছে।

| Iteration | `number` | যোগ করার পর `total` |
|---:|---:|---:|
| শুরুতে | — | 0 |
| 1 | 1 | 1 |
| 2 | 2 | 3 |
| 3 | 3 | 6 |
| 4 | 4 | 10 |

এখানে দুটি বিষয় গুরুত্বপূর্ণ:

- `total = 0` দিয়ে accumulation শুরু হয়েছে।
- `total += number` প্রতিটি iteration-এ total আপডেট করছে।

## 10. Repetition Must Have a Clear Stopping Point

প্রতিটি loop-এর execution কীভাবে শেষ হবে, তা বুঝতে হবে।

`for` loop সাধারণত iterable-এর item শেষ হলে শেষ হয়।

```python
for number in range(1, 4):
    print(number)
```

এখানে range-এর item শেষ হলে loop বন্ধ হয়।

অন্যদিকে, `while` loop condition `False` হলে বন্ধ হয়।

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

এখানে `count` বাড়তে বাড়তে `4` হলে condition `False` হয়।

যদি `count += 1` বাদ দেওয়া হয়, তাহলে `count` সবসময় `1` থাকবে এবং loop চলতেই থাকবে। এটিকে **Infinite Loop** বলা হয়।

## 11. Common Beginner Mistakes

### Mistake 1: Repetition-এর সংখ্যা ভুল গণনা করা

```python
for i in range(1, 5):
    print(i)
```

এখানে চারবার execution হবে, পাঁচবার নয়। কারণ `range()`-এর stop value অন্তর্ভুক্ত হয় না।

### Mistake 2: Variable Update করতে ভুলে যাওয়া

```python
count = 1

while count <= 3:
    print(count)
```

এই loop শেষ হবে না, কারণ `count` পরিবর্তিত হচ্ছে না।

### Mistake 3: Repetition ও Accumulation গুলিয়ে ফেলা

```python
total = 0

for number in range(1, 4):
    total = number

print(total)
```

Output:

```text
3
```

এখানে আগের value-এর সঙ্গে যোগ করা হয়নি। প্রতিবার `total` নতুন value দিয়ে replace হয়েছে।

যোগফল চাইলে লিখতে হবে:

```python
total = 0

for number in range(1, 4):
    total += number

print(total)
```

Output:

```text
6
```

### Mistake 4: অপ্রয়োজনীয় Loop ব্যবহার করা

একটি সাধারণ calculation-এর জন্য loop দরকার নাও হতে পারে।

```python
print(10 + 20)
```

কাজটি সরাসরি করা সহজ হলে অপ্রয়োজনীয় loop যোগ করবে না।

## 12. Practice Exercises

### Exercise 1

Repetition in programming বলতে কী বোঝায়?

### Exercise 2

Fixed-count repetition এবং condition-based repetition-এর পার্থক্য লেখো।

### Exercise 3

নিচের code-এর output লেখো:

```python
for i in range(4):
    print(i)
```

### Exercise 4

নিচের code-এর output কী হবে?

```python
for number in range(1, 4):
    print(number * number)
```

### Exercise 5

নিচের code-এর output কী হবে এবং কেন?

```python
total = 0

for number in range(1, 5):
    total += number

print(total)
```

### Exercise 6

নিচের code-এ কী সমস্যা রয়েছে?

```python
count = 1

while count <= 4:
    print(count)
```

### Exercise 7

১ থেকে ৫ পর্যন্ত প্রতিটি সংখ্যার দ্বিগুণ print করার Python code লেখো।

## 13. Answer Key

**Exercise 1:** একই instruction বা group of instructions একাধিকবার execute করাকে repetition বলে।

**Exercise 2:** Fixed-count repetition-এ সাধারণত আগে থেকেই কতবার কাজ হবে জানা থাকে। Condition-based repetition-এ condition `True` থাকা পর্যন্ত কাজ চলে।

**Exercise 3:**

```text
0
1
2
3
```

**Exercise 4:**

```text
1
4
9
```

**Exercise 5:**

```text
10
```

কারণ \(1 + 2 + 3 + 4 = 10\)।

**Exercise 6:** `count` আপডেট করা হচ্ছে না। তাই condition সবসময় `True` থাকবে এবং loop infinite হবে। `count += 1` যোগ করতে হবে।

**Exercise 7:**

```python
for number in range(1, 6):
    print(number * 2)
```

## 14. Chapter Progress Checklist

- [ ] Repetition-এর ধারণা বুঝেছি।
- [ ] Loop ছাড়া ও loop দিয়ে repetition-এর পার্থক্য বুঝি।
- [ ] Fixed-count repetition বুঝি।
- [ ] Condition-based repetition বুঝি।
- [ ] Data-based repetition বুঝি।
- [ ] Loop-এর প্রতিটি iteration trace করতে পারি।
- [ ] Accumulation-এর basic ধারণা বুঝেছি।
- [ ] Loop শেষ হওয়ার শর্ত বুঝতে পারি।

## 15. Summary

- Repetition হলো একই instruction বারবার execute করা।
- Fixed-count repetition-এ সাধারণত execution-এর সংখ্যা আগে থেকেই নির্ধারিত থাকে।
- Condition-based repetition একটি condition-এর ওপর নির্ভর করে।
- `for` loop iterable-এর item process করতে সুবিধাজনক।
- `while` loop condition `True` থাকা পর্যন্ত চলে।
- Accumulation ব্যবহার করে loop-এর প্রতিটি iteration-এর result জমা রাখা যায়।
- সঠিক stopping condition না থাকলে infinite loop তৈরি হতে পারে।

**Next Topic:** `04_Types_of_Loops_in_Python.md`
