# 13. Combining Conditions with `or`

## 1. Introduction

Python-এ `or` operator ব্যবহার করে একাধিক condition একসঙ্গে পরীক্ষা করা যায়।

যখন একাধিক condition-এর মধ্যে **অন্তত একটি সত্য হলেই যথেষ্ট**, তখন `or` ব্যবহার করা হয়।

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

এখানে `is_student` মিথ্যা হলেও `is_teacher` সত্য। তাই `or` expression-এর ফলাফল সত্য হয়েছে।

**মনে রাখবে:** `or`-এর ক্ষেত্রে সব condition মিথ্যা হলেই শুধু পুরো expression মিথ্যা হয়।

## 2. Syntax of `or`

```python
if condition_1 or condition_2:
    # Executes when at least one condition is true
    statement
```

তিনটি বা তার বেশি condition-ও combine করা যায়:

```python
if condition_1 or condition_2 or condition_3:
    statement
```

এখানে যেকোনো একটি condition সত্য হলেই `statement` execute হবে।

Example:

```python
day = "Friday"

if day == "Friday" or day == "Saturday" or day == "Sunday":
    print("Holiday")
else:
    print("Regular day")
```

Output:

```text
Holiday
```

এই উদাহরণে Friday, Saturday এবং Sunday-কে holiday হিসেবে ধরা হয়েছে।

## 3. Truth Table of `or`

`or` operator-এর truth table:

| Condition 1 | Condition 2 | Result |
|---|---|---|
| `True` | `True` | `True` |
| `True` | `False` | `True` |
| `False` | `True` | `True` |
| `False` | `False` | `False` |

### সহজে মনে রাখার নিয়ম

`or` মানে **অন্তত একটি condition সত্য হলেই result সত্য**।

Example:

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

## 4. Combining Comparison Conditions with `or`

`or` সাধারণত comparison operators-এর সঙ্গে ব্যবহার করা হয়।

Example:

```python
marks = 85

if marks < 40 or marks > 100:
    print("Invalid marks")
else:
    print("Valid marks")
```

Output:

```text
Valid marks
```

এখানে marks 40-এর কম নয় এবং 100-এর বেশি নয়। তাই দুটি condition-ই মিথ্যা।

অন্যদিকে, marks `120` হলে `marks > 100` সত্য হবে। ফলে `Invalid marks` print হবে।

### আরেকটি উদাহরণ

```python
temperature = 38

if temperature < 10 or temperature > 35:
    print("Temperature is outside the normal range")
else:
    print("Temperature is within the range")
```

Output:

```text
Temperature is outside the normal range
```

এখানে temperature 35-এর বেশি হওয়ায় দ্বিতীয় condition সত্য হয়েছে।

এই range-টি শুধু উদাহরণ; বাস্তব ক্ষেত্রে স্বাভাবিক temperature-এর সীমা প্রসঙ্গ অনুযায়ী নির্ধারণ করতে হবে।

## 5. Checking Multiple Accepted Values

কোনো variable-এর একাধিক গ্রহণযোগ্য value থাকলে `or` ব্যবহার করা যায়।

Example:

```python
day = input("Enter a day: ").strip().lower()

if day == "friday" or day == "saturday":
    print("Weekend")
else:
    print("Regular day")
```

Sample Input:

```text
Enter a day: Saturday
```

Output:

```text
Weekend
```

এখানে input-কে lowercase করা হয়েছে, তাই `Saturday`, `SATURDAY` এবং `saturday` একইভাবে পরীক্ষা করা যাবে।

### Alternative: Using Membership Operator

অনেকগুলো value পরীক্ষা করতে `in` operator ব্যবহার করলে code আরও সংক্ষিপ্ত হতে পারে।

```python
day = input("Enter a day: ").strip().lower()

if day in ("friday", "saturday"):
    print("Weekend")
else:
    print("Regular day")
```

দুটি version-ই একই উদ্দেশ্য পূরণ করে।

## 6. Using `or` with User Input

User input-এর একাধিক গ্রহণযোগ্য option পরীক্ষা করতে `or` ব্যবহার করা যায়।

Example:

