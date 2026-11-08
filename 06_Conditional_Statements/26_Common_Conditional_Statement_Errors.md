# 26. Common Conditional Statement Errors

## 1. Introduction

Python-এ conditional statements ব্যবহার করে condition অনুযায়ী program-এর execution নিয়ন্ত্রণ করা হয়। তবে syntax, indentation বা logical condition ভুল হলে program error দিতে পারে অথবা ভুল result দেখাতে পারে।

Conditional statements-এ সাধারণত দুই ধরনের সমস্যা দেখা যায়:

1. **Syntax Error:** Code-এর structure বা syntax ভুল।
2. **Logical Error:** Code চলে, কিন্তু result প্রত্যাশা অনুযায়ী হয় না।

এই অধ্যায়ে common errors, তাদের কারণ এবং সঠিক সমাধান শিখব।

## 2. Forgetting the Colon (`:`)

Python-এ `if`, `elif`, `else` এবং `match-case`-এর সংশ্লিষ্ট line-এর শেষে colon (`:`) দিতে হয়।

### Incorrect Code

```python
age = 20

if age >= 18
    print("Adult")
```

Output:

```text
SyntaxError
```

### Correct Code

```python
age = 20

if age >= 18:
    print("Adult")
```

Output:

```text
Adult
```

**মনে রাখবে:** Conditional statement-এর header-এর শেষে colon দিতে হবে।

## 3. Incorrect Indentation

Python-এ indentation দিয়ে code block নির্ধারণ করা হয়। সাধারণত চারটি space ব্যবহার করা হয়।

### Incorrect Code

```python
age = 20

if age >= 18:
print("Adult")
```

এখানে `print()` statement-টি `if` block-এর ভেতরে সঠিকভাবে indent করা হয়নি।

### Correct Code

```python
age = 20

if age >= 18:
    print("Adult")
```

Output:

```text
Adult
```

**সমাধান:** একই block-এর statement-গুলো একই indentation level-এ রাখবে।

## 4. Using `=` Instead of `==`

`=` এবং `==`-এর কাজ আলাদা।

- `=` দিয়ে variable-এ value assign করা হয়।
- `==` দিয়ে দুইটি value সমান কি না পরীক্ষা করা হয়।

### Incorrect Code

```python
number = 10

if number = 10:
    print("Equal")
```

Output:

```text
SyntaxError
```

### Correct Code

```python
number = 10

if number == 10:
    print("Equal")
```

Output:

```text
Equal
```

**মনে রাখবে:** Condition-এ equality পরীক্ষা করতে `==` ব্যবহার করবে।

## 5. Incorrect Use of `else`

`else`-এর পরে condition লেখা যায় না। এটি আগের `if` বা `if-elif` chain-এর কোনো condition True না হলে execute হয়।

### Incorrect Code

```python
age = 20

if age >= 18:
    print("Adult")
else age < 18:
    print("Minor")
```

Output:

```text
SyntaxError
```

### Correct Code

```python
age = 20

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

Output:

```text
Adult
```

যদি `else`-এর মতো আরেকটি condition পরীক্ষা করতে চাও, তাহলে `elif` ব্যবহার করবে।

```python
age = 20

if age >= 18:
    print("Adult")
elif age < 18:
    print("Minor")
```

তবে এখানে `else` ব্যবহার করাই সহজ, কারণ দ্বিতীয় condition-টি প্রথম condition False হলেই সত্য হবে।

## 6. Writing Multiple `if` Statements Instead of `if-elif`

Independent `if` statement-গুলো আলাদাভাবে পরীক্ষা করা হয়। কিন্তু `if-elif-else` chain-এ প্রথম True condition-এর block execute হলে বাকি branch-গুলো skip করা হয়।

### Example

```python
marks = 85

if marks >= 60:
    print("Pass")

if marks >= 80:
    print("Grade A")
```

Output:

```text
Pass
Grade A
```

দুটি `if`-এর condition-ই True, তাই দুটো message print হয়েছে।

যদি শুধু একটি grade নির্ধারণ করতে চাও, তাহলে:

```python
marks = 85

if marks >= 80:
    print("Grade A")
elif marks >= 60:
    print("Grade C")
else:
    print("Fail")
```

Output:

```text
Grade A
```

**মনে রাখবে:** একাধিক independent condition পরীক্ষা করতে `if` ব্যবহার করা যায়। কিন্তু একটি মাত্র alternative নির্বাচন করতে হলে `if-elif-else` বেশি উপযোগী হতে পারে।

## 7. Incorrect Order of Conditions

`if-elif-else`-এ condition ভুল ক্রমে লিখলে সঠিক category নির্বাচন নাও হতে পারে।

### Incorrect Code

```python
marks = 85

