# 59. Counting Digits in a Number

## 1. Introduction

Counting Digits in a Number মানে কোনো সংখ্যায় মোট কতটি digit আছে তা নির্ণয় করা।

উদাহরণ:

| Number | Digits | Digit Count |
|---:|---|---:|
| 7 | 7 | 1 |
| 42 | 4, 2 | 2 |
| 583 | 5, 8, 3 | 3 |
| 1234 | 1, 2, 3, 4 | 4 |
| 98765 | 9, 8, 7, 6, 5 | 5 |
| 0 | 0 | 1 |
| -456 | 4, 5, 6 | 3 |

এখানে `-456`-এর digit count হলো `3`, কারণ negative sign কোনো digit নয়।

Python-এ `while` loop এবং `//` operator ব্যবহার করে digit count করা যায়।

এই Topic-এ আমরা শিখব:

- Digit counting-এর basic logic
- `while` loop ব্যবহার
- `%` ও `//` operator-এর ভূমিকা
- Dry run table
- Zero ও negative number handle করা
- `for` loop ও string method ব্যবহার
- Common mistakes ও practice problems

## 2. Understanding the Basic Logic

ধরি, আমাদের `1234`-এ কয়টি digit আছে তা বের করতে হবে।

প্রথমে:

```python
number = 1234
count = 0
```

এখানে `count` variable মোট digit-এর সংখ্যা সংরক্ষণ করবে।

প্রতিবার:

1. `number // 10` দিয়ে শেষ digit বাদ দেব।
2. `count += 1` দিয়ে digit count এক বাড়াব।

মূল logic:

```python
while number > 0:
    number //= 10
    count += 1
```

প্রতিবার `number` ছোট হতে থাকবে:

```text
1234 → 123 → 12 → 1 → 0
```

এখানে মোট চারবার loop চলেছে। তাই digit count হলো `4`।

## 3. Counting Digits Using a `while` Loop

### Code

```python
number = 1234
count = 0

while number > 0:
    number //= 10
    count += 1

print("Number of digits:", count)
```

### Output

```text
Number of digits: 4
```

### Explanation

- `number = 1234` হলো original number।
- `count = 0` দিয়ে counting শুরু হয়।
- `while number > 0` condition সত্য থাকা পর্যন্ত loop চলে।
- `number //= 10` শেষ digit বাদ দেয়।
- `count += 1` একটি digit process করার জন্য count বাড়ায়।
- `number` শূন্য হলে loop শেষ হয়।

**মনে রাখবে:** এই basic code positive integer-এর জন্য লেখা। `0` ও negative number-এর জন্য অতিরিক্ত handling দরকার।

## 4. Dry Run of Digit Counting

Code:

```python
number = 1234
count = 0

while number > 0:
    number //= 10
    count += 1

print(count)
```

### Dry Run Table

| Iteration | Original `number` | Updated `number` | Updated `count` |
|---:|---:|---:|---:|
| 1 | 1234 | 123 | 1 |
| 2 | 123 | 12 | 2 |
| 3 | 12 | 1 | 3 |
| 4 | 1 | 0 | 4 |

### Final Output

```text
4
```

Original number থেকে প্রতিবার একটি digit বাদ গেছে। চারবার digit বাদ দেওয়ার পর `count` হয়েছে `4`।

## 5. Counting Digits of a Number Using `%` and `//`

Digit count করার জন্য শুধু `//` ব্যবহার করলেই চলে। তবে `%` ব্যবহার করেও প্রতিটি digit বের করা যায়।

### Code

```python
number = 583
count = 0

while number > 0:
    digit = number % 10
    print(digit)

    number //= 10
    count += 1

print("Total digits:", count)
```

### Output

```text
3
8
5
Total digits: 3
```

### Explanation

- `number % 10` শেষ digit বের করে।
- `number //= 10` শেষ digit বাদ দেয়।
- `count += 1` digit count বাড়ায়।

এখানে digit-গুলো উল্টো দিক থেকে বের হয়েছে: `3`, `8`, `5`। কিন্তু মোট digit-এর সংখ্যা `3`।

## 6. Counting Digits with User Input

এবার user-এর কাছ থেকে একটি integer নিয়ে digit count করি।

### Code

```python
number = int(input("Enter an integer: "))
number = abs(number)

count = 0

if number == 0:
    count = 1
else:
    while number > 0:
        number //= 10
        count += 1

print("Number of digits:", count)
```

