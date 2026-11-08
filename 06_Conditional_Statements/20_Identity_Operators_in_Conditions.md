# 20. Identity Operators in Conditions

## 1. Identity Operators কী?

Python-এ **Identity Operators** ব্যবহার করে দুটি variable একই object-কে নির্দেশ করছে কি না, তা পরীক্ষা করা হয়।

Python-এ দুটি Identity Operator রয়েছে:

| Operator | কাজ |
|---|---|
| `is` | দুটি reference একই object-কে নির্দেশ করছে কি না পরীক্ষা করে |
| `is not` | দুটি reference একই object-কে নির্দেশ করছে না কি না পরীক্ষা করে |

এই operator-গুলো result হিসেবে `True` অথবা `False` দেয়।

উদাহরণ:

```python
a = None

print(a is None)
print(a is not None)
```

Output:

```text
True
False
```

কারণ `a`-এর value `None`, তাই `a is None` True।

**মনে রাখবে:** Identity Operators value সমান কি না পরীক্ষা করে না; তারা object identity পরীক্ষা করে।

## 2. Object Identity কী?

Python-এ object হলো এমন একটি entity, যার নিজস্ব identity, type এবং value থাকে।

Variable সাধারণত object-এর reference ধরে রাখে। দুটি variable একই object-কে নির্দেশ করলে তাদের identity একই।

উদাহরণ:

```python
a = [10, 20, 30]
b = a

print(a is b)
print(a == b)
```

Output:

```text
True
True
```

এখানে:

- `b = a` করার ফলে `b` একই list object-কে নির্দেশ করছে।
- `a is b` True, কারণ দুটি reference একই object-কে নির্দেশ করছে।
- `a == b` True, কারণ দুটি list-এর content সমান।

এখানে `is` ও `==`—দুটির result True হলেও তাদের কাজ আলাদা।

## 3. `is` Operator কীভাবে কাজ করে?

`is` পরীক্ষা করে দুটি reference একই object-কে নির্দেশ করছে কি না।

উদাহরণ:

```python
a = [1, 2, 3]
b = a

print(a is b)
```

Output:

```text
True
```

কারণ `a` ও `b` একই list object-কে নির্দেশ করছে।

এবার আরেকটি উদাহরণ:

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a is b)
```

Output:

```text
False
```

এখানে দুটি আলাদা list object তৈরি হয়েছে। তাদের content একই হলেও identity আলাদা।

**গুরুত্বপূর্ণ:** দুটি collection-এর content সমান হলেই তারা একই object হয়ে যায় না।

## 4. `is not` Operator কীভাবে কাজ করে?

`is not` হলো `is`-এর বিপরীত identity check।

যদি দুটি reference একই object-কে নির্দেশ না করে, তাহলে `is not` True হবে।

উদাহরণ:

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a is not b)
```

Output:

```text
True
```

কারণ `a` এবং `b` দুটি আলাদা list object।

আরেকটি উদাহরণ:

```python
a = [1, 2, 3]
b = a

print(a is not b)
```

Output:

```text
False
```

কারণ `a` ও `b` একই object-কে নির্দেশ করছে।

## 5. `is` এবং `==`-এর পার্থক্য

এটি Python-এর খুব গুরুত্বপূর্ণ একটি বিষয়।

| বিষয় | `is` | `==` |
|---|---|---|
| কাজ | Object identity পরীক্ষা করে | Value equality পরীক্ষা করে |
| প্রশ্ন | একই object কি না? | Value সমান কি না? |
| একই object হলে | True | সাধারণত True |
| আলাদা object, কিন্তু সমান content | False হতে পারে | True হতে পারে |

উদাহরণ:

```python
a = [10, 20]
b = [10, 20]

print(a is b)
print(a == b)
```

Output:

```text
False
True
```

ব্যাখ্যা:

- `a is b` False, কারণ list দুটি আলাদা object।
- `a == b` True, কারণ list দুটির content সমান।

সহজভাবে মনে রাখবে:

- `==` → value সমান কি না।
- `is` → একই object কি না।

## 6. `None` পরীক্ষা করতে `is` ব্যবহার

Python-এ `None` বোঝায় কোনো value নেই বা অনুপস্থিত।

`None` পরীক্ষা করার জন্য সাধারণত `is` এবং `is not` ব্যবহার করা হয়।

উদাহরণ:

```python
result = None

if result is None:
    print("No result available")
else:
    print("Result available")
```

Output:

```text
No result available
```

কারণ `result`-এর value `None`।

আরেকটি উদাহরণ:

```python
username = "Masum"

if username is not None:
    print("Username is provided")
```

Output:

```text
Username is provided
```

