

# 27. Nested List Comprehension in Python

## 1. Introduction

**Nested List Comprehension** হলো Python-এ একটি List Comprehension-এর ভিতরে একাধিক `for` loop ব্যবহার করে List তৈরি বা process করার পদ্ধতি।

এটি সাধারণত Nested List, Matrix, এবং Multiple Loops-এর কাজ সহজে করার জন্য ব্যবহার করা হয়।

## 2. Basic Syntax

```python
[expression for outer_item in outer_iterable for inner_item in inner_iterable]
```

এখানে:

- `expression` → প্রতিটি iteration-এ যে value তৈরি হবে।
- `outer_item` → বাইরের `for` loop-এর variable।
- `inner_item` → ভিতরের `for` loop-এর variable।
- `outer_iterable` → বাইরের iterable।
- `inner_iterable` → ভিতরের iterable।

**মনে রাখবে:** প্রথমে বাইরের loop এবং পরে ভিতরের loop লিখতে হয়।

## 3. Nested Loop vs Nested List Comprehension

সাধারণ Nested Loop:

```python
numbers = []

for row in [[1, 2], [3, 4]]:
    for number in row:
        numbers.append(number)

print(numbers)
```

**Output:**
```text
[1, 2, 3, 4]
```

একই কাজ Nested List Comprehension দিয়ে:

```python
numbers = [number for row in [[1, 2], [3, 4]] for number in row]

print(numbers)
```

**Output:**
```text
[1, 2, 3, 4]
```

## 4. Flattening a Nested List

একটি Nested List-কে Single List-এ রূপান্তর করাকে **Flattening** বলে।

```python
matrix = [[1, 2], [3, 4], [5, 6]]

flat = [number for row in matrix for number in row]

print(flat)
```

**Output:**
```text
[1, 2, 3, 4, 5, 6]
```

এখানে:

1. প্রথমে `row` একটি করে inner list নেয়।
2. এরপর `number` সেই list-এর প্রতিটি element নেয়।
3. সব element একটি নতুন List-এ যুক্ত হয়।

## 5. Creating a 2D List Using Nested Comprehension

Nested List Comprehension দিয়ে সহজেই 2D List বা Matrix তৈরি করা যায়।

**Example 1: Creating a 2D List**

```python
matrix = [[0 for col in range(3)] for row in range(2)]

print(matrix)
```

**Output:**
```text
[[0, 0, 0], [0, 0, 0]]
```

এখানে:

- `range(2)` → 2টি Row তৈরি করে।
- `range(3)` → প্রতিটি Row-তে 3টি Element তৈরি করে।

**Example 2: Creating a Matrix with Numbers**

```python
matrix = [[col for col in range(3)] for row in range(2)]

print(matrix)
```

**Output:**
```text
[[0, 1, 2], [0, 1, 2]]
```

## 6. Creating a Multiplication Table

Nested List Comprehension ব্যবহার করে Multiplication Table তৈরি করা যায়।

```python
table = [[row * col for col in range(1, 4)] for row in range(1, 4)]

print(table)
```

**Output:**
```text
[[1, 2, 3], [2, 4, 6], [3, 6, 9]]
```

এখানে বাইরের loop Row নির্ধারণ করে এবং ভিতরের loop প্রতিটি Row-এর multiplication values তৈরি করে।

## 7. Creating Coordinate Pairs

Nested List Comprehension দিয়ে একাধিক Combination বা Coordinate Pair তৈরি করা যায়।

```python
pairs = [(x, y) for x in range(2) for y in range(3)]

print(pairs)
```

**Output:**
```text
[(0, 0), (0, 1), (0, 2), (1, 0), (1, 1), (1, 2)]
```

## 8. Nested List Comprehension with Conditions

Nested List Comprehension-এর সঙ্গে `if` ব্যবহার করে নির্দিষ্ট elements নির্বাচন করা যায়।

**Example 1: Filtering Even Numbers**

```python
matrix = [[1, 2, 3], [4, 5, 6]]

even_numbers = [number for row in matrix for number in row if number % 2 == 0]

print(even_numbers)
```

**Output:**
```text
[2, 4, 6]
```

**Example 2: Filtering Rows**

```python
matrix = [[1, 2], [3, 4], [5, 6]]

result = [row for row in matrix if sum(row) > 5]

print(result)
```

**Output:**
```text
[[3, 4], [5, 6]]
```

এখানে যেসব Row-এর sum `5`-এর বেশি, শুধু সেগুলো নেওয়া হয়েছে।

## 9. Difference Between Flattening and Creating a Nested List

Nested List Comprehension দিয়ে দুই ধরনের কাজ করা যায়।

| Flattening | Creating Nested List |
|---|---|
| Nested List-কে Single List করে | নতুন Nested List তৈরি করে |
| একটি `for` expression sequence ব্যবহার করে | Expression-এর ভিতরে List তৈরি করে |
| সব elements একসঙ্গে থাকে | Elements আলাদা Row-তে থাকে |

**Flattening Example:**

```python
matrix = [[1, 2], [3, 4]]

result = [number for row in matrix for number in row]

print(result)
```

