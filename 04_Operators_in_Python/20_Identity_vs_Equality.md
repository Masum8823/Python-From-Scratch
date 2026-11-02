# 20. Identity vs Equality in Python

## 1. Introduction

Python-এ দুটি object-এর মধ্যে তুলনা করার জন্য `==` এবং `is` ব্যবহার করা যায়। কিন্তু এদের কাজ এক নয়।

- `==` (Equality Operator): দুটি object-এর **value সমান কি না** পরীক্ষা করে।
- `is` (Identity Operator): দুটি variable **একই object-কে নির্দেশ করছে কি না** পরীক্ষা করে।

সহজভাবে মনে রাখো:

> `==` checks value, while `is` checks identity.

## 2. Equality Operator (`==`)

`==` অপারেটর দুটি object-এর value তুলনা করে। তাদের value সমান হলে সাধারণত `True` return করে।

### Example

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a == b)
```

**Output:**

```text
True
```

### Explanation

এখানে `a` এবং `b`-এর list-এর value একই:

- `a`-এর value: `[1, 2, 3]`
- `b`-এর value: `[1, 2, 3]`

তাই `a == b` এর ফলাফল `True`।

মনে রাখবে, value একই হলেও দুটি আলাদা object হতে পারে।

## 3. Identity Operator (`is`)

`is` অপারেটর পরীক্ষা করে দুটি variable একই object-কে নির্দেশ করছে কি না।

### Example

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a is b)
```

**Output:**

```text
False
```

### Explanation

দুটি list-এর value একই হলেও Python এখানে দুটি আলাদা list object তৈরি করেছে।

তাই `a` এবং `b` একই object নয়। এজন্য `a is b` এর ফলাফল `False`।

## 4. `==` vs `is`: Main Difference

| বিষয় | `==` | `is` |
|---|---|---|
| নাম | Equality Operator | Identity Operator |
| কী পরীক্ষা করে? | Value equality | Object identity |
| একই value, আলাদা object | সাধারণত `True` | `False` |
| একই object | সাধারণত `True` | `True` |
| প্রধান ব্যবহার | Value তুলনা করা | একই object কি না পরীক্ষা করা |

## 5. When Both Operators Return `True`

যখন দুটি variable একই object-কে নির্দেশ করে, তখন সাধারণত `==` এবং `is` দুটোই `True` হয়।

### Example

```python
a = [10, 20, 30]
b = a

print(a == b)
print(a is b)
```

**Output:**

```text
True
True
```

### Explanation

এখানে `b = a` লিখে নতুন list তৈরি করা হয়নি। বরং `b`-কে `a` যে object-কে নির্দেশ করছে, সেই একই object-এর reference দেওয়া হয়েছে।

তাই:

- `a == b` → value একই, তাই `True`
- `a is b` → object একই, তাই `True`

## 6. Understanding Object References

Python-এ variable-কে object-এর সঙ্গে যুক্ত একটি নাম হিসেবে ভাবতে পারো।

```python
a = [1, 2]
b = a
c = [1, 2]

print(a is b)
print(a is c)
print(a == c)
```

**Output:**

```text
True
False
True
```

এখানে:

- `a` এবং `b` একই list object-কে নির্দেশ করে।
- `c` একটি আলাদা list object, যার value একই।
- তাই `a is b` হলো `True`, কিন্তু `a is c` হলো `False`।
- `a == c` হলো `True`, কারণ list দুটির value একই।

## 7. Mutable Objects and Identity

Mutable object হলো এমন object, যার content পরিবর্তন করা যায়। যেমন: `list`, `dict` এবং `set`।

একটি গুরুত্বপূর্ণ বিষয় হলো, একই mutable object-এর reference একাধিক variable-এ থাকলে এক variable দিয়ে পরিবর্তন করলে অন্য variable দিয়েও পরিবর্তনটি দেখা যাবে।

### Example

```python
a = [10, 20]
b = a

b.append(30)

print(a)
print(b)
print(a is b)
```

**Output:**

```text
[10, 20, 30]
[10, 20, 30]
True
```

### Explanation

`b = a` হওয়ার কারণে `a` ও `b` একই list object-কে নির্দেশ করছে। তাই `b` দিয়ে নতুন item যোগ করলে `a`-তেও পরিবর্তনটি দেখা যায়।

### আলাদা Copy তৈরি করলে

```python
a = [10, 20]
b = a.copy()

b.append(30)

print(a)
print(b)
print(a == b)
print(a is b)
```

**Output:**

```text
[10, 20]
[10, 20, 30]
False
False
```

এখানে `a.copy()` একটি নতুন list তৈরি করেছে। তাই `b` পরিবর্তন করলেও `a` পরিবর্তিত হয়নি।

**Note:** `.copy()` সাধারণত shallow copy তৈরি করে। Nested object থাকলে ভেতরের object-গুলো shared থাকতে পারে।

## 8. Why Should We Avoid `is` for Value Comparison?

