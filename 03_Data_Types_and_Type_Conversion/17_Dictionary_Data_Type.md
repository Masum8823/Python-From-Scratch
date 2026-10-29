# 17. Dictionary Data Type in Python

## 1. What Is a Dictionary?

Python-এ **Dictionary হলো একটি built-in data type, যা তথ্যকে `key-value pairs` আকারে সংরক্ষণ করে।**

প্রতিটি item-এর দুটি অংশ থাকে:

- **Key:** যে পরিচয় ব্যবহার করে value খুঁজে পাওয়া যায়।
- **Value:** যে তথ্যটি সংরক্ষণ করা হয়েছে।

Dictionary তৈরি করতে curly braces `{}` ব্যবহার করা হয়। প্রতিটি key ও value-এর মাঝে colon `:` থাকে এবং একাধিক pair comma `,` দিয়ে আলাদা করা হয়।

Example:

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}

print(student)
```

Output:

```text
{'name': 'Masum', 'age': 22, 'cgpa': 3.95}
```

এখানে:

| Key | Value |
|---|---|
| `"name"` | `"Masum"` |
| `"age"` | `22` |
| `"cgpa"` | `3.95` |

`student["name"]` লিখলে `"Masum"` পাওয়া যাবে।

**মনে রাখবে:** List-এ সাধারণত index দিয়ে item access করা হয়, কিন্তু Dictionary-তে key দিয়ে value access করা হয়।

## 2. Characteristics of Dictionaries

Python Dictionary-এর গুরুত্বপূর্ণ বৈশিষ্ট্যগুলো হলো:

| Feature | Explanation |
|---|---|
| Key-value pairs | প্রতিটি item একটি key ও value নিয়ে গঠিত |
| Ordered | Python 3.7 থেকে insertion order সংরক্ষিত থাকে |
| Mutable | Item যোগ, update এবং remove করা যায় |
| Unique keys | একই key একাধিকবার থাকলে শেষ value কার্যকর থাকে |
| Different value types | বিভিন্ন data type-এর value রাখা যায় |
| Hashable keys | Dictionary key hashable হতে হয় |
| No positional indexing | List-এর মতো numeric index দিয়ে item access করা হয় না |

Example:

```python
student = {
    "name": "Masum",
    "age": 22,
    "active": True
}

print(student)
```

একটি Dictionary-তে String, Integer, Boolean, List, এমনকি অন্য Dictionary-ও value হিসেবে রাখা যায়।

## 3. Creating a Dictionary

### 3.1 Dictionary with Multiple Items

```python
student = {
    "name": "Masum",
    "department": "CSE",
    "semester": 9
}

print(student)
```

Output:

```text
{'name': 'Masum', 'department': 'CSE', 'semester': 9}
```

### 3.2 Empty Dictionary

Empty Dictionary তৈরি করতে `{}` অথবা `dict()` ব্যবহার করা যায়।

```python
a = {}
b = dict()

print(a)
print(b)

print(type(a))
print(type(b))
```

Output:

```text
{}
{}
<class 'dict'>
<class 'dict'>
```

### 3.3 Using the `dict()` Constructor

`dict()` constructor ব্যবহার করেও Dictionary তৈরি করা যায়।

```python
student = dict(name="Masum", age=22, cgpa=3.95)

print(student)
```

Output:

```text
{'name': 'Masum', 'age': 22, 'cgpa': 3.95}
```

এই পদ্ধতিতে key-গুলো valid Python identifiers হতে হবে এবং তাদের নাম String key হিসেবে ব্যবহৃত হয়।

### 3.4 Creating a Dictionary from Pairs

```python
data = dict([
    ("name", "Masum"),
    ("age", 22),
    ("cgpa", 3.95)
])

print(data)
```

Output:

```text
{'name': 'Masum', 'age': 22, 'cgpa': 3.95}
```

এখানে প্রতিটি pair একটি Tuple, যেখানে প্রথম item key এবং দ্বিতীয় item value।

### 3.5 Using `fromkeys()`

`dict.fromkeys()` একই value দিয়ে একাধিক key তৈরি করতে পারে।

```python
keys = ["name", "age", "cgpa"]

