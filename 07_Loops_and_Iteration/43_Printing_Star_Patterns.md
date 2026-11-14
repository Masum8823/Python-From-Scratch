# 43. Printing Star Patterns

## 1. Introduction

Star pattern হলো `*` চিহ্ন ব্যবহার করে নির্দিষ্ট আকৃতি তৈরি করা। Python-এ loop ব্যবহার করে সহজেই বিভিন্ন star pattern print করা যায়।

উদাহরণ:

```text
*
* *
* * *
* * * *
* * * * *
```

এই ধরনের pattern তৈরির জন্য সাধারণত **nested `for` loop** ব্যবহার করা হয়।

- Outer loop নির্ধারণ করে কতটি row হবে।
- Inner loop নির্ধারণ করে প্রতিটি row-তে কতটি star print হবে।

## 2. Understanding Rows and Columns

Pattern তৈরির আগে row এবং column বুঝতে হবে।

- **Row:** পাশাপাশি থাকা star-এর একটি লাইন।
- **Column:** একটি row-তে থাকা প্রতিটি অবস্থান।

উদাহরণ:

```text
* * *
* * *
```

এখানে ২টি row এবং প্রতিটি row-তে ৩টি star আছে।

তাই মোট star:

\[
2 \times 3 = 6
\]

## 3. Printing a Square Pattern

প্রথমে ৪ row ও ৪ column-এর একটি square তৈরি করি।

### Code

```python
for row in range(4):
    for column in range(4):
        print("*", end=" ")
    print()
```

### Output

```text
* * * *
* * * *
* * * *
* * * *
```

### Explanation

- Outer loop চারবার চলে।
- Inner loop প্রতিটি row-তে চারটি star print করে।
- `end=" "` star-গুলোকে একই লাইনে রাখে।
- Inner loop শেষ হলে `print()` পরবর্তী লাইনে যায়।

মোট star:

\[
4 \times 4 = 16
\]

## 4. Printing a Rectangle Pattern

Rectangle-এ row এবং column-এর সংখ্যা আলাদা হতে পারে।

### Code

```python
for row in range(3):
    for column in range(5):
        print("*", end=" ")
    print()
```

### Output

```text
* * * * *
* * * * *
* * * * *
```

এখানে ৩টি row এবং ৫টি column আছে।

মোট star:

\[
3 \times 5 = 15
\]

**মনে রাখবে:** Outer loop-এর range দিয়ে row এবং inner loop-এর range দিয়ে column নিয়ন্ত্রণ করা হচ্ছে।

## 5. Printing a Right-Angled Triangle

এবার এমন triangle তৈরি করব, যেখানে প্রতিটি নতুন row-তে একটি করে star বাড়বে।

### Code

```python
for row in range(1, 6):
    for column in range(row):
        print("*", end=" ")
    print()
```

### Output

```text
*
* *
* * *
* * * *
* * * * *
```

### Explanation

এখানে inner loop-এর `range(row)` outer loop-এর বর্তমান `row` value-এর ওপর নির্ভর করে।

- Row 1: ১টি star
- Row 2: ২টি star
- Row 3: ৩টি star
- Row 4: ৪টি star
- Row 5: ৫টি star

মোট star:

\[
1+2+3+4+5=15
\]

## 6. Dry Run of a Triangle Pattern

Code:

```python
for row in range(1, 4):
    for column in range(row):
        print("*", end=" ")
    print()
```

### Dry Run Table

| Outer `row` | Inner loop iterations | Stars printed |
|---:|---:|---|
| 1 | 1 | `*` |
| 2 | 2 | `* *` |
| 3 | 3 | `* * *` |

### Output

```text
*
* *
* * *
```

এখানে সবচেয়ে গুরুত্বপূর্ণ বিষয় হলো, inner loop-এর iteration সংখ্যা প্রতিবার পরিবর্তিত হচ্ছে।

## 7. Printing an Inverted Right-Angled Triangle

