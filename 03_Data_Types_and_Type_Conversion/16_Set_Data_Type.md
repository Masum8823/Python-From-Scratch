# 16. Set Data Type in Python

## 1. What Is a Set?

Python-এ **Set হলো একটি built-in collection data type, যেখানে unique items সংরক্ষণ করা হয়।**

Set-এর প্রধান বৈশিষ্ট্য হলো, এতে duplicate value রাখা যায় না। একই value একাধিকবার দেওয়া হলেও Set-এ তা একবারই থাকবে।

Set তৈরি করতে সাধারণত curly braces `{}` ব্যবহার করা হয়।

```python
numbers = {10, 20, 30, 40}

print(numbers)
print(type(numbers))
```

Output:

```text
{10, 20, 30, 40}
<class 'set'>
```

এখানে `numbers` একটি Set।

### Example: Duplicate Values

```python
numbers = {10, 20, 10, 30, 20, 40}

print(numbers)
```

Output:

```text
{10, 20, 30, 40}
```

Set duplicate value বাদ দিয়ে প্রতিটি unique value রাখে। Set-এর item-এর displayed order নির্দিষ্ট নাও হতে পারে।

**মনে রাখবে:** Set ব্যবহার করা হয় যখন unique values রাখা বা একাধিক collection-এর মধ্যে common ও different items খুঁজে বের করা প্রয়োজন হয়।

## 2. Characteristics of Sets

Python Set-এর গুরুত্বপূর্ণ বৈশিষ্ট্যগুলো হলো:

| Feature | Explanation |
|---|---|
| Unique items | Duplicate value রাখা হয় না |
| Unordered | নির্দিষ্ট positional order ধরে রাখা হয় না |
| Mutable | Set-এ item যোগ ও বাদ দেওয়া যায় |
| No indexing | Index দিয়ে item access করা যায় না |
| No slicing | Index-based slicing করা যায় না |
| Iterable | Loop দিয়ে item-গুলো access করা যায় |
| Hashable elements | Set-এর item-গুলো hashable হতে হয় |

Example:

```python
data = {10, 20, 30}

data.add(40)

print(data)
```

Output:

```text
{10, 20, 30, 40}
```

এখানে নতুন item যোগ করা হয়েছে। তবে Set-এর item-এর position ধরে access করা যায় না।

## 3. Creating a Set

### 3.1 Set with Multiple Items

```python
fruits = {"Apple", "Banana", "Mango"}

print(fruits)
```

Output-এ item-এর order ভিন্ন হতে পারে।

```text
{'Apple', 'Banana', 'Mango'}
```

### 3.2 Empty Set

Empty Set তৈরি করার জন্য `set()` ব্যবহার করতে হয়।

```python
empty = set()

print(empty)
print(type(empty))
```

Output:

```text
set()
<class 'set'>
```

**গুরুত্বপূর্ণ:** `{}` লিখলে Empty Set তৈরি হয় না। এটি একটি Empty Dictionary তৈরি করে।

```python
a = {}
b = set()

print(type(a))
print(type(b))
```

Output:

```text
<class 'dict'>
<class 'set'>
```

### 3.3 Set with Duplicate Values

```python
numbers = {1, 2, 3, 2, 1, 4}

print(numbers)
```

Output-এ প্রতিটি unique value একবার থাকবে।

```text
{1, 2, 3, 4}
```

### 3.4 Creating a Set with `set()`

`set()` constructor ব্যবহার করে অন্য iterable থেকে Set তৈরি করা যায়।

List থেকে:

```python
numbers = set([10, 20, 10, 30, 20])

print(numbers)
```

Output:

```text
{10, 20, 30}
```

Tuple থেকে:

```python
numbers = set((10, 20, 30, 20))

print(numbers)
```

Output:

```text
{10, 20, 30}
```

String থেকে:

```python
letters = set("banana")

print(letters)
```

Output-এর order ভিন্ন হতে পারে:

```text
{'b', 'a', 'n'}
```

String-এর প্রতিটি unique character Set-এ একবার করে থাকে।

## 4. Why Are Sets Unordered?

Set কোনো নির্দিষ্ট index-based sequence নয়। তাই List-এর মতো item-এর স্থায়ী position ধরে কাজ করা যায় না।

