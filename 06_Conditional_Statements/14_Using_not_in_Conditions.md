# 14. Using `not` in Conditions

## 1. Introduction

Python-এ `not` হলো একটি **Logical Operator**, যা কোনো condition-এর truth value উল্টে দেয়।

- `True`-এর আগে `not` দিলে ফলাফল `False` হয়।
- `False`-এর আগে `not` দিলে ফলাফল `True` হয়।

Example:

```python
print(not True)
print(not False)
```

Output:

```text
False
True
```

সহজভাবে, `not` মানে **নয়** বা **বিপরীত অবস্থা**।

যেমন:

- Account active নয়।
- User logged in নয়।
- Number positive নয়।
- Name empty নয়।

এ ধরনের condition পরীক্ষা করতে `not` ব্যবহার করা যায়।

## 2. Syntax of `not`

সাধারণ syntax:

```python
if not condition:
    statement
```

Example:

```python
is_raining = False

if not is_raining:
    print("You can go outside")
else:
    print("It is raining")
```

Output:

```text
You can go outside
```

এখানে `is_raining`-এর value `False`। তাই `not is_raining`-এর ফলাফল `True` হয়েছে।

## 3. Truth Table of `not`

`not` operator-এর truth table:

| Condition | Result of `not` |
|---|---|
| `True` | `False` |
| `False` | `True` |

Example:

```python
a = True
b = False

print(not a)
print(not b)
```

Output:

```text
False
True
```

**মনে রাখবে:** `not` একটি unary operator। অর্থাৎ এটি একটি operand বা expression-এর ওপর কাজ করে।

## 4. Using `not` with Comparison Operators

কোনো comparison সত্য নয়—এটি পরীক্ষা করতেও `not` ব্যবহার করা যায়।

Example:

```python
age = 16

if not age >= 18:
    print("Under 18")
else:
    print("18 or older")
```

Output:

```text
Under 18
```

এখানে:

1. `age >= 18`-এর ফলাফল `False`।
2. `not False` হয় `True`।
3. তাই `Under 18` print হয়।

তবে একই condition আরও সরাসরি লেখা যায়:

```python
if age < 18:
    print("Under 18")
```

সহজ comparison থাকলে সরাসরি বিপরীত operator ব্যবহার করলে code বেশি readable হয়।

## 5. Using `not` with Boolean Variables

Boolean variable-এর value `True` অথবা `False` হতে পারে।

Example:

```python
is_logged_in = False

if not is_logged_in:
    print("Please log in")
else:
    print("Welcome back")
```

Output:

```text
Please log in
```

এখানে user logged in নয়। তাই `not is_logged_in` সত্য হয়েছে।

আরেকটি উদাহরণ:

```python
is_active = True

if not is_active:
    print("Account is inactive")
else:
    print("Account is active")
```

Output:

```text
Account is active
```

এখানে `is_active` সত্য হওয়ায় `not is_active` মিথ্যা হয়েছে এবং `else` execute হয়েছে।

## 6. Using `not` with Empty Strings

Python-এ empty string (`""`) একটি **Falsy Value**।

তাই empty string-এর আগে `not` ব্যবহার করলে ফলাফল `True` হয়।

Example:

```python
name = ""

if not name:
    print("Name is empty")
else:
    print("Name is available")
```

Output:

```text
Name is empty
```

এখানে `name` empty হওয়ায় এটি falsy। তাই `not name` সত্য হয়েছে।

### Practical Example: Name Validation

```python
name = input("Enter your name: ").strip()

if not name:
    print("Name cannot be empty")
else:
    print("Hello", name)
```

Sample Input:

```text
Enter your name:
```

Output:

```text
Name cannot be empty
```

এখানে `.strip()` input-এর শুরু ও শেষের whitespace সরিয়ে দেয়। ফলে শুধু spaces দেওয়া হলেও name-টি empty হিসেবে ধরা হয়।