student = dict.fromkeys(keys, None)

print(student)
```

Output:

```text
{'name': None, 'age': None, 'cgpa': None}
```

এখানে সব key-এর value `None`।

**সতর্কতা:** Mutable value, যেমন List, `fromkeys()`-এ দিলে সব key একই List object reference করতে পারে।

```python
data = dict.fromkeys(["a", "b"], [])

data["a"].append(10)

print(data)
```

Output:

```text
{'a': [10], 'b': [10]}
```

কারণ দুটি key-এর value একই List object।

## 4. Dictionary Keys and Values

### 4.1 Keys Must Be Unique

একটি Dictionary-তে একই key একাধিকবার লিখলে শেষ value কার্যকর হয়।

```python
student = {
    "name": "Masum",
    "age": 22,
    "name": "Abdulla"
}

print(student)
```

Output:

```text
{'name': 'Abdulla', 'age': 22}
```

এখানে `"name"` key-এর শেষ value `"Abdulla"`।

তাই একই key বারবার ব্যবহার করে আলাদা item সংরক্ষণ করা যায় না।

### 4.2 Keys Must Be Hashable

Dictionary key হিসেবে সাধারণত String, Integer, Boolean এবং উপযুক্ত Tuple ব্যবহার করা যায়।

```python
data = {
    "name": "Masum",
    101: "Student ID",
    (1, 2): "Coordinate"
}

print(data["name"])
print(data[101])
print(data[(1, 2)])
```

Output:

```text
Masum
Student ID
Coordinate
```

কিন্তু List, Dictionary এবং সাধারণ Set key হিসেবে ব্যবহার করা যায় না, কারণ এগুলো unhashable।

Incorrect:

```python
data = {
    [1, 2]: "Numbers"
}
```

এটি `TypeError` তৈরি করবে।

### 4.3 Values Can Be Different Data Types

Dictionary-এর value যেকোনো ধরনের object হতে পারে।

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95,
    "active": True,
    "courses": ["AI", "MIS", "VLSI"],
    "address": None
}

print(student)
```

এখানে বিভিন্ন data type-এর value একই Dictionary-তে রাখা হয়েছে।

## 5. Accessing Dictionary Values

### 5.1 Using Square Brackets

Key ব্যবহার করে value access করা যায়।

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}

print(student["name"])
print(student["age"])
```

Output:

```text
Masum
22
```

Key Dictionary-তে না থাকলে `KeyError` হয়।

```python
student = {"name": "Masum"}

print(student["age"])
```

এই code `KeyError` তৈরি করবে।

### 5.2 Using `get()`

`get()` method ব্যবহার করে value access করা যায়। Key না থাকলে এটি default হিসেবে `None` return করে।

```python
student = {"name": "Masum"}

print(student.get("name"))
print(student.get("age"))
```

Output:

```text
Masum
None
```

নিজের পছন্দমতো default value দেওয়া যায়।

```python
student = {"name": "Masum"}

print(student.get("age", 0))
```

Output:

```text
0
```

**পার্থক্য:**

- `student["age"]` — key না থাকলে `KeyError`।
- `student.get("age")` — key না থাকলে `None`।
- `student.get("age", 0)` — key না থাকলে `0`।

## 6. Adding New Items

Dictionary mutable হওয়ায় নতুন key-value pair যোগ করা যায়।

```python
student = {
    "name": "Masum",
    "age": 22
}

student["cgpa"] = 3.95

print(student)
```

Output:

```text
{'name': 'Masum', 'age': 22, 'cgpa': 3.95}
```

এখানে `"cgpa"` নামে নতুন key যোগ হয়েছে।

একইভাবে:

```python
student = {}

student["name"] = "Masum"
student["department"] = "CSE"
student["semester"] = 9

print(student)
```

Output:

```text
{'name': 'Masum', 'department': 'CSE', 'semester': 9}
```

## 7. Updating Dictionary Values

আগে থেকে থাকা key-এর value পরিবর্তন করা যায়।

```python
student = {
    "name": "Masum",
    "age": 22
}

