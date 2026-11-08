# 23. Choosing Between if, elif and match-case

## 1. Introduction

Python-এ `if`, `elif` এবং `match-case` ব্যবহার করে বিভিন্ন condition বা pattern অনুযায়ী program-এর execution নিয়ন্ত্রণ করা যায়।

তবে সব পরিস্থিতিতে একই statement ব্যবহার করা উচিত নয়। Problem-এর ধরন অনুযায়ী সঠিক statement নির্বাচন করতে হয়।

- **`if`** — একটি condition পরীক্ষা করতে।
- **`if-elif-else`** — একাধিক condition থেকে উপযুক্ত branch নির্বাচন করতে।
- **`match-case`** — বিভিন্ন নির্দিষ্ট value বা pattern অনুযায়ী কাজ নির্বাচন করতে।

## 2. When to Use if

কোনো একটি condition পরীক্ষা করতে `if` ব্যবহার করা হয়।

উদাহরণ:

```python
age = 20

if age >= 18:
    print("You are eligible to vote.")
```

Output:

```text
You are eligible to vote.
```

এখানে `age >= 18` True হলে message print হবে। Condition False হলে কোনো output হবে না।

**কখন ব্যবহার করবে?**

- একটি condition পরীক্ষা করতে।
- কোনো কাজের আগে eligibility যাচাই করতে।
- Positive বা negative condition পরীক্ষা করতে।
- কোনো action প্রয়োজন কি না নির্ধারণ করতে।

আরও একটি উদাহরণ:

```python
balance = 500

if balance >= 100:
    print("You can make a purchase.")
```

## 3. When to Use if-else

দুটি alternative-এর মধ্যে একটি বেছে নিতে `if-else` ব্যবহার করা হয়।

উদাহরণ:

```python
number = 7

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

Output:

```text
Odd
```

এখানে number জোড় হলে `if` block execute হবে। অন্যথায় `else` block execute হবে।

**কখন ব্যবহার করবে?**

- True বা False অনুযায়ী আলাদা কাজ করতে।
- Pass বা Fail নির্ধারণ করতে।
- Even বা Odd পরীক্ষা করতে।
- Login success বা failure-এর মতো দুইটি outcome পরিচালনা করতে।

## 4. When to Use if-elif-else

যখন একাধিক condition পরীক্ষা করে একটি উপযুক্ত branch নির্বাচন করতে হয়, তখন `if-elif-else` ব্যবহার করা ভালো।

উদাহরণ:

```python
marks = 85

if marks >= 80:
    print("Grade A")
elif marks >= 70:
    print("Grade B")
elif marks >= 60:
    print("Grade C")
else:
    print("Grade F")
```

Output:

```text
Grade A
```

Python প্রথমে `if` condition পরীক্ষা করে। সেটি False হলে পরবর্তী `elif` condition পরীক্ষা করে। প্রথম True condition-এর block execute হওয়ার পর chain শেষ হয়।

**কখন ব্যবহার করবে?**

- Marks অনুযায়ী grade নির্ধারণ করতে।
- বয়স বা temperature-এর range অনুযায়ী category নির্ধারণ করতে।
- একাধিক logical condition পরীক্ষা করতে।
- বিভিন্ন comparison-এর ভিত্তিতে সিদ্ধান্ত নিতে।

### Important: Condition-এর Order

Condition সঠিক ক্রমে লেখা জরুরি।

ভুল উদাহরণ:

```python
marks = 85

if marks >= 60:
    print("Grade C")
elif marks >= 80:
    print("Grade A")
```

Output:

```text
Grade C
```

কারণ `marks >= 60` প্রথমেই True হয়েছে। ফলে পরের `elif` পরীক্ষা করা হয়নি।

সঠিক উদাহরণ:

```python
marks = 85

if marks >= 80:
    print("Grade A")
elif marks >= 60:
    print("Grade C")
```

Output:

```text
Grade A
```

## 5. When to Use match-case

যখন একটি value বা structure-এর বিভিন্ন নির্দিষ্ট pattern অনুযায়ী কাজ নির্বাচন করতে হয়, তখন `match-case` ব্যবহার করা সুবিধাজনক হতে পারে।

উদাহরণ:

```python
command = "start"

match command:
    case "start":
        print("Starting program")
    case "stop":
        print("Stopping program")
    case "pause":
        print("Pausing program")
    case _:
        print("Unknown command")
