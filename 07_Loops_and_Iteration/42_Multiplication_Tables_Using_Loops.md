# 42. Multiplication Tables Using Loops

## 1. Introduction

Multiplication table হলো কোনো সংখ্যাকে ১, ২, ৩, ৪ ইত্যাদি দিয়ে গুণ করে ফলাফল বের করার তালিকা।

উদাহরণস্বরূপ, ৫-এর multiplication table:

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
```

একটি একটি করে line লিখলে অনেক code প্রয়োজন হয়। কিন্তু loop ব্যবহার করলে অল্প code দিয়ে পুরো table তৈরি করা যায়।

## 2. Basic Multiplication Table Using a `for` Loop

প্রথমে একটি সংখ্যার table তৈরি করি।

```python
number = 5

for multiplier in range(1, 11):
    result = number * multiplier
    print(number, "x", multiplier, "=", result)
```

**Output:**

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

### Explanation

- `number = 5` দিয়ে যে সংখ্যার table তৈরি করব, সেটি নির্ধারণ করেছি।
- `range(1, 11)` multiplier-কে ১ থেকে ১০ পর্যন্ত মান দেয়।
- `number * multiplier` দিয়ে গুণফল বের হয়।
- `print()` প্রতিটি result নতুন line-এ দেখায়।

**মনে রাখবে:** `range(1, 11)`-এ `11` অন্তর্ভুক্ত হয় না। তাই multiplier-এর শেষ মান হয় `10`।

## 3. Multiplication Table Using User Input

ব্যবহারকারীর কাছ থেকে সংখ্যা নিয়েও table তৈরি করা যায়।

```python
number = int(input("Enter a number: "))

for multiplier in range(1, 11):
    print(number, "x", multiplier, "=", number * multiplier)
```

**Example Input:**

```text
Enter a number: 7
```

**Output:**

```text
7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
7 x 4 = 28
7 x 5 = 35
7 x 6 = 42
7 x 7 = 49
7 x 8 = 56
7 x 9 = 63
7 x 10 = 70
```

এখানে `input()` string দেয়, তাই `int()` দিয়ে সেটিকে integer-এ convert করা হয়েছে।

**Note:** এই উদাহরণে user একটি valid integer দেবে ধরে নেওয়া হয়েছে। অন্য ধরনের input দিলে `ValueError` হতে পারে।

## 4. Multiplication Table Using a `while` Loop

একই কাজ `while` loop দিয়েও করা যায়।

```python
number = 5
multiplier = 1

while multiplier <= 10:
    result = number * multiplier
    print(number, "x", multiplier, "=", result)

    multiplier += 1
```

**Output:**

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

### Explanation

1. `multiplier = 1` দিয়ে শুরু করা হয়েছে।
2. `multiplier <= 10` condition পরীক্ষা করা হয়।
3. Condition সত্য হলে গুণফল বের করে print করা হয়।
4. `multiplier += 1` multiplier বাড়ায়।
5. multiplier `11` হলে condition false হয় এবং loop শেষ হয়।

**গুরুত্বপূর্ণ:** `multiplier += 1` না থাকলে loop অনির্দিষ্টকাল চলতে পারে।

## 5. Using Nested Loops for Multiple Tables

Nested loop ব্যবহার করে একসঙ্গে একাধিক সংখ্যার table তৈরি করা যায়।

### Example: Tables from 1 to 3

```python
for number in range(1, 4):
    for multiplier in range(1, 6):
        print(number, "x", multiplier, "=", number * multiplier)

    print()
```

**Output:**

```text
1 x 1 = 1
1 x 2 = 2
1 x 3 = 3
1 x 4 = 4
1 x 5 = 5

2 x 1 = 2
2 x 2 = 4
2 x 3 = 6
2 x 4 = 8
2 x 5 = 10

3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
3 x 4 = 12
3 x 5 = 15
```

### Explanation

- Outer loop `number`-এর মান ১, ২ ও ৩ নির্ধারণ করে।
- Inner loop প্রতিটি সংখ্যার জন্য multiplier ১ থেকে ৫ পর্যন্ত চালায়।
- প্রতিটি table শেষ হলে `print()` একটি blank line তৈরি করে।

এখানে outer loop ৩ বার এবং inner loop প্রতিবার ৫ বার চলে। তাই মোট multiplication হয়:

\[
3 \times 5 = 15
\]

## 6. Creating the Full Multiplication Tables from 1 to 10

এবার ১ থেকে ১০ পর্যন্ত সব সংখ্যার table তৈরি করি।

```python
for number in range(1, 11):
    print("Multiplication Table of", number)

    for multiplier in range(1, 11):
        print(number, "x", multiplier, "=", number * multiplier)

    print()
