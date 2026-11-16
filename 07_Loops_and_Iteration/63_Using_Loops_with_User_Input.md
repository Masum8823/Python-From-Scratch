# 63. Using Loops with User Input

## 1. Introduction

Python-এ `input()` function দিয়ে user-এর কাছ থেকে data নেওয়া যায়। আর loop ব্যবহার করে একই input process বারবার করা যায়।

ধরি, user-এর কাছ থেকে ৫টি সংখ্যা নিতে হবে এবং সেগুলোর sum বের করতে হবে।

Loop ছাড়া প্রতিটি সংখ্যার জন্য আলাদা `input()` লিখতে হবে। কিন্তু loop ব্যবহার করলে একই code বারবার execute করা যায়।

### Example

```python
total = 0

for i in range(5):
    number = int(input("Enter a number: "))
    total += number

print("Total:", total)
```

Sample input:

```text
10
20
30
40
50
```

Output:

```text
Total: 150
```

### Learning Objectives

এই Topic শেষে তুমি পারবে:

- Loop দিয়ে বারবার user input নিতে।
- নির্দিষ্ট সংখ্যক input process করতে।
- User input-এর sum ও average বের করতে।
- নির্দিষ্ট condition অনুযায়ী input count করতে।
- Sentinel value ব্যবহার করে input নেওয়া বন্ধ করতে।
- Input validation-এর জন্য loop ব্যবহার করতে।
- Common input-loop mistakes শনাক্ত করতে।

## 2. Taking Multiple Inputs Using a `for` Loop

যখন আগে থেকেই জানা থাকে কতবার input নিতে হবে, তখন `for` loop ব্যবহার করা সুবিধাজনক।

### Code

```python
for i in range(3):
    number = int(input("Enter a number: "))
    print("You entered:", number)
```

### Sample Output

```text
Enter a number: 10
You entered: 10
Enter a number: 20
You entered: 20
Enter a number: 30
You entered: 30
```

### Explanation

- `range(3)` loop-টিকে ৩ বার চালায়।
- প্রতিবার `input()` একটি সংখ্যা নেয়।
- `int()` input-কে integer-এ রূপান্তর করে।
- `print()` user-এর দেওয়া সংখ্যা দেখায়।

এখানে user ঠিক ৩ বার input দেওয়ার সুযোগ পাবে।

## 3. Taking Multiple Inputs Using a `while` Loop

`while` loop ব্যবহার করেও নির্দিষ্ট সংখ্যক input নেওয়া যায়।

### Code

```python
count = 0

while count < 3:
    number = int(input("Enter a number: "))
    print("You entered:", number)

    count += 1
```

### Sample Output

```text
Enter a number: 5
You entered: 5
Enter a number: 10
You entered: 10
Enter a number: 15
You entered: 15
```

### Explanation

- `count = 0` দিয়ে শুরু করা হয়।
- `count < 3` True থাকা পর্যন্ত loop চলে।
- প্রতিবার input নেওয়ার পরে `count += 1` হয়।
- `count`-এর value `3` হলে condition False হয় এবং loop শেষ হয়।

**মনে রাখবে:** `count += 1` বাদ দিলে condition পরিবর্তিত হবে না এবং loop অনন্তকাল চলতে পারে।

## 4. Calculating the Sum of User Inputs

User-এর কাছ থেকে ৫টি সংখ্যা নিয়ে sum বের করি।

### Code

```python
total = 0

for i in range(5):
    number = int(input("Enter a number: "))
    total += number

print("Sum:", total)
```

### Sample Output

```text
Enter a number: 10
Enter a number: 20
Enter a number: 30
Enter a number: 40
Enter a number: 50
Sum: 150
```

### Explanation

এখানে `total` হলো accumulator variable।

প্রতিবার নতুন সংখ্যা input নেওয়ার পরে:

```python
total += number
```

নতুন সংখ্যাটি আগের total-এর সঙ্গে যোগ হয়।

Dry run:

| Input | Calculation | Total |
|---:|---|---:|
| 10 | 0 + 10 | 10 |
| 20 | 10 + 20 | 30 |
| 30 | 30 + 30 | 60 |
| 40 | 60 + 40 | 100 |
| 50 | 100 + 50 | 150 |

শেষে total হয় `150`।

## 5. Calculating the Average of User Inputs

Average বের করার formula:

\[
\text{Average}=\frac{\text{Sum of values}}{\text{Number of values}}
\]

### Code

```python
total = 0
count = 5

for i in range(count):
    number = float(input("Enter a number: "))
    total += number

average = total / count

print("Sum:", total)
print("Average:", average)
```

