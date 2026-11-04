# 14. Splitting and Unpacking Input

## 1. Introduction

Python-এ user-এর কাছ থেকে একই লাইনে একাধিক value নেওয়ার জন্য `split()` এবং unpacking খুবই গুরুত্বপূর্ণ।

ধরা যাক, user input দিল:

```text
10 20 30
```

আমরা চাই:

- প্রথম value `a`-তে রাখতে।
- দ্বিতীয় value `b`-তে রাখতে।
- তৃতীয় value `c`-তে রাখতে।

এ কাজটি এভাবে করা যায়:

```python
a, b, c = input("Enter three numbers: ").split()

print(a)
print(b)
print(c)
```

Sample Interaction:

```text
Enter three numbers: 10 20 30
10
20
30
```

এখানে `split()` input-কে ভাগ করেছে এবং unpacking-এর মাধ্যমে তিনটি value তিনটি variable-এ assign হয়েছে।

তবে মনে রাখবে, এই code-এ `a`, `b` এবং `c` এখনো string। Numeric calculation করতে চাইলে conversion প্রয়োজন হবে।

## 2. What Is `split()`?

`split()` হলো Python-এর একটি string method। এটি একটি string-কে নির্দিষ্ট separator অনুযায়ী ভাগ করে list তৈরি করে।

### Syntax

```python
string.split(separator, maxsplit)
```

এখানে:

- `separator` হলো যে character বা text দিয়ে string ভাগ হবে।
- `maxsplit` হলো সর্বোচ্চ কতবার split করা হবে।
- দুটি argument-ই optional।

Separator না দিলে `split()` এক বা একাধিক whitespace-কে separator হিসেবে ব্যবহার করে।

### Example 1: Splitting a String

```python
text = "Python is easy"

result = text.split()

print(result)
```

Output:

```text
['Python', 'is', 'easy']
```

এখানে string-টি তিনটি অংশে ভাগ হয়েছে।

### Example 2: Splitting Numbers

```python
data = "10 20 30 40"

numbers = data.split()

print(numbers)
```

Output:

```text
['10', '20', '30', '40']
```

খেয়াল করো, list-এর প্রতিটি element string।

### Example 3: Splitting Names

```python
names = "Masum Ritu Mahin"

result = names.split()

print(result)
```

Output:

```text
['Masum', 'Ritu', 'Mahin']
```

## 3. How Default `split()` Works

যখন `split()`-এর মধ্যে কোনো separator দেওয়া হয় না, তখন এটি এক বা একাধিক whitespace অনুযায়ী string ভাগ করে।

Whitespace-এর উদাহরণ:

- Space
- Tab (`\t`)
- Newline (`\n`)

### Example

```python
data = "10   20    30"

print(data.split())
```

Output:

```text
['10', '20', '30']
```

এখানে সংখ্যাগুলোর মাঝে একাধিক space থাকলেও সঠিকভাবে ভাগ হয়েছে।

### Another Example

```python
data = "  Python   is   easy  "

print(data.split())
```

Output:

```text
['Python', 'is', 'easy']
```

Default `split()` শুরু ও শেষের whitespace থেকে খালি string element তৈরি করে না।

**মনে রাখবে:** `split()` এবং `split(" ")` সব ক্ষেত্রে এক নয়।

```python
text = "Python  is easy"

print(text.split())
print(text.split(" "))
```

Output:

```text
['Python', 'is', 'easy']
['Python', '', 'is', 'easy']
```

দ্বিতীয় ক্ষেত্রে নির্দিষ্ট একটি space separator হিসেবে ব্যবহৃত হয়েছে। পরপর দুটি space-এর মাঝে কোনো character না থাকায় empty string `''` তৈরি হয়েছে।

## 4. Using a Custom Separator

কখনো input-এ comma, hyphen বা অন্য কোনো character দিয়ে value আলাদা করা থাকে।

সে ক্ষেত্রে `split()`-এর মধ্যে separator দিতে হয়।

### Example 1: Comma

```python
data = "10,20,30"

result = data.split(",")

print(result)
```

Output:

```text
['10', '20', '30']
```

### Example 2: Hyphen

```python
data = "red-green-blue"

result = data.split("-")

print(result)
```

Output:

```text
['red', 'green', 'blue']
```

### Example 3: Colon

```python
data = "10:20:30"

result = data.split(":")

print(result)
```

Output:

```text
['10', '20', '30']
```

### গুরুত্বপূর্ণ নিয়ম

