# 53. Multiplication Table Programs

## 1. Introduction

Multiplication table হলো কোনো সংখ্যাকে ১, ২, ৩ ইত্যাদি দিয়ে গুণ করে ফলাফল দেখানো।

উদাহরণস্বরূপ, ৫-এর multiplication table:

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
```

Python-এ loop ব্যবহার করে সহজেই multiplication table তৈরি করা যায়। প্রতিটি লাইন আলাদাভাবে লিখতে হয় না।

এই Topic-এ আমরা শিখব:

- `for` loop দিয়ে multiplication table
- `while` loop দিয়ে multiplication table
- User input ব্যবহার করা
- নির্দিষ্ট range পর্যন্ত table তৈরি করা
- একাধিক multiplication table তৈরি করা
- Nested loop ব্যবহার করা
- Reverse multiplication table
- Common mistakes ও practice problems

## 2. Basic Multiplication Table Using a `for` Loop

প্রথমে ৫-এর multiplication table তৈরি করি।

### Code

```python
number = 5

for i in range(1, 11):
    print(number, "x", i, "=", number * i)
```

### Output

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

- `number = 5` হলো যে সংখ্যার table তৈরি হবে।
- `range(1, 11)` ১ থেকে ১০ পর্যন্ত সংখ্যা তৈরি করে।
- `i` প্রতিবার multiplier হিসেবে কাজ করে।
- `number * i` গুণফল বের করে।
- `print()` প্রতিটি লাইন প্রদর্শন করে।

**মনে রাখবে:** `range(1, 11)`-এ ১১ অন্তর্ভুক্ত হয় না, তাই শেষ multiplier হলো ১০।

## 3. Multiplication Table Using an `f-string`

`f-string` ব্যবহার করলে output আরও সুন্দরভাবে লেখা যায়।

### Code

```python
number = 7

for i in range(1, 11):
    print(f"{number} x {i} = {number * i}")
```

### Output

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

### Explanation

`f-string`-এর মধ্যে `{}` ব্যবহার করে variable ও expression-এর value output-এ দেখানো যায়।

যেমন:

```python
print(f"{number} x {i} = {number * i}")
```

যদি `number = 7` এবং `i = 3` হয়, তাহলে output হবে:

```text
7 x 3 = 21
```

## 4. Taking User Input

ব্যবহারকারীর কাছ থেকে একটি সংখ্যা নিয়ে তার multiplication table তৈরি করা যায়।

### Code

```python
number = int(input("Enter a number: "))

for i in range(1, 11):
    print(f"{number} x {i} = {number * i}")
```

### Sample Input and Output

```text
Enter a number: 8
8 x 1 = 8
8 x 2 = 16
8 x 3 = 24
8 x 4 = 32
8 x 5 = 40
8 x 6 = 48
8 x 7 = 56
8 x 8 = 64
8 x 9 = 72
8 x 10 = 80
```

### Explanation

- `input()` ব্যবহারকারীর কাছ থেকে value নেয়।
- `int()` input-কে integer-এ রূপান্তর করে।
- Loop ১ থেকে ১০ পর্যন্ত চলে।
- প্রতিটি iteration-এ multiplication result print হয়।

এখানে input-টি integer-এ রূপান্তর করা সম্ভব হবে বলে ধরে নেওয়া হয়েছে।

## 5. Multiplication Table up to a Custom Limit

সব সময় ১০ পর্যন্ত table প্রয়োজন হয় না। ব্যবহারকারী চাইলে limit নির্ধারণ করতে পারেন।

### Code

```python
number = int(input("Enter a number: "))
limit = int(input("Enter the limit: "))

for i in range(1, limit + 1):
    print(f"{number} x {i} = {number * i}")
```

### Sample Input and Output

```text
Enter a number: 4
Enter the limit: 5
4 x 1 = 4
4 x 2 = 8
4 x 3 = 12
4 x 4 = 16
4 x 5 = 20
```

### Explanation

এখানে `limit + 1` ব্যবহার করা হয়েছে, কারণ `range()`-এর stop value অন্তর্ভুক্ত হয় না।

যদি `limit = 5` হয়, তাহলে `range(1, 6)` থেকে ১, ২, ৩, ৪, ৫ পাওয়া যায়।

## 6. Multiplication Table Using a `while` Loop

একই কাজ `while` loop দিয়েও করা যায়।

### Code

```python
number = 6
i = 1

