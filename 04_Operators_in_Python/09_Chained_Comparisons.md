# 09. Chained Comparisons in Python

## 1. Introduction to Chained Comparisons

Python-এ একাধিক Comparison Operator একসঙ্গে ব্যবহার করে কোনো Value একাধিক Condition পূরণ করে কি না পরীক্ষা করা যায়। একে **Chained Comparison** বলে।

Example:

```python
age = 20

print(18 <= age <= 25)
```

Output:

```text
True
```

এখানে Python পরীক্ষা করছে:

- `18 <= age`
- `age <= 25`

দুটি Condition-ই সত্য, তাই Result `True`।

Chained Comparison বিশেষভাবে কাজে লাগে যখন কোনো Number নির্দিষ্ট Range-এর মধ্যে আছে কি না পরীক্ষা করতে হয়।

## 2. Basic Syntax

সাধারণ Syntax:

```python
a < b < c
```

এটি নিচের দুটি Comparison-এর সমতুল্য:

```python
a < b and b < c
```

Example:

```python
number = 15

print(10 < number < 20)
```

Output:

```text
True
```

কারণ:

- `10 < 15` → `True`
- `15 < 20` → `True`

তাই পুরো Expression-এর Result `True`।

## 3. Chained Comparison with Different Operators

Chained Comparison-এ একই Operator বারবার ব্যবহার করা বাধ্যতামূলক নয়। বিভিন্ন Comparison Operator-ও ব্যবহার করা যায়।

| Expression | অর্থ |
|---|---|
| `a < b < c` | `a < b` এবং `b < c` |
| `a <= b <= c` | `a <= b` এবং `b <= c` |
| `a < b <= c` | `a < b` এবং `b <= c` |
| `a >= b > c` | `a >= b` এবং `b > c` |

Example:

```python
number = 10

print(5 < number <= 10)
print(5 <= number < 10)
print(10 >= number > 5)
```

Output:

```text
True
False
True
```

ব্যাখ্যা:

- `5 < 10 <= 10` → `True`
- `5 <= 10 < 10` → `False`
- `10 >= 10 > 5` → `True`

## 4. Checking Whether a Number Is Within a Range

Chained Comparison-এর সবচেয়ে সাধারণ ব্যবহার হলো কোনো Number একটি Range-এর মধ্যে আছে কি না পরীক্ষা করা।

Example:

```python
number = 15

print(10 <= number <= 20)
```

Output:

```text
True
```

এখানে `number`-এর মান 10 থেকে 20-এর মধ্যে রয়েছে, এবং দুই প্রান্তই অন্তর্ভুক্ত।

### Another Example

```python
number = 25

print(10 <= number <= 20)
```

Output:

```text
False
```

কারণ 25, 10 থেকে 20-এর মধ্যে নেই।

## 5. Inclusive and Exclusive Boundaries

Range পরীক্ষা করার সময় Boundary বা সীমা অন্তর্ভুক্ত কি না, তা বুঝতে হবে।

### 5.1 Inclusive Range

`<=` এবং `>=` ব্যবহার করলে সমান হওয়ার সুযোগ থাকে।

```python
number = 10

print(10 <= number <= 20)
```

Output:

```text
True
```

এখানে 10 এবং 20—দুটি Boundary-ই অন্তর্ভুক্ত।

### 5.2 Exclusive Range

`<` এবং `>` ব্যবহার করলে Boundary অন্তর্ভুক্ত হয় না।

```python
number = 10

print(10 < number < 20)
```

Output:

```text
False
```

কারণ `number` ঠিক 10, কিন্তু Condition-এ `number`-কে 10-এর চেয়ে বড় হতে হবে।

### Comparison Table

| Expression | Boundary অন্তর্ভুক্ত? |
|---|---|
| `10 <= x <= 20` | উভয় প্রান্ত অন্তর্ভুক্ত |
| `10 < x < 20` | কোনো প্রান্ত অন্তর্ভুক্ত নয় |
| `10 <= x < 20` | শুধু নিচের প্রান্ত অন্তর্ভুক্ত |
| `10 < x <= 20` | শুধু উপরের প্রান্ত অন্তর্ভুক্ত |

## 6. Chained Comparisons with Variables

একাধিক Variable দিয়েও Chained Comparison করা যায়।

```python
a = 5
b = 10
c = 15

print(a < b < c)
```

Output:

```text
True
```

এখানে Python পরীক্ষা করছে:

```python
a < b and b < c
```

অর্থাৎ:

```python
5 < 10 and 10 < 15
```

দুটি Condition-ই সত্য।

### When One Condition Is False

```python
a = 5
b = 10
c = 8

print(a < b < c)
```

Output:

```text
False
```

কারণ:

- `5 < 10` → `True`
- `10 < 8` → `False`

সবগুলো Comparison সত্য না হলে Chained Comparison-এর Result `True` হবে না।

## 7. Chained Comparisons with `if` Statements

Chained Comparison `if` Statement-এ ব্যবহার করলে Code আরও সংক্ষিপ্ত ও Readable হয়।

Example:

```python
age = 22

if 18 <= age <= 25:
    print("Age is within the range")
else:
    print("Age is outside the range")
```

Output:

```text
Age is within the range
```

এখানে `age` 18 বা তার বেশি এবং 25 বা তার কম কি না পরীক্ষা করা হয়েছে।

### Practical Example: Marks Range

ধরা যাক, Marks 40 থেকে 100-এর মধ্যে কি না পরীক্ষা করতে হবে।

```python
marks = 75

if 40 <= marks <= 100:
    print("Valid Marks")
else:
    print("Invalid Marks")
```

Output:

```text
Valid Marks
```

এখানে উভয় Boundary অন্তর্ভুক্ত।

## 8. Chained Comparisons vs Logical `and`

একটি Range পরীক্ষা করার জন্য Chained Comparison এবং Logical `and`—দুটিই ব্যবহার করা যায়।

### Using Chained Comparison

```python
age = 20

print(18 <= age <= 25)
```

Output:

```text
True
```

### Using Logical `and`

```python
age = 20

print(age >= 18 and age <= 25)
```

Output:

```text
True
```

দুটি Expression-এর Result একই।

| Chained Comparison | Equivalent Logical Expression |
|---|---|
| `10 < x < 20` | `x > 10 and x < 20` |
| `10 <= x <= 20` | `x >= 10 and x <= 20` |
| `5 < x <= 15` | `x > 5 and x <= 15` |

**Best Practice:** সাধারণ Range Checking-এর জন্য Chained Comparison সাধারণত বেশি পরিষ্কার।

## 9. Chained Comparison Does Not Mean What It Looks Like in Other Languages

Python-এ:

```python
1 < 2 < 3
```

এর অর্থ:

```python
1 < 2 and 2 < 3
```

Output:

```text
True
```

কিন্তু নিচের Expression-টি খেয়াল করো:

```python
print(1 < 2 == True)
```

Output:

```text
False
```

কারণ Python এটিকে এভাবে Evaluate করে:

```python
(1 < 2) and (2 == True)
```

দ্বিতীয় Comparison হলো `2 == True`, যার Result `False`।

সুতরাং পুরো Expression-এর Result `False`।

**মনে রাখবে:** Chained Comparison-এ মাঝের Value দুটি পাশের Comparison-এ ব্যবহৃত হয়।

## 10. Short-Circuit Behaviour

Chained Comparison-এ কোনো Comparison `False` হলে পরের Comparison-গুলো Evaluate না-ও হতে পারে। একে Short-Circuit Behaviour বলে।

Example:

```python
a = 10
b = 5
c = 20

print(a < b < c)
```

Output:

```text
False
```

Python প্রথমে `10 < 5` পরীক্ষা করে। এটি `False`, তাই `5 < 20` পরীক্ষা করার প্রয়োজন হয় না।

সাধারণ Range Comparison-এ এটি কার্যকর, তবে Comparison-এর ভেতরে Function Call বা Side Effect থাকলে Evaluation Order বোঝা জরুরি।

## 11. Comparing Strings

String-এর ক্ষেত্রেও Chained Comparison ব্যবহার করা যায়।

```python
print("apple" < "banana" < "cherry")
```

Output:

```text
True
```

Python Lexicographical Order অনুযায়ী String তুলনা করে।

তবে String-এর Range Comparison সবসময় মানুষের ভাষার Dictionary Order-এর সঙ্গে পুরোপুরি মিলে যাবে—এমন নয়। Character-এর Unicode Value ও Case গুরুত্বপূর্ণ।

## 12. Common Mistakes

### Mistake 1: Using `and` Inside a Chained Comparison Incorrectly

ভুল ধারণা:

```python
10 < number and < 20
```

এটি Syntax Error।

সঠিক:

```python
10 < number < 20
```

