# 13. Short-Circuit Evaluation in Python

## 1. Introduction to Short-Circuit Evaluation

Python-এ `and` এবং `or` Operator ব্যবহার করার সময় অনেক ক্ষেত্রে পুরো Expression Evaluate করার প্রয়োজন হয় না। Result নির্ধারণ করার জন্য যথেষ্ট তথ্য পাওয়া গেলে Python বাকি অংশ Evaluate করা বন্ধ করে দেয়।

এই আচরণকে **Short-Circuit Evaluation** বলা হয়।

Short-Circuit Evaluation মূলত দুটি Logical Operator-এর ক্ষেত্রে দেখা যায়:

- `and`
- `or`

### Example

```python
print(False and True)
print(True or False)
```

Output:

```text
False
True
```

ব্যাখ্যা:

- `False and True`-এ প্রথম Operand `False`। `and`-এর Result True হতে হলে সব Operand Truthy হতে হবে। তাই Python দ্বিতীয় Operand Evaluate না করেই `False` Return করতে পারে।
- `True or False`-এ প্রথম Operand `True`। `or`-এর Result Truthy করার জন্য এটিই যথেষ্ট। তাই দ্বিতীয় Operand Evaluate করার প্রয়োজন নেই।

**মনে রাখবে:** Short-Circuit Evaluation অপ্রয়োজনীয় Evaluation এড়িয়ে কাজ করতে পারে এবং কিছু ক্ষেত্রে Program-এর Efficiency বাড়ায়।

---

## 2. Short-Circuit Evaluation with `and`

`and` Operator-এর ক্ষেত্রে Python বাম দিক থেকে Operand Evaluate করে।

- কোনো Operand Falsy হলে Python সেটি Return করে এবং পরবর্তী Operand Evaluate করা বন্ধ করে দেয়।
- সব Operand Truthy হলে শেষ Operand Return করে।

### Example 1: First Operand Is Falsy

```python
result = 0 and 10

print(result)
```

Output:

```text
0
```

ব্যাখ্যা:

1. Python প্রথমে `0` পরীক্ষা করে।
2. `0` একটি Falsy Value।
3. তাই Python পরবর্তী Operand `10` Evaluate না করে `0` Return করে।

### Example 2: First Operand Is Truthy

```python
result = 5 and 10

print(result)
```

Output:

```text
10
```

ব্যাখ্যা:

1. `5` Truthy, তাই Python পরবর্তী Operand পরীক্ষা করে।
2. `10`-ও Truthy।
3. এটি শেষ Operand হওয়ায় Result `10`।

### Example 3: Multiple Operands

```python
result = "Python" and 100 and "Success"

print(result)
```

Output:

```text
Success
```

ব্যাখ্যা:

- `"Python"` Truthy।
- `100` Truthy।
- `"Success"` শেষ Operand এবং Truthy।

তাই শেষ Operand `"Success"` Return হয়েছে।

### Example 4: Falsy Operand in the Middle

```python
result = "Python" and 0 and "Success"

print(result)
```

Output:

```text
0
```

Python প্রথমে `"Python"` পরীক্ষা করে, যা Truthy। এরপর `0` পরীক্ষা করে, যা Falsy। তাই `0` Return করে এবং `"Success"` Evaluate করে না।

---

## 3. Short-Circuit Evaluation with `or`

`or` Operator-এর ক্ষেত্রেও Python বাম দিক থেকে Operand Evaluate করে।

- কোনো Operand Truthy হলে Python সেটি Return করে এবং পরবর্তী Operand Evaluate করা বন্ধ করে দেয়।
- সব Operand Falsy হলে শেষ Operand Return করে।

### Example 1: First Operand Is Truthy

```python
result = 10 or 20

print(result)
```

Output:

```text
10
```

ব্যাখ্যা:

`10` Truthy হওয়ায় Python পরবর্তী Operand `20` Evaluate করে না।

### Example 2: First Operand Is Falsy

