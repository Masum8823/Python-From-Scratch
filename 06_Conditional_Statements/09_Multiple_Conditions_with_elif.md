# 09. Multiple Conditions with `elif`

## 1. Introduction

Python-এ একাধিক condition পরীক্ষা করে বিভিন্ন result নির্বাচন করতে `if-elif-else` structure ব্যবহার করা হয়।

যখন কোনো problem-এর দুইটির বেশি সম্ভাব্য outcome থাকে, তখন `elif` code-কে সহজ ও organized রাখে।

Example: Marks অনুযায়ী grade নির্ধারণ।

```python
marks = 75

if marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
elif marks >= 60:
    print("B")
elif marks >= 50:
    print("C")
else:
    print("Below C")
```

Output:

```text
A
```

এখানে Python প্রথমে `marks >= 80` পরীক্ষা করে। এটি মিথ্যা হওয়ায় পরের condition পরীক্ষা করে। `marks >= 70` সত্য হওয়ায় `A` print হয় এবং chain শেষ হয়।

## 2. Why Do We Need Multiple Conditions?

অনেক problem-এ একটি condition দিয়ে সব outcome নির্ধারণ করা যায় না।

যেমন:

- Marks অনুযায়ী grade নির্ধারণ।
- বয়স অনুযায়ী category নির্ধারণ।
- Temperature অনুযায়ী weather category নির্ধারণ।
- Number positive, negative অথবা zero কি না নির্ধারণ।
- Calculator-এ operator অনুযায়ী operation নির্বাচন।
- Purchase amount অনুযায়ী discount category নির্ধারণ।

এ ধরনের problem-এ অনেকগুলো independent `if` ব্যবহার করা সম্ভব হলেও, যখন একই decision-এর মধ্যে একটি মাত্র outcome নির্বাচন করতে হয়, তখন `if-elif-else` structure সাধারণত বেশি উপযোগী।

## 3. General Syntax

```python
if condition_1:
    statement_1
elif condition_2:
    statement_2
elif condition_3:
    statement_3
elif condition_4:
    statement_4
else:
    default_statement
```

এখানে:

- `if` প্রথম condition পরীক্ষা করে।
- `elif` পরবর্তী condition পরীক্ষা করে।
- একাধিক `elif` ব্যবহার করা যায়।
- `else` সব condition মিথ্যা হলে execute হয়।
- `else` optional।
- `elif` ও `else` ব্যবহার করার সময় indentation ঠিক রাখতে হয়।

**মনে রাখবে:** Python উপর থেকে নিচে condition পরীক্ষা করে এবং প্রথম সত্য condition-এর block execute করে।

## 4. How Multiple Conditions Are Evaluated

Example:

```python
score = 65

if score >= 80:
    print("Excellent")
elif score >= 70:
    print("Very Good")
elif score >= 60:
    print("Good")
elif score >= 40:
    print("Pass")
else:
    print("Fail")
```

Output:

```text
Good
```

Execution:

| Condition | Result | Action |
|---|---|---|
| `score >= 80` | `False` | পরের condition পরীক্ষা |
| `score >= 70` | `False` | পরের condition পরীক্ষা |
| `score >= 60` | `True` | `Good` print করে chain শেষ |
| `score >= 40` | পরীক্ষা হয় না | Skip |
| `else` | execute হয় না | Skip |

প্রথম সত্য condition পাওয়া গেলে বাকি branch-গুলো আর পরীক্ষা করা হয় না।

## 5. Importance of Condition Order

একাধিক condition ব্যবহার করার সময় সঠিক order অত্যন্ত গুরুত্বপূর্ণ।

ধরো, marks অনুযায়ী grade দিতে হবে:

- 80 বা তার বেশি → A+
- 70 বা তার বেশি → A
- 60 বা তার বেশি → B
- অন্যথায় → Below B

### Incorrect Order

```python
marks = 85

if marks >= 60:
    print("B")
elif marks >= 70:
    print("A")
elif marks >= 80:
    print("A+")
else:
    print("Below B")
```

Output:

```text
B
```

কারণ `85 >= 60` প্রথম condition-এই সত্য। তাই Python আর পরের condition-গুলো পরীক্ষা করে না।

### Correct Order

```python
marks = 85

if marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
elif marks >= 60:
    print("B")
else:
    print("Below B")
```

Output:

```text
A+
```

**Rule:** যখন একাধিক condition-এর threshold পরস্পরের সঙ্গে overlap করে, তখন সাধারণত সবচেয়ে restrictive বা বড় threshold আগে পরীক্ষা করো।

