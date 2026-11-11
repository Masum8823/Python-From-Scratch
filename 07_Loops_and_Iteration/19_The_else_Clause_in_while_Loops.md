# 19. The `else` Clause in `while` Loops

## 1. Introduction

Python-এ `while` loop-এর সঙ্গে `else` clause ব্যবহার করা যায়।

সাধারণত loop-এর condition `False` হয়ে গেলে loop শেষ হয়। এইভাবে loop শেষ হলে তার `else` block execute হয়।

কিন্তু loop-এর মধ্যে `break` statement execute হয়ে loop বন্ধ হলে `else` block execute হয় না।

**মনে রাখার নিয়ম:**

- Condition `False` হয়ে loop শেষ হলে → `else` execute হয়।
- `break` দিয়ে loop বন্ধ হলে → `else` execute হয়।

## 2. Syntax of `while-else`

```python
while condition:
    # Loop body
    # Repeated statements

else:
    # Executes when the loop ends normally
```

এখানে:

- `while` condition পরীক্ষা করে।
- Condition `True` হলে loop body execute হয়।
- Condition `False` হলে loop শেষ হয়।
- Loop `break` দিয়ে বন্ধ না হলে `else` block execute হয়।

**গুরুত্বপূর্ণ:** `else` block হলো `while`-এর সমান indentation level-এ। এটি `while` body-এর ভিতরে লেখা হয় না।

## 3. Basic Example

```python
number = 1

while number <= 3:
    print(number)
    number += 1

else:
    print("Loop finished")
```

Output:

```text
1
2
3
Loop finished
```

### Explanation

1. `number = 1` দিয়ে শুরু হয়।
2. `number <= 3` সত্য থাকায় loop চলে।
3. প্রতিবার number print হওয়ার পর `number += 1` হয়।
4. `number` যখন `4` হয়, condition `False` হয়।
5. Loop স্বাভাবিকভাবে শেষ হওয়ায় `else` execute হয়।

## 4. Understanding the Execution Flow

`while-else`-এর execution flow:

1. Condition পরীক্ষা করো।
2. Condition `True` হলে loop body execute করো।
3. প্রয়োজন অনুযায়ী variable update করো।
4. আবার condition পরীক্ষা করো।
5. Condition `False` হলে loop থেকে বের হয়ে `else` execute করো।
6. কিন্তু `break` execute হলে সরাসরি loop থেকে বের হয়ে যাবে এবং `else` skip হবে।

## 5. Example with a Counter

```python
count = 1

while count <= 5:
    print("Count:", count)
    count += 1

else:
    print("Counting completed")
```

Output:

```text
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
Counting completed
```

এখানে counter `5` থেকে `6` হয়। এরপর condition `False` হওয়ায় `else` execute হয়।

## 6. What Happens When `break` Is Used?

`break` loop-কে সঙ্গে সঙ্গে বন্ধ করে দেয়। এভাবে loop বন্ধ হলে `else` execute হয় না।

```python
number = 1

while number <= 5:
    print(number)

    if number == 3:
        break

    number += 1

else:
    print("Loop finished normally")
```

Output:

```text
1
2
3
```

এখানে `number == 3` হলে `break` execute হয়। তাই `while`-এর `else` block skip করা হয়।

**মনে রাখবে:** `else` execute হওয়া নির্ভর করে loop স্বাভাবিকভাবে শেষ হয়েছে কি না, শুধু loop-এর body কতবার execute হয়েছে তার ওপর নয়।

## 7. `while-else` Without `break`

```python
number = 1

while number < 3:
    print(number)
    number += 1

else:
    print("Else block executed")
```

Output:

```text
1
2
Else block executed
```

এখানে কোনো `break` নেই। Condition `False` হওয়ায় `else` execute হয়।

## 8. `while-else` With `break`

```python
number = 1

while number < 5:
    if number == 3:
        break

    print(number)
    number += 1

else:
    print("Loop completed")
```

Output:

```text
1
2
```

যখন `number == 3` হয়, তখন `break` execute হয়। তাই `else` block execute হয় না।

## 9. Practical Example: Searching for a Number

ধরো, একটি list-এর মধ্যে নির্দিষ্ট number খুঁজতে হবে। Number পাওয়া গেলে search বন্ধ হবে; না পাওয়া গেলে জানানো হবে যে number-টি পাওয়া যায়নি।

```python
numbers = [10, 20, 30, 40, 50]
target = 30
index = 0

while index < len(numbers):
    if numbers[index] == target:
        print("Number found:", target)
        break

    index += 1

else:
    print("Number not found")
```

Output:

```text
Number found: 30
```

এখানে `30` পাওয়া গেলে `break` loop বন্ধ করে দেয়। তাই `else` execute হয় না।

### When the Number Is Not Found

```python
numbers = [10, 20, 30, 40, 50]
target = 60
index = 0

while index < len(numbers):
    if numbers[index] == target:
        print("Number found:", target)
        break

    index += 1

else:
    print("Number not found")
```

Output:

```text
Number not found
```

এখানে সব element পরীক্ষা করার পর `index`-এর value `5` হয়। তখন `index < len(numbers)` condition `False` হয়। যেহেতু `break` execute হয়নি, তাই `else` block execute হয়।

## 10. Practical Example: Password Attempts

নিচের program-এ user সর্বোচ্চ তিনবার password দেওয়ার সুযোগ পাবে।

