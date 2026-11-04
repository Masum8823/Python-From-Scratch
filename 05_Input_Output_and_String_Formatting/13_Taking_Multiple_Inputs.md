# 13. Taking Multiple Inputs

## 1. Introduction

Python-এ user-এর কাছ থেকে একাধিক value নেওয়ার বিভিন্ন পদ্ধতি রয়েছে। আমরা চাইলে প্রতিটি value আলাদা লাইনে নিতে পারি, আবার এক লাইনেও একাধিক value নিতে পারি।

যেমন, user-এর কাছ থেকে দুটি সংখ্যা নিয়ে যোগফল বের করতে চাইলে:

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print("Sum:", a + b)
```

Sample Interaction:

```text
Enter first number: 10
Enter second number: 20
Sum: 30
```

এখানে দুটি আলাদা `input()` ব্যবহার করা হয়েছে।

এই topic-এ আমরা শিখব:

- একাধিক input আলাদা লাইনে নেওয়া।
- একই লাইনে একাধিক input নেওয়া।
- `split()` দিয়ে input ভাগ করা।
- `map()` দিয়ে একাধিক value convert করা।
- একাধিক input দিয়ে practical program তৈরি করা।

## 2. Taking Multiple Inputs on Separate Lines

সবচেয়ে সহজ পদ্ধতি হলো প্রতিটি input-এর জন্য আলাদা `input()` ব্যবহার করা।

### Example 1: Taking Two Numbers

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print("First number:", a)
print("Second number:", b)
```

Sample Interaction:

```text
Enter first number: 15
Enter second number: 25
First number: 15
Second number: 25
```

### Example 2: Taking Three Numbers

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))
c = int(input("Enter third number: "))

total = a + b + c

print("Total:", total)
```

Sample Interaction:

```text
Enter first number: 10
Enter second number: 20
Enter third number: 30
Total: 60
```

### Example 3: Taking Student Information

```python
name = input("Enter your name: ")
student_id = input("Enter your student ID: ")
age = int(input("Enter your age: "))

print("Name:", name)
print("Student ID:", student_id)
print("Age:", age)
```

এখানে name ও student ID string হিসেবে নেওয়া হয়েছে, আর age integer হিসেবে নেওয়া হয়েছে।

**কখন এই পদ্ধতি ব্যবহার করবে?**

যখন প্রতিটি input আলাদা করে prompt দেখিয়ে নিতে হবে, তখন এই পদ্ধতি সহজ ও পরিষ্কার।

## 3. Taking Multiple Inputs in a Single Line

কখনো user-এর কাছ থেকে একই লাইনে একাধিক value নিতে হয়।

উদাহরণ:

```text
10 20 30
```

এখানে তিনটি সংখ্যা একটি লাইনে দেওয়া হয়েছে। এগুলো আলাদা করতে `split()` ব্যবহার করা যায়।

### Example

```python
numbers = input("Enter three numbers: ").split()

print(numbers)
```

Sample Interaction:

```text
Enter three numbers: 10 20 30
['10', '20', '30']
```

এখানে `split()` input-টিকে whitespace অনুযায়ী ভাগ করেছে।

খেয়াল করো, result একটি list এবং প্রতিটি value string।

অর্থাৎ, `split()` শুধু input ভাগ করে; এটি নিজে থেকে সংখ্যায় convert করে না।

## 4. Understanding the `split()` Method

`split()` হলো string method, যা একটি string-কে বিভিন্ন অংশে ভাগ করে list তৈরি করে।

### Syntax

```python
string.split()
```

Default অবস্থায় `split()` এক বা একাধিক whitespace-কে separator হিসেবে ব্যবহার করে।

### Example 1: Splitting Numbers

```python
data = "10 20 30"

result = data.split()

print(result)
```

Output:

```text
['10', '20', '30']
```

### Example 2: Splitting Names

```python
names = input("Enter three names: ").split()

print(names)
```

Sample Interaction:

```text
Enter three names: Masum Ritu Mahin
['Masum', 'Ritu', 'Mahin']
```

### Example 3: Splitting Comma-Separated Values

```python
data = input("Enter values separated by commas: ")

