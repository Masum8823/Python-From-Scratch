# 18. Identity Operators in Python

## 1. Introduction to Identity Operators

Python-এ **Identity Operators** ব্যবহার করে দুটি Variable একই Object-কে নির্দেশ করছে কি না, তা পরীক্ষা করা হয়।

Python-এ দুটি Identity Operator রয়েছে:

| Operator | অর্থ |
|---|---|
| `is` | দুটি Reference একই Object-কে নির্দেশ করে কি না পরীক্ষা করে |
| `is not` | দুটি Reference একই Object-কে নির্দেশ করে না কি না পরীক্ষা করে |

এই Operator-গুলো Result হিসেবে `True` অথবা `False` Return করে।

### Example

```python
a = [1, 2, 3]
b = a

print(a is b)
print(a is not b)
```

Output:

```text
True
False
```

ব্যাখ্যা:

- `b = a` করার ফলে `b` একই List Object-কে নির্দেশ করে।
- তাই `a is b` হলো `True`।
- তারা একই Object হওয়ায় `a is not b` হলো `False`।

---

## 2. Understanding Object Identity

Identity Operator বোঝার আগে Python-এর Object সম্পর্কে একটি Basic ধারণা থাকা প্রয়োজন।

Python-এ একটি Object-এর সাধারণত তিনটি গুরুত্বপূর্ণ বৈশিষ্ট্য রয়েছে:

1. **Identity:** Object-টি কোন নির্দিষ্ট Object।
2. **Type:** Object-টি কোন Data Type-এর।
3. **Value:** Object-টির মধ্যে কী Value রয়েছে।

Example:

```python
x = [10, 20]
y = [10, 20]

print(x == y)
print(x is y)
```

Output:

```text
True
False
```

ব্যাখ্যা:

- `x` এবং `y`-এর Value একই।
- কিন্তু দুটি আলাদা List Object তৈরি হয়েছে।
- তাই `x == y` হলো `True`।
- `x is y` হলো `False`।

**মনে রাখবে:** Value একই হলেই দুটি Object একই Object হয়ে যায় না।

---

## 3. The `is` Operator

`is` Operator পরীক্ষা করে দুটি Reference একই Object-কে নির্দেশ করছে কি না।

### Example 1: Same Object

```python
a = [1, 2, 3]
b = a

print(a is b)
```

Output:

```text
True
```

কারণ `b = a` করার ফলে `b` নতুন List তৈরি করেনি। এটি `a`-এর একই List Object-কে নির্দেশ করছে।

### Example 2: Separate Objects

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a is b)
```

Output:

```text
False
```

দুটি List-এর Value একই, কিন্তু তারা আলাদা Object।

### Example 3: Same Reference After Assignment

```python
x = [10, 20]
y = x

y.append(30)

print(x)
print(y)
print(x is y)
```

Output:

```text
[10, 20, 30]
[10, 20, 30]
True
```

ব্যাখ্যা:

- `x` এবং `y` একই List Object-কে নির্দেশ করে।
- `y.append(30)` সেই Object-টিকেই পরিবর্তন করে।
- তাই `x` এবং `y` উভয়ের মাধ্যমে পরিবর্তিত List দেখা যায়।

---

## 4. The `is not` Operator

`is not` Operator পরীক্ষা করে দুটি Reference আলাদা Object-কে নির্দেশ করছে কি না।

### Example 1

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a is not b)
```

Output:

```text
True
```

দুটি List আলাদা Object হওয়ায় Result `True`।

### Example 2

```python
a = [5, 10]
b = a

print(a is not b)
```

Output:

```text
False
```

কারণ `a` এবং `b` একই Object-কে নির্দেশ করে।

### Example 3: Combining Identity Checks

```python
x = [1, 2]
y = x
z = [1, 2]

print(x is y)
print(x is not z)
print(y is z)
```

Output:

```text
True
True
False
```

ব্যাখ্যা:

- `x` ও `y` একই Object।
- `x` ও `z` আলাদা Object।
- `y` ও `z`-এর Value একই হলেও Object আলাদা।

---

## 5. Difference Between `is` and `==`

এটি Identity Operators-এর সবচেয়ে গুরুত্বপূর্ণ অংশ।

`==` এবং `is`-এর কাজ আলাদা:

- `==` পরীক্ষা করে দুটি Object-এর Value সমান কি না।
- `is` পরীক্ষা করে দুটি Reference একই Object-কে নির্দেশ করছে কি না।

### Example

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

এখানে:

- `a == b` হলো `True`, কারণ List দুটির Value সমান।
- `a is b` হলো `False`, কারণ List দুটি আলাদা Object।

### Comparison Table

