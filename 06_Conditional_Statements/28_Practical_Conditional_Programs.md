# 28. Practical Conditional Programs

## 1. Introduction

আগের টপিকগুলোতে আমরা `if`, `elif`, `else`, logical operators এবং nested conditions শিখেছি। এবার এগুলো ব্যবহার করে কিছু practical program তৈরি করব।

এই অধ্যায়ে আমরা শিখব:

- Pass/Fail এবং Grade Calculator
- Even/Odd এবং Number Classification
- Age Eligibility Checker
- Largest Number Finder
- Simple Calculator
- Discount Calculator
- Electricity Bill Calculator
- Login Checker
- Leap Year Checker
- BMI Category Calculator
- Input Validation

প্রতিটি program-এর ক্ষেত্রে problem, logic, code এবং output বোঝার চেষ্টা করবে।

## 2. Pass or Fail Checker

### Problem

একজন শিক্ষার্থীর marks 40 বা তার বেশি হলে Pass, অন্যথায় Fail দেখাতে হবে।

### Logic

1. User-এর কাছ থেকে marks নিতে হবে।
2. Marks 40 বা তার বেশি কি না পরীক্ষা করতে হবে।
3. শর্ত True হলে Pass, অন্যথায় Fail দেখাতে হবে।

### Code

```python
marks = int(input("Enter your marks: "))

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

### Sample Output

```text
Enter your marks: 65
Pass
```

### Explanation

- `input()` user-এর কাছ থেকে marks নেয়।
- `int()` input-কে integer-এ রূপান্তর করে।
- `marks >= 40` True হলে `if` block execute হয়।
- অন্যথায় `else` block execute হয়।

**Note:** এই উদাহরণে ধরে নেওয়া হয়েছে marks সঠিক integer এবং valid range-এর মধ্যে দেওয়া হয়েছে।

## 3. Grade Calculator

### Problem

Marks অনুযায়ী grade নির্ধারণ করতে হবে।

| Marks | Grade |
|---|---|
| 80–100 | A |
| 70–79 | B |
| 60–69 | C |
| 40–59 | D |
| 0–39 | F |

### Code

```python
marks = int(input("Enter your marks: "))

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

### Sample Output

```text
Enter your marks: 85
Grade A
```

### Explanation

- প্রথম condition marks-এর valid range পরীক্ষা করে।
- এরপর সর্বোচ্চ grade threshold থেকে নিচের দিকে পরীক্ষা করা হয়।
- প্রথম True condition-এর block execute হয়।
- কোনো grade threshold পূরণ না হলে `else` execute হয়।

**Important:** এখানে threshold বড় থেকে ছোট ক্রমে রাখা হয়েছে। তা না হলে ভুল grade আসতে পারে।

## 4. Even or Odd Checker

### Problem

একটি integer জোড় নাকি বিজোড় তা নির্ধারণ করতে হবে।

### Code

```python
number = int(input("Enter an integer: "))

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

### Sample Output

```text
Enter an integer: 12
Even
```

### Explanation

- `%` হলো modulo operator, যা ভাগশেষ বের করে।
- 2 দিয়ে ভাগ করলে ভাগশেষ 0 হলে number জোড়।
- অন্যথায় number বিজোড়।

### Test Cases

| Input | Output |
|---:|---|
| `8` | Even |
| `7` | Odd |
| `0` | Even |
| `-4` | Even |
| `-3` | Odd |

## 5. Positive, Negative or Zero

### Problem

একটি number positive, negative নাকি zero তা নির্ধারণ করতে হবে।

### Code

```python
number = float(input("Enter a number: "))

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

### Sample Output

```text
Enter a number: -5
Negative
```

### Explanation

- `number > 0` হলে Positive।
- প্রথম condition False এবং `number < 0` True হলে Negative।
- দুটি condition-ই False হলে number হলো Zero।

এখানে `float()` ব্যবহারের কারণে decimal number-ও গ্রহণ করা যায়।

## 6. Largest of Two Numbers

### Problem

দুটি number-এর মধ্যে বড় number খুঁজে বের করতে হবে।

### Code

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

if a > b:
    print("Largest:", a)
elif b > a:
    print("Largest:", b)
else:
    print("Both numbers are equal")
