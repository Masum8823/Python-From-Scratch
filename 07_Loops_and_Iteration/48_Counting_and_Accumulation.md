# 48. Counting and Accumulation

## 1. Introduction

Python-এ loop ব্যবহার করে কোনো কাজ বারবার করার পাশাপাশি তথ্য গণনা এবং হিসাব জমা রাখা যায়।

এই কাজে দুটি গুরুত্বপূর্ণ ধারণা রয়েছে:

1. **Counting:** কোনো ঘটনা কতবার ঘটেছে, তা গণনা করা।
2. **Accumulation:** loop চলার সময় পাওয়া value-গুলো একত্র করে একটি running result তৈরি করা।

উদাহরণ:

- ১ থেকে ১০ পর্যন্ত সংখ্যা গণনা করা।
- একটি list-এ কতটি even number আছে তা বের করা।
- কয়েকটি সংখ্যার যোগফল বের করা।
- বিক্রির পরিমাণ যোগ করে মোট বিক্রি নির্ণয় করা।

## 2. Understanding a Counter

**Counter** হলো এমন একটি variable, যার মান কোনো কিছু গণনা করার জন্য পরিবর্তন করা হয়।

সাধারণত counter একটি নির্দিষ্ট মান দিয়ে শুরু হয় এবং প্রয়োজন অনুযায়ী বাড়ানো হয়।

### Example

```python
count = 0

for number in range(1, 6):
    count += 1

print("Count:", count)
```

### Output

```text
Count: 5
```

### Explanation

- `count = 0` দিয়ে গণনা শুরু হয়েছে।
- Loop মোট পাঁচবার চলে।
- প্রতিবার `count += 1` দিয়ে counter এক বাড়ে।
- শেষে `count`-এর মান হয় ৫।

**মনে রাখবে:** `count += 1` হলো `count = count + 1`-এর সংক্ষিপ্ত রূপ।

## 3. Counting Numbers in a Range

নির্দিষ্ট range-এ কতটি সংখ্যা আছে, তা counter দিয়ে গণনা করা যায়।

### Code

```python
count = 0

for number in range(1, 11):
    count += 1

print("Total numbers:", count)
```

### Output

```text
Total numbers: 10
```

এখানে `range(1, 11)` ১ থেকে ১০ পর্যন্ত মোট ১০টি সংখ্যা দেয়।

প্রতিটি সংখ্যার জন্য counter একবার বাড়ে।

## 4. Counting Even Numbers

কোনো range-এ কতটি even number আছে তা বের করতে condition ব্যবহার করা যায়।

### Code

```python
count = 0

for number in range(1, 11):
    if number % 2 == 0:
        count += 1

print("Even numbers:", count)
```

### Output

```text
Even numbers: 5
```

### Explanation

`number % 2 == 0` হলে সংখ্যাটি even।

১ থেকে ১০ পর্যন্ত even number হলো:

`2, 4, 6, 8, 10`

তাই counter মোট পাঁচবার বাড়ে।

## 5. Counting Odd Numbers

একইভাবে odd number গণনা করা যায়।

### Code

```python
count = 0

for number in range(1, 11):
    if number % 2 != 0:
        count += 1

print("Odd numbers:", count)
```

### Output

```text
Odd numbers: 5
```

### Explanation

`number % 2 != 0` হলে সংখ্যাটি odd।

১ থেকে ১০ পর্যন্ত odd number হলো:

`1, 3, 5, 7, 9`

তাই মোট পাঁচটি odd number আছে।

## 6. Counting Numbers That Satisfy a Condition

Counter ব্যবহার করে যেকোনো condition পূরণকারী value গণনা করা যায়।

### Example: Counting Numbers Greater Than 5

```python
count = 0

for number in range(1, 11):
    if number > 5:
        count += 1

print("Count:", count)
```

### Output

```text
Count: 5
```

কারণ ৬, ৭, ৮, ৯ ও ১০—এই পাঁচটি সংখ্যা ৫-এর চেয়ে বড়।

### Example: Counting Multiples of 3

```python
count = 0

for number in range(1, 21):
    if number % 3 == 0:
        count += 1

print("Multiples of 3:", count)
```

Output:

```text
Multiples of 3: 6
```

সংখ্যাগুলো হলো `3, 6, 9, 12, 15, 18`।

## 7. Understanding an Accumulator

**Accumulator** হলো এমন একটি variable, যেখানে loop চলার সময় একের পর এক value যোগ করে running result তৈরি করা হয়।

Counter সাধারণত কোনো কিছু কতবার ঘটেছে তা গণনা করে। Accumulator সাধারণত value জমা রাখে।

### Example

```python
total = 0

for number in range(1, 6):
    total += number

print("Total:", total)
```

