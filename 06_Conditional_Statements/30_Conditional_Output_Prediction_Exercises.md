# 30. Conditional Output Prediction Exercises

## 1. Introduction

**Output Prediction** হলো কোনো Python code execute করার আগে তার সম্ভাব্য output নির্ধারণ করা।

এটি শেখার মাধ্যমে তুমি বুঝতে পারবে:

- কোন condition True বা False হচ্ছে।
- `if`, `elif` ও `else` কীভাবে কাজ করে।
- `and`, `or` ও `not` কীভাবে result পরিবর্তন করে।
- Nested conditions কীভাবে execute হয়।
- কোন branch execute হবে এবং কোনটি skip হবে।
- Membership, identity এবং chained comparison কীভাবে কাজ করে।

## 2. Rules to Remember Before Predicting Output

### Rule 1: First True Condition

একটি `if-elif-else` chain-এ প্রথম True condition-এর block execute হয়। এরপর chain-এর বাকি branch-গুলো skip হয়।

### Rule 2: Independent if Statements

আলাদা `if` statement থাকলে একাধিক block execute হতে পারে।

### Rule 3: Logical Operators

- `and`: সব condition True হতে হবে।
- `or`: অন্তত একটি condition True হতে হবে।
- `not`: Boolean result উল্টে দেয়।

### Rule 4: Indentation Matters

Indentation নির্ধারণ করে কোন statement কোন block-এর অংশ।

### Rule 5: Comparison Boundaries

`>` এবং `<` strict comparison; `>=` এবং `<=` boundary value-ও অন্তর্ভুক্ত করে।

### Rule 6: `and` and `or` Return Values

Python-এ `and` ও `or` সব সময় Boolean value return করে না। এগুলো operand-এর value-ও return করতে পারে।

```python
print(5 and 3)
print(0 or 7)
```

Output:

```text
3
7
```

## 3. Level 1: Basic if-else

### Question 1

```python
x = 10

if x > 5:
    print("A")
else:
    print("B")
```

### Question 2

```python
marks = 35

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

### Question 3

```python
number = 0

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

### Question 4

```python
age = 18

if age > 18:
    print("Adult")
else:
    print("Not adult")
```

### Question 5

```python
number = 12

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

## 4. Level 2: if-elif-else

### Question 6

```python
marks = 85

if marks >= 90:
    print("A+")
elif marks >= 80:
    print("A")
elif marks >= 70:
    print("B")
else:
    print("C")
```

### Question 7

```python
x = 50

if x < 10:
    print("Small")
elif x < 100:
    print("Medium")
else:
    print("Large")
```

### Question 8

```python
temperature = 35

if temperature >= 35:
    print("Hot")
elif temperature >= 25:
    print("Warm")
else:
    print("Cool")
```

### Question 9

```python
number = 15

if number % 3 == 0:
    print("Divisible by 3")
elif number % 5 == 0:
    print("Divisible by 5")
else:
    print("Neither")
```

### Question 10

```python
marks = 40

if marks > 40:
    print("Pass")
elif marks == 40:
    print("Boundary")
else:
    print("Fail")
```

## 5. Level 3: Logical Operators

### Question 11

```python
age = 25

if age >= 18 and age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

### Question 12

```python
age = 16

if age >= 18 or age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

### Question 13

```python
x = 10

if not x > 5:
    print("A")
else:
    print("B")
```

### Question 14

```python
a = True
b = False

if a and not b:
    print("Yes")
else:
    print("No")
```

### Question 15

```python
x = 5

if x > 0 and x < 10:
    print("Inside")
elif x == 5:
    print("Five")
else:
    print("Outside")
```

### Question 16

```python
x = 7

if x < 5 or x > 10:
    print("A")
elif x >= 5 and x <= 10:
    print("B")
else:
    print("C")
```

## 6. Level 4: Nested Conditions

### Question 17

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Access granted")
    else:
        print("ID required")
else:
    print("Too young")
```

### Question 18

```python
number = -4

if number >= 0:
    if number == 0:
        print("Zero")
    else:
        print("Positive")
else:
    print("Negative")
```

### Question 19

```python
marks = 75
attendance = 80

if marks >= 40:
    if attendance >= 75:
        print("Passed")
    else:
        print("Attendance shortage")
else:
    print("Failed")
```

### Question 20

```python
x = 10

if x > 5:
    print("A")

    if x > 15:
        print("B")
    else:
        print("C")
else:
    print("D")
```

## 7. Level 5: Independent if Statements

### Question 21

```python
x = 10

if x > 5:
    print("A")

if x > 8:
    print("B")

if x > 15:
    print("C")
```

