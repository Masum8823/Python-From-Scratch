# 26. Converting Between Collection Types in Python

## 1. Introduction to Collection Type Conversion

Python-এ Collection Type Conversion হলো একটি collection-কে অন্য collection type-এ রূপান্তর করার প্রক্রিয়া।

Python-এর গুরুত্বপূর্ণ built-in collection types হলো:

- `list` — Ordered এবং mutable collection।
- `tuple` — Ordered এবং immutable collection।
- `set` — Unique elements-এর unordered collection।
- `dict` — Key-value pair সংরক্ষণ করে।

প্রয়োজন অনুযায়ী একটি collection-কে অন্য type-এ convert করা যায়।

Example:

```python
numbers = (10, 20, 30)

result = list(numbers)

print(result)
print(type(result))
```

Output:

```text
[10, 20, 30]
<class 'list'>
```

এখানে Tuple-কে List-এ convert করা হয়েছে।

**মনে রাখবে:** Conversion-এর সময় সব collection-এর বৈশিষ্ট্য অক্ষুণ্ণ থাকে না। যেমন, Set-এ duplicate elements থাকে না এবং Dictionary তৈরির সময় প্রতিটি key unique হতে হয়।

## 2. Converting an Iterable to a List

`list()` function ব্যবহার করে iterable object থেকে List তৈরি করা যায়।

Iterable হলো এমন object, যার elements একটির পর একটি access করা যায়।

### 2.1 Tuple to List

```python
data = (10, 20, 30)

result = list(data)

print(result)
```

Output:

```text
[10, 20, 30]
```

### 2.2 String to List

```python
text = "Python"

result = list(text)

print(result)
```

Output:

```text
['P', 'y', 't', 'h', 'o', 'n']
```

এখানে String-এর প্রতিটি character List-এর একটি element হয়েছে।

### 2.3 Set to List

```python
numbers = {10, 20, 30}

result = list(numbers)

print(result)
```

Output-এর element order ভিন্ন হতে পারে, কারণ Set-এর iteration order-এর ওপর নির্ভর করে result তৈরি হয়।

### 2.4 Range to List

```python
numbers = range(1, 6)

result = list(numbers)

print(result)
```

Output:

```text
[1, 2, 3, 4, 5]
```

### 2.5 Dictionary to List

Dictionary-কে সরাসরি `list()` দিয়ে convert করলে তার keys পাওয়া যায়।

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}

result = list(student)

print(result)
```

Output:

```text
['name', 'age', 'department']
```

Dictionary-এর values পেতে:

```python
result = list(student.values())

print(result)
```

Output:

```text
['Masum', 22, 'CSE']
```

Key-value pair পেতে:

```python
result = list(student.items())

print(result)
```

Output:

```text
[('name', 'Masum'), ('age', 22), ('department', 'CSE')]
```

## 3. Converting an Iterable to a Tuple

`tuple()` function ব্যবহার করে iterable object থেকে Tuple তৈরি করা যায়।

### 3.1 List to Tuple

```python
numbers = [10, 20, 30]

result = tuple(numbers)

print(result)
print(type(result))
```

Output:

```text
(10, 20, 30)
<class 'tuple'>
```

### 3.2 String to Tuple

```python
text = "ABC"

result = tuple(text)

print(result)
```

Output:

```text
('A', 'B', 'C')
```

### 3.3 Range to Tuple

```python
numbers = range(1, 5)

result = tuple(numbers)

print(result)
```

Output:

```text
(1, 2, 3, 4)
```

### 3.4 Set to Tuple

```python
numbers = {10, 20, 30}

result = tuple(numbers)

print(result)
```

Output-এর element order ভিন্ন হতে পারে, কারণ Set-এর elements-এর নির্দিষ্ট positional order নেই।

## 4. Converting an Iterable to a Set

`set()` function ব্যবহার করে iterable object থেকে Set তৈরি করা যায়।

Set-এর সবচেয়ে গুরুত্বপূর্ণ বৈশিষ্ট্য হলো, এতে duplicate elements একাধিকবার রাখা হয় না।

### 4.1 List to Set

```python
numbers = [10, 20, 10, 30, 20]

result = set(numbers)

print(result)
```

Output-এ `10`, `20` এবং `30` একবার করে থাকবে; তাদের order নির্দিষ্ট নয়।

এখানে duplicate values বাদ পড়েছে।

### 4.2 Tuple to Set

```python
numbers = (1, 2, 2, 3, 3, 3)

