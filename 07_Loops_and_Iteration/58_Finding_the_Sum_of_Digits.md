# 58. Finding the Sum of Digits

## 1. Introduction

Finding the Sum of Digits মানে কোনো সংখ্যার প্রতিটি digit আলাদা করে বের করে সেগুলো যোগ করা।

উদাহরণ:

| Number | Calculation | Sum |
|---:|---|---:|
| 123 | 1 + 2 + 3 | 6 |
| 456 | 4 + 5 + 6 | 15 |
| 1234 | 1 + 2 + 3 + 4 | 10 |
| 908 | 9 + 0 + 8 | 17 |
| 555 | 5 + 5 + 5 | 15 |

Python-এ `while` loop দিয়ে digit একে একে বের করে যোগ করা যায়।

এই Topic-এ আমরা শিখব:

- `%` ও `//` operator-এর ব্যবহার
- `while` loop দিয়ে digit sum
- Dry run table
- User input ব্যবহার
- Zero ও negative number handle করা
- `for` loop এবং string method দিয়ে digit sum
- Common mistakes ও practice problems

## 2. Understanding `%` and `//`

Digit sum বের করার জন্য দুটি operator খুব গুরুত্বপূর্ণ।

### Modulus Operator (`%`)

`% 10` দিয়ে positive integer-এর শেষ digit বের করা যায়।

```python
print(1234 % 10)
print(567 % 10)
print(908 % 10)
```

Output:

```text
4
7
8
```

### Floor Division Operator (`//`)

`// 10` দিয়ে positive integer-এর শেষ digit বাদ দেওয়া যায়।

```python
print(1234 // 10)
print(567 // 10)
print(908 // 10)
```

Output:

```text
123
56
90
```

### মনে রাখার নিয়ম

| Operation | কাজ | Example |
|---|---|---|
| `number % 10` | শেষ digit বের করে | `1234 % 10 = 4` |
| `number // 10` | শেষ digit বাদ দেয় | `1234 // 10 = 123` |

এই দুটি operation ব্যবহার করে একটি সংখ্যার সব digit process করা যায়।

## 3. Basic Logic of Digit Sum

ধরি, আমাদের `1234`-এর digit sum বের করতে হবে।

প্রথমে:

```python
number = 1234
total = 0
```

এখানে `total` variable-এ digit-গুলোর যোগফল জমা হবে।

প্রতিবার তিনটি কাজ করব:

1. `number % 10` দিয়ে শেষ digit বের করব।
2. `total += digit` দিয়ে digit-টি যোগ করব।
3. `number //= 10` দিয়ে শেষ digit বাদ দেব।

মূল formula:

```python
digit = number % 10
total += digit
number //= 10
```

এই তিনটি statement loop-এর মধ্যে বারবার চলবে।

## 4. Finding Sum of Digits Using a `while` Loop

### Code

```python
number = 1234
total = 0

while number > 0:
    digit = number % 10
    total += digit
    number //= 10

print("Sum of digits:", total)
```

### Output

```text
Sum of digits: 10
```

### Explanation

- `number = 1234` হলো original number।
- `total = 0` দিয়ে sum শুরু হয়।
- `number % 10` শেষ digit বের করে।
- `total += digit` সেই digit যোগ করে।
- `number //= 10` শেষ digit বাদ দেয়।
- `number` শূন্য হলে loop বন্ধ হয়।

হিসাবটি হলো:

```text
4 + 3 + 2 + 1 = 10
```

Digit উল্টো দিক থেকে process করা হলেও যোগফল একই থাকে।

## 5. Dry Run of Digit Sum

Code:

```python
number = 1234
total = 0

while number > 0:
    digit = number % 10
    total += digit
    number //= 10

print(total)
```

### Dry Run Table