```python
result = 0 or 20

print(result)
```

Output:

```text
20
```

ব্যাখ্যা:

1. `0` Falsy।
2. তাই Python পরবর্তী Operand পরীক্ষা করে।
3. `20` Truthy, তাই সেটি Return হয়।

### Example 3: Multiple Operands

```python
result = "" or 0 or "Python" or "Java"

print(result)
```

Output:

```text
Python
```

ব্যাখ্যা:

- `""` Falsy।
- `0` Falsy।
- `"Python"` Truthy।
- তাই Python `"Python"` Return করে এবং `"Java"` Evaluate করে না।

### Example 4: All Operands Are Falsy

```python
result = 0 or "" or None

print(result)
```

Output:

```text
None
```

সব Operand Falsy হওয়ায় শেষ Operand `None` Return হয়েছে।

---

## 4. Short-Circuit Truth Table

| Expression | প্রথম Operand | Result | দ্বিতীয় Operand Evaluate হয়? |
|---|---|---|---|
| `False and True` | Falsy | `False` | না |
| `True and False` | Truthy | `False` | হ্যাঁ |
| `True or False` | Truthy | `True` | না |
| `False or True` | Falsy | `True` | হ্যাঁ |

এই Table-এ `True` ও `False` ব্যবহার করা হয়েছে। মনে রাখবে, Python-এর `and` ও `or` সাধারণত Boolean Value-এর পরিবর্তে Operand-এর আসল Value-ও Return করতে পারে।

---

## 5. Short-Circuit Evaluation with Function Calls

Short-Circuit Evaluation বোঝার সবচেয়ে ভালো উপায় হলো Function-এর সাহায্যে দেখা যে কোনো Function সত্যিই Call হচ্ছে কি না।

### Example 1: Function Is Not Called

```python
def check():
    print("Function called")
    return True

result = False and check()

print(result)
```

Output:

```text
False
```

ব্যাখ্যা:

- `False and ...`-এর Result আগেই নির্ধারিত।
- তাই `check()` Call করা হয়নি।
- ফলে `"Function called"` Print হয়নি।

### Example 2: Function Is Called

```python
def check():
    print("Function called")
    return True

result = True and check()

print(result)
```

Output:

```text
Function called
True
```

ব্যাখ্যা:

প্রথম Operand `True`, তাই `and`-এর Result নির্ধারণ করতে Python-কে পরবর্তী Operand Evaluate করতে হয়। এজন্য `check()` Call হয়।

### Example 3: `or` Operator

```python
def check():
    print("Function called")
    return False

result = True or check()

print(result)
```

Output:

```text
True
```

এখানে প্রথম Operand `True`। তাই Python `check()` Call করে না।

**গুরুত্বপূর্ণ:** Short-Circuit-এর কারণে কোনো Function Call হবে কি না, তা নির্ভর করে Expression-এর আগের Operand-গুলোর ওপর।

---

## 6. Preventing Errors with Short-Circuit Evaluation

Short-Circuit Evaluation ব্যবহার করে কিছু Error এড়ানো যায়।

### Example: Checking Before Accessing a List

ধরো, একটি List-এর প্রথম Element Access করতে হবে। কিন্তু List Empty হলে Index Error হতে পারে।

```python
numbers = []

if numbers and numbers[0] > 10:
    print("First number is greater than 10")
else:
    print("List is empty or condition is false")
```

Output:

```text
List is empty or condition is false
```

ব্যাখ্যা:

1. `numbers` একটি Empty List, তাই এটি Falsy।
2. `and`-এর প্রথম Operand Falsy হওয়ায় দ্বিতীয় Condition Evaluate হয় না।
3. ফলে `numbers[0]` Access করার চেষ্টা করা হয় না এবং `IndexError` এড়ানো যায়।

যদি List-এ Element থাকে, তাহলে দ্বিতীয় Condition পরীক্ষা করা হবে।

```python
numbers = [15, 20]

if numbers and numbers[0] > 10:
    print("First number is greater than 10")
else:
    print("List is empty or condition is false")
```