আগের triangle-এ star-এর সংখ্যা বাড়ছিল। এবার star-এর সংখ্যা কমাব।

### Code

```python
for row in range(5, 0, -1):
    for column in range(row):
        print("*", end=" ")
    print()
```

### Output

```text
* * * * *
* * * *
* * *
* *
*
```

### Explanation

`range(5, 0, -1)` দিয়ে `row`-এর মান ৫ থেকে ১ পর্যন্ত কমে।

প্রতিটি row-তে star-এর সংখ্যা `row`-এর সমান।

## 8. Printing a Left-Aligned Triangle with a Fixed Height

একই pattern অন্যভাবেও তৈরি করা যায়।

```python
height = 5

for row in range(1, height + 1):
    print("* " * row)
```

### Output

```text
*
* * 
* * * 
* * * * 
* * * * * 
```

এখানে string repetition ব্যবহার করা হয়েছে।

- `"* " * 1` → একটি star
- `"* " * 2` → দুটি star
- `"* " * 3` → তিনটি star

এই উদাহরণে প্রতিটি row-তে star-এর সংখ্যা বাড়ানোর কাজটি string repetition করছে। তাই এখানে nested loop প্রয়োজন হয়নি।

## 9. Printing a Right-Aligned Triangle

এই pattern-এ star ডানদিকে থাকবে এবং শুরুতে space থাকবে।

### Code

```python
height = 5

for row in range(1, height + 1):
    for space in range(height - row):
        print(" ", end=" ")

    for star in range(row):
        print("*", end=" ")

    print()
```

### Output

```text
        *
      * *
    * * *
  * * * *
* * * * *
```

### Explanation

এখানে দুটি inner loop আছে।

1. প্রথম inner loop প্রয়োজনীয় leading spaces print করে।
2. দ্বিতীয় inner loop star print করে।
3. `height - row` প্রতিটি row-তে space-এর সংখ্যা কমায়।

Row বাড়ার সঙ্গে সঙ্গে space কমে এবং star বাড়ে।

## 10. Printing a Pyramid Pattern

Pyramid pattern তৈরিতে spaces ও stars—দুটিই নিয়ন্ত্রণ করতে হয়।

### Code

```python
height = 5

for row in range(1, height + 1):
    for space in range(height - row):
        print(" ", end="")

    for star in range(2 * row - 1):
        print("*", end="")

    print()
```

### Output

```text
    *
   ***
  *****
 *******
*********
```

### Explanation

প্রতিটি row-এর জন্য:

- Spaces = `height - row`
- Stars = `2 * row - 1`

তাই star-এর সংখ্যা হয় ১, ৩, ৫, ৭ ও ৯।

**গুরুত্বপূর্ণ:** এখানে `print(" ", end="")` একটি space print করে এবং একই লাইনে থাকে। Space-এর সংখ্যা অনুযায়ী pyramid-এর alignment তৈরি হয়।

## 11. Printing an Inverted Pyramid

এবার বড় pyramid থেকে ছোট pyramid তৈরি করব।

### Code

```python
height = 5

for row in range(height, 0, -1):
    for space in range(height - row):
        print(" ", end="")

    for star in range(2 * row - 1):
        print("*", end="")

    print()
```

### Output

```text
*********
 *******
  *****
   ***
    *
```

### Explanation

- Outer loop `row`-এর মান ৫ থেকে ১ পর্যন্ত কমায়।
- Row ছোট হওয়ার সঙ্গে সঙ্গে star-এর সংখ্যা কমে।
- Leading spaces-এর সংখ্যা বাড়ে।

## 12. Printing a Hollow Square

Hollow square-এ শুধু border-এর star print হবে; মাঝখানের অংশ ফাঁকা থাকবে।

### Code

```python
size = 5

for row in range(size):
    for column in range(size):
        if row == 0 or row == size - 1 or column == 0 or column == size - 1:
            print("*", end=" ")
        else:
            print(" ", end=" ")
    print()
```

### Output

```text
* * * * *
*       *
*       *
*       *
* * * * *
```

