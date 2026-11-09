# 31. Conditional Programming Exercises

## 1. Introduction

এই অধ্যায়ে Python conditional statements ব্যবহার করে বিভিন্ন programming problem solve করার practice করব।

প্রতিটি problem সমাধান করার সময়:

1. Problem ভালোভাবে বুঝবে।
2. Input ও expected output নির্ধারণ করবে।
3. প্রয়োজনীয় condition লিখবে।
4. সঠিক operator নির্বাচন করবে।
5. Python code লিখবে।
6. একাধিক test case দিয়ে program পরীক্ষা করবে।

এই অধ্যায়ের exercise-গুলো তিনটি level-এ ভাগ করা হয়েছে:

- **Level 1:** Beginner
- **Level 2:** Intermediate
- **Level 3:** Challenging

প্রথমে নিজে solve করার চেষ্টা করবে। তারপর Answer Key দেখে নিজের solution যাচাই করবে।

# Level 1: Beginner Exercises

## Exercise 1: Positive, Negative or Zero

একটি number input নিয়ে সেটি positive, negative নাকি zero তা নির্ধারণ করো।

Example:

```text
Enter a number: -5
Negative
```

## Exercise 2: Even or Odd

একটি integer input নিয়ে সেটি even নাকি odd তা নির্ধারণ করো।

Example:

```text
Enter an integer: 7
Odd
```

## Exercise 3: Pass or Fail

একজন শিক্ষার্থীর marks input নাও। Marks 40 বা তার বেশি হলে Pass, অন্যথায় Fail দেখাও।

Example:

```text
Enter marks: 65
Pass
```

ধরে নাও marks 0 থেকে 100-এর মধ্যে হতে পারে। Range-এর বাইরের marks-কে invalid দেখাবে।

## Exercise 4: Largest of Two Numbers

দুটি number input নিয়ে বড় number দেখাও। দুইটি সমান হলে সেটিও জানাবে।

Example:

```text
Enter first number: 10
Enter second number: 20
Largest: 20
```

## Exercise 5: Divisibility Checker

একটি integer input নাও। সেটি 5 দিয়ে বিভাজ্য কি না পরীক্ষা করো।

Example:

```text
Enter an integer: 25
Divisible by 5
```

## Exercise 6: Age Category

একটি বয়স input নিয়ে category নির্ধারণ করো:

- 0–12: Child
- 13–19: Teenager
- 20–59: Adult
- 60 বা তার বেশি: Senior
- Negative age: Invalid age

Example:

```text
Enter age: 16
Teenager
```

## Exercise 7: Vowel or Consonant

একটি English alphabet character input নাও। সেটি vowel নাকি consonant তা নির্ধারণ করো।

Vowels: `a`, `e`, `i`, `o`, `u`

Example:

```text
Enter a character: E
Vowel
```

Input একটি মাত্র English alphabet না হলে invalid দেখাবে।

## Exercise 8: Simple Discount

Purchase amount 5000 বা তার বেশি হলে 10% discount দাও। অন্যথায় discount নেই।

Final payable amount দেখাও। Negative amount হলে invalid দেখাবে।

Example:

```text
Enter amount: 6000
Discount: 600.0
Payable amount: 5400.0
```

# Level 2: Intermediate Exercises

## Exercise 9: Grade Calculator

Marks অনুযায়ী grade নির্ধারণ করো:

| Marks | Grade |
|---|---|
| 80–100 | A |
| 70–79 | B |
| 60–69 | C |
| 40–59 | D |
| 0–39 | F |

0–100-এর বাইরের marks invalid হিসেবে দেখাবে।

Example:

```text
Enter marks: 75
Grade B
```

## Exercise 10: Largest of Three Numbers

তিনটি number input নিয়ে সবচেয়ে বড় number বের করো। একাধিক number সমান হলেও সঠিক result দিতে হবে।

Example:

```text
Enter first number: 10
Enter second number: 25
Enter third number: 15
Largest: 25
```

## Exercise 11: Leap Year Checker

একটি year leap year কি না নির্ধারণ করো।

Rules:

- 400 দিয়ে বিভাজ্য হলে Leap Year।
- অন্যথায় 100 দিয়ে বিভাজ্য হলে Leap Year নয়।
- অন্যথায় 4 দিয়ে বিভাজ্য হলে Leap Year।
- বাকি ক্ষেত্রে Leap Year নয়।

Example:

```text
Enter year: 2000
Leap year
```

## Exercise 12: Simple Calculator

দুটি number এবং একটি operator input নাও। `+`, `-`, `*`, `/` support করবে।

Requirements:

- Operator অনুযায়ী calculation করতে হবে।
- Zero দিয়ে division করা যাবে না।
- Unsupported operator হলে invalid দেখাবে।

Example:

```text
Enter first number: 10
Enter operator: *
Enter second number: 5
Result: 50.0
```

## Exercise 13: Admission Eligibility

একজন applicant-এর:

- Marks কমপক্ষে 80 হতে হবে।
- Attendance কমপক্ষে 75% হতে হবে।

দুইটি শর্ত পূরণ করলে Eligible, অন্যথায় Not eligible দেখাবে।

Marks 0–100 এবং attendance 0–100-এর মধ্যে আছে কি না, সেটিও validate করবে।

## Exercise 14: Number Divisibility Classification

একটি integer input নিয়ে পরীক্ষা করো:

- 3 ও 5 উভয় দিয়ে বিভাজ্য হলে `Divisible by both`।
- শুধু 3 দিয়ে বিভাজ্য হলে `Divisible by 3`।
- শুধু 5 দিয়ে বিভাজ্য হলে `Divisible by 5`।
- অন্যথায় `Not divisible by 3 or 5`।

Example:

```text
Enter an integer: 15
Divisible by both
```

## Exercise 15: Electricity Bill

একটি simplified electricity bill হিসাব করো:

- প্রথম 100 units: প্রতি unit 5 টাকা।
- পরবর্তী 100 units: প্রতি unit 7 টাকা।
- 200 units-এর বেশি অংশ: প্রতি unit 10 টাকা।

Slab অনুযায়ী cumulative charge হিসাব করবে। Negative units invalid দেখাবে।

Example:

```text
Enter units: 150
Electricity bill: 850.0
```

## Exercise 16: Login Checker

একটি username এবং password input নাও।

- Username `admin` এবং password `python123` হলে Login successful।
- অন্যথায় Invalid credentials।

Example:

```text
Enter username: admin
Enter password: python123
Login successful
```

এটি conditional logic practice-এর জন্য, real authentication system নয়।

# Level 3: Challenging Exercises

## Exercise 17: Second Largest of Three Numbers

তিনটি number input নিয়ে তাদের মধ্যে দ্বিতীয় বৃহত্তম **স্বতন্ত্র value** বের করো।

যদি অন্তত দুটি স্বতন্ত্র value না থাকে, তাহলে `"No second distinct largest value"` দেখাও।

Examples:

```text
Input: 10, 20, 30
Output: 20
```

```text
Input: 10, 30, 30
Output: 10
```

```text
Input: 5, 5, 5
Output: No second distinct largest value
```

## Exercise 18: Triangle Validity and Type

তিনটি side length input নাও।

প্রথমে পরীক্ষা করো triangle তৈরি করা সম্ভব কি না।

Valid triangle-এর জন্য:

- সব side positive হতে হবে।
- যেকোনো দুই side-এর যোগফল তৃতীয় side-এর চেয়ে বড় হতে হবে।

Triangle valid হলে type নির্ধারণ করো:

- তিনটি side সমান: Equilateral
- ঠিক দুটি side সমান: Isosceles
- সব side আলাদা: Scalene

## Exercise 19: Character Classification

একটি single character input নিয়ে নির্ধারণ করো সেটি:

- Uppercase letter
- Lowercase letter
- Digit
- Special character

Example:

```text
Enter a character: A
Uppercase letter
```

একটি মাত্র character input গ্রহণ করবে।

## Exercise 20: ATM Withdrawal Checker

একটি simplified ATM program তৈরি করো।

Inputs:

- Account balance
- Withdrawal amount

Rules:

- Balance ও withdrawal amount negative হতে পারবে না।
- Withdrawal amount zero হতে পারবে না।
- Withdrawal amount balance-এর বেশি হতে পারবে না।
- সব শর্ত ঠিক থাকলে remaining balance দেখাবে।

