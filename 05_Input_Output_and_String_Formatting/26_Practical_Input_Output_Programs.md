# 26. Practical Input/Output Programs in Python

## 1. Introduction

আগের topics-এ আমরা শিখেছি কীভাবে Python-এ input নিতে হয়, output দেখাতে হয়, data type convert করতে হয় এবং string format করতে হয়।

এখন এসব concept ব্যবহার করে কয়েকটি practical program তৈরি করব।

এই chapter-এ আমরা শিখব:

1. Personal information display
2. Two-number calculator
3. Rectangle area calculator
4. Celsius to Fahrenheit converter
5. Student marks and percentage calculator
6. Shopping bill calculator
7. Discount calculator
8. Simple interest calculator
9. Time converter
10. BMI calculator
11. Multiple-subject average calculator
12. Input validation
13. Formatted report generation

প্রতিটি program-এ code, sample input, output এবং explanation থাকবে।

## 2. Program 1: Personal Information Display

### Objective

User-এর কাছ থেকে নাম, বয়স ও department নিয়ে সুন্দরভাবে display করা।

### Code

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))
department = input("Enter your department: ")

print("\n--- Personal Information ---")
print(f"Name: {name}")
print(f"Age: {age}")
print(f"Department: {department}")
```

### Sample Input

```text
Enter your name: Masum
Enter your age: 22
Enter your department: CSE
```

### Output

```text
--- Personal Information ---
Name: Masum
Age: 22
Department: CSE
```

### Explanation

- `input()` দিয়ে user-এর কাছ থেকে তথ্য নেওয়া হয়েছে।
- `age`-এর জন্য `int()` ব্যবহার করা হয়েছে।
- `\n` output-এর আগে নতুন line তৈরি করেছে।
- f-string দিয়ে variable-এর value সুন্দরভাবে দেখানো হয়েছে।

**Learning point:** String input ও numeric input-এর পার্থক্য বুঝতে হবে।

## 3. Program 2: Two-Number Calculator

### Objective

দুটি number নিয়ে যোগ, বিয়োগ, গুণ ও ভাগ করা।

### Code

```python
first = float(input("Enter first number: "))
second = float(input("Enter second number: "))

print("\n--- Calculator Result ---")
print(f"Addition: {first + second:.2f}")
print(f"Subtraction: {first - second:.2f}")
print(f"Multiplication: {first * second:.2f}")

if second != 0:
    print(f"Division: {first / second:.2f}")
else:
    print("Division: Cannot divide by zero.")
```

### Sample Input

```text
Enter first number: 20
Enter second number: 5
```

### Output

```text
--- Calculator Result ---
Addition: 25.00
Subtraction: 15.00
Multiplication: 100.00
Division: 4.00
```

### Explanation

- `float()` integer ও decimal—দুই ধরনের numeric input নিতে পারে।
- Arithmetic operators দিয়ে calculations করা হয়েছে।
- `:.2f` দুই decimal places দেখিয়েছে।
- `if second != 0` দিয়ে zero division এড়ানো হয়েছে।

**Learning point:** Calculation করার আগে সম্ভাব্য invalid operation বিবেচনা করতে হবে।

## 4. Program 3: Rectangle Area and Perimeter

### Objective

Rectangle-এর length ও width নিয়ে area এবং perimeter বের করা।

### Formula

\[
\text{Area}=\text{Length}\times\text{Width}
\]

\[
\text{Perimeter}=2(\text{Length}+\text{Width})
\]

### Code

```python
length = float(input("Enter length: "))
width = float(input("Enter width: "))

if length > 0 and width > 0:
    area = length * width
    perimeter = 2 * (length + width)

    print(f"Area: {area:.2f}")
    print(f"Perimeter: {perimeter:.2f}")
else:
    print("Length and width must be positive.")
```

### Sample Input

```text
Enter length: 10
Enter width: 5
```

### Output

```text
Area: 50.00
Perimeter: 30.00
```

### Explanation

- `float()` decimal measurement নিতে সাহায্য করে।
- Area বের করতে multiplication করা হয়েছে।
- Perimeter-এর formula-তে addition ও multiplication ব্যবহার হয়েছে।
- Positive measurement না হলে error message দেখানো হয়েছে।

## 5. Program 4: Celsius to Fahrenheit Converter

### Objective

Temperature Celsius থেকে Fahrenheit-এ convert করা।

### Formula

\[
F=\frac{9}{5}C+32
\]

এখানে \(C\) হলো Celsius এবং \(F\) হলো Fahrenheit।

### Code

```python
celsius = float(input("Enter temperature in Celsius: "))

