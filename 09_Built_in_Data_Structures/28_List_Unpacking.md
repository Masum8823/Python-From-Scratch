

# 28. List Comprehension with Nested Conditions

## 1. Introduction

Python List Comprehension-এর মধ্যে একাধিক `if` condition ব্যবহার করে নির্দিষ্ট elements নির্বাচন করা যায়।

যখন একটি List-এর elements-এর ওপর একাধিক শর্ত প্রয়োগ করতে হয়, তখন **List Comprehension with Nested Conditions** ব্যবহার করা হয়।

এতে `and`, `or`, একাধিক `if` এবং `if-else` ব্যবহার করা যায়।

## 2. Basic Syntax

```python
[expression for item in iterable if condition1 if condition2]
```

এখানে:

- `expression` → যে value নতুন List-এ যুক্ত হবে।
- `item` → প্রতিটি element।
- `condition1` → প্রথম শর্ত।
- `condition2` → দ্বিতীয় শর্ত।

একাধিক `if` ব্যবহার করলে সব condition পূরণ করতে হয়।

## 3. Using Multiple if Conditions

একাধিক `if` ব্যবহার করে একটি element-এর ওপর একাধিক শর্ত প্রয়োগ করা যায়।

**Example:**

```python
numbers = [10, 15, 20, 25, 30, 35, 40]

result = [x for x in numbers if x > 15 if x % 2 == 0]

print(result)
```

**Output:**

```text
[20, 30, 40]
```

এখানে:

- প্রথম condition: Number অবশ্যই `15`-এর বেশি হতে হবে।
- দ্বিতীয় condition: Number অবশ্যই Even হতে হবে।

দুইটি condition পূরণ করলেই element নতুন List-এ যুক্ত হবে।

## 4. Using and Operator

একাধিক condition একসঙ্গে পরীক্ষা করতে `and` ব্যবহার করা যায়।

**Example:**

```python
numbers = [5, 10, 15, 20, 25, 30]

result = [x for x in numbers if x > 10 and x < 30]

print(result)
```

**Output:**

```text
[15, 20, 25]
```

এখানে দুইটি condition-ই True হতে হবে।

## 5. Using or Operator

যখন একাধিক condition-এর মধ্যে যেকোনো একটি True হলেই element নির্বাচন করতে হবে, তখন `or` ব্যবহার করা হয়।

**Example:**

```python
numbers = [5, 10, 15, 20, 25, 30]

result = [x for x in numbers if x == 10 or x == 30]

print(result)
```

**Output:**

```text
[10, 30]
```

এখানে Number `10` অথবা `30` হলেই সেটি নতুন List-এ যুক্ত হবে।

## 6. Combining and and or Operators

একই List Comprehension-এ `and` এবং `or` একসঙ্গে ব্যবহার করা যায়।

**Example:**

```python
numbers = [5, 10, 15, 20, 25, 30, 35]

result = [x for x in numbers if (x > 10 and x < 25) or x == 35]

print(result)
```

**Output:**

```text
[15, 20, 35]
```

এখানে:

- Number `10`-এর বেশি এবং `25`-এর কম হলে নেওয়া হবে।
- অথবা Number `35` হলেও নেওয়া হবে।

**Important:** Condition পরিষ্কার রাখতে parentheses `()` ব্যবহার করা ভালো।

## 7. Nested Conditions with Strings

String-এর elements-এর ওপর একাধিক condition ব্যবহার করা যায়।

**Example:**

```python
names = ["Masum", "Rahim", "Karim", "Rafi", "Abdullah"]

result = [name for name in names if len(name) > 4 if name.startswith("M") or name.startswith("A")]

print(result)
```

**Output:**

```text
['Masum', 'Abdullah']
```

এখানে:

- Name-এর length অবশ্যই `4`-এর বেশি হতে হবে।
- Name অবশ্যই `M` অথবা `A` দিয়ে শুরু হতে হবে।

## 8. Nested Conditions in Nested List Comprehension

Nested List Comprehension-এর সঙ্গে একাধিক condition ব্যবহার করা যায়।

**Example:**

```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

result = [x for row in matrix for x in row if x > 3 if x % 2 == 0]

print(result)
```

**Output:**

```text
[4, 6, 8]
```

এখানে:

- প্রথমে Nested List থেকে প্রতিটি element নেওয়া হয়েছে।
- এরপর Number `3`-এর বেশি হতে হবে।
- Number Even হতে হবে।

## 9. Using if-else with Multiple Conditions

List Comprehension-এ `if-else` ব্যবহার করে condition অনুযায়ী আলাদা value তৈরি করা যায়।

**Example:**

```python
numbers = [10, 15, 20, 25, 30]

result = ["Even" if x % 2 == 0 else "Odd" for x in numbers]

print(result)
```

**Output:**

```text
['Even', 'Odd', 'Even', 'Odd', 'Even']
```

একাধিক condition-এর সঙ্গে `if-else` ব্যবহার করা যায়।

**Example:**

```python
numbers = [5, 10, 15, 20, 25, 30]

result = ["Small" if x < 10 else "Medium" if x < 20 else "Large" for x in numbers]

print(result)
```

**Output:**

```text
['Small', 'Medium', 'Medium', 'Large', 'Large', 'Large']
```

এখানে:

