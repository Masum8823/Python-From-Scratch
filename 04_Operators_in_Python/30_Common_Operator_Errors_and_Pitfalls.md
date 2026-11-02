# 30. Common Operator Errors and Pitfalls in Python

## 1. Introduction

Python-এ operator ব্যবহার করে calculation, comparison, logical decision এবং আরও অনেক কাজ করা যায়। তবে operator ভুলভাবে ব্যবহার করলে unexpected output, `TypeError`, `SyntaxError` বা `ZeroDivisionError` হতে পারে।

এই অধ্যায়ে আমরা শিখব:

- Arithmetic operator-এর সাধারণ ভুল
- Comparison ও logical operator-এর ভুল
- Assignment এবং equality-এর পার্থক্য
- Integer division ও floating-point result
- Operator precedence ও associativity-এর ভুল
- Identity এবং equality-এর পার্থক্য
- Bitwise operator-এর ভুল
- Error শনাক্ত ও সমাধানের কৌশল

---

## 2. Confusing `=` and `==`

Python-এ `=` এবং `==` সম্পূর্ণ আলাদা কাজ করে।

- `=` হলো assignment operator; variable-এ value assign করে।
- `==` হলো equality comparison operator; দুটি value সমান কি না পরীক্ষা করে।

### Incorrect Example

```python
x = 10

if x = 10:
    print("Equal")
```

**Error:** `SyntaxError`

কারণ `if` condition-এর মধ্যে `x = 10` দিয়ে assignment করা যায় না।

### Correct Example

```python
x = 10

if x == 10:
    print("Equal")
```

**Output:**

```text
Equal
```

**মনে রাখবে:** Value assign করতে `=`, আর equality পরীক্ষা করতে `==` ব্যবহার করো।

---

## 3. Division by Zero

কোনো সংখ্যাকে শূন্য দিয়ে ভাগ করলে Python `ZeroDivisionError` দেয়।

### Example

```python
a = 10
b = 0

print(a / b)
```

**Error:**

```text
ZeroDivisionError: division by zero
```

একই সমস্যা `//` এবং `%` operator-এর ক্ষেত্রেও হয়।

```python
print(10 // 0)
print(10 % 0)
```

প্রথম expression-এই error হবে। তাই দ্বিতীয় expression কার্যকর হবে না।

### Solution

ভাগ করার আগে divisor শূন্য কি না পরীক্ষা করো।

```python
a = 10
b = 0

if b != 0:
    print(a / b)
else:
    print("Cannot divide by zero")
```

**Output:**

```text
Cannot divide by zero
```

---

## 4. Confusing `/` and `//`

`/` এবং `//` একই ধরনের division নয়।

- `/` সাধারণ division করে।
- `//` floor division করে; ফলাফল নিচের পূর্ণসংখ্যার দিকে floor হয়, তবে result-এর type operand-এর ওপর নির্ভর করতে পারে।

### Example

```python
print(7 / 2)
print(7 // 2)
```

**Output:**

```text
3.5
3
```

Negative number-এর ক্ষেত্রে floor division আরও গুরুত্বপূর্ণ।

```python
print(-7 // 2)
```

**Output:**

```text
-4
```

কারণ \(-7/2=-3.5\), এবং floor হলো \(-4\)।

এটিকে zero-এর দিকে truncate করলে `-3` হতো, কিন্তু Python floor division তা করে না।

---

## 5. Misunderstanding the Modulo Operator

Modulo operator `%` division-এর remainder বা অবশিষ্টাংশের সঙ্গে সম্পর্কিত।

তবে Python-এ result-এর sign divisor-এর sign-এর সঙ্গে সামঞ্জস্যপূর্ণ হয়।

### Example

```python
print(7 % 3)
print(-7 % 3)
print(7 % -3)
```

**Output:**

```text
1
2
-2
```

ব্যাখ্যা:

```python
-7 == (-3 * 3) + 2
7 == (-3 * -3) + -2
```

সাধারণভাবে Python-এ:

```python
a == (a // b) * b + (a % b)
```

যখন `b` শূন্য নয়, তখন এই সম্পর্কটি প্রযোজ্য।

**Common mistake:** Negative number-এর modulo result সব সময় positive হবে ধরে নেওয়া। বাস্তবে result-এর sign divisor-এর sign-এর সঙ্গে সম্পর্কিত।

