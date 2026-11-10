# 10. while Loop Syntax and Execution

## 1. Introduction

Python-এর `while` loop ব্যবহার করে একটি condition `True` থাকা পর্যন্ত code বারবার execute করা যায়।

কিন্তু loop সঠিকভাবে বুঝতে হলে শুধু syntax জানলেই হবে না। জানতে হবে:

- Loop কোথা থেকে শুরু হয়।
- Condition কখন check হয়।
- Loop body কখন execute হয়।
- Variable কখন update হয়।
- Condition `False` হলে কী ঘটে।

এই বিষয়গুলো বোঝার জন্য আমরা syntax, execution flow এবং dry run শিখব।

## 2. Basic Syntax of a while Loop

Python-এ `while` loop-এর সাধারণ syntax:

```python
while condition:
    statement_1
    statement_2
    statement_3
```

এখানে:

| অংশ | কাজ |
|---|---|
| `while` | Loop শুরু করে |
| `condition` | Loop চলবে কি না নির্ধারণ করে |
| `:` | Loop body শুরু হওয়ার নির্দেশ দেয় |
| Indented statements | Condition `True` হলে execute হয় |

Condition অবশ্যই এমন expression হতে হবে, যার truth value Python পরীক্ষা করতে পারে।

### Example

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

## 3. Understanding Each Part

### 3.1 Initialization

```python
count = 1
```

Initialization মানে variable-এর প্রাথমিক value নির্ধারণ করা।

এখানে `count`-এর শুরুতে value `1`।

### 3.2 Condition

```python
while count <= 3:
```

এই condition নির্ধারণ করে loop body execute হবে কি না।

- `count`-এর value `1`, `2` বা `3` হলে condition `True`।
- `count`-এর value `4` হলে condition `False`।

### 3.3 Loop Body

```python
print(count)
```

Condition `True` হলে এই statement execute হয়।

### 3.4 Updating the Variable

```python
count += 1
```

এটি `count`-এর value এক বাড়ায়।

সমতুল্য statement:

```python
count = count + 1
```

Variable update না করলে এই উদাহরণে loop শেষ হবে না।

## 4. Step-by-Step Execution Flow

একটি `while` loop সাধারণত এভাবে কাজ করে:

1. প্রয়োজনীয় variable initialize করা হয়।
2. Condition পরীক্ষা করা হয়।
3. Condition `True` হলে loop body execute হয়।
4. Body-এর statement-গুলো ক্রমানুসারে চলে।
5. Body শেষ হলে condition আবার পরীক্ষা করা হয়।
6. Condition `True` থাকলে আবার body execute হয়।
7. Condition `False` হলে loop শেষ হয় এবং পরবর্তী statement execute হয়।

### Flowchart

```text
       Start
         |
         v
 Initialize Variable
         |
         v
   Check Condition
         |
     +---+---+
     |       |
   True     False
     |       |
     v       v
  Loop Body  Exit Loop
     |
     v
  Update Variable
     |
     +-------> Check Condition
```

**মনে রাখবে:** Variable update loop body-এর অংশ হলে সেটি execute হওয়ার পর condition আবার check হয়। সব `while` loop-এ update statement থাকা বাধ্যতামূলক নয়; তবে loop শেষ হওয়ার কোনো উপযুক্ত ব্যবস্থা থাকা জরুরি।

## 5. Dry Run of a while Loop

Dry run হলো code execute না করেও প্রতিটি ধাপে variable-এর value ও output অনুসরণ করা।

নিচের code দেখো:

```python
count = 1

while count <= 3:
    print(count)
    count += 1

print("Finished")
```

### Dry Run Table

| Step | `count` | Condition | Action |
|---:|---:|---|---|
| 1 | 1 | `1 <= 3` → `True` | `1` print |
| 2 | 2 | `2 <= 3` → `True` | `2` print |
| 3 | 3 | `3 <= 3` → `True` | `3` print |
| 4 | 4 | `4 <= 3` → `False` | Loop শেষ |
| 5 | 4 | — | `Finished` print |

Output:

```text
1
2
3
Finished
```

এখানে `Finished` loop body-এর বাইরে থাকায় loop শেষ হওয়ার পরে একবার execute হয়।

## 6. Condition Is Checked Before the Loop Body

Python-এর `while` loop-এ প্রতিটি iteration-এর আগে condition পরীক্ষা করা হয়।

### Example

```python
number = 10

while number < 5:
    print("Inside loop")

print("Outside loop")
```

Output:

```text
Outside loop
```

কারণ:

```python
10 < 5
```

এর result `False`।

তাই `Inside loop` print হয় না। সরাসরি loop-এর পরের statement execute হয়।

## 7. The Order of Statements Matters

Loop body-এর statement-গুলোর ক্রম output পরিবর্তন করতে পারে।

### Example A: Print Then Update

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

### Example B: Update Then Print

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

দ্বিতীয় উদাহরণে প্রথমে `count` এক বাড়ছে, তারপর print হচ্ছে। তাই প্রথম output `1` নয়, `2`।

**Exam Tip:** Code trace করার সময় loop body-এর statement-গুলো উপরে থেকে নিচে ক্রমানুসারে অনুসরণ করবে।

## 8. Execution with a Counter

Counter ব্যবহার করে কতবার loop execute হচ্ছে তা track করা যায়।

```python
count = 0

while count < 4:
    count += 1
    print("Iteration:", count)
```

