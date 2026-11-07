# 11. Logical Operators in Conditions

## 1. Introduction

Python-এ একাধিক condition একসঙ্গে পরীক্ষা করার জন্য **Logical Operators** ব্যবহার করা হয়।

Python-এর প্রধান তিনটি logical operator হলো:

| Operator | কাজ |
|---|---|
| `and` | সব condition সত্য হলে ফলাফল সত্য |
| `or` | অন্তত একটি condition সত্য হলে ফলাফল সত্য |
| `not` | condition-এর ফলাফল উল্টে দেয় |

Example:

```python
age = 20
has_id = True

if age >= 18 and has_id:
    print("Entry allowed")
```

Output:

```text
Entry allowed
```

এখানে `age >= 18` এবং `has_id` — দুটি condition-ই সত্য। তাই message print হয়েছে।

## 2. The `and` Operator

`and` operator ব্যবহার করা হয় যখন **সব condition সত্য হওয়া প্রয়োজন**।

Example:

```python
age = 22
has_id = True

if age >= 18 and has_id:
    print("Eligible")
else:
    print("Not eligible")
```

Output:

```text
Eligible
```

কারণ:

- `age >= 18` → `True`
- `has_id` → `True`
- `True and True` → `True`

### Truth Table of `and`

| Condition 1 | Condition 2 | Result |
|---|---|---|
| `True` | `True` | `True` |
| `True` | `False` | `False` |
| `False` | `True` | `False` |
| `False` | `False` | `False` |

**মনে রাখবে:** `and`-এর ক্ষেত্রে একটি condition-ও `False` হলে পুরো combination মিথ্যা হয়।

### Example: Exam Eligibility

```python
attendance = 85
marks = 60

if attendance >= 75 and marks >= 40:
    print("Exam requirements satisfied")
else:
    print("Requirements not satisfied")
```

Output:

```text
Exam requirements satisfied
```

এখানে attendance কমপক্ষে 75 এবং marks কমপক্ষে 40 — দুটি শর্তই পূরণ হয়েছে।

## 3. The `or` Operator

`or` operator ব্যবহার করা হয় যখন **অন্তত একটি condition সত্য হলেই যথেষ্ট**।

Example:

```python
is_student = False
is_teacher = True

if is_student or is_teacher:
    print("Access granted")
else:
    print("Access denied")
```

Output:

```text
Access granted
```

কারণ `is_teacher` সত্য। `or`-এর জন্য একটি condition সত্য হওয়াই যথেষ্ট।

### Truth Table of `or`

| Condition 1 | Condition 2 | Result |
|---|---|---|
| `True` | `True` | `True` |
| `True` | `False` | `True` |
| `False` | `True` | `True` |
| `False` | `False` | `False` |

**মনে রাখবে:** `or`-এর ক্ষেত্রে সব condition মিথ্যা হলেই শুধু ফলাফল মিথ্যা হয়।

### Example: Discount Eligibility

```python
is_member = False
purchase_amount = 6000

if is_member or purchase_amount >= 5000:
    print("Discount available")
else:
    print("No discount")
```

Output:

```text
Discount available
```

এখানে customer member নয়, কিন্তু purchase amount 5000 বা তার বেশি। তাই দ্বিতীয় condition সত্য এবং discount পাওয়া যাবে।

## 4. The `not` Operator

`not` operator একটি condition-এর ফলাফল উল্টে দেয়।

| Original value | After `not` |
|---|---|
| `True` | `False` |
| `False` | `True` |

Example:

```python
is_raining = False

if not is_raining:
    print("You can go outside")
else:
    print("Take an umbrella")
```

Output:

```text
You can go outside
```

এখানে `is_raining`-এর value `False`। তাই `not is_raining` হয় `True`।

### Example: Checking a Blocked Account

```python
is_blocked = False

if not is_blocked:
    print("Account is active")
else:
    print("Account is blocked")
```

Output:

```text
Account is active
```

এখানে account blocked নয়, তাই `not is_blocked` সত্য।

## 5. Using Multiple Logical Operators

একটি condition-এর মধ্যে একাধিক logical operator ব্যবহার করা যায়।

Example:

```python
age = 25
has_id = True
is_blocked = False

if age >= 18 and has_id and not is_blocked:
    print("Access granted")
else:
    print("Access denied")
```

Output:

```text
Access granted
```

এখানে তিনটি বিষয় পরীক্ষা করা হয়েছে:

1. বয়স কমপক্ষে 18 কি না।
2. পরিচয়পত্র আছে কি না।
3. Account blocked নয় কি না।

সব শর্ত পূরণ হওয়ায় access granted হয়েছে।

### Example: Scholarship Eligibility

