# 08. Comparison Operators in Python

## 1. Introduction to Comparison Operators

Comparison Operators হলো এমন Operators, যেগুলো দুটি Value-এর মধ্যে তুলনা করে।

তুলনার Result হিসেবে Python সাধারণত দুটি Boolean Value-এর একটি দেয়:

- `True` — Condition সত্য।
- `False` — Condition মিথ্যা।

Example:

```python
a = 10
b = 20

print(a < b)
print(a > b)
```

Output:

```text
True
False
```

এখানে `10`, `20`-এর চেয়ে ছোট, তাই প্রথম Result `True`। কিন্তু `10`, `20`-এর চেয়ে বড় নয়, তাই দ্বিতীয় Result `False`।

## 2. Types of Comparison Operators

Python-এর ছয়টি প্রধান Comparison Operator হলো:

| Operator | Name | কাজ |
|---|---|---|
| `==` | Equal to | দুটি Value সমান কি না পরীক্ষা করে |
| `!=` | Not equal to | দুটি Value অসমান কি না পরীক্ষা করে |
| `>` | Greater than | বাম Value বড় কি না পরীক্ষা করে |
| `<` | Less than | বাম Value ছোট কি না পরীক্ষা করে |
| `>=` | Greater than or equal to | বাম Value বড় অথবা সমান কি না পরীক্ষা করে |
| `<=` | Less than or equal to | বাম Value ছোট অথবা সমান কি না পরীক্ষা করে |

## 3. Equal to Operator (`==`)

`==` Operator দুটি Value সমান কি না পরীক্ষা করে।

Value দুটি সমান হলে `True`, অন্যথায় `False` দেয়।

Example:

```python
a = 10
b = 10
c = 20

print(a == b)
print(a == c)
```

Output:

```text
True
False
```

ব্যাখ্যা:

- `a == b` → `10 == 10` → `True`
- `a == c` → `10 == 20` → `False`

### Practical Example

একজন Student-এর প্রাপ্ত Marks 80 কি না পরীক্ষা করা যাক।

```python
marks = 80

print(marks == 80)
```

Output:

```text
True
```

### Important: `=` vs `==`

এই দুটি Operator-এর কাজ আলাদা।

| Operator | কাজ |
|---|---|
| `=` | Variable-এ Value Assign করে |
| `==` | দুটি Value তুলনা করে |

Example:

```python
number = 10

print(number == 10)
```

Output:

```text
True
```

এখানে `number = 10` দিয়ে Value Assign করা হয়েছে এবং `number == 10` দিয়ে Value তুলনা করা হয়েছে।

## 4. Not Equal to Operator (`!=`)

`!=` Operator দুটি Value সমান নয় কি না পরীক্ষা করে।

Value দুটি অসমান হলে `True`, সমান হলে `False` দেয়।

Example:

```python
a = 10
b = 20
c = 10

print(a != b)
print(a != c)
```

Output:

```text
True
False
```

ব্যাখ্যা:

- `10 != 20` → `True`
- `10 != 10` → `False`

### Practical Example

একটি PIN সঠিক PIN-এর সঙ্গে মেলে না কি না পরীক্ষা:

```python
entered_pin = 1234
correct_pin = 5678

print(entered_pin != correct_pin)
```

Output:

```text
True
```

এই উদাহরণে দুটি PIN আলাদা। তবে বাস্তব Authentication System-এ শুধু Comparison Operator ব্যবহার করাই যথেষ্ট নয়; নিরাপদ Authentication ব্যবস্থা প্রয়োজন।

## 5. Greater Than Operator (`>`)

`>` Operator পরীক্ষা করে বাম পাশের Value ডান পাশের Value-এর চেয়ে বড় কি না।

Example:

```python
a = 25
b = 15

print(a > b)
print(b > a)
```

Output:

```text
True
False
```

### Practical Example: Passing Marks