fahrenheit = (celsius * 9 / 5) + 32

print(f"Temperature: {fahrenheit:.2f} F")
```

### Sample Input

```text
Enter temperature in Celsius: 25
```

### Output

```text
Temperature: 77.00 F
```

### Explanation

- User Celsius temperature দিয়েছে।
- Formula অনুযায়ী Fahrenheit হিসাব করা হয়েছে।
- f-string দিয়ে result দুই decimal places-এ দেখানো হয়েছে।

**Learning point:** Formula-based program-এ input, calculation এবং formatted output—তিনটি ধাপই গুরুত্বপূর্ণ।

## 6. Program 5: Student Marks and Percentage Calculator

### Objective

প্রাপ্ত নম্বর ও মোট নম্বর থেকে percentage বের করা।

### Formula

\[
\text{Percentage}=\frac{\text{Obtained Marks}}{\text{Total Marks}}\times100
\]

### Code

```python
name = input("Enter student name: ")
obtained = float(input("Enter obtained marks: "))
total = float(input("Enter total marks: "))

if total > 0 and 0 <= obtained <= total:
    percentage = obtained / total

    print("\n--- Student Result ---")
    print(f"Name: {name}")
    print(f"Marks: {obtained:g}/{total:g}")
    print(f"Percentage: {percentage:.2%}")
else:
    print("Invalid marks or total marks.")
```

### Sample Input

```text
Enter student name: Masum
Enter obtained marks: 425
Enter total marks: 500
```

### Output

```text
--- Student Result ---
Name: Masum
Marks: 425/500
Percentage: 85.00%
```

### Explanation

- `total > 0` নিশ্চিত করে মোট নম্বর শূন্য নয়।
- `0 <= obtained <= total` নিশ্চিত করে প্রাপ্ত নম্বর valid range-এ আছে।
- `obtained / total` ratio বের করে।
- `:.2%` ratio-কে percentage হিসেবে দেখায়।

**Learning point:** Percentage format ব্যবহার করার সময় value ratio নাকি ইতোমধ্যে percentage—সেটি বুঝতে হবে।

## 7. Program 6: Shopping Bill Calculator

### Objective

একটি product-এর unit price ও quantity থেকে total bill তৈরি করা।

### Formula

\[
\text{Total Price}=\text{Unit Price}\times\text{Quantity}
\]

### Code

```python
product = input("Enter product name: ")
price = float(input("Enter unit price: "))
quantity = int(input("Enter quantity: "))

if price >= 0 and quantity >= 0:
    total = price * quantity

    print("\n" + "=" * 30)
    print(f"{'SHOPPING BILL':^30}")
    print("=" * 30)
    print(f"{'Product:':<15}{product}")
    print(f"{'Unit Price:':<15}Tk {price:,.2f}")
    print(f"{'Quantity:':<15}{quantity}")
    print("-" * 30)
    print(f"{'Total:':<15}Tk {total:,.2f}")
    print("=" * 30)
else:
    print("Price and quantity cannot be negative.")
```

### Sample Input

```text
Enter product name: Keyboard
Enter unit price: 1250.50
Enter quantity: 2
```

### Output

```text
==============================
         SHOPPING BILL
==============================
Product:       Keyboard
Unit Price:    Tk 1,250.50
Quantity:      2
------------------------------
Total:         Tk 2,501.00
==============================
```

### Explanation

- Product name string হিসেবে নেওয়া হয়েছে।
- Price-এর জন্য `float()` এবং quantity-এর জন্য `int()` ব্যবহার করা হয়েছে।
- `:,.2f` comma separator ও দুই decimal places দেখায়।
- Alignment specification দিয়ে bill-এর layout তৈরি করা হয়েছে।

বাস্তব billing system-এ currency calculation-এর জন্য `Decimal` ব্যবহার করা উপযুক্ত হতে পারে।

## 8. Program 7: Discount Calculator

### Objective

Original price ও discount rate থেকে discount amount এবং final price বের করা।

### Formula

\[
\text{Discount}=\frac{\text{Price}\times\text{Rate}}{100}
\]

\[
\text{Final Price}=\text{Price}-\text{Discount}
\]

### Code

```python
price = float(input("Enter original price: "))
discount_rate = float(input("Enter discount percentage: "))

