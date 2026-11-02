# 28. Conditional Expressions in Python

## 1. Conditional Expression কী?

**Conditional Expression** হলো এমন একটি expression, যার condition সত্য বা মিথ্যা হওয়ার ওপর নির্ভর করে দুটি value-এর মধ্যে একটি নির্বাচন করা হয়।

Python-এ একে অনেক সময় **Ternary Operator** বা **Ternary Conditional Expression** বলা হয়।

### Syntax

```python
value_if_true if condition else value_if_false
```

এখানে:

- `condition`: যে শর্ত পরীক্ষা করা হবে।
- `value_if_true`: condition সত্য হলে যে value পাওয়া যাবে।
- `value_if_false`: condition মিথ্যা হলে যে value পাওয়া যাবে।

### Example

```python
age = 20

status = "Adult" if age >= 18 else "Minor"

print(status)
```

**Output:**

```text
Adult
```

ব্যাখ্যা:

1. `age >= 18` condition পরীক্ষা করা হয়।
2. Condition সত্য, কারণ `age` হলো `20`।
3. তাই `"Adult"` value-টি `status` variable-এ assign হয়।

যদি `age = 15` হতো, তাহলে output হতো:

```text
Minor
```

---

## 2. Conditional Expression কীভাবে কাজ করে?

Conditional expression-এ condition প্রথমে পরীক্ষা করা হয়। এরপর condition-এর ফল অনুযায়ী একটি value নির্বাচন করা হয়।

### Example

```python
number = 7

result = "Positive" if number > 0 else "Not Positive"

print(result)
```

**Output:**

```text
Positive
```

এখানে `number > 0` সত্য, তাই `"Positive"` নির্বাচন করা হয়েছে।

আরেকটি উদাহরণ:

```python
number = -3

result = "Positive" if number > 0 else "Not Positive"

print(result)
```

**Output:**

```text
Not Positive
```

এখানে condition মিথ্যা, তাই `else`-এর পরের value নির্বাচন করা হয়েছে।

**মনে রাখবে:** Conditional expression একটি value তৈরি করে। তাই এটি variable-এ assign করা যায়, function-এ argument হিসেবে পাঠানো যায় অথবা অন্য expression-এর মধ্যে ব্যবহার করা যায়।

---

## 3. Conditional Expression vs if-else Statement

Conditional expression এবং `if-else` statement একই ধরনের সিদ্ধান্ত নিতে পারে, কিন্তু তাদের ব্যবহার এক নয়।

### Using if-else Statement

```python
age = 20

if age >= 18:
    status = "Adult"
else:
    status = "Minor"

print(status)
```

**Output:**

```text
Adult
```

### Using Conditional Expression

```python
age = 20

status = "Adult" if age >= 18 else "Minor"

print(status)
```

**Output:**

```text
Adult
```

দুটি code-এর output একই।

| বিষয় | `if-else` Statement | Conditional Expression |
|---|---|---|
| ব্যবহার | সিদ্ধান্ত নেওয়া ও বিভিন্ন কাজ করা | condition অনুযায়ী value নির্বাচন |
| Structure | একাধিক statement থাকতে পারে | একটি expression |
| Syntax | একাধিক লাইনে লেখা হয় | সাধারণত এক লাইনে লেখা হয় |
| Best use | জটিল logic | সহজ value selection |

**কোনটি ব্যবহার করবে?**

- শুধু দুটি value-এর মধ্যে একটি নির্বাচন করতে হলে conditional expression ব্যবহার করতে পারো।
- একাধিক কাজ, জটিল logic বা অনেকগুলো branch থাকলে `if-elif-else` ব্যবহার করো।

---

## 4. Conditional Expression with Numbers

সংখ্যা তুলনা করে conditional expression ব্যবহার করা যায়।

### Example 1: Even or Odd

```python
number = 8

result = "Even" if number % 2 == 0 else "Odd"

print(result)
```

**Output:**

```text
Even
```

ব্যাখ্যা:

- `number % 2 == 0` হলে সংখ্যাটি জোড়।
- Condition সত্য হলে `"Even"` নির্বাচন হয়।
- অন্যথায় `"Odd"` নির্বাচন হয়।

### Example 2: Positive or Negative

```python
number = -5

result = "Positive" if number > 0 else "Negative or Zero"

print(result)
```

**Output:**

```text
Negative or Zero
```

এখানে `number > 0` মিথ্যা।

খেয়াল করো, এই code-এ শূন্যকেও `"Negative or Zero"` বলা হচ্ছে। শূন্যকে আলাদাভাবে চিহ্নিত করতে চাইলে আরও একটি condition দরকার।

### Example 3: Maximum of Two Numbers

```python
a = 15
b = 10

maximum = a if a > b else b

print(maximum)
```

**Output:**

```text
15
```

এখানে `a > b` সত্য, তাই `a`-এর value নির্বাচন করা হয়েছে।

### Example 4: Minimum of Two Numbers

```python
a = 15
b = 10

minimum = a if a < b else b

print(minimum)
```

**Output:**

```text
10
```

