# 27. Debugging Conditional Logic

## 1. What Is Debugging?

**Debugging** হলো program-এর error বা unexpected behavior খুঁজে বের করে তার কারণ নির্ধারণ করা এবং সেটি ঠিক করার প্রক্রিয়া।

Conditional logic debugging বলতে `if`, `elif`, `else`, logical operators এবং Boolean expressions-এর সমস্যা খুঁজে বের করাকে বোঝায়।

সাধারণত তিন ধরনের সমস্যা দেখা যায়:

1. **Syntax Error:** Code-এর syntax ভুল হওয়ায় program run করতে পারে না।
2. **Runtime Error:** Program চলার সময় error তৈরি হয়।
3. **Logical Error:** Program run করে, কিন্তু result প্রত্যাশা অনুযায়ী হয় না।

উদাহরণ:

```python
marks = 85

if marks >= 60:
    print("Grade C")
elif marks >= 80:
    print("Grade A")
```

Output:

```text
Grade C
```

Code-টি run হচ্ছে, কিন্তু grade-এর নিয়ম অনুযায়ী 85 marks-এর জন্য A পাওয়ার কথা।

এটি একটি **Logical Error**। প্রথম condition `marks >= 60` True হওয়ায় পরের `elif` পরীক্ষা করা হচ্ছে না।

Correct code:

```python
marks = 85

if marks >= 80:
    print("Grade A")
elif marks >= 60:
    print("Grade C")
```

Output:

```text
Grade A
```

## 2. Step-by-Step Debugging Process

Conditional logic-এর সমস্যা খুঁজে বের করার জন্য এই ধাপগুলো অনুসরণ করতে পারো।

1. **Expected Result নির্ধারণ:** Input অনুযায়ী কী output আসার কথা?
2. **Actual Result পরীক্ষা:** Program আসলে কী output দিচ্ছে?
3. **Input ও Variable পরীক্ষা:** Variable-এ সঠিক value আছে কি না?
4. **Condition পরীক্ষা:** প্রতিটি Boolean expression True নাকি False?
5. **Execution Flow অনুসরণ:** কোন block execute হচ্ছে এবং কেন?
6. **Code সংশোধন:** ভুল condition বা order ঠিক করা।
7. **আবার Test করা:** বিভিন্ন input দিয়ে নিশ্চিত হওয়া যে সমাধানটি কাজ করছে।

উদাহরণ:

```python
age = 16

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

এখানে `age >= 18` হলো False। তাই `else` block execute হবে।

Output:

```text
Minor
```

এখানে কোনো error নেই। Condition-এর result বুঝতে পারলে program-এর behavior ব্যাখ্যা করা যায়।

## 3. Using print() for Debugging

Beginner-দের জন্য `print()` হলো debugging-এর সবচেয়ে সহজ উপায়।

Variable ও condition-এর result print করে দেখা যায়, program কীভাবে সিদ্ধান্ত নিচ্ছে।

উদাহরণ:

```python
marks = 75

print("Marks:", marks)
print("marks >= 80:", marks >= 80)
print("marks >= 60:", marks >= 60)

if marks >= 80:
    print("Grade A")
elif marks >= 60:
    print("Grade B")
else:
    print("Grade F")
```

Output:

```text
Marks: 75
marks >= 80: False
marks >= 60: True
Grade B
```

এখানে প্রতিটি condition-এর Boolean result দেখা যাচ্ছে। ফলে কোন branch execute হবে, তা সহজে বোঝা যায়।

**কখন ব্যবহার করবে?**

- Variable-এর value নিয়ে সন্দেহ হলে।
- Condition True নাকি False বুঝতে না পারলে।
- Program ভুল branch-এ যাচ্ছে মনে হলে।
- Beginner অবস্থায় execution flow বোঝার জন্য।

Debugging শেষ হলে অপ্রয়োজনীয় diagnostic `print()` statement সরিয়ে ফেলতে পারো।

## 4. Checking Each Condition Separately

একটি condition-এর মধ্যে অনেকগুলো অংশ থাকলে প্রতিটি অংশ আলাদাভাবে পরীক্ষা করা ভালো।

উদাহরণ:

```python
age = 20
has_id = False

if age >= 18 and has_id:
    print("Access granted")
else:
    print("Access denied")
