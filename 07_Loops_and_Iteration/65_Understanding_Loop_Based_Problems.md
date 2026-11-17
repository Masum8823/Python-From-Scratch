# 65. Understanding Loop-Based Problems

## 1. Introduction

Loop-based problem হলো এমন problem, যেখানে কোনো কাজ বারবার করতে হয় অথবা একাধিক data একই নিয়মে process করতে হয়।

উদাহরণ:

- ১ থেকে ১০০ পর্যন্ত সংখ্যার sum বের করা।
- একটি list থেকে even সংখ্যা গণনা করা।
- User-এর কাছ থেকে যতক্ষণ প্রয়োজন input নেওয়া।
- একটি সংখ্যার digit গণনা করা।
- একটি list-এর maximum value খুঁজে বের করা।

এই ধরনের problem solve করার জন্য শুধু loop-এর syntax জানলেই হবে না। Problem-টি বুঝতে হবে এবং সঠিক logic তৈরি করতে হবে।

### Learning Objectives

এই Topic শেষে তুমি পারবে:

- Problem statement থেকে input ও output শনাক্ত করতে।
- Problem-এর condition বুঝতে।
- উপযুক্ত loop নির্বাচন করতে।
- Counter ও accumulator নির্ধারণ করতে।
- Problem-কে ছোট ছোট ধাপে ভাগ করতে।
- Pseudocode ও algorithm তৈরি করতে।
- Dry run করে solution যাচাই করতে।
- Common problem-solving mistakes এড়িয়ে চলতে।

## 2. Understanding the Problem Statement

Code লেখার আগে problem statement ভালোভাবে বুঝতে হবে।

ধরি, problem হলো:

**Write a Python program to find the sum of all even numbers from 1 to 10.**

প্রথমে problem-টিকে কয়েকটি প্রশ্নে ভাগ করি।

| Question | Answer |
|---|---|
| Input কী? | এখানে user input প্রয়োজন নেই |
| কোন range? | 1 থেকে 10 |
| কোন সংখ্যা নিতে হবে? | Even numbers |
| কী বের করতে হবে? | Sum |
| কোন loop ব্যবহার করা যায়? | `for` loop |
| কোন variable লাগবে? | `number`, `total` |

এখন even সংখ্যাগুলো হলো:

\[
2,4,6,8,10
\]

তাদের sum:

\[
2+4+6+8+10=30
\]

### Python Code

```python
total = 0

for number in range(1, 11):
    if number % 2 == 0:
        total += number

print("Sum:", total)
```

Output:

```text
Sum: 30
```

**মূল ধারণা:** Code লেখার আগে problem-এর input, required output এবং processing rules শনাক্ত করো।

## 3. Identifying Input, Process and Output

একটি problem-কে সাধারণত তিনটি অংশে ভাগ করা যায়।

1. **Input:** কী data পাওয়া যাবে?
2. **Process:** সেই data দিয়ে কী কাজ করতে হবে?
3. **Output:** শেষ পর্যন্ত কী ফলাফল দেখাতে হবে?

এই পদ্ধতিকে IPO (Input–Process–Output) বলা হয়।

### Example

Problem: Take five numbers from the user and calculate their average.

| Part | Description |
|---|---|
| Input | পাঁচটি সংখ্যা |
| Process | সংখ্যাগুলোর sum বের করে 5 দিয়ে ভাগ করা |
| Output | Average |

### Code

```python
total = 0

for i in range(5):
    number = float(input("Enter a number: "))
    total += number

average = total / 5

print("Average:", average)
```

Sample input:

```text
10
20
30
40
50
```

Output:

```text
Average: 30.0
```

এই problem-এ loop পাঁচবার input নেয়, accumulator sum রাখে এবং শেষে average বের হয়।

## 4. Identifying Repetition

Problem-এর কোন কাজটি বারবার করতে হবে, তা খুঁজে বের করো।

ধরি, problem হলো:

**Print the numbers from 1 to 5.**

এখানে একই কাজ—সংখ্যা print করা—পাঁচবার করতে হবে।

### Code

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

এখানে loop-এর প্রতিটি iteration-এ `number`-এর value পরিবর্তিত হয়।

### কীভাবে repetition চিনবে?

