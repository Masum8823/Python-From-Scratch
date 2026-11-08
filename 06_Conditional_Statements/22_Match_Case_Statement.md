# 22. Match-Case Statement

## 1. Match-Case Statement কী?

Python-এ `match-case` হলো একটি control flow statement, যা কোনো value বা structure-এর সঙ্গে বিভিন্ন pattern মিলিয়ে উপযুক্ত code execute করতে সাহায্য করে।

এটি Python 3.10 থেকে চালু হয়েছে।

যখন কোনো variable-এর value অনুযায়ী অনেকগুলো নির্দিষ্ট option-এর মধ্যে একটি নির্বাচন করতে হয়, তখন `match-case` ব্যবহার করা যায়।

উদাহরণ:

```python
day = 2

match day:
    case 1:
        print("Sunday")
    case 2:
        print("Monday")
    case 3:
        print("Tuesday")
    case _:
        print("Invalid day")
```

Output:

```text
Monday
```

এখানে:

- `match day` — `day`-এর value পরীক্ষা করা হচ্ছে।
- `case 1` — value `1`-এর সঙ্গে মিলিয়ে দেখা হচ্ছে।
- `case 2` — value `2`-এর সঙ্গে মিলিয়ে দেখা হচ্ছে।
- `case _` — অন্য কোনো pattern না মিললে এটি match করতে পারে।

যেহেতু `day = 2`, তাই `case 2`-এর code execute হয়েছে।

## 2. Match-Case-এর Syntax

সাধারণ syntax:

```python
match expression:
    case pattern1:
        # Code for pattern1
    case pattern2:
        # Code for pattern2
    case _:
        # Default case
```

প্রতিটি অংশের কাজ:

| অংশ | কাজ |
|---|---|
| `match` | যে value বা expression পরীক্ষা করা হবে |
| `case` | একটি সম্ভাব্য pattern নির্ধারণ করে |
| `:` | block শুরু করে |
| Indentation | কোন code কোন case-এর অন্তর্ভুক্ত তা বোঝায় |
| `case _` | অন্য কোনো pattern না মিললে match করতে পারে |

`case _`-কে সাধারণত default case হিসেবে ব্যবহার করা হয়।

## 3. Match-Case কীভাবে কাজ করে?

Python `match` expression-এর value নিয়ে `case`-গুলোকে ক্রমানুসারে পরীক্ষা করে।

যে প্রথম case-এর pattern সফলভাবে match করে এবং তার guard থাকলে guard-ও True হয়, সেই case-এর body execute হয়। এরপর পুরো `match` statement শেষ হয়।

উদাহরণ:

```python
number = 3

match number:
    case 1:
        print("One")
    case 2:
        print("Two")
    case 3:
        print("Three")
    case 4:
        print("Four")
```

Output:

```text
Three
```

এখানে `number`-এর value `3`, তাই `case 3` match করেছে।

**গুরুত্বপূর্ণ:** কোনো case match না করলে এবং matching `case _` না থাকলে `match` statement কোনো case-এর body execute না করেই শেষ হতে পারে। এটি নিজে থেকে error তৈরি করে না।

## 4. `case _` — Default Case

`case _` ব্যবহার করা হয় অন্য কোনো pattern match না করলে বিকল্প action নেওয়ার জন্য।

উদাহরণ:

```python
choice = 5

match choice:
    case 1:
        print("Add")
    case 2:
        print("Subtract")
    case 3:
        print("Multiply")
    case _:
        print("Invalid choice")
```

Output:

```text
Invalid choice
```

কারণ `choice`-এর value 1, 2 অথবা 3 নয়।

এখানে `_` একটি wildcard pattern। এটি যেকোনো value match করতে পারে, কিন্তু সেই value-কে কোনো variable-এ সংরক্ষণ করে না।

## 5. একাধিক Value-এর জন্য একই Case

একাধিক নির্দিষ্ট value-এর জন্য একই code execute করতে `|` ব্যবহার করা যায়।

একে **OR pattern** বলা হয়।

উদাহরণ:

```python
day = "Friday"

match day:
    case "Friday" | "Saturday":
        print("Weekend")
    case "Sunday" | "Monday" | "Tuesday" | "Wednesday" | "Thursday":
        print("Working day")
    case _:
        print("Invalid day")
```

Output:

```text
Weekend
```

এখানে `day` যদি `"Friday"` অথবা `"Saturday"` হয়, তাহলে একই message print হবে।

এটি নিচের `if` condition-এর মতো:

```python
if day == "Friday" or day == "Saturday":
    print("Weekend")
```

তবে `match-case`-এ একাধিক নির্দিষ্ট pattern সাজিয়ে লেখা যায়।

## 6. User Input-এর সঙ্গে Match-Case

User-এর কাছ থেকে input নিয়ে বিভিন্ন option অনুযায়ী কাজ করা যায়।

উদাহরণ:

```python
choice = input("Enter your choice (1-3): ")

match choice:
    case "1":
        print("You selected Add")
    case "2":
        print("You selected Subtract")
    case "3":
        print("You selected Multiply")
    case _:
        print("Invalid choice")
```

Input:

```text
2
```

Output:

```text
You selected Subtract
```

এখানে `input()` string return করে। তাই `"1"`, `"2"` ও `"3"` string হিসেবে match করা হয়েছে।

যদি integer হিসেবে পরীক্ষা করতে চাও, তাহলে input convert করতে পারো:

```python
choice = int(input("Enter your choice: "))

match choice:
    case 1:
        print("Add")
    case 2:
        print("Subtract")
    case 3:
        print("Multiply")
    case _:
        print("Invalid choice")
```

তবে এখানে non-numeric input দিলে `int()`-এ `ValueError` হতে পারে। প্রয়োজন হলে input validation করতে হবে।

## 7. Match-Case দিয়ে Simple Calculator

একটি operator-এর value অনুযায়ী arithmetic operation নির্বাচন করা যায়।

```python
a = 10
b = 5
operator = "+"

match operator:
    case "+":
        print(a + b)
    case "-":
        print(a - b)
    case "*":
        print(a * b)
    case "/":
        if b != 0:
            print(a / b)
        else:
            print("Cannot divide by zero")
    case _:
        print("Invalid operator")
```

Output:

```text
15
```

এখানে `operator`-এর value `"+"`, তাই প্রথম case execute হয়েছে।

**Note:** Calculator-এর division case-এ `b != 0` পরীক্ষা করা হয়েছে, যাতে zero দিয়ে ভাগ করার চেষ্টা না করা হয়।

## 8. Match-Case-এ Guard ব্যবহার

কখনো pattern match করলেই যথেষ্ট হয় না; অতিরিক্ত condition-ও পরীক্ষা করতে হয়।

`case`-এর সঙ্গে `if` ব্যবহার করে এই অতিরিক্ত condition দেওয়া যায়। একে **Guard** বলে।

উদাহরণ:

```python
number = 10

match number:
    case n if n > 0:
        print("Positive")
    case n if n < 0:
        print("Negative")
    case 0:
        print("Zero")
```

Output:

```text
Positive
```

এখানে:

- `case n if n > 0` — value-টি `n` variable-এ bind করা হয়, তারপর `n > 0` পরীক্ষা করা হয়।
- Guard True হলে সেই case-এর body execute হয়।
- Guard False হলে Python পরের case পরীক্ষা করে।

এই উদাহরণে `n` হলো capture pattern, যা matched value-কে variable-এ রাখে।

এই ধরনের simple numeric comparison-এর ক্ষেত্রে `if-elif-else`-ও বেশ পরিষ্কার হতে পারে। `match-case` বিশেষভাবে উপযোগী যখন বিভিন্ন pattern অনুযায়ী কাজ নির্বাচন করতে হয়।

## 9. Match-Case-এ Tuple Pattern

`match-case` শুধু একটি নির্দিষ্ট value নয়, tuple-এর মতো structure-এর pattern-ও match করতে পারে।

উদাহরণ:

```python
point = (0, 5)

match point:
    case (0, 0):
        print("Origin")
    case (0, y):
        print("On the Y-axis")
    case (x, 0):
        print("On the X-axis")
    case (x, y):
        print("A point in the plane")
```

Output:

```text
On the Y-axis
```

ব্যাখ্যা:

- `(0, 0)` — origin point।
- `(0, y)` — প্রথম value `0` হলে দ্বিতীয় value `y`-তে রাখা হয়।
- `(x, 0)` — দ্বিতীয় value `0` হলে প্রথম value `x`-তে রাখা হয়।
- `(x, y)` — অন্য যেকোনো দুই-value tuple match করতে পারে।

