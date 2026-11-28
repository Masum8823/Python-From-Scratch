# 25. List Comprehension Basics

## 1. What Is List Comprehension?

Python-এ **List Comprehension** হলো একটি সহজ এবং সংক্ষিপ্ত পদ্ধতি, যার মাধ্যমে একটি existing iterable থেকে নতুন List তৈরি করা যায়।

সাধারণত `for` loop ব্যবহার করে নতুন List তৈরি করতে একাধিক লাইন code লিখতে হয়। কিন্তু List Comprehension ব্যবহার করে একই কাজ এক লাইনে করা যায়।

**Example 1: Using a Normal `for` Loop**

```python
numbers = [1, 2, 3, 4, 5]

squares = []

for number in numbers:
    squares.append(number ** 2)

print(squares)
```

**Output:**

```text
[1, 4, 9, 16, 25]
```

**Example 2: Using List Comprehension**

```python
numbers = [1, 2, 3, 4, 5]

squares = [number ** 2 for number in numbers]

print(squares)
```

**Output:**

```text
[1, 4, 9, 16, 25]
```

দুটি code একই কাজ করে। তবে List Comprehension ব্যবহার করলে কম code লিখতে হয়।

---

## 2. Basic Syntax of List Comprehension

List Comprehension-এর একটি নির্দিষ্ট syntax রয়েছে।

**Syntax:**

```python
new_list = [expression for item in iterable]
```

এখানে:

- `new_list` হলো নতুন তৈরি হওয়া List।
- `expression` নির্ধারণ করে নতুন List-এ কী value থাকবে।
- `item` iterable-এর প্রতিটি element গ্রহণ করে।
- `iterable` হলো List, Tuple, String বা অন্য কোনো iterable।

**Example:**

```python
numbers = [1, 2, 3, 4, 5]

doubled = [number * 2 for number in numbers]

print(doubled)
```

**Output:**

```text
[2, 4, 6, 8, 10]
```

এখানে প্রতিটি number-এর সাথে `2` গুণ করে নতুন List তৈরি করা হয়েছে।

---

## 3. Creating a New List Using List Comprehension

List Comprehension ব্যবহার করে existing List থেকে বিভিন্নভাবে নতুন List তৈরি করা যায়।

### 3.1 Creating a List of Squares

**Example:**

```python
numbers = [1, 2, 3, 4, 5]

squares = [number ** 2 for number in numbers]

print(squares)
```

**Output:**

```text
[1, 4, 9, 16, 25]
```

এখানে প্রতিটি number-এর square বের করে নতুন List তৈরি করা হয়েছে।

### 3.2 Creating a List of Cubes

**Example:**

```python
numbers = [1, 2, 3, 4, 5]

cubes = [number ** 3 for number in numbers]

print(cubes)
```

**Output:**

```text
[1, 8, 27, 64, 125]
```

এখানে প্রতিটি number-এর cube বের করা হয়েছে।

### 3.3 Creating a List of Doubled Values

**Example:**

```python
numbers = [10, 20, 30, 40]

doubled = [number * 2 for number in numbers]

print(doubled)
```

**Output:**

```text
[20, 40, 60, 80]
```

এখানে প্রতিটি element-এর value দ্বিগুণ করে নতুন List তৈরি করা হয়েছে।

---

## 4. List Comprehension with Strings

List Comprehension ব্যবহার করে String-এর প্রতিটি character নিয়েও নতুন List তৈরি করা যায়।

**Example:**

```python
name = "Python"

letters = [letter for letter in name]

print(letters)
```

**Output:**

```text
['P', 'y', 't', 'h', 'o', 'n']
```

এখানে String-এর প্রতিটি character আলাদা element হিসেবে নতুন List-এ রাখা হয়েছে।

### Converting Characters to Uppercase

**Example:**

```python
fruits = ["apple", "banana", "mango"]

uppercase_fruits = [fruit.upper() for fruit in fruits]

print(uppercase_fruits)
```

**Output:**

```text
['APPLE', 'BANANA', 'MANGO']
```

এখানে প্রতিটি fruit-এর নাম uppercase করে নতুন List তৈরি করা হয়েছে।

---

## 5. List Comprehension with `range()`

`range()` ব্যবহার করেও List Comprehension দিয়ে নতুন List তৈরি করা যায়।

**Example 1: Creating Numbers from 0 to 4**

