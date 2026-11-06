# 05. The `if` Statement

## 1. Introduction

Python-এ `if` statement ব্যবহার করে কোনো condition সত্য হলে নির্দিষ্ট code execute করানো হয়।

সহজভাবে, **কোনো শর্ত পূরণ হলে কাজ করানোর জন্য `if` statement ব্যবহার করা হয়।**

বাস্তব উদাহরণ:

- Marks 40 বা তার বেশি হলে `Pass` দেখানো।
- বয়স 18 বা তার বেশি হলে eligibility দেখানো।
- Number positive হলে message দেখানো।
- Password সঠিক হলে login success দেখানো।

Example:

```python
age = 20

if age >= 18:
    print("You are an adult.")
```

Output:

```text
You are an adult.
```

এখানে `age >= 18` সত্য হওয়ায় `print()` execute হয়েছে।

## 2. Syntax of the `if` Statement

Python-এ `if` statement-এর সাধারণ syntax:

```python
if condition:
    statement
```

এখানে:

- `if` হলো Python keyword।
- `condition` হলো যে expression পরীক্ষা করা হবে।
- `:` condition-এর শেষ নির্দেশ করে।
- Indented statement হলো condition সত্য হলে যে code execute হবে।

Example:

```python
number = 10

if number > 0:
    print("Positive number")
```

Output:

```text
Positive number
```

যেহেতু `10 > 0` সত্য, তাই message print হয়েছে।

## 3. How Does the `if` Statement Work?

`if` statement সাধারণত নিচের ধাপে কাজ করে:

1. Python `if` keyword পায়।
2. Condition evaluate করে।
3. Condition সত্য হলে indented block execute করে।
4. Condition মিথ্যা হলে block skip করে।
5. এরপর program-এর পরবর্তী statement execute করে।

### Flowchart

```text
       Start
         |
         v
  Check condition
         |
         v
   Is it True?
     /     \
   Yes      No
    |        |
    v        |
Execute      |
if block     |
    |        |
    +----+---+
         |
         v
  Next statement
```

মনে রাখবে, `if` statement-এ condition মিথ্যা হলে তার block execute হয় না। `if` নিজে থেকে অন্য কোনো alternative block চালায় না।

## 4. When the Condition Is True

Condition সত্য হলে `if` block-এর code execute হয়।

Example:

```python
marks = 75

if marks >= 40:
    print("Congratulations!")
    print("You passed the exam.")

print("Result checked.")
```

Output:

```text
Congratulations!
You passed the exam.
Result checked.
```

ব্যাখ্যা:

- `marks >= 40` সত্য।
- তাই `if` block-এর দুটি `print()` execute হয়েছে।
- শেষের `print()` block-এর বাইরে থাকায় সেটিও execute হয়েছে।

## 5. When the Condition Is False

Condition মিথ্যা হলে `if` block skip হয়।

Example:

```python
marks = 25

if marks >= 40:
    print("You passed the exam.")

print("Result checked.")
```

Output:

```text
Result checked.
```

ব্যাখ্যা:

- `25 >= 40` মিথ্যা।
- তাই `print("You passed the exam.")` execute হয়নি।
- `if` block-এর বাইরের statement execute হয়েছে।

**Important:** Condition মিথ্যা হলেও program error ছাড়াই চলতে পারে। শুধু `if` block-এর code skip হয়।

## 6. Understanding Indentation

Python-এ indentation হলো line-এর শুরুতে whitespace দেওয়া। এটি code block নির্ধারণ করে।

`if` statement-এর মধ্যে থাকা code সাধারণত চারটি space দিয়ে indent করা হয়।

Correct example:

```python
age = 20

if age >= 18:
    print("Eligible")
    print("Age requirement satisfied.")

print("Program finished.")
```

Output:

```text
Eligible
Age requirement satisfied.
Program finished.
```

এখানে প্রথম দুটি `print()` `if` block-এর মধ্যে। শেষেরটি block-এর বাইরে।

### Incorrect Indentation

```python
age = 20

if age >= 18:
print("Eligible")
```

এটি `IndentationError` তৈরি করবে, কারণ `if`-এর পরের statement indent করা হয়নি।

Correct version:

```python
age = 20

if age >= 18:
    print("Eligible")
```

### Indentation Changes the Program's Meaning

```python
number = 10

if number > 0:
    print("Positive")
    print("Inside the if block")

print("Outside the if block")
```

Output:

```text
Positive
Inside the if block
Outside the if block
```