### Question 22

```python
marks = 85

if marks >= 40:
    print("Pass")

if marks >= 80:
    print("Grade A")
else:
    print("Below A")
```

### Question 23

```python
x = 5

if x > 0:
    print("Positive")

if x % 2 == 0:
    print("Even")
else:
    print("Odd")
```

## 8. Level 6: Chained Comparisons and Precedence

### Question 24

```python
x = 7

print(5 < x < 10)
```

### Question 25

```python
x = 10

print(5 < x != 10)
```

### Question 26

```python
x = 8

if x > 5 and x < 10:
    print("A")
else:
    print("B")
```

### Question 27

```python
x = 5

if x == 5 or x == 10 and x > 0:
    print("Yes")
else:
    print("No")
```

### Question 28

```python
x = 5

if not x == 5:
    print("A")
else:
    print("B")
```

### Question 29

```python
x = 10

if x > 5 and x < 8 or x == 10:
    print("True")
else:
    print("False")
```

### Question 30

```python
x = 5

result = "A" if x > 10 else "B" if x > 3 else "C"
print(result)
```

## 9. Level 7: Truthiness and Logical Return Values

### Question 31

```python
if 0:
    print("A")
else:
    print("B")
```

### Question 32

```python
if []:
    print("A")
else:
    print("B")
```

### Question 33

```python
print(5 and 3)
```

### Question 34

```python
print(0 or 10)
```

### Question 35

```python
name = ""

if not name:
    print("Name is empty")
else:
    print("Name is available")
```

### Question 36

```python
x = None

if x is None:
    print("No value")
else:
    print("Has value")
```

## 10. Level 8: Membership and Identity

### Question 37

```python
name = "Python"

if "P" in name:
    print("Found")
else:
    print("Not found")
```

### Question 38

```python
numbers = [1, 2, 3]

if 4 not in numbers:
    print("Missing")
else:
    print("Present")
```

### Question 39

```python
student = {"name": "Masum", "age": 22}

if "name" in student:
    print("Key found")
else:
    print("Key missing")
```

### Question 40

```python
a = [1, 2]
b = a

if a is b:
    print("Same object")
else:
    print("Different objects")
```

## 11. Level 9: Find the Logical Error

প্রতিটি প্রশ্নে code-এর output predict করার পাশাপাশি problem থাকলে সেটিও চিহ্নিত করো।

### Question 41

```python
marks = 90

if marks >= 40:
    print("Pass")
elif marks >= 80:
    print("A")
```

### Question 42

```python
choice = "no"

if choice == "yes" or "y":
    print("Confirmed")
else:
    print("Cancelled")
```

### Question 43

```python
age = 15

if age >= 18 or age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

### Question 44

```python
number = 0

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
elif number > 0:
    print("Zero")
```

### Question 45

```python
x = 10

if x > 5:
    print("A")
elif x > 8:
    print("B")
elif x > 9:
    print("C")