কখনো কখনো integer বা string-এর ক্ষেত্রে `is` ব্যবহার করলেও `True` দেখা যেতে পারে। এর কারণ Python কিছু object reuse বা cache করতে পারে।

### Example

```python
a = 100
b = 100

print(a == b)
print(a is b)
```

এখানে `a == b` অবশ্যই `True` হবে। `a is b`-ও কোনো Python environment-এ `True` হতে পারে, কিন্তু এই আচরণের ওপর নির্ভর করা উচিত নয়।

**সঠিক নিয়ম:**

```python
a = "Python"
b = "Python"

print(a == b)  # Value comparison
```

Value তুলনা করার জন্য `==` ব্যবহার করবে, `is` নয়।

## 9. Special Use of `is None`

Python-এ `None` বোঝায় কোনো value নেই বা অনুপস্থিত।

কোনো variable-এর value `None` কি না পরীক্ষা করার recommended উপায় হলো `is None`।

### Example

```python
result = None

if result is None:
    print("No result available")
```

**Output:**

```text
No result available
```

`None` নয় কি না পরীক্ষা করতে:

```python
if result is not None:
    print("Result is available")
```

এখানে `is not` হলো identity check-এর বিপরীত।

## 10. Equality Can Be Customized

Python-এর অনেক built-in object-এ `==` value তুলনা করে। তবে custom class-এর ক্ষেত্রে `==`-এর আচরণ `__eq__()` method দিয়ে নির্ধারণ করা যেতে পারে।

অন্যদিকে, `is` পরীক্ষা করে object identity; এটি custom equality method-এর ওপর নির্ভর করে না।

তাই `==` এবং `is` সব ক্ষেত্রে একই অর্থ বহন করে না।

## 11. Common Mistakes

### Mistake 1: Value তুলনা করতে `is` ব্যবহার করা

```python
a = [1, 2]
b = [1, 2]

print(a is b)
```

Output `False`, কারণ list দুটি আলাদা object।

Value তুলনা করতে লিখবে:

```python
print(a == b)
```

### Mistake 2: `b = a`-কে copy মনে করা

```python
a = [1, 2]
b = a
```

এটি নতুন list তৈরি করে না। একই object-এর reference তৈরি করে।

আলাদা list প্রয়োজন হলে:

```python
b = a.copy()
```

### Mistake 3: `is`-এর ফল সবসময় অনুমান করা

Integer বা string-এর ক্ষেত্রে `is`-এর ফল implementation-এর optimization-এর ওপর নির্ভর করতে পারে। তাই object identity সত্যিই পরীক্ষা করার প্রয়োজন না থাকলে এটি ব্যবহার করবে না।

## 12. Quick Comparison Examples

| Code | Result | কারণ |
|---|---|---|
| `[1, 2] == [1, 2]` | `True` | Value একই |
| `[1, 2] is [1, 2]` | `False` | দুটি আলাদা list object |
| `a = [1, 2]; b = a; a is b` | `True` | একই object |
| `10 == 10` | `True` | Value একই |
| `x is None` | Boolean result | `x` ঠিক `None` object কি না |
| `x is not None` | Boolean result | `x` `None` object নয় কি না |

## 13. Practice Exercises

### Exercise 1

```python
a = [5, 10]
b = [5, 10]

print(a == b)
print(a is b)
```

**Answer:**

```text
True
False
```

### Exercise 2

```python
x = [1, 2, 3]
y = x

y.append(4)

print(x)
print(x is y)
```

**Answer:**

```text
[1, 2, 3, 4]
True
```

### Exercise 3

```python
value = None
print(value is None)
print(value is not None)
```

**Answer:**

```text
True
False
```

### Exercise 4

কোনটি value comparison-এর জন্য ব্যবহার করা উচিত?

- A. `is`
- B. `==`

**Answer:** B. `==`

## 14. Summary

- `==` দুটি object-এর value equality পরীক্ষা করে।
- `is` দুটি variable একই object-কে নির্দেশ করছে কি না পরীক্ষা করে।
- একই value থাকলেও দুটি আলাদা object হতে পারে।
- `b = a` সাধারণত নতুন object তৈরি করে না; একই object-এর reference দেয়।
- `a.copy()` দিয়ে আলাদা list তৈরি করা যায়।
- Integer বা string-এর value তুলনায় `is` ব্যবহার করবে না।
- `None` পরীক্ষা করার জন্য `is None` এবং `is not None` ব্যবহার করবে।

## 15. Self-Assessment Checklist

- [ ] `==` ও `is`-এর পার্থক্য বুঝতে পারি।
- [ ] একই value-এর দুটি আলাদা object চিনতে পারি।
- [ ] Assignment এবং copying-এর পার্থক্য বুঝি।
- [ ] Mutable object-এর shared reference ব্যাখ্যা করতে পারি।
- [ ] `is None` সঠিকভাবে ব্যবহার করতে পারি।
- [ ] Value comparison-এর জন্য `==` ব্যবহার করতে পারি।