```

### Sample Output

```text
Enter first number: 15
Enter second number: 10
Largest: 15.0
```

### Explanation

- `a > b` হলে `a` বড়।
- `b > a` হলে `b` বড়।
- কোনোটিই True না হলে দুইটি number সমান।

এখানে `else` ব্যবহার করায় সমান number-এর জন্যও সঠিক result পাওয়া যায়।

## 7. Largest of Three Numbers

### Problem

তিনটি number-এর মধ্যে সবচেয়ে বড় number নির্ধারণ করতে হবে।

### Code

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

### Sample Output

```text
Enter first number: 12
Enter second number: 25
Enter third number: 18
Largest: 25.0
```

### Explanation

- `a` বড় বা সমান কি না, বাকি দুইটি number-এর সঙ্গে পরীক্ষা করা হয়।
- সেটি False হলে `b`-এর জন্য একই পরীক্ষা হয়।
- অন্যথায় `c` সবচেয়ে বড় বা সমান হবে।

এখানে `>=` ব্যবহার করায় সমান number থাকলেও program কাজ করে।

## 8. Age Eligibility Checker

### Problem

একজন ব্যক্তির বয়স 18 বা তার বেশি হলে adult, অন্যথায় minor দেখাতে হবে।

### Code

```python
age = int(input("Enter your age: "))

if age < 0:
    print("Invalid age")
elif age >= 18:
    print("Adult")
else:
    print("Minor")
```

### Sample Output

```text
Enter your age: 20
Adult
```

### Explanation

- Negative age-কে invalid হিসেবে ধরা হয়েছে।
- বয়স 18 বা তার বেশি হলে Adult।
- অন্যথায় Minor।

বাস্তব ক্ষেত্রে age eligibility-এর নিয়ম কাজ বা service অনুযায়ী ভিন্ন হতে পারে।

## 9. Simple Calculator

### Problem

দুটি number এবং একটি operator নিয়ে basic arithmetic operation সম্পন্ন করতে হবে।

সমর্থিত operator: `+`, `-`, `*`, `/`

### Code

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
    if b != 0:
        print("Result:", a / b)
    else:
        print("Error: Division by zero")
else:
    print("Invalid operator")
```

### Sample Output

```text
Enter first number: 10
Enter operator (+, -, *, /): /
Enter second number: 2
Result: 5.0
```

### Explanation

- Operator অনুযায়ী `if-elif` সঠিক operation নির্বাচন করে।
- Division-এর ক্ষেত্রে nested `if` দিয়ে divisor zero কি না পরীক্ষা করা হয়।
- `b != 0` হলে division নিরাপদে করা যায়।
- Unsupported operator দিলে error message দেখানো হয়।

এটি একটি basic learning calculator; এখানে invalid numeric input-এর exception handling যোগ করা হয়নি।

## 10. Discount Calculator

### Problem

Shopping-এর total amount অনুযায়ী discount নির্ধারণ করতে হবে।

- Amount 5000 বা বেশি হলে 20% discount।
- Amount 2000 বা বেশি হলে 10% discount।
- অন্যথায় discount নেই।

### Code

```python
amount = float(input("Enter total amount: "))

if amount < 0:
    print("Invalid amount")
elif amount >= 5000:
    discount = amount * 0.20
    print("Discount:", discount)
    print("Payable amount:", amount - discount)
elif amount >= 2000:
    discount = amount * 0.10
    print("Discount:", discount)
    print("Payable amount:", amount - discount)
else:
    print("No discount")
    print("Payable amount:", amount)
```

### Sample Output

```text
Enter total amount: 6000
Discount: 1200.0
Payable amount: 4800.0
```

### Explanation

Discount বের করার formula:

`Discount = Amount × Discount Rate`

Payable amount-এর formula:

`Payable Amount = Amount - Discount`

এখানে 20% discount-এর জন্য `0.20` এবং 10% discount-এর জন্য `0.10` ব্যবহার করা হয়েছে।

## 11. Electricity Bill Calculator

### Problem

ব্যবহৃত electricity units অনুযায়ী একটি simplified bill হিসাব করতে হবে।

এই উদাহরণে rate:

- প্রথম 100 units: প্রতি unit 5 টাকা।
- পরবর্তী 100 units: প্রতি unit 7 টাকা।
- 200-এর বেশি units: অতিরিক্ত প্রতি unit 10 টাকা।

