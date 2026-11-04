# 15. Input Validation Basics

## 1. Introduction to Input Validation

**Input Validation** হলো user-এর দেওয়া input আমাদের program-এর প্রয়োজনীয় শর্ত পূরণ করছে কি না, তা যাচাই করার প্রক্রিয়া।

ধরা যাক, একটি program-এ user-এর বয়স নিতে হবে। বয়সের জায়গায় user যদি `abc`, `-5` অথবা `20` দেয়, তাহলে প্রতিটি input একইভাবে গ্রহণ করা উচিত নয়।

- `20` — গ্রহণযোগ্য বয়স হতে পারে।
- `abc` — সংখ্যায় convert করা যায় না।
- `-5` — সাধারণ বয়সের ক্ষেত্রে গ্রহণযোগ্য নয়।

Input validation ব্যবহার করে আমরা সঠিক input গ্রহণ করতে এবং ভুল input-এর জন্য উপযুক্ত message দেখাতে পারি।

### Why Is Input Validation Important?

Input validation-এর প্রধান উদ্দেশ্য:

1. ভুল input শনাক্ত করা।
2. Program-এ অপ্রয়োজনীয় error কমানো।
3. Input-এর data type ও format যাচাই করা।
4. নির্দিষ্ট range-এর মধ্যে value আছে কি না পরীক্ষা করা।
5. User-কে সঠিক input দেওয়ার নির্দেশনা দেওয়া।
6. Program-কে আরও reliable ও user-friendly করা।

## 2. Basic Input Validation

সবচেয়ে সহজ validation হলো input পাওয়ার পর সেটি পরীক্ষা করা।

### Example

```python
age = int(input("Enter your age: "))

if age >= 0:
    print("Valid age")
else:
    print("Age cannot be negative")
```

Input:

```text
Enter your age: 20
```

Output:

```text
Valid age
```

কিন্তু এখানে একটি সমস্যা রয়েছে। User যদি `abc` দেয়, তাহলে `int()` conversion-এর সময় `ValueError` হবে।

তাই শুধু condition ব্যবহার করলেই সব ধরনের ভুল input সামলানো যায় না।

## 3. Validating Numeric Input with `try-except`

User-এর input integer-এ convert করা সম্ভব কি না, তা পরীক্ষা করতে `try-except` ব্যবহার করা যায়।

### Example

```python
try:
    age = int(input("Enter your age: "))
    print("Your age is:", age)

except ValueError:
    print("Please enter a valid integer.")
```

Input:

```text
Enter your age: abc
```

Output:

```text
Please enter a valid integer.
```

এখানে:

- `try` block-এর মধ্যে risky operation রাখা হয়েছে।
- `int()` conversion সফল হলে program পরের statement চালাবে।
- Conversion ব্যর্থ হয়ে `ValueError` হলে `except` block চলবে।

**মনে রাখবে:** `try-except` error সামলায়; এটি নিজে থেকে input-কে সঠিক করে না।

## 4. Validating Positive Numbers

অনেক program-এ শুধু সংখ্যায় input দিলেই হবে না, সংখ্যাটি positive হতে হবে।

যেমন: পণ্যের quantity, দৈর্ঘ্য বা পরীক্ষার প্রশ্নে নির্ধারিত কোনো positive value।

### Example

```python
number = int(input("Enter a positive number: "))

if number > 0:
    print("Valid input")
else:
    print("Number must be positive")
```

Input:

```text
Enter a positive number: -5
```

Output:

```text
Number must be positive
```

এখানে negative number integer হিসেবে valid হলেও program-এর নিয়ম অনুযায়ী গ্রহণযোগ্য নয়।

এটি একটি গুরুত্বপূর্ণ পার্থক্য:

- **Type validation:** input integer কি না।
- **Rule validation:** integer-টি program-এর শর্ত পূরণ করছে কি না।

## 5. Validating a Range of Values

