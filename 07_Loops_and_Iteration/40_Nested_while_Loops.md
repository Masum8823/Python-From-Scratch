# 40. Nested `while` Loops

## 1. Introduction

Python-এ একটি `while` loop-এর ভেতরে আরেকটি `while` loop ব্যবহার করলে তাকে **Nested `while` Loop** বলে।

`while` loop কোনো condition সত্য থাকা পর্যন্ত চলে। Nested `while` loop-এ বাইরের loop-এর প্রতিটি iteration-এর জন্য ভেতরের loop তার condition অনুযায়ী চলে।

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

এখানে:

- `i` বাইরের loop নিয়ন্ত্রণ করে।
- `j` ভেতরের loop নিয়ন্ত্রণ করে।
- প্রতিটি outer iteration-এ inner loop দুইবার চলে।

## 2. Syntax of Nested `while` Loops

```python
outer_variable = initial_value

while outer_condition:
    inner_variable = initial_value

    while inner_condition:
        statement
        update_inner_variable

    update_outer_variable
```

এই structure-এ:

1. Outer variable initialize করা হয়।
2. Outer condition পরীক্ষা করা হয়।
3. Outer condition সত্য হলে inner variable initialize করা হয়।
4. Inner loop condition সত্য থাকা পর্যন্ত চলে।
5. Inner loop শেষ হলে outer variable update হয়।
6. Outer condition আবার পরীক্ষা করা হয়।

**মনে রাখবে:** Inner variable-এর initialization সাধারণত outer loop-এর ভেতরে রাখতে হয়, যাতে প্রতিটি নতুন outer iteration-এ inner loop আবার শুরু থেকে চলতে পারে।

## 3. Understanding the Outer and Inner Loops

### Example

```python
i = 1

while i <= 2:
    j = 1

    while j <= 3:
        print("i =", i, "j =", j)
        j += 1

    i += 1
```

**Output:**

```text
i = 1 j = 1
i = 1 j = 2
i = 1 j = 3
i = 2 j = 1
i = 2 j = 2
i = 2 j = 3
```

### Explanation

প্রথমে `i = 1` হয়। এরপর inner loop-এ `j`-এর মান `1`, `2`, `3` হয়।

Inner loop শেষ হলে `i` এক বাড়ে। এবার `i = 2` হয় এবং `j` আবার `1` থেকে শুরু করে।

Inner loop সম্পূর্ণ শেষ হওয়ার পরেই outer loop পরবর্তী iteration শুরু করে।

## 4. Step-by-Step Dry Run

Code:

```python
i = 1

while i <= 2:
    j = 1

    while j <= 2:
        print(i, j)
        j += 1

    i += 1
```

### Dry Run Table

| Step | `i` | `j` | Action |
|---:|---:|---:|---|
| 1 | 1 | 1 | `1 1` print |
| 2 | 1 | 2 | `1 2` print |
| 3 | 1 | 3 | Inner condition false |
| 4 | 2 | 1 | `2 1` print |
| 5 | 2 | 2 | `2 2` print |
| 6 | 2 | 3 | Inner condition false |
| 7 | 3 | — | Outer condition false |

Output:

```text
1 1
1 2
2 1
2 2
```

এখানে `j = 3` হলে inner loop শেষ হয়। এরপর `i` বাড়ে এবং পরবর্তী outer iteration-এ `j` আবার `1` হয়।

## 5. Why Must We Reset the Inner Variable?

Nested `while` loop-এর সবচেয়ে গুরুত্বপূর্ণ বিষয়গুলোর একটি হলো inner variable পুনরায় initialize করা।

### Incorrect Example

```python
i = 1
j = 1

while i <= 3:
    while j <= 2:
        print(i, j)
        j += 1

    i += 1
```

**Output:**

```text
1 1
1 2
```

### কেন এমন হয়?

- প্রথমবার inner loop `j = 1` ও `j = 2` নিয়ে চলে।
- এরপর `j`-এর মান `3` হয়।
- Inner loop শেষ হয়।
- `i` বাড়লেও `j` আবার `1` হয় না।
- তাই পরবর্তী outer iteration-এ inner loop আর চলে না।

### Correct Example

```python
i = 1

while i <= 3:
    j = 1

    while j <= 2:
        print(i, j)
        j += 1

    i += 1
```

এখানে `j = 1` outer loop-এর ভেতরে রাখা হয়েছে। তাই প্রতিটি outer iteration-এ inner loop নতুন করে শুরু হয়।

