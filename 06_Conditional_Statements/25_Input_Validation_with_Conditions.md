# 25. Input Validation with Conditions

## 1. What Is Input Validation?

**Input Validation** হলো user-এর দেওয়া input সঠিক, গ্রহণযোগ্য এবং নির্দিষ্ট নিয়মের মধ্যে আছে কি না পরীক্ষা করার প্রক্রিয়া।

User ভুল data দিলে program যেন ভুল সিদ্ধান্ত না নেয়, সে জন্য input validation ব্যবহার করা হয়।

উদাহরণ:

```python
age = int(input("Enter your age: "))

if age >= 18:
    print("Eligible")
else:
    print("Not eligible")
```

এই program-এ age পরীক্ষা করা হচ্ছে। কিন্তু user যদি `-5` দেয়, তাহলে program সেটিকে age হিসেবে গ্রহণ করবে। আবার user যদি `abc` দেয়, তাহলে `int()` conversion-এ error হবে।

তাই শুধু condition ব্যবহার করাই সবসময় যথেষ্ট নয়। Input-এর type এবং গ্রহণযোগ্য range-ও যাচাই করতে হয়।

## 2. Why Is Input Validation Needed?

Input validation-এর প্রধান উদ্দেশ্য:

- ভুল input গ্রহণ করা থেকে বিরত থাকা।
- Invalid data দিয়ে ভুল calculation হওয়া ঠেকানো।
- Program-এর unexpected behavior কমানো।
- User-কে পরিষ্কার error message দেওয়া।
- Application-এর reliability বাড়ানো।

উদাহরণ হিসেবে, marks-এর valid range যদি 0 থেকে 100 হয়, তাহলে 150 marks গ্রহণ করা উচিত নয়।

```python
marks = float(input("Enter marks: "))

if marks < 0 or marks > 100:
    print("Invalid marks")
elif marks >= 40:
    print("Pass")
else:
    print("Fail")
```

Input:

```text
Enter marks: 150
```

Output:

```text
Invalid marks
```

এখানে valid range-এর বাইরে থাকা marks-এর জন্য grade নির্ধারণ করা হচ্ছে না।

**Note:** এই উদাহরণে ধরে নেওয়া হয়েছে যে user numeric input দেবে। Non-numeric input সামলাতে অতিরিক্ত validation প্রয়োজন।

## 3. Checking Empty Input

কখনো user কোনো কিছু না লিখে Enter চাপতে পারে। এমন input পরীক্ষা করতে `if` ব্যবহার করা যায়।

```python
name = input("Enter your name: ")

if name == "":
    print("Name cannot be empty")
else:
    print("Welcome,", name)
```

Input:

```text
Enter your name:
```

Output:

```text
Name cannot be empty
```

এখানে `name == ""` পরীক্ষা করছে string-টি empty কি না।

আরও সংক্ষিপ্তভাবে লেখা যায়:

```python
name = input("Enter your name: ")

if not name:
    print("Name cannot be empty")
else:
    print("Welcome,", name)
```

Python-এ empty string `""` হলো falsy value।

### Leading and Trailing Spaces

User যদি শুধু কয়েকটি space দেয়, তাহলে input string technically empty নয়।

```python
name = input("Enter your name: ").strip()

if not name:
    print("Name cannot be empty")
else:
    print("Welcome,", name)
```

`strip()` string-এর শুরু ও শেষের whitespace সরিয়ে দেয়। ফলে শুধু space দেওয়া input-ও validation-এ empty হিসেবে ধরা হবে।

## 4. Checking Numeric Ranges

কোনো number নির্দিষ্ট range-এর মধ্যে আছে কি না যাচাই করতে comparison operators ব্যবহার করা হয়।

ধরা যাক, age 0 থেকে 120-এর মধ্যে হতে হবে।

```python
age = int(input("Enter your age: "))

if age < 0 or age > 120:
    print("Invalid age")
else:
    print("Age accepted")
```

Input:

```text
Enter your age: -5
```

Output:

```text
Invalid age
```

এখানে:

- `age < 0` হলে age invalid।
- `age > 120` হলেও age invalid।
- অন্যথায় age গ্রহণ করা হয়।

একই condition chained comparison দিয়েও লেখা যায়:

```python
if 0 <= age <= 120:
    print("Age accepted")
else:
    print("Invalid age")
```

দুটি condition-ই একই valid range বোঝায়।

**গুরুত্বপূর্ণ:** Age-এর maximum range এখানে উদাহরণ হিসেবে 120 ধরা হয়েছে। বাস্তব application-এর নিয়ম অনুযায়ী range নির্ধারণ করতে হবে।

## 5. Checking Allowed Choices

যখন user-কে নির্দিষ্ট কিছু option-এর মধ্যে একটি বেছে নিতে বলা হয়, তখন membership operator `in` ব্যবহার করা যায়।

```python
choice = input("Choose yes or no: ").strip().lower()

if choice in ("yes", "y", "no", "n"):
    print("Valid choice")
else:
    print("Invalid choice")
```

Input:

```text
Choose yes or no: YES
```

Output:

```text
Valid choice
```

এখানে `.lower()` input-কে lowercase করে। তাই `YES`, `Yes` এবং `yes` একইভাবে handle করা যায়।

Tuple-এর মধ্যে অনুমোদিত choice-গুলো রাখা হয়েছে। User-এর input সেই tuple-এর কোনো value-এর সঙ্গে মিললে condition True হবে।

## 6. Combining Multiple Validation Conditions

একটি input valid হতে একাধিক শর্ত পূরণ করতে হতে পারে।

ধরা যাক, username:

- Empty হতে পারবে না।
- কমপক্ষে 5 characters হতে হবে।
- সর্বোচ্চ 15 characters হতে হবে।

```python
username = input("Enter username: ").strip()

if not username:
    print("Username cannot be empty")
elif len(username) < 5:
    print("Username must contain at least 5 characters")
elif len(username) > 15:
    print("Username cannot exceed 15 characters")
else:
    print("Username accepted")
```

Input:

```text
Enter username: mas
```

Output:

```text
Username must contain at least 5 characters
```

এখানে `len()` দিয়ে string-এর length বের করা হয়েছে।

প্রথম invalid condition পাওয়া গেলে তার message দেখানো হবে এবং পরের `elif` condition-গুলো আর পরীক্ষা করা হবে না।

**Note:** এটি একটি basic length validation। বাস্তব username-এর জন্য allowed characters, uniqueness এবং অন্যান্য rules-ও থাকতে পারে।

## 7. Validating Numeric Input Before Conversion

এখন পর্যন্ত numeric input নেওয়ার সময় সরাসরি `int()` বা `float()` ব্যবহার করেছি। কিন্তু user text দিলে conversion error হতে পারে।

উদাহরণ:

```python
age = int(input("Enter your age: "))
```

User যদি `abc` লেখে, তাহলে `ValueError` হবে।

`str.isdigit()` দিয়ে কিছু সাধারণ positive integer input পরীক্ষা করা যায়:

```python
age_text = input("Enter your age: ").strip()

if age_text.isdigit():
    age = int(age_text)

    if age <= 120:
        print("Age accepted")
    else:
        print("Age is too large")
else:
    print("Please enter a valid whole number")
```

Input:

```text
Enter your age: abc
```

Output:

```text
Please enter a valid whole number
```

তবে মনে রাখবে, `isdigit()` সব ধরনের valid numeric string শনাক্ত করে না। যেমন `-5` এবং `3.5`-এর জন্য এটি False দেয়।

তাই signed integer বা decimal number validate করতে আরও উপযুক্ত পদ্ধতি প্রয়োজন হতে পারে। পরবর্তী সময়ে `try-except` ব্যবহার করে conversion error সামলানো শিখবে।

## 8. Using Conditions to Validate Marks

ধরা যাক, marks 0 থেকে 100-এর মধ্যে হতে হবে এবং 40 হলো pass mark।