তবে সব problem-এ descending order প্রয়োজন হয় না। Condition-এর logical relationship বুঝে order নির্ধারণ করতে হবে।

## 6. Understanding Overlapping Conditions

দুটি condition-এর মধ্যে overlap থাকলে একটি value একাধিক condition পূরণ করতে পারে।

Example:

```python
number = 15

if number > 0:
    print("Positive")
elif number > 10:
    print("Greater than 10")
```

Output:

```text
Positive
```

এখানে `15 > 0` এবং `15 > 10`—দুটিই সত্য। কিন্তু প্রথম condition সত্য হওয়ায় দ্বিতীয় branch execute হয়নি।

যদি দুইটি property-ই দেখাতে চাও, তাহলে independent `if` ব্যবহার করো:

```python
number = 15

if number > 0:
    print("Positive")

if number > 10:
    print("Greater than 10")
```

Output:

```text
Positive
Greater than 10
```

**মূল পার্থক্য:**

- একই decision-এর মধ্যে একটি outcome বেছে নিতে `if-elif-else`।
- একাধিক সত্য condition-এর জন্য একাধিক action চালাতে independent `if`।

## 7. Checking Ranges with `elif`

একটি value কোন range-এর মধ্যে আছে, তা নির্ধারণ করতে `elif` ব্যবহার করা যায়।

Example: Age category

```python
age = 25

if age < 0:
    print("Invalid age")
elif age < 13:
    print("Child")
elif age < 20:
    print("Teenager")
elif age < 60:
    print("Adult")
else:
    print("Senior")
```

Output:

```text
Adult
```

এখানে:

- Negative age → Invalid age
- 0–12 → Child
- 13–19 → Teenager
- 20–59 → Adult
- 60 বা তার বেশি → Senior

### Why Does This Work?

ধরো, `age = 25`।

1. `age < 0` → False
2. `age < 13` → False
3. `age < 20` → False
4. `age < 60` → True

তাই `Adult` print হয়।

আগের condition-গুলো মিথ্যা হওয়ায় প্রতিটি পরবর্তী condition-এর অর্থ আগের range-গুলো বাদ দিয়ে বোঝা যায়।

## 8. Using Explicit Range Conditions

Range checking-এর আরেকটি উপায় হলো `and` দিয়ে lower ও upper boundary দুটোই পরীক্ষা করা।

Example:

```python
marks = 75

if 80 <= marks <= 100:
    print("A+")
elif 70 <= marks < 80:
    print("A")
elif 60 <= marks < 70:
    print("B")
elif 40 <= marks < 60:
    print("Pass")
elif 0 <= marks < 40:
    print("Fail")
else:
    print("Invalid marks")
```

Output:

```text
A
```

এখানে chained comparison ব্যবহার করা হয়েছে।

যেমন:

```python
70 <= marks < 80
```

এর অর্থ:

```python
marks >= 70 and marks < 80
```

দুটিই একই logic প্রকাশ করে।

এই explicit range version-এ 0 থেকে 100-এর বাইরে থাকা marks-কে invalid হিসেবে দেখানো হচ্ছে।

## 9. Practical Example 1: Grade Calculator

একটি student-এর marks অনুযায়ী grade নির্ধারণ করো।

```python
marks = float(input("Enter marks (0-100): "))

if marks < 0 or marks > 100:
    print("Invalid marks")
elif marks >= 80:
    print("Grade: A+")
elif marks >= 70:
    print("Grade: A")
elif marks >= 60:
    print("Grade: B")
elif marks >= 50:
    print("Grade: C")
elif marks >= 40:
    print("Grade: D")
else:
    print("Grade: F")
```

Sample Input:

```text
Enter marks (0-100): 88
```

Output:

```text
Grade: A+
```

এখানে invalid range প্রথমে পরীক্ষা করা হয়েছে। তারপর grade-এর threshold বড় থেকে ছোট ক্রমে পরীক্ষা করা হয়েছে।

এটি একটি example grading scale; বাস্তব পরীক্ষায় নির্ধারিত grading policy ব্যবহার করতে হবে।

## 10. Practical Example 2: Temperature Category

Temperature অনুযায়ী একটি simple category নির্ধারণ করা যাক।

```python
temperature = float(input("Enter temperature in Celsius: "))

if temperature < 0:
    print("Below freezing")
elif temperature < 15:
    print("Cold")
elif temperature < 25:
    print("Mild")
elif temperature < 35:
    print("Warm")
else:
    print("Hot")
```

Sample Input:

```text
Enter temperature in Celsius: 28
```

Output:

```text
Warm
```

এই category-গুলো শেখার উদাহরণ; বাস্তব আবহাওয়ার অনুভূতি humidity, wind এবং অন্যান্য বিষয়ের ওপরও নির্ভর করে।

## 11. Practical Example 3: Electricity Usage Category

বিদ্যুৎ ব্যবহারের unit অনুযায়ী category নির্ধারণ করা যাক।

```python
units = int(input("Enter units used: "))

if units < 0:
    print("Invalid units")
elif units <= 100:
    print("Low usage")
elif units <= 300:
    print("Medium usage")
else:
    print("High usage")
```

Sample Input:

```text
Enter units used: 250
```

Output:

```text
Medium usage
```

এই code usage category নির্ধারণ করে; এটি কোনো actual electricity bill calculate করে না।

## 12. Practical Example 4: Simple Calculator

Operator অনুযায়ী calculation নির্বাচন করা যাক।

```python
a = float(input("Enter first number: "))
operator = input("Enter operator (+, -, *, /): ")
b = float(input("Enter second number: "))

if operator == "+":
    print("Result:", a + b)
elif operator == "-":
    print("Result:", a - b)
elif operator == "*":
    print("Result:", a * b)
elif operator == "/":
    if b == 0:
        print("Cannot divide by zero")
    else:
        print("Result:", a / b)
else:
    print("Invalid operator")
```

Sample Input:

```text
Enter first number: 12
Enter operator (+, -, *, /): /
Enter second number: 4
```

Output:

```text
Result: 3.0
```

এখানে operator অনুযায়ী একটি operation নির্বাচন করা হয়। Division-এর ক্ষেত্রে nested `if` দিয়ে zero check করা হয়েছে।

## 13. Practical Example 5: Discount Category

Purchase amount অনুযায়ী discount rate নির্ধারণ করা যাক।

```python
amount = float(input("Enter purchase amount: "))

if amount < 0:
    print("Invalid amount")
elif amount >= 5000:
    print("Discount rate: 15%")
elif amount >= 3000:
    print("Discount rate: 10%")
elif amount >= 1000:
    print("Discount rate: 5%")
else:
    print("No discount")
```

Sample Input:

```text
Enter purchase amount: 3500
```

Output:

```text
Discount rate: 10%
```

এখানে শুধু discount rate দেখানো হয়েছে, discount-এর টাকার পরিমাণ calculate করা হয়নি।

## 14. Practical Example 6: Number Classification

একটি number zero, positive even, positive odd, negative even অথবা negative odd কি না, তা নির্ধারণ করা যাক।

```python
number = int(input("Enter an integer: "))

if number == 0:
    print("Zero")
elif number > 0 and number % 2 == 0:
    print("Positive even")
elif number > 0 and number % 2 != 0:
    print("Positive odd")
elif number < 0 and number % 2 == 0:
    print("Negative even")
else:
    print("Negative odd")
```

Sample Input:

```text
Enter an integer: -7
```

Output:

```text
Negative odd
```

এখানে:

- Zero আলাদাভাবে পরীক্ষা করা হয়েছে।
- Positive number হলে even/odd পরীক্ষা করা হয়েছে।
- Negative number হলে even/odd অনুযায়ী classification হয়েছে।

Python-এ negative integer-এর ক্ষেত্রেও `number % 2 == 0` even number শনাক্ত করে।

## 15. Practical Example 7: Login Attempt Category

একটি number-এর ভিত্তিতে login attempt-এর status দেখানো যাক।

```python
attempts = int(input("Enter failed login attempts: "))

if attempts < 0:
    print("Invalid attempt count")
elif attempts == 0:
    print("No failed attempts")
elif attempts < 3:
    print("Warning")
elif attempts < 5:
    print("High risk")
else:
    print("Account review required")
```

Sample Input:

```text
Enter failed login attempts: 4
```

Output:

```text
High risk
```

এটি শুধু conditional statement শেখানোর উদাহরণ। বাস্তব security system-এ risk policy আলাদাভাবে নির্ধারণ করতে হয়।

## 16. Handling Boundary Values

Range-based condition লেখার সময় boundary value বিশেষভাবে পরীক্ষা করা দরকার।

ধরো, category:

- 80 বা তার বেশি → A+
- 70 বা তার বেশি → A
- 60 বা তার বেশি → B
- অন্যথায় → Below B

| Marks | Expected output |
|---:|---|
| 79 | A |
| 80 | A+ |
| 70 | A |
| 69 | B |
| 60 | B |
| 59 | Below B |

