# 67. Loop Invariants: Basic Introduction

## 1. Introduction

Loop invariant হলো এমন একটি condition বা property, যা loop-এর প্রতিটি iteration-এর নির্দিষ্ট একটি point-এ সত্য থাকে।

সহজভাবে বললে, loop চলার সময় এমন একটি নিয়ম থাকতে পারে, যা প্রতিবার loop execute হওয়ার পরও ঠিক থাকে।

ধরি, আমরা `1` থেকে `5` পর্যন্ত সংখ্যার sum বের করছি। প্রতিবার নতুন সংখ্যা যোগ করার পর `total`-এর value হবে এখন পর্যন্ত যোগ করা সংখ্যাগুলোর sum।

এই সম্পর্কটি আমাদের বুঝতে সাহায্য করে যে program সঠিকভাবে কাজ করছে কি না।

### Example

```python
total = 0

for number in range(1, 6):
    total += number
    print(total)
```

Output:

```text
1
3
6
10
15
```

এখানে প্রতিটি iteration শেষে `total` এখন পর্যন্ত process করা সংখ্যাগুলোর sum-এর সমান।

যেমন:

- প্রথম iteration শেষে: `total = 1`
- দ্বিতীয় iteration শেষে: `total = 1 + 2 = 3`
- তৃতীয় iteration শেষে: `total = 1 + 2 + 3 = 6`

এই সম্পর্কটি হলো loop invariant-এর একটি সহজ উদাহরণ।

## 2. Why Are Loop Invariants Important?

Loop invariant ব্যবহার করে loop-এর logic বুঝতে এবং algorithm সঠিক কি না বিশ্লেষণ করতে সুবিধা হয়।

এর প্রধান ব্যবহার:

1. Loop-এর correctness বুঝতে সাহায্য করা।
2. Counter ও accumulator-এর logic যাচাই করা।
3. Algorithm-এর ভুল খুঁজে বের করা।
4. প্রতিটি iteration-এর পরে variable-এর অর্থ পরিষ্কার রাখা।
5. Algorithm correctness-এর formal proof তৈরি করতে সাহায্য করা।

Beginner পর্যায়ে loop invariant বোঝার জন্য mathematical proof মুখস্থ করার চেয়ে উদাহরণ দিয়ে variable-এর পরিবর্তন অনুসরণ করা বেশি কার্যকর।

## 3. Understanding a Simple Loop Invariant

ধরি, `1` থেকে `n` পর্যন্ত সংখ্যার sum বের করতে হবে।

```python
n = 5
total = 0

for number in range(1, n + 1):
    total += number

print(total)
```

Output:

```text
15
```

এখানে একটি invariant নির্ধারণ করা যায়:

**প্রতিটি iteration শেষে `total` এখন পর্যন্ত process করা সংখ্যাগুলোর sum-এর সমান।**

### Dry Run Table

| Iteration | Current number | Total after iteration |
|---:|---:|---:|
| 1 | 1 | 1 |
| 2 | 2 | 3 |
| 3 | 3 | 6 |
| 4 | 4 | 10 |
| 5 | 5 | 15 |

প্রতিটি iteration-এ invariant সত্য থাকে।

শেষ iteration-এর পরে সব সংখ্যা process হয়ে যায়। তাই `total`-এ সম্পূর্ণ sum পাওয়া যায়।

## 4. The Three Main Parts of a Loop Invariant

Loop invariant দিয়ে algorithm correctness ব্যাখ্যা করার সময় সাধারণত তিনটি বিষয় দেখা হয়:

1. Initialization
2. Maintenance
3. Termination

এই তিনটি বিষয় বুঝলে loop invariant-এর মূল ধারণাটি পরিষ্কার হবে।

### 4.1 Initialization

Loop-এর প্রথম iteration-এর আগে invariant সত্য কি না, তা পরীক্ষা করা হয়।

উদাহরণ:

```python
total = 0
```

Sum বের করার ক্ষেত্রে শুরুতে কোনো সংখ্যা যোগ করা হয়নি। তাই এখন পর্যন্ত process করা সংখ্যার sum `0`।

এটি initial state-এর সঙ্গে সামঞ্জস্যপূর্ণ।

### 4.2 Maintenance

