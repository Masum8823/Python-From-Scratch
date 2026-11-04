# 12. Taking Integer and Float Input

## 1. Introduction

Python-এ user-এর কাছ থেকে number নেওয়ার জন্য সাধারণত `input()` ব্যবহার করা হয়। কিন্তু `input()` সবসময় string return করে। তাই number নিয়ে calculation করতে চাইলে প্রয়োজন অনুযায়ী `int()` অথবা `float()` ব্যবহার করতে হয়।

Python-এ numeric input নেওয়ার জন্য প্রধানত দুটি conversion function গুরুত্বপূর্ণ:

- `int()` — integer বা পূর্ণসংখ্যার জন্য।
- `float()` — floating-point বা decimal number-এর জন্য।

### Example

```python
age = int(input("Enter your age: "))
price = float(input("Enter product price: "))

print("Age:", age)
print("Price:", price)
```

Sample Interaction:

```text
Enter your age: 22
Enter product price: 99.50
Age: 22
Price: 99.5
```

এখানে `age` integer এবং `price` float হিসেবে সংরক্ষিত হয়েছে।

## 2. Taking Integer Input with `int()`

Integer হলো পূর্ণসংখ্যা, যেমন `5`, `10`, `0`, `-7`।

User-এর কাছ থেকে integer নিতে সাধারণত নিচের syntax ব্যবহার করা হয়:

```python
variable = int(input("Enter an integer: "))
```

### Example 1: Taking a Number

```python
number = int(input("Enter a number: "))

print("Number:", number)
print("Type:", type(number))
```

Sample Interaction:

```text
Enter a number: 25
Number: 25
Type: <class 'int'>
```

### Example 2: Taking Age

```python
age = int(input("Enter your age: "))

print("Your age is:", age)
```

Sample Interaction:

```text
Enter your age: 21
Your age is: 21
```

### Example 3: Taking Quantity

```python
quantity = int(input("Enter product quantity: "))

print("Quantity:", quantity)
```

Sample Interaction:

```text
Enter product quantity: 5
Quantity: 5
```

Quantity সাধারণত পূর্ণসংখ্যা হয়, তাই এখানে `int()` উপযুক্ত।

**মনে রাখবে:** `int(input())` ব্যবহার করলে user-কে এমন input দিতে হবে, যা integer-এ convert করা যায়। যেমন `25` গ্রহণযোগ্য, কিন্তু `25.5` সরাসরি integer-এ convert করা যায় না।

## 3. Taking Float Input with `float()`

Float হলো এমন numeric type, যা দশমিক মানসহ সংখ্যা প্রকাশ করতে পারে।

উদাহরণ:

- `10.5`
- `99.99`
- `0.75`
- `-3.25`

User-এর কাছ থেকে float নিতে নিচের syntax ব্যবহার করা হয়:

```python
variable = float(input("Enter a decimal number: "))
```

### Example 1: Taking a Decimal Number

```python
number = float(input("Enter a number: "))

print("Number:", number)
print("Type:", type(number))
```

Sample Interaction:

```text
Enter a number: 12.5
Number: 12.5
Type: <class 'float'>
```

### Example 2: Taking Product Price

```python
price = float(input("Enter product price: "))

print("Product price:", price)
```

Sample Interaction:

```text
Enter product price: 150.75
Product price: 150.75
```

### Example 3: Taking Temperature

```python
temperature = float(input("Enter temperature: "))

print("Temperature:", temperature)
```

Sample Interaction:

```text
Enter temperature: 36.5
Temperature: 36.5
```

**মনে রাখবে:** `float()` দিয়ে পূর্ণসংখ্যার মতো input দিলেও float value তৈরি হয়। যেমন `float("10")`-এর ফল `10.0`।

## 4. Difference Between `int()` and `float()`

| বিষয় | `int()` | `float()` |
|---|---|---|
| Data type | `int` | `float` |
| সাধারণ ব্যবহার | পূর্ণসংখ্যা | Decimal-সহ সংখ্যা |
| Example input | `25` | `25.75` |
| Conversion result | `int("25")` → `25` | `float("25.75")` → `25.75` |
| Integer text | `"10"` গ্রহণ করে | `"10"` গ্রহণ করে |
| Decimal text | `"10.5"` সরাসরি গ্রহণ করে না | `"10.5"` গ্রহণ করে |

### Example

```python
a = int(input("Enter an integer: "))
b = float(input("Enter a decimal number: "))

print(a, type(a))
print(b, type(b))
```

Sample Interaction:

```text
Enter an integer: 10
Enter a decimal number: 10.5
10 <class 'int'>
10.5 <class 'float'>
```

## 5. Understanding `int()` with Decimal Values

একটি গুরুত্বপূর্ণ বিষয় হলো, `int()` ব্যবহার করে decimal text সরাসরি integer-এ convert করা যায় না।

### Example 1: Invalid Conversion

```python
number = int("12.5")
```

এতে `ValueError` হবে।

কারণ `"12.5"` একটি decimal number-এর text representation, integer-এর নয়।

### Example 2: Converting a Float to Integer

```python
number = int(12.9)

print(number)
```

Output:

```text
12
```

এখানে `int()` decimal অংশ বাদ দিয়েছে। এটি সাধারণ rounding নয়।

আরও উদাহরণ:

```python
print(int(12.9))
print(int(12.1))
print(int(-12.9))
```

Output:

```text
12
12
-12
```

`int()` এখানে শূন্যের দিকে truncate করে; নিকটতম পূর্ণসংখ্যায় round করে না।

যদি decimal value প্রয়োজন হয়, তাহলে `float()` ব্যবহার করাই উপযুক্ত।

## 6. Taking Two Integer Inputs

দুটি integer নিয়ে arithmetic operation করা খুব সাধারণ একটি কাজ।

### Example: Addition

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

total = a + b

print("Total:", total)
```

Sample Interaction:

```text
Enter first number: 15
Enter second number: 25
Total: 40
```

### Example: Subtraction

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

result = a - b

print("Difference:", result)
```

Sample Interaction:

```text
Enter first number: 30
Enter second number: 12
Difference: 18
```

### Example: Multiplication

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

result = a * b

print("Product:", result)
```

Sample Interaction:

```text
Enter first number: 6
Enter second number: 7
Product: 42
```

## 7. Taking Two Float Inputs

Decimal value নিয়ে calculation করার জন্য `float()` ব্যবহার করা যায়।

### Example: Addition

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

total = a + b

print("Total:", total)
```

Sample Interaction:

```text
Enter first number: 12.5
Enter second number: 7.25
Total: 19.75
```

### Example: Average

```python
mark1 = float(input("Enter first mark: "))
mark2 = float(input("Enter second mark: "))

average = (mark1 + mark2) / 2

print("Average:", average)
```

Sample Interaction:

```text
Enter first mark: 80
Enter second mark: 91
Average: 85.5
```

এখানে পূর্ণসংখ্যার মতো marks দিলেও `float()` ব্যবহার করার কারণে values float হয়েছে।

## 8. Taking Integer and Float Inputs Together

একটি program-এ integer ও float—দুই ধরনের input নেওয়া যায়।

### Example: Shopping Bill

```python
quantity = int(input("Enter quantity: "))
price = float(input("Enter unit price: "))

total = quantity * price

print("Quantity:", quantity)
print("Unit Price:", price)
print("Total Bill:", total)
```

Sample Interaction:

```text
Enter quantity: 3
Enter unit price: 49.50
Quantity: 3
Unit Price: 49.5
Total Bill: 148.5
```

এখানে:

- `quantity` হলো integer।
- `price` হলো float।
- `total` হলো float, কারণ integer ও float গুণ করলে ফল সাধারণত float হয়।

### আরেকটি উদাহরণ: Distance and Time

```python
distance = float(input("Enter distance in kilometers: "))
time = float(input("Enter time in hours: "))

if time > 0:
    speed = distance / time
    print("Speed:", speed, "km/h")
else:
    print("Time must be greater than zero.")
```

Sample Interaction:

```text
Enter distance in kilometers: 120
Enter time in hours: 2.5
Speed: 48.0 km/h
```

এখানে distance ও time-এর জন্য float নেওয়া হয়েছে, কারণ এগুলোতে decimal value থাকতে পারে।

## 9. Taking Multiple Numeric Inputs

একাধিক numeric input আলাদা লাইনে নেওয়া যায়।

### Example: Three Integer Inputs

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))
c = int(input("Enter third number: "))

total = a + b + c

print("Total:", total)
```

Sample Interaction:

```text
Enter first number: 10
Enter second number: 20
Enter third number: 30
Total: 60
```

### Example: Three Float Inputs

```python
a = float(input("Enter first value: "))
b = float(input("Enter second value: "))
c = float(input("Enter third value: "))

average = (a + b + c) / 3