এখানে indentation অনুযায়ী প্রথম দুটি statement `if` block-এর মধ্যে এবং শেষ statement block-এর বাইরে।

## 7. The Importance of the Colon (`:`)

Python-এ `if` condition-এর শেষে colon দিতে হয়।

Correct:

```python
number = 5

if number > 0:
    print("Positive")
```

Incorrect:

```python
number = 5

if number > 0
    print("Positive")
```

দ্বিতীয় code-এ colon না থাকায় `SyntaxError` হবে।

**Rule:** `if` condition লেখার পর `:` দিতে হবে।

## 8. Using Comparison Operators with `if`

Comparison operators ব্যবহার করে condition তৈরি করা যায়।

| Operator | Example | Meaning |
|---|---|---|
| `==` | `age == 18` | বয়স ঠিক 18 কি না |
| `!=` | `number != 0` | Number শূন্য নয় কি না |
| `>` | `marks > 40` | Marks 40-এর বেশি কি না |
| `<` | `price < 100` | Price 100-এর কম কি না |
| `>=` | `marks >= 40` | Marks অন্তত 40 কি না |
| `<=` | `age <= 60` | বয়স সর্বোচ্চ 60 কি না |

Example:

```python
marks = 85

if marks >= 40:
    print("Pass")
```

Output:

```text
Pass
```

## 9. Using Variables as Conditions

Boolean variable-কে সরাসরি `if` condition হিসেবে ব্যবহার করা যায়।

Example:

```python
is_logged_in = True

if is_logged_in:
    print("Welcome back!")
```

Output:

```text
Welcome back!
```

এখানে `is_logged_in`-এর value `True`, তাই block execute হয়েছে।

যদি value `False` হয়:

```python
is_logged_in = False

if is_logged_in:
    print("Welcome back!")
```

Output:

```text
```

কোনো output আসবে না, কারণ condition মিথ্যা।

### Best Practice

Boolean variable-এর ক্ষেত্রে নিচের পদ্ধতি সাধারণত পরিষ্কার:

```python
if is_logged_in:
    print("Welcome back!")
```

সাধারণত `if is_logged_in == True:` লেখার প্রয়োজন নেই।

## 10. Using Logical Operators with `if`

একাধিক condition একসঙ্গে যাচাই করতে `and`, `or` এবং `not` ব্যবহার করা যায়।

### 10.1 Using `and`

`and`-এর ক্ষেত্রে সব condition সত্য হতে হবে।

```python
age = 22
has_id = True

if age >= 18 and has_id:
    print("Entry allowed")
```

Output:

```text
Entry allowed
```

### 10.2 Using `or`

`or`-এর ক্ষেত্রে অন্তত একটি condition সত্য হলেই expression truthy হয়।

```python
has_ticket = False
has_pass = True

if has_ticket or has_pass:
    print("Entry allowed")
```

Output:

```text
Entry allowed
```

### 10.3 Using `not`

`not` condition-এর truth value উল্টে দেয়।

```python
is_blocked = False

if not is_blocked:
    print("Access allowed")
```

Output:

```text
Access allowed
```

## 11. Using Arithmetic Expressions in `if`

Arithmetic calculation-এর result ব্যবহার করেও condition তৈরি করা যায়।

Example:

```python
a = 10
b = 5

if a + b > 12:
    print("The sum is greater than 12.")
```

Output:

```text
The sum is greater than 12.
```

এখানে Python প্রথমে `a + b` হিসাব করে। Result 15, যা 12-এর চেয়ে বড়। তাই condition সত্য।

### Another Example

```python
price = 500
quantity = 3

if price * quantity >= 1000:
    print("Bulk purchase")
```

Output:

```text
Bulk purchase
```

এখানে মোট মূল্য `500 * 3 = 1500`, যা 1000-এর বেশি।

## 12. Taking User Input with `if`

User-এর কাছ থেকে input নিয়ে condition পরীক্ষা করা যায়।

Example:

```python
age = int(input("Enter your age: "))

if age >= 18:
    print("You are eligible.")
```

Sample Input:

```text
Enter your age: 21
```

Output:

```text
You are eligible.
```

যদি input 15 হয়, তাহলে কোনো output আসবে না, কারণ condition মিথ্যা।

### Input Validation Note

এখানে `int()` ব্যবহার করা হয়েছে। User যদি `abc`-এর মতো non-numeric text দেয়, তাহলে `ValueError` হবে। পরে input validation-এর topic-এ এই ধরনের error handle করা শিখব।

