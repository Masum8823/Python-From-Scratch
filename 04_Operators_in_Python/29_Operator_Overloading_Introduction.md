# 29. Operator Overloading in Python

## 1. Operator Overloading কী?

**Operator Overloading** হলো এমন একটি feature, যার মাধ্যমে একই operator বিভিন্ন data type বা object-এর জন্য ভিন্ন অর্থে কাজ করতে পারে।

Python-এ built-in data type-এর ক্ষেত্রে আমরা এর ব্যবহার প্রতিদিনই দেখি।

### Example 1: `+` Operator with Numbers

```python
print(10 + 20)
```

**Output:**

```text
30
```

এখানে `+` operator দুটি সংখ্যাকে যোগ করেছে।

### Example 2: `+` Operator with Strings

```python
print("Hello " + "Python")
```

**Output:**

```text
Hello Python
```

এখানে একই `+` operator দুটি string-কে একসঙ্গে যুক্ত করেছে। এই কাজকে **String Concatenation** বলা হয়।

### Example 3: `*` Operator with Numbers

```python
print(5 * 3)
```

**Output:**

```text
15
```

এখানে `*` multiplication করেছে।

### Example 4: `*` Operator with Strings

```python
print("Hi! " * 3)
```

**Output:**

```text
Hi! Hi! Hi! 
```

এখানে `*` string-টিকে তিনবার repeat করেছে।

এই উদাহরণগুলোতে একই operator বিভিন্ন ধরনের object-এর ওপর ভিন্নভাবে কাজ করছে।

---

## 2. কেন Operator Overloading প্রয়োজন?

Operator overloading-এর মাধ্যমে custom object-এর সঙ্গে পরিচিত operator ব্যবহার করা যায়।

এর প্রধান সুবিধাগুলো হলো:

1. Code সহজে পড়া যায়।
2. Custom object-এর ওপর স্বাভাবিক mathematical operation করা যায়।
3. Class-এর object-কে built-in data type-এর মতো ব্যবহার করা যায়।
4. Complex object-এর operation আরও পরিষ্কারভাবে প্রকাশ করা যায়।

ধরো, তোমার একটি `Point` class আছে, যা 2D coordinate সংরক্ষণ করে।

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y
```

এখন দুটি point যোগ করতে চাইলে, operator overloading ছাড়া আলাদা method ব্যবহার করতে হতে পারে।

Operator overloading ব্যবহার করলে এভাবে লেখা সম্ভব:

```python
p3 = p1 + p2
```

এই `+` কীভাবে কাজ করবে, তা class-এর মধ্যে নির্ধারণ করা যায়।

---

## 3. Special Methods বা Dunder Methods

Python-এ operator overloading সাধারণত **Special Methods** ব্যবহার করে করা হয়।

এগুলোকে **Dunder Methods**-ও বলা হয়। Dunder শব্দটি এসেছে “double underscore” থেকে।

যেমন:

```python
__add__()
__sub__()
__mul__()
__eq__()
__lt__()
```

এগুলোর নামের শুরুতে এবং শেষে দুটি underscore রয়েছে।

### গুরুত্বপূর্ণ Operator এবং তাদের Special Methods

| Operator | Special Method | কাজ |
|---|---|---|
| `+` | `__add__()` | যোগ |
| `-` | `__sub__()` | বিয়োগ |
| `*` | `__mul__()` | গুণ |
| `/` | `__truediv__()` | সাধারণ ভাগ |
| `//` | `__floordiv__()` | Floor division |
| `%` | `__mod__()` | Modulo |
| `**` | `__pow__()` | Power |
| `==` | `__eq__()` | Equality comparison |
| `<` | `__lt__()` | Less-than comparison |
| `>` | `__gt__()` | Greater-than comparison |
| `<=` | `__le__()` | Less-than-or-equal |
| `>=` | `__ge__()` | Greater-than-or-equal |
| `!=` | `__ne__()` | Not-equal comparison |
| `-obj` | `__neg__()` | Unary negative |
| `str(obj)` | `__str__()` | Readable string representation |

