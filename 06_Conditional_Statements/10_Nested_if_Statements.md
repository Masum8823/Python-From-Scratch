# 10. Nested `if` Statements

## 1. Introduction

Python-এ একটি `if` statement-এর ভেতরে আরেকটি `if` statement ব্যবহার করাকে **Nested `if` Statement** বলা হয়।

সহজভাবে, একটি condition সত্য হওয়ার পর তার ভেতরে আরও একটি condition পরীক্ষা করার প্রয়োজন হলে nested `if` ব্যবহার করা যায়।

Example:

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Entry allowed")
```

Output:

```text
Entry allowed
```

এখানে প্রথমে পরীক্ষা করা হয়েছে বয়স 18 বা তার বেশি কি না। Condition সত্য হওয়ার পর ভেতরের `if` পরীক্ষা করেছে পরিচয়পত্র আছে কি না।

দুটি condition-ই সত্য হওয়ায় `Entry allowed` print হয়েছে।

## 2. Why Do We Need Nested `if`?

কিছু problem-এ একটি condition-এর ফলাফলের ওপর ভিত্তি করে পরবর্তী condition পরীক্ষা করতে হয়।

যেমন:

- বয়স 18 বা তার বেশি হলে পরিচয়পত্র পরীক্ষা করা।
- Username সঠিক হলে password পরীক্ষা করা।
- Account balance যথেষ্ট হলে withdrawal অনুমোদন করা।
- Student eligible হলে তার marks অনুযায়ী grade নির্ধারণ করা।
- একটি number positive হলে সেটি even নাকি odd তা পরীক্ষা করা।

এ ধরনের ক্ষেত্রে nested `if` ব্যবহার করলে decision-এর ধাপগুলো আলাদা করে বোঝানো যায়।

## 3. Basic Syntax

```python
if condition_1:
    if condition_2:
        statement
```

এখানে:

- প্রথম `if` বাইরের condition পরীক্ষা করে।
- বাইরের condition সত্য হলেই ভেতরের `if`-এ প্রবেশ করা হয়।
- দ্বিতীয় `if` নিজের condition পরীক্ষা করে।
- উভয় condition সত্য হলে `statement` execute হয়।

একাধিক level-এ nested `if` ব্যবহার করা সম্ভব, তবে অপ্রয়োজনীয় nesting এড়িয়ে চলা ভালো।

## 4. How Nested `if` Works

Example:

```python
age = 22
has_ticket = True

if age >= 18:
    if has_ticket:
        print("You can enter")
```

Output:

```text
You can enter
```

Execution steps:

1. `age >= 18` পরীক্ষা করা হয়।
2. `22 >= 18` সত্য।
3. তাই ভেতরের `if has_ticket` পরীক্ষা করা হয়।
4. `has_ticket`-এর value `True`।
5. তাই `You can enter` print হয়।

**Important:** বাইরের condition মিথ্যা হলে ভেতরের `if` execute-ই হয় না।

## 5. Understanding Indentation

Nested `if`-এ indentation অত্যন্ত গুরুত্বপূর্ণ।

Correct example:

```python
age = 20

if age >= 18:
    print("Adult")

    if age >= 21:
        print("Age is at least 21")
```

Output:

```text
Adult
```

এখানে:

- `if age >= 18:` হলো outer `if`।
- `print("Adult")` outer block-এর অংশ।
- `if age >= 21:` outer block-এর ভেতরে রয়েছে।
- `print("Age is at least 21")` inner block-এর অংশ।

দ্বিতীয় condition মিথ্যা হওয়ায় শেষের message print হয়নি।

### Indentation Structure

```python
if outer_condition:
    # Outer block

    if inner_condition:
        # Inner block
```

Python-এ সাধারণত প্রতিটি indentation level-এর জন্য 4টি space ব্যবহার করা হয়।

## 6. Nested `if-else`

Nested `if`-এর ভেতরে `else` ব্যবহার করা যায়।

Example:

```python
age = 20
has_id = False

if age >= 18:
    if has_id:
        print("Entry allowed")
    else:
        print("ID required")
else:
    print("Underage")
```

Output:

```text
ID required
```

এখানে বাইরের `if` পরীক্ষা করেছে বয়স 18 বা তার বেশি কি না। সেটি সত্য হওয়ায় ভেতরের `if-else` কাজ করেছে।

ভেতরের condition মিথ্যা হওয়ায় `ID required` print হয়েছে।

**মনে রাখবে:** `else` যে `if`-এর সঙ্গে একই indentation level-এ থাকে, সেটি সেই `if`-এর সঙ্গে যুক্ত হয়।

## 7. Nested `if-elif-else`

Nested structure-এর ভেতরে `elif`-ও ব্যবহার করা যায়।

Example:

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Entry allowed")
    elif not has_id:
        print("ID required")
    else:
        print("Unknown status")
else:
    print("Underage")
```