### Sample Input

```text
10
20
30
40
50
```

### Output

```text
Sum: 150.0
Average: 30.0
```

### Explanation

- `total` সব input-এর sum রাখে।
- `count` মোট input-এর সংখ্যা রাখে।
- `total / count` দিয়ে average বের হয়।

**Important:** Average বের করার সময় count শূন্য হওয়া যাবে না। এই উদাহরণে `count = 5`, তাই division by zero-এর সমস্যা নেই।

## 6. Counting Positive, Negative and Zero Inputs

User-এর কাছ থেকে ৫টি integer নিয়ে positive, negative ও zero-এর সংখ্যা গণনা করি।

### Code

```python
positive = 0
negative = 0
zero = 0

for i in range(5):
    number = int(input("Enter an integer: "))

    if number > 0:
        positive += 1
    elif number < 0:
        negative += 1
    else:
        zero += 1

print("Positive numbers:", positive)
print("Negative numbers:", negative)
print("Zeros:", zero)
```

### Sample Input

```text
10
-5
0
20
-2
```

### Output

```text
Positive numbers: 2
Negative numbers: 2
Zeros: 1
```

### Explanation

প্রতিটি input-এর জন্য:

- Number `0`-এর বড় হলে positive count বাড়ে।
- Number `0`-এর ছোট হলে negative count বাড়ে।
- অন্যথায় zero count বাড়ে।

এখানে মোট input:

\[
2+2+1=5
\]

অর্থাৎ তিনটি category-তে সব input গণনা করা হয়েছে।

## 7. Finding the Maximum Value from User Inputs

User-এর কাছ থেকে কয়েকটি সংখ্যা নিয়ে সবচেয়ে বড় সংখ্যাটি বের করা যায়।

### Code

```python
count = int(input("How many numbers? "))

if count <= 0:
    print("Please enter a positive count.")
else:
    maximum = int(input("Enter number 1: "))

    for i in range(2, count + 1):
        number = int(input(f"Enter number {i}: "))

        if number > maximum:
            maximum = number

    print("Maximum:", maximum)
```

### Sample Output

```text
How many numbers? 4
Enter number 1: 15
Enter number 2: 8
Enter number 3: 32
Enter number 4: 21
Maximum: 32
```

### Explanation

- প্রথম input-কে প্রাথমিক maximum ধরা হয়।
- পরের প্রতিটি সংখ্যার সঙ্গে maximum তুলনা করা হয়।
- নতুন সংখ্যা বড় হলে maximum update হয়।
- সব input নেওয়ার পরে maximum print হয়।

**কেন `maximum = 0` দিয়ে শুরু করিনি?**

কারণ সব input negative হলে `0` ভুল maximum হতে পারে। প্রথম input-কে maximum ধরলে negative সংখ্যার ক্ষেত্রেও সঠিক ফল পাওয়া যায়।

## 8. Using a Sentinel Value to Stop Input

কখনো user আগে থেকে জানে না কতটি সংখ্যা input দেবে। তখন sentinel value ব্যবহার করা যায়।

Sentinel হলো একটি নির্দিষ্ট value, যা input নেওয়া বন্ধ করার সংকেত দেয়।

ধরি, `-1` দিলে input নেওয়া বন্ধ হবে।

### Code

```python
total = 0

while True:
    number = int(input("Enter a number (-1 to stop): "))

    if number == -1:
        break

    total += number

print("Sum:", total)
```

### Sample Output

```text
Enter a number (-1 to stop): 10
Enter a number (-1 to stop): 20
Enter a number (-1 to stop): 30
Enter a number (-1 to stop): -1
Sum: 60
```

### Explanation

- `while True` বারবার input নেয়।
- User `-1` দিলে `break` loop বন্ধ করে।
- Sentinel value sum-এর সঙ্গে যোগ হয় না, কারণ check-টি addition-এর আগে করা হয়েছে।
- Loop শেষ হলে total print হয়।

**সতর্কতা:** এই পদ্ধতিতে `-1` একটি বৈধ data value হিসেবেও ব্যবহার করা যাবে না। যদি negative number-ও data হিসেবে দরকার হয়, তাহলে অন্য sentinel বা আলাদা stopping mechanism নির্বাচন করতে হবে।

## 9. Counting Inputs Until the Sentinel Value

Sentinel value ব্যবহার করে শুধু sum নয়, input-এর সংখ্যা গণনাও করা যায়।

### Code

```python
count = 0

while True:
    number = int(input("Enter a number (0 to stop): "))

    if number == 0:
        break

    count += 1

print("Total inputs:", count)
```

