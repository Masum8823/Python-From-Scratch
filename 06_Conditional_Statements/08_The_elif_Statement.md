# 08. The `elif` Statement

## 1. Introduction

Python-এ `elif`-এর পূর্ণরূপ হলো **else if**। একাধিক condition ধারাবাহিকভাবে পরীক্ষা করার জন্য এটি ব্যবহার করা হয়।

যখন প্রথম condition মিথ্যা হয়, তখন Python পরবর্তী `elif` condition পরীক্ষা করে। যে condition প্রথম সত্য হয়, তার block execute হয় এবং বাকি `elif` ও `else` block আর পরীক্ষা করা হয় না।

সহজভাবে:

- `if` দিয়ে প্রথম condition পরীক্ষা করা হয়।
- `elif` দিয়ে পরবর্তী condition পরীক্ষা করা হয়।
- `else` দিয়ে বাকি সব অবস্থার জন্য default action নির্ধারণ করা হয়।

Example:

```python
marks = 75

if marks >= 80:
    print("Grade A+")
elif marks >= 70:
    print("Grade A")
else:
    print("Grade below A")
```

Output:

```text
Grade A
```

এখানে `marks >= 80` মিথ্যা, কিন্তু `marks >= 70` সত্য। তাই `Grade A` print হয়েছে।

## 2. Why Do We Need `elif`?

শুধু `if-else` ব্যবহার করলে সাধারণত একটি condition এবং তার বিকল্প ফলাফল নির্ধারণ করা হয়। কিন্তু অনেক সময় দুইটির বেশি সম্ভাব্য ফলাফল থাকে।

ধরো, marks অনুযায়ী grade দিতে হবে:

- 80 বা তার বেশি → A+
- 70 বা তার বেশি → A
- 60 বা তার বেশি → B
- অন্যথায় → Below B

এ ক্ষেত্রে `elif` ব্যবহার করলে code সহজ ও পরিষ্কার হয়।

```python
marks = 65

if marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
elif marks >= 60:
    print("B")
else:
    print("Below B")
```

Output:

```text
B
```

এখানে একাধিক condition থাকলেও শুধু একটি result print হয়েছে।

## 3. Syntax of `if-elif-else`

Python-এ সাধারণ syntax:

```python
if condition_1:
    statement_1
elif condition_2:
    statement_2
elif condition_3:
    statement_3
else:
    default_statement
```

এখানে:

- `if` প্রথম condition পরীক্ষা করে।
- `elif` পরবর্তী condition পরীক্ষা করে।
- প্রয়োজন অনুযায়ী একাধিক `elif` লেখা যায়।
- `else` optional; এটি থাকলে আগের সব condition মিথ্যা হওয়ার ক্ষেত্রে execute হয়।
- `if`-এর পরে একাধিক `elif` থাকতে পারে।
- `else` থাকলে সেটি সব `elif`-এর পরে লিখতে হয়।

**Important:** Python-এ `elseif` বা `else if` আলাদা keyword হিসেবে লেখা হয় না। সঠিক keyword হলো `elif`।

## 4. How Does `elif` Work?

Python `if-elif-else` structure-এ ওপর থেকে নিচে condition পরীক্ষা করে।

1. প্রথমে `if` condition পরীক্ষা করে।
2. `if` সত্য হলে তার block execute করে এবং chain শেষ হয়।
3. `if` মিথ্যা হলে প্রথম `elif` পরীক্ষা করে।
4. সেটি মিথ্যা হলে পরবর্তী `elif` পরীক্ষা করে।
5. কোনো condition সত্য না হলে, `else` থাকলে সেটি execute হয়।

### Example

```python
number = 0

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

Output:

```text
Zero
```

ব্যাখ্যা:

- `number > 0` মিথ্যা।
- `number < 0`-ও মিথ্যা।
- তাই `else` block execute হয়েছে।

## 5. Understanding the Execution Flow

ধরো, `marks = 75`।

```python
marks = 75

if marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
elif marks >= 60:
    print("B")
else:
    print("Fail")