```python
numbers = {10, 20, 30, 40}

print(numbers)
```

Python কোনো নির্দিষ্ট order-এ item দেখাতে পারে, কিন্তু সেই order-এর ওপর নির্ভর করা উচিত নয়।

Set-এ নিচের কাজগুলো করা যায় না:

```python
numbers = {10, 20, 30}

print(numbers[0])
```

এটি `TypeError` তৈরি করবে, কারণ Set indexing support করে না।

একইভাবে Set slicing-ও support করে না।

**মনে রাখবে:** Set-এ item খোঁজার জন্য indexing-এর পরিবর্তে membership operator `in` ব্যবহার করা হয়।

## 5. Adding Items to a Set

Set mutable হওয়ায় এতে নতুন item যোগ করা যায়।

### 5.1 `add()`

`add()` একটি item যোগ করে।

```python
fruits = {"Apple", "Banana"}

fruits.add("Mango")

print(fruits)
```

Output-এ তিনটি unique item থাকবে:

```text
{'Apple', 'Banana', 'Mango'}
```

আগে থেকেই থাকা item যোগ করলে duplicate তৈরি হয় না।

```python
numbers = {10, 20, 30}

numbers.add(20)

print(numbers)
```

Output:

```text
{10, 20, 30}
```

### 5.2 `update()`

`update()` একটি বা একাধিক iterable-এর item Set-এ যোগ করে।

```python
numbers = {10, 20}

numbers.update([30, 40, 50])

print(numbers)
```

Output:

```text
{10, 20, 30, 40, 50}
```

Tuple থেকেও item যোগ করা যায়:

```python
numbers = {10, 20}

numbers.update((30, 40))

print(numbers)
```

Output:

```text
{10, 20, 30, 40}
```

একাধিক iterable ব্যবহার করা যায়:

```python
numbers = {1, 2}

numbers.update([3, 4], (5, 6))

print(numbers)
```

Output:

```text
{1, 2, 3, 4, 5, 6}
```

### `add()` vs `update()`

| `add()` | `update()` |
|---|---|
| একটি item যোগ করে | Iterable-এর item-গুলো যোগ করে |
| List-কে একটি item হিসেবে যোগ করতে চাইলে তা hashable না হলে সম্ভব নয় | List-এর individual item যোগ করে |
| `numbers.add(5)` | `numbers.update([5, 6])` |

Example:

```python
a = {1, 2}
a.add((3, 4))

b = {1, 2}
b.update((3, 4))

print(a)
print(b)
```

Output:

```text
{1, 2, (3, 4)}
{1, 2, 3, 4}
```

এখানে Tuple hashable হওয়ায় `add()` দিয়ে একটি item হিসেবে যোগ করা গেছে। `update()` Tuple-এর item-গুলো আলাদাভাবে যোগ করেছে।

## 6. Removing Items from a Set

Set থেকে item বাদ দেওয়ার জন্য কয়েকটি method রয়েছে।

### 6.1 `remove()`

`remove()` নির্দিষ্ট item বাদ দেয়।

```python
numbers = {10, 20, 30, 40}

numbers.remove(20)

print(numbers)
```

Output:

```text
{10, 30, 40}
```

Item Set-এ না থাকলে `KeyError` হয়।

```python
numbers = {10, 20, 30}

numbers.remove(50)
```

এই code `KeyError` তৈরি করবে।

### 6.2 `discard()`

`discard()`-ও নির্দিষ্ট item বাদ দেয়। তবে item না থাকলে error তৈরি করে না।

```python
numbers = {10, 20, 30}

numbers.discard(20)
numbers.discard(50)

print(numbers)
```

Output:

```text
{10, 30}
```

এখানে `50` Set-এ না থাকলেও কোনো error হয়নি।

**মনে রাখবে:**

- `remove()` — item না থাকলে `KeyError`।
- `discard()` — item না থাকলে কোনো error নয়।

### 6.3 `pop()`

`pop()` Set থেকে একটি arbitrary item বাদ দেয় এবং সেটি return করে।

```python
numbers = {10, 20, 30}

removed = numbers.pop()

print("Removed:", removed)
print(numbers)
```

কোন item বাদ যাবে, তা আগে থেকে ধরে নেওয়া যাবে না।

Empty Set থেকে `pop()` করলে `KeyError` হয়।

