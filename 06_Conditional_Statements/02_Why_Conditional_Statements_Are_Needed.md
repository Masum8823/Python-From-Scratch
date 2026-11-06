# 02. Why Conditional Statements Are Needed

## 1. Introduction

Programming-এ শুধু instruction একের পর এক execute করলেই সব সমস্যার সমাধান হয় না। অনেক সময় input বা পরিস্থিতি অনুযায়ী program-কে আলাদা সিদ্ধান্ত নিতে হয়।

এই সিদ্ধান্ত নেওয়ার জন্য **Conditional Statements** ব্যবহার করা হয়।

উদাহরণ:

- Marks অনুযায়ী Pass বা Fail নির্ধারণ করা।
- বয়স অনুযায়ী eligibility পরীক্ষা করা।
- সঠিক password দিলে login করা।
- Balance পর্যাপ্ত হলে টাকা উত্তোলন করা।
- Number positive, negative নাকি zero তা নির্ধারণ করা।

এসব ক্ষেত্রে condition অনুযায়ী program-এর behavior পরিবর্তিত হয়।

## 2. What Happens Without Conditional Statements?

ধরো, একটি program student-এর marks নিয়ে result দেখাবে।

### Without a Condition

```python
marks = 25

print("Pass")
```

Output:

```text
Pass
```

এখানে marks 25 হলেও program `Pass` দেখাচ্ছে। কারণ program-এ কোনো decision-making logic নেই।

Marks 80 দিলেও একই output আসবে:

```text
Pass
```

অর্থাৎ program input অনুযায়ী সিদ্ধান্ত নিচ্ছে না।

### With a Condition

```python
marks = 25

if marks >= 40:
    print("Pass")
```

Output:

```text
```

এবার program condition পরীক্ষা করে। যেহেতু `25 >= 40` মিথ্যা, তাই `print()` execute হয় না।

Marks 80 হলে:

```python
marks = 80

if marks >= 40:
    print("Pass")
```

Output:

```text
Pass
```

**মূল ধারণা:** Conditional statements program-কে input ও পরিস্থিতি অনুযায়ী কাজ করার সুযোগ দেয়।

## 3. Conditional Statements and Decision Making

বাস্তব জীবনে আমরা প্রতিদিন condition অনুযায়ী সিদ্ধান্ত নিই।

উদাহরণ:

- বৃষ্টি হলে ছাতা নিয়ে বের হব।
- পরীক্ষায় নির্দিষ্ট নম্বর পেলে পাস করব।
- টাকা যথেষ্ট থাকলে পণ্য কিনব।

Programming-এও একই ধারণা ব্যবহার করা হয়।

### Real-Life Logic

```text
Check the condition
        |
        v
Is the condition True?
      /     \
    Yes      No
     |        |
  Do task   Skip task
```

এটি একটি সাধারণ `if` statement-এর logic। `if`-এর condition সত্য হলে তার block execute হয়; মিথ্যা হলে block skip হয়।

## 4. Use Case 1: Pass or Fail

একজন student-এর marks অনুযায়ী result নির্ধারণ করা।

```python
marks = int(input("Enter your marks: "))

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

Sample Input:

```text
Enter your marks: 65
```

Output:

```text
Pass
```

আরেকটি input:

```text
Enter your marks: 25
```

Output:

```text
Fail
```

এখানে `if` ও `else` দুটি আলাদা পরিস্থিতি handle করছে।

**কেন প্রয়োজন?** Condition ছাড়া program বুঝতে পারত না কখন `Pass` এবং কখন `Fail` দেখাতে হবে।

## 5. Use Case 2: Age Eligibility

ধরো, একটি event-এ অংশ নিতে বয়স কমপক্ষে 18 হতে হবে।

```python
age = int(input("Enter your age: "))

if age >= 18:
    print("You are eligible.")
else:
    print("You are not eligible.")
```

Input:

```text
Enter your age: 20
```

Output:

```text
You are eligible.
```

এখানে `age >= 18` condition eligibility যাচাই করছে।

বাস্তব application-এ বয়স ছাড়াও অন্য নিয়ম থাকতে পারে। এখানে শুধু উদাহরণ হিসেবে বয়সের শর্ত ব্যবহার করা হয়েছে।

## 6. Use Case 3: Positive, Negative or Zero

একটি number positive, negative নাকি zero—তা নির্ধারণ করতে একাধিক condition দরকার।

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

Input:

```text
Enter a number: -7
```

Output:

```text
Negative
```

এখানে:

- `number > 0` হলে Positive।
- প্রথম condition মিথ্যা এবং `number < 0` সত্য হলে Negative।
- দুটি condition-ই মিথ্যা হলে Zero।

এই উদাহরণে `if`, `elif` ও `else` একসঙ্গে ব্যবহার করা হয়েছে।

## 7. Use Case 4: Login System

একটি basic login program-এ user-এর দেওয়া password সঠিক কি না যাচাই করা যায়।

```python
correct_password = "python123"
password = input("Enter password: ")