Output:

```text
First number is greater than 10
```

এই Pattern-টি Empty Collection পরীক্ষা করে নিরাপদে Element Access করার একটি সাধারণ উপায়।

---

## 7. Checking `None` Before Accessing an Attribute

ধরো, কোনো Variable-এ Object থাকতে পারে, আবার `None`-ও থাকতে পারে। Object না থাকলে তার Attribute Access করার চেষ্টা করলে Error হতে পারে।

```python
user = None

if user and user.name == "Masum":
    print("User found")
else:
    print("User is not available")
```

Output:

```text
User is not available
```

এখানে `user` হলো `None`, যা Falsy। তাই `user.name` Evaluate হয় না।

তবে বাস্তবে `user`-এর Type এবং Attribute নিশ্চিত করে নেওয়া উচিত। এই Example-এ ধরে নেওয়া হয়েছে যে `user` থাকলে তার `name` Attribute রয়েছে।

---

## 8. Short-Circuit Evaluation and Order of Conditions

`and` ও `or`-এর ক্ষেত্রে Condition-এর ক্রম গুরুত্বপূর্ণ হতে পারে, বিশেষ করে যখন কোনো Condition পরের Condition-কে নিরাপদ করে।

### Example: Safe Division

```python
number = 0

if number != 0 and 100 / number > 2:
    print("Condition satisfied")
else:
    print("Cannot divide by zero")
```

Output:

```text
Cannot divide by zero
```

ব্যাখ্যা:

1. `number != 0` False।
2. `and`-এর প্রথম Condition False হওয়ায় দ্বিতীয় Condition Evaluate হয় না।
3. ফলে `100 / number` চালানো হয় না এবং `ZeroDivisionError` এড়ানো যায়।

### Incorrect Order

```python
number = 0

# এই Expression চালালে ZeroDivisionError হবে:
# if 100 / number > 2 and number != 0:
#     print("Condition satisfied")
```

এখানে Division আগে Evaluate হয়। তাই `number != 0` পরীক্ষা করার আগেই Error ঘটে।

**Best Practice:** কোনো Condition পরের Operation-কে নিরাপদ করে তুললে সেই Condition আগে রাখো।

---

## 9. Short-Circuit Evaluation vs Normal Evaluation

Short-Circuit Evaluation-এ সব Operand Evaluate করা হয় না। অন্যদিকে, `and` বা `or` ছাড়া সাধারণ Arithmetic Expression-এ প্রয়োজনীয় Operand Evaluate করতে হয়।

Example:

```python
print(False and (10 / 0 > 1))
print(True or (10 / 0 > 1))
```

Output:

```text
False
True
```

এখানে কোনো Error হয়নি, কারণ Division-এর অংশটুকু Evaluate-ই করা হয়নি।

কিন্তু নিচের Expression-এ Error হবে:

```python
# print(10 / 0)
```

কারণ এখানে Division Operation সরাসরি Evaluate করা হচ্ছে।

**মনে রাখবে:** Short-Circuit শুধু Result নির্ধারণ করার জন্য যথেষ্ট তথ্য পাওয়া গেলে বাকি Operand-এর Evaluation এড়িয়ে যায়।

---

## 10. Common Mistakes

### Mistake 1: Thinking `and` Always Returns `True` or `False`

```python
print(5 and 10)
```

Output:

```text
10
```

এখানে `and` শেষ Truthy Operand `10` Return করেছে।

### Mistake 2: Thinking `or` Evaluates Every Operand

```python
print("Hello" or 10 / 0)
```

Output:

```text
Hello
```

`"Hello"` Truthy হওয়ায় Division Evaluate হয়নি।

### Mistake 3: Placing a Safety Check Too Late

ভুল Order:

```python
# number = 0
# result = 100 / number if number != 0 else None
```

উপরের Conditional Expression-টি আসলে নিরাপদ, কারণ `number != 0` False হলে Division Evaluate হয় না।

