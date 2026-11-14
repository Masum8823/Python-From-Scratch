# 46. Controlling Nested Loops

## 1. Introduction

Nested loop হলো একটি loop-এর ভেতরে আরেকটি loop। Python-এ nested loop ব্যবহার করে pattern printing, multiplication table, matrix processing এবং বিভিন্ন problem solve করা যায়।

কখনো কখনো নির্দিষ্ট condition পূরণ হলে loop থামাতে হয়, কোনো iteration বাদ দিতে হয় অথবা outer loop-এর পরবর্তী ধাপে যেতে হয়। এসব কাজের জন্য loop control statements ব্যবহার করা হয়।

প্রধান control statements:

- `break`: যে loop-এর মধ্যে আছে, সেই loop থেকে বের হয়ে যায়।
- `continue`: বর্তমান iteration বাদ দিয়ে একই loop-এর পরবর্তী iteration-এ যায়।
- `pass`: কোনো কাজ করে না; placeholder হিসেবে ব্যবহৃত হয়।

Nested loop-এ এই statement-গুলোর scope বোঝা খুব গুরুত্বপূর্ণ।

## 2. Understanding Control Flow in Nested Loops

প্রথমে একটি সাধারণ nested loop দেখি।

### Code

```python
for row in range(1, 4):
    for column in range(1, 4):
        print(row, column)
```

### Output

```text
1 1
1 2
1 3
2 1
2 2
2 3
3 1
3 2
3 3
```

### Explanation

- Outer loop-এর `row` ১ থেকে ৩ পর্যন্ত চলে।
- প্রতিটি `row`-এর জন্য inner loop-এর `column` আবার ১ থেকে ৩ পর্যন্ত চলে।
- তাই মোট iteration হয় \(3 \times 3 = 9\) বার।

এখন যদি inner loop-এর মধ্যে `break` ব্যবহার করি, তাহলে execution-এর flow পরিবর্তিত হবে।

## 3. Using `break` in an Inner Loop

Inner loop-এর মধ্যে `break` ব্যবহার করলে শুধু inner loop বন্ধ হয়। Outer loop চলতে থাকে।

### Code

```python
for row in range(1, 4):
    for column in range(1, 4):
        if column == 2:
            break

        print(row, column)
```

### Output

```text
1 1
2 1
3 1
```

### Explanation

প্রতিটি row-এর জন্য:

1. Inner loop `column = 1` দিয়ে শুরু হয়।
2. `column = 2` হলে condition সত্য হয়।
3. `break` inner loop বন্ধ করে।
4. Outer loop পরবর্তী row-তে যায়।

**মনে রাখবে:** `break` যে loop-এর ভেতরে লেখা হয়, সেটিকেই বন্ধ করে—সব nested loop একসঙ্গে বন্ধ করে না।

## 4. Using `continue` in an Inner Loop

Inner loop-এর মধ্যে `continue` ব্যবহার করলে শুধু inner loop-এর বর্তমান iteration বাদ যায়।

### Code

```python
for row in range(1, 4):
    for column in range(1, 4):
        if column == 2:
            continue

        print(row, column)
```

### Output

```text
1 1
1 3
2 1
2 3
3 1
3 3
```

### Explanation

- `column == 2` হলে সেই iteration-এ `print()` চালানো হয় না।
- Inner loop-এর `column = 3` iteration চলতে থাকে।
- এরপর outer loop-এর পরবর্তী row শুরু হয়।

এখানে প্রতিটি row থেকে শুধু column ২ বাদ গেছে।

## 5. Using `break` in an Outer Loop

Outer loop-এর body-তে থাকা `break` outer loop বন্ধ করে দেয়।

### Code

```python
for row in range(1, 5):
    if row == 3:
        break

    for column in range(1, 4):
        print(row, column)
```

### Output

```text
1 1
1 2
1 3
2 1
2 2
2 3
```

### Explanation

- Row ১-এর inner loop সম্পূর্ণ চলে।
- Row ২-এর inner loop সম্পূর্ণ চলে।
- `row == 3` হলে outer loop-এর `break` কার্যকর হয়।
- এরপর আর কোনো row process করা হয় না।

