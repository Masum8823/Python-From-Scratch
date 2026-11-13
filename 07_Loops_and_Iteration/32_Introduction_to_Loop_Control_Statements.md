# 32. Introduction to Loop Control Statements

## 1. Introduction

Python-এ loop control statements ব্যবহার করে loop-এর execution নিয়ন্ত্রণ করা যায়।

সাধারণত তিনটি গুরুত্বপূর্ণ statement রয়েছে:

1. `break`
2. `continue`
3. `pass`

এগুলো দেখতে একই রকম মনে হলেও, প্রতিটির কাজ আলাদা।

- `break` — loop সম্পূর্ণ বন্ধ করে।
- `continue` — বর্তমান iteration-এর বাকি অংশ বাদ দিয়ে পরবর্তী iteration শুরু করে।
- `pass` — কোনো কাজ করে না; এটি একটি placeholder statement।

## 2. What Are Loop Control Statements?

Loop control statements হলো এমন statement, যেগুলো loop-এর execution flow পরিবর্তন করতে পারে বা নির্দিষ্ট code block-এ কোনো কাজ না করেও syntax পূরণ করতে পারে।

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

এখানে `number`-এর value `3` হলে `break` loop বন্ধ করে দেয়।

সাধারণভাবে loop `1` থেকে `5` পর্যন্ত চলার কথা ছিল, কিন্তু control statement-এর কারণে এটি আগেই শেষ হয়েছে।

## 3. The `break` Statement

`break` statement ব্যবহার করে loop-কে সঙ্গে সঙ্গে শেষ করা যায়।

### Example

```python
for number in range(1, 6):
    if number == 4:
        break

    print(number)
```

**Output:**

```text
1
2
3
```

### Explanation

1. প্রথমে `number = 1`, তাই `1` print হয়।
2. এরপর `2` এবং `3` print হয়।
3. `number = 4` হলে condition সত্য হয়।
4. `break` loop বন্ধ করে দেয়।
5. `4` ও `5` print হয় না।

### When to use `break`

- নির্দিষ্ট value পাওয়া গেলে search বন্ধ করতে।
- User-এর নির্দিষ্ট command পেলে menu loop বন্ধ করতে।
- কোনো condition পূরণ হলে loop থেকে বের হতে।

## 4. The `continue` Statement

`continue` statement বর্তমান iteration-এর বাকি অংশ বাদ দিয়ে পরবর্তী iteration শুরু করে।

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
- `number = 3` হলে `continue` execute হয়।
- তাই `print(number)` statement-টি ওই iteration-এ execute হয় না।
- Loop পরবর্তী value `4` নিয়ে আবার চলে।

**মনে রাখবে:** `continue` loop বন্ধ করে না। এটি শুধু বর্তমান iteration-এর বাকি অংশ বাদ দেয়।

### When to use `continue`

- নির্দিষ্ট value skip করতে।
- শুধু valid data process করতে।
- কোনো condition পূরণ হলে বর্তমান iteration-এর বাকি কাজ বাদ দিতে।

## 5. The `pass` Statement

`pass` একটি null statement। এটি execute হলে কোনো কাজ করে না।

Python-এ কোনো block-এর মধ্যে statement থাকা প্রয়োজন, কিন্তু এখনো সেখানে code লিখতে প্রস্তুত না হলে `pass` ব্যবহার করা যায়।

### Example

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

### Explanation

`number = 2` হলে `pass` execute হয়, কিন্তু কোনো পরিবর্তন ঘটে না। এরপর `print(number)` execute হয় এবং `2` print হয়।

**মনে রাখবে:** `pass` কোনো value skip করে না, loop বন্ধ করে না, এবং নিজে থেকে পরবর্তী iteration-এও যায় না।

### When to use `pass`

- Function বা class-এর body পরে পূরণ করার জন্য।
- কোনো condition-এর block সাময়িকভাবে খালি রাখতে।
- Program-এর structure আগে তৈরি করে implementation পরে লেখার জন্য।

Example:

```python
def calculate_result():
    pass
```

এটি একটি syntactically valid function definition, কিন্তু function-টি এখনো কোনো কাজ করে না।

## 6. Comparing `break`, `continue`, and `pass`

| Statement | কাজ | Loop বন্ধ করে? |
|---|---|---|
| `break` | Loop থেকে বের হয় | হ্যাঁ |
| `continue` | বর্তমান iteration-এর বাকি অংশ বাদ দেয় | না |
| `pass` | কোনো কাজ করে না | না |

### সহজভাবে মনে রাখার কৌশল

- `break` = Stop the loop
- `continue` = Skip this iteration
- `pass` = Do nothing

## 7. Example: All Three Statements

নিচের code-এ তিনটি statement আলাদাভাবে ব্যবহার করা হয়েছে।

```python
for number in range(1, 6):
    if number == 2:
        continue

    if number == 4:
        break

    if number == 3:
        pass

    print(number)
```

**Output:**

```text
1
3
```

### Dry Run Table