```

এই program মোট ১০টি multiplication table তৈরি করবে। প্রতিটি table-এ ১০টি multiplication থাকবে।

মোট multiplication:

\[
10 \times 10 = 100
\]

প্রতিটি table-এর শুরুতে শিরোনাম এবং শেষে একটি blank line থাকবে।

## 7. Formatted Multiplication Table

Output সুন্দরভাবে সাজাতে f-string ব্যবহার করা যায়।

```python
number = 7

for multiplier in range(1, 11):
    result = number * multiplier
    print(f"{number} x {multiplier:2} = {result:3}")
```

**Output:**

```text
7 x  1 =   7
7 x  2 =  14
7 x  3 =  21
7 x  4 =  28
7 x  5 =  35
7 x  6 =  42
7 x  7 =  49
7 x  8 =  56
7 x  9 =  63
7 x 10 =  70
```

এখানে:

- `{multiplier:2}` multiplier-এর জন্য অন্তত ২ character-এর জায়গা রাখে।
- `{result:3}` result-এর জন্য অন্তত ৩ character-এর জায়গা রাখে।
- ছোট সংখ্যার আগে প্রয়োজন অনুযায়ী space যোগ হয়।

Width নির্ধারণ করলে মান বড় হলে Python সেটিকে কাটে না; প্রয়োজন হলে নির্ধারিত width-এর চেয়ে বেশি জায়গা ব্যবহার করে।

## 8. Multiplication Table in Reverse Order

চাইলে table উল্টো দিক থেকেও print করা যায়।

```python
number = 5

for multiplier in range(10, 0, -1):
    print(number, "x", multiplier, "=", number * multiplier)
```

**Output:**

```text
5 x 10 = 50
5 x 9 = 45
5 x 8 = 40
5 x 7 = 35
5 x 6 = 30
5 x 5 = 25
5 x 4 = 20
5 x 3 = 15
5 x 2 = 10
5 x 1 = 5
```

এখানে `range(10, 0, -1)` দিয়ে ১০ থেকে ১ পর্যন্ত গণনা করা হয়েছে।

- Start: `10`
- Stop: `0` — অন্তর্ভুক্ত নয়
- Step: `-1`

## 9. Taking the Start and End of a Table

ব্যবহারকারী কত থেকে কত পর্যন্ত table দেখতে চায়, সেটিও নির্ধারণ করতে পারে।

```python
number = int(input("Enter a number: "))
start = int(input("Enter starting multiplier: "))
end = int(input("Enter ending multiplier: "))

for multiplier in range(start, end + 1):
    print(number, "x", multiplier, "=", number * multiplier)
```

**Example Input:**

```text
Enter a number: 4
Enter starting multiplier: 3
Enter ending multiplier: 7
```

**Output:**

```text
4 x 3 = 12
4 x 4 = 16
4 x 5 = 20
4 x 6 = 24
4 x 7 = 28
```

এখানে `end + 1` ব্যবহার করা হয়েছে, কারণ `range()`-এর stop value অন্তর্ভুক্ত হয় না।

এই উদাহরণে start ও end integer এবং `start <= end` ধরে নেওয়া হয়েছে।

## 10. Dry Run of a Multiplication Table

Code:

```python
number = 3

for multiplier in range(1, 4):
    print(number, "*", multiplier, "=", number * multiplier)
```

### Dry Run Table

| Iteration | `number` | `multiplier` | Calculation | Output |
|---:|---:|---:|---|---|
| 1 | 3 | 1 | \(3 \times 1 = 3\) | `3 * 1 = 3` |
| 2 | 3 | 2 | \(3 \times 2 = 6\) | `3 * 2 = 6` |
| 3 | 3 | 3 | \(3 \times 3 = 9\) | `3 * 3 = 9` |

এখানে multiplier-এর মান প্রতিবার বাড়ছে, কিন্তু `number` অপরিবর্তিত থাকছে।

## 11. Common Mistakes

### Mistake 1: Incorrect `range()` Stop Value

```python
for multiplier in range(1, 10):
    print(5 * multiplier)
```

এখানে multiplier ১ থেকে ৯ পর্যন্ত চলে। ১০-এর table line পাওয়া যায় না।

১০ পর্যন্ত চাইলে:

```python
for multiplier in range(1, 11):
    print(5 * multiplier)
```

### Mistake 2: Forgetting to Update a `while` Loop

```python
multiplier = 1

