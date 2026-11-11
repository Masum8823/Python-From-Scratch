# 20. Introduction to the `for` Loop

## 1. Introduction

Python-এ **`for` loop** ব্যবহার করা হয় কোনো iterable-এর item একে একে access করার জন্য।

Iterable হলো এমন একটি object, যার item-গুলো একে একে পাওয়া যায়। যেমন:

- List
- Tuple
- String
- Set
- Dictionary
- `range()` object

উদাহরণ:

```python
for number in [1, 2, 3, 4, 5]:
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

এখানে `for` loop list-এর প্রতিটি item একে একে নেয় এবং print করে।

## 2. Why Do We Need a `for` Loop?

ধরো, `1` থেকে `5` পর্যন্ত number print করতে হবে।

`for` loop ছাড়া:

```python
print(1)
print(2)
print(3)
print(4)
print(5)
```

এই পদ্ধতিতে প্রতিটি number-এর জন্য আলাদা statement লিখতে হয়।

`for` loop ব্যবহার করে:

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

এখানে অল্প code ব্যবহার করে একই কাজ করা হয়েছে।

**`for` loop-এর সুবিধা:**

- Repeated code কমায়।
- Iterable-এর item একে একে process করে।
- List, string, tuple, dictionary ইত্যাদির ওপর সহজে কাজ করে।
- Counting ও data processing সহজ করে।

## 3. Syntax of the `for` Loop

```python
for variable in iterable:
    # Loop body
    statement
```

এখানে:

| অংশ | অর্থ |
|---|---|
| `for` | Loop শুরু করে |
| `variable` | প্রতিটি iteration-এ item-এর value পায় |
| `in` | Iterable থেকে item নেওয়া বোঝায় |
| `iterable` | যে object-এর item-গুলো access করা হবে |
| `:` | Loop body শুরু হওয়ার নির্দেশ দেয় |
| Indented statement | প্রতিটি iteration-এ execute হয় |

## 4. Understanding the Loop Variable

Loop variable প্রতিটি iteration-এ iterable-এর পরবর্তী item-এর value পায়।

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

এখানে:

- প্রথম iteration-এ `number = 10`
- দ্বিতীয় iteration-এ `number = 20`
- তৃতীয় iteration-এ `number = 30`

সব item process হয়ে গেলে loop শেষ হয়।

**মনে রাখবে:** `number` নামটি বাধ্যতামূলক নয়। তুমি `item`, `value` বা অন্য উপযুক্ত variable name ব্যবহার করতে পারো।

## 5. How a `for` Loop Works

ধরো, code হলো:

```python
for fruit in ["Apple", "Mango", "Banana"]:
    print(fruit)
```

Loop-এর কাজ:

1. Iterable থেকে প্রথম item নেয়: `"Apple"`।
2. `fruit` variable-এ value রাখে।
3. `print(fruit)` execute করে।
4. পরবর্তী item `"Mango"` নেয়।
5. একইভাবে `"Banana"` process করে।
6. আর item না থাকলে loop শেষ হয়।

Output:

```text
Apple
Mango
Banana
```

এখানে আলাদাভাবে counter update করতে হয়নি।

## 6. Using `for` with a List

List-এর item একে একে process করতে `for` loop ব্যবহার করা যায়।

```python
students = ["Masum", "Ritu", "Mahin"]

for student in students:
    print(student)
```

Output:

```text
Masum
Ritu
Mahin
```

এখানে প্রতিবার `student` variable list-এর পরবর্তী নামটি পায়।

## 7. Using `for` with a String

String-এর character-গুলো একে একে access করা যায়।

```python
word = "Python"

for character in word:
    print(character)
```

Output:

```text
P
y
t
h
o
n
```

এখানে প্রতিটি iteration-এ একটি character পাওয়া যায়।

## 8. Using `for` with a Tuple

Tuple-এর item-গুলোও একে একে process করা যায়।

```python
numbers = (10, 20, 30)

for number in numbers:
    print(number)
```

Output:

```text
10
20
30
```

List ও tuple-এর ক্ষেত্রে loop ব্যবহারের syntax একই।

## 9. Using `for` with a Set

Set-এর item-গুলোও iterate করা যায়।

```python
colors = {"Red", "Green", "Blue"}

for color in colors:
    print(color)
