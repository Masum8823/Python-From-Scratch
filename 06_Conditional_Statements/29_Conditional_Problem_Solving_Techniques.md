# 29. Conditional Problem-Solving Techniques

## 1. Introduction

**Conditional Problem Solving** হলো কোনো problem-এর requirements বুঝে উপযুক্ত conditions তৈরি করা এবং সেগুলো ব্যবহার করে সঠিক result বের করার প্রক্রিয়া।

Python-এ conditional problem solving-এর জন্য সাধারণত ব্যবহার করা হয়:

- `if`
- `elif`
- `else`
- Comparison operators
- Logical operators (`and`, `or`, `not`)
- Nested conditions
- Boolean expressions

শুধু syntax জানলেই হবে না। কোন condition আগে পরীক্ষা করতে হবে, কোন operator ব্যবহার করতে হবে এবং কোন input-এ কী output আসবে—এগুলোও বুঝতে হবে।

## 2. Step-by-Step Problem-Solving Method

যেকোনো conditional problem সমাধান করতে নিচের ধাপগুলো অনুসরণ করো।

### Step 1: Understand the Problem

প্রথমে problem-টি মনোযোগ দিয়ে পড়বে।

নিজেকে প্রশ্ন করবে:

- কী input দেওয়া হবে?
- কী output দেখাতে হবে?
- কোন কোন rule অনুসরণ করতে হবে?
- কোনো special case আছে কি?

### Step 2: Identify the Conditions

Problem-এর মধ্যে থাকা rules-গুলোকে condition-এ রূপান্তর করবে।

উদাহরণ:

Problem: Marks 40 বা তার বেশি হলে Pass, অন্যথায় Fail।

Condition:

```python
marks >= 40
```

### Step 3: Choose the Correct Operators

Condition অনুযায়ী operator নির্বাচন করবে।

| Requirement | Operator |
|---|---|
| সমান | `==` |
| সমান নয় | `!=` |
| বড় | `>` |
| ছোট | `<` |
| বড় বা সমান | `>=` |
| ছোট বা সমান | `<=` |
| সব condition সত্য হতে হবে | `and` |
| অন্তত একটি condition সত্য হতে হবে | `or` |
| result উল্টাতে হবে | `not` |

### Step 4: Arrange the Conditions

একাধিক condition থাকলে সেগুলোর order ঠিক করবে।

যেমন grade calculator-এ সাধারণত বড় threshold আগে পরীক্ষা করা হয়।

```python
if marks >= 80:
    print("Grade A")
elif marks >= 60:
    print("Grade B")
else:
    print("Grade C")
```

এখানে `marks = 90` হলে প্রথম condition True হবে এবং `Grade A` দেখাবে।

### Step 5: Write the Code

Problem-এর logic অনুযায়ী Python code লিখবে।

### Step 6: Test Different Inputs

শুধু একটি input দিয়ে পরীক্ষা করবে না। Normal value, boundary value এবং unusual value দিয়ে program পরীক্ষা করবে।

### Step 7: Debug and Improve

Output ভুল হলে condition, operator, order এবং indentation পরীক্ষা করবে।

## 3. Converting a Problem into Conditions

Problem-এর সাধারণ বাক্যকে Python condition-এ রূপান্তর করা একটি গুরুত্বপূর্ণ skill।

| Problem statement | Python condition |
|---|---|
| Age 18 বা তার বেশি | `age >= 18` |
| Marks 40-এর বেশি | `marks > 40` |
| Number শূন্য | `number == 0` |
| Number জোড় | `number % 2 == 0` |
| Number 3 দিয়ে বিভাজ্য | `number % 3 == 0` |
| Age 18 থেকে 60-এর মধ্যে, দুই প্রান্তসহ | `18 <= age <= 60` |
| Username `"admin"` | `username == "admin"` |
| Choice `"yes"` অথবা `"y"` | `choice == "yes" or choice == "y"` |
| Number 1 থেকে 10-এর বাইরে | `number < 1 or number > 10` |

