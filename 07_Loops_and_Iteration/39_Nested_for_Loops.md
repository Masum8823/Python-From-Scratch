# 39. Nested `for` Loops

## 1. Introduction

Python-এ একটি `for` loop-এর ভেতরে আরেকটি `for` loop ব্যবহার করলে তাকে **Nested `for` Loop** বলে।

এটি ব্যবহার করা হয় যখন বাইরের প্রতিটি item বা value-এর জন্য ভেতরের loop-এর সব iteration চালাতে হয়।

### Basic Example

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
- `i` বাইরের loop নিয়ন্ত্রণ করে।
- `j` ভেতরের loop নিয়ন্ত্রণ করে।
- প্রতিটি `i`-এর জন্য `j` দুইবার চলে।

## 2. Syntax of Nested `for` Loops

```python
for outer_variable in outer_iterable:
    for inner_variable in inner_iterable:
        statement
```

**কাজ করার নিয়ম:**

1. Outer loop প্রথম value নেয়।
2. Inner loop তার সব value নিয়ে চলে।
3. Inner loop শেষ হলে outer loop পরবর্তী value নেয়।
4. Outer loop শেষ না হওয়া পর্যন্ত এই প্রক্রিয়া চলতে থাকে।

Indentation সঠিক রাখা বাধ্যতামূলক।

## 3. Understanding Execution Order

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

### Dry Run Table

| Step | `i` | `j` | Output |
|---:|---:|---:|---|
| 1 | 1 | 1 | `1 1` |
| 2 | 1 | 2 | `1 2` |
| 3 | 1 | 3 | `1 3` |
| 4 | 2 | 1 | `2 1` |
| 5 | 2 | 2 | `2 2` |
| 6 | 2 | 3 | `2 3` |

লক্ষ্য করো, `i = 1` অবস্থায় `j`-এর সব iteration শেষ হয়েছে। তারপর `i = 2` হয়েছে।

## 4. Printing Number Combinations

Nested `for` loop দিয়ে বিভিন্ন সংখ্যার combination তৈরি করা যায়।

### Example 1

```python
for i in range(1, 4):
    for j in range(1, 3):
        print(i, j)
```

Output:

```text
1 1
1 2
2 1
2 2
3 1
3 2
```

### Example 2: Multiplying Values

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(i * j)
```

Output:

```text
1
2
3
2
4
6
3
6
9
```

প্রতিটি outer iteration-এর জন্য inner loop তিনটি multiplication করে।

## 5. Creating a Multiplication Table

Nested `for` loop দিয়ে একাধিক সংখ্যার multiplication table তৈরি করা যায়।

### Example: Tables from 1 to 3

```python
for i in range(1, 4):
    for j in range(1, 6):
        print(i, "x", j, "=", i * j)
    print()
```

**Output:**

```text
1 x 1 = 1
1 x 2 = 2
1 x 3 = 3
1 x 4 = 4
1 x 5 = 5

2 x 1 = 2
2 x 2 = 4
2 x 3 = 6
2 x 4 = 8
2 x 5 = 10

3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
3 x 4 = 12
3 x 5 = 15
```

এখানে:
- `i` table-এর সংখ্যা নির্ধারণ করে।
- `j` multiplier নির্ধারণ করে।
- Inner loop শেষ হলে `print()` নতুন line-এর পাশাপাশি একটি ফাঁকা line তৈরি করে।

## 6. Printing Star Patterns

Nested `for` loop-এর একটি গুরুত্বপূর্ণ ব্যবহার হলো pattern printing।

### Example 1: Square Pattern

```python
for row in range(1, 5):
    for column in range(1, 5):
        print("*", end=" ")
    print()
```

Output:

```text
* * * *
* * * *
* * * *
* * * *
```

**Explanation:**
- Outer loop চারটি row তৈরি করে।
- Inner loop প্রতিটি row-তে চারটি star print করে।
- `end=" "` একই line-এ star-গুলো print করে।
- Inner loop শেষ হলে বাইরের `print()` নতুন line শুরু করে।

### Example 2: Right-Angled Triangle

```python
for row in range(1, 5):
    for column in range(row):
        print("*", end=" ")
    print()
