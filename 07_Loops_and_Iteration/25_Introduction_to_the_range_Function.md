# 25. Introduction to the `range()` Function

## 1. Introduction

Python-এ `range()` একটি built-in function, যা নির্দিষ্ট নিয়ম অনুযায়ী integer-এর একটি sequence তৈরি করতে সাহায্য করে।

এটি সবচেয়ে বেশি ব্যবহার করা হয় `for` loop-এর সঙ্গে, যখন কোনো কাজ নির্দিষ্ট সংখ্যক বার চালাতে হয়।

**Example:**

```python
for number in range(5):
    print(number)
```

**Output:**

```text
0
1
2
3
4
```

এখানে `range(5)` দিয়ে `0` থেকে `4` পর্যন্ত integer পাওয়া গেছে।

**Important:** `range(5)`-এ `5` অন্তর্ভুক্ত হয় না। অর্থাৎ, `range()`-এর stop value সবসময় বাদ থাকে।

## 2. Why Do We Need `range()`?

ধরো, তোমাকে 1 থেকে 5 পর্যন্ত সংখ্যা print করতে হবে।

`range()` ছাড়া:

```python
print(1)
print(2)
print(3)
print(4)
print(5)
```

`for` loop ও `range()` ব্যবহার করে:

```python
for number in range(1, 6):
    print(number)
```

**Output:**

```text
1
2
3
4
5
```

দ্বিতীয় পদ্ধতিতে কম code লিখে একই কাজ করা যায়। সংখ্যার পরিমাণ অনেক বেশি হলেও একই নিয়মে কাজ করা সম্ভব।

## 3. Basic Syntax of `range()`

`range()` সাধারণত তিনভাবে ব্যবহার করা হয়:

```python
range(stop)
range(start, stop)
range(start, stop, step)
```

| Form | কাজ |
|---|---|
| `range(stop)` | `0` থেকে শুরু করে `stop`-এর আগ পর্যন্ত |
| `range(start, stop)` | `start` থেকে শুরু করে `stop`-এর আগ পর্যন্ত |
| `range(start, stop, step)` | নির্দিষ্ট `step` অনুযায়ী সামনে বা পেছনে এগোয় |

এখানে:

- `start`: sequence-এর শুরুর integer।
- `stop`: যে value-তে পৌঁছানোর আগেই sequence শেষ হবে।
- `step`: প্রতিবার কত করে বাড়বে বা কমবে।

`start` default হিসেবে `0` এবং `step` default হিসেবে `1`।

## 4. Understanding the Stop Value

`range()`-এর সবচেয়ে গুরুত্বপূর্ণ নিয়ম হলো **stop value অন্তর্ভুক্ত হয় না**।

```python
for number in range(1, 5):
    print(number)
```

**Output:**

```text
1
2
3
4
```

এখানে:

- Start = `1`
- Stop = `5`
- Step = `1`

তাই `1`, `2`, `3`, `4` পাওয়া গেছে; `5` পাওয়া যায়নি।

### মনে রাখার কৌশল

যদি `1` থেকে `10` পর্যন্ত print করতে চাও, তাহলে লিখবে:

```python
range(1, 11)
```

শেষের `11` শুধু stop boundary হিসেবে ব্যবহৃত হয়েছে; এটি sequence-এর অংশ নয়।

## 5. Using `range()` with a `for` Loop

`range()` একটি iterable range object দেয়। `for` loop সেটি থেকে একে একে integer নেয়।

```python
for i in range(3):
    print("Hello Python")
```

**Output:**

```text
Hello Python
Hello Python
Hello Python
```

এখানে `range(3)` তিনটি integer দেয়: `0`, `1`, `2`। তাই loop তিনবার চলে।

মনে রাখবে, এখানে `i`-এর value print করা হয়নি। প্রতিবার একই message print করা হয়েছে।

## 6. Using `range()` for Counting

### Counting from 0 to 4

```python
for i in range(5):
    print(i)
```

Output:

```text
0
1
2
3
4
```

### Counting from 1 to 5

```python
for i in range(1, 6):
    print(i)
```

Output:

```text
1
2
3
4
5
```

### Counting from 1 to 10

```python
for i in range(1, 11):
    print(i)
```

Output:

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

এই তিনটি উদাহরণের পার্থক্য হলো `start` এবং `stop` value।

## 7. Understanding the Range Object

`range()` সরাসরি list তৈরি করে না। এটি একটি `range` object দেয়, যা প্রয়োজন অনুযায়ী integer সরবরাহ করে।

```python
numbers = range(5)

print(numbers)
print(type(numbers))
```

**Output:**

```text
range(0, 5)
<class 'range'>
```

সব value একসঙ্গে list হিসেবে দেখতে চাইলে `list()` ব্যবহার করতে পারো:

```python
numbers = range(5)

print(list(numbers))
```

**Output:**

```text
[0, 1, 2, 3, 4]
```

এখানে `list()` range object-এর integer-গুলোকে list-এ রূপান্তর করেছে।

**মনে রাখবে:** বড় range-এর সব value একসঙ্গে list-এ রূপান্তর করলে বেশি memory লাগতে পারে। সাধারণ loop-এর জন্য `range()` সরাসরি ব্যবহার করাই যথেষ্ট।

## 8. Dry Run of `range()`

Code:

```python
for number in range(1, 5):
    print(number * 10)
```

Dry run table:

| Iteration | `number` | `number * 10` |
|---|---:|---:|
| 1 | 1 | 10 |
| 2 | 2 | 20 |
| 3 | 3 | 30 |
| 4 | 4 | 40 |

Output:

```text
10
20
30
40
```

Loop-এর প্রতিটি iteration-এ `range()` থেকে একটি integer নেওয়া হয়েছে, তারপর সেটিকে `10` দিয়ে গুণ করা হয়েছে।

## 9. Using `range()` to Repeat a Task

`range()` ব্যবহার করে একই কাজ নির্দিষ্ট সংখ্যক বার করা যায়।

### Example: Printing a message five times

```python
for i in range(5):
    print("I am learning Python.")
```

Output:

```text
I am learning Python.
I am learning Python.
I am learning Python.
I am learning Python.
I am learning Python.
```

### Example: Printing multiplication table values

```python
for i in range(1, 6):
    print(5 * i)
```

Output:

```text
5
10
15
20
25
```

এখানে `range(1, 6)` পাঁচটি integer দিয়েছে। প্রতিটি integer-কে `5` দিয়ে গুণ করা হয়েছে।

## 10. Counting the Number of Iterations

Positive step-এর ক্ষেত্রে `range(start, stop, step)`-এ iteration-এর সংখ্যা বের করার একটি সূত্র হলো:

\[
\text{Iterations} =
\begin{cases}
0, & \text{যদি start} \geq \text{stop} \\
\left\lceil \frac{\text{stop}-\text{start}}{\text{step}} \right\rceil, & \text{অন্যথায়}
\end{cases}
\]

এখানে `step` positive হতে হবে। Negative step-এর ক্ষেত্রে নিয়ম আলাদা।

**Example:**

```python
for i in range(2, 12, 3):
    print(i)
```

Output:

```text
2
5
8
11
```

এখানে:

- Start = `2`
- Stop = `12`
- Step = `3`

প্রতিবার `3` যোগ হয়েছে। মোট iteration চারটি।

## 11. Using `range()` with Conditions

`range()`-এর সঙ্গে `if` statement ব্যবহার করে নির্দিষ্ট শর্ত পূরণ করা integer নিয়ে কাজ করা যায়।

### Example: Printing even numbers

```python
for number in range(1, 11):
    if number % 2 == 0:
        print(number)
```

Output:

```text
2
4
6
8
10
```

এখানে `range()` 1 থেকে 10 পর্যন্ত integer দিয়েছে। `if` statement শুধু even number-গুলো print করেছে।

তবে শুধু even number দরকার হলে step ব্যবহার করে আরও সহজে লেখা যায়:

```python
for number in range(2, 11, 2):
    print(number)
```

Output:

```text
2
4
6
8
10
```

## 12. Using `range()` with `len()`

List-এর item সংখ্যা অনুযায়ী loop চালাতে `range()`-এর সঙ্গে `len()` ব্যবহার করা যায়।

```python
fruits = ["Apple", "Mango", "Banana"]

for i in range(len(fruits)):
    print(i, fruits[i])
```

Output:

```text
0 Apple
1 Mango
2 Banana
```

এখানে:

- `len(fruits)` হলো `3`।
- `range(3)` থেকে `0`, `1`, `2` পাওয়া যায়।
- `fruits[i]` দিয়ে সংশ্লিষ্ট item পাওয়া যায়।

তবে index প্রয়োজন না হলে সাধারণ iteration সহজ:

```python
for fruit in fruits:
    print(fruit)
```

Index এবং item দুটোই প্রয়োজন হলে `enumerate(fruits)` সাধারণত আরও পরিষ্কার পদ্ধতি।

## 13. Common Mistakes

### Mistake 1: Expecting the stop value to be included

ভুল ধারণা:

```python
for i in range(1, 5):
    print(i)
```

এখানে `5` print হবে না।

`1` থেকে `5` পর্যন্ত print করতে:

```python
for i in range(1, 6):
    print(i)
```

### Mistake 2: Using zero as the step

```python
for i in range(1, 10, 0):
    print(i)
```

এতে `ValueError` হবে, কারণ `range()`-এর step শূন্য হতে পারে না।

