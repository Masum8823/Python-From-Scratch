# 11. Writing Your First while Loop

## 1. Introduction

আগের topic-গুলোতে আমরা `while` loop-এর syntax ও execution শিখেছি। এবার সেগুলো ব্যবহার করে নিজের প্রথম loop program লিখব।

একটি `while` loop লিখতে সাধারণত চারটি বিষয় প্রয়োজন হয়:

1. Initial value নির্ধারণ করা।
2. একটি condition লেখা।
3. Condition `True` হলে কাজ করা।
4. প্রয়োজন অনুযায়ী variable update করা।

এই ধাপগুলো অনুসরণ করলে সহজে একটি working loop তৈরি করা যায়।

## 2. Your First while Loop Program

প্রথমে একটি সহজ program লিখি, যা `Hello Python` তিনবার print করবে।

```python
count = 1

while count <= 3:
    print("Hello Python")
    count += 1
```

### Output

```text
Hello Python
Hello Python
Hello Python
```

### Explanation

**Line 1:**

```python
count = 1
```

`count` variable তৈরি করে এর initial value `1` দেওয়া হয়েছে।

**Line 2:**

```python
while count <= 3:
```

যতক্ষণ `count`-এর value `3` বা তার কম থাকবে, ততক্ষণ loop চলবে।

**Line 3:**

```python
print("Hello Python")
```

প্রতিটি iteration-এ `Hello Python` print হবে।

**Line 4:**

```python
count += 1
```

প্রতিবার `count` এক করে বাড়বে।

`count` যখন `4` হবে, তখন condition `False` হবে এবং loop শেষ হবে।

## 3. Printing Numbers from 1 to 5

এবার `1` থেকে `5` পর্যন্ত number print করি।

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

### Output

```text
1
2
3
4
5
```

### Dry Run

| Iteration | `number` | Condition | Output |
|---:|---:|---|---:|
| 1 | 1 | `True` | 1 |
| 2 | 2 | `True` | 2 |
| 3 | 3 | `True` | 3 |
| 4 | 4 | `True` | 4 |
| 5 | 5 | `True` | 5 |
| শেষ পরীক্ষা | 6 | `False` | নেই |

এখানে `number`-এর value প্রতিবার এক বাড়ছে।

## 4. Printing Numbers from 1 to 10

একই নিয়ম ব্যবহার করে `1` থেকে `10` পর্যন্ত print করতে পারি।

```python
number = 1

while number <= 10:
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
6
7
8
9
10
```

খেয়াল করো, শুধু condition-এর সীমা `5` থেকে `10` করা হয়েছে।

## 5. Printing Even Numbers

এবার `2` থেকে শুরু করে প্রতিবার `2` বাড়িয়ে even number print করি।

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

এখানে `number += 2` ব্যবহারের কারণে প্রতিবার পরবর্তী even number পাওয়া যাচ্ছে।

### Alternative Method

প্রতিটি number পরীক্ষা করেও even number বের করা যায়।

```python
number = 1

while number <= 10:
    if number % 2 == 0:
        print(number)

    number += 1
```

Output একই হবে:

```text
2
4
6
8
10
```

প্রথম পদ্ধতিতে সরাসরি even number তৈরি করা হয়। দ্বিতীয় পদ্ধতিতে সব number পরীক্ষা করে even number print করা হয়।

## 6. Counting Backward

শুধু সামনে গোনা নয়, `while` loop দিয়ে উল্টো দিকেও গোনা যায়।

### Example: Countdown from 5 to 1

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

এখানে:

- শুরুতে `count = 5`।
- প্রতিবার `count` এক কমে।
- `count` যখন `0` হয়, তখন `count >= 1` condition `False` হয়।
- Loop শেষ হওয়ার পর `Finished!` print হয়।

## 7. Calculating the Sum of Numbers

Loop ব্যবহার করে একাধিক number-এর যোগফলও বের করা যায়।

### Example: Sum from 1 to 5

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

### Explanation

- `number = 1` দিয়ে counting শুরু হয়েছে।
- `total = 0` দিয়ে যোগফলের প্রাথমিক value নির্ধারণ করা হয়েছে।
- `total += number` বর্তমান number-কে total-এর সঙ্গে যোগ করে।
- `number += 1` পরবর্তী number-এ যায়।
- সব number যোগ হয়ে গেলে loop শেষ হয়।

মনে রাখবে, `number` হলো counter-এর মতো কাজ করা variable, আর `total` হলো accumulator।

## 8. Multiplication Table Using while

এবার একটি number-এর multiplication table তৈরি করি।

```python
number = 5
multiplier = 1

while multiplier <= 10:
    print(number, "x", multiplier, "=", number * multiplier)
    multiplier += 1
```

Output:

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

এখানে `multiplier` `1` থেকে `10` পর্যন্ত পরিবর্তিত হচ্ছে। প্রতিটি iteration-এ `number * multiplier` হিসাব করে print করা হচ্ছে।

## 9. Taking User Input in a while Loop

`while` loop ব্যবহার করে user-এর কাছ থেকে input নিয়ে কাজ করা যায়।

### Example: Repeat Until the User Enters 0

```python
number = -1

while number != 0:
    number = int(input("Enter a number (0 to stop): "))

print("Loop ended.")
```

উদাহরণস্বরূপ, user যদি `5`, `8`, তারপর `0` দেয়, তাহলে loop তিনবার input নেবে। `0` দেওয়ার পরে loop শেষ হবে।

Output-এর একটি সম্ভাব্য রূপ:

```text
Enter a number (0 to stop): 5
Enter a number (0 to stop): 8
Enter a number (0 to stop): 0
Loop ended.
```

এখানে `number = -1` দেওয়া হয়েছে, যাতে শুরুতে condition `number != 0` সত্য হয় এবং প্রথম input নেওয়া যায়।