ধরা যাক, একজন Student-এর Marks 40-এর বেশি কি না পরীক্ষা করতে হবে।

```python
marks = 65

print(marks > 40)
```

Output:

```text
True
```

**মনে রাখবে:** `>` শুধু বড় হওয়ার ক্ষেত্রে `True` দেয়। দুটি Value সমান হলে Result `False`।

```python
print(40 > 40)
```

Output:

```text
False
```

## 6. Less Than Operator (`<`)

`<` Operator পরীক্ষা করে বাম পাশের Value ডান পাশের Value-এর চেয়ে ছোট কি না।

Example:

```python
a = 10
b = 25

print(a < b)
print(b < a)
```

Output:

```text
True
False
```

### Practical Example: Age Check

```python
age = 16

print(age < 18)
```

Output:

```text
True
```

এখানে `age` হলো 18-এর চেয়ে ছোট।

সমান হলে Result `False` হবে:

```python
print(18 < 18)
```

Output:

```text
False
```

## 7. Greater Than or Equal to Operator (`>=`)

`>=` Operator পরীক্ষা করে বাম Value ডান Value-এর চেয়ে বড় অথবা সমান কি না।

Example:

```python
print(20 >= 10)
print(20 >= 20)
print(10 >= 20)
```

Output:

```text
True
True
False
```

এখানে:

- `20 >= 10` → `True`
- `20 >= 20` → `True`
- `10 >= 20` → `False`

### Practical Example: Passing Criteria

ধরা যাক, পরীক্ষায় Pass করতে কমপক্ষে 40 Marks প্রয়োজন।

```python
marks = 40

print(marks >= 40)
```

Output:

```text
True
```

এখানে `>=` ব্যবহার করা হয়েছে, কারণ ঠিক 40 পেলেও Pass করা যায়।

## 8. Less Than or Equal to Operator (`<=`)

`<=` Operator পরীক্ষা করে বাম Value ডান Value-এর চেয়ে ছোট অথবা সমান কি না।

Example:

```python
print(10 <= 20)
print(20 <= 20)
print(30 <= 20)
```

Output:

```text
True
True
False
```

### Practical Example: Age Limit

কোনো কার্যক্রমে সর্বোচ্চ বয়স 25 বছর হলে:

```python
age = 25

print(age <= 25)
```

Output:

```text
True
```

এখানে ঠিক 25 বছর হলেও Condition সত্য।

## 9. Comparison Operators with Variables

Comparison Operators সাধারণত Variables-এর Value তুলনা করতে ব্যবহার করা হয়।

```python
num1 = 50
num2 = 30

print(num1 == num2)
print(num1 != num2)
print(num1 > num2)
print(num1 < num2)
print(num1 >= num2)
print(num1 <= num2)
```

Output:

```text
False
True
True
False
True
False
```

Variable-এর Value পরিবর্তন করলে Comparison-এর Result-ও পরিবর্তিত হতে পারে।

## 10. Comparison Operators with Integers and Floats

Python-এ Integer ও Float তুলনা করা যায়।

Example:

```python
print(5 == 5.0)
print(5 < 5.5)
print(6 > 5.5)
```

Output:

```text
True
True
True
```

এখানে `5` এবং `5.0` Numeric Value হিসেবে সমান, তাই `5 == 5.0` হলো `True`।

**Note:** Float-এর Precision সীমিত হওয়ায় কিছু Decimal Value তুলনা করার সময় সতর্ক থাকতে হয়।

## 11. Comparison Operators with Strings

Python-এ String-ও তুলনা করা যায়।

### 11.1 String Equality

```python
print("Python" == "Python")
print("Python" == "python")
```

Output:

```text
True
False
```

String Comparison Case-Sensitive। অর্থাৎ, Uppercase এবং Lowercase Letter আলাদা হিসেবে বিবেচিত হয়।

### 11.2 String Inequality

```python
print("apple" != "orange")
```

Output:

```text
True
```

### 11.3 Lexicographical Comparison

String-এর ক্ষেত্রে `<`, `>` ইত্যাদি Operators Lexicographical Order অনুযায়ী Character তুলনা করে।

```python
print("apple" < "banana")
print("cat" > "car")
```

Output:

```text
True
True
```

Character-এর Unicode Value অনুযায়ী তুলনা করা হয়। তাই String Comparison-কে সবসময় সাধারণ Dictionary Order-এর সঙ্গে এক করে দেখা ঠিক নয়।

### 11.4 Comparing Different Types

Python-এ `int` ও `str`-এর মধ্যে সাধারণ Ordering Comparison করা যায় না।

```python
print(10 > "5")
```

এখানে `TypeError` হবে।

তবে `==` এবং `!=` দিয়ে ভিন্ন Data Type-এর Value তুলনা করা যায়:

```python
print(10 == "10")
print(10 != "10")
```

Output:

```text
False
True
```

কারণ Integer `10` এবং String `"10"` একই Data Type-এর Value নয় এবং সাধারণ Equality Comparison-এ সমান নয়।

## 12. Comparison Operators with Boolean Values

Boolean Value হলো `True` এবং `False`।

```python
print(True == True)
print(True == False)
print(False != True)
```

Output:

```text
True
False
True
```

Python-এ `bool` হলো `int`-এর Subclass। তাই Numeric Context-এ `True`-এর মান `1` এবং `False`-এর মান `0` হিসেবে ব্যবহৃত হতে পারে।

```python
print(True == 1)
print(False == 0)
```

Output:

```text
True
True
```

তবে Code আরও পরিষ্কার রাখতে Boolean Value-এর সঙ্গে Boolean Comparison করাই সাধারণত ভালো।

## 13. Comparison Results Are Boolean Values

Comparison Operator-এর Result সাধারণত Boolean Value হয়।

```python
result = 10 > 5

print(result)
print(type(result))
```

Output:

```text
True
<class 'bool'>
```

এখানে `result` Variable-এ `True` সংরক্ষিত হয়েছে।

Boolean Result ব্যবহার করে পরবর্তীতে Conditional Statement লেখা যায়।

```python
marks = 75
passed = marks >= 40

if passed:
    print("Passed")
else:
    print("Failed")
```

Output:

```text
Passed
```

## 14. Using Comparison Operators in Conditions

Comparison Operators Decision Making-এর ভিত্তি।

### Example 1: Even or Odd Check-এর সঙ্গে Comparison

```python
number = 10

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

Output:

```text
Even
```

এখানে `%` Remainder বের করে এবং `==` পরীক্ষা করে Remainder Zero কি না।

### Example 2: Age Eligibility

```python
age = 20

if age >= 18:
    print("Eligible")
else:
    print("Not Eligible")
```

Output:

```text
Eligible
```

### Example 3: Marks Evaluation

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

এই উদাহরণগুলোতে Comparison Operator-এর Result ব্যবহার করে Program-এর পরবর্তী কাজ নির্ধারণ করা হচ্ছে।

## 15. Common Mistakes

### Mistake 1: Using `=` Instead of `==`

ভুল:

```python
number = 10

if number = 10:
    print("Equal")
```

এটি Syntax Error তৈরি করবে।

সঠিক:

```python
number = 10

if number == 10:
    print("Equal")
```

Output:

```text
Equal
```

### Mistake 2: Confusing `>` with `>=`

```python
print(50 > 50)
print(50 >= 50)
```

Output:

```text
False
True
```

`>`-এ সমান হওয়ার সুযোগ নেই, কিন্তু `>=`-এ আছে।

### Mistake 3: Comparing Incompatible Types

```python
print(10 < "20")
```

এখানে `TypeError` হবে।

প্রয়োজনে String-কে Integer-এ Convert করতে হবে:

```python
print(10 < int("20"))
```

Output:

```text
True
```

### Mistake 4: Ignoring Case Sensitivity

```python
print("Python" == "python")
```

Output:

```text
False
```

Case-Insensitive Comparison প্রয়োজন হলে উভয় String-কে একই Case-এ Convert করা যায়।

```python
first = "Python"
second = "python"

