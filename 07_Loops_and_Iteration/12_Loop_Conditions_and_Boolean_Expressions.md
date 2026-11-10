# 12. Loop Conditions and Boolean Expressions

## 1. Introduction

Python-এর `while` loop একটি condition-এর ওপর নির্ভর করে কাজ করে। Condition `True` হলে loop body execute হয়, আর `False` হলে loop বন্ধ হয়ে যায়।

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

এখানে `count <= 3` হলো loop condition। Python প্রতিবার condition পরীক্ষা করে এবং result অনুযায়ী সিদ্ধান্ত নেয়।

এই topic-এ আমরা শিখব:

- Boolean values: `True` ও `False`
- Boolean expressions
- Comparison operators
- Logical operators
- Loop condition কীভাবে কাজ করে
- ভুল condition থেকে কীভাবে সমস্যা তৈরি হয়

## 2. What Is a Boolean Value?

Python-এ `bool` হলো একটি built-in data type। এর দুটি value রয়েছে:

- `True`
- `False`

উদাহরণ:

```python
print(10 > 5)
print(10 < 5)
```

Output:

```text
True
False
```

প্রথম expression সত্য, তাই result `True`। দ্বিতীয় expression মিথ্যা, তাই result `False`।

**মনে রাখবে:** Python-এ `True` ও `False`-এর প্রথম অক্ষর capital হতে হবে।

## 3. What Is a Boolean Expression?

**Definition:** A Boolean expression is an expression that evaluates to `True` or `False`.

সহজ ভাষায়, যে expression-এর result `True` অথবা `False` হয়, তাকে Boolean expression বলা হয়।

উদাহরণ:

```python
age = 20

print(age >= 18)
print(age < 18)
print(age == 20)
```

Output:

```text
True
False
True
```

এখানে `age >= 18`, `age < 18` এবং `age == 20`—সবগুলো Boolean expression।

Loop-এর condition হিসেবে এ ধরনের expression ব্যবহার করা হয়।

## 4. Comparison Operators in Loop Conditions

Comparison operators দুটি value-এর মধ্যে তুলনা করে এবং Boolean result দেয়।

| Operator | অর্থ | উদাহরণ | Result |
|---|---|---|---|
| `==` | সমান | `5 == 5` | `True` |
| `!=` | সমান নয় | `5 != 3` | `True` |
| `>` | বড় | `8 > 4` | `True` |
| `<` | ছোট | `3 < 7` | `True` |
| `>=` | বড় অথবা সমান | `5 >= 5` | `True` |
| `<=` | ছোট অথবা সমান | `4 <= 6` | `True` |

### Example

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

এখানে `number <= 5` একটি comparison expression।

যতক্ষণ `number`-এর value `5` বা তার কম, ততক্ষণ condition `True` থাকে।

## 5. How a Loop Condition Works

নিচের program-টি দেখো:

```python
count = 1

while count < 4:
    print(count)
    count += 1
```

Output:

```text
1
2
3
```

### Dry Run Table

| `count` | Condition: `count < 4` | Action |
|---:|---|---|
| 1 | `True` | 1 print, তারপর count বাড়ে |
| 2 | `True` | 2 print, তারপর count বাড়ে |
| 3 | `True` | 3 print, তারপর count বাড়ে |
| 4 | `False` | Loop শেষ |

Condition শুধু loop শুরুতে একবার পরীক্ষা হয় না। প্রতিটি iteration-এর আগে আবার পরীক্ষা করা হয়।

## 6. Using Variables in Conditions

Loop condition-এ variable ব্যবহার করা যায়। Variable-এর value পরিবর্তিত হলে condition-এর result-ও পরিবর্তিত হতে পারে।

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

এখানে `number`-এর value পরিবর্তিত হওয়ার সঙ্গে সঙ্গে `number <= 10` condition পুনরায় পরীক্ষা করা হয়।

যখন `number` হয় `12`, তখন condition `False` হয় এবং loop শেষ হয়।