while i <= 10:
    print(f"{number} x {i} = {number * i}")
    i += 1
```

### Output

```text
6 x 1 = 6
6 x 2 = 12
6 x 3 = 18
6 x 4 = 24
6 x 5 = 30
6 x 6 = 36
6 x 7 = 42
6 x 8 = 48
6 x 9 = 54
6 x 10 = 60
```

### Explanation

- `i = 1` দিয়ে শুরু হয়।
- `while i <= 10` condition পরীক্ষা করে।
- Condition সত্য হলে multiplication result print হয়।
- `i += 1` multiplier এক বাড়ায়।
- `i`-এর মান ১০ ছাড়ালে loop শেষ হয়।

**গুরুত্বপূর্ণ:** `i += 1` বাদ দিলে loop অনন্তকাল চলতে পারে।

## 7. Dry Run of a Multiplication Table

Code:

```python
number = 3

for i in range(1, 4):
    print(f"{number} x {i} = {number * i}")
```

### Dry Run Table

| Iteration | `number` | `i` | `number * i` |
|---:|---:|---:|---:|
| 1 | 3 | 1 | 3 |
| 2 | 3 | 2 | 6 |
| 3 | 3 | 3 | 9 |

### Output

```text
3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
```

প্রতিবার `i`-এর মান পরিবর্তিত হয়, কিন্তু `number` অপরিবর্তিত থাকে।

## 8. Printing Multiple Multiplication Tables

একটি range-এর একাধিক সংখ্যার multiplication table তৈরি করতে outer loop ব্যবহার করা যায়।

### Code

```python
for number in range(1, 6):
    print(f"\nMultiplication table of {number}")

    for i in range(1, 11):
        print(f"{number} x {i} = {number * i}")
```

### Output

```text
Multiplication table of 1
1 x 1 = 1
1 x 2 = 2
...
1 x 10 = 10

Multiplication table of 2
2 x 1 = 2
2 x 2 = 4
...
2 x 10 = 20
```

এখানে `...` দিয়ে মাঝের লাইনগুলো সংক্ষেপে দেখানো হয়েছে। Program চালালে সব লাইন print হবে।

### Explanation

- Outer loop `number`-এর মান ১ থেকে ৫ পর্যন্ত পরিবর্তন করে।
- Inner loop প্রতিটি সংখ্যার জন্য ১ থেকে ১০ পর্যন্ত multiplication করে।
- Outer loop-এর প্রতিটি iteration-এ একটি নতুন table তৈরি হয়।

এটি nested loop-এর একটি বাস্তব উদাহরণ।

## 9. Understanding Nested Loops in Multiplication Tables

Nested loop হলো একটি loop-এর ভেতরে আরেকটি loop।

```python
for number in range(2, 5):
    for i in range(1, 4):
        print(number, "x", i, "=", number * i)
```

### Output

```text
2 x 1 = 2
2 x 2 = 4
2 x 3 = 6
3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
4 x 1 = 4
4 x 2 = 8
4 x 3 = 12
```

### Execution Process

1. Outer loop-এ `number = 2` হয়।
2. Inner loop `i = 1, 2, 3` নিয়ে চলে।
3. Inner loop শেষ হলে outer loop-এ `number = 3` হয়।
4. Inner loop আবার শুরু থেকে চলে।
5. একইভাবে `number = 4`-এর table তৈরি হয়।

**মনে রাখবে:** প্রতিটি outer iteration-এর জন্য inner loop সম্পূর্ণভাবে চলে।

## 10. Multiplication Table in Reverse Order

কখনো ১০ থেকে ১ পর্যন্ত reverse order-এ table দেখাতে হতে পারে।

### Code

```python
number = 5

for i in range(10, 0, -1):
    print(f"{number} x {i} = {number * i}")