student["age"] = 23

print(student)
```

Output:

```text
{'name': 'Masum', 'age': 23}
```

এখানে নতুন key তৈরি হয়নি; আগের `"age"` key-এর value পরিবর্তিত হয়েছে।

### Using `update()`

`update()` দিয়ে একসঙ্গে একাধিক key-value pair যোগ বা পরিবর্তন করা যায়।

```python
student = {
    "name": "Masum",
    "age": 22
}

student.update({
    "age": 23,
    "cgpa": 3.95
})

print(student)
```

Output:

```text
{'name': 'Masum', 'age': 23, 'cgpa': 3.95}
```

এখানে `"age"` update হয়েছে এবং `"cgpa"` নতুন key হিসেবে যোগ হয়েছে।

## 8. Removing Items from a Dictionary

Dictionary থেকে item বাদ দেওয়ার কয়েকটি পদ্ধতি রয়েছে।

### 8.1 `pop()`

`pop()` নির্দিষ্ট key-এর item বাদ দেয় এবং তার value return করে।

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}

removed = student.pop("age")

print(removed)
print(student)
```

Output:

```text
22
{'name': 'Masum', 'cgpa': 3.95}
```

Key না থাকলে `KeyError` হতে পারে। তবে default value দিলে error এড়ানো যায়।

```python
student = {"name": "Masum"}

removed = student.pop("age", 0)

print(removed)
```

Output:

```text
0
```

### 8.2 `popitem()`

`popitem()` Dictionary-এর শেষ inserted key-value pair remove করে এবং সেটিকে Tuple হিসেবে return করে।

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}

removed = student.popitem()

print(removed)
print(student)
```

Output:

```text
('cgpa', 3.95)
{'name': 'Masum', 'age': 22}
```

Python 3.7 থেকে এটি LIFO (Last In, First Out) নিয়মে কাজ করে।

Empty Dictionary-তে `popitem()` ব্যবহার করলে `KeyError` হয়।

### 8.3 `del`

`del` দিয়ে নির্দিষ্ট key-এর item বাদ দেওয়া যায়।

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}

del student["age"]

print(student)
```

Output:

```text
{'name': 'Masum', 'cgpa': 3.95}
```

Key না থাকলে `KeyError` হয়।

পুরো Dictionary variable মুছতেও `del` ব্যবহার করা যায়।

```python
student = {"name": "Masum"}

del student
```

এরপর `student` access করলে `NameError` হবে, যদি একই নামে অন্য binding তৈরি না করা হয়।

### 8.4 `clear()`

`clear()` Dictionary-এর সব key-value pair বাদ দেয়।

```python
student = {
    "name": "Masum",
    "age": 22
}

student.clear()

print(student)
```

Output:

```text
{}
```

Dictionary object-এর binding থাকে, কিন্তু Dictionary খালি হয়ে যায়।

## 9. Checking Whether a Key Exists

Dictionary-তে `in` এবং `not in` operator সাধারণত key পরীক্ষা করে।

```python
student = {
    "name": "Masum",
    "age": 22
}

print("name" in student)
print("cgpa" in student)
print("cgpa" not in student)
```

Output:

```text
True
False
True
```

**মনে রাখবে:** `in` দিয়ে Dictionary পরীক্ষা করলে defaultভাবে key খোঁজা হয়, value নয়।

Value পরীক্ষা করতে:

```python
student = {
    "name": "Masum",
    "age": 22
}

print("Masum" in student.values())
print(22 in student.values())
```

Output:

```text
True
True
```

## 10. Getting All Keys, Values and Items

Dictionary-এর key, value এবং key-value pair আলাদাভাবে পাওয়ার জন্য তিনটি গুরুত্বপূর্ণ method রয়েছে।

### 10.1 `keys()`

`keys()` সব key-এর একটি view return করে।

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}

