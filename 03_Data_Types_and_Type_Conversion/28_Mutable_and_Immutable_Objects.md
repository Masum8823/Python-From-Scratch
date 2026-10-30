# 28. Mutable and Immutable Objects in Python

## 1. Introduction to Mutable and Immutable Objects

Python-এ প্রতিটি value একটি object-এর সঙ্গে সম্পর্কিত। কোনো object তৈরি হওয়ার পর তার internal value পরিবর্তন করা যায় কি না, তার ওপর ভিত্তি করে object-কে প্রধানত দুই ভাগে ভাগ করা হয়।

**Mutable Object:** যে object তৈরি হওয়ার পর তার content পরিবর্তন করা যায়।

**Immutable Object:** যে object তৈরি হওয়ার পর তার content পরিবর্তন করা যায় না।

Examples:

```python
# Mutable object
numbers = [10, 20, 30]
numbers[0] = 100

print(numbers)

# Immutable object
text = "Python"
# text[0] = "J"  # TypeError
```

Output:

```text
[100, 20, 30]
```

এখানে List-এর element পরিবর্তন করা গেছে। কিন্তু String-এর নির্দিষ্ট character সরাসরি পরিবর্তন করা যায় না।

**মনে রাখবে:** Immutable object-এর value পরিবর্তন করা যায় না মানে variable-টিকে নতুন value assign করা যাবে না—এমন নয়।

## 2. Mutable Objects in Python

Mutable object-এর content তৈরি হওয়ার পরে পরিবর্তন করা যায়। সাধারণত একই object-এর মধ্যে পরিবর্তন ঘটে।

Python-এর গুরুত্বপূর্ণ mutable types:

- `list`
- `dict`
- `set`
- `bytearray`

Example:

```python
numbers = [10, 20, 30]

numbers.append(40)
numbers[0] = 100

print(numbers)
```

Output:

```text
[100, 20, 30, 40]
```

এখানে List-এর element পরিবর্তন ও নতুন element যোগ করা হয়েছে।

### 2.1 Mutable Dictionary

```python
student = {
    "name": "Masum",
    "age": 22
}

student["age"] = 23
student["department"] = "CSE"

print(student)
```

Output:

```text
{'name': 'Masum', 'age': 23, 'department': 'CSE'}
```

Dictionary-এর value পরিবর্তন করা এবং নতুন key-value pair যোগ করা যায়।

### 2.2 Mutable Set

```python
numbers = {10, 20, 30}

numbers.add(40)
numbers.remove(20)

print(numbers)
```

Output-এ `10`, `30` ও `40` থাকবে। Set-এর element order নির্দিষ্ট নয়।

## 3. Immutable Objects in Python

Immutable object-এর তৈরি হয়ে যাওয়া value সরাসরি পরিবর্তন করা যায় না। নতুন value প্রয়োজন হলে সাধারণত নতুন object তৈরি হয় অথবা অন্য কোনো existing object reference করা হয়।

Python-এর গুরুত্বপূর্ণ immutable types:

- `int`
- `float`
- `complex`
- `bool`
- `str`
- `tuple`
- `bytes`
- `frozenset`

`None`-ও একটি immutable singleton object।

Example:

```python
number = 10

number = number + 5

print(number)
```

Output:

```text
15
```

এখানে `10` Integer object-কে পরিবর্তন করা হয়নি। Expression `number + 5` একটি নতুন Integer value তৈরি করেছে, এরপর `number` variable সেই value-কে reference করছে।

### 3.1 Immutable String

```python
text = "Python"

# text[0] = "J"  # TypeError

text = "Jython"

print(text)
```

Output:

```text
Jython
```

এখানে String-এর character সরাসরি পরিবর্তন করা হয়নি। `text`-কে নতুন String assign করা হয়েছে।

### 3.2 Immutable Tuple

```python
data = (10, 20, 30)

# data[0] = 100  # TypeError
```

Tuple-এর element সরাসরি পরিবর্তন করা যায় না।

তবে Tuple-এর মধ্যে Mutable object থাকলে সেই nested object পরিবর্তন করা সম্ভব। বিষয়টি পরে ব্যাখ্যা করা হয়েছে।