Separator input-এর format-এর সঙ্গে মিলতে হবে।

```python
data = "10,20,30"

print(data.split(","))
```

এটি comma অনুযায়ী ভাগ করবে।

কিন্তু:

```python
data = "10,20,30"

print(data.split("-"))
```

এখানে hyphen নেই। তাই পুরো string-টি একটি element হিসেবেই থাকবে:

```text
['10,20,30']
```

## 5. What Is Unpacking?

**Unpacking** হলো কোনো iterable-এর element-গুলোকে একাধিক variable-এ আলাদাভাবে assign করার পদ্ধতি।

### Example 1: Basic Unpacking

```python
a, b, c = [10, 20, 30]

print(a)
print(b)
print(c)
```

Output:

```text
10
20
30
```

এখানে:

- `a = 10`
- `b = 20`
- `c = 30`

### Example 2: Unpacking a Tuple

```python
x, y = (5, 15)

print(x)
print(y)
```

Output:

```text
5
15
```

Unpacking-এর জন্য শুধু list বা tuple নয়, অন্য iterable-ও ব্যবহার করা যায়।

### Example 3: Unpacking Input

```python
a, b, c = input("Enter three values: ").split()

print(a, b, c)
```

Sample Interaction:

```text
Enter three values: apple mango orange
apple mango orange
```

এখানে `split()` একটি list তৈরি করেছে এবং সেই list-এর element-গুলো `a`, `b` ও `c`-তে assign হয়েছে।

## 6. Combining `split()` with Unpacking

এক লাইনে একাধিক input নেওয়ার ক্ষেত্রে এই দুটি একসঙ্গে খুব কাজে লাগে।

### Example 1: Taking Two Values

```python
name, city = input("Enter name and city: ").split()

print("Name:", name)
print("City:", city)
```

Sample Interaction:

```text
Enter name and city: Masum Dhaka
Name: Masum
City: Dhaka
```

### Example 2: Taking Three Values

```python
name, student_id, section = input(
    "Enter name, ID and section: "
).split()

print("Name:", name)
print("Student ID:", student_id)
print("Section:", section)
```

Sample Interaction:

```text
Enter name, ID and section: Masum 00125 9A
Name: Masum
Student ID: 00125
Section: 9A
```

এখানে সব value string হিসেবে রাখা হয়েছে। তাই student ID-এর শুরুতে থাকা zero-ও অক্ষুণ্ণ রয়েছে।

### Example 3: Taking Two Integers

```python
a, b = map(int, input("Enter two integers: ").split())

print("Sum:", a + b)
```

Sample Interaction:

```text
Enter two integers: 10 20
Sum: 30
```

এখানে তিনটি কাজ হয়েছে:

1. `input()` string নিয়েছে।
2. `split()` string-টিকে ভাগ করেছে।
3. `map(int, ...)` প্রতিটি অংশকে integer-এ convert করেছে।

## 7. Understanding `map()` with Unpacking

`map()` একটি function-কে iterable-এর প্রতিটি element-এর ওপর প্রয়োগ করে।

### Example

```python
numbers = map(int, ["10", "20", "30"])

a, b, c = numbers

print(a)
print(b)
print(c)
```

Output:

```text
10
20
30
```

এখানে `map(int, ...)` প্রতিটি string-কে integer-এ convert করেছে। এরপর unpacking-এর মাধ্যমে value-গুলো variable-এ assign হয়েছে।

### Taking Float Values

```python
a, b, c = map(float, input("Enter three values: ").split())

print("Total:", a + b + c)
```

Sample Interaction:

```text
Enter three values: 10.5 20.25 30
Total: 60.75
```

এখানে তিনটি value float হিসেবে নেওয়া হয়েছে।

**মনে রাখবে:** `map()` নিজে list return করে না; Python 3-এ এটি একটি map iterator return করে। Unpacking করার সময় এটি থেকে value নেওয়া যায়।

## 8. Unpacking-এর ক্ষেত্রে Value-এর সংখ্যা মেলানো

সাধারণ unpacking-এ variable-এর সংখ্যা এবং element-এর সংখ্যা সমান হতে হয়।

### Example 1: Correct Unpacking

```python
a, b = [10, 20]

print(a, b)
```

Output:

```text
10 20
```

এখানে দুটি variable এবং দুটি value রয়েছে।

### Example 2: Too Many Values

```python
a, b = [10, 20, 30]
```