কখনো input নির্দিষ্ট range-এর মধ্যে থাকতে হয়।

উদাহরণস্বরূপ, পরীক্ষার নম্বর 0 থেকে 100-এর মধ্যে হতে হবে।

### Example

```python
marks = int(input("Enter your marks: "))

if 0 <= marks <= 100:
    print("Valid marks")
else:
    print("Marks must be between 0 and 100.")
```

Input:

```text
Enter your marks: 85
```

Output:

```text
Valid marks
```

Input:

```text
Enter your marks: 120
```

Output:

```text
Marks must be between 0 and 100.
```

Python-এ `0 <= marks <= 100` একটি chained comparison। এটি পরীক্ষা করে `marks` একই সঙ্গে 0-এর সমান বা বড় এবং 100-এর সমান বা ছোট কি না।

তবে `abc` দিলে এই code-এও `ValueError` হতে পারে। তাই প্রয়োজন হলে type validation এবং range validation একসঙ্গে করতে হবে।

## 6. Combining Type and Range Validation

একটি input গ্রহণযোগ্য হওয়ার জন্য সেটি integer হতে হবে এবং নির্দিষ্ট range-এ থাকতে হবে।

### Example

```python
try:
    marks = int(input("Enter your marks (0-100): "))

    if 0 <= marks <= 100:
        print("Valid marks")
    else:
        print("Marks must be between 0 and 100.")

except ValueError:
    print("Please enter a whole number.")
```

এখানে তিনটি সম্ভাব্য ফলাফল রয়েছে:

| Input | Result |
|---|---|
| `85` | Valid marks |
| `120` | Range error message |
| `hello` | Whole number error message |

এই পদ্ধতিতে conversion error এবং range error আলাদাভাবে handle করা যায়।

## 7. Validating Floating-Point Input

কোনো input decimal number হতে পারে। সে ক্ষেত্রে `float()` ব্যবহার করা যায়।

### Example

```python
try:
    price = float(input("Enter product price: "))

    if price >= 0:
        print("Valid price:", price)
    else:
        print("Price cannot be negative.")

except ValueError:
    print("Please enter a valid number.")
```

Input:

```text
Enter product price: 99.50
```

Output:

```text
Valid price: 99.5
```

এই example-এ negative price প্রত্যাখ্যান করা হয়েছে।

মনে রাখবে, `float()` কিছু special value যেমন `nan` এবং `inf`-ও গ্রহণ করতে পারে। কোনো application-এ শুধু finite number গ্রহণ করা প্রয়োজন হলে `math.isfinite()` দিয়ে অতিরিক্ত validation করতে পারো।

## 8. Validating Empty Input

User শুধু Enter চাপলে `input()` একটি empty string (`""`) return করে।

### Example

```python
name = input("Enter your name: ").strip()

if name:
    print("Hello,", name)
else:
    print("Name cannot be empty.")
```

Input:

```text
Enter your name:
```

Output:

```text
Name cannot be empty.
```

এখানে `.strip()` string-এর শুরু ও শেষের whitespace সরিয়ে দেয়। ফলে user শুধু space দিলেও `name` empty হয়ে যাবে।

**কেন `if name` কাজ করে?**

Python-এ empty string falsy। তাই `if name:` তখনই true হবে, যখন `name` empty string নয়।

## 9. Validating Text Input

কখনো input-এ শুধু alphabetic character থাকা প্রয়োজন হতে পারে।

Python-এর `.isalpha()` method পরীক্ষা করে string-এর সব character alphabetic কি না।

### Example

```python
name = input("Enter your name: ").strip()

if name and name.isalpha():
    print("Valid name")
else:
    print("Please enter letters only.")
```

Input:

```text
Enter your name: Masum
```

Output:

```text
Valid name
```

কিন্তু `Abdulla Masum` দিলে validation ব্যর্থ হবে, কারণ মাঝখানে space আছে।

