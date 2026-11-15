# 50. Finding the Average of Numbers

## 1. Introduction

Average হলো কয়েকটি সংখ্যার যোগফলকে মোট সংখ্যার পরিমাণ দিয়ে ভাগ করলে যে মান পাওয়া যায়।

উদাহরণস্বরূপ, তিনটি সংখ্যার মান ১০, ২০ এবং ৩০ হলে:

\[
\text{Average}=\frac{10+20+30}{3}=20
\]

Python-এ loop ব্যবহার করে অনেকগুলো সংখ্যার sum এবং count বের করে average নির্ণয় করা যায়।

এই Topic-এ আমরা শিখব:

- Average-এর formula
- Sum ও count ব্যবহার করে average বের করা
- `for` এবং `while` loop ব্যবহার করা
- User input থেকে average বের করা
- List-এর average নির্ণয় করা
- Even, odd এবং condition অনুযায়ী average বের করা
- Division by zero এবং অন্যান্য common mistakes

## 2. Understanding the Average Formula

Average বের করার formula:

\[
\text{Average}=\frac{\text{Sum of Values}}{\text{Number of Values}}
\]

এখানে:

- **Sum:** সব সংখ্যার যোগফল।
- **Count:** মোট কতটি সংখ্যা রয়েছে।
- **Average:** সংখ্যাগুলোর গড় মান।

### Example

ধরা যাক, তিনটি পরীক্ষার marks হলো ৭০, ৮০ এবং ৯০।

Sum:

\[
70+80+90=240
\]

Count:

\[
3
\]

Average:

\[
\frac{240}{3}=80
\]

সুতরাং average marks হলো ৮০।

## 3. Calculating Average Using a Loop

প্রথমে loop দিয়ে sum এবং count বের করতে হবে। তারপর sum-কে count দিয়ে ভাগ করতে হবে।

### Code

```python
total = 0
count = 0

for number in range(1, 6):
    total += number
    count += 1

average = total / count

print("Sum:", total)
print("Count:", count)
print("Average:", average)
```

### Output

```text
Sum: 15
Count: 5
Average: 3.0
```

### Explanation

- `total = 0` যোগফল জমা রাখে।
- `count = 0` সংখ্যার পরিমাণ গণনা করে।
- `total += number` প্রতিটি সংখ্যা যোগ করে।
- `count += 1` প্রতিটি সংখ্যার জন্য count বাড়ায়।
- `total / count` average বের করে।

এখানে ১ থেকে ৫ পর্যন্ত সংখ্যার average হলো ৩.০।

## 4. Calculating Average Using a `for` Loop

ব্যবহারকারী একটি limit দিলে ১ থেকে সেই limit পর্যন্ত সংখ্যার average বের করা যায়।

### Code

```python
n = int(input("Enter the limit: "))

total = 0
count = 0

for number in range(1, n + 1):
    total += number
    count += 1

if count > 0:
    average = total / count
    print("Average:", average)
else:
    print("No numbers available")
```

### Sample Input and Output

```text
Enter the limit: 5
Average: 3.0
```

### Explanation

১ থেকে ৫ পর্যন্ত:

- Sum = ১৫
- Count = ৫
- Average = ১৫ / ৫ = ৩.০

যদি `n = 0` বা negative integer হয়, তাহলে `range(1, n + 1)` খালি থাকবে। সে ক্ষেত্রে `count` হবে ০ এবং `else` block চলবে।

এই উদাহরণে input একটি integer হবে বলে ধরে নেওয়া হয়েছে।

## 5. Calculating Average Using a `while` Loop

একই কাজ `while` loop দিয়েও করা যায়।

### Code

```python
number = 1
n = 5

total = 0
count = 0

while number <= n:
    total += number
    count += 1
    number += 1

if count > 0:
    average = total / count
    print("Average:", average)
else:
    print("No numbers available")
```

### Output

```text
Average: 3.0
```

### Explanation

প্রতিবার loop চলার সময়:

1. বর্তমান সংখ্যা `total`-এর সঙ্গে যোগ হয়।
2. `count` এক বাড়ে।
3. `number` এক বাড়ে।

সব সংখ্যা process করা হলে average বের করা হয়।

**মনে রাখবে:** `number += 1` বাদ দিলে এই loop অনন্তকাল চলতে পারে।

## 6. Dry Run of Average Calculation

Code:

```python
total = 0
count = 0

for number in range(1, 4):
    total += number
    count += 1

average = total / count
print(average)
```

### Dry Run Table

| Iteration | `number` | `total` | `count` |
|---:|---:|---:|---:|
| 1 | 1 | 1 | 1 |
| 2 | 2 | 3 | 2 |
| 3 | 3 | 6 | 3 |

Loop শেষ হওয়ার পরে:

- Total = ৬
- Count = ৩
- Average = ৬ / ৩ = ২.০

### Output

```text
2.0
```

## 7. Calculating Average of User-Entered Numbers

ধরা যাক, ব্যবহারকারী প্রথমে জানাবেন কতটি সংখ্যা দেবেন। এরপর সেই সংখ্যাগুলোর average বের করতে হবে।

### Code

```python
n = int(input("How many numbers? "))

total = 0

for i in range(n):
    number = float(input("Enter a number: "))
    total += number

if n > 0:
    average = total / n
    print("Average:", average)
else:
    print("No numbers available")
```

### Sample Input and Output

```text
How many numbers? 3
Enter a number: 10
Enter a number: 20
Enter a number: 30
Average: 20.0
```

### Explanation

- `n` নির্ধারণ করে কয়টি সংখ্যা input নেওয়া হবে।
- `float()` integer এবং decimal—দুই ধরনের numeric input গ্রহণ করতে পারে।
- Loop সব সংখ্যার sum বের করে।
- `n > 0` হলে average হিসাব করা হয়।

এখানে count আগে থেকেই জানা, তাই আলাদা `count` variable প্রয়োজন হয়নি।

## 8. Calculating Average of a List

একটি list-এর average বের করার জন্য list-এর সব element যোগ করে element-এর সংখ্যা দিয়ে ভাগ করতে হয়।

### Code

```python
numbers = [10, 20, 30, 40, 50]

total = 0

for number in numbers:
    total += number

if len(numbers) > 0:
    average = total / len(numbers)
    print("Average:", average)
else:
    print("List is empty")
```

### Output

```text
Average: 30.0
```

### Explanation

- Sum = ১৫০
- `len(numbers)` = ৫
- Average = ১৫০ / ৫ = ৩০.০

এখানে `len()` list-এ মোট কতটি element রয়েছে, তা বের করে।

## 9. Using `sum()` and `len()`

Python-এ list-এর average বের করার সহজ উপায় হলো `sum()` এবং `len()` ব্যবহার করা।

### Code

```python
numbers = [10, 20, 30, 40, 50]

if len(numbers) > 0:
    average = sum(numbers) / len(numbers)
    print("Average:", average)
else:
    print("List is empty")
```

### Output

```text
Average: 30.0
```

এখানে:

- `sum(numbers)` সব সংখ্যার যোগফল দেয়।
- `len(numbers)` মোট element-এর সংখ্যা দেয়।
- দুইটির ভাগফল average।

List খালি হলে `len(numbers)` শূন্য হয়। তাই division করার আগে পরীক্ষা করা হয়েছে।

## 10. Calculating Average of Even Numbers

কোনো range-এর শুধু even number-গুলোর average বের করতে হলে sum এবং count—দুটিই condition-এর ভেতরে update করতে হবে।

### Code

```python
total = 0
count = 0

for number in range(1, 11):
    if number % 2 == 0:
        total += number
        count += 1

if count > 0:
    average = total / count
    print("Average of even numbers:", average)
else:
    print("No even numbers found")
```

### Output

```text
Average of even numbers: 6.0
```

### Explanation

Even number-গুলো:

`2, 4, 6, 8, 10`

Sum:

\[
2+4+6+8+10=30
\]

