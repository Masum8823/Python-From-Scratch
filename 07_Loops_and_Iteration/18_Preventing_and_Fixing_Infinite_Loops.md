# 18. Preventing and Fixing Infinite Loops

## 1. Introduction

**Infinite loop** হলো এমন একটি loop, যা প্রত্যাশিত সময়ে শেষ হয় না। এটি সাধারণত ঘটে যখন loop-এর condition কখনো `False` হয় না অথবা exit করার ব্যবস্থা কাজ করে না।

Infinite loop প্রতিরোধ করার জন্য তিনটি বিষয় সবচেয়ে গুরুত্বপূর্ণ:

1. **Condition:** Loop কখন চলবে?
2. **Update:** প্রতিটি iteration-এ কোন variable পরিবর্তিত হবে?
3. **Termination:** Loop কখন শেষ হবে?

এই তিনটি বিষয় ঠিক থাকলে accidental infinite loop হওয়ার সম্ভাবনা অনেক কমে যায়।

## 2. Always Check the Loop Condition

Loop লেখার আগে বুঝতে হবে, কোন অবস্থায় condition `False` হবে।

### Incorrect Code

```python
count = 1

while count <= 5:
    print(count)
```

এখানে `count` পরিবর্তন হচ্ছে না। তাই `count <= 5` সবসময় `True` থাকে।

### Correct Code

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

এখন `count` একসময় `6` হবে এবং `count <= 5` মিথ্যা হবে।

**Rule:** প্রতিটি `while` loop-এর condition কখন মিথ্যা হবে, তা আগে থেকেই চিন্তা করো।

## 3. Ensure the Loop Variable Moves in the Correct Direction

Variable-এর update direction অবশ্যই condition-এর সঙ্গে সামঞ্জস্যপূর্ণ হতে হবে।

### Incorrect Countdown

```python
number = 5

while number >= 1:
    print(number)
    number += 1
```

এখানে `number` বাড়ছে, অথচ condition চালু থাকবে যতক্ষণ `number >= 1`। তাই loop শেষ হবে না।

### Correct Countdown

```python
number = 5

while number >= 1:
    print(number)
    number -= 1
```

Output:

```text
5
4
3
2
1
```

এখানে `number` কমতে কমতে `0` হয়। তখন condition মিথ্যা হয়।

## 4. Use a Clear Termination Condition

Loop-এর termination condition সহজ ও পরিষ্কার রাখলে ভুল কম হয়।

### Example: Print 1 to 10

```python
number = 1

while number <= 10:
    print(number)
    number += 1
```

এখানে:

- Initial value: `1`
- Required last value: `10`
- Update: `number += 1`
- Termination condition: `number <= 10`

এই তথ্যগুলো স্পষ্ট থাকায় loop যাচাই করা সহজ।

## 5. Avoid Incorrect Logical Conditions

`and` ও `or` ভুলভাবে ব্যবহার করলে loop অনাকাঙ্ক্ষিতভাবে চলতে পারে।

### Incorrect Code

```python
number = 1

while number < 5 or number > 0:
    print(number)
    number += 1
```

`number` যখন `5` বা তার বেশি হয়, তখনও `number > 0` সত্য থাকে। তাই loop শেষ হয় না।

### Correct Code

```python
number = 1

while number < 5:
    print(number)
    number += 1
```

Output:

```text
1
2
3
4
```

**মনে রাখবে:** Condition-এ `and` অথবা `or` বসানোর আগে পুরো expression-এর অর্থ বুঝে নাও।

## 6. Check Whether the Target Value Is Reachable

কোনো নির্দিষ্ট value-তে পৌঁছানো পর্যন্ত loop চালালে, update-এর মাধ্যমে সেই value-তে পৌঁছানো সম্ভব কি না যাচাই করতে হবে।

### Incorrect Code

```python
number = 2

while number != 5:
    print(number)
    number += 2
```

Value হবে:

`2 → 4 → 6 → 8 → 10 → ...`

প্রতিবার `2` যোগ হওয়ায় `number` কখনো `5` হবে না।

### Better Version

যদি উদ্দেশ্য হয় `5`-এ পৌঁছালে loop বন্ধ করা:

```python
number = 2

while number < 5:
    print(number)
    number += 1
```

Output:

```text
2
3
4
```

এখানে `number` যখন `5` হয়, তখন loop শেষ হয়।

## 7. Use `break` When an Explicit Exit Is Needed

কখনো loop-এর মধ্যে একটি নির্দিষ্ট ঘটনা ঘটলে loop বন্ধ করতে হয়। তখন `break` ব্যবহার করা যায়।

```python
while True:
    text = input("Enter a word (exit to stop): ")

    if text == "exit":
        break

    print("You entered:", text)

print("Program finished.")
```

এখানে user `exit` লিখলে `break` loop থেকে বের করে দেয়।

এটি একটি intentional infinite loop-এর উদাহরণ, যার exit mechanism আছে।

**সতর্কতা:** `break` সব সমস্যার সমাধান নয়। সাধারণ counter-controlled loop-এ সঠিক condition ও update রাখাই যথেষ্ট।

## 8. Use Dry Run to Detect Problems

**Dry run** হলো code execute না করেই প্রতিটি ধাপে variable-এর value ও condition পরীক্ষা করা।

নিচের code-টি দেখি:

```python
count = 1

while count <= 4:
    print(count)
    count += 1
```

Dry run:

| Iteration | `count` | `count <= 4` | কাজ |
|---|---:|---|---|
| 1 | 1 | True | 1 print, তারপর count = 2 |
| 2 | 2 | True | 2 print, তারপর count = 3 |
| 3 | 3 | True | 3 print, তারপর count = 4 |
| 4 | 4 | True | 4 print, তারপর count = 5 |
| 5 | 5 | False | Loop বন্ধ |

Dry run করলে সহজেই বোঝা যায়, condition কখন `False` হবে।

## 9. Use Debugging Output

Loop-এর ভিতরে variable-এর value print করলে update ঠিকভাবে হচ্ছে কি না বোঝা যায়।

```python
count = 1

while count <= 5:
    print("Before update:", count)
    count += 1
    print("After update:", count)
```

Sample Output:

```text
Before update: 1
After update: 2
Before update: 2
After update: 3
...
Before update: 5
After update: 6
```

এখানে `Before update` ও `After update` দেখে counter-এর পরিবর্তন বোঝা যায়।

Debugging শেষ হলে প্রয়োজন না থাকলে অতিরিক্ত debugging output সরিয়ে ফেলবে।

## 10. Be Careful With User Input

User input-এর ওপর নির্ভরশীল loop-এ exit condition কখনো পূরণ না হলে loop চলতেই পারে।

### Example

```python
while True:
    answer = input("Type yes to continue or exit to stop: ")

    if answer.lower() == "exit":
        break

    print("You entered:", answer)
```

এখানে `.lower()` ব্যবহারের ফলে `EXIT`, `Exit` এবং `exit`—সবগুলোই গ্রহণ করা হবে।

তবে user যদি `exit` না লেখে, তাহলে loop চলতে থাকবে। তাই prompt-এ exit command স্পষ্টভাবে জানানো গুরুত্বপূর্ণ।

## 11. Common Loop-Fixing Checklist

কোনো loop শেষ না হলে নিচের প্রশ্নগুলো পরীক্ষা করো:

1. Variable initialize করা হয়েছে কি?
2. Loop-এর condition সঠিক কি?
3. Condition-এর variable update হচ্ছে কি?
4. Variable সঠিক direction-এ পরিবর্তিত হচ্ছে কি?
5. `and` ও `or` সঠিকভাবে ব্যবহৃত হয়েছে কি?
6. নির্দিষ্ট target value-তে পৌঁছানো সম্ভব কি?
7. `break` বা অন্য exit mechanism প্রয়োজন কি?
8. Boundary condition (`<`, `<=`, `>`, `>=`) ঠিক আছে কি?
9. Dry run করে termination point যাচাই করেছি কি?
10. User input-এর ক্ষেত্রে exit command স্পষ্ট কি?

## 12. Practical Debugging Examples

### Example 1: Fix the Counter

Incorrect code:

```python
count = 1

while count <= 3:
    print(count)
```

