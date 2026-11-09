# 05. Understanding Loop Execution Flow

## 1. Introduction

Loop execution flow বলতে বোঝায়, একটি loop চলার সময় program কোন ক্রমে বিভিন্ন ধাপ সম্পন্ন করে।

একটি loop শুধু code বারবার চালায় না; প্রতিটি iteration-এ নির্দিষ্ট নিয়ম অনুসরণ করে। যেমন:

1. Loop শুরু হয়।
2. প্রয়োজন অনুযায়ী condition পরীক্ষা করা হয় অথবা পরবর্তী item নেওয়া হয়।
3. Loop body execute হয়।
4. পরবর্তী iteration-এর জন্য execution এগিয়ে যায়।
5. Loop শেষ হওয়ার শর্ত পূরণ হলে loop বন্ধ হয়।

এই chapter-এ আমরা `for` ও `while` loop-এর execution flow আলাদাভাবে বুঝব।

## 2. Execution Flow of a `while` Loop

`while` loop-এর ক্ষেত্রে প্রতিটি iteration শুরু হওয়ার আগে condition পরীক্ষা করা হয়।

### General Flow

1. প্রথমে condition পরীক্ষা করা হয়।
2. Condition `True` হলে loop body execute হয়।
3. Loop body-এর statement-গুলো execute হয়।
4. আবার condition পরীক্ষা করা হয়।
5. Condition `False` হলে loop বন্ধ হয় এবং পরের statement execute হয়।

### Example

```python
count = 1

while count <= 3:
    print(count)
    count += 1

print("Loop finished")
```

**Output:**

```text
1
2
3
Loop finished
```

### Step-by-Step Execution

| Step | `count` | Condition `count <= 3` | কী হবে |
|---:|---:|---|---|
| 1 | 1 | `True` | 1 print হবে |
| 2 | 2 | `True` | 2 print হবে |
| 3 | 3 | `True` | 3 print হবে |
| 4 | 4 | `False` | Loop শেষ হবে |

শেষ iteration-এ `count += 1` execute হওয়ার পর `count`-এর value ৪ হয়। এরপর condition পরীক্ষা করে `False` পাওয়া যায়।

তাই loop body আর execute হয় না।

**Important:** `while` loop-এ condition শুরুতেই `False` হলে loop body একবারও execute হয় না।

উদাহরণ:

```python
count = 5

while count < 3:
    print(count)

print("Finished")
```

Output:

```text
Finished
```

কারণ `5 < 3` হলো `False`।

## 3. Execution Flow of a `for` Loop

`for` loop একটি iterable থেকে একটির পর একটি item নেয়। প্রতিটি item-এর জন্য loop body execute হয়।

### General Flow

1. Iterable থেকে পরবর্তী item নেওয়া হয়।
2. Item-টি loop variable-এ রাখা হয়।
3. Loop body execute হয়।
4. পরবর্তী item নেওয়া হয়।
5. সব item শেষ হলে loop বন্ধ হয়।

### Example

```python
for number in range(1, 4):
    print(number)

print("Loop finished")
```

**Output:**

```text
1
2
3
Loop finished
```

### Step-by-Step Execution

| Iteration | `number` | Action |
|---:|---:|---|
| 1 | 1 | 1 print হবে |
| 2 | 2 | 2 print হবে |
| 3 | 3 | 3 print হবে |
| — | — | আর item নেই, তাই loop শেষ |

এখানে `range(1, 4)` থেকে `1`, `2` ও `3` পাওয়া যায়। Stop value `4` অন্তর্ভুক্ত হয় না।

`for` loop-এ সাধারণত আলাদাভাবে loop variable বাড়াতে হয় না। Iterable থেকে পরবর্তী item স্বয়ংক্রিয়ভাবে পাওয়া যায়।

## 4. Difference Between `for` and `while` Execution Flow

| বিষয় | `for` Loop | `while` Loop |
|---|---|---|
| পরবর্তী ধাপ | Iterable থেকে item নেয় | Condition পরীক্ষা করে |
| Body কখন চলে? | Item পাওয়া গেলে | Condition `True` হলে |
| Loop কখন শেষ হয়? | Iterable-এর item শেষ হলে অথবা অন্য control flow-তে | Condition `False` হলে অথবা অন্য control flow-তে |
| Variable update | সাধারণত iterable থেকে value আসে | প্রয়োজন অনুযায়ী body-তে update করতে হয় |
| শুরুতেই body skip হতে পারে? | Iterable-এ item না থাকলে | Condition শুরুতেই `False` হলে |