Output:

```text
Entry allowed
```

এখানে inner `if-elif-else` বাইরের condition সত্য হওয়ার পরই পরীক্ষা করা হয়।

তবে এই উদাহরণে `elif not has_id` এবং শেষের `else` প্রয়োজনীয় নয়, কারণ `has_id` একটি Boolean value। এটি দেখানোর জন্যই রাখা হয়েছে যে nested block-এর ভেতরেও `elif` ও `else` ব্যবহার করা যায়।

আরও সহজভাবে:

```python
age = 20
has_id = False

if age >= 18:
    if has_id:
        print("Entry allowed")
    else:
        print("ID required")
else:
    print("Underage")
```

## 8. Practical Example 1: Positive Number and Even/Odd

একটি number positive হলে সেটি even নাকি odd তা পরীক্ষা করা যাক।

```python
number = int(input("Enter an integer: "))

if number > 0:
    if number % 2 == 0:
        print("Positive even number")
    else:
        print("Positive odd number")
else:
    print("Number is not positive")
```

Sample Input:

```text
Enter an integer: 8
```

Output:

```text
Positive even number
```

ব্যাখ্যা:

1. প্রথমে `number > 0` পরীক্ষা করা হয়।
2. Number positive হলে ভেতরের condition পরীক্ষা করা হয়।
3. `number % 2 == 0` সত্য হলে even, অন্যথায় odd print হয়।
4. Number positive না হলে outer `else` execute হয়।

Note: Zero এখানে positive নয়, তাই `Number is not positive` দেখাবে।

## 9. Practical Example 2: Login Verification

Username সঠিক হলে password পরীক্ষা করা হবে।

```python
username = input("Enter username: ")
password = input("Enter password: ")

if username == "admin":
    if password == "python123":
        print("Login successful")
    else:
        print("Incorrect password")
else:
    print("Incorrect username")
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

এখানে username সঠিক না হলে password condition-এ প্রবেশ করা হয় না।

**Security note:** এটি শুধু শেখার উদাহরণ। বাস্তব application-এ password source code-এ সরাসরি রাখা উচিত নয়; secure password storage এবং authentication ব্যবস্থা প্রয়োজন।

## 10. Practical Example 3: Student Eligibility

একজন student-এর attendance যথেষ্ট হলে তার marks অনুযায়ী result দেখানো যাক।

```python
attendance = float(input("Enter attendance percentage: "))

if 0 <= attendance <= 100:
    if attendance >= 75:
        marks = float(input("Enter marks: "))

        if 0 <= marks <= 100:
            if marks >= 40:
                print("Eligible and passed")
            else:
                print("Eligible but failed")
        else:
            print("Invalid marks")
    else:
        print("Attendance too low")
else:
    print("Invalid attendance")
```

Sample Input:

```text
Enter attendance percentage: 85
Enter marks: 72
```

Output:

```text
Eligible and passed
```

এখানে একাধিক ধাপে condition পরীক্ষা করা হয়েছে:

1. Attendance বৈধ কি না।
2. Attendance কমপক্ষে 75% কি না।
3. Marks বৈধ কি না।
4. Marks কমপক্ষে 40 কি না।

প্রতিটি পরবর্তী ধাপ আগের condition পূরণ হওয়ার পরই execute হয়।

এই threshold-গুলো উদাহরণস্বরূপ; বাস্তব course-এর নিয়ম অনুযায়ী পরিবর্তন করতে হবে।

## 11. Practical Example 4: ATM Withdrawal

Account balance যথেষ্ট হলে withdrawal অনুমোদন করা যাক।

```python
balance = 5000
amount = float(input("Enter withdrawal amount: "))

if amount > 0:
    if amount <= balance:
        balance = balance - amount
        print("Withdrawal successful")
        print("Remaining balance:", balance)
    else:
        print("Insufficient balance")
else:
    print("Invalid withdrawal amount")
```

Sample Input:

```text
Enter withdrawal amount: 1200
```

Output:

```text
Withdrawal successful
Remaining balance: 3800.0
```

এখানে:

- Withdrawal amount positive হতে হবে।
- Amount positive হলে balance যথেষ্ট কি না পরীক্ষা করা হয়।
- Balance যথেষ্ট হলে withdrawal সম্পন্ন হয়।

এটি basic logic শেখার উদাহরণ। বাস্তব financial application-এ transaction safety, concurrency এবং decimal monetary arithmetic-এর মতো অতিরিক্ত বিষয় প্রয়োজন।

## 12. Practical Example 5: Discount Eligibility

একজন customer member হলে purchase amount অনুযায়ী discount দেওয়া হবে।

```python
is_member = input("Are you a member? (yes/no): ").strip().lower()
amount = float(input("Enter purchase amount: "))