এতে `ValueError` হবে, কারণ দুটি variable-এর জন্য তিনটি value রয়েছে।

### Example 3: Not Enough Values

```python
a, b, c = [10, 20]
```

এতেও `ValueError` হবে, কারণ তিনটি variable-এর জন্য মাত্র দুটি value রয়েছে।

### Input-এর ক্ষেত্রেও একই নিয়ম

```python
a, b = input().split()
```

Input:

```text
10 20 30
```

এখানে তিনটি value পাওয়া যায়, কিন্তু variable দুটি। তাই `ValueError` হবে।

**Solution:** প্রয়োজনীয় variable-এর সংখ্যা ঠিক করো, অথবা input-এর format যাচাই করো।

## 9. Using `maxsplit`

`split()`-এর `maxsplit` parameter দিয়ে সর্বোচ্চ কতবার split হবে, তা নির্ধারণ করা যায়।

### Syntax

```python
string.split(separator, maxsplit)
```

### Example 1

```python
text = "Python is easy to learn"

print(text.split(" ", 2))
```

Output:

```text
['Python', 'is', 'easy to learn']
```

এখানে সর্বোচ্চ দুইবার split হয়েছে। তাই বাকি অংশ একসঙ্গে রয়েছে।

### Example 2: Splitting a Name and Remaining Text

```python
text = "Masum Abdulla Al Masum"

first, remaining = text.split(" ", 1)

print("First part:", first)
print("Remaining:", remaining)
```

Output:

```text
First part: Masum
Remaining: Abdulla Al Masum
```

এখানে `maxsplit=1` দেওয়ার কারণে প্রথম space-এ একবার split হয়েছে।

### গুরুত্বপূর্ণ সীমাবদ্ধতা

`maxsplit` ব্যবহার করলেও input-এর format সঠিক হতে হবে। যেমন `a, b = input().split()` ব্যবহার করলে ঠিক দুটি অংশ পাওয়ার নিশ্চয়তা থাকতে হবে; অন্যথায় unpacking error হতে পারে।

## 10. Using `rsplit()`

`rsplit()` হলো `split()`-এর মতো একটি string method, তবে `maxsplit` ব্যবহার করলে এটি ডান দিক থেকে split শুরু করে।

### Example

```python
text = "one-two-three-four"

print(text.rsplit("-", 1))
```

Output:

```text
['one-two-three', 'four']
```

এখানে ডান দিক থেকে একবার split হয়েছে।

### Difference

```python
text = "one-two-three-four"

print(text.split("-", 1))
print(text.rsplit("-", 1))
```

Output:

```text
['one', 'two-three-four']
['one-two-three', 'four']
```

- `split("-", 1)` বাম দিক থেকে একবার split করে।
- `rsplit("-", 1)` ডান দিক থেকে একবার split করে।

এগুলো তখন কাজে লাগে, যখন string-এর শুরু বা শেষের অংশ আলাদা করতে হয়।

## 11. Handling Spaces Around Comma-Separated Values

ধরা যাক, user input দিল:

```text
10, 20, 30
```

এখন:

```python
data = input("Enter values: ").split(",")

print(data)
```

Output:

```text
['10', ' 20', ' 30']
```

দ্বিতীয় ও তৃতীয় element-এর শুরুতে space রয়েছে।

Numeric conversion-এর ক্ষেত্রে `int()` ও `float()`-এর মতো function সাধারণত এই surrounding whitespace গ্রহণ করে:

```python
numbers = list(map(int, input("Enter values: ").split(",")))

print(numbers)
```

Input:

```text
10, 20, 30
```

Output:

```text
[10, 20, 30]
```

Text value-এর ক্ষেত্রে whitespace পরিষ্কার করতে `.strip()` ব্যবহার করা যায়।

```python
names = input("Enter names: ").split(",")

names = [name.strip() for name in names]

print(names)
```

Input:

```text
Masum, Ritu, Mahin
```

Output:

```text
['Masum', 'Ritu', 'Mahin']
```

এখানে `.strip()` প্রতিটি নামের শুরু ও শেষের whitespace সরিয়ে দিয়েছে।

## 12. Common Errors and Solutions

### Error 1: Wrong Number of Values

```python
a, b, c = input().split()
```

Input:

```text
10 20
```

এখানে মাত্র দুটি value পাওয়া যায়। তাই `ValueError` হবে।

**Solution:** সঠিক সংখ্যক value দাও অথবা list ব্যবহার করে input গ্রহণ করো।

