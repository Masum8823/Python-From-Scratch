# 41. Understanding Inner and Outer Loops

## 1. Introduction

Nested loop-এ একটি loop-এর ভেতরে আরেকটি loop থাকে। এখানে:

- **Outer Loop:** বাইরের loop, যা inner loop-এর execution নিয়ন্ত্রণ করে।
- **Inner Loop:** বাইরের loop-এর ভেতরে থাকা loop, যা প্রতিটি outer iteration-এ চলে।

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

এখানে `i` হলো outer loop-এর variable এবং `j` হলো inner loop-এর variable।

## 2. What Is an Outer Loop?

Outer loop হলো nested structure-এর বাইরের loop।

এটি নির্ধারণ করে কতবার inner loop চালানো হবে।

### Example

```python
for i in range(1, 4):
    print("Outer loop:", i)
```

**Output:**

```text
Outer loop: 1
Outer loop: 2
Outer loop: 3
```

এখানে outer loop তিনবার চলে।

Nested loop-এ প্রতিবার outer loop একটি নতুন value নিলে inner loop সাধারণত আবার শুরু থেকে চলে।

## 3. What Is an Inner Loop?

Inner loop হলো outer loop-এর ভেতরে থাকা loop।

এটি প্রতিটি outer iteration-এর জন্য নিজের condition বা iterable অনুযায়ী কাজ করে।

### Example

```python
for i in range(1, 3):
    for j in range(1, 4):
        print("Inner loop:", j)
```

**Output:**

```text
Inner loop: 1
Inner loop: 2
Inner loop: 3
Inner loop: 1
Inner loop: 2
Inner loop: 3
```

এখানে outer loop দুইবার চলে এবং inner loop প্রতিবার তিনবার চলে।

সুতরাং inner loop-এর body মোট ছয়বার execute হয়।

## 4. Main Difference Between Outer and Inner Loops

| বিষয় | Outer Loop | Inner Loop |
|---|---|---|
| অবস্থান | বাইরের দিকে থাকে | Outer loop-এর ভেতরে থাকে |
| প্রধান কাজ | Inner loop কতবার চালানো হবে তা নিয়ন্ত্রণ করা | প্রতিটি outer iteration-এ নিজের কাজ করা |
| Execution order | প্রথমে শুরু হয় | Outer iteration-এর ভেতরে শুরু হয় |
| পুনরাবৃত্তি | নিজের condition বা iterable অনুযায়ী চলে | প্রতিটি outer iteration-এ সাধারণত নতুন করে চলে |
| Example variable | `i` | `j` |

**মনে রাখবে:** Outer ও inner হলো অবস্থানভিত্তিক নাম। এগুলো আলাদা কোনো Python keyword নয়।

## 5. How Do Both Loops Work Together?

Code:

```python
for i in range(1, 3):
    for j in range(1, 4):
        print(i, j)
```

### Step-by-Step Execution

1. Outer loop `i = 1` নেয়।
2. Inner loop `j = 1` নেয় এবং `1 1` print করে।
3. Inner loop `j = 2` নেয় এবং `1 2` print করে।
4. Inner loop `j = 3` নেয় এবং `1 3` print করে।
5. Inner loop শেষ হয়।
6. Outer loop `i = 2` নেয়।
7. Inner loop আবার `j = 1` থেকে শুরু করে।
8. `2 1`, `2 2`, `2 3` print হয়।
9. Outer loop শেষ হয়।

### Dry Run Table

| Outer `i` | Inner `j` | Output |
|---:|---:|---|
| 1 | 1 | `1 1` |
| 1 | 2 | `1 2` |
| 1 | 3 | `1 3` |
| 2 | 1 | `2 1` |
| 2 | 2 | `2 2` |
| 2 | 3 | `2 3` |

## 6. How Many Times Does Each Loop Run?

যদি outer loop \(m\) বার চলে এবং inner loop প্রতিবার \(n\) বার চলে, তাহলে:

- Outer loop-এর iteration সংখ্যা = \(m\)
- Inner loop-এর মোট iteration সংখ্যা = \(m \times n\)

### Example

```python
for i in range(1, 5):
    for j in range(1, 6):
        print(i, j)
```

এখানে:

- Outer loop = ৪ বার
- Inner loop প্রতিবার = ৫ বার
- Inner loop-এর মোট iteration = \(4 \times 5 = 20\)

তবে `break`, `return` বা অন্য control flow execution আগেই বন্ধ করলে মোট iteration কম হতে পারে।

## 7. Understanding the Role of Indentation

Python-এ indentation নির্ধারণ করে কোন statement কোন loop-এর অংশ।

### Example 1: `print(j)` Inside the Inner Loop

```python
for i in range(1, 3):
    for j in range(1, 4):
        print(i, j)
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

`print(i, j)` inner loop-এর ভেতরে থাকায় এটি ছয়বার চলে।

### Example 2: `print(i)` Outside the Inner Loop

```python
for i in range(1, 3):
    for j in range(1, 4):
        print("Inner:", j)

    print("Outer:", i)
```

Output:

```text
Inner: 1
Inner: 2
Inner: 3
Outer: 1
Inner: 1
Inner: 2
Inner: 3
Outer: 2
```

এখানে `print("Outer:", i)` inner loop-এর বাইরে, কিন্তু outer loop-এর ভেতরে। তাই এটি প্রতিটি outer iteration-এর শেষে একবার চলে।

## 8. Outer and Inner Loops with `while`

Outer ও inner loop শুধু `for` loop নয়; `while` loop-ও হতে পারে।

### Example

```python
i = 1

while i <= 2:
    j = 1

    while j <= 3:
        print(i, j)
        j += 1

    i += 1
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

এখানে:

- `i` outer loop নিয়ন্ত্রণ করে।
- `j` inner loop নিয়ন্ত্রণ করে।
- `j` প্রতিবার update হয়।
- Inner loop শেষ হলে `i` update হয়।

**গুরুত্বপূর্ণ:** `j = 1` outer loop-এর ভেতরে থাকার কারণে প্রতিটি outer iteration-এ inner loop আবার শুরু থেকে চলে।

## 9. What Happens When the Inner Loop Is Empty?

Inner loop-এর iterable খালি হলে inner loop-এর body execute হয় না।

### Example

```python
for i in range(1, 4):
    for j in range(0):
        print(i, j)

    print("Outer:", i)
```

**Output:**

```text
Outer: 1
Outer: 2
Outer: 3
```

`range(0)` কোনো value দেয় না। তাই inner loop-এর `print(i, j)` চলে না, কিন্তু outer loop চলতে থাকে।

## 10. Using `break` and `continue`

Nested loop-এ `break` ও `continue` সাধারণত যে loop-এর ভেতরে লেখা হয়, সেই নিকটতম loop-কে প্রভাবিত করে।

### Example: `break` in the Inner Loop

```python
for i in range(1, 4):
    for j in range(1, 4):
        if j == 2:
            break

        print(i, j)
```

**Output:**

```text
1 1
2 1
3 1
```

Inner loop প্রতিবার `j == 2` হলে বন্ধ হয়। এরপর outer loop পরবর্তী iteration শুরু করে।

### Example: `continue` in the Inner Loop

```python
for i in range(1, 3):
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
```

`j == 2` হলে শুধু ওই iteration-এর `print()` বাদ পড়ে।

## 11. Practical Example: Rows and Columns

Nested loop দিয়ে row ও column-এর grid তৈরি করা যায়।

```python
for row in range(1, 4):
    for column in range(1, 5):
        print("*", end=" ")
    print()
```

**Output:**

```text
* * * *
* * * *
* * * *
```

এখানে:

- Outer loop তিনটি row তৈরি করে।
- Inner loop প্রতিটি row-তে চারটি star print করে।
- মোট star = \(3 \times 4 = 12\)।

## 12. Common Mistakes

### Mistake 1: Thinking the Inner Loop Runs Only Once

Inner loop প্রতিটি outer iteration-এ সাধারণত সম্পূর্ণ চলে, শুধু একবার নয়।

### Mistake 2: Confusing the Variables

`i` ও `j` শুধু প্রচলিত variable name। চাইলে `row`, `column`, `student`, `subject` ইত্যাদি অর্থপূর্ণ নাম ব্যবহার করা যায়।

### Mistake 3: Wrong Indentation

