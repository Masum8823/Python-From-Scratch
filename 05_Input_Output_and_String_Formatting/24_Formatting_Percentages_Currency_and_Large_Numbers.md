# 24. Formatting Percentages, Currency and Large Numbers in Python

## 1. Introduction

Python-এ কোনো number হিসাব করার পর সেটিকে user-friendly format-এ দেখানো গুরুত্বপূর্ণ।

যেমন:

```python
price = 1250.5
percentage = 0.875
population = 2500000

print(price)
print(percentage)
print(population)
```

Output:

```text
1250.5
0.875
2500000
```

এই output সঠিক হলেও ব্যবহারকারীর জন্য আরও পরিষ্কারভাবে দেখানো যায়:

```text
Price: Tk 1,250.50
Percentage: 87.50%
Population: 2,500,000
```

এই topic-এ আমরা শিখব:

- Percentage formatting
- Currency formatting
- Large number formatting
- Decimal places ও rounding
- Practical billing ও result calculation
- Formatting-এর সাধারণ ভুল

## 2. Formatting Percentages

Percentage হলো কোনো value-কে 100-এর ভিত্তিতে প্রকাশ করার পদ্ধতি।

Percentage হিসাব করার formula:

\[
\text{Percentage}=\frac{\text{Obtained Value}}{\text{Total Value}}\times100
\]

### Example 1: Calculate Percentage

```python
obtained = 425
total = 500

percentage = (obtained / total) * 100

print(percentage)
```

Output:

```text
85.0
```

এখানে percentage হিসাব করা হয়েছে, কিন্তু `%` চিহ্ন যোগ করা হয়নি।

### Example 2: Display Percentage

```python
obtained = 425
total = 500

percentage = (obtained / total) * 100

print(f"Percentage: {percentage:.2f}%")
```

Output:

```text
Percentage: 85.00%
```

এখানে:

- `:.2f` দুই decimal places দেখায়।
- শেষে `%` একটি সাধারণ character হিসেবে লেখা হয়েছে।
- `percentage`-এর value পরিবর্তন হয়নি।

## 3. Percentage Formatting Using f-Strings

f-string-এর format specification-এ `%` ব্যবহার করলে Python value-কে 100 দিয়ে গুণ করে percentage হিসেবে দেখায়।

### Example 1: Basic Percentage

```python
score = 0.85

print(f"{score:.2%}")
```

Output:

```text
85.00%
```

এখানে `0.85` হলো ratio, অর্থাৎ 85%।

### Example 2: Different Precision

```python
score = 0.85678

print(f"{score:.0%}")
print(f"{score:.1%}")
print(f"{score:.2%}")
```

Output:

```text
86%
85.7%
85.68%
```

এখানে precision পরিবর্তনের মাধ্যমে দশমিকের পর কতটি digit থাকবে তা নিয়ন্ত্রণ করা হয়েছে।

### Important Difference

```python
score = 85

print(f"{score:.2f}%")
print(f"{score:.2%}")
```

Output:

```text
85.00%
8500.00%
```

প্রথম লাইনে `85`-কে decimal format করে `%` character যোগ করা হয়েছে। দ্বিতীয় লাইনে Python `85`-কে 100 দিয়ে গুণ করেছে।

**মনে রাখবে:**

- Value যদি `85` হয় এবং সেটি ইতোমধ্যে percentage হয়, তাহলে `f"{score:.2f}%"` ব্যবহার করতে পারো।
- Value যদি `0.85`-এর মতো ratio হয়, তাহলে `f"{score:.2%}"` ব্যবহার করো।

## 4. Percentage Calculation in Practical Programs

### Example: Student Result

```python
name = "Masum"
obtained_marks = 425
total_marks = 500

if total_marks > 0 and 0 <= obtained_marks <= total_marks:
    percentage = obtained_marks / total_marks

    print(f"Student: {name}")
    print(f"Marks: {obtained_marks}/{total_marks}")
    print(f"Percentage: {percentage:.2%}")
else:
    print("Invalid marks or total marks.")
```