| Iteration | Original `number` | `digit = number % 10` | New `total` | Updated `number` |
|---:|---:|---:|---:|---:|
| 1 | 1234 | 4 | 4 | 123 |
| 2 | 123 | 3 | 7 | 12 |
| 3 | 12 | 2 | 9 | 1 |
| 4 | 1 | 1 | 10 | 0 |

### Final Output

```text
10
```

প্রতিটি iteration-এ একটি digit বের করে `total`-এর সঙ্গে যোগ করা হয়েছে।

## 6. Finding Sum of Digits with User Input

এবার user-এর কাছ থেকে একটি non-negative integer নিয়ে digit sum বের করি।

### Code

```python
number = int(input("Enter a non-negative integer: "))
total = 0

if number < 0:
    print("Please enter a non-negative integer.")
else:
    while number > 0:
        digit = number % 10
        total += digit
        number //= 10

    print("Sum of digits:", total)
```

### Sample Input and Output 1

```text
Enter a non-negative integer: 567
Sum of digits: 18
```

কারণ:

```text
5 + 6 + 7 = 18
```

### Sample Input and Output 2

```text
Enter a non-negative integer: 908
Sum of digits: 17
```

কারণ:

```text
9 + 0 + 8 = 17
```

এই code-এ ধরে নেওয়া হয়েছে user valid integer দেবেন। অক্ষর বা decimal input দিলে `int()` থেকে `ValueError` হতে পারে।

## 7. Finding Sum of Digits of Zero

যদি input `0` হয়, তাহলে:

```python
number = 0
total = 0

while number > 0:
    digit = number % 10
    total += digit
    number //= 10

print(total)
```

Output:

```text
0
```

এখানে loop একবারও চলে না, কারণ `number > 0` condition শুরুতেই False। তবে `total`-এর initial value `0` হওয়ায় সঠিক result পাওয়া যায়।

## 8. Finding Sum of Digits of a Negative Number

Negative number-এর digit sum বের করতে চাইলে প্রথমে `abs()` ব্যবহার করে absolute value নেওয়া যায়।

উদাহরণ: `-1234`-এর digit sum হবে `1 + 2 + 3 + 4 = 10`।

### Code

```python
number = int(input("Enter an integer: "))
number = abs(number)

total = 0

while number > 0:
    digit = number % 10
    total += digit
    number //= 10

print("Sum of digits:", total)
```

### Sample Output

```text
Enter an integer: -1234
Sum of digits: 10
```

এখানে negative sign-টিকে digit হিসেবে ধরা হয়নি। শুধু সংখ্যাটির digit-গুলোর যোগফল বের করা হয়েছে।

## 9. Finding Sum of Digits Using a `for` Loop

`for` loop এবং string conversion ব্যবহার করেও digit sum বের করা যায়।

### Code

```python
number = 1234
total = 0

for digit in str(abs(number)):
    total += int(digit)

print("Sum of digits:", total)
```

### Output

```text
Sum of digits: 10
```

### Explanation

- `abs(number)` negative হলে তার absolute value নেয়।
- `str()` সংখ্যাটিকে string-এ রূপান্তর করে।
- `for` loop প্রতিটি character-এর ওপর চলে।
- `int(digit)` character-টিকে integer-এ রূপান্তর করে।
- `total += int(digit)` digit যোগ করে।

উদাহরণস্বরূপ, `str(1234)` হলো `"1234"`। Loop একে একে `"1"`, `"2"`, `"3"` ও `"4"` পায়।

এই পদ্ধতিতে arithmetic digit extraction-এর পরিবর্তে string iteration ব্যবহার করা হয়েছে।

## 10. Finding Digit Sum Using a Function

Digit sum-এর logic বারবার ব্যবহার করতে চাইলে একটি function তৈরি করা যায়।

### Code

```python
def sum_of_digits(number):
    number = abs(number)
    total = 0

    while number > 0:
        digit = number % 10
        total += digit
        number //= 10

    return total


print(sum_of_digits(1234))
print(sum_of_digits(567))
print(sum_of_digits(-908))
```

