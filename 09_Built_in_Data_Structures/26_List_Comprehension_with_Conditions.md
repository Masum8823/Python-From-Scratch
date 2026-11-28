# 26. List Comprehension with Multiple Conditions

## 1. Introduction to Multiple Conditions in List Comprehension

Python-এ List Comprehension-এর মধ্যে একাধিক condition ব্যবহার করে নির্দিষ্ট element নির্বাচন করে নতুন List তৈরি করা যায়।

একাধিক condition ব্যবহার করার জন্য সাধারণত `and` এবং `or` logical operators ব্যবহার করা হয়।

**Example:**

```python
numbers = [5, 10, 15, 20, 25, 30, 35, 40]

result = [
    number for number in numbers
    if number > 10 and number < 40
]

print(result)
```

**Output:**

```text
[15, 20, 25, 30, 35]
```

এখানে দুটি condition পূরণ করতে হবে:

- Number অবশ্যই `10`-এর চেয়ে বড় হতে হবে।
- Number অবশ্যই `40`-এর চেয়ে ছোট হতে হবে।

---

## 2. Using `and` Operator in List Comprehension

`and` operator ব্যবহার করলে সব condition True হতে হবে। কোনো একটি condition False হলে element নতুন List-এ যুক্ত হবে না।

**Syntax:**

```python
new_list = [
    expression for item in iterable
    if condition1 and condition2
]
```

### Example 1: Selecting Numbers Within a Range

```python
numbers = [5, 10, 15, 20, 25, 30, 35, 40]

result = [
    number for number in numbers
    if number >= 15 and number <= 30
]

print(result)
```

**Output:**

```text
[15, 20, 25, 30]
```

এখানে শুধু `15` থেকে `30` পর্যন্ত number নির্বাচন করা হয়েছে।

### Example 2: Selecting Even Numbers Within a Range

```python
numbers = [5, 10, 15, 20, 25, 30, 35, 40]

result = [
    number for number in numbers
    if number > 10 and number < 40 and number % 2 == 0
]

print(result)
```

**Output:**

```text
[20, 30]
```

এখানে তিনটি condition পূরণ করতে হবে:

1. Number `10`-এর চেয়ে বড় হতে হবে।
2. Number `40`-এর চেয়ে ছোট হতে হবে।
3. Number Even হতে হবে।

### Example 3: Selecting Positive Even Numbers

```python
numbers = [-10, -5, 0, 5, 10, 15, 20, 25]

result = [
    number for number in numbers
    if number > 0 and number % 2 == 0
]

print(result)
```

**Output:**

```text
[10, 20]
```

এখানে শুধু positive Even Number নির্বাচন করা হয়েছে।

---

## 3. Using `or` Operator in List Comprehension

`or` operator ব্যবহার করলে একাধিক condition-এর মধ্যে যেকোনো একটি True হলেই element নতুন List-এ যুক্ত হবে।

**Syntax:**

```python
new_list = [
    expression for item in iterable
    if condition1 or condition2
]
```

### Example 1: Selecting Specific Numbers

```python
numbers = [5, 10, 15, 20, 25, 30, 35]

result = [
    number for number in numbers
    if number == 10 or number == 30
]

print(result)
```

**Output:**

```text
[10, 30]
```

এখানে number `10` অথবা `30` হলে সেটি নতুন List-এ যুক্ত হবে।

### Example 2: Selecting Numbers Divisible by 2 or 3

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 12]

result = [
    number for number in numbers
    if number % 2 == 0 or number % 3 == 0
]

print(result)
```

**Output:**

```text
[2, 3, 4, 6, 8, 9, 10, 12]
```

এখানে যেসব number `2` অথবা `3` দিয়ে বিভাজ্য, সেগুলো নির্বাচন করা হয়েছে।

### Example 3: Selecting Negative or Zero Values

```python
numbers = [-10, -5, 0, 5, 10, 15]

result = [
    number for number in numbers
    if number < 0 or number == 0
]

print(result)
```

**Output:**

```text
[-10, -5, 0]
```

এখানে negative number অথবা zero নির্বাচন করা হয়েছে।

---

## 4. Using Multiple `if` Conditions

List Comprehension-এ একাধিক `if` condition আলাদাভাবেও লেখা যায়।

**Syntax:**

```python
new_list = [
    expression for item in iterable
    if condition1
    if condition2
]
```

এখানে প্রতিটি `if` condition পূরণ করতে হবে।

**Example:**

```python
numbers = [5, 10, 15, 20, 25, 30, 35, 40]

result = [
    number for number in numbers
    if number > 10
    if number % 2 == 0
]

