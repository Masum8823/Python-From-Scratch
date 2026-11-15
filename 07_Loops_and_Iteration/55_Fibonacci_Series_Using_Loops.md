# 55. Fibonacci Series Using Loops

## 1. Introduction

Fibonacci Series হলো এমন একটি number sequence, যেখানে প্রথম দুটি সংখ্যার পর প্রতিটি নতুন সংখ্যা আগের দুটি সংখ্যার যোগফল।

সাধারণভাবে এই sequence শুরু হয়:

```text
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ...
```

এখানে:

- প্রথম সংখ্যা `0`
- দ্বিতীয় সংখ্যা `1`
- তৃতীয় সংখ্যা `0 + 1 = 1`
- চতুর্থ সংখ্যা `1 + 1 = 2`
- পঞ্চম সংখ্যা `1 + 2 = 3`
- ষষ্ঠ সংখ্যা `2 + 3 = 5`

Python-এ loop ব্যবহার করে সহজেই Fibonacci Series তৈরি করা যায়।

এই Topic-এ আমরা শিখব:

- Fibonacci Series-এর ধারণা ও নিয়ম
- `for` loop দিয়ে Fibonacci Series
- `while` loop দিয়ে Fibonacci Series
- User input দিয়ে নির্দিষ্ট সংখ্যক term তৈরি
- Dry run ও variable update
- নির্দিষ্ট limit পর্যন্ত Fibonacci সংখ্যা
- Common mistakes ও practice problems

## 2. Understanding the Fibonacci Series

Fibonacci Series-এর প্রতিটি নতুন সংখ্যা আগের দুটি সংখ্যার যোগফল।

ধরি, প্রথম দুটি সংখ্যা:

\[
F_0 = 0,\qquad F_1 = 1
\]

এরপর:

\[
F_n = F_{n-1} + F_{n-2}
\]

এখানে \(n \geq 2\)।

উদাহরণ:

| Position | Calculation | Fibonacci number |
|---:|---|---:|
| 1 | Starting value | 0 |
| 2 | Starting value | 1 |
| 3 | 0 + 1 | 1 |
| 4 | 1 + 1 | 2 |
| 5 | 1 + 2 | 3 |
| 6 | 2 + 3 | 5 |
| 7 | 3 + 5 | 8 |
| 8 | 5 + 8 | 13 |

**মনে রাখবে:** Fibonacci Series-এর প্রচলিত শুরু `0, 1` হলেও কিছু বই বা সমস্যায় `1, 1` দিয়ে শুরু করা হয়। Program লেখার আগে প্রশ্নে কোন convention চাওয়া হয়েছে তা দেখে নিতে হবে।

## 3. Fibonacci Series Using a `for` Loop

প্রথমে ১০টি Fibonacci term print করি।

### Code

```python
a = 0
b = 1

for i in range(10):
    print(a, end=" ")

    a, b = b, a + b
```

### Output

```text
0 1 1 2 3 5 8 13 21 34
```

### Explanation

- `a = 0` প্রথম term ধরে রাখে।
- `b = 1` দ্বিতীয় term ধরে রাখে।
- `range(10)` loop-টি ১০ বার চালায়।
- `print(a, end=" ")` বর্তমান Fibonacci term print করে।
- `a, b = b, a + b` পরবর্তী দুটি value update করে।

এই line-টি বিশেষভাবে গুরুত্বপূর্ণ:

```python
a, b = b, a + b
```

এটি Python-এর multiple assignment ব্যবহার করে। ডান পাশের expression-গুলো আগে evaluate হয়, তারপর বাম পাশের variable-গুলো update হয়।

উদাহরণস্বরূপ, যদি `a = 2` এবং `b = 3` হয়, তাহলে update-এর পরে:

- `a = 3`
- `b = 5`

এভাবেই series চলতে থাকে।

## 4. Understanding Variable Updates

Fibonacci Series-এ দুটি variable ব্যবহার করা হয়, কারণ প্রতিটি নতুন term বের করতে আগের দুটি term প্রয়োজন।

ধরি:

```python
a = 2
b = 3

a, b = b, a + b
```

Update-এর পরে:

```text
a = 3
b = 5
```

কারণ নতুন `a` হয় পুরোনো `b`, আর নতুন `b` হয় পুরোনো `a + b`।

### Why Multiple Assignment Is Useful

একই কাজ temporary variable ব্যবহার করেও করা যায়:

```python
a = 2
b = 3

next_number = a + b
a = b
b = next_number

print(a, b)
```

Output:

```text
3 5
```

এখানে `next_number` সাময়িকভাবে পরবর্তী Fibonacci number ধরে রাখে।