Boundary value হলো এমন value, যা একটি range-এর শুরু বা শেষের কাছে থাকে এবং condition ঠিকভাবে লেখা হয়েছে কি না যাচাই করতে সাহায্য করে।

**Tip:** `79`, `80`, `70`, `69`, `60` এবং `59`-এর মতো value দিয়ে program test করলে threshold-related bug সহজে ধরা যায়।

## 17. Common Mistakes

### Mistake 1: Checking a Broad Condition First

Incorrect:

```python
marks = 90

if marks >= 40:
    print("Pass")
elif marks >= 80:
    print("A+")
```

Output:

```text
Pass
```

কারণ প্রথম condition সত্য হওয়ায় দ্বিতীয় branch execute হয়নি।

### Mistake 2: Forgetting the Lower Boundary

ধরো, একটি category-তে 50 থেকে 69 পর্যন্ত marks রাখতে হবে।

```python
if marks < 70:
    print("Category B")
```

এই condition শুধু 50–69 নয়, 50-এর নিচের সব value-ও গ্রহণ করবে।

সঠিক range check:

```python
if 50 <= marks < 70:
    print("Category B")
```

### Mistake 3: Incorrect Range Logic

Incorrect:

```python
if marks >= 50 or marks < 70:
    print("Category B")
```

এই condition প্রায় সব numeric value-এর জন্য সত্য, কারণ `marks >= 50` অথবা `marks < 70`—অন্তত একটি সাধারণত সত্য হবে।

Correct:

```python
if marks >= 50 and marks < 70:
    print("Category B")
```

অথবা:

```python
if 50 <= marks < 70:
    print("Category B")
```

### Mistake 4: Ignoring Invalid Input Range

```python
marks = float(input("Enter marks: "))

if marks >= 80:
    print("A+")
elif marks >= 40:
    print("Pass")
else:
    print("Fail")
```

এখানে `marks = 150` দিলেও `A+` দেখাবে। যদি marks অবশ্যই 0 থেকে 100-এর মধ্যে হতে হয়, তাহলে invalid range প্রথমে check করতে হবে।

### Mistake 5: Using `elif` When Multiple Results Are Needed

যদি একই number-এর জন্য `Positive` এবং `Greater than 10`—দুটিই print করতে হয়, তাহলে independent `if` ব্যবহার করতে হবে। `elif` chain-এ প্রথম সত্য branch-এর পরের branch-গুলো পরীক্ষা করা হয় না।

## 18. Problem-Solving Method

একাধিক condition-এর problem সমাধান করার সময় এই ধাপগুলো অনুসরণ করো:

1. Problem-এর সব সম্ভাব্য outcome চিহ্নিত করো।
2. প্রতিটি outcome-এর condition লিখে ফেলো।
3. Invalid input বা exceptional case থাকলে সেগুলো বিবেচনা করো।
4. Overlapping condition আছে কি না যাচাই করো।
5. Threshold condition-গুলো উপযুক্ত order-এ সাজাও।
6. প্রতিটি block-এর indentation ঠিক রাখো।
7. Boundary value দিয়ে program test করো।
8. Condition-এর order বদলালে output পরিবর্তন হচ্ছে কি না যাচাই করো।

এই পদ্ধতি অনুসরণ করলে complex decision-making problem-ও সহজে organize করা যায়।

## 19. Practice Exercises

নিজে solve করার চেষ্টা করো।

### Exercise 1: Grade Calculator

Marks অনুযায়ী grade নির্ধারণ করো:

- 80 বা তার বেশি → A+
- 70 বা তার বেশি → A
- 60 বা তার বেশি → B
- 50 বা তার বেশি → C
- 40 বা তার বেশি → D
- অন্যথায় → F

Marks 0–100-এর বাইরে হলে `Invalid marks` দেখাবে।

### Exercise 2: Age Category

বয়স অনুযায়ী category নির্ধারণ করো:

- Negative → Invalid age
- 13-এর কম → Child
- 20-এর কম → Teenager
- 60-এর কম → Adult
- অন্যথায় → Senior

### Exercise 3: Number Classification

একটি integer input নিয়ে zero, positive even, positive odd, negative even অথবা negative odd হিসেবে classify করো।

### Exercise 4: Calculator

দুটি number ও একটি operator input নিয়ে `if-elif-else` ব্যবহার করে calculation করো। Division-এর ক্ষেত্রে zero check করো।

### Exercise 5: Range Checking

একটি integer input নাও:

- 1–10 → Small
- 11–50 → Medium
- 51–100 → Large
- অন্যথায় → Outside range