## 4. Variable and Object: The Basic Difference

Python-এ variable-কে object-এর জন্য একটি name বা reference হিসেবে বোঝা সুবিধাজনক।

Example:

```python
a = [10, 20, 30]
b = a

print(a)
print(b)
```

Output:

```text
[10, 20, 30]
[10, 20, 30]
```

এখানে `a` ও `b` একই List object-কে reference করছে।

তাই `b` দিয়ে List পরিবর্তন করলে `a` দিয়েও পরিবর্তনটি দেখা যাবে।

```python
a = [10, 20, 30]
b = a

b[0] = 100

print(a)
print(b)
```

Output:

```text
[100, 20, 30]
[100, 20, 30]
```

কারণ এখানে দুটি আলাদা List তৈরি হয়নি। দুটি name একই Mutable object-এর সঙ্গে যুক্ত।

## 5. Object Identity: `id()` and `is`

Python-এ object identity পরীক্ষা করতে `is` operator ব্যবহার করা যায়। `id()` function object-এর identity প্রকাশ করে।

### 5.1 Using `is`

```python
a = [1, 2, 3]
b = a
c = [1, 2, 3]

print(a is b)
print(a is c)
print(a == c)
```

Output:

```text
True
False
True
```

ব্যাখ্যা:

- `a is b` → একই object।
- `a is c` → আলাদা object।
- `a == c` → content সমান।

**গুরুত্বপূর্ণ পার্থক্য:**

- `is` পরীক্ষা করে দুটি reference একই object নির্দেশ করছে কি না।
- `==` পরীক্ষা করে দুটি value সমান কি না।

### 5.2 Using `id()`

```python
a = [1, 2, 3]
b = a
c = [1, 2, 3]

print(id(a) == id(b))
print(id(a) == id(c))
```

Output:

```text
True
False
```

সাধারণভাবে, object জীবিত থাকা অবস্থায় তার identity স্থিতিশীল থাকে। `id()`-এর নির্দিষ্ট সংখ্যাটি Python implementation ও execution অনুযায়ী ভিন্ন হতে পারে।

সাধারণ value comparison-এর জন্য `id()` প্রয়োজন হয় না; `is` এবং `==`-এর পার্থক্য বোঝাই বেশি গুরুত্বপূর্ণ।

## 6. Reassignment Does Not Always Mean Mutation

কোনো variable-এ নতুন value assign করা এবং existing object mutate করা দুটি আলাদা বিষয়।

### 6.1 Reassigning a Variable

```python
a = [10, 20]
b = a

a = [100, 200]

print(a)
print(b)
```

Output:

```text
[100, 200]
[10, 20]
```

এখানে `a`-কে নতুন List assign করা হয়েছে। `b` এখনও আগের List-কে reference করছে।

### 6.2 Mutating an Object

```python
a = [10, 20]
b = a

a.append(30)

print(a)
print(b)
```

Output:

```text
[10, 20, 30]
[10, 20, 30]
```

এখানে নতুন List assign করা হয়নি। Existing List object পরিবর্তিত হয়েছে।

**মনে রাখবে:**

- Reassignment: variable অন্য object-কে reference করতে পারে।
- Mutation: Mutable object-এর content পরিবর্তিত হয়।

## 7. Mutable and Immutable Types: Comparison Table

| Feature | Mutable Object | Immutable Object |
|---|---|---|
| Content পরিবর্তন | সম্ভব | সরাসরি সম্ভব নয় |
| Existing object mutate | সম্ভব | সম্ভব নয় |
| Example | `list`, `dict`, `set` | `int`, `str`, `tuple`, `bytes` |
| Multiple references | একই পরিবর্তন দেখতে পারে | একই object reference করলেও value mutate হয় না |
| Common operation | `append()`, key update, `add()` | নতুন value তৈরি বা assign |

এই পার্থক্য বোঝা Python-এ unexpected result এবং debugging-এর সমস্যা কমায়।

## 8. Shallow Copy

Mutable collection copy করার সময় একটি গুরুত্বপূর্ণ বিষয় হলো **Shallow Copy**।