**সতর্কতা:** আগে `a = b` করে ফেললে এবং তারপর `a + b` হিসাব করলে আগের `a`-এর value হারিয়ে যেতে পারে। তাই multiple assignment অথবা temporary variable ব্যবহার করা ভালো।

## 5. Dry Run of the Fibonacci Series

Code:

```python
a = 0
b = 1

for i in range(6):
    print(a, end=" ")
    a, b = b, a + b
```

### Dry Run Table

| Iteration | Printed `a` | Old `b` | New `a` | New `b` |
|---:|---:|---:|---:|---:|
| 1 | 0 | 1 | 1 | 1 |
| 2 | 1 | 1 | 1 | 2 |
| 3 | 1 | 2 | 2 | 3 |
| 4 | 2 | 3 | 3 | 5 |
| 5 | 3 | 5 | 5 | 8 |
| 6 | 5 | 8 | 8 | 13 |

### Output

```text
0 1 1 2 3 5
```

প্রতিটি iteration-এ প্রথমে বর্তমান `a` print হয়, তারপর দুটি variable update হয়।

## 6. Taking User Input for the Number of Terms

এবার user কতটি term চান, তা input হিসেবে নেওয়া হবে।

### Code

```python
terms = int(input("How many terms? "))

a = 0
b = 1

if terms <= 0:
    print("Enter a positive number of terms.")
else:
    for i in range(terms):
        print(a, end=" ")
        a, b = b, a + b
```

### Sample Input and Output

```text
How many terms? 7
0 1 1 2 3 5 8
```

### Explanation

- `terms` নির্ধারণ করে কতটি সংখ্যা print হবে।
- `terms <= 0` হলে input গ্রহণ করা হয় না।
- `range(terms)` ঠিক `terms` বার loop চালায়।
- প্রতিবার একটি Fibonacci number print হয়।

উদাহরণ:

- `terms = 1` হলে: `0`
- `terms = 2` হলে: `0 1`
- `terms = 5` হলে: `0 1 1 2 3`

এখানে input একটি valid integer হবে বলে ধরে নেওয়া হয়েছে।

## 7. Fibonacci Series Using a `while` Loop

একই series `while` loop দিয়েও তৈরি করা যায়।

### Code

```python
terms = 10

a = 0
b = 1
count = 0

while count < terms:
    print(a, end=" ")
    a, b = b, a + b
    count += 1
```

### Output

```text
0 1 1 2 3 5 8 13 21 34
```

### Explanation

- `count = 0` দিয়ে iteration গণনা শুরু হয়।
- `while count < terms` নির্দিষ্ট সংখ্যক term নিশ্চিত করে।
- `a` print হওয়ার পর Fibonacci variables update হয়।
- `count += 1` প্রতিবার counter বাড়ায়।
- `count` ১০ হলে loop শেষ হয়।

**মনে রাখবে:** `count += 1` বাদ দিলে loop শেষ হবে না।

## 8. Fibonacci Series with User Input Using `while`

### Code

```python
terms = int(input("How many terms? "))

a = 0
b = 1
count = 0

if terms <= 0:
    print("Enter a positive number of terms.")
else:
    while count < terms:
        print(a, end=" ")
        a, b = b, a + b
        count += 1
```

### Sample Input and Output

```text
How many terms? 5
0 1 1 2 3
```

এখানে `while` loop ব্যবহার করে user-এর নির্ধারিত সংখ্যক term print করা হয়।

## 9. Generating Fibonacci Numbers up to a Limit

কখনো নির্দিষ্ট সংখ্যক term নয়, বরং একটি maximum value পর্যন্ত Fibonacci number print করতে হয়।

যেমন, ৫০-এর সমান বা ছোট Fibonacci number-গুলো:

```text
0 1 1 2 3 5 8 13 21 34
```

### Code

```python
limit = 50

a = 0
b = 1

while a <= limit:
    print(a, end=" ")
    a, b = b, a + b
```

### Output

```text
0 1 1 2 3 5 8 13 21 34
```

### Explanation

এখানে condition:

```python
while a <= limit:
```

বর্তমান Fibonacci number limit-এর সমান বা ছোট থাকা পর্যন্ত loop চালায়।

`a`-এর পরবর্তী value ৫৫ হলে condition মিথ্যা হয়ে যায় এবং loop শেষ হয়।

**পার্থক্য:**

- নির্দিষ্ট সংখ্যক term চাইলে counter ব্যবহার করো।
- নির্দিষ্ট value-এর মধ্যে Fibonacci number চাইলে value-based condition ব্যবহার করো।

## 10. Finding Fibonacci Numbers up to a User-Defined Limit

### Code

```python
limit = int(input("Enter the maximum limit: "))

a = 0
b = 1

while a <= limit:
    print(a, end=" ")
    a, b = b, a + b
```

