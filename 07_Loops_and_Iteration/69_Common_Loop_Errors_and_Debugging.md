# 69. Common Loop Errors and Debugging

## 1. Introduction

Loop ব্যবহার করে একই কাজ বারবার করা যায়। কিন্তু loop-এর condition, indentation, variable update বা control statement-এ ভুল থাকলে program ভুল output দিতে পারে, অপ্রত্যাশিতভাবে বন্ধ হতে পারে, এমনকি অনির্দিষ্টকাল চলতেও পারে।

এই ভুলগুলো শনাক্ত করে সমাধান করার প্রক্রিয়াকে **Debugging** বলা হয়।

এই topic-এ আমরা শিখব:

- Common loop errors শনাক্ত করা।
- Infinite loop-এর কারণ খুঁজে বের করা।
- ভুল condition ও variable update ঠিক করা।
- `break` ও `continue`-এর ভুল ব্যবহার শনাক্ত করা।
- Dry run ও debugging statement ব্যবহার করা।
- Loop-এর logic ধাপে ধাপে পরীক্ষা করা।

## 2. Infinite Loop

Infinite loop হলো এমন loop, যেটি স্বাভাবিকভাবে শেষ হয় না।

### Incorrect Code

```python
number = 1

while number <= 5:
    print(number)
```

এখানে `number`-এর value কখনো পরিবর্তন হচ্ছে না। তাই condition সব সময় True থাকে।

Output বারবার এমন হবে:

```text
1
1
1
1
...
```

### Correct Code

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

Output:

```text
1
2
3
4
5
```

**Solution:** `while` loop-এর variable কীভাবে পরিবর্তিত হচ্ছে এবং condition শেষ পর্যন্ত False হবে কি না, তা যাচাই করবে।

## 3. Incorrect Loop Condition

ভুল condition-এর কারণে loop প্রয়োজনের চেয়ে বেশি, কম অথবা একেবারেই execute নাও হতে পারে।

### Incorrect Code

```python
number = 1

while number > 5:
    print(number)
    number += 1
```

Output:

```text
```

কোনো output নেই, কারণ শুরুতেই `1 > 5` False।

### Correct Code

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

Output:

```text
1
2
3
4
5
```

**Solution:** Loop শুরু হওয়ার আগেই initial value দিয়ে condition পরীক্ষা করবে।

## 4. Incorrect Variable Update

Loop variable ভুলভাবে update করলে loop infinite হতে পারে অথবা প্রত্যাশিত output নাও দিতে পারে।

### Incorrect Code

```python
number = 5

while number > 0:
    print(number)
    number += 1
```

এখানে `number` কমার বদলে বাড়ছে। তাই `number > 0` সব সময় True থাকবে।

### Correct Code

```python
number = 5

while number > 0:
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

**Solution:** Condition-এর সঙ্গে update-এর দিক মিলিয়ে দেখবে।

- বাড়তে থাকা variable-এর ক্ষেত্রে upper boundary অতিক্রম হচ্ছে কি না দেখো।
- কমতে থাকা variable-এর ক্ষেত্রে lower boundary অতিক্রম হচ্ছে কি না দেখো।

## 5. Off-by-One Error

Off-by-one error হলে loop একবার বেশি অথবা একবার কম চলে।

### Incorrect Code

```python
for number in range(1, 5):
    print(number)
```

Output:

```text
1
2
3
4
```

যদি `1` থেকে `5` পর্যন্ত print করতে চাও, তাহলে `5` বাদ পড়ে গেছে।

### Correct Code

```python
for number in range(1, 6):
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

**Solution:** `range()`-এর stop value অন্তর্ভুক্ত হয় না—এটি মনে রাখবে।

## 6. Incorrect Indentation

Python-এ indentation দিয়ে code block নির্ধারণ করা হয়। ভুল indentation-এর কারণে syntax error অথবা ভুল logic তৈরি হতে পারে।

### Incorrect Code

```python
for number in range(1, 4):
print(number)
```

এখানে `print(number)` loop body-তে সঠিকভাবে indent করা হয়নি। ফলে `IndentationError` হবে।

### Correct Code

```python
for number in range(1, 4):
    print(number)
```

Output:

```text
1
2
3
```

