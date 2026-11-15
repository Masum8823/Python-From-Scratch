# 49. Finding the Sum of Numbers

## 1. Introduction

Programming-এ অনেক সময় একাধিক সংখ্যার যোগফল বের করতে হয়। যেমন:

- ১ থেকে ১০০ পর্যন্ত সংখ্যার যোগফল।
- Even বা odd number-গুলোর যোগফল।
- User-এর দেওয়া সংখ্যাগুলোর যোগফল।
- একটি list-এর সব সংখ্যার যোগফল।
- নির্দিষ্ট শর্ত পূরণকারী সংখ্যার যোগফল।

Python-এ এসব problem সহজে solve করতে loop এবং accumulator ব্যবহার করা যায়।

## 2. Understanding the Sum

Sum মানে হলো একাধিক সংখ্যার যোগফল।

উদাহরণ:

\[
1+2+3+4+5=15
\]

Loop ব্যবহার করে একবারে একটি সংখ্যা `total` variable-এর সঙ্গে যোগ করা যায়।

```python
total = 0

for number in range(1, 6):
    total += number

print("Sum:", total)
```

Output:

```text
Sum: 15
```

এখানে `total` হলো accumulator। প্রতিবার loop চলার সময় এর মান update হয়।

## 3. Why Do We Initialize `total = 0`?

যোগফল বের করার আগে accumulator-কে `0` দিয়ে initialize করা হয়।

```python
total = 0
```

কারণ, ০-এর সঙ্গে কোনো সংখ্যা যোগ করলে সেই সংখ্যার মান পরিবর্তিত হয় না।

যদি accumulator initialize না করা হয়, তাহলে `total += number` লেখার সময় সাধারণত `NameError` হবে।

## 4. Finding the Sum from 1 to N

ধরা যাক, ১ থেকে \(N\) পর্যন্ত সব পূর্ণসংখ্যার যোগফল বের করতে হবে।

### Code

```python
n = int(input("Enter a positive number: "))

total = 0

for number in range(1, n + 1):
    total += number

print("Sum:", total)
```

### Sample Input and Output

```text
Enter a positive number: 5
Sum: 15
```

### Explanation

- `n`-এ ব্যবহারকারীর দেওয়া সংখ্যা রাখা হয়।
- `range(1, n + 1)` দিয়ে ১ থেকে `n` পর্যন্ত সংখ্যা পাওয়া যায়।
- প্রতিটি সংখ্যা `total`-এর সঙ্গে যোগ হয়।
- শেষে মোট যোগফল print হয়।

**মনে রাখবে:** `range()`-এর stop value অন্তর্ভুক্ত হয় না। তাই `n`-কে অন্তর্ভুক্ত করতে `n + 1` ব্যবহার করা হয়েছে।

এই উদাহরণে positive integer input দেওয়া হবে বলে ধরে নেওয়া হয়েছে।

## 5. Finding the Sum Using a `while` Loop

একই problem `while` loop দিয়েও solve করা যায়।

### Code

```python
n = int(input("Enter a positive number: "))

number = 1
total = 0

while number <= n:
    total += number
    number += 1

print("Sum:", total)
```

### Sample Input and Output

```text
Enter a positive number: 5
Sum: 15
```

### Explanation

1. `number = 1` দিয়ে শুরু হয়।
2. `number <= n` সত্য হলে loop চলে।
3. বর্তমান সংখ্যা `total`-এর সঙ্গে যোগ হয়।
4. `number += 1` দিয়ে পরবর্তী সংখ্যায় যাওয়া হয়।
5. `number > n` হলে loop শেষ হয়।

`number += 1` বাদ দিলে condition সত্য থাকা অবস্থায় loop অনন্তকাল চলতে পারে।

## 6. Dry Run of the Sum

Code:

```python
total = 0

for number in range(1, 5):
    total += number

print(total)
```

### Dry Run Table

| Iteration | `number` | Previous `total` | New `total` |
|---:|---:|---:|---:|
| 1 | 1 | 0 | 1 |
| 2 | 2 | 1 | 3 |
| 3 | 3 | 3 | 6 |
| 4 | 4 | 6 | 10 |

Output:

```text
10
```

অর্থাৎ, \(1+2+3+4=10\)।

## 7. Finding the Sum of Even Numbers

শুধু even number-গুলোর যোগফল বের করতে `if` condition ব্যবহার করা যায়।

### Code

```python
n = int(input("Enter the limit: "))

total = 0

for number in range(1, n + 1):
    if number % 2 == 0:
        total += number

print("Sum of even numbers:", total)
```

### Sample Input and Output

```text
Enter the limit: 10
Sum of even numbers: 30
```

