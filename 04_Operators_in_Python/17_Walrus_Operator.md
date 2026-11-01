# 17. Walrus Operator in Python (`:=`)

## 1. Introduction to the Walrus Operator

Python-এ **Walrus Operator (`:=`)** হলো এমন একটি Operator, যার মাধ্যমে কোনো Expression-এর মধ্যে Variable-এ Value Assign করা যায় এবং একই সঙ্গে সেই Value ব্যবহারও করা যায়।

এটিকে **Assignment Expression Operator**-ও বলা হয়।

Python 3.8 থেকে Walrus Operator ব্যবহার করা যায়।

### Example

```python
number = 10

print(number)
```

Output:

```text
10
```

এবার Walrus Operator ব্যবহার করি:

```python
print(number := 10)
```

Output:

```text
10
```

এখানে `number := 10` Expression-টি `number`-এ `10` Assign করেছে এবং Expression-এর Result হিসেবে `10` দিয়েছে। তাই `print()` সেই Value Print করেছে।

**মনে রাখবে:**

- `=` হলো সাধারণ Assignment Operator।
- `:=` হলো Assignment Expression Operator।
- `:=` ব্যবহার করে Assign করার পাশাপাশি Expression-এর Result-ও পাওয়া যায়।

---

## 2. Syntax of the Walrus Operator

Walrus Operator-এর সাধারণ Syntax:

```python
variable := expression
```

Example:

```python
x := 5
```

এই Code-টি Python-এর সাধারণ Statement হিসেবে সরাসরি ব্যবহার করা যাবে না। Walrus Operator সাধারণত এমন কোনো Context-এ ব্যবহার করতে হয় যেখানে Expression গ্রহণযোগ্য।

সঠিক Example:

```python
print(x := 5)
print(x)
```

Output:

```text
5
5
```

ব্যাখ্যা:

1. `x := 5`-এর মাধ্যমে `x`-এ `5` Assign হয়েছে।
2. Expression-এর Result `5`।
3. `print()` Result-টি Print করেছে।
4. পরের লাইনে `x` ব্যবহার করায় আবার `5` Print হয়েছে।

---

## 3. Difference Between `=` and `:=`

এই দুটি Operator-এর পার্থক্য বোঝা খুব গুরুত্বপূর্ণ।

| বিষয় | `=` | `:=` |
|---|---|---|
| নাম | Assignment Operator | Walrus Operator |
| কাজ | Variable-এ Value Assign করে | Expression-এর মধ্যে Value Assign করে |
| সাধারণ ব্যবহার | `x = 10` | `print(x := 10)` |
| Expression-এর Result | Assignment নিজে Expression নয় | Assign করা Value Expression-এর Result হয় |
| ব্যবহার | সাধারণ Assignment Statement | নির্দিষ্ট Expression Context |

### Example 1: Normal Assignment

```python
x = 10

print(x)
```

Output:

```text
10
```

### Example 2: Walrus Operator

```python
print(x := 10)
```

Output:

```text
10
```

দুটি Code-ই `10` Print করে, তবে তাদের Assignment-এর পদ্ধতি আলাদা।

**Important:** সাধারণ Assignment-এ `=` ব্যবহার করবে। Walrus Operator ব্যবহার করবে যখন Expression-এর মধ্যে Assign করা সুবিধাজনক হয়।

---

## 4. Why Do We Need the Walrus Operator?

কিছু ক্ষেত্রে একই Expression-এর Result একটি Variable-এ সংরক্ষণ করে সঙ্গে সঙ্গে ব্যবহার করার প্রয়োজন হয়।

Walrus Operator ছাড়া:

```python
numbers = [10, 20, 30]

count = len(numbers)

if count > 2:
    print(count)
```

Output:

```text
3
```

Walrus Operator ব্যবহার করে:

```python
numbers = [10, 20, 30]

if (count := len(numbers)) > 2:
    print(count)
```

Output:

```text
3
```

দ্বিতীয় Example-এ:

- `len(numbers)` List-এর Length বের করেছে।
- `count := len(numbers)` Result-টি `count`-এ Assign করেছে।
- `count > 2` Condition পরীক্ষা করেছে।
- Condition True হওয়ায় `count` Print হয়েছে।

এখানে একই Result আলাদাভাবে Calculate ও Assign করার প্রয়োজন কমেছে।