```python
cgpa = 3.85
is_regular_student = True
has_disciplinary_issue = False

if cgpa >= 3.75 and is_regular_student and not has_disciplinary_issue:
    print("Eligible for scholarship")
else:
    print("Not eligible for scholarship")
```

Output:

```text
Eligible for scholarship
```

এই উদাহরণে scholarship-এর শর্তগুলো demonstration-এর জন্য দেওয়া হয়েছে। বাস্তব scholarship-এর নিয়ম আলাদা হতে পারে।

## 6. Combining Conditions with Parentheses

একাধিক `and` এবং `or` ব্যবহার করলে parentheses `()` দিয়ে condition-এর grouping স্পষ্ট করা যায়।

Example:

```python
age = 17
has_permission = True

if age >= 18 or (age >= 16 and has_permission):
    print("Entry allowed")
else:
    print("Entry denied")
```

Output:

```text
Entry allowed
```

কারণ:

- `age >= 18` → `False`
- `age >= 16` → `True`
- `has_permission` → `True`
- `age >= 16 and has_permission` → `True`
- `False or True` → `True`

Parentheses condition পড়তে ও বোঝতে সহজ করে।

### Another Example

```python
marks = 85
attendance = 60

if marks >= 80 and attendance >= 75 or marks >= 90:
    print("Qualified")
else:
    print("Not qualified")
```

এখানে `and` operator-এর precedence `or`-এর চেয়ে বেশি। তাই Python condition-টিকে এভাবে মূল্যায়ন করে:

```python
if (marks >= 80 and attendance >= 75) or marks >= 90:
```

Output:

```text
Not qualified
```

কারণ প্রথম group মিথ্যা এবং `marks >= 90`-ও মিথ্যা।

**Best practice:** জটিল condition-এ parentheses ব্যবহার করে নিজের intended logic স্পষ্ট করে দাও।

## 7. Logical Operators with Comparison Operators

Logical operators সাধারণত comparison operators-এর সঙ্গে ব্যবহার করা হয়।

| Comparison | Meaning |
|---|---|
| `age >= 18` | বয়স কমপক্ষে 18 |
| `marks >= 40` | Marks কমপক্ষে 40 |
| `temperature > 30` | Temperature 30-এর বেশি |
| `username == "admin"` | Username admin-এর সমান |
| `amount != 0` | Amount শূন্য নয় |

Example:

```python
marks = 75
attendance = 80

if marks >= 40 and attendance >= 75:
    print("Passed and attendance requirement met")
```

Output:

```text
Passed and attendance requirement met
```

এখানে দুটি comparison-এর ফলাফল `and` দিয়ে combine করা হয়েছে।

## 8. Logical Operators with User Input

User input দিয়ে condition পরীক্ষা করার সময় logical operators অনেক কাজে লাগে।

Example:

```python
age = int(input("Enter your age: "))

if age >= 18 and age <= 60:
    print("Age is within the range")
else:
    print("Age is outside the range")
```

Sample Input:

```text
Enter your age: 25
```

Output:

```text
Age is within the range
```

এই condition-টি আরও সংক্ষেপে লেখা যায়:

```python
if 18 <= age <= 60:
    print("Age is within the range")
```

Python-এর chained comparison ব্যবহার করে range check করা অনেক সময় বেশি readable হয়।

## 9. Logical Operators with Strings

Strings-এর সঙ্গেও logical operators ব্যবহার করা যায়।

Example:

```python
username = input("Enter username: ")

if username == "admin" or username == "manager":
    print("Authorized user")
else:
    print("Unauthorized user")
```

Sample Input:

```text
Enter username: manager
```

Output:

```text
Authorized user
```

এখানে username দুটি অনুমোদিত value-এর যেকোনো একটির সমান হলেই condition সত্য হয়।

### Checking an Empty String

```python
name = input("Enter your name: ")

if not name:
    print("Name cannot be empty")
else:
    print("Hello", name)
```

এখানে empty string `""` একটি falsy value। তাই `not name` সত্য হয় যখন `name` empty থাকে।

তবে শুধু whitespace দেওয়া হলে string empty হয় না। সেটিও খালি হিসেবে ধরতে চাইলে:

```python
name = input("Enter your name: ").strip()

if not name:
    print("Name cannot be empty")
else:
    print("Hello", name)
```

`.strip()` string-এর শুরু ও শেষের whitespace সরিয়ে দেয়।

## 10. Truthiness and Logical Operators

Python-এ logical operators শুধু `True` ও `False` নিয়েই কাজ করে না; অনেক ক্ষেত্রে তারা operand-এর আসল value-ও return করে।

সাধারণ falsy values:

- `False`
- `None`
- `0`
- `0.0`
- `""`
- `[]`
- `{}`
- `set()`