### Sample Input and Output

```text
Enter the maximum limit: 20
0 1 1 2 3 5 8 13
```

এখানে ২০-এর সমান বা ছোট সব Fibonacci number print হয়।

যদি limit negative হয়, তাহলে `a = 0` থেকে শুরু করায় loop একবারও চলবে না। প্রয়োজন হলে negative limit-এর জন্য আলাদা validation message যোগ করা যায়।

## 11. Storing Fibonacci Numbers in a List

কখনো Fibonacci number print না করে list-এর মধ্যে সংরক্ষণ করতে হয়।

### Code

```python
terms = 8

a = 0
b = 1
fibonacci = []

for i in range(terms):
    fibonacci.append(a)
    a, b = b, a + b

print(fibonacci)
```

### Output

```text
[0, 1, 1, 2, 3, 5, 8, 13]
```

### Explanation

- `fibonacci = []` একটি খালি list তৈরি করে।
- `append(a)` বর্তমান term list-এ যোগ করে।
- Variables update করে পরবর্তী term তৈরি হয়।
- শেষে সম্পূর্ণ list print হয়।

এভাবে list-এ রাখা Fibonacci number পরে search, indexing বা অন্য calculation-এ ব্যবহার করা যায়।

## 12. Calculating the Sum of Fibonacci Terms

একটি নির্দিষ্ট সংখ্যক Fibonacci term-এর sum বের করা যায়।

### Code

```python
terms = 7

a = 0
b = 1
total = 0

for i in range(terms):
    total += a
    a, b = b, a + b

print("Sum:", total)
```

### Output

```text
Sum: 20
```

কারণ প্রথম সাতটি term হলো:

`0, 1, 1, 2, 3, 5, 8`

তাদের যোগফল:

`0 + 1 + 1 + 2 + 3 + 5 + 8 = 20`

এখানে `total` একটি accumulator, যা প্রতিটি term-এর যোগফল জমা রাখে।

## 13. Common Mistakes

### Mistake 1: Updating Variables in the Wrong Order

ভুল:

```python
a = 0
b = 1

a = b
b = a + b

print(a, b)
```

Output:

```text
1 2
```

এখানে নতুন `a` বসানোর পর `b = a + b` হিসাব হয়েছে। ফলে পুরোনো `a`-এর value হারিয়ে গেছে।

সঠিক:

```python
a, b = b, a + b
```

অথবা temporary variable ব্যবহার করো।

### Mistake 2: Printing `b` Instead of `a`

```python
a = 0
b = 1

for i in range(5):
    print(b, end=" ")
    a, b = b, a + b
```

Output:

```text
1 1 2 3 5
```

এটি শুরুতেই `1` print করে, তাই প্রচলিত `0, 1, 1, 2, ...` sequence-এর প্রথম term বাদ পড়ে যায়।

প্রচলিত sequence দিয়ে শুরু করতে চাইলে `print(a, end=" ")` ব্যবহার করো।

### Mistake 3: Forgetting the Counter Update

ভুল:

```python
count = 0

while count < 5:
    print(a, end=" ")
    a, b = b, a + b
```

এখানে `count` বাড়ছে না, তাই loop শেষ হবে না।

সঠিক:

```python
count += 1
```

### Mistake 4: Using the Wrong Number of Terms

```python
for i in range(terms):
```

এখানে loop ঠিক `terms` বার চলে। কিন্তু:

```python
for i in range(terms + 1):
```

লিখলে loop `terms + 1` বার চলবে।

যদি ঠিক ১০টি term প্রয়োজন হয়, তাহলে `range(10)` ব্যবহার করতে হবে।

### Mistake 5: Confusing Terms with the Maximum Limit

`terms = 10` মানে ১০টি Fibonacci number print করতে হবে।

অন্যদিকে `limit = 10` মানে ১০-এর সমান বা ছোট Fibonacci number print করতে হবে।

দুটি শর্ত এক নয়।

## 14. Practice Exercises

### Exercise 1

`for` loop ব্যবহার করে প্রথম ১০টি Fibonacci term print করো।

### Exercise 2

User-এর কাছ থেকে term-এর সংখ্যা নিয়ে Fibonacci Series তৈরি করো।

### Exercise 3

`while` loop ব্যবহার করে প্রথম ৮টি Fibonacci term print করো।

### Exercise 4

৫০-এর সমান বা ছোট সব Fibonacci number print করো।

### Exercise 5

প্রথম ৬টি Fibonacci term-এর sum বের করো।

### Exercise 6

প্রথম ৭টি Fibonacci term একটি list-এ সংরক্ষণ করো।

### Exercise 7