Problem statement-এ এই ধরনের নির্দেশনা থাকলে loop প্রয়োজন হতে পারে:

- Repeat a task.
- Print numbers from one value to another.
- Process every item.
- Take multiple inputs.
- Continue until a condition is met.
- Count or sum a sequence of values.

তবে প্রতিটি problem-এ loop থাকতেই হবে এমন নয়। যদি কাজটি একবারই করতে হয়, loop প্রয়োজন নাও হতে পারে।

## 5. Choosing Between `for` and `while`

সঠিক loop নির্বাচন problem-solving-এর গুরুত্বপূর্ণ অংশ।

### Use a `for` loop when

- Iteration-এর সংখ্যা জানা থাকে।
- নির্দিষ্ট range process করতে হয়।
- List, tuple বা string-এর প্রতিটি element নিয়ে কাজ করতে হয়।

Example:

```python
for number in range(1, 6):
    print(number)
```

### Use a `while` loop when

- Condition True থাকা পর্যন্ত কাজ করতে হয়।
- কতবার loop চলবে তা আগে থেকে জানা নেই।
- User-এর কাছ থেকে sentinel value না দেওয়া পর্যন্ত input নিতে হয়।

Example:

```python
while True:
    number = int(input("Enter 0 to stop: "))

    if number == 0:
        break

    print("You entered:", number)
```

### Comparison

| Situation | Suitable loop |
|---|---|
| Print 1–100 | `for` |
| Process every list item | `for` |
| Take exactly 5 inputs | `for` |
| Repeat until password is correct | `while` |
| Take input until sentinel value | `while` |
| Repeat while a condition is True | `while` |

কিছু problem `for` এবং `while`—দুটো দিয়েই solve করা যায়। সবচেয়ে সহজ ও পরিষ্কার solution বেছে নেবে।

## 6. Identifying the Required Variables

Problem অনুযায়ী সঠিক variable নির্ধারণ করতে হবে।

### Common variables

| Variable type | Purpose | Example |
|---|---|---|
| Counter | সংখ্যা গণনা | `count = 0` |
| Accumulator | Sum বা total রাখা | `total = 0` |
| Loop variable | বর্তমান iteration-এর value রাখা | `number` |
| Maximum tracker | সবচেয়ে বড় value রাখা | `maximum` |
| Minimum tracker | সবচেয়ে ছোট value রাখা | `minimum` |
| Flag | কোনো condition ঘটেছে কি না মনে রাখা | `found = False` |

### Example: Count Even Numbers

```python
numbers = [2, 5, 8, 11, 14]
count = 0

for number in numbers:
    if number % 2 == 0:
        count += 1

print(count)
```

Output:

```text
3
```

এখানে `count` হলো counter, কারণ এটি even সংখ্যার সংখ্যা গণনা করে।

### Example: Sum Even Numbers

```python
numbers = [2, 5, 8, 11, 14]
total = 0

for number in numbers:
    if number % 2 == 0:
        total += number

print(total)
```

Output:

```text
24
```

এখানে `total` হলো accumulator, কারণ এটি even সংখ্যাগুলোর sum জমা রাখে।

**মনে রাখবে:** Counter সাধারণত `+= 1` দিয়ে বাড়ে, আর accumulator-এর সঙ্গে data value যোগ হয়।

## 7. Converting a Problem into Small Steps

বড় problem সরাসরি code করার চেষ্টা না করে ছোট ছোট ধাপে ভাগ করো।

ধরি, problem হলো:

**Find the maximum number from a list.**

### Step 1: Understand the goal

List-এর সবচেয়ে বড় value বের করতে হবে।

### Step 2: Choose the variable

`maximum` variable ব্যবহার করব।

### Step 3: Initialize the variable

প্রথম element-কে initial maximum ধরব।

### Step 4: Process each element

Loop দিয়ে প্রতিটি element পরীক্ষা করব।

### Step 5: Compare and update

নতুন element `maximum`-এর চেয়ে বড় হলে maximum update করব।

### Step 6: Display the result

Loop শেষ হলে maximum print করব।

### Code

```python
numbers = [12, 5, 27, 8, 19]

maximum = numbers[0]

for number in numbers:
    if number > maximum:
        maximum = number

print("Maximum:", maximum)
```

Output:

```text
Maximum: 27
```