### Sample Input and Output 1

```text
Enter an integer: 56789
Number of digits: 5
```

### Sample Input and Output 2

```text
Enter an integer: -456
Number of digits: 3
```

### Sample Input and Output 3

```text
Enter an integer: 0
Number of digits: 1
```

### Explanation

- `abs(number)` negative sign সরিয়ে absolute value নেয়।
- Number `0` হলে digit count সরাসরি `1` হয়।
- অন্যথায় `while` loop দিয়ে digit count করা হয়।

এই code-এ ধরে নেওয়া হয়েছে user valid integer দেবেন। Text বা decimal input দিলে `int()` থেকে `ValueError` হতে পারে।

## 7. Why Does Zero Have One Digit?

এটি একটি গুরুত্বপূর্ণ বিষয়।

আগের basic code:

```python
number = 0
count = 0

while number > 0:
    number //= 10
    count += 1

print(count)
```

Output:

```text
0
```

এটি digit count হিসেবে ভুল, কারণ `0`-এর একটি digit আছে।

সমস্যা হলো `number > 0` condition শুরুতেই False। তাই loop একবারও চলে না।

### Correct Solution

```python
number = 0
count = 1 if number == 0 else 0

while number > 0:
    number //= 10
    count += 1

print(count)
```

Output:

```text
1
```

এখানে zero-এর জন্য `count = 1` করা হয়েছে। অন্যদিকে positive number-এর ক্ষেত্রে `count = 0` দিয়ে loop শুরু হবে।

## 8. Counting Digits of Negative Numbers

Negative number-এর digit count করার সময় negative sign গণনা করা হয় না।

যেমন:

```text
-12345
```

এখানে:

- Sign: `-`
- Digits: `1`, `2`, `3`, `4`, `5`
- Digit count: `5`

### Code

```python
number = -12345
number = abs(number)

count = 0

if number == 0:
    count = 1
else:
    while number > 0:
        number //= 10
        count += 1

print("Number of digits:", count)
```

### Output

```text
Number of digits: 5
```

`abs()` ব্যবহারের ফলে `-12345` হয়ে যায় `12345`। তারপর সাধারণ digit-counting logic কাজ করে।

## 9. Counting Digits Using a `for` Loop

`for` loop এবং string conversion দিয়েও digit count করা যায়।

### Code

```python
number = -12345

digit_count = len(str(abs(number)))

print("Number of digits:", digit_count)
```

### Output

```text
Number of digits: 5
```

### Explanation

- `abs(number)` negative sign বাদ দিয়ে absolute value নেয়।
- `str()` সংখ্যাটিকে string-এ রূপান্তর করে।
- `len()` string-এর character সংখ্যা গণনা করে।

উদাহরণ:

```python
print(str(12345))
print(len(str(12345)))
```

Output:

```text
12345
5
```

এটি সবচেয়ে সহজ পদ্ধতিগুলোর একটি। তবে loop-এর logic শেখার জন্য `while` পদ্ধতিটি গুরুত্বপূর্ণ।

## 10. Counting Digits Using a `for` Loop and String Iteration

String-এর প্রতিটি character-এর ওপর `for` loop চালিয়েও digit count করা যায়।

### Code

```python
number = -5832
text = str(abs(number))

count = 0

for digit in text:
    count += 1

print("Number of digits:", count)
```

### Output

```text
Number of digits: 4
```

এখানে `text` হলো `"5832"`। Loop চারটি character-এর প্রতিটির জন্য `count` এক বাড়ায়।

এই পদ্ধতিতে `len()` ব্যবহার করা হয়নি; বরং loop-এর মাধ্যমে সরাসরি counting করা হয়েছে।

## 11. Counting Digits and Finding Sum Together

একই loop ব্যবহার করে digit count ও digit sum একসঙ্গে বের করা যায়।

### Code

```python
number = 12345
count = 0
total = 0

while number > 0:
    digit = number % 10

    count += 1
    total += digit

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

প্রতিটি iteration-এ:

- `number % 10` শেষ digit বের করে।
- `count += 1` digit count বাড়ায়।
- `total += digit` digit-টি যোগ করে।
- `number //= 10` শেষ digit বাদ দেয়।

এইভাবে একটি loop-এ দুটি result পাওয়া যায়।