**মনে রাখবে:** “বেশি” এবং “বেশি বা সমান” এক নয়। Problem-এর wording অনুযায়ী `>` অথবা `>=` বেছে নিতে হবে।

## 4. Using Pseudocode Before Writing Python

**Pseudocode** হলো সাধারণ ভাষা ও programming-এর মাঝামাঝি একটি সহজ, code-এর মতো বর্ণনা। এটি দিয়ে আগে logic সাজানো যায়।

### Problem: Check Whether a Number Is Positive, Negative or Zero

Pseudocode:

```text
START
INPUT number

IF number > 0
    DISPLAY "Positive"
ELSE IF number < 0
    DISPLAY "Negative"
ELSE
    DISPLAY "Zero"

END
```

Python code:

```python
number = float(input("Enter a number: "))

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

Pseudocode লেখার সুবিধা হলো, Python syntax নিয়ে চিন্তা করার আগেই problem-এর logic পরিষ্কার করা যায়।

## 5. Using a Flowchart to Plan Conditions

**Flowchart** হলো diagram-এর মাধ্যমে program-এর execution flow দেখানোর পদ্ধতি।

সাধারণ flowchart symbols:

| Symbol | Meaning |
|---|---|
| Oval | Start / End |
| Parallelogram | Input / Output |
| Rectangle | Processing |
| Diamond | Decision / Condition |
| Arrow | Flow direction |

উদাহরণ: Pass/Fail checker-এর flow:

```text
       Start
         |
     Input marks
         |
    marks >= 40?
       /     \
     Yes      No
      |        |
    Pass      Fail
       \      /
          End
```

এখানে diamond-এর মধ্যে condition পরীক্ষা করা হয়। Result অনুযায়ী flow Yes অথবা No branch-এ যায়।

## 6. Choosing Between if, if-elif-else and Nested if

সব problem একই structure দিয়ে সমাধান করা উচিত নয়।

### Use `if`

যখন একটি condition পরীক্ষা করতে হয়।

```python
age = 20

if age >= 18:
    print("Adult")
```

### Use `if-else`

যখন দুটি alternative result থাকে।

```python
number = 7

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

### Use `if-elif-else`

যখন একাধিক alternative-এর মধ্যে একটি নির্বাচন করতে হয়।

```python
marks = 75

if marks >= 80:
    print("A")
elif marks >= 60:
    print("B")
else:
    print("C")
```

### Use Nested `if`

যখন দ্বিতীয় condition শুধু প্রথম condition পূরণ হলে পরীক্ষা করতে হয়।

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Access granted")
    else:
        print("ID required")
else:
    print("Age requirement not met")
```

Nested conditions অপ্রয়োজনীয়ভাবে বেশি ব্যবহার না করে সহজ structure বেছে নেওয়া ভালো।

## 7. Solving Problems with Multiple Conditions

যখন একটি result-এর জন্য একাধিক requirement পূরণ করতে হয়, তখন `and` ব্যবহার করা হয়।

### Example: Exam Eligibility

Problem:

- Attendance কমপক্ষে 75% হতে হবে।
- Assignment marks কমপক্ষে 40 হতে হবে।

```python
attendance = float(input("Enter attendance percentage: "))
assignment_marks = float(input("Enter assignment marks: "))

if attendance >= 75 and assignment_marks >= 40:
    print("Eligible for exam")
else:
    print("Not eligible for exam")
```

এখানে দুইটি condition-ই True হতে হবে।

যদি attendance 80% হয় কিন্তু assignment marks 30 হয়, তাহলে result হবে `Not eligible for exam`।

**Note:** এটি practice-এর জন্য তৈরি নিয়ম। বাস্তব প্রতিষ্ঠানের eligibility rules আলাদা হতে পারে।

## 8. Solving Problems with Alternative Conditions

যখন একাধিক alternative-এর যেকোনো একটি পূরণ হলেই result গ্রহণযোগ্য হয়, তখন `or` ব্যবহার করা হয়।

### Example: Special Discount

Problem:

Customer-এর membership `"gold"` হলে অথবা purchase amount 5000 বা তার বেশি হলে discount দেওয়া হবে।

```python
membership = input("Enter membership type: ")
amount = float(input("Enter purchase amount: "))