Shallow copy একটি নতুন outer object তৈরি করে, কিন্তু nested objects-গুলোকে সাধারণত copy না করে reference হিসেবে ভাগ করে।

Example:

```python
original = [10, 20, 30]
copied = original.copy()

copied[0] = 100

print(original)
print(copied)
```

Output:

```text
[10, 20, 30]
[100, 20, 30]
```

এখানে `copied` একটি নতুন List। তাই outer List-এর element পরিবর্তন করলে `original` পরিবর্তিত হয় না।

তবে nested object থাকলে আচরণ ভিন্ন হতে পারে।

```python
original = [[1, 2], [3, 4]]
copied = original.copy()

copied[0][0] = 100

print(original)
print(copied)
```

Output:

```text
[[100, 2], [3, 4]]
[[100, 2], [3, 4]]
```

এখানে outer List আলাদা হলেও inner List-গুলো shared। তাই nested element পরিবর্তন করলে দুটি List-এই পরিবর্তন দেখা যায়।

## 9. Deep Copy

Nested objects-সহ independent copy প্রয়োজন হলে `copy.deepcopy()` ব্যবহার করা যায়।

Example:

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

এখানে nested List-ও copy করা হয়েছে।

**মনে রাখবে:**

- Shallow copy: outer container নতুন, nested objects shared থাকতে পারে।
- Deep copy: nested objects-সহ copy করার চেষ্টা করে।

সব object-এর ক্ষেত্রে deep copy একইভাবে সম্ভব বা উপযুক্ত নয়। Custom objects ও external resources-এর ক্ষেত্রে বিশেষ বিবেচনা প্রয়োজন হতে পারে।

## 10. Mutable Objects Inside an Immutable Tuple

Tuple immutable হলেও এর মধ্যে Mutable object রাখা যায়।

Example:

```python
data = ([1, 2], [3, 4])

data[0].append(5)

print(data)
```

Output:

```text
([1, 2, 5], [3, 4])
```

এখানে Tuple-এর structure পরিবর্তন করা হয়নি। Tuple-এর প্রথম element যে List-কে reference করে, সেই List পরিবর্তিত হয়েছে।

কিন্তু Tuple-এর element-কে সরাসরি অন্য object দিয়ে replace করা যাবে না।

```python
data = ([1, 2], [3, 4])

# data[0] = [100, 200]  # TypeError
```

**মূল ধারণা:** Tuple-এর reference structure immutable, কিন্তু এর মধ্যে থাকা Mutable object নিজে পরিবর্তনযোগ্য হতে পারে।

## 11. Mutable Objects as Function Arguments

Python-এ function-এ object pass করলে function সেই object-এর reference পেতে পারে। তাই Mutable object পরিবর্তন করলে caller সেই পরিবর্তন দেখতে পারে।

Example:

```python
def add_item(items):
    items.append(40)

numbers = [10, 20, 30]

add_item(numbers)

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

Function-এর মধ্যে একই List object পরিবর্তন করা হয়েছে।

### 11.1 Reassigning the Parameter

```python
def replace_list(items):
    items = [100, 200, 300]

numbers = [10, 20, 30]

replace_list(numbers)

print(numbers)
```

Output:

```text
[10, 20, 30]
```

এখানে function-এর `items` parameter-কে নতুন List assign করা হয়েছে। কিন্তু caller-এর `numbers` variable এখনও আগের List-কে reference করছে।

**মনে রাখবে:** Function-এর ভিতরে Mutable object mutate করা এবং parameter-কে নতুন object assign করা এক বিষয় নয়।

## 12. Mutable Default Argument Problem

Function-এর default argument হিসেবে Mutable object ব্যবহার করলে একই object একাধিক function call-এ পুনরায় ব্যবহার হতে পারে।

Example:

```python
def add_item(item, items=[]):
    items.append(item)
    return items

print(add_item("Pen"))
print(add_item("Book"))
print(add_item("Notebook"))
```

Output:

```text
['Pen']
['Pen', 'Book']
['Pen', 'Book', 'Notebook']
```

অনেক সময় এটি প্রত্যাশিত আচরণ নয়। কারণ default List-টি প্রতিটি function call-এ নতুন করে তৈরি হয় না।

### Correct Approach

```python
def add_item(item, items=None):
    if items is None:
        items = []

    items.append(item)
    return items