while multiplier <= 10:
    print(5 * multiplier)
```

এখানে multiplier বাড়ছে না। তাই loop শেষ হবে না।

### Mistake 3: Incorrect Indentation

Nested loop-এ multiplication-এর statement inner loop-এর ভেতরে থাকতে হবে। অন্যথায় প্রতিটি multiplier-এর জন্য সঠিক output তৈরি নাও হতে পারে।

### Mistake 4: Forgetting `int()` for Input

```python
number = input("Enter a number: ")
```

এখানে `number` string হবে। তাই numeric multiplication করার আগে integer-এ convert করতে হবে, যদি integer input প্রত্যাশিত হয়।

### Mistake 5: Forgetting `end + 1`

যদি user-এর দেওয়া শেষ multiplier-টিও অন্তর্ভুক্ত করতে হয়, তাহলে `range(start, end + 1)` ব্যবহার করতে হবে।

## 12. Practice Exercises

### Exercise 1: Write a Program

User-এর কাছ থেকে একটি সংখ্যা নিয়ে তার ১ থেকে ১০ পর্যন্ত multiplication table print করো।

### Exercise 2: Find the Output

```python
for multiplier in range(1, 5):
    print(4, "x", multiplier, "=", 4 * multiplier)
```

### Exercise 3: Count the Multiplications

```python
for number in range(1, 6):
    for multiplier in range(1, 11):
        print(number * multiplier)
```

মোট কতবার multiplication হবে?

### Exercise 4: Find the Output

```python
for number in range(2, 4):
    for multiplier in range(1, 4):
        print(number * multiplier, end=" ")
    print()
```

### Exercise 5: Write a Program

Nested loop ব্যবহার করে ১ থেকে ৫ পর্যন্ত সংখ্যার table তৈরি করো, যেখানে প্রতিটি table ১ থেকে ৩ পর্যন্ত multiplier ব্যবহার করবে।

### Exercise 6: Fix the Code

```python
number = 6
multiplier = 1

while multiplier <= 10:
    print(number, "x", multiplier, "=", number * multiplier)
```

কেন loop শেষ হচ্ছে না? Code-টি ঠিক করো।

## 13. Practice Answer Key

### Answer 1

```python
number = int(input("Enter a number: "))

for multiplier in range(1, 11):
    print(number, "x", multiplier, "=", number * multiplier)
```

### Answer 2

```text
4 x 1 = 4
4 x 2 = 8
4 x 3 = 12
4 x 4 = 16
```

### Answer 3

Outer loop ৫ বার এবং inner loop প্রতিবার ১০ বার চলে।

মোট multiplication:

\[
5 \times 10 = 50
\]

### Answer 4

```text
2 4 6
3 6 9
```

প্রথম line-এ ২-এর table এবং দ্বিতীয় line-এ ৩-এর table-এর প্রথম তিনটি result print হয়।

### Answer 5

```python
for number in range(1, 6):
    for multiplier in range(1, 4):
        print(number, "x", multiplier, "=", number * multiplier)

    print()
```

### Answer 6

সমস্যা হলো `multiplier` update করা হয়নি।

সঠিক code:

```python
number = 6
multiplier = 1

while multiplier <= 10:
    print(number, "x", multiplier, "=", number * multiplier)
    multiplier += 1
```

## 14. Chapter Summary

- `for` loop দিয়ে একটি সংখ্যার multiplication table তৈরি করা যায়।
- `while` loop দিয়েও একই কাজ করা যায়।
- Nested loop দিয়ে একসঙ্গে একাধিক table তৈরি করা যায়।
- `range()`-এর stop value অন্তর্ভুক্ত হয় না।
- f-string দিয়ে output সুন্দরভাবে সাজানো যায়।
- Reverse table-এর জন্য negative step ব্যবহার করা যায়।
- `while` loop-এ multiplier update করতে ভুললে infinite loop হতে পারে।

## 15. Completion Checklist

- [ ] `for` loop দিয়ে একটি table তৈরি করতে পারি।
- [ ] `while` loop দিয়ে একটি table তৈরি করতে পারি।
- [ ] User input নিয়ে table তৈরি করতে পারি।
- [ ] Nested loop দিয়ে একাধিক table তৈরি করতে পারি।
- [ ] f-string দিয়ে output format করতে পারি।
- [ ] Reverse multiplication table তৈরি করতে পারি।
- [ ] Dry run করে multiplication-এর output বের করতে পারি।

**Next Topic:** `43_Printing_Star_Patterns.md`