এই উদাহরণে list-টি non-empty ধরে নেওয়া হয়েছে। Empty list হলে `numbers[0]` ব্যবহার করার আগে সেটি পরীক্ষা করতে হবে।

## 8. Writing an Algorithm Before Coding

Algorithm হলো কোনো problem solve করার জন্য সাজানো ধাপগুলোর একটি পরিষ্কার নির্দেশনা।

Problem: Find the sum of numbers from 1 to 5.

### Algorithm

1. Start.
2. Set `total = 0`.
3. Repeat for numbers from 1 to 5.
4. Add the current number to `total`.
5. Display `total`.
6. End.

### Python Code

```python
total = 0

for number in range(1, 6):
    total += number

print("Sum:", total)
```

Output:

```text
Sum: 15
```

Algorithm আগে তৈরি করলে code লেখার সময় কোন কাজটি কখন করতে হবে তা পরিষ্কার থাকে।

## 9. Writing Pseudocode

Pseudocode হলো সাধারণ ভাষায় algorithm-এর মতো করে solution লেখা। এটি Python-এর exact syntax মেনে চলতে বাধ্য নয়।

Problem: Count positive numbers in a list.

### Pseudocode

```text
START
SET count = 0

FOR each number in the list
    IF number > 0
        INCREASE count by 1

DISPLAY count
END
```

### Python Code

```python
numbers = [-2, 5, 0, 8, -1, 3]
count = 0

for number in numbers:
    if number > 0:
        count += 1

print("Positive count:", count)
```

Output:

```text
Positive count: 3
```

Pseudocode-এর মূল উদ্দেশ্য হলো code লেখার আগে logic পরিষ্কার করা।

## 10. Understanding Loop Conditions

`while` loop-এর ক্ষেত্রে condition সঠিকভাবে নির্ধারণ করতে হবে।

Problem: Print numbers from 1 to 5.

### Code

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

এখানে:

- Initial value হলো `1`।
- Loop condition হলো `number <= 5`।
- প্রতিবার `number += 1` হয়।
- `number` যখন `6` হয়, condition False হয়ে যায়।

### Common condition mistakes

ভুল:

```python
while number < 5:
```

যদি লক্ষ্য 1 থেকে 5 পর্যন্ত print করা হয়, তাহলে এই condition-এ `5` print হবে না।

সঠিক:

```python
while number <= 5:
```

**Rule:** Problem-এ শেষ value অন্তর্ভুক্ত কি না, তা দেখে `<` বা `<=` নির্বাচন করবে।

## 11. Understanding Counters and Accumulators

Counter এবং accumulator loop-based problem-এর সবচেয়ে গুরুত্বপূর্ণ দুটি ধারণা।

### Counter example

১ থেকে ১০ পর্যন্ত even সংখ্যার সংখ্যা গণনা করা।

```python
count = 0

for number in range(1, 11):
    if number % 2 == 0:
        count += 1

print(count)
```

Output:

```text
5
```

### Accumulator example

১ থেকে ১০ পর্যন্ত even সংখ্যার sum বের করা।

```python
total = 0

for number in range(1, 11):
    if number % 2 == 0:
        total += number

print(total)
```

Output:

```text
30
```

### Key difference

- `count += 1`: একটি matching item গণনা করে।
- `total += number`: item-এর value total-এর সঙ্গে যোগ করে।

কোনো problem-এ count ও sum দুটোই চাইলে একই loop-এর মধ্যে দুটি variable রাখা যায়।

## 12. Understanding Sentinel-Based Problems

কিছু problem-এ iteration-এর সংখ্যা আগে থেকে জানা থাকে না। তখন sentinel value ব্যবহার করা যায়।

Problem: User যতগুলো positive number দেবে, সেগুলোর sum বের করো। `0` দিলে input বন্ধ হবে। Negative number বাদ দিতে হবে।

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

print("Sum:", total)
```

Sample input:

```text
10
-5
20
0
```

Output:

```text
Negative number ignored.
Sum: 30
```

### Problem-solving steps

1. Sentinel নির্ধারণ করো: `0`।
2. `while True` দিয়ে input নেওয়া শুরু করো।
3. Sentinel হলে `break` করো।
4. Positive হলে sum-এ যোগ করো।
5. Negative হলে বাদ দাও।
6. Loop শেষে sum print করো।

এই উদাহরণে `0` stopping signal, তাই সেটি data হিসেবে process করা হয় না।

## 13. Dry Running a Loop-Based Problem

Dry run হলো code execute না করে প্রতিটি iteration-এর variable value হাতে হাতে অনুসরণ করা।

Problem: Find the sum of even numbers from 1 to 6.

### Code

```python
total = 0