```

Output:

```text
Access denied
```

এখন debugging-এর জন্য:

```python
print("Age condition:", age >= 18)
print("ID condition:", has_id)
print("Combined condition:", age >= 18 and has_id)
```

Output:

```text
Age condition: True
ID condition: False
Combined condition: False
```

ব্যাখ্যা:

- `age >= 18` হলো True।
- `has_id` হলো False।
- `and` ব্যবহৃত হওয়ায় দুইটি condition True না হলে combined result True হবে না।

এভাবে condition-এর কোন অংশটি প্রত্যাশিত result দিচ্ছে না, তা শনাক্ত করা যায়।

## 5. Debugging if-elif-else Order

`if-elif-else` chain-এ প্রথম True condition-এর block execute হয়। তাই condition-এর order ভুল হলে program ভুল category নির্বাচন করতে পারে।

ভুল উদাহরণ:

```python
temperature = 38

if temperature >= 25:
    print("Warm")
elif temperature >= 35:
    print("Very hot")
else:
    print("Cool")
```

Output:

```text
Warm
```

কেন ভুল?

`temperature >= 25` প্রথমেই True হয়েছে। ফলে `temperature >= 35` আর পরীক্ষা করা হয়নি।

Correct code:

```python
temperature = 38

if temperature >= 35:
    print("Very hot")
elif temperature >= 25:
    print("Warm")
else:
    print("Cool")
```

Output:

```text
Very hot
```

**Debugging tip:** Threshold বা overlapping range থাকলে সবচেয়ে নির্দিষ্ট বা বড় threshold আগে পরীক্ষা করা দরকার কি না, তা যাচাই করবে।

## 6. Debugging Boundary Conditions

Boundary condition হলো কোনো range বা limit-এর ঠিক সীমানায় থাকা value।

যেমন, marks 40 বা তার বেশি হলে pass।

ভুল code:

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

এখানে `marks > 40` মানে marks অবশ্যই 40-এর চেয়ে বেশি হতে হবে। কিন্তু নিয়মে 40-ও অন্তর্ভুক্ত।

Correct code:

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

Boundary test করার জন্য এই value-গুলো পরীক্ষা করতে পারো:

- Limit-এর নিচে: `39`
- Limit-এর ঠিক সমান: `40`
- Limit-এর ওপরে: `41`

এভাবে বোঝা যায় condition সঠিকভাবে কাজ করছে কি না।

## 7. Using Test Cases to Find Logical Errors

একটি input দিয়ে program ঠিক মনে হলেও অন্য input-এ ভুল হতে পারে। তাই একাধিক test case ব্যবহার করা উচিত।

উদাহরণ: একটি number positive, negative অথবা zero কি না নির্ধারণ করা।

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

Test cases:

| Input | Expected Output |
|---:|---|
| `10` | Positive |
| `-5` | Negative |
| `0` | Zero |

প্রতিটি input দিয়ে program চালিয়ে actual output-এর সঙ্গে expected output তুলনা করবে।

বিশেষ করে zero, negative number, empty input এবং boundary value-এর মতো গুরুত্বপূর্ণ case পরীক্ষা করা উচিত।

## 8. Debugging with Truth Tables

Logical operators-এর condition ভুল হলে truth table ব্যবহার করে logic যাচাই করা যায়।

ধরা যাক:

```python
age = 16

if age >= 18 or age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

এই condition-টি প্রায় সব numeric age-এর জন্য True। কারণ 18-এর কম হলে `age <= 60` True এবং 18 বা তার বেশি হলে `age >= 18` True।

যদি উদ্দেশ্য হয় age 18 থেকে 60-এর মধ্যে হলে eligible বলা, তাহলে `and` ব্যবহার করতে হবে।

```python
age = 16

if age >= 18 and age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

Output:

```text
Not eligible
```

Truth table:

| A | B | A and B | A or B |
|---|---|---|---|
| True | True | True | True |
| True | False | False | True |
| False | True | False | True |
| False | False | False | False |

এখানে:

- `and` — সব condition True হতে হবে।
- `or` — অন্তত একটি condition True হলেই হবে।
- `not` — Boolean result উল্টে দেয়।

## 9. Debugging Nested Conditions

Nested `if`-এ একাধিক level থাকায় কোন block execute হচ্ছে তা বোঝা কঠিন হতে পারে।

উদাহরণ:

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

এখানে:

1. বাইরের condition `age >= 18` True।
2. ভেতরের condition `has_id` False।
3. ভেতরের `else` execute হয়।

Debugging-এর সময় প্রতিটি level-এর condition আলাদা করে পরীক্ষা করবে। একই সঙ্গে indentation ঠিক আছে কি না নিশ্চিত করবে, কারণ indentation নির্ধারণ করে কোন `if`-এর সঙ্গে `else` যুক্ত হবে।

## 10. Using Python's Debugger

`print()` দিয়ে debugging সহজ হলেও Python-এর built-in debugger `pdb` ব্যবহার করে program-এর execution আরও বিস্তারিতভাবে পরীক্ষা করা যায়।

উদাহরণ:

```python
age = 16

