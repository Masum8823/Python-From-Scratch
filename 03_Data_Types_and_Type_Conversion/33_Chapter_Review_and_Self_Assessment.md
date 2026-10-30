# 33. Chapter Review and Self-Assessment

## 1. Chapter Overview

এই Chapter-এ Python-এর Data Types, Type Checking, Type Conversion এবং Type Compatibility সম্পর্কে শেখা হয়েছে।

প্রধান Topics:

1. Introduction to Data Types
2. Built-in Data Types
3. Dynamic Typing
4. Type Checking
5. Numeric Types
6. String, Boolean এবং None
7. List, Tuple, Set এবং Dictionary
8. Bytes এবং Bytearray
9. Type Conversion
10. Mutable and Immutable Objects
11. Type Compatibility and Common Errors
12. Choosing the Right Data Type
13. Data Types Best Practices

## 2. Built-in Data Types: Quick Revision

| Data Type | Example | Main Purpose |
|---|---|---|
| `int` | `100` | পূর্ণসংখ্যা |
| `float` | `3.95` | Decimal Number |
| `complex` | `2 + 3j` | Complex Number |
| `str` | `"Python"` | Text |
| `bool` | `True` | Logical State |
| `NoneType` | `None` | অনুপস্থিত বা নির্ধারিত নয় এমন Value |
| `list` | `[10, 20]` | Ordered, Mutable Collection |
| `tuple` | `(10, 20)` | Ordered, Immutable Sequence |
| `set` | `{10, 20}` | Unique Elements |
| `dict` | `{"name": "Masum"}` | Key-Value Data |
| `bytes` | `b"ABC"` | Immutable Binary Data |
| `bytearray` | `bytearray(b"ABC")` | Mutable Binary Data |
| `frozenset` | `frozenset({1, 2})` | Immutable Set |

**মনে রাখবে:** Empty Set তৈরি করতে `set()` ব্যবহার করতে হয়। `{}` একটি Empty Dictionary তৈরি করে।

## 3. Type Checking

### Using `type()`

কোনো Object-এর Type জানতে ব্যবহার করা হয়।

```python
value = 100

print(type(value))
```

Output:

```text
<class 'int'>
```

### Using `isinstance()`

কোনো Object নির্দিষ্ট Type বা তার Subclass-এর Instance কি না পরীক্ষা করে।

```python
value = 100

print(isinstance(value, int))
```

Output:

```text
True
```

সাধারণ Type Checking-এর জন্য `isinstance()` বেশি উপযোগী।

## 4. Dynamic Typing

Python একটি Dynamically Typed Language। Variable-এর জন্য আগে থেকে নির্দিষ্ট Type ঘোষণা করতে হয় না।

```python
value = 100
print(type(value))

value = "Python"
print(type(value))
```

Output:

```text
<class 'int'>
<class 'str'>
```

এখানে একই Variable Name প্রথমে Integer এবং পরে String Object-কে reference করছে।

**মনে রাখবে:** Python Dynamically Typed হলেও প্রতিটি Object-এর নিজস্ব Type থাকে।

## 5. Type Conversion

Type Conversion-এর মাধ্যমে একটি Value-কে অন্য Data Type-এ রূপান্তর করা হয়।

### Implicit Conversion

কিছু Operation-এ Python স্বয়ংক্রিয়ভাবে Numeric Type promote করে।

```python
result = 10 + 2.5

print(result)
print(type(result))
```

Output:

```text
12.5
<class 'float'>
```

### Explicit Conversion

Programmer নিজে Conversion Function ব্যবহার করে।

```python
number = int("100")
price = float("25.5")
text = str(500)
```

Common Conversion Functions:

| Function | Purpose |
|---|---|
| `int()` | Integer-এ Convert |
| `float()` | Float-এ Convert |
| `str()` | String-এ Convert |
| `bool()` | Boolean-এ Convert |
| `list()` | List তৈরি |
| `tuple()` | Tuple তৈরি |
| `set()` | Set তৈরি |
| `dict()` | Dictionary তৈরি |

সব Conversion সফল হয় না। Invalid Conversion হলে Error হতে পারে।

## 6. Mutable vs Immutable

| Mutable | Immutable |
|---|---|
| `list` | `int` |
| `dict` | `float` |
| `set` | `complex` |
| `bytearray` | `bool` |
| | `str` |
| | `bytes` |
| | `frozenset` |
| | `NoneType` |

Tuple-এর Element Reference পরিবর্তন করা যায় না। তবে Tuple-এর ভিতরে Mutable Object থাকলে সেই Object পরিবর্তন করা সম্ভব।

Example:

```python
a = [10, 20]
b = a

b.append(30)

print(a)
```

Output:

```text
[10, 20, 30]
```

`a` এবং `b` একই List Object-কে reference করছে।

## 7. `is` vs `==`

এই দুটি Operator-এর কাজ আলাদা।

