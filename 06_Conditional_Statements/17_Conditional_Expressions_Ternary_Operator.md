# 17. Conditional Expressions (Ternary Operator)

## 1. Conditional Expression কী?

Python-এ **Conditional Expression** ব্যবহার করে কোনো condition-এর ওপর ভিত্তি করে দুটি value-এর মধ্যে একটি নির্বাচন করা যায়।

এটিকে সাধারণভাবে **Ternary Operator** বলা হয়।

সহজভাবে বললে, ছোট `if-else` statement-কে এক লাইনে লেখার একটি পদ্ধতি হলো Ternary Operator।

সাধারণ `if-else`:

```python
age = 20

if age >= 18:
    status = "Adult"
else:
    status = "Minor"

print(status)
```

Output:

```text
Adult
```

একই কাজ Ternary Operator দিয়ে:

```python
age = 20

status = "Adult" if age >= 18 else "Minor"

print(status)
```

Output:

```text
Adult
```

দুটি program-এর result একই। তবে দ্বিতীয় program-এ condition এবং দুটি possible value এক লাইনে লেখা হয়েছে।

## 2. Ternary Operator-এর Syntax

Python-এ Conditional Expression-এর syntax হলো:

```python
value_if_true if condition else value_if_false
```

এখানে তিনটি গুরুত্বপূর্ণ অংশ রয়েছে:

| অংশ | কাজ |
|---|---|
| `value_if_true` | Condition True হলে এই value নেওয়া হবে |
| `condition` | যে condition পরীক্ষা করা হবে |
| `value_if_false` | Condition False হলে এই value নেওয়া হবে |

উদাহরণ:

```python
number = 10

result = "Positive" if number > 0 else "Not positive"

print(result)
```

Output:

```text
Positive
```

কারণ `number > 0` True। তাই `"Positive"` value-টি `result`-এ assign হয়েছে।

**মনে রাখবে:** Python-এ `if`-এর পর condition, তারপর True-এর value, এবং `else`-এর পরে False-এর value লেখা হয়।

## 3. Ternary Operator কীভাবে কাজ করে?

ধাপে ধাপে একটি উদাহরণ দেখি:

```python
marks = 75

result = "Pass" if marks >= 40 else "Fail"

print(result)
```

Output:

```text
Pass
```

কাজের ধাপ:

1. Python প্রথমে `marks >= 40` condition পরীক্ষা করে।
2. Condition True হওয়ায় `"Pass"` value নির্বাচন করে।
3. `"Pass"` value-টি `result` variable-এ assign হয়।
4. `print(result)` output দেখায়।

এবার marks পরিবর্তন করি:

```python
marks = 30

result = "Pass" if marks >= 40 else "Fail"

print(result)
```

Output:

```text
Fail
```

এবার condition False হওয়ায় `"Fail"` নির্বাচন হয়েছে।

## 4. Ternary Operator দিয়ে Maximum Number বের করা

দুটি সংখ্যার মধ্যে বড় সংখ্যা বের করার জন্য এটি ব্যবহার করা যায়।

```python
a = 15
b = 25

maximum = a if a > b else b

print(maximum)
```

Output:

```text
25
```

ব্যাখ্যা:

- `a > b` অর্থাৎ `15 > 25` হলো False।
- তাই `else`-এর পরের value `b` নির্বাচন হয়েছে।
- `maximum`-এর value হয়েছে `25`।

একইভাবে minimum number বের করা যায়:

```python
a = 15
b = 25

minimum = a if a < b else b

print(minimum)
```

Output:

```text
15
```

**সতর্কতা:** উপরের maximum উদাহরণে দুটি সংখ্যা সমান হলেও `b` নির্বাচন হবে। সমান সংখ্যার ক্ষেত্রে কোন value নির্বাচন করতে হবে, সেটি প্রয়োজন অনুযায়ী নির্ধারণ করবে।

## 5. Even এবং Odd নির্ণয়

কোনো সংখ্যা জোড় নাকি বিজোড়, তা নির্ণয় করতেও Conditional Expression ব্যবহার করা যায়।

```python
number = 7

result = "Even" if number % 2 == 0 else "Odd"

print(result)
```

Output:

```text
Odd
```

ব্যাখ্যা:

- `number % 2 == 0` পরীক্ষা করে সংখ্যাটি ২ দিয়ে নিঃশেষে বিভাজ্য কি না।
- `7 % 2` হলো `1`।
- Condition False হওয়ায় `"Odd"` নির্বাচন হয়েছে।

আরেকটি উদাহরণ:

```python
number = 12

result = "Even" if number % 2 == 0 else "Odd"

print(result)
```

Output:

```text
Even
```

## 6. Positive, Negative এবং Zero নির্ণয়

Ternary Operator দিয়ে দুটি সম্ভাব্য result নির্বাচন করা সহজ। তবে তিনটি বা তার বেশি category থাকলে nested Conditional Expression ব্যবহার করা যায়।

উদাহরণ:

```python
number = -5

result = "Positive" if number > 0 else (
    "Negative" if number < 0 else "Zero"
)

print(result)
```

