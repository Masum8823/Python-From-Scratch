# 29. Counting Forward and Backward

## 1. Introduction

Python-এ loop ব্যবহার করে সহজেই সামনে (forward) এবং পেছনে (backward) counting করা যায়।

- **Forward counting:** ছোট সংখ্যা থেকে বড় সংখ্যার দিকে গণনা করা।
- **Backward counting:** বড় সংখ্যা থেকে ছোট সংখ্যার দিকে গণনা করা।

এ কাজের জন্য `for` loop-এর সঙ্গে `range()` function খুবই উপযোগী।

## 2. Forward Counting

Forward counting-এ সংখ্যা সাধারণত ছোট থেকে বড় হয়।

### Example: Counting from 1 to 10

```python
for number in range(1, 11):
    print(number)
```

**Output:**

```text
1
2
3
4
5
6
7
8
9
10
```

এখানে `range(1, 11)` ব্যবহার করা হয়েছে, কারণ `stop` value `11` অন্তর্ভুক্ত হয় না।

### Example: Counting from 5 to 15

```python
for number in range(5, 16):
    print(number)
```

**Output:**

```text
5
6
7
8
9
10
11
12
13
14
15
```

## 3. Forward Counting with a Step

সব সময় এক করে বাড়তে হবে এমন নয়। চাইলে 2, 3 বা অন্য কোনো পরিমাণ করে বাড়ানো যায়।

### Counting by 2

```python
for number in range(2, 21, 2):
    print(number)
```

**Output:**

```text
2
4
6
8
10
12
14
16
18
20
```

### Counting by 3

```python
for number in range(3, 31, 3):
    print(number)
```

**Output:**

```text
3
6
9
12
15
18
21
24
27
30
```

### Counting by 5

```python
for number in range(5, 51, 5):
    print(number)
```

**Output:**

```text
5
10
15
20
25
30
35
40
45
50
```

**মনে রাখবে:** `step` নির্ধারণ করে প্রতিবার কত করে সংখ্যা বাড়বে বা কমবে।

## 4. Backward Counting

Backward counting-এ বড় সংখ্যা থেকে ছোট সংখ্যার দিকে যাওয়া হয়। এ জন্য `range()`-এ negative step ব্যবহার করতে হয়।

### Example: Counting from 10 to 1

```python
for number in range(10, 0, -1):
    print(number)
```

**Output:**

```text
10
9
8
7
6
5
4
3
2
1
```

এখানে:

- Start = `10`
- Stop = `0`
- Step = `-1`

প্রতিবার 1 করে কমেছে। `0` print হয়নি, কারণ stop value অন্তর্ভুক্ত হয় না।

### Example: Counting from 20 to 10

```python
for number in range(20, 9, -1):
    print(number)
```

**Output:**

```text
20
19
18
17
16
15
14
13
12
11
10
```

`10`-ও print করার জন্য stop value `9` রাখা হয়েছে।

## 5. Backward Counting with Different Steps

### Counting backward by 2

```python
for number in range(20, 0, -2):
    print(number)
```

**Output:**

```text
20
18
16
14
12
10
8
6
4
2
```

### Counting backward by 3

```python
for number in range(30, 0, -3):
    print(number)
```

**Output:**

```text
30
27
24
21
18
15
12
9
6
3
```

এখানে প্রতিবার যথাক্রমে 2 ও 3 করে কমেছে।

## 6. Understanding Forward and Backward Counting

নিচের table-টি দেখো:

| Code | Direction | Step |
|---|---|---:|
| `range(1, 6)` | Forward | `+1` |
| `range(1, 11, 2)` | Forward | `+2` |
| `range(10, 0, -1)` | Backward | `-1` |
| `range(20, 0, -2)` | Backward | `-2` |

**সহজ নিয়ম:**

- সামনে counting-এর জন্য সাধারণত positive step।
- পেছনে counting-এর জন্য negative step।
- `stop` value কখনোই sequence-এর অংশ নয়।
- `step = 0` ব্যবহার করা যায় না।

## 7. Dry Run: Forward Counting

Code:

```python
for number in range(2, 8, 2):
    print(number)
```

**Dry Run Table:**

| Iteration | `number` | Output |
|---|---:|---:|
| 1 | 2 | 2 |
| 2 | 4 | 4 |
| 3 | 6 | 6 |

পরবর্তী value `8`, কিন্তু `stop = 8`, তাই এটি অন্তর্ভুক্ত হয় না।

**Output:**

```text
2
4
6
```

## 8. Dry Run: Backward Counting

Code:

```python
for number in range(9, 0, -3):
    print(number)
```

**Dry Run Table:**

| Iteration | `number` | পরবর্তী value |
|---|---:|---:|
| 1 | 9 | 6 |
| 2 | 6 | 3 |
| 3 | 3 | 0 |

পরবর্তী value `0`, যা stop value। তাই loop এখানেই শেষ।

**Output:**

```text
9
6
3
```

## 9. Countdown Program

Countdown হলো নির্দিষ্ট সংখ্যা থেকে 1 পর্যন্ত পিছিয়ে গণনা করা। এটি timer, quiz বা launch sequence-এর মতো কাজে ব্যবহার করা যায়।

```python
print("Countdown started!")

for number in range(5, 0, -1):
    print(number)

print("Finished!")
```

**Output:**

```text
Countdown started!
5
4
3
2
1
Finished!
```

এখানে loop শেষ হওয়ার পর `Finished!` print হয়েছে।

## 10. Countdown with a Message

```python
for number in range(5, 0, -1):
    print("Remaining:", number)

print("Time is up!")
```

**Output:**

```text
Remaining: 5
Remaining: 4
Remaining: 3
Remaining: 2
Remaining: 1
Time is up!
```