if is_member == "yes":
    if amount >= 5000:
        print("Discount: 15%")
    elif amount >= 3000:
        print("Discount: 10%")
    else:
        print("Discount: 5%")
else:
    print("No member discount")
```

Sample Input:

```text
Are you a member? (yes/no): yes
Enter purchase amount: 3500
```

Output:

```text
Discount: 10%
```

এখানে প্রথমে membership পরীক্ষা করা হয়েছে। Customer member হলে তার purchase amount অনুযায়ী inner `if-elif-else` কাজ করে।

## 13. Nested `if` vs `if-elif-else`

দুটির কাজ আলাদা।

### Nested `if`

একটি condition সত্য হওয়ার পর তার ভেতরে আরেকটি condition পরীক্ষা করা হয়।

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Allowed")
```

Output:

```text
Allowed
```

### `if-elif-else`

একাধিক বিকল্পের মধ্যে একটি branch নির্বাচন করা হয়।

```python
marks = 75

if marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
else:
    print("Below A")
```

Output:

```text
A
```

| Nested `if` | `if-elif-else` |
|---|---|
| একটি condition-এর ভেতরে আরেকটি condition থাকে | একই decision chain-এ একাধিক alternative থাকে |
| ধাপে ধাপে decision নেওয়ার জন্য উপযোগী | একাধিক alternative থেকে একটি বেছে নিতে উপযোগী |
| একাধিক indentation level তৈরি হয় | সাধারণত একই level-এ branch লেখা হয় |

প্রয়োজনে একই program-এ nested `if` এবং `if-elif-else` একসঙ্গে ব্যবহার করা যায়।

## 14. Nested `if` vs Logical Operators

কখনো nested `if`-এর পরিবর্তে `and` ব্যবহার করে একই logic লেখা যায়।

### Nested Version

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Entry allowed")
```

### Logical Operator Version

```python
age = 20
has_id = True

if age >= 18 and has_id:
    print("Entry allowed")
```

দুটি example-ই এখানে একই output দেয়।

### কখন কোনটি ব্যবহার করবে?

- Condition দুটি একসঙ্গে সত্য হওয়া প্রয়োজন হলে `and` ব্যবহার করে এক লাইনে লেখা যায়।
- প্রতিটি condition-এর জন্য আলাদা action দরকার হলে nested `if` সুবিধাজনক।
- Decision-এর ধাপগুলো স্পষ্টভাবে আলাদা করতে হলে nested `if` উপযোগী হতে পারে।

তবে সব nested logic-কে সরাসরি `and` দিয়ে প্রতিস্থাপন করা যায় না। ভেতরের condition-এর আগে বাইরের condition পূরণ হওয়া দরকার হতে পারে।

## 15. Common Mistakes

### Mistake 1: Incorrect Indentation

Incorrect:

```python
if age >= 18:
if has_id:
    print("Allowed")
```

এখানে inner `if`-এর indentation নেই, তাই `IndentationError` হবে।

Correct:

```python
if age >= 18:
    if has_id:
        print("Allowed")
```

### Mistake 2: Confusing the `else` Block

```python
age = 16
has_id = False

if age >= 18:
    if has_id:
        print("Allowed")
    else:
        print("ID required")
else:
    print("Underage")
```

Output:

```text
Underage
```

কারণ বাইরের condition মিথ্যা। তাই outer `else` execute হয়, inner `else` নয়।

### Mistake 3: Unnecessary Deep Nesting

অনেকগুলো nested level code-কে কঠিন করে তুলতে পারে।

অতিরিক্ত nesting এড়ানোর জন্য প্রয়োজন অনুযায়ী logical operators, `elif`, অথবা early-return pattern ব্যবহার করা যায়। `return` function-এর ভেতরে ব্যবহার করা হয়।

### Mistake 4: Forgetting Invalid Input

```python
age = int(input("Enter age: "))

if age >= 18:
    print("Adult")
```

এখানে negative age-এর জন্য কোনো validation নেই। Problem-এর requirement অনুযায়ী invalid input check করতে হতে পারে।

### Mistake 5: Checking the Inner Condition Too Early

ভেতরের condition outer block-এর বাইরে লিখলে সেটি আর nested থাকবে না।

যদি inner condition কেবল outer condition সত্য হলে পরীক্ষা করা প্রয়োজন হয়, তাহলে inner `if`-কে outer block-এর ভেতরে রাখতে হবে।

## 16. Practice Exercises

নিজে solve করার চেষ্টা করো।

### Exercise 1: Even or Odd

একটি integer input নাও। Number positive হলে nested `if` দিয়ে even বা odd নির্ধারণ করো। অন্যথায় `Not positive` দেখাও।

### Exercise 2: Login System

Username সঠিক হলে password পরীক্ষা করো। দুইটি সঠিক হলে `Login successful`, username ভুল হলে `Incorrect username` এবং শুধু password ভুল হলে `Incorrect password` দেখাও।

### Exercise 3: Student Result

প্রথমে attendance 75% বা তার বেশি কি না পরীক্ষা করো। Attendance যথেষ্ট হলে marks input নিয়ে marks 40 বা তার বেশি কি না পরীক্ষা করো।

### Exercise 4: ATM Withdrawal

একটি balance এবং withdrawal amount নাও। Amount positive হলে balance যথেষ্ট কি না পরীক্ষা করো। এরপর success অথবা error message দেখাও।

### Exercise 5: Output Prediction

```python
x = 10