if price >= 0 and 0 <= discount_rate <= 100:
    discount = price * discount_rate / 100
    final_price = price - discount

    print(f"Original Price: Tk {price:,.2f}")
    print(f"Discount Rate: {discount_rate:.2f}%")
    print(f"Discount Amount: Tk {discount:,.2f}")
    print(f"Final Price: Tk {final_price:,.2f}")
else:
    print("Enter a valid price and discount rate.")
```

### Sample Input

```text
Enter original price: 2500
Enter discount percentage: 15
```

### Output

```text
Original Price: Tk 2,500.00
Discount Rate: 15.00%
Discount Amount: Tk 375.00
Final Price: Tk 2,125.00
```

### Explanation

- Discount rate সরাসরি percentage হিসেবে input নেওয়া হয়েছে।
- তাই হিসাবের সময় rate-কে 100 দিয়ে ভাগ করা হয়েছে।
- `0 <= discount_rate <= 100` দিয়ে rate-এর range যাচাই করা হয়েছে।

## 9. Program 8: Simple Interest Calculator

### Objective

Principal, annual interest rate ও time থেকে simple interest এবং total amount বের করা।

### Formula

\[
SI=\frac{P\times R\times T}{100}
\]

\[
A=P+SI
\]

এখানে:

- \(P\) = Principal
- \(R\) = Annual interest rate in percent
- \(T\) = Time in years
- \(SI\) = Simple interest
- \(A\) = Total amount

### Code

```python
principal = float(input("Enter principal amount: "))
rate = float(input("Enter annual interest rate (%): "))
time = float(input("Enter time in years: "))

if principal >= 0 and rate >= 0 and time >= 0:
    interest = principal * rate * time / 100
    total_amount = principal + interest

    print(f"Principal: Tk {principal:,.2f}")
    print(f"Simple Interest: Tk {interest:,.2f}")
    print(f"Total Amount: Tk {total_amount:,.2f}")
else:
    print("Values cannot be negative.")
```

### Sample Input

```text
Enter principal amount: 10000
Enter annual interest rate (%): 5
Enter time in years: 2
```

### Output

```text
Principal: Tk 10,000.00
Simple Interest: Tk 1,000.00
Total Amount: Tk 11,000.00
```

### Explanation

- Principal, rate ও time input নেওয়া হয়েছে।
- Formula ব্যবহার করে simple interest হিসাব করা হয়েছে।
- Principal ও interest যোগ করে total amount বের করা হয়েছে।

এটি simple-interest calculation; compound interest-এর formula আলাদা।

## 10. Program 9: Time Converter

### Objective

মোট seconds-কে hours, minutes ও seconds-এ convert করা।

### Example

মোট seconds = 3672

- Hours = 1
- Minutes = 1
- Seconds = 12

### Code

```python
total_seconds = int(input("Enter total seconds: "))

if total_seconds >= 0:
    hours = total_seconds // 3600
    remaining_seconds = total_seconds % 3600

    minutes = remaining_seconds // 60
    seconds = remaining_seconds % 60

    print(f"Hours: {hours}")
    print(f"Minutes: {minutes}")
    print(f"Seconds: {seconds}")
else:
    print("Seconds cannot be negative.")
```

### Sample Input

```text
Enter total seconds: 3672
```

### Output

```text
Hours: 1
Minutes: 1
Seconds: 12
```

### Explanation

- `//` integer floor division করে।
- `%` remainder বের করে।
- `3600` seconds = 1 hour।
- `60` seconds = 1 minute।

এটি integer division ও modulo operator-এর practical application।

## 11. Program 10: BMI Calculator

### Objective

Weight ও height থেকে Body Mass Index (BMI) হিসাব করা।

### Formula

\[
BMI=\frac{\text{Weight in kg}}{(\text{Height in metres})^2}
\]

### Code

```python
weight = float(input("Enter weight in kg: "))
height = float(input("Enter height in metres: "))

if weight > 0 and height > 0:
    bmi = weight / (height ** 2)

    print(f"BMI: {bmi:.2f}")
else:
    print("Weight and height must be positive.")
```

### Sample Input

```text
Enter weight in kg: 65
Enter height in metres: 1.70
```

### Output

```text
BMI: 22.49
```

### Explanation

- `weight` ও `height` float হিসেবে নেওয়া হয়েছে।
- `height ** 2` height-এর square বের করেছে।
- Formula অনুযায়ী BMI হিসাব করা হয়েছে।
- Positive input না হলে calculation করা হয়নি।

এই program শুধু BMI-এর numeric value হিসাব করে; এটি নিজে থেকে কোনো medical assessment দেয় না।