Example:

```text
Enter balance: 5000
Enter withdrawal amount: 1200
Remaining balance: 3800.0
```

এটি শুধু programming practice; বাস্তব ATM বা banking system নয়।

## Exercise 21: Shipping Cost Calculator

Order amount অনুযায়ী shipping cost নির্ধারণ করো:

- Amount 3000 বা তার বেশি: Free shipping
- Amount 1000 থেকে 2999.99: Shipping 100 টাকা
- Amount 1000-এর কম: Shipping 150 টাকা
- Negative amount: Invalid

Shipping cost-সহ total payable amount দেখাও।

## Exercise 22: Password Rule Checker

একটি password input নিয়ে নিচের নিয়মগুলো পরীক্ষা করো:

- অন্তত 8 character হতে হবে।
- অন্তত একটি uppercase letter থাকতে হবে।
- অন্তত একটি lowercase letter থাকতে হবে।
- অন্তত একটি digit থাকতে হবে।

সব নিয়ম পূরণ করলে `"Password meets the basic rules"` দেখাবে। অন্যথায় কোন নিয়মগুলো পূরণ হয়নি, সেগুলো দেখাবে।

এই exercise-এ string methods ও loops ব্যবহার করা যেতে পারে। এটি password security-এর পূর্ণ পরীক্ষা নয়।

## Exercise 23: Rock, Paper, Scissors

দুইজন player-এর choice input নাও:

- `rock`
- `paper`
- `scissors`

Rules:

- Rock beats scissors.
- Scissors beats paper.
- Paper beats rock.
- একই choice হলে draw।
- অন্য input হলে invalid choice।

Example:

```text
Player 1: rock
Player 2: scissors
Player 1 wins
```

## Exercise 24: Mini Menu System

একটি menu তৈরি করো:

```text
1. Check Even/Odd
2. Check Positive/Negative/Zero
3. Check Pass/Fail
4. Exit
```

User-এর choice অনুযায়ী সঠিক operation সম্পন্ন করো। Invalid choice হলে error message দেখাও।

# Answer Key

নিচে সব exercise-এর একটি করে সম্ভাব্য solution দেওয়া হলো। একই problem-এর একাধিক সঠিক solution থাকতে পারে।

## Solution 1: Positive, Negative or Zero

```python
number = float(input("Enter a number: "))

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

## Solution 2: Even or Odd

```python
number = int(input("Enter an integer: "))

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

## Solution 3: Pass or Fail

```python
marks = float(input("Enter marks: "))

if marks < 0 or marks > 100:
    print("Invalid marks")
elif marks >= 40:
    print("Pass")
else:
    print("Fail")
```

## Solution 4: Largest of Two Numbers

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

## Solution 5: Divisibility Checker

```python
number = int(input("Enter an integer: "))

if number % 5 == 0:
    print("Divisible by 5")
else:
    print("Not divisible by 5")
```

## Solution 6: Age Category

```python
age = int(input("Enter age: "))

if age < 0:
    print("Invalid age")
elif age <= 12:
    print("Child")
elif age <= 19:
    print("Teenager")
elif age <= 59:
    print("Adult")
else:
    print("Senior")
```

## Solution 7: Vowel or Consonant

```python
character = input("Enter a character: ")

if len(character) != 1 or not character.isascii() or not character.isalpha():
    print("Invalid character")
elif character.lower() in "aeiou":
    print("Vowel")
else:
    print("Consonant")
```

`lower()` uppercase letter-কে lowercase করে, তাই `A` এবং `a` একইভাবে পরীক্ষা করা যায়।

## Solution 8: Simple Discount

```python
amount = float(input("Enter amount: "))

if amount < 0:
    print("Invalid amount")
elif amount >= 5000:
    discount = amount * 0.10
    print("Discount:", discount)
    print("Payable amount:", amount - discount)
else:
    print("Discount: 0")
    print("Payable amount:", amount)
```

## Solution 9: Grade Calculator

```python
marks = float(input("Enter marks: "))

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

## Solution 10: Largest of Three Numbers

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

## Solution 11: Leap Year Checker

```python
year = int(input("Enter year: "))

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

## Solution 12: Simple Calculator

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

