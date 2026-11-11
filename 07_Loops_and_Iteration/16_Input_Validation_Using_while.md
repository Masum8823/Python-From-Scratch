# 16. Input Validation Using `while`

## 1. Introduction

**Input validation** হলো user-এর দেওয়া input নির্দিষ্ট নিয়ম বা শর্ত পূরণ করে কি না, তা পরীক্ষা করা।

User ভুল input দিলে program যেন ভুলভাবে কাজ না করে, সে জন্য input validation ব্যবহার করা হয়।

উদাহরণস্বরূপ, একটি program-এ বয়স `1` থেকে `120`-এর মধ্যে হতে হবে। User যদি `-5` দেয়, তাহলে program আবার input চাইবে।

```python
age = int(input("Enter your age: "))

while age < 1 or age > 120:
    print("Invalid age! Try again.")
    age = int(input("Enter your age: "))

print("Your age is:", age)
```

Sample Output:

```text
Enter your age: -5
Invalid age! Try again.
Enter your age: 150
Invalid age! Try again.
Enter your age: 21
Your age is: 21
```

এখানে `age < 1 or age > 120` condition `True` থাকা পর্যন্ত loop চলবে। Valid age দিলে condition `False` হয় এবং loop শেষ হয়।

**মনে রাখবে:** Input validation-এর মূল উদ্দেশ্য হলো ভুল বা গ্রহণযোগ্য নয় এমন input শনাক্ত করা এবং সঠিক input নেওয়া।

## 2. Why Is Input Validation Needed?

Input validation বিভিন্ন সমস্যার সমাধানে কাজে লাগে।

- Marks নির্দিষ্ট range-এর মধ্যে রাখা।
- Age-এর গ্রহণযোগ্য সীমা যাচাই করা।
- Menu থেকে valid option নির্বাচন করানো।
- Empty input গ্রহণ না করা।
- Positive number চাওয়া।
- User-কে ভুল input সংশোধনের সুযোগ দেওয়া।

উদাহরণ:

```python
marks = int(input("Enter marks (0-100): "))

while marks < 0 or marks > 100:
    print("Marks must be between 0 and 100.")
    marks = int(input("Enter marks again: "))

print("Accepted marks:", marks)
```

এই program-এ `0` ও `100` valid, কারণ condition-এ `< 0` এবং `> 100` ব্যবহার করা হয়েছে।

**সীমাবদ্ধতা:** এখানে ধরে নেওয়া হয়েছে user integer input দেবে। `abc` বা `12.5` দিলে `int()` থেকে `ValueError` হতে পারে। পরে exception handling অধ্যায়ে এ ধরনের error সামলানো শিখব।

## 3. General Structure of Input Validation

`while` দিয়ে input validation-এর সাধারণ structure:

```python
value = get_input()

while not_valid(value):
    print("Invalid input. Try again.")
    value = get_input()

# Valid input নিয়ে কাজ
```

এখানে:

1. প্রথমে input নেওয়া হয়।
2. Input valid কি না যাচাই করা হয়।
3. Invalid হলে loop body execute হয়।
4. User-এর কাছ থেকে নতুন input নেওয়া হয়।
5. Valid input পেলে loop বন্ধ হয়।
6. এরপর valid input নিয়ে কাজ করা হয়।

এখানে `not_valid(value)` কেবল ধারণা বোঝানোর জন্য লেখা হয়েছে; এটি Python-এর built-in function নয়।

## 4. Validating a Positive Number

ধরো, user-কে একটি positive integer দিতে হবে।

```python
number = int(input("Enter a positive integer: "))

while number <= 0:
    print("Invalid input!")
    number = int(input("Enter a positive integer: "))

print("Accepted:", number)
```

Sample Output:

```text
Enter a positive integer: -3
Invalid input!
Enter a positive integer: 0
Invalid input!
Enter a positive integer: 8
Accepted: 8
```

এখানে positive integer-এর জন্য শর্ত হলো `number > 0`। তাই `number <= 0` হলে input invalid হিসেবে ধরা হচ্ছে।

## 5. Validating a Number Within a Range

কোনো input নির্দিষ্ট range-এর মধ্যে আছে কি না, তা যাচাই করা একটি সাধারণ কাজ।

### Example: Marks Validation

