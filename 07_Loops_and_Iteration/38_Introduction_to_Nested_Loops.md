# 38. Introduction to Nested Loops

## 1. What Is a Nested Loop?

Python-এ একটি loop-এর ভেতরে আরেকটি loop থাকলে তাকে **Nested Loop** বলে।

সাধারণ loop একটি sequence বা নির্দিষ্ট range-এর ওপর পুনরাবৃত্তি করে। Nested loop-এ বাইরের loop-এর প্রতিটি iteration-এর জন্য ভেতরের loop-ও চলে।

### Example

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

এখানে:
- `i` হলো outer loop-এর variable।
- `j` হলো inner loop-এর variable।
- প্রতিটি `i`-এর জন্য `j` তিনটি মান নেয়।

## 2. Why Do We Need Nested Loops?

কিছু সমস্যা সমাধান করতে একটি loop যথেষ্ট নয়। একটি কাজের প্রতিটি ধাপের ভেতরে আবার একাধিক কাজ করতে হলে nested loop কাজে লাগে।

### Real-Life Example

ধরো, একটি ক্লাসে ৩টি row-তে শিক্ষার্থীরা বসেছে এবং প্রতিটি row-তে ৪টি seat আছে।

- Outer loop প্রতিটি row নির্দেশ করতে পারে।
- Inner loop প্রতিটি row-এর seat নির্দেশ করতে পারে।

```python
for row in range(1, 4):
    for seat in range(1, 5):
        print("Row:", row, "Seat:", seat)
```

এই code-এ মোট \(3 \times 4 = 12\)টি row-seat combination print হবে।

## 3. Basic Structure of a Nested Loop

Nested `for` loop-এর সাধারণ structure:

```python
for outer_variable in outer_sequence:
    for inner_variable in inner_sequence:
        statement
```

এখানে:

1. Outer loop শুরু হয়।
2. Inner loop শুরু থেকে শেষ পর্যন্ত চলে।
3. Inner loop শেষ হলে outer loop পরবর্তী iteration নেয়।
4. Outer loop শেষ না হওয়া পর্যন্ত একই প্রক্রিয়া চলতে থাকে।

**গুরুত্বপূর্ণ:** Indentation ঠিক রাখতে হবে। Inner loop-টি outer loop-এর ভেতরে থাকতে হবে।

## 4. First Simple Example

```python
for i in range(1, 3):
    for j in range(1, 3):
        print("Hello")
```

**Output:**

```text
Hello
Hello
Hello
Hello
```

### Explanation

- Outer loop ২ বার চলে।
- Inner loop প্রতিবার ২ বার চলে।
- `print("Hello")` মোট \(2 \times 2 = 4\) বার চলে।

এখানে `i` ও `j` print করা হয়নি, তাই output-এ শুধু `Hello` দেখা যায়।

## 5. Understanding Outer and Inner Loops

```python
for i in range(1, 4):
    print("Outer:", i)

    for j in range(1, 3):
        print("Inner:", j)
```

**Output:**

```text
Outer: 1
Inner: 1
Inner: 2
Outer: 2
Inner: 1
Inner: 2
Outer: 3
Inner: 1
Inner: 2
```

### Explanation

প্রথমে `i = 1` হয়। এরপর outer loop-এর print চলে এবং inner loop সম্পূর্ণ চলে।

তারপর `i = 2` হয় এবং inner loop আবার শুরু থেকে চলে। একইভাবে `i = 3` হলে inner loop আবার সম্পূর্ণ চলে।

**মূল নিয়ম:** Inner loop-এর variable প্রতিটি নতুন inner-loop execution-এ `range()` থেকে আবার মান নেয়।

## 6. Nested Loop with Numbers

### Example: Number Pairs

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

এখানে:
- প্রথম সংখ্যাটি `i`।
- দ্বিতীয় সংখ্যাটি `j`।
- প্রতিটি outer iteration-এ inner loop দুইবার চলে।

## 7. Dry Run of a Nested Loop

Code:

```python
for i in range(1, 3):
    for j in range(1, 3):
        print(i, j)
```

### Dry Run Table

| Step | `i` | `j` | Output |
|---:|---:|---:|---|
| 1 | 1 | 1 | `1 1` |
| 2 | 1 | 2 | `1 2` |
| 3 | 2 | 1 | `2 1` |
| 4 | 2 | 2 | `2 2` |

মোট ৪টি output line তৈরি হয়।

### How to Dry Run

1. প্রথমে outer loop-এর প্রথম মান নাও।
2. ওই মানের জন্য inner loop-এর সব মান অনুসরণ করো।
3. Inner loop শেষ হলে outer loop-এর পরের মান নাও।
4. একইভাবে বাকি iteration অনুসরণ করো।

## 8. Nested Loops with `while`

Nested loop শুধু `for` দিয়ে নয়, `while` দিয়েও লেখা যায়।

```python
i = 1

while i <= 2:
    j = 1

    while j <= 3:
        print(i, j)
        j += 1

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

এখানে `j = 1` outer loop-এর ভেতরে রাখা হয়েছে। তাই প্রতিটি outer iteration-এ inner loop আবার ১ থেকে শুরু হয়।

`j += 1` না থাকলে inner loop শেষ হবে না। `i += 1` না থাকলে outer loop শেষ হবে না।

## 9. How Many Times Does a Nested Loop Run?

যদি outer loop \(m\) বার চলে এবং inner loop প্রতিবার \(n\) বার চলে, তাহলে inner-loop body মোট:

\[
m \times n
\]

বার চলে।

### Example

```python
for i in range(1, 5):
    for j in range(1, 6):
        print("*")
