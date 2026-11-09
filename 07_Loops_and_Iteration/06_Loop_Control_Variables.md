# 06. Loop Control Variables

## 1. Introduction

Loop-এর ভেতরে অনেক সময় এমন variable ব্যবহার করা হয়, যার value প্রতিটি iteration-এ পরিবর্তিত হয়। এই variable-গুলো loop-এর execution নিয়ন্ত্রণ করতে বা calculation-এর result ধরে রাখতে সাহায্য করে।

উদাহরণস্বরূপ, একটি `while` loop পাঁচবার চালাতে হলে আমরা একটি variable ব্যবহার করতে পারি, যার value প্রতিবার বাড়বে।

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

এখানে `count` variable-এর value পরিবর্তিত হওয়ার কারণে loop একসময় শেষ হয়।

এই ধরনের variable কীভাবে কাজ করে, তা বোঝা loop শেখার জন্য খুবই গুরুত্বপূর্ণ।

## 2. What Is a Loop Control Variable?

**Definition:** A loop control variable is a variable used to control or track the execution of a loop.

সহজ ভাষায়, যে variable-এর সাহায্যে loop-এর repetition নিয়ন্ত্রণ করা হয় অথবা iteration-এর অগ্রগতি track করা হয়, তাকে loop control variable বলা যায়।

উদাহরণ:

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

এখানে `count` variable:

- Loop-এর শুরুতে `1` value নেয়।
- প্রতিবার loop চলার পর এক করে বাড়ে।
- `count`-এর value `4` হলে condition `False` হয়।
- ফলে loop শেষ হয়।

### Execution Table

| Iteration | Loop শুরুতে `count` | Condition | Output | Update-এর পর `count` |
|---:|---:|---|---:|---:|
| 1 | 1 | `True` | 1 | 2 |
| 2 | 2 | `True` | 2 | 3 |
| 3 | 3 | `True` | 3 | 4 |
| শেষ পরীক্ষা | 4 | `False` | নেই | 4 |

**Note:** `for` loop-এও loop variable থাকে, যা iterable থেকে প্রতিটি iteration-এর value পায়। তবে `while` loop-এর মতো সেটিকে সবসময় নিজে update করতে হয় না।

## 3. Why Are Loop Control Variables Needed?

Loop control variable কয়েকটি গুরুত্বপূর্ণ কাজে ব্যবহার করা হয়।

### 3.1 Controlling the Number of Iterations

```python
count = 0

while count < 4:
    print("Python")
    count += 1
```

Output:

```text
Python
Python
Python
Python
```

এখানে `count`-এর সাহায্যে চারটি iteration নিয়ন্ত্রণ করা হয়েছে।

### 3.2 Tracking the Current Value

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

এখানে `number` প্রতিটি iteration-এ বর্তমান value ধরে রাখে।

### 3.3 Counting Items

```python
numbers = [10, 20, 30, 40]
count = 0

for number in numbers:
    count += 1

print("Number of items:", count)
```

Output:

```text
Number of items: 4
```

এখানে `count` প্রতিবার এক করে বাড়ে এবং মোট item-এর সংখ্যা ধরে রাখে।

### 3.4 Storing a Running Result

```python
total = 0

for number in range(1, 5):
    total += number

print(total)
```

Output:

```text
10
```

এখানে `total` প্রতিটি iteration-এর যোগফল জমা রাখে।

## 4. Counter Variables

**Definition:** A counter variable keeps track of how many times an event occurs or how many items have been processed.

Counter হলো এমন variable, যা কোনো কাজের সংখ্যা গণনা করে।

### Example 1: Counting Iterations

```python
count = 0

for i in range(5):
    count += 1

print(count)
```

Output:

```text
5
```

এখানে `count` প্রতিটি iteration-এ এক করে বাড়ছে।

### Example 2: Counting Even Numbers

```python
numbers = [2, 5, 8, 11, 14]
even_count = 0

for number in numbers:
    if number % 2 == 0:
        even_count += 1

print("Even numbers:", even_count)
```

Output:

```text
Even numbers: 3
```

এখানে শুধু even number পাওয়া গেলে `even_count` বাড়ছে।

### Dry Run

| `number` | Even? | `even_count` |
|---:|---|---:|
| 2 | Yes | 1 |
| 5 | No | 1 |
| 8 | Yes | 2 |
| 11 | No | 2 |
| 14 | Yes | 3 |

Counter-এর value সাধারণত কোনো event ঘটলে বা নির্দিষ্ট item পাওয়া গেলে বাড়ানো হয়।

## 5. Accumulator Variables

**Definition:** An accumulator variable stores a running result by combining values during repeated execution.