### Error 2: Invalid Integer

```python
a, b = map(int, input().split())
```

Input:

```text
10 hello
```

এখানে `ValueError` হবে, কারণ `"hello"` integer-এ convert করা যায় না।

### Error 3: Incorrect Separator

```python
a, b = input().split(",")
```

Input:

```text
10 20
```

এখানে comma নেই। তাই একটি অংশ পাওয়া যাবে, দুটি নয়। ফলে unpacking-এ `ValueError` হবে।

**Solution:**

```python
a, b = input().split()
```

অথবা input-এ comma ব্যবহার করো।

### Error 4: Confusing String and Integer

```python
a, b = input().split()

print(a + b)
```

Input:

```text
10 20
```

Output:

```text
1020
```

কারণ `a` এবং `b` string।

Numeric addition করতে:

```python
a, b = map(int, input().split())

print(a + b)
```

Output:

```text
30
```

### Error 5: Empty Input

```python
a, b = input().split()
```

User কিছু না লিখে Enter চাপলে কোনো অংশ পাওয়া যাবে না। ফলে unpacking-এ `ValueError` হবে।

এ ধরনের error সামলানোর জন্য input validation এবং exception handling প্রয়োজন হতে পারে।

## 13. Practical Programs

### Program 1: Add Three Integers

```python
a, b, c = map(int, input("Enter three integers: ").split())

total = a + b + c

print("Total:", total)
```

Sample Interaction:

```text
Enter three integers: 10 20 30
Total: 60
```

### Program 2: Student Information

```python
name, student_id, section = input(
    "Enter name, ID and section: "
).split()

print("Name:", name)
print("Student ID:", student_id)
print("Section:", section)
```

Sample Interaction:

```text
Enter name, ID and section: Masum 00125 9A
Name: Masum
Student ID: 00125
Section: 9A
```

### Program 3: Find Sum and Average

```python
a, b, c, d = map(float, input("Enter four numbers: ").split())

total = a + b + c + d
average = total / 4

print("Sum:", total)
print("Average:", average)
```

### Program 4: Split a Date

```python
day, month, year = input("Enter date (DD-MM-YYYY): ").split("-")

print("Day:", day)
print("Month:", month)
print("Year:", year)
```

Sample Interaction:

```text
Enter date (DD-MM-YYYY): 16-10-2026
Day: 16
Month: 10
Year: 2026
```

এখানে date-এর অংশগুলো string হিসেবে রাখা হয়েছে। প্রয়োজন হলে পরে integer-এ convert করা যায়।

### Program 5: Calculate Total from Comma-Separated Numbers

```python
numbers = list(map(float, input("Enter numbers separated by commas: ").split(",")))

print("Numbers:", numbers)
print("Total:", sum(numbers))
```

Sample Interaction:

```text
Enter numbers separated by commas: 10.5,20,30.25
Numbers: [10.5, 20.0, 30.25]
Total: 60.75
```

## 14. Practice Exercises

### Exercise 1: Basic Splitting

নিচের string-টিকে `split()` ব্যবহার করে list-এ রূপান্তর করো:

```text
Python is easy to learn
```

### Exercise 2: Two Variables

একই লাইনে দুটি নাম input নিয়ে দুটি আলাদা variable-এ রাখো।

### Exercise 3: Three Integers

একই লাইনে তিনটি integer input নিয়ে তাদের যোগফল বের করো।

### Exercise 4: Comma-Separated Values

`10,20,30,40` input নিয়ে integer-এর list তৈরি করো।

### Exercise 5: Predict the Output

```python
text = "A  B C"

print(text.split())
print(text.split(" "))
```

দুটি output কী হবে?

### Exercise 6: Find the Error

```python
a, b = input().split()
```

User `10 20 30` দিলে কী error হবে? কেন?

### Exercise 7: Use `maxsplit`

```text
Python is very easy to learn
```

এটিকে সর্বোচ্চ দুইবার split করে ফলাফল দেখাও।

### Exercise 8: Use `rsplit`

```text
red-green-blue-yellow
```

ডান দিক থেকে একবার split করো।

### Exercise 9: Student Report

একই লাইনে student-এর নাম, ID এবং section input নিয়ে আলাদাভাবে print করো। ID-এর শুরুতে zero থাকলে যেন সেটি অক্ষুণ্ণ থাকে।

### Exercise 10: Challenge

একই লাইনে পাঁচটি float input নাও। তাদের list তৈরি করো এবং total, average, maximum ও minimum বের করো।

