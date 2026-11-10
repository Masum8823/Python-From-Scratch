# 14. Counter-Controlled `while` Loops

## 1. Introduction

Counter-controlled `while` loop হলো এমন একটি loop, যেখানে একটি counter variable ব্যবহার করে নির্দিষ্ট সংখ্যক বার loop চালানো হয়।

উদাহরণ:

```python
count = 1

while count <= 5:
    print("Hello Python")
    count += 1
```

Output:

```text
Hello Python
Hello Python
Hello Python
Hello Python
Hello Python
```

এখানে `count` variable-এর সাহায্যে loop পাঁচবার চালানো হয়েছে।

প্রতিবার loop চলার পর `count += 1` counter-এর value এক করে বাড়ায়। `count` যখন `6` হয়, তখন `count <= 5` condition `False` হয় এবং loop বন্ধ হয়ে যায়।

## 2. What Is a Counter?

**Counter** হলো এমন একটি variable, যা কোনো কাজ কতবার ঘটেছে বা loop কতবার চলেছে তা গণনা করে।

উদাহরণ:

```python
count = 0

count += 1
count += 1
count += 1

print(count)
```

Output:

```text
3
```

এখানে `count` তিনবার বাড়ানো হয়েছে। তাই এর final value `3`।

Counter সাধারণত `0` বা `1` থেকে শুরু করা হয়। কোনটি ব্যবহার করবে, তা সমস্যার প্রয়োজনের ওপর নির্ভর করে।

- `count = 0` — শূন্য থেকে গণনা শুরু করতে।
- `count = 1` — প্রথম iteration-কে `1` হিসেবে ধরতে।

## 3. Structure of a Counter-Controlled Loop

একটি counter-controlled `while` loop-এর সাধারণ structure:

```python
counter = starting_value

while condition:
    # কাজ
    counter += increment
```

এখানে:

| অংশ | কাজ |
|---|---|
| Initialization | Counter-এর প্রাথমিক value নির্ধারণ |
| Condition | Loop চলবে কি না পরীক্ষা |
| Loop body | প্রতিবার যে কাজ হবে |
| Update | Counter-এর value পরিবর্তন |

উদাহরণ:

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

## 4. Counting from 1 to N

১ থেকে একটি নির্দিষ্ট সংখ্যা পর্যন্ত গণনা করা counter-controlled loop-এর সবচেয়ে সাধারণ ব্যবহার।

```python
n = 5
count = 1

while count <= n:
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

এখানে `n = 5`, তাই loop ১ থেকে ৫ পর্যন্ত চলেছে।

### Dry Run

| Iteration | `count` | `count <= n` | Output |
|---:|---:|---|---:|
| 1 | 1 | `True` | 1 |
| 2 | 2 | `True` | 2 |
| 3 | 3 | `True` | 3 |
| 4 | 4 | `True` | 4 |
| 5 | 5 | `True` | 5 |
| পরবর্তী check | 6 | `False` | কিছুই নয় |

## 5. Counting from 0 to N

কখনো কখনো গণনা `0` থেকে শুরু করতে হয়।

```python
count = 0

while count < 5:
    print(count)
    count += 1
```

Output:

```text
0
1
2
3
4
```

এখানে condition হলো `count < 5`। তাই `count`-এর value `5` হলে loop বন্ধ হয়ে যায়।

### গুরুত্বপূর্ণ পার্থক্য

| Condition | Starting value | Output-এর সংখ্যা |
|---|---:|---:|
| `count <= 5` | 1 | 5 বার |
| `count < 5` | 0 | 5 বার |
| `count < 5` | 1 | 4 বার |
| `count <= 5` | 0 | 6 বার |

Loop কতবার চলবে, তা নির্ভর করে initial value, condition এবং update-এর ওপর।

## 6. Running a Loop Exactly N Times

ধরো, একটি message ঠিক ১০ বার print করতে হবে।

```python
count = 0

while count < 10:
    print("Welcome")
    count += 1