```

Condition checking:

| Step | Condition | Result |
|---|---|---|
| 1 | `marks >= 80` | `False` |
| 2 | `marks >= 70` | `True` |
| 3 | `marks >= 60` | পরীক্ষা করা হবে না |
| 4 | `else` | execute হবে না |

Output:

```text
A
```

দ্বিতীয় condition সত্য হওয়ার পর Python আর পরের condition পরীক্ষা করে না।

## 6. Order of Conditions Matters

`elif` ব্যবহার করার সময় condition-এর order খুব গুরুত্বপূর্ণ।

ধরো, আমরা grade নির্ধারণ করতে চাই:

- 80 বা তার বেশি → A+
- 70 বা তার বেশি → A
- 60 বা তার বেশি → B
- অন্যথায় → Below B

### Incorrect Order

```python
marks = 85

if marks >= 60:
    print("B")
elif marks >= 70:
    print("A")
elif marks >= 80:
    print("A+")
else:
    print("Below B")
```

Output:

```text
B
```

কেন?

কারণ `85 >= 60` প্রথম condition-এই সত্য। Python সঙ্গে সঙ্গে `B` print করে chain শেষ করে দেয়। পরের condition-গুলো পরীক্ষা হয় না।

### Correct Order

```python
marks = 85

if marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
elif marks >= 60:
    print("B")
else:
    print("Below B")
```

Output:

```text
A+
```

**Rule:** যখন condition-গুলো বড়-ছোট threshold-এর ওপর নির্ভর করে, তখন সাধারণত বেশি threshold থেকে কম threshold-এর দিকে সাজানো ভালো।

তবে সব ক্ষেত্রে descending order বাধ্যতামূলক নয়। সঠিক order নির্ভর করে problem-এর logic-এর ওপর।

## 7. Practical Example 1: Grade Calculation

একজন student-এর marks অনুযায়ী grade নির্ধারণ করা যাক।

```python
marks = float(input("Enter your marks: "))

if marks >= 80:
    print("Grade: A+")
elif marks >= 70:
    print("Grade: A")
elif marks >= 60:
    print("Grade: B")
elif marks >= 50:
    print("Grade: C")
elif marks >= 40:
    print("Grade: D")
else:
    print("Grade: F")
```

Sample Input:

```text
Enter your marks: 76
```

Output:

```text
Grade: A
```

এখানে উপরের threshold-গুলো ধারাবাহিকভাবে পরীক্ষা করা হয়। 76-এর জন্য প্রথম condition মিথ্যা, কিন্তু `marks >= 70` সত্য।

Note: এটি একটি উদাহরণমূলক grading scale। বাস্তবে university বা course-এর নির্ধারিত grading policy অনুসরণ করতে হবে।

## 8. Practical Example 2: Positive, Negative or Zero

একটি number positive, negative নাকি zero তা নির্ধারণ করা যাক।

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive number")
elif number < 0:
    print("Negative number")
else:
    print("Zero")
```

Sample Input:

```text
Enter a number: -8
```

Output:

```text
Negative number
```

এখানে তিনটি সম্ভাব্য ফলাফলের জন্য তিনটি branch রয়েছে।

## 9. Practical Example 3: Number Classification

একটি integer-এর মান অনুযায়ী category নির্ধারণ করা যাক।

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

এই program-এ সব integer ঠিক একটি category-তে পড়বে।

| Input | Output |
|---:|---|
| `10` | `Positive` |
| `-5` | `Negative` |
| `0` | `Zero` |

## 10. Practical Example 4: Age Categories

```python
age = int(input("Enter your age: "))

if age < 0:
    print("Invalid age")
elif age < 13:
    print("Child")
elif age < 20:
    print("Teenager")
elif age < 60:
    print("Adult")
else:
    print("Senior")
```

Sample Input:

```text
Enter your age: 16
```

Output:

```text
Teenager
```

ব্যাখ্যা:

- `age < 0` মিথ্যা।
- `age < 13` মিথ্যা।
- `age < 20` সত্য।
- তাই `Teenager` print হয়েছে।

এখানে condition-গুলো ascending threshold অনুযায়ী লেখা হয়েছে। আগের condition-গুলো মিথ্যা হওয়ার বিষয়টি পরবর্তী branch-গুলোর interpretation-এ গুরুত্বপূর্ণ।