```python
choice = input("Enter yes or y: ").strip().lower()

if choice == "yes" or choice == "y":
    print("You selected yes")
else:
    print("You did not select yes")
```

Sample Input:

```text
Enter yes or y: Y
```

Output:

```text
You selected yes
```

এখানে `lower()` ব্যবহারের কারণে uppercase `Y`-ও গ্রহণযোগ্য হয়েছে।

## 7. Practical Example: Discount Eligibility

ধরা যাক, customer member হলে অথবা purchase amount কমপক্ষে 5000 টাকা হলে discount পাবে।

```python
is_member = input("Are you a member? (yes/no): ").strip().lower()
amount = float(input("Enter purchase amount: "))

if is_member == "yes" or amount >= 5000:
    print("Discount available")
else:
    print("No discount")
```

Sample Input:

```text
Are you a member? (yes/no): no
Enter purchase amount: 6000
```

Output:

```text
Discount available
```

Customer member নয়, কিন্তু purchase amount 5000 বা তার বেশি। তাই `or` expression সত্য হয়েছে।

### কখন discount পাওয়া যাবে?

| Member? | Purchase amount | Discount? |
|---|---:|---|
| Yes | 2000 | Yes |
| No | 6000 | Yes |
| Yes | 6000 | Yes |
| No | 2000 | No |

এখানে member হওয়া অথবা নির্দিষ্ট পরিমাণ কেনাকাটা করা—যেকোনো একটি শর্ত পূরণ হলেই discount পাওয়া যাবে।

## 8. Practical Example: Access Permission

ধরা যাক, student অথবা teacher—যেকোনো একজন অনুমোদিত user হলে access দেওয়া হবে।

```python
role = input("Enter your role: ").strip().lower()

if role == "student" or role == "teacher":
    print("Access granted")
else:
    print("Access denied")
```

Sample Input:

```text
Enter your role: teacher
```

Output:

```text
Access granted
```

এখানে role দুটি অনুমোদিত value-এর যেকোনো একটির সমান হলেই condition সত্য হয়।

বাস্তব application-এ শুধু role-এর নাম input হিসেবে গ্রহণ করাই যথেষ্ট নয়; প্রকৃত authentication ও authorization প্রয়োজন।

## 9. Practical Example: Number Classification

একটি number positive অথবা negative কি না পরীক্ষা করা যাক।

```python
number = int(input("Enter an integer: "))

if number > 0 or number < 0:
    print("Number is non-zero")
else:
    print("Number is zero")
```

Sample Input:

```text
Enter an integer: -8
```

Output:

```text
Number is non-zero
```

এখানে:

- `number > 0` সত্য হলে number positive।
- `number < 0` সত্য হলে number negative।
- দুই condition-ই মিথ্যা হলে number zero।

তাই `or` ব্যবহার করে positive ও negative—দুই অবস্থাই পরীক্ষা করা হয়েছে।

## 10. Practical Example: Free Delivery

ধরা যাক, customer member হলে অথবা purchase amount কমপক্ষে 3000 টাকা হলে free delivery পাবে।

```python
is_member = input("Are you a member? (yes/no): ").strip().lower()
amount = float(input("Enter purchase amount: "))

if is_member == "yes" or amount >= 3000:
    print("Free delivery")
else:
    print("Delivery charge applies")
```

Sample Input:

```text
Are you a member? (yes/no): yes
Enter purchase amount: 1000
```

Output:

```text
Free delivery
```

Purchase amount 3000-এর কম হলেও customer member হওয়ায় free delivery পেয়েছে।

## 11. Combining `or` with `and`

একটি expression-এ `or` এবং `and` একসঙ্গে ব্যবহার করা যায়।

Example:

```python
age = 20
has_id = True
is_member = False

if (age >= 18 and has_id) or is_member:
    print("Access granted")
else:
    print("Access denied")
```

Output:

```text
Access granted
```

এখানে:

1. `age >= 18` সত্য।
2. `has_id` সত্য।
3. তাই `(age >= 18 and has_id)` সত্য।
4. `True or False`-এর ফলাফল সত্য।

অর্থাৎ বয়স ও পরিচয়পত্রের শর্ত পূরণ হলে অথবা member হলে access দেওয়া হবে।