```python
marks_text = input("Enter your marks: ").strip()

if marks_text.isdigit():
    marks = int(marks_text)

    if marks > 100:
        print("Marks cannot exceed 100")
    elif marks >= 40:
        print("Pass")
    else:
        print("Fail")
else:
    print("Please enter whole-number marks")
```

Input:

```text
Enter your marks: 85
```

Output:

```text
Pass
```

এখানে প্রথমে input-টি whole-number digits কি না পরীক্ষা করা হয়েছে। তারপর marks-এর range এবং pass condition পরীক্ষা করা হয়েছে।

এই পদ্ধতি শুধু non-negative whole-number marks-এর জন্য। Decimal marks বা অন্য numeric format গ্রহণ করতে হলে validation logic পরিবর্তন করতে হবে।

## 9. Validating a Simple Menu

Menu-based program-এ user-এর choice সঠিক কি না যাচাই করা যায়।

```python
choice = input("Choose 1, 2, or 3: ").strip()

if choice not in ("1", "2", "3"):
    print("Invalid choice")
else:
    match choice:
        case "1":
            print("Add")
        case "2":
            print("Subtract")
        case "3":
            print("Multiply")
```

Input:

```text
Choose 1, 2, or 3: 5
```

Output:

```text
Invalid choice
```

এখানে `match-case` চালানোর আগে input validate করা হয়েছে। ফলে শুধু অনুমোদিত option-গুলোই process করা হচ্ছে।

## 10. Common Input Validation Mistakes

### Mistake 1: শুধু upper limit পরীক্ষা করা

ভুল:

```python
if age <= 120:
    print("Valid age")
```

এখানে negative age-ও গ্রহণ করা হবে।

সঠিক:

```python
if 0 <= age <= 120:
    print("Valid age")
else:
    print("Invalid age")
```

### Mistake 2: Input-এর type যাচাই না করা

```python
age = input("Enter age: ")

if age >= 18:
    print("Eligible")
```

এখানে string ও integer-এর মধ্যে comparison করার চেষ্টা হবে এবং `TypeError` হবে।

### Mistake 3: `is` দিয়ে value comparison করা

ভুল:

```python
if choice is "yes":
    print("Confirmed")
```

সঠিক:

```python
if choice == "yes":
    print("Confirmed")
```

`==` value তুলনা করে, কিন্তু `is` object identity পরীক্ষা করে।

### Mistake 4: শুধু empty string পরীক্ষা করা

```python
name = input("Enter name: ")

if name == "":
    print("Empty")
```

শুধু spaces দেওয়া হলে এই condition False হবে। প্রয়োজন হলে `strip()` ব্যবহার করো।

### Mistake 5: `isdigit()`-কে সব number-এর validation মনে করা

`isdigit()` negative number বা decimal number-এর জন্য সাধারণ সমাধান নয়। Input format অনুযায়ী validation পদ্ধতি বেছে নিতে হবে।

### Mistake 6: Invalid input-এর পরেও calculation করা

Input invalid হলে program-কে সেই data দিয়ে calculation চালিয়ে যাওয়া উচিত নয়। আগে validation, তারপর processing করতে হবে।

## 11. Practice Exercises

### Question 1: Age Validation

User-এর age input নাও। Age 0 থেকে 120-এর মধ্যে হলে `Valid age`, অন্যথায় `Invalid age` print করো।

### Question 2: Empty Name

User-এর কাছ থেকে name নাও। Empty input অথবা শুধু spaces দিলে error message দেখাও।

### Question 3: Marks Validation

Marks 0 থেকে 100-এর মধ্যে হলে valid, অন্যথায় invalid দেখাও।

### Question 4: Allowed Choice

User-কে `yes`, `no`, `y` অথবা `n` লিখতে বলো। অন্য কিছু লিখলে invalid choice দেখাও। Uppercase input-ও গ্রহণ করতে হবে।

### Question 5: Username Length

Username-এর length কমপক্ষে 5 এবং সর্বোচ্চ 15 characters হতে হবে।

### Question 6: Whole-Number Validation

User-এর কাছ থেকে age string হিসেবে নাও। `isdigit()` দিয়ে পরীক্ষা করে valid whole number হলে integer-এ convert করো।