print(add_item("Pen"))
print(add_item("Book"))
```

Output:

```text
['Pen']
['Book']
```

এখানে প্রতিবার argument না দিলে নতুন List তৈরি হয়।

## 13. Why Immutable Objects Are Useful

Immutable object-এর কিছু গুরুত্বপূর্ণ সুবিধা রয়েছে।

1. **Predictability:** Object-এর value অনিচ্ছাকৃতভাবে পরিবর্তিত হয় না।
2. **Safer sharing:** একই immutable object একাধিক reference থেকে ব্যবহার করলেও mutation নিয়ে চিন্তা করতে হয় না।
3. **Dictionary keys and Set elements:** Hashable immutable objects key বা Set element হিসেবে ব্যবহার করা যায়।
4. **Simpler reasoning:** Value পরিবর্তন করতে নতুন object বা নতুন assignment প্রয়োজন হয়।

তবে সব Immutable object hashable—এমন নয়। উদাহরণস্বরূপ, Tuple-এর মধ্যে unhashable List থাকলে সেই Tuple-ও hashable হবে না।

Example:

```python
point = (10, 20)

locations = {
    point: "Campus"
}

print(locations[point])
```

Output:

```text
Campus
```

এখানে Tuple-টি hashable হওয়ায় Dictionary key হিসেবে ব্যবহার করা গেছে।

কিন্তু:

```python
data = ([10, 20],)

# locations = {data: "Example"}  # TypeError
```

এই Tuple-এর মধ্যে List থাকায় Tuple-টি hashable নয়।

## 14. Common Mistakes

### 14.1 Using `is` Instead of `==`

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a is b)
print(a == b)
```

Output:

```text
False
True
```

Value comparison করতে `==` ব্যবহার করো। একই object কি না পরীক্ষা করতে `is` ব্যবহার করো।

### 14.2 Assuming Assignment Creates a Copy

```python
a = [1, 2, 3]
b = a

b.append(4)

print(a)
```

Output:

```text
[1, 2, 3, 4]
```

`b = a` নতুন List তৈরি করেনি। এটি একই List-এর আরেকটি reference তৈরি করেছে।

### 14.3 Assuming Every Tuple Is Fully Immutable

Tuple-এর element reference পরিবর্তন করা যায় না, কিন্তু এর মধ্যে থাকা Mutable object পরিবর্তন করা সম্ভব।

```python
data = ([1, 2],)

data[0].append(3)

print(data)
```

Output:

```text
([1, 2, 3],)
```

### 14.4 Confusing Shallow Copy with Deep Copy

```python
original = [[1, 2]]
copied = original.copy()

copied[0].append(3)

print(original)
```

Output:

```text
[[1, 2, 3]]
```

Nested List shared থাকার কারণে original-ও পরিবর্তিত হয়েছে।

### 14.5 Modifying a List While Iterating

একই List-এর মধ্যে iteration করার সময় element সরানো বা যোগ করলে unexpected result হতে পারে।

```python
numbers = [1, 2, 3, 4, 5]

for number in numbers:
    if number % 2 == 0:
        numbers.remove(number)

print(numbers)
```

এই ধরনের code-এ element skip হওয়ার মতো অপ্রত্যাশিত আচরণ হতে পারে।

আরও নিরাপদ পদ্ধতি হলো নতুন List তৈরি করা:

```python
numbers = [1, 2, 3, 4, 5]

numbers = [
    number for number in numbers
    if number % 2 != 0
]

print(numbers)
```

Output:

```text
[1, 3, 5]
```

## 15. Practical Examples

### Example 1: Shared List Reference

```python
first = ["Python", "Java"]
second = first

second.append("C++")

print(first)
print(second)
```

Output:

```text
['Python', 'Java', 'C++']
['Python', 'Java', 'C++']
```

### Example 2: Independent List Copy

```python
first = ["Python", "Java"]
second = first.copy()

second.append("C++")

print(first)
print(second)
```

Output:

```text
['Python', 'Java']
['Python', 'Java', 'C++']
```