তবে Code ছোট করার জন্য অপ্রয়োজনীয়ভাবে Walrus Operator ব্যবহার করা উচিত নয়।

---

## 5. Walrus Operator with `if` Statements

`if` Statement-এর Condition-এর মধ্যে কোনো Value Assign করে সেটি পরীক্ষা করা যায়।

### Example 1: Checking a Number

```python
if (number := 15) > 10:
    print(number)
```

Output:

```text
15
```

ব্যাখ্যা:

- `number := 15`-এর মাধ্যমে `number`-এ `15` Assign হয়েছে।
- এরপর `15 > 10` পরীক্ষা করা হয়েছে।
- Condition True হওয়ায় `15` Print হয়েছে।

### Example 2: Checking String Length

```python
name = "Python"

if (length := len(name)) > 5:
    print("Length:", length)
```

Output:

```text
Length: 6
```

এখানে String-এর Length `length` Variable-এ Assign হয়েছে এবং একই Value Condition-এ ব্যবহার হয়েছে।

### Example 3: Checking a List

```python
items = [1, 2, 3, 4]

if (size := len(items)) > 0:
    print("Items found:", size)
```

Output:

```text
Items found: 4
```

List-এর Length শূন্যের বেশি কি না পরীক্ষা করা হয়েছে।

---

## 6. Walrus Operator with `while` Loops

`while` Loop-এ Walrus Operator বিশেষভাবে উপকারী হতে পারে, যখন কোনো Function-এর Result বারবার নেওয়া এবং পরীক্ষা করা প্রয়োজন হয়।

### Example 1: Basic Counter

```python
count = 0

while (count := count + 1) <= 3:
    print(count)
```

Output:

```text
1
2
3
```

ব্যাখ্যা:

1. `count` প্রথমে `0`।
2. Condition-এর মধ্যে `count`-এর Value এক বাড়ানো হয়।
3. নতুন Value `3` পর্যন্ত হলে Loop চলে।
4. Value `4` হলে Condition False হয় এবং Loop বন্ধ হয়।

এই Example-টি শেখার জন্য উপকারী। তবে সাধারণ Counter-এর ক্ষেত্রে `for` Loop বা প্রচলিত `while` Loop অনেক সময় আরও পরিষ্কার হয়।

### Example 2: Reading Until an Empty Line

```python
while (text := input("Enter text: ")) != "":
    print("You entered:", text)

print("Program ended.")
```

সম্ভাব্য Input ও Output:

```text
Enter text: Hello
You entered: Hello
Enter text: Python
You entered: Python
Enter text:
Program ended.
```

ব্যাখ্যা:

- `input()` User-এর কাছ থেকে Text নেয়।
- `text := input(...)` Input-টি `text`-এ Assign করে।
- Input খালি না হলে Loop চলে।
- User Enter চাপলে খালি String পাওয়া যায় এবং Loop বন্ধ হয়।

এই Pattern-টি User Input-ভিত্তিক Program-এ কাজে লাগতে পারে।

---

## 7. Walrus Operator with List Comprehensions

List Comprehension ব্যবহার করে নতুন List তৈরি করা যায়। Walrus Operator কিছু ক্ষেত্রে Calculation-এর Result সংরক্ষণ করে সেটি আবার ব্যবহার করতে সাহায্য করে।

### Example 1: Calculating Squares

```python
numbers = [1, 2, 3, 4, 5]

squares = [
    square
    for number in numbers
    if (square := number ** 2) > 10
]

print(squares)
```

Output:

```text
[16, 25]
```

ব্যাখ্যা:

- প্রতিটি `number`-এর Square বের করা হয়।
- `square := number ** 2` Result-টি `square`-এ Assign করে।
- `square > 10` হলে সেটি নতুন List-এ যোগ হয়।
- তাই `16` এবং `25` পাওয়া যায়।

এখানে `square` হলো Walrus Operator দিয়ে Assign করা Variable।

### Example 2: String Length Filtering

```python
words = ["cat", "python", "book", "programming"]

result = [
    word
    for word in words
    if (length := len(word)) > 4
]

print(result)
```

Output:

```text
['python', 'programming']
```

এখানে পাঁচ অক্ষরের বেশি এমন শব্দগুলো নতুন List-এ রাখা হয়েছে।

**সতর্কতা:** List Comprehension-এর মধ্যে Walrus Operator ব্যবহার করলে Code জটিল হয়ে যাচ্ছে কি না খেয়াল করবে। প্রয়োজনে সাধারণ `for` Loop ব্যবহার করো।