**মনে রাখবে:** Outer loop-এ `break` হলে তার ভেতরের inner loop-ও আর নতুন করে execute হয় না।

## 6. Using `continue` in an Outer Loop

Outer loop-এর মধ্যে `continue` ব্যবহার করলে বর্তমান outer iteration-এর বাকি অংশ বাদ যায়। ফলে সেই iteration-এর inner loop execute হয় না।

### Code

```python
for row in range(1, 5):
    if row == 3:
        continue

    for column in range(1, 4):
        print(row, column)
```

### Output

```text
1 1
1 2
1 3
2 1
2 2
2 3
4 1
4 2
4 3
```

### Explanation

- Row ১ ও ২-এর inner loop চলে।
- Row ৩ হলে `continue` outer loop-এর পরবর্তী iteration-এ পাঠায়।
- তাই Row ৩-এর inner loop চলে না।
- এরপর Row ৪-এর inner loop চলে।

## 7. Breaking Out of Multiple Nested Loops

Python-এর সাধারণ `break` statement একবারে একাধিক nested loop বন্ধ করে না। কখনো inner loop থেকে বের হওয়ার পর outer loop-ও বন্ধ করতে হয়।

এ কাজ করার কয়েকটি উপায় আছে।

### Method 1: Using a Flag Variable

Flag variable ব্যবহার করে বোঝানো যায় যে নির্দিষ্ট কাজ পাওয়া গেছে কি না।

### Code

```python
found = False

for row in range(1, 5):
    for column in range(1, 5):
        if row == 2 and column == 3:
            found = True
            break

        print(row, column)

    if found:
        break

print("Target found")
```

### Output

```text
1 1
1 2
1 3
1 4
2 1
2 2
Target found
```

### Explanation

1. Inner loop-এ target condition পাওয়া গেলে `found = True` হয়।
2. Inner loop-এর `break` সেটিকে বন্ধ করে।
3. Outer loop-এর `if found:` condition সত্য হয়।
4. Outer loop-এর `break` সেটিকেও বন্ধ করে।

Target position `(2, 3)` পাওয়ার পর সেটি print করার আগে loop বন্ধ হয়েছে।

### Method 2: Using a Function and `return`

যদি nested loop কোনো function-এর মধ্যে থাকে, তাহলে `return` দিয়ে পুরো function থেকে বের হওয়া যায়।

### Code

```python
def search_target():
    for row in range(1, 5):
        for column in range(1, 5):
            if row == 2 and column == 3:
                print("Target found")
                return

            print(row, column)

search_target()
```

### Output

```text
1 1
1 2
1 3
1 4
2 1
2 2
Target found
```

এখানে `return` পুরো function execution শেষ করে দেয়। তাই আলাদা flag প্রয়োজন হয়নি।

**Note:** `return` কেবল function-এর ভেতরে ব্যবহার করা যায়।

## 8. Using Conditions to Control Nested Loops

অনেক সময় `break` বা `continue` ছাড়াও condition ব্যবহার করে প্রয়োজনীয় iteration নিয়ন্ত্রণ করা যায়।

### Code

```python
for row in range(1, 5):
    for column in range(1, 5):
        if column <= row:
            print("*", end=" ")

    print()
```

### Output

```text
*
* *
* * *
* * * *
```

### Explanation

এখানে `column <= row` সত্য হলেই star print হয়। Condition মিথ্যা হলে `print("*", end=" ")` চালানো হয় না।

এই পদ্ধতিতে inner loop চলতে থাকে, কিন্তু output নিয়ন্ত্রণ করা হয় condition দিয়ে।

## 9. Combining `break` and `continue`

একই nested loop-এ `break` এবং `continue` একসঙ্গে ব্যবহার করা যায়।

### Code

```python
for row in range(1, 4):
    for column in range(1, 6):
        if column == 2:
            continue

        if column == 5:
            break

        print(column, end=" ")

    print()
```

### Output

```text
1 3 4
1 3 4
1 3 4
```