Correct code:

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

### Example 2: Fix the Countdown

Incorrect code:

```python
number = 5

while number > 0:
    print(number)
    number += 1
```

Correct code:

```python
number = 5

while number > 0:
    print(number)
    number -= 1
```

### Example 3: Fix the Condition

Incorrect code:

```python
number = 1

while number <= 5 or number >= 1:
    print(number)
    number += 1
```

Correct code:

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

এখানে `number <= 5` একাই প্রয়োজনীয় শর্ত পূরণ করে।

### Example 4: Fix the Sentinel Loop

Incorrect code:

```python
while True:
    value = input("Enter stop to finish: ")
    print(value)
```

Correct code:

```python
while True:
    value = input("Enter stop to finish: ")

    if value.lower() == "stop":
        break

    print(value)
```

এখন `stop` লিখলে loop শেষ হবে।

## 13. Practice Exercises

### Exercise 1

নিচের code-এ সমস্যা খুঁজে বের করে ঠিক করো।

```python
number = 1

while number <= 5:
    print(number)
```

### Exercise 2

এই countdown loop কেন শেষ হয় না?

```python
count = 10

while count >= 1:
    print(count)
    count += 1
```

### Exercise 3

নিচের loop কি শেষ হবে? Dry run করে দেখাও।

```python
number = 1

while number < 8:
    print(number)
    number += 3
```

### Exercise 4

নিচের loop কেন infinite?

```python
number = 2

while number != 9:
    print(number)
    number += 2
```

### Exercise 5

User `exit` লিখলে বন্ধ হবে—এমন একটি loop তৈরি করো।

### Exercise 6

Infinite loop debugging-এর জন্য অন্তত চারটি বিষয় লেখো, যেগুলো যাচাই করা উচিত।

## 14. Answer Key

### Exercise 1

`number` update হচ্ছে না।

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

### Exercise 2

`count` বাড়ছে, ফলে `count >= 1` সবসময় সত্য থাকে। `count += 1`-এর বদলে `count -= 1` করতে হবে।

### Exercise 3

এটি শেষ হবে। Value হবে `1, 4, 7, 10`। `10 < 8` মিথ্যা হওয়ায় loop বন্ধ হবে।

### Exercise 4

Value হবে `2, 4, 6, 8, 10, ...`। `number` কখনো `9` হবে না। তাই `number != 9` সত্যই থাকবে।

### Exercise 5

```python
while True:
    command = input("Enter command: ")

    if command.lower() == "exit":
        break

    print("Command:", command)
```

### Exercise 6

- Condition যাচাই করা।
- Variable update হচ্ছে কি না দেখা।
- Update direction পরীক্ষা করা।
- Logical operator পরীক্ষা করা।
- Target value reachable কি না দেখা।
- Dry run বা debugging output ব্যবহার করা।

## 15. Chapter Progress Checklist

- [ ] Loop condition পরীক্ষা করতে পারি।
- [ ] Missing update ঠিক করতে পারি।
- [ ] ভুল update direction শনাক্ত করতে পারি।
- [ ] Logical condition-এর ভুল ঠিক করতে পারি।
- [ ] Target value reachable কি না বুঝতে পারি।
- [ ] `break` দিয়ে explicit exit তৈরি করতে পারি।
- [ ] Dry run ও debugging output ব্যবহার করতে পারি।
- [ ] Infinite loop-এর সাধারণ কারণগুলো শনাক্ত করতে পারি।

## 16. Summary

- Infinite loop প্রতিরোধের জন্য condition, update ও termination বুঝতে হবে।
- Variable সঠিক দিকে পরিবর্তিত হচ্ছে কি না যাচাই করতে হবে।
- `and` ও `or`-এর ভুল ব্যবহার loop-কে অনির্দিষ্টকাল চালাতে পারে।
- Dry run ও debugging output দিয়ে সমস্যা শনাক্ত করা যায়।
- `while True` ব্যবহার করলে প্রয়োজনীয় exit mechanism রাখতে হবে।
- Loop ঠিক করার পর expected output দিয়ে পরীক্ষা করতে হবে।

**Next Topic:** `19_The_else_Clause_in_while_Loops.md`
