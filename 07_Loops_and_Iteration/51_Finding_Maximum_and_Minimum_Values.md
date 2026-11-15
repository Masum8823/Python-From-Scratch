# 51. Finding Maximum and Minimum Values

## 1. Introduction

Programming-এ অনেক সময় একাধিক সংখ্যার মধ্যে সবচেয়ে বড় বা সবচেয়ে ছোট সংখ্যা খুঁজে বের করতে হয়।

যেমন:

- একটি list-এর সবচেয়ে বড় সংখ্যা বের করা।
- কয়েকজন শিক্ষার্থীর মধ্যে সর্বোচ্চ marks খুঁজে বের করা।
- কয়েকটি সংখ্যার মধ্যে minimum value নির্ণয় করা।
- User-এর দেওয়া সংখ্যাগুলোর maximum ও minimum বের করা।

এই কাজগুলো করার জন্য আমরা loop এবং comparison operator ব্যবহার করতে পারি।

## 2. Understanding Maximum and Minimum

**Maximum:** কোনো collection-এর সবচেয়ে বড় value।

**Minimum:** কোনো collection-এর সবচেয়ে ছোট value।

উদাহরণ:

```python
numbers = [12, 5, 27, 8, 19]
```

এখানে:

- Maximum = `27`
- Minimum = `5`

আমরা প্রতিটি সংখ্যা পরীক্ষা করে বর্তমান maximum ও minimum update করব।

## 3. Finding the Maximum Value Using a Loop

Maximum বের করার একটি সহজ পদ্ধতি হলো প্রথম সংখ্যাটিকে initial maximum হিসেবে নেওয়া। এরপর বাকি সংখ্যাগুলোর সঙ্গে তুলনা করা।

### Code

```python
numbers = [12, 5, 27, 8, 19]

maximum = numbers[0]

for number in numbers:
    if number > maximum:
        maximum = number

print("Maximum:", maximum)
```

### Output

```text
Maximum: 27
```

### Explanation

- `numbers[0]` list-এর প্রথম value, অর্থাৎ `12`।
- প্রথমে `maximum = 12`।
- প্রতিটি সংখ্যার সঙ্গে `maximum` তুলনা করা হয়।
- বর্তমান সংখ্যা বড় হলে `maximum` update হয়।
- Loop শেষে `maximum`-এ সবচেয়ে বড় value থাকে।

**মনে রাখবে:** `maximum = numbers[0]` করার আগে list খালি কি না নিশ্চিত হতে হবে।

## 4. Dry Run of Maximum Value

Code:

```python
numbers = [12, 5, 27, 8]

maximum = numbers[0]

for number in numbers:
    if number > maximum:
        maximum = number

print(maximum)
```

### Dry Run Table

| Iteration | Current number | Previous maximum | New maximum |
|---:|---:|---:|---:|
| 1 | 12 | 12 | 12 |
| 2 | 5 | 12 | 12 |
| 3 | 27 | 12 | 27 |
| 4 | 8 | 27 | 27 |

### Output

```text
27
```

প্রতিটি iteration-এ maximum-এর সঙ্গে বর্তমান সংখ্যার তুলনা হয়। বড় value পাওয়া গেলে maximum পরিবর্তিত হয়।

## 5. Finding the Minimum Value Using a Loop

Minimum বের করার পদ্ধতিও একই, তবে condition-এ `<` ব্যবহার করতে হবে।

### Code

```python
numbers = [12, 5, 27, 8, 19]

minimum = numbers[0]

for number in numbers:
    if number < minimum:
        minimum = number

print("Minimum:", minimum)
```

### Output

```text
Minimum: 5
```

### Explanation

- প্রথমে `minimum = 12`।
- প্রতিটি সংখ্যার সঙ্গে minimum তুলনা করা হয়।
- বর্তমান সংখ্যা ছোট হলে minimum update হয়।
- Loop শেষে সবচেয়ে ছোট value পাওয়া যায়।

## 6. Dry Run of Minimum Value

Code:

```python
numbers = [12, 5, 27, 8]

minimum = numbers[0]

for number in numbers:
    if number < minimum:
        minimum = number

print(minimum)
```

### Dry Run Table

| Iteration | Current number | Previous minimum | New minimum |
|---:|---:|---:|---:|
| 1 | 12 | 12 | 12 |
| 2 | 5 | 12 | 5 |
| 3 | 27 | 5 | 5 |
| 4 | 8 | 5 | 5 |

### Output

```text
5
```

## 7. Finding Maximum and Minimum Together

একটি loop ব্যবহার করেই maximum এবং minimum—দুটিই বের করা যায়।

### Code

