# 26. `range()` with One Argument

## 1. Introduction

Python-এ `range()` function-এ শুধু একটি argument দিলে সেটি `stop` value হিসেবে কাজ করে।

**Syntax:**

```python
range(stop)
```

এখানে:

- `stop` হলো একটি integer, যা sequence-এর শেষ boundary নির্ধারণ করে।
- Sequence শুরু হয় `0` থেকে।
- `stop` value অন্তর্ভুক্ত হয় না।
- Default step হলো `1`।

**Example:**

```python
for i in range(5):
    print(i)
```

**Output:**

```text
0
1
2
3
4
```

এখানে `range(5)` পাঁচটি integer দিয়েছে: `0`, `1`, `2`, `3`, `4`।

## 2. Why Does `range(n)` Start from Zero?

`range()`-এর এক argument-এর form-এ start value default হিসেবে `0` থাকে।

তাই:

```python
print(list(range(5)))
```

**Output:**

```text
[0, 1, 2, 3, 4]
```

আরেকটি উদাহরণ:

```python
print(list(range(3)))
```

**Output:**

```text
[0, 1, 2]
```

মনে রাখবে, `range(n)`-এ `n` হলো stop value, sequence-এর শেষ item নয়।

## 3. Understanding the Number of Iterations

যদি `n` একটি positive integer হয়, তাহলে `range(n)` মোট `n`টি integer দেয়।

| Code | Integer sequence | Iterations |
|---|---|---:|
| `range(1)` | `0` | 1 |
| `range(2)` | `0, 1` | 2 |
| `range(3)` | `0, 1, 2` | 3 |
| `range(5)` | `0, 1, 2, 3, 4` | 5 |
| `range(10)` | `0` থেকে `9` | 10 |

**সহজ নিয়ম:** `range(n)`-এর ক্ষেত্রে `n` positive হলে loop মোট `n` বার চলে।

`range(0)` বা `range(-3)`-এর মতো ক্ষেত্রে sequence খালি হয়, তাই loop একবারও চলে না।

## 4. Printing a Message Multiple Times

একই message নির্দিষ্ট সংখ্যক বার print করতে `range()` ব্যবহার করা যায়।

```python
for i in range(4):
    print("I am learning Python.")
```

**Output:**

```text
I am learning Python.
I am learning Python.
I am learning Python.
I am learning Python.
```

এখানে `i`-এর value print করা হয়নি। `range(4)` চারটি integer দেওয়ায় message-টি চারবার print হয়েছে।

## 5. Dry Run of `range(3)`

Code:

```python
for i in range(3):
    print(i)
```

**Dry Run Table:**

| Iteration | `i` | Output |
|---|---:|---:|
| 1 | 0 | 0 |
| 2 | 1 | 1 |
| 3 | 2 | 2 |

এরপর `range()` থেকে আর কোনো integer পাওয়া যায় না, তাই loop শেষ হয়।

**Final Output:**

```text
0
1
2
```

## 6. Performing Calculations with `range(n)`

`range(n)`-এর integer ব্যবহার করে calculation করা যায়।

### Example 1: Printing squares

```python
for i in range(5):
    print(i ** 2)
```

**Output:**

```text
0
1
4
9
16
```

এখানে `i`-এর value `0` থেকে `4` পর্যন্ত এবং প্রতিটি value-এর square print হয়েছে।

### Example 2: Adding a fixed number

```python
for i in range(4):
    print(i + 10)
```

**Output:**

```text
10
11
12
13
```

### Example 3: Multiplying each value by 2

```python
for i in range(5):
    print(i * 2)
```

**Output:**

```text
0
2
4
6
8
```

## 7. Using `range(n)` to Calculate a Sum

`range(n)` ব্যবহার করে `0` থেকে `n-1` পর্যন্ত integer-এর যোগফল বের করা যায়।

**Example:**

```python
total = 0

for i in range(5):
    total += i

print("Total:", total)
```

**Output:**

```text
Total: 10
```

কারণ:

\[
0+1+2+3+4=10
\]

এখানে `total` হলো accumulator, যা প্রতিটি iteration-এ যোগফল জমা রাখে।

## 8. Counting Even Numbers Using `range(n)`

`range(n)` দিয়ে শুরু থেকে `n-1` পর্যন্ত সংখ্যা পরীক্ষা করা যায়।

```python
count = 0

for number in range(10):
    if number % 2 == 0:
        count += 1

print("Even numbers:", count)
```

**Output:**

```text
Even numbers: 5
```

এখানে `range(10)` থেকে `0`–`9` পাওয়া যায়। Even number হলো `0`, `2`, `4`, `6`, `8`।

মনে রাখবে, Python-এ `0 % 2 == 0`, তাই `0`-ও even number।

## 9. Using `range(n)` with Conditional Statements

Loop-এর ভেতরে `if` ব্যবহার করে নির্দিষ্ট condition পূরণ করা item print করা যায়।

```python
for number in range(8):
    if number > 3:
        print(number)
```

**Output:**

```text
4
5
6
7
```

এখানে `range(8)` থেকে `0` থেকে `7` পর্যন্ত integer পাওয়া গেছে। `if` statement শুধু `3`-এর চেয়ে বড় সংখ্যাগুলো print করেছে।

## 10. Using `range(0)` and Negative Values

`range()`-এর stop value শূন্য বা negative হলে, default positive step-এর কারণে sequence খালি থাকে।

### Example 1: `range(0)`

```python
for i in range(0):
    print(i)

print("Loop finished.")
```

**Output:**

```text
Loop finished.
```

Loop-এর body একবারও execute হয়নি।

### Example 2: `range(-3)`

```python
for i in range(-3):
    print(i)

print("Done.")
```