if marks >= 60:
    print("Grade C")
elif marks >= 80:
    print("Grade A")
else:
    print("Fail")
```

Output:

```text
Grade C
```

কেন?

`marks >= 60` প্রথমেই True হয়েছে। তাই পরের `elif marks >= 80` পরীক্ষা করা হয়নি।

### Correct Code

```python
marks = 85

if marks >= 80:
    print("Grade A")
elif marks >= 60:
    print("Grade C")
else:
    print("Fail")
```

Output:

```text
Grade A
```

**সমাধান:** Overlapping range থাকলে সাধারণত বড় threshold আগে পরীক্ষা করবে।

## 8. Incorrect Use of `and` and `or`

Logical operators ভুলভাবে ব্যবহার করলে condition-এর result ভুল হতে পারে।

### Incorrect Logic

```python
age = 15

if age >= 18 or age <= 60:
    print("Eligible")
```

Output:

```text
Eligible
```

এখানে condition-টি প্রায় সব numeric age-এর জন্য True, কারণ 18-এর কম হলে দ্বিতীয় অংশ True এবং 18 বা তার বেশি হলে প্রথম অংশ True।

### Correct Logic

```python
age = 15

if age >= 18 and age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

Output:

```text
Not eligible
```

একই condition এভাবে আরও সংক্ষেপে লেখা যায়:

```python
if 18 <= age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

**মনে রাখবে:**

- `and` — সব condition True হতে হবে।
- `or` — অন্তত একটি condition True হলেই হবে।

## 9. Incorrect Use of `not`

`not` একটি Boolean condition-এর result উল্টে দেয়।

### Example

```python
is_logged_in = False

if not is_logged_in:
    print("Please log in")
```

Output:

```text
Please log in
```

কখনো `not` ভুল জায়গায় ব্যবহার করলে logic বদলে যেতে পারে।

```python
age = 20

if not age >= 18:
    print("Not an adult")
else:
    print("Adult")
```

Output:

```text
Adult
```

এখানে `age >= 18` True, তাই `not True` হলো False। ফলে `else` block execute হয়েছে।

**সমাধান:** জটিল condition-এ parentheses ব্যবহার করে logic পরিষ্কার রাখবে।

## 10. Forgetting That `input()` Returns a String

`input()` সাধারণত string return করে। তাই numeric comparison করার আগে প্রয়োজন অনুযায়ী type conversion করতে হবে।

### Incorrect Code

```python
age = input("Enter age: ")

if age >= 18:
    print("Adult")
```

যদি user `20` দেয়, তবুও string ও integer-এর comparison-এর কারণে `TypeError` হবে।

### Correct Code

```python
age = int(input("Enter age: "))

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

এখানে ধরে নেওয়া হয়েছে যে user integer input দেবে। Non-numeric input দিলে `int()` conversion-এ `ValueError` হতে পারে।

## 11. Comparing Strings Incorrectly

String comparison case-sensitive। তাই `"yes"` এবং `"YES"` এক নয়।

### Example

```python
answer = input("Continue? ")

if answer == "yes":
    print("Continuing")
else:
    print("Cancelled")
```

User `YES` লিখলে output হবে:

```text
Cancelled
```

Case-insensitive input চাইলে:

```python
answer = input("Continue? ").strip().lower()

if answer == "yes":
    print("Continuing")
else:
    print("Cancelled")
```

এখন `YES`, `Yes` এবং `yes` একইভাবে গ্রহণ করা হবে।

## 12. Using `is` Instead of `==`

`==` value equality পরীক্ষা করে, কিন্তু `is` object identity পরীক্ষা করে।

### Incorrect Approach

```python
choice = input("Enter yes: ")

if choice is "yes":
    print("Confirmed")
```

এভাবে string-এর value পরীক্ষা করা উচিত নয়। `is` দিয়ে identity পরীক্ষা করা হয়, string-এর content নয়।

### Correct Approach

```python
choice = input("Enter yes: ")

if choice == "yes":
    print("Confirmed")
```

`None` পরীক্ষা করার সময় `is None` ব্যবহার করা সঠিক:

```python
result = None

if result is None:
    print("No result")
```

## 13. Forgetting Boundary Conditions

Range বা limit পরীক্ষা করার সময় `>` এবং `>=`-এর পার্থক্য গুরুত্বপূর্ণ।

ধরা যাক, 40 বা তার বেশি marks হলে pass।

### Incorrect Code

```python
marks = 40

if marks > 40:
    print("Pass")
else:
    print("Fail")
```

Output:

```text
Fail
```

কারণ `40 > 40` False।