breakpoint()

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

Program `breakpoint()`-এ থেমে debugger-এ প্রবেশ করবে।

সেখানে সাধারণত এই command-গুলো ব্যবহার করা যায়:

| Command | কাজ |
|---|---|
| `n` | পরবর্তী line-এ যাওয়া |
| `s` | function call-এর ভেতরে প্রবেশ করা |
| `c` | পরবর্তী breakpoint পর্যন্ত চালানো |
| `p age` | `age` variable-এর value print করা |
| `p age >= 18` | condition-এর result পরীক্ষা করা |
| `q` | debugger থেকে বের হওয়া |

এই উদাহরণে `p age >= 18` লিখলে `False` দেখা যাবে।

**Note:** `breakpoint()` চালাতে Python 3.7 বা তার পরবর্তী version ব্যবহার করা যায়। VS Code-এর debugger দিয়েও breakpoint বসিয়ে variable ও condition পরীক্ষা করা সম্ভব।

## 11. Debugging with VS Code

VS Code-এ Python code debug করার জন্য:

1. Python file খুলবে।
2. যে line-এ execution থামাতে চাও, তার বাঁ পাশে click করে breakpoint বসাবে।
3. Run and Debug ব্যবহার করে debugging শুরু করবে।
4. Program breakpoint-এ থামলে Variables panel থেকে variable-এর value দেখবে।
5. Step Over বা Step Into ব্যবহার করে code ধাপে ধাপে চালাবে।
6. Condition-এর result ও execution flow পরীক্ষা করবে।

**Breakpoint** হলো code-এর এমন একটি স্থান, যেখানে debugger program-এর execution সাময়িকভাবে থামায়।

উদাহরণ:

```python
marks = 75

if marks >= 80:
    print("Grade A")
elif marks >= 60:
    print("Grade B")
else:
    print("Grade F")
```

`if` ও `elif`-এর line-এ breakpoint বসালে দেখা যাবে কোন condition পরীক্ষা হচ্ছে এবং কোন branch execute হচ্ছে।

## 12. Common Debugging Mistakes

### Mistake 1: শুধু একটি input দিয়ে পরীক্ষা করা

একটি test case সব logical error ধরতে পারে না।

**সমাধান:** Normal value, boundary value এবং unusual value দিয়ে পরীক্ষা করবে।

### Mistake 2: শুধু output দেখা, condition না দেখা

Output ভুল হলে কোন condition False বা True হচ্ছে তা পরীক্ষা না করলে কারণ খুঁজে পাওয়া কঠিন হতে পারে।

**সমাধান:** প্রয়োজন হলে `print()` দিয়ে intermediate value ও Boolean result দেখবে।

### Mistake 3: Condition-এর order উপেক্ষা করা

`if-elif-else`-এ প্রথম True branch-এর পর বাকি branch skip হয়।

**সমাধান:** Condition-এর ক্রম এবং overlapping range যাচাই করবে।

### Mistake 4: Logical operator ভুল নির্বাচন

Range check-এ `or`-এর বদলে `and` প্রয়োজন হতে পারে।

**সমাধান:** প্রতিটি condition আলাদা করে লিখে truth table বা test case দিয়ে যাচাই করবে।

### Mistake 5: Variable-এর value ভুল ধরে নেওয়া

Input conversion, reassignment বা অন্য calculation-এর কারণে variable-এর value প্রত্যাশার চেয়ে আলাদা হতে পারে।

**সমাধান:** Debugger বা `print()` দিয়ে প্রকৃত value পরীক্ষা করবে।

### Mistake 6: Code পরিবর্তনের পর পুনরায় পরীক্ষা না করা

একটি error ঠিক করলেও অন্য input-এ নতুন সমস্যা থাকতে পারে।

**সমাধান:** Code সংশোধনের পর সংশ্লিষ্ট সব test case আবার চালাবে।

## 13. Practice Exercises

### Question 1: Find the Logical Error

```python
marks = 90

if marks >= 50:
    print("Pass")
elif marks >= 80:
    print("Grade A")
```

- Output কী হবে?
- Problem কোথায়?
- কীভাবে ঠিক করবে?

### Question 2: Debug the Range

```python
age = 17

if age >= 18 or age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

যদি উদ্দেশ্য হয় 18 থেকে 60 বছরের মধ্যে eligible বলা, তাহলে code ঠিক করো।

### Question 3: Boundary Condition

```python
number = 0

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
elif number > 0:
    print("Zero")