প্রতিটি iteration-এ loop-এর কাজ invariant-কে সত্য রাখে কি না, তা পরীক্ষা করা হয়।

```python
total += number
```

বর্তমান সংখ্যাটি `total`-এর সঙ্গে যোগ হওয়ায় `total` এখন পর্যন্ত process করা সব সংখ্যার sum-ই থাকে।

### 4.3 Termination

Loop শেষ হলে invariant এবং loop-এর stopping condition ব্যবহার করে বোঝানো হয় যে final result সঠিক।

উদাহরণে loop `1` থেকে `5` পর্যন্ত সব সংখ্যা process করে। Loop শেষে `total = 15`।

তাই final result সঠিক।

**মনে রাখবে:** Initialization, Maintenance ও Termination হলো loop invariant দিয়ে correctness বোঝানোর গুরুত্বপূর্ণ ধাপ।

## 5. Loop Invariant in a Counting Problem

ধরি, একটি list-এর positive সংখ্যার count বের করব।

```python
numbers = [-2, 5, 0, 8, -1, 3]
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

### Loop Invariant

**প্রতিটি iteration শেষে `count` এখন পর্যন্ত process করা list-এর positive সংখ্যার সংখ্যার সমান।**

### Dry Run Table

| Number | Positive? | Count after iteration |
|---:|---|---:|
| -2 | No | 0 |
| 5 | Yes | 1 |
| 0 | No | 1 |
| 8 | Yes | 2 |
| -1 | No | 2 |
| 3 | Yes | 3 |

প্রতিটি iteration-এ invariant বজায় থাকে। Loop শেষে পুরো list process হওয়ায় `count = 3` পাওয়া যায়।

## 6. Loop Invariant in a Maximum-Finding Problem

ধরি, একটি non-empty list থেকে maximum value বের করব।

```python
numbers = [12, 5, 27, 8, 19]

maximum = numbers[0]

for number in numbers:
    if number > maximum:
        maximum = number

print(maximum)
```

Output:

```text
27
```

### Loop Invariant

**প্রতিটি iteration শেষে `maximum` হলো এখন পর্যন্ত process করা সংখ্যাগুলোর মধ্যে সবচেয়ে বড় সংখ্যা।**

### Dry Run Table

| Number | Maximum before | Maximum after |
|---:|---:|---:|
| 12 | 12 | 12 |
| 5 | 12 | 12 |
| 27 | 12 | 27 |
| 8 | 27 | 27 |
| 19 | 27 | 27 |

প্রতিবার নতুন সংখ্যাটি বর্তমান maximum-এর সঙ্গে তুলনা করা হয়। নতুন সংখ্যাটি বড় হলেই maximum update হয়।

Loop শেষে `maximum` পুরো list-এর সর্বোচ্চ value নির্দেশ করে।

এখানে list-টি non-empty হতে হবে, কারণ `numbers[0]` ব্যবহার করা হয়েছে।

## 7. Loop Invariant in a Searching Problem

ধরি, একটি list-এ target value খুঁজব।

```python
numbers = [10, 20, 30, 40, 50]
target = 40

found = False

for number in numbers:
    if number == target:
        found = True
        break

print(found)
```

Output:

```text
True
```

এখানে `found` flag ব্যবহার করা হয়েছে।

Search চলার সময় একটি গুরুত্বপূর্ণ property হলো:

**যতক্ষণ পর্যন্ত target পাওয়া যায়নি, ততক্ষণ পর্যন্ত ইতিমধ্যে পরীক্ষা করা element-গুলোর মধ্যে target নেই।**

যদি target পাওয়া যায়, `found = True` হয় এবং `break` loop বন্ধ করে।

যদি loop শেষ হয় কিন্তু target না পাওয়া যায়, তাহলে `found` False-ই থাকে।

এটি search algorithm-এর correctness বুঝতে সাহায্য করে।

## 8. Loop Invariant and Accumulator Variables

Accumulator-এর ক্ষেত্রে invariant সাধারণত বলে, variable-এ এখন পর্যন্ত process করা data-এর সঠিক aggregate value আছে।

যেমন, even সংখ্যাগুলোর sum:

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

### Loop Invariant

**প্রতিটি iteration শেষে `total` হলো এখন পর্যন্ত process করা even সংখ্যাগুলোর sum।**

Odd সংখ্যার ক্ষেত্রে `total` পরিবর্তিত হয় না। Even সংখ্যার ক্ষেত্রে বর্তমান value যোগ হয়।

এভাবেই invariant বজায় থাকে।

## 9. What Happens When an Invariant Is Broken?

কোনো ভুল statement loop invariant নষ্ট করতে পারে।

ধরি, positive সংখ্যার count বের করতে গিয়ে ভুল করে count reset করা হয়েছে।

### Incorrect Code

```python
numbers = [5, 15, 25, 35]
count = 0

