# 37. Nested Loops and Control Flow

## 1. Introduction

Python-এ যখন একটি loop-এর ভেতরে আরেকটি loop ব্যবহার করা হয়, তখন তাকে **Nested Loop** বলা হয়।

Nested loop ব্যবহার করা হয় যখন কোনো কাজের জন্য বারবার loop চালানোর পাশাপাশি প্রতিটি iteration-এর ভেতরে আরও কিছু কাজ পুনরাবৃত্তি করতে হয়।

### Example

```python
for i in range(1, 4):
    for j in range(1, 3):
        print(i, j)
```

**Output:**

```text
1 1
1 2
2 1
2 2
3 1
3 2
```

এখানে একটি `for` loop-এর ভেতরে আরেকটি `for` loop রয়েছে।

- বাইরের loop-এর variable হলো `i`।
- ভেতরের loop-এর variable হলো `j`।
- প্রতিবার বাইরের loop চললে ভেতরের loop সম্পূর্ণ চলে।

## 2. Structure of a Nested Loop

সাধারণ structure:

```python
for outer_variable in outer_sequence:
    for inner_variable in inner_sequence:
        # Inner loop body
        statement
```

এখানে:

- `outer_variable` বাইরের loop নিয়ন্ত্রণ করে।
- `inner_variable` ভেতরের loop নিয়ন্ত্রণ করে।
- Inner loop-এর body বাইরের loop-এর প্রতিটি iteration-এ execute হয়।

Nested loop-এ `while` এবং `for`—দুই ধরনের loop-ই ব্যবহার করা যায়।

## 3. How Does a Nested Loop Work?

নিচের code-টি দেখো:

```python
for i in range(1, 4):
    for j in range(1, 3):
        print(i, j)
```

### Step-by-Step Execution

**Step 1:** বাইরের loop `i = 1` নেয়।

**Step 2:** ভেতরের loop `j = 1` নেয় এবং `1 1` print করে।

**Step 3:** ভেতরের loop `j = 2` নেয় এবং `1 2` print করে।

**Step 4:** ভেতরের loop শেষ হয়। বাইরের loop এবার `i = 2` নেয়।

**Step 5:** ভেতরের loop আবার শুরু থেকে চলে এবং `2 1`, `2 2` print করে।

**Step 6:** একইভাবে `i = 3` হলে `3 1`, `3 2` print হয়।

**Step 7:** বাইরের loop শেষ হয়।

### Dry Run Table

| Outer `i` | Inner `j` | Output |
|---:|---:|---|
| 1 | 1 | `1 1` |
| 1 | 2 | `1 2` |
| 2 | 1 | `2 1` |
| 2 | 2 | `2 2` |
| 3 | 1 | `3 1` |
| 3 | 2 | `3 2` |

**মূল নিয়ম:** Inner loop শেষ হওয়ার পরেই outer loop-এর পরবর্তী iteration শুরু হয়।

## 4. Number of Iterations in Nested Loops

Nested loop-এর মোট iteration বের করতে একটি সহজ নিয়ম ব্যবহার করা যায়।

যদি বাইরের loop \(m\) বার চলে এবং প্রতিবার inner loop \(n\) বার চলে, তাহলে inner loop-এর body মোট:

\[
m \times n
\]

বার execute হবে।

### Example

```python
for i in range(1, 5):
    for j in range(1, 4):
        print(i, j)
```

- Outer loop চলে 4 বার।
- Inner loop প্রতিবার চলে 3 বার।
- মোট execution = \(4 \times 3 = 12\) বার।

**Note:** এই গুণের নিয়ম তখনই সরাসরি প্রযোজ্য, যখন প্রতিটি outer iteration-এ inner loop-এর iteration সংখ্যা একই থাকে এবং `break` বা অন্য কোনো control flow তা পরিবর্তন না করে।

## 5. Nested `for` Loops

Nested `for` loop সাধারণত sequence-এর প্রতিটি item-এর সঙ্গে অন্য sequence-এর item মিলিয়ে কাজ করতে ব্যবহৃত হয়।

### Example: Print Number Pairs

```python
for i in range(1, 3):
    for j in range(1, 4):
        print(i, j)
```