Space-সহ নাম গ্রহণ করতে চাইলে:

```python
name = input("Enter your full name: ").strip()

if name and all(part.isalpha() for part in name.split()):
    print("Valid name")
else:
    print("Please enter a valid name.")
```

এই উদাহরণটি প্রতিটি অংশে alphabetic character আছে কি না পরীক্ষা করে।

তবে `.isalpha()` সব ভাষার alphabetic character গ্রহণ করতে পারে এবং hyphen, apostrophe বা digit গ্রহণ করে না। বাস্তব application-এ নাম যাচাইয়ের নিয়ম প্রয়োজন অনুযায়ী তৈরি করতে হবে।

## 10. Validating Multiple Inputs

একই লাইনে একাধিক value নেওয়ার সময় value-এর সংখ্যা ও data type যাচাই করা প্রয়োজন হতে পারে।

### Example: Three Integers

```python
try:
    values = list(map(int, input("Enter three integers: ").split()))

    if len(values) == 3:
        print("Numbers:", values)
        print("Total:", sum(values))
    else:
        print("Please enter exactly three integers.")

except ValueError:
    print("All values must be integers.")
```

Input:

```text
Enter three integers: 10 20 30
```

Output:

```text
Numbers: [10, 20, 30]
Total: 60
```

Input:

```text
Enter three integers: 10 20
```

Output:

```text
Please enter exactly three integers.
```

এখানে প্রথমে list তৈরি করা হয়েছে। তারপর `len(values)` দিয়ে element-এর সংখ্যা পরীক্ষা করা হয়েছে।

এটি সরাসরি unpacking করার চেয়ে সুবিধাজনক, কারণ value-এর সংখ্যা ভুল হলেও program সেটি পরীক্ষা করার সুযোগ পায়।

## 11. Repeating Input Until It Is Valid

কখনো একবার ভুল input দিলেই program বন্ধ করা উচিত নয়। বরং সঠিক input না পাওয়া পর্যন্ত আবার input নেওয়া যায়।

এ ক্ষেত্রে `while` loop ব্যবহার করা হয়।

### Example: Positive Integer

```python
while True:
    try:
        number = int(input("Enter a positive integer: "))

        if number > 0:
            print("Accepted:", number)
            break

        print("Number must be greater than zero.")

    except ValueError:
        print("Please enter a valid integer.")
```

Sample Interaction:

```text
Enter a positive integer: abc
Please enter a valid integer.
Enter a positive integer: -5
Number must be greater than zero.
Enter a positive integer: 10
Accepted: 10
```

এখানে:

- `while True` loop-টি বারবার চালায়।
- `try-except` ভুল numeric input handle করে।
- `if` positive number পরীক্ষা করে।
- `break` সঠিক input পেলে loop বন্ধ করে।

এই পদ্ধতি form, menu ও command-line program-এ কাজে লাগে।

## 12. Validating Yes/No Input

কখনো user-এর কাছ থেকে Yes বা No ধরনের উত্তর নিতে হয়।

### Example

```python
answer = input("Do you want to continue? (yes/no): ").strip().lower()

if answer == "yes":
    print("Continuing...")
elif answer == "no":
    print("Program stopped.")
else:
    print("Please enter yes or no.")
```

Input:

```text
Do you want to continue? (yes/no): YES
```

Output:

```text
Continuing...
```

এখানে:

- `.strip()` অতিরিক্ত শুরু ও শেষের whitespace সরায়।
- `.lower()` uppercase letter-কে lowercase করে।
- `if-elif-else` অনুমোদিত উত্তর পরীক্ষা করে।

তাই `YES`, `Yes` ও `yes` একইভাবে কাজ করবে।

## 13. Common Input Validation Mistakes

### Mistake 1: Assuming All Input Is Numeric

```python
age = int(input("Enter age: "))
```

সমস্যা: user text দিলে `ValueError` হবে।