result = set(numbers)

print(result)
```

Output-এর Set-এ থাকবে শুধু unique values: `1`, `2` এবং `3`।

### 4.3 String to Set

```python
text = "banana"

result = set(text)

print(result)
```

Set-এ `b`, `a` এবং `n`—প্রতিটি character একবার করে থাকবে। Output order নির্দিষ্ট নয়।

### 4.4 Removing Duplicates from a List

List থেকে duplicate values বাদ দেওয়ার একটি সহজ উপায় হলো Set ব্যবহার করা।

```python
numbers = [1, 2, 2, 3, 1, 4]

unique_numbers = list(set(numbers))

print(unique_numbers)
```

এখানে unique values পাওয়া যাবে, কিন্তু original order বজায় থাকবে—এমন নিশ্চয়তা নেই।

যদি original order বজায় রেখে duplicate বাদ দিতে চাও, তাহলে Dictionary-এর insertion-order property ব্যবহার করা যায়:

```python
numbers = [1, 2, 2, 3, 1, 4]

unique_numbers = list(dict.fromkeys(numbers))

print(unique_numbers)
```

Output:

```text
[1, 2, 3, 4]
```

এটি কাজ করে যখন elements Dictionary key হিসেবে ব্যবহারযোগ্য হয়, অর্থাৎ hashable হয়।

## 5. Converting Pairs to a Dictionary

`dict()` function ব্যবহার করে key-value pair-এর iterable থেকে Dictionary তৈরি করা যায়।

প্রতিটি pair-এ দুটি element থাকতে হবে: প্রথমটি key, দ্বিতীয়টি value।

### 5.1 List of Tuples to Dictionary

```python
data = [
    ("name", "Masum"),
    ("age", 22),
    ("department", "CSE")
]

student = dict(data)

print(student)
```

Output:

```text
{'name': 'Masum', 'age': 22, 'department': 'CSE'}
```

### 5.2 List of Lists to Dictionary

```python
data = [
    ["name", "Masum"],
    ["age", 22]
]

student = dict(data)

print(student)
```

Output:

```text
{'name': 'Masum', 'age': 22}
```

প্রতিটি inner list-এ ঠিক দুটি element থাকতে হবে।

### 5.3 Using `zip()` to Create a Dictionary

দুটি iterable-এর corresponding elements দিয়ে Dictionary তৈরি করতে `zip()` ব্যবহার করা যায়।

```python
keys = ["name", "age", "department"]
values = ["Masum", 22, "CSE"]

student = dict(zip(keys, values))

print(student)
```

Output:

```text
{'name': 'Masum', 'age': 22, 'department': 'CSE'}
```

**Important:** `zip()` সাধারণত সবচেয়ে ছোট iterable শেষ হলে থেমে যায়। তাই দুটি iterable-এর length আলাদা হলে অতিরিক্ত elements বাদ পড়তে পারে।

## 6. Converting a Dictionary to Other Collections

Dictionary থেকে keys, values অথবা key-value pairs নিয়ে বিভিন্ন collection তৈরি করা যায়।

ধরা যাক:

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}
```

### 6.1 Dictionary Keys to List

```python
keys = list(student.keys())

print(keys)
```

Output:

```text
['name', 'age', 'department']
```

### 6.2 Dictionary Values to List

```python
values = list(student.values())

print(values)
```

Output:

```text
['Masum', 22, 'CSE']
```

### 6.3 Dictionary Items to List

```python
items = list(student.items())

print(items)
```

Output:

```text
[('name', 'Masum'), ('age', 22), ('department', 'CSE')]
```

এখানে প্রতিটি item একটি Tuple হিসেবে রয়েছে।

### 6.4 Dictionary Keys to Set

```python
keys = set(student.keys())

print(keys)
```

এখানে Dictionary-এর keys দিয়ে Set তৈরি হয়েছে। Key-গুলো unique হওয়ায় কোনো duplicate থাকবে না।

## 7. Converting a List of Pairs to a Dictionary: Duplicate Keys

Dictionary-তে প্রতিটি key unique। তাই duplicate key থাকলে পরের value আগের value-কে replace করে।

Example:

```python
data = [
    ("name", "Masum"),
    ("age", 22),
    ("name", "Abdulla")
]

result = dict(data)

print(result)
```

Output:

```text
{'name': 'Abdulla', 'age': 22}
```

