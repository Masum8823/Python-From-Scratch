# 35. The `pass` Statement in Loops

## 1. Introduction

Python-এ `pass` একটি null statement। এটি execute হলে কোনো কাজ করে না।

কোনো code block-এর মধ্যে Python statement থাকা প্রয়োজন, কিন্তু সেখানে এখনই কোনো কাজ লিখতে না চাইলে `pass` ব্যবহার করা যায়।

**সহজভাবে:** `pass` মানে হলো আপাতত কিছু না করা।

Loop-এর মধ্যে `pass` ব্যবহার করা যায়, তবে এটি loop বন্ধ করে না বা বর্তমান iteration skip করে না।

## 2. Syntax of `pass`

```python
pass
```

এটি একটি সম্পূর্ণ statement। তাই যেখানে Python statement প্রয়োজন, সেখানে `pass` ব্যবহার করা যায়।

### Example

```python
for number in range(1, 4):
    pass

print("Loop completed")
```

**Output:**

```text
Loop completed
```

এখানে loop তিনবার চলেছে, কিন্তু loop-এর ভেতরে কোনো কাজ হয়নি।

## 3. Using `pass` in a `for` Loop

### Example 1: Empty Loop Body

```python
for number in range(1, 6):
    pass
```

এই code-এ কোনো output নেই।

### Explanation

- `range(1, 6)` পাঁচটি integer সরবরাহ করে।
- `for` loop পাঁচবার চলে।
- প্রতিবার `pass` execute হয়।
- `pass` কোনো কাজ করে না।

এটি valid Python code, যদিও বাস্তবে কাজ না করা loop-এর প্রয়োজন খুব কমই হয়।

### Example 2: Using `pass` with a Condition

```python
for number in range(1, 6):
    if number == 3:
        pass
    else:
        print(number)
```

**Output:**

```text
1
2
4
5
```

এখানে `number == 3` হলে `pass` execute হয়। অন্য সংখ্যার ক্ষেত্রে `print()` execute হয়।

**গুরুত্বপূর্ণ:** `pass` নিজে `3`-কে skip করেনি। `3` print হয়নি কারণ `print(number)` শুধু `else` block-এর মধ্যে রয়েছে।

## 4. Does `pass` Skip an Iteration?

না। `pass` নিজে iteration skip করে না।

### Example

```python
for number in range(1, 5):
    pass
    print(number)
```

**Output:**

```text
1
2
3
4
```

### Explanation

প্রতিটি iteration-এ:

1. `pass` execute হয়, কিন্তু কিছু করে না।
2. এরপর `print(number)` execute হয়।
3. পরবর্তী iteration শুরু হয়।

তাই `pass`-এর পরের statement স্বাভাবিকভাবে চলে।

## 5. Using `pass` in a `while` Loop

`while` loop-এর মধ্যেও `pass` ব্যবহার করা যায়।

### Example

```python
number = 1

while number <= 3:
    pass
    number += 1

print("Finished")
```

**Output:**

```text
Finished
```

### Explanation

- `number` শুরু হয়েছে `1` থেকে।
- `pass` কোনো কাজ করে না।
- `number += 1` প্রতিবার `number` বাড়ায়।
- `number` যখন `4` হয়, condition false হয়।
- Loop শেষ হয়।

এখানে `number += 1` না থাকলে loop শেষ হতো না।

### Important Warning

নিচের code-টি চালানো উচিত নয়:

```python
number = 1

while number <= 3:
    pass
```

এখানে `number` কখনো update হয় না। Condition সব সময় সত্য থাকে, ফলে loop অনির্দিষ্টকাল চলতে থাকে।

`pass` variable update করে না এবং নিজে থেকে loop শেষও করে না।

## 6. Using `pass` as a Placeholder

`pass`-এর সবচেয়ে গুরুত্বপূর্ণ ব্যবহার হলো placeholder হিসেবে কাজ করা।

ধরা যাক, তুমি একটি program-এর structure তৈরি করছ, কিন্তু কিছু logic পরে লিখবে।

### Example

```python
for number in range(1, 6):
    if number % 2 == 0:
        pass
    else:
        print(number)
```

**Output:**

```text
1
3
5
```

এখানে even number-এর জন্য `if` block আপাতত খালি রাখা হয়েছে। Python-এ `if`-এর body একেবারে খালি রাখা যায় না, তাই `pass` ব্যবহার করা হয়েছে।

### Without `pass`

```python
for number in range(1, 6):
    if number % 2 == 0:
    else:
        print(number)
```

এটি `SyntaxError` তৈরি করবে, কারণ `if` block-এর ভেতরে কোনো statement নেই।

## 7. Using `pass` While Developing a Program

ধরা যাক, তুমি একটি number-processing program তৈরি করছ। এখনো even number-এর logic লেখা হয়নি।

```python
for number in range(1, 6):
    if number % 2 == 0:
        pass
    else:
        print("Odd:", number)
```

**Output:**

```text
Odd: 1
Odd: 3
Odd: 5
```

এখানে `pass` দিয়ে even number-এর block সাময়িকভাবে পূরণ করা হয়েছে।

পরে চাইলে সেখানে logic যোগ করতে পারো:

```python
for number in range(1, 6):
    if number % 2 == 0:
        print("Even:", number)
    else:
        print("Odd:", number)
```

**Output:**

```text
Odd: 1
Even: 2
Odd: 3
Even: 4
Odd: 5
```

## 8. Difference Between `pass`, `break`, and `continue`

এই তিনটি statement-এর কাজ আলাদা।

