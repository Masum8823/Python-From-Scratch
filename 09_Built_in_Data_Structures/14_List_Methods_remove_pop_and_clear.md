# 14. List Methods remove(), pop() and clear() in Python

## 1. Introduction

Python List থেকে elements মুছে ফেলার জন্য কয়েকটি গুরুত্বপূর্ণ Built-in Method রয়েছে।

এর মধ্যে সবচেয়ে বেশি ব্যবহৃত তিনটি method হলো:

1. `remove()`
2. `pop()`
3. `clear()`

এই তিনটি method-এর কাজ আলাদা।

| Method | কাজ |
|---|---|
| `remove()` | নির্দিষ্ট value মুছে ফেলে। |
| `pop()` | নির্দিষ্ট index-এর element মুছে ফেলে। |
| `clear()` | List-এর সব elements মুছে ফেলে। |

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

numbers.remove(20)
numbers.pop()
numbers.clear()

print(numbers)
```

Output:

```text
[]
```

এখানে তিনটি method ব্যবহার করে ধাপে ধাপে List পরিবর্তন করা হয়েছে।

## 2. Understanding the remove() Method

`remove()` method ব্যবহার করে List থেকে নির্দিষ্ট value-এর প্রথম occurrence মুছে ফেলা যায়।

Syntax:

```python
list_name.remove(value)
```

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

fruits.remove("Banana")

print(fruits)
```

Output:

```text
['Apple', 'Mango', 'Orange']
```

এখানে `"Banana"` value-টি List থেকে মুছে গেছে।

**Important Points:**

- `remove()` value দিয়ে কাজ করে।
- এটি শুধু প্রথম matching value মুছে ফেলে।
- List-এ value না থাকলে `ValueError` দেয়।
- এটি Original List পরিবর্তন করে।
- এটি `None` return করে।

## 3. Removing the First Occurrence of a Value

একটি List-এ একই value একাধিকবার থাকলে `remove()` শুধু প্রথম occurrence মুছে দেয়।

উদাহরণ:

```python
numbers = [10, 20, 30, 20, 40, 20]

numbers.remove(20)

print(numbers)
```

Output:

```text
[10, 30, 20, 40, 20]
```

এখানে `20` তিনবার ছিল। কিন্তু `remove()` শুধু প্রথম `20` মুছে দিয়েছে।

## 4. Removing All Occurrences of a Value

যদি কোনো নির্দিষ্ট value-এর সব occurrences মুছতে চাও, তাহলে `while` loop ব্যবহার করা যায়।

উদাহরণ:

```python
numbers = [10, 20, 30, 20, 40, 20]

while 20 in numbers:
    numbers.remove(20)

print(numbers)
```

Output:

```text
[10, 30, 40]
```

এখানে:

- `20 in numbers` দিয়ে পরীক্ষা করা হচ্ছে List-এ `20` আছে কি না।
- `while` loop যতক্ষণ `20` পাবে, ততক্ষণ সেটি remove করবে।
- সব `20` মুছে গেলে Loop বন্ধ হবে।

## 5. Using remove() with Different Data Types

`remove()` শুধু Integer-এর জন্য নয়। String, Float এবং অন্যান্য Data Type-এর value-ও remove করা যায়।

উদাহরণ:

```python
data = [10, "Python", 3.5, True, "Java"]

data.remove("Python")

print(data)
```

Output:

```text
[10, 3.5, True, 'Java']
```

এখানে `"Python"` String-টি মুছে ফেলা হয়েছে।

## 6. Understanding the pop() Method

`pop()` method ব্যবহার করে List থেকে নির্দিষ্ট index-এর element মুছে ফেলা যায়।

এটি মুছে ফেলা element-টি return করে।

Syntax:

```python
list_name.pop(index)
```

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

numbers.pop(2)

print(numbers)
```

Output:

```text
[10, 20, 40, 50]
```

এখানে index `2`-এর element `30` মুছে গেছে।

**Important Points:**

- `pop()` index দিয়ে কাজ করে।
- Index না দিলে শেষ element মুছে যায়।
- এটি মুছে ফেলা element-টি return করে।
- Original List পরিবর্তন করে।
- Invalid index দিলে `IndexError` হয়।
- Empty List থেকে `pop()` করলে `IndexError` হয়।

## 7. Using pop() Without an Index

`pop()`-এর মধ্যে কোনো index না দিলে এটি List-এর শেষ element মুছে ফেলে।

উদাহরণ:

```python
numbers = [10, 20, 30, 40]

removed = numbers.pop()

print("Removed:", removed)
print("Updated List:", numbers)
```

Output:

```text
Removed: 40
Updated List: [10, 20, 30]
```

এখানে:

- `pop()` শেষ element `40` মুছে দিয়েছে।
- Removed element-টি `removed` Variable-এ রাখা হয়েছে।
- Original List থেকে `40` চলে গেছে।

## 8. Using pop() with Positive and Negative Index

`pop()` method-এর সঙ্গে Positive এবং Negative দুই ধরনের Index ব্যবহার করা যায়।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

numbers.pop(1)

print(numbers)

numbers.pop(-1)

print(numbers)
```