এখানে `"name"` key-এর শেষ value `"Abdulla"` রাখা হয়েছে।

**সতর্কতা:** Duplicate key থাকলে আগের value হারিয়ে যেতে পারে। তাই Dictionary conversion-এর আগে data যাচাই করা গুরুত্বপূর্ণ।

## 8. Converting Between Collections and Data Loss

Collection conversion-এর সময় কিছু তথ্য হারিয়ে যেতে পারে অথবা পরিবর্তিত হতে পারে।

| Conversion | কী হতে পারে |
|---|---|
| List → Tuple | Element order বজায় থাকে; collection immutable হয় |
| Tuple → List | Element order বজায় থাকে; collection mutable হয় |
| List → Set | Duplicate elements বাদ যায়; order হারাতে পারে |
| String → List | প্রতিটি character আলাদা element হয় |
| String → Set | Duplicate characters বাদ যায়; order হারাতে পারে |
| Dictionary → List | শুধু keys পাওয়া যায় |
| Pairs → Dictionary | Duplicate keys-এর আগের values replace হতে পারে |
| `zip()` → Dictionary | Unequal-length iterable হলে অতিরিক্ত elements বাদ পড়তে পারে |

Conversion করার আগে বুঝতে হবে, কোন information বজায় রাখতে হবে।

## 9. Shallow Copy and Nested Collections

Collection conversion করলেই সব ক্ষেত্রে nested object-এর independent copy তৈরি হয় না।

Example:

```python
original = [[1, 2], [3, 4]]
copied = list(original)

copied[0][0] = 100

print(original)
print(copied)
```

Output:

```text
[[100, 2], [3, 4]]
[[100, 2], [3, 4]]
```

এখানে outer List নতুন হলেও inner List-গুলো একই nested object reference করে।

এ ধরনের copy-কে **shallow copy** বলা হয়।

Independent nested copy প্রয়োজন হলে:

```python
import copy

original = [[1, 2], [3, 4]]
copied = copy.deepcopy(original)

copied[0][0] = 100

print(original)
print(copied)
```

Output:

```text
[[1, 2], [3, 4]]
[[100, 2], [3, 4]]
```

এখানে `deepcopy()` nested objects-সহ independent copy তৈরি করেছে।

## 10. Common Conversion Errors

### 10.1 Creating a Set from Unhashable Elements

```python
data = [[1, 2], [3, 4]]

result = set(data)
```

এটি `TypeError` তৈরি করবে, কারণ List unhashable এবং Set-এর element হিসেবে সরাসরি রাখা যায় না।

যদি data উপযুক্ত হয়, তাহলে Tuple ব্যবহার করা যেতে পারে:

```python
data = [[1, 2], [3, 4]]

result = set(tuple(item) for item in data)

print(result)
```

Output-এর Tuple order নির্দিষ্ট নয়।

### 10.2 Invalid Dictionary Pair

```python
data = [("name", "Masum"), ("age", 22, "extra")]

result = dict(data)
```

এটি `ValueError` তৈরি করবে, কারণ প্রতিটি pair-এ ঠিক দুটি element থাকতে হয়।

### 10.3 Passing a Non-Iterable to `list()`

```python
result = list(10)
```

এটি `TypeError` তৈরি করবে, কারণ Integer `10` iterable নয়।

যদি একটি Integer-কে List-এর একটি element হিসেবে রাখতে চাও:

```python
result = [10]

print(result)
```

Output:

```text
[10]
```

### 10.4 Converting Dictionary Directly to Set

```python
student = {"name": "Masum", "age": 22}

result = set(student)

print(result)
```

এখানে Dictionary-এর keys দিয়ে Set তৈরি হবে, values দিয়ে নয়।

### 10.5 Losing Order When Using Set

```python
numbers = [3, 1, 3, 2, 1]

result = list(set(numbers))

print(result)
```

এখানে duplicate বাদ যাবে, কিন্তু original List-এর order বজায় থাকার নিশ্চয়তা নেই।

## 11. Practical Examples

### Example 1: Convert Marks to a Tuple

```python
marks = [85, 90, 78, 92]

marks_tuple = tuple(marks)

print(marks_tuple)
print(type(marks_tuple))
```

Output:

```text
(85, 90, 78, 92)
<class 'tuple'>
```

### Example 2: Find Unique Student IDs

```python
student_ids = [101, 102, 101, 103, 102, 104]

unique_ids = set(student_ids)

print(unique_ids)
```

