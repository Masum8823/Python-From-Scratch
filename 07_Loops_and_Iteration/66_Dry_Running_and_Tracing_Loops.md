# 66. Dry Running and Tracing Loops

## 1. Introduction

Dry Run হলো code execute না করে হাতে হাতে প্রতিটি ধাপ অনুসরণ করে program-এর কাজ বোঝার পদ্ধতি।

Loop Tracing হলো loop-এর প্রতিটি iteration-এ variable-এর value, condition এবং output কীভাবে পরিবর্তিত হয়, তা অনুসরণ করা।

সহজভাবে:

- **Dry Run:** Code হাতে হাতে execute করার মতো করে অনুসরণ করা।
- **Loop Tracing:** বিশেষভাবে loop-এর প্রতিটি iteration বিশ্লেষণ করা।

এই দুটি technique ব্যবহার করে আমরা বুঝতে পারি:

- Loop কতবার চলবে।
- প্রতিবার variable-এর value কী হবে।
- কোন condition True বা False হবে।
- কখন loop শেষ হবে।
- Final output কী হবে।

## 2. Why Is Dry Running Important?

Dry running আমাদের code-এর logic বুঝতে সাহায্য করে।

এর প্রধান ব্যবহার:

1. Output predict করা।
2. Variable-এর value trace করা।
3. Infinite loop-এর কারণ খুঁজে বের করা।
4. Off-by-one error শনাক্ত করা।
5. Counter ও accumulator-এর কাজ বোঝা।
6. Exam-এর code tracing problem solve করা।
7. Code-এর logic ঠিক আছে কি না পরীক্ষা করা।

বিশেষ করে beginner হিসেবে code বুঝতে সমস্যা হলে dry run একটি কার্যকর পদ্ধতি।

## 3. Understanding a Simple Loop

নিচের code-টি দেখি:

```python
for number in range(1, 4):
    print(number)
```

### Step-by-Step Execution

`range(1, 4)` থেকে পাওয়া যায়:

```text
1, 2, 3
```

প্রতিটি iteration-এ `number`-এর value পরিবর্তিত হয়।

| Iteration | `number` | Output |
|---:|---:|---:|
| 1 | 1 | 1 |
| 2 | 2 | 2 |
| 3 | 3 | 3 |

Final output:

```text
1
2
3
```

এখানে loop তিনবার চলে, কারণ `4` হলো exclusive stop value।

## 4. Tracing a `while` Loop

Code:

```python
number = 1

while number <= 3:
    print(number)
    number += 1
```

### Dry Run Table

| Iteration | Value before condition | Condition `number <= 3` | Output | Value after update |
|---:|---:|---|---:|---:|
| 1 | 1 | True | 1 | 2 |
| 2 | 2 | True | 2 | 3 |
| 3 | 3 | True | 3 | 4 |
| 4 | 4 | False | — | 4 |

Final output:

```text
1
2
3
```

### Explanation

1. প্রথমে `number = 1`।
2. Condition True হলে loop body execute হয়।
3. `number += 1` দিয়ে value এক বাড়ে।
4. `number = 4` হলে condition False হয়।
5. Loop বন্ধ হয়।

**Important:** `while` loop-এ condition প্রতিটি iteration-এর আগে পরীক্ষা করা হয়।

## 5. Tracing a Counter Variable

Counter variable কোনো ঘটনা কতবার ঘটেছে, তা গণনা করে।

Code:

```python
count = 0

for number in range(1, 6):
    if number % 2 == 0:
        count += 1

print(count)
```

### Dry Run Table

| Number | Even? | Count before | Count after |
|---:|---|---:|---:|
| 1 | No | 0 | 0 |
| 2 | Yes | 0 | 1 |
| 3 | No | 1 | 1 |
| 4 | Yes | 1 | 2 |
| 5 | No | 2 | 2 |

Final output:

```text
2
```

কারণ `1` থেকে `5` পর্যন্ত even সংখ্যা হলো `2` ও `4`।

## 6. Tracing an Accumulator Variable

Accumulator variable দিয়ে sum বা total জমা রাখা হয়।

Code:

```python
total = 0

for number in range(1, 5):
    total += number

print(total)
```

### Dry Run Table

| Iteration | Number | Total before | Total after |
|---:|---:|---:|---:|
| 1 | 1 | 0 | 1 |
| 2 | 2 | 1 | 3 |
| 3 | 3 | 3 | 6 |
| 4 | 4 | 6 | 10 |

Final output:

```text
10
```

এখানে:

\[
1+2+3+4=10
\]