```

### Output

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

### Explanation

`range(10, 0, -1)`-এর অর্থ:

- Start = ১০
- Stop = ০, কিন্তু এটি অন্তর্ভুক্ত নয়
- Step = -১

তাই multiplier ১০ থেকে ১ পর্যন্ত কমে।

## 11. Creating a Table with a `while` Loop and User Input

ব্যবহারকারীর দেওয়া সংখ্যা এবং limit ব্যবহার করে `while` loop চালানো যায়।

### Code

```python
number = int(input("Enter a number: "))
limit = int(input("Enter the limit: "))

i = 1

while i <= limit:
    print(f"{number} x {i} = {number * i}")
    i += 1
```

### Sample Input and Output

```text
Enter a number: 9
Enter the limit: 4
9 x 1 = 9
9 x 2 = 18
9 x 3 = 27
9 x 4 = 36
```

এই program-এ multiplier-এর শুরু ১ এবং শেষ limit পর্যন্ত।

## 12. Printing Multiplication Tables in a Grid

Nested loop ব্যবহার করে multiplication result-গুলো grid আকারে দেখানো যায়।

### Code

```python
for number in range(1, 6):
    for i in range(1, 6):
        print(f"{number * i:4}", end="")
    print()
```

### Output

```text
   1   2   3   4   5
   2   4   6   8  10
   3   6   9  12  15
   4   8  12  16  20
   5  10  15  20  25
```

### Explanation

- Outer loop row নির্ধারণ করে।
- Inner loop column-এর value নির্ধারণ করে।
- `number * i` multiplication result তৈরি করে।
- `:4` প্রতিটি result-এর জন্য চার character-এর field width রাখে।
- `end=""` একই লাইনে result print করে।
- Inner loop শেষ হলে `print()` নতুন line তৈরি করে।

এই code ১ থেকে ৫ পর্যন্ত multiplication grid তৈরি করে; এটি প্রতিটি সংখ্যার আলাদা পূর্ণ table নয়।

## 13. Handling Invalid Limits

ব্যবহারকারী যদি শূন্য বা negative limit দেন, তাহলে table-এর loop নাও চলতে পারে। তাই limit validate করা যায়।

### Code

```python
number = int(input("Enter a number: "))
limit = int(input("Enter a positive limit: "))

if limit <= 0:
    print("Limit must be positive.")
else:
    for i in range(1, limit + 1):
        print(f"{number} x {i} = {number * i}")
```

### Explanation

- `limit <= 0` হলে error message দেখায়।
- Positive limit হলে multiplication table তৈরি হয়।
- এতে অপ্রত্যাশিত empty output এড়ানো যায়।

এই উদাহরণে numeric integer input ধরে নেওয়া হয়েছে।

## 14. Common Mistakes

### Mistake 1: Incorrect `range()` Stop Value

ভুল:

```python
for i in range(1, 10):
    print(5 * i)
```

এটি শুধু ১ থেকে ৯ পর্যন্ত চলে।

১০ পর্যন্ত চাইলে:

```python
for i in range(1, 11):
    print(5 * i)
```

### Mistake 2: Forgetting to Update the `while` Loop

ভুল:

```python
i = 1

while i <= 10:
    print(5 * i)
```

এখানে `i` পরিবর্তন হচ্ছে না, তাই loop শেষ হবে না।

সঠিক:

```python
i = 1

while i <= 10:
    print(5 * i)
    i += 1
```

### Mistake 3: Wrong Indentation

ভুল:

```python
for i in range(1, 4):
print(5 * i)
```

এখানে `print()`-এর indentation নেই, তাই `IndentationError` হবে।

সঠিক:

```python
for i in range(1, 4):
    print(5 * i)
```

### Mistake 4: Updating the Wrong Variable

Nested loop-এ inner loop-এর multiplier `i` সঠিকভাবে update করতে হবে। Outer ও inner variable গুলিয়ে ফেললে ভুল output হতে পারে।

### Mistake 5: Forgetting `print()` After a Grid Row

Grid-এর inner loop-এর পরে `print()` না দিলে সব result একই লাইনে চলে আসবে।

## 15. Practice Exercises

### Exercise 1

`for` loop ব্যবহার করে ১২-এর multiplication table ১ থেকে ১০ পর্যন্ত print করো।

### Exercise 2

ব্যবহারকারীর দেওয়া সংখ্যার table ১ থেকে ১৫ পর্যন্ত তৈরি করো।

### Exercise 3

`while` loop ব্যবহার করে ৭-এর table তৈরি করো।

### Exercise 4

Nested loop ব্যবহার করে ২, ৩ এবং ৪-এর multiplication table ১ থেকে ৫ পর্যন্ত print করো।

### Exercise 5

৯-এর multiplication table ১০ থেকে ১ পর্যন্ত reverse order-এ print করো।

### Exercise 6

ব্যবহারকারীর দেওয়া number ও limit ব্যবহার করে multiplication table তৈরি করো।

### Exercise 7

১ থেকে ৫ পর্যন্ত multiplication grid তৈরি করো।

### Exercise 8

নিচের code-এর output নির্ণয় করো:

```python
for number in range(2, 4):
    for i in range(1, 3):
        print(number * i)