for number in numbers:
    if number > 10:
        count = 0
        count += 1

print(count)
```

Output:

```text
1
```

কিন্তু সঠিক count হওয়া উচিত `3`।

### Why Is It Wrong?

প্রতিবার `number > 10` হলে:

```python
count = 0
```

আগের count মুছে যায়। ফলে `count` আর এখন পর্যন্ত পাওয়া matching সংখ্যার মোট count নির্দেশ করে না।

### Correct Code

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

এখন প্রতিটি matching element-এর জন্য count এক বাড়ে এবং invariant বজায় থাকে।

## 10. Loop Invariant in a `while` Loop

Loop invariant শুধু `for` loop-এর জন্য নয়; `while` loop-এর ক্ষেত্রেও প্রযোজ্য।

ধরি, `1` থেকে `5` পর্যন্ত sum বের করব।

```python
number = 1
total = 0

while number <= 5:
    total += number
    number += 1

print(total)
```

Output:

```text
15
```

এখানে loop-এর body শেষ হওয়ার পরে:

- `total` হলো `1` থেকে `number - 1` পর্যন্ত সংখ্যার sum।
- `number` হলো পরবর্তী যে সংখ্যাটি process করা হবে।

উদাহরণস্বরূপ, প্রথম iteration শেষে `number = 2` এবং `total = 1`।

তাই:

\[
total = 1 = 1
\]

দ্বিতীয় iteration শেষে `number = 3` এবং `total = 3`।

তাই:

\[
total = 1+2 = 3
\]

এই সম্পর্কটি প্রতিটি iteration-এর শেষে বজায় থাকে।

## 11. How to Identify a Loop Invariant

কোনো loop-এর invariant খুঁজতে এই প্রশ্নগুলো করো:

1. Loop-এর আগে variable-এর initial value কী?
2. প্রতিটি iteration-এ variable কীভাবে পরিবর্তিত হয়?
3. Iteration শেষ হলে variable কোন তথ্য নির্দেশ করে?
4. পরবর্তী iteration-এও সেই সম্পর্কটি কি সত্য থাকে?
5. Loop শেষ হলে সেই সম্পর্ক থেকে final answer কি পাওয়া যায়?

### Example

```python
total = 0

for number in range(1, 6):
    total += number
```

সম্ভাব্য invariant:

> প্রতিটি iteration শেষে `total` হলো এখন পর্যন্ত process করা সংখ্যাগুলোর sum।

এই বাক্যটি loop-এর কাজ ও `total`-এর অর্থ দুটোই ব্যাখ্যা করে।

## 12. Common Mistakes

### Mistake 1: Confusing an Invariant with a Loop Condition

Loop condition বলে loop চলবে কি না।

Invariant বলে loop-এর নির্দিষ্ট point-এ কোন property সত্য থাকে।

দুটো এক জিনিস নয়।

### Mistake 2: Ignoring Initialization

Invariant loop-এর শুরুতে সত্য না হলে শুধু loop body সঠিক হলেই যথেষ্ট নয়।

### Mistake 3: Forgetting Maintenance

প্রতিটি iteration-এ invariant বজায় আছে কি না, তা যাচাই করতে হবে।

### Mistake 4: Ignoring Termination

Loop শেষ হওয়ার পরে invariant থেকে final result পাওয়া যাচ্ছে কি না, সেটিও পরীক্ষা করতে হবে।

### Mistake 5: Writing a Vague Invariant

“`total` সঠিক আছে” বললে variable-এর অর্থ পরিষ্কার হয় না।

এর চেয়ে ভালো:

“`total` এখন পর্যন্ত process করা সংখ্যাগুলোর sum।”

### Mistake 6: Assuming Every Variable Is an Invariant

সব variable-এর জন্য invariant তৈরি করা প্রয়োজন নেই। Problem-এর correctness বোঝাতে সাহায্য করে এমন গুরুত্বপূর্ণ property নির্বাচন করো।

## 13. Practice Exercises

### Exercise 1

নিচের loop-এর জন্য একটি invariant লেখো।

```python
count = 0