### Operator Precedence

Python-এ `and` operator-এর precedence `or`-এর চেয়ে বেশি।

তাই:

```python
if a or b and c:
    print("Yes")
```

এটি এভাবে evaluate হয়:

```python
if a or (b and c):
    print("Yes")
```

তবে intended logic পরিষ্কার রাখতে parentheses ব্যবহার করাই ভালো।

## 12. Short-Circuit Evaluation with `or`

Python-এ `or` short-circuit evaluation ব্যবহার করে।

এর অর্থ, প্রথম condition সত্য হলে Python সাধারণত পরবর্তী condition evaluate করে না।

Example:

```python
number = 10

if number > 0 or 10 / 0 > 1:
    print("Condition is true")
```

Output:

```text
Condition is true
```

এখানে `number > 0` সত্য। তাই Python দ্বিতীয় condition evaluate করে না। ফলে `ZeroDivisionError` হয় না।

### আরেকটি উদাহরণ

```python
name = "Masum"

if name or len(name) > 0:
    print("Name is available")
```

Output:

```text
Name is available
```

এখানে `name` non-empty string হওয়ায় এটি truthy। তাই `or`-এর দ্বিতীয় অংশ evaluate করার প্রয়োজন হয় না।

## 13. Common Mistakes

### Mistake 1: Using `or` When All Conditions Must Be True

ধরা যাক, marks কমপক্ষে 40 এবং attendance কমপক্ষে 75—দুটিই প্রয়োজন।

Incorrect:

```python
if marks >= 40 or attendance >= 75:
    print("Eligible")
```

এখানে একটি condition সত্য হলেই `Eligible` print হবে।

Correct:

```python
if marks >= 40 and attendance >= 75:
    print("Eligible")
```

### Mistake 2: Incorrect Comparison

Incorrect:

```python
age = 20

if age == 18 or 21:
    print("Allowed")
```

এখানে `21` একটি truthy value, তাই condition সবসময় সত্য হবে।

Correct:

```python
if age == 18 or age == 21:
    print("Allowed")
```

### Mistake 3: Incorrect Range Validation

ধরা যাক, number 10 থেকে 50-এর বাইরে হলে invalid।

Correct:

```python
if number < 10 or number > 50:
    print("Outside range")
else:
    print("Within range")
```

কিন্তু নিচের condition ভুল:

```python
if number < 10 or number < 50:
    print("Outside range")
```

কারণ `number < 50` সত্য হলেই condition সত্য হয়ে যাবে, এমনকি number range-এর ভেতরে থাকলেও।

### Mistake 4: Forgetting Parentheses

জটিল condition-এ parentheses না দিলে intended logic-এর সঙ্গে actual logic আলাদা হতে পারে।

```python
if age >= 18 and has_id or is_member:
    print("Allowed")
```

Python এটিকে এভাবে evaluate করে:

```python
if (age >= 18 and has_id) or is_member:
```

যদি অন্য logic প্রয়োজন হয়, তাহলে parentheses দিয়ে সেটি স্পষ্ট করতে হবে।

### Mistake 5: Comparing the Same Variable Incorrectly

Incorrect:

```python
if day == "Friday" or "Saturday":
    print("Weekend")
```

Correct:

```python
if day == "Friday" or day == "Saturday":
    print("Weekend")
```

অথবা:

```python
if day in ("Friday", "Saturday"):
    print("Weekend")
```

## 14. Practice Exercises

নিজে solve করার চেষ্টা করো।

### Exercise 1: Accepted Age

একটি integer age input নাও। বয়স 18 অথবা 60 হলে `Accepted age` print করো।

### Exercise 2: Number Outside Range

একটি integer input নাও। Number 10-এর কম অথবা 100-এর বেশি হলে `Outside range` print করো।

### Exercise 3: Weekend

একটি day input নাও। Day Friday অথবা Saturday হলে `Weekend` print করো।

### Exercise 4: Discount

একজন customer member হলে অথবা purchase amount 5000 বা তার বেশি হলে `Discount available` print করো।

### Exercise 5: Number Classification

একটি integer input নাও। Number positive অথবা negative হলে `Non-zero` print করো। অন্যথায় `Zero` print করো।