একটি statement inner loop-এর ভেতরে নাকি বাইরে, তা তার indentation দেখে নির্ধারিত হয়।

### Mistake 4: Forgetting to Reset the `while` Loop Variable

Nested `while` loop-এ inner variable সঠিকভাবে initialize না করলে inner loop পরবর্তী outer iteration-এ নাও চলতে পারে।

### Mistake 5: Updating the Wrong Variable

Inner loop-এর variable update করতে ভুলে গেলে inner loop শেষ নাও হতে পারে। Outer variable update না করলে outer loop চলতেই পারে।

## 13. Practice Exercises

### Exercise 1: Find the Output

```python
for i in range(1, 3):
    for j in range(1, 3):
        print(i)
```

### Exercise 2: Count the Iterations

```python
for i in range(1, 5):
    for j in range(1, 4):
        print(i, j)
```

`print(i, j)` মোট কতবার execute হবে?

### Exercise 3: Find the Output

```python
for i in range(1, 3):
    for j in range(1, 4):
        print(j, end=" ")

    print()
```

### Exercise 4: Identify the Outer Loop

```python
for row in range(1, 4):
    for column in range(1, 5):
        print(row, column)
```

কোনটি outer loop এবং কোনটি inner loop?

### Exercise 5: Explain the Difference

Inner loop-এর ভেতরে `print()` এবং inner loop-এর বাইরে কিন্তু outer loop-এর ভেতরে `print()` রাখলে কী পার্থক্য হয়?

### Exercise 6: Fix the Code

```python
i = 1
j = 1

while i <= 2:
    while j <= 2:
        print(i, j)
        j += 1

    i += 1
```

Code-টি এমনভাবে ঠিক করো, যাতে প্রতিটি outer iteration-এ inner loop দুইবার চলে।

## 14. Practice Answer Key

### Answer 1

```text
1
1
2
2
```

প্রতিটি outer iteration-এ inner loop দুইবার চলে এবং `i` print হয়।

### Answer 2

Outer loop চারবার এবং inner loop প্রতিবার তিনবার চলে।

মোট execution:

\[
4 \times 3 = 12
\]

### Answer 3

```text
1 2 3
1 2 3
```

প্রতিটি outer iteration-এ inner loop তিনটি সংখ্যা print করে।

### Answer 4

- Outer loop: `for row in range(1, 4)`
- Inner loop: `for column in range(1, 5)`

### Answer 5

- Inner loop-এর ভেতরের `print()` প্রতিটি inner iteration-এ চলে।
- Inner loop-এর বাইরের কিন্তু outer loop-এর ভেতরের `print()` প্রতিটি outer iteration-এ একবার চলে।

### Answer 6

```python
i = 1

while i <= 2:
    j = 1

    while j <= 2:
        print(i, j)
        j += 1

    i += 1
```

এখানে `j = 1` outer loop-এর ভেতরে রাখা হয়েছে, তাই প্রতিবার inner loop নতুন করে শুরু হয়।

## 15. Chapter Summary

- Outer loop হলো nested structure-এর বাইরের loop।
- Inner loop হলো outer loop-এর ভেতরের loop।
- Inner loop প্রতিটি outer iteration-এ সাধারণত সম্পূর্ণ চলে।
- Indentation দিয়ে বোঝা যায় কোন statement কোন loop-এর অংশ।
- Inner loop খালি হলেও outer loop চলতে পারে।
- `break` ও `continue` সাধারণত নিকটতম enclosing loop-কে প্রভাবিত করে।
- Nested `while` loop-এ variable initialization ও update খুব গুরুত্বপূর্ণ।

## 16. Completion Checklist

- [ ] Outer ও inner loop আলাদা করতে পারি।
- [ ] Nested loop-এর execution order ব্যাখ্যা করতে পারি।
- [ ] Dry run table তৈরি করতে পারি।
- [ ] Loop-এর indentation বুঝতে পারি।
- [ ] মোট iteration হিসাব করতে পারি।
- [ ] Nested `while` loop-এর variable initialization ও update বুঝি।
- [ ] Nested loop-এ `break` ও `continue`-এর প্রভাব ব্যাখ্যা করতে পারি।

**Next Topic:** `42_Multiplication_Tables_Using_Loops.md`