### Exercise 6: Output Prediction

```python
x = 75

if x >= 50:
    print("A")
elif x >= 70:
    print("B")
else:
    print("C")
```

Output কী হবে? Condition-এর order কেন গুরুত্বপূর্ণ, তা ব্যাখ্যা করো।

### Exercise 7: Find the Error

```python
marks = 65

if marks >= 80:
    print("A+")
elif marks >= 60 or marks < 70:
    print("B")
else:
    print("Below B")
```

`elif` condition-এ logic-এর সমস্যা কী? সঠিক condition লিখো।

## 20. Practice Answer Key

### Answer 1

```python
marks = float(input("Enter marks (0-100): "))

if marks < 0 or marks > 100:
    print("Invalid marks")
elif marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
elif marks >= 60:
    print("B")
elif marks >= 50:
    print("C")
elif marks >= 40:
    print("D")
else:
    print("F")
```

### Answer 2

```python
age = int(input("Enter age: "))

if age < 0:
    print("Invalid age")
elif age < 13:
    print("Child")
elif age < 20:
    print("Teenager")
elif age < 60:
    print("Adult")
else:
    print("Senior")
```

### Answer 3

```python
number = int(input("Enter an integer: "))

if number == 0:
    print("Zero")
elif number > 0 and number % 2 == 0:
    print("Positive even")
elif number > 0:
    print("Positive odd")
elif number % 2 == 0:
    print("Negative even")
else:
    print("Negative odd")
```

### Answer 4

```python
a = float(input("Enter first number: "))
operator = input("Enter operator (+, -, *, /): ")
b = float(input("Enter second number: "))

if operator == "+":
    print(a + b)
elif operator == "-":
    print(a - b)
elif operator == "*":
    print(a * b)
elif operator == "/":
    if b == 0:
        print("Cannot divide by zero")
    else:
        print(a / b)
else:
    print("Invalid operator")
```

### Answer 5

```python
number = int(input("Enter an integer: "))

if 1 <= number <= 10:
    print("Small")
elif 11 <= number <= 50:
    print("Medium")
elif 51 <= number <= 100:
    print("Large")
else:
    print("Outside range")
```

### Answer 6

Output:

```text
A
```

কারণ `75 >= 50` সত্য। তাই Python দ্বিতীয় `elif` condition পরীক্ষা করে না।

### Answer 7

সমস্যাটি হলো `or` ব্যবহার করা হয়েছে। `marks >= 60 or marks < 70` অনেক বেশি value-এর জন্যও সত্য হতে পারে।

সঠিক condition:

```python
elif marks >= 60 and marks < 70:
    print("B")
```

অথবা:

```python
elif 60 <= marks < 70:
    print("B")
```

## 21. Chapter Summary

- একাধিক outcome-এর মধ্যে একটি নির্বাচন করতে `if-elif-else` ব্যবহার করা যায়।
- Python ওপর থেকে নিচে condition পরীক্ষা করে।
- প্রথম সত্য condition-এর block execute হয়।
- Overlapping condition-এর ক্ষেত্রে order গুরুত্বপূর্ণ।
- Threshold-based condition সাধারণত সবচেয়ে restrictive threshold থেকে শুরু করা সুবিধাজনক।
- Range check করতে `and` অথবা chained comparison ব্যবহার করা যায়।
- Invalid input range প্রথমে check করা অনেক ক্ষেত্রে প্রয়োজন।
- একাধিক result প্রয়োজন হলে independent `if` ব্যবহার করা উচিত।
- Boundary value দিয়ে test করলে logic-এর ভুল ধরা সহজ হয়।

## 22. Self-Assessment Checklist

- [ ] একাধিক condition-এর জন্য `if-elif-else` লিখতে পারি।
- [ ] Condition-এর order কেন গুরুত্বপূর্ণ, তা বুঝি।
- [ ] Overlapping condition শনাক্ত করতে পারি।
- [ ] Range checking করতে পারি।
- [ ] Boundary value দিয়ে program test করতে পারি।
- [ ] `and` ও `or` সঠিকভাবে ব্যবহার করতে পারি।
- [ ] Grade calculator ও number classifier লিখতে পারি।
- [ ] Independent `if` ও `elif` chain-এর পার্থক্য বুঝি।

## 23. Next Topic

পরবর্তী file:

`10_Nested_if_Statements.md`

সেখানে একটি `if` block-এর ভেতরে আরেকটি `if` statement ব্যবহার করে multiple-level decision নেওয়া শেখা হবে।