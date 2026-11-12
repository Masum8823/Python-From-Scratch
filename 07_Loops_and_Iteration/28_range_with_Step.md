# 28. `range()` with Step

## 1. Introduction

Python-এর `range()` function-এ তিনটি argument ব্যবহার করা যায়:

```python
range(start, stop, step)
```

এখানে:

- `start`: sequence কোথা থেকে শুরু হবে।
- `stop`: যে boundary-তে পৌঁছানোর আগেই sequence শেষ হবে।
- `step`: প্রতিবার কত করে বাড়বে বা কমবে।

**Example:**

```python
for number in range(2, 11, 2):
    print(number)
```

**Output:**

```text
2
4
6
8
10
```

এখানে `start = 2`, `stop = 11` এবং `step = 2`। তাই প্রতিবার 2 করে বেড়েছে।

## 2. Understanding the Step Value

`step` নির্ধারণ করে পরবর্তী integer কত দূরে থাকবে।

```python
print(list(range(1, 11, 1)))
print(list(range(1, 11, 2)))
print(list(range(1, 11, 3)))
```

**Output:**

```text
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
[1, 3, 5, 7, 9]
[1, 4, 7, 10]
```

পার্থক্যটি দেখো:

| Code | Step | কীভাবে এগোয় |
|---|---:|---|
| `range(1, 11, 1)` | 1 | প্রতিবার 1 করে |
| `range(1, 11, 2)` | 2 | প্রতিবার 2 করে |
| `range(1, 11, 3)` | 3 | প্রতিবার 3 করে |

**মনে রাখবে:** `step`-এর default value হলো `1`। তাই `range(start, stop)` লিখলেও সংখ্যাগুলো এক করে বাড়ে।

## 3. Printing Even Numbers

Even number হলো এমন integer, যা 2 দিয়ে নিঃশেষে বিভাজ্য।

`range()`-এর step ব্যবহার করে even number সরাসরি print করা যায়।

```python
for number in range(2, 11, 2):
    print(number)
```

**Output:**

```text
2
4
6
8
10
```

এখানে `if` condition ব্যবহার করতে হয়নি, কারণ step `2` করে বাড়ছে এবং শুরু হয়েছে `2` থেকে।

## 4. Printing Odd Numbers

Odd number-এর ক্ষেত্রে `1` থেকে শুরু করে step `2` ব্যবহার করা যায়।

```python
for number in range(1, 11, 2):
    print(number)
```

**Output:**

```text
1
3
5
7
9
```

এখানে প্রতিটি সংখ্যা odd, কারণ `1` থেকে প্রতিবার `2` যোগ করা হয়েছে।

## 5. Counting in Multiples

`range()` ব্যবহার করে কোনো সংখ্যার multiples print করা যায়।

### Multiples of 3

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

### Multiples of 5

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

এখানে start এবং step একই multiple দিয়ে শুরু করা হয়েছে। তাই প্রতিটি generated number সংশ্লিষ্ট সংখ্যার multiple।

## 6. Dry Run of `range(start, stop, step)`

নিচের code-টি দেখো:

```python
for number in range(3, 16, 4):
    print(number)
```

**Dry Run Table:**

| Iteration | `number` | পরবর্তী value |
|---|---:|---:|
| 1 | 3 | 7 |
| 2 | 7 | 11 |
| 3 | 11 | 15 |
| 4 | 15 | 19 |

পরবর্তী value `19`, যা stop value `16`-এর চেয়ে বড়। তাই আর কোনো iteration হয় না।

**Output:**

```text
3
7
11
15
```

এখানে প্রতিবার `4` যোগ হয়েছে। `16` অন্তর্ভুক্ত হয়নি।

## 7. Calculating the Number of Iterations

যখন `step` positive এবং `start < stop`, তখন iteration-এর সংখ্যা বের করার সূত্র:

\[
\text{Iterations}
=
\left\lceil \frac{\text{stop}-\text{start}}{\text{step}} \right\rceil
\]

এই সূত্রটি positive step-এর ক্ষেত্রে প্রযোজ্য।

**Example:**

```python
for number in range(2, 15, 3):
    print(number)
```

Generated values:

```text
2
5
8
11
14
```

Iteration count:

\[
\left\lceil \frac{15-2}{3} \right\rceil
=
\left\lceil 4.33\ldots \right\rceil
=5
\]

তাই loop পাঁচবার চলে।

## 8. Calculating the Sum Using Step

Step ব্যবহার করে নির্দিষ্ট interval-এর integer-গুলোর যোগফল বের করা যায়।