**মনে রাখবে:** Special method-এর নামগুলো Python-এর নির্ধারিত নাম। নিজের ইচ্ছামতো নাম পরিবর্তন করলে Python সেগুলোকে একই operator-এর implementation হিসেবে চিনবে না।

---

## 4. How Operator Overloading Works

ধরো, আমরা একটি `Number` class তৈরি করব। এই class-এর দুটি object যোগ করার সময় `+` operator ব্যবহার করতে চাই।

Python যখন নিচের expression দেখে:

```python
a + b
```

তখন সাধারণভাবে `a` object-এর `__add__()` special method ব্যবহার করার চেষ্টা করে।

ধারণাগতভাবে:

```python
a + b
```

এটি অনেকটা এভাবে কাজ করে:

```python
a.__add__(b)
```

এটি বোঝার জন্য একটি সহজ উদাহরণ দেখি।

```python
class Number:
    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        return self.value + other.value


a = Number(10)
b = Number(20)

print(a + b)
```

**Output:**

```text
30
```

### ব্যাখ্যা

1. `Number(10)` একটি object তৈরি করে, যার `value` হলো `10`।
2. `Number(20)` আরেকটি object তৈরি করে, যার `value` হলো `20`।
3. `a + b` expression-এ Python `__add__()` method ব্যবহার করে।
4. Method দুটি object-এর `value` যোগ করে `30` return করে।

এখানে আমরা custom class-এর জন্য `+` operator-এর আচরণ নির্ধারণ করেছি।

---

## 5. Example: Overloading the `+` Operator

এবার একটি `Point` class তৈরি করি। দুটি point যোগ করলে তাদের `x` এবং `y` coordinate আলাদাভাবে যোগ হবে।

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):
        return Point(
            self.x + other.x,
            self.y + other.y
        )

    def __str__(self):
        return f"({self.x}, {self.y})"


p1 = Point(2, 3)
p2 = Point(4, 5)

p3 = p1 + p2

print(p3)
```

**Output:**

```text
(6, 8)
```

### ধাপে ধাপে ব্যাখ্যা

প্রথম point:

```python
p1 = Point(2, 3)
```

এখানে `x = 2` এবং `y = 3`।

দ্বিতীয় point:

```python
p2 = Point(4, 5)
```

এখানে `x = 4` এবং `y = 5`।

যোগ করার সময়:

```python
p3 = p1 + p2
```

Python `__add__()` method ব্যবহার করে।

Coordinate-এর হিসাব:

```text
x = 2 + 4 = 6
y = 3 + 5 = 8
```

তাই নতুন point হলো `(6, 8)`।

এখানে `__add__()` একটি নতুন `Point` object return করেছে। আর `__str__()` method object-টিকে সুন্দরভাবে print করতে সাহায্য করেছে।

---

## 6. Example: Overloading the `-` Operator

`-` operator-এর আচরণ নির্ধারণ করতে `__sub__()` method ব্যবহার করা যায়।

```python
class Number:
    def __init__(self, value):
        self.value = value

    def __sub__(self, other):
        return self.value - other.value


a = Number(50)
b = Number(20)

print(a - b)
```

**Output:**

```text
30
```

এখানে:

- `a`-এর value হলো `50`।
- `b`-এর value হলো `20`।
- `__sub__()` method `50 - 20` হিসাব করে `30` return করেছে।

---

## 7. Example: Overloading the `*` Operator

`*` operator-এর custom behaviour নির্ধারণ করতে `__mul__()` ব্যবহার করা হয়।

```python
class Number:
    def __init__(self, value):
        self.value = value

    def __mul__(self, other):
        return self.value * other.value


a = Number(6)
b = Number(7)