### Explanation

প্রতিটি row-এর inner loop-এ:

- Column ১: print হয়।
- Column ২: `continue` হওয়ায় বাদ যায়।
- Column ৩ ও ৪: print হয়।
- Column ৫: `break` হওয়ায় inner loop বন্ধ হয়।

এ কারণে প্রতিটি row-তে একই output দেখা যায়।

## 10. Using `pass` in Nested Loops

`pass` কোনো iteration বাদ দেয় না বা loop বন্ধ করে না। এটি শুধু কোনো কাজ না করার নির্দেশ দেয়।

### Code

```python
for row in range(1, 4):
    for column in range(1, 4):
        if column == 2:
            pass

        print(row, column)
```

### Output

```text
1 1
1 2
1 3
2 1
2 2
2 3
3 1
3 2
3 3
```

### Explanation

`column == 2` হলেও `pass` কোনো পরিবর্তন আনে না। এরপর `print()` চালু হয়।

তাই:

- `break` loop বন্ধ করে।
- `continue` বর্তমান iteration বাদ দেয়।
- `pass` কোনো কাজ করে না।

## 11. Practical Example: Finding a Number in a Matrix

ধরা যাক, একটি nested list-এর মধ্যে নির্দিষ্ট সংখ্যা খুঁজতে হবে।

### Code

```python
matrix = [
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
]

target = 50
found = False

for row in range(len(matrix)):
    for column in range(len(matrix[row])):
        if matrix[row][column] == target:
            print("Found at:", row, column)
            found = True
            break

    if found:
        break

if not found:
    print("Not found")
```

### Output

```text
Found at: 1 1
```

### Explanation

Python-এ list indexing শূন্য থেকে শুরু হয়। তাই `50` দ্বিতীয় row এবং দ্বিতীয় column-এ থাকলেও তার index হলো `(1, 1)`।

- `matrix[row][column]` দিয়ে প্রতিটি element পরীক্ষা করা হয়।
- Target পাওয়া গেলে `found = True` হয়।
- Inner ও outer loop বন্ধ করা হয়।

এই পদ্ধতি বড় matrix-এ target খোঁজার জন্য কাজে লাগে।

## 12. Dry Run: Inner Loop with `break`

Code:

```python
for row in range(1, 3):
    for column in range(1, 4):
        if column == 3:
            break

        print(row, column)
```

### Dry Run Table

| Row | Column | Condition `column == 3` | Action |
|---:|---:|---|---|
| 1 | 1 | False | `1 1` print |
| 1 | 2 | False | `1 2` print |
| 1 | 3 | True | Inner loop stops |
| 2 | 1 | False | `2 1` print |
| 2 | 2 | False | `2 2` print |
| 2 | 3 | True | Inner loop stops |

### Output

```text
1 1
1 2
2 1
2 2
```

এখানে inner loop প্রতিটি row-তে `column = 3` এ পৌঁছালে বন্ধ হয়, কিন্তু outer loop পরবর্তী row-তে যায়।

## 13. Common Mistakes

### Mistake 1: Thinking `break` Stops Every Loop

`break` শুধু সবচেয়ে ভেতরের সেই loop-টি বন্ধ করে, যার body-তে এটি লেখা আছে।

### Mistake 2: Using `continue` in the Wrong Loop

Inner loop-এ `continue` দিলে শুধু inner loop-এর বর্তমান iteration বাদ যায়। Outer loop-এর বর্তমান iteration বাদ দিতে হলে `continue` outer loop-এর body-তে থাকতে হবে।

### Mistake 3: Forgetting the Flag Check

Flag variable ব্যবহার করে inner loop বন্ধ করার পর outer loop-এ flag পরীক্ষা না করলে outer loop চলতে থাকবে।

### Mistake 4: Confusing `pass` with `continue`

`pass` কোনো iteration বাদ দেয় না। এটি শুধু empty statement হিসেবে কাজ করে।

### Mistake 5: Incorrect Indentation

`break` বা `continue`-এর indentation নির্ধারণ করে কোন loop-কে control করা হচ্ছে।