```python
correct_password = "python123"
attempts = 0

while attempts < 3:
    password = input("Enter password: ")
    attempts += 1

    if password == correct_password:
        print("Login successful")
        break

else:
    print("Maximum attempts reached")
```

এখানে:

- সঠিক password দিলে `break` execute হয়।
- তাই `else` block execute হয় না।
- তিনবার ভুল password দিলে condition `False` হয়।
- তখন `else` block execute হয়।

এই উদাহরণে `input()`-এ যা লেখা হবে, তা string হিসেবে নেওয়া হয়।

## 11. Difference Between `while` and `while-else`

| বিষয় | `while` | `while-else` |
|---|---|---|
| Loop condition | `True` থাকলে body চলে | একই নিয়ম |
| Condition `False` হলে | Loop শেষ হয় | Loop শেষ হয়ে `else` চলে |
| `break` হলে | Loop বন্ধ হয় | Loop বন্ধ হয়, `else` চলে না |
| প্রধান ব্যবহার | Repetition | স্বাভাবিক completion বা search failure বোঝানো |

## 12. Common Mistakes

### Mistake 1: Wrong Indentation

Incorrect:

```python
number = 1

while number <= 2:
    print(number)
    number += 1
    else:
        print("Done")
```

এখানে `else`-এর indentation ভুল, তাই `SyntaxError` হবে।

Correct:

```python
number = 1

while number <= 2:
    print(number)
    number += 1

else:
    print("Done")
```

### Mistake 2: Thinking `else` Always Executes

```python
number = 1

while number <= 5:
    if number == 2:
        break

    number += 1

else:
    print("Finished")
```

এখানে `break` execute হওয়ায় `Finished` print হবে না।

### Mistake 3: Thinking `else` Belongs to the `if`

```python
number = 1

while number <= 3:
    if number == 2:
        print("Two")

    number += 1

else:
    print("Loop ended")
```

Output:

```text
Two
Loop ended
```

এখানে `else` হলো `while` loop-এর অংশ, `if` statement-এর নয়।

## 13. Dry Run Example

```python
number = 1

while number <= 3:
    print(number)

    if number == 2:
        break

    number += 1

else:
    print("Completed")
```

Dry run:

| Step | `number` | Condition | Action |
|---|---:|---|---|
| 1 | 1 | `1 <= 3` → True | 1 print; number = 2 |
| 2 | 2 | `2 <= 3` → True | 2 print; `break` execute |
| 3 | 2 | — | Loop বন্ধ; `else` skip |

Output:

```text
1
2
```

## 14. Practice Exercises

### Exercise 1

Output কী হবে?

```python
number = 1

while number <= 3:
    print(number)
    number += 1

else:
    print("Done")
```

### Exercise 2

Output কী হবে?

```python
number = 1

while number <= 5:
    if number == 3:
        break

    print(number)
    number += 1

else:
    print("Done")
```

### Exercise 3

নিচের code-এ `else` কেন execute হবে না?

```python
count = 0

while count < 4:
    count += 1

    if count == 2:
        break

else:
    print("Loop completed")
```

### Exercise 4

একটি list-এ target number পাওয়া না গেলে `"Not found"` print করার program লেখো। Search করার জন্য `while-else` ব্যবহার করো।

### Exercise 5

নিজের ভাষায় লেখো, `while-else`-এ `break`-এর ভূমিকা কী?

## 15. Answer Key

### Exercise 1

Output:

```text
1
2
3
Done
```

Condition `False` হওয়ায় `else` execute হবে।

### Exercise 2

Output:

```text
1
2
```

`number == 3` হলে `break` execute হয়। তাই `else` skip হয়।

### Exercise 3

`count` যখন `2` হয়, তখন `break` execute হয়ে loop বন্ধ করে। তাই `else` execute হয় না।

### Exercise 4

```python
numbers = [10, 20, 30, 40]
target = 50
index = 0

while index < len(numbers):
    if numbers[index] == target:
        print("Found")
        break

    index += 1

else:
    print("Not found")
```

Output:

```text
Not found
```

### Exercise 5

`break` loop-কে স্বাভাবিক condition-based completion-এর আগেই বন্ধ করে। তাই `while-else`-এর `else` block execute হয় না।

## 16. Chapter Progress Checklist

- [ ] `while-else`-এর syntax বুঝেছি।
- [ ] Condition `False` হলে `else` execute হয়—এটি বুঝেছি।
- [ ] `break` ব্যবহার করলে `else` skip হয়—এটি বুঝেছি।
- [ ] `while-else` দিয়ে search problem সমাধান করতে পারি।
- [ ] Dry run করে `else` execute হবে কি না নির্ধারণ করতে পারি।
- [ ] `else`-এর indentation সঠিকভাবে লিখতে পারি।

## 17. Summary

- Python-এ `while` loop-এর সঙ্গে `else` clause ব্যবহার করা যায়।
- Condition `False` হয়ে loop শেষ হলে `else` execute হয়।
- `break` দিয়ে loop বন্ধ হলে `else` execute হয় না।
- List-এ search করা এবং কোনো item পাওয়া না গেলে message দেখানোর কাজে এটি উপকারী।
- `else` হলো `while`-এর অংশ; `if`-এর অংশ নয়।

**Next Topic:** `20_Introduction_to_the_for_Loop.md`
