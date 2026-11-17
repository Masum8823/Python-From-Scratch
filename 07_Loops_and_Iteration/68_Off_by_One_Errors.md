# 68. Off-by-One Errors

## 1. Introduction

Off-by-one error হলো এমন একটি programming mistake, যেখানে loop প্রত্যাশার চেয়ে **একবার বেশি অথবা একবার কম** execute হয়।

ধরি, আমরা `1` থেকে `5` পর্যন্ত সংখ্যা print করতে চাই।

কিন্তু ভুল condition বা `range()` ব্যবহার করার কারণে program শুধু `1` থেকে `4` পর্যন্ত print করল। এটি একটি off-by-one error।

### Example

ভুল code:

```python
for number in range(1, 5):
    print(number)
```

Output:

```text
1
2
3
4
```

কিন্তু আমাদের প্রয়োজন ছিল:

```text
1
2
3
4
5
```

সঠিক code:

```python
for number in range(1, 6):
    print(number)
```

এখানে `range(1, 6)` ব্যবহার করতে হয়েছে, কারণ `range()`-এর stop value অন্তর্ভুক্ত হয় না।

### Learning Objectives

এই Topic শেষে তুমি পারবে:

- Off-by-one error শনাক্ত করতে।
- `range()`-এর start ও stop value সঠিকভাবে ব্যবহার করতে।
- `<` ও `<=`-এর পার্থক্য বুঝতে।
- Loop-এর iteration count নির্ণয় করতে।
- `while` loop-এ boundary error ঠিক করতে।
- List indexing-সংক্রান্ত ভুল এড়াতে।

## 2. Why Do Off-by-One Errors Happen?

Off-by-one error সাধারণত কয়েকটি কারণে ঘটে:

1. `range()`-এর stop value অন্তর্ভুক্ত মনে করা।
2. `<` ও `<=` ভুলভাবে ব্যবহার করা।
3. Loop-এর শুরু ও শেষের value ভুল নির্ধারণ করা।
4. List-এর index এবং element count গুলিয়ে ফেলা।
5. Loop variable ভুল সময়ে update করা।
6. Loop কতবার চলবে তা ঠিকভাবে গণনা না করা।

এই ভুলগুলো ছোট মনে হলেও output বা calculation ভুল করে দিতে পারে।

## 3. Understanding the Stop Value of `range()`

Python-এর `range()` function-এ stop value অন্তর্ভুক্ত হয় না।

Syntax:

```python
range(start, stop, step)
```

এখানে:

- `start`: শুরু করার value, অন্তর্ভুক্ত।
- `stop`: যে value-তে পৌঁছানোর আগে sequence থামে; এটি অন্তর্ভুক্ত নয়।
- `step`: কত করে value বাড়বে বা কমবে।

### Example 1

```python
for number in range(1, 5):
    print(number)
```

Output:

```text
1
2
3
4
```

এখানে `5` অন্তর্ভুক্ত নয়।

### Example 2

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

**Rule:** `1` থেকে `n` পর্যন্ত integer অন্তর্ভুক্ত করতে চাইলে সাধারণত `range(1, n + 1)` ব্যবহার করবে।

## 4. Understanding `<` and `<=` in a `while` Loop

`while` loop-এ condition-এর boundary সঠিকভাবে নির্বাচন করতে হয়।

### Example 1: Using `<`

```python
number = 1

while number < 5:
    print(number)
    number += 1
```

Output:

```text
1
2
3
4
```

কারণ `number = 5` হলে `number < 5` False হয়।

### Example 2: Using `<=`

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

Output:

```text
1
2
3
4
5
```

এখানে `5`-ও অন্তর্ভুক্ত হয়েছে।

### Comparison

| Condition | Output values | Iterations |
|---|---|---:|
| `number < 5` | 1–4 | 4 |
| `number <= 5` | 1–5 | 5 |

**মনে রাখবে:** শেষ value অন্তর্ভুক্ত করতে হবে কি না, সেটি problem-এর requirement দেখে ঠিক করবে।

## 5. Calculating the Number of Iterations

Loop কতবার চলবে তা আগে থেকে হিসাব করতে পারলে off-by-one error কম হয়।

### Example 1

```python
for number in range(5):
    print(number)
```

Output:

```text
0
1
2
3
4
```