print(a * b)
```

**Output:**

```text
42
```

এখানে `a * b` expression-এর মাধ্যমে দুটি custom object-এর value গুণ করা হয়েছে।

---

## 8. Operator Overloading for Comparison

Arithmetic operator ছাড়াও comparison operator overload করা যায়।

যেমন, `==` operator-এর behaviour নির্ধারণ করতে `__eq__()` ব্যবহার করা হয়।

### Example

```python
class Student:
    def __init__(self, student_id):
        self.student_id = student_id

    def __eq__(self, other):
        return self.student_id == other.student_id


s1 = Student(101)
s2 = Student(101)
s3 = Student(102)

print(s1 == s2)
print(s1 == s3)
```

**Output:**

```text
True
False
```

### ব্যাখ্যা

- `s1` এবং `s2`-এর `student_id` একই, তাই ফল `True`।
- `s1` এবং `s3`-এর `student_id` আলাদা, তাই ফল `False`।

এখানে `==` operator-এর behaviour আমরা class-এর মধ্যে নির্ধারণ করেছি।

**গুরুত্বপূর্ণ:** `==` সাধারণত value equality পরীক্ষা করে, কিন্তু custom class-এ কীভাবে equality নির্ধারিত হবে তা class-এর implementation-এর ওপর নির্ভর করতে পারে।

---

## 9. Operator Overloading vs Method Calling

একই কাজ operator অথবা সরাসরি special method call করে করা যেতে পারে।

### Using the Operator

```python
class Number:
    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        return self.value + other.value


a = Number(10)
b = Number(5)

print(a + b)
```

**Output:**

```text
15
```

### Calling the Method Directly

```python
print(a.__add__(b))
```

**Output:**

```text
15
```

দুটির ফল একই হলেও সাধারণত operator ব্যবহার করাই বেশি পরিষ্কার:

```python
a + b
```

এটি পড়তে ও বুঝতে সহজ।

---

## 10. Operator Overloading-এর সীমাবদ্ধতা

Operator overloading মানে যেকোনো operator-কে যেকোনো ইচ্ছামতো কাজ করানো নয়। কিছু গুরুত্বপূর্ণ বিষয় মনে রাখতে হবে।

### 1. সঠিক special method ব্যবহার করতে হবে

`+` operator overload করতে `__add__()` ব্যবহার করা হয়; `__sub__()` নয়।

### 2. Behaviour যৌক্তিক হওয়া উচিত

যদি `Point` object-এর `+` operator coordinate যোগ করে, তাহলে এটি সহজে বোঝা যায়।

কিন্তু `+` operator দিয়ে অপ্রত্যাশিত কোনো কাজ করালে code বোঝা কঠিন হতে পারে।

### 3. Return value সঠিক হতে হবে

`__add__()` একটি value return করতে পারে, যেমন সংখ্যা বা নতুন object। কোনটি উপযুক্ত, তা class-এর উদ্দেশ্যের ওপর নির্ভর করে।

### 4. সব operator স্বয়ংক্রিয়ভাবে overload হয় না

Custom class-এ operator-এর প্রয়োজনীয় behaviour বাস্তবায়ন করতে হয়। সঠিক special method না থাকলে operation ব্যর্থ হতে পারে অথবা অন্য কোনো fallback behaviour কার্যকর হতে পারে।

### 5. Unsupported operand handle করতে হয়

যদি class অন্য ধরনের object-এর সঙ্গে operation support না করে, তাহলে সাধারণত `NotImplemented` return করার মাধ্যমে Python-কে অন্য operand-এর implementation চেষ্টা করার সুযোগ দেওয়া যায়।

উদাহরণ:

```python
class Number:
    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        if not isinstance(other, Number):
            return NotImplemented

        return Number(self.value + other.value)
```

এখানে `Number` object ছাড়া অন্য ধরনের operand পেলে method `NotImplemented` return করে।

`NotImplemented` একটি বিশেষ value; এটি `NotImplementedError` exception-এর সমান নয়।

---

## 11. Common Mistakes

### Mistake 1: ভুল special method-এর নাম ব্যবহার করা

`+` operator-এর জন্য `__addition__()` লিখলে Python সেটিকে `+` operator-এর special method হিসেবে চিনবে না।

সঠিক নাম:

```python
__add__()
```

### Mistake 2: Method-এর parameter ভুল লেখা

```python
def __add__(self, other):
    return self.value + other.value
