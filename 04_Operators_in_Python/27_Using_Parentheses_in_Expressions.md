# 27. Using Parentheses in Expressions

## 1. Parentheses কী?

Python-এ **Parentheses `()`** ব্যবহার করে expression-এর নির্দিষ্ট অংশকে একসঙ্গে group করা হয়।

এটি calculation-এর order স্পষ্ট করতে এবং expression সহজে বুঝতে সাহায্য করে।

### Example

```python
result = (2 + 3) * 4
print(result)
```

**Output:**
```text
20
```

এখানে parentheses-এর ভেতরের `2 + 3` আগে হিসাব করা হয়েছে।

```python
(2 + 3) * 4
5 * 4
20
```

অন্যদিকে, parentheses ছাড়া:

```python
result = 2 + 3 * 4
print(result)
```

**Output:**
```text
14
```

কারণ multiplication-এর precedence addition-এর চেয়ে বেশি।

---

## 2. Parentheses কেন ব্যবহার করা হয়?

Python-এ parentheses ব্যবহারের প্রধান কারণগুলো হলো:

1. Expression-এর evaluation order স্পষ্ট করা।
2. Operator precedence-এর কারণে ভুল বোঝাবুঝি এড়ানো।
3. Complex calculation সহজে পড়া ও বোঝা।
4. নির্দিষ্ট অংশকে আগে calculate করা।
5. Logical condition-কে পরিষ্কারভাবে group করা।

---

## 3. Controlling the Order of Calculation

Parentheses ব্যবহার করে calculation-এর grouping পরিবর্তন করা যায়।

### Example 1: Addition and Multiplication

```python
print(5 + 3 * 2)
print((5 + 3) * 2)
```

**Output:**
```text
11
16
```

প্রথম expression:

```python
5 + (3 * 2)
5 + 6
11
```

দ্বিতীয় expression:

```python
(5 + 3) * 2
8 * 2
16
```

### Example 2: Subtraction

```python
print(20 - 5 - 3)
print(20 - (5 - 3))
```

**Output:**
```text
12
18
```

প্রথম expression:

```python
(20 - 5) - 3
15 - 3
12
```

দ্বিতীয় expression:

```python
20 - (5 - 3)
20 - 2
18
```

### Example 3: Division

```python
print(24 / 4 * 2)
print(24 / (4 * 2))
```

**Output:**
```text
12.0
3.0
```

প্রথম expression:

```python
(24 / 4) * 2
6.0 * 2
12.0
```

দ্বিতীয় expression:

```python
24 / (4 * 2)
24 / 8
3.0
```

---

## 4. Parentheses and Operator Precedence

Python-এ operator precedence নির্ধারণ করে কোন operator আগে কাজ করবে। তবে parentheses দিয়ে expression-এর grouping স্পষ্টভাবে নিয়ন্ত্রণ করা যায়।

### Example

```python
print(2 + 3 * 4 ** 2)
print((2 + 3) * 4 ** 2)
print((2 + 3 * 4) ** 2)
```

**Output:**
```text
50
80
196
```

ব্যাখ্যা:

**প্রথম expression:**
```python
2 + 3 * 4 ** 2
2 + 3 * 16
2 + 48
50
```

**দ্বিতীয় expression:**
```python
(2 + 3) * 4 ** 2
5 * 16
80
```

**তৃতীয় expression:**
```python
(2 + 3 * 4) ** 2
(2 + 12) ** 2
14 ** 2
196
```

মনে রাখবে, parentheses-এর ভেতরে থাকলেই সব operator একই ক্রমে কাজ করে না। Parentheses প্রথমে কোন অংশটি evaluate হবে তা নির্ধারণ করে; সেই অংশের ভেতরে Python-এর operator precedence-এর নিয়ম কার্যকর থাকে।

---

## 5. Nested Parentheses

একটি parentheses-এর ভেতরে আরেকটি parentheses থাকলে তাকে **Nested Parentheses** বলা হয়।

### Example

```python
result = ((2 + 3) * (4 + 1))
print(result)
```

**Output:**
```text
25
```

ধাপে ধাপে:

```python
(2 + 3) = 5
(4 + 1) = 5
5 * 5 = 25
```

### আরেকটি Example

```python
result = (10 + (6 - 2)) * 3
print(result)
```

**Output:**
```text
42
```

ব্যাখ্যা:

```python
(6 - 2) = 4
10 + 4 = 14
14 * 3 = 42
```

**নিয়ম:** Nested expression বুঝতে সবচেয়ে ভেতরের parentheses থেকে হিসাব শুরু করো।

---

## 6. Parentheses with Exponentiation

Exponentiation operator `**`-এর সঙ্গে parentheses বিশেষভাবে গুরুত্বপূর্ণ।

### Example 1