---

## 6. Confusing `**` with `^`

Python-এ exponentiation-এর operator হলো `**`, `^` নয়।

- `**` হলো power বা exponentiation।
- `^` হলো bitwise XOR।

### Incorrect for Power

```python
print(2 ^ 3)
```

**Output:**

```text
1
```

এটি `2`-এর power `3` নয়।

### Correct Example

```python
print(2 ** 3)
```

**Output:**

```text
8
```

**মনে রাখবে:** Power-এর জন্য `**`, আর bitwise XOR-এর জন্য `^`।

---

## 7. Operator Precedence Mistakes

Operator precedence নির্ধারণ করে কোন operator আগে কাজ করবে।

### Example

```python
result = 2 + 3 * 4
print(result)
```

**Output:**

```text
14
```

কারণ multiplication আগে হয়।

অনেকে ভুল করে এভাবে হিসাব করে:

```text
(2 + 3) * 4 = 20
```

কিন্তু expression-এ parentheses নেই।

### Correct Grouping When Needed

```python
result = (2 + 3) * 4
print(result)
```

**Output:**

```text
20
```

**Solution:** Expression জটিল হলে parentheses ব্যবহার করে grouping স্পষ্ট করো।

---

## 8. Exponentiation Associativity Mistakes

Python-এর exponentiation operator `**` right-to-left grouping অনুসরণ করে।

### Example

```python
print(2 ** 3 ** 2)
```

**Output:**

```text
512
```

কারণ:

```python
2 ** (3 ** 2)
2 ** 9
512
```

এটিকে `(2 ** 3) ** 2` হিসেবে হিসাব করা হয় না।

```python
print((2 ** 3) ** 2)
```

**Output:**

```text
64
```

**Solution:** একাধিক `**` থাকলে grouping বুঝে নাও; প্রয়োজন হলে parentheses ব্যবহার করো।

---

## 9. Unary Minus and Exponentiation

Negative sign এবং exponentiation একসঙ্গে থাকলে ভুল output অনুমান করা সহজ।

### Example

```python
print(-3 ** 2)
print((-3) ** 2)
```

**Output:**

```text
-9
9
```

ব্যাখ্যা:

```python
-3 ** 2
```

এটি `-(3 ** 2)` হিসেবে group হয়।

অন্যদিকে:

```python
(-3) ** 2
```

এখানে পুরো `-3` হলো base।

**Solution:** Negative number-কে exponentiation-এর base হিসেবে ব্যবহার করতে চাইলে parentheses দাও।

---

## 10. Confusing `and` and `or`

Logical operator ভুলভাবে ব্যবহার করলে condition-এর ফল প্রত্যাশার বাইরে যেতে পারে।

### Example

ধরো, একজন শিক্ষার্থীর বয়স 18 থেকে 25-এর মধ্যে হতে হবে।

**Incorrect Logic:**

```python
age = 30

if age >= 18 or age <= 25:
    print("Eligible")
else:
    print("Not Eligible")
```

**Output:**

```text
Eligible
```

এখানে `30 >= 18` সত্য, তাই `or` condition সত্য হয়ে যায়।

### Correct Logic

```python
age = 30

if age >= 18 and age <= 25:
    print("Eligible")
else:
    print("Not Eligible")
```

**Output:**

```text
Not Eligible
```

আরও সংক্ষিপ্তভাবে:

```python
age = 30

if 18 <= age <= 25:
    print("Eligible")
else:
    print("Not Eligible")
```

**Output:**

```text
Not Eligible
```

**মনে রাখবে:**

- `and`: সব condition সত্য হতে হবে।
- `or`: অন্তত একটি condition সত্য হলেই হবে।

---

## 11. Confusing `is` and `==`

`==` value equality পরীক্ষা করে, আর `is` পরীক্ষা করে দুটি reference একই object-কে নির্দেশ করছে কি না।

### Example

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a == b)
print(a is b)
```

**Output:**

```text
True
False
```

দুটি list-এর content একই, তাই `a == b` সত্য। কিন্তু এগুলো আলাদা list object, তাই `a is b` মিথ্যা।

### Common Mistake

```python
value = 1000

if value is 1000:
    print("Equal")