প্রতিটি iteration-এ বর্তমান সংখ্যাটি `total`-এর সঙ্গে যোগ হয়।

## 7. Tracing a Loop with `if-else`

Code:

```python
for number in range(1, 6):
    if number % 2 == 0:
        print(number, "Even")
    else:
        print(number, "Odd")
```

### Dry Run Table

| Number | `number % 2 == 0` | Selected branch |
|---:|---|---|
| 1 | False | `else` |
| 2 | True | `if` |
| 3 | False | `else` |
| 4 | True | `if` |
| 5 | False | `else` |

Output:

```text
1 Odd
2 Even
3 Odd
4 Even
5 Odd
```

Dry run করার সময় শুধু loop নয়, প্রতিটি condition-এর ফলাফলও অনুসরণ করতে হবে।

## 8. Tracing a Loop with `break`

`break` execute হলে loop সঙ্গে সঙ্গে বন্ধ হয়ে যায়।

Code:

```python
for number in range(1, 6):
    if number == 4:
        break
    print(number)
```

### Dry Run Table

| Number | Condition `number == 4` | Action |
|---:|---|---|
| 1 | False | Print 1 |
| 2 | False | Print 2 |
| 3 | False | Print 3 |
| 4 | True | Loop stops |

Output:

```text
1
2
3
```

`number = 4` হলে `break` execute হয়। তাই `4` print হয় না।

## 9. Tracing a Loop with `continue`

`continue` বর্তমান iteration-এর বাকি অংশ বাদ দিয়ে পরবর্তী iteration শুরু করে।

Code:

```python
for number in range(1, 6):
    if number == 3:
        continue
    print(number)
```

### Dry Run Table

| Number | Condition `number == 3` | Action |
|---:|---|---|
| 1 | False | Print 1 |
| 2 | False | Print 2 |
| 3 | True | Skip printing |
| 4 | False | Print 4 |
| 5 | False | Print 5 |

Output:

```text
1
2
4
5
```

এখানে `3` বাদ পড়েছে, কিন্তু loop বন্ধ হয়নি।

## 10. Tracing Nested Loops

Nested loop-এ একটি loop-এর ভেতরে আরেকটি loop থাকে।

Code:

```python
for row in range(1, 4):
    for column in range(1, 3):
        print(row, column)
```

### Execution

প্রথমে `row = 1` হয়। তখন inner loop চলে:

- `column = 1`
- `column = 2`

এরপর `row = 2` হলে inner loop আবার শুরু হয়।

### Dry Run Table

| Outer `row` | Inner `column` | Output |
|---:|---:|---|
| 1 | 1 | `1 1` |
| 1 | 2 | `1 2` |
| 2 | 1 | `2 1` |
| 2 | 2 | `2 2` |
| 3 | 1 | `3 1` |
| 3 | 2 | `3 2` |

Output:

```text
1 1
1 2
2 1
2 2
3 1
3 2
```

মোট iteration:

\[
3\times2=6
\]

এখানে outer loop তিনবার এবং প্রতিবার inner loop দুবার চলে।

## 11. Tracing Variable Updates Carefully

কোনো variable update হওয়ার আগে এবং পরে তার value আলাদা হতে পারে।

Code:

```python
number = 2

while number < 10:
    print(number)
    number += 3
```

### Dry Run Table

| Iteration | Value before condition | Condition | Output | Value after update |
|---:|---:|---|---:|---:|
| 1 | 2 | True | 2 | 5 |
| 2 | 5 | True | 5 | 8 |
| 3 | 8 | True | 8 | 11 |
| 4 | 11 | False | — | 11 |

Output:

```text
2
5
8
```

এখানে `number`-এর value `2, 5, 8, 11` হয়। কিন্তু `11` print হয় না, কারণ condition পরীক্ষা করার সময় সেটি False।

**মনে রাখবে:** Loop-এর ভেতরে variable update হলে পরবর্তী condition সেই updated value ব্যবহার করে।

## 12. Tracing the `else` Clause in a Loop

Loop-এর `else` clause স্বাভাবিকভাবে loop শেষ হলে execute হয়। `break` দিয়ে loop বন্ধ করলে এটি execute হয় না।

### Example 1: Normal Completion

```python
for number in range(1, 4):
    print(number)
else:
    print("Loop completed")
```

Output:

```text
1
2
3
Loop completed
```

### Example 2: Using `break`

```python
for number in range(1, 4):
    if number == 2:
        break
    print(number)
else:
    print("Loop completed")
```

Output:

```text
1
```