```

Output:

```text
*
* *
* * *
* * * *
```

এখানে inner loop-এর iteration সংখ্যা `row`-এর মানের ওপর নির্ভর করে।

- প্রথম row-তে ১টি star।
- দ্বিতীয় row-তে ২টি star।
- তৃতীয় row-তে ৩টি star।
- চতুর্থ row-তে ৪টি star।

## 7. Printing Number Patterns

### Example 1: Increasing Numbers

```python
for row in range(1, 5):
    for column in range(1, row + 1):
        print(column, end=" ")
    print()
```

Output:

```text
1
1 2
1 2 3
1 2 3 4
```

### Explanation

`range(1, row + 1)` ব্যবহার করায় প্রতিটি row-তে `1` থেকে বর্তমান row number পর্যন্ত print হয়।

### Example 2: Repeating the Row Number

```python
for row in range(1, 5):
    for column in range(row):
        print(row, end=" ")
    print()
```

Output:

```text
1
2 2
3 3 3
4 4 4 4
```

এখানে প্রতিটি row-তে সেই row-এর সংখ্যাটিই বারবার print হয়।

## 8. Using Conditions Inside Nested `for` Loops

Nested loop-এর মধ্যে `if` ব্যবহার করে নির্দিষ্ট value নির্বাচন করা যায়।

### Example: Print Only Even Products

```python
for i in range(1, 4):
    for j in range(1, 4):
        product = i * j

        if product % 2 == 0:
            print(product)
```

Output:

```text
2
2
4
2
4
6
6
```

শুধু যেসব product ২ দিয়ে বিভাজ্য, সেগুলো print হয়। একই product একাধিক combination থেকে আসতে পারে, তাই output-এ সংখ্যার পুনরাবৃত্তি হতে পারে।

## 9. Iterating Over Two Lists

Nested `for` loop দিয়ে দুটি list-এর সব pair তৈরি করা যায়।

### Example

```python
colors = ["Red", "Blue"]
sizes = ["S", "M", "L"]

for color in colors:
    for size in sizes:
        print(color, size)
```

Output:

```text
Red S
Red M
Red L
Blue S
Blue M
Blue L
```

এখানে প্রতিটি color-এর সঙ্গে প্রতিটি size জোড়া তৈরি হয়েছে।

মোট pair:

\[
2 \times 3 = 6
\]

## 10. Using `break` in Nested `for` Loops

Nested loop-এ `break` ব্যবহার করলে এটি সাধারণত যে loop-এর ভেতরে আছে, সেই নিকটতম loop-টিকেই বন্ধ করে।

### Example

```python
for i in range(1, 4):
    for j in range(1, 4):
        if j == 2:
            break

        print(i, j)
```

Output:

```text
1 1
2 1
3 1
```

### Explanation

প্রতিটি outer iteration-এ inner loop শুরু হয়। `j == 2` হলে inner loop বন্ধ হয়। এরপর outer loop তার পরবর্তী iteration শুরু করে।

**গুরুত্বপূর্ণ:** এখানে `break` outer loop বন্ধ করছে না।

## 11. Using `continue` in Nested `for` Loops

`continue` বর্তমান iteration-এর বাকি অংশ বাদ দিয়ে একই loop-এর পরবর্তী iteration শুরু করে।

### Example

```python
for i in range(1, 3):
    for j in range(1, 4):
        if j == 2:
            continue

        print(i, j)