```

এখানে তিনটি color-ই print হবে, তবে তাদের output order নির্দিষ্ট নয়।

**মনে রাখবে:** Set-এর item-গুলোর কোনো নির্দিষ্ট iteration order ধরে নিয়ে program লিখবে না।

## 10. Using `for` with a Dictionary

Dictionary-এর ওপর সরাসরি `for` loop চালালে সাধারণত key পাওয়া যায়।

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}

for key in student:
    print(key)
```

Output:

```text
name
age
department
```

Dictionary-এর value পেতে `.values()` ব্যবহার করা যায়:

```python
for value in student.values():
    print(value)
```

Output:

```text
Masum
22
CSE
```

Key এবং value একসঙ্গে পেতে `.items()` ব্যবহার করা যায়:

```python
for key, value in student.items():
    print(key, value)
```

Output:

```text
name Masum
age 22
department CSE
```

Python-এর আধুনিক dictionary insertion order বজায় রাখে। তাই এই উদাহরণে key-গুলো যে ক্রমে যোগ করা হয়েছে, সেই ক্রমে iteration হয়।

## 11. Using `for` with `range()`

`range()` ব্যবহার করে নির্দিষ্ট সংখ্যক iteration চালানো যায়।

```python
for number in range(5):
    print(number)
```

Output:

```text
0
1
2
3
4
```

`range(5)` তৈরি করে `0` থেকে `4` পর্যন্ত number।

এখানে `5` অন্তর্ভুক্ত নয়।

আরেকটি উদাহরণ:

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

`range()` সম্পর্কে বিস্তারিত পরবর্তী topic-গুলোতে আলোচনা করা হবে।

## 12. Difference Between `for` and `while`

| বিষয় | `for` loop | `while` loop |
|---|---|---|
| প্রধান ব্যবহার | Iterable-এর item process করা | Condition সত্য থাকা পর্যন্ত চলা |
| Iteration | Iterable-এর item অনুযায়ী | Condition-এর ওপর নির্ভরশীল |
| Counter update | Counting-এর ক্ষেত্রে সাধারণত প্রয়োজন হয় না | Counter-based loop-এ সাধারণত প্রয়োজন হয় |
| Infinite loop risk | Iterable শেষ হলে সাধারণত শেষ হয় | Update বা condition ভুল হলে infinite হতে পারে |
| উদাহরণ | List-এর সব item print করা | User-এর সঠিক input না পাওয়া পর্যন্ত অপেক্ষা করা |

**কোনটি ব্যবহার করবে?**

- List, string বা অন্য iterable-এর প্রতিটি item process করতে চাইলে `for` ব্যবহার করো।
- কোনো condition পূরণ না হওয়া পর্যন্ত চলতে চাইলে `while` ব্যবহার করো।
- নির্দিষ্ট সংখ্যক বার কাজ করতে চাইলে `for` ও `range()` সাধারণত সহজ পদ্ধতি।

## 13. `for` Loop vs Manual Indexing

ধরো, list-এর সব নাম print করতে হবে।

### Using Manual Indexing

```python
names = ["Masum", "Ritu", "Mahin"]
index = 0

while index < len(names):
    print(names[index])
    index += 1
```

### Using `for`

```python
names = ["Masum", "Ritu", "Mahin"]

for name in names:
    print(name)
```

দুইটি code-ই একই নামগুলো print করে। তবে সরাসরি item দরকার হলে `for` loop বেশি সহজ ও পাঠযোগ্য।

## 14. Common Mistakes

### Mistake 1: Forgetting the Colon

Incorrect:

```python
for number in [1, 2, 3]
    print(number)
```

এখানে `:` না থাকায় `SyntaxError` হবে।

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

এখানে loop body indent করা হয়নি। ফলে `IndentationError` হবে।

Correct:

```python
for number in [1, 2, 3]:
    print(number)
```

### Mistake 3: Expecting `range(5)` to Start at 1

```python
for number in range(5):
    print(number)
```

Output `0` থেকে শুরু হবে, `1` থেকে নয়।

`1` থেকে `5` পর্যন্ত চাইলে:

```python
for number in range(1, 6):
    print(number)
```

### Mistake 4: Assuming a Set Has a Fixed Order

```python
numbers = {3, 1, 2}

for number in numbers:
    print(number)
```

এখানে iteration order নির্দিষ্ট ধরে নেওয়া যাবে না। নির্দিষ্ট order দরকার হলে:

```python
for number in sorted(numbers):
    print(number)
```

## 15. Practical Programs

### Program 1: Print All Numbers in a List

```python
numbers = [5, 10, 15, 20]

for number in numbers:
    print(number)
```

### Program 2: Calculate the Sum of a List