### 6.4 `clear()`

`clear()` Set-এর সব item বাদ দেয়।

```python
numbers = {10, 20, 30}

numbers.clear()

print(numbers)
```

Output:

```text
set()
```

## 7. Checking Whether an Item Exists

Set-এর মধ্যে কোনো item আছে কি না পরীক্ষা করতে `in` এবং `not in` ব্যবহার করা হয়।

```python
fruits = {"Apple", "Banana", "Mango"}

print("Apple" in fruits)
print("Orange" in fruits)
print("Orange" not in fruits)
```

Output:

```text
True
False
True
```

Set-এ membership testing সাধারণত খুব কার্যকর। গড় ক্ষেত্রে এটি দ্রুত কাজ করে, যদিও performance data ও implementation-এর ওপর নির্ভর করে।

## 8. Iterating Through a Set

`for` loop ব্যবহার করে Set-এর item-গুলো access করা যায়।

```python
fruits = {"Apple", "Banana", "Mango"}

for fruit in fruits:
    print(fruit)
```

এখানে item-গুলো Set-এর iteration order অনুযায়ী print হবে। Output-এর order অন্য পরিবেশে বা run-এ ভিন্ন হতে পারে।

**মনে রাখবে:** Set-এর iteration order-এর ওপর নির্ভর করে কোনো program design করা উচিত নয়।

## 9. Set Union

**Union** দুটি Set-এর সব unique item একসঙ্গে সংগ্রহ করে।

ধরা যাক:

```python
A = {1, 2, 3}
B = {3, 4, 5}
```

Union-এর result হবে `{1, 2, 3, 4, 5}`।

### 9.1 Using `union()`

```python
A = {1, 2, 3}
B = {3, 4, 5}

result = A.union(B)

print(result)
```

Output:

```text
{1, 2, 3, 4, 5}
```

### 9.2 Using `|` Operator

```python
A = {1, 2, 3}
B = {3, 4, 5}

print(A | B)
```

Output:

```text
{1, 2, 3, 4, 5}
```

দুটি Set-এর common item `3` result-এ একবারই এসেছে।

## 10. Set Intersection

**Intersection** দুটি Set-এর common item-গুলো return করে।

```python
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}

print(A.intersection(B))
```

Output:

```text
{3, 4}
```

`&` operator দিয়েও Intersection করা যায়।

```python
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}

print(A & B)
```

Output:

```text
{3, 4}
```

যে item দুটি Set-এই রয়েছে, শুধু সেগুলোই result-এ থাকবে।

## 11. Set Difference

**Difference** প্রথম Set-এ আছে, কিন্তু দ্বিতীয় Set-এ নেই—এমন item-গুলো return করে।

```python
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}

print(A.difference(B))
```

Output:

```text
{1, 2}
```

`-` operator দিয়েও Difference করা যায়।

```python
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}

print(A - B)
print(B - A)
```

Output:

```text
{1, 2}
{5, 6}
```

**গুরুত্বপূর্ণ:** Difference-এর result operand-এর order-এর ওপর নির্ভর করে। `A - B` এবং `B - A` একই নাও হতে পারে।

## 12. Symmetric Difference

**Symmetric Difference** দুটি Set-এর এমন item-গুলো return করে, যেগুলো যেকোনো একটিতে আছে, কিন্তু উভয়টিতে একসঙ্গে নেই।

```python
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}

print(A.symmetric_difference(B))
```

Output:

```text
{1, 2, 5, 6}
```

`^` operator দিয়েও করা যায়।

```python
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}

print(A ^ B)
```

Output:

```text
{1, 2, 5, 6}
```

এখানে common item `3` এবং `4` result-এ নেই।

## 13. Summary of Set Operations

ধরা যাক:

```python
A = {1, 2, 3}
B = {3, 4, 5}
```

| Operation | Method | Operator | Result |
|---|---|---|---|
| Union | `A.union(B)` | `A \| B` | `{1, 2, 3, 4, 5}` |
| Intersection | `A.intersection(B)` | `A & B` | `{3}` |
| Difference | `A.difference(B)` | `A - B` | `{1, 2}` |
| Symmetric difference | `A.symmetric_difference(B)` | `A ^ B` | `{1, 2, 4, 5}` |