**Note:** এই code-এ `number = 0` হলে count `0` দেখাবে। Zero-এর জন্য digit count `1` করতে চাইলে আগের special-case logic যোগ করতে হবে।

## 12. Counting Digits Using a Function

একই কাজ বারবার করতে হলে function তৈরি করা যায়।

### Code

```python
def count_digits(number):
    number = abs(number)

    if number == 0:
        return 1

    count = 0

    while number > 0:
        number //= 10
        count += 1

    return count


print(count_digits(12345))
print(count_digits(-456))
print(count_digits(0))
```

### Output

```text
5
3
1
```

### Explanation

- `def count_digits(number)` function তৈরি করে।
- `abs(number)` negative sign বাদ দেয়।
- Zero হলে function সরাসরি `1` return করে।
- অন্যথায় loop দিয়ে digit count হয়।
- `return count` result ফেরত দেয়।

`return` ব্যবহার করায় function-এর result অন্য calculation-এও ব্যবহার করা যায়।

উদাহরণ:

```python
result = count_digits(12345)
print(result * 2)
```

Output:

```text
10
```

## 13. Counting Digits Without Modifying the Original Number

`while` loop-এ original number পরিবর্তিত হয়ে যায়। Original value প্রয়োজন হলে একটি temporary variable ব্যবহার করো।

### Code

```python
number = 12345
temp = abs(number)
count = 0

if temp == 0:
    count = 1
else:
    while temp > 0:
        temp //= 10
        count += 1

print("Original number:", number)
print("Number of digits:", count)
```

### Output

```text
Original number: 12345
Number of digits: 5
```

এখানে `temp` পরিবর্তিত হয়েছে, কিন্তু `number` আগের মতো `12345` আছে।

এটি ভালো practice, যখন একই original number দিয়ে পরে অন্য calculation করতে হবে।

## 14. Common Mistakes

### Mistake 1: Forgetting the Special Case for Zero

ভুল:

```python
number = 0
count = 0

while number > 0:
    number //= 10
    count += 1
```

এখানে `count` হবে `0`, যা digit count হিসেবে ভুল।

সঠিকভাবে zero-এর জন্য `count = 1` করতে হবে।

### Mistake 2: Counting the Negative Sign

`len(str(-123))` করলে `4` পাওয়া যায়, কারণ string-এ `-`-ও একটি character।

যদি শুধু digit count করতে চাও:

```python
len(str(abs(-123)))
```

Output:

```text
3
```

### Mistake 3: Forgetting to Update the Number

ভুল:

```python
while number > 0:
    count += 1
```

`number` পরিবর্তিত হচ্ছে না। তাই positive input-এর ক্ষেত্রে loop অনন্তকাল চলবে।

সঠিক:

```python
number //= 10
```

### Mistake 4: Initializing `count` Incorrectly

Positive number-এর জন্য:

```python
count = 0
```

দিয়ে শুরু করতে হবে, তারপর প্রতিটি digit-এর জন্য এক বাড়াতে হবে।

তবে `0`-এর জন্য আলাদা handling প্রয়োজন।

### Mistake 5: Modifying the Original Number Unintentionally

যদি original number পরে প্রয়োজন হয়, সরাসরি সেটিকে পরিবর্তন না করে:

```python
temp = abs(number)
```

ব্যবহার করো।

### Mistake 6: Confusing Digits with Characters

String-এর ক্ষেত্রে `len()` সব character গণনা করে, শুধু digit নয়।

উদাহরণ:

```python
text = "-123"
print(len(text))
```

Output:

```text
4
```

কিন্তু সংখ্যাটির digit count `3`।

## 15. Practice Exercises

### Exercise 1

`1234`-এ মোট কয়টি digit আছে, তা `while` loop দিয়ে বের করো।

### Exercise 2

User-এর কাছ থেকে একটি integer নিয়ে digit count করো। Negative number ও zero সঠিকভাবে handle করতে হবে।

### Exercise 3

নিচের code-এর output নির্ণয় করো:

```python
number = 56789
count = 0

while number > 0:
    number //= 10
    count += 1

print(count)
```

### Exercise 4

`-9876`-এর digit count বের করো।

### Exercise 5

`for` loop ব্যবহার করে `123456`-এর digit count বের করো।

### Exercise 6

নিচের code-এ ভুলটি খুঁজে বের করো:

```python
number = 0
count = 0

while number > 0:
    number //= 10
    count += 1

print(count)
```

### Exercise 7

`count_digits(number)` নামে একটি function লেখো, যা integer-এর digit count return করবে।

### Exercise 8

একটি loop ব্যবহার করে `9876`-এর digit count ও digit sum একসঙ্গে বের করো।

### Exercise 9

কেন `len(str(-123))` শুধু digit count বের করার জন্য সরাসরি ব্যবহার করা উচিত নয়?

### Exercise 10

Original number পরিবর্তন না করে `1234567`-এর digit count বের করো।

## 16. Practice Answer Key

### Answer 1

```python
number = 1234
count = 0

while number > 0:
    number //= 10
    count += 1

print(count)
```

Output:

```text
4
```

### Answer 2

```python
number = int(input("Enter an integer: "))
temp = abs(number)

if temp == 0:
    count = 1
else:
    count = 0

    while temp > 0:
        temp //= 10
        count += 1

print("Number of digits:", count)
```

### Answer 3

Output:

```text
5
```

### Answer 4

```python
number = -9876
number = abs(number)

count = 0

while number > 0:
    number //= 10
    count += 1

print(count)
```

Output:

```text
4
```

### Answer 5

```python
number = 123456
count = 0

for digit in str(number):
    count += 1

print(count)
```

Output:

```text
6
```

### Answer 6

সমস্যা হলো `number = 0` হওয়ায় `number > 0` condition শুরুতেই False। তাই loop চলে না এবং `count = 0` থাকে।

সঠিক output হওয়া উচিত `1`।

### Answer 7

```python
def count_digits(number):
    number = abs(number)

    if number == 0:
        return 1

    count = 0

    while number > 0:
        number //= 10
        count += 1

    return count


print(count_digits(1234))
```

Output:

```text
4
```

### Answer 8

```python
number = 9876
count = 0
total = 0

while number > 0:
    digit = number % 10
    count += 1
    total += digit
    number //= 10

print("Count:", count)
print("Sum:", total)
```

Output:

```text
Count: 4
Sum: 30
```

### Answer 9

কারণ `str(-123)` হলো `"-123"`। এতে negative sign-সহ মোট চারটি character আছে। শুধু digit গণনা করতে `abs()` ব্যবহার করে sign বাদ দিতে হবে।

```python
print(len(str(abs(-123))))
```

Output:

```text
3
```

### Answer 10

```python
number = 1234567
temp = number
count = 0

while temp > 0:
    temp //= 10
    count += 1

print("Original number:", number)
print("Digit count:", count)
```

Output:

```text
Original number: 1234567
Digit count: 7
```

## 17. Chapter Summary

- Digit counting মানে সংখ্যায় মোট কতটি digit আছে তা নির্ণয় করা।
- `number // 10` দিয়ে positive integer-এর শেষ digit বাদ দেওয়া যায়।
- প্রতিটি iteration-এ `count += 1` করলে digit count বাড়ে।
- `0`-এর digit count `1`।
- Negative sign digit নয়; negative integer-এর ক্ষেত্রে `abs()` ব্যবহার করা যায়।
- `len(str(abs(number)))` দিয়ে সহজে digit count করা যায়।
- `for` ও `while`—দুই loop দিয়েই digit count করা সম্ভব।
- Function তৈরি করে digit-counting logic পুনরায় ব্যবহার করা যায়।
- Original number সংরক্ষণ করতে temporary variable ব্যবহার করা যায়।
- একই loop-এ digit count ও digit sum বের করা যায়।

## 18. Completion Checklist

- [ ] `while` loop দিয়ে digit count করতে পারি।
- [ ] `%` ও `//` operator-এর ভূমিকা বুঝি।
- [ ] Dry run table তৈরি করতে পারি।
- [ ] Zero-এর special case handle করতে পারি।
- [ ] Negative number-এর digit count করতে পারি।
- [ ] `for` loop ও string conversion ব্যবহার করতে পারি।
- [ ] Function তৈরি করে digit count return করতে পারি।
- [ ] Original number পরিবর্তন না করে calculation করতে পারি।
- [ ] Digit count ও digit sum একসঙ্গে বের করতে পারি।
- [ ] Common mistakes শনাক্ত করতে পারি।

**Next Topic:** `60_Palindrome_Number_Checking.md`