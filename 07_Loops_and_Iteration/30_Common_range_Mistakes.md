# 30. Common `range()` Mistakes

## 1. Introduction

Python-এ `range()` function ব্যবহার করে একটি নির্দিষ্ট sequence of integers তৈরি করা যায়। এটি সাধারণত `for` loop-এর সঙ্গে ব্যবহার করা হয়।

তবে `range()` ব্যবহারের সময় কিছু common mistake হয়:

- Stop value-কে sequence-এর অংশ মনে করা।
- ভুল step ব্যবহার করা।
- Forward counting-এর জায়গায় backward counting করা বা উল্টোটা।
- Empty range তৈরি করা।
- `range()`-এর argument ভুলভাবে দেওয়া।
- Output prediction করার সময় sequence-এর শেষ value ভুল হিসাব করা।

এই ভুলগুলো বুঝতে পারলে loop-এর output সহজে নির্ণয় করা যাবে।

## 2. Mistake 1: Forgetting That the Stop Value Is Excluded

`range()`-এর সবচেয়ে গুরুত্বপূর্ণ নিয়ম হলো, **start অন্তর্ভুক্ত হয়, কিন্তু stop অন্তর্ভুক্ত হয় না।**

### Example

```python
for number in range(1, 5):
    print(number)
```

**Output:**

```text
1
2
3
4
```

এখানে `5` print হয়নি।

কারণ:

- Start = `1`
- Stop = `5`
- Step = `1`

সুতরাং sequence হলো `1, 2, 3, 4`।

### Correct way to print 1 to 5

```python
for number in range(1, 6):
    print(number)
```

**Output:**

```text
1
2
3
4
5
```

**মনে রাখবে:** নির্দিষ্ট শেষ সংখ্যাটি print করতে চাইলে step-এর দিক অনুযায়ী stop value এমনভাবে দিতে হবে, যাতে সেটি sequence-এ না এলেও তার আগের value হিসেবে শেষ সংখ্যাটি আসে।

## 3. Mistake 2: Using the Wrong Step Direction

`range()`-এর default step হলো `1`। তাই start যদি stop-এর চেয়ে বড় হয়, তাহলে negative step দিতে হবে।

### Incorrect example

```python
for number in range(10, 1):
    print(number)
```

**Output:**

```text
```

কোনো output নেই।

কারণ default step `+1`, কিন্তু `10` থেকে `1`-এর দিকে যেতে হলে negative step প্রয়োজন।

### Correct example

```python
for number in range(10, 0, -1):
    print(number)
```

**Output:**

```text
10
9
8
7
6
5
4
3
2
1
```

## 4. Mistake 3: Using a Negative Step for Forward Counting

Forward counting-এর জন্য সাধারণত positive step প্রয়োজন।

### Incorrect example

```python
for number in range(1, 10, -1):
    print(number)
```

**Output:**

```text
```

কোনো output নেই।

কারণ `1` থেকে শুরু করে `10`-এর দিকে যেতে হলে positive step প্রয়োজন। Negative step ব্যবহার করলে sequence stop-এর দিকে এগোয় না।

### Correct example

```python
for number in range(1, 10, 1):
    print(number)
```

**Output:**

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
```

এখানে `1` থেকে `9` পর্যন্ত print হয়েছে।

## 5. Mistake 4: Using Zero as the Step

`range()`-এর step কখনো `0` হতে পারে না।

### Incorrect example

```python
for number in range(1, 10, 0):
    print(number)
```

এটি চালালে error হবে:

```text
ValueError: range() arg 3 must not be zero
```

কারণ Python বুঝতে পারবে না প্রতিবার কত করে পরবর্তী value তৈরি করতে হবে।

### Correct examples

```python
range(1, 10, 1)
range(1, 10, 2)
range(10, 0, -1)
```

এখানে সব step non-zero।

## 6. Mistake 5: Misunderstanding the One-Argument Form

`range(n)`-এ counting শুরু হয় `0` থেকে, এবং `n` অন্তর্ভুক্ত হয় না।

### Example

```python
for number in range(5):
    print(number)
```

**Output:**

```text
0
1
2
3
4
```

এখানে মোট পাঁচটি সংখ্যা print হয়েছে, `1` থেকে `5` নয়।

যদি `1` থেকে `5` পর্যন্ত print করতে চাও:

```python
for number in range(1, 6):
    print(number)
```

## 7. Mistake 6: Confusing the Number of Iterations with the Last Value

`range()` কতবার চলবে আর শেষ value কত হবে—এ দুটি আলাদা বিষয়।

### Example

```python
for number in range(3, 12, 2):
    print(number)