এখানে `username`-এর value `None` নয়, তাই condition True।

**Best practice:** `None` পরীক্ষা করতে `value is None` বা `value is not None` ব্যবহার করো।

## 7. Conditional Statements-এ Identity Operators

Identity Operators সরাসরি `if` condition-এর মধ্যে ব্যবহার করা যায়।

উদাহরণ:

```python
a = [1, 2, 3]
b = a

if a is b:
    print("Same object")
else:
    print("Different objects")
```

Output:

```text
Same object
```

এখানে দুটি variable একই list object-কে নির্দেশ করছে।

এবার:

```python
a = [1, 2, 3]
b = [1, 2, 3]

if a is not b:
    print("Different objects")
else:
    print("Same object")
```

Output:

```text
Different objects
```

দুটি list-এর content সমান, কিন্তু object identity আলাদা।

## 8. Mutable Objects-এর সঙ্গে Identity

List, dictionary ও set-এর মতো mutable object পরিবর্তন করা যায়।

যদি দুটি variable একই mutable object-কে নির্দেশ করে, তাহলে একটি variable দিয়ে object পরিবর্তন করলে অন্য variable দিয়েও সেই পরিবর্তন দেখা যাবে।

উদাহরণ:

```python
a = [10, 20]
b = a

b.append(30)

print(a)
print(b)
print(a is b)
```

Output:

```text
[10, 20, 30]
[10, 20, 30]
True
```

ব্যাখ্যা:

- `b = a` করার ফলে `a` ও `b` একই list object-কে নির্দেশ করছে।
- `b.append(30)` সেই list-টিকেই পরিবর্তন করেছে।
- তাই `a` এবং `b` উভয় variable থেকেই পরিবর্তিত list দেখা যাচ্ছে।

এবার আলাদা list ব্যবহার করি:

```python
a = [10, 20]
b = [10, 20]

b.append(30)

print(a)
print(b)
print(a is b)
```

Output:

```text
[10, 20]
[10, 20, 30]
False
```

এখানে দুটি আলাদা list object রয়েছে। তাই `b` পরিবর্তন করলে `a` পরিবর্তিত হয় না।

## 9. `is` এবং `is not` দিয়ে Boolean পরীক্ষা

Boolean values-এর ক্ষেত্রে identity check করা সম্ভব।

উদাহরণ:

```python
a = True
b = True

print(a is b)
print(a == b)
```

Output:

```text
True
True
```

তবে সাধারণ Boolean equality পরীক্ষা করার জন্য `==` ব্যবহার করাই যথেষ্ট।

উদাহরণ:

```python
is_active = True

if is_active:
    print("Active")
```

এখানে `if is_active:` লেখাই সবচেয়ে সহজ ও readable।

Boolean value পরীক্ষা করার জন্য সাধারণত `is True` ব্যবহার করার প্রয়োজন নেই, যদি না identity check-ই উদ্দেশ্য হয়।

## 10. Integer ও String-এর ক্ষেত্রে সতর্কতা

একই value-এর integer বা string নিয়ে `is` ব্যবহার করে equality পরীক্ষা করা উচিত নয়।

উদাহরণ:

```python
a = 1000
b = 1000

print(a == b)
```

Output:

```text
True
```

এখানে `==` value equality পরীক্ষা করে।

কিন্তু নিচের expression-এর result ধরে নেওয়া ঠিক নয়:

```python
a is b
```

Python কিছু immutable object পুনর্ব্যবহার বা cache করতে পারে। ফলে নির্দিষ্ট integer বা string-এর ক্ষেত্রে `is`-এর result implementation ও context-এর ওপর নির্ভর করতে পারে।

সঠিক নিয়ম:

```python
a = "Python"
b = "Python"

print(a == b)
```

Output:

```text
True
```

দুটি string-এর content সমান কি না জানতে `==` ব্যবহার করো।

**মনে রাখবে:** সাধারণ value comparison-এর জন্য `is` নয়, `==` ব্যবহার করতে হবে।

## 11. Identity Operators এবং Truthiness-এর পার্থক্য

Identity check এবং Truthiness check এক জিনিস নয়।

উদাহরণ:

```python
value = 0

print(bool(value))
print(value is None)
```

Output:

```text
False
False
```

ব্যাখ্যা:

- `bool(value)` পরীক্ষা করে value Truthy কি না।
- `value is None` পরীক্ষা করে value `None` কি না।

`0` Falsy হলেও এটি `None` নয়।

আরেকটি উদাহরণ:

```python
value = []

print(bool(value))
print(value is None)
```

Output:

```text
False
False
```

Empty list Falsy, কিন্তু `None` নয়।

তাই কোনো value Falsy হলেই সেটি `None` হয়ে যায় না।