### Question 7: Menu Validation

শুধু `1`, `2` অথবা `3` গ্রহণ করবে এমন একটি menu validation program লেখো।

### Question 8: Error শনাক্ত করো

নিচের code-এ কী সমস্যা?

```python
marks = int(input("Enter marks: "))

if marks <= 100:
    print("Valid marks")
```

## 12. Answer Key

### Answer 1

```python
age = int(input("Enter age: "))

if 0 <= age <= 120:
    print("Valid age")
else:
    print("Invalid age")
```

এটি ধরে নেয় যে user integer input দেবে।

### Answer 2

```python
name = input("Enter name: ").strip()

if not name:
    print("Name cannot be empty")
else:
    print("Name accepted")
```

### Answer 3

```python
marks = float(input("Enter marks: "))

if 0 <= marks <= 100:
    print("Valid marks")
else:
    print("Invalid marks")
```

এখানে decimal marks গ্রহণ করা হয়, কিন্তু non-numeric input দিলে conversion error হতে পারে।

### Answer 4

```python
choice = input("Enter yes or no: ").strip().lower()

if choice in ("yes", "no", "y", "n"):
    print("Valid choice")
else:
    print("Invalid choice")
```

### Answer 5

```python
username = input("Enter username: ").strip()

if not username:
    print("Username cannot be empty")
elif len(username) < 5:
    print("Too short")
elif len(username) > 15:
    print("Too long")
else:
    print("Username accepted")
```

### Answer 6

```python
age_text = input("Enter age: ").strip()

if age_text.isdigit():
    age = int(age_text)
    print("Valid whole number:", age)
else:
    print("Invalid whole number")
```

### Answer 7

```python
choice = input("Enter choice (1-3): ").strip()

if choice in ("1", "2", "3"):
    print("Valid choice")
else:
    print("Invalid choice")
```

### Answer 8

Code-টি শুধু `marks <= 100` পরীক্ষা করছে। তাই negative marks-ও valid হিসেবে গ্রহণ হবে।

সঠিক:

```python
marks = int(input("Enter marks: "))

if 0 <= marks <= 100:
    print("Valid marks")
else:
    print("Invalid marks")
```

এখানেও ধরে নেওয়া হয়েছে যে user integer input দেবে।

## 13. Quick Revision

- Input validation হলো input গ্রহণযোগ্য কি না পরীক্ষা করা।
- Empty input পরীক্ষা করতে `if not value` ব্যবহার করা যায়।
- শুরু ও শেষের spaces সরাতে `strip()` ব্যবহার করা যায়।
- Numeric range পরীক্ষা করতে comparison ও chained comparison ব্যবহার করা যায়।
- Allowed choices পরীক্ষা করতে `in` ব্যবহার করা যায়।
- `len()` দিয়ে string-এর length পরীক্ষা করা যায়।
- `isdigit()` কিছু whole-number input পরীক্ষা করতে পারে, কিন্তু সব numeric format-এর জন্য উপযুক্ত নয়।
- `int()` ও `float()` conversion error দিতে পারে।
- Invalid input হলে processing বন্ধ বা উপযুক্তভাবে পরিচালনা করা উচিত।
- `try-except` দিয়ে conversion error সামলানো যায়; এটি আমরা Exception Handling অধ্যায়ে বিস্তারিত শিখব।

## 14. Self-Assessment Checklist

- [ ] Input validation-এর প্রয়োজন ব্যাখ্যা করতে পারি।
- [ ] Empty input ও whitespace-only input পরীক্ষা করতে পারি।
- [ ] Numeric range validate করতে পারি।
- [ ] Allowed choices পরীক্ষা করতে পারি।
- [ ] Username-এর length validate করতে পারি।
- [ ] `isdigit()`-এর সীমাবদ্ধতা বুঝি।
- [ ] Invalid input দিয়ে calculation করার সমস্যা বুঝি।
- [ ] `TypeError` ও `ValueError` হওয়ার সাধারণ কারণ শনাক্ত করতে পারি।

**পরবর্তী টপিক:** `26_Common_Conditional_Statement_Errors.md`