```python
numbers = [12, 5, 27, 8, 19]

maximum = numbers[0]
minimum = numbers[0]

for number in numbers:
    if number > maximum:
        maximum = number

    if number < minimum:
        minimum = number

print("Maximum:", maximum)
print("Minimum:", minimum)
```

### Output

```text
Maximum: 27
Minimum: 5
```

### Explanation

- `maximum` সবচেয়ে বড় value সংরক্ষণ করে।
- `minimum` সবচেয়ে ছোট value সংরক্ষণ করে।
- প্রতিটি সংখ্যার জন্য দুইটি condition পরীক্ষা করা হয়।
- সব সংখ্যা পরীক্ষা করা হলে final result পাওয়া যায়।

একই loop-এ দুইটি value বের করা সম্ভব হওয়ায় অপ্রয়োজনীয়ভাবে list-টি দুইবার traverse করতে হয় না।

## 8. Why Do We Initialize with the First Element?

ধরা যাক, সব সংখ্যা negative:

```python
numbers = [-15, -4, -20, -8]
```

যদি maximum-এর initial value `0` ধরা হয়, তাহলে program ভুলভাবে `0`-কে maximum দেখাতে পারে। কারণ list-এর কোনো সংখ্যাই ০ নয়।

সঠিক পদ্ধতি:

```python
maximum = numbers[0]
```

একইভাবে minimum-এর ক্ষেত্রেও প্রথম element ব্যবহার করা ভালো।

```python
minimum = numbers[0]
```

এতে positive, negative ও zero—সব ধরনের সংখ্যার ক্ষেত্রে সঠিক ফল পাওয়া যায়, যদি list-এ অন্তত একটি value থাকে।

## 9. Finding Maximum and Minimum in User Input

ব্যবহারকারী কতটি সংখ্যা দেবেন, তা প্রথমে input নিয়ে maximum ও minimum বের করা যায়।

### Code

```python
n = int(input("How many numbers? "))

if n <= 0:
    print("Please enter a positive count.")
else:
    first = float(input("Enter a number: "))

    maximum = first
    minimum = first

    for i in range(n - 1):
        number = float(input("Enter a number: "))

        if number > maximum:
            maximum = number

        if number < minimum:
            minimum = number

    print("Maximum:", maximum)
    print("Minimum:", minimum)
```

### Sample Input and Output

```text
How many numbers? 4
Enter a number: 12
Enter a number: 5
Enter a number: 27
Enter a number: 8
Maximum: 27.0
Minimum: 5.0
```

### Explanation

- প্রথমে `n`-এর মান নেওয়া হয়।
- `n` positive হলে প্রথম সংখ্যাটি input নেওয়া হয়।
- প্রথম সংখ্যাকে initial maximum ও minimum ধরা হয়।
- বাকি `n - 1` সংখ্যার সঙ্গে তুলনা করা হয়।
- শেষে maximum এবং minimum print হয়।

এখানে input-গুলো numeric হবে বলে ধরে নেওয়া হয়েছে।

## 10. Finding Maximum and Minimum with a `while` Loop

একই কাজ `while` loop ব্যবহার করেও করা যায়।

### Code

```python
numbers = [15, 7, 32, 4, 21]

index = 1
maximum = numbers[0]
minimum = numbers[0]

while index < len(numbers):
    number = numbers[index]

    if number > maximum:
        maximum = number

    if number < minimum:
        minimum = number

    index += 1

print("Maximum:", maximum)
print("Minimum:", minimum)
```

### Output

```text
Maximum: 32
Minimum: 4
```

### Explanation

- `index = 1` দিয়ে দ্বিতীয় element থেকে শুরু করা হয়েছে।
- প্রথম element ইতিমধ্যে initial maximum ও minimum হিসেবে নেওয়া হয়েছে।
- `index < len(numbers)` condition যতক্ষণ সত্য, loop চলবে।
- প্রতিবার `index += 1` দিয়ে পরের element-এ যাওয়া হয়।

এখানে list-এ অন্তত একটি element আছে বলে ধরে নেওয়া হয়েছে।

## 11. Finding Maximum and Minimum Using Built-in Functions

Python-এ maximum ও minimum বের করার built-in function রয়েছে।

### Using `max()`

```python
numbers = [12, 5, 27, 8, 19]

print(max(numbers))
```

Output:

```text
27
```

### Using `min()`

```python
numbers = [12, 5, 27, 8, 19]

print(min(numbers))
```

Output:

```text
5
```

### Using Both

```python
numbers = [12, 5, 27, 8, 19]

print("Maximum:", max(numbers))
print("Minimum:", min(numbers))
```

Output:

```text
Maximum: 27
Minimum: 5
```

`max()` এবং `min()` দিয়ে কাজটি সহজে করা যায়। তবে loop ব্যবহার করে নিজের algorithm তৈরি করলে comparison এবং iteration-এর ধারণা ভালোভাবে বোঝা যায়।

**সতর্কতা:** খালি iterable-এ default value না দিয়ে `max()` বা `min()` ব্যবহার করলে `ValueError` হয়।

## 12. Finding the Highest Marks

একটি list-এ শিক্ষার্থীদের marks থাকলে সর্বোচ্চ marks বের করা যায়।

### Code

```python
marks = [75, 88, 92, 67, 85]

highest = marks[0]

for mark in marks:
    if mark > highest:
        highest = mark

print("Highest marks:", highest)
```

### Output

```text
Highest marks: 92
```

এখানে `highest` variable সর্বোচ্চ marks সংরক্ষণ করে।

একইভাবে minimum marks বের করতে `mark < lowest` condition ব্যবহার করা যায়।

## 13. Finding the Largest Negative Number

সব সংখ্যাই negative হলেও maximum খুঁজে পাওয়া সম্ভব।

### Code

```python
numbers = [-15, -4, -20, -8]

maximum = numbers[0]

for number in numbers:
    if number > maximum:
        maximum = number

print("Maximum:", maximum)
```

### Output

```text
Maximum: -4
```

Negative সংখ্যার মধ্যে `-4` সবচেয়ে বড়, কারণ এটি অন্য negative সংখ্যাগুলোর তুলনায় শূন্যের কাছাকাছি।

একই list-এর minimum হবে `-20`।

## 14. Finding the Second Largest Value

দ্বিতীয় বৃহত্তম **স্বতন্ত্র** value খুঁজে বের করার একটি সহজ পদ্ধতি হলো প্রথমে unique value-গুলো নিয়ে sort করা।

### Code

```python
numbers = [10, 25, 15, 25, 20]

unique_numbers = sorted(set(numbers))

if len(unique_numbers) >= 2:
    print("Second largest:", unique_numbers[-2])
else:
    print("No second largest distinct value")
```

### Output

```text
Second largest: 20
```

### Explanation

- `set(numbers)` duplicate value বাদ দেয়।
- `sorted()` সংখ্যাগুলো ছোট থেকে বড় সাজায়।
- `unique_numbers[-2]` শেষ থেকে দ্বিতীয় value দেয়।

Sorted list:

`[10, 15, 20, 25]`

এখানে দ্বিতীয় বৃহত্তম স্বতন্ত্র value হলো `20`।

**মনে রাখবে:** এই পদ্ধতিতে `set()` এবং sorting ব্যবহার করা হয়েছে। শুধু loop দিয়ে second-largest বের করার algorithm আলাদাভাবে অনুশীলন করা যায়।

## 15. Common Mistakes

### Mistake 1: Initializing Maximum with Zero

ভুল:

```python
numbers = [-10, -5, -20]
maximum = 0
```

এখানে ০ list-এর element নয়, তাই maximum ভুল হবে।

সঠিক:

```python
maximum = numbers[0]
```

### Mistake 2: Using the Wrong Comparison Operator

Maximum-এর জন্য:

```python
if number > maximum:
    maximum = number
```

Minimum-এর জন্য:

```python
if number < minimum:
    minimum = number
```

দুইটি operator উল্টো ব্যবহার করলে ফল ভুল হবে।

### Mistake 3: Forgetting to Update the Variable

ভুল:

```python
if number > maximum:
    print(number)
```

এটি শুধু বড় value print করে; `maximum` update করে না।

সঠিক:

```python
if number > maximum:
    maximum = number
```

### Mistake 4: Accessing an Empty List

ভুল:

```python
numbers = []
maximum = numbers[0]
```

এখানে `IndexError` হবে, কারণ list-এ কোনো element নেই।

সঠিক:

```python
numbers = []

if len(numbers) > 0:
    maximum = numbers[0]
    print(maximum)
else:
    print("List is empty")
```

### Mistake 5: Confusing Maximum with Second Largest

`max(numbers)` সবসময় সবচেয়ে বড় value দেয়। এটি দ্বিতীয় বৃহত্তম value দেয় না।

দ্বিতীয় বৃহত্তম স্বতন্ত্র value খুঁজতে duplicate-এর বিষয়টি বিবেচনা করতে হবে।

## 16. Practice Exercises

### Exercise 1: Maximum

```python
numbers = [5, 12, 3, 25, 9]
```

Loop ব্যবহার করে maximum বের করো।

### Exercise 2: Minimum