এখানে `point = (0, 5)`, তাই `(0, y)` pattern match করেছে এবং `y = 5` হয়েছে।

**গুরুত্বপূর্ণ:** `case (x, y)`-এর মতো capture pattern যেকোনো matching two-item sequence-এর value bind করতে পারে। তাই সাধারণত এটি শেষে রাখা হয়, যদি তার আগে নির্দিষ্ট pattern পরীক্ষা করতে চাও।

## 10. Match-Case এবং If-Elif-Else-এর পার্থক্য

দুটিই program-এর execution নিয়ন্ত্রণ করতে পারে, তবে তাদের ব্যবহারের ধরন আলাদা।

| বিষয় | `if-elif-else` | `match-case` |
|---|---|---|
| প্রধান ব্যবহার | Boolean condition পরীক্ষা | Value বা pattern match করা |
| Range check | খুব উপযোগী | Guard দিয়ে করা যায়, তবে সবসময় সবচেয়ে সহজ নয় |
| নির্দিষ্ট option নির্বাচন | করা যায় | বেশ পরিষ্কারভাবে করা যায় |
| একাধিক value একই action | `or` ব্যবহার করা যায় | `|` OR pattern ব্যবহার করা যায় |
| Structure matching | সাধারণত আলাদা logic লাগে | Built-in pattern matching সমর্থন করে |
| Python version | সাধারণ `if`-এর জন্য version restriction নেই | Python 3.10 বা পরবর্তী সংস্করণ প্রয়োজন |

### `if-elif-else` কখন ব্যবহার করবে?

যখন condition-এর মধ্যে comparison, range বা একাধিক logical rule থাকবে।

```python
marks = 85

if marks >= 80:
    print("A")
elif marks >= 70:
    print("B")
else:
    print("Other")
```

### `match-case` কখন ব্যবহার করবে?

যখন নির্দিষ্ট value বা pattern অনুযায়ী বিভিন্ন action নির্বাচন করতে হবে।

```python
command = "start"

match command:
    case "start":
        print("Starting")
    case "stop":
        print("Stopping")
    case _:
        print("Unknown command")
```

দুটি statement-ই গুরুত্বপূর্ণ। পরিস্থিতি অনুযায়ী সহজ ও readable পদ্ধতিটি বেছে নেবে।

## 11. Common Mistakes

### Mistake 1: Python version পুরোনো থাকা

`match-case` Python 3.10-এ যোগ হয়েছে।

Python 3.9 বা তার আগের version-এ এই syntax ব্যবহার করলে `SyntaxError` হবে।

Version পরীক্ষা:

```bash
python --version
```

প্রয়োজনে `python3 --version` ব্যবহার করতে পারো।

### Mistake 2: `case`-এর পরে colon না দেওয়া

ভুল:

```python
match choice:
    case 1
        print("One")
```

সঠিক:

```python
match choice:
    case 1:
        print("One")
```

### Mistake 3: Indentation ভুল করা

ভুল:

```python
match choice:
case 1:
print("One")
```

সঠিক:

```python
match choice:
    case 1:
        print("One")
```

### Mistake 4: Input-এর type ভুল বোঝা

```python
choice = input("Enter choice: ")

match choice:
    case 1:
        print("One")
    case _:
        print("Other")
```

এখানে user `1` লিখলেও `input()` string `"1"` return করে। তাই integer pattern `1`-এর সঙ্গে এটি match করবে না।

সঠিক পদ্ধতি:

```python
choice = input("Enter choice: ")

match choice:
    case "1":
        print("One")
    case _:
        print("Other")
```

অথবা input-কে integer-এ convert করতে পারো।

### Mistake 5: `case _`-কে সাধারণ variable মনে করা

`case _` হলো wildcard pattern। এটি যেকোনো value match করে, কিন্তু value-টি variable হিসেবে সংরক্ষণ করে না।

### Mistake 6: সব condition-এর জন্য Match-Case ব্যবহার করা

কোনো range পরীক্ষা করার জন্য যেমন `age >= 18`, `if` ব্যবহার করা সাধারণত বেশি সহজ।

শুধু নতুন syntax ব্যবহার করার জন্য code জটিল করবে না। Readability-কে গুরুত্ব দেবে।

