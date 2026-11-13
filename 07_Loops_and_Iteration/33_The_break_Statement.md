# 33. The `break` Statement

## 1. Introduction

Python-এ `break` statement ব্যবহার করে কোনো loop-কে নির্দিষ্ট condition পূরণ হওয়ার সঙ্গে সঙ্গে বন্ধ করা যায়।

সাধারণত loop নির্ধারিত sequence শেষ হওয়া পর্যন্ত বা condition সত্য থাকা পর্যন্ত চলে। কিন্তু কোনো নির্দিষ্ট পরিস্থিতিতে loop আগেই শেষ করার প্রয়োজন হতে পারে। তখন `break` ব্যবহার করা হয়।

**সহজভাবে:** `break` মানে হলো বর্তমান loop থেকে বের হয়ে যাওয়া।

## 2. Syntax of `break`

```python
for variable in sequence:
    if condition:
        break
```

এখানে condition সত্য হলে `break` execute হয় এবং loop বন্ধ হয়ে যায়।

`break` সাধারণত `for` ও `while` loop-এর ভেতরে ব্যবহার করা হয়।

## 3. Using `break` in a `for` Loop

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

1. প্রথম iteration-এ `number = 1`।
2. Condition `number == 3` মিথ্যা, তাই `1` print হয়।
3. একইভাবে `2` print হয়।
4. `number = 3` হলে condition সত্য হয়।
5. `break` loop বন্ধ করে দেয়।
6. তাই `3`, `4` ও `5` print হয় না।

## 4. Understanding the Execution Flow

নিচের code-টি দেখো:

```python
for number in range(1, 6):
    print("Checking:", number)

    if number == 4:
        break

print("Loop ended")
```

**Output:**

```text
Checking: 1
Checking: 2
Checking: 3
Checking: 4
Loop ended
```

এখানে `print("Checking:", number)` আগে execute হয়েছে। এরপর condition পরীক্ষা করে `break` হয়েছে।

তাই `4`-এর checking message print হয়েছে, কিন্তু loop `5` পর্যন্ত যায়নি।

Loop-এর বাইরের `print("Loop ended")` স্বাভাবিকভাবেই execute হয়েছে।

## 5. Using `break` in a `while` Loop

`while` loop-এ কোনো condition পূরণ হলে `break` দিয়ে loop বন্ধ করা যায়।

### Example

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

### Explanation

- `number` শুরু হয়েছে `1` থেকে।
- প্রতিবার `number` print হওয়ার পর এটি `1` করে বাড়ছে।
- `number == 5` হলে `break` execute হয়।
- ফলে loop বন্ধ হয়ে যায়।

এখানে `number = 5` অবস্থায় `print(number)` execute হয়নি, কারণ `break` তার আগেই এসেছে।

## 6. Difference Between `break` Position

একই `break` condition হলেও code-এর অবস্থানের কারণে output আলাদা হতে পারে।

### Example A: `break` Before `print()`

```python
for number in range(1, 5):
    if number == 3:
        break

    print(number)
```

**Output:**

```text
1
2
```

### Example B: `break` After `print()`

```python
for number in range(1, 5):
    print(number)

    if number == 3:
        break
```

**Output:**

```text
1
2
3
```

**মনে রাখবে:** `break` execute হওয়ার আগে যে statement-গুলো চলে, সেগুলোর ফলাফল থাকবে। `break`-এর পরে একই iteration-এ থাকা statement-গুলো আর execute হবে না।

## 7. Practical Example: Searching for a Number

একটি list-এর মধ্যে নির্দিষ্ট সংখ্যা খুঁজে পেতে `break` ব্যবহার করা যায়।

```python
numbers = [10, 20, 30, 40, 50]
target = 30

for number in numbers:
    if number == target:
        print("Number found:", number)
        break
```

**Output:**

```text
Number found: 30
```

### Explanation

- Loop প্রথমে `10` পরীক্ষা করে।
- তারপর `20` পরীক্ষা করে।
- `30` পাওয়া গেলে message print হয়।
- `break` loop বন্ধ করে দেয়।
- `40` ও `50` আর পরীক্ষা করা হয় না।

এভাবে target পাওয়া গেলে অপ্রয়োজনীয় iteration এড়ানো যায়।

## 8. Searching When the Value Is Not Found

যদি target list-এ না থাকে, তাহলে কোনো `break` execute হবে না।

```python
numbers = [10, 20, 30, 40, 50]
target = 60

for number in numbers:
    if number == target:
        print("Number found")
        break

print("Search completed")
```

**Output:**

```text
Search completed
```

এখানে `60` list-এ নেই। তাই loop স্বাভাবিকভাবে শেষ হয়েছে।