if password == correct_password:
    print("Login successful.")
else:
    print("Incorrect password.")
```

Input:

```text
Enter password: python123
```

Output:

```text
Login successful.
```

অন্য password দিলে:

```text
Incorrect password.
```

এখানে `==` operator দুটি string-এর value সমান কি না পরীক্ষা করছে।

**Important:** এটি শুধু শেখার জন্য তৈরি একটি basic example। বাস্তব login system-এ password নিরাপদভাবে সংরক্ষণ ও যাচাই করার জন্য আরও শক্তিশালী security ব্যবস্থা প্রয়োজন।

## 8. Use Case 5: ATM Withdrawal

ধরো, কোনো account-এ 5,000 টাকা আছে। User টাকা তুলতে চাইলে balance যথেষ্ট কি না পরীক্ষা করতে হবে।

```python
balance = 5000
withdraw = float(input("Enter withdrawal amount: "))

if withdraw > 0 and withdraw <= balance:
    balance = balance - withdraw
    print(f"Withdrawal successful. Balance: Tk {balance:.2f}")
else:
    print("Invalid amount or insufficient balance.")
```

Input:

```text
Enter withdrawal amount: 1500
```

Output:

```text
Withdrawal successful. Balance: Tk 3500.00
```

এখানে দুটি condition যাচাই করা হচ্ছে:

- `withdraw > 0`: টাকার পরিমাণ positive হতে হবে।
- `withdraw <= balance`: তোলার পরিমাণ available balance-এর বেশি হতে পারবে না।

`and` operator নিশ্চিত করছে যে দুটি condition-ই সত্য হতে হবে।

## 9. Use Case 6: Discount Eligibility

ধরো, 2,000 টাকা বা তার বেশি কেনাকাটা করলে 10% discount পাওয়া যাবে।

```python
total = float(input("Enter purchase amount: "))

if total >= 2000:
    discount = total * 0.10
    final_price = total - discount

    print(f"Discount: Tk {discount:.2f}")
    print(f"Final Price: Tk {final_price:.2f}")
else:
    print("No discount available.")
    print(f"Final Price: Tk {total:.2f}")
```

Input:

```text
Enter purchase amount: 2500
```

Output:

```text
Discount: Tk 250.00
Final Price: Tk 2250.00
```

এখানে purchase amount-এর ওপর ভিত্তি করে program ভিন্ন calculation করছে।

## 10. Use Case 7: Number Divisibility

একটি number 5 দিয়ে নিঃশেষে বিভাজ্য কি না পরীক্ষা করা।

```python
number = int(input("Enter a number: "))

if number % 5 == 0:
    print("Divisible by 5")
else:
    print("Not divisible by 5")
```

Input:

```text
Enter a number: 25
```

Output:

```text
Divisible by 5
```

`number % 5` remainder বের করে। Remainder zero হলে number-টি 5 দিয়ে নিঃশেষে বিভাজ্য।

## 11. Benefits of Conditional Statements

Conditional statements ব্যবহারের প্রধান সুবিধাগুলো হলো:

| Benefit | Explanation |
|---|---|
| Decision making | Condition অনুযায়ী সিদ্ধান্ত নেওয়া যায়। |
| Flexible programs | বিভিন্ন input-এর জন্য আলাদা behavior তৈরি করা যায়। |
| Input checking | User-এর input বা value যাচাই করা যায়। |
| Error prevention | Division by zero-এর মতো কিছু error এড়ানো যায়। |
| Real-world solutions | Login, grading, billing ও eligibility system তৈরি করা যায়। |
| Better control | Program কোন code execute করবে তা নিয়ন্ত্রণ করা যায়। |

তবে conditional statements নিজে থেকেই সব error প্রতিরোধ করে না। সঠিক condition, type checking এবং প্রয়োজনীয় validation-ও গুরুত্বপূর্ণ।

## 12. Common Mistakes

### Mistake 1: Always Printing the Same Result

```python
marks = 20
print("Pass")
```

এখানে marks যাচাই করা হয়নি।

Correct approach:

```python
marks = 20

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

### Mistake 2: Using the Wrong Comparison Operator

```python
marks = 40

if marks > 40:
    print("Pass")
```