```

এভাবে value comparison করা উচিত নয়। Identity comparison-এর ফল object creation এবং implementation-এর ওপর নির্ভর করতে পারে।

### Correct Example

```python
value = 1000

if value == 1000:
    print("Equal")
```

**Output:**

```text
Equal
```

`None` পরীক্ষা করার সময় সাধারণত `is` ব্যবহার করা হয়:

```python
result = None

if result is None:
    print("No result")
```

**Output:**

```text
No result
```

---

## 12. Confusing `in` with Other Operators

`in` operator কোনো collection-এর মধ্যে একটি value আছে কি না পরীক্ষা করে।

### Example

```python
numbers = [10, 20, 30]

print(20 in numbers)
print(40 in numbers)
```

**Output:**

```text
True
False
```

### Common Mistake with Dictionaries

```python
student = {
    "name": "Masum",
    "age": 22
}

print("name" in student)
print("Masum" in student)
```

**Output:**

```text
True
False
```

Dictionary-এর ক্ষেত্রে `in` সাধারণত key পরীক্ষা করে, value নয়।

Value পরীক্ষা করতে:

```python
print("Masum" in student.values())
```

**Output:**

```text
True
```

---

## 13. Confusing `not`, `and`, and `or`

Logical operators-এর precedence আলাদা। Python-এ `not`-এর precedence `and` এবং `or`-এর চেয়ে বেশি।

### Example

```python
print(not True or True)
```

**Output:**

```text
True
```

এটি এভাবে group হয়:

```python
(not True) or True
False or True
True
```

Complex condition-এ parentheses ব্যবহার করলে intention পরিষ্কার হয়।

```python
age = 20
has_id = False

result = (age >= 18) and has_id
print(result)
```

**Output:**

```text
False
```

---

## 14. Short-Circuit Evaluation Pitfalls

Python-এর `and` এবং `or` short-circuit evaluation করে। অর্থাৎ, ফলাফল নির্ধারণ হয়ে গেলে পরের operand evaluate নাও হতে পারে।

### Example

```python
x = 0

result = x != 0 and 10 / x > 1
print(result)
```

**Output:**

```text
False
```

এখানে `x != 0` মিথ্যা। তাই `10 / x` evaluate করা হয় না এবং `ZeroDivisionError` হয় না।

### Common Mistake

```python
x = 0

result = x == 0 or 10 / x > 1
print(result)
```

**Output:**

```text
True
```

এখানে প্রথম condition সত্য, তাই দ্বিতীয় operand evaluate করা হয় না।

**গুরুত্বপূর্ণ:** Short-circuit behaviour কাজে লাগানো যায়, তবে complex condition এমনভাবে লিখবে যেন code সহজে বোঝা যায়।

---

## 15. Augmented Assignment Mistakes

Augmented assignment operator যেমন `+=`, `-=`, `*=`, `/=` আগের value-এর সঙ্গে operation করে assignment করতে সাহায্য করে।

### Example

```python
x = 10
x += 5

print(x)
```

**Output:**

```text
15
```

এটি অনেকটা নিচের code-এর সমতুল্য:

```python
x = x + 5
```

### Common Mistake

```python
x = 10
x =+ 5

print(x)
```

**Output:**

```text
5
```

`=+` হলো `=`-এর পরে unary `+`; এটি `+=` নয়।

সঠিক code:

```python
x = 10
x += 5