### Explanation

১ থেকে ১০ পর্যন্ত even number হলো:

`2, 4, 6, 8, 10`

তাই:

\[
2+4+6+8+10=30
\]

`number % 2 == 0` condition শুধু even number-গুলোর জন্য সত্য হয়।

## 8. Finding the Sum of Odd Numbers

Odd number-এর যোগফল বের করার জন্য condition হবে `number % 2 != 0`।

### Code

```python
n = int(input("Enter the limit: "))

total = 0

for number in range(1, n + 1):
    if number % 2 != 0:
        total += number

print("Sum of odd numbers:", total)
```

### Sample Input and Output

```text
Enter the limit: 10
Sum of odd numbers: 25
```

১ থেকে ১০ পর্যন্ত odd number হলো:

`1, 3, 5, 7, 9`

তাই:

\[
1+3+5+7+9=25
\]

## 9. Finding the Sum of Multiples of a Number

একটি নির্দিষ্ট সংখ্যার গুণিতকগুলোর যোগফলও loop দিয়ে বের করা যায়।

### Example: Sum of Multiples of 3 up to 20

```python
total = 0

for number in range(1, 21):
    if number % 3 == 0:
        total += number

print("Sum:", total)
```

Output:

```text
Sum: 63
```

এখানে গুণিতকগুলো হলো:

`3, 6, 9, 12, 15, 18`

তাই:

\[
3+6+9+12+15+18=63
\]

## 10. Finding the Sum of Numbers Entered by the User

ধরা যাক, ব্যবহারকারী কতটি সংখ্যা দেবেন তা প্রথমে জানাবেন। এরপর সেই সংখ্যাগুলোর যোগফল বের করতে হবে।

### Code

```python
count = int(input("How many numbers? "))

total = 0

for i in range(count):
    number = int(input("Enter a number: "))
    total += number

print("Total sum:", total)
```

### Sample Input and Output

```text
How many numbers? 3
Enter a number: 10
Enter a number: 20
Enter a number: 30
Total sum: 60
```

### Explanation

- `count` নির্ধারণ করে কতবার input নেওয়া হবে।
- `range(count)` loop-কে নির্দিষ্ট সংখ্যক বার চালায়।
- প্রতিটি input `number` variable-এ রাখা হয়।
- `total += number` দিয়ে যোগফল জমা হয়।

এখানে `count` non-negative integer এবং প্রতিটি input integer হবে বলে ধরে নেওয়া হয়েছে।

## 11. Finding the Sum Until a Sentinel Value

কখনো ব্যবহারকারী আগে থেকে জানেন না কতটি সংখ্যা দেবেন। এ ক্ষেত্রে একটি sentinel value ব্যবহার করা যায়।

Sentinel value হলো এমন একটি নির্দিষ্ট value, যা input নেওয়া বন্ধ করার সংকেত দেয়।

### Code

```python
total = 0

while True:
    number = int(input("Enter a number (0 to stop): "))

    if number == 0:
        break

    total += number

print("Total sum:", total)
```

### Sample Input and Output

```text
Enter a number (0 to stop): 10
Enter a number (0 to stop): 20
Enter a number (0 to stop): 5
Enter a number (0 to stop): 0
Total sum: 35
```

### Explanation

- `while True` দিয়ে loop শুরু হয়।
- প্রতিবার একটি সংখ্যা input নেওয়া হয়।
- সংখ্যা `0` হলে `break` loop বন্ধ করে।
- অন্যথায় সংখ্যাটি `total`-এর সঙ্গে যোগ হয়।

এখানে sentinel value `0` যোগফলের অন্তর্ভুক্ত হয় না।

**সতর্কতা:** এই পদ্ধতিতে `0` একটি valid data value হলেও সেটি stop signal হিসেবে ব্যবহৃত হচ্ছে। তাই input data-তে `0`-কে আলাদা সংখ্যা হিসেবে যোগ করা যাবে না।

## 12. Finding the Sum of a List

একটি list-এর সব সংখ্যার যোগফল বের করতে `for` loop ব্যবহার করা যায়।

### Code

```python
numbers = [10, 20, 30, 40, 50]

total = 0

for number in numbers:
    total += number

print("Sum:", total)
```

### Output

```text
Sum: 150
```

### Explanation

Loop list-এর প্রতিটি element-এর মধ্য দিয়ে যায় এবং accumulator-এ যোগ করে।

এখানে:

\[
10+20+30+40+50=150
\]

## 13. Finding the Sum of Positive Numbers Only

একটি list-এ positive ও negative—দুই ধরনের সংখ্যা থাকলে শুধু positive সংখ্যাগুলোর sum বের করা যায়।

