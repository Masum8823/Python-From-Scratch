# 11. Logical Operators in Python

## 1. Introduction to Logical Operators

Python-এ **Logical Operators** ব্যবহার করে এক বা একাধিক Condition-এর মধ্যে Logical Relationship পরীক্ষা করা হয়।

Python-এ প্রধানত তিনটি Logical Operator রয়েছে:

| Operator | কাজ | উদাহরণ |
|---|---|---|
| `and` | সব Condition True হলে True | `5 > 2 and 10 > 5` |
| `or` | অন্তত একটি Condition True হলে True | `5 < 2 or 10 > 5` |
| `not` | Result উল্টে দেয় | `not True` |

Logical Operators সাধারণত `if` Statement, Loop এবং Decision-Making Program-এ ব্যবহৃত হয়।

### Example

```python
age = 20

print(age >= 18 and age <= 60)
print(age < 18 or age > 60)
print(not age >= 18)
```

Output:

```text
True
False
False
```

ব্যাখ্যা:

- প্রথম Expression-এ দুটি Condition-ই True, তাই Result `True`।
- দ্বিতীয় Expression-এ দুটি Condition-ই False, তাই Result `False`।
- তৃতীয় Expression-এ `age >= 18` True। `not` সেটিকে False করে দেয়।

---

## 2. The `and` Operator

`and` Operator ব্যবহার করা হয় যখন একাধিক Condition-এর **সবগুলো True হওয়া প্রয়োজন**।

### Truth Table

| Condition A | Condition B | A `and` B |
|---|---|---|
| True | True | True |
| True | False | False |
| False | True | False |
| False | False | False |

সহজভাবে মনে রাখবে:

**`and` → সব Condition True হলে তবেই Result True।**

### Example 1: Basic Usage

```python
print(True and True)
print(True and False)
print(False and True)
print(False and False)
```

Output:

```text
True
False
False
False
```

### Example 2: Comparing Numbers

```python
x = 15

print(x > 10 and x < 20)
print(x > 20 and x < 30)
```

Output:

```text
True
False
```

ব্যাখ্যা:

- `x > 10` এবং `x < 20` দুটিই True, তাই প্রথম Result `True`।
- দ্বিতীয় Expression-এ `x > 20` False, তাই পুরো Result `False`।

### Example 3: Checking Age

ধরো, কোনো Website-এ Registration করার জন্য বয়স কমপক্ষে 18 এবং সর্বোচ্চ 60 হতে হবে।

```python
age = 25

if age >= 18 and age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

Output:

```text
Eligible
```

এখানে উভয় Condition পূরণ হওয়ায় User Eligible।

### Example 4: Multiple Conditions

```python
marks = 85

if marks >= 80 and marks <= 100:
    print("Excellent result")
```

Output:

```text
Excellent result
```

এখানে Marks 80 বা তার বেশি এবং 100 বা তার কম হতে হবে।

---

## 3. The `or` Operator

`or` Operator ব্যবহার করা হয় যখন একাধিক Condition-এর মধ্যে **অন্তত একটি True হলেই যথেষ্ট**।

### Truth Table

| Condition A | Condition B | A `or` B |
|---|---|---|
| True | True | True |
| True | False | True |
| False | True | True |
| False | False | False |

সহজভাবে মনে রাখবে:

**`or` → অন্তত একটি Condition True হলে Result True।**

### Example 1: Basic Usage

```python
print(True or True)
print(True or False)
print(False or True)
print(False or False)
```

Output:

```text
True
True
True
False
```

### Example 2: Comparing Numbers

```python
x = 5

print(x < 10 or x > 20)
print(x > 10 or x > 20)
```

Output:

```text
True
False
```

ব্যাখ্যা:

- প্রথম Expression-এ `x < 10` True, তাই Result `True`।
- দ্বিতীয় Expression-এ দুটি Condition-ই False, তাই Result `False`।

### Example 3: Checking Login Information

ধরো, একজন User Email অথবা Phone Number ব্যবহার করে Login করতে পারবে।

```python
email_provided = False
phone_provided = True

if email_provided or phone_provided:
    print("You can continue")
else:
    print("Provide your email or phone")
```

Output:

```text
You can continue
```

এখানে অন্তত একটি Condition True হওয়ায় User Continue করতে পারবে।

**Note:** এটি শুধু Logical Operator-এর উদাহরণ; বাস্তব Authentication-এর জন্য অতিরিক্ত Validation প্রয়োজন।

### Example 4: Weekend Checking

```python
day = "Friday"

if day == "Friday" or day == "Saturday":
    print("Weekend")
else:
    print("Working day")
