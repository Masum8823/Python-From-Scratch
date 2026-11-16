# 64. Combining Loops with Conditional Statements

## 1. Introduction

Python-এ loop এবং conditional statement একসঙ্গে ব্যবহার করে complex problem সহজে solve করা যায়।

- **Loop:** একই কাজ বারবার করে।
- **Conditional statement:** কোনো condition অনুযায়ী সিদ্ধান্ত নেয়।

ধরি, আমাদের কাছে ৫টি সংখ্যা আছে। আমরা জানতে চাই, এর মধ্যে কয়টি even এবং কয়টি odd।

এখানে loop প্রতিটি সংখ্যা পরীক্ষা করবে এবং `if-else` নির্ধারণ করবে সংখ্যাটি even নাকি odd।

### Example

```python
numbers = [10, 15, 20, 25, 30]

even_count = 0
odd_count = 0

for number in numbers:
    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

print("Even:", even_count)
print("Odd:", odd_count)
```

### Output

```text
Even: 3
Odd: 2
```

### Learning Objectives

এই Topic শেষে তুমি পারবে:

- Loop ও conditional statement একসঙ্গে ব্যবহার করতে।
- List-এর data condition অনুযায়ী process করতে।
- Even, odd, positive ও negative সংখ্যা গণনা করতে।
- Marks থেকে pass/fail বের করতে।
- Nested conditions ও loops ব্যবহার করতে।
- বাস্তব problem-এর logic তৈরি করতে।
- Common mistakes শনাক্ত করতে।

## 2. Why Do We Combine Loops and Conditions?

ধরি, একটি list-এ অনেকগুলো সংখ্যা আছে:

```python
numbers = [5, 10, 15, 20, 25, 30]
```

আমরা শুধু ১০-এর বড় সংখ্যাগুলো print করতে চাই।

শুধু loop ব্যবহার করলে সব সংখ্যাই print হবে। শুধু `if` ব্যবহার করলে প্রতিটি সংখ্যার জন্য আলাদা condition লিখতে হবে।

দুটিকে একসঙ্গে ব্যবহার করলে:

```python
for number in numbers:
    if number > 10:
        print(number)
```

Output:

```text
15
20
25
30
```

এখানে:

1. `for` loop প্রতিটি element নেয়।
2. `if` condition পরীক্ষা করে।
3. Condition True হলে সংখ্যাটি print হয়।

এভাবেই loop ও condition একসঙ্গে কাজ করে।

## 3. Finding Even and Odd Numbers

কোনো integer even নাকি odd, তা পরীক্ষা করার নিয়ম:

```python
number % 2 == 0
```

Condition True হলে even, অন্যথায় odd।

### Code

```python
numbers = [12, 7, 4, 9, 15, 20]

for number in numbers:
    if number % 2 == 0:
        print(number, "is even")
    else:
        print(number, "is odd")
```

### Output

```text
12 is even
7 is odd
4 is even
9 is odd
15 is odd
20 is even
```

### Explanation

প্রতিটি iteration-এ একটি সংখ্যা নেওয়া হয়।

- Remainder `0` হলে `if` block চলে।
- অন্যথায় `else` block চলে।

এখানে `else` মানে সংখ্যাটি even নয়, তাই odd।

## 4. Counting Numbers Based on a Condition

Loop ও condition ব্যবহার করে নির্দিষ্ট শর্ত পূরণকারী element গণনা করা যায়।

ধরি, একটি list-এ কয়টি সংখ্যা `10`-এর বড় তা বের করব।

### Code

```python
numbers = [5, 15, 8, 20, 12, 3]

count = 0

for number in numbers:
    if number > 10:
        count += 1

print("Count:", count)
```

### Output

```text
Count: 3
```

### Explanation

List-এর মধ্যে `15`, `20` ও `12` হলো `10`-এর বড়।

তাই মোট count `3`।

**মনে রাখবে:**

- `count = 0` দিয়ে শুরু করতে হয়।
- Condition True হলে `count += 1` করতে হয়।
- Loop শেষ হলে final count পাওয়া যায়।

## 5. Calculating the Sum of Selected Numbers