```

Output-এ `Welcome` মোট ১০ বার দেখা যাবে।

এখানে counter `0` থেকে শুরু হয়েছে। প্রতিবার body execute হওয়ার পরে counter এক করে বাড়ছে।

**সহজ নিয়ম:** Counter `0` থেকে শুরু করে `count < N` condition ব্যবহার করলে, counter প্রতিবার ঠিক এক করে বাড়লে এবং loop body-এর ভেতরে `break` বা অন্য কোনো early exit না থাকলে, loop মোট `N` বার চলে।

## 7. Counting Backward

Counter-controlled loop দিয়ে উল্টো দিকেও গণনা করা যায়।

```python
count = 5

while count >= 1:
    print(count)
    count -= 1
```

Output:

```text
5
4
3
2
1
```

এখানে:

- Starting value: `5`
- Condition: `count >= 1`
- Update: `count -= 1`

Counter কমতে কমতে `0` হলে condition `False` হয়।

## 8. Counting with a Step

প্রতিবার counter এক করে বাড়ানো বাধ্যতামূলক নয়। নির্দিষ্ট step ব্যবহার করা যায়।

### Example 1: Odd Numbers

```python
number = 1

while number <= 9:
    print(number)
    number += 2
```

Output:

```text
1
3
5
7
9
```

### Example 2: Multiples of 5

```python
number = 5

while number <= 25:
    print(number)
    number += 5
```

Output:

```text
5
10
15
20
25
```

এখানে update-এর পরিমাণ নির্ধারণ করে কোন কোন value-তে loop body execute হবে।

## 9. Taking the Limit from User Input

Counter-controlled loop-এর শেষ সীমা user-এর কাছ থেকেও নেওয়া যায়।

```python
n = int(input("Enter the limit: "))
count = 1

while count <= n:
    print(count)
    count += 1
```

যদি user `4` দেয়, output হবে:

```text
1
2
3
4
```

যদি user `0` বা negative integer দেয়, এই program কোনো সংখ্যা print করবে না, কারণ শুরুতেই `count <= n` condition `False` হবে।

**Note:** এই উদাহরণে ধরে নেওয়া হয়েছে user integer input দেবে। ভুল input দিলে `int()` থেকে `ValueError` হতে পারে।

## 10. Using a Counter to Count Items

Counter শুধু সংখ্যা print করার জন্য নয়; কোনো condition পূরণ করা item কতটি আছে তা গণনা করতেও ব্যবহার করা যায়।

উদাহরণ: ১ থেকে ১০ পর্যন্ত জোড় সংখ্যা গণনা করা।

```python
number = 1
count = 0

while number <= 10:
    if number % 2 == 0:
        count += 1

    number += 1

print("Even numbers:", count)
```

Output:

```text
Even numbers: 5
```

এখানে:

- `number` loop-এর সংখ্যা নিয়ন্ত্রণ করে।
- `count` জোড় সংখ্যার সংখ্যা গণনা করে।
- কোনো সংখ্যা জোড় হলে `count += 1` হয়।

এই দুই variable-এর কাজ আলাদা।

## 11. Counting User Input

User যতগুলো সংখ্যা দেবে, তার মধ্যে কয়টি সংখ্যা positive তা গণনা করা যায়।

```python
count = 0
positive_count = 0

while count < 5:
    number = int(input("Enter a number: "))

    if number > 0:
        positive_count += 1

    count += 1

print("Positive numbers:", positive_count)
```

এই program ঠিক পাঁচটি integer input নেয়। এরপর positive সংখ্যার সংখ্যা print করে।

উদাহরণ input:

```text
4
-2
7
0
9
```

Output:

```text
Positive numbers: 3
```

এখানে `count` পাঁচটি input নেওয়া হয়েছে কি না নিয়ন্ত্রণ করে। `positive_count` শুধু positive input গণনা করে।

## 12. Common Mistakes

### Mistake 1: Wrong Starting Value

```python
count = 1

while count < 5:
    print(count)
    count += 1
```

Output:

```text
1
2
3
4
```

এখানে `5` print হবে না, কারণ condition হলো `count < 5`।

### Mistake 2: Forgetting to Update the Counter

```python
count = 1

while count <= 5:
    print(count)
```

Counter পরিবর্তন না হওয়ায় loop অনির্দিষ্টকাল চলতে থাকবে।

### Mistake 3: Updating in the Wrong Direction

```python
count = 1

while count <= 5:
    print(count)
    count -= 1
```

Counter কমছে, তাই condition কখনো `False` হবে না।

### Mistake 4: Incorrect Step Size

```python
count = 1