### Mistake 6: Printing After `break`

যদি `break` আগে execute হয়, তাহলে তার পরে থাকা statement ওই iteration-এ execute হবে না।

## 14. Practice Exercises

### Exercise 1: Inner Loop Break

নিচের code-এর output বের করো।

```python
for row in range(1, 4):
    for column in range(1, 5):
        if column == 3:
            break
        print(column, end=" ")
    print()
```

### Exercise 2: Inner Loop Continue

নিচের code-এর output বের করো।

```python
for row in range(1, 4):
    for column in range(1, 5):
        if column == 2:
            continue
        print(column, end=" ")
    print()
```

### Exercise 3: Outer Loop Continue

শুধু row ২ বাদ দিয়ে বাকি row-গুলোর ১ থেকে ৩ পর্যন্ত column print করো।

### Exercise 4: Stop at a Target

Nested loop ব্যবহার করে `(2, 2)` position-এ পৌঁছালে inner ও outer loop—দুটিই বন্ধ করো।

### Exercise 5: Explain the Difference

`break`, `continue` এবং `pass`-এর মধ্যে পার্থক্য লেখো।

### Exercise 6: Find the Output

```python
for row in range(1, 4):
    for column in range(1, 4):
        if row == 2:
            break
        print(row, column)
```

## 15. Practice Answer Key

### Answer 1

```text
1 2
1 2
1 2
```

Column ৩ হলে প্রতিবার inner loop বন্ধ হয়।

### Answer 2

```text
1 3 4
1 3 4
1 3 4
```

Column ২ বাদ যায়, কিন্তু inner loop চলতে থাকে।

### Answer 3

```python
for row in range(1, 4):
    if row == 2:
        continue

    for column in range(1, 4):
        print(row, column)
```

Output:

```text
1 1
1 2
1 3
3 1
3 2
3 3
```

### Answer 4

```python
found = False

for row in range(1, 4):
    for column in range(1, 4):
        if row == 2 and column == 2:
            found = True
            break

    if found:
        break
```

### Answer 5

| Statement | কাজ |
|---|---|
| `break` | যে loop-এর মধ্যে আছে, সেটি বন্ধ করে |
| `continue` | বর্তমান iteration বাদ দেয় |
| `pass` | কোনো কাজ করে না |

### Answer 6

```text
1 1
1 2
1 3
```

Row ১-এর inner loop সম্পূর্ণ চলে। Row ২ হলে outer loop-এর ভেতরে থাকা `break` outer loop বন্ধ করে দেয়, তাই Row ৩ execute হয় না।

## 16. Chapter Summary

- Nested loop-এর প্রতিটি loop-এর নিজস্ব execution flow থাকে।
- Inner loop-এর `break` শুধু inner loop বন্ধ করে।
- Outer loop-এর `break` outer loop বন্ধ করে।
- Inner loop-এর `continue` inner loop-এর বর্তমান iteration বাদ দেয়।
- Outer loop-এর `continue` বর্তমান outer iteration-এর বাকি অংশ বাদ দেয়।
- একাধিক loop বন্ধ করতে flag variable অথবা function-এর ভেতরে `return` ব্যবহার করা যায়।
- `pass` কোনো iteration বাদ দেয় না বা loop বন্ধ করে না।
- Condition ব্যবহার করেও nested loop-এর output নিয়ন্ত্রণ করা যায়।

## 17. Completion Checklist

- [ ] Nested loop-এর execution flow বুঝি।
- [ ] Inner loop-এ `break` ব্যবহার করতে পারি।
- [ ] Inner loop-এ `continue` ব্যবহার করতে পারি।
- [ ] Outer loop-এ `break` ও `continue` ব্যবহার করতে পারি।
- [ ] Flag variable দিয়ে একাধিক loop বন্ধ করতে পারি।
- [ ] `break`, `continue` ও `pass`-এর পার্থক্য বুঝি।
- [ ] Nested loop-এর dry run করতে পারি।

**Next Topic:** `47_Common_Nested_Loop_Mistakes.md`