Output:

```text
Student: Masum
Marks: 425/500
Percentage: 85.00%
```

এখানে ratio হিসেবে `obtained_marks / total_marks` হিসাব করা হয়েছে। তাই percentage দেখানোর জন্য `.2%` ব্যবহার করা হয়েছে।

## 5. Formatting Currency

Currency হলো টাকা, ডলার বা অন্য কোনো দেশের আর্থিক একক।

Python-এর f-string নিজে থেকে কোনো currency symbol যোগ করে না। প্রয়োজন অনুযায়ী `Tk`, `$`, `€` বা অন্য symbol লিখতে হয়।

### Example 1: Bangladeshi Taka

```python
price = 1250.5

print(f"Price: Tk {price:.2f}")
```

Output:

```text
Price: Tk 1250.50
```

### Example 2: Dollar

```python
price = 49.9

print(f"Price: ${price:.2f}")
```

Output:

```text
Price: $49.90
```

### Example 3: Euro

```python
price = 79.5

print(f"Price: €{price:.2f}")
```

Output:

```text
Price: €79.50
```

এখানে currency symbol বা label সাধারণ text হিসেবে যোগ করা হয়েছে।

**Note:** বাস্তব financial application-এ currency-এর locale, symbol placement এবং decimal rules দেশভেদে আলাদা হতে পারে।

## 6. Adding Thousand Separators to Currency

বড় amount-এর মধ্যে comma ব্যবহার করলে পড়তে সুবিধা হয়।

### Example

```python
price = 1250000.5

print(f"Price: Tk {price:,.2f}")
```

Output:

```text
Price: Tk 1,250,000.50
```

এখানে:

- `,` thousand separator যোগ করে।
- `.2f` দুই decimal places দেখায়।
- `Tk` currency label হিসেবে ব্যবহৃত হয়েছে।

### Another Example

```python
salary = 45000

print(f"Monthly Salary: Tk {salary:,.2f}")
```

Output:

```text
Monthly Salary: Tk 45,000.00
```

এভাবে salary, product price, invoice amount এবং report-এর value format করা যায়।

## 7. Formatting Large Integers

বড় integer সাধারণত comma separator দিয়ে display করা হয়।

### Example

```python
population = 170000000

print(f"Population: {population:,}")
```

Output:

```text
Population: 170,000,000
```

### More Examples

```python
print(f"{1000:,}")
print(f"{1000000:,}")
print(f"{2500000000:,}")
```

Output:

```text
1,000
1,000,000
2,500,000,000
```

কমা শুধু output-এর representation-এ যোগ হয়েছে। মূল integer পরিবর্তন হয়নি।

## 8. Formatting Large Floating-Point Numbers

বড় floating-point number-এর ক্ষেত্রেও comma ও decimal precision একসঙ্গে ব্যবহার করা যায়।

### Example

```python
amount = 1234567890.5678

print(f"{amount:,.2f}")
```

Output:

```text
1,234,567,890.57
```

### Example with Label

```python
company_revenue = 987654321.456

print(f"Revenue: Tk {company_revenue:,.2f}")
```

Output:

```text
Revenue: Tk 987,654,321.46
```

এই format financial summary বা sales report-এ ব্যবহার করা যায়।

## 9. Choosing the Correct Decimal Places

সব number-এর জন্য একই precision প্রয়োজন হয় না।

| Value | Suggested display | Example output |
|---|---|---|
| Student percentage | 2 decimal places | `85.50%` |
| Product price | 2 decimal places | `Tk 125.50` |
| Large population | No decimal places | `170,000,000` |
| Scientific measurement | Requirement অনুযায়ী | `12.346` |
| Average marks | 2 decimal places | `88.75` |

এগুলো সাধারণ উদাহরণ; বাস্তব project-এ প্রয়োজন অনুযায়ী precision নির্বাচন করতে হবে।