### Output

```text
10
18
17
```

### Explanation

- `def sum_of_digits(number)` function তৈরি করে।
- `abs(number)` negative input-কে non-negative করে।
- `total`-এ digit sum জমা হয়।
- `return total` ফলাফল ফেরত দেয়।

Function-এর ভেতরে `print()` না করে `return` ব্যবহার করায় result অন্য calculation-এও ব্যবহার করা যায়।

উদাহরণ:

```python
result = sum_of_digits(1234)
print(result * 2)
```

Output:

```text
20
```

## 11. Counting Digits and Finding Their Sum Together

একই loop ব্যবহার করে digit-এর সংখ্যা এবং digit sum—দুটিই বের করা যায়।

### Code

```python
number = 12345
total = 0
count = 0

while number > 0:
    digit = number % 10
    total += digit
    count += 1
    number //= 10

print("Digit count:", count)
print("Sum of digits:", total)
```

### Output

```text
Digit count: 5
Sum of digits: 15
```

### Explanation

প্রতিবার loop চলার সময়:

- একটি digit বের হয়।
- `total`-এ digit যোগ হয়।
- `count` এক বাড়ে।
- Original number থেকে শেষ digit বাদ যায়।

তাই একই loop দিয়ে দুটি result পাওয়া যায়।

**Note:** এই code `0`-এর জন্য digit count `0` দেখাবে, যদিও decimal representation-এ `0`-এর একটি digit আছে। Zero-সহ সঠিক digit count প্রয়োজন হলে আলাদা condition যোগ করতে হবে।

## 12. Common Mistakes

### Mistake 1: Initializing `total` with the Original Number

ভুল:

```python
number = 123
total = number
```

এতে original number-টি sum-এর মধ্যে আগেই যোগ হয়ে যায়।

সঠিক:

```python
total = 0
```

### Mistake 2: Forgetting to Update `number`

ভুল:

```python
digit = number % 10
total += digit
```

যদি `number` পরিবর্তন না হয়, তাহলে একই digit বারবার process হবে এবং loop শেষ হবে না।

সঠিক:

```python
number //= 10
```

### Mistake 3: Using `/` Instead of `//`

ভুল:

```python
number = number / 10
```

`/` float result দেয়। Digit extraction-এর এই পদ্ধতিতে `//` ব্যবহার করা উচিত।

সঠিক:

```python
number = number // 10
```

### Mistake 4: Forgetting to Add the Digit

ভুল:

```python
digit = number % 10
number //= 10
```

এখানে digit বের করা হয়েছে, কিন্তু `total`-এ যোগ করা হয়নি।

সঠিক:

```python
total += digit
```

### Mistake 5: Incorrect Handling of Negative Numbers

শুধু `while number > 0` ব্যবহার করলে negative input-এর ক্ষেত্রে loop চলবে না।

Negative number-এর digit sum চাইলে:

```python
number = abs(number)
```

ব্যবহার করা যায়।

### Mistake 6: Forgetting the Initial Value for Zero

`total = 0` দিয়ে শুরু করতে হবে। তাহলে input `0` হলেও result সঠিকভাবে `0` হবে।

## 13. Practice Exercises

### Exercise 1

`1234`-এর digit sum বের করার জন্য `while` loop লেখো।

### Exercise 2

User-এর কাছ থেকে একটি non-negative integer নিয়ে digit sum বের করো।

### Exercise 3

`9087`-এর digit sum কত?

### Exercise 4

নিচের code-এর output নির্ণয় করো:

```python
number = 456
total = 0

while number > 0:
    digit = number % 10
    total += digit
    number //= 10

print(total)
```

### Exercise 5

`for` loop এবং string conversion ব্যবহার করে `789`-এর digit sum বের করো।

### Exercise 6

নিচের code-এ ভুলটি খুঁজে বের করো:

```python
number = 123
total = 0

while number > 0:
    digit = number % 10
    total += digit

print(total)
```

