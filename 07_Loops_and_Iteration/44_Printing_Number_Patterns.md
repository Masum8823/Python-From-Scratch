# 44. Printing Number Patterns

## 1. Introduction

Number pattern হলো সংখ্যা ব্যবহার করে নির্দিষ্ট নিয়মে সাজানো output। Python-এ `for` loop ও nested loop ব্যবহার করে সহজেই এই pattern তৈরি করা যায়।

উদাহরণ:

```text
1
1 2
1 2 3
1 2 3 4
```

এখানে প্রতিটি নতুন row-তে আগের row-এর চেয়ে একটি সংখ্যা বেশি আছে।

Number pattern তৈরির জন্য সাধারণত:

- **Outer loop:** কতটি row হবে তা নিয়ন্ত্রণ করে।
- **Inner loop:** প্রতিটি row-তে কোন সংখ্যাগুলো print হবে তা নিয়ন্ত্রণ করে।
- **`print()`:** প্রতিটি row শেষ হলে নতুন line তৈরি করে।
- **`end=" "`:** একই লাইনে একাধিক সংখ্যা print করতে সাহায্য করে।

## 2. Pattern 1: Increasing Number Triangle

প্রথম pattern-এ প্রতিটি row-তে ১ থেকে row number পর্যন্ত সংখ্যা print হবে।

### Code

```python
for row in range(1, 6):
    for number in range(1, row + 1):
        print(number, end=" ")
    print()
```

### Output

```text
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

### Explanation

- Outer loop `row`-এর মান ১ থেকে ৫ পর্যন্ত নেয়।
- Inner loop ১ থেকে `row` পর্যন্ত সংখ্যা print করে।
- প্রতিটি row-এর শেষে `print()` নতুন line তৈরি করে।

উদাহরণস্বরূপ, `row = 3` হলে inner loop `1`, `2`, `3` print করে।

## 3. Pattern 2: Repeating Row Numbers

এই pattern-এ প্রতিটি row-তে একই সংখ্যা একাধিকবার print হবে।

### Code

```python
for row in range(1, 6):
    for column in range(row):
        print(row, end=" ")
    print()
```

### Output

```text
1
2 2
3 3 3
4 4 4 4
5 5 5 5 5
```

### Explanation

এখানে `print(row, end=" ")` ব্যবহার করা হয়েছে। তাই প্রতিটি row-তে `row`-এর একই মান বারবার print হয়।

| Row | Repetition | Output |
|---:|---:|---|
| 1 | 1 বার | `1` |
| 2 | 2 বার | `2 2` |
| 3 | 3 বার | `3 3 3` |
| 4 | 4 বার | `4 4 4 4` |

## 4. Pattern 3: Increasing Rows with Repeated Ones

এখানে প্রতিটি row-তে শুধু `1` থাকবে, তবে row অনুযায়ী সংখ্যা বাড়বে।

### Code

```python
for row in range(1, 6):
    for column in range(row):
        print(1, end=" ")
    print()
```

### Output

```text
1
1 1
1 1 1
1 1 1 1
1 1 1 1 1
```

### Explanation

এখানে `print(1, end=" ")`-এ স্থিরভাবে `1` print করা হচ্ছে। Inner loop-এর iteration সংখ্যা `row` অনুযায়ী বাড়ছে।

## 5. Pattern 4: Decreasing Number Triangle

এবার প্রতিটি row-তে সংখ্যার পরিমাণ কমবে।

### Code

```python
for row in range(5, 0, -1):
    for number in range(1, row + 1):
        print(number, end=" ")
    print()
```

### Output

```text
1 2 3 4 5
1 2 3 4
1 2 3
1 2
1
```

### Explanation

- Outer loop ৫ থেকে ১ পর্যন্ত কমে।
- Inner loop প্রতিটি row-তে ১ থেকে `row` পর্যন্ত সংখ্যা print করে।
- ফলে প্রতিটি নতুন row-তে একটি করে সংখ্যা কমে।

## 6. Pattern 5: Decreasing Numbers from the Row Value

এই pattern-এ প্রতিটি row-তে row number থেকে ১ পর্যন্ত সংখ্যা print হবে।

### Code

```python
for row in range(5, 0, -1):
    for number in range(row, 0, -1):
        print(number, end=" ")
    print()
