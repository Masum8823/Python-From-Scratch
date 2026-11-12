# 31. The `else` Clause in `for` Loops

## 1. Introduction

Python-এ `for` loop-এর সঙ্গে `else` clause ব্যবহার করা যায়।

সাধারণভাবে:

- Loop স্বাভাবিকভাবে শেষ হলে `else` block execute হয়।
- Loop-এর মধ্যে `break` execute হলে `else` block execute হয় না।
- Loop-এ কোনো item না থাকলেও, যদি `break` না ঘটে, তাহলে `else` block execute হয়।

এটি বিশেষভাবে searching, checking এবং কোনো item পাওয়া গেছে কি না তা নির্ধারণ করার ক্ষেত্রে কাজে লাগে।

## 2. Basic Syntax

```python
for variable in sequence:
    # Loop body
    statements
else:
    # Executes if the loop finishes without break
    statements
```

এখানে:

- `for` loop sequence-এর item-গুলোর ওপর কাজ করে।
- `else` block loop-এর স্বাভাবিক সমাপ্তির পরে execute হয়।
- `break` loop-কে মাঝপথে শেষ করে দেয়।

**মনে রাখবে:** এখানে `else`-এর অর্থ সরাসরি `if-else`-এর মতো “condition false” নয়। এটি মূলত loop `break` ছাড়া শেষ হয়েছে কি না, তার ওপর নির্ভর করে।

## 3. Example: Simple `for-else` Loop

```python
for number in range(1, 6):
    print(number)
else:
    print("Loop completed!")
```

**Output:**

```text
1
2
3
4
5
Loop completed!
```

### Explanation

1. Loop `1` থেকে `5` পর্যন্ত চলে।
2. প্রতিটি সংখ্যা print হয়।
3. Loop স্বাভাবিকভাবে শেষ হয়।
4. তাই `else` block execute হয়।

## 4. Understanding the Execution Flow

নিচের code-টি দেখো:

```python
for number in range(3):
    print("Number:", number)

print("Outside the loop")
```

**Output:**

```text
Number: 0
Number: 1
Number: 2
Outside the loop
```

এখানে `print("Outside the loop")` loop-এর বাইরে রয়েছে। এটি loop শেষ হওয়ার পরে execute হয়।

এখন `else` যোগ করলে:

```python
for number in range(3):
    print("Number:", number)
else:
    print("Loop else executed")

print("Outside the loop")
```

**Output:**

```text
Number: 0
Number: 1
Number: 2
Loop else executed
Outside the loop
```

এখানে প্রথমে loop body, তারপর `else` block এবং সবশেষে loop-এর বাইরের statement execute হয়েছে।

## 5. The `else` Clause with `break`

`break` statement loop-কে সঙ্গে সঙ্গে বন্ধ করে দেয়।

যদি `break` execute হয়, তাহলে loop-এর `else` block execute হয় না।

### Example

```python
for number in range(1, 6):
    print(number)

    if number == 3:
        break
else:
    print("Loop completed!")
```

**Output:**

```text
1
2
3
```

### Explanation

- প্রথমে `1` print হয়।
- তারপর `2` print হয়।
- `3` print হওয়ার পর condition `number == 3` সত্য হয়।
- `break` loop বন্ধ করে দেয়।
- তাই `else` block execute হয় না।

## 6. Difference Between Normal Completion and `break`

| Situation | Loop-এর ফলাফল | `else` execute হবে? |
|---|---|---|
| সব item process হয় | স্বাভাবিকভাবে শেষ | হ্যাঁ |
| `break` execute হয় | মাঝপথে শেষ | না |
| Sequence empty | কোনো iteration হয় না | হ্যাঁ |
| `continue` execute হয় | পরবর্তী iteration-এ যায় | `break` না হলে হ্যাঁ |

**গুরুত্বপূর্ণ:** `continue` loop বন্ধ করে না। তাই শুধু `continue` ব্যবহার করলে `else` execute হওয়ায় বাধা সৃষ্টি হয় না।

## 7. The `else` Clause with an Empty Sequence

যদি sequence-এ কোনো item না থাকে, তাহলে loop body একবারও execute হবে না। তারপরও `break` না ঘটায় `else` execute হবে।

### Example

```python
for number in range(0):
    print(number)
else:
    print("No iterations occurred")
```

**Output:**

```text
No iterations occurred
```

এখানে `range(0)` empty sequence তৈরি করে। তাই কোনো সংখ্যা print হয়নি।

## 8. The `else` Clause with `continue`

`continue` বর্তমান iteration-এর বাকি অংশ বাদ দিয়ে পরবর্তী iteration শুরু করে।

### Example