```

### Exercise 9

নিচের code-এ ভুলটি খুঁজে বের করো:

```python
i = 1

while i <= 5:
    print(3 * i)
```

### Exercise 10

এমন একটি program লেখো, যেখানে user একটি positive limit দেবেন এবং program সেই limit পর্যন্ত একটি সংখ্যার multiplication table তৈরি করবে।

## 16. Practice Answer Key

### Answer 1

```python
for i in range(1, 11):
    print(f"12 x {i} = {12 * i}")
```

### Answer 2

```python
number = int(input("Enter a number: "))

for i in range(1, 16):
    print(f"{number} x {i} = {number * i}")
```

### Answer 3

```python
i = 1

while i <= 10:
    print(f"7 x {i} = {7 * i}")
    i += 1
```

### Answer 4

```python
for number in range(2, 5):
    for i in range(1, 6):
        print(f"{number} x {i} = {number * i}")
    print()
```

### Answer 5

```python
for i in range(10, 0, -1):
    print(f"9 x {i} = {9 * i}")
```

### Answer 6

```python
number = int(input("Enter a number: "))
limit = int(input("Enter the limit: "))

for i in range(1, limit + 1):
    print(f"{number} x {i} = {number * i}")
```

### Answer 7

```python
for number in range(1, 6):
    for i in range(1, 6):
        print(f"{number * i:4}", end="")
    print()
```

### Answer 8

Output:

```text
2
4
3
6
```

প্রথমে `number = 2` হলে ২ ও ৪ print হয়। এরপর `number = 3` হলে ৩ ও ৬ print হয়।

### Answer 9

সমস্যা হলো `i`-এর মান বাড়ানো হয়নি। সঠিক code:

```python
i = 1

while i <= 5:
    print(3 * i)
    i += 1
```

### Answer 10

```python
number = int(input("Enter a number: "))
limit = int(input("Enter a positive limit: "))

if limit <= 0:
    print("Limit must be positive.")
else:
    for i in range(1, limit + 1):
        print(f"{number} x {i} = {number * i}")
```

## 17. Chapter Summary

- Multiplication table তৈরিতে loop ব্যবহার করা হয়।
- `for` loop নির্দিষ্ট range-এর জন্য উপযোগী।
- `while` loop ব্যবহার করলে multiplier update করতে হয়।
- User input দিয়ে number ও limit নির্ধারণ করা যায়।
- Nested loop দিয়ে একাধিক table বা multiplication grid তৈরি করা যায়।
- `range(start, stop)`-এ stop value অন্তর্ভুক্ত হয় না।
- Reverse table তৈরিতে negative step ব্যবহার করা যায়।
- `f-string` output-কে সুন্দর ও readable করে।
- সঠিক indentation এবং loop variable update নিশ্চিত করতে হবে।

## 18. Completion Checklist

- [ ] `for` loop দিয়ে multiplication table তৈরি করতে পারি।
- [ ] `while` loop দিয়ে multiplication table তৈরি করতে পারি।
- [ ] User input নিতে পারি।
- [ ] Custom limit ব্যবহার করতে পারি।
- [ ] Reverse multiplication table তৈরি করতে পারি।
- [ ] Nested loop দিয়ে একাধিক table তৈরি করতে পারি।
- [ ] Multiplication grid তৈরি করতে পারি।
- [ ] `range()`-এর stop value বুঝি।
- [ ] Infinite loop ও indentation error ঠিক করতে পারি।

**Next Topic:** `54_Factorial_Using_Loops.md`