for number in range(1, 7):
    if number % 2 == 0:
        total += number

print(total)
```

### Dry Run Table

| Number | Even? | Total before | Total after |
|---:|---|---:|---:|
| 1 | No | 0 | 0 |
| 2 | Yes | 0 | 2 |
| 3 | No | 2 | 2 |
| 4 | Yes | 2 | 6 |
| 5 | No | 6 | 6 |
| 6 | Yes | 6 | 12 |

Output:

```text
12
```

Dry run করলে বোঝা যায় condition কখন True হচ্ছে এবং variable কীভাবে update হচ্ছে।

## 14. Checking Edge Cases

Edge case হলো এমন বিশেষ input বা situation, যেটি সাধারণ input থেকে আলাদা এবং solution-এ সমস্যা তৈরি করতে পারে।

Problem অনুযায়ী edge case পরীক্ষা করা গুরুত্বপূর্ণ।

### Example 1: Maximum of an Empty List

```python
numbers = []
```

Empty list-এর ক্ষেত্রে `numbers[0]` ব্যবহার করলে `IndexError` হবে।

সঠিকভাবে পরীক্ষা করা যায়:

```python
numbers = []

if len(numbers) == 0:
    print("List is empty.")
else:
    maximum = numbers[0]

    for number in numbers:
        if number > maximum:
            maximum = number

    print("Maximum:", maximum)
```

### Example 2: Average with No Values

```python
total = 0
count = 0
```

`total / count` করলে division by zero হবে।

সঠিকভাবে:

```python
if count > 0:
    print(total / count)
else:
    print("No values available.")
```

### Example 3: Counting Digits in Zero

```python
number = 0
count = 0

while number > 0:
    count += 1
    number //= 10

print(count)
```

Output:

```text
0
```

কিন্তু zero-এর digit count হওয়া উচিত `1`। কারণ `while number > 0` condition প্রথম থেকেই False।

সংশোধিত code:

```python
number = 0
count = 0

if number == 0:
    count = 1
else:
    while number > 0:
        count += 1
        number //= 10

print(count)
```

Output:

```text
1
```

**Lesson:** শুধু সাধারণ input নয়, zero, empty collection, negative value ও invalid input-এর মতো situation-ও বিবেচনা করো।

## 15. A Complete Problem-Solving Example

Problem: একটি list থেকে even সংখ্যাগুলোর count, sum ও average বের করো।

### Step 1: Identify the input

```python
numbers = [2, 5, 8, 11, 14, 17]
```

### Step 2: Identify the required outputs

- Even count
- Even sum
- Even average

### Step 3: Initialize variables

```python
count = 0
total = 0
```

### Step 4: Process the list

প্রতিটি সংখ্যার জন্য even condition পরীক্ষা করতে হবে।

### Step 5: Calculate the average

Even সংখ্যা থাকলেই শুধু average বের করব।

### Complete Code

```python
numbers = [2, 5, 8, 11, 14, 17]

count = 0
total = 0

for number in numbers:
    if number % 2 == 0:
        count += 1
        total += number

if count > 0:
    average = total / count
    print("Count:", count)
    print("Sum:", total)
    print("Average:", average)
else:
    print("No even numbers found.")
```

Output:

```text
Count: 3
Sum: 24
Average: 8.0
```

### Why is this solution effective?

- একটি loop-এই সব even সংখ্যা process করা হয়েছে।
- Count ও sum একই সঙ্গে update হয়েছে।
- Division by zero এড়াতে `count > 0` পরীক্ষা করা হয়েছে।
- Code সহজ ও readable রাখা হয়েছে।

## 16. Common Problem-Solving Mistakes

### Mistake 1: Coding Before Understanding the Problem

Problem না বুঝে code লেখা শুরু করলে ভুল variable বা condition নির্বাচন হতে পারে।

**Solution:** আগে input, process ও output লিখে নাও।

### Mistake 2: Incorrect Initialization

Counter ও accumulator সাধারণত loop-এর আগে initialize করতে হয়।

ভুল:

```python
for number in numbers:
    total = 0
    total += number