Output:

```text
[10, 30, 40, 50]
[10, 30, 40]
```

এখানে:

- `pop(1)` index `1`-এর element `20` মুছে দিয়েছে।
- `pop(-1)` শেষ element `50` মুছে দিয়েছে।

## 9. Understanding the clear() Method

`clear()` method ব্যবহার করে List-এর সব elements একসঙ্গে মুছে ফেলা যায়।

Syntax:

```python
list_name.clear()
```

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

fruits.clear()

print(fruits)
```

Output:

```text
[]
```

এখানে List-এর সব elements মুছে গেছে।

**Important Points:**

- `clear()` কোনো argument গ্রহণ করে না।
- এটি List-এর সব elements মুছে দেয়।
- List-টি Empty হয়ে যায়।
- Original List object থেকে যায়।
- এটি `None` return করে।

## 10. Difference Between clear() and Creating an Empty List

`clear()` ব্যবহার করলে Original List-এর সব elements মুছে যায়।

কিন্তু Variable-কে নতুন Empty List assign করলে Variable নতুন List-কে reference করে।

উদাহরণ:

```python
numbers = [10, 20, 30]

numbers.clear()

print(numbers)
```

Output:

```text
[]
```

এবার নতুন Empty List assign করার উদাহরণ:

```python
numbers = [10, 20, 30]

numbers = []

print(numbers)
```

Output:

```text
[]
```

দুটি Output একই হলেও কাজের মধ্যে পার্থক্য রয়েছে।

- `clear()` আগের List object-টিকেই Empty করে।
- `numbers = []` Variable-কে নতুন একটি Empty List-এর সঙ্গে যুক্ত করে।

## 11. Understanding Return Values

`remove()`, `pop()` এবং `clear()`-এর Return Value এক নয়।

| Method | Return Value |
|---|---|
| `remove()` | `None` |
| `pop()` | Removed element |
| `clear()` | `None` |

উদাহরণ:

```python
numbers1 = [10, 20, 30]
numbers2 = [10, 20, 30]
numbers3 = [10, 20, 30]

result1 = numbers1.remove(20)
result2 = numbers2.pop(1)
result3 = numbers3.clear()

print(result1)
print(result2)
print(result3)
```

Output:

```text
None
20
None
```

এখানে:

- `remove(20)` শুধু value মুছে দিয়েছে এবং `None` return করেছে।
- `pop(1)` `20` মুছে সেটি return করেছে।
- `clear()` সব elements মুছে `None` return করেছে।

## 12. Checking the List Before Removing Elements

কোনো value remove করার আগে সেটি List-এ আছে কি না পরীক্ষা করা ভালো।

উদাহরণ:

```python
numbers = [10, 20, 30, 40]

if 30 in numbers:
    numbers.remove(30)

print(numbers)
```

Output:

```text
[10, 20, 40]
```

এখানে `in` operator দিয়ে আগে পরীক্ষা করা হয়েছে `30` List-এ আছে কি না।

এভাবে value না থাকলে `remove()`-এর `ValueError` এড়ানো যায়।

## 13. Practical Example: Removing Completed Tasks

ধরো, তোমার একটি Task List আছে। কোনো Task শেষ হলে সেটি List থেকে remove করতে হবে।

উদাহরণ:

```python
tasks = ["Study Python", "Practice C", "Read Book"]

completed_task = "Practice C"

if completed_task in tasks:
    tasks.remove(completed_task)

print("Remaining Tasks:", tasks)
```

Output:

```text
Remaining Tasks: ['Study Python', 'Read Book']
```

এখানে Completed Task-টি List থেকে মুছে ফেলা হয়েছে।

## 14. Practical Example: Removing Items Using pop()

ধরো, একটি Shopping List থেকে শেষ Item-টি Remove করতে হবে এবং কোন Item Remove হয়েছে তা দেখতে হবে।

উদাহরণ:

```python
shopping_list = ["Rice", "Milk", "Eggs", "Bread"]

removed_item = shopping_list.pop()

print("Removed Item:", removed_item)
print("Shopping List:", shopping_list)
```

Output:

```text
Removed Item: Bread
Shopping List: ['Rice', 'Milk', 'Eggs']
```

এখানে `pop()` শেষ Item-টি Remove করে Return করেছে।

## 15. Common Mistakes

### Mistake 1: Using Index with remove()

ভুল:

```python
numbers = [10, 20, 30]

numbers.remove(1)
```

এখানে `remove()` index `1` খুঁজবে না। এটি value `1` খুঁজবে।

যেহেতু `1` List-এ নেই, তাই `ValueError` হবে।

Correct:

```python
numbers = [10, 20, 30]

numbers.remove(20)

print(numbers)
```

Output:

```text
[10, 30]
```

### Mistake 2: Using Value with pop()

ভুল:

```python
numbers = [10, 20, 30]