মনে রাখার সহজ উপায়:

- **Union:** সব unique item।
- **Intersection:** Common item।
- **Difference:** প্রথমটিতে আছে, দ্বিতীয়টিতে নেই।
- **Symmetric Difference:** একটিতে আছে, কিন্তু উভয়টিতে নেই।

## 14. Updating a Set with Set Operations

Set-এর mathematical operation-গুলোর in-place version-ও রয়েছে। এগুলো original Set পরিবর্তন করে।

### 14.1 `update()`

Union-এর মতো কাজ করে এবং original Set-এ item যোগ করে।

```python
A = {1, 2, 3}
B = {3, 4, 5}

A.update(B)

print(A)
```

Output:

```text
{1, 2, 3, 4, 5}
```

### 14.2 `intersection_update()`

শুধু common item রেখে দেয়।

```python
A = {1, 2, 3, 4}
B = {3, 4, 5}

A.intersection_update(B)

print(A)
```

Output:

```text
{3, 4}
```

### 14.3 `difference_update()`

অন্য Set-এ থাকা item-গুলো বাদ দেয়।

```python
A = {1, 2, 3, 4}
B = {3, 4, 5}

A.difference_update(B)

print(A)
```

Output:

```text
{1, 2}
```

### 14.4 `symmetric_difference_update()`

দুটি Set-এর symmetric difference result-টি original Set-এ রাখে।

```python
A = {1, 2, 3}
B = {3, 4, 5}

A.symmetric_difference_update(B)

print(A)
```

Output:

```text
{1, 2, 4, 5}
```

এই method-গুলো original Set পরিবর্তন করে; তাই ব্যবহার করার আগে নিশ্চিত হও যে পরিবর্তনটি প্রয়োজন।

## 15. Subset and Superset

Set-এর মধ্যে অন্য Set-এর সব item আছে কি না, তা যাচাই করতে Subset ও Superset ব্যবহার করা হয়।

### 15.1 Subset

যদি `A`-এর প্রতিটি item `B`-তে থাকে, তাহলে `A` হলো `B`-এর Subset।

```python
A = {1, 2}
B = {1, 2, 3, 4}

print(A.issubset(B))
print(A <= B)
```

Output:

```text
True
True
```

### 15.2 Superset

যদি `A`-তে `B`-এর সব item থাকে, তাহলে `A` হলো `B`-এর Superset।

```python
A = {1, 2, 3, 4}
B = {1, 2}

print(A.issuperset(B))
print(A >= B)
```

Output:

```text
True
True
```

### 15.3 Proper Subset and Proper Superset

যখন একটি Set অন্য Set-এর Subset, কিন্তু দুটি Set সমান নয়, তখন তাকে Proper Subset বলা হয়।

```python
A = {1, 2}
B = {1, 2, 3}

print(A < B)
print(B > A)
```

Output:

```text
True
True
```

এখানে `<` এবং `>` numeric comparison নয়; Set-এর ক্ষেত্রে এগুলো Proper Subset এবং Proper Superset নির্দেশ করে।

## 16. Disjoint Sets

দুটি Set-এর মধ্যে কোনো common item না থাকলে তাদের **Disjoint Sets** বলা হয়।

```python
A = {1, 2, 3}
B = {4, 5, 6}

print(A.isdisjoint(B))
```

Output:

```text
True
```

এখানে কোনো common item নেই।

অন্য উদাহরণ:

```python
A = {1, 2, 3}
B = {3, 4, 5}

print(A.isdisjoint(B))
```

Output:

```text
False
```

এখানে `3` উভয় Set-এ আছে।

## 17. Frozen Set

`frozenset` হলো Set-এর immutable version। একবার তৈরি হলে এর item যোগ বা বাদ দেওয়া যায় না।

```python
numbers = frozenset([10, 20, 30])

print(numbers)
print(type(numbers))
```

Output:

```text
frozenset({10, 20, 30})
<class 'frozenset'>
```

এ ধরনের operation করা যাবে না:

```python
numbers = frozenset([10, 20, 30])

numbers.add(40)
```

এটি `AttributeError` তৈরি করবে, কারণ `frozenset`-এ `add()` method নেই।

তবে Frozen Set-এর সঙ্গে সাধারণ Set-এর মতো অনেক mathematical operation করা যায়।