## 7. Using `not` with Numbers

Python-এ `0` একটি falsy value। কিন্তু non-zero integer সাধারণত truthy হয়।

Example:

```python
number = 0

if not number:
    print("Number is zero")
else:
    print("Number is non-zero")
```

Output:

```text
Number is zero
```

কারণ `not 0`-এর ফলাফল `True`।

তবে গুরুত্বপূর্ণ বিষয় হলো, `if not number` শুধু zero পরীক্ষা করে না; এটি সব falsy numeric value-ও গ্রহণ করে, যেমন `0.0`।

যদি নির্দিষ্টভাবে zero পরীক্ষা করতে চাও, তাহলে এটি বেশি স্পষ্ট:

```python
if number == 0:
    print("Number is zero")
```

## 8. Using `not` with Lists

Empty list (`[]`) একটি falsy value। Non-empty list truthy হয়।

Example:

```python
items = []

if not items:
    print("List is empty")
else:
    print("List has items")
```

Output:

```text
List is empty
```

Non-empty list-এর উদাহরণ:

```python
items = ["Python", "Java"]

if not items:
    print("List is empty")
else:
    print("List has items")
```

Output:

```text
List has items
```

### Practical Example: Checking a Shopping Cart

```python
cart = []

if not cart:
    print("Your cart is empty")
else:
    print("Proceed to checkout")
```

Output:

```text
Your cart is empty
```

এখানে cart empty কি না তা পরীক্ষা করা হয়েছে।

এই pattern list, tuple, dictionary এবং set-এর মতো collection-এর ক্ষেত্রেও ব্যবহার করা যায়।

## 9. Using `not` with Membership Operators

কোনো item list, tuple, set বা string-এর মধ্যে নেই কি না পরীক্ষা করতে `not in` ব্যবহার করা যায়।

Example:

```python
languages = ["Python", "Java", "C++"]

if "PHP" not in languages:
    print("PHP is not available")
else:
    print("PHP is available")
```

Output:

```text
PHP is not available
```

এখানে `"PHP"` list-এর মধ্যে নেই। তাই `"PHP" not in languages` সত্য হয়েছে।

### Another Example

```python
username = "masum"

if username not in ("admin", "root"):
    print("Regular user")
else:
    print("Privileged username")
```

Output:

```text
Regular user
```

এখানে username অনুমোদিত privileged username-গুলোর মধ্যে নেই।

## 10. Using `not` with `and` and `or`

`not`-কে `and` এবং `or`-এর সঙ্গে ব্যবহার করা যায়।

Example:

```python
is_logged_in = True
is_banned = False

if is_logged_in and not is_banned:
    print("Access granted")
else:
    print("Access denied")
```

Output:

```text
Access granted
```

এখানে:

- `is_logged_in` সত্য।
- `is_banned` মিথ্যা।
- `not is_banned` সত্য।
- তাই `True and True`-এর ফলাফল সত্য।

### Another Example

```python
has_ticket = False
is_invited = True

if not has_ticket and is_invited:
    print("Entry allowed")
else:
    print("Entry denied")
```

Output:

```text
Entry allowed
```

এখানে ticket নেই, কিন্তু invitation আছে। Condition-এ `not has_ticket` এবং `is_invited`—দুটি সত্য হয়েছে।

## 11. Operator Precedence of `not`

Python-এ `not`-এর precedence `and` এবং `or`-এর চেয়ে বেশি।

Example:

```python
a = True
b = False
c = False

print(not a and b)
print(not (a and b))
print(a or not b)
```

Output:

```text
False
True
True
```

ব্যাখ্যা:

1. `not a and b` → `False and False` → `False`
2. `not (a and b)` → `not False` → `True`
3. `a or not b` → `True or True` → `True`

Parentheses ব্যবহার করলে expression-এর intended meaning আরও স্পষ্ট হয়।

## 12. Difference Between `not`, `!=` and `is not`