- `10`-এর কম হলে `"Small"`।
- অন্যথায় `20`-এর কম হলে `"Medium"`।
- বাকি ক্ষেত্রে `"Large"`।

## 10. Difference Between Multiple if and if-else

| Multiple if | if-else |
|---|---|
| একাধিক condition পরীক্ষা করে | Condition অনুযায়ী value নির্বাচন করে |
| সব condition True হতে হয় | True বা False অনুযায়ী আলাদা value দেয় |
| Element filter করতে ব্যবহৃত হয় | Element-এর value পরিবর্তন করতে ব্যবহৃত হয় |

**Multiple if Example:**

```python
numbers = [5, 10, 15, 20]

result = [x for x in numbers if x > 5 if x < 20]

print(result)
```

**Output:**

```text
[10, 15]
```

**if-else Example:**

```python
numbers = [5, 10, 15, 20]

result = ["Pass" if x >= 10 else "Fail" for x in numbers]

print(result)
```

**Output:**

```text
['Fail', 'Pass', 'Pass', 'Pass']
```

## 11. Common Mistakes

### Mistake 1: Using Multiple if Incorrectly

ভুল:

```python
numbers = [10, 20, 30]

result = [x for x in numbers if x > 10 else 0]
```

এখানে `if-else`-এর অবস্থান ভুল।

সঠিক:

```python
numbers = [10, 20, 30]

result = [x if x > 10 else 0 for x in numbers]

print(result)
```

**Output:**

```text
[0, 20, 30]
```

### Mistake 2: Forgetting and / or Logic

```python
numbers = [10, 15, 20, 25, 30]

result = [x for x in numbers if x > 10 and x < 30]

print(result)
```

**Output:**

```text
[15, 20, 25]
```

এখানে `and` ব্যবহার করায় দুইটি condition-ই True হতে হবে।

### Mistake 3: Confusing Filtering with Conditional Expression

Filtering:

```python
numbers = [5, 10, 15, 20]

result = [x for x in numbers if x > 10]

print(result)
```

**Output:**

```text
[15, 20]
```

Conditional Expression:

```python
numbers = [5, 10, 15, 20]

result = ["High" if x > 10 else "Low" for x in numbers]

print(result)
```

**Output:**

```text
['Low', 'Low', 'High', 'High']
```

## 12. Practice Exercises

### Exercise 1: Find Numbers Between 10 and 50

একটি List থেকে `10`-এর বেশি এবং `50`-এর কম Number বের করো।

**Solution:**

```python
numbers = [5, 15, 25, 35, 45, 55]

result = [x for x in numbers if x > 10 and x < 50]

print(result)
```

**Output:**

```text
[15, 25, 35, 45]
```

### Exercise 2: Find Even Numbers Greater Than 10

**Solution:**

```python
numbers = [5, 10, 15, 20, 25, 30, 35, 40]

result = [x for x in numbers if x > 10 if x % 2 == 0]

print(result)
```

**Output:**

```text
[20, 30, 40]
```

### Exercise 3: Select Names Starting with A or M

**Solution:**

```python
names = ["Masum", "Rahim", "Abdullah", "Karim", "Amin"]

result = [name for name in names if name.startswith("A") or name.startswith("M")]

print(result)
```

**Output:**

```text
['Masum', 'Abdullah', 'Amin']
```

### Exercise 4: Replace Numbers with Even and Odd

**Solution:**

```python
numbers = [1, 2, 3, 4, 5, 6]

result = ["Even" if x % 2 == 0 else "Odd" for x in numbers]

print(result)
```

**Output:**

```text
['Odd', 'Even', 'Odd', 'Even', 'Odd', 'Even']
```

## 13. Important Rules

1. একাধিক `if` ব্যবহার করে elements filter করা যায়।
2. Multiple `if` ব্যবহার করলে সব condition True হতে হবে।
3. `and` ব্যবহার করলে সব condition True হতে হবে।
4. `or` ব্যবহার করলে যেকোনো একটি condition True হলেই হবে।
5. `if-else` ব্যবহার করে condition অনুযায়ী value নির্বাচন করা যায়।
6. `if-else` expression সাধারণত `for` loop-এর আগে লিখতে হয়।
7. একাধিক condition থাকলে parentheses ব্যবহার করলে code বোঝা সহজ হয়।

## 14. Chapter Summary

- Nested Conditions দিয়ে একাধিক শর্ত পরীক্ষা করা যায়।
- Multiple `if` দিয়ে elements filter করা যায়।
- `and` এবং `or` দিয়ে একাধিক condition combine করা যায়।
- `if-else` দিয়ে condition অনুযায়ী আলাদা value তৈরি করা যায়।
- Nested List Comprehension-এর সঙ্গেও multiple conditions ব্যবহার করা যায়।

## 15. Self-Assessment Checklist

- [ ] Multiple `if` ব্যবহার করতে পারি।
- [ ] `and` এবং `or` ব্যবহার করতে পারি।
- [ ] একাধিক condition combine করতে পারি।
- [ ] String-এর ওপর nested conditions ব্যবহার করতে পারি।
- [ ] Nested List Comprehension-এ conditions ব্যবহার করতে পারি।
- [ ] `if-else` এবং filtering-এর পার্থক্য বুঝতে পারি।
- [ ] Common Mistakes বুঝতে পেরেছি।

## 16. Next Topic

**29. List Comprehension with Functions**