অথবা:

```python
number > 10 and number < 20
```

### Mistake 2: Forgetting the Boundary

```python
number = 20

print(10 < number < 20)
```

Output:

```text
False
```

কারণ `20 < 20` মিথ্যা।

20-কে অন্তর্ভুক্ত করতে চাইলে:

```python
print(10 < number <= 20)
```

Output:

```text
True
```

### Mistake 3: Confusing Chaining with Separate Comparisons

```python
print(10 < 20 < 15)
```

Output:

```text
False
```

কারণ:

- `10 < 20` → `True`
- `20 < 15` → `False`

### Mistake 4: Assuming Every Type Can Be Compared

```python
print(1 < "2" < 3)
```

এখানে `TypeError` হবে, কারণ Integer এবং String-এর মধ্যে এই ধরনের Ordering Comparison করা যায় না।

## 13. Practice Exercises

### Basic Level

1. `5 < 10 < 15`-এর Result বের করো।
2. `10 <= 10 <= 20`-এর Result বের করো।
3. `10 < 10 < 20`-এর Result বের করো।
4. `5 <= 8 < 10`-এর Result বের করো।
5. `20 >= 15 > 10`-এর Result বের করো।

### Intermediate Level

6. একটি Number 1 থেকে 100-এর মধ্যে আছে কি না পরীক্ষা করো।
7. একটি বয়স 18 থেকে 25-এর মধ্যে কি না পরীক্ষা করো।
8. Marks 0 থেকে 100-এর মধ্যে আছে কি না পরীক্ষা করো।
9. একটি Temperature 20-এর বেশি এবং 35-এর সমান বা কম কি না পরীক্ষা করো।
10. Chained Comparison ব্যবহার করে একটি Number 50 থেকে 100-এর মধ্যে আছে কি না পরীক্ষা করো।

### Output Prediction

```python
x = 15

print(10 < x < 20)
print(10 <= x <= 15)
print(15 < x <= 20)
print(5 < 10 < 8)
print(1 < 2 == True)
```

### Solution

```text
True
True
False
False
False
```

## 14. Practical Challenge

একটি Program তৈরি করো, যেখানে একটি Student-এর Marks যাচাই করা হবে।

Requirements:

1. `marks` নামে একটি Variable তৈরি করো।
2. Marks 0 থেকে 100-এর মধ্যে কি না Chained Comparison দিয়ে পরীক্ষা করো।
3. Marks বৈধ হলে Print করো `"Valid Marks"`।
4. Marks বৈধ না হলে Print করো `"Invalid Marks"`।
5. এরপর Marks 40 বা তার বেশি কি না পরীক্ষা করে Pass/Fail নির্ধারণ করো।

Example:

```python
marks = 85

if 0 <= marks <= 100:
    print("Valid Marks")

    if marks >= 40:
        print("Pass")
    else:
        print("Fail")
else:
    print("Invalid Marks")
```

Output:

```text
Valid Marks
Pass
```

## 15. Chapter Summary

- Chained Comparison-এ একাধিক Comparison Operator একসঙ্গে ব্যবহার করা হয়।
- `10 < x < 20` হলো `10 < x and x < 20`-এর সমতুল্য।
- Range Checking-এর জন্য Chained Comparison খুব কার্যকর।
- `<=` এবং `>=` Boundary অন্তর্ভুক্ত করে।
- `<` এবং `>` Boundary অন্তর্ভুক্ত করে না।
- Chained Comparison-এর Result সাধারণত Boolean Value হয়।
- একটি Comparison `False` হলে পরের Comparison Evaluate না-ও হতে পারে।
- Chained Comparison-এ মাঝের Value দুটি পাশের Comparison-এ ব্যবহৃত হয়।

## 16. Self-Assessment Checklist

- [ ] Chained Comparison কী বুঝি।
- [ ] একাধিক Comparison একসঙ্গে লিখতে পারি।
- [ ] Inclusive ও Exclusive Range-এর পার্থক্য বুঝি।
- [ ] Chained Comparison-কে Logical `and` দিয়ে প্রকাশ করতে পারি।
- [ ] `if` Statement-এ Chained Comparison ব্যবহার করতে পারি।
- [ ] Short-Circuit Behaviour-এর Basic ধারণা বুঝি।
- [ ] Range Checking-এর জন্য সঠিক Operator নির্বাচন করতে পারি।

**Next Topic:** `10_Comparing_Different_Data_Types.md`