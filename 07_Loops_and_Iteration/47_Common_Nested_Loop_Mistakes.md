# 47. Common Nested Loop Mistakes

## 1. Introduction

Nested loop হলো একটি loop-এর ভেতরে আরেকটি loop। এটি star pattern, number pattern, multiplication table এবং matrix-এর মতো problem solve করতে কাজে লাগে।

তবে nested loop লেখার সময় কিছু সাধারণ ভুল হয়:

- ভুল indentation
- ভুল `range()` ব্যবহার
- Inner ও outer loop-এর variable গুলিয়ে ফেলা
- ভুল জায়গায় `break` বা `continue` লেখা
- `while` loop-এর variable update করতে ভুলে যাওয়া
- ভুলভাবে `print()` ব্যবহার করা
- প্রয়োজনের চেয়ে বেশি বা কম iteration চালানো

এই ভুলগুলো বুঝতে পারলে nested loop-এর code লেখা এবং debugging করা সহজ হবে।

## 2. Mistake 1: Incorrect Indentation

Python-এ indentation দিয়ে বোঝানো হয় কোন statement কোন loop বা condition-এর অন্তর্ভুক্ত।

### Incorrect Code

```python
for row in range(1, 4):
    for column in range(1, 4):
    print(row, column)
```

এখানে `print()`-এর indentation ভুল। এটি inner loop-এর body-তে সঠিকভাবে রাখা হয়নি।

এই code চালালে `IndentationError` হবে।

### Correct Code

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

**মনে রাখবে:** সাধারণত Python-এ প্রতিটি nested block-এর জন্য চারটি space ব্যবহার করা হয়।

## 3. Mistake 2: Using the Wrong `range()`

`range()`-এর stop value অন্তর্ভুক্ত হয় না। এই নিয়ম ভুলে গেলে iteration-এর সংখ্যা ভুল হতে পারে।

### Incorrect Code

```python
for row in range(1, 5):
    for column in range(1, row):
        print("*", end=" ")
    print()
```

### Output

```text
*
* *
* * *
*
```

শেষ row-তে `row = 4` হলে তিনটি star print হয়। কিন্তু `range(1, row)`-এর stop value বাদ যায় বলে প্রথম row-তে কোনো star print হয় না।

### Correct Code

```python
for row in range(1, 5):
    for column in range(1, row + 1):
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

**মনে রাখবে:** `row` সংখ্যক item চাইলে অনেক ক্ষেত্রে `range(1, row + 1)` ব্যবহার করতে হয়।

## 4. Mistake 3: Confusing Outer and Inner Loop Variables

Outer ও inner loop-এর variable আলাদা কাজে ব্যবহৃত হয়। তাদের গুলিয়ে ফেললে output ভুল হতে পারে।

### Incorrect Logic

```python
for row in range(1, 5):
    for column in range(1, 5):
        print(column, end=" ")
    print()
```

### Output

```text
1 2 3 4
1 2 3 4
1 2 3 4
1 2 3 4
```

এটি ভুল code নয়। তবে যদি উদ্দেশ্য হয় প্রতিটি row-তে row number বারবার print করা, তাহলে logic ভুল।

### Correct Code

```python
for row in range(1, 5):
    for column in range(row):
        print(row, end=" ")
    print()
```

### Output

```text
1
2 2
3 3 3
4 4 4 4
```

এখানে `row` নির্ধারণ করে কোন সংখ্যা print হবে এবং `column` নির্ধারণ করে কতবার print হবে।

## 5. Mistake 4: Forgetting to Update a `while` Loop Variable

Nested `while` loop-এ variable update না করলে infinite loop হতে পারে।

### Incorrect Code

```python
row = 1

while row <= 3:
    column = 1

    while column <= 3:
        print(row, column)
        # column update করা হয়নি

    row += 1
```

এই code-এ `column` সবসময় ১ থাকে। তাই `column <= 3` condition সবসময় সত্য হয় এবং inner loop চলতেই থাকে।

### Correct Code

```python
row = 1

while row <= 3:
    column = 1

    while column <= 3:
        print(row, column)
        column += 1

    row += 1