### Mistake 3: Using a step in the wrong direction

```python
for i in range(5, 1):
    print(i)
```

এখানে output আসবে না। কারণ default step `1`, কিন্তু start `5` এবং stop `1`।

পেছনের দিকে যেতে negative step প্রয়োজন:

```python
for i in range(5, 1, -1):
    print(i)
```

Output:

```text
5
4
3
2
```

### Mistake 4: Confusing `range(5)` with `range(1, 5)`

- `range(5)` → `0, 1, 2, 3, 4`
- `range(1, 5)` → `1, 2, 3, 4`

দুটির output এক নয়, কারণ প্রথমটির start default হিসেবে `0`।

### Mistake 5: Using non-integer arguments

`range()`-এর `start`, `stop` এবং `step` argument integer হতে হবে।

```python
range(1, 5.5)
```

এতে `TypeError` হবে।

## 14. Practice Exercises

নিজে চেষ্টা করো। তারপর Answer Key দিয়ে মিলিয়ে নাও।

### Exercise 1

`range()` ব্যবহার করে `0` থেকে `9` পর্যন্ত সংখ্যা print করো।

### Exercise 2

`range()` ব্যবহার করে `1` থেকে `20` পর্যন্ত সংখ্যা print করো।

### Exercise 3

`range()` ব্যবহার করে `2, 4, 6, 8, 10` print করো।

### Exercise 4

`range()` ব্যবহার করে `10, 9, 8, 7, 6` print করো।

### Exercise 5

নিচের code-এর output কী হবে?

```python
for i in range(3):
    print(i + 5)
```

### Exercise 6

নিচের code-এ কতবার loop চলবে?

```python
for i in range(4, 15, 3):
    print(i)
```

### Exercise 7

`range()` ব্যবহার করে `7`-এর multiplication table-এর প্রথম 10টি ফল print করো।

### Exercise 8

নিচের code-এ কেন output আসবে না?

```python
for i in range(5, 1):
    print(i)
```

## 15. Practice Answer Key

### Answer 1

```python
for i in range(10):
    print(i)
```

Output: `0` থেকে `9` পর্যন্ত।

### Answer 2

```python
for i in range(1, 21):
    print(i)
```

Output: `1` থেকে `20` পর্যন্ত।

### Answer 3

```python
for i in range(2, 11, 2):
    print(i)
```

Output:

```text
2
4
6
8
10
```

### Answer 4

```python
for i in range(10, 5, -1):
    print(i)
```

Output:

```text
10
9
8
7
6
```

### Answer 5

```python
for i in range(3):
    print(i + 5)
```

Output:

```text
5
6
7
```

### Answer 6

```python
for i in range(4, 15, 3):
    print(i)
```

Output:

```text
4
7
10
13
```

মোট iteration: `4` বার।

### Answer 7

```python
for i in range(1, 11):
    print(7 * i)
```

Output:

```text
7
14
21
28
35
42
49
56
63
70
```

### Answer 8

Default step `1`, তাই `5` থেকে শুরু করে `1`-এর দিকে যাওয়া সম্ভব নয়। এজন্য range খালি থাকে এবং loop চলে না।

## 16. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `range()` কী এবং কেন ব্যবহার করা হয়।
- `range(stop)`, `range(start, stop)` এবং `range(start, stop, step)`।
- Stop value অন্তর্ভুক্ত না হওয়ার নিয়ম।
- `range()` ব্যবহার করে counting ও repetition।
- `range()`-এর integer-গুলো list হিসেবে দেখা।
- `range()`-এর সঙ্গে condition ও `len()` ব্যবহার।
- ভুল step এবং ভুল counting-এর সমস্যা শনাক্ত করা।

### Quick Revision Table

| Code | যে integer-গুলো পাওয়া যায় |
|---|---|
| `range(5)` | `0, 1, 2, 3, 4` |
| `range(1, 5)` | `1, 2, 3, 4` |
| `range(2, 11, 2)` | `2, 4, 6, 8, 10` |
| `range(5, 1, -1)` | `5, 4, 3, 2` |
| `range(5, 1)` | কোনো integer নয় |

## 17. Completion Checklist

- [ ] `range()`-এর কাজ বুঝি।
- [ ] `start`, `stop` এবং `step`-এর ব্যবহার জানি।
- [ ] Stop value বাদ যাওয়ার নিয়ম বুঝি।
- [ ] `range()` দিয়ে নির্দিষ্ট সংখ্যক বার loop চালাতে পারি।
- [ ] Positive ও negative step ব্যবহার করতে পারি।
- [ ] `range()` এবং `len()` একসঙ্গে ব্যবহার করতে পারি।
- [ ] Common `range()` errors শনাক্ত করতে পারি।

**Next Topic:** `26_range_with_One_Argument.md`
