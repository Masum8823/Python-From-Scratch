# 13. Updating Variables Inside a Loop

## 1. Introduction

Loop-এর ভিতরে variable-এর value পরিবর্তন করাকে **updating a variable** বলা হয়।

অনেক loop-এ প্রতিবার iteration-এর পর variable-এর value পরিবর্তন করতে হয়। এতে loop-এর condition একসময় `False` হতে পারে এবং loop শেষ হয়।

উদাহরণ:

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

Output:

```text
1
2
3
4
5
```

এখানে `count += 1` প্রতিবার `count`-এর value এক করে বাড়ায়।

যদি variable update না করা হতো, তাহলে condition সবসময় `True` থাকত এবং loop অনির্দিষ্টকাল চলতে পারত।

## 2. What Is Variable Updating?

Variable updating মানে variable-এর বর্তমান value পরিবর্তন করে নতুন value assign করা।

উদাহরণ:

```python
number = 10

number = number + 5

print(number)
```

Output:

```text
15
```

এখানে প্রথমে `number`-এর value `10`। এরপর `number + 5` হিসাব করে `15` variable-টিতে assign করা হয়েছে।

আরও একটি উদাহরণ:

```python
number = 10
number = number - 3

print(number)
```

Output:

```text
7
```

**মনে রাখবে:** `number = number + 5`-এ `=` assignment operator। এটি mathematical equation নয়; ডান পাশের expression হিসাব করে ফলাফল বাম পাশের variable-এ রাখা হয়।

## 3. Incrementing a Variable

Variable-এর value বাড়ানোকে সাধারণভাবে **incrementing** বলা হয়।

### 3.1 Increment by 1

```python
count = 0

count = count + 1
print(count)

count = count + 1
print(count)

count = count + 1
print(count)
```

Output:

```text
1
2
3
```

প্রতিবার `count` এক করে বাড়ছে।

### 3.2 Using the `+=` Operator

Python-এ `count += 1` হলো `count = count + 1`-এর সংক্ষিপ্ত রূপ।

```python
count = 0

count += 1
print(count)

count += 1
print(count)

count += 1
print(count)
```

Output:

```text
1
2
3
```

দুটি পদ্ধতির ফলাফল এখানে একই।

### 3.3 Increment by a Different Amount

Variable শুধু এক করে বাড়াতে হয় না। প্রয়োজন অনুযায়ী অন্য পরিমাণেও বাড়ানো যায়।

```python
number = 5

number += 2
print(number)

number += 3
print(number)

number += 10
print(number)
```

Output:

```text
7
10
20
```

## 4. Decrementing a Variable

Variable-এর value কমানোকে সাধারণভাবে **decrementing** বলা হয়।

### 4.1 Decrement by 1

```python
count = 5

count -= 1
print(count)

count -= 1
print(count)

count -= 1
print(count)
```

Output:

```text
4
3
2
```

### 4.2 Using the `-=` Operator

`count -= 1` হলো `count = count - 1`-এর সংক্ষিপ্ত রূপ।

উদাহরণ:

```python
number = 20

number -= 5

print(number)
```

Output:

```text
15
```

Decrement সাধারণত countdown, reverse counting এবং কিছু condition-controlled loop-এ কাজে লাগে।

## 5. Updating Variables in a `while` Loop

`while` loop-এ variable update করা বিশেষভাবে গুরুত্বপূর্ণ। কারণ loop-এর condition variable-এর value-এর ওপর নির্ভর করতে পারে।

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

Output:

```text
1
2
3
4
5
```

এখানে:

1. `count = 1` দিয়ে শুরু হয়।
2. `count <= 5` পরীক্ষা করা হয়।
3. Condition `True` হলে `count` print হয়।
4. `count += 1` দিয়ে value বাড়ে।
5. আবার condition পরীক্ষা করা হয়।
6. `count` যখন `6` হয়, condition `False` হয়ে যায়।

### Dry Run Table

| Iteration | শুরুতে `count` | Condition | Printed value | Update-এর পর |
|---:|---:|---|---:|---:|
| 1 | 1 | `True` | 1 | 2 |
| 2 | 2 | `True` | 2 | 3 |
| 3 | 3 | `True` | 3 | 4 |
| 4 | 4 | `True` | 4 | 5 |
| 5 | 5 | `True` | 5 | 6 |
| পরবর্তী check | 6 | `False` | কিছুই নয় | Loop শেষ |

## 6. Updating Before and After Printing

Loop body-তে variable update করার অবস্থান output পরিবর্তন করতে পারে।