```python
numbers = [number for number in range(5)]

print(numbers)
```

**Output:**

```text
[0, 1, 2, 3, 4]
```

এখানে `range(5)` থেকে `0` থেকে `4` পর্যন্ত number নিয়ে নতুন List তৈরি হয়েছে।

**Example 2: Creating Squares Using `range()`**

```python
squares = [number ** 2 for number in range(1, 6)]

print(squares)
```

**Output:**

```text
[1, 4, 9, 16, 25]
```

এখানে `range(1, 6)` থেকে `1` থেকে `5` পর্যন্ত number-এর square তৈরি করা হয়েছে।

---

## 6. List Comprehension with `if` Condition

List Comprehension-এর মধ্যে `if` condition ব্যবহার করে নির্দিষ্ট condition পূরণ করা element নিয়ে নতুন List তৈরি করা যায়।

**Syntax:**

```python
new_list = [expression for item in iterable if condition]
```

এখানে:

- `expression` নতুন List-এর value নির্ধারণ করে।
- `item` প্রতিটি element গ্রহণ করে।
- `condition` পরীক্ষা করে কোন element নতুন List-এ থাকবে।

### 6.1 Selecting Even Numbers

**Example:**

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8]

even_numbers = [number for number in numbers if number % 2 == 0]

print(even_numbers)
```

**Output:**

```text
[2, 4, 6, 8]
```

এখানে শুধু যেসব number `2` দিয়ে বিভাজ্য, সেগুলো নতুন List-এ রাখা হয়েছে।

### 6.2 Selecting Odd Numbers

**Example:**

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8]

odd_numbers = [number for number in numbers if number % 2 != 0]

print(odd_numbers)
```

**Output:**

```text
[1, 3, 5, 7]
```

### 6.3 Selecting Numbers Greater Than 10

**Example:**

```python
numbers = [5, 10, 15, 20, 25, 30]

result = [number for number in numbers if number > 10]

print(result)
```

**Output:**

```text
[15, 20, 25, 30]
```

এখানে শুধু `10`-এর চেয়ে বড় number নতুন List-এ রাখা হয়েছে।

---

## 7. List Comprehension with `if-else` Condition

List Comprehension-এর মধ্যে `if-else` ব্যবহার করে condition অনুযায়ী নতুন value তৈরি করা যায়।

**Syntax:**

```python
new_list = [value_if_true if condition else value_if_false for item in iterable]
```

এখানে:

- Condition True হলে `value_if_true` নেওয়া হয়।
- Condition False হলে `value_if_false` নেওয়া হয়।

**Example:**

```python
numbers = [1, 2, 3, 4, 5, 6]

result = ["Even" if number % 2 == 0 else "Odd" for number in numbers]

print(result)
```

**Output:**

```text
['Odd', 'Even', 'Odd', 'Even', 'Odd', 'Even']
```

এখানে:

- Even number হলে `"Even"` রাখা হয়েছে।
- Odd number হলে `"Odd"` রাখা হয়েছে।

### Another Example: Replacing Negative Numbers

```python
numbers = [10, -5, 20, -8, 30]

result = [number if number > 0 else 0 for number in numbers]

print(result)
```

**Output:**

```text
[10, 0, 20, 0, 30]
```

এখানে positive number অপরিবর্তিত রাখা হয়েছে এবং negative number-এর পরিবর্তে `0` রাখা হয়েছে।

**Important Difference:**

List Comprehension-এ শুধু `if` এবং `if-else`-এর অবস্থান আলাদা।

- শুধু `if` ব্যবহার করলে condition শেষে থাকে।
- `if-else` ব্যবহার করলে conditional expression শুরুতে থাকে।

**Only `if`:**

```python
[number for number in numbers if number > 0]
```

**With `if-else`:**

```python
[number if number > 0 else 0 for number in numbers]
```

---

## 8. List Comprehension with Multiple Conditions

একটি List Comprehension-এ একাধিক `if` condition ব্যবহার করা যায়।

**Example:**

```python
numbers = [10, 15, 20, 25, 30, 35, 40]

result = [
    number for number in numbers
    if number > 10 and number < 40
    if number % 2 == 0
]

print(result)
```

**Output:**

```text
[20, 30]
```

এখানে দুটি condition পূরণ করতে হবে:

1. Number `10`-এর চেয়ে বড় এবং `40`-এর চেয়ে ছোট হতে হবে।
2. Number অবশ্যই Even হতে হবে।

