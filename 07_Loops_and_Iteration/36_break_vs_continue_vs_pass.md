# 36. `break` vs `continue` vs `pass`

## 1. Introduction

Python-এ `break`, `continue` এবং `pass` হলো তিনটি গুরুত্বপূর্ণ statement। এগুলো loop-এর মধ্যে ব্যবহার করা যায়, কিন্তু প্রতিটির কাজ আলাদা।

- `break` — loop বন্ধ করে।
- `continue` — বর্তমান iteration-এর বাকি অংশ বাদ দেয়।
- `pass` — কোনো কাজ করে না।

এই পার্থক্য ভালোভাবে বোঝা জরুরি, কারণ একই code-এ statement পরিবর্তন করলে output-ও পরিবর্তিত হতে পারে।

## 2. The `break` Statement

`break` ব্যবহার করে loop থেকে সঙ্গে সঙ্গে বের হয়ে আসা যায়।

### Example

```python
for number in range(1, 6):
    if number == 3:
        break

    print(number)
```

**Output:**

```text
1
2
```

### Explanation

- `1` ও `2` print হয়।
- `number == 3` হলে `break` execute হয়।
- Loop বন্ধ হয়ে যায়।
- `4` ও `5`-এর iteration আর হয় না।

**মনে রাখবে:** `break` নিকটতম enclosing loop-টি বন্ধ করে।

## 3. The `continue` Statement

`continue` বর্তমান iteration-এর বাকি অংশ বাদ দিয়ে পরবর্তী iteration শুরু করে।

### Example

```python
for number in range(1, 6):
    if number == 3:
        continue

    print(number)
```

**Output:**

```text
1
2
4
5
```

### Explanation

- `1` ও `2` print হয়।
- `number == 3` হলে `continue` execute হয়।
- ওই iteration-এর `print(number)` execute হয় না।
- এরপর loop `4` ও `5` নিয়ে চলে।

**মনে রাখবে:** `continue` loop বন্ধ করে না।

## 4. The `pass` Statement

`pass` একটি null statement। এটি execute হলে কোনো কাজ করে না।

### Example

```python
for number in range(1, 6):
    if number == 3:
        pass

    print(number)
```

**Output:**

```text
1
2
3
4
5
```

### Explanation

- `number == 3` হলে `pass` execute হয়।
- `pass` কোনো statement বাদ দেয় না।
- এরপর `print(number)` execute হয়।
- তাই সব সংখ্যাই print হয়।

**মনে রাখবে:** `pass` মূলত placeholder হিসেবে ব্যবহার করা হয়।

## 5. Main Differences

| Feature | `break` | `continue` | `pass` |
|---|---|---|---|
| প্রধান কাজ | Loop বন্ধ করা | বর্তমান iteration-এর বাকি অংশ বাদ দেওয়া | কোনো কাজ না করা |
| Loop বন্ধ করে? | হ্যাঁ | না | না |
| বর্তমান iteration-এর বাকি code | Execute হয় না | Execute হয় না | স্বাভাবিকভাবে execute হয় |
| পরবর্তী iteration | ওই loop-এ হয় না | হয়, যদি loop চলতে পারে | স্বাভাবিক নিয়মে হয় |
| Placeholder হিসেবে ব্যবহার | না | না | হ্যাঁ |
| `while` loop-এ infinite loop-এর ঝুঁকি | Exit logic-এর ওপর নির্ভর করে | Variable update বাদ পড়লে হতে পারে | Variable update না থাকলে হতে পারে |

## 6. Same Program, Three Different Results

এবার একই code-এ শুধু control statement পরিবর্তন করে দেখি।

### Case 1: Using `break`

```python
for number in range(1, 5):
    if number == 3:
        break

    print(number)
```

Output:

```text
1
2
```

### Case 2: Using `continue`

```python
for number in range(1, 5):
    if number == 3:
        continue

    print(number)
```

Output:

```text
1
2
4
```

### Case 3: Using `pass`

```python
for number in range(1, 5):
    if number == 3:
        pass

    print(number)
```

Output:

```text
1
2
3
4
```

### Conclusion

- `break` ব্যবহার করলে `3`-এ পৌঁছে loop বন্ধ হয়।
- `continue` ব্যবহার করলে শুধু `3`-এর print বাদ পড়ে।
- `pass` ব্যবহার করলে `3`-সহ সব সংখ্যাই print হয়।

## 7. Understanding Execution Flow

নিচের table-টি মনে রাখলে পার্থক্য বোঝা সহজ হবে।

| Statement | `number = 1` | `number = 2` | `number = 3` | `number = 4` |
|---|---|---|---|---|
| `break` at 3 | Print | Print | Loop stops | Reached হয় না |
| `continue` at 3 | Print | Print | Print skipped | Print |
| `pass` at 3 | Print | Print | Print | Print |

এখানে প্রতিটি ক্ষেত্রে condition হলো `number == 3`।

## 8. `break`, `continue`, and `pass` in a `while` Loop

### Using `break`

```python
number = 1

while number <= 5:
    if number == 4:
        break

    print(number)
    number += 1
```

Output:

```text
1
2
3
```

`number` যখন `4` হয়, loop বন্ধ হয়।

### Using `continue`

```python
number = 0

while number < 5:
    number += 1

    if number == 3:
        continue

    print(number)
```

Output:

```text
1
2
4
5
```

এখানে `continue`-এর আগে variable update হয়েছে। তাই loop সঠিকভাবে শেষ হয়।

### Using `pass`

```python
number = 0

while number < 3:
    number += 1

    if number == 2:
        pass

    print(number)
```

Output:

```text
1
2
3
```

`pass` কোনো iteration বাদ দেয়নি।

## 9. Common Mistakes

