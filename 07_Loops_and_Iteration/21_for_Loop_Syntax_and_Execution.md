# 21. `for` Loop Syntax and Execution

## 1. Introduction

Python-এর `for` loop ব্যবহার করে কোনো iterable-এর item একে একে access করা যায়। প্রতিটি item-এর জন্য loop body একবার execute হয়।

উদাহরণ:

```python
for number in [10, 20, 30]:
    print(number)
```

Output:

```text
10
20
30
```

এখানে loop তিনবার execute হয়েছে, কারণ list-এ তিনটি item রয়েছে।

এই topic-এ আমরা শিখব:

- `for` loop-এর syntax
- Loop variable-এর কাজ
- Iterable থেকে item নেওয়ার নিয়ম
- প্রতিটি iteration-এর execution order
- Loop শেষ হওয়ার নিয়ম
- Dry run ও common mistakes

## 2. General Syntax of a `for` Loop

```python
for variable in iterable:
    statement_1
    statement_2
```

এখানে:

| অংশ | কাজ |
|---|---|
| `for` | Loop শুরু করে |
| `variable` | প্রতিটি iteration-এ item-এর value পায় |
| `in` | Iterable থেকে item নেওয়া বোঝায় |
| `iterable` | যে object-এর item process করা হবে |
| `:` | Loop body শুরু হওয়ার নির্দেশ দেয় |
| Indented statements | প্রতিটি iteration-এ execute হয় |

উদাহরণ:

```python
fruits = ["Apple", "Mango", "Banana"]

for fruit in fruits:
    print(fruit)
```

Output:

```text
Apple
Mango
Banana
```

এখানে `fruit` হলো loop variable এবং `fruits` হলো iterable।

## 3. Understanding the Loop Variable

Loop variable হলো এমন একটি variable, যেখানে প্রতিটি iteration-এ iterable-এর পরবর্তী item-এর value রাখা হয়।

```python
for number in [5, 10, 15]:
    print(number)
```

Execution:

- প্রথম iteration: `number = 5`
- দ্বিতীয় iteration: `number = 10`
- তৃতীয় iteration: `number = 15`

Output:

```text
5
10
15
```

Loop variable-এর নাম নিজের প্রয়োজন অনুযায়ী দেওয়া যায়।

```python
for item in [5, 10, 15]:
    print(item)
```

এখানে `number`-এর পরিবর্তে `item` ব্যবহার করা হয়েছে। Output একই থাকবে।

**Best practice:** Variable-এর নাম এমন রাখো, যাতে বোঝা যায় সেটিতে কী ধরনের value থাকবে।

## 4. Understanding an Iterable

**Iterable** হলো এমন একটি object, যার item-গুলো একে একে পাওয়া যায়।

উদাহরণ:

```python
# List
for item in [1, 2, 3]:
    print(item)

# String
for character in "ABC":
    print(character)

# Tuple
for item in (10, 20, 30):
    print(item)
```

এখানে list, string এবং tuple—তিনটিই iterable।

Dictionary-তে সরাসরি loop চালালে key পাওয়া যায়:

```python
student = {"name": "Masum", "age": 22}

for key in student:
    print(key)
```

Output:

```text
name
age
```

Set-এর ক্ষেত্রেও loop চালানো যায়, তবে নির্দিষ্ট iteration order ধরে নেওয়া উচিত নয়।

## 5. How a `for` Loop Executes

নিচের code-টি দেখি:

```python
numbers = [2, 4, 6]

for number in numbers:
    print(number)
```

Loop-এর execution steps:

1. Iterable থেকে প্রথম item `2` নেওয়া হয়।
2. `number`-এর value `2` হয়।
3. `print(number)` execute হয়।
4. পরবর্তী item `4` নেওয়া হয়।
5. আবার loop body execute হয়।
6. একইভাবে `6` process হয়।
7. আর কোনো item না থাকায় loop শেষ হয়।

Output:

```text
2
4
6
```