Count = ৫

Average:

\[
\frac{30}{5}=6
\]

**গুরুত্বপূর্ণ:** শুধু even number-এর average চাইলে odd number-কে sum বা count—কোনোটিতেই অন্তর্ভুক্ত করা যাবে না।

## 11. Calculating Average of Odd Numbers

Odd number-এর average বের করার জন্য condition হবে `number % 2 != 0`।

### Code

```python
total = 0
count = 0

for number in range(1, 11):
    if number % 2 != 0:
        total += number
        count += 1

if count > 0:
    average = total / count
    print("Average of odd numbers:", average)
else:
    print("No odd numbers found")
```

### Output

```text
Average of odd numbers: 5.0
```

১ থেকে ১০ পর্যন্ত odd number:

`1, 3, 5, 7, 9`

Sum = ২৫ এবং count = ৫।

Average = ২৫ / ৫ = ৫.০।

## 12. Calculating Average of Positive Numbers

একটি list-এ positive, negative এবং zero থাকতে পারে। শুধু positive সংখ্যাগুলোর average বের করার উদাহরণ:

### Code

```python
numbers = [-10, 20, 30, -5, 40, 0]

total = 0
count = 0

for number in numbers:
    if number > 0:
        total += number
        count += 1

if count > 0:
    average = total / count
    print("Average of positive numbers:", average)
else:
    print("No positive numbers found")
```

### Output

```text
Average of positive numbers: 30.0
```

Positive number-গুলো হলো `20, 30, 40`।

Sum = ৯০ এবং count = ৩।

Average = ৯০ / ৩ = ৩০.০।

## 13. Calculating Student Average Marks

ধরা যাক, একজন শিক্ষার্থীর কয়েকটি পরীক্ষার marks দেওয়া আছে। সেগুলোর average বের করতে হবে।

### Code

```python
marks = [75, 80, 90, 85, 70]

total = 0

for mark in marks:
    total += mark

average = total / len(marks)

print("Total marks:", total)
print("Average marks:", average)
```

### Output

```text
Total marks: 400
Average marks: 80.0
```

এখানে পাঁচটি পরীক্ষার marks যোগ করে পাঁচ দিয়ে ভাগ করা হয়েছে।

বাস্তব program-এ list খালি হতে পারে কি না, তা বিবেচনা করে `len(marks) > 0` পরীক্ষা করা উচিত।

## 14. Understanding Division by Zero

Average বের করার সময় সবচেয়ে গুরুত্বপূর্ণ বিষয়গুলোর একটি হলো **division by zero** এড়িয়ে চলা।

### Incorrect Code

```python
total = 0
count = 0

average = total / count
```

এখানে `count` শূন্য। তাই Python `ZeroDivisionError` দেবে।

### Correct Code

```python
total = 0
count = 0

if count > 0:
    average = total / count
    print(average)
else:
    print("Cannot calculate average")
```

### Output

```text
Cannot calculate average
```

**মনে রাখবে:** কোনো value না থাকলে average সাধারণভাবে নির্ধারিত নয়। তাই count শূন্য হলে average বের করার চেষ্টা না করে উপযুক্ত message দেখাতে হবে।

## 15. Common Mistakes

### Mistake 1: Forgetting to Count the Values

ভুল:

```python
total = 0

for number in range(1, 6):
    total += number

average = total / 5
```

এই code নির্দিষ্টভাবে পাঁচটি সংখ্যার জন্য কাজ করে। কিন্তু input বা list-এর element সংখ্যা পরিবর্তিত হলে `5` ব্যবহার করা ভুল ফল দিতে পারে।

ভালো পদ্ধতি:

```python
numbers = [10, 20, 30]

if len(numbers) > 0:
    average = sum(numbers) / len(numbers)
    print(average)
```

### Mistake 2: Counting Every Value but Summing Only Some Values

যদি শুধু even number-এর average বের করতে চাও, তাহলে odd number-এর জন্য count বাড়ানো যাবে না।

ভুল:

```python
total = 0
count = 0

for number in range(1, 6):
    if number % 2 == 0:
        total += number
    count += 1
```

এখানে sum শুধু even number-এর হলেও count সব সংখ্যার জন্য বাড়ছে।

সঠিক:

```python
total = 0
count = 0

for number in range(1, 6):
    if number % 2 == 0:
        total += number
        count += 1
```

### Mistake 3: Initializing Inside the Loop

ভুল:

```python
for number in range(1, 6):
    total = 0
    total += number
```

প্রতিবার `total` শূন্য হয়ে যায়। ফলে আগের যোগফল জমা থাকে না।

সঠিক:

```python
total = 0

for number in range(1, 6):
    total += number
```

### Mistake 4: Using Integer Division Unnecessarily

```python
print(5 // 2)
```

Output:

```text
2
```

`//` floor division ব্যবহার করে। সাধারণ average বের করার জন্য `/` ব্যবহার করো, কারণ average decimal হতে পারে।

```python
print(5 / 2)
```

Output:

```text
2.5
```

### Mistake 5: Forgetting the Empty List

```python
numbers = []
```

এই list-এর average বের করতে `sum(numbers) / len(numbers)` লিখলে zero division হবে। আগে list খালি কি না পরীক্ষা করতে হবে।

## 16. Practical Program: Average Until a Sentinel Value

ব্যবহারকারী `0` দিলে input নেওয়া বন্ধ হবে। তার আগে দেওয়া সংখ্যাগুলোর average বের করতে হবে।

### Code

```python
total = 0
count = 0

while True:
    number = float(input("Enter a number (0 to stop): "))

    if number == 0:
        break

    total += number
    count += 1

if count > 0:
    average = total / count
    print("Average:", average)
else:
    print("No numbers entered")
```

### Sample Input and Output

```text
Enter a number (0 to stop): 10
Enter a number (0 to stop): 20
Enter a number (0 to stop): 30
Enter a number (0 to stop): 0
Average: 20.0
```

### Explanation

- `0` হলো sentinel value।
- Sentinel input-টি sum বা count-এর মধ্যে অন্তর্ভুক্ত হয় না।
- অন্য সংখ্যাগুলো sum ও count-এ যোগ হয়।
- Loop শেষ হওয়ার পর count শূন্যের বেশি হলে average বের হয়।

এই উদাহরণে `0`-কে stop signal হিসেবে ব্যবহার করা হয়েছে, তাই আলাদা data value হিসেবে zero যোগ করা যাবে না।

## 17. Using Python's `statistics` Module

Python-এর standard library-তে `statistics` module রয়েছে। এর `mean()` function দিয়ে arithmetic mean বা সাধারণ average বের করা যায়।

### Code

```python
from statistics import mean

numbers = [10, 20, 30, 40, 50]

print(mean(numbers))
```

### Output

```text
30
```

এটি list-এর average বের করার আরেকটি সহজ পদ্ধতি।

তবে list খালি হলে `mean()` ব্যবহার করা যাবে না; সে ক্ষেত্রে `StatisticsError` হতে পারে।

## 18. Comparing Different Methods

| Method | ব্যবহার |
|---|---|
| `for` loop | নির্দিষ্ট range বা iterable-এর average |
| `while` loop | Condition অনুযায়ী value process করা |
| `sum() / len()` | List-এর average |
| `sum / count` | User input বা filtered values-এর average |
| `statistics.mean()` | Arithmetic mean সহজে বের করা |

## 19. Practice Exercises

### Exercise 1

১ থেকে ১০ পর্যন্ত সংখ্যার average বের করো।

### Exercise 2

১ থেকে ১০০ পর্যন্ত even number-গুলোর average বের করো।

### Exercise 3

১ থেকে ৫০ পর্যন্ত odd number-গুলোর average বের করো।

### Exercise 4

নিচের list-এর average বের করো:

```python
numbers = [10, 20, 30, 40, 50]
```

### Exercise 5

ব্যবহারকারীর দেওয়া পাঁচটি সংখ্যার average বের করার program লেখো।