দুই ধরনের loop-এর execution flow আলাদা হলেও, অনেক problem-এ তাদের দিয়ে একই কাজ করা যায়।

## 5. Understanding the Order of Statements

Loop body-এর ভেতরে statement-গুলোর order গুরুত্বপূর্ণ।

### Example A: Print Before Updating

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

এখানে প্রথমে বর্তমান value print হয়, তারপর value বাড়ে।

### Example B: Update Before Printing

```python
count = 1

while count <= 3:
    count += 1
    print(count)
```

Output:

```text
2
3
4
```

এখানে প্রথমে value বাড়ানো হয়, তারপর print করা হয়।

দুটি code-এর মধ্যে শুধু statement-এর order পরিবর্তন হয়েছে, কিন্তু output আলাদা হয়েছে।

**শিক্ষা:** Loop trace করার সময় শুধু condition নয়, loop body-এর প্রতিটি statement কোন ক্রমে execute হচ্ছে সেটিও দেখতে হবে।

## 6. Dry Run: Tracking Variable Values

**Dry Run** হলো code execute না করে ধাপে ধাপে variable-এর value এবং program-এর output অনুসরণ করা।

নিচের code দেখি:

```python
total = 0

for number in range(1, 4):
    total += number
    print(total)
```

Output:

```text
1
3
6
```

### Dry Run Table

| Iteration | `number` | আগের `total` | নতুন `total` | Output |
|---:|---:|---:|---:|---:|
| শুরুতে | — | — | 0 | — |
| 1 | 1 | 0 | 1 | 1 |
| 2 | 2 | 1 | 3 | 3 |
| 3 | 3 | 3 | 6 | 6 |

এখানে `total` প্রতিটি iteration-এ আগের value-এর সঙ্গে নতুন number যোগ করে আপডেট হচ্ছে।

## 7. Loop Execution with `if` Statements

Loop-এর ভেতরে conditional statement ব্যবহার করলে প্রতিটি iteration-এ condition অনুযায়ী আলাদা কাজ করা যায়।

### Example: Print Only Even Numbers

```python
for number in range(1, 7):
    if number % 2 == 0:
        print(number)
```

Output:

```text
2
4
6
```

### Execution Flow

| `number` | `number % 2 == 0` | Action |
|---:|---|---|
| 1 | `False` | কিছু print হবে না |
| 2 | `True` | 2 print হবে |
| 3 | `False` | কিছু print হবে না |
| 4 | `True` | 4 print হবে |
| 5 | `False` | কিছু print হবে না |
| 6 | `True` | 6 print হবে |

এখানে loop ছয়বার চলে, কিন্তু `print()` মাত্র তিনবার execute হয়।

**মনে রাখবে:** Loop-এর iteration সংখ্যা এবং কোনো নির্দিষ্ট statement কতবার execute হবে, তা সবসময় এক নয়।

## 8. Nested Loop Execution Flow

একটি loop-এর ভেতরে আরেকটি loop থাকলে বাইরের loop-এর প্রতিটি iteration-এ ভেতরের loop তার নিজস্ব iteration সম্পন্ন করে।

### Example

```python
for row in range(1, 3):
    for column in range(1, 4):
        print(row, column)
```

Output:

```text
1 1
1 2
1 3
2 1
2 2
2 3
```

### Execution Flow

- `row = 1` হলে inner loop `column = 1, 2, 3` নেয়।
- Inner loop শেষ হলে outer loop পরবর্তী value নেয়।
- `row = 2` হলে inner loop আবার `column = 1, 2, 3` নেয়।
- Outer loop শেষ হলে পুরো nested loop শেষ হয়।

এখানে outer loop ২ বার এবং inner loop প্রতিবার ৩ বার চলে। তাই `print()` মোট \(2 \times 3 = 6\) বার execute হয়।

Nested loop-এর execution flow পরবর্তী nested loop section-এ আরও বিস্তারিত শিখব।

## 9. Common Loop Execution Mistakes