```

সঠিক:

```python
total = 0

for number in numbers:
    total += number
```

### Mistake 3: Incorrect Range

`range(1, 10)` শুধু `1` থেকে `9` পর্যন্ত দেয়।

`10`-কেও অন্তর্ভুক্ত করতে হলে:

```python
range(1, 11)
```

### Mistake 4: Forgetting the Update in a `while` Loop

```python
number = 1

while number <= 5:
    print(number)
```

এখানে `number` পরিবর্তন হয় না, তাই loop শেষ হবে না।

সঠিক:

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

### Mistake 5: Using the Wrong Condition

Even সংখ্যার জন্য:

```python
number % 2 == 0
```

Odd সংখ্যার জন্য:

```python
number % 2 != 0
```

Condition problem-এর requirement-এর সঙ্গে মিলতে হবে।

### Mistake 6: Updating a Variable at the Wrong Time

Sum বা count update করার আগে condition পরীক্ষা করতে হবে, যদি শুধু matching values process করার প্রয়োজন হয়।

### Mistake 7: Ignoring Edge Cases

Empty list, zero, negative numbers এবং invalid input বিবেচনা না করলে program সব situation-এ সঠিক কাজ নাও করতে পারে।

### Mistake 8: Not Testing the Output

Code লেখা শেষ হলেই কাজ শেষ নয়। Sample input দিয়ে output যাচাই করতে হবে।

## 17. A Simple Problem-Solving Checklist

যেকোনো loop-based problem solve করার সময় এই checklist অনুসরণ করতে পারো।

1. **Understand:** Problem-এ কী চাওয়া হয়েছে?
2. **Input:** কী data দেওয়া থাকবে?
3. **Output:** কী result দেখাতে হবে?
4. **Repetition:** কোন কাজটি বারবার করতে হবে?
5. **Condition:** কোন rule অনুযায়ী decision নিতে হবে?
6. **Variables:** Counter, accumulator বা অন্য কোন variable লাগবে?
7. **Loop choice:** `for` নাকি `while`?
8. **Algorithm:** ধাপগুলো আগে লিখে নাও।
9. **Code:** Python code তৈরি করো।
10. **Dry run:** কয়েকটি iteration হাতে হাতে পরীক্ষা করো।
11. **Edge cases:** বিশেষ input-গুলো বিবেচনা করো।
12. **Test:** Sample input ও output মিলিয়ে দেখো।

## 18. Practice Exercises

### Exercise 1

Problem: ১ থেকে ২০ পর্যন্ত সংখ্যার sum বের করো।

নিজে নির্ধারণ করো:
- কোন loop ব্যবহার করবে?
- কোন variable লাগবে?
- Output কত হবে?

### Exercise 2

Problem: একটি list থেকে positive সংখ্যার count বের করো।

```python
numbers = [-5, 10, 0, 8, -2, 15]
```

### Exercise 3

Problem: User-এর কাছ থেকে ৫টি সংখ্যা নিয়ে সবচেয়ে ছোট সংখ্যাটি বের করো।

### Exercise 4

Problem: `1` থেকে `50` পর্যন্ত যেসব সংখ্যা `3` দিয়ে বিভাজ্য, সেগুলোর count বের করো।

### Exercise 5

Problem: User `0` না দেওয়া পর্যন্ত input নাও এবং positive সংখ্যাগুলোর sum বের করো।

### Exercise 6

Problem: একটি list থেকে even সংখ্যাগুলোর count ও sum একই loop-এ বের করো।

```python
numbers = [4, 7, 10, 13, 16, 19]
```

### Exercise 7: Output Prediction

নিচের code-এর output কী?

```python
total = 0

for number in range(1, 6):
    if number > 2:
        total += number

print(total)
```

### Exercise 8: Find the Error

নিচের code-এ problem কী?

```python
count = 0

for number in [5, 15, 25, 35]:
    if number > 10:
        count = 0
        count += 1