```python
marks = int(input("Enter marks (0-100): "))

while marks < 0 or marks > 100:
    print("Invalid marks!")
    marks = int(input("Enter marks (0-100): "))

print("Marks accepted:", marks)
```

Valid range হলো `0` থেকে `100`, উভয় সীমাসহ।

| Input | Valid/Invalid | কারণ |
|---:|---|---|
| `-1` | Invalid | `0`-এর চেয়ে ছোট |
| `0` | Valid | সর্বনিম্ন সীমার সমান |
| `50` | Valid | Range-এর মধ্যে |
| `100` | Valid | সর্বোচ্চ সীমার সমান |
| `101` | Invalid | `100`-এর চেয়ে বড় |

### গুরুত্বপূর্ণ Logical Rule

Range-এর বাইরে থাকা বোঝাতে:

```python
marks < 0 or marks > 100
```

Range-এর মধ্যে থাকা বোঝাতে:

```python
marks >= 0 and marks <= 100
```

দুটি expression-এর অর্থ আলাদা। Input validation-এ কোন condition ব্যবহার করবে, তা বুঝে নিতে হবে।

## 6. Validating a Menu Choice

Menu-based program-এ user-কে নির্দিষ্ট option থেকে নির্বাচন করতে বলা হয়।

```python
choice = input("Choose A, B, or C: ").upper()

while choice not in ("A", "B", "C"):
    print("Invalid choice!")
    choice = input("Choose A, B, or C: ").upper()

print("You selected:", choice)
```

Sample Output:

```text
Choose A, B, or C: X
Invalid choice!
Choose A, B, or C: b
You selected: B
```

এখানে:

- `input()` string return করে।
- `.upper()` ছোট হাতের অক্ষরকে বড় হাতের অক্ষরে রূপান্তর করে।
- `choice not in ("A", "B", "C")` যাচাই করে input অনুমোদিত option-এর মধ্যে আছে কি না।

## 7. Validating Non-Empty Text

কখনো user যেন empty input দিতে না পারে, সেটি নিশ্চিত করতে হয়।

```python
name = input("Enter your name: ").strip()

while name == "":
    print("Name cannot be empty!")
    name = input("Enter your name: ").strip()

print("Hello,", name)
```

Sample Output:

```text
Enter your name:
Name cannot be empty!
Enter your name:    
Name cannot be empty!
Enter your name: Masum
Hello, Masum
```

এখানে `.strip()` string-এর শুরু ও শেষের whitespace সরিয়ে দেয়। তাই user শুধু space দিলেও input empty হিসেবে ধরা হয়।

**মনে রাখবে:** `.strip()` মূল string-কে পরিবর্তন না করে একটি নতুন string return করে। সেই returned value `name`-এ assign করা হয়েছে।

## 8. Validating a Password Length

ধরো, একটি learning program-এ password অন্তত ৮টি character-এর হতে হবে।

```python
password = input("Enter a password: ")

while len(password) < 8:
    print("Password must contain at least 8 characters.")
    password = input("Enter a password: ")

print("Password length accepted.")
```

Sample Output:

```text
Enter a password: abc
Password must contain at least 8 characters.
Enter a password: python123
Password length accepted.
```

এখানে `len(password)` password-এর character সংখ্যা গণনা করে।

**Security note:** এটি শুধু length validation-এর উদাহরণ। বাস্তব authentication system-এর জন্য password নিরাপদে সংরক্ষণ, rate limiting ও অন্যান্য security ব্যবস্থা প্রয়োজন।

## 9. Validating Integer Input with `isdigit()`

`isdigit()` দিয়ে পরীক্ষা করা যায় একটি string-এর সব character digit কি না।

```python
text = input("Enter a positive whole number: ")

while not text.isdigit():
    print("Invalid input!")
    text = input("Enter a positive whole number: ")

number = int(text)
print("Accepted number:", number)
```

Sample Output:

```text
Enter a positive whole number: hello
Invalid input!
Enter a positive whole number: 12
Accepted number: 12
```

এখানে প্রথমে string হিসেবে input নেওয়া হচ্ছে। `isdigit()` সত্য হলে সেটিকে `int`-এ convert করা হচ্ছে।

**সীমাবদ্ধতা:**

- `"-5".isdigit()` হলো `False`।
- `"3.5".isdigit()` হলো `False`।
- Empty string-এর জন্য `isdigit()` হলো `False`।
- কিছু Unicode digit character-ও `True` দিতে পারে।