### Mistake 1: Condition কখন পরীক্ষা হয় তা ভুলে যাওয়া

```python
count = 10

while count < 5:
    print(count)
```

কোনো output হবে না, কারণ condition শুরুতেই `False`।

### Mistake 2: Update-এর আগে ও পরে Print-এর পার্থক্য না বোঝা

```python
count = 1

while count <= 3:
    count += 1
    print(count)
```

Output হবে `2`, `3`, `4` — `1`, `2`, `3` নয়।

### Mistake 3: `range()`-এর Stop Value অন্তর্ভুক্ত ধরে নেওয়া

```python
for i in range(1, 4):
    print(i)
```

Output হবে `1`, `2`, `3`।

### Mistake 4: প্রতিটি Iteration-এ Condition বা `if`-এর ফলাফল না দেখা

```python
for number in range(1, 5):
    if number > 2:
        print(number)
```

Output:

```text
3
4
```

Loop চারবার চললেও `print()` দুইবার execute হয়েছে।

### Mistake 5: Loop Body-এর Indentation ভুল করা

```python
for i in range(3):
    print("Inside loop")

print("Outside loop")
```

Output:

```text
Inside loop
Inside loop
Inside loop
Outside loop
```

`print("Outside loop")` loop body-এর বাইরে, তাই এটি loop শেষ হওয়ার পরে একবার execute হয়।

## 10. Practice Exercises

প্রতিটি প্রশ্নের ক্ষেত্রে আগে dry run করে output অনুমান করো।

### Exercise 1

নিচের code-এর output কী?

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

### Exercise 2

নিচের code-এর output কী?

```python
for number in range(2, 6):
    print(number)
```

### Exercise 3

নিচের code-এর output কী?

```python
count = 1

while count < 4:
    count += 1
    print(count)
```

### Exercise 4

নিচের code-এ `print()` কতবার execute হবে?

```python
for number in range(1, 8):
    if number % 2 == 0:
        print(number)
```

### Exercise 5

নিচের code-এর output কী?

```python
total = 0

for number in range(1, 4):
    total += number

print("Total:", total)
```

### Exercise 6

নিচের code-এর output কী?

```python
for row in range(1, 3):
    for column in range(1, 3):
        print(row, column)
```

### Exercise 7

নিচের code-এ কোনো output হবে কি?

```python
count = 5

while count < 3:
    print(count)
```

## 11. Answer Key

### Exercise 1

```text
1
2
3
```

### Exercise 2

```text
2
3
4
5
```

### Exercise 3

```text
2
3
4
```

প্রথমে `count` এক করে বাড়ে, তারপর print হয়।

### Exercise 4

`print()` মোট ৩ বার execute হবে। Output:

```text
2
4
6
```

### Exercise 5

```text
Total: 6
```

### Exercise 6

```text
1 1
1 2
2 1
2 2
```

### Exercise 7

কোনো output হবে না। কারণ `5 < 3` শুরুতেই `False`।

## 12. Chapter Progress Checklist

- [ ] `while` loop-এর execution flow বুঝেছি।
- [ ] `for` loop-এর execution flow বুঝেছি।
- [ ] Condition কখন পরীক্ষা হয়, বুঝতে পারি।
- [ ] Variable update-এর order বুঝতে পারি।
- [ ] Dry run table তৈরি করতে পারি।
- [ ] Loop-এর ভেতরে `if` statement-এর execution বুঝি।
- [ ] Nested loop-এর basic flow বুঝেছি।
- [ ] Loop-এর output manually বের করতে পারি।

## 13. Summary

- Loop execution flow হলো loop চলার সময় statement-গুলো যে ক্রমে execute হয়।
- `while` loop প্রতিটি iteration-এর আগে condition পরীক্ষা করে।
- `for` loop iterable থেকে একটির পর একটি item নেয়।
- Statement-এর order পরিবর্তন হলে output পরিবর্তিত হতে পারে।
- Dry run করে variable-এর value ও output ধাপে ধাপে বোঝা যায়।
- Loop-এর ভেতরে conditional statement থাকলে সব iteration-এ একই statement execute নাও হতে পারে।
- Nested loop-এ inner loop প্রতিটি outer iteration-এর জন্য চলে।

**Next Topic:** `06_Loop_Control_Variables.md`