এখানে slab অনুযায়ী cumulative charge হিসাব করা হবে।

### Code

```python
units = float(input("Enter electricity units: "))

if units < 0:
    print("Invalid units")
elif units <= 100:
    bill = units * 5
    print("Electricity bill:", bill)
elif units <= 200:
    bill = (100 * 5) + ((units - 100) * 7)
    print("Electricity bill:", bill)
else:
    bill = (100 * 5) + (100 * 7) + ((units - 200) * 10)
    print("Electricity bill:", bill)
```

### Sample Output

```text
Enter electricity units: 150
Electricity bill: 850.0
```

### Explanation

150 units-এর জন্য:

- প্রথম 100 units: `100 × 5 = 500`
- পরবর্তী 50 units: `50 × 7 = 350`
- মোট bill: `500 + 350 = 850`

**Note:** এটি practice-এর জন্য তৈরি simplified example। বাস্তব electricity bill-এ fixed charge, VAT, demand charge এবং অন্যান্য নিয়ম থাকতে পারে।

## 12. Login Checker

### Problem

Username ও password সঠিক হলে login successful দেখাতে হবে।

### Code

```python
correct_username = "student"
correct_password = "python123"

username = input("Enter username: ")
password = input("Enter password: ")

if username == correct_username and password == correct_password:
    print("Login successful")
else:
    print("Invalid username or password")
```

### Sample Output

```text
Enter username: student
Enter password: python123
Login successful
```

### Explanation

এখানে `and` ব্যবহার করা হয়েছে। তাই username এবং password—দুটিই সঠিক হতে হবে।

যেকোনো একটি ভুল হলে combined condition False হবে।

**Security Note:** এটি শুধু শেখার উদাহরণ। বাস্তব application-এ password code-এর মধ্যে plain text হিসেবে রাখা উচিত নয়। Authentication-এর জন্য secure password hashing এবং অন্যান্য security measures প্রয়োজন।

## 13. Leap Year Checker

### Problem

একটি year leap year কি না নির্ধারণ করতে হবে।

### Rules

একটি year leap year হবে যদি:

- এটি 400 দিয়ে বিভাজ্য হয়; অথবা
- এটি 4 দিয়ে বিভাজ্য হয়, কিন্তু 100 দিয়ে বিভাজ্য নয়।

### Code

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

### Sample Output

```text
Enter a year: 2024
Leap year
```

### Explanation

- 400 দিয়ে বিভাজ্য হলে Leap Year।
- তা না হলে 100 দিয়ে বিভাজ্য হলে Leap Year নয়।
- অন্যথায় 4 দিয়ে বিভাজ্য হলে Leap Year।
- কোনো শর্ত পূরণ না হলে Leap Year নয়।

### Test Cases

| Year | Result |
|---:|---|
| 2024 | Leap year |
| 1900 | Not a leap year |
| 2000 | Leap year |
| 2023 | Not a leap year |

## 14. BMI Category Calculator

### Problem

BMI value অনুযায়ী একটি সাধারণ category দেখাতে হবে।

BMI-এর formula:

`BMI = Weight (kg) / Height (m)²`

এই উদাহরণে প্রাপ্তবয়স্কদের জন্য প্রচলিত screening categories ব্যবহার করা হচ্ছে।

### Code

```python
weight = float(input("Enter weight in kg: "))
height = float(input("Enter height in meters: "))

if weight <= 0 or height <= 0:
    print("Invalid weight or height")
else:
    bmi = weight / (height ** 2)

    print("BMI:", round(bmi, 2))

    if bmi < 18.5:
        print("Underweight")
    elif bmi < 25:
        print("Normal weight")
    elif bmi < 30:
        print("Overweight")
    else:
        print("Obesity range")
```

### Sample Output

```text
Enter weight in kg: 70
Enter height in meters: 1.75
BMI: 22.86
Normal weight
```

### Explanation

- Weight ও height positive কি না প্রথমে পরীক্ষা করা হয়।
- `height ** 2` দিয়ে height-এর square বের করা হয়।
- `round(bmi, 2)` BMI-কে দুই decimal place-এ দেখায়।
- এরপর `if-elif-else` দিয়ে category নির্ধারণ করা হয়।

**Note:** BMI একটি screening measure, একা এটি দিয়ে কারও স্বাস্থ্য নির্ণয় করা যায় না। শিশু-কিশোরদের ক্ষেত্রে এই adult thresholds প্রযোজ্য নয়।