সমাধান: প্রয়োজন অনুযায়ী `try-except` ব্যবহার করো।

### Mistake 2: Checking Only the Data Type

```python
age = int(input("Enter age: "))

if isinstance(age, int):
    print("Valid age")
```

সমস্যা: `-10`-ও integer, কিন্তু বয়স হিসেবে এটি গ্রহণযোগ্য নয়।

সমাধান: type-এর পাশাপাশি প্রয়োজনীয় range ও business rules যাচাই করো।

### Mistake 3: Checking Only the Range

```python
marks = int(input("Enter marks: "))

if 0 <= marks <= 100:
    print("Valid")
```

সমস্যা: input `abc` হলে range check-এর আগেই conversion ব্যর্থ হবে।

সমাধান: আগে conversion error handle করো, তারপর range check করো।

### Mistake 4: Using `bool()` to Validate Yes/No

```python
answer = input("Enter yes or no: ")

if bool(answer):
    print("Accepted")
```

সমস্যা: `"no"` একটি non-empty string, তাই `bool("no")` হলো `True`।

সমাধান: অনুমোদিত value-এর সঙ্গে সরাসরি তুলনা করো।

```python
answer = input("Enter yes or no: ").strip().lower()

if answer in ("yes", "no"):
    print("Accepted")
else:
    print("Invalid answer")
```

### Mistake 5: Catching Every Exception Without a Reason

```python
try:
    number = int(input("Enter a number: "))
except:
    print("Error")
```

সমস্যা: bare `except` অনেক অপ্রত্যাশিত exception-ও ধরে ফেলতে পারে।

সমাধান: যে error প্রত্যাশিত, সেটি নির্দিষ্ট করে handle করো।

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("Please enter a valid integer.")
```

## 14. Practice Exercises

### Exercise 1: Positive Number

একটি integer input নাও। সংখ্যা positive হলে `Valid` এবং অন্যথায় উপযুক্ত message দেখাও।

### Exercise 2: Marks Validation

0 থেকে 100-এর মধ্যে marks গ্রহণ করো। Range-এর বাইরে হলে error message দেখাও। Text input দিলে `ValueError` handle করো।

### Exercise 3: Empty Name

User-এর নাম input নাও। নাম empty বা শুধু whitespace হলে গ্রহণ করবে না।

### Exercise 4: Yes/No Validation

User-এর উত্তর `yes` অথবা `no` কি না পরীক্ষা করো। Uppercase ও lowercase উভয় input গ্রহণ করো।

### Exercise 5: Positive Decimal

একটি decimal number input নাও। সেটি valid এবং positive কি না পরীক্ষা করো।

### Exercise 6: Three Integers

এক লাইনে ঠিক তিনটি integer গ্রহণ করো। ভুল সংখ্যা বা non-integer input হলে উপযুক্ত message দেখাও।

### Exercise 7: Retry Until Valid

একটি positive integer না পাওয়া পর্যন্ত user-এর কাছ থেকে input নিতে থাকো।

### Exercise 8: Age Range

বয়স 0 থেকে 120-এর মধ্যে হলে গ্রহণ করো। অন্যথায় প্রত্যাখ্যান করো। Non-integer input-ও handle করো।

## 15. Practice Answer Key

### Answer 1

```python
try:
    number = int(input("Enter an integer: "))

    if number > 0:
        print("Valid")
    else:
        print("Number must be positive.")

except ValueError:
    print("Please enter a valid integer.")
```

### Answer 2

```python
try:
    marks = int(input("Enter marks (0-100): "))

    if 0 <= marks <= 100:
        print("Valid marks")
    else:
        print("Marks must be between 0 and 100.")

except ValueError:
    print("Please enter a whole number.")
```

### Answer 3

```python
name = input("Enter your name: ").strip()

if name:
    print("Hello,", name)
else:
    print("Name cannot be empty.")
```

### Answer 4

```python
answer = input("Enter yes or no: ").strip().lower()