### Output

```text
Total: 15
```

### Explanation

প্রতিবার `number`-এর মান `total`-এর সঙ্গে যোগ হয়।

- প্রথমে `total = 0`
- এরপর ১ যোগ হয়ে `total = 1`
- তারপর ২ যোগ হয়ে `total = 3`
- এরপর ৩ যোগ হয়ে `total = 6`
- এরপর ৪ যোগ হয়ে `total = 10`
- শেষে ৫ যোগ হয়ে `total = 15`

এইভাবে accumulator ধাপে ধাপে চূড়ান্ত ফলাফল তৈরি করে।

## 8. Counter vs Accumulator

| বিষয় | Counter | Accumulator |
|---|---|---|
| কাজ | ঘটনা বা item গণনা করা | Value জমা রাখা |
| সাধারণ update | `count += 1` | `total += number` |
| উদাহরণ | Even number-এর সংখ্যা | সব সংখ্যার যোগফল |
| প্রাথমিক মান | সাধারণত `0` | যোগের জন্য সাধারণত `0` |
| পরিবর্তন | সাধারণত নির্দিষ্ট ধাপে বাড়ে | বিভিন্ন value যোগ হতে পারে |

**মনে রাখবে:** Counter-ও একটি variable, accumulator-ও একটি variable। তাদের পার্থক্য মূলত ব্যবহারের উদ্দেশ্যে।

## 9. Finding the Sum of Even Numbers

Accumulator ব্যবহার করে নির্দিষ্ট condition পূরণকারী সংখ্যার যোগফল বের করা যায়।

### Code

```python
total = 0

for number in range(1, 11):
    if number % 2 == 0:
        total += number

print("Sum of even numbers:", total)
```

### Output

```text
Sum of even numbers: 30
```

এখানে যোগ করা সংখ্যাগুলো হলো:

`2 + 4 + 6 + 8 + 10 = 30`

Odd number-গুলো যোগ করা হয়নি, কারণ condition শুধু even number-এর জন্য সত্য হয়।

## 10. Counting and Accumulation Together

অনেক problem-এ counter এবং accumulator একসঙ্গে ব্যবহার করতে হয়।

### Example: Count and Sum of Even Numbers

```python
count = 0
total = 0

for number in range(1, 11):
    if number % 2 == 0:
        count += 1
        total += number

print("Count:", count)
print("Sum:", total)
```

### Output

```text
Count: 5
Sum: 30
```

### Explanation

- `count` even number-এর সংখ্যা গণনা করে।
- `total` even number-গুলোর যোগফল জমা রাখে।
- Condition সত্য হলে দুইটি variable-ই update হয়।

এটি একটি গুরুত্বপূর্ণ programming pattern।

## 11. Counting and Summing User Input

ব্যবহারকারীর দেওয়া একাধিক সংখ্যার count এবং sum বের করাও সম্ভব।

### Code

```python
count = int(input("How many numbers? "))

total = 0

for i in range(count):
    number = int(input("Enter a number: "))
    total += number

print("Sum:", total)
```

### Sample Input and Output

```text
How many numbers? 3
Enter a number: 10
Enter a number: 20
Enter a number: 30
Sum: 60
```

### Explanation

- প্রথমে ব্যবহারকারী কয়টি সংখ্যা দেবেন তা নেওয়া হয়।
- Loop সেই সংখ্যক বার চলে।
- প্রতিবার একটি সংখ্যা input নেওয়া হয়।
- `total += number` দিয়ে যোগফল জমা রাখা হয়।

এই উদাহরণে input-গুলোকে integer-এ রূপান্তর করা হচ্ছে। ব্যবহারকারী integer-এর বদলে অন্য কোনো text দিলে `ValueError` হতে পারে।

## 12. Calculating an Average

Average বের করতে প্রথমে sum এবং count বের করতে হয়।

Formula:

\[
\text{Average} = \frac{\text{Sum}}{\text{Count}}
\]

### Code

```python
total = 0
count = 0

for number in range(1, 6):
    total += number
    count += 1

if count > 0:
    average = total / count
    print("Average:", average)
else:
    print("No numbers available")
```

### Output

```text
Average: 3.0
```

### Explanation

- Sum = ১৫
- Count = ৫
- Average = \(15 / 5 = 3.0\)

`count > 0` পরীক্ষা করা হয়েছে, যাতে count শূন্য হলে division by zero না ঘটে।

## 13. Using an Accumulator with a List

List-এর value-গুলোর sum এবং condition অনুযায়ী count বের করাও সহজ।

### Code