result = data.split(",")

print(result)
```

Sample Interaction:

```text
Enter values separated by commas: 10,20,30
['10', '20', '30']
```

এখানে `split(",")` ব্যবহার করা হয়েছে, তাই comma অনুযায়ী string ভাগ হয়েছে।

**মনে রাখবে:** `split()`-এর result-এ প্রতিটি অংশ string থাকে, যতক্ষণ না আলাদাভাবে conversion করা হয়।

## 5. Taking Multiple Integer Inputs with `map()`

যদি একই লাইনে একাধিক integer নিতে চাই, তাহলে `map()` এবং `int()` একসঙ্গে ব্যবহার করা যায়।

### Syntax

```python
a, b = map(int, input().split())
```

এখানে কাজের ধাপগুলো হলো:

1. `input()` একটি string নেয়।
2. `split()` string-টিকে আলাদা অংশে ভাগ করে।
3. `map(int, ...)` প্রতিটি অংশকে integer-এ convert করে।
4. `a` ও `b` variable-এ value assign হয়।

### Example

```python
a, b = map(int, input("Enter two numbers: ").split())

print("Sum:", a + b)
```

Sample Interaction:

```text
Enter two numbers: 10 20
Sum: 30
```

এখানে একই লাইনে দুটি integer নেওয়া হয়েছে।

### Another Example: Three Integers

```python
a, b, c = map(int, input("Enter three numbers: ").split())

print("Total:", a + b + c)
```

Sample Interaction:

```text
Enter three numbers: 10 20 30
Total: 60
```

এখানে তিনটি integer একই লাইনে নেওয়া হয়েছে।

## 6. Taking Multiple Float Inputs with `map()`

একই পদ্ধতিতে একাধিক float input নেওয়া যায়।

### Example

```python
a, b = map(float, input("Enter two decimal numbers: ").split())

print("Sum:", a + b)
```

Sample Interaction:

```text
Enter two decimal numbers: 10.5 20.25
Sum: 30.75
```

এখানে `map(float, ...)` প্রতিটি input-কে float-এ convert করেছে।

### Example: Average of Three Numbers

```python
a, b, c = map(float, input("Enter three numbers: ").split())

average = (a + b + c) / 3

print("Average:", average)
```

Sample Interaction:

```text
Enter three numbers: 10 20 30
Average: 20.0
```

পূর্ণসংখ্যার মতো value দিলেও `float()` ব্যবহার করার কারণে প্রতিটি value float হয়েছে।

## 7. Understanding Unpacking

একাধিক input নেওয়ার সময় প্রায়ই এমন code দেখা যায়:

```python
a, b, c = map(int, input().split())
```

এখানে `a`, `b` এবং `c`-তে আলাদা value assign হয়। এই প্রক্রিয়াকে **unpacking** বলা হয়।

### Example

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

এখানে list-এর তিনটি value তিনটি variable-এ assign হয়েছে।

একইভাবে:

```python
a, b, c = map(int, input().split())
```

যদি user লেখে:

```text
10 20 30
```

তাহলে:

- `a = 10`
- `b = 20`
- `c = 30`

### গুরুত্বপূর্ণ নিয়ম

Unpacking করার সময় value-এর সংখ্যা এবং variable-এর সংখ্যা মিলতে হবে।

```python
a, b = 10, 20
```

এটি সঠিক।

কিন্তু:

```python
a, b = 10, 20, 30
```

এতে `ValueError` হবে, কারণ দুটি variable-এর জন্য তিনটি value দেওয়া হয়েছে।

একইভাবে, দুটি variable নিয়ে input-এ তিনটি value দিলে `ValueError` হবে।

## 8. Difference Between `split()` and `map()`

`split()` এবং `map()` এক কাজ করে না।

| Method | কাজ |
|---|---|
| `split()` | String-কে বিভিন্ন অংশে ভাগ করে |
| `map()` | একটি function প্রতিটি item-এর ওপর প্রয়োগ করে |
| `int()` | উপযুক্ত value-কে integer-এ convert করে |
| `float()` | উপযুক্ত value-কে float-এ convert করে |

### Example: Only `split()`

```python
data = input("Enter numbers: ").split()