`break` execute হওয়ার কারণে `else` block চলে না।

Dry run-এ তাই loop স্বাভাবিকভাবে শেষ হয়েছে, নাকি `break` দিয়ে বের হয়েছে, সেটি খেয়াল রাখতে হবে।

## 13. A Systematic Dry-Run Method

যেকোনো loop trace করার জন্য এই ধাপগুলো অনুসরণ করো।

### Step 1: Identify Initial Values

সব variable-এর initial value লিখে নাও।

```python
number = 1
total = 0
```

### Step 2: Check the Loop Condition

`while` হলে condition পরীক্ষা করো। `for` হলে iterable থেকে পরবর্তী value নাও।

### Step 3: Execute the Loop Body

Statement-গুলো উপরের দিক থেকে নিচের দিকে অনুসরণ করো।

### Step 4: Evaluate Conditions

প্রতিটি `if`, `elif` বা `else` কোন branch execute করবে, তা নির্ধারণ করো।

### Step 5: Update Variables

Counter, accumulator ও loop control variable-এর নতুন value লিখে রাখো।

### Step 6: Repeat

পরবর্তী iteration-এর জন্য একই ধাপ অনুসরণ করো।

### Step 7: Check the Exit Condition

Loop কখন শেষ হচ্ছে, তা নির্ধারণ করো।

### Step 8: Write the Final Output

`print()` statement-গুলো যে ক্রমে execute হয়েছে, সেই ক্রমে output লেখো।

## 14. Complete Dry-Run Example

Problem: `1` থেকে `6` পর্যন্ত সংখ্যার মধ্যে even সংখ্যাগুলোর sum এবং count বের করো।

Code:

```python
count = 0
total = 0

for number in range(1, 7):
    if number % 2 == 0:
        count += 1
        total += number

print("Count:", count)
print("Sum:", total)
```

### Dry Run Table

| Number | Even? | Count before | Count after | Total after |
|---:|---|---:|---:|---:|
| 1 | No | 0 | 0 | 0 |
| 2 | Yes | 0 | 1 | 2 |
| 3 | No | 1 | 1 | 2 |
| 4 | Yes | 1 | 2 | 6 |
| 5 | No | 2 | 2 | 6 |
| 6 | Yes | 2 | 3 | 12 |

Output:

```text
Count: 3
Sum: 12
```

এখানে even সংখ্যাগুলো হলো `2`, `4` ও `6`।

তাই count `3` এবং sum `12`।

## 15. Common Dry-Running Mistakes

### Mistake 1: Ignoring the Initial Value

ভুলভাবে variable-এর value অনুমান করলে পুরো trace ভুল হতে পারে।

**Solution:** প্রথমে সব variable-এর initial value লিখবে।

### Mistake 2: Forgetting the Exclusive Stop Value

```python
range(1, 5)
```

এটি `1, 2, 3, 4` দেয়; `5` দেয় না।

### Mistake 3: Updating Variables in the Wrong Order

Code:

```python
a = 2
b = 3

a = b
b = a
```

Final values:

```text
a = 3
b = 3
```

কারণ প্রথম statement-এ `a`-এর value `3` হয়ে যায়। পরের statement সেই updated value ব্যবহার করে।

যদি দুটি value swap করতে চাও:

```python
a, b = b, a
```

তাহলে `a = 3` এবং `b = 2` হবে।

### Mistake 4: Forgetting `continue`

`continue` execute হলে বর্তমান iteration-এর বাকি statement-গুলো execute হয় না।

### Mistake 5: Assuming `break` Skips Only One Statement

`break` শুধু একটি statement বাদ দেয় না; এটি সবচেয়ে ভেতরের চলমান loop-টি বন্ধ করে দেয়।

### Mistake 6: Confusing `print()` with Variable Update

```python
number = 1
print(number)
number += 1
```

এখানে output `1`, কারণ print update-এর আগে execute হয়েছে।

### Mistake 7: Forgetting Nested Loop Repetition

Outer loop-এর প্রতিটি iteration-এ inner loop সাধারণত আবার শুরু হয়। তাই nested loop trace করার সময় দুটো loop-এর value আলাদা করে track করতে হবে।

### Mistake 8: Stopping the Trace Too Early

একটি iteration শেষ হলেই loop শেষ হয় না। Loop condition False না হওয়া পর্যন্ত অথবা `break` না হওয়া পর্যন্ত trace চালিয়ে যেতে হবে।

## 16. Practice Exercises

প্রথমে নিজে dry run করার চেষ্টা করো। এরপর answer key দিয়ে যাচাই করবে।