## 7. Using Logical Operators

একাধিক condition একত্র করতে logical operators ব্যবহার করা যায়।

Python-এর প্রধান logical operators:

- `and`
- `or`
- `not`

### 7.1 The `and` Operator

`and`-এর উভয় পাশের condition `True` হলে result `True` হয়।

```python
number = 1

while number <= 5 and number > 0:
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

এখানে `number <= 5` এবং `number > 0`—দুটো condition-ই সত্য হতে হবে।

### 7.2 The `or` Operator

`or`-এর অন্তত একটি condition `True` হলে result `True` হয়।

```python
number = 1

while number < 3 or number == 3:
    print(number)
    number += 1
```

Output:

```text
1
2
3
```

`number` যখন `4`, তখন উভয় condition `False` হয় এবং loop শেষ হয়।

এই উদাহরণে condition-টি `number <= 3` দিয়েও লেখা যায়।

### 7.3 The `not` Operator

`not` একটি Boolean result-এর বিপরীত result দেয়।

```python
is_finished = False

while not is_finished:
    print("Working...")
    is_finished = True
```

Output:

```text
Working...
```

প্রথমে `is_finished` হলো `False`, তাই `not is_finished` হলো `True`। Body execute হওয়ার পরে variable `True` হয়। পরবর্তী condition check-এ `not is_finished` হয় `False`।

## 8. Combining Conditions with User Input

User-এর দেওয়া value অনুযায়ী loop চালানো যায়।

```python
number = int(input("Enter a number greater than 0: "))

while number <= 0:
    number = int(input("Invalid! Enter a positive number: "))

print("Accepted:", number)
```

যতক্ষণ number শূন্য বা তার চেয়ে ছোট, ততক্ষণ আবার input নেওয়া হবে।

উদাহরণ:

```text
Enter a number greater than 0: -3
Invalid! Enter a positive number: 0
Invalid! Enter a positive number: 7
Accepted: 7
```

**Note:** এই উদাহরণ ধরে নেয় user integer input দেবে। অক্ষর বা decimal দিলে `int()` থেকে `ValueError` হতে পারে।

## 9. Truthy and Falsy Values in Conditions

Python-এ condition হিসেবে শুধু comparison expression নয়, অন্যান্য value-ও ব্যবহার করা যায়।

সাধারণ falsy values:

- `False`
- `None`
- `0`
- `0.0`
- `""` — empty string
- `[]` — empty list
- `{}` — empty dictionary
- `set()` — empty set

অন্যদিকে, non-empty string ও non-empty collection সাধারণত truthy।

### Example

```python
items = [10, 20, 30]

while items:
    print(items.pop())
```

Output:

```text
30
20
10
```

`items`-এ item থাকা পর্যন্ত condition truthy থাকে। প্রতিবার `pop()` একটি item সরিয়ে দেয়। List খালি হলে condition falsy হয় এবং loop শেষ হয়।

**সতর্কতা:** `pop()` list পরিবর্তন করে। এই উদাহরণে সেটি ইচ্ছাকৃতভাবে করা হয়েছে।

## 10. Common Mistakes in Loop Conditions

### Mistake 1: Wrong Comparison Operator

ভুল:

```python
count = 1

while count = 5:
    print(count)
```

এখানে `=` assignment operator। Condition-এ equality পরীক্ষা করতে `==` ব্যবহার করতে হয়।

সঠিক:

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

### Mistake 2: Condition Never Becomes False

```python
count = 1

while count <= 5:
    print(count)
    count += 0
```

`count` পরিবর্তিত হয় না। তাই condition সবসময় `True` থাকে।

### Mistake 3: Incorrect Use of `or`

```python
number = 10

while number < 5 or number > 20:
    print(number)
```

এখানে condition শুরুতেই `False`, কারণ `10 < 5` মিথ্যা এবং `10 > 20`-ও মিথ্যা। তাই body execute হবে না।

কোনো number `5` থেকে `20`-এর মধ্যে আছে কি না পরীক্ষা করতে চাইলে সাধারণত লিখবে:

```python
while number < 5 or number > 20:
    number = int(input("Enter a number from 5 to 20: "))