```

### Explanation

- `column += 1` inner loop-কে এগিয়ে নেয়।
- `row += 1` outer loop-কে এগিয়ে নেয়।
- দুইটি variable-ই update হওয়ায় loop শেষ হয়।

**গুরুত্বপূর্ণ:** `while` loop-এ condition-এর সঙ্গে সম্পর্কিত variable সঠিকভাবে update হচ্ছে কি না, সবসময় পরীক্ষা করবে।

## 6. Mistake 5: Not Resetting the Inner Loop Variable

Nested `while` loop-এ প্রতিটি নতুন row-এর জন্য inner loop-এর variable সাধারণত আবার initialize করতে হয়।

### Incorrect Code

```python
row = 1
column = 1

while row <= 3:
    while column <= 3:
        print(row, column)
        column += 1

    row += 1
```

### Output

```text
1 1
1 2
1 3
```

প্রথম row-এর পর `column`-এর মান ৪ হয়ে যায়। এরপর পরবর্তী row-তে inner loop আর চলে না।

### Correct Code

```python
row = 1

while row <= 3:
    column = 1

    while column <= 3:
        print(row, column)
        column += 1

    row += 1
```

এখানে প্রতিবার outer loop শুরু হলে `column = 1` করা হয়। ফলে প্রতিটি row-তে inner loop তিনবার চলে।

## 7. Mistake 6: Incorrect Placement of `print()`

Nested pattern-এ `print()` কোথায় রাখা হয়েছে, তার ওপর output নির্ভর করে।

### Incorrect Code

```python
for row in range(1, 4):
    for column in range(1, 4):
        print("*", end=" ")
        print()
```

### Output

```text
*
*
*
*
*
*
*
*
*
```

এখানে `print()` inner loop-এর ভেতরে আছে। তাই প্রতিটি star-এর পরে নতুন line তৈরি হচ্ছে।

### Correct Code

```python
for row in range(1, 4):
    for column in range(1, 4):
        print("*", end=" ")
    print()
```

### Output

```text
* * *
* * *
* * *
```

**মনে রাখবে:** প্রতিটি row শেষ হওয়ার পরে নতুন line চাইলে `print()`-কে inner loop-এর বাইরে কিন্তু outer loop-এর ভেতরে রাখবে।

## 8. Mistake 7: Misunderstanding `break`

`break` শুধু সেই loop বন্ধ করে, যার body-তে statement-টি আছে।

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

প্রতিটি row-তে `column == 2` হলে inner loop বন্ধ হয়। কিন্তু outer loop পরবর্তী row-তে চলে যায়।

যদি উদ্দেশ্য হয় inner এবং outer—দুই loop-ই বন্ধ করা, তাহলে flag variable বা function-এর ভেতরে `return` ব্যবহার করা যেতে পারে।

## 9. Mistake 8: Misunderstanding `continue`

`continue` বর্তমান iteration-এর বাকি অংশ বাদ দিয়ে একই loop-এর পরবর্তী iteration-এ যায়।

### Code

```python
for row in range(1, 3):
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
```

### Explanation

শুধু `column == 2`-এর iteration বাদ যায়। Column ৩-এর iteration ঠিকই চলে।

যদি `continue`-কে outer loop-এর body-তে রাখা হয়, তাহলে তার প্রভাব হবে ভিন্ন—সেই row-এর বাকি অংশ বাদ যাবে।

## 10. Mistake 9: Incorrect Condition in a Nested Loop

Condition ভুল হলে প্রয়োজনীয় value print নাও হতে পারে।

### Incorrect Code

```python
for row in range(1, 5):
    for column in range(1, 5):
        if column < row:
            print("*", end=" ")
    print()
```

### Output

```text


*
* *
* * *
```

এখানে `column < row` শর্তের কারণে `column` ও `row` সমান হলে star print হয় না। প্রথম row-তে কোনো star-ই print হয় না।

### Correct Code

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

এখানে `column <= row` ব্যবহার করায় row-এর শেষ position-টিও অন্তর্ভুক্ত হয়েছে।

## 11. Mistake 10: Using the Wrong Update Direction

`while` loop-এ variable ভুল দিকে update করলে condition কখনো false নাও হতে পারে।

### Incorrect Code

```python
row = 5

while row >= 1:
    print(row)
    row += 1