```python
A = frozenset([1, 2, 3])
B = frozenset([3, 4, 5])

print(A | B)
print(A & B)
```

Output:

```text
frozenset({1, 2, 3, 4, 5})
frozenset({3})
```

যেহেতু Frozen Set immutable এবং hashable, এর সব item hashable হলে এটি Dictionary key বা অন্য Set-এর item হিসেবেও ব্যবহার করা যায়।

## 18. Which Values Can a Set Contain?

Set-এর item-গুলো **hashable** হতে হয়। সাধারণভাবে Integer, Float, String এবং Tuple-এর মতো immutable ও hashable object Set-এর item হতে পারে।

Example:

```python
data = {10, 3.5, "Python", (1, 2)}

print(data)
```

এটি valid Set।

কিন্তু List, Dictionary এবং Set-এর মতো unhashable object সরাসরি Set-এর item হতে পারে না।

Incorrect:

```python
data = {[1, 2], [3, 4]}
```

এটি `TypeError` তৈরি করবে, কারণ List unhashable।

একইভাবে:

```python
data = {{1, 2}, {3, 4}}
```

এটিও `TypeError` তৈরি করবে, কারণ সাধারণ Set নিজেই unhashable।

প্রয়োজন হলে List-কে Tuple-এ এবং nested Set-কে `frozenset`-এ রূপান্তর করা যেতে পারে—তবে সেগুলোর সব nested item-ও hashable হতে হবে।

## 19. Removing Duplicates from a List

Set-এর একটি পরিচিত ব্যবহার হলো List থেকে duplicate value বাদ দেওয়া।

```python
numbers = [10, 20, 10, 30, 20, 40]

unique_numbers = set(numbers)

print(unique_numbers)
```

Output-এর order ভিন্ন হতে পারে:

```text
{10, 20, 30, 40}
```

তবে মনে রাখবে, Set-এ রূপান্তর করলে List-এর original order সংরক্ষিত থাকে না।

যদি duplicate বাদ দেওয়ার পাশাপাশি original order রাখতে চাও, তাহলে:

```python
numbers = [10, 20, 10, 30, 20, 40]

unique_numbers = list(dict.fromkeys(numbers))

print(unique_numbers)
```

Output:

```text
[10, 20, 30, 40]
```

এখানে Dictionary-এর insertion order ব্যবহার করে প্রথম occurrence-এর ক্রম রাখা হয়েছে।

## 20. Common Beginner Mistakes

### Mistake 1: Using `{}` to Create an Empty Set

```python
data = {}

print(type(data))
```

Output:

```text
<class 'dict'>
```

Empty Set-এর জন্য:

```python
data = set()

print(type(data))
```

Output:

```text
<class 'set'>
```

### Mistake 2: Trying to Access Items by Index

```python
numbers = {10, 20, 30}

print(numbers[0])
```

এটি `TypeError` তৈরি করবে। Set indexing support করে না।

### Mistake 3: Assuming Set Order Is Fixed

```python
numbers = {50, 10, 40, 20, 30}

print(numbers)
```

Output-এর order-এর ওপর নির্ভর করবে না। Ordered output প্রয়োজন হলে:

```python
numbers = {50, 10, 40, 20, 30}

print(sorted(numbers))
```

Output:

```text
[10, 20, 30, 40, 50]
```

এখানে `sorted()` একটি List return করে।

### Mistake 4: Using `remove()` for a Missing Item

```python
numbers = {10, 20, 30}

numbers.remove(50)
```

এটি `KeyError` তৈরি করবে। Item না থাকলেও error এড়াতে `discard()` ব্যবহার করা যায়।

### Mistake 5: Adding a List to a Set

```python
numbers = {1, 2}

numbers.add([3, 4])
```

এটি `TypeError` তৈরি করবে, কারণ List unhashable। আলাদা item যোগ করতে `update([3, 4])` ব্যবহার করো।

### Mistake 6: Confusing `add()` and `update()`

```python
A = {1, 2}
A.add((3, 4))

print(A)
```

এখানে Tuple-টি একটি item হিসেবে যুক্ত হয়েছে।

```python
B = {1, 2}
B.update((3, 4))

print(B)
```

এখানে `3` এবং `4` আলাদা item হিসেবে যোগ হয়েছে।