Set-এর মধ্যে প্রতিটি ID একবার করে থাকবে।

### Example 3: Create a Student Dictionary

```python
fields = ["name", "id", "department"]
values = ["Masum", 1350, "CSE"]

student = dict(zip(fields, values))

print(student)
```

Output:

```text
{'name': 'Masum', 'id': 1350, 'department': 'CSE'}
```

### Example 4: Convert Dictionary Values to a List

```python
prices = {
    "pen": 10,
    "book": 80,
    "bag": 650
}

price_list = list(prices.values())

print(price_list)
```

Output:

```text
[10, 80, 650]
```

### Example 5: Remove Duplicates While Preserving Order

```python
courses = ["Python", "AI", "Python", "MIS", "AI"]

unique_courses = list(dict.fromkeys(courses))

print(unique_courses)
```

Output:

```text
['Python', 'AI', 'MIS']
```

## 12. Practice Exercises

### Exercise 1: List to Tuple

নিচের List-কে Tuple-এ convert করো এবং result-এর type পরীক্ষা করো।

```python
numbers = [10, 20, 30, 40]
```

### Exercise 2: Remove Duplicates

নিচের List থেকে duplicate values বাদ দিয়ে একটি Set তৈরি করো।

```python
numbers = [1, 2, 2, 3, 1, 4, 4, 5]
```

### Exercise 3: String to List

`"Python"` String-কে List-এ convert করো এবং প্রতিটি character আলাদাভাবে print করো।

### Exercise 4: Dictionary Conversion

নিচের Dictionary থেকে keys, values এবং items-এর আলাদা List তৈরি করো।

```python
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}
```

### Exercise 5: Pairs to Dictionary

নিচের data থেকে Dictionary তৈরি করো:

```python
data = [
    ("name", "Masum"),
    ("cgpa", 3.95),
    ("department", "CSE")
]
```

### Exercise 6: Identify Data Loss

নিচের code-এর output অনুমান করো:

```python
numbers = [1, 2, 2, 3, 1]

print(list(set(numbers)))
```

Duplicate values কীভাবে বাদ পড়ে এবং কেন order নিশ্চিত নয়, তা ব্যাখ্যা করো।

### Exercise 7: Duplicate Dictionary Keys

নিচের code-এর output অনুমান করো:

```python
data = [
    ("a", 10),
    ("b", 20),
    ("a", 30)
]

print(dict(data))
```

### Exercise 8: Mini Project — Student Records

একটি program তৈরি করো, যেখানে:

1. Student names-এর একটি List থাকবে।
2. List-টিকে Tuple-এ convert করবে।
3. Duplicate names বাদ দিয়ে একটি Set তৈরি করবে।
4. Names এবং marks-এর pair থেকে Dictionary তৈরি করবে।
5. প্রতিটি collection-এর type এবং result print করবে।

## 13. Key Takeaways

- `list()`, `tuple()`, `set()` এবং `dict()` ব্যবহার করে বিভিন্ন collection তৈরি করা যায়।
- String থেকে List বা Tuple তৈরি করলে প্রতিটি character আলাদা element হয়।
- Set duplicate elements বাদ দেয় এবং original order বজায় রাখার নিশ্চয়তা দেয় না।
- Dictionary-কে সরাসরি List বা Set-এ convert করলে keys পাওয়া যায়।
- `dict()` key-value pair-এর iterable থেকে Dictionary তৈরি করতে পারে।
- Duplicate Dictionary keys-এর ক্ষেত্রে পরের value আগের value-কে replace করে।
- `zip()`-এর iterable-গুলোর length আলাদা হলে অতিরিক্ত elements বাদ পড়তে পারে।
- Shallow copy-তে nested objects shared থাকতে পারে; `deepcopy()` nested objects-এর independent copy তৈরিতে কাজে লাগে।
- Conversion-এর আগে data loss এবং collection-এর বৈশিষ্ট্য বিবেচনা করা উচিত।

## 14. Next Topic

পরবর্তী ফাইল:

**`27_Type_Conversion_Errors.md`**

সেখানে Type Conversion-এর সময় `ValueError`, `TypeError` এবং অন্যান্য সাধারণ সমস্যা কেন হয়, কীভাবে error handle করতে হয় এবং নিরাপদ conversion কীভাবে লিখতে হয়—এসব বিস্তারিতভাবে শেখা হবে।