```

Output:

```text
Weekend
```

এখানে দুটি Condition-এর যেকোনো একটি True হলেই `Weekend` Print হবে।

---

## 4. The `not` Operator

`not` Operator একটি Condition-এর Boolean Result উল্টে দেয়।

- `not True` → `False`
- `not False` → `True`

### Truth Table

| Condition | `not` Condition |
|---|---|
| True | False |
| False | True |

### Example 1: Basic Usage

```python
print(not True)
print(not False)
```

Output:

```text
False
True
```

### Example 2: Negating a Comparison

```python
age = 16

print(age >= 18)
print(not age >= 18)
```

Output:

```text
False
True
```

ব্যাখ্যা:

`age >= 18` False, কারণ বয়স 16। `not` এই False Result-কে True করে দেয়।

তবে সহজে বোঝার জন্য এভাবে লেখা যায়:

```python
age = 16

print(not (age >= 18))
```

Output:

```text
True
```

### Example 3: Checking Whether a User Is Not Logged In

```python
is_logged_in = False

if not is_logged_in:
    print("Please log in")
```

Output:

```text
Please log in
```

`is_logged_in` False হওয়ায় `not is_logged_in` True হয়েছে।

---

## 5. Using Multiple Logical Operators

একটি Expression-এ একাধিক Logical Operator ব্যবহার করা যায়।

### Example 1: Using `and` and `or`

```python
age = 25
has_id = True

if (age >= 18 and has_id) or age >= 60:
    print("Condition satisfied")
else:
    print("Condition not satisfied")
```

Output:

```text
Condition satisfied
```

এখানে:

1. `age >= 18` → True
2. `has_id` → True
3. `age >= 18 and has_id` → True
4. `True or False` → True

তাই `Condition satisfied` Print হয়েছে।

### Example 2: Combining Three Conditions

```python
age = 22
has_ticket = True
is_banned = False

if age >= 18 and has_ticket and not is_banned:
    print("Entry allowed")
else:
    print("Entry denied")
```

Output:

```text
Entry allowed
```

এখানে:

- বয়স 18 বা তার বেশি।
- Ticket আছে।
- User Banned নয়।

সব Condition পূরণ হওয়ায় Entry Allowed।

---

## 6. Logical Operators and Truth Values

Logical Operators শুধু `True` ও `False` নিয়েই কাজ করে না। Python-এ অন্যান্য Value-ও Logical Context-এ ব্যবহার করা যায়।

যেমন:

- `0` → Falsy
- `""` → Falsy
- `None` → Falsy
- `1` → Truthy
- `"Python"` → Truthy
- `[1, 2]` → Truthy

### Example

```python
print(bool(0))
print(bool(5))
print(bool(""))
print(bool("Python"))
```

Output:

```text
False
True
False
True
```

এখানে `bool()` ব্যবহার করে Value-গুলোকে Boolean-এ Convert করা হয়েছে।

### Using Values Directly

```python
print(0 or 10)
print(5 and 10)
print(not "")
```

Output:

```text
10
10
True
```

খেয়াল করো, প্রথম দুটি Expression-এ Result সরাসরি `True` বা `False` নয়। Python `and` ও `or`-এর ক্ষেত্রে সাধারণত Operand-এর একটি Value Return করে।

এটি পরবর্তী `Truthiness in Logical Expressions` Topic-এ বিস্তারিত আলোচনা করা হবে।

---

## 7. Logical Operators with User Input

ধরো, একটি Program User-এর বয়স এবং পরীক্ষার Marks নিয়ে Eligibility পরীক্ষা করবে।

```python
age = int(input("Enter your age: "))
marks = int(input("Enter your marks: "))

if age >= 18 and marks >= 50:
    print("You are eligible")
else:
    print("You are not eligible")
```

Example Input:

```text
Enter your age: 20
Enter your marks: 75
```

Output:

```text
You are eligible
```

ব্যাখ্যা:

- বয়স 18 বা তার বেশি।
- Marks 50 বা তার বেশি।
- দুটি Condition-ই True হওয়ায় User Eligible।

এখানে `int()` ব্যবহার করা হয়েছে, কারণ `input()` সাধারণত String Return করে।

---

## 8. Difference Between `and`, `or`, and `not`

| বিষয় | `and` | `or` | `not` |
|---|---|---|---|
| কাজ | সব Condition True কি না পরীক্ষা করে | অন্তত একটি True কি না পরীক্ষা করে | Truth Value উল্টে দেয় |
| প্রয়োজনীয় Operand | সাধারণত দুই বা বেশি | সাধারণত দুই বা বেশি | একটি |
| কখন True হয়? | সব Operand Truthy হলে | কোনো Operand Truthy হলে | Operand Falsy হলে |
| উদাহরণ | `True and False` | `True or False` | `not True` |
| Boolean Result | `False` | `True` | `False` |

**মুখস্থ করার সহজ নিয়ম:**

- `and` = সবগুলো দরকার।
- `or` = যেকোনো একটি যথেষ্ট।
- `not` = উল্টো Result।

---

## 9. Common Mistakes

### Mistake 1: Using `and` Instead of `or`

ভুল:

```python
day = "Friday"