while count <= 5:
    print(count)
    count += 2
```

Output:

```text
1
3
5
```

এটি ভুল নয়, যদি উদ্দেশ্য হয় বিজোড় সংখ্যা print করা। কিন্তু ১ থেকে ৫ পর্যন্ত সব integer print করতে চাইলে `count += 1` ব্যবহার করতে হবে।

### Mistake 5: Off-by-One Error

```python
count = 0

while count <= 5:
    print(count)
    count += 1
```

এখানে `0` থেকে `5` পর্যন্ত মোট ৬টি সংখ্যা print হবে। কারণ দুই প্রান্তই অন্তর্ভুক্ত।

## 13. Practice Exercises

### Exercise 1

Counter-controlled loop কী?

### Exercise 2

নিচের code-এর output কী হবে?

```python
count = 1

while count <= 4:
    print(count)
    count += 1
```

### Exercise 3

নিচের loop-এর body মোট কতবার execute হবে?

```python
count = 0

while count < 7:
    count += 1
```

### Exercise 4

১০ থেকে ১ পর্যন্ত countdown করার program লেখো।

### Exercise 5

১ থেকে ২০ পর্যন্ত ৩-এর গুণিতকগুলো print করো।

### Exercise 6

১ থেকে ১০ পর্যন্ত বিজোড় সংখ্যার সংখ্যা গণনা করো।

### Exercise 7

নিচের code-এর output কী হবে?

```python
count = 2

while count <= 10:
    print(count)
    count += 3
```

### Exercise 8

নিচের code-এ কয়টি সংখ্যা print হবে?

```python
count = 0

while count <= 5:
    print(count)
    count += 1
```

### Exercise 9

User-এর কাছ থেকে একটি positive integer `n` নিয়ে `1` থেকে `n` পর্যন্ত সব integer print করার program লেখো।

## 14. Answer Key

### Exercise 1

যে `while` loop-এ একটি counter variable ব্যবহার করে iteration-এর সংখ্যা নিয়ন্ত্রণ করা হয়, তাকে counter-controlled loop বলে।

### Exercise 2

```text
1
2
3
4
```

### Exercise 3

মোট ৭ বার।

### Exercise 4

```python
count = 10

while count >= 1:
    print(count)
    count -= 1
```

### Exercise 5

```python
number = 3

while number <= 20:
    print(number)
    number += 3
```

Output:

```text
3
6
9
12
15
18
```

### Exercise 6

```python
number = 1
count = 0

while number <= 10:
    if number % 2 != 0:
        count += 1

    number += 1

print(count)
```

Output:

```text
5
```

### Exercise 7

```text
2
5
8
```

এরপর `count` হয় `11`, ফলে condition `False` হয়।

### Exercise 8

মোট ৬টি সংখ্যা: `0, 1, 2, 3, 4, 5`।

### Exercise 9

```python
n = int(input("Enter a positive integer: "))
count = 1

while count <= n:
    print(count)
    count += 1
```

এই solution ধরে নেয় user positive integer input দেবে।

## 15. Chapter Progress Checklist

- [ ] Counter কী এবং কেন ব্যবহার করা হয় বুঝেছি।
- [ ] নির্দিষ্ট সংখ্যক বার loop চালাতে পারি।
- [ ] Starting value ও condition-এর সম্পর্ক বুঝেছি।
- [ ] Forward ও backward counting করতে পারি।
- [ ] বিভিন্ন step size ব্যবহার করতে পারি।
- [ ] Counter দিয়ে condition পূরণ করা item গণনা করতে পারি।
- [ ] Off-by-one error শনাক্ত করতে পারি।

## 16. Summary

- Counter-controlled loop একটি counter variable দিয়ে iteration নিয়ন্ত্রণ করে।
- Initialization counter-এর starting value নির্ধারণ করে।
- Condition নির্ধারণ করে loop চলবে কি না।
- Update counter-কে সামনে বা পেছনে এগিয়ে নেয়।
- `count < N` এবং `count <= N`-এর মধ্যে গুরুত্বপূর্ণ পার্থক্য রয়েছে।
- Counter-controlled loop counting, item counting এবং নির্দিষ্ট সংখ্যক input নেওয়ার কাজে ব্যবহার করা হয়।

**Next Topic:** `15_Sentinel_Controlled_while_Loops.md`