**Output:**

```text
1 1
1 2
1 3
2 1
2 2
2 3
```

প্রথমে `i = 1` অবস্থায় সব `j`-এর মান ব্যবহার হয়। এরপর `i = 2` হলে আবার সব `j`-এর মান ব্যবহার হয়।

## 6. Nested `while` Loops

একটি `while` loop-এর ভেতরে আরেকটি `while` loop-ও ব্যবহার করা যায়।

### Example

```python
i = 1

while i <= 3:
    j = 1

    while j <= 2:
        print(i, j)
        j += 1

    i += 1
```

**Output:**

```text
1 1
1 2
2 1
2 2
3 1
3 2
```

### Explanation

- `i` বাইরের loop নিয়ন্ত্রণ করে।
- প্রতিবার বাইরের loop শুরু হলে `j = 1` করা হয়।
- Inner loop `j = 1` এবং `j = 2` নিয়ে চলে।
- Inner loop শেষ হলে `i` বাড়ে।
- এরপর নতুন outer iteration-এ `j` আবার `1` থেকে শুরু হয়।

**গুরুত্বপূর্ণ:** Inner `while` loop-এর variable সঠিকভাবে initialize ও update না করলে infinite loop হতে পারে।

## 7. Mixed Nested Loops

Nested loop-এ `for` এবং `while` একসঙ্গে ব্যবহার করা যায়।

### Example: `for` Inside `while`

```python
i = 1

while i <= 2:
    for j in range(1, 4):
        print(i, j)

    i += 1
```

**Output:**

```text
1 1
1 2
1 3
2 1
2 2
2 3
```

এখানে বাইরের `while` loop এবং ভেতরের `for` loop একসঙ্গে কাজ করছে।

## 8. Control Flow in Nested Loops

Nested loop-এ control flow বোঝার জন্য তিনটি বিষয় গুরুত্বপূর্ণ:

1. Inner loop কখন শুরু হয়।
2. Inner loop কখন শেষ হয়।
3. Outer loop কখন পরবর্তী iteration শুরু করে।

সাধারণভাবে inner loop স্বাভাবিকভাবে শেষ হলে outer loop এগিয়ে যায়। তবে `break` ও `continue` ব্যবহার করলে execution-এর পথ পরিবর্তিত হতে পারে।

### Example: `continue` in the Inner Loop

```python
for i in range(1, 4):
    for j in range(1, 4):
        if j == 2:
            continue

        print(i, j)
```

**Output:**

```text
1 1
1 3
2 1
2 3
3 1
3 3
```

এখানে `continue` inner loop-এর বর্তমান iteration বাদ দেয়। ফলে `j = 2` হলে print হয় না, কিন্তু inner loop চলতে থাকে।

## 9. Common Mistakes

### Mistake 1: Assuming Both Loops Move Together

```python
for i in range(1, 4):
    for j in range(1, 3):
        print(i, j)
```

এখানে `i` এবং `j` একই সঙ্গে বাড়ে না। প্রতিটি `i`-এর জন্য `j`-এর loop সম্পূর্ণ চলে।

### Mistake 2: Forgetting to Reset the Inner `while` Variable

ভুল code:

```python
i = 1
j = 1

while i <= 3:
    while j <= 2:
        print(i, j)
        j += 1

    i += 1
```

এখানে inner loop প্রথমবার শেষ হলে `j = 3` হয়। পরবর্তী outer iteration-এ `j <= 2` false থাকায় inner loop আর চলে না।

সঠিক code:

```python
i = 1

while i <= 3:
    j = 1

    while j <= 2:
        print(i, j)
        j += 1

    i += 1
```

প্রতিবার outer loop শুরু হলে `j` আবার `1` হয়।

### Mistake 3: Wrong Indentation

```python
for i in range(1, 4):
    for j in range(1, 3):
        print(i)

    print(j)
```

এখানে `print(j)` inner loop-এর বাইরে, তাই প্রতিটি outer iteration-এ এটি একবার চলে। এটি inner loop-এর প্রতিটি iteration-এ চলে না।

### Mistake 4: Updating the Wrong Variable

