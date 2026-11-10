# 09. Introduction to the `while` Loop

## 1. Introduction

Python-এ `while` loop ব্যবহার করে কোনো condition `True` থাকা পর্যন্ত একটি code block বারবার execute করা যায়।

ধরো, তোমাকে `Hello` পাঁচবার print করতে হবে। প্রতিবার আলাদা করে `print()` না লিখে loop ব্যবহার করতে পারো।

```python
count = 1

while count <= 5:
    print("Hello")
    count += 1
```

Output:

```text
Hello
Hello
Hello
Hello
Hello
```

এখানে `while` loop পাঁচবার `Hello` print করেছে।

## 2. What Is a `while` Loop?

**Definition:** A `while` loop repeatedly executes a block of code as long as its condition is `True`.

সহজ ভাষায়, যতক্ষণ condition `True` থাকবে, ততক্ষণ `while` loop-এর ভেতরের code চলতে থাকবে।

Condition `False` হয়ে গেলে loop বন্ধ হয়ে যায়।

### Basic Syntax

```python
while condition:
    # Code to execute repeatedly
```

এখানে:

- `while` হলো Python-এর keyword।
- `condition` হলো একটি expression, যার truth value পরীক্ষা করা হয়।
- `:` দিয়ে loop body শুরু হয়।
- Indented code হলো loop body।
- Condition `True` হলে body execute হয়।

## 3. How Does a `while` Loop Work?

নিচের code-টি দেখো:

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

Output:

```text
1
2
3
```

### Step-by-Step Execution

1. `count = 1` দিয়ে variable initialize হয়।
2. Python `count <= 3` condition পরীক্ষা করে।
3. Condition `True` হলে `print(count)` execute হয়।
4. `count += 1` দিয়ে `count` এক বাড়ে।
5. আবার condition পরীক্ষা হয়।
6. `count`-এর value `4` হলে condition `False` হয়।
7. Loop শেষ হয়।

### Dry Run Table

| Iteration | `count` | `count <= 3` | Output |
|---:|---:|---|---:|
| 1 | 1 | `True` | 1 |
| 2 | 2 | `True` | 2 |
| 3 | 3 | `True` | 3 |
| শেষ পরীক্ষা | 4 | `False` | নেই |

**মনে রাখবে:** প্রতিটি iteration-এর আগে `while` loop-এর condition আবার পরীক্ষা করা হয়।

## 4. The Role of the Condition

`while` loop-এর condition নির্ধারণ করে loop চলবে কি না।

### Example 1: Condition Is True

```python
number = 1

while number <= 3:
    print(number)
    number += 1
```

Output:

```text
1
2
3
```

### Example 2: Condition Is False at the Beginning

```python
number = 10

while number < 5:
    print(number)
```

Output: কোনো output নেই।

কারণ শুরুতেই `10 < 5` হলো `False`। তাই loop body execute হয় না।

## 5. Updating the Variable

অনেক `while` loop-এ এমন variable থাকে, যার value প্রতিটি iteration-এ পরিবর্তন করতে হয়।

```python
count = 1

while count <= 4:
    print(count)
    count += 1
```

এখানে:

```python
count += 1
```

এর অর্থ:

```python
count = count + 1
```

এই update-এর কারণে `count` ধীরে ধীরে বাড়ে এবং একসময় condition `False` হয়।

যদি variable সঠিকভাবে update না করা হয়, তাহলে loop অনির্দিষ্টকাল চলতে পারে।

## 6. Common Uses of the `while` Loop

### 6.1 Counting

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

এটি ১ থেকে ৫ পর্যন্ত print করে।

### 6.2 Countdown

```python
count = 5

while count >= 1:
    print(count)
    count -= 1

print("Finished!")
```

Output:

```text
5
4
3
2
1
Finished!
```

### 6.3 Calculating a Sum

```python
number = 1
total = 0

while number <= 5:
    total += number
    number += 1

print("Total:", total)
```

Output:

```text
Total: 15
```

### 6.4 Repeating Until a Condition Is Met

```python
number = 1

while number < 10:
    number *= 2
    print(number)
```

Output:

```text
2
4
8
16
```

এখানে প্রতিবার `number` দ্বিগুণ হচ্ছে। Loop body চলার পর condition আবার পরীক্ষা করা হয়। `number`-এর value `16` হলে পরবর্তী condition `16 < 10` হলো `False`, তাই loop শেষ হয়।

## 7. `while` Loop with User Input

User-এর কাছ থেকে নির্দিষ্ট input না পাওয়া পর্যন্ত loop চালানো যায়।

```python
answer = ""

while answer != "yes":
    answer = input("Type yes to continue: ")

print("Continuing...")
```

যতক্ষণ User `yes` লিখবে না, ততক্ষণ input নেওয়া হবে।

উদাহরণস্বরূপ, User যদি `no`, তারপর `maybe`, এরপর `yes` লেখে, তাহলে `yes` দেওয়ার পরে loop শেষ হবে।

**Note:** String comparison case-sensitive। তাই `YES` ও `yes` সমান নয়।

## 8. `while` Loop vs `if` Statement