print(count)
```

### Exercise 9: Algorithm Writing

`1` থেকে `10` পর্যন্ত odd সংখ্যাগুলোর sum বের করার algorithm লেখো।

### Exercise 10: Complete Problem

একটি list থেকে:
- Positive সংখ্যা গণনা করো।
- Negative সংখ্যা গণনা করো।
- Zero-এর সংখ্যা গণনা করো।

Input list:

```python
numbers = [5, -2, 0, 8, -7, 0, 3]
```

## 19. Practice Answer Key

### Answer 1

```python
total = 0

for number in range(1, 21):
    total += number

print(total)
```

Output:

```text
210
```

### Answer 2

```python
numbers = [-5, 10, 0, 8, -2, 15]
count = 0

for number in numbers:
    if number > 0:
        count += 1

print(count)
```

Output:

```text
3
```

### Answer 3

```python
numbers = []

for i in range(5):
    number = int(input("Enter a number: "))
    numbers.append(number)

minimum = numbers[0]

for number in numbers:
    if number < minimum:
        minimum = number

print("Minimum:", minimum)
```

### Answer 4

```python
count = 0

for number in range(1, 51):
    if number % 3 == 0:
        count += 1

print(count)
```

Output:

```text
16
```

### Answer 5

```python
total = 0

while True:
    number = int(input("Enter a number (0 to stop): "))

    if number == 0:
        break

    if number > 0:
        total += number

print("Sum:", total)
```

### Answer 6

```python
numbers = [4, 7, 10, 13, 16, 19]

count = 0
total = 0

for number in numbers:
    if number % 2 == 0:
        count += 1
        total += number

print("Count:", count)
print("Sum:", total)
```

Output:

```text
Count: 3
Sum: 30
```

### Answer 7

Output:

```text
12
```

কারণ `3 + 4 + 5 = 12`।

### Answer 8

সমস্যা হলো `count = 0` loop-এর ভেতরে condition-এর অধীনে রাখা হয়েছে। ফলে প্রতিবার matching value পাওয়ার সময় count আবার reset হচ্ছে।

সঠিক code:

```python
count = 0

for number in [5, 15, 25, 35]:
    if number > 10:
        count += 1

print(count)
```

Output:

```text
3
```

### Answer 9

Algorithm:

1. Start.
2. Set `total = 0`.
3. Repeat for numbers from 1 to 10.
4. If the number is odd, add it to `total`.
5. Display `total`.
6. End.

Python code:

```python
total = 0

for number in range(1, 11):
    if number % 2 != 0:
        total += number

print(total)
```

Output:

```text
25
```

### Answer 10

```python
numbers = [5, -2, 0, 8, -7, 0, 3]

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

Output:

```text
Positive: 3
Negative: 2
Zero: 2
```

## 20. Chapter Summary

- Loop-based problem-এ একই কাজ বারবার করতে হয়।
- Code লেখার আগে input, process ও output শনাক্ত করতে হবে।
- নির্দিষ্ট iteration-এর জন্য সাধারণত `for` loop সুবিধাজনক।
- Condition-নির্ভর repetition-এর জন্য `while` loop ব্যবহার করা যায়।
- Counter দিয়ে সংখ্যা গণনা করা হয়।
- Accumulator দিয়ে sum বা total রাখা হয়।
- Algorithm ও pseudocode problem-এর logic পরিষ্কার করে।
- Dry run করে variable-এর পরিবর্তন বোঝা যায়।
- Edge case পরীক্ষা করা গুরুত্বপূর্ণ।
- Code-এর output sample result-এর সঙ্গে মিলিয়ে যাচাই করতে হবে।

## 21. Completion Checklist

- [ ] Problem statement বিশ্লেষণ করতে পারি।
- [ ] Input, process ও output শনাক্ত করতে পারি।
- [ ] `for` ও `while`-এর মধ্যে উপযুক্ত loop নির্বাচন করতে পারি।
- [ ] Counter ও accumulator ব্যবহার করতে পারি।
- [ ] Algorithm ও pseudocode লিখতে পারি।
- [ ] Loop-এর dry run করতে পারি।
- [ ] Edge case বিবেচনা করতে পারি।
- [ ] Loop-based problem-এর ভুল শনাক্ত করতে পারি।
- [ ] নিজের solution test করতে পারি।

**Next Topic:** `66_Dry_Running_and_Tracing_Loops.md`