print("Average:", average)
```

Sample Interaction:

```text
Enter first value: 10.5
Enter second value: 20.5
Enter third value: 30.5
Average: 20.5
```

এখানে তিনটি float value-এর average বের করা হয়েছে।

## 10. Common Errors and Solutions

### Error 1: Entering Decimal Text into `int()`

```python
age = int(input("Enter a number: "))
```

যদি user `12.5` লেখে, তাহলে `ValueError` হবে।

**Solution:** Decimal input গ্রহণ করতে চাইলে `float()` ব্যবহার করো।

```python
number = float(input("Enter a number: "))
```

### Error 2: Entering Text Instead of a Number

```python
number = int(input("Enter a number: "))
```

User `hello` লিখলে `ValueError` হবে।

কারণ `"hello"` integer-এ convert করা যায় না।

### Error 3: Empty Input

```python
number = float(input("Enter a number: "))
```

User কিছু না লিখে Enter চাপলে `ValueError` হবে, কারণ empty string-কে float-এ convert করা যায় না।

### Error 4: Dividing by Zero

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

print(a / b)
```

User দ্বিতীয় সংখ্যাটি `0` দিলে `ZeroDivisionError` হবে।

**Solution:**

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

if b != 0:
    print("Result:", a / b)
else:
    print("Cannot divide by zero.")
```

### Error 5: Assuming `int()` Rounds a Number

```python
print(int(9.8))
```

Output হবে `9`, `10` নয়।

কারণ `int()` decimal অংশ বাদ দেয়।

## 11. Practical Programs

### Program 1: Calculate the Sum of Two Numbers

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

sum_result = a + b

print("Sum:", sum_result)
```

### Program 2: Calculate Rectangle Area

```python
length = float(input("Enter length: "))
width = float(input("Enter width: "))

area = length * width

print("Area:", area)
```

Sample Interaction:

```text
Enter length: 5.5
Enter width: 3
Area: 16.5
```

### Program 3: Calculate Average Marks

```python
mark1 = float(input("Enter first subject marks: "))
mark2 = float(input("Enter second subject marks: "))
mark3 = float(input("Enter third subject marks: "))

total = mark1 + mark2 + mark3
average = total / 3

print("Total Marks:", total)
print("Average Marks:", average)
```

### Program 4: Calculate Discounted Price

```python
price = float(input("Enter original price: "))
discount = float(input("Enter discount percentage: "))

discount_amount = price * discount / 100
final_price = price - discount_amount

print("Discount Amount:", discount_amount)
print("Final Price:", final_price)
```

Sample Interaction:

```text
Enter original price: 1000
Enter discount percentage: 10
Discount Amount: 100.0
Final Price: 900.0
```

### Program 5: Convert Minutes into Hours and Minutes

```python
total_minutes = int(input("Enter total minutes: "))

hours = total_minutes // 60
minutes = total_minutes % 60

print("Hours:", hours)
print("Minutes:", minutes)
```

Sample Interaction:

```text
Enter total minutes: 135
Hours: 2
Minutes: 15
```

এখানে `//` দিয়ে পূর্ণ ঘণ্টা এবং `%` দিয়ে অবশিষ্ট মিনিট বের করা হয়েছে।

## 12. Best Practices

1. পূর্ণসংখ্যার input-এর জন্য `int()` ব্যবহার করো।
2. Decimal input-এর জন্য `float()` ব্যবহার করো।
3. User কী ধরনের input দেবে, তা আগে নির্ধারণ করো।
4. `int()` decimal text সরাসরি convert করতে পারে না—এটি মনে রাখো।
5. Division করার আগে divisor শূন্য কি না, পরীক্ষা করো।
6. User-এর ভুল input সামলানোর জন্য পরবর্তী সময়ে exception handling শিখবে।
7. Money-related হিসাবের ক্ষেত্রে floating-point precision-এর সীমাবদ্ধতা মাথায় রাখো। নির্ভুল আর্থিক হিসাবের জন্য Python-এর `decimal.Decimal` উপযোগী হতে পারে।

## 13. Practice Exercises

### Exercise 1: Integer Input

User-এর কাছ থেকে একটি integer নাও এবং তার বর্গফল print করো।

### Exercise 2: Float Input

User-এর কাছ থেকে একটি decimal number নাও এবং সেটিকে `3` দিয়ে গুণ করো।

### Exercise 3: Addition

দুটি integer input নিয়ে তাদের যোগফল বের করো।

### Exercise 4: Average

তিনটি float input নিয়ে তাদের average বের করো।

### Exercise 5: Shopping Bill

User-এর কাছ থেকে quantity এবং unit price নাও। Total bill হিসাব করো।

### Exercise 6: Temperature

Celsius temperature input নিয়ে Fahrenheit-এ convert করো।