কিন্তু শুধু `break` ব্যবহার করলে value পাওয়া যায়নি—এমন message স্বয়ংক্রিয়ভাবে দেখাবে না। এর জন্য একটি flag variable অথবা loop-এর `else` clause ব্যবহার করা যায়।

### Using `for-else`

```python
numbers = [10, 20, 30, 40, 50]
target = 60

for number in numbers:
    if number == target:
        print("Number found")
        break
else:
    print("Number not found")
```

**Output:**

```text
Number not found
```

`break` ছাড়া loop শেষ হওয়ায় `else` execute হয়েছে।

## 9. Using `break` to Stop User Input

ধরা যাক, user যতক্ষণ ইচ্ছা number input দিতে পারবে। `0` দিলে input নেওয়া বন্ধ হবে।

```python
while True:
    number = int(input("Enter a number (0 to stop): "))

    if number == 0:
        break

    print("You entered:", number)

print("Input finished")
```

**Sample Input and Output:**

```text
Enter a number (0 to stop): 5
You entered: 5
Enter a number (0 to stop): 8
You entered: 8
Enter a number (0 to stop): 0
Input finished
```

### Explanation

- `while True` একটি loop তৈরি করে, যার condition সব সময় সত্য।
- `0` ছাড়া অন্য number দিলে সেটি print হয়।
- `0` দিলে `break` loop বন্ধ করে।
- তারপর loop-এর বাইরের message print হয়।

**Note:** এই উদাহরণে valid integer input ধরে নেওয়া হয়েছে। অন্য ধরনের input দিলে `int()`-এ `ValueError` হতে পারে।

## 10. Using `break` in a Menu Program

Menu-based program-এ user exit option নির্বাচন করলে loop বন্ধ করতে `break` ব্যবহার করা যায়।

```python
while True:
    print("1. Say Hello")
    print("2. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        print("Hello!")
    elif choice == "2":
        print("Goodbye!")
        break
    else:
        print("Invalid choice")
```

**Sample Output:**

```text
1. Say Hello
2. Exit
Enter your choice: 1
Hello!
1. Say Hello
2. Exit
Enter your choice: 2
Goodbye!
```

এখানে user `"2"` দিলে `break` loop বন্ধ করে দেয়। ফলে menu আর পুনরায় দেখানো হয় না।

## 11. Using `break` in Nested Loops

একটি loop-এর ভেতরে আরেকটি loop থাকলে তাকে nested loop বলে।

Nested loop-এ `break` ব্যবহার করলে এটি **যে loop-এর ভেতরে রয়েছে, সেই সবচেয়ে ভেতরের loop-টিকে** বন্ধ করে।

### Example

```python
for i in range(1, 4):
    print("Outer:", i)

    for j in range(1, 4):
        if j == 2:
            break

        print("Inner:", j)
```

**Output:**

```text
Outer: 1
Inner: 1
Outer: 2
Inner: 1
Outer: 3
Inner: 1
```

### Explanation

- Outer loop-এর `i` প্রথমে `1` হয়।
- Inner loop-এ `j = 1` হলে সেটি print হয়।
- `j = 2` হলে `break` inner loop বন্ধ করে।
- এরপর outer loop-এর পরবর্তী iteration শুরু হয়।
- একই ঘটনা `i = 2` ও `i = 3`-এর জন্য ঘটে।

**গুরুত্বপূর্ণ:** এখানে outer loop বন্ধ হয়নি; শুধু inner loop বন্ধ হয়েছে।

## 12. Stopping an Outer Loop from a Nested Loop

শুধু inner loop-এর `break` দিয়ে outer loop বন্ধ করা যায় না। Outer loop-ও বন্ধ করতে হলে অতিরিক্ত logic প্রয়োজন।

একটি সহজ পদ্ধতি হলো flag variable ব্যবহার করা।

```python
stop = False

for i in range(1, 4):
    for j in range(1, 4):
        if i == 2 and j == 2:
            stop = True
            break

        print(i, j)

    if stop:
        break
```

**Output:**

```text
1 1
1 2
1 3
2 1
```

### Explanation

1. `i = 2` এবং `j = 2` হলে `stop = True` হয়।
2. Inner loop-এর `break` inner loop বন্ধ করে।
3. এরপর outer loop-এর ভেতরের `if stop` condition পরীক্ষা হয়।
4. Condition সত্য হওয়ায় outer loop-ও বন্ধ হয়।

এই পদ্ধতি ব্যবহার করে nested loop থেকে বের হওয়ার logic তৈরি করা যায়।

## 13. The `break` Statement and the Loop `else` Clause

`for` বা `while` loop-এর সঙ্গে `else` থাকলে `break`-এর একটি বিশেষ প্রভাব রয়েছে।

- Loop স্বাভাবিকভাবে শেষ হলে `else` execute হয়।
- `break` execute হলে `else` execute হয় না।

### Example