### Sample Output

```text
Enter a number (0 to stop): 10
Enter a number (0 to stop): 20
Enter a number (0 to stop): 30
Enter a number (0 to stop): 0
Total inputs: 3
```

### Explanation

- প্রতিটি non-zero input-এর জন্য count বাড়ে।
- `0` এলে loop বন্ধ হয়।
- `0` নিজে count-এর অন্তর্ভুক্ত হয় না।

এখানে zero-কে sentinel হিসেবে ব্যবহার করায় zero-কে সাধারণ data হিসেবে গণনা করা হচ্ছে না।

## 10. Calculating an Average Until the Sentinel

এবার user যতগুলো সংখ্যা ইচ্ছা input দিতে পারবে। `-1` দিলে input শেষ হবে এবং average বের হবে।

### Code

```python
total = 0
count = 0

while True:
    number = float(input("Enter a number (-1 to stop): "))

    if number == -1:
        break

    total += number
    count += 1

if count > 0:
    average = total / count
    print("Average:", average)
else:
    print("No numbers were entered.")
```

### Sample Output

```text
Enter a number (-1 to stop): 10
Enter a number (-1 to stop): 20
Enter a number (-1 to stop): 30
Enter a number (-1 to stop): -1
Average: 20.0
```

### Explanation

- `total` সব valid input-এর sum রাখে।
- `count` valid input-এর সংখ্যা রাখে।
- Sentinel `-1` sum বা count-এ অন্তর্ভুক্ত হয় না।
- `count > 0` হলে average বের হয়।
- কোনো data না থাকলে division না করে message দেখায়।

এই উদাহরণে `-1`-কে sentinel ধরা হয়েছে, তাই `-1`-কে সাধারণ data হিসেবে যোগ করা যাবে না।

## 11. Input Validation Using Loops

Input validation হলো user-এর দেওয়া input গ্রহণযোগ্য কি না, তা পরীক্ষা করা।

ধরি, marks অবশ্যই `0` থেকে `100`-এর মধ্যে হতে হবে।

### Code

```python
marks = int(input("Enter marks (0-100): "))

while marks < 0 or marks > 100:
    print("Invalid marks. Try again.")
    marks = int(input("Enter marks (0-100): "))

print("Accepted marks:", marks)
```

### Sample Output

```text
Enter marks (0-100): 120
Invalid marks. Try again.
Enter marks (0-100): -5
Invalid marks. Try again.
Enter marks (0-100): 85
Accepted marks: 85
```

### Explanation

Condition:

```python
marks < 0 or marks > 100
```

এর অর্থ marks গ্রহণযোগ্য range-এর বাইরে কি না।

- Marks `0`-এর কম হলে আবার input নেওয়া হয়।
- Marks `100`-এর বেশি হলেও আবার input নেওয়া হয়।
- Marks `0` থেকে `100`-এর মধ্যে হলে loop শেষ হয়।

এই উদাহরণে ধরে নেওয়া হয়েছে user integer-এ রূপান্তরযোগ্য input দেবেন। যেমন `abc` দিলে `int()` error হবে। সেটিও handle করতে হলে `try-except` ব্যবহার করা যায়।

## 12. Combining User Input with Conditions

Loop-এর সঙ্গে conditional statement ব্যবহার করে input-এর মধ্যে নির্দিষ্ট ধরনের value খুঁজে বের করা যায়।

ধরি, user-এর কাছ থেকে ৫টি integer নিয়ে even ও odd count করব।

### Code

```python
even_count = 0
odd_count = 0

for i in range(5):
    number = int(input("Enter an integer: "))

    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

print("Even count:", even_count)
print("Odd count:", odd_count)
```

### Sample Input

```text
2
5
8
11
14
```

### Output

```text
Even count: 3
Odd count: 2
```

### Explanation

- `number % 2 == 0` হলে even count বাড়ে।
- অন্যথায় odd count বাড়ে।
- পাঁচটি input process হওয়ার পর final counts print হয়।

## 13. Storing User Inputs in a List

যদি শুধু sum বা count নয়, পরেও input-গুলো ব্যবহার করতে হয়, তাহলে list-এ সংরক্ষণ করা যায়।

### Code

```python
numbers = []

for i in range(5):
    number = int(input("Enter a number: "))
    numbers.append(number)

print("Numbers:", numbers)
print("Sum:", sum(numbers))
print("Maximum:", max(numbers))
print("Minimum:", min(numbers))
```

### Sample Input

```text
10
25
5
40
20
```

### Output

