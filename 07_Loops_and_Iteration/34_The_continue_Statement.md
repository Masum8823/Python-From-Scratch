# 34. The `continue` Statement

## 1. Introduction

Python-এ `continue` statement ব্যবহার করে loop-এর বর্তমান iteration-এর বাকি অংশ বাদ দিয়ে পরবর্তী iteration শুরু করা যায়।

সহজভাবে:

**`continue` = বর্তমান iteration skip করে পরবর্তী iteration-এ যাও।**

এটি `for` এবং `while`—দুই ধরনের loop-এই ব্যবহার করা যায়।

## 2. Syntax of `continue`

```python
for variable in sequence:
    if condition:
        continue

    # Remaining statements
```

এখানে condition সত্য হলে `continue` execute হয়। ফলে ওই iteration-এ `continue`-এর পরের statement-গুলো execute হয় না।

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

এখানে `number = 3` হলে `print(number)` execute হয়নি। কিন্তু loop বন্ধও হয়নি; `4` ও `5`-এর জন্য চলেছে।

## 3. Understanding the Execution Flow

নিচের code-টি দেখো:

```python
for number in range(1, 5):
    print("Checking:", number)

    if number == 2:
        continue

    print("Accepted:", number)
```

**Output:**

```text
Checking: 1
Accepted: 1
Checking: 2
Checking: 3
Accepted: 3
Checking: 4
Accepted: 4
```

### Explanation

- `Checking` statement প্রতিটি iteration-এ আগে execute হয়।
- `number = 2` হলে `continue` execute হয়।
- তাই ওই iteration-এ `Accepted` message print হয় না।
- এরপর loop পরবর্তী iteration শুরু করে।

**গুরুত্বপূর্ণ:** `continue`-এর আগে execute হওয়া statement-এর output মুছে যায় না।

## 4. Using `continue` in a `for` Loop

### Example: Skip Number 3

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

এখানে শুধু `3` skip হয়েছে। বাকি সংখ্যাগুলো print হয়েছে।

### Example: Skip Multiple Numbers

```python
for number in range(1, 11):
    if number == 3 or number == 7:
        continue

    print(number)
```

**Output:**

```text
1
2
4
5
6
8
9
10
```

এখানে `3` এবং `7`—দুটিই skip হয়েছে।

## 5. Using `continue` to Skip Even Numbers

যদি শুধু odd number print করতে চাও, তাহলে even number-গুলো skip করতে পারো।

```python
for number in range(1, 11):
    if number % 2 == 0:
        continue

    print(number)
```

**Output:**

```text
1
3
5
7
9
```

### Explanation

- `number % 2 == 0` হলে সংখ্যাটি even।
- Condition সত্য হলে `continue` execute হয়।
- তাই even number print হয় না।
- Odd number-এর ক্ষেত্রে condition false, তাই `print()` execute হয়।

## 6. Using `continue` to Skip Odd Numbers

এবার শুধু even number print করব।

```python
for number in range(1, 11):
    if number % 2 != 0:
        continue

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

এখানে odd number-গুলো skip করা হয়েছে।

## 7. Using `continue` with Strings

`continue` ব্যবহার করে কোনো string-এর নির্দিষ্ট character বাদ দেওয়া যায়।

### Example: Skip Spaces

```python
text = "Python is easy"

for character in text:
    if character == " ":
        continue

    print(character)
```

**Output:**

```text
P
y
t
h
o
n
i
s
e
a
s
y
```

এখানে space character-গুলো print হয়নি।

### Example: Skip Vowels

```python
text = "python"

for character in text:
    if character in "aeiou":
        continue

    print(character)
```

**Output:**

```text
p
y
t
h
n
```

এখানে `o` vowel হওয়ায় skip হয়েছে।

## 8. Using `continue` with Lists

List-এর নির্দিষ্ট value skip করেও অন্য value-গুলো process করা যায়।

### Example: Skip Zero

```python
numbers = [10, 0, 20, 0, 30]

for number in numbers:
    if number == 0:
        continue

    print(number)
```

**Output:**

```text
10
20
30
```

এখানে zero বাদ দিয়ে বাকি সংখ্যাগুলো print হয়েছে।

### Example: Skip Negative Numbers

```python
numbers = [10, -5, 20, -2, 30]