**Example: Sum of even numbers from 2 to 10**

```python
total = 0

for number in range(2, 11, 2):
    total += number

print("Total:", total)
```

**Output:**

```text
Total: 30
```

কারণ:

\[
2+4+6+8+10=30
\]

### Example: Sum of multiples of 5

```python
total = 0

for number in range(5, 31, 5):
    total += number

print(total)
```

**Output:**

```text
105
```

কারণ:

\[
5+10+15+20+25+30=105
\]

## 9. Using a Negative Step

`step` negative হলে sequence পেছনের দিকে এগোয়।

**Example:**

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

- `start = 10`
- `stop = 0`
- `step = -1`

প্রতিবার 1 করে কমেছে। `0` অন্তর্ভুক্ত হয়নি।

**Important:** Negative step ব্যবহার করলে সাধারণত `start`-এর মান `stop`-এর চেয়ে বড় হতে হয়, যাতে sequence পেছনের দিকে এগোতে পারে।

## 10. Counting Backward with Different Steps

### Counting backward by 2

```python
for number in range(10, 0, -2):
    print(number)
```

**Output:**

```text
10
8
6
4
2
```

### Counting backward by 3

```python
for number in range(15, 0, -3):
    print(number)
```

**Output:**

```text
15
12
9
6
3
```

Negative step ব্যবহার করে countdown, reverse interval এবং বিভিন্ন numerical problem সমাধান করা যায়।

## 11. Choosing the Correct Step

Step-এর sign এবং start-stop-এর সম্পর্ক বুঝতে হবে।

| Code | ফলাফল | কারণ |
|---|---|---|
| `range(1, 10, 2)` | `1, 3, 5, 7, 9` | Positive step, সামনে এগোয় |
| `range(10, 0, -2)` | `10, 8, 6, 4, 2` | Negative step, পেছনে এগোয় |
| `range(10, 1, 1)` | Empty | Positive step, কিন্তু start বড় |
| `range(1, 10, -1)` | Empty | Negative step, কিন্তু start ছোট |
| `range(5, 5, 1)` | Empty | Start ও stop সমান |

**সহজ নিয়ম:**

- সামনে গণনা করতে সাধারণত positive step ব্যবহার করো।
- পেছনে গণনা করতে negative step ব্যবহার করো।
- `step = 0` ব্যবহার করা যাবে না।

## 12. Using Step with Conditional Statements

Step ছাড়াও condition ব্যবহার করে item নির্বাচন করা যায়। তবে উপযুক্ত step ব্যবহার করলে code সহজ হয়।

### Method 1: Using `if`

```python
for number in range(1, 11):
    if number % 2 == 0:
        print(number)
```

### Method 2: Using `step`

```python
for number in range(2, 11, 2):
    print(number)
```

দুটি code-এর output একই:

```text
2
4
6
8
10
```

যখন pattern নির্দিষ্ট interval-এ হয়, তখন `step` ব্যবহার করা সুবিধাজনক। আরও জটিল condition থাকলে `if` প্রয়োজন হতে পারে।

## 13. Using Step with Lists

List-এর index-গুলো নির্দিষ্ট interval-এ access করতেও step ব্যবহার করা যায়।

```python
fruits = ["Apple", "Mango", "Banana", "Orange", "Grape", "Guava"]

for i in range(0, len(fruits), 2):
    print(fruits[i])
```

**Output:**

```text
Apple
Banana
Grape
```

এখানে index পাওয়া গেছে `0`, `2`, `4`।

অর্থাৎ, list-এর প্রতি দ্বিতীয় index-এর item print হয়েছে।

**সতর্কতা:** Step যদি `0` হয়, `range()` `ValueError` দেবে। আর list-এর size অনুযায়ী valid stop boundary নির্বাচন করা প্রয়োজন।

## 14. Common Mistakes

### Mistake 1: Using a zero step

ভুল:

```python
for number in range(1, 10, 0):
    print(number)
```

এতে `ValueError` হবে, কারণ step শূন্য হতে পারে না।

### Mistake 2: Using the wrong step direction

ভুল:

```python
for number in range(10, 0, 1):
    print(number)
```

এখানে কোনো output হবে না। Start `10`, stop `0`, কিন্তু step `1` সামনে এগোয়।

সঠিক:

```python
for number in range(10, 0, -1):
    print(number)
```

### Mistake 3: Assuming the stop value is included

```python
print(list(range(2, 10, 2)))
```

Output:

```text
[2, 4, 6, 8]
```