```

## 12. Answer Key with Explanations

নিজে সব প্রশ্ন solve করার পর এই অংশের সঙ্গে মিলিয়ে নেবে।

| Question | Output | Explanation |
|---:|---|---|
| 1 | `A` | 10 > 5 True |
| 2 | `Fail` | 35 >= 40 False |
| 3 | `Zero` | দুই comparison-ই False |
| 4 | `Not adult` | 18 > 18 False |
| 5 | `Even` | 12 % 2 = 0 |
| 6 | `A` | 85 >= 80, কিন্তু 90-এর কম |
| 7 | `Medium` | 50 < 100 |
| 8 | `Hot` | 35 >= 35 |
| 9 | `Divisible by 3` | প্রথম condition True, তাই `elif` skip |
| 10 | `Boundary` | 40 > 40 False, 40 == 40 True |
| 11 | `Eligible` | দুই condition True |
| 12 | `Eligible` | `age <= 60` True, তাই `or` True |
| 13 | `B` | `x > 5` True; `not True` False |
| 14 | `Yes` | True and not False = True |
| 15 | `Inside` | প্রথম condition True |
| 16 | `B` | 7 প্রথম range-এর বাইরে, দ্বিতীয় range-এর মধ্যে |
| 17 | `Access granted` | বয়স ও ID দুইটিই গ্রহণযোগ্য |
| 18 | `Negative` | -4 >= 0 False |
| 19 | `Passed` | Marks ও attendance-এর শর্ত পূরণ |
| 20 | `A`, তারপর `C` | Outer ও inner condition অনুযায়ী |
| 21 | `A`, `B` | প্রথম দুইটি `if` True; তৃতীয়টি False |
| 22 | `Pass`, `Grade A` | দ্বিতীয় `if` True, তাই তার `else` skip |
| 23 | `Positive`, `Odd` | দুটি independent condition আলাদাভাবে পরীক্ষা হয় |
| 24 | `True` | 5 < 7 < 10 |
| 25 | `False` | 10 != 10 False |
| 26 | `A` | 8 > 5 এবং 8 < 10 |
| 27 | `Yes` | `and`-এর precedence `or`-এর চেয়ে বেশি; বাম পাশই True |
| 28 | `B` | `not (5 == 5)` False |
| 29 | `True` | প্রথম অংশ False, কিন্তু `x == 10` True |
| 30 | `B` | `x > 10` False; এরপর `x > 3` True |
| 31 | `B` | 0 falsy |
| 32 | `B` | Empty list falsy |
| 33 | `3` | `and` প্রথম falsy operand অথবা শেষ operand return করে |
| 34 | `10` | `or` প্রথম truthy operand return করে |
| 35 | `Name is empty` | Empty string falsy, তাই `not name` True |
| 36 | `No value` | `x is None` True |
| 37 | `Found` | `"P"` string-এর মধ্যে আছে |
| 38 | `Missing` | 4 list-এ নেই |
| 39 | `Key found` | Dictionary-তে `"name"` key আছে |
| 40 | `Same object` | `b = a` একই list object-কে refer করে |
| 41 | `Pass` | প্রথম condition True; `"A"` branch-এ পৌঁছায় না |
| 42 | `Confirmed` | `"y"` non-empty string, তাই expression truthy |
| 43 | `Eligible` | `age <= 60` True; logic উদ্দেশ্য অনুযায়ী ভুল |
| 44 | কোনো output নেই | Zero-এর জন্য condition নেই; শেষ condition-টিও `number > 0` |
| 45 | `A` | প্রথম condition True; পরের `elif`-গুলো skip |

## 13. Correcting the Logical Errors

### Question 41: Grade Condition Order

```python
marks = 90

if marks >= 80:
    print("A")
elif marks >= 40:
    print("Pass")
else:
    print("Fail")
```

এখানে বড় threshold আগে পরীক্ষা করা হয়েছে।

### Question 42: Correct `or` Condition

ভুল:

```python
if choice == "yes" or "y":
    print("Confirmed")
```

সঠিক:

```python
if choice == "yes" or choice == "y":
    print("Confirmed")
else:
    print("Cancelled")
```

অথবা:

```python
if choice in ("yes", "y"):
    print("Confirmed")
else:
    print("Cancelled")
```

### Question 43: Correct Range Condition

ভুল:

```python
if age >= 18 or age <= 60:
    print("Eligible")
```

সঠিক:

```python
if age >= 18 and age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

### Question 44: Correct Zero Condition

```python
number = 0

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

### Question 45: Correct Order

```python
x = 10

if x > 9:
    print("C")
elif x > 8:
    print("B")
elif x > 5:
    print("A")
```

এখানে সবচেয়ে বড় threshold আগে রাখা হয়েছে। `x = 10` হলে output হবে `C`।

## 14. Exam Strategy for Output Prediction

Exam-এ conditional code-এর output predict করার সময়:

1. Variable-এর initial value লিখে নাও।
2. প্রথম condition True নাকি False তা নির্ধারণ করো।
3. `if-elif-else` হলে প্রথম True branch খুঁজে বের করো।
4. Nested condition হলে indentation অনুসরণ করো।
5. Independent `if` থাকলে প্রতিটি condition আলাদাভাবে পরীক্ষা করো।
6. `and`, `or`, `not`-এর precedence মনে রাখো।
7. Boundary value এবং membership/identity condition সতর্কভাবে পরীক্ষা করো।
8. শেষ পর্যন্ত যে statement-গুলো execute হয়, সেগুলোর output সঠিক ক্রমে লেখো।

## 15. Quick Revision Checklist

- [ ] `if-else` output predict করতে পারি।
- [ ] `if-elif-else`-এর first-True rule বুঝি।
- [ ] Independent `if` ও `if-elif`-এর পার্থক্য বুঝি।
- [ ] Nested conditions trace করতে পারি।
- [ ] `and`, `or`, `not` সঠিকভাবে evaluate করতে পারি।
- [ ] Chained comparisons ও operator precedence বুঝি।
- [ ] Truthy ও falsy values শনাক্ত করতে পারি।
- [ ] `in`, `not in`, `is` ও `is not`-এর ব্যবহার বুঝি।
- [ ] Logical errors শনাক্ত ও সংশোধন করতে পারি।

**পরবর্তী টপিক:** `31_Conditional_Programming_Exercises.md`