```

### Output

```text
5 4 3 2 1
4 3 2 1
3 2 1
2 1
1
```

### Explanation

এখানে inner loop-এর `range(row, 0, -1)` row number থেকে শুরু করে ১ পর্যন্ত উল্টোভাবে চলে।

উদাহরণস্বরূপ, `row = 3` হলে output হবে `3 2 1`।

## 7. Pattern 6: Continuous Number Triangle

এই pattern-এ প্রতিটি row-তে নতুন সংখ্যা ১ থেকে শুরু না করে আগের row-এর পরবর্তী সংখ্যা থেকে শুরু হবে। একে **Floyd’s Triangle** বলা হয়।

### Code

```python
number = 1

for row in range(1, 6):
    for column in range(row):
        print(number, end=" ")
        number += 1
    print()
```

### Output

```text
1
2 3
4 5 6
7 8 9 10
11 12 13 14 15
```

### Explanation

- `number = 1` দিয়ে শুরু করা হয়েছে।
- প্রতিবার একটি সংখ্যা print করার পর `number += 1` দিয়ে পরবর্তী সংখ্যা নেওয়া হয়।
- Inner loop শেষ হলে পরবর্তী row শুরু হয়।
- `number` outer loop-এর বাইরে initialize করা হয়েছে, তাই এর মান row পরিবর্তনের পরও বজায় থাকে।

**গুরুত্বপূর্ণ:** যদি `number = 1` outer loop-এর ভেতরে রাখা হতো, তাহলে প্রতিটি row-তে আবার ১ থেকে শুরু হতো।

## 8. Pattern 7: Repeating Odd Numbers

এই pattern-এ প্রতিটি row-তে সংশ্লিষ্ট বিজোড় সংখ্যা বারবার print হবে।

### Code

```python
for row in range(1, 6):
    odd_number = 2 * row - 1

    for column in range(row):
        print(odd_number, end=" ")

    print()
```

### Output

```text
1
3 3
5 5 5
7 7 7 7
9 9 9 9 9
```

### Explanation

বিজোড় সংখ্যা বের করার সূত্র:

\[
\text{Odd number} = 2 \times \text{row} - 1
\]

যেমন:

- Row 1: \(2 \times 1 - 1 = 1\)
- Row 2: \(2 \times 2 - 1 = 3\)
- Row 3: \(2 \times 3 - 1 = 5\)

## 9. Pattern 8: Repeating Even Numbers

একইভাবে জোড় সংখ্যার pattern তৈরি করা যায়।

### Code

```python
for row in range(1, 6):
    even_number = 2 * row

    for column in range(row):
        print(even_number, end=" ")

    print()
```

### Output

```text
2
4 4
6 6 6
8 8 8 8
10 10 10 10 10
```

### Explanation

জোড় সংখ্যা বের করার সূত্র:

\[
\text{Even number} = 2 \times \text{row}
\]

এখানে প্রতিটি row-তে সংশ্লিষ্ট জোড় সংখ্যাটি row number অনুযায়ী বারবার print হয়।

## 10. Pattern 9: Centered Number Pyramid

এই pattern-এ সংখ্যা বাড়তে বাড়তে pyramid তৈরি হবে।

### Code

```python
height = 5

for row in range(1, height + 1):
    for space in range(height - row):
        print(" ", end="")

    for number in range(1, row + 1):
        print(number, end=" ")

    print()
```

### Output

```text
    1
   1 2
  1 2 3
 1 2 3 4
1 2 3 4 5
```

### Explanation

এখানে দুটি inner loop আছে।

1. প্রথম inner loop leading spaces print করে।
2. দ্বিতীয় inner loop ১ থেকে `row` পর্যন্ত সংখ্যা print করে।
3. Row বাড়ার সঙ্গে সঙ্গে space কমে এবং সংখ্যা বাড়ে।

## 11. Pattern 10: Palindromic Number Pyramid

এই pattern-এ সংখ্যা প্রথমে বাড়ে, তারপর আবার কমে।

### Code

```python
height = 5

for row in range(1, height + 1):
    for space in range(height - row):
        print(" ", end="")

    for number in range(1, row + 1):
        print(number, end="")

    for number in range(row - 1, 0, -1):
        print(number, end="")

    print()
```

### Output

```text
    1
   121
  12321
 1234321
