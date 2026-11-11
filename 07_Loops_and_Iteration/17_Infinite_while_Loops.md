# 17. Infinite `while` Loops

## 1. Introduction

**Infinite loop** হলো এমন একটি loop, যা নিজে থেকে শেষ হয় না, কারণ এর termination condition কখনো `False` হয় না।

উদাহরণ:

```python
while True:
    print("Hello Python")
```

এই program বারবার `Hello Python` print করতে থাকবে। কারণ `True` সবসময় সত্য, তাই condition কখনো `False` হবে না।

Infinite loop সবসময় ভুল নয়। কিছু program-এ বারবার user input নেওয়া, server চালু রাখা বা menu দেখানোর জন্য ইচ্ছাকৃতভাবে infinite loop ব্যবহার করা হয়। তবে loop থেকে বের হওয়ার ব্যবস্থা থাকা প্রয়োজন।

## 2. Why Does an Infinite Loop Occur?

সাধারণত নিচের কারণগুলোতে infinite loop তৈরি হয়:

1. Condition সবসময় `True` থাকে।
2. Condition-এ ব্যবহৃত variable update করা হয় না।
3. Variable ভুল দিকে update করা হয়।
4. Update-এর কারণে condition কখনো `False` হয় না।
5. Loop-এর termination condition ভুলভাবে লেখা হয়।

## 3. Infinite Loop Caused by a Constant Condition

যদি condition সবসময় `True` হয়, তাহলে loop নিজে থেকে শেষ হবে না।

```python
while True:
    print("Running...")
```

Output বারবার হবে:

```text
Running...
Running...
Running...
...
```

এখানে `True`-এর value পরিবর্তিত হয় না। তাই loop অনির্দিষ্টকাল চলতে থাকবে।

**মনে রাখবে:** ইচ্ছাকৃতভাবে `while True` ব্যবহার করলে সাধারণত `break`, কোনো termination condition অথবা অন্য কোনো exit mechanism রাখা হয়।

## 4. Infinite Loop Caused by a Missing Update

```python
count = 1

while count <= 5:
    print(count)
```

এখানে `count`-এর value সবসময় `1` থাকে। ফলে `count <= 5` condition সবসময় `True`।

Output:

```text
1
1
1
1
...
```

### Correct Version

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

`count += 1` যোগ করার ফলে counter বাড়ে এবং একসময় condition `False` হয়।

## 5. Infinite Loop Caused by Updating in the Wrong Direction

Condition ও update-এর direction একে অপরের সঙ্গে সামঞ্জস্যপূর্ণ হতে হবে।

ভুল code:

```python
count = 1

while count <= 5:
    print(count)
    count -= 1
```

এখানে `count` কমছে:

`1, 0, -1, -2, -3, ...`

প্রতিটি value-ই `5`-এর সমান বা ছোট। তাই condition কখনো `False` হবে না।

### Correct Version

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

এখানে counter সঠিক দিকে বাড়ছে।

## 6. Infinite Loop Caused by an Incorrect Condition

কখনো condition-ই ভুলভাবে লেখা হয়।

```python
number = 1

while number != 5:
    print(number)
    number += 2
```

এখানে `number`-এর value হবে:

`1, 3, 5, ...`

আসলে এই code-টি infinite loop নয়, কারণ `number` যখন `5` হয়, তখন condition `False` হয়ে যায়।

কিন্তু যদি শুরু হয় `2` থেকে:

```python
number = 2

while number != 5:
    print(number)
    number += 2
```

তাহলে `number` হবে:

`2, 4, 6, 8, 10, ...`

Counter কখনো `5` হবে না। তাই `number != 5` সবসময় `True` থাকবে এবং loop শেষ হবে না।

**শিক্ষা:** কোনো নির্দিষ্ট value-তে পৌঁছানোর উদ্দেশ্য থাকলে update-এর ধাপ এমন কি না, যাতে সেই value-তে পৌঁছানো সম্ভব হয়, তা যাচাই করতে হবে।

## 7. Infinite Loop Caused by Incorrect Logical Operators

`and` ও `or` ভুলভাবে ব্যবহার করলেও loop অনাকাঙ্ক্ষিতভাবে চলতে পারে।

```python
number = 1

while number < 5 or number > 0:
    print(number)
    number += 1
```

এই condition-এর অর্থ:

- `number < 5` সত্য, অথবা
- `number > 0` সত্য।

`number` যখন `5` বা তার বেশি হয়, তখনও `number > 0` সত্য থাকে। তাই condition কখনো `False` হয় না।

### Correct Version

যদি `1` থেকে `4` পর্যন্ত print করতে চাও:

```python
number = 1

while number < 5 and number > 0:
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

এখানে `number` যখন `5` হয়, তখন উভয় condition একসঙ্গে সত্য থাকে না। ফলে loop বন্ধ হয়।

## 8. Intentional Infinite Loops

কিছু ক্ষেত্রে program-কে বারবার কাজ করার জন্য চালু রাখতে হয়। তখন `while True` ব্যবহার করা যায়।

### Example 1: Menu-Based Program

```python
while True:
    print("1. Say Hello")
    print("2. Exit")

    choice = input("Choose an option: ")

    if choice == "1":
        print("Hello!")

    elif choice == "2":
        print("Goodbye!")
        break

    else:
        print("Invalid choice!")
```

Sample Output:

```text
1. Say Hello
2. Exit
Choose an option: 1
Hello!

1. Say Hello
2. Exit
Choose an option: 2
Goodbye!
```

এখানে:

- `while True` menu-টি বারবার দেখায়।
- `break` loop থেকে বের করে।
- `"2"` নির্বাচন করলে loop বন্ধ হয়।

### Example 2: Repeated User Input

```python
while True:
    message = input("Enter a message (type 'exit' to stop): ")

    if message == "exit":
        break

    print("You entered:", message)
```

এখানে user `"exit"` না লেখা পর্যন্ত input নেওয়া হবে।

### Example 3: Number Guessing Loop

```python
secret = 7

while True:
    guess = int(input("Guess the number: "))

    if guess == secret:
        print("Correct!")
        break
    else:
        print("Try again.")
```

সঠিক উত্তর দিলে `break` loop বন্ধ করে। এখানে ধরে নেওয়া হয়েছে user integer input দেবে।

**গুরুত্বপূর্ণ:** Infinite loop ব্যবহার করার আগে নিশ্চিত হতে হবে, প্রয়োজন হলে loop থেকে বের হওয়ার ব্যবস্থা আছে।

## 9. Difference Between an Infinite Loop and a Long Loop

কোনো loop অনেকবার চলে বলেই সেটি infinite loop নয়।

### Long but Finite Loop

```python
count = 1

while count <= 100000:
    count += 1

print("Finished")
```

এই loop অনেকবার চলে, কিন্তু `count` একসময় `100001` হয় এবং condition `False` হয়ে যায়।

### Infinite Loop

```python
count = 1

while count > 0:
    count += 1
```

সাধারণভাবে এই loop থামবে না। Python-এর integer-এর নির্দিষ্ট fixed maximum নেই, তাই `count` বাড়তেই থাকবে—যতক্ষণ না program বাহ্যিকভাবে বন্ধ হয় বা অন্য কোনো runtime সমস্যা ঘটে।

## 10. How to Stop an Infinite Loop

যদি program অনিচ্ছাকৃতভাবে চলতে থাকে, তাহলে:

### Method 1: Stop It in the Terminal

VS Code terminal-এ Python program চালানোর সময় সাধারণত `Ctrl + C` চাপলে `KeyboardInterrupt` দিয়ে execution থামানো যায়।

### Method 2: Check the Condition

নিজেকে প্রশ্ন করো:

- Condition কখন `False` হবে?
- Variable-এর value কি পরিবর্তিত হচ্ছে?
- Variable সঠিক দিকে পরিবর্তিত হচ্ছে?
- Logical operator সঠিকভাবে ব্যবহার করা হয়েছে?

### Method 3: Add Temporary Debugging Output

```python
count = 1

while count <= 5:
    print("Current count:", count)
    count += 1
