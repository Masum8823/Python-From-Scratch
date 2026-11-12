# 27. `range()` with Start and Stop

## 1. Introduction

Python-এ `range()` function-এ দুটি argument দিলে প্রথমটি `start` এবং দ্বিতীয়টি `stop` হিসেবে কাজ করে।

**Syntax:**

```python
range(start, stop)
```

এখানে:

- `start`: sequence-এর প্রথম integer।
- `stop`: যে boundary-তে পৌঁছানোর আগেই sequence শেষ হবে।
- Default `step` হলো `1`।
- `start` অন্তর্ভুক্ত হয়, কিন্তু `stop` অন্তর্ভুক্ত হয় না।

**Example:**

```python
for number in range(2, 7):
    print(number)
```

**Output:**

```text
2
3
4
5
6
```

এখানে `2` থেকে শুরু হয়েছে, কিন্তু `7` print হয়নি।

## 2. Understanding Start and Stop

নিচের code-টি দেখো:

```python
print(list(range(3, 8)))
```

**Output:**

```text
[3, 4, 5, 6, 7]
```

এখানে:

| Parameter | Value | অর্থ |
|---|---:|---|
| `start` | 3 | এখান থেকে শুরু |
| `stop` | 8 | এই value অন্তর্ভুক্ত নয় |
| `step` | 1 | প্রতিবার 1 করে বাড়ে |

তাই sequence হলো `3, 4, 5, 6, 7`।

**মনে রাখার নিয়ম:** `range(start, stop)`-এ `start` থেকে `stop - 1` পর্যন্ত integer পাওয়া যায়, যদি `start < stop` হয়।

## 3. Printing Numbers from 1 to 10

`1` থেকে `10` পর্যন্ত সংখ্যা print করতে:

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

এখানে `stop` হিসেবে `11` ব্যবহার করা হয়েছে, কারণ `stop` value অন্তর্ভুক্ত হয় না।

## 4. Starting from a Different Number

তুমি যেকোনো integer থেকে counting শুরু করতে পারো।

### Example 1: From 5 to 9

```python
for number in range(5, 10):
    print(number)
```

**Output:**

```text
5
6
7
8
9
```

### Example 2: From 10 to 15

```python
for number in range(10, 16):
    print(number)
```

**Output:**

```text
10
11
12
13
14
15
```

### Example 3: From 20 to 25

```python
for number in range(20, 26):
    print(number)
```

**Output:**

```text
20
21
22
23
24
25
```

প্রতিটি উদাহরণে start ও stop পরিবর্তন করা হয়েছে। Default step `1` থাকায় সংখ্যাগুলো এক করে বেড়েছে।

## 5. Dry Run of `range(start, stop)`

Code:

```python
for number in range(3, 7):
    print(number * 2)
```

**Dry Run Table:**

| Iteration | `number` | `number * 2` |
|---|---:|---:|
| 1 | 3 | 6 |
| 2 | 4 | 8 |
| 3 | 5 | 10 |
| 4 | 6 | 12 |

**Output:**

```text
6
8
10
12
```

`range(3, 7)` চারটি integer দিয়েছে: `3`, `4`, `5`, `6`।

## 6. Calculating the Number of Iterations

যখন `start < stop` এবং default step `1`, তখন iteration-এর সংখ্যা:

\[
\text{Iterations} = \text{stop} - \text{start}
\]

**Example:**

```python
for number in range(4, 12):
    print(number)
```

এখানে:

\[
12-4=8
\]

তাই loop মোট 8 বার চলে।

**আরেকটি উদাহরণ:**

```python
for number in range(10, 15):
    print(number)
```

Iteration count:

\[
15-10=5
\]

অর্থাৎ, loop মোট 5 বার চলে।

## 7. Calculating the Sum Using Start and Stop

`range(start, stop)` ব্যবহার করে নির্দিষ্ট সীমার integer-গুলোর যোগফল বের করা যায়।

**Example: Sum from 1 to 5**