সাধারণত non-empty string ও collection truthy হয়।

Example:

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

### Important Difference

```python
print(5 and 3)
print(0 and 3)
print(0 or 3)
print("" or "Python")
```

Output:

```text
3
0
3
Python
```

কারণ:

- `and` প্রথম falsy operand পেলে সেটি return করে; সব truthy হলে শেষ operand return করে।
- `or` প্রথম truthy operand return করে; সব falsy হলে শেষ operand return করে।
- `not` সবসময় Boolean value (`True` বা `False`) return করে।

তাই logical expression-এর result সবসময় Boolean হবে—এমন ধরে নেওয়া যাবে না।

## 11. Short-Circuit Evaluation

Python-এর `and` এবং `or` operator **short-circuit evaluation** ব্যবহার করে। অর্থাৎ ফলাফল নির্ধারণ করা সম্ভব হলে বাকি condition আর পরীক্ষা করা হয় না।

### Short-Circuit with `and`

```python
x = 0

if x != 0 and 10 / x > 1:
    print("Condition is true")
else:
    print("Condition is false")
```

Output:

```text
Condition is false
```

এখানে `x != 0` মিথ্যা। তাই Python দ্বিতীয় condition `10 / x > 1` পরীক্ষা করে না। ফলে division by zero error হয় না।

### Short-Circuit with `or`

```python
x = 10

if x > 0 or 10 / 0 > 1:
    print("Condition is true")
```

Output:

```text
Condition is true
```

প্রথম condition সত্য হওয়ায় Python দ্বিতীয় অংশটি পরীক্ষা করে না।

**মনে রাখবে:**

- `False and ...` হলে পরের অংশ evaluate করার প্রয়োজন হয় না।
- `True or ...` হলে পরের অংশ evaluate করার প্রয়োজন হয় না।

এটি performance এবং কিছু ক্ষেত্রে error এড়ানোর জন্য গুরুত্বপূর্ণ।

## 12. Common Mistakes

### Mistake 1: Writing `and` Instead of `or`

```python
age = 20

if age < 13 and age > 19:
    print("Teenager")
```

এই condition কখনোই সত্য হতে পারে না। একই সংখ্যার জন্য বয়স একই সঙ্গে 13-এর কম এবং 19-এর বেশি হতে পারে না।

Correct:

```python
if age >= 13 and age <= 19:
    print("Teenager")
```

অথবা:

```python
if 13 <= age <= 19:
    print("Teenager")
```

### Mistake 2: Repeating a Comparison Incorrectly

Incorrect:

```python
if age == 18 or 21:
    print("Allowed")
```

এটি সঠিকভাবে দুইটি বয়স পরীক্ষা করে না। `21` একটি truthy value, তাই condition সবসময় সত্য হবে।

Correct:

```python
if age == 18 or age == 21:
    print("Allowed")
```

### Mistake 3: Incorrect Use of `not`

```python
is_active = True

if not is_active:
    print("Inactive")
else:
    print("Active")
```

এখানে `not is_active` মিথ্যা, তাই `Active` print হয়। `not` condition-এর ফলাফল উল্টে দেয়।

### Mistake 4: Forgetting Operator Precedence

```python
if a or b and c:
    print("Yes")
```

এখানে `and` আগে evaluate হয়। Condition-টি এমন:

```python
if a or (b and c):
```

Intended logic ভিন্ন হলে parentheses ব্যবহার করো।

### Mistake 5: Assuming `and` and `or` Always Return Booleans

```python
print("Hello" and "Python")
```

Output:

```text
Python
```

এটি `True` print করে না। কারণ `and` এখানে শেষ truthy operand return করেছে।

## 13. Practical Problem-Solving Examples

### Example 1: Number Range

```python
number = int(input("Enter a number: "))

if number >= 1 and number <= 100:
    print("Number is within range")
else:
    print("Number is outside range")
```

### Example 2: Free Delivery

```python
purchase = float(input("Enter purchase amount: "))
is_member = input("Are you a member? (yes/no): ").strip().lower()

if purchase >= 3000 or is_member == "yes":
    print("Free delivery")
else:
    print("Delivery charge applies")
```

### Example 3: Valid Username

```python
username = input("Enter username: ").strip()

if username and len(username) >= 4:
    print("Username accepted")
else:
    print("Username must contain at least 4 characters")
```

এখানে প্রথমে `username` empty কি না পরীক্ষা হয়। Empty হলে `and` short-circuit করে, তাই `len(username) >= 4` আর evaluate করা হয় না।

### Example 4: Weekend Check

```python
day = input("Enter day: ").strip().lower()

if day == "friday" or day == "saturday":
    print("Weekend")
else:
    print("Regular day")
```

