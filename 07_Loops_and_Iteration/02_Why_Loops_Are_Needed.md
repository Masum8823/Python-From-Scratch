# 02. Why Loops Are Needed

## 1. Introduction

Programming-এ অনেক সময় একই ধরনের কাজ বারবার করতে হয়। যেমন, ১০ জন student-এর নাম print করা, ১ থেকে ১০০ পর্যন্ত সংখ্যা যোগ করা অথবা একটি list-এর সব item পরীক্ষা করা।

প্রতিটি কাজের জন্য আলাদা আলাদা code লিখলে program বড় হয় এবং পরিবর্তন করাও কঠিন হয়ে পড়ে। এই সমস্যা সমাধানের জন্য **Loop** ব্যবহার করা হয়।

Loop একই code বারবার execute করে repetitive কাজ সহজ, দ্রুত এবং maintainable করে।

## 2. Problem Without a Loop

ধরো, আমাদের ৫টি সংখ্যা print করতে হবে।

```python
print(1)
print(2)
print(3)
print(4)
print(5)
```

Output:

```text
1
2
3
4
5
```

এই code কাজ করছে। কিন্তু এখন যদি ১০০টি সংখ্যা print করতে হয়, তাহলে কি ১০০টি `print()` statement লিখব?

এতে কয়েকটি সমস্যা হবে:

- অনেক বেশি code লিখতে হবে।
- একই code বারবার লিখতে হবে।
- পরিবর্তন করতে বেশি সময় লাগবে।
- ভুল হওয়ার সম্ভাবনা বাড়বে।
- Code পড়া ও maintain করা কঠিন হবে।

## 3. Solving the Same Problem With a Loop

একই কাজ `for` loop দিয়ে সহজে করা যায়।

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

এখানে `range(1, 6)` থেকে ১ থেকে ৫ পর্যন্ত সংখ্যা পাওয়া যায় এবং loop প্রতিটি সংখ্যা print করে।

১০০টি সংখ্যা print করতে চাইলে শুধু range পরিবর্তন করলেই হবে:

```python
for number in range(1, 101):
    print(number)
```

এভাবে একই structure ব্যবহার করে অনেকগুলো value process করা যায়।

## 4. Main Reasons for Using Loops

### 4.1 To Avoid Repeated Code

একই কাজের জন্য বারবার একই statement লেখার প্রয়োজন হয় না।

Without loop:

```python
print("Welcome")
print("Welcome")
print("Welcome")
print("Welcome")
```

With loop:

```python
for i in range(4):
    print("Welcome")
```

দুই ক্ষেত্রেই `Welcome` চারবার print হবে।

### 4.2 To Process Large Amounts of Data

ধরো, একটি list-এ অনেকগুলো student-এর নাম রয়েছে।

```python
students = ["Masum", "Ritu", "Mahin", "Tusher"]

for student in students:
    print(student)
```

Output:

```text
Masum
Ritu
Mahin
Tusher
```

List-এ আরও student যোগ করলেও একই loop দিয়ে তাদের নাম print করা যাবে।

### 4.3 To Perform Repeated Calculations

ধরো, ১ থেকে ৫ পর্যন্ত সংখ্যার যোগফল বের করতে হবে।

```python
total = 0

for number in range(1, 6):
    total = total + number

print("Total:", total)
```

Output:

```text
Total: 15
```

প্রতিটি iteration-এ `number`-এর value `total`-এর সঙ্গে যোগ হচ্ছে।

| Iteration | `number` | `total` |
|---:|---:|---:|
| শুরুতে | — | 0 |
| 1 | 1 | 1 |
| 2 | 2 | 3 |
| 3 | 3 | 6 |
| 4 | 4 | 10 |
| 5 | 5 | 15 |

এই ধরনের calculation-কে **Accumulation** বলা হয়। এটি পরবর্তী topic-এ আরও বিস্তারিত শিখব।

### 4.4 To Repeat Work Until a Condition Is Met

কখন কাজ বন্ধ করতে হবে তা আগে থেকে নির্দিষ্ট সংখ্যায় জানা না থাকলেও loop ব্যবহার করা যায়।

উদাহরণ: সঠিক password না দেওয়া পর্যন্ত আবার input নেওয়া।

```python
password = ""

while password != "python123":
    password = input("Enter password: ")

print("Access granted")
```

এই code সঠিক password না পাওয়া পর্যন্ত input চাইবে।

**Note:** এটি শেখার জন্য একটি সাধারণ উদাহরণ। বাস্তব authentication system-এ password নিরাপদভাবে সংরক্ষণ ও যাচাই করতে হয়।

### 4.5 To Automate Repetitive Tasks

Loop ব্যবহার করে বিভিন্ন repetitive task স্বয়ংক্রিয় করা যায়, যেমন:

- একাধিক number-এর মধ্যে even number খুঁজে বের করা।
- একটি list-এর সব value-এর যোগফল বের করা।
- একাধিক record পরীক্ষা করা।
- একটি multiplication table তৈরি করা।
- নির্দিষ্ট সংখ্যক বার কোনো message print করা।

## 5. Loops Make Programs Easier to Maintain

ধরো, তুমি একটি message ১০ বার print করতে চাও।

```python
for i in range(10):
    print("Keep learning Python")
```

এখন ১০ বার পরিবর্তে ২০ বার print করতে চাইলে শুধু `range(10)` পরিবর্তন করে `range(20)` করতে হবে।

```python
for i in range(20):
    print("Keep learning Python")
```

অর্থাৎ, একই code structure রেখে সহজেই কাজের পরিমাণ পরিবর্তন করা যায়।

তবে মনে রাখবে, loop ব্যবহার করলেই সব program স্বয়ংক্রিয়ভাবে দ্রুত হবে এমন নয়। এর প্রধান সুবিধা হলো repeated logic কমানো এবং code সহজে পরিচালনা করা।