### Example

```python
average = 87.4567
population = 170000000

print(f"Average: {average:.2f}")
print(f"Population: {population:,}")
```

Output:

```text
Average: 87.46
Population: 170,000,000
```

## 10. Understanding Rounding

Fixed decimal places-এ number format করলে displayed result round হতে পারে।

### Example

```python
number = 12.3456

print(f"{number:.2f}")
print(f"{number:.3f}")
```

Output:

```text
12.35
12.346
```

এখানে original variable `number` পরিবর্তিত হয়নি। শুধু display-তে rounded representation দেখানো হয়েছে।

### Check the Original Value

```python
number = 12.3456

print(f"Formatted: {number:.2f}")
print(f"Original: {number}")
```

Output:

```text
Formatted: 12.35
Original: 12.3456
```

**Important:** Floating-point number-এর binary representation-এর কারণে কিছু decimal value-তে rounding প্রত্যাশার চেয়ে আলাদা মনে হতে পারে। Exact decimal arithmetic প্রয়োজন হলে `decimal.Decimal` বিবেচনা করো।

## 11. Currency and Financial Accuracy

সাধারণ শেখার program-এ `float` দিয়ে price হিসাব করা যায়। তবে financial application-এ `float` ব্যবহার করলে binary floating-point precision issue দেখা দিতে পারে।

### Example of Float Limitation

```python
print(0.1 + 0.2)
```

Output:

```text
0.30000000000000004
```

এই কারণেই exact decimal arithmetic প্রয়োজন হলে `Decimal` ব্যবহার করা উপকারী।

### Using Decimal

```python
from decimal import Decimal

price = Decimal("19.99")
quantity = Decimal("3")

total = price * quantity

print(f"Total: Tk {total:.2f}")
```

Output:

```text
Total: Tk 59.97
```

এখানে decimal value string থেকে তৈরি করা হয়েছে, যাতে binary float থেকে আসা approximation এড়ানো যায়।

**Best practice:** Financial calculation-এ প্রয়োজন অনুযায়ী `Decimal` ব্যবহার করো এবং rounding-এর নিয়ম স্পষ্টভাবে নির্ধারণ করো।

## 12. Practical Program: Product Bill

```python
product_name = "Keyboard"
unit_price = 1250.50
quantity = 2

total = unit_price * quantity

print("=" * 35)
print(f"{'PRODUCT BILL':^35}")
print("=" * 35)
print(f"{'Product:':<15}{product_name}")
print(f"{'Unit Price:':<15}Tk {unit_price:,.2f}")
print(f"{'Quantity:':<15}{quantity}")
print("-" * 35)
print(f"{'Total:':<15}Tk {total:,.2f}")
print("=" * 35)
```

Output:

```text
===================================
           PRODUCT BILL
===================================
Product:       Keyboard
Unit Price:    Tk 1,250.50
Quantity:      2
-----------------------------------
Total:         Tk 2,501.00
===================================
```

এই program-এ product name, unit price, quantity ও total price সুন্দরভাবে দেখানো হয়েছে।

## 13. Practical Program: Discount Calculation

Discount-এর amount এবং final price বের করতে percentage ব্যবহার করা যায়।

### Formula

\[
\text{Discount}=\text{Original Price}\times\frac{\text{Discount Rate}}{100}
\]

\[
\text{Final Price}=\text{Original Price}-\text{Discount}
\]

### Example

```python
original_price = 2500.00
discount_rate = 15.0

discount_amount = original_price * discount_rate / 100
final_price = original_price - discount_amount

print(f"Original Price: Tk {original_price:,.2f}")
print(f"Discount Rate: {discount_rate:.2f}%")
print(f"Discount Amount: Tk {discount_amount:,.2f}")
print(f"Final Price: Tk {final_price:,.2f}")
```

Output:

```text
Original Price: Tk 2,500.00
Discount Rate: 15.00%
Discount Amount: Tk 375.00
Final Price: Tk 2,125.00
```