**Solution:** একই block-এর statement-গুলো একই indentation level-এ রাখবে। সাধারণত প্রতি level-এ চারটি space ব্যবহার করা হয়।

## 7. Updating the Variable at the Wrong Position

Variable update কোথায় রাখা হয়েছে, তার ওপর output নির্ভর করতে পারে।

### Example

```python
number = 1

while number <= 3:
    number += 1
    print(number)
```

Output:

```text
2
3
4
```

এখানে print করার আগে variable update হচ্ছে।

যদি `1`, `2`, `3` print করতে চাও, তাহলে:

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

**Solution:** প্রথমে নির্ধারণ করবে, বর্তমান value print বা process করার পরে update করতে হবে, নাকি আগে।

## 8. Incorrect Use of `break`

`break` বর্তমান সবচেয়ে ভেতরের loop-টি সঙ্গে সঙ্গে বন্ধ করে দেয়।

### Incorrect Logic

```python
for number in range(1, 6):
    if number > 2:
        break
    print(number)
```

Output:

```text
1
2
```

এখানে `number = 3` হলে loop বন্ধ হয়ে যায়।

যদি উদ্দেশ্য হয় শুধু `3`-কে বাদ দিয়ে বাকি সংখ্যা print করা, তাহলে `break` নয়, `continue` ব্যবহার করতে হবে।

### Correct Code

```python
for number in range(1, 6):
    if number == 3:
        continue
    print(number)
```

Output:

```text
1
2
4
5
```

**Solution:** পুরো loop বন্ধ করতে চাইলে `break`; শুধু বর্তমান iteration বাদ দিতে চাইলে `continue` ব্যবহার করবে।

## 9. Incorrect Use of `continue`

`continue` বর্তমান iteration-এর বাকি অংশ বাদ দিয়ে পরবর্তী iteration শুরু করে।

### Common Mistake

```python
number = 1

while number <= 5:
    if number == 3:
        continue
    print(number)
    number += 1
```

এখানে `number = 3` হলে `continue` execute হয়। ফলে `number += 1` statement-টি আর execute হয় না। `number` সব সময় `3` থাকে এবং loop আটকে যায়।

### Correct Code

```python
number = 1

while number <= 5:
    if number == 3:
        number += 1
        continue

    print(number)
    number += 1
```

Output:

```text
1
2
4
5
```

**Solution:** `while` loop-এ `continue` ব্যবহার করলে পরবর্তী iteration-এর আগে loop variable update হচ্ছে কি না নিশ্চিত করবে।

## 10. Incorrect Accumulator Initialization

Accumulator দিয়ে sum বা total হিসাব করা হয়। সঠিক initial value ব্যবহার করা জরুরি।

### Incorrect Code

```python
total = 10

for number in range(1, 4):
    total += number

print(total)
```

Output:

```text
16
```

যদি `1 + 2 + 3`-এর sum বের করতে চাও, তাহলে initial value `10` ভুল।

### Correct Code

```python
total = 0

for number in range(1, 4):
    total += number

print(total)
```

Output:

```text
6
```

**Solution:** Sum-এর accumulator সাধারণত `0` দিয়ে শুরু করবে। Multiplication-এর product accumulator সাধারণত `1` দিয়ে শুরু করবে।

## 11. Incorrect Counter Initialization

Counter কতটি item বা ঘটনা ঘটেছে, তা গণনা করে।

### Incorrect Code

```python
count = 1

for number in range(1, 6):
    count += 1

print(count)
```

Output:

```text
6
```

Loop পাঁচবার চললেও counter শুরু হয়েছে `1` থেকে।

### Correct Code

```python
count = 0

for number in range(1, 6):
    count += 1

print(count)
```

Output:

```text
5
```

**Solution:** যদি শুরুতে কোনো item গণনা করা না হয়ে থাকে, তাহলে counter `0` দিয়ে শুরু করবে।

## 12. Modifying the Wrong Variable

একাধিক variable থাকলে ভুল variable update করলে loop-এর logic নষ্ট হতে পারে।

### Incorrect Code

```python
row = 1

while row <= 3:
    column = 1

    while column <= 3:
        print("*", end=" ")
        row += 1

    print()
```

এখানে inner loop-এর মধ্যে `row` update হচ্ছে, কিন্তু `column` update হচ্ছে না। ফলে inner loop শেষ হয় না।