### Explanation

একটি position border-এর অংশ হবে যদি:

- প্রথম row হয়, অথবা
- শেষ row হয়, অথবা
- প্রথম column হয়, অথবা
- শেষ column হয়।

এই শর্তগুলোর যেকোনো একটি সত্য হলে star print হয়। অন্যথায় space print হয়।

## 13. Printing a Hollow Right-Angled Triangle

এই pattern-এ triangle-এর border-এ star থাকবে।

### Code

```python
height = 5

for row in range(1, height + 1):
    for column in range(1, row + 1):
        if column == 1 or column == row or row == height:
            print("*", end=" ")
        else:
            print(" ", end=" ")
    print()
```

### Output

```text
*
* *
*   *
*     *
* * * * *
```

### Explanation

Star print হবে যখন:

- `column == 1`: প্রথম column
- `column == row`: row-এর শেষ column
- `row == height`: শেষ row

এ কারণে triangle-এর দুই পাশ এবং নিচের border-এ star থাকে।

## 14. Printing a Diamond Pattern

Diamond pattern-এ প্রথমে pyramid এবং পরে inverted pyramid তৈরি করা হয়।

### Code

```python
height = 4

for row in range(1, height + 1):
    for space in range(height - row):
        print(" ", end="")

    for star in range(2 * row - 1):
        print("*", end="")

    print()

for row in range(height - 1, 0, -1):
    for space in range(height - row):
        print(" ", end="")

    for star in range(2 * row - 1):
        print("*", end="")

    print()
```

### Output

```text
   *
  ***
 *****
*******
 *****
  ***
   *
```

### Explanation

- প্রথম outer loop pyramid তৈরি করে।
- দ্বিতীয় outer loop inverted pyramid তৈরি করে।
- দ্বিতীয় loop `height - 1` থেকে শুরু হয়, তাই মাঝের সবচেয়ে বড় row দ্বিতীয়বার print হয় না।

## 15. Understanding `print()` and `end`

Star pattern তৈরিতে `end` খুব গুরুত্বপূর্ণ।

### Example 1

```python
print("*")
print("*")
print("*")
```

Output:

```text
*
*
*
```

প্রতিটি `print()`-এর পরে স্বাভাবিকভাবে newline হয়।

### Example 2

```python
print("*", end=" ")
print("*", end=" ")
print("*")
```

Output:

```text
* * *
```

প্রথম দুটি `print()` newline তৈরি করে না। শেষের `print()` করে।

**মনে রাখবে:** Inner loop-এ সাধারণত `end=" "` বা `end=""` ব্যবহার করা হয়, আর inner loop শেষ হলে `print()` দিয়ে পরবর্তী row-তে যাওয়া হয়।

## 16. Common Mistakes

### Mistake 1: Forgetting the Final `print()`

Inner loop-এর পরে `print()` না থাকলে সব row একই লাইনে চলে আসতে পারে।

### Mistake 2: Using the Wrong Range

`range(1, 5)` পাঁচটি নয়, চারটি value দেয়: ১, ২, ৩, ৪।

### Mistake 3: Incorrect Indentation

Inner loop-এর বাইরে থাকা `print()` প্রতিটি row শেষে newline তৈরি করে। এটি ভুল indentation-এ থাকলে pattern নষ্ট হতে পারে।

### Mistake 4: Printing Spaces Incorrectly

Pyramid-এর জন্য leading spaces সঠিকভাবে নিয়ন্ত্রণ করতে হয়। Space বেশি বা কম হলে pattern মাঝখানে aligned দেখাবে না।

### Mistake 5: Forgetting the Border Condition

Hollow pattern তৈরির সময় border-এর শর্তগুলো সঠিকভাবে লিখতে হবে। যেমন, square-এর জন্য প্রথম/শেষ row অথবা প্রথম/শেষ column পরীক্ষা করতে হয়।

### Mistake 6: Using the Wrong Star Formula