তাই `isdigit()` সব ধরনের numeric input যাচাই করার universal পদ্ধতি নয়।

## 10. Combining Input Validation with Conditions

Input valid হওয়ার পর সেই input নিয়ে conditional statement ব্যবহার করা যায়।

```python
marks = int(input("Enter marks (0-100): "))

while marks < 0 or marks > 100:
    print("Invalid marks!")
    marks = int(input("Enter marks (0-100): "))

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

Sample Output:

```text
Enter marks (0-100): 120
Invalid marks!
Enter marks (0-100): 75
Pass
```

এখানে দুটি আলাদা কাজ হচ্ছে:

1. `while` loop valid marks নিশ্চিত করছে।
2. `if-else` result অনুযায়ী Pass বা Fail নির্ধারণ করছে।

**মূল ধারণা:** Input validation এবং program-এর main logic আলাদা রাখলে code বোঝা ও maintain করা সহজ হয়।

## 11. Avoiding Repeated Input Code with a Flag

কখনো validation loop-এ Boolean flag ব্যবহার করা যায়।

```python
valid = False

while not valid:
    number = int(input("Enter a number from 1 to 10: "))

    if 1 <= number <= 10:
        valid = True
    else:
        print("Invalid number!")

print("Accepted:", number)
```

এখানে:

- শুরুতে `valid = False`।
- Input range-এর মধ্যে থাকলে `valid = True` হয়।
- পরবর্তী condition check-এ `not valid` হয় `False`, তাই loop শেষ হয়।

এটি বোঝার একটি বিকল্প পদ্ধতি। সাধারণ range validation-এর ক্ষেত্রে সরাসরি `while number < 1 or number > 10` লিখলেও চলে।

এখানেও ধরে নেওয়া হয়েছে input integer হিসেবে convert করা যাবে।

## 12. Common Input Validation Mistakes

### Mistake 1: Using `and` Instead of `or`

ভুল:

```python
while marks < 0 and marks > 100:
    marks = int(input("Enter marks again: "))
```

একটি সাধারণ integer একই সঙ্গে `0`-এর ছোট এবং `100`-এর বড় হতে পারে না। তাই condition কখনো সত্য হবে না।

সঠিক:

```python
while marks < 0 or marks > 100:
    marks = int(input("Enter marks again: "))
```

### Mistake 2: Forgetting to Take New Input

ভুল:

```python
number = int(input("Enter a positive number: "))

while number <= 0:
    print("Try again.")
```

এখানে `number` update করা হচ্ছে না। Invalid value দিলে loop চলতেই থাকবে।

সঠিক:

```python
number = int(input("Enter a positive number: "))

while number <= 0:
    print("Try again.")
    number = int(input("Enter a positive number: "))
```

### Mistake 3: Incorrect Boundary Conditions

যদি `0` থেকে `100` পর্যন্ত উভয় সীমা valid হয়, তাহলে:

```python
while marks < 0 or marks > 100:
    ...
```

সঠিক। কিন্তু `marks <= 0` ব্যবহার করলে `0`-ও invalid হয়ে যাবে।

### Mistake 4: Converting Before Validating

```python
number = int(input("Enter a number: "))
```

User যদি `abc` দেয়, তাহলে validation loop শুরু হওয়ার আগেই `ValueError` হতে পারে।

এই chapter-এর integer validation উদাহরণগুলো ধরে নেয় input integer হিসেবে convert করা যাবে। Nonnumeric input সামলাতে `try-except` ব্যবহার করা হয়, যা exception handling অধ্যায়ে বিস্তারিত শেখা হবে।

### Mistake 5: Incorrectly Checking Empty Input

শুধু:

```python
while name == "":
    ...
```

ব্যবহার করলে space-only input ধরা পড়বে না। তাই সাধারণত:

```python
name = input("Enter your name: ").strip()

while name == "":
    print("Name cannot be empty.")
    name = input("Enter your name: ").strip()
```

ব্যবহার করা ভালো।

## 13. Practice Exercises

### Exercise 1

Input validation কী?

### Exercise 2

নিচের code-এ `marks = 105` দিলে কী হবে?

```python
marks = 105

while marks < 0 or marks > 100:
    print("Invalid marks!")
    marks = 80

print("Accepted:", marks)
```

### Exercise 3

কোন operator দিয়ে range-এর বাইরে থাকা condition পরীক্ষা করা হচ্ছে?

```python
while age < 1 or age > 120:
    ...