```

এখানে `row` ক্রমাগত বাড়ছে। তাই `row >= 1` condition সবসময় সত্য থাকবে।

### Correct Code

```python
row = 5

while row >= 1:
    print(row)
    row -= 1
```

### Output

```text
5
4
3
2
1
```

**মনে রাখবে:** Countdown loop-এ সাধারণত decrement করতে হয়; count-up loop-এ increment করতে হয়।

## 12. Mistake 11: Using Too Many or Too Few Iterations

Nested loop-এর মোট iteration নির্ভর করে outer ও inner loop-এর iteration সংখ্যার ওপর।

### Example

```python
for row in range(1, 4):
    for column in range(1, 5):
        print("*", end=" ")
    print()
```

এখানে outer loop ৩ বার এবং inner loop প্রতিটি row-তে ৪ বার চলে।

মোট star:

\[
3 \times 4 = 12
\]

যদি ভুল করে `range(1, 4)` inner loop-এ ব্যবহার করা হয়, তাহলে প্রতিটি row-তে ৩টি star print হবে। তাই expected output-এর সঙ্গে `range()` মিলিয়ে দেখতে হবে।

## 13. Mistake 12: Forgetting That Inner Loop Runs Again

প্রতিবার outer loop-এর নতুন iteration শুরু হলে inner loop আবার শুরু হয়।

### Code

```python
for row in range(1, 4):
    for column in range(1, 3):
        print(column, end=" ")
    print()
```

### Output

```text
1 2
1 2
1 2
```

এখানে inner loop-এর `column` আবার ১ থেকে শুরু হয়। এটি কোনো ভুল নয়; nested loop-এর স্বাভাবিক আচরণ।

কিন্তু যদি ধারাবাহিকভাবে সংখ্যা print করতে চাও, তাহলে counter-কে outer loop-এর বাইরে রাখতে হবে।

```python
number = 1

for row in range(1, 4):
    for column in range(1, 3):
        print(number, end=" ")
        number += 1
    print()
```

Output:

```text
1 2
3 4
5 6
```

## 14. Debugging Nested Loops Step by Step

Nested loop-এর ভুল খুঁজে বের করার জন্য নিচের ধাপগুলো অনুসরণ করো।

1. **Outer loop পরীক্ষা করো:** কতটি row বা group তৈরি হবে?
2. **Inner loop পরীক্ষা করো:** প্রতিটি row-তে কতটি iteration হবে?
3. **`range()` পরীক্ষা করো:** start, stop এবং step সঠিক কি না?
4. **Indentation পরীক্ষা করো:** কোন statement কোন loop-এর অংশ?
5. **Variable update পরীক্ষা করো:** `while` loop-এ variable পরিবর্তিত হচ্ছে কি না?
6. **Condition পরীক্ষা করো:** `if`, `break` ও `continue` সঠিক জায়গায় আছে কি না?
7. **Dry run করো:** প্রথম কয়েকটি iteration হাতে হিসাব করো।
8. **Output মিলিয়ে দেখো:** expected ও actual output তুলনা করো।

## 15. Dry Run Example

Code:

```python
for row in range(1, 4):
    for column in range(1, 4):
        if row == column:
            print("X", end=" ")
        else:
            print("O", end=" ")
    print()
```

### Dry Run Table

| Row | Column | Condition `row == column` | Output |
|---:|---:|---|---|
| 1 | 1 | True | X |
| 1 | 2 | False | O |
| 1 | 3 | False | O |
| 2 | 1 | False | O |
| 2 | 2 | True | X |
| 2 | 3 | False | O |
| 3 | 1 | False | O |
| 3 | 2 | False | O |
| 3 | 3 | True | X |

### Output

```text
X O O
O X O
O O X
```

এখানে `row` ও `column` সমান হলে `X`, অন্যথায় `O` print হয়।

## 16. Common Mistakes Summary

| Mistake | Problem | Solution |
|---|---|---|
| Incorrect indentation | `IndentationError` বা ভুল flow | প্রতিটি block-এর indentation ঠিক করা |
| Wrong `range()` | কম বা বেশি iteration | start, stop ও step যাচাই |
| Inner variable reset না করা | পরবর্তী row-তে inner loop না চলা | প্রয়োজনমতো variable আবার initialize করা |
| `while` variable update না করা | Infinite loop | condition-এর variable update করা |
| `print()` ভুল জায়গায় রাখা | Output-এর line break ভুল হওয়া | `print()`-এর indentation ঠিক করা |
| `break` ভুল বোঝা | ভুল loop বন্ধ হওয়া | `break` কোন loop-এর body-তে আছে দেখা |
| `continue` ভুল বোঝা | ভুল iteration বাদ যাওয়া | statement-এর scope পরীক্ষা |
| ভুল condition | ভুল output | condition হাতে পরীক্ষা করা |

## 17. Practice Exercises

### Exercise 1: Find the Error

```python
for row in range(1, 4):
    for column in range(1, 4):
    print(row, column)