## 15. Practice Answer Key

### Answer 1

```python
text = "Python is easy to learn"

print(text.split())
```

Output:

```text
['Python', 'is', 'easy', 'to', 'learn']
```

### Answer 2

```python
first_name, second_name = input("Enter two names: ").split()

print(first_name)
print(second_name)
```

### Answer 3

```python
a, b, c = map(int, input("Enter three integers: ").split())

print("Sum:", a + b + c)
```

### Answer 4

```python
numbers = list(map(int, input("Enter comma-separated values: ").split(",")))

print(numbers)
```

Input `10,20,30,40` হলে output হবে:

```text
[10, 20, 30, 40]
```

### Answer 5

Output:

```text
['A', 'B', 'C']
['A', '', 'B', 'C']
```

Default `split()` একাধিক whitespace একসঙ্গে handle করে, কিন্তু `split(" ")` প্রতিটি space character অনুযায়ী ভাগ করে।

### Answer 6

`ValueError` হবে, কারণ দুটি variable-এর জন্য তিনটি value দেওয়া হয়েছে।

### Answer 7

```python
text = "Python is very easy to learn"

print(text.split(" ", 2))
```

Output:

```text
['Python', 'is', 'very easy to learn']
```

### Answer 8

```python
text = "red-green-blue-yellow"

print(text.rsplit("-", 1))
```

Output:

```text
['red-green-blue', 'yellow']
```

### Answer 9

```python
name, student_id, section = input("Enter name, ID and section: ").split()

print("Name:", name)
print("Student ID:", student_id)
print("Section:", section)
```

### Answer 10

```python
numbers = list(map(float, input("Enter five numbers: ").split()))

if len(numbers) == 5:
    print("Total:", sum(numbers))
    print("Average:", sum(numbers) / 5)
    print("Maximum:", max(numbers))
    print("Minimum:", min(numbers))
else:
    print("Please enter exactly five numbers.")
```

## 16. Best Practices

1. Default `split()` ব্যবহার করো যখন input whitespace দিয়ে আলাদা করা থাকে।
2. Comma বা অন্য separator থাকলে `split(",")` বা উপযুক্ত separator ব্যবহার করো।
3. `split()`-এর result সাধারণত string-এর list—এটি মনে রাখবে।
4. Numeric calculation-এর জন্য প্রয়োজন অনুযায়ী `map(int, ...)` বা `map(float, ...)` ব্যবহার করো।
5. Unpacking করার সময় variable ও value-এর সংখ্যা মিলিয়ে দাও।
6. Text-এর আশপাশের whitespace সরাতে `.strip()` ব্যবহার করতে পারো।
7. Input-এর format আগে নির্ধারণ করো, যাতে separator নিয়ে ভুল না হয়।
8. User input ভুল হতে পারে—তাই বড় program-এ input validation ব্যবহার করো।

## 17. Chapter Summary

- `split()` string-কে separator অনুযায়ী ভাগ করে list তৈরি করে।
- Default `split()` whitespace অনুযায়ী ভাগ করে।
- `split(",")` comma অনুযায়ী ভাগ করে।
- Unpacking দিয়ে iterable-এর value একাধিক variable-এ assign করা যায়।
- `map()` ব্যবহার করে একাধিক value convert করা যায়।
- `maxsplit` সর্বোচ্চ split-এর সংখ্যা নির্ধারণ করে।
- `rsplit()` ডান দিক থেকে split করতে পারে।
- ভুল value count, separator বা data type-এর কারণে error হতে পারে।

## 18. Self-Assessment Checklist

- [ ] `split()` কীভাবে কাজ করে, তা বুঝি।
- [ ] Default ও custom separator ব্যবহার করতে পারি।
- [ ] Unpacking দিয়ে একাধিক variable-এ value assign করতে পারি।
- [ ] `map()` দিয়ে numeric input convert করতে পারি।
- [ ] `maxsplit` ও `rsplit()`-এর ব্যবহার বুঝি।
- [ ] Input-এর ভুল সংখ্যা বা format শনাক্ত করতে পারি।
- [ ] Comma-separated input থেকে numeric list তৈরি করতে পারি।

**Next Topic:** `15_Input_Validation_Basics.md` — এখানে user-এর input সঠিক কি না যাচাই করা, ভুল input শনাক্ত করা এবং program-কে আরও নির্ভরযোগ্য করার মৌলিক পদ্ধতি শিখব।