print(first.lower() == second.lower())
```

Output:

```text
True
```

### Mistake 5: Assuming `==` and `is` Are the Same

`==` Value Equality পরীক্ষা করে, কিন্তু `is` Object Identity পরীক্ষা করে।

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a == b)
print(a is b)
```

Output:

```text
True
False
```

দুটি List-এর Content সমান, কিন্তু তারা আলাদা Object। এই বিষয়টি পরবর্তী Identity Operators Topic-এ বিস্তারিত আলোচনা করা হবে।

## 16. Practice Exercises

### Basic Level

1. `10 == 10`-এর Result বের করো।
2. `15 != 20`-এর Result বের করো।
3. `25 > 30`-এর Result বের করো।
4. `40 >= 40`-এর Result বের করো।
5. `18 <= 17`-এর Result বের করো।

### Intermediate Level

6. একটি Number 100-এর বেশি কি না পরীক্ষা করো।
7. একজন Student 40 বা তার বেশি Marks পেয়েছে কি না পরীক্ষা করো।
8. দুটি Number সমান কি না পরীক্ষা করো।
9. দুটি String একই কি না পরীক্ষা করো।
10. একটি বয়স 18 থেকে 25-এর মধ্যে কি না পরীক্ষা করো। এই কাজের জন্য একাধিক Comparison Operator ব্যবহার করার চেষ্টা করো।

### Output Prediction

```python
a = 10
b = 20

print(a == b)
print(a != b)
print(a < b)
print(a >= b)

print(5 == 5.0)
print("Python" == "python")
```

### Solution

```text
False
True
True
False
True
False
```

### Practical Challenge

একটি Student Result Program তৈরি করো।

Requirements:

1. একটি Variable-এ Marks রাখো।
2. Marks `40` বা তার বেশি কি না পরীক্ষা করো।
3. Condition সত্য হলে `Pass` Print করো।
4. অন্যথায় `Fail` Print করো।
5. `==`, `!=`, `>` এবং `>=` Operators ব্যবহার করে আলাদা Comparison Test করো।

## 17. Chapter Summary

- Comparison Operators দুটি Value-এর মধ্যে তুলনা করে।
- `==` সমান কি না পরীক্ষা করে।
- `!=` অসমান কি না পরীক্ষা করে।
- `>` বড় এবং `<` ছোট কি না পরীক্ষা করে।
- `>=` বড় অথবা সমান এবং `<=` ছোট অথবা সমান কি না পরীক্ষা করে।
- Comparison-এর Result সাধারণত `True` অথবা `False` হয়।
- `=` Value Assign করে, আর `==` Value তুলনা করে।
- Integer ও Float তুলনা করা যায়, কিন্তু `int` ও `str`-এর Ordering Comparison সাধারণত Error তৈরি করে।
- String Comparison Case-Sensitive।
- Comparison Operators `if-else` এবং অন্যান্য Decision-Making Logic-এ গুরুত্বপূর্ণ।

## 18. Self-Assessment Checklist

- [ ] ছয়টি Comparison Operator চিনতে পারি।
- [ ] `=` এবং `==`-এর পার্থক্য বুঝি।
- [ ] `>` ও `>=`-এর পার্থক্য বুঝি।
- [ ] `True` এবং `False` Result ব্যাখ্যা করতে পারি।
- [ ] Integer, Float এবং String Comparison করতে পারি।
- [ ] Comparison Operator দিয়ে Conditional Statement লিখতে পারি।
- [ ] Common Comparison Errors শনাক্ত করতে পারি।

**Next Topic:** `09_Chained_Comparisons.md`