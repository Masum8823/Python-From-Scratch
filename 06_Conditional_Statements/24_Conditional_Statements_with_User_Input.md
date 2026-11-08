# 24. Conditional Statements with User Input

## 1. Introduction

Python-এ `input()` function ব্যবহার করে user-এর কাছ থেকে data নেওয়া যায়। এরপর conditional statements (`if`, `if-else`, `if-elif-else`) ব্যবহার করে সেই data অনুযায়ী বিভিন্ন কাজ করা যায়।

এভাবে program শুধু নির্দিষ্ট value নিয়ে কাজ করে না; user যে value দেয়, তার ওপর ভিত্তি করে সিদ্ধান্তও নিতে পারে।

উদাহরণ:

```python
age = int(input("Enter your age: "))

if age >= 18:
    print("You are an adult.")
else:
    print("You are not an adult yet.")
```

Input:

```text
Enter your age: 20
```

Output:

```text
You are an adult.
```

এখানে:

1. `input()` user-এর কাছ থেকে age নেয়।
2. `int()` input-কে integer-এ convert করে।
3. `if` condition পরীক্ষা করে age 18 বা তার বেশি কি না।
4. Condition অনুযায়ী উপযুক্ত message print হয়।

## 2. Understanding the Program Flow

User input-এর সঙ্গে conditional statement ব্যবহার করলে সাধারণত program এই ধাপগুলো অনুসরণ করে:

1. User-এর কাছ থেকে input নেওয়া।
2. প্রয়োজন হলে input-এর type convert করা।
3. Input-এর ওপর condition পরীক্ষা করা।
4. Condition অনুযায়ী উপযুক্ত block execute করা।
5. Result দেখানো।

উদাহরণ:

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive number")
elif number < 0:
    print("Negative number")
else:
    print("Zero")
```

Input `-5` হলে output:

```text
Negative number
```

এখানে একই program positive, negative এবং zero—তিন ধরনের number handle করতে পারে।

## 3. Taking String Input

`input()` ব্যবহার করে নাম, city, choice বা অন্য কোনো text নেওয়া যায়।

মনে রাখবে, `input()` সাধারণত string return করে।

উদাহরণ:

```python
name = input("Enter your name: ")

if name:
    print("Welcome,", name)
else:
    print("Name cannot be empty.")
```

Input:

```text
Enter your name: Masum
```

Output:

```text
Welcome, Masum
```

এখানে `if name` পরীক্ষা করছে string-টি empty কি না।

- Non-empty string হলে condition True।
- Empty string `""` হলে condition False।

শুধু space দেওয়া input-ও non-empty string। Space-কে empty হিসেবে বিবেচনা করতে চাইলে `strip()` ব্যবহার করা যায়।

```python
name = input("Enter your name: ").strip()

if name:
    print("Welcome,", name)
else:
    print("Name cannot be empty.")
```

`strip()` string-এর শুরু ও শেষের whitespace সরিয়ে দেয়।

## 4. Taking Numeric Input

Number-এর ওপর comparison বা mathematical operation করতে হলে input-কে প্রয়োজনীয় numeric type-এ convert করতে হয়।

### Integer Input

```python
age = int(input("Enter your age: "))

if age >= 18:
    print("Eligible")
else:
    print("Not eligible")
```

### Float Input

```python
temperature = float(input("Enter temperature: "))

if temperature > 30:
    print("Hot weather")
else:
    print("Not too hot")
```

`int()` পূর্ণসংখ্যার input-এর জন্য এবং `float()` decimal number-এর input-এর জন্য ব্যবহার করা যায়।

**সতর্কতা:** User যদি `int()`-এর ক্ষেত্রে `abc` বা `float()`-এর ক্ষেত্রে অসংগত text দেয়, তাহলে conversion error হতে পারে। পরে আমরা input validation ও exception handling আরও বিস্তারিত শিখব।

## 5. Using if-else with User Input

দুটি সম্ভাব্য outcome থাকলে `if-else` ব্যবহার করা যায়।

### Example: Even or Odd

```python
number = int(input("Enter an integer: "))