### Exercise 6

নিচের list থেকে শুধু positive number-গুলোর average বের করো:

```python
numbers = [-5, 10, 20, -3, 30]
```

### Exercise 7

নিচের code-এর output নির্ণয় করো:

```python
total = 0
count = 0

for number in range(2, 7, 2):
    total += number
    count += 1

print(total / count)
```

### Exercise 8

একটি empty list-এর average বের করার আগে কী পরীক্ষা করা উচিত?

### Exercise 9

`while` loop ব্যবহার করে ১ থেকে ৫ পর্যন্ত সংখ্যার average বের করো।

### Exercise 10

`statistics.mean()` ব্যবহার করে `[5, 10, 15, 20]`-এর average বের করো।

## 20. Practice Answer Key

### Answer 1

```python
total = 0
count = 0

for number in range(1, 11):
    total += number
    count += 1

print(total / count)
```

Output: `5.5`

### Answer 2

```python
total = 0
count = 0

for number in range(2, 101, 2):
    total += number
    count += 1

print(total / count)
```

Output: `51.0`

### Answer 3

```python
total = 0
count = 0

for number in range(1, 51, 2):
    total += number
    count += 1

print(total / count)
```

Output: `25.0`

### Answer 4

```python
numbers = [10, 20, 30, 40, 50]

if len(numbers) > 0:
    print(sum(numbers) / len(numbers))
else:
    print("Empty list")
```

Output: `30.0`

### Answer 5

```python
total = 0

for i in range(5):
    number = float(input("Enter a number: "))
    total += number

average = total / 5
print("Average:", average)
```

### Answer 6

```python
numbers = [-5, 10, 20, -3, 30]

total = 0
count = 0

for number in numbers:
    if number > 0:
        total += number
        count += 1

if count > 0:
    print(total / count)
else:
    print("No positive numbers")
```

Output: `20.0`

### Answer 7

Output:

```text
4.0
```

কারণ, যোগ করা সংখ্যাগুলো হলো `2, 4, 6`। Sum = ১২ এবং count = ৩। Average = ১২ / ৩ = ৪.০।

### Answer 8

```python
if len(numbers) > 0:
    average = sum(numbers) / len(numbers)
else:
    print("Cannot calculate average")
```

### Answer 9

```python
number = 1
total = 0
count = 0

while number <= 5:
    total += number
    count += 1
    number += 1

if count > 0:
    print(total / count)
```

Output: `3.0`

### Answer 10

```python
from statistics import mean

numbers = [5, 10, 15, 20]

print(mean(numbers))
```

Output: `12.5`

## 21. Chapter Summary

- Average বের করার formula হলো `sum / count`।
- Sum বের করতে accumulator এবং count বের করতে counter ব্যবহার করা যায়।
- `for` ও `while` loop দিয়ে average হিসাব করা যায়।
- List-এর average বের করতে `sum()` এবং `len()` ব্যবহার করা যায়।
- নির্দিষ্ট condition অনুযায়ী average বের করতে sum ও count—দুটিই একই condition-এর ভেতরে update করতে হয়।
- Count শূন্য হলে division by zero এড়াতে হবে।
- `/` সাধারণ division করে; `//` floor division করে।
- `statistics.mean()` arithmetic mean বের করার একটি built-in library function।

## 22. Completion Checklist

- [ ] Average-এর formula বুঝি।
- [ ] Sum ও count দিয়ে average বের করতে পারি।
- [ ] `for` loop দিয়ে average বের করতে পারি।
- [ ] `while` loop দিয়ে average বের করতে পারি।
- [ ] User input-এর average বের করতে পারি।
- [ ] List-এর average বের করতে পারি।
- [ ] Even, odd ও positive number-এর average বের করতে পারি।
- [ ] Empty list ও zero count সামলাতে পারি।
- [ ] `sum()`, `len()` ও `statistics.mean()` ব্যবহার করতে পারি।

**Next Topic:** `51_Finding_Maximum_and_Minimum_Values.md`