### Example 3: Immutable String Reassignment

```python
first = "Hello"
second = first

first = first + " Python"

print(first)
print(second)
```

Output:

```text
Hello Python
Hello
```

এখানে নতুন String তৈরি হয়েছে এবং শুধু `first`-কে সেটি assign করা হয়েছে।

### Example 4: Function Mutating a Dictionary

```python
def update_student(student):
    student["cgpa"] = 3.95

data = {"name": "Masum"}

update_student(data)

print(data)
```

Output:

```text
{'name': 'Masum', 'cgpa': 3.95}
```

Function-এর মধ্যে একই Dictionary object পরিবর্তন হয়েছে।

## 16. Practice Exercises

### Exercise 1: Mutable or Immutable?

নিচের type-গুলোকে Mutable অথবা Immutable হিসেবে চিহ্নিত করো:

- `int`
- `float`
- `str`
- `list`
- `tuple`
- `dict`
- `set`
- `bytes`
- `bytearray`
- `frozenset`

### Exercise 2: Reference Sharing

Output অনুমান করো:

```python
a = [10, 20]
b = a

b.append(30)

print(a)
print(b)
print(a is b)
```

### Exercise 3: Reassignment vs Mutation

Output অনুমান করো:

```python
a = [1, 2, 3]
b = a

a = [4, 5, 6]

print(a)
print(b)
```

### Exercise 4: Shallow Copy

Output অনুমান করো:

```python
original = [[1, 2], [3, 4]]
copied = original.copy()

copied[0][0] = 100

print(original)
print(copied)
```

### Exercise 5: Deep Copy

উপরের Exercise-টি `copy.deepcopy()` ব্যবহার করে আবার লেখো। Output-এর পার্থক্য ব্যাখ্যা করো।

### Exercise 6: Tuple with a List

Output অনুমান করো:

```python
data = ([1, 2], [3, 4])

data[0].append(5)

print(data)
```

কেন Tuple-এর ভিতরের List পরিবর্তন করা গেল, ব্যাখ্যা করো।

### Exercise 7: Mutable Default Argument

নিচের code-এ সমস্যা চিহ্নিত করো এবং সঠিকভাবে লেখো:

```python
def collect(value, data=[]):
    data.append(value)
    return data
```

### Exercise 8: Mini Project — Student Record Copy

একটি Student Dictionary তৈরি করো, যেখানে nested List হিসেবে courses থাকবে।

তারপর:

1. একটি shallow copy তৈরি করো।
2. একটি deep copy তৈরি করো।
3. দুই copy-এর nested List পরিবর্তন করো।
4. Original object-এ কী পরিবর্তন হয়, তা পরীক্ষা করো।

## 17. Key Takeaways

- Mutable object-এর content পরিবর্তন করা যায়; Immutable object-এর content সরাসরি পরিবর্তন করা যায় না।
- `list`, `dict`, `set` এবং `bytearray` Mutable।
- `int`, `float`, `bool`, `str`, `bytes` এবং সাধারণ Tuple Immutable।
- Variable assignment সাধারণত নতুন object copy করে না; reference তৈরি বা পরিবর্তন করে।
- `is` object identity পরীক্ষা করে; `==` value equality পরীক্ষা করে।
- Shallow copy nested objects shared রাখতে পারে।
- Deep copy nested objects-সহ copy করার চেষ্টা করে।
- Function-এর ভিতরে Mutable argument পরিবর্তন করলে caller সেই পরিবর্তন দেখতে পারে।
- Mutable default argument অপ্রত্যাশিত ফল তৈরি করতে পারে; প্রয়োজন হলে `None` ব্যবহার করে নতুন object তৈরি করো।
- Tuple-এর মধ্যে Mutable object থাকলে সেই object পরিবর্তন করা সম্ভব।

## 18. Next Topic

পরবর্তী ফাইল:

**`29_Type_Compatibility_and_Common_Errors.md`**

সেখানে বিভিন্ন data type একসঙ্গে ব্যবহার করার নিয়ম, compatible ও incompatible operations, type-related errors এবং সেগুলো সমাধানের উপায় শেখা হবে।