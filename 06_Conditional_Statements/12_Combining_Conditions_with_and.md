# 12. Combining Conditions with `and`

## 1. Introduction

Python-এ `and` operator ব্যবহার করে একাধিক condition একসঙ্গে পরীক্ষা করা যায়।

যখন সবগুলো condition সত্য হওয়া প্রয়োজন, তখন `and` ব্যবহার করা হয়।

Example:

```python
age = 22
has_id = True

if age >= 18 and has_id:
    print("Entry allowed")
else:
    print("Entry denied")
```

Output:

```text
Entry allowed
```

এখানে দুটি condition রয়েছে:

- `age >= 18` → `True`
- `has_id` → `True`

দুটি condition-ই সত্য হওয়ায় `Entry allowed` print হয়েছে।

**মনে রাখবে:** `and`-এর ক্ষেত্রে যেকোনো একটি condition মিথ্যা হলেই পুরো condition মিথ্যা হয়।

## 2. Syntax of `and`

```python
if condition_1 and condition_2:
    # Code executes when both conditions are true
    statement
```

তিনটি condition-ও combine করা যায়:

```python
if condition_1 and condition_2 and condition_3:
    statement
```

এখানে সব condition সত্য হতে হবে।

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

এখানে বয়স যথেষ্ট, পরিচয়পত্র আছে এবং account blocked নয়। তাই সব শর্ত পূরণ হয়েছে।

## 3. Truth Table of `and`

`and` operator-এর ফলাফল বুঝতে truth table গুরুত্বপূর্ণ।

| Condition 1 | Condition 2 | Result |
|---|---|---|
| `True` | `True` | `True` |
| `True` | `False` | `False` |
| `False` | `True` | `False` |
| `False` | `False` | `False` |

### সহজে মনে রাখার নিয়ম

`and` মানে **সবগুলো সত্য হতে হবে**।

শুধু একটি condition `False` হলেও result হবে `False`।

Example:

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

## 4. Combining Comparison Conditions

সাধারণত `and` operator comparison operators-এর সঙ্গে ব্যবহার করা হয়।

Example:

```python
marks = 75
attendance = 80

if marks >= 40 and attendance >= 75:
    print("Requirements satisfied")
else:
    print("Requirements not satisfied")
```

Output:

```text
Requirements satisfied
```

এখানে:

- `marks >= 40` সত্য।
- `attendance >= 75` সত্য।

তাই result সত্য হয়েছে।

অন্যদিকে:

```python
marks = 75
attendance = 60

if marks >= 40 and attendance >= 75:
    print("Requirements satisfied")
else:
    print("Requirements not satisfied")
```

Output:

```text
Requirements not satisfied
```

Marks-এর condition সত্য হলেও attendance-এর condition মিথ্যা। তাই পুরো `and` expression মিথ্যা।

## 5. Checking a Range with `and`

কোনো value একটি নির্দিষ্ট range-এর মধ্যে আছে কি না যাচাই করতে `and` ব্যবহার করা যায়।

Example:

```python
number = 35

if number >= 10 and number <= 50:
    print("Number is within range")
else:
    print("Number is outside range")
```

Output:

```text
Number is within range
```

এখানে number-টি একই সঙ্গে 10 বা তার বেশি এবং 50 বা তার কম হতে হবে।

Python-এ এই condition আরও সহজভাবে লেখা যায়:

```python
if 10 <= number <= 50:
    print("Number is within range")
```

এটিকে **Chained Comparison** বলা হয়।

দুটি version-ই এখানে একই অর্থ প্রকাশ করে।

### Boundary Values

```python
number = 10
print(10 <= number <= 50)
```

Output:

```text
True
```

```python
number = 50
print(10 <= number <= 50)
```

Output:

```text
True
```

```python
number = 51
print(10 <= number <= 50)
```

Output:

```text
False
```

`10 <= number <= 50` condition-এ 10 এবং 50—দুটি boundary-ই অন্তর্ভুক্ত।

## 6. Using `and` with User Input