```python
numbers = [18, 7, 32, 4, 11]
```

Loop ব্যবহার করে minimum বের করো।

### Exercise 3: Both Maximum and Minimum

```python
numbers = [10, -5, 30, 0, 15]
```

একটি loop ব্যবহার করে maximum ও minimum বের করো।

### Exercise 4: User Input

ব্যবহারকারীর দেওয়া পাঁচটি সংখ্যার maximum ও minimum বের করার program লেখো।

### Exercise 5: Negative Numbers

```python
numbers = [-12, -3, -25, -8]
```

Maximum এবং minimum বের করো।

### Exercise 6: Predict the Output

```python
numbers = [4, 9, 2, 7]

maximum = numbers[0]

for number in numbers:
    if number > maximum:
        maximum = number

print(maximum)
```

### Exercise 7: Built-in Functions

`max()` এবং `min()` ব্যবহার করে `[8, 2, 15, 6]`-এর maximum ও minimum বের করো।

### Exercise 8: Empty List

একটি list খালি হলে maximum বের করার আগে কী পরীক্ষা করা উচিত?

## 17. Practice Answer Key

### Answer 1

```python
numbers = [5, 12, 3, 25, 9]

maximum = numbers[0]

for number in numbers:
    if number > maximum:
        maximum = number

print(maximum)
```

Output:

```text
25
```

### Answer 2

```python
numbers = [18, 7, 32, 4, 11]

minimum = numbers[0]

for number in numbers:
    if number < minimum:
        minimum = number

print(minimum)
```

Output:

```text
4
```

### Answer 3

```python
numbers = [10, -5, 30, 0, 15]

maximum = numbers[0]
minimum = numbers[0]

for number in numbers:
    if number > maximum:
        maximum = number

    if number < minimum:
        minimum = number

print("Maximum:", maximum)
print("Minimum:", minimum)
```

Output:

```text
Maximum: 30
Minimum: -5
```

### Answer 4

```python
first = float(input("Enter a number: "))

maximum = first
minimum = first

for i in range(4):
    number = float(input("Enter a number: "))

    if number > maximum:
        maximum = number

    if number < minimum:
        minimum = number

print("Maximum:", maximum)
print("Minimum:", minimum)
```

### Answer 5

```python
numbers = [-12, -3, -25, -8]

maximum = numbers[0]
minimum = numbers[0]

for number in numbers:
    if number > maximum:
        maximum = number

    if number < minimum:
        minimum = number

print("Maximum:", maximum)
print("Minimum:", minimum)
```

Output:

```text
Maximum: -3
Minimum: -25
```

### Answer 6

Output:

```text
9
```

কারণ, list-এর সবচেয়ে বড় value হলো `9`।

### Answer 7

```python
numbers = [8, 2, 15, 6]

print("Maximum:", max(numbers))
print("Minimum:", min(numbers))
```

Output:

```text
Maximum: 15
Minimum: 2
```

### Answer 8

```python
if len(numbers) > 0:
    maximum = numbers[0]
else:
    print("List is empty")
```

খালি list-এ `numbers[0]` access করলে `IndexError` হবে।

## 18. Chapter Summary

- Maximum হলো সবচেয়ে বড় value।
- Minimum হলো সবচেয়ে ছোট value।
- Loop ব্যবহার করে প্রতিটি সংখ্যার সঙ্গে বর্তমান maximum বা minimum তুলনা করা হয়।
- Maximum-এর জন্য `>` এবং minimum-এর জন্য `<` ব্যবহার করা হয়।
- Initial value হিসেবে list-এর প্রথম element নেওয়া ভালো।
- Maximum ও minimum একই loop-এ বের করা যায়।
- `max()` এবং `min()` Python-এর built-in function।
- Empty list হলে প্রথম element access করার আগে পরীক্ষা করতে হবে।
- Second-largest distinct value খুঁজতে duplicate value বিবেচনা করতে হবে।

## 19. Completion Checklist

- [ ] Loop ব্যবহার করে maximum বের করতে পারি।
- [ ] Loop ব্যবহার করে minimum বের করতে পারি।
- [ ] একই loop-এ maximum ও minimum বের করতে পারি।
- [ ] Dry run table তৈরি করতে পারি।
- [ ] User input থেকে maximum ও minimum বের করতে পারি।
- [ ] Negative number-এর ক্ষেত্রেও সঠিক ফল বের করতে পারি।
- [ ] `max()` ও `min()` ব্যবহার করতে পারি।
- [ ] Empty list সামলাতে পারি।
- [ ] Second-largest distinct value-এর ধারণা বুঝি।

**Next Topic:** `52_Counting_Even_and_Odd_Numbers.md`