for number in [2, 4, 6, 8]:
    count += 1
```

### Exercise 2

নিচের loop-এ `total` কী নির্দেশ করে?

```python
total = 0

for number in range(1, 6):
    if number % 2 != 0:
        total += number
```

### Exercise 3

নিচের code-এ invariant কেন বজায় থাকে না, ব্যাখ্যা করো।

```python
count = 0

for number in [10, 20, 30]:
    count = 0
    count += 1
```

### Exercise 4

নিচের maximum-finding loop-এর invariant লেখো।

```python
numbers = [8, 3, 15, 6]
maximum = numbers[0]

for number in numbers:
    if number > maximum:
        maximum = number
```

### Exercise 5

Loop invariant দিয়ে `1` থেকে `n` পর্যন্ত sum বের করার correctness বোঝাতে Initialization, Maintenance ও Termination—এই তিনটি ধাপ সংক্ষেপে লেখো।

## 14. Practice Answer Key

### Answer 1

প্রতিটি iteration শেষে `count` হলো এখন পর্যন্ত process করা element-এর সংখ্যা।

### Answer 2

প্রতিটি iteration শেষে `total` হলো এখন পর্যন্ত process করা odd সংখ্যাগুলোর sum।

### Answer 3

`count = 0` প্রতিটি iteration-এ আগের count মুছে দেয়। তাই count মোট process করা element-এর সংখ্যা নির্দেশ করে না।

### Answer 4

প্রতিটি iteration শেষে `maximum` হলো এখন পর্যন্ত process করা element-গুলোর মধ্যে সর্বোচ্চ value।

### Answer 5

- **Initialization:** শুরুতে `total = 0`; কোনো সংখ্যা process হয়নি, তাই sum শূন্য।
- **Maintenance:** প্রতিটি iteration-এ বর্তমান সংখ্যা `total`-এর সঙ্গে যোগ হওয়ায় `total` এখন পর্যন্ত process করা সংখ্যাগুলোর sum থাকে।
- **Termination:** Loop শেষ হলে `1` থেকে `n` পর্যন্ত সব সংখ্যা process হয়েছে। তাই `total` হলো প্রয়োজনীয় sum।

## 15. Chapter Summary

- Loop invariant হলো loop-এর নির্দিষ্ট point-এ সত্য থাকা একটি property।
- Invariant loop-এর logic এবং correctness বোঝাতে সাহায্য করে।
- Initialization-এ invariant শুরুতে সত্য কি না দেখা হয়।
- Maintenance-এ প্রতিটি iteration-এ invariant বজায় থাকে কি না দেখা হয়।
- Termination-এ loop শেষ হওয়ার পরে final result সঠিক কি না বোঝানো হয়।
- Counter, accumulator, maximum ও searching algorithm-এ invariant ব্যবহার করা যায়।
- ভুল initialization বা update invariant নষ্ট করতে পারে।
- Loop invariant একটি formal reasoning technique; এটি শুধু loop condition নয়।

## 16. Completion Checklist

- [ ] Loop invariant কী তা ব্যাখ্যা করতে পারি।
- [ ] Initialization, Maintenance ও Termination বুঝতে পারি।
- [ ] Counter ও accumulator-এর invariant লিখতে পারি।
- [ ] Maximum-finding problem-এর invariant শনাক্ত করতে পারি।
- [ ] Searching problem-এর invariant ব্যাখ্যা করতে পারি।
- [ ] ভুল update কীভাবে invariant নষ্ট করে বুঝতে পারি।
- [ ] Invariant ব্যবহার করে loop-এর correctness ব্যাখ্যা করতে পারি।

**Next Topic:** `68_Off_by_One_Errors.md`