এখানে প্রতিটি iteration-এ সংখ্যার সঙ্গে একটি message দেখানো হয়েছে।

## 11. Counting Forward and Backward Using `while`

`for` loop ছাড়াও `while` ব্যবহার করে counting করা যায়। এখানে variable নিজে update করতে হয়।

### Forward counting

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

**Output:**

```text
1
2
3
4
5
```

### Backward counting

```python
number = 5

while number >= 1:
    print(number)
    number -= 1
```

**Output:**

```text
5
4
3
2
1
```

**পার্থক্য:** `while` loop-এ variable update করতে ভুললে infinite loop হতে পারে। `for` loop-এর ক্ষেত্রে `range()` নিজেই পরবর্তী value সরবরাহ করে।

## 12. Comparing `for` and `while` for Counting

| বিষয় | `for` loop | `while` loop |
|---|---|---|
| ব্যবহার | নির্দিষ্ট sequence-এ counting | Condition-নির্ভর counting |
| Variable update | `range()` পরবর্তী value দেয় | সাধারণত নিজে update করতে হয় |
| Infinite loop-এর ঝুঁকি | সাধারণ range-এ কম | Update ভুল হলে বেশি |
| উদাহরণ | `range(1, 6)` | `while number <= 5` |

নির্দিষ্ট সংখ্যক বার counting করার জন্য `for` ও `range()` সাধারণত সহজ পদ্ধতি। কোনো condition পূরণ না হওয়া পর্যন্ত চলতে হলে `while` উপযোগী হতে পারে।

## 13. Common Mistakes

### Mistake 1: Forgetting the negative step

ভুল:

```python
for number in range(10, 0):
    print(number)
```

এখানে কোনো output হবে না, কারণ default step `+1`, কিন্তু start `10` এবং stop `0`।

সঠিক:

```python
for number in range(10, 0, -1):
    print(number)
```

### Mistake 2: Including the stop value incorrectly

```python
for number in range(1, 10):
    print(number)
```

এখানে `10` print হবে না।

`1` থেকে `10` পর্যন্ত print করতে:

```python
for number in range(1, 11):
    print(number)
```

### Mistake 3: Updating a `while` loop in the wrong direction

ভুল:

```python
number = 5

while number >= 1:
    print(number)
    number += 1
```

এখানে `number` ক্রমাগত বাড়ছে। ফলে condition সত্যই থেকে যাবে এবং loop চলতেই থাকবে।

সঠিক:

```python
number = 5

while number >= 1:
    print(number)
    number -= 1
```

### Mistake 4: Using zero as the step

```python
range(10, 0, 0)
```

এটি `ValueError` তৈরি করবে। Step অবশ্যই non-zero integer হতে হবে।

## 14. Practice Exercises

### Exercise 1

`1` থেকে `20` পর্যন্ত forward counting করো।

### Exercise 2

`15` থেকে `1` পর্যন্ত backward counting করো।

### Exercise 3

`2` থেকে `30` পর্যন্ত even number print করো।

### Exercise 4

`30` থেকে `3` পর্যন্ত 3 করে কমিয়ে print করো।

### Exercise 5

`10` থেকে `1` পর্যন্ত countdown করো। শেষে `Blast off!` print করো।

### Exercise 6

নিচের code-এর output কী হবে?

```python
for number in range(4, 15, 4):
    print(number)
```

### Exercise 7

নিচের code-এর output কী হবে?

```python
for number in range(12, 1, -5):
    print(number)
```

### Exercise 8

`while` loop ব্যবহার করে `5, 4, 3, 2, 1` print করো।

## 15. Practice Answer Key

### Answer 1

```python
for number in range(1, 21):
    print(number)
```

### Answer 2

```python
for number in range(15, 0, -1):
    print(number)
```

### Answer 3

```python
for number in range(2, 31, 2):
    print(number)
```

### Answer 4

```python
for number in range(30, 2, -3):
    print(number)
```

Output:

```text
30
27
24
21
18
15
12
9
6
3
```

### Answer 5

```python
for number in range(10, 0, -1):
    print(number)

print("Blast off!")
```

### Answer 6

```text
4
8
12
```

কারণ sequence-এর পরবর্তী value `16`, যা stop value `15`-এর সীমার বাইরে।

### Answer 7

```text
12
7
2
```

প্রতিবার 5 করে কমেছে। Stop value `1` অন্তর্ভুক্ত হয়নি।

### Answer 8

```python
number = 5

while number >= 1:
    print(number)
    number -= 1
```

## 16. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Forward counting এবং backward counting।
- Positive ও negative step-এর ব্যবহার।
- `range()` দিয়ে even number ও multiples print করা।
- Countdown program তৈরি করা।
- `for` ও `while` দিয়ে counting করা।
- Stop value এবং step direction-সংক্রান্ত ভুল এড়ানো।

### Quick Revision Table

| প্রয়োজন | Code |
|---|---|
| 1 থেকে 10 | `range(1, 11)` |
| 2 করে সামনে | `range(2, 11, 2)` |
| 10 থেকে 1 | `range(10, 0, -1)` |
| 2 করে পেছনে | `range(10, 0, -2)` |
| 3 করে পেছনে | `range(15, 0, -3)` |

## 17. Completion Checklist

- [ ] Forward counting করতে পারি।
- [ ] Backward counting করতে পারি।
- [ ] Positive ও negative step সঠিকভাবে ব্যবহার করতে পারি।
- [ ] Countdown program লিখতে পারি।
- [ ] `for` ও `while` দিয়ে counting-এর পার্থক্য বুঝি।
- [ ] Stop value কেন বাদ যায়, তা ব্যাখ্যা করতে পারি।

**Next Topic:** `30_Common_range_Mistakes.md`