User input নিয়ে একাধিক condition যাচাই করা যায়।

Example:

```python
age = int(input("Enter your age: "))
country = input("Enter your country: ").strip().lower()

if age >= 18 and country == "bangladesh":
    print("Conditions satisfied")
else:
    print("Conditions not satisfied")
```

Sample Input:

```text
Enter your age: 22
Enter your country: Bangladesh
```

Output:

```text
Conditions satisfied
```

এখানে `strip()` অতিরিক্ত শুরু ও শেষের whitespace সরায় এবং `lower()` input-কে lowercase করে।

এটি শুধু condition combination শেখানোর উদাহরণ। বাস্তব eligibility rules হলে সংশ্লিষ্ট নিয়ম অনুযায়ী যাচাই করতে হবে।

## 7. Practical Example: Student Eligibility

ধরা যাক, একটি student-এর marks কমপক্ষে 40 এবং attendance কমপক্ষে 75% হলে তাকে eligible বলা হবে।

```python
marks = float(input("Enter marks: "))
attendance = float(input("Enter attendance percentage: "))

if marks >= 40 and attendance >= 75:
    print("Eligible")
else:
    print("Not eligible")
```

Sample Input:

```text
Enter marks: 65
Enter attendance percentage: 85
```

Output:

```text
Eligible
```

### যখন একটি condition মিথ্যা

Input:

```text
Enter marks: 65
Enter attendance percentage: 60
```

Output:

```text
Not eligible
```

কারণ attendance-এর condition পূরণ হয়নি।

এই example-এ marks এবং attendance-এর valid range আলাদাভাবে যাচাই করা হয়নি। প্রয়োজন হলে validation যোগ করতে হবে।

## 8. Practical Example: Login Conditions

একটি simple example-এ username ও password—দুটিই সঠিক হলে login successful হবে।

```python
username = input("Enter username: ")
password = input("Enter password: ")

if username == "admin" and password == "python123":
    print("Login successful")
else:
    print("Invalid username or password")
```

Sample Input:

```text
Enter username: admin
Enter password: python123
```

Output:

```text
Login successful
```

যেকোনো একটি value ভুল হলে `else` block execute হবে।

**Security note:** এটি শুধু শিক্ষামূলক উদাহরণ। বাস্তব application-এ source code-এর মধ্যে plaintext password রাখা উচিত নয়।

## 9. Practical Example: Free Delivery

ধরা যাক, একজন customer member এবং তার purchase amount কমপক্ষে 2000 টাকা হলে free delivery পাবে।

```python
is_member = input("Are you a member? (yes/no): ").strip().lower()
amount = float(input("Enter purchase amount: "))

if is_member == "yes" and amount >= 2000:
    print("Free delivery")
else:
    print("Delivery charge applies")
```

Sample Input:

```text
Are you a member? (yes/no): yes
Enter purchase amount: 2500
```

Output:

```text
Free delivery
```

এখানে membership এবং purchase amount—দুটো শর্তই পূরণ হতে হবে।

## 10. Practical Example: Positive and Even Number

একটি number positive এবং even—দুটিই কি না পরীক্ষা করা যাক।

```python
number = int(input("Enter an integer: "))

if number > 0 and number % 2 == 0:
    print("Positive even number")
else:
    print("Condition not satisfied")
```

Sample Input:

```text
Enter an integer: 12
```

Output:

```text
Positive even number
```

এখানে:

- `number > 0` number positive কি না যাচাই করে।
- `number % 2 == 0` number even কি না যাচাই করে।

দুটি condition সত্য হলে message print হয়।

Note: Zero even হলেও positive নয়। Negative even number-ও প্রথম condition পূরণ করে না।

## 11. Combining `and` with `not`

`not` ব্যবহার করে কোনো condition-এর বিপরীত অবস্থা যাচাই করা যায়।

Example:

```python
is_logged_in = True
is_banned = False

if is_logged_in and not is_banned:
    print("You may continue")
else:
    print("Access denied")
```