### Exercise 1: Simple `for` Loop

Output কী হবে?

```python
for i in range(2, 7):
    print(i)
```

### Exercise 2: Counter

Output কী হবে?

```python
count = 0

for i in range(1, 8):
    if i % 2 != 0:
        count += 1

print(count)
```

### Exercise 3: Accumulator

Output কী হবে?

```python
total = 0

for i in range(1, 5):
    total += i * 2

print(total)
```

### Exercise 4: `while` Loop

Output কী হবে?

```python
number = 10

while number > 4:
    print(number)
    number -= 2
```

### Exercise 5: `break`

Output কী হবে?

```python
for i in range(1, 7):
    if i > 4:
        break
    print(i)
```

### Exercise 6: `continue`

Output কী হবে?

```python
for i in range(1, 6):
    if i % 2 == 0:
        continue
    print(i)
```

### Exercise 7: Nested Loop

Output কী হবে?

```python
for i in range(1, 3):
    for j in range(1, 3):
        print(i + j)
```

### Exercise 8: Condition and Accumulator

Output কী হবে?

```python
total = 0

for number in [3, 6, 9, 12]:
    if number > 5:
        total += number

print(total)
```

### Exercise 9: Variable Update

Output কী হবে?

```python
number = 1

while number < 8:
    number *= 2
    print(number)
```

### Exercise 10: Loop `else`

Output কী হবে?

```python
for i in range(3):
    if i == 5:
        break
else:
    print("Finished")
```

## 17. Practice Answer Key

### Answer 1

```text
2
3
4
5
6
```

কারণ `range(2, 7)`-এ `7` অন্তর্ভুক্ত নয়।

### Answer 2

```text
4
```

Odd সংখ্যাগুলো `1`, `3`, `5` ও `7`। তাই count `4`।

### Answer 3

```text
20
```

হিসাব:

\[
2+4+6+8=20
\]

### Answer 4

```text
10
8
6
```

এরপর `number = 4` হয় এবং `number > 4` False হয়ে যায়।

### Answer 5

```text
1
2
3
4
```

`i = 5` হলে `break` execute হয়, তাই `5` print হয় না।

### Answer 6

```text
1
3
5
```

Even সংখ্যাগুলো skip করা হয়েছে।

### Answer 7

```text
2
3
3
4
```

হিসাব:

- `i = 1`: `1 + 1 = 2`, `1 + 2 = 3`
- `i = 2`: `2 + 1 = 3`, `2 + 2 = 4`

### Answer 8

```text
27
```

কারণ `6 + 9 + 12 = 27`।

### Answer 9

```text
2
4
8
```

প্রতিবার `number` দ্বিগুণ হয়। `8` print হওয়ার পর condition False হয়।

### Answer 10

```text
Finished
```

`range(3)` থেকে `0`, `1`, `2` পাওয়া যায়। কোনো value `5` নয়, তাই `break` হয় না এবং loop-এর `else` execute হয়।

## 18. Chapter Summary

- Dry run হলো code হাতে হাতে অনুসরণ করার পদ্ধতি।
- Loop tracing প্রতিটি iteration-এর variable, condition ও output বোঝায়।
- `for` loop iterable থেকে value নেয়।
- `while` loop condition True থাকা পর্যন্ত চলে।
- Counter গণনা করে, accumulator sum জমা রাখে।
- `break` loop বন্ধ করে এবং `continue` বর্তমান iteration-এর বাকি অংশ skip করে।
- Nested loop-এ inner loop প্রতিটি outer iteration-এ পুনরায় চলে।
- Loop-এর `else` স্বাভাবিক completion-এর পরে execute হয়।
- Dry run করতে initial value, condition, update ও exit point অনুসরণ করতে হয়।
- Dry run-এর মাধ্যমে logic error এবং off-by-one error শনাক্ত করা যায়।

## 19. Completion Checklist

- [ ] `for` loop trace করতে পারি।
- [ ] `while` loop trace করতে পারি।
- [ ] Counter ও accumulator-এর পরিবর্তন লিখতে পারি।
- [ ] `if-else`-সহ loop trace করতে পারি।
- [ ] `break` ও `continue`-এর প্রভাব বুঝতে পারি।
- [ ] Nested loop-এর execution অনুসরণ করতে পারি।
- [ ] Loop-এর `else` clause trace করতে পারি।
- [ ] Dry-run table তৈরি করতে পারি।
- [ ] Code execute না করেই output predict করতে পারি।

**Next Topic:** `67_Loop_Invariants_Basic_Introduction.md`