### Example A: Print Before Updating

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

### Example B: Update Before Printing

```python
count = 1

while count <= 3:
    count += 1
    print(count)
```

Output:

```text
2
3
4
```

দ্বিতীয় উদাহরণে প্রথমে `count` এক করে বাড়ানো হচ্ছে, তারপর print করা হচ্ছে। তাই প্রথম output `2`।

**Exam tip:** Loop-এর output বের করার সময় body-র statement কোন ক্রমে লেখা আছে, সেটা খেয়াল করবে।

## 7. Updating Variables in a Countdown Loop

Countdown-এর ক্ষেত্রে সাধারণত variable কমানো হয়।

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

`count`-এর value `5` থেকে শুরু করে প্রতিবার এক করে কমছে। যখন `count` হয় `0`, তখন `count >= 1` condition `False` হয়ে যায়।

### Dry Run

| `count` | `count >= 1` | Action |
|---:|---|---|
| 5 | `True` | 5 print |
| 4 | `True` | 4 print |
| 3 | `True` | 3 print |
| 2 | `True` | 2 print |
| 1 | `True` | 1 print |
| 0 | `False` | Loop শেষ |

## 8. Updating by More Than One

একবারে একের বেশি করে variable বাড়ানো বা কমানো যায়।

### Example: Print Even Numbers

```python
number = 2

while number <= 10:
    print(number)
    number += 2
```

Output:

```text
2
4
6
8
10
```

এখানে `number += 2` ব্যবহার করায় প্রতিবার জোড় সংখ্যার পরের জোড় সংখ্যায় পৌঁছানো হচ্ছে।

### Example: Count Backward by 2

```python
number = 10

while number >= 2:
    print(number)
    number -= 2
```

Output:

```text
10
8
6
4
2
```

## 9. Using a Variable Update to Build a Sum

Variable updating শুধু counting-এর জন্য নয়; যোগফল হিসাব করতেও কাজে লাগে।

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

এখানে দুটি variable-এর আলাদা কাজ রয়েছে:

- `number` — কোন সংখ্যা যোগ করা হবে, তা নিয়ন্ত্রণ করে।
- `total` — এখন পর্যন্ত যোগ করা সংখ্যাগুলোর যোগফল ধরে রাখে।

### Dry Run Table

| `number` | `total` update | নতুন `total` |
|---:|---|---:|
| 1 | `0 + 1` | 1 |
| 2 | `1 + 2` | 3 |
| 3 | `3 + 3` | 6 |
| 4 | `6 + 4` | 10 |
| 5 | `10 + 5` | 15 |

এরপর `number` হয় `6`। Condition `6 <= 5` মিথ্যা, তাই loop শেষ হয়।

## 10. What Happens If We Forget to Update?

নিচের code-টি দেখো:

```python
count = 1

while count <= 5:
    print(count)
```

এই code-এ `count`-এর value পরিবর্তিত হচ্ছে না। এটি সবসময় `1` থাকছে।

তাই `count <= 5` সবসময় `True` এবং `1` বারবার print হতে থাকবে। একে **infinite loop** বলা হয়।

সঠিক code:

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

এখানে `count += 1` condition-টিকে শেষ পর্যন্ত `False` করে।

## 11. What Happens If We Update in the Wrong Direction?

Condition ও update-এর direction একে অপরের সঙ্গে সামঞ্জস্যপূর্ণ হওয়া প্রয়োজন।

ভুল উদাহরণ:

```python
count = 1

while count <= 5:
    print(count)
    count -= 1
```

এখানে `count` বাড়ার পরিবর্তে কমছে:

`1, 0, -1, -2, -3, ...`

প্রতিটি value-ই `5`-এর চেয়ে ছোট বা সমান। তাই condition কখনো `False` হবে না।

সঠিক code:

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

**মূল নিয়ম:** Condition এবং update এমন হতে হবে যেন প্রয়োজনীয় iteration-এর পর condition `False` হয়।

## 12. Counter vs Accumulator

Loop-এ প্রায়ই দুটি ধরনের variable ব্যবহৃত হয়।

| বিষয় | Counter | Accumulator |
|---|---|---|
| কাজ | কতবার বা কয়টি item হয়েছে গণনা | মোট value জমা রাখা |
| সাধারণ শুরু | `0` | যোগফলের জন্য `0` |
| Update | `count += 1` | `total += value` |
| উদাহরণ | কয়টি সংখ্যা জোড় | সংখ্যাগুলোর যোগফল |

### Example