## 6. Updating Variables Correctly

Nested `while` loop-এ সাধারণত দুটি variable update করতে হয়:

- Inner loop-এর variable, inner loop-এর ভেতরে।
- Outer loop-এর variable, inner loop শেষ হওয়ার পরে।

### Example

```python
i = 1

while i <= 3:
    j = 1

    while j <= 3:
        print("*", end=" ")
        j += 1

    print()
    i += 1
```

**Output:**

```text
* * *
* * *
* * *
```

এখানে `j += 1` inner loop-কে শেষ করে এবং `i += 1` outer loop-কে শেষ করে।

## 7. Nested `while` Loop with Conditions

Nested loop-এর ভেতরে `if` ব্যবহার করে নির্দিষ্ট condition অনুযায়ী কাজ করা যায়।

### Example: Print Only Even Numbers

```python
i = 1

while i <= 3:
    j = 1

    while j <= 3:
        if j % 2 == 0:
            print(i, j)

        j += 1

    i += 1
```

**Output:**

```text
1 2
2 2
3 2
```

এখানে `j`-এর মান `2` হলেই condition সত্য হয় এবং output print হয়।

## 8. Nested `while` Loop for a Multiplication Table

### Example: Tables of 1 and 2

```python
number = 1

while number <= 2:
    multiplier = 1

    while multiplier <= 5:
        print(number, "x", multiplier, "=", number * multiplier)
        multiplier += 1

    print()
    number += 1
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
```

এখানে outer loop table-এর সংখ্যা নির্বাচন করে এবং inner loop multiplier পরিবর্তন করে।

## 9. Nested `while` Loop with User Input

Nested `while` loop ব্যবহার করে menu বা repeated input-এর program তৈরি করা যায়।

### Example

```python
choice = "yes"

while choice == "yes":
    number = 1

    while number <= 3:
        print("Number:", number)
        number += 1

    choice = input("Continue? (yes/no): ").lower()
```

**Example Interaction:**

```text
Number: 1
Number: 2
Number: 3
Continue? (yes/no): no
```

এখানে outer loop user-এর choice নিয়ন্ত্রণ করে। Inner loop প্রতিবার `1` থেকে `3` পর্যন্ত print করে।

এই উদাহরণে `input()`-এ `yes` বা `no` দেওয়া হচ্ছে ধরে নেওয়া হয়েছে। বাস্তব program-এ অন্য input-এর validation যোগ করা যেতে পারে।

## 10. Infinite Loops in Nested `while` Loops

Nested `while` loop-এ কোনো variable update না করলে infinite loop হতে পারে।

### Mistake 1: Inner Variable Not Updated

```python
i = 1

while i <= 3:
    j = 1

    while j <= 2:
        print(i, j)

    i += 1
```

এখানে `j` কখনো বাড়ছে না। তাই inner loop শেষ হয় না এবং `i`-ও বাড়তে পারে না।

### Mistake 2: Outer Variable Not Updated

```python
i = 1

while i <= 3:
    j = 1

    while j <= 2:
        print(i, j)
        j += 1
```

এখানে inner loop শেষ হয়, কিন্তু `i` বাড়ে না। ফলে outer loop বারবার একই কাজ করে।

### Correct Approach

```python
i = 1

while i <= 3:
    j = 1

    while j <= 2:
        print(i, j)
        j += 1

    i += 1
```

**মনে রাখবে:** Inner ও outer—দুই loop-এর condition-ই এমনভাবে পরিবর্তন করতে হবে, যাতে প্রয়োজনীয় সময়ে false হয়।

## 11. Using `break` in Nested `while` Loops

`break` নিকটতম enclosing loop বন্ধ করে।

### Example

```python
i = 1

while i <= 3:
    j = 1

    while j <= 3:
        if j == 2:
            break

        print(i, j)
        j += 1

    i += 1
```

**Output:**

```text
1 1
2 1
3 1
```

প্রতিটি outer iteration-এ inner loop `j = 2` হলে বন্ধ হয়। এরপর outer loop পরবর্তী iteration-এ যায়।

## 12. Using `continue` in Nested `while` Loops

`continue` বর্তমান iteration-এর বাকি অংশ বাদ দেয়। তবে `while` loop-এ এটি ব্যবহারের সময় variable update-এর অবস্থান গুরুত্বপূর্ণ।

### Correct Example