print(data)
print(type(data[0]))
```

Input:

```text
10 20 30
```

Output:

```text
['10', '20', '30']
<class 'str'>
```

### Example: `split()` with `map()`

```python
data = list(map(int, input("Enter numbers: ").split()))

print(data)
print(type(data[0]))
```

Input:

```text
10 20 30
```

Output:

```text
[10, 20, 30]
<class 'int'>
```

এখানে `map(int, ...)` প্রতিটি string-কে integer-এ convert করেছে এবং `list()` result-টিকে list বানিয়েছে।

Python 3-এ `map()` নিজে সরাসরি list নয়; এটি একটি iterable object return করে। তাই list দরকার হলে `list()` ব্যবহার করা হয়।

## 9. Taking Multiple Inputs with a Custom Separator

Default `split()` whitespace অনুযায়ী string ভাগ করে। তবে নির্দিষ্ট separator দিয়েও ভাগ করা যায়।

### Example: Comma-Separated Integers

```python
a, b, c = map(int, input("Enter three numbers: ").split(","))

print("Total:", a + b + c)
```

Sample Interaction:

```text
Enter three numbers: 10,20,30
Total: 60
```

এখানে `split(",")` ব্যবহার করা হয়েছে।

### Example: Hyphen-Separated Values

```python
a, b, c = input("Enter three values: ").split("-")

print(a)
print(b)
print(c)
```

Sample Interaction:

```text
Enter three values: red-green-blue
red
green
blue
```

এখানে value-গুলো string হিসেবেই রয়েছে, কারণ `int()` বা `float()` দিয়ে conversion করা হয়নি।

**সতর্কতা:** `split(",")` ব্যবহার করলে input-এ comma থাকতে হবে। যেমন `10,20,30` সঠিক, কিন্তু `10 20 30` দিলে তিনটি value আলাদা হবে না।

## 10. Taking a List of Numbers

যখন input-এর সংখ্যা আগে থেকে নির্দিষ্ট নয়, তখন list ব্যবহার করা সুবিধাজনক।

### Example

```python
numbers = list(map(int, input("Enter numbers: ").split()))

print("Numbers:", numbers)
print("Total:", sum(numbers))
```

Sample Interaction:

```text
Enter numbers: 10 20 30 40 50
Numbers: [10, 20, 30, 40, 50]
Total: 150
```

এখানে পাঁচটি সংখ্যা নেওয়া হয়েছে। চাইলে user আরও বেশি বা কম সংখ্যা দিতে পারে।

`sum()` list-এর numeric value-গুলোর যোগফল বের করে।

### Example: Find the Maximum

```python
numbers = list(map(int, input("Enter numbers: ").split()))

print("Maximum:", max(numbers))
```

Sample Interaction:

```text
Enter numbers: 12 45 7 89 23
Maximum: 89
```

এই program-এ `max()` সবচেয়ে বড় সংখ্যাটি বের করে।

খেয়াল রাখবে, `max()` ব্যবহার করার আগে list-এ অন্তত একটি value থাকা প্রয়োজন।

## 11. Common Errors and Their Solutions

### Error 1: Wrong Number of Inputs

```python
a, b = map(int, input().split())
```

User যদি লেখে:

```text
10 20 30
```

তাহলে `ValueError` হবে, কারণ দুটি variable-এর জন্য তিনটি value দেওয়া হয়েছে।

**Solution:** প্রয়োজন অনুযায়ী variable-এর সংখ্যা মিলিয়ে দাও।

```python
a, b, c = map(int, input().split())
```

### Error 2: Invalid Numeric Input

```python
a, b = map(int, input().split())
```

User যদি লেখে:

```text
10 hello
```

তাহলে `ValueError` হবে, কারণ `"hello"` integer-এ convert করা যায় না।

### Error 3: Forgetting `split()`

```python
a, b = map(int, input())
```

এটি সাধারণত প্রত্যাশিতভাবে দুটি সংখ্যা পড়বে না। `input()`-এর string character অনুযায়ী iterate হবে; এটি whitespace দিয়ে আলাদা করা numeric value-এর তালিকা নয়।

**Correct code:**

```python
a, b = map(int, input().split())
```

### Error 4: Using `split(",")` with Space-Separated Input

```python
a, b = map(int, input().split(","))
```

User যদি লেখে `10 20`, তাহলে প্রত্যাশিত দুটি value পাওয়া যাবে না এবং conversion error হবে।

**Solution:** Input-এর format অনুযায়ী separator ব্যবহার করো।

```python
a, b = map(int, input().split())
```

### Error 5: Forgetting `list()` When a List Is Needed

```python
numbers = map(int, input().split())