### Code

```python
numbers = [10, -5, 20, -3, 7, 0]

total = 0

for number in numbers:
    if number > 0:
        total += number

print("Sum of positive numbers:", total)
```

### Output

```text
Sum of positive numbers: 37
```

Positive number-গুলো হলো `10, 20, 7`।

তাই:

\[
10+20+7=37
\]

শূন্য এবং negative number-গুলো যোগ করা হয়নি।

## 14. Finding the Sum of Numbers Within a Range

কখনো ১ থেকে \(N\) পর্যন্ত নয়, বরং একটি নির্দিষ্ট start ও end-এর মধ্যে থাকা সংখ্যাগুলোর যোগফল বের করতে হয়।

### Code

```python
start = int(input("Enter the start: "))
end = int(input("Enter the end: "))

total = 0

for number in range(start, end + 1):
    total += number

print("Sum:", total)
```

### Sample Input and Output

```text
Enter the start: 3
Enter the end: 7
Sum: 25
```

কারণ:

\[
3+4+5+6+7=25
\]

এই উদাহরণে `start <= end` ধরে নেওয়া হয়েছে।

## 15. Using Python's Built-in `sum()` Function

Python-এ সংখ্যার iterable-এর যোগফল বের করার জন্য built-in `sum()` function রয়েছে।

### Example

```python
numbers = [10, 20, 30, 40]

print(sum(numbers))
```

Output:

```text
100
```

Range-এর যোগফলও বের করা যায়:

```python
print(sum(range(1, 6)))
```

Output:

```text
15
```

### তাহলে loop কেন শিখব?

- Loop দিয়ে sum কীভাবে কাজ করে, তা বোঝা যায়।
- Condition ব্যবহার করে নির্দিষ্ট value যোগ করা যায়।
- User input থেকে data process করা যায়।
- Programming problem-solving-এর ভিত্তি তৈরি হয়।

বাস্তব কাজে simple sum-এর জন্য `sum()` ভালো পছন্দ। কিন্তু logic শেখা বা custom condition প্রয়োগের ক্ষেত্রে loop গুরুত্বপূর্ণ।

## 16. Mathematical Formula for Sum

১ থেকে \(n\) পর্যন্ত পূর্ণসংখ্যার যোগফল বের করার একটি formula আছে:

\[
S=\frac{n(n+1)}{2}
\]

যেমন, \(n=5\) হলে:

\[
S=\frac{5(5+1)}{2}=15
\]

Python code:

```python
n = 5

total = n * (n + 1) // 2

print(total)
```

Output:

```text
15
```

এই formula শুধু ১ থেকে \(n\) পর্যন্ত ধারাবাহিক পূর্ণসংখ্যার যোগফলের জন্য প্রযোজ্য। যেকোনো list বা arbitrary input-এর sum বের করার সাধারণ বিকল্প নয়।

## 17. Comparing Different Methods

| Method | কখন ব্যবহার করবে |
|---|---|
| `for` loop | নির্দিষ্ট range বা iterable-এর sum |
| `while` loop | Condition অনুযায়ী sum |
| `if` + loop | নির্দিষ্ট condition পূরণকারী সংখ্যার sum |
| Sentinel loop | Stop value না পাওয়া পর্যন্ত input |
| `sum()` | Iterable-এর সাধারণ sum |
| Mathematical formula | ১ থেকে \(n\) পর্যন্ত ধারাবাহিক পূর্ণসংখ্যার sum |

## 18. Common Mistakes

### Mistake 1: Forgetting to Initialize `total`

ভুল:

```python
for number in range(1, 6):
    total += number
```

সঠিক:

```python
total = 0

for number in range(1, 6):
    total += number
```

### Mistake 2: Initializing `total` Inside the Loop

ভুল:

```python
for number in range(1, 6):
    total = 0
    total += number

print(total)
```

Output: `5`

প্রতিবার `total` শূন্য হয়ে যাওয়ায় আগের যোগফল হারিয়ে যায়।

### Mistake 3: Forgetting `n + 1`

```python
for number in range(1, 6):
    print(number)
```

এখানে ১ থেকে ৫ পর্যন্ত সংখ্যা পাওয়া যায়। কিন্তু `range(1, n)` ব্যবহার করলে `n` অন্তর্ভুক্ত হবে না।

### Mistake 4: Adding 1 Instead of the Number

ভুল:

```python
total = 0

for number in range(1, 6):
    total += 1
```

Output: `5`

সঠিক:

```python
total = 0

for number in range(1, 6):
    total += number
```

Output: `15`

### Mistake 5: Forgetting to Update the `while` Loop