```

**Output:**

```text
3
5
7
9
11
```

এখানে:

- মোট iteration = `5`
- শেষ value = `11`
- Stop value = `12`

Step `2` হওয়ায় sequence-এর প্রতিটি value দুই করে বাড়ছে।

### Dry Run Table

| Iteration | Value |
|---|---:|
| 1 | 3 |
| 2 | 5 |
| 3 | 7 |
| 4 | 9 |
| 5 | 11 |

পরবর্তী value `13`, যা stop value `12`-এর সীমা অতিক্রম করে।

## 8. Mistake 7: Incorrectly Calculating the Stop Value

ধরা যাক, `2` থেকে `10` পর্যন্ত even numbers print করতে হবে।

### Incorrect example

```python
for number in range(2, 10, 2):
    print(number)
```

**Output:**

```text
2
4
6
8
```

এখানে `10` print হয়নি।

### Correct example

```python
for number in range(2, 11, 2):
    print(number)
```

**Output:**

```text
2
4
6
8
10
```

Stop value `11` হলেও sequence-এ `11` আসবে না, কারণ step `2`।

## 9. Mistake 8: Assuming Every Stop Value Will Be Reached

`range()`-এ stop value দেওয়া মানেই সেই value sequence-এ থাকবে না।

### Example

```python
for number in range(1, 10, 3):
    print(number)
```

**Output:**

```text
1
4
7
```

Sequence-এর পরবর্তী value `10`, কিন্তু stop value `10` হওয়ায় এটি অন্তর্ভুক্ত হয়নি।

### Another example

```python
for number in range(2, 12, 4):
    print(number)
```

**Output:**

```text
2
6
10
```

পরবর্তী value `14`, যা stop value `12`-এর বাইরে।

**মূল কথা:** `range()` নির্দিষ্ট step অনুসরণ করে। Stop value-তে পৌঁছানো বাধ্যতামূলক নয়।

## 10. Mistake 9: Incorrect Backward Counting with Step

Backward counting-এ negative step ব্যবহার করতে হয়। Step-এর পরিমাণও ঠিক রাখতে হবে।

### Example

```python
for number in range(10, 0, -3):
    print(number)
```

**Output:**

```text
10
7
4
1
```

এখানে `10` থেকে শুরু করে প্রতিবার `3` কমেছে।

পরবর্তী value `-2`, যা stop value `0`-এর নিচে চলে যায়।

### Common confusion

অনেকে মনে করে `range(10, 0, -3)` সব সময় `10, 7, 4, 1, 0` print করবে।

এটি ভুল। `0` stop value হওয়ায় অন্তর্ভুক্ত হয় না। তাছাড়া এই step-এ sequence সরাসরি `0`-তেও পৌঁছায় না।

## 11. Mistake 10: Passing Non-Integer Arguments

`range()`-এর start, stop ও step হিসেবে integer প্রয়োজন।

### Incorrect example

```python
range(1.5, 10, 1)
```

এটি `TypeError` তৈরি করবে।

### Correct example

```python
range(1, 10, 1)
```

যদি decimal values নিয়ে কাজ করতে হয়, তাহলে `range()` সরাসরি উপযুক্ত নয়। প্রয়োজন অনুযায়ী `while` loop বা অন্য numerical tools ব্যবহার করা যায়।

**সতর্কতা:** `int(1.5)` লিখলে ফল `1` হবে। এটি rounding নয়; decimal অংশ বাদ পড়ে। তাই float-কে integer-এ রূপান্তর করার আগে কাঙ্ক্ষিত ফল নিশ্চিত করতে হবে।

## 12. Mistake 11: Confusing `range()` with a List

Python 3-এ `range()` একটি `range` object তৈরি করে; সরাসরি list তৈরি করে না।

### Example

```python
numbers = range(1, 6)

print(numbers)
print(list(numbers))
```

**Output:**

```text
range(1, 6)
[1, 2, 3, 4, 5]
```

- `range(1, 6)` একটি range object।
- `list(numbers)` সেটির value-গুলোকে list-এ রূপান্তর করে।

যখন সব value একসঙ্গে দেখতে হবে বা list হিসেবে ব্যবহার করতে হবে, তখন `list()` ব্যবহার করা যায়।

## 13. Mistake 12: Miscounting an Empty Range

কিছু `range()`-এ কোনো value-ই থাকে না।

### Examples

```python
print(list(range(0)))
print(list(range(5, 1)))
print(list(range(1, 5, -1)))
```

**Output:**

```text
[]
[]
[]
```

কারণ:

- `range(0)`-এ কোনো value নেই।
- `range(5, 1)`-এ default positive step দিয়ে stop-এর দিকে যাওয়া যায় না।
- `range(1, 5, -1)`-এ negative step দিয়ে stop-এর দিকে যাওয়া যায় না।

Empty range হলে loop-এর body একবারও execute হয় না।

## 14. Mistake 13: Modifying the Loop Variable and Expecting to Change `range()`

`for` loop-এর variable-কে body-এর মধ্যে পরিবর্তন করলে `range()`-এর পরবর্তী value বদলে যায় না।

### Example

```python
for number in range(1, 5):
    number += 10
    print(number)
