# 15. Operator Precedence in Conditions

## 1. Operator Precedence কী?

**Operator Precedence** হলো Python-এর এমন একটি নিয়ম, যার মাধ্যমে নির্ধারিত হয় একটি expression-এর মধ্যে একাধিক operator থাকলে কোন operator আগে কাজ করবে।

সহজভাবে বললে, একটি condition-এর মধ্যে `not`, `and`, `or` একসঙ্গে থাকলে Python নিজের নির্দিষ্ট নিয়ম অনুসারে expression evaluate করে।

উদাহরণ:

```python
result = True or False and False
print(result)
```

Output:

```text
True
```

কেন `True` হলো?

কারণ Python-এ `and` operator-এর precedence, `or`-এর চেয়ে বেশি। তাই প্রথমে:

```python
False and False
```

এর result হবে `False`।

তারপর expression হবে:

```python
True or False
```

এর result হবে `True`।

সুতরাং final output:

```text
True
```

## 2. Conditional Statements-এ Operator Precedence কেন গুরুত্বপূর্ণ?

একটি condition-এ একাধিক operator থাকলে precedence না বুঝে output ভুল predict করা হতে পারে।

উদাহরণ:

```python
age = 20
has_id = False

if age >= 18 and has_id or age >= 21:
    print("Allowed")
else:
    print("Not allowed")
```

Output:

```text
Not allowed
```

এখানে Python প্রথমে comparison operators evaluate করবে:

```python
age >= 18  # True
age >= 21  # False
```

তারপর `and` আগে evaluate হবে:

```python
True and False  # False
```

সবশেষে `or` evaluate হবে:

```python
False or False  # False
```

তাই `else` block execute হবে।

**মনে রাখবে:** Condition-এ operator-এর order না বুঝলে program-এর logic ভুল হতে পারে।

## 3. Python-এ Conditional Operators-এর Precedence

নিচের তালিকাটি সাধারণ precedence-এর ক্রম দেখায়। তালিকার উপরের operator-এর precedence নিচের operator-এর চেয়ে বেশি।

| Priority | Operator | কাজ |
|---|---|---|
| 1 | `()` | Expression group করা |
| 2 | Arithmetic operators: `**`, `*`, `/`, `//`, `%`, `+`, `-` | গাণিতিক হিসাব |
| 3 | Comparison operators: `<`, `>`, `<=`, `>=`, `==`, `!=` | তুলনা করা |
| 4 | Membership: `in`, `not in` | কোনো item আছে কি না |
| 5 | Identity: `is`, `is not` | একই object কি না |
| 6 | `not` | Logical NOT |
| 7 | `and` | Logical AND |
| 8 | `or` | Logical OR |

**Note:** Comparison, membership ও identity operators একই precedence level-এ থাকে এবং chained comparison-এর নিজস্ব নিয়ম আছে। উপরের তালিকাটি শেখার সুবিধার জন্য সাজানো হয়েছে।

সবচেয়ে গুরুত্বপূর্ণ তিনটি নিয়ম:

1. `not` আগে evaluate হয়।
2. `and`, `or`-এর আগে evaluate হয়।
3. Parentheses `()` ব্যবহার করে evaluation-এর order স্পষ্ট করা যায়।

## 4. `not`, `and` এবং `or`-এর Precedence

এই তিনটি operator-এর precedence:

```text
not  >  and  >  or
```

এখানে `>` চিহ্নের অর্থ হলো precedence বেশি।

উদাহরণ:

```python
a = True
b = False
c = False

print(a or b and c)
```

Output:

```text
True
```

ব্যাখ্যা:

প্রথমে `and`:

```python
b and c
# False
```

তারপর `or`:

```python
a or False
# True
```

আরেকটি উদাহরণ:

```python
a = True
b = False

print(not a or b)
```

Output:

```text
False
```

কারণ:

```python
not a       # False
False or b  # False
```

## 5. Parentheses ব্যবহার করে Precedence নিয়ন্ত্রণ

Parentheses বা `()` ব্যবহার করে expression-এর কোন অংশ আগে evaluate হবে, তা নির্দিষ্ট করা যায়।

উদাহরণ:

```python
print(True or False and False)
print((True or False) and False)
```

Output:

```text
True
False
```

প্রথম expression-এ `and` আগে evaluate হয়:

```python
True or (False and False)
# True
```

দ্বিতীয় expression-এ parentheses-এর ভেতরের অংশ আগে evaluate হয়:

```python
(True or False) and False
# True and False
# False
```