## 13. Practical Example 1: Checking a Positive Number

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive number")
```

Sample Input:

```text
Enter a number: 12
```

Output:

```text
Positive number
```

Input `-5` বা `0` হলে কোনো output আসবে না। কারণ condition শুধু positive number-এর জন্য সত্য।

## 14. Practical Example 2: Checking Even Number

একটি number even কি না, তা `if` দিয়ে পরীক্ষা করা যায়।

```python
number = int(input("Enter a number: "))

if number % 2 == 0:
    print("Even number")
```

Sample Input:

```text
Enter a number: 8
```

Output:

```text
Even number
```

এখানে `number % 2` remainder বের করে। Remainder শূন্য হলে number even।

Odd number-এর জন্য এই `if` block execute হবে না।

## 15. Practical Example 3: Checking Passing Marks

```python
marks = float(input("Enter your marks: "))

if marks >= 40:
    print("Pass")
```

Sample Input:

```text
Enter your marks: 65
```

Output:

```text
Pass
```

এখানে marks 40 বা তার বেশি হলে `Pass` দেখাবে।

যদি marks 40-এর কম হয়, কোনো output আসবে না। Pass এবং Fail—দুটিই দেখানোর প্রয়োজন হলে `if-else` ব্যবহার করতে হবে।

## 16. Practical Example 4: Checking a Discount

ধরো, 2,000 টাকা বা তার বেশি কেনাকাটা করলে discount পাওয়া যাবে।

```python
total = float(input("Enter purchase amount: "))

if total >= 2000:
    print("You are eligible for a discount.")
```

Sample Input:

```text
Enter purchase amount: 2500
```

Output:

```text
You are eligible for a discount.
```

এখানে শুধু discount eligibility যাচাই করা হচ্ছে। Amount 2,000-এর কম হলে block execute হবে না।

## 17. Practical Example 5: Checking Password

```python
password = input("Enter password: ")

if password == "python123":
    print("Login successful.")
```

Sample Input:

```text
Enter password: python123
```

Output:

```text
Login successful.
```

Password ভুল হলে কোনো output আসবে না।

এটি শেখার জন্য basic example। বাস্তব login system-এ password handling ও authentication-এর জন্য নিরাপদ পদ্ধতি প্রয়োজন।

## 18. Multiple Independent `if` Statements

একটি program-এ একাধিক independent `if` statement থাকতে পারে।

Example:

```python
number = 12

if number > 0:
    print("Positive")

if number % 2 == 0:
    print("Even")

if number > 10:
    print("Greater than 10")
```

Output:

```text
Positive
Even
Greater than 10
```

এখানে তিনটি condition আলাদাভাবে পরীক্ষা করা হয়েছে। সবগুলো সত্য হওয়ায় তিনটি block-ই execute হয়েছে।

**Important:** একাধিক independent `if` statement ব্যবহার করলে প্রতিটি condition আলাদাভাবে পরীক্ষা করা হয়। একটির সত্য হওয়া অন্য condition-গুলো পরীক্ষা করা বন্ধ করে না।

## 19. Code Outside the `if` Block

`if` block-এর বাইরে থাকা statement condition সত্য বা মিথ্যা—দুই ক্ষেত্রেই execute হয়, যদি program স্বাভাবিকভাবে সেখানে পৌঁছায়।

Example:

```python
number = -5

if number > 0:
    print("Positive")

print("Checking completed.")
```

Output:

```text
Checking completed.
```

এখানে `number > 0` মিথ্যা, তাই `Positive` print হয়নি। কিন্তু `Checking completed.` block-এর বাইরে থাকায় print হয়েছে।

## 20. Common Mistakes

### Mistake 1: Forgetting the Colon

Incorrect:

```python
if age >= 18
    print("Eligible")
```

Correct:

```python
if age >= 18:
    print("Eligible")
```

### Mistake 2: Forgetting Indentation

Incorrect:

```python
if number > 0:
print("Positive")
```

Correct:

```python
if number > 0:
    print("Positive")
```

### Mistake 3: Using Assignment Instead of Comparison

Incorrect:

```python
if age = 18:
    print("Age is 18")
```

Correct:

```python
if age == 18:
    print("Age is 18")
```

### Mistake 4: Expecting Output When the Condition Is False

```python
marks = 30

if marks >= 40:
    print("Pass")
```

এখানে কোনো output আসবে না। কারণ `30 >= 40` মিথ্যা।

যদি false case-এর জন্যও message প্রয়োজন হয়, তাহলে `if-else` ব্যবহার করতে হবে।

### Mistake 5: Incorrect Indentation Level

```python
if age >= 18:
    print("Eligible")
        print("Welcome")