এই তিনটি এক জিনিস নয়।

### `not`

কোনো expression-এর truth value উল্টে দেয়।

```python
is_active = True
print(not is_active)
```

Output:

```text
False
```

### `!=`

দুটি value সমান নয় কি না পরীক্ষা করে।

```python
print(10 != 5)
```

Output:

```text
True
```

### `is not`

দুটি reference একই object নির্দেশ করছে কি না পরীক্ষা করে।

```python
value = None

if value is not None:
    print("Has a value")
else:
    print("No value")
```

Output:

```text
No value
```

**মনে রাখবে:**

| Operator | Purpose |
|---|---|
| `not x` | `x`-এর truth value উল্টে দেয় |
| `x != y` | `x` ও `y`-এর value সমান নয় কি না পরীক্ষা করে |
| `x is not y` | `x` ও `y` একই object নয় কি না পরীক্ষা করে |

`None` পরীক্ষা করার জন্য সাধারণত `is None` অথবা `is not None` ব্যবহার করা হয়।

## 13. De Morgan's Laws

`not`, `and` এবং `or`-এর সম্পর্ক বোঝার জন্য De Morgan's Laws গুরুত্বপূর্ণ।

দুটি নিয়ম:

1. `not (A and B)` সমতুল্য `(not A) or (not B)`।
2. `not (A or B)` সমতুল্য `(not A) and (not B)`।

### Example 1

```python
a = True
b = False

print(not (a and b))
print((not a) or (not b))
```

Output:

```text
True
True
```

দুটি expression-এর result একই।

### Example 2

```python
a = True
b = False

print(not (a or b))
print((not a) and (not b))
```

Output:

```text
False
False
```

এই নিয়মগুলো complex conditions সহজ করার জন্য কাজে লাগে।

## 14. Common Mistakes

### Mistake 1: Confusing `not` with `!=`

Incorrect:

```python
if not age == 18:
    print("Not 18")
```

এই code valid, কিন্তু পড়তে কিছুটা কঠিন হতে পারে।

আরও সহজভাবে:

```python
if age != 18:
    print("Not 18")
```

### Mistake 2: Using `not` When Direct Comparison Is Clearer

```python
if not age >= 18:
    print("Under 18")
```

এটি valid। তবে নিচের version সাধারণত আরও পরিষ্কার:

```python
if age < 18:
    print("Under 18")
```

### Mistake 3: Forgetting Truthiness

```python
name = "False"

if not name:
    print("Empty")
else:
    print("Not empty")
```

Output:

```text
Not empty
```

কারণ `"False"` একটি non-empty string। এটি Boolean `False` নয়।

### Mistake 4: Confusing Empty and Whitespace Strings

```python
name = "   "

if not name:
    print("Empty")
else:
    print("Not empty")
```

Output:

```text
Not empty
```

কারণ string-এ spaces আছে। শুধু empty string নয়, whitespace-only input-ও খালি হিসেবে ধরতে চাইলে `.strip()` ব্যবহার করো।

### Mistake 5: Using `not` Incorrectly with Multiple Conditions

```python
if not age >= 18 and has_id:
    print("Condition satisfied")
```

এটি এমন অর্থ দেয়:

```python
if (not (age >= 18)) and has_id:
```

অর্থাৎ বয়স 18-এর কম এবং পরিচয়পত্র আছে—দুটি শর্তই সত্য হতে হবে।

তাই complex expression-এ parentheses দিয়ে logic পরিষ্কার রাখা ভালো।

## 15. Practice Exercises

নিজে solve করার চেষ্টা করো।

### Exercise 1: Login Check

`is_logged_in = False` দিয়ে শুরু করো। User logged in না থাকলে `Please log in` print করো।

### Exercise 2: Empty Name

একটি name input নাও। `.strip()` ব্যবহার করে name empty কি না পরীক্ষা করো। Empty হলে error message দেখাও।

### Exercise 3: Empty List