```python
i = 1

while i <= 3:
    j = 1

    while j <= 2:
        print(i, j)
        i += 1
```

এখানে `j` update হচ্ছে না। ফলে inner loop শেষ হবে না এবং `i` বাড়তে থাকবে। এটি infinite loop।

সঠিকভাবে inner loop-এর মধ্যে `j += 1` এবং inner loop-এর পরে `i += 1` ব্যবহার করতে হবে।

## 10. Practical Applications of Nested Loops

Nested loop বিভিন্ন সমস্যায় কাজে লাগে:

- Multiplication table তৈরি করা।
- Star ও number pattern print করা।
- দুইটি list-এর item জোড়া তৈরি করা।
- দুই-মাত্রিক data বা matrix process করা।
- Row ও column নিয়ে কাজ করা।
- একাধিক combination পরীক্ষা করা।

### Example: Simple Grid

```python
for row in range(1, 4):
    for column in range(1, 4):
        print("*", end=" ")
    print()
```

**Output:**

```text
* * *
* * *
* * *
```

এখানে inner loop প্রতিটি row-তে তিনটি `*` print করে। এরপর outer loop-এর জন্য `print()` নতুন line শুরু করে।

## 11. Practice Exercises

### Exercise 1: Find the Output

```python
for i in range(1, 3):
    for j in range(1, 3):
        print(i, j)
```

### Exercise 2: Find the Total Iterations

```python
for i in range(1, 5):
    for j in range(1, 6):
        print(i, j)
```

মোট কতবার `print()` execute হবে?

### Exercise 3: Find the Output

```python
for i in range(1, 4):
    for j in range(1, 4):
        if j == 3:
            continue
        print(i, j)
```

### Exercise 4: Find the Output

```python
for i in range(1, 3):
    for j in range(1, 4):
        print("*", end="")
    print()
```

### Exercise 5: Fix the Code

```python
i = 1
j = 1

while i <= 2:
    while j <= 2:
        print(i, j)
        j += 1
    i += 1
```

এমনভাবে code ঠিক করো, যাতে প্রতিটি `i`-এর জন্য `j` দুইবার চলে।

## 12. Practice Answer Key

### Answer 1

```text
1 1
1 2
2 1
2 2
```

### Answer 2

Outer loop 4 বার এবং inner loop প্রতিবার 5 বার চলে।

মোট iteration = \(4 \times 5 = 20\) বার।

### Answer 3

```text
1 1
1 2
2 1
2 2
3 1
3 2
```

`j == 3` হলে inner loop-এর সেই iteration-এ `print()` বাদ পড়ে।

### Answer 4

```text
***
***
```

প্রতিটি outer iteration-এ inner loop তিনটি `*` print করে।

### Answer 5

```python
i = 1

while i <= 2:
    j = 1

    while j <= 2:
        print(i, j)
        j += 1

    i += 1
```

এখানে প্রতিবার outer loop শুরু হলে `j = 1` করা হয়।

## 13. Chapter Summary

- Nested loop হলো একটি loop-এর ভেতরে আরেকটি loop।
- Inner loop প্রতিটি outer iteration-এ সম্পূর্ণ চলে।
- সমান সংখ্যক inner iteration হলে মোট execution বের করতে outer ও inner iteration সংখ্যা গুণ করা যায়।
- `for`, `while`, অথবা দুই ধরনের loop একসঙ্গে ব্যবহার করা যায়।
- Inner `while` loop-এর variable সঠিকভাবে initialize ও update করতে হয়।
- `break` ও `continue` কোন loop-এর মধ্যে আছে, তা দেখে তাদের প্রভাব বুঝতে হয়।

## 14. Completion Checklist

- [ ] Nested loop কী, তা ব্যাখ্যা করতে পারি।
- [ ] Outer ও inner loop আলাদা করতে পারি।
- [ ] Nested loop-এর output dry run করতে পারি।
- [ ] মোট iteration সংখ্যা বের করতে পারি।
- [ ] Nested `for` ও `while` loop লিখতে পারি।
- [ ] Nested loop-এ indentation ও variable-update-এর ভুল শনাক্ত করতে পারি।

**Next Topic:** `38_Introduction_to_Nested_Loops.md`