Output:

```text
Iteration: 1
Iteration: 2
Iteration: 3
Iteration: 4
```

এখানে `count` প্রথমে `0`। প্রতিটি iteration-এ এটি এক বাড়ে। `count` যখন `4`, তখন body শেষ হয় এবং পরবর্তী condition check-এ loop বন্ধ হয়।

## 9. Execution with an Accumulator

Accumulator ব্যবহার করে loop-এর মধ্যে calculation-এর result জমা রাখা যায়।

```python
number = 1
total = 0

while number <= 4:
    total += number
    number += 1

print("Total:", total)
```

Output:

```text
Total: 10
```

### Dry Run Table

| Iteration | `number` | আগের `total` | নতুন `total` |
|---:|---:|---:|---:|
| শুরু | — | — | 0 |
| 1 | 1 | 0 | 1 |
| 2 | 2 | 1 | 3 |
| 3 | 3 | 3 | 6 |
| 4 | 4 | 6 | 10 |

শেষ iteration-এর পরে `number` হয় `5`। এরপর `number <= 4` condition `False` হয়, ফলে loop শেষ হয়।

## 10. What Happens When the Condition Becomes False?

Condition `False` হলে:

1. Loop body আর execute হয় না।
2. Loop থেকে control বের হয়ে আসে।
3. Loop-এর পরের statement execute হয়।

### Example

```python
count = 1

while count <= 2:
    print("Loop")
    count += 1

print("Done")
```

Output:

```text
Loop
Loop
Done
```

`Done` loop-এর বাইরে থাকায় এটি loop শেষ হওয়ার পরে execute হয়।

## 11. Common Syntax Errors

### Error 1: Missing Colon

ভুল:

```python
while count <= 3
    print(count)
```

সঠিক:

```python
while count <= 3:
    print(count)
```

### Error 2: Incorrect Indentation

ভুল:

```python
while count <= 3:
print(count)
```

সঠিক:

```python
while count <= 3:
    print(count)
```

### Error 3: Missing Initialization

```python
while count <= 3:
    print(count)
    count += 1
```

যদি `count` আগে define না করা থাকে, তাহলে `NameError` হবে।

### Error 4: Incorrect Update

```python
count = 1

while count <= 3:
    print(count)
    count -= 1
```

এখানে `count` কমতে থাকে। তাই `count <= 3` condition `True`-ই থাকে এবং loop শেষ হয় না।

## 12. Practice Exercises

### Exercise 1

`while` loop-এর basic syntax লেখো।

### Exercise 2

নিচের code-এর output কী হবে?

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

### Exercise 3

নিচের code-এর output কী হবে?

```python
count = 1

while count <= 3:
    count += 1
    print(count)
```

### Exercise 4

নিচের code-এর output কী হবে?

```python
number = 5

while number < 2:
    print(number)

print("End")
```

### Exercise 5

নিচের code-এর output কী হবে?

```python
number = 1
total = 0

while number <= 3:
    total += number
    number += 1

print(total)
```

### Exercise 6

নিচের code-এ কেন loop শেষ হয় না?

```python
count = 1

while count <= 5:
    print(count)
    count += 0
```

### Exercise 7

নিচের code-এর output অনুমান করো।

```python
count = 1

while count < 4:
    print(count)
    count += 1

print(count)
```

## 13. Answer Key

### Exercise 1

```python
while condition:
    statement
```

### Exercise 2

```text
1
2
3
```

### Exercise 3

```text
2
3
4
```

কারণ print করার আগে `count` এক বাড়ানো হচ্ছে।

### Exercise 4

```text
End
```

কারণ `5 < 2` হলো `False`, তাই loop body execute হয় না।

### Exercise 5

```text
6
```

কারণ \(1 + 2 + 3 = 6\)।

### Exercise 6

`count += 0` করলে `count`-এর value পরিবর্তিত হয় না। এটি `1`-ই থাকে, তাই `count <= 5` সবসময় `True` হয়।

### Exercise 7

```text
1
2
3
4
```

Loop body-তে `1`, `2`, `3` print হয়। এরপর `count` হয় `4`; condition `False` হওয়ায় loop শেষ হয়। তারপর বাইরের `print(count)` `4` print করে।

## 14. Chapter Progress Checklist

- [ ] `while` loop-এর syntax লিখতে পারি।
- [ ] Initialization, condition, body ও update শনাক্ত করতে পারি।
- [ ] Loop-এর execution flow ব্যাখ্যা করতে পারি।
- [ ] Dry run table তৈরি করতে পারি।
- [ ] Statement-এর ক্রম output-এ কীভাবে প্রভাব ফেলে বুঝেছি।
- [ ] Condition `False` হলে কী ঘটে জানি।
- [ ] Infinite loop-এর সাধারণ কারণ শনাক্ত করতে পারি।

## 15. Summary

- `while` loop-এর condition body execute করার আগে পরীক্ষা করা হয়।
- Condition `True` হলে body execute হয়; `False` হলে loop শেষ হয়।
- Loop body-এর statement-গুলো ক্রমানুসারে execute হয়।
- Counter ও accumulator ব্যবহার করে calculation করা যায়।
- Variable update-এর ভুলে infinite loop হতে পারে।
- Dry run করে loop-এর output ও variable-এর value নির্ণয় করা যায়।

**Next Topic:** `11_Writing_Your_First_while_Loop.md`