সহজ ভাষায়, যে variable প্রতিটি iteration-এর value জমা করে একটি চলমান result তৈরি করে, তাকে accumulator বলা হয়।

### Example: Calculating a Sum

```python
total = 0

for number in range(1, 6):
    total += number

print("Total:", total)
```

Output:

```text
Total: 15
```

এখানে `total` প্রতিবার নতুন number-এর সঙ্গে আগের total যোগ করে।

### Dry Run

| Iteration | `number` | আগের `total` | নতুন `total` |
|---:|---:|---:|---:|
| শুরুতে | — | — | 0 |
| 1 | 1 | 0 | 1 |
| 2 | 2 | 1 | 3 |
| 3 | 3 | 3 | 6 |
| 4 | 4 | 6 | 10 |
| 5 | 5 | 10 | 15 |

এখানে:

```python
total += number
```

এর অর্থ:

```python
total = total + number
```

### Example: Calculating a Product

```python
product = 1

for number in range(1, 5):
    product *= number

print(product)
```

Output:

```text
24
```

কারণ:

\[
1 \times 2 \times 3 \times 4 = 24
\]

এখানে `product` একটি accumulator, যা গুণফল ধরে রাখে। গুণফল শুরু করার জন্য `1` ব্যবহার করা হয়েছে, কারণ `1` দিয়ে গুণ করলে value অপরিবর্তিত থাকে।

## 6. Counter vs Accumulator

Counter ও accumulator-এর কাজ আলাদা।

| বিষয় | Counter | Accumulator |
|---|---|---|
| প্রধান কাজ | সংখ্যা গণনা করা | চলমান result জমা রাখা |
| সাধারণ update | `count += 1` | `total += number` |
| Initial value | সাধারণত `0` | কাজ অনুযায়ী নির্ধারিত |
| উদাহরণ | Even number কতটি আছে | সব number-এর যোগফল |
| Value কী বোঝায় | কতবার ঘটনা ঘটেছে | এখন পর্যন্ত হিসাবের result |

### Combined Example

একটি list-এর even number-এর সংখ্যা এবং তাদের যোগফল বের করি।

```python
numbers = [2, 5, 8, 11, 14]

even_count = 0
even_total = 0

for number in numbers:
    if number % 2 == 0:
        even_count += 1
        even_total += number

print("Even count:", even_count)
print("Even total:", even_total)
```

Output:

```text
Even count: 3
Even total: 24
```

এখানে:

- `even_count` হলো counter।
- `even_total` হলো accumulator।

## 7. Initializing Loop Variables

**Initialization** বলতে variable-এর প্রাথমিক value নির্ধারণ করাকে বোঝায়।

উদাহরণ:

```python
count = 0
total = 0
```

Loop শুরু হওয়ার আগে variable initialize করা গুরুত্বপূর্ণ, যাতে variable-এর প্রাথমিক value সঠিক থাকে।

### Example: Correct Initialization

```python
total = 0

for number in range(1, 4):
    total += number

print(total)
```

Output:

```text
6
```

### What Happens Without Initialization?

```python
for number in range(1, 4):
    total += number

print(total)
```

যদি `total` আগে define করা না থাকে, তাহলে সাধারণ Python environment-এ `NameError` হবে।

**Rule:** Counter বা accumulator হিসেবে ব্যবহার করার variable-কে loop-এর আগে সঠিকভাবে initialize করো।

## 8. Updating Loop Variables

`while` loop-এ condition পরিবর্তন করার জন্য প্রায়ই variable update করতে হয়।

### Increasing a Variable

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

Output:

```text
1
2
3
```

### Decreasing a Variable

```python
count = 3

while count >= 1:
    print(count)
    count -= 1
```

Output:

```text
3
2
1
```

প্রথম উদাহরণে variable বাড়ছে, দ্বিতীয় উদাহরণে কমছে।

Update সঠিক না হলে condition কখনো `False` নাও হতে পারে। সে ক্ষেত্রে loop infinite হয়ে যেতে পারে।

## 9. Loop Variables in a `for` Loop

`for` loop-এর variable iterable থেকে value পায়।

```python
for number in [10, 20, 30]:
    print(number)
```

Output:

```text
10
20
30
```

প্রতিটি iteration-এ `number`-এর value যথাক্রমে `10`, `20` এবং `30` হয়।

### Important Difference

```python
for number in range(1, 4):
    print(number)
```

এখানে `number`-কে নিজে `number += 1` দিয়ে update করতে হয় না।

কিন্তু:

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

এখানে `count`-কে update করতে হয়েছে।

## 10. Common Mistakes

### Mistake 1: Counter Initialize না করা

ভুল:

```python
for i in range(5):
    count += 1
```