print(result)
```

**Output:**

```text
[20, 30, 40]
```

এখানে:

- প্রথম condition পরীক্ষা করে number `10`-এর চেয়ে বড় কি না।
- দ্বিতীয় condition পরীক্ষা করে number Even কি না।
- দুটি condition পূরণ হলেই number নতুন List-এ যুক্ত হয়।

**Important:** এখানে একাধিক `if` ব্যবহার করা হয়েছে। এটি `and` দিয়ে একই শর্ত লেখার মতোই কাজ করছে।

---

## 5. Combining `and` and `or` Operators

একই List Comprehension-এ `and` এবং `or` একসাথে ব্যবহার করা যায়।

এক্ষেত্রে condition-এর grouping পরিষ্কার রাখতে parentheses `()` ব্যবহার করা ভালো।

**Example 1:**

```python
numbers = [5, 10, 15, 20, 25, 30, 35, 40]

result = [
    number for number in numbers
    if (number == 10 or number == 20) and number > 10
]

print(result)
```

**Output:**

```text
[20]
```

এখানে:

- Number `10` অথবা `20` হতে হবে।
- একই সাথে number `10`-এর চেয়ে বড় হতে হবে।

তাই শুধু `20` নির্বাচন হয়েছে।

### Example 2: Selecting Specific Even or Odd Values

```python
numbers = [5, 10, 15, 20, 25, 30, 35, 40]

result = [
    number for number in numbers
    if (number < 20 or number > 30) and number % 2 == 0
]

print(result)
```

**Output:**

```text
[10, 40]
```

এখানে:

- Number `20`-এর চেয়ে ছোট অথবা `30`-এর চেয়ে বড় হতে হবে।
- Number অবশ্যই Even হতে হবে।

---

## 6. Multiple Conditions with String Lists

String-এর List-এর ক্ষেত্রেও একাধিক condition ব্যবহার করা যায়।

### Example 1: Selecting Long and Uppercase Words

```python
words = ["apple", "BANANA", "mango", "ORANGE", "grapes"]

result = [
    word for word in words
    if len(word) > 5 and word.isupper()
]

print(result)
```

**Output:**

```text
['BANANA', 'ORANGE']
```

এখানে:

- `len(word) > 5` দিয়ে পাঁচটির বেশি character আছে কি না পরীক্ষা করা হয়েছে।
- `word.isupper()` দিয়ে String uppercase কি না পরীক্ষা করা হয়েছে।

### Example 2: Selecting Words with Specific Lengths

```python
words = ["cat", "apple", "banana", "dog", "mango"]

result = [
    word for word in words
    if len(word) == 3 or len(word) == 5
]

print(result)
```

**Output:**

```text
['cat', 'apple', 'mango', 'dog']
```

এখানে 3 অথবা 5 character-এর String নির্বাচন করা হয়েছে।

---

## 7. Multiple Conditions with `if-else`

List Comprehension-এ `if-else` ব্যবহার করে condition অনুযায়ী নতুন value তৈরি করা যায়।

**Syntax:**

```python
new_list = [
    value_if_true if condition else value_if_false
    for item in iterable
]
```

### Example 1: Even and Odd

```python
numbers = [1, 2, 3, 4, 5, 6]

result = [
    "Even" if number % 2 == 0 else "Odd"
    for number in numbers
]

print(result)
```

**Output:**

```text
['Odd', 'Even', 'Odd', 'Even', 'Odd', 'Even']
```

### Example 2: Using Multiple Conditions in `if-else`

```python
numbers = [5, 10, 15, 20, 25, 30, 35]

result = [
    "Selected" if number > 10 and number < 30 else "Not Selected"
    for number in numbers
]

print(result)
```

**Output:**

```text
['Not Selected', 'Not Selected', 'Selected', 'Selected', 'Selected', 'Not Selected', 'Not Selected']
```

এখানে:

- Number `10`-এর চেয়ে বড় এবং `30`-এর চেয়ে ছোট হলে `"Selected"`।
- অন্যথায় `"Not Selected"`।

---

## 8. Difference Between Multiple `if` and `if-else`

List Comprehension-এ `if` এবং `if-else`-এর কাজ আলাদা।

| Feature | Multiple `if` | `if-else` |
|---|---|---|
| Purpose | Filter elements | Select output values |
| Condition False | Element বাদ যায় | Alternative value নেওয়া হয় |
| Output Length | কম হতে পারে | সাধারণত input-এর সমান |
| Position | Expression-এর পরে | Expression-এর মধ্যে |

**Example 1: Multiple `if`**

```python
numbers = [1, 2, 3, 4, 5]

result = [number for number in numbers if number > 2]

print(result)
```

**Output:**

```text
[3, 4, 5]
```

এখানে condition False হলে element বাদ পড়ে যায়।

**Example 2: `if-else`**

```python
numbers = [1, 2, 3, 4, 5]