for number in numbers:
    if number < 0:
        continue

    print(number)
```

**Output:**

```text
10
20
30
```

এখানে negative number-গুলো skip হয়েছে।

## 9. Using `continue` in a `while` Loop

`while` loop-এ `continue` ব্যবহার করার সময় বিশেষ সতর্ক থাকতে হয়।

### Example

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

### Explanation

1. `number` শুরু হয়েছে `0` থেকে।
2. Loop-এর শুরুতে `number` এক করে বাড়ে।
3. `number == 3` হলে `continue` execute হয়।
4. তাই `3` print হয় না।
5. পরবর্তী iteration-এ `number` আবার বাড়ে এবং loop চলতে থাকে।

এখানে increment statement `continue`-এর আগে রয়েছে, তাই `number` সঠিকভাবে update হচ্ছে।

## 10. Important Warning: `continue` Can Cause an Infinite Loop

`while` loop-এ `continue`-এর কারণে variable update বাদ পড়ে গেলে infinite loop হতে পারে।

### Incorrect Example

```python
number = 1

while number <= 5:
    if number == 3:
        continue

    print(number)
    number += 1
```

এই code-এ:

- `number = 1` ও `2` হলে print হয় এবং variable বাড়ে।
- `number = 3` হলে `continue` execute হয়।
- ফলে `number += 1` execute হয় না।
- `number` সব সময় `3` থাকে।
- Loop অনির্দিষ্টকাল চলতে থাকে।

### Correct Example

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

এখানে `continue`-এর আগে `number += 1` করা হয়েছে। ফলে `number`-এর value `3` থেকে `4` হয় এবং loop চলতে থাকে।

আরও সহজ উপায় হলো loop-এর শুরুতেই variable update করা, যেমন Topic 9-এ দেখানো হয়েছে।

## 11. Difference Between `break` and `continue`

| বিষয় | `break` | `continue` |
|---|---|---|
| কাজ | Loop বন্ধ করে | বর্তমান iteration skip করে |
| পরবর্তী iteration | হয় না | হয় |
| Loop-এর বাকি অংশ | সম্পূর্ণ বন্ধ | শুধু বর্তমান iteration-এর বাকি অংশ বাদ |
| ব্যবহার | Search শেষ করা, loop থেকে বের হওয়া | নির্দিষ্ট value বাদ দেওয়া |

### Example: `break`

```python
for number in range(1, 6):
    if number == 3:
        break

    print(number)
```

Output:

```text
1
2
```

### Example: `continue`

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

## 12. Using `continue` with Nested Loops

Nested loop-এ `continue` ব্যবহার করলে এটি যে loop-এর মধ্যে রয়েছে, সেই loop-এর বর্তমান iteration skip করে।

### Example

```python
for i in range(1, 3):
    for j in range(1, 4):
        if j == 2:
            continue

        print(i, j)
```

**Output:**

```text
1 1
1 3
2 1
2 3
```

### Explanation

- Outer loop `i = 1` ও `i = 2` নেয়।
- Inner loop প্রতিবার `j = 1, 2, 3` নেয়।
- `j = 2` হলে inner loop-এর বর্তমান iteration skip হয়।
- `j = 1` ও `j = 3` print হয়।

এখানে outer loop skip হয়নি; শুধু inner loop-এর নির্দিষ্ট iteration বাদ পড়েছে।

## 13. Practical Example: Processing Valid Marks

ধরা যাক, একটি list-এ কিছু valid ও invalid marks আছে। আমরা `0` থেকে `100`-এর বাইরে থাকা marks skip করব।

```python
marks_list = [85, -5, 70, 110, 95]

for marks in marks_list:
    if marks < 0 or marks > 100:
        continue

    print("Valid marks:", marks)
```

**Output:**

```text
Valid marks: 85
Valid marks: 70
Valid marks: 95
```

এখানে `-5` ও `110` invalid হওয়ায় skip হয়েছে।

**Note:** এই example-এ invalid marks-কে শুধু বাদ দেওয়া হয়েছে। বাস্তব application-এ invalid data আলাদাভাবে report বা log করার প্রয়োজন হতে পারে।

## 14. Practical Example: Processing Names

কোনো list-এ খালি string থাকলে সেটি skip করা যায়।

```python
names = ["Masum", "", "Ritu", "", "Mahin"]