`count` আগে define করা না থাকলে error হবে।

সঠিক:

```python
count = 0

for i in range(5):
    count += 1

print(count)
```

### Mistake 2: Accumulator-এর ভুল Initial Value

যোগফলের জন্য:

```python
total = 0
```

গুণফলের জন্য:

```python
product = 1
```

ভুল initial value দিলে result ভুল হতে পারে।

### Mistake 3: Accumulator-এর পরিবর্তে Assignment করা

ভুল:

```python
total = 0

for number in range(1, 4):
    total = number

print(total)
```

Output:

```text
3
```

এখানে প্রতিবার আগের value replace হচ্ছে।

সঠিক:

```python
total = 0

for number in range(1, 4):
    total += number

print(total)
```

Output:

```text
6
```

### Mistake 4: `while` Loop-এ Update করতে ভুলে যাওয়া

```python
count = 1

while count <= 3:
    print(count)
```

এখানে `count` বাড়ছে না, তাই loop শেষ হবে না।

### Mistake 5: Counter ও Accumulator গুলিয়ে ফেলা

যদি জানতে চাও কতটি even number আছে, counter ব্যবহার করবে। যদি জানতে চাও even number-গুলোর যোগফল কত, accumulator ব্যবহার করবে।

## 11. Practice Exercises

### Exercise 1

Loop control variable কী?

### Exercise 2

Counter ও accumulator-এর মধ্যে পার্থক্য লেখো।

### Exercise 3

নিচের code-এর output কী হবে?

```python
count = 0

for i in range(4):
    count += 1

print(count)
```

### Exercise 4

নিচের code-এর output কী হবে?

```python
total = 0

for number in range(1, 5):
    total += number

print(total)
```

### Exercise 5

নিচের code-এর output কী হবে?

```python
product = 1

for number in range(1, 4):
    product *= number

print(product)
```

### Exercise 6

একটি list-এ কয়টি odd number আছে তা গণনা করার code লেখো।

```python
numbers = [1, 2, 5, 8, 9, 12]
```

### Exercise 7

নিচের code-এ কী সমস্যা রয়েছে?

```python
count = 1

while count <= 5:
    print(count)
    count -= 1
```

## 12. Answer Key

### Exercise 1

Loop control variable হলো এমন variable, যা loop-এর execution নিয়ন্ত্রণ বা iteration-এর অগ্রগতি track করতে সাহায্য করে।

### Exercise 2

Counter কোনো ঘটনা বা item-এর সংখ্যা গণনা করে। Accumulator repeated calculation-এর result জমা রাখে।

### Exercise 3

```text
4
```

### Exercise 4

```text
10
```

কারণ \(1 + 2 + 3 + 4 = 10\)।

### Exercise 5

```text
6
```

কারণ \(1 \times 2 \times 3 = 6\)।

### Exercise 6

```python
numbers = [1, 2, 5, 8, 9, 12]
odd_count = 0

for number in numbers:
    if number % 2 != 0:
        odd_count += 1

print("Odd count:", odd_count)
```

Output:

```text
Odd count: 3
```

### Exercise 7

`count` এক করে কমছে। তাই এটি `5`-এর চেয়ে ছোটই থাকবে এবং condition সবসময় `True` হবে। Loop শেষ করতে `count += 1` ব্যবহার করতে হবে।

## 13. Chapter Progress Checklist

- [ ] Loop control variable কী, বুঝেছি।
- [ ] Counter variable দিয়ে সংখ্যা গণনা করতে পারি।
- [ ] Accumulator দিয়ে যোগফল ও গুণফল বের করতে পারি।
- [ ] Initialization কেন প্রয়োজন, বুঝেছি।
- [ ] `for` loop ও `while` loop-এর variable handling-এর পার্থক্য জানি।
- [ ] Loop variable-এর value dry run করতে পারি।
- [ ] Infinite loop-এর একটি সাধারণ কারণ শনাক্ত করতে পারি।

## 14. Summary

- Loop control variable loop-এর execution নিয়ন্ত্রণ বা অগ্রগতি track করতে সাহায্য করে।
- Counter কোনো item বা ঘটনার সংখ্যা গণনা করে।
- Accumulator calculation-এর চলমান result জমা রাখে।
- Counter ও accumulator loop শুরু হওয়ার আগে initialize করতে হয়।
- `while` loop-এ প্রয়োজন অনুযায়ী variable update করতে হয়।
- `for` loop-এর variable সাধারণত iterable থেকে পরবর্তী value পায়।
- সঠিক initialization ও update loop-এর result নির্ভুল রাখতে সাহায্য করে।

**Next Topic:** `07_Entry_Controlled_and_Exit_Controlled_Loops.md`