একটি empty list তৈরি করো। `not` ব্যবহার করে list empty কি না পরীক্ষা করো।

### Exercise 4: Membership

একটি list তৈরি করো:

```python
languages = ["Python", "Java", "C++"]
```

`"PHP"` list-এর মধ্যে না থাকলে `PHP is unavailable` print করো।

### Exercise 5: Output Prediction

```python
a = True
b = False

print(not a)
print(not b)
print(not (a and b))
```

Output কী হবে?

### Exercise 6: Output Prediction

```python
items = []

if not items:
    print("Empty")
else:
    print("Not empty")
```

Output কী হবে?

### Exercise 7: Fix the Logic

নিচের code-টি এমনভাবে লেখো, যেন account blocked না থাকলে `Account available` print হয়।

```python
is_blocked = False
```

### Exercise 8: Apply De Morgan's Law

নিচের expression-টির সমতুল্য expression লেখো:

```python
not (a or b)
```

### Exercise 9: Distinguish Operators

`not`, `!=` এবং `is not`—এই তিনটির পার্থক্য নিজের ভাষায় ব্যাখ্যা করো এবং প্রতিটির একটি example লেখো।

## 16. Practice Answer Key

### Answer 1

```python
is_logged_in = False

if not is_logged_in:
    print("Please log in")
```

### Answer 2

```python
name = input("Enter your name: ").strip()

if not name:
    print("Name cannot be empty")
else:
    print("Hello", name)
```

### Answer 3

```python
items = []

if not items:
    print("List is empty")
else:
    print("List has items")
```

### Answer 4

```python
languages = ["Python", "Java", "C++"]

if "PHP" not in languages:
    print("PHP is unavailable")
```

### Answer 5

```text
False
True
True
```

### Answer 6

```text
Empty
```

### Answer 7

```python
is_blocked = False

if not is_blocked:
    print("Account available")
```

### Answer 8

```python
(not a) and (not b)
```

### Answer 9

- `not x`: `x`-এর truth value উল্টে দেয়।
- `x != y`: দুটি value সমান নয় কি না পরীক্ষা করে।
- `x is not y`: দুটি reference একই object নির্দেশ করে না কি না পরীক্ষা করে।

## 17. Chapter Summary

- `not` operator কোনো condition-এর truth value উল্টে দেয়।
- `not True` → `False` এবং `not False` → `True`।
- Empty string, empty list এবং zero-এর মতো falsy value-এর সঙ্গে `not` ব্যবহার করা যায়।
- `not in` দিয়ে কোনো item collection-এর মধ্যে নেই কি না পরীক্ষা করা যায়।
- `not`-এর precedence `and` ও `or`-এর চেয়ে বেশি।
- `not`, `!=` এবং `is not`-এর কাজ আলাদা।
- De Morgan's Laws complex condition সহজ করতে সাহায্য করে।
- Code readable রাখতে যেখানে সম্ভব সরাসরি comparison ব্যবহার করো।

## 18. Self-Assessment Checklist

- [ ] `not` operator-এর কাজ ব্যাখ্যা করতে পারি।
- [ ] `not`-এর truth table মনে আছে।
- [ ] `not` দিয়ে Boolean variable পরীক্ষা করতে পারি।
- [ ] Empty string ও empty collection পরীক্ষা করতে পারি।
- [ ] `not in` ব্যবহার করতে পারি।
- [ ] `not`, `!=` ও `is not`-এর পার্থক্য বুঝি।
- [ ] De Morgan's Laws ব্যাখ্যা করতে পারি।
- [ ] `not` ব্যবহার করে practical conditions লিখতে পারি।

## 19. Next Topic

পরবর্তী file:

`15_Operator_Precedence_in_Conditions.md`

সেখানে comparison operators, `not`, `and` ও `or` একসঙ্গে থাকলে Python কোন ক্রমে condition evaluate করে, তা উদাহরণসহ শেখা হবে।