## Solution 13: Admission Eligibility

```python
marks = float(input("Enter marks: "))
attendance = float(input("Enter attendance: "))

if marks < 0 or marks > 100 or attendance < 0 or attendance > 100:
    print("Invalid input")
elif marks >= 80 and attendance >= 75:
    print("Eligible")
else:
    print("Not eligible")
```

## Solution 14: Number Divisibility Classification

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

উভয় দিয়ে বিভাজ্য হওয়ার condition প্রথমে পরীক্ষা করতে হবে।

## Solution 15: Electricity Bill

```python
units = float(input("Enter units: "))

if units < 0:
    print("Invalid units")
elif units <= 100:
    bill = units * 5
    print("Electricity bill:", bill)
elif units <= 200:
    bill = 100 * 5 + (units - 100) * 7
    print("Electricity bill:", bill)
else:
    bill = 100 * 5 + 100 * 7 + (units - 200) * 10
    print("Electricity bill:", bill)
```

## Solution 16: Login Checker

```python
username = input("Enter username: ")
password = input("Enter password: ")

if username == "admin" and password == "python123":
    print("Login successful")
else:
    print("Invalid credentials")
```

## Solution 17: Second Largest Distinct Value

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))
c = float(input("Enter third number: "))

if a == b and b == c:
    print("No second distinct largest value")
elif a == b:
    print("Second largest:", c)
elif a == c:
    print("Second largest:", b)
elif b == c:
    print("Second largest:", a)
else:
    if a > b and a > c:
        if b > c:
            print("Second largest:", b)
        else:
            print("Second largest:", c)
    elif b > a and b > c:
        if a > c:
            print("Second largest:", a)
        else:
            print("Second largest:", c)
    else:
        if a > b:
            print("Second largest:", a)
        else:
            print("Second largest:", b)
```

এখানে আগে equal values-এর case পরীক্ষা করা হয়েছে। এরপর সবচেয়ে বড় ও দ্বিতীয় বৃহত্তম স্বতন্ত্র value নির্ধারণ করা হয়েছে।

## Solution 18: Triangle Validity and Type

```python
a = float(input("Enter first side: "))
b = float(input("Enter second side: "))
c = float(input("Enter third side: "))

if a <= 0 or b <= 0 or c <= 0:
    print("Invalid triangle")
elif a + b <= c or a + c <= b or b + c <= a:
    print("Invalid triangle")
elif a == b and b == c:
    print("Equilateral triangle")
elif a == b or a == c or b == c:
    print("Isosceles triangle")
else:
    print("Scalene triangle")
```

Triangle-এর validity যাচাই করার পর type নির্ধারণ করা হয়েছে।

## Solution 19: Character Classification

```python
character = input("Enter a character: ")

if len(character) != 1:
    print("Invalid input")
elif character.isascii() and character.isupper():
    print("Uppercase letter")
elif character.isascii() and character.islower():
    print("Lowercase letter")
elif character.isascii() and character.isdigit():
    print("Digit")
else:
    print("Special character")
```

এই solution-এ ASCII English character, digit এবং অন্য single character আলাদা করা হয়েছে।

## Solution 20: ATM Withdrawal Checker

```python
balance = float(input("Enter balance: "))
withdrawal = float(input("Enter withdrawal amount: "))

if balance < 0 or withdrawal < 0:
    print("Invalid amount")
elif withdrawal == 0:
    print("Withdrawal must be greater than zero")
elif withdrawal > balance:
    print("Insufficient balance")
else:
    remaining = balance - withdrawal
    print("Remaining balance:", remaining)
```

## Solution 21: Shipping Cost Calculator

```python
amount = float(input("Enter order amount: "))

if amount < 0:
    print("Invalid amount")
elif amount >= 3000:
    shipping = 0
    print("Shipping cost:", shipping)
    print("Total payable:", amount + shipping)
elif amount >= 1000:
    shipping = 100
    print("Shipping cost:", shipping)
    print("Total payable:", amount + shipping)
else:
    shipping = 150
    print("Shipping cost:", shipping)
    print("Total payable:", amount + shipping)
```

## Solution 22: Password Rule Checker

```python
password = input("Enter password: ")