numbers.pop(30)
```

এখানে `pop()` index `30` খুঁজবে। কিন্তু List-এ এত বড় index নেই।

তাই `IndexError` হবে।

Correct:

```python
numbers = [10, 20, 30]

numbers.pop(2)

print(numbers)
```

Output:

```text
[10, 20]
```

### Mistake 3: Assigning remove() to a Variable

ভুল:

```python
numbers = [10, 20, 30]

result = numbers.remove(20)

print(result)
```

Output:

```text
None
```

কারণ `remove()` Removed Value return করে না।

Correct:

```python
numbers = [10, 20, 30]

numbers.remove(20)

print(numbers)
```

Output:

```text
[10, 30]
```

### Mistake 4: Calling clear() with an Argument

ভুল:

```python
numbers = [10, 20, 30]

numbers.clear(20)
```

Output:

```text
TypeError: list.clear() takes no arguments
```

কারণ `clear()` কোনো argument গ্রহণ করে না।

Correct:

```python
numbers = [10, 20, 30]

numbers.clear()

print(numbers)
```

Output:

```text
[]
```

## 16. Important Rules

- `remove(value)` নির্দিষ্ট value-এর প্রথম occurrence মুছে ফেলে।
- `remove()` কোনো value না পেলে `ValueError` দেয়।
- `pop(index)` নির্দিষ্ট index-এর element মুছে ফেলে।
- `pop()`-এ index না দিলে শেষ element মুছে যায়।
- `pop()` Removed Element return করে।
- `pop()`-এ Invalid Index দিলে `IndexError` হয়।
- Empty List থেকে `pop()` করা যায় না।
- `clear()` List-এর সব elements মুছে দেয়।
- `clear()` কোনো argument গ্রহণ করে না।
- `remove()` এবং `clear()` `None` return করে।
- তিনটি method-ই Original List পরিবর্তন করে।
- `remove()` value দিয়ে কাজ করে, কিন্তু `pop()` index দিয়ে কাজ করে।

## 17. Practice Exercises

### Exercise 1: Remove a Specific Value

নিচের List থেকে `"Banana"` মুছে ফেলো।

Solution:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

fruits.remove("Banana")

print(fruits)
```

Output:

```text
['Apple', 'Mango', 'Orange']
```

### Exercise 2: Remove All Occurrences

নিচের List থেকে সব `10` মুছে ফেলো।

Solution:

```python
numbers = [10, 20, 10, 30, 10, 40]

while 10 in numbers:
    numbers.remove(10)

print(numbers)
```

Output:

```text
[20, 30, 40]
```

### Exercise 3: Remove and Store an Element

`pop()` ব্যবহার করে index `2`-এর element মুছে Variable-এ রাখো।

Solution:

```python
numbers = [10, 20, 30, 40, 50]

removed = numbers.pop(2)

print("Removed:", removed)
print("Updated List:", numbers)
```

Output:

```text
Removed: 30
Updated List: [10, 20, 40, 50]
```

### Exercise 4: Empty a List

`clear()` ব্যবহার করে List-এর সব elements মুছে ফেলো।

Solution:

```python
colors = ["Red", "Green", "Blue"]

colors.clear()

print(colors)
```

Output:

```text
[]
```

### Exercise 5: Predict the Output

নিচের Code-এর Output কী হবে?

```python
numbers = [10, 20, 30, 40, 50]

numbers.remove(30)

removed = numbers.pop()

print(numbers)
print(removed)
```

Solution:

```text
[10, 20, 40]
50
```

## 18. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `remove()` method-এর বিস্তারিত ব্যবহার।
- Duplicate values থেকে প্রথম occurrence remove করা।
- Loop ব্যবহার করে সব occurrences remove করা।
- `pop()` method-এর বিস্তারিত ব্যবহার।
- Positive এবং Negative Index দিয়ে elements remove করা।
- Removed element Variable-এ সংরক্ষণ করা।
- `clear()` দিয়ে List Empty করা।
- তিনটি method-এর Return Value।
- Practical Examples এবং Common Mistakes।

## 19. Self-Assessment Checklist

- [ ] `remove()` method-এর কাজ বুঝি।
- [ ] Duplicate values থেকে প্রথম occurrence remove করতে পারি।
- [ ] `while` loop দিয়ে সব occurrences remove করতে পারি।
- [ ] `pop()` method-এর কাজ বুঝি।
- [ ] `pop()` দিয়ে removed element সংরক্ষণ করতে পারি।
- [ ] Negative Index দিয়ে `pop()` ব্যবহার করতে পারি।
- [ ] `clear()` দিয়ে List Empty করতে পারি।
- [ ] তিনটি method-এর Return Value জানি।
- [ ] `remove()` এবং `pop()`-এর পার্থক্য বুঝি।
- [ ] Common Errors identify করতে পারি।

## 20. Next Topic

**15. Searching Lists with in and not in**

পরবর্তী topic-এ আমরা শিখব কীভাবে Python List-এর মধ্যে কোনো নির্দিষ্ট element আছে কি না খুঁজে বের করতে হয়। এজন্য `in` এবং `not in` Membership Operators ব্যবহার করব।