if x > 5:
    if x > 15:
        print("A")
    else:
        print("B")
else:
    print("C")
```

Output কী হবে? কেন?

### Exercise 6: Output Prediction

```python
age = 17
has_id = True

if age >= 18:
    if has_id:
        print("Allowed")
    else:
        print("ID required")
else:
    print("Underage")
```

Output কী হবে?

### Exercise 7: Simplify the Condition

নিচের nested `if`-এর সমতুল্য `and` ব্যবহার করা code লেখো।

```python
if age >= 18:
    if has_id:
        print("Allowed")
```

## 17. Practice Answer Key

### Answer 1

```python
number = int(input("Enter an integer: "))

if number > 0:
    if number % 2 == 0:
        print("Even")
    else:
        print("Odd")
else:
    print("Not positive")
```

### Answer 2

```python
username = input("Enter username: ")
password = input("Enter password: ")

if username == "admin":
    if password == "python123":
        print("Login successful")
    else:
        print("Incorrect password")
else:
    print("Incorrect username")
```

### Answer 3

```python
attendance = float(input("Enter attendance: "))

if 0 <= attendance <= 100:
    if attendance >= 75:
        marks = float(input("Enter marks: "))

        if 0 <= marks <= 100:
            if marks >= 40:
                print("Passed")
            else:
                print("Failed")
        else:
            print("Invalid marks")
    else:
        print("Attendance too low")
else:
    print("Invalid attendance")
```

### Answer 4

```python
balance = 5000
amount = float(input("Enter withdrawal amount: "))

if amount > 0:
    if amount <= balance:
        balance -= amount
        print("Withdrawal successful")
        print("Remaining balance:", balance)
    else:
        print("Insufficient balance")
else:
    print("Invalid amount")
```

### Answer 5

Output:

```text
B
```

কারণ `x > 5` সত্য। এরপর inner condition `x > 15` মিথ্যা হওয়ায় inner `else` execute হয়।

### Answer 6

Output:

```text
Underage
```

কারণ `age >= 18` মিথ্যা। তাই outer `else` execute হয়।

### Answer 7

```python
if age >= 18 and has_id:
    print("Allowed")
```

## 18. Chapter Summary

- Nested `if` হলো একটি `if` block-এর ভেতরে আরেকটি `if` statement।
- Outer condition সত্য হলেই inner block-এ প্রবেশ করা হয়।
- Nested `if`-এ indentation সঠিক রাখা অত্যন্ত গুরুত্বপূর্ণ।
- Inner `if`, `elif` এবং `else` ব্যবহার করা যায়।
- `else` যে `if`-এর সঙ্গে একই indentation level-এ থাকে, সেটির সঙ্গে যুক্ত হয়।
- Login, eligibility, withdrawal এবং multi-step decision-এর মতো problem-এ nested `if` কাজে লাগে।
- অতিরিক্ত nesting code পড়তে কঠিন করে তুলতে পারে।
- সহজ condition combination-এর ক্ষেত্রে `and` বা `or` ব্যবহার করা যেতে পারে।

## 19. Self-Assessment Checklist

- [ ] Nested `if` কী, তা ব্যাখ্যা করতে পারি।
- [ ] একটি `if`-এর ভেতরে আরেকটি `if` লিখতে পারি।
- [ ] Nested `if-else`-এর execution flow বুঝি।
- [ ] Indentation অনুযায়ী কোন `else` কোন `if`-এর সঙ্গে যুক্ত, তা শনাক্ত করতে পারি।
- [ ] Nested `if` ব্যবহার করে login বা eligibility program লিখতে পারি।
- [ ] Nested `if` ও `if-elif-else`-এর পার্থক্য বুঝি।
- [ ] Nested `if` এবং logical operator-এর সম্পর্ক বুঝি।

## 20. Next Topic

পরবর্তী file:

`11_Logical_Operators_in_Conditions.md`

সেখানে `and`, `or` এবং `not` ব্যবহার করে একাধিক condition combine করার নিয়ম বিস্তারিতভাবে শেখা হবে।