**Output:**
```text
[1, 2, 3, 4]
```

**Nested List Example:**

```python
result = [[number for number in range(3)] for row in range(2)]

print(result)
```

**Output:**
```text
[[0, 1, 2], [0, 1, 2]]
```

## 10. Important Rules

1. Nested List Comprehension-এ একাধিক `for` loop ব্যবহার করা যায়।
2. প্রথমে Outer Loop এবং পরে Inner Loop লিখতে হয়।
3. Loop-এর order সাধারণ Nested Loop-এর order-এর মতোই হয়।
4. `if` condition ব্যবহার করে elements filter করা যায়।
5. Nested List তৈরি করতে Expression-এর ভিতরে নতুন List তৈরি করা যায়।
6. Flattening করলে Nested List-এর elements একটি Single List-এ চলে আসে।

## 11. Common Mistakes

### Mistake 1: Reversing the Loop Order

ভুল:

```python
matrix = [[1, 2], [3, 4]]

result = [number for number in row for row in matrix]
```

এখানে `row` ব্যবহারের আগে সেটি তৈরি করা হয়নি।

সঠিক:

```python
matrix = [[1, 2], [3, 4]]

result = [number for row in matrix for number in row]

print(result)
```

**Output:**
```text
[1, 2, 3, 4]
```

### Mistake 2: Confusing Flattening with Nested List Creation

Flattening:

```python
result = [x for row in [[1, 2], [3, 4]] for x in row]

print(result)
```

**Output:**
```text
[1, 2, 3, 4]
```

Nested List:

```python
result = [[x for x in range(2)] for row in range(2)]

print(result)
```

**Output:**
```text
[[0, 1], [0, 1]]
```

### Mistake 3: Creating Rows with Shared References

নিচের পদ্ধতিটি এড়িয়ে চলবে:

```python
matrix = [[0] * 3] * 2

matrix[0][0] = 5

print(matrix)
```

**Output:**
```text
[[5, 0, 0], [5, 0, 0]]
```

এখানে দুইটি Row একই inner list-কে reference করে।

সঠিক পদ্ধতি:

```python
matrix = [[0 for col in range(3)] for row in range(2)]

matrix[0][0] = 5

print(matrix)
```

**Output:**
```text
[[5, 0, 0], [0, 0, 0]]
```

এবার প্রতিটি Row আলাদা List হিসেবে তৈরি হয়েছে।

## 12. Practice Exercises

### Exercise 1: Flatten a Nested List

নিচের Nested List-কে Single List-এ রূপান্তর করো।

```python
numbers = [[10, 20], [30, 40], [50, 60]]
```

**Solution:**

```python
result = [number for row in numbers for number in row]

print(result)
```

**Output:**
```text
[10, 20, 30, 40, 50, 60]
```

### Exercise 2: Create a 3×3 Matrix

Nested List Comprehension ব্যবহার করে 3টি Row এবং 3টি Column তৈরি করো।

**Solution:**

```python
matrix = [[0 for col in range(3)] for row in range(3)]

print(matrix)
```

**Output:**
```text
[[0, 0, 0], [0, 0, 0], [0, 0, 0]]
```

### Exercise 3: Find Odd Numbers

নিচের Nested List থেকে Odd Numbers বের করো।

```python
numbers = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

**Solution:**

```python
odd_numbers = [x for row in numbers for x in row if x % 2 != 0]

print(odd_numbers)
```

**Output:**
```text
[1, 3, 5, 7, 9]
```

### Exercise 4: Create Coordinate Pairs

`x` এবং `y`-এর জন্য `range(2)` ব্যবহার করে সব Coordinate Pair তৈরি করো।

**Solution:**

```python
pairs = [(x, y) for x in range(2) for y in range(2)]

print(pairs)
```

**Output:**
```text
[(0, 0), (0, 1), (1, 0), (1, 1)]
```

## 13. Chapter Summary

- Nested List Comprehension-এ একাধিক `for` loop ব্যবহার করা হয়।
- এটি Nested List Flatten করতে সাহায্য করে।
- 2D List বা Matrix তৈরি করা যায়।
- Multiple Combinations এবং Coordinate Pairs তৈরি করা যায়।
- `if` condition ব্যবহার করে elements filter করা যায়।
- Loop-এর order সাধারণ Nested Loop-এর মতোই রাখতে হয়।
- Independent Rows তৈরি করতে Nested List Comprehension ব্যবহার করা ভালো।

## 14. Self-Assessment Checklist

- [ ] Nested List Comprehension কী বুঝতে পেরেছি।
- [ ] এর Basic Syntax বুঝতে পেরেছি।
- [ ] Nested List Flatten করতে পারি।
- [ ] 2D Matrix তৈরি করতে পারি।
- [ ] Multiplication Table তৈরি করতে পারি।
- [ ] Coordinate Pairs তৈরি করতে পারি।
- [ ] Conditions ব্যবহার করে elements filter করতে পারি।
- [ ] Common Mistakes বুঝতে পেরেছি।

## 15. Next Topic

**28. List Comprehension with Nested Conditions**