result = [
    number if number > 2 else 0
    for number in numbers
]

print(result)
```

**Output:**

```text
[0, 0, 3, 4, 5]
```

এখানে condition False হলে `0` রাখা হয়েছে।

---

## 9. Common Beginner Mistakes

### Mistake 1: Using `and` Instead of `or`

**Incorrect:**

```python
numbers = [10, 20, 30, 40]

result = [
    number for number in numbers
    if number == 10 and number == 30
]

print(result)
```

**Output:**

```text
[]
```

এখানে একটি number একই সময়ে `10` এবং `30` হতে পারে না।

**Correct:**

```python
numbers = [10, 20, 30, 40]

result = [
    number for number in numbers
    if number == 10 or number == 30
]

print(result)
```

**Output:**

```text
[10, 30]
```

### Mistake 2: Incorrect Placement of `if-else`

**Incorrect:**

```python
numbers = [1, 2, 3, 4]

result = [
    number for number in numbers
    if number % 2 == 0 else 0
]
```

এখানে `if-else`-এর syntax ভুল।

**Correct:**

```python
numbers = [1, 2, 3, 4]

result = [
    number if number % 2 == 0 else 0
    for number in numbers
]

print(result)
```

**Output:**

```text
[0, 2, 0, 4]
```

### Mistake 3: Forgetting Parentheses in Complex Conditions

একাধিক `and` এবং `or` ব্যবহার করলে condition-এর grouping পরিষ্কার রাখা জরুরি।

**Better Practice:**

```python
numbers = [10, 15, 20, 25, 30, 35]

result = [
    number for number in numbers
    if (number == 10 or number == 20) and number % 2 == 0
]

print(result)
```

**Output:**

```text
[10, 20]
```

### Mistake 4: Using `and` When Only One Condition Is Required

```python
numbers = [10, 20, 30, 40]

result = [
    number for number in numbers
    if number < 20 or number > 30
]

print(result)
```

**Output:**

```text
[10, 40]
```

এখানে `or` ব্যবহার করা হয়েছে, কারণ দুটি condition-এর যেকোনো একটি পূরণ হলেই element নির্বাচন করতে হবে।

---

## 10. Important Points to Remember

1. Multiple Conditions ব্যবহার করে নির্দিষ্ট element নির্বাচন করা যায়।
2. `and` ব্যবহার করলে সব condition True হতে হবে।
3. `or` ব্যবহার করলে যেকোনো একটি condition True হলেই হবে।
4. একাধিক `if` ব্যবহার করে sequential filtering করা যায়।
5. `if-else` condition অনুযায়ী নতুন value তৈরি করে।
6. শুধু `if` ব্যবহার করলে condition False হলে element বাদ যায়।
7. `if-else` ব্যবহার করলে condition False হলেও alternative value পাওয়া যায়।
8. Complex condition-এ parentheses `()` ব্যবহার করলে code বোঝা সহজ হয়।
9. String এবং Number উভয়ের ক্ষেত্রেই multiple conditions ব্যবহার করা যায়।
10. অতিরিক্ত complex List Comprehension এড়িয়ে চলা উচিত।

---

## 11. Practice Exercises

### Exercise 1

নিচের List থেকে `10`-এর চেয়ে বড় এবং `30`-এর চেয়ে ছোট number নির্বাচন করো।

```python
numbers = [5, 10, 15, 20, 25, 30, 35]
```

**Solution:**

```python
numbers = [5, 10, 15, 20, 25, 30, 35]

result = [
    number for number in numbers
    if number > 10 and number < 30
]

print(result)
```

**Output:**

```text
[15, 20, 25]
```

### Exercise 2

নিচের List থেকে `10` অথবা `30` নির্বাচন করো।

```python
numbers = [10, 20, 30, 40, 50]
```

**Solution:**

```python
numbers = [10, 20, 30, 40, 50]

result = [
    number for number in numbers
    if number == 10 or number == 30
]

print(result)
```

**Output:**

```text
[10, 30]
```

### Exercise 3

নিচের List থেকে positive Even Number নির্বাচন করো।

```python
numbers = [-10, -5, 0, 5, 10, 15, 20, 25]
```

**Solution:**

```python
numbers = [-10, -5, 0, 5, 10, 15, 20, 25]

result = [
    number for number in numbers
    if number > 0 and number % 2 == 0
]

print(result)
```

**Output:**

```text
[10, 20]
```

### Exercise 4

নিচের List থেকে যেসব number `3` অথবা `5` দিয়ে বিভাজ্য, সেগুলো নির্বাচন করো।

```python
numbers = [3, 5, 10, 12, 15, 20, 25, 30]
```

**Solution:**

```python
numbers = [3, 5, 10, 12, 15, 20, 25, 30]