print(student.keys())
```

Output:

```text
dict_keys(['name', 'age', 'cgpa'])
```

List হিসেবে প্রয়োজন হলে:

```python
print(list(student.keys()))
```

Output:

```text
['name', 'age', 'cgpa']
```

### 10.2 `values()`

`values()` সব value-এর একটি view return করে।

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}

print(student.values())
```

Output:

```text
dict_values(['Masum', 22, 3.95])
```

### 10.3 `items()`

`items()` প্রতিটি key-value pair-কে Tuple হিসেবে দেয়।

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}

print(student.items())
```

Output:

```text
dict_items([('name', 'Masum'), ('age', 22), ('cgpa', 3.95)])
```

এগুলো view object। Dictionary পরিবর্তিত হলে সংশ্লিষ্ট view-তে পরিবর্তন দেখা যেতে পারে।

## 11. Iterating Through a Dictionary

Dictionary-এর key, value অথবা উভয়ই নিয়ে loop চালানো যায়।

### 11.1 Iterating Through Keys

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}

for key in student:
    print(key)
```

Output:

```text
name
age
cgpa
```

সরাসরি Dictionary-এর ওপর loop চালালে key পাওয়া যায়।

### 11.2 Iterating Through Values

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}

for value in student.values():
    print(value)
```

Output:

```text
Masum
22
3.95
```

### 11.3 Iterating Through Key-Value Pairs

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}

for key, value in student.items():
    print(key, ":", value)
```

Output:

```text
name : Masum
age : 22
cgpa : 3.95
```

এখানে `items()` থেকে পাওয়া প্রতিটি pair unpack করে `key` ও `value` variable-এ রাখা হয়েছে।

## 12. Nested Dictionaries

একটি Dictionary-এর মধ্যে আরেকটি Dictionary রাখা হলে তাকে Nested Dictionary বলা হয়।

```python
students = {
    "student1": {
        "name": "Masum",
        "cgpa": 3.95
    },
    "student2": {
        "name": "Ritu",
        "cgpa": 3.90
    }
}

print(students)
```

Nested Dictionary-এর value access করতে একাধিক key ব্যবহার করা যায়।

```python
print(students["student1"]["name"])
print(students["student2"]["cgpa"])
```

Output:

```text
Masum
3.9
```

এখানে প্রথমে বাইরের Dictionary থেকে শিক্ষার্থীর record নেওয়া হয়েছে, তারপর সেই record থেকে নির্দিষ্ট value access করা হয়েছে।

Nested Dictionary ব্যবহার করা হয় structured data সংরক্ষণে, যেমন student records, product details এবং API responses।

## 13. Dictionary Copying

Dictionary mutable হওয়ায় copy করার সময়ও সতর্ক থাকা প্রয়োজন।

### 13.1 Assignment Is Not a Copy

```python
a = {"name": "Masum", "age": 22}
b = a

b["age"] = 23

print(a)
print(b)
```

Output:

```text
{'name': 'Masum', 'age': 23}
{'name': 'Masum', 'age': 23}
```

এখানে `a` ও `b` একই Dictionary object-কে নির্দেশ করছে।

### 13.2 Copy with `copy()`

```python
a = {"name": "Masum", "age": 22}
b = a.copy()

b["age"] = 23

print(a)
print(b)
```

Output:

```text
{'name': 'Masum', 'age': 22}
{'name': 'Masum', 'age': 23}
```

এখানে `b` একটি shallow copy।

**সতর্কতা:** Nested Dictionary বা List-এর মতো mutable value থাকলে shallow copy inner object-গুলোকে আলাদাভাবে copy করে না। Deep copy প্রয়োজন হলে `copy` module-এর `deepcopy()` ব্যবহার করা যায়।

## 14. Useful Dictionary Methods