Output:

```text
You may continue
```

এখানে:

- `is_logged_in` সত্য।
- `not is_banned` সত্য, কারণ `is_banned` মিথ্যা।

তাই পুরো expression সত্য হয়েছে।

আরেকটি উদাহরণ:

```python
has_ticket = True
is_cancelled = True

if has_ticket and not is_cancelled:
    print("Entry allowed")
else:
    print("Entry denied")
```

Output:

```text
Entry denied
```

Ticket থাকলেও event cancelled হওয়ায় `not is_cancelled` মিথ্যা হয়েছে।

## 12. Short-Circuit Evaluation with `and`

Python-এ `and` operator short-circuit evaluation ব্যবহার করে।

এর অর্থ, প্রথম condition মিথ্যা হলে Python সাধারণত পরের condition evaluate করে না, কারণ পুরো expression তখনই মিথ্যা নির্ধারিত হয়ে যায়।

Example:

```python
number = 0

if number != 0 and 10 / number > 2:
    print("Condition is true")
else:
    print("Condition is false")
```

Output:

```text
Condition is false
```

প্রথম condition `number != 0` মিথ্যা। তাই Python `10 / number > 2` evaluate করে না।

ফলে `ZeroDivisionError` হয় না।

### Short-Circuit-এর উপকারিতা

- অপ্রয়োজনীয় evaluation কমায়।
- কিছু ক্ষেত্রে error এড়াতে সাহায্য করে।
- এক condition-এর ফলাফলের ওপর পরের condition নির্ভর করলে কার্যকর হয়।

তবে short-circuit-এর ওপর নির্ভর করার আগে condition-এর ক্রম সঠিকভাবে সাজানো জরুরি।

## 13. Common Mistakes

### Mistake 1: Using `and` for Alternative Conditions

Incorrect:

```python
age = 18

if age == 18 and age == 21:
    print("Allowed")
```

একই `age` একই সঙ্গে 18 এবং 21 হতে পারে না।

যদি 18 অথবা 21—যেকোনো একটি গ্রহণযোগ্য হয়, তাহলে `or` ব্যবহার করতে হবে:

```python
if age == 18 or age == 21:
    print("Allowed")
```

### Mistake 2: Incorrect Range Condition

Incorrect:

```python
number = 25

if number < 10 and number > 50:
    print("Within range")
```

এই condition কখনোই সত্য হতে পারে না।

Correct:

```python
if number >= 10 and number <= 50:
    print("Within range")
```

### Mistake 3: Forgetting One Condition

যদি requirement-এ marks এবং attendance—দুটোই যাচাই করতে বলা হয়, তাহলে একটি condition বাদ দেওয়া যাবে না।

```python
if marks >= 40 and attendance >= 75:
    print("Eligible")
```

### Mistake 4: Repeating the Variable Incorrectly

Incorrect:

```python
if marks >= 40 and <= 100:
    print("Valid marks")
```

এটি invalid syntax।

Correct:

```python
if marks >= 40 and marks <= 100:
    print("Valid marks")
```

অথবা:

```python
if 40 <= marks <= 100:
    print("Valid marks")
```

### Mistake 5: Ignoring Input Validation

```python
marks = float(input("Enter marks: "))

if marks >= 40 and marks <= 100:
    print("Valid passing marks")
```

এই code range যাচাই করে, কিন্তু non-numeric input দিলে `ValueError` হতে পারে। Input validation এবং exception handling পরবর্তী অধ্যায়ে আরও বিস্তারিত শেখা হবে।

## 14. Practice Exercises

নিজে code লেখার চেষ্টা করো।

### Exercise 1: Age Range

একটি integer age input নাও। বয়স 18 থেকে 60-এর মধ্যে হলে `Age accepted` print করো।

### Exercise 2: Exam Result

Marks কমপক্ষে 40 এবং attendance কমপক্ষে 75 হলে `Eligible` print করো।

### Exercise 3: Positive and Divisible