Iteration count: `5`

কারণ `range(5)` থেকে পাঁচটি value পাওয়া যায়।

### Example 2

```python
for number in range(2, 8):
    print(number)
```

Output:

```text
2
3
4
5
6
7
```

Iteration count: `6`

এখানে start `2` এবং stop `8`। Step `1` হলে start ও stop-এর পার্থক্য:

\[
8-2=6
\]

### Example 3

```python
for number in range(1, 11, 2):
    print(number)
```

Output:

```text
1
3
5
7
9
```

Iteration count: `5`

এখানে step `2`, তাই প্রতিবার দুই করে বাড়ছে।

## 6. Off-by-One Error in Summation

ধরি, `1` থেকে `10` পর্যন্ত সব সংখ্যার sum বের করতে হবে।

ভুল code:

```python
total = 0

for number in range(1, 10):
    total += number

print(total)
```

Output:

```text
45
```

এখানে `10` যোগ হয়নি।

সঠিক code:

```python
total = 0

for number in range(1, 11):
    total += number

print(total)
```

Output:

```text
55
```

কারণ:

\[
1+2+3+\cdots+10=55
\]

**Lesson:** Loop-এর range ঠিক থাকলেও result যাচাই করতে হবে যে শেষ সংখ্যাটি process হয়েছে কি না।

## 7. Off-by-One Error in List Indexing

Python list-এর index `0` থেকে শুরু হয়।

ধরি:

```python
numbers = [10, 20, 30, 40, 50]
```

Index-গুলো:

| Index | Value |
|---:|---:|
| 0 | 10 |
| 1 | 20 |
| 2 | 30 |
| 3 | 40 |
| 4 | 50 |

এখানে element সংখ্যা `5`, কিন্তু শেষ index `4`।

### Common Mistake

```python
numbers = [10, 20, 30, 40, 50]

for index in range(1, len(numbers) + 1):
    print(numbers[index])
```

এই code-এ প্রথম element বাদ পড়ে এবং শেষ iteration-এ `numbers[5]` access করার চেষ্টা হয়। ফলে `IndexError` হবে।

### Correct Code

```python
numbers = [10, 20, 30, 40, 50]

for index in range(len(numbers)):
    print(numbers[index])
```

Output:

```text
10
20
30
40
50
```

কারণ `len(numbers)` হলো `5`, তাই `range(5)` থেকে index `0`–`4` পাওয়া যায়।

### Easier Alternative

```python
for number in numbers:
    print(number)
```

শুধু element দরকার হলে সরাসরি list-এর ওপর loop চালানো আরও সহজ।

## 8. Off-by-One Error with `while` Loop Updates

Loop variable কখন update হচ্ছে, সেটিও গুরুত্বপূর্ণ।

### Example 1: Update After Printing

```python
number = 1

while number <= 3:
    print(number)
    number += 1
```

Output:

```text
1
2
3
```

### Example 2: Update Before Printing

```python
number = 1

while number <= 3:
    number += 1
    print(number)
```

Output:

```text
2
3
4
```

দ্বিতীয় code-এ প্রথমে variable update করা হয়েছে। তাই `1` print হয়নি এবং `4` print হয়েছে।

**Lesson:** Update statement-এর অবস্থান output পরিবর্তন করতে পারে।

## 9. Off-by-One Error in Counting

ধরি, `1` থেকে `10` পর্যন্ত কয়টি সংখ্যা আছে তা গণনা করতে হবে।

```python
count = 0

for number in range(1, 11):
    count += 1

print(count)
```

Output:

```text
10
```

কিন্তু যদি লেখা হয়:

```python
count = 0

for number in range(1, 10):
    count += 1

print(count)
```

Output:

```text
9
```

দ্বিতীয় code-এ `10` বাদ পড়েছে বলে count এক কম হয়েছে।

**Rule:** শুধু output-এর সংখ্যা নয়, loop-এর প্রতিটি value problem-এর প্রয়োজন অনুযায়ী process হচ্ছে কি না যাচাই করবে।

## 10. Off-by-One Errors in Reverse Loops

Backward counting-এর সময়ও boundary ভুল হতে পারে।

### Example 1

```python
for number in range(5, 0, -1):
    print(number)
```

Output:

```text
5
4
3
2
1
```

### Example 2