| বিষয় | `==` | `is` |
|---|---|---|
| নাম | Equality Operator | Identity Operator |
| কী পরীক্ষা করে | Value সমান কি না | একই Object কি না |
| Result | `True` বা `False` | `True` বা `False` |
| Example | `a == b` | `a is b` |
| সমান Value-এর আলাদা List | `True` | `False` |

**Exam Tip:** `==` মানে *same value*; `is` মানে *same object*।

---

## 6. Identity Operators with Variables

Variable-এর মাধ্যমে Object Reference কীভাবে কাজ করে, তা বোঝা গুরুত্বপূর্ণ।

### Example 1: Integer Variables

```python
a = 100
b = a

print(a == b)
print(a is b)
```

Output:

```text
True
True
```

এখানে `b = a` করার ফলে উভয় Variable একই Integer Object-কে নির্দেশ করে।

### Example 2: Reassignment

```python
a = 10
b = a

a = 20

print(a)
print(b)
print(a is b)
```

Output:

```text
20
10
False
```

ব্যাখ্যা:

- শুরুতে `a` ও `b` একই Integer Object-কে নির্দেশ করছিল।
- `a = 20` করার ফলে `a`-কে নতুন Value Assign করা হয়েছে।
- `b`-এর Assignment পরিবর্তিত হয়নি।
- তাই `a` ও `b` এখন একই Object-কে নির্দেশ করছে না।

এটি Variable Reassignment-এর একটি গুরুত্বপূর্ণ উদাহরণ।

---

## 7. Identity Operators with Lists

List একটি Mutable Object। তাই Identity Operators-এর সঙ্গে List ব্যবহার করলে Reference-এর আচরণ সহজে দেখা যায়।

### Example 1: Copying a Reference

```python
numbers1 = [1, 2, 3]
numbers2 = numbers1

print(numbers1 is numbers2)
```

Output:

```text
True
```

এখানে নতুন List তৈরি হয়নি; একই List-এর Reference Assign হয়েছে।

### Example 2: Creating a Separate List

```python
numbers1 = [1, 2, 3]
numbers2 = numbers1.copy()

print(numbers1 == numbers2)
print(numbers1 is numbers2)
```

Output:

```text
True
False
```

ব্যাখ্যা:

- `.copy()` একটি নতুন, Shallow Copy List তৈরি করেছে।
- দুটি List-এর Value সমান।
- কিন্তু তারা আলাদা List Object।

### Example 3: Modifying One List

```python
numbers1 = [1, 2, 3]
numbers2 = numbers1

numbers2.append(4)

print(numbers1)
print(numbers1 is numbers2)
```

Output:

```text
[1, 2, 3, 4]
True
```

কারণ উভয় Variable একই List Object-কে নির্দেশ করে।

---

## 8. Identity Operators with `None`

Python-এ `None` বোঝায় কোনো Value নেই বা অনুপস্থিত Value।

`None` পরীক্ষা করার জন্য সাধারণত `is` এবং `is not` ব্যবহার করা হয়।

### Example 1: Checking for `None`

```python
result = None

print(result is None)
```

Output:

```text
True
```

### Example 2: Checking That a Value Is Not `None`

```python
result = 100

print(result is not None)
```

Output:

```text
True
```

### Example 3: Conditional Check

```python
value = None

if value is None:
    print("No value available.")
else:
    print(value)
```

Output:

```text
No value available.
```

এখানে `value` হলো `None`, তাই `if` Condition True হয়েছে।

**Best Practice:** কোনো Variable-এর Value `None` কি না পরীক্ষা করতে `value is None` বা `value is not None` ব্যবহার করবে। `value == None` লেখার পরিবর্তে Identity Check-ই পছন্দনীয়।

---

## 9. Identity Operators with Strings and Numbers

String ও Number-এর ক্ষেত্রে Identity Operator ব্যবহারে সতর্ক থাকা প্রয়োজন।

Python কিছু ক্ষেত্রে Memory বা Performance Optimization-এর জন্য একই Value-এর Object Reuse করতে পারে। আবার অন্য ক্ষেত্রে আলাদা Object তৈরি হতে পারে।

তাই নিচের মতো Code-এর Result ধরে নেওয়া উচিত নয়:

```python
a = 1000
b = 1000

print(a == b)
print(a is b)
```

Value সমান হওয়ায় `a == b` হলো `True`। কিন্তু `a is b`-এর Result নির্ভর করতে পারে Python কীভাবে Object তৈরি করেছে তার ওপর।

অন্যদিকে:

```python
a = "Python"
b = "Python"

print(a == b)
```

Output:

```text
True
```

String-এর Value সমান হওয়ায় `==` হলো `True`।

**গুরুত্বপূর্ণ নিয়ম:** দুটি String বা Number-এর Value সমান কি না পরীক্ষা করতে `==` ব্যবহার করবে। `is` ব্যবহার করবে যখন সত্যিই একই Object কি না পরীক্ষা করতে চাও।