### Another Example: Using `or`

```python
numbers = [5, 10, 15, 20, 25, 30]

result = [number for number in numbers if number == 10 or number == 30]

print(result)
```

**Output:**

```text
[10, 30]
```

এখানে `or` ব্যবহার করে দুটি condition-এর যেকোনো একটি True হলেই number নেওয়া হয়েছে।

---

## 9. List Comprehension with Nested Lists

List Comprehension ব্যবহার করে Nested List-এর element নিয়েও কাজ করা যায়।

**Example:**

```python
numbers = [[1, 2], [3, 4], [5, 6]]

result = [number for row in numbers for number in row]

print(result)
```

**Output:**

```text
[1, 2, 3, 4, 5, 6]
```

এখানে:

- প্রথম `for` loop প্রতিটি inner List access করে।
- দ্বিতীয় `for` loop প্রতিটি inner List-এর element access করে।
- সব element একসাথে একটি নতুন List-এ রাখা হয়েছে।

### Creating a 2D List Using List Comprehension

**Example:**

```python
matrix = [[0 for column in range(3)] for row in range(2)]

print(matrix)
```

**Output:**

```text
[[0, 0, 0], [0, 0, 0]]
```

এখানে 2টি Row এবং 3টি Column নিয়ে একটি 2D List তৈরি হয়েছে।

---

## 10. List Comprehension with Built-in Functions

List Comprehension-এর expression হিসেবে বিভিন্ন built-in function এবং method ব্যবহার করা যায়।

### 10.1 Using `abs()`

`abs()` কোনো number-এর absolute value return করে।

**Example:**

```python
numbers = [-10, -5, 0, 5, 10]

result = [abs(number) for number in numbers]

print(result)
```

**Output:**

```text
[10, 5, 0, 5, 10]
```

### 10.2 Using `len()`

**Example:**

```python
fruits = ["Apple", "Banana", "Mango"]

lengths = [len(fruit) for fruit in fruits]

print(lengths)
```

**Output:**

```text
[5, 6, 5]
```

এখানে প্রতিটি fruit-এর character সংখ্যা নতুন List-এ রাখা হয়েছে।

### 10.3 Using `round()`

**Example:**

```python
numbers = [3.14159, 2.71828, 1.41421]

result = [round(number, 2) for number in numbers]

print(result)
```

**Output:**

```text
[3.14, 2.72, 1.41]
```

এখানে প্রতিটি number-কে দুই decimal place পর্যন্ত round করা হয়েছে।

---

## 11. Difference Between Normal `for` Loop and List Comprehension

Normal `for` loop এবং List Comprehension দুটো দিয়েই নতুন List তৈরি করা যায়।

তবে এদের লেখার পদ্ধতিতে পার্থক্য রয়েছে।

**Using Normal `for` Loop:**

```python
numbers = [1, 2, 3, 4, 5]

squares = []

for number in numbers:
    squares.append(number ** 2)

print(squares)
```

**Output:**

```text
[1, 4, 9, 16, 25]
```

**Using List Comprehension:**

```python
numbers = [1, 2, 3, 4, 5]

squares = [number ** 2 for number in numbers]

print(squares)
```

**Output:**

```text
[1, 4, 9, 16, 25]
```

**Comparison:**

| Feature | Normal `for` Loop | List Comprehension |
|---|---|---|
| Syntax | Multiple lines | Usually one line |
| Readability | Easy for complex logic | Easy for simple logic |
| Code Length | More code | Less code |
| List Creation | Uses `append()` | Creates List directly |
| Usage | Complex operations | Simple transformations and filtering |

**Note:** List Comprehension সবসময় ব্যবহার করা প্রয়োজন নেই। Complex logic হলে সাধারণ `for` loop ব্যবহার করলে code পড়তে ও বুঝতে সুবিধা হয়।

---

## 12. Common Beginner Mistakes

### Mistake 1: Forgetting the Correct Syntax

**Incorrect:**

```python
numbers = [1, 2, 3, 4]

result = [for number in numbers number * 2]
```

এখানে expression সঠিক জায়গায় লেখা হয়নি।

**Correct:**

```python
numbers = [1, 2, 3, 4]

result = [number * 2 for number in numbers]

print(result)
```

**Output:**

```text
[2, 4, 6, 8]
```