```

Zero input-এর জন্য কেন কোনো output আসে না? Code ঠিক করো।

### Question 4: Trace the Condition

```python
age = 16
has_permission = True

if age >= 18 and has_permission:
    print("Allowed")
else:
    print("Not allowed")
```

- `age >= 18`-এর result কী?
- `has_permission`-এর result কী?
- Combined condition-এর result কী?
- Output কী হবে?

### Question 5: Find the Syntax Error

```python
number = 5

if number > 0
    print("Positive")
```

Error কোথায়?

### Question 6: Design Test Cases

একটি program 0 থেকে 100-এর মধ্যে marks গ্রহণ করবে। 40 বা তার বেশি হলে Pass, অন্যথায় Fail।

কমপক্ষে চারটি test case লেখো, যাতে valid boundary এবং invalid range পরীক্ষা করা যায়।

### Question 7: Use Debugging Prints

নিচের code-এ কোন condition True হচ্ছে তা print করে দেখাও।

```python
marks = 65

if marks >= 80:
    print("A")
elif marks >= 60:
    print("B")
else:
    print("F")
```

## 14. Answer Key

### Answer 1

Output:

```text
Pass
```

কারণ `marks >= 50` প্রথমেই True হয়েছে। যদি grade নির্ধারণ করতে চাও, বড় threshold আগে পরীক্ষা করবে।

```python
marks = 90

if marks >= 80:
    print("Grade A")
elif marks >= 50:
    print("Pass")
else:
    print("Fail")
```

### Answer 2

সমস্যা হলো `or` ব্যবহার করা হয়েছে। এখানে `and` প্রয়োজন।

```python
age = 17

if age >= 18 and age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

### Answer 3

Zero-এর জন্য `number > 0` False এবং `number < 0`-ও False। তৃতীয় condition আবার `number > 0`, তাই সেটিও False।

সঠিক code:

```python
number = 0

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

### Answer 4

- `age >= 18` → False
- `has_permission` → True
- Combined condition → False
- Output → `Not allowed`

### Answer 5

`if number > 0` line-এর শেষে colon (`:`) নেই।

```python
if number > 0:
    print("Positive")
```

### Answer 6

সম্ভাব্য test cases:

| Input | Expected result |
|---:|---|
| `-1` | Invalid marks |
| `0` | Fail |
| `39` | Fail |
| `40` | Pass |
| `100` | Pass |
| `101` | Invalid marks |

এই test cases-এ valid range-এর দুই প্রান্ত এবং pass/fail boundary পরীক্ষা করা হয়েছে।

### Answer 7

```python
marks = 65

print("marks >= 80:", marks >= 80)
print("marks >= 60:", marks >= 60)

if marks >= 80:
    print("A")
elif marks >= 60:
    print("B")
else:
    print("F")
```

Output:

```text
marks >= 80: False
marks >= 60: True
B
```

## 15. Quick Revision

- Debugging হলো program-এর error বা unexpected behavior খুঁজে বের করে ঠিক করা।
- Logical error হলে code run করলেও ভুল result আসতে পারে।
- `print()` দিয়ে variable ও condition-এর result পরীক্ষা করা যায়।
- `if-elif-else`-এ প্রথম True condition-এর block execute হয়।
- Boundary value দিয়ে test করলে comparison error ধরা যায়।
- Truth table দিয়ে logical operators-এর behavior যাচাই করা যায়।
- Nested conditions debug করতে প্রতিটি level পরীক্ষা করতে হয়।
- `pdb` ও VS Code debugger দিয়ে code ধাপে ধাপে চালানো যায়।
- Code সংশোধনের পরে একাধিক test case দিয়ে পুনরায় পরীক্ষা করতে হবে।

## 16. Self-Assessment Checklist

- [ ] Syntax, runtime ও logical error-এর পার্থক্য বুঝি।
- [ ] `print()` দিয়ে variable ও condition debug করতে পারি।
- [ ] `if-elif-else`-এর execution flow অনুসরণ করতে পারি।
- [ ] Boundary test cases তৈরি করতে পারি।
- [ ] `and`, `or` ও `not`-এর logic পরীক্ষা করতে পারি।
- [ ] Nested conditions-এর execution flow বুঝি।
- [ ] `breakpoint()` ও debugger-এর basic ধারণা জানি।
- [ ] Code ঠিক করার পর test cases দিয়ে যাচাই করতে পারি।

**পরবর্তী টপিক:** `28_Practical_Conditional_Programs.md`