```python
for number in range(1, 5):
    if number == 2:
        continue

    print(number)
else:
    print("Loop finished without break")
```

**Output:**

```text
1
3
4
Loop finished without break
```

### Explanation

- `1` print হয়।
- `2`-এর ক্ষেত্রে `continue` পরবর্তী iteration-এ চলে যায়।
- `3` ও `4` print হয়।
- কোনো `break` execute হয়নি।
- তাই `else` block execute হয়।

## 9. Practical Example: Searching for a Number

`for-else`-এর সবচেয়ে পরিচিত ব্যবহার হলো কোনো sequence-এর মধ্যে একটি value খোঁজা।

ধরা যাক, একটি list থেকে `7` খুঁজতে হবে।

```python
numbers = [2, 4, 6, 7, 9]

target = 7

for number in numbers:
    if number == target:
        print("Number found!")
        break
else:
    print("Number not found!")
```

**Output:**

```text
Number found!
```

### Explanation

1. Loop list-এর প্রতিটি number পরীক্ষা করে।
2. `number == target` সত্য হলে `"Number found!"` print হয়।
3. `break` loop বন্ধ করে।
4. `else` execute হয় না, কারণ loop `break` দিয়ে শেষ হয়েছে।

## 10. Practical Example: Number Not Found

এবার target এমন একটি সংখ্যা রাখি, যা list-এ নেই।

```python
numbers = [2, 4, 6, 7, 9]

target = 5

for number in numbers:
    if number == target:
        print("Number found!")
        break
else:
    print("Number not found!")
```

**Output:**

```text
Number not found!
```

এখানে কোনো number-ই `5`-এর সমান নয়। তাই `break` execute হয়নি। Loop স্বাভাবিকভাবে শেষ হয়েছে এবং `else` block execute হয়েছে।

## 11. Dry Run: Searching for a Number

Code:

```python
numbers = [3, 5, 8]
target = 8

for number in numbers:
    if number == target:
        print("Found")
        break
else:
    print("Not found")
```

**Dry Run Table:**

| Iteration | `number` | `number == target` | Action |
|---|---:|---|---|
| 1 | 3 | False | Continue |
| 2 | 5 | False | Continue |
| 3 | 8 | True | Print `Found`, then `break` |

**Output:**

```text
Found
```

যেহেতু `break` execute হয়েছে, `else` block চালানো হয়নি।

## 12. Practical Example: Checking for Even Numbers

একটি list-এ কোনো even number আছে কি না, তা পরীক্ষা করা যাক।

```python
numbers = [1, 3, 5, 7, 8, 9]

for number in numbers:
    if number % 2 == 0:
        print("Even number found:", number)
        break
else:
    print("No even number found")
```

**Output:**

```text
Even number found: 8
```

এখানে `number % 2 == 0` দিয়ে even number পরীক্ষা করা হয়েছে।

প্রথম even number পাওয়া গেলে `break` loop বন্ধ করে দেয়।

### যদি list-এ even number না থাকে

```python
numbers = [1, 3, 5, 7, 9]

for number in numbers:
    if number % 2 == 0:
        print("Even number found:", number)
        break
else:
    print("No even number found")
```

**Output:**

```text
No even number found
```

## 13. Practical Example: Checking for a Prime Number

`for-else` ব্যবহার করে একটি সংখ্যার কোনো divisor পাওয়া গেছে কি না, সেটি পরীক্ষা করা যায়।

```python
number = 11

for divisor in range(2, number):
    if number % divisor == 0:
        print("Not a prime number")
        break
else:
    print("Prime number")
```

**Output:**

```text
Prime number
```

### Explanation

- `range(2, number)` দিয়ে `2` থেকে `number - 1` পর্যন্ত divisor পরীক্ষা করা হয়।
- কোনো divisor দিয়ে নিঃশেষে ভাগ গেলে সংখ্যাটি prime নয়।
- এমন divisor পাওয়া গেলে `break` execute হয়।
- কোনো divisor পাওয়া না গেলে loop স্বাভাবিকভাবে শেষ হয় এবং `else` execute হয়।

**Note:** এই example-টি `number > 1` ধরে নেওয়া হয়েছে। `0`, `1` বা negative number-এর ক্ষেত্রে আলাদা validation প্রয়োজন।

## 14. `for-else` vs `if-else`

`for-else` এবং `if-else` এক জিনিস নয়।

### `if-else` Example

```python
age = 17

if age >= 18:
    print("Adult")
else:
    print("Not an adult")
```

**Output:**

```text
Not an adult
```

এখানে `else` execute হয়েছে কারণ `if` condition false ছিল।

### `for-else` Example

```python
for number in range(3):
    print(number)
else:
    print("Loop completed")
```