Note: বয়সের category এখানে কেবল শেখার উদাহরণ; বাস্তব ক্ষেত্রে category-এর সংজ্ঞা ভিন্ন হতে পারে।

## 11. Practical Example 5: Electricity Bill Category

ধরো, বিদ্যুৎ ব্যবহারের unit অনুযায়ী একটি simple category দেখাতে হবে।

```python
units = int(input("Enter electricity units: "))

if units < 0:
    print("Invalid units")
elif units <= 100:
    print("Low usage")
elif units <= 300:
    print("Medium usage")
else:
    print("High usage")
```

Sample Input:

```text
Enter electricity units: 250
```

Output:

```text
Medium usage
```

এখানে:

- Negative unit invalid।
- 0–100 হলে Low usage।
- 101–300 হলে Medium usage।
- 300-এর বেশি হলে High usage।

এটি usage classification-এর উদাহরণ, বাস্তব electricity tariff calculation নয়।

## 12. Practical Example 6: Simple Calculator

দুটি number ও একটি operator input নিয়ে calculation করা যাক।

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
        print("Cannot divide by zero")
else:
    print("Invalid operator")
```

Sample Input:

```text
Enter first number: 10
Enter operator (+, -, *, /): *
Enter second number: 5
```

Output:

```text
Result: 50.0
```

এখানে operator অনুযায়ী সঠিক calculation বেছে নেওয়া হয়েছে। Division-এর ক্ষেত্রে zero check করার জন্য nested `if` ব্যবহার করা হয়েছে।

## 13. Practical Example 7: Ticket Price

বয়স অনুযায়ী ticket price নির্ধারণ করা যাক।

```python
age = int(input("Enter your age: "))

if age < 0:
    print("Invalid age")
elif age < 5:
    print("Free ticket")
elif age < 18:
    print("Child ticket")
else:
    print("Regular ticket")
```

Sample Input:

```text
Enter your age: 12
```

Output:

```text
Child ticket
```

এই উদাহরণে প্রথমে invalid age check করা হয়েছে। এরপর বয়স অনুযায়ী বাকি category নির্ধারণ করা হয়েছে।

## 14. `if-elif-else` vs Multiple Independent `if` Statements

এই পার্থক্যটি খুব গুরুত্বপূর্ণ।

### Using `if-elif-else`

```python
number = 10

if number > 0:
    print("Positive")
elif number > 5:
    print("Greater than 5")
```

Output:

```text
Positive
```

প্রথম condition সত্য হওয়ায় দ্বিতীয় condition পরীক্ষা করা হয় না।

### Using Independent `if` Statements

```python
number = 10

if number > 0:
    print("Positive")

if number > 5:
    print("Greater than 5")
```

Output:

```text
Positive
Greater than 5
```

এখানে প্রতিটি `if` আলাদাভাবে পরীক্ষা করা হয়েছে।

| `if-elif-else` chain | Independent `if` statements |
|---|---|
| প্রথম সত্য condition-এর branch execute হয় | প্রতিটি condition আলাদাভাবে পরীক্ষা হয় |
| সাধারণত একটি branch execute হয় | একাধিক block execute হতে পারে |
| বিকল্পগুলোর মধ্যে একটি বেছে নিতে উপযোগী | একাধিক independent action-এর জন্য উপযোগী |

**কখন কোনটি ব্যবহার করবে?**

- একই decision-এর মধ্যে একটি মাত্র ফলাফল বেছে নিতে হলে `if-elif-else` ব্যবহার করো।
- একাধিক condition সত্য হলে একাধিক কাজ করাতে হলে independent `if` ব্যবহার করো।

## 15. `elif` Without `else`

`else` optional। প্রয়োজন হলে `else` ছাড়াও একাধিক `elif` ব্যবহার করা যায়।

Example:

```python
marks = 75

if marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
elif marks >= 60:
    print("B")
```

Output:

```text
A
```

যদি সব condition মিথ্যা হয়, তাহলে কোনো branch execute হবে না।

Example:

```python
marks = 30

if marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
elif marks >= 60:
    print("B")