Formula:

`Fahrenheit = (Celsius × 9 / 5) + 32`

### Exercise 7: Division

দুটি float input নাও। দ্বিতীয় সংখ্যা শূন্য না হলে ভাগফল দেখাও; অন্যথায় উপযুক্ত message দেখাও।

### Exercise 8: Discount

Original price এবং discount percentage input নিয়ে final price হিসাব করো।

### Exercise 9: Time Conversion

মোট সেকেন্ড input নিয়ে কত ঘণ্টা, মিনিট এবং সেকেন্ড হয়, তা বের করো।

### Exercise 10: Challenge Program

একজন শিক্ষার্থীর পাঁচটি subject-এর marks input নাও। Total এবং average বের করো। Average `40` বা তার বেশি হলে `Pass`, অন্যথায় `Fail` দেখাও।

## 14. Practice Answer Key

### Answer 1

```python
number = int(input("Enter an integer: "))

print("Square:", number ** 2)
```

### Answer 2

```python
number = float(input("Enter a decimal number: "))

print("Result:", number * 3)
```

### Answer 3

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print("Sum:", a + b)
```

### Answer 4

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))
c = float(input("Enter third number: "))

print("Average:", (a + b + c) / 3)
```

### Answer 5

```python
quantity = int(input("Enter quantity: "))
price = float(input("Enter unit price: "))

print("Total Bill:", quantity * price)
```

### Answer 6

```python
celsius = float(input("Enter temperature in Celsius: "))

fahrenheit = (celsius * 9 / 5) + 32

print("Fahrenheit:", fahrenheit)
```

### Answer 7

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

if b != 0:
    print("Quotient:", a / b)
else:
    print("Cannot divide by zero.")
```

### Answer 8

```python
price = float(input("Enter original price: "))
discount = float(input("Enter discount percentage: "))

final_price = price - (price * discount / 100)

print("Final Price:", final_price)
```

### Answer 9

```python
total_seconds = int(input("Enter total seconds: "))

hours = total_seconds // 3600
remaining_seconds = total_seconds % 3600

minutes = remaining_seconds // 60
seconds = remaining_seconds % 60

print("Hours:", hours)
print("Minutes:", minutes)
print("Seconds:", seconds)
```

### Answer 10

```python
mark1 = float(input("Enter subject 1 marks: "))
mark2 = float(input("Enter subject 2 marks: "))
mark3 = float(input("Enter subject 3 marks: "))
mark4 = float(input("Enter subject 4 marks: "))
mark5 = float(input("Enter subject 5 marks: "))

total = mark1 + mark2 + mark3 + mark4 + mark5
average = total / 5

print("Total Marks:", total)
print("Average Marks:", average)

if average >= 40:
    print("Pass")
else:
    print("Fail")
```

এই শেষ উদাহরণে কেবল average-এর ভিত্তিতে Pass/Fail নির্ধারণ করা হয়েছে। বাস্তবে প্রতিটি subject-এ আলাদা pass mark থাকলে সেই নিয়মও পরীক্ষা করতে হবে।

## 15. Chapter Summary

- `input()` string return করে।
- `int(input())` দিয়ে integer input নেওয়া যায়।
- `float(input())` দিয়ে float input নেওয়া যায়।
- `int()` decimal অংশ বাদ দেয়; এটি rounding করে না।
- `float()` পূর্ণসংখ্যার মতো input-কেও float-এ convert করে।
- Invalid input দিলে `ValueError` হতে পারে।
- শূন্য দিয়ে ভাগ করলে `ZeroDivisionError` হতে পারে।
- Integer ও float input ব্যবহার করে calculator, average, bill, discount এবং unit conversion-এর মতো program তৈরি করা যায়।

## 16. Self-Assessment Checklist

- [ ] `int(input())` ব্যবহার করে integer input নিতে পারি।
- [ ] `float(input())` ব্যবহার করে decimal input নিতে পারি।
- [ ] Integer ও float-এর পার্থক্য বুঝি।
- [ ] `int()` কেন decimal অংশ বাদ দেয়, তা বুঝি।
- [ ] একাধিক numeric input নিয়ে calculation করতে পারি।
- [ ] Invalid input ও division by zero-এর সমস্যা শনাক্ত করতে পারি।
- [ ] বাস্তব সমস্যার জন্য ছোট numeric program লিখতে পারি।

**Next Topic:** `13_Taking_Multiple_Inputs.md` — এখানে একই লাইনে বা আলাদা লাইনে একাধিক input নেওয়ার পদ্ধতি শিখব।