```

কী ভুল আছে? কীভাবে ঠিক করবে?

### Exercise 2: Predict the Output

```python
for row in range(1, 4):
    for column in range(1, row + 1):
        print(column, end=" ")
    print()
```

### Exercise 3: Fix the Infinite Loop

```python
row = 1

while row <= 3:
    column = 1

    while column <= 3:
        print("*", end=" ")
    print()
    row += 1
```

### Exercise 4: Fix the Pattern

Expected output:

```text
*
* *
* * *
* * * *
```

Code:

```python
for row in range(1, 5):
    for column in range(1, row):
        print("*", end=" ")
    print()
```

### Exercise 5: Predict the Output

```python
for row in range(1, 4):
    for column in range(1, 4):
        if column == 2:
            continue
        print(row, column)
```

### Exercise 6: Count the Iterations

```python
for row in range(1, 5):
    for column in range(1, 6):
        print("*", end=" ")
    print()
```

মোট কতটি star print হবে?

## 18. Practice Answer Key

### Answer 1

`print()`-এর indentation ভুল।

Correct code:

```python
for row in range(1, 4):
    for column in range(1, 4):
        print(row, column)
```

### Answer 2

```text
1
1 2
1 2 3
```

### Answer 3

Inner loop-এর ভেতরে `column += 1` যোগ করতে হবে।

```python
row = 1

while row <= 3:
    column = 1

    while column <= 3:
        print("*", end=" ")
        column += 1

    print()
    row += 1
```

### Answer 4

`range(1, row)` পরিবর্তন করে `range(1, row + 1)` করতে হবে।

```python
for row in range(1, 5):
    for column in range(1, row + 1):
        print("*", end=" ")
    print()
```

### Answer 5

```text
1 1
1 3
2 1
2 3
3 1
3 3
```

Column ২-এর iteration বাদ যায়।

### Answer 6

Outer loop ৪ বার এবং inner loop প্রতিবার ৫ বার চলে।

\[
4 \times 5 = 20
\]

মোট ২০টি star print হবে।

## 19. Chapter Summary

- Nested loop-এর সবচেয়ে সাধারণ সমস্যা হলো indentation, ভুল range এবং variable update-এর ভুল।
- Outer ও inner loop-এর variable আলাদা কাজ করে।
- `while` loop-এর condition-এর variable সঠিকভাবে update করতে হয়।
- Inner loop-এর variable অনেক সময় প্রতিটি outer iteration-এ আবার initialize করতে হয়।
- `break` ও `continue`-এর প্রভাব নির্ভর করে এগুলো কোন loop-এর মধ্যে আছে তার ওপর।
- `print()`-এর indentation output-এর shape পরিবর্তন করতে পারে।
- Dry run এবং expected output-এর সঙ্গে তুলনা করে debugging সহজ হয়।

## 20. Completion Checklist

- [ ] Nested loop-এর indentation ঠিক রাখতে পারি।
- [ ] `range()`-এর start, stop ও step বুঝি।
- [ ] Inner loop-এর variable reset করার প্রয়োজন বুঝি।
- [ ] Infinite loop-এর কারণ খুঁজে বের করতে পারি।
- [ ] `break` ও `continue`-এর scope বুঝি।
- [ ] Output দেখে nested loop debug করতে পারি।
- [ ] Dry run করে iteration ও output যাচাই করতে পারি।

**Next Topic:** `48_Counting_and_Accumulation.md`