- `==` → Value Equality পরীক্ষা করে।
- `is` → Object Identity পরীক্ষা করে।

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a == b)
print(a is b)
```

Output:

```text
True
False
```

দুটি List-এর Content সমান, কিন্তু তারা আলাদা Object।

`None` পরীক্ষা করার সময় সাধারণত `is None` ব্যবহার করা হয়।

## 8. Shallow Copy vs Deep Copy

### Shallow Copy

Outer Collection নতুন তৈরি হয়, কিন্তু Nested Object Shared থাকতে পারে।

```python
original = [[1, 2], [3, 4]]
copied = original.copy()

copied[0][0] = 100

print(original)
```

Output:

```text
[[100, 2], [3, 4]]
```

### Deep Copy

Nested Object-সহ Copy করার চেষ্টা করে।

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

## 9. Choosing the Right Data Type

| Requirement | Suitable Type |
|---|---|
| Text | `str` |
| Whole-number count | `int` |
| Decimal measurement | `float` |
| Precise decimal financial calculation | `decimal.Decimal` |
| True/False state | `bool` |
| Ordered, changeable collection | `list` |
| Fixed sequence | `tuple` |
| Unique values | `set` |
| Key-Value information | `dict` |
| Missing value | `None` |
| Immutable binary data | `bytes` |
| Mutable binary data | `bytearray` |

Data Type নির্বাচন করার সময় Data-এর Nature, প্রয়োজনীয় Operation, Mutability এবং Precision বিবেচনা করতে হবে।

## 10. Common Errors

| Error | Common Cause |
|---|---|
| `TypeError` | Operation-এর জন্য উপযুক্ত Type না থাকা |
| `ValueError` | Type গ্রহণযোগ্য, কিন্তু Value অবৈধ |
| `IndexError` | Sequence-এর বাইরে Index Access |
| `KeyError` | Dictionary-তে অনুপস্থিত Key Access |
| `AttributeError` | নেই এমন Attribute বা Method ব্যবহার |
| `ZeroDivisionError` | শূন্য দিয়ে Division |
| `OverflowError` | কোনো Operation-এর Result Represent করা সম্ভব না হওয়া |

Example:

```python
try:
    number = int("hello")
except ValueError:
    print("Invalid integer value.")