নিচের code-এর output নির্ণয় করো:

```python
a = 0
b = 1

for i in range(5):
    print(a, end=" ")
    a, b = b, a + b
```

### Exercise 8

নিচের code-এ ভুলটি খুঁজে বের করো:

```python
a = 0
b = 1
count = 0

while count < 5:
    print(a, end=" ")
    a, b = b, a + b
```

### Exercise 9

`a, b = b, a + b` line-টি কী কাজ করে, ব্যাখ্যা করো।

### Exercise 10

User-এর দেওয়া maximum limit পর্যন্ত Fibonacci number print করো।

## 15. Practice Answer Key

### Answer 1

```python
a = 0
b = 1

for i in range(10):
    print(a, end=" ")
    a, b = b, a + b
```

Output:

```text
0 1 1 2 3 5 8 13 21 34
```

### Answer 2

```python
terms = int(input("Enter number of terms: "))

a = 0
b = 1

if terms <= 0:
    print("Enter a positive number.")
else:
    for i in range(terms):
        print(a, end=" ")
        a, b = b, a + b
```

### Answer 3

```python
a = 0
b = 1
count = 0

while count < 8:
    print(a, end=" ")
    a, b = b, a + b
    count += 1
```

Output:

```text
0 1 1 2 3 5 8 13
```

### Answer 4

```python
a = 0
b = 1

while a <= 50:
    print(a, end=" ")
    a, b = b, a + b
```

Output:

```text
0 1 1 2 3 5 8 13 21 34
```

### Answer 5

```python
a = 0
b = 1
total = 0

for i in range(6):
    total += a
    a, b = b, a + b

print(total)
```

Output:

```text
12
```

কারণ প্রথম ছয়টি term-এর sum হলো `0 + 1 + 1 + 2 + 3 + 5 = 12`।

### Answer 6

```python
a = 0
b = 1
fibonacci = []

for i in range(7):
    fibonacci.append(a)
    a, b = b, a + b

print(fibonacci)
```

Output:

```text
[0, 1, 1, 2, 3, 5, 8]
```

### Answer 7

Output:

```text
0 1 1 2 3
```

### Answer 8

এখানে `count` বাড়ানো হয়নি। তাই condition সবসময় সত্য থাকে এবং loop শেষ হয় না।

সঠিক code:

```python
a = 0
b = 1
count = 0

while count < 5:
    print(a, end=" ")
    a, b = b, a + b
    count += 1
```

### Answer 9

এই line-টি পুরোনো `b`-কে নতুন `a` এবং পুরোনো `a + b`-কে নতুন `b` হিসেবে সেট করে। এর ফলে পরবর্তী Fibonacci number তৈরি হয়।

### Answer 10

```python
limit = int(input("Enter maximum limit: "))

a = 0
b = 1

while a <= limit:
    print(a, end=" ")
    a, b = b, a + b
```

এই code-এ non-negative maximum limit ধরে নেওয়া হয়েছে।

## 16. Chapter Summary

- Fibonacci Series-এ প্রতিটি নতুন term আগের দুটি term-এর যোগফল।
- প্রচলিত sequence শুরু হয় `0, 1, 1, 2, 3, 5, ...` দিয়ে।
- `a` ও `b` variable দিয়ে আগের দুটি term রাখা যায়।
- `a, b = b, a + b` পরবর্তী term তৈরি করে।
- `for` loop নির্দিষ্ট সংখ্যক term-এর জন্য উপযোগী।
- `while` loop নির্দিষ্ট সংখ্যক term অথবা maximum limit পর্যন্ত sequence তৈরি করতে পারে।
- `append()` ব্যবহার করে term-গুলো list-এ রাখা যায়।
- Accumulator ব্যবহার করে Fibonacci term-এর sum বের করা যায়।
- Variable update ও counter update সঠিক না হলে ভুল output বা infinite loop হতে পারে।

## 17. Completion Checklist

- [ ] Fibonacci Series-এর নিয়ম বুঝি।
- [ ] `for` loop দিয়ে Fibonacci Series তৈরি করতে পারি।
- [ ] `while` loop দিয়ে Fibonacci Series তৈরি করতে পারি।
- [ ] User input নিয়ে term-এর সংখ্যা নির্ধারণ করতে পারি।
- [ ] Maximum limit পর্যন্ত Fibonacci number print করতে পারি।
- [ ] Fibonacci number list-এ সংরক্ষণ করতে পারি।
- [ ] Fibonacci term-এর sum বের করতে পারি।
- [ ] Dry run table তৈরি করতে পারি।
- [ ] Variable update-এর ভুল শনাক্ত করতে পারি।

**Next Topic:** `56_Prime_Number_Checking_Using_Loops.md`