সাধারণভাবে প্রতিটি iteration-এ iterable থেকে একটি item নেওয়া হয়, loop variable-এ সেটি assign করা হয় এবং body execute হয়।

## 6. The Execution Order

একটি `for` loop-এর execution order বুঝতে এই উদাহরণটি দেখো:

```python
for number in [1, 2, 3]:
    print("Start:", number)
    print("Square:", number ** 2)

print("Loop ended")
```

Output:

```text
Start: 1
Square: 1
Start: 2
Square: 4
Start: 3
Square: 9
Loop ended
```

প্রতিটি iteration-এ প্রথমে `Start` print হয়, তারপর `Square` print হয়।

Loop শেষ হওয়ার পর indentation-এর বাইরে থাকা `print("Loop ended")` একবার execute হয়।

**মনে রাখবে:** Loop body-এর সব statement প্রতিটি iteration-এ execute হয়, যদি মাঝখানে `break`, exception বা অন্য কোনো control-flow পরিবর্তন না ঘটে।

## 7. Understanding Indentation

Python-এ indentation দিয়ে বোঝানো হয় কোন statement loop body-এর অংশ।

```python
for number in [1, 2, 3]:
    print(number)

print("Finished")
```

Output:

```text
1
2
3
Finished
```

এখানে `print(number)` loop-এর ভিতরে, কিন্তু `print("Finished")` loop-এর বাইরে।

আরেকটি উদাহরণ:

```python
for number in [1, 2, 3]:
    print("Inside loop")
    print(number)

print("Outside loop")
```

Output:

```text
Inside loop
1
Inside loop
2
Inside loop
3
Outside loop
```

এখানে loop-এর ভিতরের দুটি statement-ই প্রতিটি iteration-এ execute হয়।

## 8. Using `for` with `range()`

`range()` নির্দিষ্ট সংখ্যার sequence তৈরি করে, যা `for` loop-এর সঙ্গে খুব বেশি ব্যবহৃত হয়।

### Example 1: One Argument

```python
for number in range(4):
    print(number)
```

Output:

```text
0
1
2
3
```

`range(4)`-এ `0` থেকে `3` পর্যন্ত value পাওয়া যায়।

### Example 2: Start and Stop

```python
for number in range(2, 6):
    print(number)
```

Output:

```text
2
3
4
5
```

এখানে শুরু `2`, কিন্তু stop value `6` অন্তর্ভুক্ত নয়।

### Example 3: Start, Stop and Step

```python
for number in range(2, 11, 2):
    print(number)
```

Output:

```text
2
4
6
8
10
```

এখানে প্রতিটি iteration-এ `2` করে বাড়ছে।

`range()`-এর বিস্তারিত ব্যবহার পরবর্তী topic-গুলোতে আলোচনা করা হবে।

## 9. The Loop Variable After the Loop

Python-এ `for` loop শেষ হওয়ার পরও loop variable সাধারণত available থাকে, যদি loop অন্তত একবার execute হয়ে থাকে।

```python
for number in [10, 20, 30]:
    print(number)

print("Last value:", number)
```

Output:

```text
10
20
30
Last value: 30
```

এখানে loop শেষ হওয়ার পর `number`-এর value `30`।

তবে iterable খালি হলে loop body execute হবে না:

```python
for number in []:
    print(number)

print("Finished")
```

Output:

```text
Finished
```

এখানে `number` আগে define না থাকলে loop-এর বাইরে `number` ব্যবহার করলে `NameError` হবে।

**Best practice:** Loop-এর বাইরে loop variable-এর শেষ value-এর ওপর নির্ভর না করে প্রয়োজনীয় value আলাদাভাবে সংরক্ষণ করো।

## 10. What Happens with an Empty Iterable?

Iterable-এ কোনো item না থাকলে `for` loop-এর body একবারও execute হয় না।

```python
numbers = []

for number in numbers:
    print(number)

print("No items processed")
```

Output:

```text
No items processed
```

এখানে list খালি, তাই কোনো number print হয় না।

এটি মনে রাখা জরুরি, বিশেষ করে list থেকে data নিয়ে কাজ করার সময়।