এখানে `discount_rate` ইতোমধ্যে percentage হিসেবে আছে, তাই সেটিকে আবার 100 দিয়ে গুণ করা হয়নি। বরং calculation-এ 100 দিয়ে ভাগ করা হয়েছে।

## 14. Practical Program: Sales Report

```python
product_a_sales = 125000
product_b_sales = 245500
product_c_sales = 98500

total_sales = product_a_sales + product_b_sales + product_c_sales

print("=" * 40)
print(f"{'SALES REPORT':^40}")
print("=" * 40)
print(f"{'Product A:':<20}Tk {product_a_sales:>15,}")
print(f"{'Product B:':<20}Tk {product_b_sales:>15,}")
print(f"{'Product C:':<20}Tk {product_c_sales:>15,}")
print("-" * 40)
print(f"{'Total Sales:':<20}Tk {total_sales:>15,}")
print("=" * 40)
```

Output:

```text
========================================
              SALES REPORT
========================================
Product A:          Tk         125,000
Product B:          Tk         245,500
Product C:          Tk          98,500
----------------------------------------
Total Sales:        Tk         469,000
========================================
```

এই program-এ large numbers comma দিয়ে এবং amount column width নির্ধারণ করে display করা হয়েছে।

## 15. Common Mistakes

### Mistake 1: Ratio and Percentage Confusion

```python
score = 0.85

print(f"{score:.2f}%")
print(f"{score:.2%}")
```

Output:

```text
0.85%
85.00%
```

প্রথম লাইনে ratio-কে decimal format করে `%` character যোগ করা হয়েছে। দ্বিতীয় লাইনে ratio-কে percentage হিসেবে format করা হয়েছে।

### Mistake 2: Forgetting Thousand Separator

```python
amount = 1250000

print(f"Tk {amount:.2f}")
print(f"Tk {amount:,.2f}")
```

Output:

```text
Tk 1250000.00
Tk 1,250,000.00
```

দ্বিতীয় output বড় amount পড়তে সুবিধা দেয়।

### Mistake 3: Expecting Formatting to Change the Variable

```python
price = 125.567

formatted_price = f"{price:.2f}"

print(formatted_price)
print(price)
```

Output:

```text
125.57
125.567
```

Formatted output একটি string। এটি original variable-এর value পরিবর্তন করে না।

### Mistake 4: Using Float for Every Financial Calculation

সাধারণ example-এ `float` ব্যবহার করা যায়। কিন্তু exact decimal arithmetic দরকার হলে `Decimal` ব্যবহার করো এবং rounding policy নির্ধারণ করো।

### Mistake 5: Adding Currency Symbols Incorrectly

Python নিজে থেকে `Tk` বা `$` যোগ করে না।

```python
price = 1500

print(f"Tk {price:,.2f}")
print(f"${price:,.2f}")
```

Output:

```text
Tk 1,500.00
$1,500.00
```

Currency label বা symbol প্রয়োজন অনুযায়ী দিতে হবে।

## 16. Practice Exercises

### Exercise 1: Percentage

`obtained = 460` এবং `total = 500` থেকে percentage বের করে দুই decimal places-এ দেখাও।

### Exercise 2: Currency

`price = 1575.5`-কে `Tk 1,575.50` হিসেবে দেখাও।

### Exercise 3: Large Number

`population = 175000000`-কে comma separator দিয়ে দেখাও।

### Exercise 4: Discount

একটি product-এর price Tk 4,000 এবং discount rate 12%। Discount amount ও final price বের করো।

### Exercise 5: Average Marks

তিনটি subject-এর marks `85`, `92`, `78`। Average দুই decimal places-এ দেখাও।

### Exercise 6: Product Bill

Product name, unit price, quantity এবং total price দেখিয়ে একটি bill তৈরি করো।

### Exercise 7: Float and Decimal