if membership == "gold" or amount >= 5000:
    print("Discount available")
else:
    print("No discount")
```

এখানে membership Gold না হলেও amount 5000 বা তার বেশি হলে discount পাওয়া যাবে।

যদি দুইটি condition-ই False হয়, তাহলে discount পাওয়া যাবে না।

## 9. Solving Range-Based Problems

যখন কোনো value একটি নির্দিষ্ট range-এর মধ্যে থাকতে হয়, তখন chained comparison ব্যবহার করা যায়।

### Example: Valid Marks

Problem: Marks 0 থেকে 100-এর মধ্যে হলে valid।

```python
marks = float(input("Enter marks: "))

if 0 <= marks <= 100:
    print("Valid marks")
else:
    print("Invalid marks")
```

এখানে `0` এবং `100`—দুই প্রান্তই অন্তর্ভুক্ত।

সমতুল্য condition:

```python
if marks >= 0 and marks <= 100:
    print("Valid marks")
else:
    print("Invalid marks")
```

দুইটি পদ্ধতিই কাজ করে।

## 10. Handling Boundary Values

**Boundary value** হলো condition বা range-এর সীমানায় থাকা value।

ধরা যাক, 40 বা তার বেশি marks পেলে Pass।

Test cases:

| Marks | Expected result |
|---:|---|
| 39 | Fail |
| 40 | Pass |
| 41 | Pass |

যদি code-এ `marks > 40` লেখা হয়, তাহলে 40 marks ভুলভাবে Fail হবে।

Correct condition:

```python
if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

**Rule:** Problem-এ “at least” বা “or more” থাকলে সাধারণত `>=` এবং “at most” বা “or less” থাকলে সাধারণত `<=` প্রয়োজন হয়।

## 11. Handling Special Cases

কোনো problem-এর সাধারণ input ছাড়াও special case থাকতে পারে।

উদাহরণ:

- Zero
- Negative number
- Empty string
- Invalid range
- Equal numbers
- Missing information

### Example: Division

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

if b == 0:
    print("Cannot divide by zero")
else:
    print("Result:", a / b)
```

এখানে division করার আগে divisor zero কি না পরীক্ষা করা হচ্ছে।

এটি একটি গুরুত্বপূর্ণ problem-solving technique: operation করার আগে সেই operation-এর জন্য প্রয়োজনীয় condition যাচাই করা।

## 12. Simplifying Complex Conditions

কখনো একটি condition-এ অনেকগুলো অংশ থাকলে সেটি পড়তে কঠিন হয়ে যায়।

উদাহরণ:

```python
age = 25
has_id = True
is_blocked = False

if age >= 18 and has_id and not is_blocked:
    print("Access granted")
else:
    print("Access denied")
```

এই condition-এর অর্থ:

1. Age কমপক্ষে 18 হতে হবে।
2. ID থাকতে হবে।
3. User blocked হওয়া যাবে না।

Condition-টি পড়ার সময় প্রতিটি অংশের অর্থ আলাদাভাবে বোঝার চেষ্টা করবে।

আরও complex logic হলে intermediate Boolean variables ব্যবহার করতে পারো:

```python
is_adult = age >= 18
has_required_id = has_id
account_is_active = not is_blocked

if is_adult and has_required_id and account_is_active:
    print("Access granted")
else:
    print("Access denied")