`if` এবং `while`—দুটিই condition ব্যবহার করে, কিন্তু তাদের কাজ আলাদা।

| `if` Statement | `while` Loop |
|---|---|
| Condition `True` হলে body একবার execute করে | Condition `True` থাকা পর্যন্ত বারবার execute করে |
| Repetition নিজে থেকে করে না | Repetition করে |
| প্রতিবার আবার পরীক্ষা করতে চাইলে নতুন execution দরকার | প্রতিটি iteration-এর আগে condition পরীক্ষা করে |

### Example Using `if`

```python
count = 1

if count <= 3:
    print(count)
```

Output:

```text
1
```

### Example Using `while`

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

Output:

```text
1
2
3
```

## 9. Important Rules

1. `while` keyword-এর পরে condition লিখতে হয়।
2. Condition-এর পরে colon (`:`) দিতে হয়।
3. Loop body সঠিকভাবে indent করতে হয়।
4. Condition শুরুতেই `False` হলে body execute হয় না।
5. প্রয়োজন অনুযায়ী condition পরিবর্তনের জন্য variable update করতে হয়।
6. Loop শেষ হওয়ার উপযুক্ত ব্যবস্থা থাকতে হবে।
7. Loop body-তে `break` ব্যবহার করেও loop আগেই বন্ধ করা যায়।

## 10. Common Beginner Mistakes

### Mistake 1: Colon দিতে ভুলে যাওয়া

ভুল:

```python
while count <= 5
    print(count)
```

সঠিক:

```python
while count <= 5:
    print(count)
```

### Mistake 2: Indentation ভুল করা

ভুল:

```python
count = 1

while count <= 3:
print(count)
count += 1
```

সঠিক:

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

### Mistake 3: Variable Update করতে ভুলে যাওয়া

```python
count = 1

while count <= 3:
    print(count)
```

এখানে `count` সবসময় `1` থাকে। Condition সবসময় `True`, তাই loop থামে না।

### Mistake 4: ভুল Condition লেখা

```python
count = 1

while count >= 3:
    print(count)
    count += 1
```

Output: কোনো output নেই।

কারণ শুরুতেই `1 >= 3` হলো `False`।

## 11. Practice Exercises

### Exercise 1

`while` loop কী?

### Exercise 2

নিচের code-এর output কী হবে?

```python
count = 1

while count <= 4:
    print(count)
    count += 1
```

### Exercise 3

নিচের code-এর output কী হবে?

```python
number = 8

while number < 5:
    print(number)
```

### Exercise 4

১ থেকে ১০ পর্যন্ত number print করার জন্য `while` loop লেখো।

### Exercise 5

১০ থেকে ১ পর্যন্ত countdown করার জন্য `while` loop লেখো।

### Exercise 6

১ থেকে ৫ পর্যন্ত number-এর যোগফল বের করার জন্য `while` loop লেখো।

### Exercise 7

নিচের code-এ কী সমস্যা রয়েছে?

```python
number = 1

while number <= 5:
    print(number)
    number -= 1
```

## 12. Answer Key

### Exercise 1

`while` loop হলো এমন একটি loop, যা condition `True` থাকা পর্যন্ত code বারবার execute করে।

### Exercise 2

```text
1
2
3
4
```

### Exercise 3

কোনো output নেই। Condition শুরুতেই `False`।

### Exercise 4

```python
number = 1

while number <= 10:
    print(number)
    number += 1
```

### Exercise 5

```python
number = 10

while number >= 1:
    print(number)
    number -= 1
```

### Exercise 6

```python
number = 1
total = 0

while number <= 5:
    total += number
    number += 1

print(total)
```

Output:

```text
15
```

### Exercise 7

`number` এক করে কমছে। ফলে এটি কখনো `5`-এর চেয়ে বড় হবে না; condition `number <= 5` সত্যই থাকবে এবং loop শেষ হবে না। এখানে `number += 1` ব্যবহার করতে হবে।

## 13. Chapter Progress Checklist

- [ ] `while` loop-এর সংজ্ঞা বুঝেছি।
- [ ] Syntax ও colon-এর ব্যবহার জানি।
- [ ] Condition কীভাবে পরীক্ষা হয় বুঝেছি।
- [ ] Variable update করতে পারি।
- [ ] Counter ও accumulator দিয়ে problem solve করতে পারি।
- [ ] Infinite loop-এর সাধারণ কারণ শনাক্ত করতে পারি।
- [ ] `while` loop দিয়ে counting, countdown ও sum করতে পারি।

## 14. Summary

- `while` loop condition `True` থাকা পর্যন্ত code execute করে।
- প্রতিটি iteration-এর আগে condition পরীক্ষা করা হয়।
- Condition শুরুতেই `False` হলে loop body চলে না।
- Variable update করা প্রয়োজন হলে তা সঠিকভাবে করতে হয়।
- ভুল condition বা ভুল update infinite loop তৈরি করতে পারে।
- `while` loop counting, calculation ও user input-এর মতো কাজে ব্যবহার করা যায়।

**Next Topic:** `10_while_Loop_Syntax_and_Execution.md`