print(numbers)
```

এখানে সাধারণত সংখ্যার list-এর বদলে একটি `map` object-এর পরিচয় দেখা যাবে।

**Solution:**

```python
numbers = list(map(int, input().split()))

print(numbers)
```

## 12. Practical Programs

### Program 1: Add Two Numbers in One Line

```python
a, b = map(int, input("Enter two numbers: ").split())

print("Sum:", a + b)
```

Sample Interaction:

```text
Enter two numbers: 25 35
Sum: 60
```

### Program 2: Calculate Average of Five Numbers

```python
a, b, c, d, e = map(float, input("Enter five marks: ").split())

average = (a + b + c + d + e) / 5

print("Average:", average)
```

Sample Interaction:

```text
Enter five marks: 80 75 90 85 70
Average: 80.0
```

### Program 3: Sum Any Number of Integers

```python
numbers = list(map(int, input("Enter numbers: ").split()))

total = sum(numbers)

print("Total:", total)
```

Sample Interaction:

```text
Enter numbers: 5 10 15 20
Total: 50
```

### Program 4: Find Minimum and Maximum

```python
numbers = list(map(int, input("Enter numbers: ").split()))

print("Minimum:", min(numbers))
print("Maximum:", max(numbers))
```

Sample Interaction:

```text
Enter numbers: 18 5 42 11 27
Minimum: 5
Maximum: 42
```

### Program 5: Calculate Shopping Total

```python
prices = list(map(float, input("Enter product prices: ").split()))

total = sum(prices)

print("Total Price:", total)
```

Sample Interaction:

```text
Enter product prices: 100.50 250 75.25
Total Price: 425.75
```

## 13. Practice Exercises

### Exercise 1: Two Integers

একই লাইনে দুটি integer নিয়ে তাদের যোগফল বের করো।

### Exercise 2: Three Integers

একই লাইনে তিনটি integer নিয়ে তাদের গুণফল বের করো।

### Exercise 3: Average

একই লাইনে চারটি float input নিয়ে average বের করো।

### Exercise 4: List of Numbers

একই লাইনে যেকোনো সংখ্যক integer নিয়ে list তৈরি করো এবং list-টি print করো।

### Exercise 5: Sum and Maximum

একটি integer list input নিয়ে তার total এবং maximum বের করো।

### Exercise 6: Comma-Separated Input

User-এর কাছ থেকে `10,20,30,40`-এর মতো comma-separated integer input নিয়ে যোগফল বের করো।

### Exercise 7: Find the Minimum

একই লাইনে দেওয়া integer-গুলোর মধ্যে সবচেয়ে ছোট সংখ্যা বের করো।

### Exercise 8: Product Prices

একই লাইনে কয়েকটি decimal price input নিয়ে মোট price বের করো।

### Exercise 9: Predict the Output

```python
a, b, c = map(int, input().split())

print(a + b + c)
```

Input:

```text
5 10 15
```

Output কী হবে?

### Exercise 10: Challenge

একই লাইনে পাঁচটি integer input নাও। তাদের sum, average, maximum এবং minimum print করো।

## 14. Practice Answer Key

### Answer 1

```python
a, b = map(int, input("Enter two integers: ").split())

print("Sum:", a + b)
```

### Answer 2

```python
a, b, c = map(int, input("Enter three integers: ").split())