```python
for number in range(5, 1, -1):
    print(number)
```

Output:

```text
5
4
3
2
```

দ্বিতীয় code-এ `1` বাদ গেছে, কারণ stop value `1` অন্তর্ভুক্ত নয়।

**Rule:** Descending `range()`-এও stop value exclusive থাকে।

## 11. Off-by-One Errors in Nested Loops

Nested loop-এ ভুল range ব্যবহার করলে pattern-এর row বা column এক কম বা বেশি হতে পারে।

### Incorrect Code

```python
for row in range(1, 5):
    for column in range(1, row):
        print("*", end=" ")
    print()
```

এখানে প্রতিটি row-তে star-এর সংখ্যা row number-এর চেয়ে এক কম।

Output:

```text

*
* *
* * *
```

### Correct Code

```python
for row in range(1, 5):
    for column in range(1, row + 1):
        print("*", end=" ")
    print()
```

Output:

```text
*
* *
* * *
* * * *
```

এখানে `row + 1` ব্যবহারের কারণে `row`-এর সমান সংখ্যক star print হয়।

## 12. Off-by-One Error in User Input

ধরি, user-এর কাছ থেকে `5`টি সংখ্যা নিয়ে sum বের করতে হবে।

ভুল code:

```python
total = 0

for i in range(1, 5):
    number = int(input("Enter a number: "))
    total += number

print(total)
```

এই code-এ `range(1, 5)` থেকে চারটি value পাওয়া যায়। তাই চারবার input নেওয়া হয়।

সঠিক code:

```python
total = 0

for i in range(5):
    number = int(input("Enter a number: "))
    total += number

print("Sum:", total)
```

এখানে `range(5)` পাঁচবার loop চালায়।

**Rule:** যদি ঠিক `n` বার কাজ করতে হয়, সাধারণত `range(n)` সবচেয়ে সহজ।

## 13. How to Prevent Off-by-One Errors

Off-by-one error এড়ানোর জন্য এই পদ্ধতিগুলো অনুসরণ করো।

1. **Problem-এর boundary নির্ধারণ করো:** শুরু ও শেষের value অন্তর্ভুক্ত কি না বুঝে নাও।
2. **`range()`-এর stop value মনে রাখো:** Stop value অন্তর্ভুক্ত হয় না।
3. **ছোট example দিয়ে পরীক্ষা করো:** যেমন `range(1, 4)` হাতে লিখে দেখো।
4. **Iteration count হিসাব করো:** Loop কতবার চলার কথা, তা আগে নির্ধারণ করো।
5. **Index ও length আলাদা করে বোঝো:** List-এর length `n` হলে শেষ index সাধারণত `n - 1`।
6. **Update statement পরীক্ষা করো:** Variable কখন বাড়ছে বা কমছে, তা দেখো।
7. **Dry run করো:** প্রথম ও শেষ iteration বিশেষভাবে যাচাই করো।
8. **Output পরীক্ষা করো:** প্রথম value এবং শেষ value দুটোই এসেছে কি না দেখো।

## 14. Dry Run Example

Code:

```python
total = 0

for number in range(2, 8):
    total += number

print(total)
```

### Dry Run Table

| Iteration | Number | Total |
|---:|---:|---:|
| 1 | 2 | 2 |
| 2 | 3 | 5 |
| 3 | 4 | 9 |
| 4 | 5 | 14 |
| 5 | 6 | 20 |
| 6 | 7 | 27 |

Output:

```text
27
```

এখানে `8` যোগ হয়নি, কারণ stop value exclusive।

যদি `2` থেকে `8` পর্যন্ত sum দরকার হয়, তাহলে লিখতে হবে:

```python
for number in range(2, 9):
    total += number
```

তখন sum হবে `35`।

## 15. Common Mistakes Summary

| Mistake | Result | Solution |
|---|---|---|
| `range(1, 5)` দিয়ে 1–5 আশা করা | 5 বাদ পড়ে | `range(1, 6)` |
| `number < 5` দিয়ে 5 অন্তর্ভুক্ত আশা করা | 5 বাদ পড়ে | প্রয়োজন হলে `number <= 5` |
| `range(len(numbers) + 1)` ব্যবহার করা | শেষ index-এর বাইরে যাওয়ার ঝুঁকি | `range(len(numbers))` |
| `range(1, n)` দিয়ে n বার কাজ আশা করা | সাধারণত n−1 বার | প্রয়োজন অনুযায়ী `range(n)` |
| Reverse loop-এ stop value ভুল করা | শেষ value বাদ পড়ে | Step ও stop ঠিক করো |
| Update-এর অবস্থান না দেখা | প্রথম বা শেষ output বদলে যেতে পারে | Dry run করো |