---

## 5. Conditional Expression with Strings

Condition অনুযায়ী string নির্বাচন করতেও এটি ব্যবহার করা যায়।

### Example 1: Pass or Fail

```python
marks = 75

result = "Pass" if marks >= 40 else "Fail"

print(result)
```

**Output:**

```text
Pass
```

### Example 2: Login Status

```python
is_logged_in = True

message = "Welcome" if is_logged_in else "Please log in"

print(message)
```

**Output:**

```text
Welcome
```

### Example 3: Discount Eligibility

```python
purchase_amount = 1500

discount = "Eligible" if purchase_amount >= 1000 else "Not Eligible"

print(discount)
```

**Output:**

```text
Eligible
```

এ ধরনের expression ছোট সিদ্ধান্তগুলো সহজে প্রকাশ করতে সাহায্য করে।

---

## 6. Conditional Expression with Function Calls

Conditional expression-এর মাধ্যমে কোন function call করা হবে, সেটিও নির্বাচন করা যায়।

### Example

```python
number = 5

result = abs(number) if number < 0 else number

print(result)
```

**Output:**

```text
5
```

এখানে condition মিথ্যা, তাই `else`-এর value `number` নির্বাচন করা হয়েছে। `abs(number)` call করার প্রয়োজন হয়নি।

আরেকটি উদাহরণ:

```python
def greet():
    return "Hello"

def welcome():
    return "Welcome"

is_new_user = True

message = greet() if is_new_user else welcome()

print(message)
```

**Output:**

```text
Hello
```

এখানে condition সত্য, তাই `greet()` call করা হয়েছে।

---

## 7. Nested Conditional Expressions

একটি conditional expression-এর ভেতরে আরেকটি conditional expression ব্যবহার করলে তাকে **Nested Conditional Expression** বলা হয়।

### Example: Positive, Negative or Zero

```python
number = 0

result = "Positive" if number > 0 else "Negative" if number < 0 else "Zero"

print(result)
```

**Output:**

```text
Zero
```

এটি এভাবে group করা হয়:

```python
result = (
    "Positive"
    if number > 0
    else ("Negative" if number < 0 else "Zero")
)
```

ধাপে ধাপে:

1. `number > 0` পরীক্ষা করা হয়।
2. Condition মিথ্যা, তাই পরের conditional expression পরীক্ষা করা হয়।
3. `number < 0`-ও মিথ্যা।
4. তাই `"Zero"` নির্বাচন করা হয়।

### Example: Grade Selection

```python
marks = 85

grade = "A" if marks >= 80 else "B" if marks >= 70 else "C"

print(grade)
```

**Output:**

```text
A
```

প্রথম condition সত্য হওয়ায় `"A"` নির্বাচন করা হয়েছে।

### Nested Expression-এর সতর্কতা

অনেকগুলো nested conditional expression এক লাইনে লিখলে code বোঝা কঠিন হতে পারে।

জটিল ক্ষেত্রে `if-elif-else` ব্যবহার করা ভালো:

```python
marks = 85

if marks >= 80:
    grade = "A"
elif marks >= 70:
    grade = "B"
else:
    grade = "C"

print(grade)
```

**Output:**

```text
A
```

এটি বড় decision-making logic-এর জন্য বেশি readable।

---

## 8. Conditional Expression and Operator Precedence

Conditional expression-এর নিজস্ব precedence আছে। এটি সাধারণ arithmetic operator-এর চেয়ে কম precedence অনুসরণ করে।

তবে জটিল expression-এ parentheses ব্যবহার করলে code আরও পরিষ্কার হয়।

### Example 1

```python
result = 10 + 5 if True else 10 - 5

print(result)
```

**Output:**

```text
15
```

Condition সত্য হওয়ায় `10 + 5` নির্বাচন করা হয়েছে।

### Example 2

```python
result = (10 + 5) if False else (10 - 5)

print(result)
```

**Output:**

```text
5
```

Condition মিথ্যা হওয়ায় `else`-এর expression নির্বাচন করা হয়েছে।

### Example 3: Arithmetic inside a Condition

```python
a = 5
b = 3

result = a + b if a > b else a - b

print(result)
```

**Output:**

```text
8
```

এখানে `a > b` সত্য, তাই `a + b` হিসাব করা হয়েছে।

---

## 9. Truthy and Falsy Values in Conditional Expressions

Conditional expression-এ condition হিসেবে শুধু comparison ব্যবহার করতে হয় না। যেকোনো expression ব্যবহার করা যায়, যার truth value নির্ধারণ করা সম্ভব।

### Example 1: Empty String

```python
name = ""

message = name if name else "Unknown"

print(message)
```

**Output:**

```text
Unknown
```

Empty string `""` হলো falsy value।

### Example 2: Non-empty String

```python
name = "Masum"

message = name if name else "Unknown"

print(message)
```

**Output:**

```text
Masum
```

Non-empty string truthy হওয়ায় `name` নির্বাচন করা হয়েছে।

### Example 3: Zero

```python
number = 0

result = number if number else 100

print(result)
```