## 12. Practice Exercises

প্রতিটি প্রশ্নের output নিজে predict করো।

### Question 1

```python
number = 2

match number:
    case 1:
        print("One")
    case 2:
        print("Two")
    case _:
        print("Other")
```

### Question 2

```python
choice = "4"

match choice:
    case "1":
        print("First")
    case "2":
        print("Second")
    case _:
        print("Invalid")
```

### Question 3

```python
day = "Saturday"

match day:
    case "Friday" | "Saturday":
        print("Weekend")
    case _:
        print("Working day")
```

### Question 4

```python
number = -5

match number:
    case n if n > 0:
        print("Positive")
    case n if n < 0:
        print("Negative")
    case _:
        print("Zero")
```

### Question 5

```python
point = (3, 0)

match point:
    case (0, 0):
        print("Origin")
    case (0, y):
        print("Y-axis")
    case (x, 0):
        print("X-axis")
    case (x, y):
        print("Other point")
```

### Question 6

নিচের code-এ কী সমস্যা?

```python
choice = input("Choice: ")

match choice:
    case 1:
        print("One")
```

### Question 7

`match-case` কোন Python version থেকে চালু হয়েছে?

### Question 8

কোন পরিস্থিতিতে `if-elif-else` ব্যবহার করা বেশি উপযোগী: নির্দিষ্ট command নির্বাচন, নাকি marks-এর range পরীক্ষা?

## 13. Answer Key

### Answer 1

```text
Two
```

`number`-এর value `2`, তাই `case 2` match করেছে।

### Answer 2

```text
Invalid
```

`choice` হলো string `"4"`। এটি `"1"` বা `"2"` নয়।

### Answer 3

```text
Weekend
```

`"Saturday"` OR pattern-এর সঙ্গে match করেছে।

### Answer 4

```text
Negative
```

`n < 0` True হয়েছে।

### Answer 5

```text
X-axis
```

Point-এর দ্বিতীয় value `0`, তাই `(x, 0)` pattern match করেছে।

### Answer 6

`input()` string return করে, কিন্তু code-এ integer pattern `1` ব্যবহার করা হয়েছে। String `"1"` match করতে চাইলে `case "1":` লিখতে হবে।

### Answer 7

Python 3.10 থেকে।

### Answer 8

Marks-এর range পরীক্ষা করতে সাধারণত `if-elif-else` বেশি উপযোগী। নির্দিষ্ট command নির্বাচন করতে `match-case` বেশ পরিষ্কার হতে পারে।

## 14. Quick Revision

- `match-case` Python 3.10 থেকে পাওয়া যায়।
- `match`-এর পরে যে value বা expression পরীক্ষা করতে হবে, তা লেখা হয়।
- `case` দিয়ে সম্ভাব্য pattern নির্ধারণ করা হয়।
- `case _` হলো wildcard pattern, যা default case হিসেবে ব্যবহার করা যায়।
- `|` দিয়ে একাধিক alternative pattern লেখা যায়।
- `case`-এর সঙ্গে `if` ব্যবহার করে guard দেওয়া যায়।
- `match-case` tuple-এর মতো structure-এর pattern-ও match করতে পারে।
- `input()` string return করে—তাই pattern-এর data type খেয়াল রাখতে হবে।
- Range ও complex Boolean condition-এর ক্ষেত্রে `if-elif-else` প্রায়ই বেশি পরিষ্কার।
- Readable code লেখার জন্য পরিস্থিতি অনুযায়ী সঠিক statement বেছে নিতে হবে।

## 15. Self-Assessment Checklist

- [ ] `match-case`-এর syntax লিখতে পারি।
- [ ] `case _`-এর কাজ বুঝি।
- [ ] একাধিক value-এর জন্য OR pattern ব্যবহার করতে পারি।
- [ ] User input-এর সঙ্গে `match-case` ব্যবহার করতে পারি।
- [ ] Guard কী, তা বুঝি।
- [ ] Tuple pattern matching-এর ধারণা বুঝি।
- [ ] `if-elif-else` ও `match-case`-এর পার্থক্য বলতে পারি।
- [ ] Common errors শনাক্ত করতে পারি।

**পরবর্তী টপিক:** `23_Choosing_between_if_elif_and_match_case.md`