123454321
```

### Explanation

প্রতিটি row-তে তিনটি ধাপ অনুসরণ করা হয়:

1. প্রয়োজনীয় leading spaces print করা।
2. ১ থেকে `row` পর্যন্ত সংখ্যা বাড়ানো।
3. `row - 1` থেকে ১ পর্যন্ত সংখ্যা কমানো।

উদাহরণস্বরূপ, `row = 4` হলে:

- Increasing: `1234`
- Decreasing: `321`
- Combined: `1234321`

## 12. Pattern 11: Number Pyramid with Repeated Row Values

এই pattern-এ pyramid-এর মতো আকৃতি থাকবে, কিন্তু প্রতিটি row-তে একই সংখ্যা বারবার print হবে।

### Code

```python
height = 5

for row in range(1, height + 1):
    for space in range(height - row):
        print(" ", end="")

    for column in range(row):
        print(row, end=" ")

    print()
```

### Output

```text
        1
      2 2
    3 3 3
  4 4 4 4
5 5 5 5 5
```

### Explanation

- প্রথম inner loop spaces তৈরি করে।
- দ্বিতীয় inner loop বর্তমান `row` number বারবার print করে।
- প্রতিটি নতুন row-তে একটি করে repetition বাড়ে।

## 13. Pattern 12: Multiplication-Based Number Pattern

Loop ব্যবহার করে multiplication-এর ভিত্তিতেও number pattern তৈরি করা যায়।

### Code

```python
for row in range(1, 6):
    for column in range(1, row + 1):
        print(row * column, end=" ")
    print()
```

### Output

```text
1
2 4
3 6 9
4 8 12 16
5 10 15 20 25
```

### Explanation

এখানে প্রতিটি value হলো:

\[
\text{Value} = \text{row} \times \text{column}
\]

যেমন, `row = 4` হলে:

- \(4 \times 1 = 4\)
- \(4 \times 2 = 8\)
- \(4 \times 3 = 12\)
- \(4 \times 4 = 16\)

## 14. Understanding `end` and `print()`

Number pattern-এ `end` এবং `print()`-এর কাজ জানা জরুরি।

### Example 1: Without `end`

```python
for number in range(1, 4):
    print(number)
```

Output:

```text
1
2
3
```

প্রতিটি `print()` নতুন line তৈরি করে।

### Example 2: With `end=" "`

```python
for number in range(1, 4):
    print(number, end=" ")
```

Output:

```text
1 2 3
```

`end=" "` ব্যবহার করার কারণে সংখ্যাগুলো একই লাইনে থাকে।

### Example 3: Moving to the Next Row

```python
for row in range(1, 4):
    for number in range(1, row + 1):
        print(number, end=" ")
    print()
```

এখানে inner loop-এর শেষে থাকা `print()` প্রতিটি row সম্পূর্ণ হলে নতুন line তৈরি করে।

## 15. Dry Run of Floyd’s Triangle

Code:

```python
number = 1

for row in range(1, 4):
    for column in range(row):
        print(number, end=" ")
        number += 1
    print()
```

### Dry Run Table

| Row | Inner iterations | Printed numbers | Next `number` |
|---:|---:|---|---:|
| 1 | 1 | `1` | 2 |
| 2 | 2 | `2 3` | 4 |
| 3 | 3 | `4 5 6` | 7 |

### Output

```text
1
2 3
4 5 6
```

এখানে `number` প্রতিটি iteration-এ বাড়ছে এবং পরবর্তী row-তেও তার আগের মান বজায় রাখছে।

## 16. Common Mistakes

### Mistake 1: Initializing the Counter in the Wrong Place

যদি continuous number pattern তৈরি করতে চাও, তাহলে counter সাধারণত outer loop-এর বাইরে initialize করতে হবে।

### Mistake 2: Incorrect Range

```python
for number in range(1, row):
```

এখানে `row` অন্তর্ভুক্ত হবে না। ১ থেকে `row` পর্যন্ত সংখ্যা চাইলে লিখতে হবে:

```python
for number in range(1, row + 1):
```

### Mistake 3: Forgetting `end=" "`

`end` ব্যবহার না করলে প্রতিটি সংখ্যা আলাদা line-এ চলে যাবে।

### Mistake 4: Incorrect Decreasing Range

```python
range(5, 0, -1)
```

এটি ৫ থেকে ১ পর্যন্ত চলে। Stop value `0` অন্তর্ভুক্ত হয় না।

### Mistake 5: Updating the Counter Incorrectly

Floyd’s Triangle-এ `number += 1` বাদ পড়লে একই সংখ্যা বারবার print হতে পারে।

### Mistake 6: Confusing Row and Column

- `row` সাধারণত বর্তমান row নির্দেশ করে।
- `column` সাধারণত ওই row-এর ভেতরের position নির্দেশ করে।

তবে variable name বাধ্যতামূলক নয়; code-এর logic অনুযায়ী নাম নির্বাচন করা যায়।

## 17. Practice Exercises

### Exercise 1: Increasing Triangle

নিচের pattern তৈরি করো:

```text
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