```python
i = 1

while i <= 2:
    j = 0

    while j < 3:
        j += 1

        if j == 2:
            continue

        print(i, j)

    i += 1
```

**Output:**

```text
1 1
1 3
2 1
2 3
```

এখানে `continue`-এর আগে `j += 1` হয়েছে। তাই `j == 2` হলেও পরবর্তী iteration-এ `j`-এর মান বাড়তে থাকে।

## 13. Common Mistakes

### Mistake 1: Forgetting to Reset the Inner Variable

প্রতিটি outer iteration-এ inner loop নতুন করে চালাতে চাইলে প্রয়োজন অনুযায়ী inner variable পুনরায় initialize করতে হবে।

### Mistake 2: Forgetting an Update Statement

Inner বা outer loop-এর variable update না হলে infinite loop হতে পারে।

### Mistake 3: Incorrect Indentation

Inner loop-এর code অবশ্যই তার block-এর মধ্যে indent করতে হবে।

### Mistake 4: Placing `continue` Before the Update

`continue` যদি `while` loop-এর variable update-এর আগে চলে, তাহলে update বাদ পড়ে যেতে পারে এবং loop আটকে যেতে পারে।

### Mistake 5: Confusing Inner and Outer Variables

`i` ও `j`-এর মতো আলাদা variable ব্যবহার করলে কোন loop কোন variable নিয়ন্ত্রণ করছে, তা বোঝা সহজ হয়।

## 14. Practice Exercises

### Exercise 1: Find the Output

```python
i = 1

while i <= 2:
    j = 1

    while j <= 2:
        print(i, j)
        j += 1

    i += 1
```

### Exercise 2: Count the Executions

```python
i = 1

while i <= 3:
    j = 1

    while j <= 4:
        print("*")
        j += 1

    i += 1
```

মোট কতটি star print হবে?

### Exercise 3: Find the Output

```python
i = 1

while i <= 2:
    j = 1

    while j <= 3:
        if j == 2:
            j += 1
            continue

        print(i, j)
        j += 1

    i += 1
```

### Exercise 4: Identify the Error

```python
i = 1

while i <= 3:
    j = 1

    while j <= 2:
        print(i, j)

    i += 1
```

কেন এই code শেষ হবে না?

### Exercise 5: Write a Program

Nested `while` loop ব্যবহার করে নিচের pattern print করো:

```text
* * *
* * *
```

## 15. Practice Answer Key

### Answer 1

```text
1 1
1 2
2 1
2 2
```

### Answer 2

Outer loop ৩ বার এবং inner loop প্রতিবার ৪ বার চলে।

মোট star:

\[
3 \times 4 = 12
\]

### Answer 3

```text
1 1
1 3
2 1
2 3
```

`j == 2` হলে `j` আগে বাড়ানো হয়, তারপর `continue` বর্তমান iteration-এর বাকি অংশ বাদ দেয়।

### Answer 4

Inner loop-এর ভেতরে `j += 1` নেই। তাই `j` সব সময় `1` থাকে এবং `j <= 2` condition সব সময় সত্য থাকে।

### Answer 5

```python
i = 1

while i <= 2:
    j = 1

    while j <= 3:
        print("*", end=" ")
        j += 1

    print()
    i += 1
```

Output:

```text
* * *
* * *
```

## 16. Chapter Summary

- Nested `while` loop হলো একটি `while` loop-এর ভেতরে আরেকটি `while` loop।
- Inner loop প্রতিটি outer iteration-এ চলে।
- Inner variable প্রয়োজন অনুযায়ী প্রতিবার initialize করতে হয়।
- Inner ও outer variable সঠিকভাবে update করতে হয়।
- `break` নিকটতম loop বন্ধ করে।
- `continue` বর্তমান iteration-এর বাকি অংশ বাদ দেয়।
- Update বাদ পড়লে infinite loop তৈরি হতে পারে।

## 17. Completion Checklist

- [ ] Nested `while` loop-এর structure বুঝি।
- [ ] Outer ও inner loop-এর execution trace করতে পারি।
- [ ] Inner variable reset করার কারণ বুঝি।
- [ ] Inner ও outer variable update করতে পারি।
- [ ] Nested `while` loop দিয়ে pattern তৈরি করতে পারি।
- [ ] Infinite loop-এর কারণ শনাক্ত করতে পারি।
- [ ] `break` ও `continue` সঠিকভাবে ব্যবহার করতে পারি।

**Next Topic:** `41_Understanding_Inner_and_Outer_Loops.md`