## 12. Common Mistakes

### Mistake 1: `is` দিয়ে value equality পরীক্ষা করা

ভুল পদ্ধতি:

```python
a = [1, 2, 3]
b = [1, 2, 3]

if a is b:
    print("Equal")
```

এখানে `"Equal"` print হবে না, কারণ list দুটি আলাদা object।

সঠিক:

```python
if a == b:
    print("Equal")
```

Output:

```text
Equal
```

### Mistake 2: `None`-এর সঙ্গে `==` ব্যবহার করা

নিচের code সাধারণত কাজ করে:

```python
value = None

if value == None:
    print("No value")
```

তবে Python-এ প্রচলিত ও recommended style হলো:

```python
if value is None:
    print("No value")
```

### Mistake 3: `is`-কে `in`-এর সঙ্গে গুলিয়ে ফেলা

- `is` → দুটি reference একই object-কে নির্দেশ করছে কি না।
- `in` → কোনো collection-এর মধ্যে value আছে কি না।

উদাহরণ:

```python
numbers = [10, 20, 30]

print(20 in numbers)
```

Output:

```text
True
```

এখানে `in` ব্যবহার হয়েছে, কারণ list-এর মধ্যে `20` আছে কি না পরীক্ষা করা হচ্ছে।

### Mistake 4: সব Falsy value-কে `None` মনে করা

```python
print(0 is None)
print("" is None)
print([] is None)
```

Output:

```text
False
False
False
```

এগুলো Falsy হতে পারে, কিন্তু `None` নয়।

## 13. Practice Exercises

প্রতিটি প্রশ্নের output নিজে predict করো।

### Question 1

```python
a = [1, 2]
b = a

print(a is b)
print(a == b)
```

### Question 2

```python
a = [1, 2]
b = [1, 2]

print(a is b)
print(a == b)
```

### Question 3

```python
value = None

print(value is None)
print(value is not None)
```

### Question 4

```python
value = 0

print(bool(value))
print(value is None)
```

### Question 5

```python
a = [10, 20]
b = a

b.append(30)

print(a)
print(a is b)
```

### Question 6

```python
a = "Python"
b = "Python"

print(a == b)
```

### Question 7

```python
a = [5, 10]
b = [5, 10]

if a == b:
    print("Equal values")

if a is not b:
    print("Different objects")
```

### Question 8

```python
result = None

if result is None:
    print("Waiting")
else:
    print("Completed")
```

## 14. Answer Key

### Answer 1

```text
True
True
```

`a` এবং `b` একই list object-কে নির্দেশ করছে।

### Answer 2

```text
False
True
```

List দুটি আলাদা object, কিন্তু content সমান।

### Answer 3

```text
True
False
```

`value` হলো `None`।

### Answer 4

```text
False
False
```

`0` Falsy, কিন্তু `None` নয়।

### Answer 5

```text
[10, 20, 30]
True
```

`a` ও `b` একই list object-কে নির্দেশ করছে।

### Answer 6

```text
True
```

দুটি string-এর content সমান।

### Answer 7

```text
Equal values
Different objects
```

Value equality এবং object identity আলাদা বিষয়।

### Answer 8

```text
Waiting
```

`result is None` condition True।

## 15. Quick Revision

- **Identity Operators:** `is` এবং `is not`।
- `is` পরীক্ষা করে দুটি reference একই object-কে নির্দেশ করছে কি না।
- `is not` পরীক্ষা করে দুটি reference একই object-কে নির্দেশ করছে না কি না।
- `==` value equality পরীক্ষা করে।
- `None` পরীক্ষা করতে `is None` বা `is not None` ব্যবহার করো।
- List বা dictionary-এর content সমান হলেই object identity একই হয় না।
- Mutable object-এর reference share করলে এক reference দিয়ে করা পরিবর্তন অন্য reference দিয়েও দেখা যায়।
- সাধারণ integer বা string equality পরীক্ষা করতে `==` ব্যবহার করো।
- Truthiness এবং identity এক নয়।

## 16. Self-Assessment Checklist

- [ ] Identity Operators কী, তা বুঝি।
- [ ] `is` এবং `is not` ব্যবহার করতে পারি।
- [ ] `is` ও `==`-এর পার্থক্য বুঝি।
- [ ] `None` সঠিকভাবে পরীক্ষা করতে পারি।
- [ ] একই object ও আলাদা object-এর পার্থক্য বুঝি।
- [ ] Mutable object-এর shared reference বুঝি।
- [ ] Truthiness এবং identity-এর পার্থক্য বলতে পারি।

**পরবর্তী টপিক:** `21_Chained_Comparisons_in_Conditions.md`