## 15. Input Validation with Conditions

### Problem

User-এর দেওয়া number 1 থেকে 10-এর মধ্যে আছে কি না পরীক্ষা করতে হবে।

### Code

```python
number = int(input("Enter a number from 1 to 10: "))

if number < 1 or number > 10:
    print("Invalid number")
else:
    print("Valid number")
```

### Sample Output

```text
Enter a number from 1 to 10: 7
Valid number
```

### Explanation

`number < 1 or number > 10` True হবে যখন number অনুমোদিত range-এর বাইরে থাকবে।

তাই:

- 0 → Invalid number
- 1 → Valid number
- 7 → Valid number
- 10 → Valid number
- 11 → Invalid number

এখানে `int(input())` ব্যবহার করায় non-integer input দিলে `ValueError` হতে পারে। Invalid text-ও সামলাতে চাইলে পরবর্তী সময়ে `try-except` ব্যবহার করতে হবে।

## 16. Common Mistakes in Practical Programs

### Mistake 1: Condition-এর ভুল order

```python
if marks >= 40:
    print("Pass")
elif marks >= 80:
    print("Grade A")
```

এখানে 80 বা তার বেশি marks হলেও প্রথম condition True হওয়ায় `Grade A` দেখাবে না।

**Solution:** বড় threshold আগে পরীক্ষা করবে।

### Mistake 2: `and` ও `or` গুলিয়ে ফেলা

18 থেকে 60-এর মধ্যে বয়স পরীক্ষা করতে:

```python
if age >= 18 and age <= 60:
    print("Eligible")
```

এখানে `and` দরকার, কারণ দুইটি শর্তই সত্য হতে হবে।

### Mistake 3: Boundary operator ভুল হওয়া

40 বা তার বেশি হলে pass করার নিয়মে `marks > 40` ব্যবহার করলে 40 marks-কে Fail দেখাবে।

**Solution:** নিয়ম অনুযায়ী `>=` ব্যবহার করবে।

### Mistake 4: Division by zero

```python
result = a / b
```

`b` শূন্য হলে `ZeroDivisionError` হবে।

**Solution:** Division-এর আগে `b != 0` পরীক্ষা করবে।

### Mistake 5: Invalid input সামলাতে না পারা

`int(input())`-এ user text দিলে program error দিতে পারে।

**Solution:** পরবর্তী chapter-এ `try-except` দিয়ে এই সমস্যা সামলানো শিখবে।

## 17. Practice Exercises

নিজে code লেখার চেষ্টা করবে। প্রথমে answer key না দেখে সমাধান করবে।

### Exercise 1: Voting Eligibility

User-এর বয়স input নাও। বয়স 18 বা তার বেশি হলে `"Eligible to vote"` এবং অন্যথায় `"Not eligible"` দেখাও। Negative age-ও validate করো।

### Exercise 2: Largest of Four Numbers

চারটি number input নিয়ে সবচেয়ে বড় number বের করো। সব number সমান হলেও যেন সঠিক result আসে।

### Exercise 3: Student Grade Calculator

নিচের grading scale অনুযায়ী grade নির্ধারণ করো:

| Marks | Grade |
|---|---|
| 90–100 | A+ |
| 80–89 | A |
| 70–79 | B |
| 60–69 | C |
| 40–59 | D |
| 0–39 | F |

0–100-এর বাইরের marks-কে invalid হিসেবে দেখাবে।

### Exercise 4: Simple Login Validation

একটি username input নাও। Username `"admin"` হলে `"Welcome Admin"` দেখাও। `"student"` হলে `"Welcome Student"` দেখাও। অন্য সব ক্ষেত্রে `"Unknown User"` দেখাও।

### Exercise 5: Number Divisibility

একটি integer input নাও।

- 3 ও 5 উভয় দিয়ে বিভাজ্য হলে `"Divisible by both"`।
- শুধু 3 দিয়ে বিভাজ্য হলে `"Divisible by 3"`।
- শুধু 5 দিয়ে বিভাজ্য হলে `"Divisible by 5"`।
- অন্যথায় `"Not divisible by 3 or 5"`।

### Exercise 6: Shipping Cost