### Mistake 1: Thinking `pass` Works Like `continue`

ভুল ধারণা: `pass` বর্তমান iteration বাদ দেয়।

সঠিক ধারণা: `pass` কোনো কাজ করে না। পরের statement স্বাভাবিকভাবে execute হয়।

### Mistake 2: Thinking `continue` Stops the Loop

ভুল ধারণা: `continue` loop বন্ধ করে।

সঠিক ধারণা: `continue` বর্তমান iteration-এর বাকি অংশ বাদ দিয়ে পরবর্তী iteration শুরু করে।

### Mistake 3: Thinking `break` Skips Only One Value

ভুল ধারণা: `break` শুধু একটি সংখ্যা বাদ দেয়।

সঠিক ধারণা: `break` নিকটতম loop-টি সম্পূর্ণ বন্ধ করে দেয়।

### Mistake 4: Forgetting Variable Updates in `while`

`while` loop-এ `continue`-এর কারণে variable update বাদ পড়ে গেলে infinite loop হতে পারে।

উদাহরণ:

```python
number = 1

while number <= 5:
    if number == 3:
        continue

    number += 1
```

এখানে `number == 3` হলে update execute হয় না। ফলে loop চলতেই থাকে।

## 10. When Should You Use Each Statement?

### Use `break` when:

- Search result পাওয়া গেলে loop বন্ধ করতে হবে।
- User exit option নির্বাচন করেছে।
- নির্দিষ্ট condition-এ আর iteration প্রয়োজন নেই।

### Use `continue` when:

- নির্দিষ্ট সংখ্যা বা value বাদ দিতে হবে।
- Invalid data skip করে valid data process করতে হবে।
- বর্তমান iteration-এর বাকি কাজ প্রয়োজন নেই।

### Use `pass` when:

- কোনো code block আপাতত খালি রাখতে হবে।
- পরে implementation যোগ করা হবে।
- Function, class বা condition-এর structure আগে তৈরি করতে হবে।

## 11. Practice Exercises

### Exercise 1: Find the Output

```python
for number in range(1, 6):
    if number == 4:
        break

    print(number)
```

### Exercise 2: Find the Output

```python
for number in range(1, 6):
    if number == 2:
        continue

    print(number)
```

### Exercise 3: Find the Output

```python
for number in range(1, 5):
    if number == 3:
        pass

    print(number)
```

### Exercise 4: Identify the Statement

কোন statement loop সম্পূর্ণ বন্ধ করে?

### Exercise 5: Identify the Statement

কোন statement বর্তমান iteration-এর বাকি অংশ বাদ দেয়?

### Exercise 6: Identify the Statement

কোন statement কোনো কাজ না করে placeholder হিসেবে ব্যবহার করা যায়?

### Exercise 7: Find the Output

```python
for number in range(1, 6):
    if number == 2:
        pass
    elif number == 4:
        continue
    elif number == 5:
        break

    print(number)
```

### Exercise 8: Fix the Code

নিচের code-এ `continue` ব্যবহার করে `3` skip করতে হবে, কিন্তু infinite loop তৈরি করা যাবে না।

```python
number = 1

while number <= 5:
    if number == 3:
        continue

    print(number)
    number += 1
```

## 12. Practice Answer Key

### Answer 1

```text
1
2
3
```

`4` হলে loop বন্ধ হয়।

### Answer 2

```text
1
3
4
5
```

`2`-এর iteration-এ `print()` বাদ পড়ে।

### Answer 3

```text
1
2
3
4
```

`pass` কোনো কাজ করে না।

### Answer 4

**Answer: `break`**

### Answer 5

**Answer: `continue`**

### Answer 6

**Answer: `pass`**

### Answer 7

```text
1
2
3
```

Explanation:

- `1` print হয়।
- `2`-এর ক্ষেত্রে `pass` কোনো প্রভাব ফেলে না, তাই `2` print হয়।
- `3` print হয়।
- `4` হলে `continue` execute হয়, তাই `4` print হয় না।
- `5` হলে `break` execute হয়, তাই loop বন্ধ হয়।

### Answer 8

```python
number = 1

while number <= 5:
    if number == 3:
        number += 1
        continue

    print(number)
    number += 1
```

Output:

```text
1
2
4
5
```

এখানে `number == 3` হলে `continue`-এর আগে variable update করা হয়েছে।

## 13. Exam-Ready Short Answer

**Question: Differentiate between `break`, `continue`, and `pass` in Python.**

**Answer:**

- `break` terminates the nearest enclosing loop immediately.
- `continue` skips the remaining statements in the current iteration and proceeds to the next iteration.
- `pass` performs no operation and is used as a placeholder when a statement is syntactically required.

## 14. Chapter Summary

এই topic থেকে মূল বিষয়গুলো:

- `break` = loop বন্ধ করে।
- `continue` = বর্তমান iteration-এর বাকি অংশ বাদ দেয়।
- `pass` = কোনো কাজ করে না।
- তিনটি statement-এর কাজ এক নয়।
- `while` loop-এ `continue` ব্যবহার করার সময় variable update নিশ্চিত করতে হবে।
- Nested loop-এ `break` ও `continue` সাধারণত যে loop-এর মধ্যে আছে, সেটিকেই প্রভাবিত করে।

## 15. Completion Checklist

- [ ] `break`-এর কাজ বুঝি।
- [ ] `continue`-এর কাজ বুঝি।
- [ ] `pass`-এর কাজ বুঝি।
- [ ] একই code-এ তিনটির output তুলনা করতে পারি।
- [ ] `while` loop-এ infinite loop এড়াতে পারি।
- [ ] Exam-এ তিনটির পার্থক্য লিখতে পারি।

**Next Topic:** `37_Nested_Loops_and_Control_Flow.md`