## 16. Practice Exercises

প্রতিটি প্রশ্নে loop-এর output বা iteration count নির্ণয় করো।

### Exercise 1

```python
for i in range(1, 6):
    print(i)
```

### Exercise 2

```python
for i in range(1, 6):
    print(i * 2)
```

### Exercise 3

```python
count = 0

for i in range(1, 11):
    if i % 2 == 0:
        count += 1

print(count)
```

### Exercise 4

```python
number = 1

while number < 5:
    print(number)
    number += 1
```

### Exercise 5

```python
for i in range(10, 0, -2):
    print(i)
```

### Exercise 6

```python
numbers = [10, 20, 30, 40]

for i in range(1, len(numbers)):
    print(numbers[i])
```

### Exercise 7

নিচের code-এ কেন `5`টি input নেওয়া হবে না?

```python
for i in range(1, 5):
    number = int(input("Enter a number: "))
```

### Exercise 8

১ থেকে ২০ পর্যন্ত সংখ্যার sum বের করতে সঠিক `range()` কী হবে?

### Exercise 9

নিচের code-এর output কী?

```python
number = 3

while number <= 7:
    print(number)
    number += 2
```

### Exercise 10

নিচের code-এ কতটি star print হবে?

```python
for row in range(1, 4):
    for column in range(1, row + 1):
        print("*", end="")
    print()
```

## 17. Practice Answer Key

### Answer 1

```text
1
2
3
4
5
```

মোট 5 বার।

### Answer 2

```text
2
4
6
8
10
```

### Answer 3

```text
5
```

১ থেকে ১০ পর্যন্ত পাঁচটি even সংখ্যা আছে।

### Answer 4

```text
1
2
3
4
```

`number = 5` হলে condition False হয়।

### Answer 5

```text
10
8
6
4
2
```

### Answer 6

```text
20
30
40
```

প্রথম element-এর index `0`, তাই সেটি বাদ পড়েছে।

### Answer 7

`range(1, 5)` থেকে `1`, `2`, `3`, `4` পাওয়া যায়। তাই loop চারবার চলে।

সঠিক:

```python
for i in range(5):
    number = int(input("Enter a number: "))
```

### Answer 8

```python
range(1, 21)
```

### Answer 9

```text
3
5
7
```

এরপর `number = 9` হয় এবং condition False হয়ে যায়।

### Answer 10

```text
*
**
***
```

মোট star:

\[
1+2+3=6
\]

## 18. Chapter Summary

- Off-by-one error হলো loop একবার বেশি বা কম চালানোর ভুল।
- `range()`-এর stop value exclusive।
- `<` শেষ value বাদ দেয়, আর `<=` condition অনুযায়ী শেষ value অন্তর্ভুক্ত করতে পারে।
- List-এর length ও শেষ index এক নয়।
- Backward loop-এও stop value exclusive থাকে।
- Nested loop-এর ভুল range pattern-এর row বা column বদলে দিতে পারে।
- Update statement-এর অবস্থান output পরিবর্তন করতে পারে।
- Dry run ও iteration count যাচাই করলে এই ভুলগুলো সহজে শনাক্ত করা যায়।

## 19. Completion Checklist

- [ ] Off-by-one error কী ব্যাখ্যা করতে পারি।
- [ ] `range()`-এর সঠিক boundary নির্ধারণ করতে পারি।
- [ ] `<` ও `<=`-এর পার্থক্য বুঝি।
- [ ] Loop-এর iteration count বের করতে পারি।
- [ ] List indexing-এর boundary error এড়াতে পারি।
- [ ] Reverse loop-এর stop value ঠিক করতে পারি।
- [ ] Nested loop-এর range ঠিক করতে পারি।
- [ ] Dry run করে off-by-one error শনাক্ত করতে পারি।

**Next Topic:** `69_Common_Loop_Errors_and_Debugging.md`