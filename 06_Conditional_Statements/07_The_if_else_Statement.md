# 07. The `if-else` Statement

## 1. Introduction

Python-এ `if-else` statement ব্যবহার করা হয় condition-এর ফলাফল অনুযায়ী দুটি বিকল্পের মধ্যে একটি বেছে নেওয়ার জন্য।

- Condition `True` হলে `if` block execute হয়।
- Condition `False` হলে `else` block execute হয়।

সহজভাবে, **শর্ত সত্য হলে একটি কাজ, আর শর্ত মিথ্যা হলে অন্য কাজ করার জন্য `if-else` ব্যবহার করা হয়।**

Example:

```python
marks = 35

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

Output:

```text
Fail
```

এখানে `marks >= 40` মিথ্যা, তাই `else` block execute হয়েছে।

## 2. Syntax of `if-else`

Python-এ `if-else` statement-এর syntax:

```python
if condition:
    statement_if_true
else:
    statement_if_false
```

এখানে:

- `if` condition পরীক্ষা করে।
- `:` block শুরু হওয়ার নির্দেশ দেয়।
- `statement_if_true` condition সত্য হলে execute হয়।
- `else` condition মিথ্যা হলে বিকল্প block নির্দেশ করে।
- `statement_if_false` condition মিথ্যা হলে execute হয়।

মনে রাখবে, `else`-এর পরে কোনো condition লেখা হয় না।

## 3. How Does `if-else` Work?

`if-else` statement সাধারণত এভাবে কাজ করে:

1. Python `if` condition evaluate করে।
2. Condition সত্য হলে `if` block execute করে।
3. Condition মিথ্যা হলে `else` block execute করে।
4. দুটি block-এর মধ্যে একটি execute হওয়ার পর program পরবর্তী statement-এ যায়।

### Flowchart

```text
          Start
            |
            v
     Check condition
            |
            v
       Is it True?
        /       \
      Yes        No
       |          |
       v          v
   Execute     Execute
   if block   else block
       |          |
       +----+-----+
            |
            v
      Next statement
```

**Important:** একই `if-else` structure-এ স্বাভাবিকভাবে `if` ও `else` block-এর দুটিই execute হয় না। Condition অনুযায়ী একটি block বেছে নেওয়া হয়।

## 4. Example When the Condition Is True

```python
age = 20

if age >= 18:
    print("You are eligible.")
else:
    print("You are not eligible.")
```

Output:

```text
You are eligible.
```

ব্যাখ্যা:

- `age`-এর value 20।
- `20 >= 18` সত্য।
- তাই `if` block execute হয়েছে।
- `else` block execute হয়নি।

## 5. Example When the Condition Is False

```python
age = 15

if age >= 18:
    print("You are eligible.")
else:
    print("You are not eligible.")
```

Output:

```text
You are not eligible.
```

ব্যাখ্যা:

- `age`-এর value 15।
- `15 >= 18` মিথ্যা।
- তাই `if` block skip হয়েছে।
- `else` block execute হয়েছে।

## 6. Difference Between `if` and `if-else`

| Feature | `if` | `if-else` |
|---|---|---|
| Purpose | Condition সত্য হলে কাজ করে | সত্য ও মিথ্যা—দুই অবস্থার জন্য কাজ নির্ধারণ করে |
| True condition | `if` block execute হয় | `if` block execute হয় |
| False condition | `if` block skip হয় | `else` block execute হয় |
| Alternative action | সরাসরি নির্ধারিত থাকে না | `else` দিয়ে নির্ধারণ করা যায় |

### Using Only `if`

```python
marks = 30

if marks >= 40:
    print("Pass")
```

Output:

```text
```

কোনো output আসবে না।

### Using `if-else`

```python
marks = 30

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

Output:

```text
Fail
```

এখানে দুই অবস্থার জন্যই result নির্ধারিত আছে।

## 7. Indentation in `if-else`

Python-এ indentation সঠিকভাবে ব্যবহার করতে হয়।

Correct:

```python
if condition:
    print("Condition is true")
else:
    print("Condition is false")
```

এখানে:

- `if` ও `else` একই indentation level-এ আছে।
- তাদের অধীনে থাকা statement চারটি space দিয়ে indent করা হয়েছে।

Incorrect:

```python
if condition:
    print("Condition is true")
    else:
        print("Condition is false")
```

এটি ভুল indentation structure এবং error তৈরি করবে।

**Rule:** `else`-কে তার matching `if`-এর সঙ্গে একই level-এ লিখবে।