```

Output:

```text
Starting program
```

**কখন ব্যবহার করবে?**

- Menu থেকে নির্দিষ্ট option নির্বাচন করতে।
- Command অনুযায়ী action নিতে।
- নির্দিষ্ট status বা category handle করতে।
- একাধিক value-এর জন্য একই action নির্ধারণ করতে।
- Tuple বা অন্যান্য supported structure-এর pattern পরীক্ষা করতে।

মনে রাখবে, `match-case` Python 3.10 বা তার পরবর্তী version-এ ব্যবহার করা যায়।

## 6. Comparison Table

| বিষয় | `if` | `if-elif-else` | `match-case` |
|---|---|---|---|
| প্রধান কাজ | একটি condition পরীক্ষা | একাধিক condition পরীক্ষা | Pattern অনুযায়ী branch নির্বাচন |
| Range checking | উপযোগী | খুব উপযোগী | Guard দিয়ে সম্ভব |
| Boolean conditions | উপযোগী | খুব উপযোগী | সাধারণত কম সুবিধাজনক |
| নির্দিষ্ট menu option | সম্ভব | সম্ভব | খুব উপযোগী |
| একাধিক alternative | `if`-এর সঙ্গে অন্য statement লাগতে পারে | উপযোগী | OR pattern (`\|`) ব্যবহার করা যায় |
| Structure matching | সাধারণত আলাদা logic লাগে | সাধারণত আলাদা logic লাগে | Built-in pattern matching |
| Version | সাধারণ Python versions | সাধারণ Python versions | Python 3.10+ |

## 7. Same Problem Using Different Statements

একটি problem বিভিন্নভাবে সমাধান করা যায়। নিচের উদাহরণগুলো দেখলে পার্থক্য পরিষ্কার হবে।

### Example 1: Number Positive কি না

একটি condition যথেষ্ট হলে `if` ব্যবহার করা যায়।

```python
number = 10

if number > 0:
    print("Positive")
```

Output:

```text
Positive
```

### Example 2: Positive, Negative অথবা Zero

এখানে একাধিক condition রয়েছে, তাই `if-elif-else` স্বাভাবিক পছন্দ।

```python
number = -5

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

Output:

```text
Negative
```

### Example 3: Menu Option নির্বাচন

নির্দিষ্ট command বা option নির্বাচন করতে `match-case` পরিষ্কারভাবে লেখা যায়।

```python
choice = 2

match choice:
    case 1:
        print("Add")
    case 2:
        print("Subtract")
    case 3:
        print("Multiply")
    case _:
        print("Invalid choice")
```

Output:

```text
Subtract
```

## 8. Can We Always Replace if-elif with match-case?

না। `match-case` সব ধরনের `if-elif` condition-এর সরাসরি বিকল্প নয়।

যেমন:

```python
age = 25

if age >= 18 and age <= 60:
    print("Eligible")
```

এখানে একটি range এবং logical condition পরীক্ষা করা হচ্ছে। তাই `if` ব্যবহার করা সহজ ও পরিষ্কার।

অন্যদিকে:

```python
status = "pending"

match status:
    case "pending":
        print("Please wait")
    case "approved":
        print("Request approved")
    case "rejected":
        print("Request rejected")
    case _:
        print("Unknown status")
```

এখানে নির্দিষ্ট status অনুযায়ী কাজ নির্বাচন করা হচ্ছে। তাই `match-case` একটি ভালো পছন্দ।

**মূল কথা:** শুধু code ছোট করার জন্য নয়, problem-এর logic সবচেয়ে পরিষ্কারভাবে প্রকাশ করার জন্য statement নির্বাচন করবে।

## 9. Common Mistakes

### Mistake 1: সব condition-এ শুধু if ব্যবহার করা

অনেক independent `if` ব্যবহার করলে একাধিক block execute হতে পারে।

```python
marks = 85

if marks >= 60:
    print("Pass")

if marks >= 80:
    print("Grade A")
```

Output:

```text
Pass
Grade A
```

যদি কেবল একটি grade নির্বাচন করতে চাও, তাহলে সঠিকভাবে সাজানো `if-elif-else` ব্যবহার করা ভালো।

### Mistake 2: if-elif-এর condition ভুল ক্রমে লেখা

বড় threshold আগে পরীক্ষা করা উচিত, যদি grade-এর মতো overlapping range থাকে।

### Mistake 3: match-case দিয়ে range পরীক্ষা জটিল করা