```

এখানে `self` বর্তমান object-কে এবং `other` অন্য object-কে নির্দেশ করে।

### Mistake 3: Object-এর বদলে attribute ভুলভাবে ব্যবহার করা

যদি `other` একটি `Number` object হয়, তাহলে তার value পেতে:

```python
other.value
```

ব্যবহার করতে হবে। `other`-কে সরাসরি সংখ্যা ধরে নেওয়া যাবে না।

### Mistake 4: `__str__()` এবং `__add__()`-এর কাজ গুলিয়ে ফেলা

- `__add__()` `+` operator-এর behaviour নির্ধারণ করে।
- `__str__()` object-এর readable string representation তৈরি করে।

এরা আলাদা উদ্দেশ্যে ব্যবহৃত হয়।

---

## 12. Practice Exercises

প্রথমে নিজে output অনুমান করো। এরপর Answer Key মিলিয়ে দেখো।

### Exercise 1

```python
class Number:
    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        return self.value + other.value


a = Number(12)
b = Number(8)

print(a + b)
```

### Exercise 2

```python
class Number:
    def __init__(self, value):
        self.value = value

    def __sub__(self, other):
        return self.value - other.value


a = Number(30)
b = Number(10)

print(a - b)
```

### Exercise 3

```python
class Student:
    def __init__(self, student_id):
        self.student_id = student_id

    def __eq__(self, other):
        return self.student_id == other.student_id


a = Student(5)
b = Student(5)

print(a == b)
```

### Exercise 4

নিচের code-এ কোন special method ব্যবহার করা হয়েছে?

```python
def __mul__(self, other):
    return self.value * other.value
```

### Exercise 5

কোন special method `print(object)`-এর জন্য readable string representation তৈরি করতে সাহায্য করে?

### Answer Key

| Exercise | Answer |
|---|---|
| 1 | `20` |
| 2 | `20` |
| 3 | `True` |
| 4 | `__mul__()` — multiplication operator |
| 5 | `__str__()` |

---

## 13. Quick Revision

- Operator overloading একই operator-কে বিভিন্ন object-এর জন্য ভিন্নভাবে কাজ করতে দেয়।
- Python-এ এটি সাধারণত special বা dunder methods দিয়ে করা হয়।
- `+` operator-এর জন্য `__add__()` ব্যবহৃত হয়।
- `-` operator-এর জন্য `__sub__()` ব্যবহৃত হয়।
- `*` operator-এর জন্য `__mul__()` ব্যবহৃত হয়।
- `==` operator-এর জন্য `__eq__()` ব্যবহৃত হয়।
- `__str__()` object-এর readable string representation তৈরি করে।
- Custom operator behaviour যৌক্তিক ও সহজে বোঝার মতো হওয়া উচিত।
- Unsupported operand-এর ক্ষেত্রে `NotImplemented` ব্যবহার করা যেতে পারে।

## 14. Self-Assessment Checklist

- [ ] Operator overloading-এর অর্থ বুঝি।
- [ ] Built-in data type-এ operator-এর ভিন্ন ব্যবহার চিনতে পারি।
- [ ] Special বা dunder method শনাক্ত করতে পারি।
- [ ] `__add__()` দিয়ে custom object যোগ করতে পারি।
- [ ] `__sub__()` ও `__mul__()`-এর কাজ বুঝি।
- [ ] `__eq__()` দিয়ে custom equality comparison বুঝি।
- [ ] `__str__()` ও `__add__()`-এর পার্থক্য বুঝি।
- [ ] Operator overloading-এর common mistakes শনাক্ত করতে পারি।

পরবর্তী Topic: **30. Common Operator Errors and Pitfalls**