```

এভাবে variable-এর বর্তমান value দেখলে loop কেন চলছে, তা বুঝতে সুবিধা হয়।

## 11. Common Mistakes and Solutions

| Mistake | সমস্যা | সমাধান |
|---|---|---|
| Variable update না করা | Condition একই থাকে | প্রয়োজনমতো variable update করো |
| ভুল দিকে update | Condition কখনো মিথ্যা হয় না | Condition অনুযায়ী update-এর direction ঠিক করো |
| ভুল `or` ব্যবহার | একটি condition সত্য থাকায় loop চলতে থাকে | প্রয়োজন অনুযায়ী `and`/`or` নির্বাচন করো |
| অসম্ভব target value | Counter target-এ পৌঁছায় না | Update step যাচাই করো |
| `while True`-তে exit না রাখা | Loop বন্ধ করার উপায় নেই | `break` বা অন্য termination mechanism যোগ করো |
| Boundary ভুল লেখা | অতিরিক্ত বা কম iteration হয় | `<`, `<=`, `>`, `>=` যাচাই করো |

## 12. Practice Exercises

### Exercise 1

Infinite loop কী?

### Exercise 2

নিচের code-টি কেন infinite loop তৈরি করে?

```python
count = 1

while count <= 5:
    print(count)
```

### Exercise 3

নিচের code কি infinite loop? কারণ ব্যাখ্যা করো।

```python
number = 1

while number < 10:
    print(number)
    number += 2
```

### Exercise 4

নিচের code-টি কি infinite loop?

```python
number = 2

while number != 5:
    print(number)
    number += 2
```

### Exercise 5

নিচের code-এ logical mistake কোথায়?

```python
number = 1

while number < 5 or number > 0:
    print(number)
    number += 1
```

### Exercise 6

`while True` ব্যবহার করে এমন একটি program লেখো, যা user `"exit"` লিখলে বন্ধ হবে।

### Exercise 7

নিচের code-এ loop কেন শেষ হয় না?

```python
count = 10

while count >= 1:
    print(count)
    count += 1
```

### Exercise 8

VS Code terminal-এ চলতে থাকা Python loop সাধারণত কোন keyboard shortcut দিয়ে বন্ধ করা যায়?

## 13. Answer Key

### Exercise 1

যে loop নিজে থেকে শেষ হয় না, কারণ তার termination condition কখনো `False` হয় না, তাকে infinite loop বলে।

### Exercise 2

`count`-এর value update হচ্ছে না। তাই `count <= 5` সবসময় `True`।

### Exercise 3

এটি infinite loop নয়। `number`-এর value হবে `1, 3, 5, 7, 9, 11`। `11 < 10` মিথ্যা হওয়ায় loop শেষ হবে।

### Exercise 4

হ্যাঁ, এই code অনির্দিষ্টকাল চলবে। `number`-এর value `2, 4, 6, 8, ...` হবে এবং কখনো `5` হবে না।

### Exercise 5

`or` ব্যবহারের কারণে `number > 0` condition সত্য থাকলে loop চলতেই থাকে। এই উদাহরণে positive number বাড়তে থাকায় condition কখনো `False` হয় না।

### Exercise 6

```python
while True:
    command = input("Enter a command: ")

    if command == "exit":
        break

    print("Command:", command)
```

### Exercise 7

`count` একের পর এক বাড়ছে। তাই `count >= 1` condition সবসময় `True` থাকে। Countdown-এর জন্য `count -= 1` ব্যবহার করতে হবে।

### Exercise 8

`Ctrl + C`।

## 14. Chapter Progress Checklist

- [ ] Infinite loop কী বুঝেছি।
- [ ] Missing update-এর কারণে infinite loop শনাক্ত করতে পারি।
- [ ] Wrong-direction update-এর সমস্যা বুঝেছি।
- [ ] Logical operator-এর ভুল শনাক্ত করতে পারি।
- [ ] `while True` ও `break` ব্যবহার করতে পারি।
- [ ] Long loop ও infinite loop-এর পার্থক্য বুঝেছি।
- [ ] Terminal থেকে loop বন্ধ করতে পারি।
- [ ] Loop condition ও update পরীক্ষা করে সমস্যা সমাধান করতে পারি।

## 15. Summary

- Infinite loop এমন loop, যার termination condition কখনো `False` হয় না।
- Variable update না করা বা ভুল দিকে update করা সাধারণ কারণ।
- ভুল logical operator ও unreachable target value-ও infinite loop তৈরি করতে পারে।
- `while True` ইচ্ছাকৃতভাবে ব্যবহার করা যায়, তবে exit mechanism থাকা প্রয়োজন।
- `break` loop থেকে বের হতে সাহায্য করে।
- Debugging-এর সময় condition, variable update এবং boundary পরীক্ষা করা জরুরি।

**Next Topic:** `18_Preventing_and_Fixing_Infinite_Loops.md`