তাই output আলাদা হয়েছে।

**Best practice:** Condition জটিল হলে parentheses ব্যবহার করো। এতে code পড়া এবং logic বোঝা সহজ হয়।

## 6. Comparison Operators আগে, Logical Operators পরে

সাধারণত comparison operators, `not`, `and` ও `or`-এর আগে evaluate হয়।

উদাহরণ:

```python
age = 20

print(age >= 18 and age <= 30)
```

Output:

```text
True
```

প্রথমে comparisons:

```python
age >= 18  # True
age <= 30  # True
```

তারপর:

```python
True and True
# True
```

এবার আরেকটি উদাহরণ:

```python
x = 10

print(x > 5 or x < 3 and x == 10)
```

Output:

```text
True
```

প্রথমে comparisons:

```python
x > 5   # True
x < 3   # False
x == 10 # True
```

এরপর `and`:

```python
False and True
# False
```

সবশেষে `or`:

```python
True or False
# True
```

## 7. `not` এবং Comparison Operator-এর Precedence

এটি খুব গুরুত্বপূর্ণ একটি বিষয়।

Python-এ:

```python
not a == b
```

এর অর্থ:

```python
not (a == b)
```

এটির অর্থ কিন্তু নিচের expression নয়:

```python
(not a) == b
```

উদাহরণ:

```python
a = 5
b = 5

print(not a == b)
print(not (a == b))
```

Output:

```text
False
False
```

কারণ `a == b` হলো `True`, আর `not True` হলো `False`।

আরেকটি উদাহরণ:

```python
a = 5
b = 10

print(not a == b)
```

Output:

```text
True
```

কারণ `a == b` হলো `False`; তাই `not False` হলো `True`।

**মনে রাখবে:** `not a == b`-এর বদলে `a != b` লিখলে অনেক সময় condition আরও পরিষ্কার হয়।

## 8. `and` এবং `or` একসঙ্গে ব্যবহার

যখন একই condition-এ `and` ও `or` থাকে, তখন `and` আগে evaluate হয়।

উদাহরণ:

```python
age = 20
has_permission = False

if age >= 18 and has_permission or age >= 25:
    print("Access granted")
else:
    print("Access denied")
```

Output:

```text
Access denied
```

ব্যাখ্যা:

```python
age >= 18       # True
has_permission  # False
age >= 25       # False
```

এরপর:

```python
True and False  # False
False or False  # False
```

তাই `else` execute হবে।

এবার parentheses ব্যবহার করলে:

```python
if age >= 18 and (has_permission or age >= 25):
    print("Access granted")
else:
    print("Access denied")
```

Output:

```text
Access denied
```

এখানে আগে parentheses-এর ভেতরের অংশ evaluate হয়:

```python
False or False  # False
True and False  # False
```

এই উদাহরণে দুই ক্ষেত্রেই output একই হলেও, অন্য values ব্যবহার করলে parentheses-এর কারণে result আলাদা হতে পারে।

## 9. Practical Example: Login Validation

```python
username = "admin"
password = "1234"
is_blocked = False

if username == "admin" and password == "1234" and not is_blocked:
    print("Login successful")
else:
    print("Login failed")
```

Output:

```text
Login successful
```

ব্যাখ্যা:

- `username == "admin"` → `True`
- `password == "1234"` → `True`
- `not is_blocked` → `True`

সবগুলো condition `and` দিয়ে যুক্ত করা হয়েছে। তাই সব condition `True` হওয়ায় login successful হয়েছে।

## 10. Practical Example: Discount Eligibility

একটি দোকানে customer-এর বয়স ১৮ বছরের কম অথবা membership থাকলে discount দেওয়া হবে।

```python
age = 16
has_membership = False

if age < 18 or has_membership:
    print("Discount available")
else:
    print("No discount")
```

Output:

```text
Discount available
```

কারণ:

```python
age < 18        # True
has_membership  # False

True or False   # True
```

এখানে `or`-এর যেকোনো একটি condition `True` হলেই পুরো expression `True` হবে।

## 11. Common Mistakes

### Mistake 1: `and` ও `or`-এর precedence ভুলে যাওয়া

ভুল ধারণা:

```python
True or False and False
```

এর result `False` মনে করা।

সঠিক output:

```text
True
```

কারণ `and` আগে evaluate হয়।

### Mistake 2: Parentheses ছাড়া জটিল condition লেখা

```python
if age >= 18 and has_id or is_admin:
    print("Allowed")
```