## 11. The Number of Iterations

সাধারণভাবে `for` loop-এর iteration সংখ্যা নির্ভর করে iterable থেকে কতটি item পাওয়া যায় তার ওপর।

```python
for item in ["A", "B", "C", "D"]:
    print(item)
```

এখানে চারটি item থাকায় loop চারবার execute হবে।

`range(1, 6)` ব্যবহার করলে পাঁচটি value পাওয়া যায়, তাই loop পাঁচবার execute হয়।

তবে `break` ব্যবহার করলে iterable শেষ হওয়ার আগেই loop বন্ধ হতে পারে।

## 12. Using `break` and `continue`

এই topic-এ শুধু basic ধারণা রাখি; বিস্তারিত control statements পরের topic-এ আলোচনা করা হবে।

### `break`

`break` loop-কে সঙ্গে সঙ্গে বন্ধ করে।

```python
for number in [1, 2, 3, 4, 5]:
    if number == 3:
        break

    print(number)
```

Output:

```text
1
2
```

`number == 3` হলে loop বন্ধ হয়, তাই `3` print হয় না।

### `continue`

`continue` বর্তমান iteration-এর বাকি অংশ skip করে পরবর্তী iteration-এ যায়।

```python
for number in [1, 2, 3, 4, 5]:
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

এখানে শুধু `3` print করা হয়নি।

## 13. Dry Run Example 1

Code:

```python
for number in [3, 6, 9]:
    print(number + 1)
```

Dry run:

| Iteration | `number` | Expression | Output |
|---|---:|---|---:|
| 1 | 3 | `3 + 1` | 4 |
| 2 | 6 | `6 + 1` | 7 |
| 3 | 9 | `9 + 1` | 10 |

Output:

```text
4
7
10
```

## 14. Dry Run Example 2

Code:

```python
total = 0

for number in [2, 3, 4]:
    total += number
    print(total)

print("Final:", total)
```

Dry run:

| Iteration | `number` | আগের `total` | নতুন `total` | Output |
|---|---:|---:|---:|---|
| 1 | 2 | 0 | 2 | 2 |
| 2 | 3 | 2 | 5 | 5 |
| 3 | 4 | 5 | 9 | 9 |

শেষে output:

```text
2
5
9
Final: 9
```

এখানে `total` একটি accumulator, যা প্রতিবার আগের value-এর সঙ্গে নতুন number যোগ করে।

## 15. Common Mistakes

### Mistake 1: Forgetting the Colon

Incorrect:

```python
for number in [1, 2, 3]
    print(number)
```

এখানে colon (`:`) নেই, তাই `SyntaxError` হবে।

Correct:

```python
for number in [1, 2, 3]:
    print(number)
```

### Mistake 2: Incorrect Indentation

Incorrect:

```python
for number in [1, 2, 3]:
print(number)
```

এখানে loop body indent করা হয়নি।

Correct:

```python
for number in [1, 2, 3]:
    print(number)
```

### Mistake 3: Confusing the Item with the Index

```python
names = ["Masum", "Ritu", "Mahin"]

for name in names:
    print(name)
```

এখানে `name` হলো item, index নয়। তাই `name`-এর value হবে `"Masum"`, `"Ritu"` এবং `"Mahin"`।

Index-সহ item পেতে `enumerate()` ব্যবহার করা যায়:

```python
for index, name in enumerate(names):
    print(index, name)
```

Output:

```text
0 Masum
1 Ritu
2 Mahin
```

### Mistake 4: Modifying a List While Iterating Over It

Loop চলার সময় একই list থেকে item মুছে ফেললে কিছু item skip হয়ে যেতে পারে।

তাই list থেকে নির্দিষ্ট item বাদ দেওয়ার প্রয়োজন হলে list-এর copy বা নতুন list তৈরি করার মতো নিরাপদ পদ্ধতি ব্যবহার করা ভালো। এ বিষয়ে data structures-এর chapter-এ আরও বিস্তারিত আলোচনা করা হবে।

## 16. Practical Programs

### Program 1: Print Numbers from 1 to 5

```python
for number in range(1, 6):
    print(number)