Pyramid-এর star সংখ্যা সাধারণত `2 * row - 1`। শুধু `row` ব্যবহার করলে সেটি pyramid হবে না; triangle-এর মতো দেখাবে।

## 17. Practice Exercises

### Exercise 1: Square Pattern

৫ row ও ৫ column-এর একটি solid square print করো।

### Exercise 2: Right-Angled Triangle

নিচের pattern তৈরি করো:

```text
*
* *
* * *
* * * *
```

### Exercise 3: Inverted Triangle

নিচের pattern তৈরি করো:

```text
* * * *
* * *
* *
*
```

### Exercise 4: Right-Aligned Triangle

নিচের pattern তৈরি করো:

```text
      *
    * *
  * * *
* * * *
```

### Exercise 5: Pyramid

নিচের pattern তৈরি করো:

```text
   *
  ***
 *****
*******
```

### Exercise 6: Hollow Square

৫ × ৫ hollow square তৈরি করো।

### Exercise 7: Find the Output

```python
for row in range(1, 4):
    for column in range(row):
        print("*", end="")
    print()
```

### Exercise 8: Count the Stars

```python
for row in range(1, 6):
    for column in range(row):
        print("*", end="")
    print()
```

মোট কতটি star print হবে?

## 18. Practice Answer Key

### Answer 1

```python
for row in range(5):
    for column in range(5):
        print("*", end=" ")
    print()
```

### Answer 2

```python
for row in range(1, 5):
    for column in range(row):
        print("*", end=" ")
    print()
```

### Answer 3

```python
for row in range(4, 0, -1):
    for column in range(row):
        print("*", end=" ")
    print()
```

### Answer 4

```python
height = 4

for row in range(1, height + 1):
    for space in range(height - row):
        print(" ", end=" ")

    for star in range(row):
        print("*", end=" ")

    print()
```

### Answer 5

```python
height = 4

for row in range(1, height + 1):
    for space in range(height - row):
        print(" ", end="")

    for star in range(2 * row - 1):
        print("*", end="")

    print()
```

### Answer 6

```python
size = 5

for row in range(size):
    for column in range(size):
        if row == 0 or row == size - 1 or column == 0 or column == size - 1:
            print("*", end=" ")
        else:
            print(" ", end=" ")
    print()
```

### Answer 7

```text
*
**
***
```

প্রথম row-তে একটি, দ্বিতীয় row-তে দুটি এবং তৃতীয় row-তে তিনটি star print হয়।

### Answer 8

মোট star:

\[
1+2+3+4+5=15
\]

সুতরাং মোট ১৫টি star print হবে।

## 19. Chapter Summary

- Star pattern তৈরিতে nested loop খুব কার্যকর।
- Outer loop row-এর সংখ্যা নিয়ন্ত্রণ করে।
- Inner loop প্রতিটি row-এর content নিয়ন্ত্রণ করে।
- `end=" "` একই লাইনে একাধিক star print করতে সাহায্য করে।
- Triangle-এ প্রতিটি row-তে star বাড়ে বা কমে।
- Pyramid তৈরিতে spaces ও stars দুটোই নিয়ন্ত্রণ করতে হয়।
- Hollow pattern-এ condition ব্যবহার করে border print করা হয়।
- Diamond তৈরিতে pyramid ও inverted pyramid একসঙ্গে ব্যবহার করা যায়।

## 20. Completion Checklist

- [ ] Solid square ও rectangle তৈরি করতে পারি।
- [ ] Right-angled triangle তৈরি করতে পারি।
- [ ] Inverted triangle তৈরি করতে পারি।
- [ ] Right-aligned triangle ও pyramid তৈরি করতে পারি।
- [ ] Hollow square তৈরি করতে পারি।
- [ ] Diamond pattern তৈরি করতে পারি।
- [ ] `print()` ও `end`-এর ব্যবহার বুঝি।
- [ ] Nested loop-এর dry run করতে পারি।

**Next Topic:** `44_Printing_Number_Patterns.md`