result = [
    number for number in numbers
    if number % 3 == 0 or number % 5 == 0
]

print(result)
```

**Output:**

```text
[3, 5, 10, 12, 15, 20, 25, 30]
```

### Exercise 5

নিচের List থেকে 5 character-এর বেশি এবং uppercase word নির্বাচন করো।

```python
words = ["apple", "BANANA", "mango", "ORANGE", "grapes"]
```

**Solution:**

```python
words = ["apple", "BANANA", "mango", "ORANGE", "grapes"]

result = [
    word for word in words
    if len(word) > 5 and word.isupper()
]

print(result)
```

**Output:**

```text
['BANANA', 'ORANGE']
```

### Exercise 6

Even number হলে `"Even"` এবং Odd number হলে `"Odd"` রাখো।

```python
numbers = [1, 2, 3, 4, 5]
```

**Solution:**

```python
numbers = [1, 2, 3, 4, 5]

result = [
    "Even" if number % 2 == 0 else "Odd"
    for number in numbers
]

print(result)
```

**Output:**

```text
['Odd', 'Even', 'Odd', 'Even', 'Odd']
```

### Exercise 7

Number `10`-এর চেয়ে বড় এবং `30`-এর চেয়ে ছোট হলে `"Yes"` অন্যথায় `"No"` রাখো।

```python
numbers = [5, 10, 15, 20, 25, 30, 35]
```

**Solution:**

```python
numbers = [5, 10, 15, 20, 25, 30, 35]

result = [
    "Yes" if number > 10 and number < 30 else "No"
    for number in numbers
]

print(result)
```

**Output:**

```text
['No', 'No', 'Yes', 'Yes', 'Yes', 'No', 'No']
```

### Exercise 8

নিচের List থেকে positive অথবা zero number নির্বাচন করো।

```python
numbers = [-10, -5, 0, 5, 10]
```

**Solution:**

```python
numbers = [-10, -5, 0, 5, 10]

result = [
    number for number in numbers
    if number > 0 or number == 0
]

print(result)
```

**Output:**

```text
[0, 5, 10]
```

### Exercise 9

নিচের code-এর output কী হবে?

```python
numbers = [5, 10, 15, 20, 25, 30]

result = [
    number for number in numbers
    if number > 10 and number % 2 == 0
]

print(result)
```

**Solution:**

```text
[20, 30]
```

### Exercise 10

নিচের code-এর output কী হবে?

```python
numbers = [10, 20, 30, 40]

result = [
    number for number in numbers
    if number == 10 or number == 40
]

print(result)
```

**Solution:**

```text
[10, 40]
```

---

## 12. Chapter Summary

এই topic-এ আমরা List Comprehension-এর মধ্যে Multiple Conditions ব্যবহার করা শিখেছি।

- `and` ব্যবহার করে সব condition পূরণ হওয়া element নির্বাচন করা যায়।
- `or` ব্যবহার করে যেকোনো একটি condition পূরণ হওয়া element নির্বাচন করা যায়।
- একাধিক `if` দিয়ে sequential filtering করা যায়।
- `if-else` ব্যবহার করে condition অনুযায়ী নতুন value তৈরি করা যায়।
- Parentheses ব্যবহার করে complex conditions পরিষ্কারভাবে লেখা যায়।
- Number এবং String উভয়ের ক্ষেত্রেই multiple conditions ব্যবহার করা যায়।

---

## 13. Self-Assessment Checklist

নিজে যাচাই করো:

- [ ] List Comprehension-এ multiple conditions ব্যবহার করতে পারি।
- [ ] `and` operator-এর কাজ বুঝতে পেরেছি।
- [ ] `or` operator-এর কাজ বুঝতে পেরেছি।
- [ ] একাধিক `if` condition ব্যবহার করতে পারি।
- [ ] `if-else` দিয়ে নতুন value তৈরি করতে পারি।
- [ ] `and` এবং `or` একসাথে ব্যবহার করতে পারি।
- [ ] String-এর উপর multiple conditions ব্যবহার করতে পারি।
- [ ] Positive এবং Even Number নির্বাচন করতে পারি।
- [ ] Complex conditions-এ parentheses ব্যবহার করতে পারি।
- [ ] Multiple `if` এবং `if-else`-এর পার্থক্য বুঝতে পেরেছি।

---

## 14. Next Topic

**27. Nested List Comprehension**

পরবর্তী topic-এ আমরা Nested List Comprehension শিখব। এর মাধ্যমে nested loop ব্যবহার করে সংক্ষিপ্তভাবে Nested List তৈরি এবং process করা যায়।