```python
total = 0

for number in range(1, 6):
    total += number

print("Total:", total)
```

**Output:**

```text
Total: 15
```

কারণ:

\[
1+2+3+4+5=15
\]

**Example: Sum from 5 to 10**

```python
total = 0

for number in range(5, 11):
    total += number

print("Total:", total)
```

**Output:**

```text
Total: 45
```

কারণ:

\[
5+6+7+8+9+10=45
\]

## 8. Using `range()` with Conditional Statements

`range(start, stop)`-এর সঙ্গে `if` ব্যবহার করে নির্দিষ্ট শর্ত পূরণ করা integer নির্বাচন করা যায়।

### Example 1: Printing even numbers

```python
for number in range(1, 11):
    if number % 2 == 0:
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

### Example 2: Printing numbers greater than 5

```python
for number in range(1, 11):
    if number > 5:
        print(number)
```

**Output:**

```text
6
7
8
9
10
```

এখানে range সব integer দিয়েছে, কিন্তু `if` statement অনুযায়ী কিছু integer-ই print হয়েছে।

## 9. Using Start and Stop with a List

List-এর index access করতেও `range(start, stop)` ব্যবহার করা যায়।

```python
fruits = ["Apple", "Mango", "Banana", "Orange", "Grape"]

for i in range(1, 4):
    print(fruits[i])
```

**Output:**

```text
Mango
Banana
Orange
```

এখানে index `1`, `2` এবং `3` ব্যবহার করা হয়েছে। Index `4` অন্তর্ভুক্ত হয়নি।

মনে রাখবে, list-এর index `0` থেকে শুরু হয়। তাই index-এ `range()` ব্যবহার করার সময় valid index-এর সীমা খেয়াল রাখতে হবে।

## 10. What Happens When Start Equals Stop?

যদি `start` এবং `stop` সমান হয়, তাহলে sequence খালি হয়।

```python
for number in range(5, 5):
    print(number)

print("Finished")
```

**Output:**

```text
Finished
```

এখানে loop body একবারও execute হয়নি।

কারণ `range(5, 5)`-এ প্রথম integer `5` হওয়ার কথা হলেও `stop` value `5` অন্তর্ভুক্ত নয়।

## 11. What Happens When Start Is Greater Than Stop?

Default step `1` হলে `start` যদি `stop`-এর চেয়ে বড় হয়, তাহলে sequence খালি থাকে।

```python
for number in range(8, 3):
    print(number)

print("Finished")
```

**Output:**

```text
Finished
```

কারণ default step সামনে এগোয়, কিন্তু `8` থেকে শুরু করে `3`-এর আগ পর্যন্ত যাওয়ার মতো sequence তৈরি হয় না।

পেছনের দিকে counting করতে negative step প্রয়োজন। সেটি পরের topic-এ বিস্তারিত শিখব।

## 12. Common Mistakes

### Mistake 1: Forgetting the exclusive stop

ভুল:

```python
for number in range(1, 5):
    print(number)
```

এখানে `5` print হবে না।

`1` থেকে `5` পর্যন্ত print করতে:

```python
for number in range(1, 6):
    print(number)
```

### Mistake 2: Confusing start with iteration count

```python
for number in range(5, 10):
    print(number)
```

এখানে `5` থেকে শুরু হয়েছে বলে loop 5 বার চলে না। এটি চলে 5 বার, কারণ `10 - 5 = 5`।

### Mistake 3: Using an invalid list index

```python
fruits = ["Apple", "Mango", "Banana"]

for i in range(1, 5):
    print(fruits[i])
```

এখানে `i`-এর value হবে `1`, `2`, `3`, `4`। কিন্তু list-এর valid index হলো `0`, `1`, `2`। তাই `fruits[3]` access করার সময় `IndexError` হবে।

সঠিক:

```python
for i in range(1, 3):
    print(fruits[i])