এখানে `10` অন্তর্ভুক্ত হয়নি। `10`-ও দরকার হলে stop value `11` করতে হবে।

### Mistake 4: Choosing a step that skips the desired value

```python
print(list(range(1, 10, 3)))
```

Output:

```text
[1, 4, 7]
```

এখানে `10` পাওয়া যায়নি। Step `3` করে বাড়ার কারণে পরবর্তী value `10` হলেও stop boundary সেটিকে বাদ দিয়েছে।

### Mistake 5: Using a float step

```python
range(1, 10, 0.5)
```

এতে `TypeError` হবে। `range()`-এর start, stop ও step integer হতে হবে।

## 15. Practice Exercises

### Exercise 1

`range()` ব্যবহার করে `2, 4, 6, 8, 10, 12` print করো।

### Exercise 2

`range()` ব্যবহার করে `5, 10, 15, 20, 25` print করো।

### Exercise 3

`range()` ব্যবহার করে `20` থেকে `2` পর্যন্ত 2 করে কমিয়ে print করো।

### Exercise 4

নিচের code-এর output কী হবে?

```python
for i in range(3, 16, 4):
    print(i)
```

### Exercise 5

`1` থেকে `50` পর্যন্ত 5-এর multiples-এর যোগফল বের করো।

### Exercise 6

নিচের code-এ কেন output আসবে না?

```python
for i in range(1, 10, -1):
    print(i)
```

### Exercise 7

নিচের list থেকে index `0`, `2`, `4`-এর item print করো।

```python
subjects = ["Python", "Java", "AI", "Database", "Networking"]
```

### Exercise 8

নিচের code-এর output এবং iteration count বের করো।

```python
for i in range(2, 20, 5):
    print(i)
```

## 16. Practice Answer Key

### Answer 1

```python
for number in range(2, 13, 2):
    print(number)
```

Output:

```text
2
4
6
8
10
12
```

### Answer 2

```python
for number in range(5, 26, 5):
    print(number)
```

Output:

```text
5
10
15
20
25
```

### Answer 3

```python
for number in range(20, 1, -2):
    print(number)
```

Output:

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

### Answer 4

```python
for i in range(3, 16, 4):
    print(i)
```

Output:

```text
3
7
11
15
```

### Answer 5

```python
total = 0

for number in range(5, 51, 5):
    total += number

print(total)
```

Output:

```text
275
```

কারণ:

\[
5+10+15+\cdots+50=275
\]

### Answer 6

Step `-1` হওয়ায় sequence পেছনের দিকে এগোতে চায়, কিন্তু start `1` এবং stop `10`। এই direction-এ কোনো value তৈরি হয় না, তাই loop চলে না।

### Answer 7

```python
subjects = ["Python", "Java", "AI", "Database", "Networking"]

for i in range(0, len(subjects), 2):
    print(subjects[i])
```

Output:

```text
Python
AI
Networking
```

### Answer 8

```python
for i in range(2, 20, 5):
    print(i)
```

Output:

```text
2
7
12
17
```

মোট iteration: `4` বার।

## 17. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `range(start, stop, step)`-এর তিনটি argument।
- Positive step দিয়ে সামনে গণনা করা।
- Negative step দিয়ে পেছনে গণনা করা।
- Even, odd এবং multiples print করা।
- Step ব্যবহার করে sum বের করা।
- List-এর নির্দিষ্ট interval-এর index access করা।
- Step direction ও stop boundary-এর common mistake এড়ানো।

### Quick Revision Table

| Code | Sequence |
|---|---|
| `range(2, 11, 2)` | `2, 4, 6, 8, 10` |
| `range(1, 11, 2)` | `1, 3, 5, 7, 9` |
| `range(5, 26, 5)` | `5, 10, 15, 20, 25` |
| `range(10, 0, -1)` | `10` থেকে `1` |
| `range(10, 0, -2)` | `10, 8, 6, 4, 2` |
| `range(1, 10, -1)` | Empty sequence |

## 18. Completion Checklist

- [ ] `range(start, stop, step)` বুঝি।
- [ ] Positive step ব্যবহার করতে পারি।
- [ ] Negative step ব্যবহার করতে পারি।
- [ ] Even ও odd number print করতে পারি।
- [ ] Multiples ও তাদের sum বের করতে পারি।
- [ ] List-এর নির্দিষ্ট index access করতে পারি।
- [ ] Wrong step direction ও zero-step error শনাক্ত করতে পারি।

**Next Topic:** `29_Counting_Forward_and_Backward.md`