### Correct Code

```python
row = 1

while row <= 3:
    column = 1

    while column <= 3:
        print("*", end=" ")
        column += 1

    print()
    row += 1
```

Output:

```text
* * *
* * *
* * *
```

**Solution:** Nested loop-এ outer ও inner loop-এর control variable আলাদা করে track করবে।

## 13. Forgetting to Reset the Inner Loop Variable

Nested `while` loop-এ inner loop-এর variable প্রতিবার নতুন outer iteration-এর শুরুতে initialize করতে হয়।

### Incorrect Code

```python
row = 1
column = 1

while row <= 3:
    while column <= 3:
        print("*", end=" ")
        column += 1

    print()
    row += 1
```

Output:

```text
* * *
```

প্রথম row-এর পরে `column = 4` হয়ে যায়। পরবর্তী outer iteration-গুলোতে inner loop আর চলে না।

### Correct Code

```python
row = 1

while row <= 3:
    column = 1

    while column <= 3:
        print("*", end=" ")
        column += 1

    print()
    row += 1
```

এখানে প্রতিটি row-এর শুরুতে `column = 1` করা হয়।

## 14. Confusing `=` and `==`

Python-এ `=` assignment-এর জন্য এবং `==` value comparison-এর জন্য ব্যবহার করা হয়।

### Incorrect Code

```python
number = 1

while number = 5:
    print(number)
```

এটি `SyntaxError` তৈরি করবে, কারণ `while` condition-এ সাধারণ assignment `=` ব্যবহার করা যায় না।

### Correct Code

```python
number = 1

while number == 5:
    print(number)
```

এই code syntax-wise সঠিক, তবে condition শুরুতেই False হওয়ায় কোনো output হবে না।

যদি `1` থেকে `5` পর্যন্ত print করতে চাও:

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

**Solution:** Condition-এর জন্য `==`, `!=`, `<`, `>`, `<=` ও `>=` সঠিকভাবে ব্যবহার করবে।

## 15. Incorrect Logical Conditions

`and` ও `or` ভুলভাবে ব্যবহার করলে loop-এর condition প্রত্যাশামতো কাজ নাও করতে পারে।

### Incorrect Code

```python
number = 1

while number < 5 or number > 10:
    print(number)
    number += 1
```

এখানে `number < 5` True থাকা পর্যন্ত loop চলে। `number = 5` থেকে `10` পর্যন্ত condition False হয়, তাই loop বন্ধ হয়ে যায়।

কিন্তু যদি উদ্দেশ্য হয় `5` থেকে `10`-এর বাইরের value-গুলো নিয়ে loop চালানো, তাহলে `number = 1` থেকে শুরু করলে এই condition-এর ফলাফল বুঝে নিতে হবে।

### Another Common Mistake

```python
if choice == "yes" or "y":
    print("Accepted")
```

এখানে `"y"` একটি non-empty string, তাই condition সব সময় True হয়।

সঠিক code:

```python
if choice == "yes" or choice == "y":
    print("Accepted")
```

**Solution:** `or` বা `and` ব্যবহার করার সময় প্রতিটি comparison সম্পূর্ণভাবে লিখবে।

## 16. Incorrect Sentinel Handling

Sentinel-controlled loop-এ sentinel value দিয়ে input গ্রহণ বন্ধ করা হয়। Sentinel-কে data হিসেবে গণনা বা sum-এর সঙ্গে যোগ করা উচিত নয়, যদি problem-এ অন্য কিছু বলা না থাকে।

### Incorrect Code

```python
total = 0
number = int(input("Enter number (0 to stop): "))

while number != 0:
    total += number
    number = int(input("Enter number (0 to stop): "))
    total += number

print(total)
```

এখানে নতুন input `0` হলেও সেটি `total`-এর সঙ্গে যোগ করা হচ্ছে। `0` যোগ করলে sum বদলায় না, কিন্তু sentinel-এর পরবর্তী input-ও সঠিকভাবে handle হচ্ছে না—এ ধরনের duplicated update আরও বড় ভুলের কারণ হতে পারে।

### Correct Code

```python
total = 0
number = int(input("Enter number (0 to stop): "))

while number != 0:
    total += number
    number = int(input("Enter number (0 to stop): "))

print("Sum:", total)
```