```

**Output:**

```text
11
12
13
14
```

এখানে প্রতিবার `range()` থেকে আসা value-এর সঙ্গে `10` যোগ করা হয়েছে।

কিন্তু পরবর্তী iteration-এ `range()` আবার তার পরবর্তী নির্ধারিত value দেয়। তাই এটি `while` loop-এর counter update-এর মতো কাজ করে না।

## 15. Mistake 14: Off-by-One Errors

Off-by-one error হলো loop প্রয়োজনের তুলনায় একবার বেশি বা একবার কম চালানো।

### Example: Printing 1 to 10

ভুল:

```python
for number in range(1, 10):
    print(number)
```

এখানে `10` বাদ পড়েছে।

সঠিক:

```python
for number in range(1, 11):
    print(number)
```

### Example: List Index

```python
names = ["Masum", "Ritu", "Mahin"]

for index in range(len(names)):
    print(names[index])
```

**Output:**

```text
Masum
Ritu
Mahin
```

এখানে `len(names)` হলো `3`, তাই index-গুলো `0, 1, 2`।

`range(len(names))` ব্যবহার করলে valid index পাওয়া যায়। তবে শুধু item-এর value দরকার হলে সরাসরি list-এর ওপর loop করা আরও সহজ:

```python
for name in names:
    print(name)
```

## 16. Quick Reference Table

| প্রয়োজন | সঠিক code | ফলাফল |
|---|---|---|
| `0` থেকে `4` | `range(5)` | `0, 1, 2, 3, 4` |
| `1` থেকে `5` | `range(1, 6)` | `1, 2, 3, 4, 5` |
| `2` করে সামনে | `range(2, 11, 2)` | `2, 4, 6, 8, 10` |
| `5` থেকে `1` | `range(5, 0, -1)` | `5, 4, 3, 2, 1` |
| `2` করে পেছনে | `range(10, 0, -2)` | `10, 8, 6, 4, 2` |
| Empty range | `range(5, 1)` | কোনো value নেই |

## 17. Practice Exercises

### Exercise 1: Find the Output

```python
for number in range(1, 6):
    print(number)
```

### Exercise 2: Find the Output

```python
for number in range(2, 12, 3):
    print(number)
```

### Exercise 3: Find the Output

```python
for number in range(10, 0, -4):
    print(number)
```

### Exercise 4: Find the Output

```python
for number in range(5, 1):
    print(number)
```

### Exercise 5: Fix the Code

নিচের code-এ `1` থেকে `10` পর্যন্ত print করতে হবে।

```python
for number in range(1, 10):
    print(number)
```

### Exercise 6: Fix the Code

নিচের code-এ `10` থেকে `1` পর্যন্ত print করতে হবে।

```python
for number in range(10, 0):
    print(number)
```

### Exercise 7: Find the Output

```python
for number in range(3, 15, 4):
    print(number)
```

### Exercise 8: Explain the Error

```python
for number in range(1, 10, 0):
    print(number)
```

## 18. Practice Answer Key

### Answer 1

```text
1
2
3
4
5
```

### Answer 2

```text
2
5
8
11
```

### Answer 3

```text
10
6
2
```

### Answer 4

কোনো output হবে না। Default step `+1`, কিন্তু start `5` stop `1`-এর চেয়ে বড়।

### Answer 5

```python
for number in range(1, 11):
    print(number)
```

### Answer 6

```python
for number in range(10, 0, -1):
    print(number)
```

### Answer 7

```text
3
7
11
```

পরবর্তী value `15`, কিন্তু stop value `15` অন্তর্ভুক্ত নয়।

### Answer 8

`ValueError` হবে, কারণ `range()`-এর step `0` হতে পারে না।

## 19. Chapter Summary

এই topic-এ আমরা শিখেছি:

1. `range()`-এর stop value বাদ যায়।
2. Forward counting-এর জন্য সাধারণত positive step লাগে।
3. Backward counting-এর জন্য negative step লাগে।
4. Step `0` হলে `ValueError` হয়।
5. `range()`-এর arguments integer হতে হয়।
6. Start, stop ও step-এর অসামঞ্জস্যে empty range হতে পারে।
7. `range()` একটি range object তৈরি করে।
8. Off-by-one error এড়াতে start ও stop সাবধানে নির্ধারণ করতে হয়।

## 20. Completion Checklist

- [ ] `range()`-এর stop value-এর নিয়ম বুঝি।
- [ ] Positive ও negative step সঠিকভাবে ব্যবহার করতে পারি।
- [ ] Empty range শনাক্ত করতে পারি।
- [ ] `ValueError` ও `TypeError`-এর সাধারণ কারণ বুঝি।
- [ ] Off-by-one error ঠিক করতে পারি।
- [ ] `range()`-এর output dry run করে বের করতে পারি।

**Next Topic:** `31_The_else_Clause_in_for_Loops.md`