```

Output:

```text
```

এখানে কোনো output নেই, কারণ সব condition মিথ্যা এবং `else` নেই।

## 16. Can We Use Multiple `elif` Statements?

হ্যাঁ। প্রয়োজন অনুযায়ী একাধিক `elif` ব্যবহার করা যায়।

Example:

```python
day = 4

if day == 1:
    print("Monday")
elif day == 2:
    print("Tuesday")
elif day == 3:
    print("Wednesday")
elif day == 4:
    print("Thursday")
elif day == 5:
    print("Friday")
else:
    print("Other day")
```

Output:

```text
Thursday
```

এই example-এ পাঁচটি `elif` ব্যবহার করা হয়েছে। Python প্রথম সত্য condition পেয়ে গেলে chain শেষ করে।

## 17. Common Mistakes

### Mistake 1: Writing `elseif`

Incorrect:

```python
if marks >= 80:
    print("A+")
elseif marks >= 70:
    print("A")
```

এটি Python-এর valid syntax নয়।

Correct:

```python
if marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
```

### Mistake 2: Wrong Condition Order

Incorrect:

```python
marks = 90

if marks >= 40:
    print("Pass")
elif marks >= 80:
    print("A+")
```

Output:

```text
Pass
```

`marks >= 40` আগে সত্য হওয়ায় `A+` branch-এ পৌঁছানো হয় না।

যদি grade নির্ধারণ করতে চাও, তাহলে সঠিক threshold order ব্যবহার করতে হবে।

### Mistake 3: Incorrect Indentation

Incorrect:

```python
if marks >= 80:
    print("A+")
    elif marks >= 70:
        print("A")
```

Correct:

```python
if marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
```

### Mistake 4: Forgetting the Colon

Incorrect:

```python
elif marks >= 70
    print("A")
```

Correct:

```python
elif marks >= 70:
    print("A")
```

### Mistake 5: Overlapping Conditions Without Understanding Their Order

```python
number = 15

if number > 0:
    print("Positive")
elif number > 10:
    print("Greater than 10")
```

Output:

```text
Positive
```

এখানে দ্বিতীয় condition সত্য হতে পারত, কিন্তু প্রথম condition-ই সত্য হওয়ায় সেটি পরীক্ষা করা হয়নি।

যদি দুইটি property-ই দেখাতে চাও, তাহলে independent `if` ব্যবহার করা উচিত।

## 18. Practice Exercises

নিজে solve করার চেষ্টা করো।

### Exercise 1: Positive, Negative or Zero

একটি integer input নিয়ে `if-elif-else` দিয়ে number positive, negative নাকি zero নির্ধারণ করো।

### Exercise 2: Grade Calculator

Marks অনুযায়ী grade দেখাও:

- 80 বা তার বেশি → A+
- 70 বা তার বেশি → A
- 60 বা তার বেশি → B
- 50 বা তার বেশি → C
- 40 বা তার বেশি → D
- অন্যথায় → F

### Exercise 3: Age Category

বয়স অনুযায়ী নিচের message দেখাও:

- Negative → Invalid age
- 13-এর কম → Child
- 20-এর কম → Teenager
- অন্যথায় → Adult

### Exercise 4: Divisibility

একটি integer input নাও:

- 5 দিয়ে বিভাজ্য হলে `Divisible by 5`
- 3 দিয়ে বিভাজ্য হলে `Divisible by 3`
- অন্যথায় `Not divisible by 3 or 5`

**Hint:** 3 ও 5 উভয় দিয়ে বিভাজ্য number-এর ক্ষেত্রে প্রথমে 5-এর condition পরীক্ষা করলে সেটি 5-এর branch-এ চলে যেতে পারে। Problem-এর requirement অনুযায়ী condition order নির্ধারণ করো।

### Exercise 5: Simple Calculator

দুটি number এবং একটি operator (`+`, `-`, `*`, `/`) input নিয়ে `if-elif-else` দিয়ে result বের করো। Division-এর ক্ষেত্রে zero check করো।

### Exercise 6: Output Prediction

```python
score = 85

if score >= 60:
    print("B")
elif score >= 80:
    print("A")
else:
    print("F")