## 12. Program 11: Multiple-Subject Average Calculator

### Objective

এক লাইনে একাধিক subject-এর marks নিয়ে average বের করা।

### Code

```python
marks_text = input("Enter marks separated by spaces: ")
parts = marks_text.split()

if len(parts) == 0:
    print("Please enter at least one mark.")
else:
    try:
        marks = list(map(float, parts))

        if any(mark < 0 or mark > 100 for mark in marks):
            print("Each mark must be between 0 and 100.")
        else:
            average = sum(marks) / len(marks)

            print(f"Total Subjects: {len(marks)}")
            print(f"Total Marks: {sum(marks):g}")
            print(f"Average Marks: {average:.2f}")

    except ValueError:
        print("Please enter valid numeric marks.")
```

### Sample Input

```text
Enter marks separated by spaces: 85 90 78 92
```

### Output

```text
Total Subjects: 4
Total Marks: 345
Average Marks: 86.25
```

### Explanation

- `split()` input-কে আলাদা string-এ ভাগ করেছে।
- `map(float, parts)` প্রতিটি mark-কে float-এ convert করেছে।
- `sum()` total marks হিসাব করেছে।
- `len()` subject count বের করেছে।
- `any()` দিয়ে প্রতিটি mark-এর range যাচাই করা হয়েছে।
- `try-except` invalid numeric input handle করেছে।

## 13. Program 12: Simple Input Validation

### Objective

User-এর কাছ থেকে valid positive number না পাওয়া পর্যন্ত input নিতে থাকা।

### Code

```python
while True:
    try:
        number = float(input("Enter a positive number: "))

        if number > 0:
            print(f"Accepted number: {number:g}")
            break

        print("Number must be greater than zero.")

    except ValueError:
        print("Invalid input. Please enter a number.")
```

### Example Interaction

```text
Enter a positive number: abc
Invalid input. Please enter a number.
Enter a positive number: -5
Number must be greater than zero.
Enter a positive number: 12.5
Accepted number: 12.5
```

### Explanation

- `while True` loop input নেওয়া চালিয়ে যায়।
- `try-except` invalid numeric input handle করে।
- `if number > 0` positive value যাচাই করে।
- `break` valid input পাওয়া গেলে loop শেষ করে।

## 14. Program 13: Formatted Student Report

### Objective

একজন student-এর নাম, marks, percentage এবং average সুন্দর report আকারে দেখানো।

### Code

```python
name = input("Enter student name: ")
marks1 = float(input("Enter subject 1 marks: "))
marks2 = float(input("Enter subject 2 marks: "))
marks3 = float(input("Enter subject 3 marks: "))

marks = [marks1, marks2, marks3]

if any(mark < 0 or mark > 100 for mark in marks):
    print("Marks must be between 0 and 100.")
else:
    total = sum(marks)
    average = total / len(marks)
    percentage = total / 300

    print("\n" + "=" * 36)
    print(f"{'STUDENT REPORT':^36}")
    print("=" * 36)
    print(f"{'Name:':<15}{name}")
    print(f"{'Subject 1:':<15}{marks1:g}")
    print(f"{'Subject 2:':<15}{marks2:g}")
    print(f"{'Subject 3:':<15}{marks3:g}")
    print("-" * 36)
    print(f"{'Total Marks:':<15}{total:g}/300")
    print(f"{'Average:':<15}{average:.2f}")
    print(f"{'Percentage:':<15}{percentage:.2%}")
    print("=" * 36)
```

### Sample Input

```text
Enter student name: Masum
Enter subject 1 marks: 85
Enter subject 2 marks: 90
Enter subject 3 marks: 95
```

### Output

```text
====================================
           STUDENT REPORT
====================================
Name:          Masum
Subject 1:     85
Subject 2:     90
Subject 3:     95
------------------------------------
Total Marks:   270/300
Average:       90.00
Percentage:    90.00%
====================================
```

### Explanation

- List-এ subject marks রাখা হয়েছে।
- `sum()` দিয়ে total marks বের করা হয়েছে।
- `len()` দিয়ে subject count বের করা হয়েছে।
- `:.2f` average-কে দুই decimal places-এ দেখিয়েছে।
- `:.2%` ratio-কে percentage-এ দেখিয়েছে।
- Alignment specification দিয়ে report সাজানো হয়েছে।

## 15. Common Mistakes in Practical Programs

### Mistake 1: Forgetting Type Conversion

```python
first = input()
second = input()

print(first + second)
```