**Note:** এই program ধরে নেয় user integer input দেবে। অক্ষর বা decimal input দিলে `int()` error দিতে পারে; পরে exception handling-এ এটি সামলানো শিখব।

## 10. Finding the Factorial of a Number

Factorial হলো একটি positive integer থেকে `1` পর্যন্ত সব integer-এর গুণফল।

উদাহরণ:

\[
5! = 5 \times 4 \times 3 \times 2 \times 1 = 120
\]

Python code:

```python
number = 5
factorial = 1
counter = 1

while counter <= number:
    factorial *= counter
    counter += 1

print("Factorial:", factorial)
```

Output:

```text
Factorial: 120
```

এখানে `factorial` accumulator হিসেবে কাজ করছে।

`factorial = 1` দিয়ে শুরু করা হয়েছে, কারণ গুণফলের প্রাথমিক value হিসেবে `1` প্রয়োজন।

এই code-টি `number = 0` হলেও `0! = 1` সঠিকভাবে দেবে, কারণ loop body execute হবে না এবং `factorial`-এর value `1`-ই থাকবে।

## 11. Common Mistakes While Writing a while Loop

### Mistake 1: Forgetting to Update the Variable

ভুল:

```python
count = 1

while count <= 5:
    print(count)
```

এখানে `count` পরিবর্তিত হচ্ছে না। তাই loop অনির্দিষ্টকাল চলবে।

সঠিক:

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

### Mistake 2: Using the Wrong Condition

```python
count = 1

while count >= 5:
    print(count)
    count += 1
```

এখানে শুরুতেই condition `False`, তাই কোনো output হবে না।

### Mistake 3: Incorrect Indentation

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

### Mistake 4: Incorrect Initial Value

```python
total = 0

while total < 5:
    total += 1
    print(total)
```

এই code-এ `total` শুধু যোগফল নয়, condition নিয়ন্ত্রণের কাজও করছে। ছোট উদাহরণে এটি ঠিকভাবে কাজ করলেও counting ও total আলাদা variable-এ রাখলে বড় program বুঝতে সহজ হয়।

## 12. Practice Exercises

নিজে code লেখার চেষ্টা করো। তারপর নিচের answer key-এর সঙ্গে মিলিয়ে নাও।

### Exercise 1: Print Numbers

`1` থেকে `20` পর্যন্ত number print করার program লেখো।

### Exercise 2: Odd Numbers

`1` থেকে `15` পর্যন্ত সব odd number print করো।

### Exercise 3: Countdown

`10` থেকে `1` পর্যন্ত countdown করো এবং শেষে `Go!` print করো।

### Exercise 4: Sum

`1` থেকে `10` পর্যন্ত সব integer-এর যোগফল বের করো।

### Exercise 5: Multiplication Table

User-এর দেওয়া একটি integer-এর multiplication table `1` থেকে `10` পর্যন্ত print করো।

### Exercise 6: Count Even Numbers

`1` থেকে `20` পর্যন্ত কতটি even number আছে, তা count করো।

### Exercise 7: Factorial

একটি নির্দিষ্ট non-negative integer-এর factorial বের করো।

## 13. Answer Key

### Exercise 1

```python
number = 1

while number <= 20:
    print(number)
    number += 1
```

### Exercise 2

```python
number = 1

while number <= 15:
    if number % 2 != 0:
        print(number)

    number += 1
```

### Exercise 3

```python
count = 10

while count >= 1:
    print(count)
    count -= 1

print("Go!")
```

### Exercise 4

```python
number = 1
total = 0

while number <= 10:
    total += number
    number += 1

print("Total:", total)
```

Output:

```text
Total: 55
```

### Exercise 5

```python
number = int(input("Enter a number: "))
multiplier = 1

while multiplier <= 10:
    print(number, "x", multiplier, "=", number * multiplier)
    multiplier += 1
```

### Exercise 6

```python
number = 1
even_count = 0

while number <= 20:
    if number % 2 == 0:
        even_count += 1

    number += 1

print("Even count:", even_count)
```

Output:

```text
Even count: 10
```

### Exercise 7

```python
number = 5
factorial = 1
counter = 1

while counter <= number:
    factorial *= counter
    counter += 1

print("Factorial:", factorial)
```

Output:

```text
Factorial: 120
```

এই solution-এ `number = 5` নির্দিষ্ট করা আছে। অন্য non-negative integer-এর factorial বের করতে `number`-এর value পরিবর্তন করবে।

## 14. Chapter Progress Checklist

- [ ] নিজের প্রথম `while` loop লিখতে পারি।
- [ ] Counting ও countdown করতে পারি।
- [ ] Even ও odd number print করতে পারি।
- [ ] Counter ও accumulator ব্যবহার করতে পারি।
- [ ] Multiplication table তৈরি করতে পারি।
- [ ] User input-এর ভিত্তিতে loop চালাতে পারি।
- [ ] Loop ব্যবহার করে factorial বের করতে পারি।
- [ ] ভুল condition ও variable update শনাক্ত করতে পারি।

## 15. Summary

- `while` loop condition `True` থাকা পর্যন্ত code execute করে।
- Loop লিখতে initialization, condition, body এবং প্রয়োজনীয় update বুঝতে হয়।
- Counter দিয়ে iteration বা item গণনা করা যায়।
- Accumulator দিয়ে sum ও factorial-এর মতো calculation করা যায়।
- User input-এর ওপর ভিত্তি করেও loop চালানো যায়।
- সঠিক condition ও update নিশ্চিত করলে অনাকাঙ্ক্ষিত infinite loop এড়ানো যায়।

**Next Topic:** `12_Loop_Conditions_and_Boolean_Expressions.md`