**Output:**

```text
100
```

এখানে `0` falsy হওয়ায় `else`-এর value নির্বাচন করা হয়েছে।

**সতর্কতা:** যদি `0`-ও একটি valid value হয় এবং শুধু `None`-এর ক্ষেত্রে default value দিতে চাও, তাহলে truthiness-এর পরিবর্তে explicit comparison ব্যবহার করো।

```python
number = 0

result = number if number is not None else 100

print(result)
```

**Output:**

```text
0
```

এখানে `number` শূন্য হলেও `None` নয়, তাই `0`-ই রাখা হয়েছে।

---

## 10. Common Mistakes

### Mistake 1: Syntax-এর Order ভুল করা

ভুল:

```python
result = if age >= 18 "Adult" else "Minor"
```

এটি invalid syntax।

সঠিক:

```python
result = "Adult" if age >= 18 else "Minor"
```

Conditional expression-এর সঠিক structure:

```python
value_if_true if condition else value_if_false
```

### Mistake 2: `else` বাদ দেওয়া

ভুল:

```python
result = "Pass" if marks >= 40
```

Conditional expression-এ `else` অংশ আবশ্যক।

সঠিক:

```python
result = "Pass" if marks >= 40 else "Fail"
```

### Mistake 3: Nested Expression ভুল বোঝা

```python
x = 5

result = "A" if x > 10 else "B" if x > 3 else "C"

print(result)
```

**Output:**

```text
B
```

প্রথম condition মিথ্যা হলেও পরের conditional expression পরীক্ষা করা হয়।

### Mistake 4: Zero-কে Falsy ধরে ভুল সিদ্ধান্ত নেওয়া

```python
score = 0

result = score if score else 50

print(result)
```

**Output:**

```text
50
```

এটি `score` শূন্য কি না, তা পরীক্ষা করছে না; বরং `score` truthy কি না, তা পরীক্ষা করছে।

---

## 11. Practice Exercises

প্রথমে নিজে output অনুমান করো। তারপর Answer Key মিলিয়ে দেখো।

### Exercise 1

```python
age = 17

status = "Adult" if age >= 18 else "Minor"

print(status)
```

### Exercise 2

```python
number = 11

result = "Even" if number % 2 == 0 else "Odd"

print(result)
```

### Exercise 3

```python
a = 25
b = 40

maximum = a if a > b else b

print(maximum)
```

### Exercise 4

```python
marks = 35

result = "Pass" if marks >= 40 else "Fail"

print(result)
```

### Exercise 5

```python
number = -8

result = "Positive" if number > 0 else "Negative" if number < 0 else "Zero"

print(result)
```

### Exercise 6

```python
name = ""

result = name if name else "Guest"

print(result)
```

### Exercise 7

```python
x = 10

result = "High" if x > 10 else "Equal" if x == 10 else "Low"

print(result)
```

### Exercise 8

```python
value = 0

result = value if value is not None else 100

print(result)
```

### Answer Key

| Exercise | Output | Explanation |
|---|---|---|
| 1 | `Minor` | `17 >= 18` মিথ্যা |
| 2 | `Odd` | `11 % 2` হলো `1` |
| 3 | `40` | `a > b` মিথ্যা |
| 4 | `Fail` | `35 >= 40` মিথ্যা |
| 5 | `Negative` | সংখ্যা শূন্যের চেয়ে ছোট |
| 6 | `Guest` | Empty string falsy |
| 7 | `Equal` | `x == 10` সত্য |
| 8 | `0` | `0 is not None` সত্য |

---

## 12. Quick Revision

- Conditional expression condition অনুযায়ী একটি value নির্বাচন করে।
- এর syntax: `value_if_true if condition else value_if_false`।
- একে Ternary Conditional Expression-ও বলা হয়।
- সাধারণত ছোট ও সহজ decision-এর জন্য ব্যবহার করা হয়।
- Nested conditional expression সম্ভব, কিন্তু অতিরিক্ত nested হলে readability কমে।
- Empty string এবং `0`-এর মতো falsy value ব্যবহারের সময় সতর্ক থাকতে হবে।
- Conditional expression-এ `else` অংশ আবশ্যক।
- জটিল decision-making logic-এর জন্য `if-elif-else` বেশি পরিষ্কার হতে পারে।

## 13. Self-Assessment Checklist

- [ ] Conditional expression-এর syntax লিখতে পারি।
- [ ] `if-else` statement ও conditional expression-এর পার্থক্য বুঝি।
- [ ] সংখ্যার ওপর condition প্রয়োগ করতে পারি।
- [ ] Maximum ও minimum নির্বাচন করতে পারি।
- [ ] Nested conditional expression বুঝতে পারি।
- [ ] Truthy ও falsy value-এর ব্যবহার বুঝি।
- [ ] Conditional expression-এর common syntax error শনাক্ত করতে পারি।
- [ ] জটিল expression-এর বদলে কখন `if-elif-else` ব্যবহার করতে হবে বুঝি।

পরবর্তী Topic: **29. Operator Overloading Introduction**