```

Output:

```text
1 1
1 3
2 1
2 3
```

এখানে inner loop-এর `j == 2` iteration-এ `print()` execute হয় না। অন্য iteration-গুলো স্বাভাবিকভাবে চলে।

## 12. Common Mistakes

### Mistake 1: Incorrect Indentation

Inner loop-কে outer loop-এর ভেতরে সঠিকভাবে indent করতে হবে।

### Mistake 2: Confusing `range()` Limits

`range(1, 4)` হলো `1, 2, 3`। এখানে `4` অন্তর্ভুক্ত নয়।

### Mistake 3: Forgetting the Newline

Pattern print করার সময় inner loop-এর পরে `print()` না রাখলে সব output একই line-এ চলে আসতে পারে।

### Mistake 4: Misunderstanding `break`

Inner loop-এ থাকা `break` স্বয়ংক্রিয়ভাবে outer loop বন্ধ করে না।

### Mistake 5: Incorrect Inner Loop Range

যদি প্রতিটি row-তে row number অনুযায়ী star print করতে চাও, তাহলে `range(row)` বা `range(1, row + 1)` ব্যবহার করা যেতে পারে।

## 13. Practice Exercises

### Exercise 1: Find the Output

```python
for i in range(1, 3):
    for j in range(1, 3):
        print(i + j)
```

### Exercise 2: Count the Iterations

```python
for i in range(1, 5):
    for j in range(1, 4):
        print("*")
```

মোট কতটি star print হবে?

### Exercise 3: Find the Output

```python
for row in range(1, 4):
    for column in range(row):
        print("#", end="")
    print()
```

### Exercise 4: Find the Output

```python
for i in range(1, 3):
    for j in range(1, 4):
        if j == 3:
            break
        print(i, j)
```

### Exercise 5: Write a Program

Nested `for` loop ব্যবহার করে নিচের pattern তৈরি করো:

```text
*
* *
* * *
```

### Exercise 6: Write a Program

দুটি list থেকে সব possible pair print করো:

```python
letters = ["A", "B"]
numbers = [1, 2]
```

## 14. Practice Answer Key

### Answer 1

```text
2
3
3
4
```

কারণ:
- `i = 1`, `j = 1` হলে `1 + 1 = 2`।
- `i = 1`, `j = 2` হলে `1 + 2 = 3`।
- `i = 2`, `j = 1` হলে `2 + 1 = 3`।
- `i = 2`, `j = 2` হলে `2 + 2 = 4`।

### Answer 2

Outer loop চারবার এবং inner loop প্রতিবার তিনবার চলে।

মোট star = \(4 \times 3 = 12\)।

### Answer 3

```text
#
##
###
```

### Answer 4

```text
1 1
1 2
2 1
2 2
```

`j == 3` হলে inner loop বন্ধ হয়। তাই `j = 3`-এর কোনো output নেই।

### Answer 5

```python
for row in range(1, 4):
    for column in range(row):
        print("*", end=" ")
    print()
```

### Answer 6

```python
letters = ["A", "B"]
numbers = [1, 2]

for letter in letters:
    for number in numbers:
        print(letter, number)
```

Output:

```text
A 1
A 2
B 1
B 2
```

## 15. Chapter Summary

- Nested `for` loop একটি `for` loop-এর ভেতরে আরেকটি `for` loop।
- Inner loop প্রতিটি outer iteration-এ সম্পূর্ণ চলে।
- Multiplication table, patterns ও combinations তৈরিতে এটি কাজে লাগে।
- `if` ব্যবহার করে নির্দিষ্ট value নির্বাচন করা যায়।
- `break` নিকটতম loop বন্ধ করে।
- `continue` বর্তমান iteration-এর বাকি অংশ বাদ দেয়।
- `range()`-এর stop value অন্তর্ভুক্ত হয় না।

## 16. Completion Checklist

- [ ] Nested `for` loop লিখতে পারি।
- [ ] Outer ও inner loop-এর execution বুঝি।
- [ ] Dry run করে output বের করতে পারি।
- [ ] Multiplication table তৈরি করতে পারি।
- [ ] Star ও number pattern print করতে পারি।
- [ ] দুটি list-এর সব combination তৈরি করতে পারি।
- [ ] Nested loop-এ `break` ও `continue`-এর কাজ বুঝি।

**Next Topic:** `40_Nested_while_Loops.md`