```python
print(2 ** 3 ** 2)
```

**Output:**
```text
512
```

কারণ `**` ডান দিক থেকে group হয়:

```python
2 ** (3 ** 2)
2 ** 9
512
```

### Example 2

```python
print((2 ** 3) ** 2)
```

**Output:**
```text
64
```

কারণ parentheses-এর কারণে আগে `2 ** 3` হিসাব করা হয়।

### Example 3: Negative Number

```python
print(-3 ** 2)
print((-3) ** 2)
```

**Output:**
```text
-9
9
```

ব্যাখ্যা:

```python
-3 ** 2
-(3 ** 2)
-9
```

কিন্তু:

```python
(-3) ** 2
(-3) * (-3)
9
```

তাই negative number-কে exponentiation-এর base হিসেবে নিতে চাইলে parentheses ব্যবহার করো।

---

## 7. Parentheses in Logical Expressions

Logical expressions-এ `and`, `or` ও `not` ব্যবহারের সময় parentheses condition-এর grouping স্পষ্ট করতে পারে।

### Example 1: Without Parentheses

```python
age = 20
has_id = True

print(age >= 18 and has_id)
```

**Output:**
```text
True
```

### Example 2: With Parentheses

```python
age = 16
has_permission = True

print((age >= 18) or has_permission)
```

**Output:**
```text
True
```

এখানে `age >= 18` মিথ্যা, কিন্তু `has_permission` সত্য। তাই `or` expression-এর ফল `True`।

### Example 3: Complex Condition

```python
age = 20
has_id = True
is_member = False

result = (age >= 18 and has_id) or is_member
print(result)
```

**Output:**
```text
True
```

এখানে:

- `age >= 18` সত্য।
- `has_id` সত্য।
- প্রথম group `True and True`, যার ফল `True`।
- `True or False`-এর ফল `True`।

Parentheses ব্যবহার করলে complex condition বোঝা সহজ হয়।

---

## 8. Parentheses with Comparison Operators

Comparison operator যেমন `>`, `<`, `==`, `!=` এবং `>=`-এর সঙ্গে parentheses ব্যবহার করা যায়।

### Example

```python
x = 10

print((x > 5) and (x < 20))
```

**Output:**
```text
True
```

এখানে:

```python
x > 5
```

ফল `True`, এবং:

```python
x < 20
```

ফলও `True`।

তাই:

```python
True and True
```

ফলাফল `True`।

Python-এ এটির সংক্ষিপ্ত রূপও লেখা যায়:

```python
print(5 < x < 20)
```

**Output:**
```text
True
```

এটি একটি chained comparison। সাধারণত range check করার জন্য এই রূপটি পরিষ্কার ও সুবিধাজনক।

---

## 9. Parentheses in Function Calls

Python-এ function call করার সময়ও parentheses ব্যবহার করা হয়।

### Example

```python
print("Hello Python")
```

এখানে `print()` একটি function call। Parentheses-এর ভেতরে function-এ পাঠানো argument রয়েছে।

আরেকটি উদাহরণ:

```python
def add(a, b):
    return a + b

result = add(5, 3)
print(result)
```

**Output:**
```text
8
```

এখানে `add(5, 3)` function-টিকে `5` এবং `3` argument হিসেবে পাঠায়।

খেয়াল করো, এখানে parentheses-এর কাজ শুধু calculation group করা নয়; function call-এর syntax-এর অংশ হিসেবেও এটি ব্যবহৃত হয়েছে।

---

## 10. Parentheses in Mathematical Formulas

বাস্তব সমস্যার formula Python-এ লেখার সময় parentheses calculation-এর order স্পষ্ট করে।

### Example: Average

তিনটি সংখ্যার average:

\[
\text{Average} = \frac{a+b+c}{3}
\]

Python code:

```python
a = 10
b = 20
c = 30

average = (a + b + c) / 3
print(average)
```

**Output:**
```text
20.0
```

এখানে `(a + b + c)` আগে হিসাব করা হয়েছে।

### Example: Rectangle Area

Rectangle-এর area:

\[
\text{Area} = \text{length} \times \text{width}
\]

```python
length = 10
width = 5

area = length * width
print(area)
```

**Output:**
```text
50
```

এই formula-তে parentheses প্রয়োজন নেই, কারণ multiplication-এর grouping নিয়ে কোনো ambiguity নেই।

**Best Practice:** Formula-তে parentheses তখন ব্যবহার করো, যখন grouping স্পষ্ট করা প্রয়োজন বা code পড়তে সুবিধা হয়।

---

## 11. Parentheses and Readability

Parentheses শুধু calculation নিয়ন্ত্রণের জন্য নয়; code পরিষ্কার রাখতেও সাহায্য করে।

### Less Readable

```python
result = a + b * c - d / e
```

