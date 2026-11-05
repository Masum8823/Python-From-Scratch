# 01. Introduction to Conditional Statements

## 1. What Are Conditional Statements?

**Conditional Statements** হলো programming-এর এমন একটি পদ্ধতি, যার মাধ্যমে কোনো condition সত্য নাকি মিথ্যা তার ওপর ভিত্তি করে program সিদ্ধান্ত নেয় এবং নির্দিষ্ট code execute করে।

সহজভাবে বললে, condition অনুযায়ী program-কে আলাদা কাজ করতে বলাই হলো conditional programming।

### Real-Life Example

ধরো, তুমি বিশ্ববিদ্যালয়ে পরীক্ষা দিচ্ছ।

- Marks 40 বা তার বেশি হলে Pass।
- Marks 40-এর কম হলে Fail।

এখানে marks-এর ওপর ভিত্তি করে result নির্ধারণ করা হচ্ছে। এটি একটি decision-making process।

Python-এ আমরা এভাবে লিখতে পারি:

```python
marks = 75

if marks >= 40:
    print("Pass")
```

Output:

```text
Pass
```

এখানে `marks >= 40` হলো condition। যেহেতু `75 >= 40` সত্য, তাই `print("Pass")` execute হয়েছে।

## 2. Why Do We Need Conditional Statements?

Conditional statements ছাড়া program সাধারণত লিখিত instruction অনুযায়ী একের পর এক কাজ করে। কিন্তু বাস্তব সমস্যার সমাধানে অনেক সময় বিভিন্ন পরিস্থিতিতে বিভিন্ন কাজ করতে হয়।

উদাহরণ:

- Student-এর marks অনুযায়ী pass বা fail নির্ধারণ করা।
- বয়স অনুযায়ী eligibility যাচাই করা।
- Password সঠিক হলে login করতে দেওয়া।
- Account balance পর্যাপ্ত হলে টাকা উত্তোলন করা।
- Number positive, negative নাকি zero তা নির্ধারণ করা।
- Product-এর price অনুযায়ী discount দেওয়া।

এ ধরনের decision নেওয়ার জন্য conditional statements প্রয়োজন।

### Example Without a Condition

```python
marks = 25

print("Pass")
```

Output:

```text
Pass
```

এখানে marks মাত্র 25 হলেও program সবসময় `Pass` দেখাবে। কারণ program-কে কোনো condition যাচাই করতে বলা হয়নি।

### Example With a Condition

```python
marks = 25

if marks >= 40:
    print("Pass")
```

Output:

```text
```

এখানে কোনো output নেই। কারণ `25 >= 40` মিথ্যা, তাই `if` block execute হয়নি।

**মূল ধারণা:** Condition ব্যবহার করলে program পরিস্থিতি অনুযায়ী কাজ করতে পারে।

## 3. What Is a Condition?

**Condition** হলো এমন একটি expression, যার result সত্য (`True`) অথবা মিথ্যা (`False`) হয়।

উদাহরণ:

```python
10 > 5
```

Result:

```python
True
```

আরেকটি উদাহরণ:

```python
10 < 5
```

Result:

```python
False
```

Python-এ condition যাচাই করার জন্য সাধারণত comparison operators ব্যবহার করা হয়।

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `==` | Equal to | `5 == 5` | `True` |
| `!=` | Not equal to | `5 != 3` | `True` |
| `>` | Greater than | `8 > 5` | `True` |
| `<` | Less than | `3 < 5` | `True` |
| `>=` | Greater than or equal to | `5 >= 5` | `True` |
| `<=` | Less than or equal to | `4 <= 3` | `False` |

এই operators-এর বিস্তারিত ব্যবহার পরবর্তী topic-এ শেখা হবে।

## 4. The Basic Structure of a Conditional Statement

Python-এ একটি সাধারণ `if` statement-এর structure হলো:

```python
if condition:
    statement
```

এখানে:

- `if` হলো Python-এর keyword।
- `condition` নির্ধারণ করে code execute হবে কি না।
- `:` condition-এর শেষ নির্দেশ করে।
- Indented statement হলো সেই code, যা condition সত্য হলে execute হবে।

### Example

```python
age = 20

if age >= 18:
    print("You are eligible.")
```

Output:

```text
You are eligible.
```

কারণ `age >= 18` অর্থাৎ `20 >= 18` সত্য।

### When the Condition Is False

```python
age = 15

if age >= 18:
    print("You are eligible.")
```

Output:

```text
```

এখানে condition মিথ্যা হওয়ায় `print()` execute হয়নি।

## 5. How Python Evaluates a Condition

Python সাধারণত condition evaluate করে `True` অথবা `False` ফলাফল পায়। এরপর সেই result অনুযায়ী সিদ্ধান্ত নেয়।

উদাহরণ:

```python
number = 12

if number > 10:
    print("Number is greater than 10.")
```

Program-এর কাজের ধাপ:

1. `number`-এর value হলো `12`।
2. Python `number > 10` condition পরীক্ষা করে।
3. `12 > 10` সত্য, তাই result হয় `True`।
4. `if` block-এর `print()` execute হয়।

Output:

```text
Number is greater than 10.
```

অন্যদিকে `number = 5` হলে condition মিথ্যা হতো এবং `if` block execute হতো না।

## 6. Understanding True and False

Python-এ `True` এবং `False` হলো Boolean data type-এর দুটি value।

```python
print(10 > 5)
print(10 < 5)
print(7 == 7)
print(7 != 7)
```

Output:

```text
True
False
True
False
```

Conditional statements এই Boolean result ব্যবহার করে সিদ্ধান্ত নেয়।

মনে রাখবে:

- `True` হলে `if` block execute হয়।
- `False` হলে `if` block execute হয় না।
- সাধারণ `if` statement-এ condition মিথ্যা হলে কোনো কাজ না-ও হতে পারে; বিকল্প কাজের জন্য `else` ব্যবহার করা যায়, যা পরবর্তী topic-এ শেখা হবে।

## 7. Practical Example: Pass or Fail

এবার user-এর কাছ থেকে marks নিয়ে result নির্ধারণ করি।

```python
marks = int(input("Enter your marks: "))

if marks >= 40:
    print("You passed.")
```

Sample Input:

```text
Enter your marks: 65
```

Output:

```text
You passed.
```

আরেকটি input:

```text
Enter your marks: 25
```

Output:

```text
```

এখানে 25-এর জন্য কোনো message দেখানো হয়নি, কারণ program-এ শুধু pass condition লেখা আছে।

আরও complete program-এ pass ও fail—দুটি পরিস্থিতির জন্যই আলাদা output দেওয়া যায়।

## 8. Practical Example: Positive Number

একটি number positive কি না, তা পরীক্ষা করি।

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive number")
```

Sample Input:

```text
Enter a number: 8
```

Output:

```text
Positive number
```

যদি input `-8` বা `0` হয়, তাহলে condition মিথ্যা হবে এবং কোনো output দেখাবে না।

## 9. Common Mistakes

### Mistake 1: Forgetting the Colon

Incorrect:

```python
if age >= 18
    print("Eligible")
```

এখানে `:` না থাকায় `SyntaxError` হবে।

Correct:

```python
if age >= 18:
    print("Eligible")
```

### Mistake 2: Incorrect Indentation

Incorrect:

```python
if age >= 18:
print("Eligible")
```

এখানে `print()`-কে `if` block-এর ভেতরে indent করা হয়নি। সাধারণত এটি `IndentationError` তৈরি করবে।

Correct:

```python
if age >= 18:
    print("Eligible")
```

### Mistake 3: Using `=` Instead of `==`

ভুল ধারণা:

```python
if number = 10:
    print("Ten")
```

এটি `SyntaxError` তৈরি করবে। `=` assignment-এর জন্য ব্যবহৃত হয়; equality comparison-এর জন্য `==` ব্যবহার করতে হয়।

Correct:

```python
if number == 10:
    print("Ten")
```

### Mistake 4: Incorrect Comparison

```python
marks = 40

if marks > 40:
    print("Pass")
```

এখানে output হবে না, কারণ `40 > 40` মিথ্যা।

যদি 40-কে pass mark হিসেবে ধরা হয়, তাহলে লিখতে হবে:

```python
if marks >= 40:
    print("Pass")
```

## 10. Practice Exercises

প্রথমে নিজে solve করার চেষ্টা করো।

### Exercise 1: Age Check

একটি variable-এ বয়স রাখো। বয়স 18 বা তার বেশি হলে `Adult` print করো।

### Exercise 2: Number Check

একটি integer input নিয়ে সেটি 100-এর বেশি হলে `Greater than 100` print করো।

### Exercise 3: Even Number

একটি number input নিয়ে সেটি even হলে `Even number` print করো।

Hint: Modulo operator `%` ব্যবহার করো।

### Exercise 4: Exam Result

Marks 33 বা তার বেশি হলে `Pass` print করো।

### Exercise 5: Password Check

একটি password variable-এ `"python123"` রাখো। User-এর input তার সমান হলে `Correct password` print করো।

## 11. Practice Answer Key

### Answer 1

```python
age = 20

if age >= 18:
    print("Adult")
```

### Answer 2

```python
number = int(input("Enter a number: "))

if number > 100:
    print("Greater than 100")
```

### Answer 3

```python
number = int(input("Enter a number: "))

if number % 2 == 0:
    print("Even number")
```

### Answer 4

```python
marks = int(input("Enter marks: "))

if marks >= 33:
    print("Pass")
```

### Answer 5

```python
password = "python123"
user_password = input("Enter password: ")

if user_password == password:
    print("Correct password")
```

## 12. Chapter Summary

- Conditional statements program-কে decision নিতে সাহায্য করে।
- Condition evaluate হয়ে `True` অথবা `False` result দেয়।
- Python-এর `if` statement condition সত্য হলে নির্দিষ্ট code execute করে।
- Comparison operators দিয়ে condition তৈরি করা যায়।
- `:` এবং সঠিক indentation conditional statements-এর জন্য গুরুত্বপূর্ণ।
- `=` assignment-এর জন্য এবং `==` equality comparison-এর জন্য ব্যবহৃত হয়।
- Condition মিথ্যা হলে সাধারণ `if` block execute হয় না।

## 13. Self-Assessment Checklist

- [ ] Conditional statement কী, তা ব্যাখ্যা করতে পারি।
- [ ] Condition কীভাবে `True` বা `False` হয় বুঝি।
- [ ] Basic `if` statement লিখতে পারি।
- [ ] Comparison operators দিয়ে condition তৈরি করতে পারি।
- [ ] Indentation ও colon সঠিকভাবে ব্যবহার করতে পারি।
- [ ] Condition সত্য ও মিথ্যা হলে program-এর behavior predict করতে পারি।
- [ ] Basic decision-making program নিজে লিখতে পারি।

## 14. Next Topic

পরবর্তী file:

`02_Why_Conditional_Statements_Are_Needed.md`

সেখানে আমরা আরও বাস্তব উদাহরণ দিয়ে বুঝব কেন conditional statements প্রয়োজন এবং এগুলো ছাড়া program-এর কী সীমাবদ্ধতা থাকে।