এই example-এ Friday ও Saturday-কে weekend হিসেবে ধরা হয়েছে; এটি স্থানীয় calendar-এর উদাহরণ।

## 14. Practice Exercises

নিজে solve করার চেষ্টা করো।

### Exercise 1: Driving Eligibility

বয়স 18 বা তার বেশি এবং driving license আছে—এমন হলে `Can drive` print করো। অন্যথায় `Cannot drive` print করো।

### Exercise 2: Number Range

একটি integer input নাও। Number 10 থেকে 50-এর মধ্যে, দুই প্রান্তসহ, থাকলে `Within range` print করো।

### Exercise 3: Discount

একজন customer member হলে অথবা purchase amount 5000 বা তার বেশি হলে `Discount available` print করো।

### Exercise 4: Using `not`

একটি Boolean variable `is_logged_in` তৈরি করো। User logged in না থাকলে `Please log in` print করো।

### Exercise 5: Output Prediction

```python
a = True
b = False

print(a and b)
print(a or b)
print(not b)
```

Output কী হবে?

### Exercise 6: Output Prediction

```python
print(0 or 10)
print(5 and 8)
print("" or "Hello")
print(not [])
```

Output কী হবে?

### Exercise 7: Fix the Code

```python
age = 20

if age == 18 or 21:
    print("Allowed")
```

Condition-টি ঠিক করো, যেন শুধু বয়স 18 অথবা 21 হলে `Allowed` print হয়।

### Exercise 8: Student Eligibility

একটি student-এর marks এবং attendance input নাও। Marks কমপক্ষে 40 এবং attendance কমপক্ষে 75 হলে `Eligible` print করো। অন্যথায় `Not eligible` print করো।

## 15. Practice Answer Key

### Answer 1

```python
age = int(input("Enter age: "))
has_license = input("Do you have a license? (yes/no): ").strip().lower()

if age >= 18 and has_license == "yes":
    print("Can drive")
else:
    print("Cannot drive")
```

### Answer 2

```python
number = int(input("Enter a number: "))

if 10 <= number <= 50:
    print("Within range")
else:
    print("Outside range")
```

### Answer 3

```python
is_member = input("Are you a member? (yes/no): ").strip().lower()
amount = float(input("Enter purchase amount: "))

if is_member == "yes" or amount >= 5000:
    print("Discount available")
else:
    print("No discount")
```

### Answer 4

```python
is_logged_in = False

if not is_logged_in:
    print("Please log in")
```

### Answer 5

```text
False
True
True
```

### Answer 6

```text
10
8
Hello
True
```

### Answer 7

```python
age = 20

if age == 18 or age == 21:
    print("Allowed")
```

### Answer 8

```python
marks = float(input("Enter marks: "))
attendance = float(input("Enter attendance: "))

if marks >= 40 and attendance >= 75:
    print("Eligible")
else:
    print("Not eligible")
```

## 16. Chapter Summary

- `and`: সব condition সত্য হলে result সত্য।
- `or`: অন্তত একটি condition সত্য হলে result সত্য।
- `not`: condition-এর truth value উল্টে দেয়।
- একাধিক condition combine করে complex decision নেওয়া যায়।
- Parentheses দিয়ে condition-এর grouping স্পষ্ট করা যায়।
- `and` এবং `or` short-circuit evaluation ব্যবহার করে।
- Logical operators operand-এর actual value return করতে পারে; শুধু `not` সবসময় Boolean return করে।
- Range checking-এর জন্য chained comparison, যেমন `10 <= number <= 50`, ব্যবহার করা যায়।
- Condition লেখার সময় `and`, `or` ও `not` সঠিকভাবে নির্বাচন করা জরুরি।

## 17. Self-Assessment Checklist

- [ ] `and`, `or` এবং `not`-এর কাজ ব্যাখ্যা করতে পারি।
- [ ] Logical operators-এর truth table মনে আছে।
- [ ] একাধিক condition combine করতে পারি।
- [ ] `and` ও `or`-এর precedence বুঝি।
- [ ] Parentheses ব্যবহার করে condition স্পষ্ট করতে পারি।
- [ ] Short-circuit evaluation ব্যাখ্যা করতে পারি।
- [ ] Logical operators-এর সঙ্গে user input ব্যবহার করতে পারি।
- [ ] `and` ও `or` সবসময় Boolean return করে না—এটি বুঝি।

## 18. Next Topic

পরবর্তী file:

`12_Combining_Conditions_with_and.md`

সেখানে `and` operator-এর ব্যবহার, truth table, range checking, বাস্তব উদাহরণ এবং practice problems আরও বিস্তারিতভাবে শেখা হবে।