`10` এবং `20` input দিলে output হবে `1020`, কারণ দুটি string concatenate হয়েছে।

**Solution:** Numeric calculation-এর জন্য `int()` বা `float()` ব্যবহার করো।

### Mistake 2: Dividing by Zero

```python
# result = total / count
```

যদি `count == 0` হয়, তাহলে `ZeroDivisionError` হবে।

**Solution:** Division-এর আগে divisor zero কি না check করো।

### Mistake 3: Invalid Input

```python
# age = int(input())
```

User `abc` দিলে `ValueError` হবে।

**Solution:** প্রয়োজন অনুযায়ী `try-except ValueError` ব্যবহার করো।

### Mistake 4: Incorrect Percentage Formula

যদি `percentage = 85` হয়, তাহলে `f"{percentage:.2%}"` output দেবে `8500.00%`।

**Solution:** Value ratio হলে `.2%` ব্যবহার করো; value ইতোমধ্যে percentage হলে `:.2f}%` ব্যবহার করতে পারো।

### Mistake 5: Invalid Range

শুধু numeric input হলেই তা valid input হয় না। যেমন, marks `150` হতে পারে numeric, কিন্তু 100-এর মধ্যে marks-এর ক্ষেত্রে এটি invalid।

**Solution:** Type validation-এর পাশাপাশি range validation করো।

## 16. Practice Exercises

নিজে code লেখার চেষ্টা করো। প্রয়োজনে আগের sections-এর examples দেখে নিতে পারো।

### Exercise 1: Age Calculator

User-এর বয়স input নিয়ে 5 বছর পর তার বয়স কত হবে, তা দেখাও।

### Exercise 2: Circle Calculator

Radius input নিয়ে circle-এর area ও circumference বের করো।

Formula:

\[
Area=\pi r^2
\]

\[
Circumference=2\pi r
\]

Hint: `import math` এবং `math.pi` ব্যবহার করো।

### Exercise 3: Temperature Converter

Celsius input নিয়ে Fahrenheit এবং Kelvin—দুটিতে convert করো।

Formula:

\[
F=\frac{9}{5}C+32
\]

\[
K=C+273.15
\]

### Exercise 4: Electricity Bill

Units consumed এবং প্রতি unit-এর rate input নিয়ে total bill হিসাব করো।

### Exercise 5: Shopping Discount

Original price ও discount percentage input নিয়ে discount amount এবং final price দেখাও।

### Exercise 6: Time Converter

মোট minutes input নিয়ে hours ও remaining minutes দেখাও।

### Exercise 7: Student Average

পাঁচটি subject-এর marks input নিয়ে total, average এবং percentage বের করো।

### Exercise 8: Currency Display

একটি amount input নিয়ে comma separator এবং দুই decimal places-সহ দেখাও।

### Exercise 9: Input Validation

একটি positive integer না পাওয়া পর্যন্ত input নিতে থাকো। Invalid input ও non-positive number handle করো।

### Exercise 10: Mini Project — Shopping Receipt

একাধিক product-এর নাম, unit price এবং quantity নিয়ে প্রতিটি product-এর subtotal ও final bill দেখাও।

## 17. Practice Answer Key

### Answer 1: Age Calculator

```python
age = int(input("Enter your age: "))

if age >= 0:
    print(f"Age after 5 years: {age + 5}")
else:
    print("Age cannot be negative.")
```

### Answer 2: Circle Calculator

```python
import math

radius = float(input("Enter radius: "))

if radius > 0:
    area = math.pi * radius ** 2
    circumference = 2 * math.pi * radius

    print(f"Area: {area:.2f}")
    print(f"Circumference: {circumference:.2f}")
else:
    print("Radius must be positive.")
```

### Answer 3: Temperature Converter

```python
celsius = float(input("Enter Celsius: "))

fahrenheit = (celsius * 9 / 5) + 32
kelvin = celsius + 273.15

print(f"Fahrenheit: {fahrenheit:.2f} F")
print(f"Kelvin: {kelvin:.2f} K")
```

### Answer 4: Electricity Bill

```python
units = float(input("Enter units consumed: "))
rate = float(input("Enter rate per unit: "))

if units >= 0 and rate >= 0:
    bill = units * rate
    print(f"Electricity Bill: Tk {bill:,.2f}")
else:
    print("Units and rate cannot be negative.")
```

এটি একটি basic flat-rate calculation। বাস্তব electricity bill-এ slab rate, fixed charge বা tax থাকতে পারে।

### Answer 5: Shopping Discount