| Method | Purpose |
|---|---|
| `get(key)` | Key-এর value পাওয়া; না থাকলে default return |
| `keys()` | সব key-এর view |
| `values()` | সব value-এর view |
| `items()` | সব key-value pair-এর view |
| `update()` | Item যোগ বা update করা |
| `pop(key)` | নির্দিষ্ট key-এর item বাদ দেওয়া |
| `popitem()` | শেষ inserted pair বাদ দেওয়া |
| `clear()` | সব item বাদ দেওয়া |
| `copy()` | Shallow copy তৈরি করা |
| `setdefault()` | Key থাকলে তার value, না থাকলে default value সেট করা |
| `fromkeys()` | নির্দিষ্ট key-গুলোর Dictionary তৈরি করা |

### Understanding `setdefault()`

`setdefault()` key-এর value return করে। Key না থাকলে default value দিয়ে নতুন item তৈরি করে।

```python
student = {"name": "Masum"}

result = student.setdefault("age", 22)

print(result)
print(student)
```

Output:

```text
22
{'name': 'Masum', 'age': 22}
```

Key আগে থেকেই থাকলে তার value পরিবর্তন করে না।

```python
student = {"name": "Masum", "age": 22}

result = student.setdefault("age", 25)

print(result)
print(student)
```

Output:

```text
22
{'name': 'Masum', 'age': 22}
```

## 15. Dictionary vs List vs Tuple vs Set

| Feature | List | Tuple | Set | Dictionary |
|---|---|---|---|---|
| Main purpose | Ordered collection | Ordered, immutable collection | Unique items | Key-value pairs |
| Syntax | `[ ]` | `( )` সাধারণত | `{ }` | `{key: value}` |
| Mutable | Yes | No | Yes | Yes |
| Duplicates | Allowed | Allowed | Not among elements | Keys unique |
| Indexing | Yes | Yes | No | Key দিয়ে access |
| Main access method | Index | Index | Membership | Key |

Example:

```python
my_list = [10, 20, 30]
my_tuple = (10, 20, 30)
my_set = {10, 20, 30}
my_dict = {"a": 10, "b": 20}
```

প্রতিটি data type-এর নিজস্ব উদ্দেশ্য রয়েছে। প্রয়োজন অনুযায়ী সঠিক type নির্বাচন করা গুরুত্বপূর্ণ।

## 16. Common Beginner Mistakes

### Mistake 1: Accessing a Missing Key

```python
student = {"name": "Masum"}

print(student["age"])
```

এটি `KeyError` তৈরি করবে।

সমাধান:

```python
print(student.get("age", 0))
```

Output:

```text
0
```

### Mistake 2: Confusing Keys with Values

```python
student = {"name": "Masum", "age": 22}

print("Masum" in student)
```

Output:

```text
False
```

কারণ `"Masum"` value, key নয়।

Value পরীক্ষা করতে:

```python
print("Masum" in student.values())
```

Output:

```text
True
```

### Mistake 3: Using an Unhashable Key

```python
data = {[1, 2]: "Numbers"}
```

এটি `TypeError` তৈরি করবে। Dictionary key হিসেবে hashable object ব্যবহার করতে হবে।

### Mistake 4: Assuming Assignment Creates a Copy

```python
a = {"x": 10}
b = a

b["x"] = 20

print(a)
```

Output:

```text
{'x': 20}
```

আলাদা shallow copy প্রয়োজন হলে `a.copy()` ব্যবহার করো।

### Mistake 5: Confusing `pop()` and `popitem()`

- `pop(key)` নির্দিষ্ট key-এর item বাদ দেয়।
- `popitem()` শেষ inserted key-value pair বাদ দেয়।

### Mistake 6: Modifying Dictionary Size During Iteration

Iteration চলাকালে Dictionary-তে key যোগ বা বাদ দিলে `RuntimeError` হতে পারে।

সমস্যাজনক উদাহরণ:

```python
data = {"a": 1, "b": 2, "c": 3}

for key in data:
    if key == "b":
        del data[key]
```

নিরাপদ পদ্ধতি হলো key-গুলোর একটি List নিয়ে iteration করা।

```python
data = {"a": 1, "b": 2, "c": 3}

for key in list(data.keys()):
    if key == "b":
        del data[key]

print(data)
```

Output:

```text
{'a': 1, 'c': 3}
```

## 17. Practice Exercises

### Exercise 1: Create a Student Dictionary