### Exercise 2: Repeating Row Numbers

```text
1
2 2
3 3 3
4 4 4 4
```

### Exercise 3: Decreasing Triangle

```text
1 2 3 4 5
1 2 3 4
1 2 3
1 2
1
```

### Exercise 4: Floyd’s Triangle

পাঁচ row-এর Floyd’s Triangle তৈরি করো।

### Exercise 5: Odd Number Pattern

```text
1
3 3
5 5 5
7 7 7 7
```

### Exercise 6: Palindromic Pyramid

```text
   1
  121
 12321
1234321
```

### Exercise 7: Find the Output

```python
for row in range(1, 4):
    for number in range(1, row + 1):
        print(number, end=" ")
    print()
```

### Exercise 8: Count the Numbers

```python
for row in range(1, 6):
    for column in range(row):
        print(row, end=" ")
    print()
```

মোট কতটি সংখ্যা print হবে?

## 18. Practice Answer Key

### Answer 1

```python
for row in range(1, 6):
    for number in range(1, row + 1):
        print(number, end=" ")
    print()
```

### Answer 2

```python
for row in range(1, 5):
    for column in range(row):
        print(row, end=" ")
    print()
```

### Answer 3

```python
for row in range(5, 0, -1):
    for number in range(1, row + 1):
        print(number, end=" ")
    print()
```

### Answer 4

```python
number = 1

for row in range(1, 6):
    for column in range(row):
        print(number, end=" ")
        number += 1
    print()
```

### Answer 5

```python
for row in range(1, 5):
    odd_number = 2 * row - 1

    for column in range(row):
        print(odd_number, end=" ")
    print()
```

### Answer 6

```python
height = 4

for row in range(1, height + 1):
    for space in range(height - row):
        print(" ", end="")

    for number in range(1, row + 1):
        print(number, end="")

    for number in range(row - 1, 0, -1):
        print(number, end="")

    print()
```

### Answer 7

```text
1
1 2
1 2 3
```

### Answer 8

মোট সংখ্যা:

\[
1+2+3+4+5=15
\]

সুতরাং মোট ১৫টি সংখ্যা print হবে।

## 19. Chapter Summary

- Nested loop ব্যবহার করে বিভিন্ন number pattern তৈরি করা যায়।
- Outer loop row-এর সংখ্যা নিয়ন্ত্রণ করে।
- Inner loop প্রতিটি row-তে কোন সংখ্যা print হবে তা নির্ধারণ করে।
- `end=" "` একই লাইনে সংখ্যা print করে।
- `print()` দিয়ে পরবর্তী row শুরু করা হয়।
- Floyd’s Triangle-এ একটি counter ধারাবাহিকভাবে বাড়ে।
- Odd ও even pattern-এ সূত্র ব্যবহার করা যায়।
- Palindromic pyramid-এ সংখ্যা প্রথমে বাড়ে, তারপর কমে।

## 20. Completion Checklist

- [ ] Increasing ও decreasing number triangle তৈরি করতে পারি।
- [ ] Repeating number pattern তৈরি করতে পারি।
- [ ] Floyd’s Triangle তৈরি করতে পারি।
- [ ] Odd ও even number pattern তৈরি করতে পারি।
- [ ] Centered number pyramid তৈরি করতে পারি।
- [ ] Palindromic number pyramid তৈরি করতে পারি।
- [ ] Nested loop-এর execution dry run করতে পারি।
- [ ] `range()`, `end` এবং counter-এর ব্যবহার বুঝি।

**Next Topic:** `45_Printing_Alphabet_Patterns.md`