## 8. Using Comparison Operators with `if-else`

Comparison operators দিয়ে condition তৈরি করা যায়।

### 8.1 Equal to (`==`)

```python
number = 10

if number == 10:
    print("Number is 10")
else:
    print("Number is not 10")
```

Output:

```text
Number is 10
```

### 8.2 Not Equal to (`!=`)

```python
number = 5

if number != 0:
    print("Number is not zero")
else:
    print("Number is zero")
```

Output:

```text
Number is not zero
```

### 8.3 Greater Than (`>`)

```python
a = 15
b = 10

if a > b:
    print("A is greater")
else:
    print("A is not greater")
```

Output:

```text
A is greater
```

### 8.4 Less Than or Equal to (`<=`)

```python
age = 60

if age <= 60:
    print("Within the age limit")
else:
    print("Age limit exceeded")
```

Output:

```text
Within the age limit
```

## 9. Using Logical Operators with `if-else`

একাধিক condition একসঙ্গে পরীক্ষা করতে `and`, `or` এবং `not` ব্যবহার করা যায়।

### 9.1 Using `and`

`and` expression সত্য হওয়ার জন্য সব condition সত্য হতে হবে।

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

যেকোনো একটি condition মিথ্যা হলে `else` block execute হবে।

### 9.2 Using `or`

`or` expression সত্য হওয়ার জন্য অন্তত একটি condition সত্য হলেই হয়।

```python
has_ticket = False
has_pass = True

if has_ticket or has_pass:
    print("Entry allowed")
else:
    print("Entry denied")
```

Output:

```text
Entry allowed
```

### 9.3 Using `not`

`not` একটি truth value উল্টে দেয়।

```python
is_blocked = False

if not is_blocked:
    print("Access allowed")
else:
    print("Access denied")
```

Output:

```text
Access allowed
```

## 10. Using `if-else` with User Input

User-এর input নিয়ে condition পরীক্ষা করা যায়।

Example:

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive number")
else:
    print("Zero or negative number")
```

Sample Input:

```text
Enter a number: -5
```

Output:

```text
Zero or negative number
```

এখানে number positive হলে প্রথম message এবং অন্যথায় দ্বিতীয় message দেখাবে।

**Note:** `int(input())`-এ non-numeric input দিলে `ValueError` হতে পারে। Input validation পরে বিস্তারিত শেখা হবে।

## 11. Practical Example 1: Pass or Fail

একজন student 40 বা তার বেশি marks পেলে pass করবে।

```python
marks = float(input("Enter your marks: "))

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

Sample Input:

```text
Enter your marks: 75
```

Output:

```text
Pass
```

যদি marks 35 হয়, output হবে `Fail`।

## 12. Practical Example 2: Even or Odd

কোনো integer even না odd, তা পরীক্ষা করা যায়।

```python
number = int(input("Enter an integer: "))

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

Sample Input:

```text
Enter an integer: 7
```

Output:

```text
Odd
```

ব্যাখ্যা:

- `%` operator remainder বের করে।
- Number-কে 2 দিয়ে ভাগ করলে remainder 0 হলে even।
- অন্যথায় odd।

এটি negative integer-এর ক্ষেত্রেও কাজ করে।

## 13. Practical Example 3: Positive or Non-Positive

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive")
else:
    print("Zero or negative")
```

Sample Input:

```text
Enter a number: 0
```

Output:

```text
Zero or negative
```

খেয়াল করো, এখানে `else` block শুধু negative number-এর জন্য নয়; zero-এর জন্যও execute হয়।

## 14. Practical Example 4: Larger of Two Numbers

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

if a > b:
    print("First number is larger")
else:
    print("First number is not larger")
```

Sample Input:

```text
Enter first number: 10
Enter second number: 20
```

Output:

```text
First number is not larger
```

এই program-এ `a` বড় না হলে `else` execute হয়। অর্থাৎ `a` ছোট হলেও, `a` ও `b` সমান হলেও একই message আসবে।

যদি তিনটি অবস্থার জন্য আলাদা result দরকার হয়—প্রথমটি বড়, দ্বিতীয়টি বড়, অথবা সমান—তাহলে `if-elif-else` ব্যবহার করা ভালো।

## 15. Practical Example 5: Discount Eligibility

ধরো, 2,000 টাকা বা তার বেশি কেনাকাটা করলে discount পাওয়া যাবে।

```python
amount = float(input("Enter purchase amount: "))

if amount >= 2000:
    print("Discount available")