print("Product:", a * b * c)
```

### Answer 3

```python
a, b, c, d = map(float, input("Enter four numbers: ").split())

print("Average:", (a + b + c + d) / 4)
```

### Answer 4

```python
numbers = list(map(int, input("Enter integers: ").split()))

print(numbers)
```

### Answer 5

```python
numbers = list(map(int, input("Enter integers: ").split()))

print("Total:", sum(numbers))
print("Maximum:", max(numbers))
```

### Answer 6

```python
numbers = list(map(int, input("Enter comma-separated integers: ").split(",")))

print("Sum:", sum(numbers))
```

### Answer 7

```python
numbers = list(map(int, input("Enter integers: ").split()))

print("Minimum:", min(numbers))
```

### Answer 8

```python
prices = list(map(float, input("Enter prices: ").split()))

print("Total Price:", sum(prices))
```

### Answer 9

Output:

```text
30
```

কারণ `5 + 10 + 15 = 30`।

### Answer 10

```python
numbers = list(map(int, input("Enter five integers: ").split()))

if len(numbers) == 5:
    print("Sum:", sum(numbers))
    print("Average:", sum(numbers) / 5)
    print("Maximum:", max(numbers))
    print("Minimum:", min(numbers))
else:
    print("Please enter exactly five integers.")
```

এখানে `len(numbers)` দিয়ে input list-এ ঠিক পাঁচটি value আছে কি না, তা পরীক্ষা করা হয়েছে।

## 15. Best Practices

1. Beginner হিসেবে আলাদা লাইনে `input()` ব্যবহার করে শুরু করো।
2. একই লাইনে একাধিক value নিতে `input().split()` ব্যবহার করো।
3. Numeric input convert করতে `map(int, ...)` অথবা `map(float, ...)` ব্যবহার করতে পারো।
4. `split()` string-কে ভাগ করে, কিন্তু নিজে থেকে numeric conversion করে না।
5. নির্দিষ্ট সংখ্যক variable ব্যবহার করলে input-এর value সংখ্যাও মিলিয়ে দাও।
6. Input format অনুযায়ী separator নির্বাচন করো।
7. List প্রয়োজন হলে `list(map(...))` ব্যবহার করো।
8. `sum()`, `min()` ও `max()` ব্যবহার করার আগে list খালি কি না, প্রয়োজন হলে পরীক্ষা করো।

## 16. Chapter Summary

- একাধিক input আলাদা লাইনে বা একই লাইনে নেওয়া যায়।
- `input()` একটি string return করে।
- `split()` string-কে বিভিন্ন অংশে ভাগ করে।
- `map(int, ...)` প্রতিটি অংশকে integer-এ convert করে।
- `map(float, ...)` প্রতিটি অংশকে float-এ convert করে।
- Unpacking-এর মাধ্যমে একাধিক variable-এ value assign করা যায়।
- `list(map(int, ...))` ব্যবহার করে integer-এর list তৈরি করা যায়।
- `sum()`, `min()` এবং `max()` list-এর ওপর বিভিন্ন calculation করতে সাহায্য করে।
- ভুল input format বা ভুল value count-এর কারণে error হতে পারে।

## 17. Self-Assessment Checklist

- [ ] আলাদা লাইনে একাধিক input নিতে পারি।
- [ ] `split()`-এর কাজ ব্যাখ্যা করতে পারি।
- [ ] একই লাইনে দুটি বা তিনটি integer নিতে পারি।
- [ ] `map()` ব্যবহার করে একাধিক value convert করতে পারি।
- [ ] Unpacking-এর নিয়ম বুঝি।
- [ ] একটি numeric list তৈরি করতে পারি।
- [ ] List-এর sum, minimum ও maximum বের করতে পারি।
- [ ] সাধারণ input-related error শনাক্ত করতে পারি।

**Next Topic:** `14_Splitting_and_Unpacking_Input.md` — এখানে `split()` এবং unpacking আরও গভীরভাবে শিখব, বিশেষ করে variable-এর সংখ্যা, separator এবং input format কীভাবে সঠিকভাবে handle করতে হয়।