এখানে প্রতিটি নতুন input condition-এ পরীক্ষা করা হয়। Sentinel `0` হলে loop body আর execute হয় না।

## 17. How to Debug a Loop Step by Step

Loop-এর ভুল খুঁজে বের করতে নিচের debugging process অনুসরণ করো।

### Step 1: Understand the Expected Result

প্রথমে program কী output দেওয়ার কথা, তা পরিষ্কার করো।

উদাহরণ: `1` থেকে `5` পর্যন্ত সংখ্যা print করার কথা।

### Step 2: Check the Initial Values

```python
number = 1
```

Variable সঠিক value দিয়ে শুরু হয়েছে কি না দেখো।

### Step 3: Check the Condition

```python
while number <= 5:
```

Condition প্রয়োজনীয় শেষ value-টি অন্তর্ভুক্ত করছে কি না যাচাই করো।

### Step 4: Check the Update

```python
number += 1
```

Variable সঠিক দিকে পরিবর্তিত হচ্ছে কি না দেখো।

### Step 5: Trace the Execution

প্রতিটি iteration-এর value লিখে রাখো।

### Step 6: Add Temporary Debugging Output

```python
number = 1

while number <= 5:
    print("Current number:", number)
    number += 1
```

এ ধরনের message variable-এর বর্তমান value দেখতে সাহায্য করে।

### Step 7: Test Boundary Values

শুরু, শেষ, শূন্য, একটি item এবং empty sequence-এর মতো গুরুত্বপূর্ণ case পরীক্ষা করো।

### Step 8: Retest After Fixing

একটি ভুল ঠিক করার পরে expected output-এর সঙ্গে actual output মিলিয়ে দেখো।

## 18. Using a Debugging Table

ধরি, নিচের code-এ সমস্যা আছে:

```python
number = 1

while number < 6:
    print(number)
    number += 2
```

### Dry Run Table

| Iteration | Number | Condition `number < 6` | Output | Next value |
|---:|---:|---|---:|---:|
| 1 | 1 | True | 1 | 3 |
| 2 | 3 | True | 3 | 5 |
| 3 | 5 | True | 5 | 7 |
| 4 | 7 | False | — | 7 |

Output:

```text
1
3
5
```

যদি উদ্দেশ্য হয় `1` থেকে `6` পর্যন্ত সব integer print করা, তাহলে `number += 2` ভুল update। যদি শুধু odd number print করাই উদ্দেশ্য হয়, তাহলে code ঠিক আছে।

**Important:** Code ভুল কি না, তা নির্ধারণ করতে expected behaviour জানা জরুরি।

## 19. Common Error Types

| Error type | Example | Possible solution |
|---|---|---|
| Infinite loop | Variable update নেই | Update যোগ করা |
| Wrong condition | শুরুতেই False | Boundary ঠিক করা |
| Off-by-one | `range(1, 5)` দিয়ে 1–5 আশা করা | `range(1, 6)` |
| Indentation error | Loop body indent করা নেই | Indentation ঠিক করা |
| Wrong update | Countdown-এ `+= 1` | `-= 1` |
| Wrong control statement | Skip করতে `break` | `continue` |
| Counter error | `count = 1` দিয়ে শুরু | প্রয়োজন অনুযায়ী `0` |
| Accumulator error | Sum-এর initial value ভুল | সাধারণত `total = 0` |
| Nested loop error | Inner variable update নেই | সঠিক variable update |
| Logic error | `or`-এর comparison অসম্পূর্ণ | প্রতিটি comparison লিখতে হবে |

## 20. Practice Exercises

প্রতিটি code-এ ভুল আছে কি না নির্ণয় করো। ভুল থাকলে সেটি ঠিক করার চেষ্টা করো।

### Exercise 1: Infinite Loop

```python
number = 1

while number <= 5:
    print(number)
```

### Exercise 2: Wrong Boundary

উদ্দেশ্য `1` থেকে `10` পর্যন্ত print করা।

```python
for number in range(1, 10):
    print(number)
```

### Exercise 3: Wrong Update

```python
number = 5

while number > 0:
    print(number)
    number += 1
```

### Exercise 4: Wrong Counter