else:
    print("No discount")
```

Sample Input:

```text
Enter purchase amount: 1500
```

Output:

```text
No discount
```

এখানে condition false হওয়ায় `else` block execute হয়েছে।

## 16. Practical Example 6: Password Check

```python
password = input("Enter password: ")

if password == "python123":
    print("Login successful")
else:
    print("Incorrect password")
```

Sample Input:

```text
Enter password: abc123
```

Output:

```text
Incorrect password
```

এটি conditional statement শেখার একটি basic example। বাস্তব application-এ নিরাপদ authentication ব্যবস্থা ব্যবহার করতে হয়।

## 17. Practical Example 7: Divisibility Check

কোনো number 5 দিয়ে বিভাজ্য কি না পরীক্ষা করা যাক।

```python
number = int(input("Enter an integer: "))

if number % 5 == 0:
    print("Divisible by 5")
else:
    print("Not divisible by 5")
```

Sample Input:

```text
Enter an integer: 25
```

Output:

```text
Divisible by 5
```

Remainder 0 হলে number-টি 5 দিয়ে বিভাজ্য।

## 18. Practical Example 8: Minimum Balance Check

```python
balance = 500
withdrawal = 700

if withdrawal <= balance:
    print("Withdrawal allowed")
else:
    print("Insufficient balance")
```

Output:

```text
Insufficient balance
```

এখানে withdrawal amount balance-এর চেয়ে বেশি। তাই `withdrawal <= balance` মিথ্যা হয়েছে।

এটি একটি basic learning example; বাস্তব financial system-এ আরও validation ও নিরাপত্তা প্রয়োজন।

## 19. Nested `if-else`

একটি `if` বা `else` block-এর মধ্যে আরেকটি `if-else` statement লেখা যায়। একে nested `if-else` বলে।

Example:

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Entry allowed")
    else:
        print("ID required")
else:
    print("Age requirement not met")
```

Output:

```text
Entry allowed
```

ব্যাখ্যা:

1. প্রথমে age পরীক্ষা করা হয়।
2. বয়স 18 বা তার বেশি হলে `has_id` পরীক্ষা করা হয়।
3. ID থাকলে `Entry allowed` দেখায়।
4. ID না থাকলে `ID required` দেখায়।
5. বয়স 18-এর কম হলে বাইরের `else` execute হয়।

Nested conditions-এর indentation ঠিক রাখা খুব গুরুত্বপূর্ণ।

## 20. Common Mistakes

### Mistake 1: Forgetting the Colon

Incorrect:

```python
if age >= 18
    print("Eligible")
else:
    print("Not eligible")
```

Correct:

```python
if age >= 18:
    print("Eligible")
else:
    print("Not eligible")
```

### Mistake 2: Wrong Indentation

Incorrect:

```python
if marks >= 40:
    print("Pass")
    else:
        print("Fail")
```

Correct:

```python
if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

### Mistake 3: Using `=` Instead of `==`

Incorrect:

```python
if number = 10:
    print("Ten")
else:
    print("Not ten")
```

Correct:

```python
if number == 10:
    print("Ten")
else:
    print("Not ten")
```

### Mistake 4: Writing a Condition After `else`

Incorrect:

```python
if marks >= 40:
    print("Pass")
else marks < 40:
    print("Fail")
```

এটি invalid syntax।

Correct:

```python
if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

`else` নিজে কোনো condition গ্রহণ করে না।

### Mistake 5: Forgetting Type Conversion

Incorrect:

```python
age = input("Enter age: ")

if age >= 18:
    print("Eligible")
else:
    print("Not eligible")
```

এখানে string ও integer-এর মধ্যে ordering comparison করার চেষ্টা হচ্ছে, তাই `TypeError` হবে।

Correct:

```python
age = int(input("Enter age: "))

if age >= 18:
    print("Eligible")
else:
    print("Not eligible")
```

### Mistake 6: Thinking Both Blocks Execute

```python
number = 5

if number > 0:
    print("Positive")
else:
    print("Not positive")
```

Output:

```text
Positive
```

একই `if-else` structure-এর উভয় block একসঙ্গে execute হয় না। Condition অনুযায়ী একটি block নির্বাচন করা হয়।

## 21. Practice Exercises

নিজে solve করার চেষ্টা করো।

### Exercise 1: Pass or Fail

একটি marks input নাও। Marks 40 বা তার বেশি হলে `Pass`, অন্যথায় `Fail` দেখাও।

### Exercise 2: Even or Odd