```

এখানে দ্বিতীয় `print()` অপ্রয়োজনীয়ভাবে অতিরিক্ত indent করা হয়েছে, তাই `IndentationError` হতে পারে।

Correct:

```python
if age >= 18:
    print("Eligible")
    print("Welcome")
```

## 21. Practice Exercises

নিজে code লিখে practice করো।

### Exercise 1: Positive Number

একটি integer input নাও। Number positive হলে `Positive` print করো।

### Exercise 2: Even Number

একটি integer input নিয়ে even হলে `Even` print করো।

### Exercise 3: Passing Marks

একটি marks input নাও। Marks 40 বা তার বেশি হলে `Pass` print করো।

### Exercise 4: Minimum Age

একটি age input নাও। বয়স 18 বা তার বেশি হলে `Eligible` print করো।

### Exercise 5: Discount Eligibility

Purchase amount 1,000 বা তার বেশি হলে `Discount available` print করো।

### Exercise 6: Password Check

User-এর input `"python123"`-এর সমান হলে `Login successful` print করো।

### Exercise 7: Multiple Conditions

`number = 20` নিয়ে আলাদা `if` statement ব্যবহার করে নিচের message-গুলো print করো:

- Positive
- Even
- Greater than 10

### Exercise 8: Output Prediction

নিচের code-এর output predict করো:

```python
x = 5

if x > 10:
    print("A")

print("B")

if x < 10:
    print("C")
```

## 22. Practice Answer Key

### Answer 1

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive")
```

### Answer 2

```python
number = int(input("Enter a number: "))

if number % 2 == 0:
    print("Even")
```

### Answer 3

```python
marks = float(input("Enter marks: "))

if marks >= 40:
    print("Pass")
```

### Answer 4

```python
age = int(input("Enter age: "))

if age >= 18:
    print("Eligible")
```

### Answer 5

```python
amount = float(input("Enter purchase amount: "))

if amount >= 1000:
    print("Discount available")
```

### Answer 6

```python
password = input("Enter password: ")

if password == "python123":
    print("Login successful")
```

### Answer 7

```python
number = 20

if number > 0:
    print("Positive")

if number % 2 == 0:
    print("Even")

if number > 10:
    print("Greater than 10")
```

Output:

```text
Positive
Even
Greater than 10
```

### Answer 8

Output:

```text
B
C
```

ব্যাখ্যা:

- `x > 10` মিথ্যা, তাই `A` print হয় না।
- `print("B")` block-এর বাইরে, তাই execute হয়।
- `x < 10` সত্য, তাই `C` print হয়।

## 23. Chapter Summary

- `if` statement condition সত্য হলে নির্দিষ্ট code execute করে।
- Syntax: `if condition:`
- Condition-এর শেষে colon দিতে হয়।
- `if` block-এর code indent করতে হয়।
- Condition মিথ্যা হলে block skip হয়।
- Comparison ও logical operators দিয়ে condition তৈরি করা যায়।
- Boolean variable সরাসরি condition হিসেবে ব্যবহার করা যায়।
- একাধিক independent `if` statement আলাদাভাবে কাজ করে।
- `if` block-এর বাইরের statement সাধারণত condition-এর ফলাফল নির্বিশেষে execute হয়।
- False condition-এর জন্য alternative action প্রয়োজন হলে `if-else` ব্যবহার করা যায়।

## 24. Self-Assessment Checklist

- [ ] `if` statement-এর syntax লিখতে পারি।
- [ ] Condition সত্য হলে code কীভাবে execute হয়, তা বুঝি।
- [ ] Condition মিথ্যা হলে কী ঘটে, তা ব্যাখ্যা করতে পারি।
- [ ] Indentation ও colon সঠিকভাবে ব্যবহার করতে পারি।
- [ ] Comparison ও logical operators ব্যবহার করে condition লিখতে পারি।
- [ ] User input নিয়ে `if` statement ব্যবহার করতে পারি।
- [ ] একাধিক independent `if` statement লিখতে পারি।
- [ ] Output prediction ও common errors solve করতে পারি।

## 25. Next Topic

পরবর্তী file:

`06_Indentation_and_Code_Blocks_in_Conditions.md`

সেখানে Python indentation কীভাবে code block নির্ধারণ করে, nested block-এর indentation, common indentation errors এবং clean code লেখার নিয়ম বিস্তারিতভাবে শেখা হবে।