Output:

```text
Negative
```

এখানে:

- `number > 0` True হলে `"Positive"`।
- প্রথম condition False হলে দ্বিতীয় condition `number < 0` পরীক্ষা হবে।
- দ্বিতীয় condition True হলে `"Negative"`।
- দুটি condition-ই False হলে `"Zero"`।

এই উদাহরণে nested expression কাজ করলেও, নতুনদের জন্য সাধারণ `if-elif-else` বেশি পরিষ্কার:

```python
number = -5

if number > 0:
    result = "Positive"
elif number < 0:
    result = "Negative"
else:
    result = "Zero"

print(result)
```

Output:

```text
Negative
```

**Best practice:** তিন বা তার বেশি condition থাকলে সাধারণত `if-elif-else` ব্যবহার করো।

## 7. User Input-এর সঙ্গে Ternary Operator

User-এর দেওয়া input-এর ভিত্তিতে result নির্বাচন করা যায়।

```python
age = int(input("Enter your age: "))

status = "Eligible" if age >= 18 else "Not eligible"

print(status)
```

Input:

```text
20
```

Output:

```text
Eligible
```

এখানে `int()` ব্যবহার করা হয়েছে, কারণ `input()` string return করে এবং আমরা বয়সকে integer হিসেবে তুলনা করছি।

যদি user সংখ্যা ছাড়া অন্য input দেয়, তাহলে `int()`-এ `ValueError` হতে পারে। Input validation শেখার সময় এ ধরনের error সামলানো শিখব।

## 8. Ternary Operator এবং Truthiness

Ternary Operator-এ condition হিসেবে শুধু comparison নয়, Truthy বা Falsy value-ও ব্যবহার করা যায়।

উদাহরণ:

```python
name = ""

message = name if name else "Guest"

print(message)
```

Output:

```text
Guest
```

কারণ `name` একটি empty string, যা Falsy। তাই `"Guest"` নির্বাচন হয়েছে।

আরেকটি উদাহরণ:

```python
items = [10, 20, 30]

message = "Items found" if items else "No items"

print(message)
```

Output:

```text
Items found
```

কারণ list-টি empty নয়, তাই এটি Truthy।

## 9. Ternary Operator দিয়ে Discount নির্ধারণ

একটি দোকানে ১০০০ টাকা বা তার বেশি কেনাকাটা করলে discount পাওয়া যাবে।

```python
amount = 1500

discount = 100 if amount >= 1000 else 0

print(discount)
```

Output:

```text
100
```

এখানে:

- Amount ১০০০ বা তার বেশি হলে discount `100`।
- অন্যথায় discount `0`।

এবার মোট মূল্য থেকে discount বাদ দিই:

```python
amount = 1500

discount = 100 if amount >= 1000 else 0
total = amount - discount

print(total)
```

Output:

```text
1400
```

এটি একটি সাধারণ learning example। বাস্তব discount system-এ percentage, eligibility rules এবং currency calculations আরও বিস্তারিত হতে পারে।

## 10. Nested Ternary Operator

একটি Conditional Expression-এর মধ্যে আরেকটি Conditional Expression ব্যবহার করলে তাকে Nested Ternary Expression বলা হয়।

উদাহরণ:

```python
marks = 85

grade = "A" if marks >= 80 else (
    "B" if marks >= 60 else "C"
)

print(grade)
```

Output:

```text
A
```

এখানে:

1. `marks >= 80` পরীক্ষা করা হয়।
2. True হওয়ায় `"A"` নির্বাচন হয়।
3. দ্বিতীয় condition পরীক্ষা করার প্রয়োজন হয় না।

Marks `70` হলে:

```python
marks = 70

grade = "A" if marks >= 80 else (
    "B" if marks >= 60 else "C"
)

print(grade)
```

Output:

```text
B
```

কারণ প্রথম condition False, কিন্তু `marks >= 60` True।

Nested Ternary ছোট expression-এ ব্যবহার করা যায়। তবে বেশি nested হলে code পড়া ও debugging কঠিন হয়।

## 11. Ternary Operator বনাম `if-else`

| বিষয় | Ternary Operator | সাধারণ `if-else` |
|---|---|---|
| গঠন | সাধারণত এক লাইনে | একাধিক লাইনে |
| ব্যবহার | ছোট expression | ছোট ও জটিল logic |
| Value নির্বাচন | সহজে করা যায় | statement-এর মাধ্যমে করা যায় |
| Readability | ছোট condition-এ ভালো | জটিল condition-এ সাধারণত ভালো |
| একাধিক কাজ | সীমিত ও কম উপযোগী | একাধিক statement চালানো যায় |

একটি গুরুত্বপূর্ণ পার্থক্য হলো, Ternary Operator একটি **expression**—এটি একটি value তৈরি করে। অন্যদিকে `if-else` হলো একটি **statement**, যা এক বা একাধিক statement execute করতে পারে।

উদাহরণ:

```python
age = 20

message = "Adult" if age >= 18 else "Minor"
```

এখানে expression-এর result `message`-এ assign হচ্ছে।