print(x)
```

**Output:**

```text
15
```

**মনে রাখবে:** `+=` এবং `=+` এক নয়।

---

## 16. Integer Division and Data Types

Python-এ `/` সাধারণত floating-point result দেয়, এমনকি ভাগফল পূর্ণসংখ্যা হলেও।

### Example

```python
print(10 / 2)
print(10 // 2)
```

**Output:**

```text
5.0
5
```

প্রথমটি `float`, দ্বিতীয়টি এখানে `int`।

### Common Mistake

যদি program-এ integer result প্রয়োজন হয়, তাহলে `/` ব্যবহার করে সরাসরি integer পাওয়া যাবে ধরে নেওয়া ঠিক নয়।

```python
result = 10 / 2

print(type(result))
```

**Output:**

```text
<class 'float'>
```

প্রয়োজন অনুযায়ী `//` অথবা উপযুক্ত type conversion ব্যবহার করো। তবে মনে রাখবে, `//` negative number-এর ক্ষেত্রে floor করে, শুধু decimal অংশ বাদ দেয় না।

---

## 17. Floating-Point Precision Issues

Floating-point number কম্পিউটারে binary representation-এর কারণে কখনো কখনো প্রত্যাশিত decimal value-এর খুব কাছাকাছি কিন্তু পুরোপুরি সমান নয়—এমন ফল দিতে পারে।

### Example

```python
print(0.1 + 0.2)
print(0.1 + 0.2 == 0.3)
```

সাধারণ Python implementation-এ output:

```text
0.30000000000000004
False
```

এটি floating-point representation-এর সীমাবদ্ধতার একটি উদাহরণ।

### Solution

Approximate comparison-এর জন্য `math.isclose()` ব্যবহার করা যায়।

```python
import math

print(math.isclose(0.1 + 0.2, 0.3))
```

**Output:**

```text
True
```

Financial calculation-এর মতো ক্ষেত্রে নির্ভুল decimal arithmetic দরকার হলে `decimal.Decimal` বিবেচনা করা যায়।

---

## 18. Bitwise Operator Mistakes

Bitwise operator সংখ্যার binary representation-এর ওপর কাজ করে।

### Example

```python
print(5 & 3)
print(5 | 3)
print(5 ^ 3)
```

**Output:**

```text
1
7
6
```

কারণ:

```text
5 = 101
3 = 011
```

- `5 & 3`: উভয় bit `1` হলে `1` → `001` = `1`
- `5 | 3`: যেকোনো একটি bit `1` হলে `1` → `111` = `7`
- `5 ^ 3`: bit দুটি আলাদা হলে `1` → `110` = `6`

### Common Mistake

```python
print(5 and 3)
```

**Output:**

```text
3
```

এটি bitwise AND নয়; এটি logical `and`। Python-এ non-zero integer truthy হওয়ায় এখানে `3` return হয়েছে।

Bitwise AND চাইলে:

```python
print(5 & 3)
```

**Output:**

```text
1
```

**মনে রাখবে:** `and` logical operator, আর `&` bitwise operator।

---

## 19. Chained Comparison Mistakes

Python-এ একাধিক comparison chain করা যায়।

### Example

```python
x = 5

print(1 < x < 10)
```

**Output:**

```text
True
```

এটি বোঝায়:

```python
1 < x and x < 10
```

### Common Mistake

```python
x = 15

if 1 < x < 10:
    print("Inside range")
else:
    print("Outside range")
```

**Output:**

```text
Outside range
```

এখানে `x`-এর মান `15`, তাই range-এর মধ্যে নেই।

Condition লেখার সময় range-এর lower ও upper bound সঠিকভাবে দাও।

---

## 20. Conditional Expression Mistakes

Conditional expression-এর সঠিক syntax হলো:

```python
value_if_true if condition else value_if_false
```

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

### Common Mistake

```python
status = if age >= 18 "Adult" else "Minor"
```

এটি invalid syntax।

সঠিক:

```python
status = "Adult" if age >= 18 else "Minor"
```

আরেকটি গুরুত্বপূর্ণ বিষয় হলো, conditional expression-এ `else` অংশ আবশ্যক।

---

## 21. Operator Overloading Mistakes

Custom class-এর object-এর জন্য operator ব্যবহার করতে চাইলে উপযুক্ত special method বাস্তবায়ন করতে হতে পারে।

### Example

```python
class Number:
    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        return self.value + other.value


a = Number(10)
b = Number(20)

print(a + b)
```

**Output:**

```text
30
```

### Common Mistake

`+` operator-এর জন্য ভুল method name ব্যবহার করা, যেমন `__addition__()`।

সঠিক method:

```python
def __add__(self, other):
    ...
```

Unsupported operand-এর ক্ষেত্রে custom class-এর behaviour কী হবে, সেটিও বিবেচনা করতে হবে।

---

## 22. Operator Errors Debugging Checklist

Operator-সংক্রান্ত ভুল হলে নিচের checklist অনুসরণ করো।

- [ ] `=` ও `==` সঠিকভাবে ব্যবহার করেছি কি?
- [ ] Division-এর divisor শূন্য কি না পরীক্ষা করেছি কি?
- [ ] `/` ও `//`-এর পার্থক্য বুঝেছি কি?
- [ ] Power-এর জন্য `**` ব্যবহার করেছি কি?
- [ ] Operator precedence ও associativity বিবেচনা করেছি কি?
- [ ] Logical condition-এ `and` ও `or` সঠিকভাবে ব্যবহার করেছি কি?
- [ ] Value comparison-এর জন্য `==`, identity-এর জন্য `is` ব্যবহার করেছি কি?
- [ ] Dictionary-তে key এবং value membership-এর পার্থক্য বুঝেছি কি?
- [ ] Floating-point result-এর precision বিবেচনা করেছি কি?
- [ ] `and` ও `&`-এর পার্থক্য বুঝেছি কি?
- [ ] Conditional expression-এর syntax সঠিক কি?
- [ ] Error message দেখে সংশ্লিষ্ট line পরীক্ষা করেছি কি?

---

## 23. Practice Exercises

প্রথমে নিজে output অনুমান করো। তারপর Answer Key দেখো।

### Exercise 1

```python
x = 10
x += 5
print(x)
```

### Exercise 2

```python
print(2 + 3 * 4)
```

### Exercise 3

```python
print(2 ** 3 ** 2)
```

### Exercise 4

```python
print(7 // 2)
print(-7 // 2)
```

### Exercise 5

```python
print(5 ^ 3)
```

### Exercise 6

```python
x = 0
print(x != 0 and 10 / x > 1)
```

### Exercise 7

```python
a = [1, 2]
b = [1, 2]

print(a == b)
print(a is b)
```

### Exercise 8

```python
student = {"name": "Masum"}

print("Masum" in student)
print("Masum" in student.values())
```

### Exercise 9

```python
print(10 / 2)
print(type(10 / 2))
```

### Exercise 10

```python
age = 16
print("Adult" if age >= 18 else "Minor")
```

### Answer Key

| Exercise | Output | Explanation |
|---|---|---|
| 1 | `15` | `+=` value যোগ করে assign করে |
| 2 | `14` | Multiplication আগে হয় |
| 3 | `512` | `**` right-to-left group হয় |
| 4 | `3`, `-4` | Floor division floor value দেয় |
| 5 | `6` | `^` bitwise XOR |
| 6 | `False` | Short-circuit-এর কারণে division হয় না |
| 7 | `True`, `False` | Value একই, list object আলাদা |
| 8 | `False`, `True` | `in` dictionary-তে key পরীক্ষা করে; `.values()` value পরীক্ষা করে |
| 9 | `5.0`, `<class 'float'>` | `/` floating-point result দেয় |
| 10 | `Minor` | Condition মিথ্যা |

---

## 24. Quick Revision

- `=` assignment করে, `==` equality পরীক্ষা করে।
- শূন্য দিয়ে ভাগ করলে `ZeroDivisionError` হয়।
- `/` ও `//`-এর কাজ আলাদা।
- `**` exponentiation করে, `^` bitwise XOR করে।
- Precedence ও associativity ভুল বুঝলে output ভুল হতে পারে।
- `and` ও `or` logical operator; `&` ও `|` bitwise operator।
- `==` value তুলনা করে, `is` object identity পরীক্ষা করে।
- Dictionary-তে `in` সাধারণত key পরীক্ষা করে।
- Floating-point calculation-এ precision issue হতে পারে।
- `+=` ও `=+` এক নয়।
- Conditional expression-এ `else` আবশ্যক।
- Complex expression-এ parentheses ব্যবহার করলে code বোঝা সহজ হয়।

## 25. Self-Assessment Checklist

- [ ] Assignment ও equality-এর পার্থক্য বুঝি।
- [ ] Division-related error শনাক্ত করতে পারি।
- [ ] Arithmetic operator-এর precedence বুঝি।
- [ ] Logical ও bitwise operator আলাদা করতে পারি।
- [ ] Identity ও equality-এর পার্থক্য বুঝি।
- [ ] Short-circuit evaluation ব্যাখ্যা করতে পারি।
- [ ] Floating-point precision issue চিনতে পারি।
- [ ] Operator-সংক্রান্ত error debug করতে পারি।
- [ ] Code execute করার আগে output অনুমান করতে পারি।

পরবর্তী Topic: **31. Operator-Based Problem Solving**