```python
numbers = [10, 15, 20, 25, 30]

total = 0
count = 0

for number in numbers:
    total += number

    if number > 20:
        count += 1

print("Sum:", total)
print("Numbers greater than 20:", count)
```

### Output

```text
Sum: 100
Numbers greater than 20: 2
```

### Explanation

List-এর সব সংখ্যার যোগফল:

`10 + 15 + 20 + 25 + 30 = 100`

২০-এর চেয়ে বড় সংখ্যা হলো ২৫ ও ৩০। তাই count = ২।

## 14. Using a `while` Loop for Counting

Counter এবং accumulator শুধু `for` loop-এ নয়, `while` loop-এও ব্যবহার করা যায়।

### Code

```python
number = 1
count = 0
total = 0

while number <= 5:
    count += 1
    total += number
    number += 1

print("Count:", count)
print("Sum:", total)
```

### Output

```text
Count: 5
Sum: 15
```

### Explanation

- `number` ১ থেকে শুরু হয়।
- প্রতিটি iteration-এ count এক বাড়ে।
- বর্তমান number যোগফলের সঙ্গে যোগ হয়।
- `number += 1` পরবর্তী সংখ্যায় যায়।

Variable update না করলে এই `while` loop অনন্তকাল চলতে পারে।

## 15. Understanding Initialization

Counter ও accumulator ব্যবহারের আগে সঠিক প্রাথমিক মান নির্ধারণ করতে হয়।

### Counting Example

```python
count = 0
count += 1
count += 1

print(count)
```

Output:

```text
2
```

### Summation Example

```python
total = 0
total += 5
total += 10

print(total)
```

Output:

```text
15
```

### কেন `total = 0`?

যোগের ক্ষেত্রে ০ একটি উপযুক্ত প্রাথমিক মান, কারণ ০ যোগ করলে অন্য সংখ্যার মান পরিবর্তিত হয় না।

যদি `total` initialize না করে সরাসরি `total += number` লেখা হয়, তাহলে সাধারণ variable-এর ক্ষেত্রে `NameError` হতে পারে।

## 16. Dry Run: Counting and Accumulation

Code:

```python
count = 0
total = 0

for number in range(1, 5):
    count += 1
    total += number

print(count)
print(total)
```

### Dry Run Table

| Iteration | `number` | `count` | `total` |
|---:|---:|---:|---:|
| 1 | 1 | 1 | 1 |
| 2 | 2 | 2 | 3 |
| 3 | 3 | 3 | 6 |
| 4 | 4 | 4 | 10 |

### Output

```text
4
10
```

প্রতিটি iteration-এর পরে `count` এবং `total`—দুটির মানই পরিবর্তিত হয়।

## 17. Common Mistakes

### Mistake 1: Forgetting to Initialize the Counter

ভুল:

```python
for number in range(1, 6):
    count += 1
```

এখানে `count` আগে initialize করা হয়নি।

সঠিক:

```python
count = 0

for number in range(1, 6):
    count += 1
```

### Mistake 2: Initializing the Accumulator Inside the Loop

ভুল:

```python
for number in range(1, 6):
    total = 0
    total += number

print(total)
```

Output:

```text
5
```

প্রতিবার loop-এর শুরুতে `total = 0` হওয়ায় আগের যোগফল হারিয়ে যায়।

সঠিক:

```python
total = 0

for number in range(1, 6):
    total += number

print(total)
```

Output:

```text
15
```

### Mistake 3: Updating the Counter Without a Condition

যদি শুধু even number গণনা করতে চাও, তাহলে `count += 1`-কে even-number condition-এর ভেতরে রাখতে হবে।

### Mistake 4: Adding the Wrong Variable

ভুল:

```python
total = 0

for number in range(1, 6):
    total += 1
```

এটি সংখ্যাগুলোর যোগফল বের করে না; বরং loop পাঁচবার চলায় total-কে ৫ করে।

সঠিক:

```python
total = 0

for number in range(1, 6):
    total += number
```

### Mistake 5: Division by Zero

কোনো item না থাকলে count শূন্য হতে পারে। Average বের করার আগে `count > 0` পরীক্ষা করতে হবে।

### Mistake 6: Confusing Count with Sum

- Count জানতে `count += 1` ব্যবহার করা হয়।
- Sum জানতে `total += number` ব্যবহার করা হয়।

দুটির উদ্দেশ্য আলাদা।

## 18. Practical Example: Counting Passed Students

ধরা যাক, কয়েকজন শিক্ষার্থীর marks দেওয়া আছে। ৪০ বা তার বেশি marks পাওয়া শিক্ষার্থীর সংখ্যা গণনা করতে হবে।

### Code