```text
Numbers: [10, 25, 5, 40, 20]
Sum: 100
Maximum: 40
Minimum: 5
```

### Explanation

- `numbers = []` দিয়ে empty list তৈরি হয়।
- `append()` প্রতিটি input list-এ যোগ করে।
- `sum()` মোট যোগফল বের করে।
- `max()` সবচেয়ে বড় value বের করে।
- `min()` সবচেয়ে ছোট value বের করে।

এখানে পাঁচটি input নেওয়া হয়েছে। List-এ data রাখা হলে পরেও data search, sort বা অন্য calculation করা যায়।

## 14. Using `while` Loop for Password Attempts

User-কে সঠিক password দেওয়া পর্যন্ত input নেওয়া যায়।

### Code

```python
correct_password = "python123"
attempts = 0
max_attempts = 3

while attempts < max_attempts:
    password = input("Enter password: ")

    if password == correct_password:
        print("Login successful.")
        break

    attempts += 1
    print("Incorrect password.")

if attempts == max_attempts and password != correct_password:
    print("Maximum attempts reached.")
```

### Sample Output

```text
Enter password: hello
Incorrect password.
Enter password: abc123
Incorrect password.
Enter password: wrong
Incorrect password.
Maximum attempts reached.
```

### Explanation

- সর্বোচ্চ তিনবার password দেওয়ার সুযোগ রয়েছে।
- সঠিক password দিলে `break` loop বন্ধ করে।
- ভুল হলে `attempts` বাড়ে।
- তিনবার ভুল হলে loop শেষ হয়।

**Security note:** এটি শুধু loop practice-এর উদাহরণ। বাস্তব login system-এ password plaintext হিসেবে রাখা বা এভাবে সরাসরি তুলনা করা যথেষ্ট নিরাপদ নয়।

## 15. Common Mistakes

### Mistake 1: Forgetting to Update the Counter

ভুল:

```python
count = 0

while count < 5:
    number = int(input("Enter a number: "))
```

এখানে `count` কখনো বাড়ে না। ফলে loop বন্ধ হবে না।

সঠিক:

```python
count += 1
```

প্রতিটি iteration-এর শেষে counter update করতে হবে।

### Mistake 2: Adding the Sentinel to the Sum

ভুল:

```python
number = int(input("Enter number: "))
total += number

if number == -1:
    break
```

এখানে `-1`-ও total-এ যোগ হয়ে যায়।

সঠিক:

```python
if number == -1:
    break

total += number
```

Sentinel check আগে করতে হবে।

### Mistake 3: Dividing by Zero

ভুল:

```python
average = total / count
```

যদি `count = 0` হয়, তাহলে `ZeroDivisionError` হবে।

সঠিক:

```python
if count > 0:
    average = total / count
else:
    print("No data available.")
```

### Mistake 4: Forgetting Type Conversion

`input()` string দেয়। তাই numeric calculation-এর জন্য সাধারণত `int()` বা `float()` প্রয়োজন।

### Mistake 5: Incorrect Loop Condition

Marks validation-এর জন্য:

```python
while marks < 0 or marks > 100:
```

সঠিক।

কিন্তু:

```python
while marks < 0 and marks > 100:
```

বাস্তব numeric value-এর জন্য condition-টি কখনো True হতে পারে না, কারণ একই number একসঙ্গে `0`-এর কম ও `100`-এর বেশি হতে পারে না।

### Mistake 6: Overwriting the Accumulator

ভুল:

```python
total = number
```

এটি প্রতিবার আগের total মুছে দেয়।

সঠিক:

```python
total += number
```

### Mistake 7: Assuming Every Input Is Valid

`int(input())`-এ user text বা decimal string দিলে error হতে পারে। User input validate করতে হলে `try-except` ব্যবহার করা যায়।

## 16. Practice Exercises

### Exercise 1

`for` loop ব্যবহার করে user-এর কাছ থেকে ৫টি integer নাও এবং sum বের করো।

### Exercise 2

`while` loop ব্যবহার করে user-এর কাছ থেকে ৩টি সংখ্যা নাও এবং average বের করো।

### Exercise 3

User-এর কাছ থেকে ১০টি integer নিয়ে even ও odd সংখ্যা গণনা করো।

### Exercise 4

User যতগুলো সংখ্যা দিতে চায়, ততগুলো নাও। `0` দিলে input বন্ধ হবে। সব non-zero input-এর sum বের করো।

### Exercise 5

Sentinel `-1` ব্যবহার করে input নেওয়া চালিয়ে যাও এবং কতটি valid number দেওয়া হয়েছে, তা গণনা করো।