কখনো সব সংখ্যার sum নয়, শুধু condition পূরণকারী সংখ্যাগুলোর sum বের করতে হয়।

ধরি, list-এর even সংখ্যাগুলোর sum বের করব।

### Code

```python
numbers = [2, 5, 8, 11, 14, 17]

total = 0

for number in numbers:
    if number % 2 == 0:
        total += number

print("Sum of even numbers:", total)
```

### Output

```text
Sum of even numbers: 24
```

কারণ:

\[
2+8+14=24
\]

### Explanation

- Loop প্রতিটি সংখ্যা নেয়।
- `if` even কি না পরীক্ষা করে।
- Even হলে `total`-এ যোগ হয়।
- Odd সংখ্যা বাদ পড়ে।

এখানে `total` হলো accumulator variable।

## 6. Finding Positive, Negative and Zero Values

একটি list-এ positive, negative ও zero-এর সংখ্যা গণনা করি।

### Code

```python
numbers = [10, -5, 0, 20, -2, 0, 7]

positive = 0
negative = 0
zero = 0

for number in numbers:
    if number > 0:
        positive += 1
    elif number < 0:
        negative += 1
    else:
        zero += 1

print("Positive:", positive)
print("Negative:", negative)
print("Zero:", zero)
```

### Output

```text
Positive: 3
Negative: 2
Zero: 2
```

### Explanation

- `if number > 0`: positive সংখ্যা গণনা করে।
- `elif number < 0`: negative সংখ্যা গণনা করে।
- `else`: শূন্য গণনা করে।

এখানে একটি সংখ্যার জন্য তিনটি category-এর মধ্যে ঠিক একটিতে count বাড়বে।

## 7. Checking Pass and Fail

শিক্ষার্থীদের marks থেকে pass ও fail-এর সংখ্যা গণনা করা একটি বাস্তব উদাহরণ।

ধরি, `40` বা তার বেশি marks পেলে pass।

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

Pass করেছে: `75`, `60`, `90`, `40`

Fail করেছে: `32`, `25`

তাই:

- Passed = 4
- Failed = 2

**Important:** Pass mark problem অনুযায়ী পরিবর্তিত হতে পারে। এখানে শুধু উদাহরণ হিসেবে `40` ব্যবহার করা হয়েছে।

## 8. Using Multiple Conditions Inside a Loop

একটি loop-এর মধ্যে একাধিক condition ব্যবহার করা যায়।

ধরি, প্রতিটি সংখ্যার জন্য পরীক্ষা করব সেটি positive, even কি না।

### Code

```python
numbers = [2, -4, 7, 10, -8, 0]

for number in numbers:
    if number > 0 and number % 2 == 0:
        print(number, "is positive and even")
```

### Output

```text
2 is positive and even
10 is positive and even
```

### Explanation

এখানে দুটি condition একসঙ্গে True হতে হবে:

1. `number > 0`
2. `number % 2 == 0`

`and` ব্যবহারের কারণে দুটো condition-ই True হলেই সংখ্যাটি print হবে।

উদাহরণ:

- `2`: positive এবং even — print হবে।
- `-4`: even, কিন্তু positive নয় — print হবে না।
- `7`: positive, কিন্তু even নয় — print হবে না।
- `0`: even, কিন্তু positive নয় — print হবে না।

## 9. Using `if-elif-else` Inside a Loop

একটি list-এর প্রতিটি marks-কে grade category-তে ভাগ করতে পারি।

ধরি:

- 80 বা তার বেশি: A
- 60–79: B
- 40–59: C
- 40-এর কম: Fail

### Code

```python
marks_list = [85, 72, 55, 30, 90]

for marks in marks_list:
    if marks >= 80:
        grade = "A"
    elif marks >= 60:
        grade = "B"
    elif marks >= 40:
        grade = "C"
    else:
        grade = "Fail"

    print(marks, "->", grade)
```

### Output

```text
85 -> A
72 -> B
55 -> C
30 -> Fail
90 -> A
```

### Explanation

প্রতিটি marks-এর জন্য conditions ওপর থেকে নিচে পরীক্ষা হয়।