| Statement | কাজ | পরবর্তী iteration হবে? |
|---|---|---|
| `pass` | কোনো কাজ করে না | স্বাভাবিক নিয়মে হবে |
| `continue` | বর্তমান iteration-এর বাকি অংশ বাদ দেয় | হ্যাঁ, যদি loop চলতে পারে |
| `break` | নিকটতম loop বন্ধ করে | ওই loop-এ আর হবে না |

### Example: `pass`

```python
for number in range(1, 4):
    pass
    print(number)
```

Output:

```text
1
2
3
```

### Example: `continue`

```python
for number in range(1, 4):
    if number == 2:
        continue
    print(number)
```

Output:

```text
1
3
```

### Example: `break`

```python
for number in range(1, 4):
    if number == 2:
        break
    print(number)
```

Output:

```text
1
```

**মনে রাখার কৌশল:**

- `pass` = Do nothing
- `continue` = Skip this iteration's remaining code
- `break` = Exit the loop

## 9. Using `pass` in Nested Loops

Nested loop-এর মধ্যেও `pass` ব্যবহার করা যায়।

### Example

```python
for i in range(1, 3):
    for j in range(1, 4):
        pass
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

এখানে inner loop মোট ছয়বার চলে। `pass` কোনো iteration বাদ দেয়নি।

## 10. Using `pass` in Conditional Logic Inside a Loop

কখনো কোনো condition পূরণ হলে আপাতত কোনো কাজ না করার প্রয়োজন হতে পারে।

### Example

```python
numbers = [10, 20, 30, 40]

for number in numbers:
    if number < 20:
        pass
    else:
        print(number)
```

**Output:**

```text
20
30
40
```

এখানে `10` print হয়নি, কারণ `number < 20` সত্য হলে `pass`-এর পর `if` block শেষ হয়েছে এবং `print()` শুধু `else` block-এ রয়েছে।

যদি `print(number)`-কে `if-else`-এর বাইরে রাখা হতো, তাহলে `10`-ও print হতো।

## 11. Common Mistakes

### Mistake 1: Thinking `pass` Skips a Number

```python
for number in range(1, 4):
    if number == 2:
        pass
    print(number)
```

**Output:**

```text
1
2
3
```

`2` print হয়েছে। কারণ `pass` কোনো statement skip করে না।

### Mistake 2: Thinking `pass` Ends a Loop

`pass` loop বন্ধ করে না। Loop স্বাভাবিক condition অনুযায়ী চলতে থাকে।

### Mistake 3: Using `pass` Without an Exit Condition

```python
number = 1

while number <= 5:
    pass
```

এটি infinite loop তৈরি করবে, কারণ variable update হচ্ছে না।

### Mistake 4: Using `pass` When Real Logic Is Needed

```python
if marks >= 40:
    pass
```

এটি syntactically valid, কিন্তু condition সত্য হলে বাস্তবে কোনো কাজ হবে না।

যদি pass করা শিক্ষার্থীকে message দেখাতে চাও, তাহলে:

```python
if marks >= 40:
    print("Passed")
```

ব্যবহার করা উচিত।

## 12. Practice Exercises

### Exercise 1: Find the Output

```python
for number in range(1, 5):
    pass
    print(number)
```

### Exercise 2: Find the Output

```python
for number in range(1, 6):
    if number == 3:
        pass
    else:
        print(number)
```

### Exercise 3: Find the Output

```python
for number in range(1, 4):
    if number == 2:
        pass
    print("Hello")
```

### Exercise 4: Identify the Statement

কোন statement কোনো কাজ করে না এবং placeholder হিসেবে ব্যবহার করা যায়?

- `break`
- `continue`
- `pass`

### Exercise 5: Write a Program

`1` থেকে `5` পর্যন্ত loop চালাও। `if number == 3` block-এ আপাতত `pass` ব্যবহার করো এবং loop-এর প্রতিটি সংখ্যাই print করো।

### Exercise 6: Explain the Error

```python
while True:
    pass
```

এই code কেন থামে না?

## 13. Practice Answer Key

### Answer 1

```text
1
2
3
4
```

`pass`-এর পর `print()` execute হয়।

### Answer 2

```text
1
2
4
5
```

`3` print হয়নি, কারণ সেটির ক্ষেত্রে `pass`-সহ `if` block execute হয়েছে এবং `print()` শুধু `else` block-এ রয়েছে।

### Answer 3

```text
Hello
Hello
Hello
```

প্রতিটি iteration-এ `print("Hello")` execute হয়েছে। `pass` এটি বন্ধ করেনি।

### Answer 4

**Answer: `pass`**

### Answer 5

```python
for number in range(1, 6):
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
5
```

### Answer 6

`while True`-এর condition সব সময় সত্য। Loop-এর ভেতরে `break` বা অন্য কোনো exit condition নেই। `pass` কিছু করে না, তাই loop অনির্দিষ্টকাল চলে।

## 14. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `pass` একটি null statement।
- এটি কোনো কাজ করে না।
- `pass` loop বন্ধ করে না।
- এটি বর্তমান iteration skip করে না।
- Empty code block-এর placeholder হিসেবে ব্যবহার করা যায়।
- `while` loop-এ variable update না করলে infinite loop হতে পারে।

## 15. Completion Checklist

- [ ] `pass` statement-এর কাজ বুঝি।
- [ ] `pass` ও `continue`-এর পার্থক্য বলতে পারি।
- [ ] `pass` ও `break`-এর পার্থক্য বলতে পারি।
- [ ] Loop-এর ভেতরে `pass` ব্যবহার করতে পারি।
- [ ] Placeholder হিসেবে `pass` ব্যবহার করতে পারি।
- [ ] `pass`-এর কারণে কেন loop থামে না, তা বুঝি।

**Next Topic:** `36_break_vs_continue_vs_pass.md`