### Mistake 2: Confusing `if` and `if-else` Positions

**Only `if`:**

```python
numbers = [1, 2, 3, 4, 5]

result = [number for number in numbers if number % 2 == 0]

print(result)
```

**Output:**

```text
[2, 4]
```

**With `if-else`:**

```python
numbers = [1, 2, 3, 4, 5]

result = ["Even" if number % 2 == 0 else "Odd" for number in numbers]

print(result)
```

**Output:**

```text
['Odd', 'Even', 'Odd', 'Even', 'Odd']
```

### Mistake 3: Forgetting the Expression

**Incorrect:**

```python
numbers = [1, 2, 3]

result = [for number in numbers]

print(result)
```

এখানে List Comprehension-এর মধ্যে কোনো expression নেই।

**Correct:**

```python
numbers = [1, 2, 3]

result = [number for number in numbers]

print(result)
```

**Output:**

```text
[1, 2, 3]
```

### Mistake 4: Using Too Much Complex Logic

একটি List Comprehension-এর মধ্যে অতিরিক্ত complex condition বা nested loop ব্যবহার করলে code বুঝতে কঠিন হতে পারে।

**Better Practice:** সহজ কাজের জন্য List Comprehension ব্যবহার করো এবং complex কাজের জন্য normal `for` loop ব্যবহার করো।

---

## 13. Important Points to Remember

1. List Comprehension দিয়ে সংক্ষিপ্তভাবে নতুন List তৈরি করা যায়।
2. এটি সাধারণত existing iterable-এর element নিয়ে কাজ করে।
3. List Comprehension-এর syntax হলো `[expression for item in iterable]`।
4. `expression` নতুন List-এর value নির্ধারণ করে।
5. `for` loop দিয়ে প্রতিটি element access করা হয়।
6. শুধু `if` ব্যবহার করে নির্দিষ্ট element filter করা যায়।
7. `if-else` ব্যবহার করে condition অনুযায়ী নতুন value তৈরি করা যায়।
8. একাধিক condition ব্যবহার করা যায়।
9. `range()` ব্যবহার করে নতুন List তৈরি করা যায়।
10. String-এর character নিয়েও List তৈরি করা যায়।
11. Nested loop ব্যবহার করে Nested List flatten করা যায়।
12. Built-in function এবং method expression হিসেবে ব্যবহার করা যায়।
13. Complex logic-এর জন্য normal `for` loop বেশি readable হতে পারে।

---

## 14. Practice Exercises

### Exercise 1

`1` থেকে `10` পর্যন্ত number নিয়ে একটি List তৈরি করো।

**Solution:**

```python
numbers = [number for number in range(1, 11)]

print(numbers)
```

**Output:**

```text
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

### Exercise 2

নিচের List-এর প্রতিটি number-এর square বের করো।

```python
numbers = [1, 2, 3, 4, 5]
```

**Solution:**

```python
numbers = [1, 2, 3, 4, 5]

squares = [number ** 2 for number in numbers]

print(squares)
```

**Output:**

```text
[1, 4, 9, 16, 25]
```

### Exercise 3

নিচের List থেকে শুধু Even Number বের করো।

```python
numbers = [10, 15, 20, 25, 30, 35]
```

**Solution:**

```python
numbers = [10, 15, 20, 25, 30, 35]

even_numbers = [number for number in numbers if number % 2 == 0]

print(even_numbers)
```

**Output:**

```text
[10, 20, 30]
```

### Exercise 4

নিচের List থেকে শুধু Odd Number বের করো।

```python
numbers = [1, 2, 3, 4, 5, 6]
```

**Solution:**

```python
numbers = [1, 2, 3, 4, 5, 6]

odd_numbers = [number for number in numbers if number % 2 != 0]

print(odd_numbers)
```

**Output:**

```text
[1, 3, 5]
```

### Exercise 5

নিচের List-এর প্রতিটি number-এর সাথে `5` যোগ করে নতুন List তৈরি করো।

```python
numbers = [10, 20, 30, 40]
```

**Solution:**

```python
numbers = [10, 20, 30, 40]

result = [number + 5 for number in numbers]

print(result)
```

**Output:**

```text
[15, 25, 35, 45]
```

### Exercise 6

নিচের List-এর প্রতিটি String uppercase করো।

```python
fruits = ["apple", "banana", "mango"]
```

**Solution:**

```python
fruits = ["apple", "banana", "mango"]