**Output:**

```text
0
1
2
Loop completed
```

এখানে `else` execute হয়েছে কারণ loop `break` ছাড়া স্বাভাবিকভাবে শেষ হয়েছে।

## 15. Common Mistakes

### Mistake 1: Thinking `else` runs only when the loop executes zero times

এটি ভুল।

```python
for number in range(1, 4):
    print(number)
else:
    print("Completed")
```

এখানে loop তিনবার চলেছে, তারপরও `else` execute হয়েছে।

### Mistake 2: Thinking `continue` skips the `else`

এটিও ভুল।

`continue` শুধু বর্তমান iteration-এর বাকি অংশ বাদ দেয়। Loop পরে `break` ছাড়া শেষ হলে `else` execute হয়।

### Mistake 3: Putting `else` at the wrong indentation

সঠিক:

```python
for number in range(3):
    print(number)
else:
    print("Completed")
```

এখানে `else`-এর indentation `for`-এর সঙ্গে একই level-এ।

### Mistake 4: Forgetting that `break` skips `else`

```python
for number in range(5):
    if number == 2:
        break
else:
    print("Completed")
```

এখানে `"Completed"` print হবে না, কারণ `break` execute হয়েছে।

### Mistake 5: Using `for-else` when ordinary code is clearer

`for-else` বিশেষ করে searching বা “কিছু পাওয়া যায়নি” ধরনের logic-এ উপযোগী। সব loop-এর সঙ্গে `else` যোগ করার প্রয়োজন নেই।

## 16. Practice Exercises

### Exercise 1: Find the Output

```python
for number in range(1, 4):
    print(number)
else:
    print("Done")
```

### Exercise 2: Find the Output

```python
for number in range(1, 5):
    if number == 3:
        break
else:
    print("Done")
```

### Exercise 3: Find the Output

```python
for number in range(1, 4):
    if number == 2:
        continue
    print(number)
else:
    print("Finished")
```

### Exercise 4: Find the Output

```python
for number in range(0):
    print(number)
else:
    print("Empty loop")
```

### Exercise 5: Write a Search Program

একটি list-এর মধ্যে `10` আছে কি না পরীক্ষা করো। পাওয়া গেলে `"Found"` এবং না পাওয়া গেলে `"Not found"` print করো। `for-else` ব্যবহার করতে হবে।

### Exercise 6: Explain the Difference

`break` এবং `continue` কীভাবে `for-else` loop-এর আচরণকে প্রভাবিত করে?

## 17. Practice Answer Key

### Answer 1

```text
1
2
3
Done
```

Loop স্বাভাবিকভাবে শেষ হয়েছে, তাই `else` execute হয়েছে।

### Answer 2

কোনো output হবে না। `number == 3` হলে `break` execute হয়, তাই `else` skip হয়।

### Answer 3

```text
1
3
Finished
```

`2`-এর ক্ষেত্রে `continue` হওয়ায় সেটি print হয়নি। কিন্তু loop `break` ছাড়া শেষ হওয়ায় `else` execute হয়েছে।

### Answer 4

```text
Empty loop
```

Loop-এর কোনো iteration হয়নি, কিন্তু `break`-ও ঘটেনি।

### Answer 5

```python
numbers = [4, 7, 10, 15]
target = 10

for number in numbers:
    if number == target:
        print("Found")
        break
else:
    print("Not found")
```

Output:

```text
Found
```

### Answer 6

- `break`: loop বন্ধ করে এবং loop-এর `else` block skip করে।
- `continue`: বর্তমান iteration বাদ দিয়ে পরের iteration-এ যায়। এটি নিজে `else` skip করে না।

## 18. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `for` loop-এর সঙ্গে `else` clause ব্যবহার করা।
- Loop স্বাভাবিকভাবে শেষ হলে `else` execute হওয়া।
- `break` execute হলে `else` skip হওয়া।
- `continue` ব্যবহার করলেও loop স্বাভাবিকভাবে শেষ হলে `else` execute হওয়া।
- Empty sequence-এর ক্ষেত্রেও `else` execute হওয়া।
- Searching ও prime-number checking-এর মতো problem-এ `for-else` ব্যবহার করা।

## 19. Completion Checklist

- [ ] `for-else`-এর syntax লিখতে পারি।
- [ ] কখন `else` execute হয় তা বুঝি।
- [ ] `break` ও `continue`-এর পার্থক্য জানি।
- [ ] Empty sequence-এর ক্ষেত্রে কী হয় তা ব্যাখ্যা করতে পারি।
- [ ] `for-else` ব্যবহার করে search program লিখতে পারি।

**Next Topic:** `32_Introduction_to_Loop_Control_Statements.md`