একটি integer input নিয়ে number even হলে `Even`, অন্যথায় `Odd` print করো।

### Exercise 3: Positive or Non-Positive

একটি number input নিয়ে positive হলে `Positive`, অন্যথায় `Zero or negative` দেখাও।

### Exercise 4: Larger Number

দুটি integer input নিয়ে প্রথমটি দ্বিতীয়টির চেয়ে বড় হলে `First is larger`, অন্যথায় `First is not larger` দেখাও।

### Exercise 5: Divisibility

একটি integer input নাও। Number 3 দিয়ে বিভাজ্য হলে `Divisible`, অন্যথায় `Not divisible` দেখাও।

### Exercise 6: Password Check

User-এর input `"admin123"`-এর সমান হলে `Access granted`, অন্যথায় `Access denied` দেখাও।

### Exercise 7: Minimum Purchase

Purchase amount 1,500 টাকা বা তার বেশি হলে `Offer available`, অন্যথায় `No offer` দেখাও।

### Exercise 8: Output Prediction

নিচের code-এর output predict করো:

```python
x = 10

if x < 5:
    print("A")
else:
    print("B")

print("C")
```

### Exercise 9: Nested Conditions

`age = 19` এবং `has_id = False` ধরে nested `if-else` লিখো:

- বয়স 18 বা তার বেশি এবং ID থাকলে `Allowed`।
- বয়স 18 বা তার বেশি কিন্তু ID না থাকলে `ID required`।
- বয়স 18-এর কম হলে `Not eligible`।

## 22. Practice Answer Key

### Answer 1

```python
marks = float(input("Enter marks: "))

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

### Answer 2

```python
number = int(input("Enter an integer: "))

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

### Answer 3

```python
number = float(input("Enter a number: "))

if number > 0:
    print("Positive")
else:
    print("Zero or negative")
```

### Answer 4

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

if a > b:
    print("First is larger")
else:
    print("First is not larger")
```

### Answer 5

```python
number = int(input("Enter an integer: "))

if number % 3 == 0:
    print("Divisible")
else:
    print("Not divisible")
```

### Answer 6

```python
password = input("Enter password: ")

if password == "admin123":
    print("Access granted")
else:
    print("Access denied")
```

### Answer 7

```python
amount = float(input("Enter purchase amount: "))

if amount >= 1500:
    print("Offer available")
else:
    print("No offer")
```

### Answer 8

Output:

```text
B
C
```

কারণ `10 < 5` মিথ্যা, তাই `else` block execute হয়। এরপর block-এর বাইরের `print("C")` execute হয়।

### Answer 9

```python
age = 19
has_id = False

if age >= 18:
    if has_id:
        print("Allowed")
    else:
        print("ID required")
else:
    print("Not eligible")
```

Output:

```text
ID required
```

## 23. Chapter Summary

- `if-else` condition-এর সত্য ও মিথ্যা—দুই অবস্থার জন্য আলাদা action নির্ধারণ করে।
- Condition সত্য হলে `if` block execute হয়।
- Condition মিথ্যা হলে `else` block execute হয়।
- `else`-এর পরে condition লেখা হয় না।
- `if` ও `else` একই indentation level-এ থাকে।
- Comparison ও logical operators দিয়ে condition তৈরি করা যায়।
- User input-এর ক্ষেত্রে প্রয়োজন অনুযায়ী type conversion করতে হয়।
- Nested `if-else` ব্যবহার করে একাধিক স্তরের decision নেওয়া যায়।
- সঠিক colon ও indentation বজায় রাখা জরুরি।

## 24. Self-Assessment Checklist

- [ ] `if-else` statement-এর syntax লিখতে পারি।
- [ ] Condition সত্য ও মিথ্যা হলে execution flow ব্যাখ্যা করতে পারি।
- [ ] `if` ও `if-else`-এর পার্থক্য বুঝি।
- [ ] `else` সঠিকভাবে ব্যবহার করতে পারি।
- [ ] Comparison ও logical operators দিয়ে decision নিতে পারি।
- [ ] User input নিয়ে `if-else` লিখতে পারি।
- [ ] Nested `if-else` বুঝি ও লিখতে পারি।
- [ ] Common syntax ও indentation errors ঠিক করতে পারি।

## 25. Next Topic

পরবর্তী file:

`08_The_elif_Statement.md`

সেখানে একাধিক condition পরীক্ষা করার জন্য `elif` ব্যবহার করা, `if-elif-else` structure এবং decision-making examples বিস্তারিতভাবে শেখা হবে।