has_upper = any(ch.isupper() for ch in password)
has_lower = any(ch.islower() for ch in password)
has_digit = any(ch.isdigit() for ch in password)
has_min_length = len(password) >= 8

if not has_min_length:
    print("Password must contain at least 8 characters")

if not has_upper:
    print("Password must contain an uppercase letter")

if not has_lower:
    print("Password must contain a lowercase letter")

if not has_digit:
    print("Password must contain a digit")

if has_min_length and has_upper and has_lower and has_digit:
    print("Password meets the basic rules")
```

এখানে `any()` ও generator expression ব্যবহার করা হয়েছে, যা পরবর্তী topic-গুলোতে বিস্তারিত শেখা হবে।

## Solution 23: Rock, Paper, Scissors

```python
player1 = input("Player 1: ").lower()
player2 = input("Player 2: ").lower()

valid_choices = ("rock", "paper", "scissors")

if player1 not in valid_choices or player2 not in valid_choices:
    print("Invalid choice")
elif player1 == player2:
    print("Draw")
elif (
    (player1 == "rock" and player2 == "scissors")
    or (player1 == "paper" and player2 == "rock")
    or (player1 == "scissors" and player2 == "paper")
):
    print("Player 1 wins")
else:
    print("Player 2 wins")
```

## Solution 24: Mini Menu System

```python
print("1. Check Even/Odd")
print("2. Check Positive/Negative/Zero")
print("3. Check Pass/Fail")
print("4. Exit")

choice = input("Enter your choice: ")

if choice == "1":
    number = int(input("Enter an integer: "))

    if number % 2 == 0:
        print("Even")
    else:
        print("Odd")

elif choice == "2":
    number = float(input("Enter a number: "))

    if number > 0:
        print("Positive")
    elif number < 0:
        print("Negative")
    else:
        print("Zero")

elif choice == "3":
    marks = float(input("Enter marks: "))

    if marks < 0 or marks > 100:
        print("Invalid marks")
    elif marks >= 40:
        print("Pass")
    else:
        print("Fail")

elif choice == "4":
    print("Goodbye!")

else:
    print("Invalid choice")
```

## 5. Additional Challenge Rules

Answer Key দেখার পর নিজের code-কে আরও উন্নত করার চেষ্টা করবে।

1. যেখানে সম্ভব duplicate code কমাও।
2. প্রতিটি program-এর জন্য boundary test cases তৈরি করো।
3. Negative value এবং invalid range পরীক্ষা করো।
4. Nested condition অপ্রয়োজনীয়ভাবে ব্যবহার কোরো না।
5. প্রতিটি condition কেন প্রয়োজন, নিজের ভাষায় ব্যাখ্যা করো।
6. পরে `try-except` শিখলে invalid text input-এর error handling যোগ করো।

## 6. Self-Assessment Checklist

- [ ] Basic `if-else` problem solve করতে পারি।
- [ ] `if-elif-else` দিয়ে multiple category নির্ধারণ করতে পারি।
- [ ] `and`, `or` এবং `not` সঠিকভাবে ব্যবহার করতে পারি।
- [ ] Nested conditions দিয়ে complex rules implement করতে পারি।
- [ ] Range ও boundary value validate করতে পারি।
- [ ] Problem statement থেকে condition তৈরি করতে পারি।
- [ ] একাধিক test case দিয়ে program যাচাই করতে পারি।
- [ ] নিজের solution-এর logic ব্যাখ্যা করতে পারি।

## 7. Final Practice Advice

Bro, সব exercise একসঙ্গে solve করার প্রয়োজন নেই। প্রতিদিন কয়েকটি problem নিজে solve করার চেষ্টা করো।

সবচেয়ে ভালো পদ্ধতি:

1. Problem পড়ো।
2. নিজের logic লিখো।
3. Code তৈরি করো।
4. Test করো।
5. Error হলে debugging করো।
6. শেষে Answer Key-এর সঙ্গে compare করো।

Code মুখস্থ করার চেয়ে **কেন একটি condition ব্যবহার করা হয়েছে এবং কীভাবে সেটি result নির্ধারণ করে**—এটা বোঝা অনেক বেশি গুরুত্বপূর্ণ।

**পরবর্তী টপিক:** `32_Chapter_Review_and_Self_Assessment.md`