Python-এর নিয়ম অনুযায়ী এটি:

```python
if (age >= 18 and has_id) or is_admin:
    print("Allowed")
```

যদি তোমার intended logic আলাদা হয়, তাহলে parentheses দিয়ে সেটি স্পষ্ট করো।

### Mistake 3: `not`-এর precedence ভুল বোঝা

```python
not age == 18
```

এটি `not (age == 18)` হিসেবে evaluate হয়।

বেশিরভাগ ক্ষেত্রে value inequality বোঝাতে নিচের expression আরও পরিষ্কার:

```python
age != 18
```

### Mistake 4: Condition অতিরিক্ত জটিল করে ফেলা

অতিরিক্ত operator একটি লাইনে লিখলে debugging কঠিন হতে পারে।

অস্পষ্ট:

```python
if age >= 18 and has_id or is_admin and not is_blocked:
    print("Allowed")
```

আরও পরিষ্কার:

```python
is_adult_with_id = age >= 18 and has_id
is_admin_allowed = is_admin and not is_blocked

if is_adult_with_id or is_admin_allowed:
    print("Allowed")
```

এভাবে intermediate Boolean variables ব্যবহার করলে logic বোঝা সহজ হয়।

## 12. Practice Exercises

প্রতিটি প্রশ্নের output নিজে বের করার চেষ্টা করো। তারপর Answer Key মিলিয়ে দেখো।

### Question 1

```python
print(True or False and False)
```

### Question 2

```python
print((True or False) and False)
```

### Question 3

```python
print(not True or True)
```

### Question 4

```python
x = 10
print(x > 5 and x < 20 or x == 0)
```

### Question 5

```python
x = 5
print(not x == 5)
```

### Question 6

```python
age = 17
has_permission = True

print(age >= 18 and has_permission)
```

### Question 7

```python
a = False
b = True
c = False

print(a or b and c)
```

### Question 8

```python
x = 8

if x > 5 and (x < 10 or x == 20):
    print("A")
else:
    print("B")
```

## 13. Answer Key

### Answer 1

Output:

```text
True
```

কারণ `and` আগে evaluate হয়।

### Answer 2

Output:

```text
False
```

কারণ parentheses-এর result `True`, এরপর `True and False` হলো `False`।

### Answer 3

Output:

```text
True
```

প্রথমে `not True` হলো `False`; এরপর `False or True` হলো `True`।

### Answer 4

Output:

```text
True
```

`x > 5` এবং `x < 20` দুটিই `True`; তাই `and`-এর result `True`।

### Answer 5

Output:

```text
False
```

কারণ `x == 5` হলো `True`; `not True` হলো `False`।

### Answer 6

Output:

```text
False
```

কারণ `age >= 18` হলো `False`। `and`-এর ক্ষেত্রে উভয় condition `True` হতে হয়।

### Answer 7

Output:

```text
False
```

প্রথমে `b and c` → `True and False` → `False`। এরপর `a or False` → `False or False` → `False`।

### Answer 8

Output:

```text
A
```

কারণ `x > 5` হলো `True`, এবং parentheses-এর ভেতরে `x < 10` হলো `True`। ফলে পুরো condition `True`।

## 14. Quick Revision

- **Operator Precedence:** কোন operator আগে evaluate হবে, সেই নিয়ম।
- **`not` > `and` > `or`:** Logical operators-এর precedence মনে রাখার সহজ নিয়ম।
- **Comparison আগে:** `age >= 18`-এর মতো comparison, logical `not`, `and`, `or`-এর আগে evaluate হয়।
- **Parentheses:** `()` ব্যবহার করে evaluation order স্পষ্ট করা যায়।
- **`not a == b`:** এর অর্থ `not (a == b)`।
- **Readable code:** জটিল condition-এ parentheses বা Boolean variables ব্যবহার করো।

## 15. Self-Assessment Checklist

- [ ] Operator Precedence কী, তা বুঝতে পারি।
- [ ] `not`, `and` ও `or`-এর precedence বলতে পারি।
- [ ] Comparison ও logical operators-এর evaluation order বুঝি।
- [ ] Parentheses ব্যবহার করে condition-এর order নিয়ন্ত্রণ করতে পারি।
- [ ] জটিল condition-এর output predict করতে পারি।
- [ ] প্রয়োজন হলে condition-কে ছোট ও readable অংশে ভাগ করতে পারি।

**পরবর্তী টপিক:** `16_Truthiness_and_Falsy_Values.md`