```

### Exercise 4

`0` থেকে `100` পর্যন্ত valid marks গ্রহণ করার program লেখো।

### Exercise 5

User `"A"`, `"B"` অথবা `"C"` না দেওয়া পর্যন্ত input নেওয়ার program লেখো। Lowercase input-ও গ্রহণ করতে হবে।

### Exercise 6

Empty বা space-only name গ্রহণ না করার program লেখো।

### Exercise 7

নিচের code-এ সমস্যা কী?

```python
marks = int(input("Enter marks: "))

while marks < 0 and marks > 100:
    marks = int(input("Enter marks again: "))
```

### Exercise 8

কেন `isdigit()` দিয়ে সরাসরি সব ধরনের number validate করা যায় না?

### Exercise 9

একটি integer `1` থেকে `10`-এর মধ্যে না আসা পর্যন্ত input নেওয়ার program লেখো।

## 14. Answer Key

### Exercise 1

Input validation হলো user-এর দেওয়া input নির্দিষ্ট নিয়ম বা শর্ত পূরণ করে কি না, তা পরীক্ষা করা।

### Exercise 2

Output:

```text
Invalid marks!
Accepted: 80
```

প্রথমে `105` invalid হওয়ায় loop চলে। এরপর `marks = 80` হওয়ায় condition `False` হয়।

### Exercise 3

`or` operator।

### Exercise 4

```python
marks = int(input("Enter marks (0-100): "))

while marks < 0 or marks > 100:
    print("Invalid marks!")
    marks = int(input("Enter marks (0-100): "))

print("Accepted:", marks)
```

### Exercise 5

```python
choice = input("Choose A, B, or C: ").upper()

while choice not in ("A", "B", "C"):
    print("Invalid choice!")
    choice = input("Choose A, B, or C: ").upper()

print("Selected:", choice)
```

### Exercise 6

```python
name = input("Enter your name: ").strip()

while name == "":
    print("Name cannot be empty!")
    name = input("Enter your name: ").strip()

print("Hello,", name)
```

### Exercise 7

`and` ভুলভাবে ব্যবহার করা হয়েছে। কোনো সাধারণ integer একই সঙ্গে `0`-এর ছোট ও `100`-এর বড় হতে পারে না। এখানে `or` ব্যবহার করতে হবে।

### Exercise 8

`isdigit()` negative sign বা decimal point গ্রহণ করে না। যেমন `"-5"` এবং `"3.5"`-এর জন্য এটি `False` দেয়।

### Exercise 9

```python
number = int(input("Enter a number from 1 to 10: "))

while number < 1 or number > 10:
    print("Invalid number!")
    number = int(input("Enter a number from 1 to 10: "))

print("Accepted:", number)
```

এই উদাহরণে ধরে নেওয়া হয়েছে user integer input দেবে।

## 15. Chapter Progress Checklist

- [ ] Input validation-এর উদ্দেশ্য বুঝেছি।
- [ ] `while` loop দিয়ে invalid input পুনরায় নিতে পারি।
- [ ] Numeric range যাচাই করতে পারি।
- [ ] Menu choice validate করতে পারি।
- [ ] Empty ও whitespace-only text শনাক্ত করতে পারি।
- [ ] `isdigit()`-এর সীমাবদ্ধতা বুঝেছি।
- [ ] `and` ও `or` সঠিকভাবে ব্যবহার করতে পারি।
- [ ] Validation loop-এ নতুন input নিতে ভুল করি না।

## 16. Summary

- Input validation ভুল বা গ্রহণযোগ্য নয় এমন input শনাক্ত করে।
- `while` loop ব্যবহার করে valid input না পাওয়া পর্যন্ত আবার input নেওয়া যায়।
- Range validation-এ boundary conditions সঠিকভাবে লিখতে হয়।
- Range-এর বাইরে থাকা যাচাই করতে প্রায়ই `or` ব্যবহার করা হয়।
- `.strip()` space-only text শনাক্ত করতে সাহায্য করে।
- `isdigit()` শুধু নির্দিষ্ট ধরনের digit string যাচাই করে।
- `int()` বা `float()` conversion ব্যর্থ হলে exception handling প্রয়োজন হতে পারে।

**Next Topic:** `17_Infinite_while_Loops.md`