```

এতে logic বোঝা সহজ হতে পারে।

## 13. Avoiding Common Problem-Solving Mistakes

### Mistake 1: Problem ভালোভাবে না বোঝা

Condition লেখার আগে expected result পরিষ্কার না হলে ভুল logic তৈরি হতে পারে।

**Solution:** Input, output এবং rules লিখে নাও।

### Mistake 2: ভুল comparison operator

`>` এবং `>=`-এর পার্থক্য না বুঝলে boundary error হয়।

**Solution:** Problem-এর exact wording অনুসরণ করো।

### Mistake 3: `and`-এর জায়গায় `or`

সব শর্ত পূরণ করতে হলে `and`; বিকল্প শর্তের যেকোনো একটি পূরণ হলেই হলে `or` ব্যবহার করবে।

### Mistake 4: Condition-এর ভুল order

`if-elif-else`-এ প্রথম True branch execute হয়।

**Solution:** Overlapping condition থাকলে order যাচাই করবে।

### Mistake 5: Special case বাদ দেওয়া

Zero, negative number বা equal values পরীক্ষা না করলে program ভুল result দিতে পারে।

**Solution:** সম্ভাব্য edge cases-এর তালিকা তৈরি করো।

### Mistake 6: Test না করা

Code দেখতে ঠিক হলেই যে সব input-এর জন্য সঠিক হবে, তা নয়।

**Solution:** একাধিক test case দিয়ে পরীক্ষা করো।

## 14. Complete Problem-Solving Example

### Problem: Calculate a Student's Final Result

Rules:

- Marks 0–100-এর বাইরে হলে Invalid marks।
- Marks 40 বা তার বেশি হলে Pass।
- Marks 40-এর কম হলে Fail।

### Step 1: Input

Student-এর marks।

### Step 2: Conditions

- Marks valid কি না।
- Marks pass threshold পূরণ করেছে কি না।

### Step 3: Pseudocode

```text
INPUT marks

IF marks < 0 OR marks > 100
    DISPLAY "Invalid marks"
ELSE IF marks >= 40
    DISPLAY "Pass"
ELSE
    DISPLAY "Fail"
```

### Step 4: Python Code

```python
marks = float(input("Enter marks: "))

if marks < 0 or marks > 100:
    print("Invalid marks")
elif marks >= 40:
    print("Pass")
else:
    print("Fail")
```

### Step 5: Test Cases

| Input | Expected output |
|---:|---|
| `-5` | Invalid marks |
| `0` | Fail |
| `39` | Fail |
| `40` | Pass |
| `100` | Pass |
| `105` | Invalid marks |

এভাবে problem বুঝে condition তৈরি, code লেখা এবং test করার সম্পূর্ণ process শেষ হয়।

## 15. Practice Exercises

প্রথমে problem বুঝে condition লিখবে, তারপর Python code তৈরি করবে।

### Exercise 1: Positive Even Number

একটি number positive এবং even—দুই শর্তই পূরণ করলে `"Positive even"` দেখাবে। অন্যথায় `"Does not meet both conditions"` দেখাবে।

### Exercise 2: Admission Eligibility

একজন applicant-এর marks 80 বা তার বেশি এবং attendance 75% বা তার বেশি হলে eligible দেখাবে। অন্যথায় not eligible দেখাবে।

### Exercise 3: Number Range

একটি number 10 থেকে 50-এর মধ্যে, দুই প্রান্তসহ, আছে কি না পরীক্ষা করো।

### Exercise 4: Largest Number

তিনটি number input নিয়ে সবচেয়ে বড় number বের করো। একাধিক number সমান হলেও program সঠিকভাবে কাজ করবে।

### Exercise 5: Discount Eligibility

Customer Gold member হলে অথবা purchase amount 5000 বা তার বেশি হলে discount available দেখাবে।

### Exercise 6: Leap Year

একটি year leap year কি না নির্ধারণ করো। 1900 এবং 2000-এর মতো century year-ও পরীক্ষা করো।

### Exercise 7: Grade Calculator

0–100-এর মধ্যে marks নিয়ে এই scale ব্যবহার করো:

- 80 বা তার বেশি: A
- 60–79: B
- 40–59: C
- 0–39: F
- Range-এর বাইরে: Invalid marks

### Exercise 8: Simple Login Rule

Username `"admin"` এবং password `"python123"`—দুইটি সঠিক হলে Login successful দেখাও। অন্যথায় Invalid credentials দেখাও।

## 16. Answer Key

### Exercise 1

```python
number = int(input("Enter an integer: "))