```python
count = 0

for number in [2, 4, 6, 8]:
    count = 1

print(count)
```

### Exercise 5: Nested Loop

```python
row = 1

while row <= 2:
    column = 1

    while column <= 3:
        print("*", end=" ")
    print()
    row += 1
```

### Exercise 6: Wrong `continue`

```python
number = 1

while number <= 5:
    if number == 3:
        continue

    print(number)
    number += 1
```

### Exercise 7: Incorrect Condition

```python
number = 1

while number < 5 or number > 10:
    print(number)
    number += 1
```

এই condition-টি `number = 1` থেকে শুরু করলে কতদূর পর্যন্ত loop চলবে?

### Exercise 8: Debugging with Dry Run

```python
total = 0

for number in range(1, 5):
    total += number * 2

print(total)
```

Output কী হবে?

## 21. Practice Answer Key

### Answer 1

সমস্যা: `number` update হচ্ছে না।

Correct code:

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

### Answer 2

Correct code:

```python
for number in range(1, 11):
    print(number)
```

### Answer 3

সমস্যা: `number` বাড়ছে, কিন্তু condition-এ কমতে থাকা দরকার।

Correct code:

```python
number = 5

while number > 0:
    print(number)
    number -= 1
```

### Answer 4

সমস্যা: প্রতিটি iteration-এ `count = 1` হওয়ায় counter বাড়ছে না।

Correct code:

```python
count = 0

for number in [2, 4, 6, 8]:
    count += 1

print(count)
```

Output:

```text
4
```

### Answer 5

সমস্যা: Inner loop-এর মধ্যে `column` update হচ্ছে না।

Correct code:

```python
row = 1

while row <= 2:
    column = 1

    while column <= 3:
        print("*", end=" ")
        column += 1

    print()
    row += 1
```

### Answer 6

সমস্যা: `number == 3` হলে `continue` execute হয়ে variable update বাদ পড়ে যায়।

Correct code:

```python
number = 1

while number <= 5:
    if number == 3:
        number += 1
        continue

    print(number)
    number += 1
```

Output:

```text
1
2
4
5
```

### Answer 7

`number = 1` থেকে শুরু করলে `number < 5` সত্য থাকা পর্যন্ত loop চলে। `number = 5` হলে দুটি condition-ই False, তাই loop বন্ধ হয়।

Output:

```text
1
2
3
4
```

### Answer 8

`range(1, 5)` থেকে `1`, `2`, `3`, `4` পাওয়া যায়।

\[
2+4+6+8=20
\]

Output:

```text
20
```

## 22. Chapter Summary

- Debugging হলো program-এর ভুল শনাক্ত ও সমাধান করার প্রক্রিয়া।
- Infinite loop সাধারণত ভুল condition বা variable update-এর কারণে হয়।
- `range()`-এর stop value exclusive হওয়ায় off-by-one error হতে পারে।
- Python-এ indentation সঠিক হওয়া জরুরি।
- `break` loop বন্ধ করে; `continue` বর্তমান iteration skip করে।
- Counter ও accumulator সঠিক initial value দিয়ে শুরু করতে হয়।
- Nested loop-এ inner এবং outer variable সঠিকভাবে update করতে হয়।
- Debugging output ও dry-run table variable-এর পরিবর্তন বুঝতে সাহায্য করে।
- Expected behaviour-এর সঙ্গে actual output তুলনা করে logic error খুঁজে বের করা যায়।

## 23. Completion Checklist

- [ ] Infinite loop শনাক্ত ও ঠিক করতে পারি।
- [ ] ভুল loop condition সংশোধন করতে পারি।
- [ ] Variable update-এর ভুল খুঁজে বের করতে পারি।
- [ ] Off-by-one error ঠিক করতে পারি।
- [ ] Indentation error বুঝতে পারি।
- [ ] `break` ও `continue` সঠিকভাবে ব্যবহার করতে পারি।
- [ ] Counter ও accumulator-এর ভুল ঠিক করতে পারি।
- [ ] Nested loop-এর common error সমাধান করতে পারি।
- [ ] Dry run ও debugging output ব্যবহার করতে পারি।
- [ ] Expected output-এর সঙ্গে actual output মিলিয়ে দেখতে পারি।

**Next Topic:** `70_Improving_Loop_Readability.md`