**Output:**

```text
Done.
```

এখানেও কোনো integer পাওয়া যায়নি।

**কেন?**

Default start `0`, default step `1`; তাই sequence-এর জন্য প্রয়োজনীয় stop condition পূরণ হয় না।

## 11. Using `range(n)` with `len()`

কোনো list-এর item সংখ্যা অনুযায়ী loop চালাতে `range(len(list_name))` ব্যবহার করা যায়।

```python
fruits = ["Apple", "Mango", "Banana"]

for i in range(len(fruits)):
    print(i, fruits[i])
```

**Output:**

```text
0 Apple
1 Mango
2 Banana
```

এখানে:

- `len(fruits)` হলো `3`।
- `range(3)` থেকে `0`, `1`, `2` পাওয়া যায়।
- `fruits[i]` দিয়ে প্রতিটি item access করা হয়।

তবে শুধু item প্রয়োজন হলে সহজ পদ্ধতি:

```python
for fruit in fruits:
    print(fruit)
```

Index ও item একসঙ্গে দরকার হলে `enumerate(fruits)` ব্যবহার করাও ভালো পদ্ধতি।

## 12. Common Mistakes

### Mistake 1: Expecting `range(5)` to print 1 to 5

```python
for i in range(5):
    print(i)
```

Output `0` থেকে `4` পর্যন্ত হবে, `1` থেকে `5` নয়।

`1` থেকে `5` পর্যন্ত দরকার হলে:

```python
for i in range(1, 6):
    print(i)
```

### Mistake 2: Thinking the argument is the last item

`range(4)`-এ `4` sequence-এর অংশ নয়।

```python
print(list(range(4)))
```

Output:

```text
[0, 1, 2, 3]
```

### Mistake 3: Expecting the loop body to execute for an empty range

```python
for i in range(0):
    print("Hello")
```

কোনো output হবে না, কারণ `range(0)` খালি।

### Mistake 4: Using a non-integer argument

```python
range(5.0)
```

এতে `TypeError` হবে। `range()`-এর argument integer হতে হবে।

## 13. Practice Exercises

### Exercise 1

`range(6)` ব্যবহার করে সব integer print করো।

### Exercise 2

`range(5)` ব্যবহার করে প্রতিটি integer-এর cube print করো।

### Exercise 3

`range(10)` ব্যবহার করে `0` থেকে `9` পর্যন্ত সংখ্যার যোগফল বের করো।

### Exercise 4

`range(10)` ব্যবহার করে `5` বা তার বেশি সংখ্যাগুলো print করো।

### Exercise 5

নিচের code-এর output কী হবে?

```python
for i in range(4):
    print(i + 2)
```

### Exercise 6

নিচের loop কতবার execute হবে?

```python
for i in range(0):
    print("Hello")
```

### Exercise 7

নিচের code-এর output কী হবে?

```python
count = 0

for i in range(6):
    if i % 2 == 0:
        count += 1

print(count)
```

### Exercise 8

একটি list-এর প্রতিটি item-এর index এবং value print করো:

```python
subjects = ["Python", "AI", "Database"]
```

## 14. Practice Answer Key

### Answer 1

```python
for i in range(6):
    print(i)
```

Output: `0, 1, 2, 3, 4, 5` — প্রতিটি নতুন লাইনে।

### Answer 2

```python
for i in range(5):
    print(i ** 3)
```

Output:

```text
0
1
8
27
64
```

### Answer 3

```python
total = 0

for i in range(10):
    total += i

print(total)
```

Output:

```text
45
```

কারণ \(0+1+2+\cdots+9=45\)।

### Answer 4

```python
for i in range(10):
    if i >= 5:
        print(i)
```

Output:

```text
5
6
7
8
9
```

### Answer 5

```python
for i in range(4):
    print(i + 2)
```

Output:

```text
2
3
4
5
```

### Answer 6

Loop মোট `0` বার execute হবে।

### Answer 7

```python
count = 0

for i in range(6):
    if i % 2 == 0:
        count += 1

print(count)
```

Output:

```text
3
```

কারণ even number হলো `0`, `2`, `4`।

### Answer 8

```python
subjects = ["Python", "AI", "Database"]

for index, subject in enumerate(subjects):
    print(index, subject)
```

Output:

```text
0 Python
1 AI
2 Database
```

## 15. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `range(n)`-এ `n` হলো stop value।
- Sequence default হিসেবে `0` থেকে শুরু হয়।
- Stop value অন্তর্ভুক্ত হয় না।
- Positive integer `n` হলে `range(n)`-এ মোট `n`টি integer থাকে।
- `range(0)` এবং negative stop value-তে sequence খালি থাকে।
- `range(n)` দিয়ে calculation, counting ও repetition করা যায়।
- `range(len(items))` দিয়ে index ব্যবহার করা যায়।

### Quick Revision Table

| Code | ফলাফল |
|---|---|
| `range(1)` | `0` |
| `range(3)` | `0, 1, 2` |
| `range(5)` | `0, 1, 2, 3, 4` |
| `range(0)` | খালি sequence |
| `range(-2)` | খালি sequence |

## 16. Completion Checklist

- [ ] `range(stop)`-এর syntax বুঝি।
- [ ] কেন sequence `0` থেকে শুরু হয়, বুঝি।
- [ ] Stop value কেন বাদ যায়, বুঝি।
- [ ] `range(n)`-এর iteration count বের করতে পারি।
- [ ] `range(n)` দিয়ে sum ও counting করতে পারি।
- [ ] Empty range-এর আচরণ বুঝি।
- [ ] `range()` ও `len()` একসঙ্গে ব্যবহার করতে পারি।

**Next Topic:** `27_range_with_Start_and_Stop.md`