```

Output কী হবে? কেন?

### Exercise 7: Independent `if` vs `elif`

নিচের দুটি code-এর output আলাদা করে লেখো এবং কারণ ব্যাখ্যা করো।

Code A:

```python
x = 12

if x > 0:
    print("Positive")
elif x > 10:
    print("Greater than 10")
```

Code B:

```python
x = 12

if x > 0:
    print("Positive")

if x > 10:
    print("Greater than 10")
```

## 19. Practice Answer Key

### Answer 1

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

### Answer 2

```python
marks = float(input("Enter marks: "))

if marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
elif marks >= 60:
    print("B")
elif marks >= 50:
    print("C")
elif marks >= 40:
    print("D")
else:
    print("F")
```

### Answer 3

```python
age = int(input("Enter age: "))

if age < 0:
    print("Invalid age")
elif age < 13:
    print("Child")
elif age < 20:
    print("Teenager")
else:
    print("Adult")
```

### Answer 4

```python
number = int(input("Enter an integer: "))

if number % 5 == 0:
    print("Divisible by 5")
elif number % 3 == 0:
    print("Divisible by 3")
else:
    print("Not divisible by 3 or 5")
```

এই solution-এ 15-এর মতো number `Divisible by 5` দেখাবে, কারণ প্রথম condition সত্য। যদি 3 ও 5 উভয় দিয়ে বিভাজ্য হওয়ার জন্য আলাদা category চাওয়া হয়, তাহলে সেটি আগে পরীক্ষা করতে হবে।

### Answer 5

```python
a = float(input("Enter first number: "))
operator = input("Enter operator (+, -, *, /): ")
b = float(input("Enter second number: "))

if operator == "+":
    print(a + b)
elif operator == "-":
    print(a - b)
elif operator == "*":
    print(a * b)
elif operator == "/":
    if b != 0:
        print(a / b)
    else:
        print("Cannot divide by zero")
else:
    print("Invalid operator")
```

### Answer 6

Output:

```text
B
```

কারণ `score >= 60` প্রথম condition-এই সত্য। তাই দ্বিতীয় condition পরীক্ষা করা হয় না।

### Answer 7

Code A output:

```text
Positive
```

Code B output:

```text
Positive
Greater than 10
```

Code A-তে প্রথম condition সত্য হওয়ায় `elif` পরীক্ষা হয় না। Code B-তে দুইটি independent `if` থাকায় দুইটি condition-ই পরীক্ষা করা হয়।

## 20. Chapter Summary

- `elif`-এর অর্থ `else if`।
- একাধিক condition পরীক্ষা করার জন্য `elif` ব্যবহার করা হয়।
- Python উপর থেকে নিচে condition পরীক্ষা করে।
- প্রথম সত্য condition-এর block execute হয়।
- `else` optional এবং সব condition মিথ্যা হলে execute হয়।
- Condition-এর order সঠিক হওয়া গুরুত্বপূর্ণ।
- `if-elif-else` chain সাধারণত একটি branch নির্বাচন করে।
- Independent `if` statements একাধিক block execute করতে পারে।
- Python-এ সঠিক keyword হলো `elif`, `elseif` নয়।

## 21. Self-Assessment Checklist

- [ ] `elif` কী এবং কেন ব্যবহার করা হয়, তা ব্যাখ্যা করতে পারি।
- [ ] `if-elif-else` syntax লিখতে পারি।
- [ ] একাধিক condition-এর execution flow বুঝি।
- [ ] Condition-এর সঠিক order নির্ধারণ করতে পারি।
- [ ] Grade calculator-এর মতো program লিখতে পারি।
- [ ] `if-elif-else` ও independent `if`-এর পার্থক্য বুঝি।
- [ ] `else` ছাড়া `elif` ব্যবহার করতে পারি।
- [ ] Common syntax ও logic errors শনাক্ত করতে পারি।

## 22. Next Topic

পরবর্তী file:

`09_Multiple_Conditions_with_elif.md`

সেখানে একাধিক condition-কে সঠিকভাবে সাজানো, overlapping conditions, range checking এবং আরও complex decision-making problem বিস্তারিতভাবে শেখা হবে।