সাধারণ `if-else`:

```python
age = 20

if age >= 18:
    print("Adult")
    print("Eligible for adult category")
else:
    print("Minor")
```

এখানে একটি branch-এর মধ্যে একাধিক statement execute করা হচ্ছে।

## 12. Common Mistakes

### Mistake 1: Syntax-এর order ভুল লেখা

ভুল:

```python
result = if age >= 18 "Adult" else "Minor"
```

এটি SyntaxError তৈরি করবে।

সঠিক:

```python
result = "Adult" if age >= 18 else "Minor"
```

### Mistake 2: `else` বাদ দেওয়া

ভুল:

```python
result = "Adult" if age >= 18
```

Python-এর Conditional Expression-এ `else` বাধ্যতামূলক।

সঠিক:

```python
result = "Adult" if age >= 18 else "Minor"
```

### Mistake 3: Condition-এর বদলে ভুল value নির্বাচন

```python
number = 5

result = "Odd" if number % 2 == 0 else "Even"

print(result)
```

Output:

```text
Odd
```

এখানে code-এর label উল্টো দেওয়া হয়েছে। Condition True হলে সংখ্যাটি Even হওয়ার কথা, কিন্তু `"Odd"` লেখা হয়েছে।

সঠিক:

```python
result = "Even" if number % 2 == 0 else "Odd"
```

### Mistake 4: অতিরিক্ত Nested Ternary ব্যবহার

অনেক condition এক লাইনে লিখলে logic বোঝা কঠিন হতে পারে।

যদি logic জটিল হয়, তাহলে `if-elif-else` ব্যবহার করো।

### Mistake 5: Ternary-কে সব ক্ষেত্রে ভালো মনে করা

এক লাইনের code সবসময় বেশি readable নয়। Code ছোট করার চেয়ে code সহজে বোঝা যায় কি না, সেটি বেশি গুরুত্বপূর্ণ।

## 13. Practice Exercises

প্রতিটি প্রশ্নের output নিজে বের করার চেষ্টা করো।

### Question 1

```python
x = 10

result = "Big" if x > 5 else "Small"

print(result)
```

### Question 2

```python
number = 9

result = "Even" if number % 2 == 0 else "Odd"

print(result)
```

### Question 3

```python
age = 16

status = "Adult" if age >= 18 else "Minor"

print(status)
```

### Question 4

```python
a = 20
b = 10

maximum = a if a > b else b

print(maximum)
```

### Question 5

```python
name = ""

result = name if name else "Unknown"

print(result)
```

### Question 6

```python
marks = 65

grade = "A" if marks >= 80 else (
    "B" if marks >= 60 else "C"
)

print(grade)
```

### Question 7

```python
number = 0

result = "Positive" if number > 0 else (
    "Negative" if number < 0 else "Zero"
)

print(result)
```

### Question 8

```python
items = []

message = "Available" if items else "Empty"

print(message)
```

## 14. Answer Key

**Question 1**

```text
Big
```

কারণ `10 > 5` True।

**Question 2**

```text
Odd
```

কারণ `9 % 2` হলো `1`।

**Question 3**

```text
Minor
```

কারণ বয়স ১৮-এর কম।

**Question 4**

```text
20
```

কারণ `a > b` True।

**Question 5**

```text
Unknown
```

কারণ empty string Falsy।

**Question 6**

```text
B
```

কারণ `marks >= 80` False, কিন্তু `marks >= 60` True।

**Question 7**

```text
Zero
```

কারণ সংখ্যাটি positive-ও নয়, negative-ও নয়।

**Question 8**

```text
Empty
```

কারণ empty list Falsy।

## 15. Quick Revision

- **Conditional Expression:** Condition অনুযায়ী দুটি value-এর মধ্যে একটি নির্বাচন করে।
- **Ternary Operator:** ছোট `if-else` expression এক লাইনে লেখার পদ্ধতি।
- **Syntax:** `value_if_true if condition else value_if_false`
- Condition True হলে `if`-এর আগের value নির্বাচিত হয়।
- Condition False হলে `else`-এর পরের value নির্বাচিত হয়।
- Nested Ternary ব্যবহার করা যায়, তবে বেশি জটিল হলে `if-elif-else` ভালো।
- Ternary Operator একটি expression; এটি value তৈরি করে।
- Readability বজায় রাখা সবসময় গুরুত্বপূর্ণ।

## 16. Self-Assessment Checklist

- [ ] Conditional Expression-এর অর্থ বুঝি।
- [ ] Ternary Operator-এর syntax লিখতে পারি।
- [ ] Condition True ও False হলে কোন value নির্বাচন হবে, তা বুঝি।
- [ ] Even/Odd এবং maximum number-এর মতো সমস্যা সমাধান করতে পারি।
- [ ] Nested Ternary বুঝতে পারি।
- [ ] কখন Ternary ব্যবহার করব এবং কখন `if-else` ব্যবহার করব, তা বুঝি।
- [ ] Common syntax mistakes শনাক্ত করতে পারি।

**পরবর্তী টপিক:** `18_Nested_Conditional_Expressions.md`