কিন্তু `and` দিয়ে লিখলে নিরাপদ Order হলো:

```python
number = 0

if number != 0 and 100 / number > 2:
    print("Valid")
else:
    print("Invalid")
```

### Mistake 4: Assuming the Skipped Operand Has No Side Effects in Every Context

যদি কোনো Function-এর মধ্যে Print, File Write বা Database Update থাকে, Short-Circuit-এর কারণে Function Call বাদ পড়ে যেতে পারে।

তাই গুরুত্বপূর্ণ Side Effect-সহ Function-কে Logical Expression-এর মধ্যে রাখলে সাবধান থাকতে হবে।

---

## 11. Practice Exercises

### Basic Level

1. `False and True`-এর Result কী?
2. `True or False`-এর দ্বিতীয় Operand Evaluate হবে কি?
3. `0 and 100` কী Return করবে?
4. `0 or 100` কী Return করবে?
5. `"" or "Python"`-এর Result কী?

### Intermediate Level

6. কেন `numbers and numbers[0] > 5` Empty List-এর ক্ষেত্রে নিরাপদ?
7. `number != 0 and 100 / number > 2`-এ প্রথম Condition-এর কাজ কী?
8. `True or check()`-এর ক্ষেত্রে `check()` Call হবে কি?
9. `and` ও `or`-এর Short-Circuit আচরণের পার্থক্য লেখো।
10. Short-Circuit Evaluation কীভাবে Error এড়াতে সাহায্য করে?

### Output Prediction

```python
print(False and 10)
print(True and 10)
print(True or 20)
print(False or 20)
print("" or "Hello")
print("A" and 0 and "B")
print([] and "Python")
print([1, 2] and "Python")
```

### Answers

```text
False
10
True
20
Hello
0
[]
Python
```

ব্যাখ্যা:

- `False and 10` → প্রথম Operand Falsy, তাই `False` Return হয়।
- `True and 10` → শেষ Operand `10` Return হয়।
- `True or 20` → প্রথম Operand Truthy, তাই `True` Return হয়।
- `False or 20` → `20` Return হয়।
- `"" or "Hello"` → `"Hello"` Return হয়।
- `"A" and 0 and "B"` → `0` Return হয়।
- `[] and "Python"` → Empty List `[]` Return হয়।
- `[1, 2] and "Python"` → List Truthy হওয়ায় `"Python"` Return হয়।

---

## 12. Chapter Summary

- Short-Circuit Evaluation হলো Result নির্ধারিত হয়ে গেলে বাকি Operand Evaluate না করা।
- `and` প্রথম Falsy Operand পেলে সেটি Return করে।
- `or` প্রথম Truthy Operand পেলে সেটি Return করে।
- Function Call-এর মতো Operation Short-Circuit-এর কারণে বাদ পড়তে পারে।
- Empty List পরীক্ষা করে Element Access করার আগে `and` ব্যবহার করা যায়।
- Division-এর আগে Divisor Zero নয় কি না পরীক্ষা করা যায়।
- Condition-এর সঠিক Order Error এড়াতে সাহায্য করে।
- `and` ও `or` সব সময় Boolean Value Return করে না।
- Side Effect-সহ Function Logical Expression-এ ব্যবহার করার সময় সতর্ক থাকা প্রয়োজন।

## 13. Self-Assessment Checklist

- [ ] Short-Circuit Evaluation ব্যাখ্যা করতে পারি।
- [ ] `and`-এর Short-Circuit আচরণ বুঝি।
- [ ] `or`-এর Short-Circuit আচরণ বুঝি।
- [ ] Function Call কখন বাদ পড়ে তা বুঝি।
- [ ] Empty List-এর ক্ষেত্রে নিরাপদে Element Access করতে পারি।
- [ ] Division-এর আগে Zero Check করতে পারি।
- [ ] Output Prediction Exercise সমাধান করতে পারি।

**Next Topic:** `14_Assignment_Operators.md`