if number % 2 == 0:
    print("Even number")
else:
    print("Odd number")
```

Input:

```text
Enter an integer: 8
```

Output:

```text
Even number
```

এখানে `%` operator remainder বের করে।

- `number % 2 == 0` হলে number even।
- অন্যথায় number odd।

### Example: Pass or Fail

```python
marks = float(input("Enter your marks: "))

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

Input:

```text
Enter your marks: 65
```

Output:

```text
Pass
```

এখানে 40-কে pass mark হিসেবে উদাহরণে ধরা হয়েছে। বাস্তবে তোমার institution-এর grading rules অনুসরণ করতে হবে।

## 6. Using if-elif-else with User Input

একাধিক category-এর মধ্যে একটি নির্বাচন করতে `if-elif-else` ব্যবহার করা হয়।

### Example: Grade Calculator

```python
marks = float(input("Enter your marks: "))

if marks < 0 or marks > 100:
    print("Invalid marks")
elif marks >= 80:
    print("Grade A")
elif marks >= 70:
    print("Grade B")
elif marks >= 60:
    print("Grade C")
elif marks >= 40:
    print("Grade D")
else:
    print("Grade F")
```

Input:

```text
Enter your marks: 75
```

Output:

```text
Grade B
```

এখানে প্রথমে marks valid কি না পরীক্ষা করা হয়েছে। এরপর উপযুক্ত grade নির্বাচন করা হয়েছে।

**গুরুত্বপূর্ণ:** বড় threshold আগে পরীক্ষা করতে হবে, কারণ `if-elif` chain-এ প্রথম True condition-এর block execute হয়।

## 7. Combining User Input with Logical Operators

একাধিক condition একসঙ্গে পরীক্ষা করতে `and`, `or` এবং `not` ব্যবহার করা যায়।

### Example 1: Age and Permission

```python
age = int(input("Enter your age: "))
has_permission = input("Do you have permission? (yes/no): ").strip().lower()

if age >= 18 and has_permission == "yes":
    print("Access granted")
else:
    print("Access denied")
```

এখানে দুইটি condition-ই True হতে হবে।

### Example 2: Accepted Choices

```python
choice = input("Enter yes or no: ").strip().lower()

if choice == "yes" or choice == "y":
    print("You selected Yes")
else:
    print("You did not select Yes")
```

এখানে user `yes` অথবা `y` লিখলে একই action execute হয়।

**Note:** দ্বিতীয় উদাহরণে অন্য সব input-কে `"You did not select Yes"` বলা হয়েছে। এটিকে আলাদা invalid input হিসেবে handle করতে চাইলে `elif` ও `else` দিয়ে আরও নির্দিষ্ট condition লিখতে হবে।

## 8. Nested Conditions with User Input

কখনো একটি condition পূরণ হওয়ার পর আরেকটি condition পরীক্ষা করতে হয়। তখন nested `if` ব্যবহার করা যায়।

উদাহরণ:

```python
username = input("Enter username: ").strip()
password = input("Enter password: ")

if username == "admin":
    if password == "1234":
        print("Login successful")
    else:
        print("Incorrect password")
else:
    print("Unknown username")
```

Sample input:

```text
Enter username: admin
Enter password: 1234
```

Output:

```text
Login successful
```

এখানে প্রথমে username পরীক্ষা করা হয়েছে। Username সঠিক হলেই password পরীক্ষা করা হয়েছে।

**Security note:** এটি শুধু conditional statement শেখার উদাহরণ। বাস্তব application-এ plain-text password এভাবে সংরক্ষণ করা নিরাপদ নয়।

## 9. Using match-case with User Input

User যদি নির্দিষ্ট menu option নির্বাচন করে, তাহলে `match-case` ব্যবহার করা যায়।

```python
choice = input("Choose an option (1-3): ")

match choice:
    case "1":
        print("You selected Add")
    case "2":
        print("You selected Subtract")
    case "3":
        print("You selected Multiply")
    case _:
        print("Invalid choice")
```

Input:

```text
Choose an option (1-3): 2
```

Output:

```text
You selected Subtract
```