for name in names:
    if name == "":
        continue

    print(name)
```

**Output:**

```text
Masum
Ritu
Mahin
```

এখানে empty string-গুলো print হয়নি।

যদি whitespace-only string-ও বাদ দিতে চাও, তাহলে `if not name.strip():` ব্যবহার করা যায়।

## 15. Common Mistakes

### Mistake 1: Thinking `continue` Stops the Whole Loop

এটি ভুল। `continue` শুধু বর্তমান iteration-এর বাকি অংশ বাদ দেয়।

### Mistake 2: Putting Important Code After `continue`

```python
for number in range(1, 5):
    if number == 2:
        continue

    print(number)
```

এখানে `number == 2` হলে `print()` আর execute হয় না, কারণ সেটি `continue`-এর পরে রয়েছে।

### Mistake 3: Forgetting to Update the `while` Loop Variable

`while` loop-এ `continue`-এর আগে প্রয়োজনীয় update না থাকলে infinite loop হতে পারে।

### Mistake 4: Using an Unnecessary `continue`

নিচের code:

```python
for number in range(1, 6):
    if number == 3:
        continue
    print(number)
```

একই কাজ অন্যভাবেও লেখা যায়:

```python
for number in range(1, 6):
    if number != 3:
        print(number)
```

দুটি code-ই `1, 2, 4, 5` print করে। কোনটি বেশি পরিষ্কার, তা পরিস্থিতির ওপর নির্ভর করে।

## 16. Practice Exercises

### Exercise 1: Find the Output

```python
for number in range(1, 6):
    if number == 4:
        continue

    print(number)
```

### Exercise 2: Find the Output

```python
for number in range(1, 11):
    if number % 2 != 0:
        continue

    print(number)
```

### Exercise 3: Find the Output

```python
for character in "banana":
    if character == "a":
        continue

    print(character)
```

### Exercise 4: Find the Output

```python
numbers = [5, -2, 8, -1, 10]

for number in numbers:
    if number < 0:
        continue

    print(number)
```

### Exercise 5: Fix the Infinite Loop

```python
number = 1

while number <= 5:
    if number == 3:
        continue

    print(number)
    number += 1
```

এমনভাবে code ঠিক করো, যেন `1, 2, 4, 5` print হয়।

### Exercise 6: Write a Program

`1` থেকে `20` পর্যন্ত শুধু `3` দিয়ে বিভাজ্য নয়—এমন সংখ্যাগুলো print করো। `continue` ব্যবহার করতে হবে।

## 17. Practice Answer Key

### Answer 1

```text
1
2
3
5
```

### Answer 2

```text
2
4
6
8
10
```

### Answer 3

```text
b
n
n
```

### Answer 4

```text
5
8
10
```

### Answer 5

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

### Answer 6

```python
for number in range(1, 21):
    if number % 3 == 0:
        continue

    print(number)
```

এখানে `3, 6, 9, 12, 15, 18` skip হবে।

## 18. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `continue` বর্তমান iteration-এর বাকি অংশ বাদ দেয়।
- `for` ও `while` loop-এ `continue` ব্যবহার করা যায়।
- Even/odd number filtering-এ এটি উপযোগী।
- String ও list থেকে নির্দিষ্ট value skip করা যায়।
- Nested loop-এ এটি সবচেয়ে ভেতরের সংশ্লিষ্ট loop-এর বর্তমান iteration skip করে।
- `while` loop-এ variable update-এর দিকে বিশেষ নজর দিতে হয়।

## 19. Completion Checklist

- [ ] `continue`-এর syntax বুঝি।
- [ ] নির্দিষ্ট সংখ্যা skip করতে পারি।
- [ ] Even ও odd number filter করতে পারি।
- [ ] String ও list-এর value skip করতে পারি।
- [ ] `while` loop-এ infinite loop এড়াতে পারি।
- [ ] `break` ও `continue`-এর পার্থক্য ব্যাখ্যা করতে পারি।

**Next Topic:** `35_The_pass_Statement_in_Loops.md`