if number > 0 and number % 2 == 0:
    print("Positive even")
else:
    print("Does not meet both conditions")
```

### Exercise 2

```python
marks = float(input("Enter marks: "))
attendance = float(input("Enter attendance percentage: "))

if marks >= 80 and attendance >= 75:
    print("Eligible")
else:
    print("Not eligible")
```

### Exercise 3

```python
number = float(input("Enter a number: "))

if 10 <= number <= 50:
    print("Inside range")
else:
    print("Outside range")
```

### Exercise 4

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))
c = float(input("Enter third number: "))

if a >= b and a >= c:
    print("Largest:", a)
elif b >= a and b >= c:
    print("Largest:", b)
else:
    print("Largest:", c)
```

### Exercise 5

```python
membership = input("Enter membership type: ")
amount = float(input("Enter purchase amount: "))

if membership == "Gold" or amount >= 5000:
    print("Discount available")
else:
    print("No discount")
```

এই উদাহরণে membership comparison case-sensitive। `"gold"` এবং `"Gold"` আলাদা string।

### Exercise 6

```python
year = int(input("Enter a year: "))

if year <= 0:
    print("Invalid year")
elif year % 400 == 0:
    print("Leap year")
elif year % 100 == 0:
    print("Not a leap year")
elif year % 4 == 0:
    print("Leap year")
else:
    print("Not a leap year")
```

### Exercise 7

```python
marks = float(input("Enter marks: "))

if marks < 0 or marks > 100:
    print("Invalid marks")
elif marks >= 80:
    print("Grade A")
elif marks >= 60:
    print("Grade B")
elif marks >= 40:
    print("Grade C")
else:
    print("Grade F")
```

### Exercise 8

```python
username = input("Enter username: ")
password = input("Enter password: ")

if username == "admin" and password == "python123":
    print("Login successful")
else:
    print("Invalid credentials")
```

এটি শুধু conditional logic শেখার example; production authentication-এর জন্য উপযুক্ত নয়।

## 17. Quick Revision

- Problem বুঝে input, output এবং rules নির্ধারণ করতে হবে।
- Problem-এর rules-কে Boolean conditions-এ রূপান্তর করতে হবে।
- `if`, `if-else`, `if-elif-else` এবং nested `if` প্রয়োজন অনুযায়ী বেছে নিতে হবে।
- সব condition পূরণ করতে হলে `and` ব্যবহার করতে হবে।
- বিকল্প condition-এর যেকোনো একটি পূরণ হলেই হলে `or` ব্যবহার করতে হবে।
- Range check করার জন্য chained comparison ব্যবহার করা যায়।
- Boundary values এবং special cases পরীক্ষা করতে হবে।
- Pseudocode ও flowchart logic সাজাতে সাহায্য করে।
- Code লেখার পরে একাধিক test case দিয়ে output যাচাই করতে হবে।

## 18. Self-Assessment Checklist

- [ ] Problem statement থেকে conditions বের করতে পারি।
- [ ] Comparison operator সঠিকভাবে নির্বাচন করতে পারি।
- [ ] `and`, `or` ও `not` দিয়ে logic তৈরি করতে পারি।
- [ ] Pseudocode থেকে Python code লিখতে পারি।
- [ ] Range এবং boundary condition বুঝি।
- [ ] Nested condition কখন ব্যবহার করতে হয় বুঝি।
- [ ] Special cases শনাক্ত করতে পারি।
- [ ] Test cases দিয়ে program যাচাই করতে পারি।
- [ ] নিজের logic ব্যাখ্যা করে solution তৈরি করতে পারি।

**পরবর্তী টপিক:** `30_Conditional_Output_Prediction_Exercises.md`