```

### Program 2: Calculate the Sum of Numbers

```python
total = 0

for number in range(1, 6):
    total += number

print("Sum:", total)
```

Output:

```text
Sum: 15
```

### Program 3: Print Each Character

```python
word = "Python"

for character in word:
    print(character)
```

### Program 4: Count Even Numbers

```python
numbers = [2, 5, 8, 11, 14]
count = 0

for number in numbers:
    if number % 2 == 0:
        count += 1

print("Even count:", count)
```

Output:

```text
Even count: 3
```

## 17. Practice Exercises

### Exercise 1

`for` loop-এর প্রতিটি iteration-এ কী ঘটে, নিজের ভাষায় লেখো।

### Exercise 2

Output কী হবে?

```python
for number in [2, 4, 6]:
    print(number * 2)
```

### Exercise 3

Output কী হবে?

```python
for character in "DOG":
    print(character)
```

### Exercise 4

Output কী হবে?

```python
total = 0

for number in [1, 2, 3]:
    total += number

print(total)
```

### Exercise 5

`1` থেকে `10` পর্যন্ত সব odd number print করার program লেখো।

### Exercise 6

একটি list-এর item এবং index একসঙ্গে print করতে `enumerate()` ব্যবহার করো।

### Exercise 7

নিচের code-এ `Finished` কতবার print হবে?

```python
for number in [1, 2, 3]:
    print(number)

print("Finished")
```

### Exercise 8

খালি list-এর ওপর `for` loop চালালে loop body কতবার execute হবে?

## 18. Answer Key

### Exercise 1

প্রতিটি iteration-এ iterable থেকে পরবর্তী item নেওয়া হয়, loop variable-এ assign করা হয় এবং loop body execute হয়।

### Exercise 2

```text
4
8
12
```

### Exercise 3

```text
D
O
G
```

### Exercise 4

```text
6
```

### Exercise 5

```python
for number in range(1, 11, 2):
    print(number)
```

Output: `1, 3, 5, 7, 9` — প্রতিটি number আলাদা লাইনে print হবে।

### Exercise 6

```python
items = ["Pen", "Book", "Bag"]

for index, item in enumerate(items):
    print(index, item)
```

### Exercise 7

`Finished` একবার print হবে, কারণ এটি loop-এর বাইরে রয়েছে।

### Exercise 8

শূন্যবার। খালি list-এ কোনো item নেই।

## 19. Chapter Progress Checklist

- [ ] `for` loop-এর syntax বুঝেছি।
- [ ] Loop variable কীভাবে value পায় বুঝেছি।
- [ ] Iterable-এর item একে একে process করতে পারি।
- [ ] Loop body-এর execution order বুঝেছি।
- [ ] Indentation-এর গুরুত্ব বুঝেছি।
- [ ] Empty iterable-এর আচরণ বুঝেছি।
- [ ] `range()` দিয়ে নির্দিষ্ট সংখ্যক iteration চালাতে পারি।
- [ ] `enumerate()` দিয়ে index ও item একসঙ্গে পেতে পারি।
- [ ] Dry run করে loop-এর output বের করতে পারি।

## 20. Summary

- `for` loop iterable-এর item একে একে process করে।
- প্রতিটি iteration-এ loop variable পরবর্তী item-এর value পায়।
- Loop body-এর indentation সঠিক হতে হবে।
- Iterable খালি হলে loop body execute হয় না।
- Iterable-এর item শেষ হলে loop সাধারণত শেষ হয়।
- `break` loop বন্ধ করে এবং `continue` বর্তমান iteration-এর বাকি অংশ skip করে।
- `enumerate()` index ও item একসঙ্গে পেতে সাহায্য করে।
- Dry run দিয়ে প্রতিটি iteration-এর value ও output যাচাই করা যায়।

**Next Topic:** `22_Iterating_Over_Strings.md`