প্রথম যে condition True হয়, সেই block execute হয়। তাই condition-এর order গুরুত্বপূর্ণ।

যদি `marks >= 40` condition-টি সবার আগে রাখা হয়, তাহলে `85`-এর মতো marks-ও C category-তে চলে যেতে পারে।

**Rule:** সাধারণত সবচেয়ে নির্দিষ্ট বা বড় threshold-এর condition আগে লিখবে।

## 10. Combining a `while` Loop with Conditions

`while` loop-এর সঙ্গে condition ব্যবহার করে user input process করা যায়।

ধরি, user `0` দিলে input বন্ধ হবে। এর মধ্যে positive সংখ্যার sum বের করব।

### Code

```python
total = 0

while True:
    number = int(input("Enter a number (0 to stop): "))

    if number == 0:
        break

    if number > 0:
        total += number
    else:
        print("Negative number ignored.")

print("Sum of positive numbers:", total)
```

### Sample Input

```text
10
-5
20
0
```

### Output

```text
Negative number ignored.
Sum of positive numbers: 30
```

### Explanation

- `while True` বারবার input নেয়।
- `number == 0` হলে `break` loop বন্ধ করে।
- Positive হলে sum-এ যোগ হয়।
- Negative হলে message দেখিয়ে সংখ্যাটি বাদ দেওয়া হয়।

এখানে `0` sentinel হিসেবে ব্যবহৃত হয়েছে, তাই সেটি sum-এ যোগ হয় না।

## 11. Combining Nested Loops with Conditions

Nested loop-এর মধ্যে condition ব্যবহার করে pattern তৈরি করা যায়।

ধরি, ১ থেকে ৩ পর্যন্ত প্রতিটি row-তে ১ থেকে ৪ পর্যন্ত সংখ্যা print করব, কিন্তু শুধু even সংখ্যা print করব।

### Code

```python
for row in range(1, 4):
    for number in range(1, 5):
        if number % 2 == 0:
            print(number, end=" ")
    print()
```

### Output

```text
2 4
2 4
2 4
```

### Explanation

- Outer loop তিনটি row তৈরি করে।
- Inner loop `1` থেকে `4` পর্যন্ত চলে।
- `if` শুধু even সংখ্যা print করে।
- `print()` পরের row-তে যায়।

এখানে প্রতিটি row-তে একই even সংখ্যা print হয়।

## 12. Searching for a Value Using Conditions

Loop ও condition দিয়ে list-এর মধ্যে target search করা যায়।

### Code

```python
numbers = [12, 25, 37, 48, 59]
target = 37

found = False

for number in numbers:
    if number == target:
        found = True
        break

if found:
    print("Target found")
else:
    print("Target not found")
```

### Output

```text
Target found
```

### Explanation

- Loop প্রতিটি element পরীক্ষা করে।
- Match হলে `found = True` হয়।
- `break` search বন্ধ করে।
- Loop শেষে `found` অনুযায়ী result দেখানো হয়।

এটি Linear Search-এর একটি সাধারণ উদাহরণ।

## 13. Finding Numbers That Satisfy Multiple Conditions

ধরি, `1` থেকে `30` পর্যন্ত যেসব সংখ্যা `3` ও `5`—দুটো দিয়েই বিভাজ্য, সেগুলো print করতে হবে।

### Code

```python
for number in range(1, 31):
    if number % 3 == 0 and number % 5 == 0:
        print(number)
```

### Output

```text
15
30
```

### Explanation

কোনো সংখ্যা `3` দিয়ে বিভাজ্য হলে:

```python
number % 3 == 0
```

আর `5` দিয়ে বিভাজ্য হলে:

```python
number % 5 == 0
```

দুটো condition-ই True হলে সংখ্যাটি print হয়।

এখানে `and` ব্যবহার করা হয়েছে, কারণ দুটি শর্তই পূরণ করতে হবে।

## 14. Dry Run Example

Code:

```python
numbers = [3, 6, 9, 12, 15]

count = 0
total = 0

for number in numbers:
    if number % 2 == 0:
        count += 1
        total += number

print("Count:", count)
print("Sum:", total)
```

### Dry Run Table