## 6. Real-Life Analogy

ধরো, তোমাকে ৫০ জন student-এর attendance নিতে হবে।

Loop ছাড়া তোমাকে প্রতিটি student-এর জন্য একই ধরনের কাজের code আলাদাভাবে লিখতে হতে পারে।

Loop ব্যবহার করলে:

1. প্রথম student-এর তথ্য নেওয়া হবে।
2. পরবর্তী student-এর তথ্য নেওয়া হবে।
3. একই প্রক্রিয়া বারবার চলবে।
4. সব student-এর কাজ শেষ হলে loop বন্ধ হবে।

Programming-এও একই ধারণা ব্যবহার করা হয়: **একই process, বিভিন্ন data অথবা একই data-এর ওপর বারবার কাজ।**

## 7. When Should We Use a Loop?

| Situation | Loop প্রয়োজন? | কারণ |
|---|---|---|
| একটি message একবার print করা | সাধারণত না | একবার `print()` যথেষ্ট |
| একটি message ১০০ বার print করা | হ্যাঁ | একই কাজ বারবার করতে হবে |
| List-এর প্রতিটি item process করা | হ্যাঁ | প্রতিটি item-এর জন্য একই logic |
| ১ থেকে ১০০ পর্যন্ত যোগফল বের করা | হ্যাঁ | অনেকগুলো সংখ্যা process করতে হবে |
| User-এর valid input না পাওয়া পর্যন্ত input নেওয়া | হ্যাঁ | Condition পূরণ না হওয়া পর্যন্ত পুনরাবৃত্তি |
| দুটি সংখ্যার যোগফল বের করা | সাধারণত না | সরাসরি যোগ করা যায় |

## 8. Common Beginner Mistakes

### Mistake 1: Repeated Code লেখা

```python
print(1)
print(2)
print(3)
print(4)
print(5)
```

সংখ্যার পরিমাণ বেশি হলে loop ব্যবহার করা সহজ।

### Mistake 2: Loop-কে অপ্রয়োজনীয়ভাবে জটিল করা

প্রতিটি ছোট কাজের জন্য loop প্রয়োজন হয় না।

```python
a = 10
b = 20

print(a + b)
```

এখানে যোগফল বের করতে loop দরকার নেই।

### Mistake 3: Loop শেষ হওয়ার বিষয়টি ভুলে যাওয়া

`while` loop-এর condition সবসময় `True` থাকলে loop চলতেই থাকবে। তাই condition এবং প্রয়োজনীয় variable update বুঝে লিখতে হবে।

### Mistake 4: Loop ব্যবহার করলেই Code সবসময় Faster ভাবা

Loop-এর মূল উদ্দেশ্য repeated কাজ সহজ করা। Performance নির্ভর করে algorithm, data size এবং implementation-এর ওপর।

## 9. Practice Exercises

### Exercise 1

Loop ব্যবহার করার যেকোনো তিনটি সুবিধা লেখো।

### Exercise 2

নিচের code-টি loop দিয়ে লেখো:

```python
print("Python")
print("Python")
print("Python")
print("Python")
print("Python")
```

### Exercise 3

নিচের code-এর output কী হবে?

```python
total = 0

for number in range(1, 4):
    total += number

print(total)
```

### Exercise 4

কোন পরিস্থিতিতে `while` loop ব্যবহার করা সুবিধাজনক?

A. নির্দিষ্ট একটি message একবার print করতে।

B. Condition পূরণ না হওয়া পর্যন্ত input নিতে।

C. দুটি সংখ্যা সরাসরি যোগ করতে।

### Exercise 5

নিচের কাজটির জন্য loop ব্যবহার করা কেন সুবিধাজনক?

একটি list-এর ২০০টি number-এর মধ্যে even number-গুলো print করা।

## 10. Answer Key

**Exercise 1:**
- Repeated code কমায়।
- অনেকগুলো data process করতে সাহায্য করে।
- Code পরিবর্তন ও maintain করা সহজ করে।

**Exercise 2:**

```python
for i in range(5):
    print("Python")
```

**Exercise 3:**

```text
6
```

কারণ \(1+2+3=6\)।

**Exercise 4:** সঠিক উত্তর **B**। Condition পূরণ না হওয়া পর্যন্ত input নেওয়ার জন্য `while` loop ব্যবহার করা সুবিধাজনক।

**Exercise 5:** Loop list-এর প্রতিটি number পরীক্ষা করতে পারে। যেসব number-এর জন্য `number % 2 == 0`, সেগুলো print করা যাবে।

## 11. Chapter Progress Checklist

- [ ] Loop কেন প্রয়োজন, বুঝতে পেরেছি।
- [ ] Loop ছাড়া repeated code লেখার অসুবিধা বুঝি।
- [ ] Loop দিয়ে repeated task করতে পারি।
- [ ] বড় data collection process করার ধারণা বুঝেছি।
- [ ] কোন পরিস্থিতিতে loop ব্যবহার করা উচিত, বুঝতে পারি।
- [ ] Loop সবসময় performance বাড়ায় না—এটি বুঝেছি।

## 12. Summary

- Loop একই code বারবার execute করতে সাহায্য করে।
- Repeated code কমিয়ে program সহজ ও maintainable করে।
- বড় data collection এবং repeated calculation process করতে loop কার্যকর।
- `for` loop সাধারণত iterable-এর item process করতে ব্যবহৃত হয়।
- `while` loop condition `True` থাকা পর্যন্ত চলে।
- সব কাজের জন্য loop দরকার হয় না; problem অনুযায়ী উপযুক্ত approach বেছে নিতে হয়।

**Next Topic:** `03_Understanding_Repetition_in_Programming.md`