### Exercise 7

`0`-এর digit sum কত? ব্যাখ্যা করো।

### Exercise 8

`-456`-এর digit sum বের করো।

### Exercise 9

একটি loop ব্যবহার করে `12345`-এর digit count ও digit sum একসঙ্গে বের করো।

### Exercise 10

একটি `sum_of_digits(number)` function লেখো, যা integer-এর digit sum return করবে।

## 14. Practice Answer Key

### Answer 1

```python
number = 1234
total = 0

while number > 0:
    digit = number % 10
    total += digit
    number //= 10

print(total)
```

Output:

```text
10
```

### Answer 2

```python
number = int(input("Enter a non-negative integer: "))
total = 0

if number < 0:
    print("Invalid input")
else:
    while number > 0:
        total += number % 10
        number //= 10

    print("Sum of digits:", total)
```

### Answer 3

```text
9 + 0 + 8 + 7 = 24
```

Answer: `24`

### Answer 4

Output:

```text
15
```

কারণ `4 + 5 + 6 = 15`।

### Answer 5

```python
number = 789
total = 0

for digit in str(number):
    total += int(digit)

print(total)
```

Output:

```text
24
```

### Answer 6

সমস্যা হলো `number`-এর শেষ digit বাদ দেওয়া হয়নি। ফলে `number` একই থাকে এবং loop অনন্তকাল চলতে থাকে।

সঠিক code:

```python
number = 123
total = 0

while number > 0:
    digit = number % 10
    total += digit
    number //= 10

print(total)
```

Output:

```text
6
```

### Answer 7

Digit sum হলো `0`। Loop একবারও চলে না, তাই `total`-এর initial value `0`-ই output হয়।

### Answer 8

```python
number = abs(-456)
total = 0

while number > 0:
    total += number % 10
    number //= 10

print(total)
```

Output:

```text
15
```

### Answer 9

```python
number = 12345
total = 0
count = 0

while number > 0:
    digit = number % 10
    total += digit
    count += 1
    number //= 10

print("Count:", count)
print("Sum:", total)
```

Output:

```text
Count: 5
Sum: 15
```

### Answer 10

```python
def sum_of_digits(number):
    number = abs(number)
    total = 0

    while number > 0:
        total += number % 10
        number //= 10

    return total


print(sum_of_digits(1234))
```

Output:

```text
10
```

## 15. Chapter Summary

- Digit sum মানে সংখ্যার প্রতিটি digit যোগ করা।
- `% 10` দিয়ে শেষ digit বের করা যায়।
- `// 10` দিয়ে শেষ digit বাদ দেওয়া যায়।
- `total = 0` দিয়ে sum শুরু করতে হয়।
- `total += digit` দিয়ে প্রতিটি digit যোগ হয়।
- `while` loop দিয়ে digit একে একে process করা যায়।
- String iteration ও `for` loop দিয়েও digit sum করা যায়।
- Function ব্যবহার করে logic পুনরায় ব্যবহার করা যায়।
- একটি loop দিয়ে digit count ও sum একসঙ্গে বের করা যায়।
- Negative input-এর জন্য `abs()` ব্যবহার করা যায়।

## 16. Completion Checklist

- [ ] `%` ও `//` operator-এর ব্যবহার বুঝি।
- [ ] `while` loop দিয়ে digit sum বের করতে পারি।
- [ ] Dry run table তৈরি করতে পারি।
- [ ] User input ব্যবহার করতে পারি।
- [ ] Zero ও negative input handle করতে পারি।
- [ ] `for` loop দিয়ে digit sum বের করতে পারি।
- [ ] Function তৈরি করে digit sum return করতে পারি।
- [ ] একই loop-এ digit count ও sum বের করতে পারি।
- [ ] Common mistakes শনাক্ত করতে পারি।

**Next Topic:** `59_Counting_Digits_in_a_Number.md`