```python
price = float(input("Enter price: "))
discount_rate = float(input("Enter discount percentage: "))

if price >= 0 and 0 <= discount_rate <= 100:
    discount = price * discount_rate / 100
    final_price = price - discount

    print(f"Discount: Tk {discount:,.2f}")
    print(f"Final Price: Tk {final_price:,.2f}")
else:
    print("Invalid price or discount rate.")
```

### Answer 6: Time Converter

```python
total_minutes = int(input("Enter total minutes: "))

if total_minutes >= 0:
    hours = total_minutes // 60
    minutes = total_minutes % 60

    print(f"Hours: {hours}")
    print(f"Minutes: {minutes}")
else:
    print("Minutes cannot be negative.")
```

### Answer 7: Student Average

```python
marks = []

for i in range(5):
    mark = float(input(f"Enter subject {i + 1} marks: "))
    marks.append(mark)

if any(mark < 0 or mark > 100 for mark in marks):
    print("Each mark must be between 0 and 100.")
else:
    total = sum(marks)
    average = total / len(marks)
    percentage = total / 500

    print(f"Total: {total:g}/500")
    print(f"Average: {average:.2f}")
    print(f"Percentage: {percentage:.2%}")
```

### Answer 8: Currency Display

```python
amount = float(input("Enter amount: "))

print(f"Amount: Tk {amount:,.2f}")
```

### Answer 9: Input Validation

```python
while True:
    try:
        number = int(input("Enter a positive integer: "))

        if number > 0:
            print(f"Accepted: {number}")
            break

        print("Number must be greater than zero.")

    except ValueError:
        print("Please enter a valid integer.")
```

### Answer 10: Mini Project — Shopping Receipt

```python
product_count = int(input("How many products? "))

if product_count <= 0:
    print("Enter at least one product.")
else:
    total_bill = 0

    print("\n" + "=" * 38)
    print(f"{'SHOPPING RECEIPT':^38}")
    print("=" * 38)

    for i in range(product_count):
        print(f"\nProduct {i + 1}")

        name = input("Product name: ")
        price = float(input("Unit price: "))
        quantity = int(input("Quantity: "))

        if price < 0 or quantity < 0:
            print("Price and quantity cannot be negative.")
            continue

        subtotal = price * quantity
        total_bill += subtotal

        print(f"{name}: Tk {subtotal:,.2f}")

    print("-" * 38)
    print(f"{'Total Bill:':<18}Tk {total_bill:,.2f}")
    print("=" * 38)
```

**Note:** এটি একটি basic practice program। Production billing system-এ input validation, empty product handling এবং monetary precision আরও শক্তভাবে implement করা উচিত।

## 18. Chapter Summary

- `input()` দিয়ে user-এর কাছ থেকে data নেওয়া যায়।
- `int()` ও `float()` দিয়ে numeric input convert করা যায়।
- `print()` ও f-string দিয়ে পরিষ্কার output তৈরি করা যায়।
- Arithmetic operators ব্যবহার করে practical calculation করা যায়।
- `if-else` দিয়ে invalid range ও zero divisor check করা যায়।
- `try-except` দিয়ে invalid numeric input handle করা যায়।
- `split()`, `map()`, `sum()` ও `len()` multiple input নিয়ে কাজ করতে সাহায্য করে।
- `:,`, `:.2f` ও `:.2%` দিয়ে number ও percentage format করা যায়।
- `while` loop দিয়ে বারবার input নিয়ে validation করা যায়।
- ছোট ছোট program practice করলে Python-এর basic concepts আরও ভালোভাবে আয়ত্ত করা যায়।

## 19. Self-Assessment Checklist

- [ ] User input নিয়ে সঠিক data type-এ convert করতে পারি।
- [ ] Basic calculator তৈরি করতে পারি।
- [ ] Formula ব্যবহার করে calculation করতে পারি।
- [ ] Percentage, currency ও large numbers format করতে পারি।
- [ ] Invalid input এবং invalid range check করতে পারি।
- [ ] `try-except` দিয়ে conversion error handle করতে পারি।
- [ ] Multiple values নিয়ে average বের করতে পারি।
- [ ] Formatted report বা receipt তৈরি করতে পারি।
- [ ] নিজে একটি ছোট input-output project তৈরি করতে পারি।

**Next Topic:** `27_Chapter_Practice_and_Self_Assessment.md` — এখানে Chapter 05-এর সব topic নিয়ে final practice, output prediction, debugging exercise এবং self-assessment থাকবে।