| Iteration | Number | Even? | Count | Total |
|---:|---:|---|---:|---:|
| 1 | 3 | No | 0 | 0 |
| 2 | 6 | Yes | 1 | 6 |
| 3 | 9 | No | 1 | 6 |
| 4 | 12 | Yes | 2 | 18 |
| 5 | 15 | No | 2 | 18 |

### Output

```text
Count: 2
Sum: 18
```

এখানে `6` ও `12` শুধু even সংখ্যা। তাই count `2` এবং sum `18`।

## 15. Common Mistakes

### Mistake 1: Incorrect Indentation

ভুল:

```python
for number in numbers:
if number > 10:
    print(number)
```

সঠিক:

```python
for number in numbers:
    if number > 10:
        print(number)
```

`if`-কে loop-এর ভেতরে রাখতে indent করতে হবে।

### Mistake 2: Initializing the Counter Inside the Loop

ভুল:

```python
for number in numbers:
    count = 0

    if number > 10:
        count += 1
```

প্রতিটি iteration-এ `count` আবার `0` হয়ে যাচ্ছে।

সঠিক:

```python
count = 0

for number in numbers:
    if number > 10:
        count += 1
```

### Mistake 3: Using `and` Instead of `or`

ধরি, `0` থেকে `100`-এর বাইরে marks হলে invalid।

ভুল:

```python
if marks < 0 and marks > 100:
    print("Invalid")
```

একটি সাধারণ number একই সঙ্গে `0`-এর কম ও `100`-এর বেশি হতে পারে না।

সঠিক:

```python
if marks < 0 or marks > 100:
    print("Invalid")
```

### Mistake 4: Incorrect Condition Order

Grade বের করার সময় বড় threshold আগে পরীক্ষা করতে হয়।

ভুল:

```python
if marks >= 40:
    grade = "C"
elif marks >= 80:
    grade = "A"
```

`80` বা তার বেশি marks-ও প্রথম condition-এ True হবে।

সঠিক:

```python
if marks >= 80:
    grade = "A"
elif marks >= 40:
    grade = "C"
```

### Mistake 5: Forgetting to Update the Accumulator

ভুল:

```python
if number % 2 == 0:
    total = number
```

এতে প্রতিবার আগের total মুছে যায়।

সঠিক:

```python
if number % 2 == 0:
    total += number
```

### Mistake 6: Unnecessary `break`

যদি সব matching element খুঁজতে হয়, তাহলে প্রথম match-এর পরে `break` দিলে বাকি element পরীক্ষা হবে না।

### Mistake 7: Incorrect Loop Condition

`while` loop ব্যবহার করলে condition ও variable update ঠিক থাকতে হবে। না হলে loop অনন্তকাল চলতে পারে।

## 16. Practice Exercises

### Exercise 1

`[10, 15, 20, 25, 30]` list থেকে শুধু even সংখ্যা print করো।

### Exercise 2

`[5, 12, 18, 25, 30, 7]` list-এ `10`-এর বড় সংখ্যার count বের করো।

### Exercise 3

`1` থেকে `50` পর্যন্ত যেসব সংখ্যা `5` দিয়ে বিভাজ্য, সেগুলোর sum বের করো।

### Exercise 4

`[45, 78, 32, 90, 55, 20]` marks list থেকে pass ও fail-এর সংখ্যা বের করো। Pass mark `40`।

### Exercise 5

`1` থেকে `100` পর্যন্ত `3` ও `5`—দুটো দিয়েই বিভাজ্য সংখ্যা print করো।

### Exercise 6

User-এর কাছ থেকে ৫টি integer নিয়ে positive, negative ও zero-এর সংখ্যা গণনা করো।

### Exercise 7

নিচের code-এর output নির্ণয় করো:

```python
numbers = [2, 5, 8, 11, 14]
total = 0

for number in numbers:
    if number % 2 == 0:
        total += number

print(total)
```

### Exercise 8

নিচের code-এ ভুলটি খুঁজে বের করো:

```python
numbers = [5, 15, 25, 35]
count = 0

for number in numbers:
    if number > 10:
        count = 0
        count += 1

print(count)
```