if answer in ("yes", "no"):
    print("Valid answer")
else:
    print("Please enter yes or no.")
```

### Answer 5

```python
import math

try:
    number = float(input("Enter a positive decimal: "))

    if math.isfinite(number) and number > 0:
        print("Valid number")
    else:
        print("Enter a finite number greater than zero.")

except ValueError:
    print("Please enter a valid number.")
```

### Answer 6

```python
try:
    values = list(map(int, input("Enter three integers: ").split()))

    if len(values) == 3:
        print("Values:", values)
    else:
        print("Enter exactly three integers.")

except ValueError:
    print("All values must be integers.")
```

### Answer 7

```python
while True:
    try:
        number = int(input("Enter a positive integer: "))

        if number > 0:
            print("Accepted:", number)
            break

        print("Number must be positive.")

    except ValueError:
        print("Please enter a valid integer.")
```

### Answer 8

```python
try:
    age = int(input("Enter your age: "))

    if 0 <= age <= 120:
        print("Valid age")
    else:
        print("Age must be between 0 and 120.")

except ValueError:
    print("Please enter a whole number.")
```

## 16. Best Practices

1. User-এর input সবসময় যাচাই করার প্রয়োজন আছে কি না, তা program-এর requirements অনুযায়ী নির্ধারণ করো।
2. `int()` বা `float()` conversion ব্যর্থ হতে পারে—প্রয়োজনে `ValueError` handle করো।
3. Data type ঠিক হলেই input গ্রহণযোগ্য হয় না; range ও অন্যান্য rules-ও পরীক্ষা করো।
4. Empty text পরীক্ষা করার সময় `.strip()` ব্যবহার করতে পারো।
5. ভুল input হলে পরিষ্কার ও নির্দিষ্ট error message দেখাও।
6. বারবার input নেওয়ার প্রয়োজন হলে loop ব্যবহার করো।
7. অপ্রত্যাশিত error লুকানোর জন্য অকারণে bare `except` ব্যবহার করো না।
8. শুধু validation-এর ওপর নির্ভর না করে, গুরুত্বপূর্ণ application-এ server-side validation ও নিরাপত্তা যাচাইও করো।

## 17. Chapter Summary

- **Input validation:** input program-এর নিয়ম পূরণ করছে কি না পরীক্ষা করা।
- **Type validation:** input প্রয়োজনীয় data type-এ convert করা যায় কি না যাচাই করা।
- **Range validation:** value নির্দিষ্ট সীমার মধ্যে আছে কি না পরীক্ষা করা।
- **`try-except`:** conversion-এর মতো operation-এ প্রত্যাশিত error handle করা।
- **`.strip()`:** string-এর শুরু ও শেষের whitespace সরানো।
- **`.lower()`:** string-এর uppercase letter-কে lowercase করা।
- **`while` loop:** সঠিক input না পাওয়া পর্যন্ত আবার input নেওয়া।
- **`if-elif-else`:** input program-এর নিয়ম পূরণ করছে কি না পরীক্ষা করা।

## 18. Self-Assessment Checklist

- [ ] Input validation-এর উদ্দেশ্য বুঝি।
- [ ] Invalid integer ও float input handle করতে পারি।
- [ ] Positive number এবং range যাচাই করতে পারি।
- [ ] Empty input শনাক্ত করতে পারি।
- [ ] Yes/No input যাচাই করতে পারি।
- [ ] `try-except` দিয়ে `ValueError` handle করতে পারি।
- [ ] ভুল input হলে পুনরায় input নেওয়ার loop তৈরি করতে পারি।
- [ ] Type validation এবং range validation-এর পার্থক্য বুঝি।

**Next Topic:** `16_String_Concatenation_and_Repetition.md` — এখানে string যোগ করা, string বারবার ব্যবহার করা এবং `+` ও `*` operator দিয়ে text তৈরি করা শিখব।