---

## 10. Identity Operators in Conditional Statements

`is` এবং `is not` `if` Statement-এর Condition-এ ব্যবহার করা যায়।

### Example 1

```python
user = None

if user is None:
    print("User not found.")
```

Output:

```text
User not found.
```

### Example 2

```python
data = [10, 20, 30]
backup = data

if data is backup:
    print("Both refer to the same object.")
```

Output:

```text
Both refer to the same object.
```

### Example 3

```python
data = [10, 20, 30]
backup = data.copy()

if data is not backup:
    print("They are different objects.")
```

Output:

```text
They are different objects.
```

এখানে `.copy()` দিয়ে আলাদা List তৈরি করা হয়েছে।

---

## 11. Common Mistakes

### Mistake 1: Using `is` to Compare Values

ভুল পদ্ধতি:

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a is b)
```

Output:

```text
False
```

যদি List-এর Value সমান কি না পরীক্ষা করতে চাও, তাহলে লিখবে:

```python
print(a == b)
```

Output:

```text
True
```

### Mistake 2: Thinking `b = a` Creates a Copy

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

এখানে `b = a` নতুন List তৈরি করেনি। তাই `b`-এর মাধ্যমে পরিবর্তন করলে `a`-এর মাধ্যমেও পরিবর্তনটি দেখা যায়।

আলাদা List প্রয়োজন হলে:

```python
a = [1, 2, 3]
b = a.copy()
```

### Mistake 3: Using `is` for `None` Incorrectly

`None` পরীক্ষা করার Recommended Style:

```python
if result is None:
    print("No result")
```

### Mistake 4: Assuming Identity Results for All Integers

```python
a = 1000
b = 1000

print(a == b)
```

Output:

```text
True
```

এটি Value Equality পরীক্ষা করে। `a is b`-এর Result-কে Value Equality-এর বিকল্প হিসেবে ব্যবহার করবে না।

---

## 12. Practice Exercises

### Basic Level

1. `is` এবং `is not`-এর কাজ ব্যাখ্যা করো।
2. `a = [1, 2]` এবং `b = a` হলে `a is b`-এর Result কী?
3. দুটি আলাদা List-এ একই Value থাকলে `a == b` এবং `a is b`-এর Result কী হবে?
4. `value is None` কেন ব্যবহার করা হয়?

### Intermediate Level

5. `a = [1, 2, 3]` এবং `b = a.copy()` নিয়ে `a == b` ও `a is b` পরীক্ষা করো।
6. `b = a` করার পর `b.append(4)` করলে `a`-এর Value কী হবে?
7. `is` এবং `==`-এর মধ্যে পার্থক্য একটি Code Example দিয়ে দেখাও।
8. `None` না হলে একটি Message Print করার Program লেখো।

### Output Prediction

```python
a = [10, 20]
b = a
c = [10, 20]

print(a == b)
print(a is b)
print(a == c)
print(a is c)
print(a is not c)
```

### Answers

```text
True
True
True
False
True
```

ব্যাখ্যা:

- `a` ও `b` একই Object-কে নির্দেশ করে।
- `a` ও `c`-এর Value সমান, কিন্তু তারা আলাদা List Object।
- তাই `a is not c` হলো `True`।

---

## 13. Chapter Summary

- Identity Operators দুটি: `is` এবং `is not`।
- `is` পরীক্ষা করে দুটি Reference একই Object-কে নির্দেশ করছে কি না।
- `is not` পরীক্ষা করে দুটি Reference একই Object-কে নির্দেশ করছে না কি না।
- `==` Value Equality পরীক্ষা করে।
- `is` Object Identity পরীক্ষা করে।
- `b = a` করলে সাধারণত একই Object-এর Reference Assign হয়; Copy তৈরি হয় না।
- `.copy()` দিয়ে List-এর Shallow Copy তৈরি করা যায়।
- `None` পরীক্ষা করতে `is None` এবং `is not None` ব্যবহার করা উচিত।
- String ও Number-এর Value তুলনা করতে সাধারণত `==` ব্যবহার করবে।

## 14. Self-Assessment Checklist

- [ ] `is` এবং `is not`-এর কাজ বুঝি।
- [ ] Identity ও Equality-এর পার্থক্য বুঝি।
- [ ] `==` এবং `is`-এর সঠিক ব্যবহার জানি।
- [ ] Variable Reference-এর Basic ধারণা বুঝি।
- [ ] List Reference এবং Copy-এর পার্থক্য বুঝি।
- [ ] `None` পরীক্ষা করতে Identity Operator ব্যবহার করতে পারি।
- [ ] Output Prediction Exercise সমাধান করতে পারি।

**Next Topic:** `19_Membership_Operators.md`