### Exercise 9

`1` থেকে `20` পর্যন্ত even সংখ্যাগুলোর sum ও count বের করো।

### Exercise 10

একটি list থেকে positive এবং even—দুটো condition পূরণকারী সংখ্যা print করো।

## 17. Practice Answer Key

### Answer 1

```python
numbers = [10, 15, 20, 25, 30]

for number in numbers:
    if number % 2 == 0:
        print(number)
```

Output:

```text
10
20
30
```

### Answer 2

```python
numbers = [5, 12, 18, 25, 30, 7]
count = 0

for number in numbers:
    if number > 10:
        count += 1

print(count)
```

Output:

```text
4
```

### Answer 3

```python
total = 0

for number in range(1, 51):
    if number % 5 == 0:
        total += number

print(total)
```

Output:

```text
275
```

### Answer 4

```python
marks_list = [45, 78, 32, 90, 55, 20]

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

Output:

```text
Passed: 4
Failed: 2
```

### Answer 5

```python
for number in range(1, 101):
    if number % 3 == 0 and number % 5 == 0:
        print(number)
```

Output:

```text
15
30
45
60
75
90
```

### Answer 6

```python
positive = 0
negative = 0
zero = 0

for i in range(5):
    number = int(input("Enter an integer: "))

    if number > 0:
        positive += 1
    elif number < 0:
        negative += 1
    else:
        zero += 1

print("Positive:", positive)
print("Negative:", negative)
print("Zero:", zero)
```

### Answer 7

Output:

```text
24
```

কারণ even সংখ্যাগুলো `2`, `8` ও `14`।

\[
2+8+14=24
\]

### Answer 8

সমস্যা হলো `count = 0` condition-এর ভেতরে রাখা হয়েছে। প্রতিবার `number > 10` হলে count আবার শূন্য হয়ে যায়।

সঠিক code:

```python
numbers = [5, 15, 25, 35]
count = 0

for number in numbers:
    if number > 10:
        count += 1

print(count)
```

Output:

```text
3
```

### Answer 9

```python
total = 0
count = 0

for number in range(1, 21):
    if number % 2 == 0:
        total += number
        count += 1

print("Sum:", total)
print("Count:", count)
```

Output:

```text
Sum: 110
Count: 10
```

### Answer 10

```python
numbers = [-4, 2, 6, -8, 10, 13, 0]

for number in numbers:
    if number > 0 and number % 2 == 0:
        print(number)
```

Output:

```text
2
6
10
```

## 18. Chapter Summary

- Loop একই কাজ বারবার করে এবং condition decision নেয়।
- `for` ও `if` ব্যবহার করে list-এর element filter করা যায়।
- Counter variable দিয়ে নির্দিষ্ট condition পূরণকারী element গণনা করা যায়।
- Accumulator variable দিয়ে নির্বাচিত সংখ্যাগুলোর sum বের করা যায়।
- `if-elif-else` দিয়ে data-কে category-তে ভাগ করা যায়।
- `and` ব্যবহার করলে সব condition True হতে হয়।
- `or` ব্যবহার করলে অন্তত একটি condition True হলেই হয়।
- Nested loop-এর মধ্যেও conditional statement ব্যবহার করা যায়।
- Condition-এর order সঠিক রাখা গুরুত্বপূর্ণ।
- Counter ও accumulator loop-এর আগে initialize করতে হয়।

## 19. Completion Checklist

- [ ] Loop ও conditional statement একসঙ্গে ব্যবহার করতে পারি।
- [ ] Even ও odd সংখ্যা বের করতে পারি।
- [ ] Condition অনুযায়ী count ও sum বের করতে পারি।
- [ ] Positive, negative ও zero গণনা করতে পারি।
- [ ] Pass/fail ও grade নির্ধারণ করতে পারি।
- [ ] Multiple conditions ব্যবহার করতে পারি।
- [ ] Nested loop-এর মধ্যে condition ব্যবহার করতে পারি।
- [ ] Dry run table তৈরি করতে পারি।
- [ ] Common mistakes শনাক্ত করতে পারি।

**Next Topic:** `65_Understanding_Loop_Based_Problems.md`