Order amount 3000 বা তার বেশি হলে shipping free। অন্যথায় shipping charge 100 টাকা। Negative order amount invalid হিসেবে দেখাও। মোট payable amount-ও print করো।

### Exercise 7: Simple Menu Program

User-কে menu দেখাও:

1. Say Hello
2. Show Python
3. Exit

User-এর choice অনুযায়ী সঠিক message দেখাও। Invalid choice হলে `"Invalid choice"` দেখাও।

## 18. Answer Key

### Exercise 1

```python
age = int(input("Enter your age: "))

if age < 0:
    print("Invalid age")
elif age >= 18:
    print("Eligible to vote")
else:
    print("Not eligible")
```

### Exercise 2

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))
c = float(input("Enter third number: "))
d = float(input("Enter fourth number: "))

largest = a

if b > largest:
    largest = b

if c > largest:
    largest = c

if d > largest:
    largest = d

print("Largest:", largest)
```

এখানে প্রতিটি number বর্তমান `largest`-এর সঙ্গে তুলনা করা হয়। সমান number থাকলেও program কাজ করে।

### Exercise 3

```python
marks = int(input("Enter marks: "))

if marks < 0 or marks > 100:
    print("Invalid marks")
elif marks >= 90:
    print("Grade A+")
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

### Exercise 4

```python
username = input("Enter username: ")

if username == "admin":
    print("Welcome Admin")
elif username == "student":
    print("Welcome Student")
else:
    print("Unknown User")
```

### Exercise 5

```python
number = int(input("Enter an integer: "))

if number % 3 == 0 and number % 5 == 0:
    print("Divisible by both")
elif number % 3 == 0:
    print("Divisible by 3")
elif number % 5 == 0:
    print("Divisible by 5")
else:
    print("Not divisible by 3 or 5")
```

এখানে উভয় দিয়ে বিভাজ্য হওয়ার condition আগে রাখা হয়েছে।

### Exercise 6

```python
amount = float(input("Enter order amount: "))

if amount < 0:
    print("Invalid amount")
elif amount >= 3000:
    print("Shipping cost: 0")
    print("Payable amount:", amount)
else:
    shipping = 100
    print("Shipping cost:", shipping)
    print("Payable amount:", amount + shipping)
```

### Exercise 7

```python
print("1. Say Hello")
print("2. Show Python")
print("3. Exit")

choice = input("Enter your choice: ")

if choice == "1":
    print("Hello!")
elif choice == "2":
    print("Python is a programming language.")
elif choice == "3":
    print("Goodbye!")
else:
    print("Invalid choice")
```

## 19. Chapter Summary

এই অধ্যায়ে আমরা শিখেছি কীভাবে conditional statements ব্যবহার করে ছোট ছোট practical program তৈরি করা যায়।

মনে রাখবে:

- `if` একটি condition পরীক্ষা করে।
- `elif` অতিরিক্ত condition পরীক্ষা করে।
- `else` আগের কোনো condition True না হলে execute হয়।
- `and` দিয়ে একাধিক শর্ত একসঙ্গে সত্য হওয়া পরীক্ষা করা যায়।
- `or` দিয়ে একাধিক বিকল্প condition পরীক্ষা করা যায়।
- Nested `if` দিয়ে এক condition-এর ভেতরে আরেক condition পরীক্ষা করা যায়।
- Input validation program-কে invalid value থেকে সুরক্ষিত রাখতে সাহায্য করে।
- Test case দিয়ে boundary এবং বিভিন্ন input পরীক্ষা করা উচিত।

## 20. Self-Assessment Checklist

- [ ] Pass/Fail checker তৈরি করতে পারি।
- [ ] Grade calculator তৈরি করতে পারি।
- [ ] Even/Odd এবং number classification করতে পারি।
- [ ] দুই বা তিনটি number-এর মধ্যে largest বের করতে পারি।
- [ ] `if-elif-else` দিয়ে calculator তৈরি করতে পারি।
- [ ] `and` ও `or` সঠিকভাবে ব্যবহার করতে পারি।
- [ ] Nested condition দিয়ে division by zero সামলাতে পারি।
- [ ] Input validation-এর basic logic বুঝি।
- [ ] নিজে test cases তৈরি করে program পরীক্ষা করতে পারি।

**পরবর্তী টপিক:** `29_Conditional_Problem_Solving_Techniques.md`