```python
numbers = [10, 20, 30, 40]
total = 0

for number in numbers:
    total += number

print("Total:", total)
```

Output:

```text
Total: 100
```

### Program 3: Count Vowels in a Word

```python
word = "education"
count = 0

for character in word:
    if character.lower() in "aeiou":
        count += 1

print("Vowels:", count)
```

Output:

```text
Vowels: 5
```

### Program 4: Print the Squares of Numbers

```python
for number in range(1, 6):
    print(number, "->", number ** 2)
```

Output:

```text
1 -> 1
2 -> 4
3 -> 9
4 -> 16
5 -> 25
```

## 16. Dry Run Example

Code:

```python
numbers = [2, 4, 6]
total = 0

for number in numbers:
    total += number

print(total)
```

Dry run:

| Iteration | `number` | আগের `total` | নতুন `total` |
|---|---:|---:|---:|
| 1 | 2 | 0 | 2 |
| 2 | 4 | 2 | 6 |
| 3 | 6 | 6 | 12 |

Output:

```text
12
```

এখানে `number` প্রতিবার list-এর পরবর্তী item নেয় এবং `total`-এর সঙ্গে যোগ হয়।

## 17. Practice Exercises

### Exercise 1

`for` loop কী এবং কেন ব্যবহার করা হয়?

### Exercise 2

Output কী হবে?

```python
for number in [2, 4, 6]:
    print(number)
```

### Exercise 3

Output কী হবে?

```python
for character in "CODE":
    print(character)
```

### Exercise 4

`1` থেকে `10` পর্যন্ত number print করার `for` loop লেখো।

### Exercise 5

নিচের list-এর সব number-এর sum বের করো।

```python
numbers = [5, 10, 15, 20]
```

### Exercise 6

Dictionary-এর সব key print করার code লেখো।

### Exercise 7

`for` ও `while` loop-এর মধ্যে দুটি পার্থক্য লেখো।

### Exercise 8

নিচের code-এ ভুল কী?

```python
for number in range(1, 5):
    print(number)
```

যদি উদ্দেশ্য হয় `1` থেকে `5` পর্যন্ত সব integer print করা।

## 18. Answer Key

### Exercise 1

`for` loop iterable-এর item একে একে process করে। Repeated code কমাতে এটি ব্যবহার করা হয়।

### Exercise 2

```text
2
4
6
```

### Exercise 3

```text
C
O
D
E
```

### Exercise 4

```python
for number in range(1, 11):
    print(number)
```

### Exercise 5

```python
numbers = [5, 10, 15, 20]
total = 0

for number in numbers:
    total += number

print(total)
```

Output:

```text
50
```

### Exercise 6

```python
student = {"name": "Masum", "age": 22}

for key in student:
    print(key)
```

### Exercise 7

- `for` loop iterable-এর item অনুযায়ী চলে; `while` loop condition অনুযায়ী চলে।
- `for` loop-এ iterable-এর item নিজে থেকে পাওয়া যায়; counter-based `while` loop-এ সাধারণত variable update করতে হয়।

### Exercise 8

`range(1, 5)`-এ `5` অন্তর্ভুক্ত নয়। সঠিক code:

```python
for number in range(1, 6):
    print(number)
```

## 19. Chapter Progress Checklist

- [ ] `for` loop-এর উদ্দেশ্য বুঝেছি।
- [ ] `for` loop-এর syntax লিখতে পারি।
- [ ] Loop variable কীভাবে value পায় বুঝেছি।
- [ ] List, tuple ও string iterate করতে পারি।
- [ ] Set ও dictionary iterate করতে পারি।
- [ ] `range()`-এর basic ব্যবহার বুঝেছি।
- [ ] `for` ও `while`-এর পার্থক্য বুঝেছি।
- [ ] Loop ব্যবহার করে sum ও counting problem সমাধান করতে পারি।

## 20. Summary

- `for` loop iterable-এর item একে একে process করে।
- List, tuple, string, set, dictionary ও `range()`-এর সঙ্গে এটি ব্যবহার করা যায়।
- Loop variable প্রতিটি iteration-এ পরবর্তী item-এর value পায়।
- `for` loop সাধারণত iterable শেষ হলে শেষ হয়।
- `while` condition-ভিত্তিক; `for` সাধারণত iterable-ভিত্তিক।
- `range()`-এর stop value অন্তর্ভুক্ত হয় না।
- সঠিক indentation ও colon ব্যবহার করতে হবে।

**Next Topic:** `21_for_Loop_Syntax_and_Execution.md`