### Exercise 6

User-এর কাছ থেকে ৫টি সংখ্যা নিয়ে maximum ও minimum বের করো।

### Exercise 7

Marks `0` থেকে `100`-এর মধ্যে না হওয়া পর্যন্ত input নিতে থাকো।

### Exercise 8

একটি list-এ user-এর কাছ থেকে ৫টি নাম নিয়ে সব নাম print করো।

### Exercise 9

নিচের code-এর output নির্ণয় করো:

```python
total = 0

for i in range(3):
    number = int(input("Enter number: "))
    total += number

print(total)
```

Input:

```text
5
10
15
```

### Exercise 10

নিচের code-এ ভুলটি খুঁজে বের করো:

```python
total = 0

while True:
    number = int(input("Enter number (-1 to stop): "))
    total += number

    if number == -1:
        break

print(total)
```

## 17. Practice Answer Key

### Answer 1

```python
total = 0

for i in range(5):
    number = int(input("Enter an integer: "))
    total += number

print("Sum:", total)
```

### Answer 2

```python
total = 0
count = 3

for i in range(count):
    number = float(input("Enter a number: "))
    total += number

print("Average:", total / count)
```

### Answer 3

```python
even_count = 0
odd_count = 0

for i in range(10):
    number = int(input("Enter an integer: "))

    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

print("Even:", even_count)
print("Odd:", odd_count)
```

### Answer 4

```python
total = 0

while True:
    number = int(input("Enter number (0 to stop): "))

    if number == 0:
        break

    total += number

print("Sum:", total)
```

### Answer 5

```python
count = 0

while True:
    number = int(input("Enter number (-1 to stop): "))

    if number == -1:
        break

    count += 1

print("Valid inputs:", count)
```

### Answer 6

```python
first = int(input("Enter number 1: "))
maximum = first
minimum = first

for i in range(4):
    number = int(input("Enter another number: "))

    if number > maximum:
        maximum = number

    if number < minimum:
        minimum = number

print("Maximum:", maximum)
print("Minimum:", minimum)
```

### Answer 7

```python
marks = int(input("Enter marks (0-100): "))

while marks < 0 or marks > 100:
    print("Invalid marks.")
    marks = int(input("Enter marks (0-100): "))

print("Accepted:", marks)
```

### Answer 8

```python
names = []

for i in range(5):
    name = input("Enter a name: ")
    names.append(name)

for name in names:
    print(name)
```

### Answer 9

Output:

```text
Enter number: 5
Enter number: 10
Enter number: 15
30
```

কারণ:

\[
5+10+15=30
\]

### Answer 10

সমস্যা হলো sentinel `-1`-কে sum-এ যোগ করার পরে loop বন্ধ করা হচ্ছে।

সঠিক code:

```python
total = 0

while True:
    number = int(input("Enter number (-1 to stop): "))

    if number == -1:
        break

    total += number

print(total)
```

## 18. Chapter Summary

- Loop দিয়ে user-এর কাছ থেকে বারবার input নেওয়া যায়।
- নির্দিষ্ট সংখ্যক input-এর জন্য `for` বা counter-controlled `while` ব্যবহার করা যায়।
- Accumulator variable দিয়ে sum হিসাব করা যায়।
- Count variable দিয়ে input বা নির্দিষ্ট category-এর সংখ্যা গণনা করা যায়।
- Average বের করতে sum-কে count দিয়ে ভাগ করতে হয়।
- Sentinel value দিয়ে user input নেওয়া বন্ধ করতে পারে।
- Sentinel value সাধারণ data হিসেবে গণনা বা যোগ করা উচিত নয়।
- Input validation-এর জন্য loop ব্যবহার করা যায়।
- List-এ input সংরক্ষণ করলে পরে আরও calculation করা যায়।
- `try-except` ব্যবহার করে invalid numeric input handle করা যায়।

## 19. Completion Checklist

- [ ] `for` loop দিয়ে multiple input নিতে পারি।
- [ ] `while` loop দিয়ে multiple input নিতে পারি।
- [ ] User input-এর sum বের করতে পারি।
- [ ] Average বের করতে পারি।
- [ ] Positive, negative, zero, even ও odd count করতে পারি।
- [ ] Maximum ও minimum বের করতে পারি।
- [ ] Sentinel value ব্যবহার করতে পারি।
- [ ] Input validation করতে পারি।
- [ ] User input list-এ store করতে পারি।
- [ ] Common mistakes শনাক্ত ও ঠিক করতে পারি।

**Next Topic:** `64_Combining_Loops_with_Conditional_Statements.md`