### More Explicit

```python
result = a + (b * c) - (d / e)
```

দুটি expression-ই একই নিয়মে evaluate হবে। দ্বিতীয়টি কোন অংশগুলো আগে হিসাব হচ্ছে তা স্পষ্ট করে।

তবে অপ্রয়োজনীয় parentheses দিয়ে code অতিরিক্ত জটিল করাও উচিত নয়।

### Best Practice

- জটিল expression-এ parentheses ব্যবহার করো।
- Logical condition-এর grouping স্পষ্ট রাখো।
- Mathematical formula-তে প্রয়োজন অনুযায়ী parentheses দাও।
- Nested parentheses বেশি হলে expression-কে কয়েকটি variable-এ ভাগ করো।
- শুধু code বড় করার জন্য অপ্রয়োজনীয় parentheses ব্যবহার করো না।

---

## 12. Common Mistakes

### Mistake 1: Parentheses বাদ দেওয়া

```python
print(2 + 3 * 4)
```

Output:
```text
14
```

কিন্তু:

```python
print((2 + 3) * 4)
```

Output:
```text
20
```

### Mistake 2: Parentheses-এর ভেতরের expression-এ precedence ভুলে যাওয়া

```python
print((2 + 3 * 4))
```

Output:
```text
14
```

শুধু পুরো expression-কে parentheses-এর মধ্যে রাখলে সব operator-এর precedence সমান হয়ে যায় না।

### Mistake 3: Parentheses বন্ধ না করা

ভুল code:

```python
print((2 + 3) * 4
```

এখানে একটি closing parenthesis `)` নেই। ফলে Python `SyntaxError` দেখাবে।

সঠিক code:

```python
print((2 + 3) * 4)
```

### Mistake 4: Negative Base-এ Parentheses না দেওয়া

```python
print(-2 ** 2)
```

Output:
```text
-4
```

কিন্তু:

```python
print((-2) ** 2)
```

Output:
```text
4
```

---

## 13. Practice Exercises

প্রথমে নিজে output অনুমান করো। তারপর answer key মিলিয়ে দেখো।

### Exercise 1

```python
print((4 + 6) * 2)
```

### Exercise 2

```python
print(4 + 6 * 2)
```

### Exercise 3

```python
print(30 - (8 + 2))
```

### Exercise 4

```python
print((2 + 3) ** 2)
```

### Exercise 5

```python
print(2 ** (2 + 3))
```

### Exercise 6

```python
print((-5) ** 2)
```

### Exercise 7

```python
x = 12
print((x >= 10) and (x <= 15))
```

### Exercise 8

```python
print(((2 + 3) * (6 - 2)) / 4)
```

### Answer Key

| Exercise | Output | Explanation |
|---|---:|---|
| 1 | `20` | `(4 + 6) * 2` |
| 2 | `16` | `4 + (6 * 2)` |
| 3 | `20` | `30 - (8 + 2)` |
| 4 | `25` | `5 ** 2` |
| 5 | `32` | `2 ** 5` |
| 6 | `25` | `(-5) * (-5)` |
| 7 | `True` | দুটি condition-ই সত্য |
| 8 | `5.0` | `(5 * 4) / 4` |

---

## 14. Quick Revision

- Parentheses `()` expression-এর grouping স্পষ্ট করে।
- Parentheses-এর ভেতরের group আগে evaluate হয়।
- Parentheses-এর ভেতরেও operator precedence কার্যকর থাকে।
- Nested parentheses-এর ক্ষেত্রে সবচেয়ে ভেতরের group থেকে হিসাব শুরু করো।
- Exponentiation ও negative number-এর ক্ষেত্রে parentheses গুরুত্বপূর্ণ।
- Logical condition পরিষ্কার করতে parentheses ব্যবহার করা যায়।
- Function call-এর syntax-এও parentheses ব্যবহৃত হয়।
- Complex expression-এ parentheses code পড়তে ও বুঝতে সুবিধা দেয়।

## 15. Self-Assessment Checklist

- [ ] Parentheses কী এবং কেন ব্যবহার করা হয়, বুঝতে পারি।
- [ ] Parentheses দিয়ে calculation-এর grouping পরিবর্তন করতে পারি।
- [ ] Operator precedence ও parentheses-এর সম্পর্ক বুঝি।
- [ ] Nested parentheses-এর expression সমাধান করতে পারি।
- [ ] Exponentiation ও negative number-এর ক্ষেত্রে parentheses ব্যবহার করতে পারি।
- [ ] Logical condition-এ parentheses ব্যবহার করতে পারি।
- [ ] Parentheses-সংক্রান্ত সাধারণ `SyntaxError` শনাক্ত করতে পারি।

পরবর্তী Topic: **28. Conditional Expressions**