### Exercise 6: Output Prediction

```python
a = False
b = True

print(a or b)
print(a or False)
print(True or False)
```

Output কী হবে?

### Exercise 7: Output Prediction

```python
x = 25

if x < 10 or x > 20:
    print("Outside")
else:
    print("Inside")
```

Output কী হবে?

### Exercise 8: Fix the Code

```python
day = "Saturday"

if day == "Friday" or "Saturday":
    print("Weekend")
else:
    print("Regular day")
```

Code-টি ঠিক করো।

### Exercise 9: Combine `and` and `or`

একজন user-এর বয়স 18 বা তার বেশি এবং পরিচয়পত্র আছে, অথবা user একজন member—এমন হলে `Access granted` print করো।

## 15. Practice Answer Key

### Answer 1

```python
age = int(input("Enter age: "))

if age == 18 or age == 60:
    print("Accepted age")
else:
    print("Other age")
```

### Answer 2

```python
number = int(input("Enter a number: "))

if number < 10 or number > 100:
    print("Outside range")
else:
    print("Within range")
```

### Answer 3

```python
day = input("Enter a day: ").strip().lower()

if day == "friday" or day == "saturday":
    print("Weekend")
else:
    print("Regular day")
```

### Answer 4

```python
is_member = input("Are you a member? (yes/no): ").strip().lower()
amount = float(input("Enter purchase amount: "))

if is_member == "yes" or amount >= 5000:
    print("Discount available")
else:
    print("No discount")
```

### Answer 5

```python
number = int(input("Enter an integer: "))

if number > 0 or number < 0:
    print("Non-zero")
else:
    print("Zero")
```

### Answer 6

```text
True
False
True
```

### Answer 7

```text
Outside
```

কারণ `25 > 20` সত্য।

### Answer 8

```python
day = "Saturday"

if day == "Friday" or day == "Saturday":
    print("Weekend")
else:
    print("Regular day")
```

### Answer 9

```python
age = int(input("Enter age: "))
has_id = input("Do you have an ID? (yes/no): ").strip().lower() == "yes"
is_member = input("Are you a member? (yes/no): ").strip().lower() == "yes"

if (age >= 18 and has_id) or is_member:
    print("Access granted")
else:
    print("Access denied")
```

## 16. Chapter Summary

- `or` operator ব্যবহার করা হয় যখন অন্তত একটি condition সত্য হলেই যথেষ্ট।
- সব condition মিথ্যা হলেই `or` expression মিথ্যা হয়।
- একাধিক accepted value, range validation, discount এবং permission checking-এ `or` কাজে লাগে।
- `and` ও `or` একসঙ্গে ব্যবহার করলে precedence বুঝতে হবে।
- Parentheses দিয়ে complex conditions স্পষ্ট করা যায়।
- `or` short-circuit evaluation ব্যবহার করে।
- একই variable-এর একাধিক value পরীক্ষা করতে `day == "Friday" or day == "Saturday"` অথবা `day in (...)` ব্যবহার করা যায়।
- Problem-এর requirement অনুযায়ী `and` ও `or` সঠিকভাবে বেছে নিতে হবে।

## 17. Self-Assessment Checklist

- [ ] `or` operator-এর কাজ ব্যাখ্যা করতে পারি।
- [ ] `or`-এর truth table মনে আছে।
- [ ] একাধিক accepted value পরীক্ষা করতে পারি।
- [ ] `or` দিয়ে range-এর বাইরে থাকা value শনাক্ত করতে পারি।
- [ ] `and` এবং `or` একসঙ্গে ব্যবহার করতে পারি।
- [ ] Short-circuit evaluation বুঝি।
- [ ] `or` ব্যবহারের সাধারণ ভুলগুলো শনাক্ত করতে পারি।
- [ ] `or` ব্যবহার করে practical program লিখতে পারি।

## 18. Next Topic

পরবর্তী file:

`14_Using_not_in_Conditions.md`

সেখানে `not` operator ব্যবহার করে condition-এর বিপরীত অবস্থা যাচাই করা, truthiness, practical examples এবং common mistakes শেখা হবে।