```python
for number in range(1, 6):
    if number == 3:
        break
else:
    print("Loop completed normally")
```

**Output:**

```text
```

কোনো output নেই, কারণ `break` execute হয়েছে।

অন্যদিকে:

```python
for number in range(1, 4):
    print(number)
else:
    print("Loop completed normally")
```

**Output:**

```text
1
2
3
Loop completed normally
```

এখানে loop স্বাভাবিকভাবে শেষ হয়েছে, তাই `else` execute হয়েছে।

## 14. Common Mistakes

### Mistake 1: Using `break` Outside a Loop

```python
if True:
    break
```

এটি `SyntaxError` তৈরি করবে, কারণ `break` loop-এর বাইরে ব্যবহার করা হয়েছে।

### Mistake 2: Thinking `break` Skips Only One Iteration

`break` শুধু বর্তমান iteration skip করে না; এটি পুরো নিকটতম loop বন্ধ করে।

বর্তমান iteration skip করার জন্য `continue` ব্যবহার করতে হয়।

### Mistake 3: Forgetting That `break` Stops Only the Nearest Loop

Nested loop-এ `break` ব্যবহার করলে সাধারণত শুধু inner loop বন্ধ হয়। Outer loop চালু থাকতে পারে।

### Mistake 4: Placing `break` After an Unreachable Condition

```python
for number in range(1, 4):
    print(number)

    if number == 5:
        break
```

এখানে `number` কখনো `5` হয় না। তাই `break` execute হয় না।

Output:

```text
1
2
3
```

### Mistake 5: Expecting a Not-Found Message Automatically

`break` loop বন্ধ করার জন্য ব্যবহৃত হয়। কোনো item পাওয়া যায়নি—এমন message দেখাতে আলাদা logic প্রয়োজন।

## 15. Practice Exercises

### Exercise 1: Find the Output

```python
for number in range(1, 7):
    if number == 4:
        break

    print(number)
```

### Exercise 2: Find the Output

```python
for number in range(2, 8):
    print(number)

    if number == 5:
        break
```

### Exercise 3: Find the Output

```python
for i in range(1, 3):
    for j in range(1, 4):
        if j == 3:
            break

        print(i, j)
```

### Exercise 4: Write a Program

`1` থেকে `20` পর্যন্ত সংখ্যা পরীক্ষা করো। `13` পাওয়া গেলে loop বন্ধ করতে `break` ব্যবহার করো।

### Exercise 5: Write a Search Program

নিচের list-এ `25` খুঁজে বের করো। পাওয়া গেলে `"Found"` print করে loop বন্ধ করো।

```python
numbers = [5, 10, 15, 20, 25, 30]
```

### Exercise 6: Explain

Nested loop-এ `break` দিলে কেন সব loop একসঙ্গে বন্ধ হয় না?

## 16. Practice Answer Key

### Answer 1

```text
1
2
3
```

`number == 4` হলে `break` execute হওয়ার কারণে `4` print হয়নি।

### Answer 2

```text
2
3
4
5
```

এখানে `print(number)` আগে execute হয়েছে। তারপর `number == 5` হলে loop বন্ধ হয়েছে।

### Answer 3

```text
1 1
1 2
2 1
2 2
```

প্রতিটি outer iteration-এ inner loop `j == 3` হলে বন্ধ হয়।

### Answer 4

```python
for number in range(1, 21):
    if number == 13:
        print("13 found")
        break

    print(number)
```

### Answer 5

```python
numbers = [5, 10, 15, 20, 25, 30]

for number in numbers:
    if number == 25:
        print("Found")
        break
```

Output:

```text
Found
```

### Answer 6

`break` যে loop-এর ভেতরে লেখা থাকে, সেটিকেই বন্ধ করে। Nested loop-এর outer loop বন্ধ করতে আলাদা logic বা অন্য control technique প্রয়োজন হতে পারে।

## 17. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `break` loop-কে তাৎক্ষণিকভাবে বন্ধ করে।
- `for` ও `while` loop-এ `break` ব্যবহার করা যায়।
- Search এবং menu program-এ `break` উপযোগী।
- `break`-এর অবস্থান output-কে প্রভাবিত করে।
- Nested loop-এ `break` সবচেয়ে ভেতরের loop বন্ধ করে।
- `break` execute হলে loop-এর `else` block চলে না।

## 18. Completion Checklist

- [ ] `break`-এর syntax বুঝি।
- [ ] `for` ও `while` loop-এ এটি ব্যবহার করতে পারি।
- [ ] Search program-এ `break` ব্যবহার করতে পারি।
- [ ] `while True` loop থেকে বের হতে পারি।
- [ ] Nested loop-এ `break`-এর আচরণ বুঝি।
- [ ] `break` ও `continue`-এর পার্থক্য বুঝি।

**Next Topic:** `34_The_continue_Statement.md`