```

### Mistake 4: Assuming the stop value is always the last item

`range(3, 8)`-এর শেষ item হলো `7`, `8` নয়।

সঠিক sequence:

```text
3, 4, 5, 6, 7
```

## 13. Practice Exercises

নিজে চেষ্টা করো, তারপর answer key দিয়ে মিলিয়ে নাও।

### Exercise 1

`range()` ব্যবহার করে `5` থেকে `15` পর্যন্ত সংখ্যা print করো।

### Exercise 2

`range()` ব্যবহার করে `20` থেকে `30` পর্যন্ত সংখ্যা print করো।

### Exercise 3

`range()` ব্যবহার করে `10` থেকে `20` পর্যন্ত integer-এর যোগফল বের করো।

### Exercise 4

নিচের code-এর output কী হবে?

```python
for i in range(4, 8):
    print(i * 3)
```

### Exercise 5

নিচের range-এ মোট কতবার loop চলবে?

```python
for i in range(7, 17):
    print(i)
```

### Exercise 6

`range()` ব্যবহার করে `1` থেকে `20` পর্যন্ত even number print করো।

### Exercise 7

নিচের code-এ কেন কোনো সংখ্যা print হবে না?

```python
for i in range(6, 6):
    print(i)
```

### Exercise 8

নিচের list থেকে index `2`, `3` এবং `4`-এর item print করো।

```python
subjects = ["Python", "Java", "AI", "Database", "Networking"]
```

## 14. Practice Answer Key

### Answer 1

```python
for number in range(5, 16):
    print(number)
```

Output: `5` থেকে `15` পর্যন্ত।

### Answer 2

```python
for number in range(20, 31):
    print(number)
```

Output: `20` থেকে `30` পর্যন্ত।

### Answer 3

```python
total = 0

for number in range(10, 21):
    total += number

print(total)
```

**Output:**

```text
165
```

### Answer 4

```python
for i in range(4, 8):
    print(i * 3)
```

Output:

```text
12
15
18
21
```

### Answer 5

মোট iteration:

\[
17-7=10
\]

অর্থাৎ, 10 বার।

### Answer 6

```python
for number in range(1, 21):
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
12
14
16
18
20
```

### Answer 7

`start` এবং `stop` সমান। তাই `range(6, 6)` খালি এবং loop body execute হয় না।

### Answer 8

```python
subjects = ["Python", "Java", "AI", "Database", "Networking"]

for i in range(2, 5):
    print(subjects[i])
```

Output:

```text
AI
Database
Networking
```

## 15. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `range(start, stop)`-এর ব্যবহার।
- `start` অন্তর্ভুক্ত হয়, `stop` অন্তর্ভুক্ত হয় না।
- Default step হলো `1`।
- Start ও stop দিয়ে iteration count বের করা।
- Sum ও conditional filtering-এর মতো কাজে range ব্যবহার।
- List-এর নির্দিষ্ট index access করা।
- Start ও stop সমান বা start বড় হলে কী হয়।

### Quick Revision Table

| Code | Sequence | Iterations |
|---|---|---:|
| `range(1, 5)` | `1, 2, 3, 4` | 4 |
| `range(3, 8)` | `3, 4, 5, 6, 7` | 5 |
| `range(5, 10)` | `5, 6, 7, 8, 9` | 5 |
| `range(5, 5)` | Empty | 0 |
| `range(8, 3)` | Empty, default step | 0 |

## 16. Completion Checklist

- [ ] `range(start, stop)`-এর syntax বুঝি।
- [ ] Start ও stop-এর পার্থক্য বুঝি।
- [ ] Stop value বাদ যাওয়ার নিয়ম মনে রাখতে পারি।
- [ ] Iteration count বের করতে পারি।
- [ ] নির্দিষ্ট range-এর sum বের করতে পারি।
- [ ] `range()` দিয়ে list-এর নির্দিষ্ট index access করতে পারি।
- [ ] Empty range-এর আচরণ বুঝি।

**Next Topic:** `28_range_with_Step.md`