নিচের তথ্য দিয়ে একটি Dictionary তৈরি করো:

- Name: Masum
- Age: 22
- Department: CSE
- CGPA: 3.95

এরপর প্রতিটি value আলাদাভাবে print করো।

### Exercise 2: Add and Update Items

```python
student = {"name": "Masum", "age": 22}
```

- `"cgpa"` key যোগ করো।
- `"age"` update করো।
- Updated Dictionary print করো।

### Exercise 3: Access with `get()`

```python
student = {"name": "Masum", "age": 22}
```

`"cgpa"` key-এর value `get()` দিয়ে বের করো। Default value হিসেবে `0` ব্যবহার করো।

### Exercise 4: Remove Items

```python
student = {
    "name": "Masum",
    "age": 22,
    "cgpa": 3.95
}
```

`pop()`, `del` এবং `popitem()` ব্যবহার করে item বাদ দেওয়ার পার্থক্য পরীক্ষা করো।

### Exercise 5: Iterate Through a Dictionary

একটি Dictionary তৈরি করে `keys()`, `values()` এবং `items()` ব্যবহার করে loop চালাও।

### Exercise 6: Count Word Frequencies

একটি ছোট Word List থেকে প্রতিটি word কতবার আছে, তা Dictionary দিয়ে গণনা করো।

Example input:

```python
words = ["python", "java", "python", "c", "java", "python"]
```

Expected result:

```text
{'python': 3, 'java': 2, 'c': 1}
```

### Exercise 7: Nested Dictionary

তিনজন শিক্ষার্থীর name ও CGPA দিয়ে Nested Dictionary তৈরি করো। দ্বিতীয় শিক্ষার্থীর CGPA access করো।

### Exercise 8: Dictionary Copy

একটি Dictionary তৈরি করে `b = a` এবং `b = a.copy()`-এর আচরণ তুলনা করো।

### Exercise 9: Student Marks Manager

একটি Dictionary-তে শিক্ষার্থীদের নাম ও marks রাখো। এরপর:

1. একটি নতুন শিক্ষার্থী যোগ করো।
2. একজনের marks update করো।
3. একজন শিক্ষার্থীর marks access করো।
4. সব শিক্ষার্থীর নাম ও marks print করো।
5. সর্বোচ্চ marks বের করো।

### Exercise 10: Mini Project — Course Information

একটি Course Dictionary তৈরি করো, যেখানে থাকবে:

- Course code
- Course name
- Credit
- Instructor
- Student list

এরপর key ব্যবহার করে প্রতিটি তথ্য access করো এবং একটি নতুন তথ্য যোগ করো।

## 18. Key Takeaways

- Dictionary key-value pairs আকারে data সংরক্ষণ করে।
- Dictionary mutable এবং insertion order সংরক্ষণ করে।
- Dictionary-এর key unique ও hashable হতে হয়।
- Value যেকোনো data type-এর হতে পারে।
- `dict[key]` দিয়ে value access করা যায়; key না থাকলে `KeyError` হয়।
- `get()` missing key-এর জন্য default value দিতে পারে।
- Assignment দিয়ে Dictionary copy হয় না; `copy()` shallow copy তৈরি করে।
- `update()` একাধিক item যোগ বা পরিবর্তন করে।
- `pop()`, `popitem()`, `del` ও `clear()` item মুছতে ব্যবহার করা হয়।
- `keys()`, `values()` ও `items()` Dictionary-এর data নিয়ে কাজ করতে সাহায্য করে।
- Nested Dictionary দিয়ে structured data সংরক্ষণ করা যায়।
- `in` operator দিয়ে Dictionary-এর key পরীক্ষা করা হয়; value পরীক্ষা করতে `values()` ব্যবহার করা যায়।

## 19. Next Topic

পরবর্তী ফাইল:

**`18_Bytes_and_Bytearray_Types.md`**

সেখানে Python-এর `bytes` ও `bytearray`, binary data, immutability, encoding এবং decoding-এর প্রাথমিক ধারণা শেখা হবে।