if day == "Friday" and day == "Saturday":
    print("Weekend")
```

এখানে Condition True হবে না। কারণ একটি Variable একই সময়ে `"Friday"` এবং `"Saturday"`—দুটির সমান হতে পারে না।

সঠিক:

```python
day = "Friday"

if day == "Friday" or day == "Saturday":
    print("Weekend")
```

Output:

```text
Weekend
```

### Mistake 2: Forgetting Parentheses

একাধিক Operator ব্যবহার করলে Expression পরিষ্কার রাখতে Parentheses ব্যবহার করা ভালো।

```python
age = 20
has_id = True

if (age >= 18 and has_id) or age >= 60:
    print("Allowed")
```

Parentheses ব্যবহার করলে কোন Condition আগে একসঙ্গে Evaluate করতে চাও, তা বোঝা সহজ হয়।

### Mistake 3: Confusing `not` with `!=`

দুটির কাজ এক নয়।

```python
x = 5

print(not x == 5)
print(x != 5)
```

Output:

```text
False
False
```

এখানে Result একই হলেও:

- `not x == 5` হলো `not (x == 5)`।
- `x != 5` সরাসরি দুটি Value অসমান কি না পরীক্ষা করে।

### Mistake 4: Assuming Logical Operators Always Return Booleans

```python
print("Hello" and "Python")
print("" or "Python")
```

Output:

```text
Python
Python
```

Python-এর `and` ও `or` Operand-এর Value Return করতে পারে। তাই এগুলো সব সময় `True` বা `False` Return করে না।

---

## 10. Practice Exercises

### Basic Level

1. `True and False`-এর Result কী?
2. `True or False`-এর Result কী?
3. `not False`-এর Result কী?
4. `10 > 5 and 5 > 2`-এর Result কী?
5. `10 < 5 or 5 > 2`-এর Result কী?

### Intermediate Level

6. এমন একটি Condition লেখো যেখানে বয়স 18 বা তার বেশি এবং Marks 50 বা তার বেশি হতে হবে।
7. `not` ব্যবহার করে `is_active = False`-এর বিপরীত Boolean Result বের করো।
8. `Friday` অথবা `Saturday` হলে `Weekend` Print করার Condition লেখো।
9. `and`, `or`, `not` ব্যবহার করে তিনটি Condition মিলিয়ে একটি Eligibility Program তৈরি করো।
10. `5 and 0` এবং `5 or 0`-এর Output কী হবে?

### Output Prediction

```python
print(True and True)
print(True and False)
print(False or True)
print(not (10 < 5))
print(10 > 5 and 20 < 15)
print(10 < 5 or 20 > 15)
print(5 and 0)
print(5 or 0)
```

### Answers

```text
True
False
True
True
False
True
0
5
```

---

## 11. Chapter Summary

- Python-এ তিনটি প্রধান Logical Operator হলো `and`, `or`, এবং `not`।
- `and`-এর ক্ষেত্রে সব Operand Truthy হলে Result True হয়।
- `or`-এর ক্ষেত্রে অন্তত একটি Operand Truthy হলে Result True হয়।
- `not` Truth Value উল্টে দেয়।
- Logical Operators একাধিক Condition একত্রে পরীক্ষা করতে সাহায্য করে।
- `if` Statement-এ Eligibility, Login Status এবং অন্যান্য Decision তৈরিতে এগুলো ব্যবহৃত হয়।
- `and` ও `or` সব সময় Boolean Return করে না; তারা Operand-এর Value-ও Return করতে পারে।
- একাধিক Condition থাকলে Parentheses ব্যবহার করলে Code বোঝা সহজ হয়।

## 12. Self-Assessment Checklist

- [ ] `and` Operator-এর কাজ বুঝি।
- [ ] `or` Operator-এর কাজ বুঝি।
- [ ] `not` Operator-এর কাজ বুঝি।
- [ ] তিনটি Operator-এর Truth Table ব্যাখ্যা করতে পারি।
- [ ] একাধিক Condition একসঙ্গে ব্যবহার করতে পারি।
- [ ] Logical Operators দিয়ে Eligibility Program লিখতে পারি।
- [ ] `and` ও `or` কীভাবে Operand Return করে, তার Basic ধারণা আছে।

**Next Topic:** `12_Truthiness_in_Logical_Expressions.md`