## 21. Practice Exercises

### Exercise 1: Create a Set

পাঁচটি Integer দিয়ে একটি Set তৈরি করো। একই Integer একাধিকবার দিয়ে পরীক্ষা করো যে duplicate কীভাবে handle হয়।

### Exercise 2: Remove Duplicates

```python
numbers = [10, 20, 10, 30, 20, 40, 50, 30]
```

এই List থেকে duplicate বাদ দিয়ে unique values বের করো।

### Exercise 3: Add and Remove

```python
numbers = {10, 20, 30}
```

- `add()` দিয়ে `40` যোগ করো।
- `update()` দিয়ে `50` ও `60` যোগ করো।
- `discard()` দিয়ে `20` বাদ দাও।
- `clear()` ব্যবহার করে Set খালি করো।

### Exercise 4: Set Operations

```python
A = {1, 2, 3, 4, 5}
B = {4, 5, 6, 7, 8}
```

নিচের operation-গুলোর result বের করো:

1. Union
2. Intersection
3. `A - B`
4. `B - A`
5. Symmetric Difference

### Exercise 5: Subset and Superset

```python
A = {1, 2}
B = {1, 2, 3, 4}
```

`issubset()` এবং `issuperset()` ব্যবহার করে সম্পর্ক পরীক্ষা করো।

### Exercise 6: Disjoint Sets

```python
A = {1, 2, 3}
B = {4, 5, 6}
C = {3, 4, 5}
```

`isdisjoint()` ব্যবহার করে `A` ও `B`, এবং `A` ও `C` পরীক্ষা করো।

### Exercise 7: Unique Student IDs

দুটি আলাদা ক্লাসের শিক্ষার্থীদের ID দিয়ে দুটি Set তৈরি করো। Union ব্যবহার করে মোট unique ID বের করো এবং Intersection দিয়ে উভয় ক্লাসে থাকা common ID বের করো।

### Exercise 8: Frozen Set

একটি `frozenset` তৈরি করো। এর ওপর Union এবং Intersection চালাও। এরপর `add()` ব্যবহার করার চেষ্টা করে error-এর কারণ ব্যাখ্যা করো।

### Exercise 9: Membership Testing

একটি Set-এ কয়েকটি programming language রাখো। `in` এবং `not in` দিয়ে পরীক্ষা করো Python এবং Java উপস্থিত আছে কি না।

### Exercise 10: Mini Project — Course Enrollment Comparison

দুটি course-এ enrolled student ID দিয়ে দুটি Set তৈরি করো।

- উভয় course-এ থাকা শিক্ষার্থী খুঁজে বের করো।
- শুধু প্রথম course-এ থাকা শিক্ষার্থী বের করো।
- শুধু দ্বিতীয় course-এ থাকা শিক্ষার্থী বের করো।
- দুই course মিলিয়ে মোট unique student ID বের করো।

## 22. Key Takeaways

- Set একটি built-in collection type, যা unique items রাখে।
- Set unordered; তাই indexing এবং slicing support করে না।
- Empty Set তৈরির জন্য `set()` ব্যবহার করতে হয়; `{}` হলো Empty Dictionary।
- `add()` একটি item যোগ করে এবং `update()` iterable-এর item-গুলো যোগ করে।
- `remove()` item না পেলে `KeyError` দেয়; `discard()` দেয় না।
- Union সব unique item সংগ্রহ করে।
- Intersection common item return করে।
- Difference প্রথম Set-এ আছে কিন্তু দ্বিতীয়টিতে নেই—এমন item return করে।
- Symmetric Difference শুধু এক পাশে থাকা item-গুলো return করে।
- `issubset()`, `issuperset()` এবং `isdisjoint()` Set-এর সম্পর্ক পরীক্ষা করে।
- Set-এর item hashable হতে হয়।
- `frozenset` হলো immutable Set।
- List থেকে duplicate বাদ দিতে Set ব্যবহার করা যায়, তবে এতে original order সংরক্ষিত থাকে না।

## 23. Next Topic

পরবর্তী ফাইল:

**`17_Dictionary_Data_Type.md`**

সেখানে Python Dictionary, key-value pairs, accessing values, adding and updating items, removing items, iteration এবং গুরুত্বপূর্ণ Dictionary methods শেখা হবে।