### Correct Code

```python
marks = 40

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

Output:

```text
Pass
```

**মনে রাখবে:**

- `>` — strictly greater than।
- `>=` — greater than or equal to।
- `<` — strictly less than।
- `<=` — less than or equal to।

Condition লেখার আগে boundary value দিয়ে পরীক্ষা করবে।

## 14. Incorrect Use of `in`

Membership operator `in` কোনো collection বা string-এর মধ্যে value আছে কি না পরীক্ষা করে।

### Incorrect Code

```python
choice = "yes"

if choice == "yes" or "y":
    print("Confirmed")
```

Output:

```text
Confirmed
```

এটি দেখতে সঠিক মনে হলেও condition ভুল। `"y"` একটি non-empty string, তাই এটি truthy। ফলে condition সবসময় True হবে।

### Correct Code

```python
choice = "yes"

if choice == "yes" or choice == "y":
    print("Confirmed")
```

অথবা:

```python
choice = "yes"

if choice in ("yes", "y"):
    print("Confirmed")
```

দুটি পদ্ধতিই এখানে সঠিক।

## 15. Incorrect Match-Case Patterns

`match-case` ব্যবহার করার সময় input-এর type এবং pattern-এর ধরন খেয়াল রাখতে হবে।

### Incorrect Code

```python
choice = input("Enter choice: ")

match choice:
    case 1:
        print("One")
    case _:
        print("Other")
```

User `1` লিখলে `input()` string `"1"` return করে। তাই integer pattern `1`-এর সঙ্গে এটি match করবে না।

### Correct Code

```python
choice = input("Enter choice: ")

match choice:
    case "1":
        print("One")
    case _:
        print("Other")
```

আরও একটি গুরুত্বপূর্ণ বিষয়: `case name:`-এর মতো bare name একটি capture pattern। এটি সাধারণত যেকোনো value match করে এবং value-টি `name`-এ bind করে। কোনো variable-এর বর্তমান value-এর সঙ্গে তুলনা করতে চাইলে bare name pattern ব্যবহার করা যাবে না।

## 16. Incorrect Use of Nested Conditions

Nested `if`-এ indentation ভুল হলে logic বদলে যেতে পারে।

### Example

```python
age = 20
has_id = False

if age >= 18:
    if has_id:
        print("Access granted")
else:
    print("Age requirement not met")
```

এখানে `else`-টি বাইরের `if age >= 18`-এর সঙ্গে যুক্ত, ভেতরের `if has_id`-এর সঙ্গে নয়। তাই বয়স 18 বা তার বেশি হলে কিন্তু `has_id` False হলে কোনো message print হবে না।

আরও পরিষ্কারভাবে লিখতে চাইলে:

```python
age = 20
has_id = False

if age >= 18:
    if has_id:
        print("Access granted")
    else:
        print("ID is required")
else:
    print("Age requirement not met")
```

Output:

```text
ID is required
```

**সমাধান:** Nested condition লেখার সময় প্রতিটি `else` কোন `if`-এর সঙ্গে যুক্ত, তা indentation দেখে নিশ্চিত করবে।

## 17. Not Handling Invalid Input

শুধু `int()` বা `float()` ব্যবহার করলেই input valid হয়ে যায় না।

### Example

```python
marks = int(input("Enter marks: "))

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

User যদি `abc` দেয়, তাহলে `ValueError` হবে। আর `150` দিলে program সেটিকে Pass হিসেবে দেখাতে পারে, যদিও marks-এর valid range হয়তো 0–100।

**সমাধান:** বাস্তব program-এ type conversion-এর error এবং acceptable range—দুটিই handle করবে। প্রয়োজন অনুযায়ী input validation এবং `try-except` ব্যবহার করা যায়।

## 18. Quick Error-Checking Table

| ভুল | সঠিক পদ্ধতি |
|---|---|
| `if`-এর শেষে colon নেই | `if condition:` |
| Block-এর indentation ভুল | Block-এর code indent করা |
| Equality পরীক্ষায় `=` | `==` ব্যবহার |
| `else condition:` লেখা | `else:` অথবা `elif condition:` |
| Range-এর condition ভুল ক্রমে | Threshold সঠিকভাবে সাজানো |
| `or`-এর সঙ্গে condition অসম্পূর্ণ | দুই পাশেই পূর্ণ condition লেখা |
| `input()`-এর string সরাসরি numeric comparison | প্রয়োজন অনুযায়ী convert করা |
| String comparison-এ `is` | `==` ব্যবহার |
| Boundary-তে `>` ব্যবহার | প্রয়োজন অনুযায়ী `>=` বা `<=` |
| `choice == "yes" or "y"` | `choice in ("yes", "y")` |
| Input validation বাদ দেওয়া | Type ও range যাচাই করা |