```python
count = 0
total = 0
number = 1

while number <= 5:
    count += 1
    total += number
    number += 1

print("Count:", count)
print("Total:", total)
```

Output:

```text
Count: 5
Total: 15
```

এখানে `count` iteration-এর সংখ্যা গণনা করছে, আর `total` যোগফল জমা করছে।

## 13. Common Mistakes

### Mistake 1: Forgetting the Update

```python
count = 1

while count <= 3:
    print(count)
```

সমস্যা: `count` পরিবর্তিত হচ্ছে না।

### Mistake 2: Wrong Update Operator

```python
count = 1

while count <= 3:
    print(count)
    count -= 1
```

সমস্যা: Condition-এর সঙ্গে update-এর direction মেলে না।

### Mistake 3: Updating Too Early

```python
count = 1

while count < 4:
    count += 1
    print(count)
```

Output হবে `2, 3, 4`; `1` print হবে না।

### Mistake 4: Incorrect Initial Value

```python
count = 10

while count <= 5:
    print(count)
    count += 1
```

কোনো output হবে না। শুরুতেই condition `False`।

### Mistake 5: Confusing Counter and Accumulator

```python
total = 0

while total < 5:
    total += 1
```

এই code শেষ পর্যন্ত চলবে, কিন্তু এখানে `total` আসলে যোগফল নয়; এটি শুধু এক করে বাড়ছে। Variable-এর নাম ও কাজের মধ্যে মিল রাখা উচিত।

## 14. Practice Exercises

### Exercise 1

`count += 1` কোন কাজ করে?

### Exercise 2

নিচের code-এর output কী?

```python
number = 2

while number <= 8:
    print(number)
    number += 2
```

### Exercise 3

নিচের code-এর output কী?

```python
count = 3

while count >= 1:
    print(count)
    count -= 1
```

### Exercise 4

নিচের code-এ সমস্যা কী?

```python
number = 1

while number <= 4:
    print(number)
    number += 0
```

### Exercise 5

নিচের code-এর output কী?

```python
count = 1

while count <= 3:
    count += 1
    print(count)
```

### Exercise 6

১ থেকে ১০ পর্যন্ত সংখ্যার যোগফল বের করার program লেখো।

### Exercise 7

১০ থেকে ২ পর্যন্ত জোড় সংখ্যাগুলো descending order-এ print করো।

### Exercise 8

নিচের code-এর output কী?

```python
count = 0
total = 0

while count < 4:
    count += 1
    total += count

print(count)
print(total)
```

## 15. Answer Key

### Exercise 1

`count += 1` হলো `count = count + 1`-এর সংক্ষিপ্ত রূপ। এটি `count`-এর value এক করে বাড়ায়।

### Exercise 2

```text
2
4
6
8
```

### Exercise 3

```text
3
2
1
```

### Exercise 4

`number += 0` value পরিবর্তন করে না। ফলে condition সবসময় `True` থাকে এবং infinite loop তৈরি হয়।

### Exercise 5

```text
2
3
4
```

### Exercise 6

```python
number = 1
total = 0

while number <= 10:
    total += number
    number += 1

print("Sum:", total)
```

Output:

```text
Sum: 55
```

### Exercise 7

```python
number = 10

while number >= 2:
    print(number)
    number -= 2
```

Output:

```text
10
8
6
4
2
```

### Exercise 8

```text
4
10
```

`count` চারবার বাড়ে এবং `total`-এ `1 + 2 + 3 + 4 = 10` জমা হয়।

## 16. Chapter Progress Checklist

- [ ] Variable updating কী বুঝেছি।
- [ ] `+=` দিয়ে increment করতে পারি।
- [ ] `-=` দিয়ে decrement করতে পারি।
- [ ] Loop-এর মধ্যে update-এর অবস্থান output-এ কী প্রভাব ফেলে বুঝেছি।
- [ ] Counter ও accumulator-এর পার্থক্য বুঝেছি।
- [ ] Variable update না করলে infinite loop কেন হয় বুঝেছি।
- [ ] Condition ও update-এর direction মিলিয়ে loop লিখতে পারি।

## 17. Summary

- Variable updating মানে variable-এর value পরিবর্তন করা।
- `count += 1` value এক করে বাড়ায়।
- `count -= 1` value এক করে কমায়।
- Loop-এর condition ও update একসঙ্গে কাজ করে।
- Counter গণনা করে, accumulator সাধারণত মোট value জমা করে।
- ভুল বা অনুপস্থিত update infinite loop তৈরি করতে পারে।

**Next Topic:** `14_Counter_Controlled_while_Loops.md`