যদি 40-ও pass mark হয়, তাহলে `>` ব্যবহার করা ভুল। কারণ `40 > 40` মিথ্যা।

Correct:

```python
if marks >= 40:
    print("Pass")
```

### Mistake 3: Ignoring Invalid Input

```python
age = int(input("Enter age: "))
```

User `abc` দিলে `ValueError` হবে। Numeric conversion-এর error handle করার জন্য প্রয়োজন অনুযায়ী `try-except` ব্যবহার করতে হবে।

### Mistake 4: Forgetting the Alternative Case

কোনো condition মিথ্যা হলে program-কে কী করতে হবে, সেটিও অনেক সময় নির্ধারণ করা দরকার।

যেমন, pass-এর পাশাপাশি fail message দেখাতে `else` ব্যবহার করা যায়।

## 13. Practice Exercises

নিজে solve করার চেষ্টা করো।

### Exercise 1: Voting Eligibility

বয়স 18 বা তার বেশি হলে `Eligible to vote` print করো; অন্যথায় `Not eligible to vote` print করো।

### Exercise 2: Even or Odd

একটি integer input নিয়ে সেটি even নাকি odd, নির্ধারণ করো।

### Exercise 3: Largest Number

দুটি number input নিয়ে কোনটি বড় তা দেখাও। দুটি সমান হলে `Equal` দেখাও।

### Exercise 4: Temperature Check

Temperature 30 বা তার বেশি হলে `Hot` এবং অন্যথায় `Not hot` print করো।

### Exercise 5: Password Check

সঠিক password-এর সঙ্গে user-এর input তুলনা করে success বা failure message দেখাও।

### Exercise 6: ATM Withdrawal

Balance ও withdrawal amount input নিয়ে withdrawal valid কি না যাচাই করো। Withdrawal positive হতে হবে এবং balance-এর বেশি হওয়া যাবে না।

## 14. Practice Answer Key

### Answer 1

```python
age = int(input("Enter age: "))

if age >= 18:
    print("Eligible to vote")
else:
    print("Not eligible to vote")
```

### Answer 2

```python
number = int(input("Enter number: "))

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

### Answer 3

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

if a > b:
    print("First number is larger")
elif b > a:
    print("Second number is larger")
else:
    print("Equal")
```

### Answer 4

```python
temperature = float(input("Enter temperature: "))

if temperature >= 30:
    print("Hot")
else:
    print("Not hot")
```

### Answer 5

```python
correct_password = "python123"
password = input("Enter password: ")

if password == correct_password:
    print("Login successful")
else:
    print("Login failed")
```

### Answer 6

```python
balance = float(input("Enter balance: "))
withdraw = float(input("Enter withdrawal amount: "))

if withdraw > 0 and withdraw <= balance:
    print("Withdrawal allowed")
else:
    print("Invalid withdrawal")
```

## 15. Chapter Summary

- Conditional statements program-কে condition অনুযায়ী সিদ্ধান্ত নিতে সাহায্য করে।
- এগুলো ছাড়া program অনেক সময় input অনুযায়ী ভিন্ন কাজ করতে পারে না।
- `if`, `elif` ও `else` দিয়ে বিভিন্ন decision path তৈরি করা যায়।
- Comparison operators condition যাচাই করে।
- Logical operators দিয়ে একাধিক condition একত্র করা যায়।
- Conditional statements grading, login, billing, eligibility ও validation-এর মতো সমস্যায় ব্যবহৃত হয়।
- সঠিক condition নির্ধারণ করা গুরুত্বপূর্ণ; ভুল condition program-এর ভুল result দিতে পারে।

## 16. Self-Assessment Checklist

- [ ] Conditional statements কেন প্রয়োজন, তা ব্যাখ্যা করতে পারি।
- [ ] Condition ছাড়া ও condition-সহ program-এর পার্থক্য বুঝি।
- [ ] `if-else` ব্যবহার করে decision নিতে পারি।
- [ ] একাধিক condition ব্যবহার করে result নির্ধারণ করতে পারি।
- [ ] `and` ও comparison operators দিয়ে condition তৈরি করতে পারি।
- [ ] Real-world problem-এর জন্য basic conditional program লিখতে পারি।
- [ ] Conditional logic-এর সাধারণ ভুল শনাক্ত করতে পারি।

## 17. Next Topic

পরবর্তী file:

`03_Conditions_and_Boolean_Expressions.md`

সেখানে আমরা condition, Boolean expression, `True` ও `False`, এবং Python কীভাবে expression evaluate করে—এসব বিস্তারিতভাবে শিখব।