result = [fruit.upper() for fruit in fruits]

print(result)
```

**Output:**

```text
['APPLE', 'BANANA', 'MANGO']
```

### Exercise 7

নিচের List-এর number Even হলে `"Even"` এবং Odd হলে `"Odd"` রাখো।

```python
numbers = [1, 2, 3, 4, 5]
```

**Solution:**

```python
numbers = [1, 2, 3, 4, 5]

result = ["Even" if number % 2 == 0 else "Odd" for number in numbers]

print(result)
```

**Output:**

```text
['Odd', 'Even', 'Odd', 'Even', 'Odd']
```

### Exercise 8

নিচের List থেকে `10`-এর চেয়ে বড় number এবং Even number নির্বাচন করো।

```python
numbers = [5, 10, 15, 20, 25, 30, 35, 40]
```

**Solution:**

```python
numbers = [5, 10, 15, 20, 25, 30, 35, 40]

result = [number for number in numbers if number > 10 and number % 2 == 0]

print(result)
```

**Output:**

```text
[20, 30, 40]
```

### Exercise 9

নিচের Nested List-কে একটি single List-এ রূপান্তর করো।

```python
numbers = [[1, 2], [3, 4], [5, 6]]
```

**Solution:**

```python
numbers = [[1, 2], [3, 4], [5, 6]]

result = [number for row in numbers for number in row]

print(result)
```

**Output:**

```text
[1, 2, 3, 4, 5, 6]
```

### Exercise 10

নিচের List-এর প্রতিটি String-এর length বের করো।

```python
fruits = ["Apple", "Banana", "Mango"]
```

**Solution:**

```python
fruits = ["Apple", "Banana", "Mango"]

result = [len(fruit) for fruit in fruits]

print(result)
```

**Output:**

```text
[5, 6, 5]
```

### Exercise 11

নিচের code-এর output কী হবে?

```python
numbers = [1, 2, 3, 4, 5]

result = [number * 2 for number in numbers if number > 2]

print(result)
```

**Solution:**

```text
[6, 8, 10]
```

### Exercise 12

নিচের code-এর output কী হবে?

```python
numbers = [1, 2, 3, 4]

result = [number if number % 2 == 0 else 0 for number in numbers]

print(result)
```

**Solution:**

```text
[0, 2, 0, 4]
```

---

## 15. Chapter Summary

এই topic-এ আমরা Python-এর List Comprehension সম্পর্কে শিখেছি।

- List Comprehension দিয়ে কম code লিখে নতুন List তৈরি করা যায়।
- Basic syntax হলো `[expression for item in iterable]`।
- `range()` ব্যবহার করে List তৈরি করা যায়।
- String থেকে character নিয়ে নতুন List তৈরি করা যায়।
- `if` ব্যবহার করে নির্দিষ্ট element filter করা যায়।
- `if-else` ব্যবহার করে condition অনুযায়ী value তৈরি করা যায়।
- Multiple conditions ব্যবহার করা যায়।
- Nested List flatten করা যায়।
- Built-in functions ব্যবহার করা যায়।

---

## 16. Self-Assessment Checklist

নিজে যাচাই করো:

- [ ] List Comprehension কী তা বুঝতে পেরেছি।
- [ ] Basic syntax লিখতে পারি।
- [ ] Existing List থেকে নতুন List তৈরি করতে পারি।
- [ ] Number-এর square এবং cube বের করতে পারি।
- [ ] String থেকে character নিয়ে List তৈরি করতে পারি।
- [ ] `range()` ব্যবহার করতে পারি।
- [ ] `if` condition ব্যবহার করে element filter করতে পারি।
- [ ] `if-else` ব্যবহার করে নতুন value তৈরি করতে পারি।
- [ ] Multiple conditions ব্যবহার করতে পারি।
- [ ] Nested List flatten করতে পারি।
- [ ] List Comprehension এবং normal `for` loop-এর পার্থক্য বুঝতে পেরেছি।

---

## 17. Next Topic

**26. List Comprehension with Multiple Conditions**

পরবর্তী topic-এ আমরা List Comprehension-এর মধ্যে একাধিক condition ব্যবহার করে কীভাবে নির্দিষ্ট element নির্বাচন এবং নতুন List তৈরি করা যায়, তা আরও বিস্তারিতভাবে শিখব।