একটি integer input নাও। Number positive এবং 5 দিয়ে বিভাজ্য হলে `Valid number` print করো।

### Exercise 4: Login

Username `student` এবং password `abc123`—দুটোই সঠিক হলে `Login successful` print করো।

### Exercise 5: Output Prediction

```python
a = 10
b = 20
c = 30

if a < b and b < c:
    print("All conditions are true")
else:
    print("At least one condition is false")
```

Output কী হবে?

### Exercise 6: Output Prediction

```python
x = 5

if x > 0 and x < 5:
    print("A")
else:
    print("B")
```

Output কী হবে?

### Exercise 7: Fix the Code

```python
marks = 85

if marks >= 40 and <= 100:
    print("Valid marks")
```

Code-টি ঠিক করো।

### Exercise 8: Range Checking

একটি integer input নাও। Number 100 থেকে 999-এর মধ্যে হলে `Three-digit positive number` print করো। অন্যথায় `Outside range` print করো।

## 15. Practice Answer Key

### Answer 1

```python
age = int(input("Enter age: "))

if 18 <= age <= 60:
    print("Age accepted")
else:
    print("Age not accepted")
```

### Answer 2

```python
marks = float(input("Enter marks: "))
attendance = float(input("Enter attendance: "))

if marks >= 40 and attendance >= 75:
    print("Eligible")
else:
    print("Not eligible")
```

### Answer 3

```python
number = int(input("Enter an integer: "))

if number > 0 and number % 5 == 0:
    print("Valid number")
else:
    print("Invalid number")
```

### Answer 4

```python
username = input("Enter username: ")
password = input("Enter password: ")

if username == "student" and password == "abc123":
    print("Login successful")
else:
    print("Login failed")
```

### Answer 5

Output:

```text
All conditions are true
```

কারণ `10 < 20` এবং `20 < 30`—দুটি condition-ই সত্য।

### Answer 6

Output:

```text
B
```

কারণ `x > 0` সত্য হলেও `x < 5` মিথ্যা। তাই পুরো `and` expression মিথ্যা।

### Answer 7

```python
marks = 85

if marks >= 40 and marks <= 100:
    print("Valid marks")
```

### Answer 8

```python
number = int(input("Enter an integer: "))

if 100 <= number <= 999:
    print("Three-digit positive number")
else:
    print("Outside range")
```

## 16. Chapter Summary

- `and` ব্যবহার করা হয় যখন সব condition সত্য হতে হবে।
- যেকোনো একটি condition মিথ্যা হলেই পুরো `and` expression মিথ্যা হয়।
- Range checking, eligibility, login verification এবং validation-এ `and` কাজে লাগে।
- একাধিক condition একসঙ্গে combine করা যায়।
- `not` দিয়ে কোনো condition-এর বিপরীত অবস্থা যাচাই করা যায়।
- Python-এর `and` operator short-circuit evaluation ব্যবহার করে।
- Range checking-এর ক্ষেত্রে `10 <= number <= 50`-এর মতো chained comparison আরও পরিষ্কার হতে পারে।
- Condition লেখার আগে problem-এর প্রতিটি requirement শনাক্ত করা জরুরি।

## 17. Self-Assessment Checklist

- [ ] `and` operator-এর কাজ ব্যাখ্যা করতে পারি।
- [ ] `and`-এর truth table মনে আছে।
- [ ] দুই বা তার বেশি condition combine করতে পারি।
- [ ] `and` দিয়ে range checking করতে পারি।
- [ ] `and` ও `not` একসঙ্গে ব্যবহার করতে পারি।
- [ ] Short-circuit evaluation বুঝি।
- [ ] `and` ও `or` কখন ব্যবহার করতে হয়, তা বুঝি।
- [ ] `and` ব্যবহার করে practical program লিখতে পারি।

## 18. Next Topic

পরবর্তী file:

`13_Combining_Conditions_with_or.md`

সেখানে `or` operator দিয়ে alternative conditions পরীক্ষা করা, truth table, practical examples এবং problem-solving techniques শেখা হবে।