| `number` | Action | Output |
|---:|---|---|
| 1 | কোনো control statement কার্যকর নয় | 1 |
| 2 | `continue` | কিছু print হয় না |
| 3 | `pass`, তারপর print | 3 |
| 4 | `break` | Loop শেষ |
| 5 | এই iteration-এ পৌঁছায় না | কিছু print হয় না |

এখানে `pass`-এর পরেও `print(number)` চলে, কিন্তু `continue` ওই statement-টি skip করে। আর `break` পুরো loop শেষ করে দেয়।

## 8. Using `break` in a `while` Loop

```python
number = 1

while number <= 10:
    if number == 5:
        break

    print(number)
    number += 1
```

**Output:**

```text
1
2
3
4
```

`number`-এর value `5` হলে loop বন্ধ হয়ে যায়।

## 9. Using `continue` in a `while` Loop

```python
number = 0

while number < 5:
    number += 1

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

এখানে `number += 1`-এর পরে `continue` আসায় `number = 3` হলে সেটি print হয় না।

**গুরুত্বপূর্ণ:** `while` loop-এ `continue` ব্যবহার করার সময় condition-এ প্রভাব ফেলা variable যেন যথাযথভাবে update হয়, তা নিশ্চিত করতে হবে। অন্যথায় infinite loop হতে পারে।

## 10. Using `pass` in Conditional Blocks

```python
age = 20

if age >= 18:
    pass
else:
    print("Underage")
```

এখানে `age >= 18` সত্য হওয়ায় `pass` execute হয়। কোনো output আসে না।

এটি syntax-এর দিক থেকে বৈধ, তবে বাস্তব program-এ কাজের প্রয়োজন না থাকলে অকারণে `pass` ব্যবহার করা উচিত নয়।

## 11. Common Mistakes

### Mistake 1: Thinking `continue` stops the loop

ভুল ধারণা: `continue` loop বন্ধ করে।

সঠিক ধারণা: `continue` শুধু বর্তমান iteration-এর বাকি অংশ বাদ দেয়।

### Mistake 2: Thinking `pass` skips an iteration

```python
for number in range(1, 4):
    pass
    print(number)
```

**Output:**

```text
1
2
3
```

`pass` কোনো statement skip করে না।

### Mistake 3: Forgetting the effect of `break`

`break` execute হওয়ার পরে একই loop-এর বাকি iteration আর হয় না।

### Mistake 4: Causing an infinite loop with `continue`

ভুল:

```python
number = 1

while number <= 5:
    if number == 3:
        continue

    number += 1
```

এখানে `number` যখন `3` হয়, তখন `continue`-এর কারণে `number += 1` আর execute হয় না। ফলে `number` সব সময় `3` থেকে যায় এবং loop চলতেই থাকে।

সঠিক:

```python
number = 1

while number <= 5:
    if number == 3:
        number += 1
        continue

    print(number)
    number += 1
```

**Output:**

```text
1
2
4
5
```

## 12. Practice Exercises

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
for number in range(1, 4):
    pass
    print(number)
```

### Exercise 4: Identify the Statement

কোন statement loop সম্পূর্ণ বন্ধ করে?

- `pass`
- `continue`
- `break`

### Exercise 5: Write a Program

`1` থেকে `10` পর্যন্ত সংখ্যা print করো, কিন্তু `5` skip করবে। `continue` ব্যবহার করতে হবে।

### Exercise 6: Write a Program

`1` থেকে counting শুরু করে `7` পেলে loop বন্ধ করো। `break` ব্যবহার করতে হবে।

## 13. Practice Answer Key

### Answer 1

```text
1
2
3
```

`4` হলে `break` execute হয়।

### Answer 2

```text
1
3
4
5
```

`2`-এর iteration skip হয়েছে।

### Answer 3

```text
1
2
3
```

`pass` কোনো কাজ করে না; তাই `print()` execute হয়।

### Answer 4

**Answer: `break`**

### Answer 5

```python
for number in range(1, 11):
    if number == 5:
        continue

    print(number)
```

### Answer 6

```python
for number in range(1, 11):
    if number == 7:
        break

    print(number)
```

## 14. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `break` loop বন্ধ করে।
- `continue` বর্তমান iteration-এর বাকি অংশ skip করে।
- `pass` কোনো কাজ করে না।
- তিনটি statement `for` ও `while` loop-এ ব্যবহার করা যায়।
- `while` loop-এ `continue` ব্যবহার করার সময় variable update-এর অবস্থান গুরুত্বপূর্ণ।

## 15. Completion Checklist

- [ ] `break` কী করে বুঝি।
- [ ] `continue` কী করে বুঝি।
- [ ] `pass`-এর ব্যবহার বুঝি।
- [ ] তিনটি statement-এর পার্থক্য বলতে পারি।
- [ ] `for` ও `while` loop-এ এগুলো ব্যবহার করতে পারি।
- [ ] `continue` থেকে তৈরি হতে পারে এমন infinite loop শনাক্ত করতে পারি।

**Next Topic:** `33_The_break_Statement.md`