```

- Outer loop: ৪ বার
- Inner loop: প্রতিবার ৫ বার
- মোট `print()` execution: \(4 \times 5 = 20\) বার

এই হিসাব ধরে নেওয়া হয় যে কোনো `break` বা অন্য control-flow statement iteration কমাচ্ছে না।

## 10. Common Uses of Nested Loops

Nested loop সাধারণত এসব কাজে ব্যবহার হয়:

1. Multiplication table তৈরি করা।
2. Star pattern print করা।
3. Number pattern তৈরি করা।
4. Row ও column নিয়ে কাজ করা।
5. Matrix বা two-dimensional data process করা।
6. একাধিক item-এর combination তৈরি করা।

### Example: Simple Pattern

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

Inner loop প্রতিটি row-তে তিনটি star print করে। Inner loop শেষ হলে বাইরের `print()` নতুন line শুরু করে।

## 11. Common Beginner Mistakes

### Mistake 1: Wrong Indentation

```python
for i in range(1, 3):
    for j in range(1, 3):
    print(i, j)
```

এখানে indentation ভুল, তাই `IndentationError` হতে পারে।

সঠিক code:

```python
for i in range(1, 3):
    for j in range(1, 3):
        print(i, j)
```

### Mistake 2: Misunderstanding the Execution Order

Inner loop একবার চলে তারপর outer loop এগোয়—এভাবে নয়। Inner loop প্রতিটি outer iteration-এ সম্পূর্ণ চলে।

### Mistake 3: Forgetting to Reset a `while` Loop Variable

যদি `j = 1` outer loop-এর বাইরে রাখা হয়, তাহলে inner loop প্রথমবার শেষ হওয়ার পর আর নাও চলতে পারে। তাই প্রয়োজন অনুযায়ী `j`-কে outer loop-এর ভেতরে initialize করতে হবে।

### Mistake 4: Forgetting Variable Updates

`while` loop-এ সঠিক variable update না করলে infinite loop হতে পারে।

## 12. Practice Exercises

### Exercise 1: Find the Output

```python
for i in range(1, 3):
    for j in range(1, 3):
        print("*")
```

### Exercise 2: Count the Iterations

```python
for i in range(1, 4):
    for j in range(1, 5):
        print(i, j)
```

মোট কতবার `print()` execute হবে?

### Exercise 3: Find the Output

```python
for i in range(1, 3):
    for j in range(1, 4):
        print(i, end=" ")
    print()
```

### Exercise 4: Complete the Code

নিচের code-এ inner loop-কে এমনভাবে পূরণ করো, যাতে প্রতিটি outer iteration-এ `1` ও `2` print হয়।

```python
for i in range(1, 4):
    for j in range(1, 3):
        # Write your statement here
```

### Exercise 5: Explain the Difference

একটি সাধারণ loop এবং nested loop-এর মধ্যে পার্থক্য কী?

## 13. Practice Answer Key

### Answer 1

```text
*
*
*
*
```

দুটি outer iteration এবং প্রতিটিতে দুটি inner iteration হয়।

### Answer 2

Outer loop ৩ বার এবং inner loop প্রতিবার ৪ বার চলে।

মোট execution:

\[
3 \times 4 = 12
\]

### Answer 3

```text
1 1 1
2 2 2
```

প্রতিটি outer iteration-এ inner loop তিনবার `i` print করে। এরপর `print()` নতুন line শুরু করে।

### Answer 4

```python
for i in range(1, 4):
    for j in range(1, 3):
        print(j)
```

এতে প্রতিটি outer iteration-এ `1` ও `2` print হবে।

### Answer 5

সাধারণ loop একটি sequence বা condition অনুযায়ী পুনরাবৃত্তি করে। Nested loop-এ একটি loop-এর ভেতরে আরেকটি loop থাকে, ফলে প্রতিটি outer iteration-এর জন্য inner loop-ও চলে।

## 14. Chapter Summary

- একটি loop-এর ভেতরে আরেকটি loop থাকলে তাকে nested loop বলে।
- Outer loop প্রতিটি iteration-এ inner loop চালায়।
- Inner loop শেষ হওয়ার পর outer loop পরবর্তী iteration শুরু করে।
- সমান সংখ্যক iteration হলে মোট execution সংখ্যা গুণ করে বের করা যায়।
- `for` ও `while`—দুই ধরনের loop nested করা যায়।
- সঠিক indentation ও variable update নিশ্চিত করতে হয়।

## 15. Completion Checklist

- [ ] Nested loop-এর সংজ্ঞা বলতে পারি।
- [ ] Outer ও inner loop শনাক্ত করতে পারি।
- [ ] Nested loop-এর execution order বুঝি।
- [ ] Dry run table তৈরি করতে পারি।
- [ ] মোট iteration হিসাব করতে পারি।
- [ ] Simple nested-loop program লিখতে পারি।

**Next Topic:** `39_Nested_for_Loops.md`