এখানে input string হওয়ায় `"1"`, `"2"` ও `"3"` ব্যবহার করা হয়েছে।

## 10. Practical Program: Simple Login Check

এই উদাহরণে username ও password-এর ভিত্তিতে message দেখানো হবে।

```python
username = input("Enter username: ").strip()
password = input("Enter password: ")

if not username or not password:
    print("Username and password are required.")
elif username == "masum" and password == "python123":
    print("Login successful")
else:
    print("Invalid username or password")
```

Sample input:

```text
Enter username: masum
Enter password: python123
```

Output:

```text
Login successful
```

ব্যাখ্যা:

- `not username` — username empty কি না পরীক্ষা করে।
- `not password` — password empty কি না পরীক্ষা করে।
- `and` — username ও password দুটিই সঠিক কি না পরীক্ষা করে।
- `else` — বাকি ক্ষেত্রে error message দেখায়।

এটিও একটি learning example, production login system নয়।

## 11. Practical Program: Discount Calculator

ধরা যাক, কেনাকাটার amount অনুযায়ী discount নির্ধারণ করতে হবে।

- Amount 5000 বা তার বেশি হলে 10% discount।
- Amount 2000 বা তার বেশি হলে 5% discount।
- অন্যথায় discount নেই।

```python
amount = float(input("Enter purchase amount: "))

if amount < 0:
    print("Invalid amount")
elif amount >= 5000:
    discount = amount * 0.10
    print(f"Discount: {discount:.2f}")
elif amount >= 2000:
    discount = amount * 0.05
    print(f"Discount: {discount:.2f}")
else:
    print("No discount")
```

Input:

```text
Enter purchase amount: 6000
```

Output:

```text
Discount: 600.00
```

এখানে `discount` হলো discount-এর টাকার পরিমাণ, final payable amount নয়। বাস্তবে financial calculation-এর জন্য floating-point precision ও currency rounding-এর বিষয়ও বিবেচনা করতে হয়।

## 12. Common Mistakes

### Mistake 1: Input convert না করা

ভুল:

```python
age = input("Enter age: ")

if age >= 18:
    print("Adult")
```

এখানে `age` string, কিন্তু `18` integer। তাই comparison করলে `TypeError` হবে।

সঠিক:

```python
age = int(input("Enter age: "))

if age >= 18:
    print("Adult")
```

### Mistake 2: String-এর সঙ্গে ভুলভাবে comparison করা

```python
answer = input("Continue? ")

if answer == "yes":
    print("Continuing")
```

এখানে `YES` বা `Yes` লিখলে condition False হবে, কারণ string comparison case-sensitive।

Case-insensitive comparison চাইলে:

```python
answer = input("Continue? ").strip().lower()

if answer == "yes":
    print("Continuing")
```

### Mistake 3: `=` এবং `==` গুলিয়ে ফেলা

- `=` দিয়ে variable-এ value assign করা হয়।
- `==` দিয়ে দুইটি value সমান কি না পরীক্ষা করা হয়।

সঠিক:

```python
choice = input("Enter choice: ")

if choice == "yes":
    print("Confirmed")
```

### Mistake 4: Condition-এর order ভুল করা

Grade calculator-এর ক্ষেত্রে ছোট threshold আগে পরীক্ষা করলে বড় grade-এর condition-এ পৌঁছানো নাও যেতে পারে।

### Mistake 5: Invalid input বিবেচনা না করা

`int(input())` ব্যবহার করলে non-integer input-এ error হতে পারে। বাস্তব program-এ input validation বা `try-except` ব্যবহার করা উচিত।

## 13. Practice Exercises

### Question 1: Positive, Negative or Zero

User-এর কাছ থেকে একটি integer নাও এবং সেটি positive, negative নাকি zero, তা print করো।

### Question 2: Even or Odd

User-এর কাছ থেকে একটি integer নিয়ে even বা odd নির্ধারণ করো।

### Question 3: Pass or Fail

User-এর marks input নাও। Marks 40 বা তার বেশি হলে `Pass`, অন্যথায় `Fail` print করো।

### Question 4: Grade Calculator

Marks অনুযায়ী grade নির্ধারণ করো:

- 80–100: A
- 70–79: B
- 60–69: C
- 40–59: D
- 0–39: F
- 0-এর কম বা 100-এর বেশি: Invalid marks

### Question 5: Largest of Two Numbers

User-এর কাছ থেকে দুটি number নাও এবং কোনটি বড় তা print করো। দুইটি সমান হলে সেটিও দেখাও।

### Question 6: Password Check

User-এর কাছ থেকে password নাও। Password `"python123"` হলে `Access granted`, অন্যথায় `Access denied` print করো।

### Question 7: Menu Program

User-এর কাছ থেকে `1`, `2` অথবা `3` input নাও। `match-case` ব্যবহার করে যথাক্রমে `Add`, `Subtract` অথবা `Multiply` print করো। অন্য input হলে `Invalid choice` দেখাও।

### Question 8: Temperature Category

User-এর কাছ থেকে temperature নাও:

- 35-এর বেশি হলে `Very hot`
- 25-এর বেশি বা সমান হলে `Warm`
- অন্যথায় `Cool`

## 14. Answer Key

### Answer 1

```python
number = int(input("Enter an integer: "))

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
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
marks = float(input("Enter marks: "))

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

এটি basic example; এখানে valid marks range যাচাই করা হয়নি।

### Answer 4

```python
marks = float(input("Enter marks: "))

if marks < 0 or marks > 100:
    print("Invalid marks")
elif marks >= 80:
    print("A")
elif marks >= 70:
    print("B")
elif marks >= 60:
    print("C")
elif marks >= 40:
    print("D")
else:
    print("F")
```

### Answer 5

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

if a > b:
    print("First number is larger")
elif b > a:
    print("Second number is larger")
else:
    print("Both numbers are equal")
```

### Answer 6

```python
password = input("Enter password: ")

if password == "python123":
    print("Access granted")
else:
    print("Access denied")
```

এটি শুধু practice example; বাস্তব authentication system-এর জন্য উপযুক্ত নয়।

### Answer 7

```python
choice = input("Enter choice (1-3): ")

match choice:
    case "1":
        print("Add")
    case "2":
        print("Subtract")
    case "3":
        print("Multiply")
    case _:
        print("Invalid choice")
```

### Answer 8

```python
temperature = float(input("Enter temperature: "))

if temperature > 35:
    print("Very hot")
elif temperature >= 25:
    print("Warm")
else:
    print("Cool")
```

## 15. Quick Revision

- `input()` দিয়ে user-এর কাছ থেকে data নেওয়া হয়।
- `input()` সাধারণত string return করে।
- Numeric comparison-এর জন্য প্রয়োজন অনুযায়ী `int()` বা `float()` ব্যবহার করতে হয়।
- `if-else` দুটি outcome-এর মধ্যে সিদ্ধান্ত নিতে পারে।
- `if-elif-else` একাধিক category পরিচালনা করতে পারে।
- `and`, `or` ও `not` দিয়ে একাধিক condition combine করা যায়।
- Nested `if` দিয়ে একটি condition-এর ভেতরে আরেকটি condition পরীক্ষা করা যায়।
- নির্দিষ্ট menu option-এর জন্য `match-case` ব্যবহার করা যায়।
- Input validation ছাড়া conversion error হতে পারে।
- বাস্তব application-এ security ও invalid input handling বিবেচনা করতে হবে।

## 16. Self-Assessment Checklist

- [ ] `input()` নিয়ে condition লিখতে পারি।
- [ ] Numeric input convert করতে পারি।
- [ ] Even/Odd এবং Pass/Fail program তৈরি করতে পারি।
- [ ] `if-elif-else` দিয়ে grade calculator তৈরি করতে পারি।
- [ ] Logical operators ব্যবহার করতে পারি।
- [ ] `match-case` দিয়ে menu program তৈরি করতে পারি।
- [ ] Input-এর data type ও validation-এর গুরুত্ব বুঝি।
- [ ] Common conditional errors শনাক্ত করতে পারি।

**পরবর্তী টপিক:** `25_Input_Validation_with_Conditions.md`