```python
marks_list = [75, 32, 60, 25, 90, 40]

passed = 0
failed = 0

for marks in marks_list:
    if marks >= 40:
        passed += 1
    else:
        failed += 1

print("Passed:", passed)
print("Failed:", failed)
```

### Output

```text
Passed: 4
Failed: 2
```

### Explanation

- `marks >= 40` হলে `passed` এক বাড়ে।
- অন্যথায় `failed` এক বাড়ে।
- মোট ৬ জন শিক্ষার্থীর মধ্যে ৪ জন pass এবং ২ জন fail করেছে।

এখানে pass/fail-এর নিয়মটি উদাহরণ হিসেবে ধরা হয়েছে।

## 19. Practice Exercises

### Exercise 1: Count from 1 to 20

Loop ব্যবহার করে ১ থেকে ২০ পর্যন্ত মোট সংখ্যা গণনা করো।

### Exercise 2: Count Even Numbers

১ থেকে ৫০ পর্যন্ত even number-এর সংখ্যা বের করো।

### Exercise 3: Sum from 1 to 100

Accumulator ব্যবহার করে ১ থেকে ১০০ পর্যন্ত সংখ্যার যোগফল বের করো।

### Exercise 4: Sum of Odd Numbers

১ থেকে ২০ পর্যন্ত odd number-গুলোর যোগফল বের করো।

### Exercise 5: Count and Sum a List

```python
numbers = [5, 10, 15, 20, 25]
```

List-এর item সংখ্যা এবং মোট যোগফল বের করো।

### Exercise 6: Calculate an Average

`[70, 80, 90, 60, 100]` list-এর average বের করো।

### Exercise 7: Count Passing Marks

```python
marks_list = [35, 50, 80, 20, 45, 90]
```

৪০ বা তার বেশি marks পাওয়া শিক্ষার্থীর সংখ্যা বের করো।

### Exercise 8: Predict the Output

```python
count = 0
total = 0

for number in range(1, 4):
    count += 1
    total += number

print(count)
print(total)
```

## 20. Practice Answer Key

### Answer 1

```python
count = 0

for number in range(1, 21):
    count += 1

print(count)
```

Output: `20`

### Answer 2

```python
count = 0

for number in range(1, 51):
    if number % 2 == 0:
        count += 1

print(count)
```

Output: `25`

### Answer 3

```python
total = 0

for number in range(1, 101):
    total += number

print(total)
```

Output: `5050`

### Answer 4

```python
total = 0

for number in range(1, 21):
    if number % 2 != 0:
        total += number

print(total)
```

Output: `100`

### Answer 5

```python
numbers = [5, 10, 15, 20, 25]

count = 0
total = 0

for number in numbers:
    count += 1
    total += number

print("Count:", count)
print("Sum:", total)
```

Output:

```text
Count: 5
Sum: 75
```

### Answer 6

```python
marks = [70, 80, 90, 60, 100]

total = 0
count = 0

for mark in marks:
    total += mark
    count += 1

average = total / count
print(average)
```

Output: `80.0`

### Answer 7

```python
marks_list = [35, 50, 80, 20, 45, 90]

passed = 0

for marks in marks_list:
    if marks >= 40:
        passed += 1

print(passed)
```

Output: `4`

### Answer 8

Output:

```text
3
6
```

Loop তিনবার চলে। Count হয় ৩ এবং sum হয় \(1+2+3=6\)।

## 21. Chapter Summary

- Counter কোনো ঘটনা বা item কতবার ঘটেছে তা গণনা করে।
- Accumulator একাধিক value জমা রেখে running result তৈরি করে।
- Counting-এর জন্য সাধারণত `count += 1` ব্যবহার করা হয়।
- Summation-এর জন্য `total += number` ব্যবহার করা হয়।
- Condition-এর সাহায্যে নির্দিষ্ট item গণনা বা যোগ করা যায়।
- Counter ও accumulator সাধারণত loop-এর বাইরে initialize করা হয়।
- Average বের করতে sum-কে count দিয়ে ভাগ করতে হয়।
- Division করার আগে count শূন্য কি না পরীক্ষা করা জরুরি।

## 22. Completion Checklist

- [ ] Counter ও accumulator-এর পার্থক্য বুঝি।
- [ ] Loop দিয়ে item গণনা করতে পারি।
- [ ] Even ও odd number গণনা করতে পারি।
- [ ] Running sum বের করতে পারি।
- [ ] Count ও sum একসঙ্গে বের করতে পারি।
- [ ] Average গণনা করতে পারি।
- [ ] `for` ও `while` loop-এ accumulator ব্যবহার করতে পারি।
- [ ] Dry run করে counter ও accumulator-এর মান বের করতে পারি।

**Next Topic:** `49_Finding_the_Sum_of_Numbers.md`