---

## 8. Walrus Operator with Functions

Function-এর Result Variable-এ Assign করে সঙ্গে সঙ্গে Condition-এ ব্যবহার করা যায়।

### Example

```python
def get_number():
    return 25

if (result := get_number()) > 20:
    print("Result:", result)
```

Output:

```text
Result: 25
```

ব্যাখ্যা:

- `get_number()` Function `25` Return করে।
- `result := get_number()` সেই Value `result`-এ Assign করে।
- এরপর `result > 20` পরীক্ষা করা হয়।
- Condition True হওয়ায় Result Print হয়।

এই পদ্ধতি তখন কাজে লাগে যখন Function Call-এর Result Condition-এও প্রয়োজন হয় এবং পরে আবার ব্যবহার করতে হয়।

---

## 9. Understanding Assignment and Evaluation

Walrus Operator ব্যবহার করার সময় Expression-এর Result কীভাবে ব্যবহার হচ্ছে, তা বুঝতে হবে।

### Example

```python
if (x := 8) > 5:
    print(x * 2)
```

Output:

```text
16
```

ধাপে ধাপে:

1. `x := 8` থেকে `x`-এর Value হয় `8`।
2. Assignment Expression-এর Result `8`।
3. `8 > 5` True।
4. `x * 2` হয় `16`।
5. `16` Print হয়।

### Another Example

```python
result = (number := 5) + 3

print(number)
print(result)
```

Output:

```text
5
8
```

এখানে:

- `number := 5`-এর Result `5`।
- এরপর `5 + 3` হিসাব করে `result`-এ `8` Assign হয়েছে।

**মনে রাখবে:** Walrus Operator-এর মাধ্যমে Assign করা Value একই Expression-এর অন্য অংশেও ব্যবহার করা যেতে পারে।

---

## 10. Parentheses and the Walrus Operator

Walrus Operator-এর ক্ষেত্রে Parentheses ব্যবহার করা প্রায়ই প্রয়োজনীয় এবং Code পরিষ্কার রাখতেও সাহায্য করে।

### Example 1: Inside a Condition

```python
if (number := 10) > 5:
    print(number)
```

Output:

```text
10
```

### Example 2: Without Appropriate Grouping

```python
# if number := 10 > 5:
#     print(number)
```

এখানে `number`-এ `10 > 5`-এর Boolean Result Assign হবে, অর্থাৎ `True`। এটি আগের Example-এর মতো নয়।

সঠিকভাবে `10` Assign করে সেটি পরীক্ষা করতে লিখবে:

```python
if (number := 10) > 5:
    print(number)
```

Output:

```text
10
```

**Rule:** Assignment Expression-এর কোন অংশটি আগে মূল্যায়ন করতে চাও, তা পরিষ্কার রাখতে Parentheses ব্যবহার করো।

---

## 11. Important Rules and Restrictions

Walrus Operator-এর কয়েকটি গুরুত্বপূর্ণ নিয়ম রয়েছে।

### Rule 1: Use Python 3.8 or Later

Walrus Operator Python 3.8-এ যুক্ত হয়েছে।

পুরোনো Python Version ব্যবহার করলে এটি Syntax Error দিতে পারে।

### Rule 2: Use It in a Valid Expression Context

Walrus Operator সাধারণ Assignment Statement-এর সরাসরি বিকল্প নয়।

```python
# x := 10
```

এভাবে একা Statement হিসেবে লিখলে Syntax Error হবে।

সঠিক:

```python
print(x := 10)
```

### Rule 3: Assignment Target Must Be a Valid Name

সাধারণ Variable Assignment করা যায়:

```python
print(number := 5)
```

কিন্তু Walrus Operator দিয়ে সরাসরি List Element বা Object Attribute Assign করা যায় না।

```python
# (items[0] := 10)  # Invalid syntax
```

এ ধরনের ক্ষেত্রে সাধারণ Assignment ব্যবহার করবে:

```python
items = [1, 2, 3]
items[0] = 10

print(items)
```

Output:

```text
[10, 2, 3]
```

### Rule 4: Avoid Unnecessary Use

Walrus Operator ব্যবহার করা সম্ভব হলেই ব্যবহার করতে হবে, এমন নয়।

সহজ Code অনেক সময় বেশি ভালো:

```python
count = len(items)

if count > 0:
    print(count)
```

এটি প্রয়োজন না হলে শুধু ছোট করার জন্য Walrus Operator-এ রূপান্তর করার দরকার নেই।

---

## 12. Common Mistakes

### Mistake 1: Confusing `=` and `:=`

```python
x = 10
```

এটি সাধারণ Assignment।

```python
print(x := 10)
```

এটি Assignment Expression।

দুটির Syntax ও ব্যবহার এক নয়।

### Mistake 2: Forgetting Parentheses

```python
if (number := 10) > 5:
    print(number)
```

Parentheses দিয়ে বোঝানো হয়েছে, আগে `10` Assign হবে এবং তারপর Condition পরীক্ষা হবে।

### Mistake 3: Assigning a Boolean Instead of a Number

```python
if number := 10 > 5:
    print(number)
```

এখানে `10 > 5` আগে মূল্যায়িত হয় এবং `number`-এ `True` Assign হয়।

যদি `number`-এ `10` Assign করতে চাও, তাহলে লিখবে:

```python
if (number := 10) > 5:
    print(number)
```

### Mistake 4: Using It Without a Good Reason

অতিরিক্ত Walrus Operator Code পড়া কঠিন করে তুলতে পারে।

সহজ, পরিষ্কার এবং Maintainable Code-কে অগ্রাধিকার দেবে।

---

## 13. Practice Exercises

### Basic Level

1. Walrus Operator ব্যবহার করে `x`-এ `20` Assign করে Print করো।
2. `(number := 15) > 10` Condition ব্যবহার করে Number Print করো।
3. String `"Python"`-এর Length Walrus Operator দিয়ে Assign করে Print করো।

### Intermediate Level

4. List `[10, 20, 30]`-এর Length Walrus Operator দিয়ে বের করে পরীক্ষা করো সেটি `2`-এর বেশি কি না।
5. একটি Function থেকে Number Return করিয়ে Walrus Operator দিয়ে Assign ও পরীক্ষা করো।
6. `[1, 2, 3, 4, 5]` থেকে Square-এর Value `10`-এর বেশি এমন Number-এর Square নিয়ে List তৈরি করো।
7. `while` Loop ব্যবহার করে User-এর খালি Input না পাওয়া পর্যন্ত Input গ্রহণ করো।

### Output Prediction

```python
print(number := 12)

if (value := 7) > 5:
    print(value * 2)

result = (x := 4) + 6

print(x)
print(result)
```

### Answers

```text
12
14
4
10
```

ব্যাখ্যা:

- প্রথমে `number`-এ `12` Assign হয়েছে এবং Print হয়েছে।
- `value`-এ `7` Assign হয়েছে। `7 > 5` True হওয়ায় `14` Print হয়েছে।
- `x`-এ `4` Assign হয়েছে।
- `4 + 6 = 10`, তাই `result`-এর Value `10`।

---

## 14. Chapter Summary

- Walrus Operator-এর Symbol হলো `:=`।
- এটি Python 3.8 থেকে পাওয়া যায়।
- এটি Assignment Expression তৈরি করে।
- একই Expression-এর মধ্যে Value Assign ও ব্যবহার করা যায়।
- `if` এবং `while` Condition-এ এটি উপকারী হতে পারে।
- List Comprehension এবং Function Call-এর Result সংরক্ষণেও এটি কাজে লাগে।
- Parentheses ব্যবহার করলে Expression পরিষ্কার থাকে।
- এটি সাধারণ `=` Assignment-এর সম্পূর্ণ বিকল্প নয়।
- অপ্রয়োজনীয় ব্যবহার এড়িয়ে পরিষ্কার Code লেখা উচিত।

## 15. Self-Assessment Checklist

- [ ] Walrus Operator কী বুঝি।
- [ ] `=` ও `:=`-এর পার্থক্য বুঝি।
- [ ] `if` Condition-এর মধ্যে এটি ব্যবহার করতে পারি।
- [ ] `while` Loop-এ এটি ব্যবহার করতে পারি।
- [ ] List Comprehension-এর মধ্যে এর ব্যবহার বুঝি।
- [ ] Parentheses কেন প্রয়োজন হতে পারে বুঝি।
- [ ] Walrus Operator-এর সাধারণ ভুলগুলো শনাক্ত করতে পারি।

**Next Topic:** `18_Identity_Operators.md`