সাধারণ numeric range-এর জন্য `if-elif-else` সাধারণত সহজবোধ্য।

### Mistake 4: match-case-এ data type ভুলে যাওয়া

`input()` string return করে। তাই string input-এর সঙ্গে integer pattern সরাসরি মিলবে না।

### Mistake 5: শুধু নতুন syntax ব্যবহার করার জন্য match-case বেছে নেওয়া

যে statement code-কে সবচেয়ে readable করে, সেটিই ব্যবহার করা উচিত।

## 10. Decision-Making Guide

| তোমার problem | Recommended statement |
|---|---|
| একটি condition পরীক্ষা | `if` |
| দুটি alternative | `if-else` |
| একাধিক range পরীক্ষা | `if-elif-else` |
| একাধিক Boolean condition | `if-elif-else` |
| Menu বা নির্দিষ্ট command নির্বাচন | `match-case` অথবা `if-elif-else` |
| একাধিক value একই action-এ পাঠানো | `match-case`-এর OR pattern বা `if`-এর logical condition |
| Tuple-এর structure match করা | `match-case` |

## 11. Practice Exercises

### Question 1

একটি number positive কি না পরীক্ষা করার জন্য কোন statement সবচেয়ে সহজ?

### Question 2

Marks অনুযায়ী A, B, C এবং F grade নির্ধারণ করতে কোন statement ব্যবহার করা ভালো?

### Question 3

একটি menu-তে `1 = Add`, `2 = Subtract`, `3 = Multiply`—এ ধরনের option handle করার জন্য `match-case` কীভাবে ব্যবহার করবে?

### Question 4

নিচের code-এর output কী?

```python
marks = 75

if marks >= 60:
    print("Pass")
elif marks >= 70:
    print("Grade B")
```

### Question 5

নিচের problem-এ কোন statement বেশি উপযোগী এবং কেন?

একজন ব্যবহারকারীর age `18` থেকে `60`-এর মধ্যে কি না পরীক্ষা করতে হবে।

### Question 6

`match-case` ব্যবহার করতে Python-এর কোন version বা পরবর্তী version প্রয়োজন?

## 12. Answer Key

**Answer 1:** `if`, কারণ একটি condition পরীক্ষা করতে হবে।

**Answer 2:** `if-elif-else`, কারণ একাধিক marks range পরীক্ষা করে একটি grade নির্বাচন করতে হবে।

**Answer 3:**

```python
choice = 1

match choice:
    case 1:
        print("Add")
    case 2:
        print("Subtract")
    case 3:
        print("Multiply")
    case _:
        print("Invalid choice")
```

**Answer 4:**

```text
Pass
```

কারণ প্রথম condition `marks >= 60` True হয়েছে। তাই `elif` পরীক্ষা করা হয়নি।

**Answer 5:** `if` বা `if-else` ব্যবহার করা বেশি সহজ, কারণ এখানে একটি numeric range পরীক্ষা করতে হবে।

```python
if 18 <= age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

**Answer 6:** Python 3.10 বা তার পরবর্তী version।

## 13. Quick Revision

- `if` একটি condition পরীক্ষা করে।
- `if-else` দুটি alternative-এর মধ্যে সিদ্ধান্ত নেয়।
- `if-elif-else` একাধিক condition পরীক্ষা করে।
- `match-case` নির্দিষ্ট value বা pattern অনুযায়ী কাজ নির্বাচন করে।
- Marks বা age-এর মতো range পরীক্ষা করতে `if-elif-else` সাধারণত বেশি উপযোগী।
- Menu, command ও নির্দিষ্ট status-এর জন্য `match-case` ভালো বিকল্প হতে পারে।
- `match-case` ব্যবহার করতে Python 3.10+ প্রয়োজন।
- Condition-এর order এবং code readability সবসময় গুরুত্ব দিতে হবে।

## 14. Self-Assessment Checklist

- [ ] `if`, `if-else` এবং `if-elif-else`-এর পার্থক্য বুঝি।
- [ ] কখন `match-case` ব্যবহার করতে হয়, তা জানি।
- [ ] Range checking-এর জন্য উপযুক্ত statement বেছে নিতে পারি।
- [ ] Menu-based program তৈরি করতে পারি।
- [ ] Condition-এর order কেন গুরুত্বপূর্ণ, তা বুঝি।
- [ ] Problem অনুযায়ী readable code লিখতে পারি।

**পরবর্তী টপিক:** `24_Conditional_Statements_with_User_Input.md`