```

Output:

```text
Invalid integer value.
```

Error Handling-এর সময় সম্ভব হলে নির্দিষ্ট Exception ধরো।

## 11. Quick Revision: Important Rules

1. `input()` সবসময় String Return করে।
2. `type()` Object-এর Type জানায়।
3. `isinstance()` Type Checking-এর জন্য উপযোগী।
4. `int("123")` সফল হলেও `int("hello")`-তে `ValueError` হয়।
5. `bool("False")` হলো `True`, কারণ এটি Empty String নয়।
6. Empty List, Empty Dictionary এবং Empty Set হলো Falsy।
7. `[]` হলো Empty List, কিন্তু `{}` হলো Empty Dictionary।
8. `set()` দিয়ে Empty Set তৈরি করা হয়।
9. List Mutable, String Immutable।
10. `b = a` সাধারণত Object Copy করে না।
11. `a.copy()` Shallow Copy তৈরি করে।
12. `copy.deepcopy(a)` Nested Objects-সহ Copy করার চেষ্টা করে।
13. `==` Value তুলনা করে, `is` Identity তুলনা করে।
14. `None` পরীক্ষা করতে `is None` ব্যবহার করা হয়।
15. Tuple-এর ভিতরে Mutable Object থাকলে সেটি পরিবর্তন করা যেতে পারে।
16. Float-এর Binary Representation-এর কারণে কিছু Decimal Calculation-এ Approximation দেখা যায়।
17. `Decimal` ব্যবহার করলে Financial Precision-এর প্রয়োজন অনুযায়ী Calculation আরও নিয়ন্ত্রণ করা যায়।
18. Type Hints নিজে থেকে সাধারণ Python Runtime-এ Type Enforce করে না।

---

## 12. Self-Assessment Quiz

প্রথমে নিজে উত্তর দাও। এরপর নিচের Answer Key খুলে মিলিয়ে দেখো।

### Question 1

`type(10.5)` কী Return করবে?

A. `int`

B. `float`

C. `str`

D. `bool`

### Question 2

কোনটি Mutable Data Type?

A. `str`

B. `int`

C. `list`

D. `tuple`

### Question 3

`bool("False")`-এর Result কী?

A. `True`

B. `False`

### Question 4

Empty Set তৈরি করার সঠিক উপায় কোনটি?

A. `{}`

B. `[]`

C. `()`

D. `set()`

### Question 5

`"10" + "20"`-এর Result কী?

A. `30`

B. `"1020"`

C. `TypeError`

D. `ValueError`

### Question 6

`int("hello")` করলে সাধারণত কী Error হবে?

A. `TypeError`

B. `ValueError`

C. `KeyError`

D. `IndexError`

### Question 7

`is` Operator কী পরীক্ষা করে?

A. Value Equality

B. Object Identity

### Question 8

List-এর Shallow Copy তৈরি করার একটি উপায় কোনটি?

A. `a.copy()`

B. `a = a`

C. `type(a)`

D. `str(a)`

### Question 9

কোন Data Type Key-Value Data সংরক্ষণ করে?

A. `list`

B. `set`

C. `dict`

D. `str`

### Question 10

`input()` Function-এর Return Type কী?

A. `int`

B. `float`

C. `str`

D. User যা লিখবে, সরাসরি সেই Value-এর Type

### Answer Key

{@body const [showAnswers,setShowAnswers] = DIL.useState(false)}
<button block onClick={() => setShowAnswers(!showAnswers)}>{showAnswers ? "Hide Answer Key" : "Show Answer Key"}</button>
{#if showAnswers}
| Question | Answer | Explanation |
|---|---|---|
| 1 | B — `float` | Decimal Number |
| 2 | C — `list` | List Mutable |
| 3 | A — `True` | Non-empty String Truthy |
| 4 | D — `set()` | `{}` Empty Dictionary |
| 5 | B — `"1020"` | String Concatenation |
| 6 | B — `ValueError` | Invalid Integer Representation |
| 7 | B — Object Identity | একই Object কি না |
| 8 | A — `a.copy()` | Shallow Copy |
| 9 | C — `dict` | Key-Value Collection |
| 10 | C — `str` | `input()` String Return করে |
{/if}

## 13. Final Practical Challenge

একটি Student Record তৈরি করো এবং নিচের সব Requirement পূরণ করো।

```python
student = {
    "name": "Masum",
    "student_id": "2026001",
    "age": 22,
    "cgpa": 3.95,
    "is_enrolled": True,
    "courses": ["Python", "AI", "MIS"]
}
```

Requirements:

1. প্রতিটি Value-এর Data Type পরীক্ষা করো।
2. Age এবং CGPA-এর Type Validate করো।
3. Age Negative হলে Error দেখাও।
4. CGPA `0` থেকে `4.0`-এর বাইরে হলে Error দেখাও।
5. Course List-এ একটি নতুন Course যোগ করো।
6. Course Count বের করো।
7. Student Dictionary-এর Shallow Copy তৈরি করো।
8. Copy-এর ভিতরের Course List পরিবর্তন করলে Original-এ কী ঘটে, পরীক্ষা করো।
9. প্রয়োজন হলে Deep Copy ব্যবহার করে Independent Copy তৈরি করো।
10. পুরো Student Record পরিষ্কারভাবে Print করো।

**Challenge Complete হলে:** নিজের Code-এ Type Checking, Type Conversion, Collection Operations এবং Error Handling—সবগুলো বিষয় একসঙ্গে ব্যবহার করতে পারবে।

## 14. Chapter Completion Checklist

- [ ] Built-in Data Types বুঝতে পারি।
- [ ] `type()` এবং `isinstance()` ব্যবহার করতে পারি।
- [ ] Numeric Types-এর পার্থক্য বুঝি।
- [ ] String, Boolean এবং None ব্যবহার করতে পারি।
- [ ] List, Tuple, Set ও Dictionary-এর পার্থক্য বুঝি।
- [ ] Implicit এবং Explicit Type Conversion বুঝি।
- [ ] Conversion Error Handle করতে পারি।
- [ ] Mutable ও Immutable Object বুঝি।
- [ ] Object Identity এবং Value Equality-এর পার্থক্য বুঝি।
- [ ] Shallow Copy এবং Deep Copy বুঝি।
- [ ] Type Compatibility Error সমাধান করতে পারি।
- [ ] Problem অনুযায়ী সঠিক Data Type নির্বাচন করতে পারি।
- [ ] নিজের ছোট Program-এ এসব Concept ব্যবহার করতে পারি।

সবগুলো বিষয় আত্মবিশ্বাসের সঙ্গে করতে পারলে Chapter 03-এর প্রধান Learning Objectives পূরণ হয়েছে। তবে Chapter সম্পূর্ণ ঘোষণা করার আগে List ও Tuple-এর বিস্তারিত Notes এবং Folder Structure-এর সঙ্গে সব File মিলিয়ে যাচাই করে নেবে।

## 15. Next Chapter

**Chapter 04 — Operators in Python**

পরবর্তী Chapter-এ শেখা হবে:

- Arithmetic Operators
- Comparison Operators
- Assignment Operators
- Logical Operators
- Identity Operators
- Membership Operators
- Bitwise Operators
- Operator Precedence and Associativity
- Practical Exercises

এই Chapter-এর ভিত্তি ভালোভাবে আয়ত্ত করলে Operators-এর কাজ বোঝা আরও সহজ হবে।