```

এখানে condition `True` থাকলে আবার input নেওয়া হয়।

### Mistake 4: Forgetting Operator Precedence

একাধিক logical operator ব্যবহার করলে parentheses দিয়ে condition পরিষ্কার করা ভালো।

```python
while (number > 0 and number < 10) or number == 20:
    print(number)
    break
```

এই condition-এর অর্থ হলো number `0`-এর চেয়ে বড় এবং `10`-এর চেয়ে ছোট, অথবা number ঠিক `20`।

এখানে `break` ব্যবহার করা হয়েছে যাতে উদাহরণটি একবার print করার পর loop বন্ধ হয়।

## 11. Practice Exercises

### Exercise 1

Boolean expression কী?

### Exercise 2

নিচের code-এর output কী হবে?

```python
number = 1

while number <= 3:
    print(number)
    number += 1
```

### Exercise 3

নিচের code-এর output কী হবে?

```python
number = 5

while number < 3:
    print(number)
```

### Exercise 4

নিচের code-এর output কী হবে?

```python
count = 1

while count <= 5 and count > 0:
    print(count)
    count += 2
```

### Exercise 5

কোন operator দিয়ে একাধিক condition-এর মধ্যে অন্তত একটি `True` হলেই result `True` পাওয়া যায়?

### Exercise 6

নিচের code-এ কী সমস্যা রয়েছে?

```python
count = 1

while count <= 3:
    print(count)
    count -= 1
```

### Exercise 7

একটি positive integer না পাওয়া পর্যন্ত user-এর কাছ থেকে input নেওয়ার program লেখো।

## 12. Answer Key

### Exercise 1

যে expression-এর result `True` অথবা `False` হয়, তাকে Boolean expression বলে।

### Exercise 2

```text
1
2
3
```

### Exercise 3

কোনো output নেই, কারণ `5 < 3` হলো `False`।

### Exercise 4

```text
1
3
5
```

এরপর `count` হয় `7`, ফলে `count <= 5` মিথ্যা হয় এবং loop শেষ হয়।

### Exercise 5

`or` operator।

### Exercise 6

`count` কমছে, ফলে `count <= 3` condition সত্যই থাকছে। `count += 1` ব্যবহার করলে এই উদাহরণে loop শেষ হবে।

### Exercise 7

```python
number = int(input("Enter a positive integer: "))

while number <= 0:
    number = int(input("Invalid! Try again: "))

print("Accepted:", number)
```

এই solution-এ ধরে নেওয়া হয়েছে যে user integer input দেবে।

## 13. Chapter Progress Checklist

- [ ] Boolean values ও Boolean expressions বুঝেছি।
- [ ] Comparison operators দিয়ে condition লিখতে পারি।
- [ ] `and`, `or` ও `not` ব্যবহার করতে পারি।
- [ ] Condition প্রতিবার কীভাবে পরীক্ষা হয় বুঝেছি।
- [ ] Truthy ও falsy values শনাক্ত করতে পারি।
- [ ] User input-এর ভিত্তিতে loop চালাতে পারি।
- [ ] ভুল condition ও infinite loop-এর কারণ বুঝতে পারি।

## 14. Summary

- Boolean expression-এর result `True` অথবা `False` হয়।
- `while` loop-এর condition প্রতিটি iteration-এর আগে পরীক্ষা করা হয়।
- Comparison operators value তুলনা করে।
- `and`, `or` ও `not` দিয়ে condition একত্র বা পরিবর্তন করা যায়।
- Python-এ truthy ও falsy value-ও condition হিসেবে ব্যবহার করা যায়।
- ভুল condition বা variable update-এর কারণে loop অনাকাঙ্ক্ষিতভাবে চলতে পারে।

**Next Topic:** `13_Updating_Variables_Inside_a_Loop.md`