## 19. Practice Exercises

প্রতিটি code-এর error বা logical problem শনাক্ত করো এবং ঠিক করো।

### Question 1

```python
age = 20

if age >= 18
    print("Adult")
```

### Question 2

```python
number = 10

if number = 10:
    print("Equal")
```

### Question 3

```python
marks = 85

if marks >= 60:
    print("C")
elif marks >= 80:
    print("A")
```

### Question 4

```python
age = 15

if age >= 18 or age <= 60:
    print("Eligible")
```

### Question 5

```python
choice = "no"

if choice == "yes" or "y":
    print("Confirmed")
else:
    print("Not confirmed")
```

### Question 6

```python
age = input("Enter age: ")

if age >= 18:
    print("Adult")
```

### Question 7

```python
marks = 40

if marks > 40:
    print("Pass")
else:
    print("Fail")
```

### Question 8

```python
choice = input("Enter choice: ")

match choice:
    case 1:
        print("One")
    case _:
        print("Other")
```

## 20. Answer Key

### Answer 1

সমস্যা: `if`-এর শেষে colon নেই।

```python
age = 20

if age >= 18:
    print("Adult")
```

### Answer 2

সমস্যা: Condition-এ assignment operator `=` ব্যবহার করা হয়েছে।

```python
number = 10

if number == 10:
    print("Equal")
```

### Answer 3

সমস্যা: `marks >= 60` আগে True হওয়ায় `elif marks >= 80` পরীক্ষা করা হবে না।

```python
marks = 85

if marks >= 80:
    print("A")
elif marks >= 60:
    print("C")
```

Output:

```text
A
```

### Answer 4

সমস্যা: `or` ব্যবহারের কারণে condition প্রায় সব numeric age-এর জন্য True।

```python
age = 15

if age >= 18 and age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

### Answer 5

সমস্যা: `"y"` আলাদা করে condition হিসেবে লেখা হয়েছে; এটি truthy।

```python
choice = "no"

if choice == "yes" or choice == "y":
    print("Confirmed")
else:
    print("Not confirmed")
```

Output:

```text
Not confirmed
```

### Answer 6

সমস্যা: `input()` string return করে।

```python
age = int(input("Enter age: "))

if age >= 18:
    print("Adult")
```

এটি numeric input-এর জন্য সঠিক; invalid text-এর জন্য অতিরিক্ত error handling প্রয়োজন।

### Answer 7

সমস্যা: `marks = 40` হলে `marks > 40` False। Pass mark 40 হলে `>=` ব্যবহার করতে হবে।

```python
marks = 40

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

### Answer 8

সমস্যা: `input()` string return করে, কিন্তু pattern হলো integer `1`।

```python
choice = input("Enter choice: ")

match choice:
    case "1":
        print("One")
    case _:
        print("Other")
```

## 21. Quick Revision

- Conditional statement-এর syntax এবং colon ঠিক রাখতে হবে।
- Python-এ indentation দিয়ে code block নির্ধারণ করা হয়।
- Assignment ও comparison operator আলাদা।
- `if-elif-else`-এর condition order গুরুত্বপূর্ণ।
- `and` ও `or`-এর logic বুঝে condition লিখতে হবে।
- `input()` string return করে।
- String-এর value তুলনা করতে `==` ব্যবহার করতে হবে।
- Boundary value পরীক্ষা করার সময় `>` ও `>=`-এর পার্থক্য খেয়াল রাখতে হবে।
- Nested `if`-এ `else` কোন `if`-এর সঙ্গে যুক্ত তা বুঝতে হবে।
- `match-case`-এ pattern-এর type ও syntax সঠিক রাখতে হবে।
- Input validation বাদ দিলে program error দিতে পারে বা ভুল result দেখাতে পারে।

## 22. Self-Assessment Checklist

- [ ] Syntax Error ও Logical Error-এর পার্থক্য বুঝি।
- [ ] Missing colon ও indentation error ঠিক করতে পারি।
- [ ] `=` ও `==`-এর পার্থক্য জানি।
- [ ] `if-elif-else`-এর condition order ঠিক রাখতে পারি।
- [ ] `and`, `or` ও `not`-এর common mistakes শনাক্ত করতে পারি।
- [ ] Input-এর data type এবং boundary condition যাচাই করতে পারি।
- [ ] `is` ও `==`-এর সঠিক ব্যবহার জানি।
- [ ] Nested conditions ও `match-case`-এর ভুল ঠিক করতে পারি।

**পরবর্তী টপিক:** `27_Debugging_Conditional_Logic.md`