`0.1 + 0.2`-এর output দেখাও। তারপর `Decimal` ব্যবহার করে exact decimal addition করো।

### Exercise 8: Output Prediction

```python
amount = 1234567.891
ratio = 0.875

print(f"Tk {amount:,.2f}")
print(f"{ratio:.1%}")
print(f"{170000000:,}")
```

Output কী হবে?

## 17. Practice Answer Key

### Answer 1

```python
obtained = 460
total = 500

percentage = obtained / total

print(f"Percentage: {percentage:.2%}")
```

Output:

```text
Percentage: 92.00%
```

### Answer 2

```python
price = 1575.5

print(f"Tk {price:,.2f}")
```

Output:

```text
Tk 1,575.50
```

### Answer 3

```python
population = 175000000

print(f"{population:,}")
```

Output:

```text
175,000,000
```

### Answer 4

```python
price = 4000
discount_rate = 12

discount = price * discount_rate / 100
final_price = price - discount

print(f"Discount: Tk {discount:,.2f}")
print(f"Final Price: Tk {final_price:,.2f}")
```

Output:

```text
Discount: Tk 480.00
Final Price: Tk 3,520.00
```

### Answer 5

```python
marks = [85, 92, 78]

average = sum(marks) / len(marks)

print(f"Average: {average:.2f}")
```

Output:

```text
Average: 85.00
```

### Answer 6

```python
product = "Mouse"
unit_price = 650
quantity = 3

total = unit_price * quantity

print(f"Product: {product}")
print(f"Unit Price: Tk {unit_price:,.2f}")
print(f"Quantity: {quantity}")
print(f"Total: Tk {total:,.2f}")
```

Output:

```text
Product: Mouse
Unit Price: Tk 650.00
Quantity: 3
Total: Tk 1,950.00
```

### Answer 7

```python
from decimal import Decimal

print(0.1 + 0.2)

result = Decimal("0.1") + Decimal("0.2")
print(result)
```

Output:

```text
0.30000000000000004
0.3
```

### Answer 8

Output:

```text
Tk 1,234,567.89
87.5%
170,000,000
```

## 18. Chapter Summary

- Percentage বের করার formula হলো `(obtained / total) * 100`।
- Ratio হিসেবে থাকা value-কে `f"{value:.2%}"` দিয়ে percentage দেখানো যায়।
- Value আগে থেকেই percentage হলে `f"{value:.2f}%"` ব্যবহার করা যায়।
- Currency label ও symbol সাধারণত string-এর মধ্যে যোগ করতে হয়।
- `:,` বড় number-এ thousand separator যোগ করে।
- `:,.2f` comma separator ও দুই decimal places একসঙ্গে ব্যবহার করে।
- Formatting output-এর representation পরিবর্তন করে; মূল variable পরিবর্তন করে না।
- Financial calculation-এ exact decimal arithmetic প্রয়োজন হলে `Decimal` বিবেচনা করতে হবে।
- বাস্তব application-এ currency, rounding এবং precision-এর নিয়ম স্পষ্ট রাখা জরুরি।

## 19. Self-Assessment Checklist

- [ ] Ratio ও percentage-এর পার্থক্য বুঝি।
- [ ] Percentage হিসাব ও format করতে পারি।
- [ ] Currency label এবং symbol যোগ করতে পারি।
- [ ] Large numbers-এ comma separator ব্যবহার করতে পারি।
- [ ] Decimal places ও rounding নিয়ন্ত্রণ করতে পারি।
- [ ] Product bill ও discount calculator তৈরি করতে পারি।
- [ ] `float` ও `Decimal`-এর মৌলিক পার্থক্য বুঝি।
- [ ] Formatted string এবং original numeric value-এর পার্থক্য বুঝি।

**Next Topic:** `25_Common_Input_Output_Errors.md` — এখানে `input()`, `print()`, type conversion এবং string formatting ব্যবহার করার সময় হওয়া সাধারণ ভুল ও তাদের সমাধান শিখব।