`while` loop-এর counter update না করলে loop অনন্তকাল চলতে পারে।

### Mistake 6: Adding the Sentinel Value

Sentinel value দিয়ে input বন্ধ করলে সেটিকে যোগফলের মধ্যে অন্তর্ভুক্ত করা উচিত নয়—যদি না problem-এ অন্য কিছু বলা থাকে।

## 19. Practice Exercises

### Exercise 1

১ থেকে ৫০ পর্যন্ত সব সংখ্যার যোগফল বের করো।

### Exercise 2

১ থেকে ১০০ পর্যন্ত even number-গুলোর যোগফল বের করো।

### Exercise 3

১ থেকে ৫০ পর্যন্ত odd number-গুলোর যোগফল বের করো।

### Exercise 4

ব্যবহারকারীর দেওয়া \(n\) সংখ্যার যোগফল বের করার program লেখো।

### Exercise 5

নিচের list-এর সব সংখ্যার যোগফল বের করো:

```python
numbers = [12, 8, 15, 5, 10]
```

### Exercise 6

নিচের list-এর positive সংখ্যাগুলোর যোগফল বের করো:

```python
numbers = [-5, 10, 20, -3, 7]
```

### Exercise 7

`while` loop ব্যবহার করে ১ থেকে ১০ পর্যন্ত যোগফল বের করো।

### Exercise 8

নিচের code-এর output বের করো:

```python
total = 0

for number in range(2, 7):
    total += number

print(total)
```

### Exercise 9

`sum()` function ব্যবহার করে ১ থেকে ১০০ পর্যন্ত যোগফল বের করো।

### Exercise 10

১ থেকে \(n\) পর্যন্ত sum বের করার mathematical formula ব্যবহার করে একটি program লেখো।

## 20. Practice Answer Key

### Answer 1

```python
total = 0

for number in range(1, 51):
    total += number

print(total)
```

Output: `1275`

### Answer 2

```python
total = 0

for number in range(2, 101, 2):
    total += number

print(total)
```

Output: `2550`

### Answer 3

```python
total = 0

for number in range(1, 51, 2):
    total += number

print(total)
```

Output: `625`

### Answer 4

```python
n = int(input("How many numbers? "))
total = 0

for i in range(n):
    number = int(input("Enter a number: "))
    total += number

print("Sum:", total)
```

### Answer 5

```python
numbers = [12, 8, 15, 5, 10]
print(sum(numbers))
```

Output: `50`

### Answer 6

```python
numbers = [-5, 10, 20, -3, 7]
total = 0

for number in numbers:
    if number > 0:
        total += number

print(total)
```

Output: `37`

### Answer 7

```python
number = 1
total = 0

while number <= 10:
    total += number
    number += 1

print(total)
```

Output: `55`

### Answer 8

Output:

```text
20
```

কারণ:

\[
2+3+4+5+6=20
\]

### Answer 9

```python
print(sum(range(1, 101)))
```

Output: `5050`

### Answer 10

```python
n = int(input("Enter a positive number: "))
total = n * (n + 1) // 2

print("Sum:", total)
```

উদাহরণ: `n = 10` হলে output `55`।

## 21. Chapter Summary

- Loop এবং accumulator দিয়ে একাধিক সংখ্যার যোগফল বের করা যায়।
- `total = 0` দিয়ে sum শুরু করা হয়।
- `total += number` বর্তমান সংখ্যাকে যোগফলে যুক্ত করে।
- `range(1, n + 1)` ব্যবহার করলে ১ থেকে \(n\) পর্যন্ত সংখ্যা পাওয়া যায়।
- Condition দিয়ে even, odd বা positive সংখ্যার sum বের করা যায়।
- User input এবং sentinel value দিয়েও যোগফল বের করা যায়।
- `sum()` iterable-এর সাধারণ যোগফল বের করার সহজ built-in function।
- ১ থেকে \(n\) পর্যন্ত sum-এর formula হলো \(n(n+1)/2\)।

## 22. Completion Checklist

- [ ] `for` loop দিয়ে sum বের করতে পারি।
- [ ] `while` loop দিয়ে sum বের করতে পারি।
- [ ] Even ও odd number-এর sum বের করতে পারি।
- [ ] User input থেকে sum বের করতে পারি।
- [ ] Sentinel value ব্যবহার করে input নিতে পারি।
- [ ] List-এর sum বের করতে পারি।
- [ ] `sum()` function ব্যবহার করতে পারি।
- [ ] Mathematical formula ব্যবহার করে sum বের করতে পারি।
- [ ] Dry run করে accumulator-এর মান নির্ণয় করতে পারি।

**Next Topic:** `50_Finding_the_Average_of_Numbers.md`