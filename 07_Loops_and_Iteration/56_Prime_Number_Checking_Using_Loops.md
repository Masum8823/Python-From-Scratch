# 56. Prime Number Checking Using Loops

## 1. Introduction

Prime Number হলো এমন একটি integer, যার **ঠিক দুটি positive divisor** আছে: `1` এবং সংখ্যাটি নিজে।

উদাহরণ:

- `2` একটি prime number, কারণ এর divisor হলো `1` ও `2`।
- `3` একটি prime number, কারণ এর divisor হলো `1` ও `3`।
- `5` একটি prime number, কারণ এর divisor হলো `1` ও `5`।
- `6` prime নয়, কারণ এর divisor হলো `1`, `2`, `3` ও `6`।

Prime number-এর কিছু উদাহরণ:

```text
2, 3, 5, 7, 11, 13, 17, 19, 23, 29
```

**গুরুত্বপূর্ণ:** `1` prime number নয়, কারণ এর মাত্র একটি positive divisor আছে। `0` এবং negative integer-ও prime number নয়।

এই Topic-এ আমরা শিখব:

- Prime number ও divisor-এর ধারণা
- `for` loop দিয়ে prime check
- `while` loop দিয়ে prime check
- Divisor count করার পদ্ধতি
- Efficient prime checking
- একটি range-এর মধ্যে prime number বের করা
- Common mistakes ও practice problems

## 2. Understanding Divisors

কোনো integer `n`-কে একটি positive integer `d` দিয়ে ভাগ করলে ভাগশেষ শূন্য হলে, `d` হলো `n`-এর divisor।

Python-এ modulus operator `%` ব্যবহার করে ভাগশেষ পরীক্ষা করা যায়।

```python
print(10 % 2)
print(10 % 3)
```

Output:

```text
0
1
```

এখানে:

- `10 % 2 == 0`, তাই `2` হলো `10`-এর divisor।
- `10 % 3 != 0`, তাই `3` হলো `10`-এর divisor নয়।

Prime checking-এর জন্য আমরা পরীক্ষা করব কোনো সংখ্যা `2` থেকে শুরু করে অন্য কোনো সংখ্যা দিয়ে নিঃশেষে বিভাজ্য কি না।

## 3. Prime Number Checking Logic

ধরি, `number = 7`।

আমরা পরীক্ষা করব:

- `7 % 2 == 0` কি না
- `7 % 3 == 0` কি না
- `7 % 4 == 0` কি না
- `7 % 5 == 0` কি না
- `7 % 6 == 0` কি না

কোনো ক্ষেত্রেই ভাগশেষ শূন্য হবে না। তাই `7` prime number।

অন্যদিকে, `number = 8` হলে:

`8 % 2 == 0`

অর্থাৎ `8`-এর একটি divisor `2` পাওয়া গেছে, যা `1` ও `8` নয়। তাই `8` prime নয়।

**মূল নিয়ম:**

1. `number <= 1` হলে prime নয়।
2. `2` থেকে শুরু করে সম্ভাব্য divisor পরীক্ষা করো।
3. কোনো divisor পাওয়া গেলে prime নয়।
4. কোনো divisor না পাওয়া গেলে prime।

## 4. Prime Checking Using a `for` Loop

প্রথমে একটি সংখ্যা prime কি না, তা `for` loop দিয়ে পরীক্ষা করি।

### Code

```python
number = 7
is_prime = True

if number <= 1:
    is_prime = False
else:
    for i in range(2, number):
        if number % i == 0:
            is_prime = False
            break

if is_prime:
    print("Prime number")
else:
    print("Not a prime number")
```

### Output

```text
Prime number
```

### Explanation

**Step 1:** `is_prime = True` দিয়ে ধরে নেওয়া হয় যে সংখ্যাটি prime।

**Step 2:** `number <= 1` হলে সেটি prime নয়।

**Step 3:** `range(2, number)` দিয়ে `2` থেকে `number - 1` পর্যন্ত divisor পরীক্ষা করা হয়।

**Step 4:** যদি `number % i == 0` হয়, তাহলে একটি divisor পাওয়া গেছে।

**Step 5:** `is_prime = False` করে `break` দিয়ে loop বন্ধ করা হয়।

**Step 6:** শেষে `is_prime`-এর value অনুযায়ী ফলাফল print হয়।

এখানে `is_prime` একটি **flag variable**। এটি prime কি না, সেই অবস্থা মনে রাখে।

## 5. Dry Run of Prime Checking

নিচের code-টি বিবেচনা করি:

```python
number = 7
is_prime = True

for i in range(2, number):
    if number % i == 0:
        is_prime = False
        break

print(is_prime)
```

### Dry Run Table

| Iteration | `i` | `7 % i` | Divisible? | `is_prime` |
|---:|---:|---:|---|---|
| 1 | 2 | 1 | No | True |
| 2 | 3 | 1 | No | True |
| 3 | 4 | 3 | No | True |
| 4 | 5 | 2 | No | True |
| 5 | 6 | 1 | No | True |

### Output

```text
True
```

কোনো divisor পাওয়া যায়নি। তাই `7` prime number।

## 6. Checking a Non-Prime Number

এবার `number = 8` ধরি।

```python
number = 8
is_prime = True

for i in range(2, number):
    if number % i == 0:
        is_prime = False
        break

print(is_prime)
```

### Dry Run Table

| Iteration | `i` | `8 % i` | Result |
|---:|---:|---:|---|
| 1 | 2 | 0 | Divisor found |
| 2 | — | — | `break` দিয়ে loop বন্ধ |

### Output

```text
False
```

`8`-কে `2` দিয়ে নিঃশেষে ভাগ করা যায়। তাই `8` prime নয়।

এখানে `break` ব্যবহার করার ফলে বাকি divisor-গুলো আর পরীক্ষা করতে হয় না।

## 7. Prime Checking with User Input

এবার user-এর কাছ থেকে একটি integer নিয়ে prime check করি।

### Code

```python
number = int(input("Enter an integer: "))

if number <= 1:
    print("Not a prime number")
else:
    is_prime = True

    for i in range(2, number):
        if number % i == 0:
            is_prime = False
            break

    if is_prime:
        print("Prime number")
    else:
        print("Not a prime number")
```

### Sample Input and Output 1

```text
Enter an integer: 13
Prime number
```

### Sample Input and Output 2

```text
Enter an integer: 15
Not a prime number
```

কারণ `15 % 3 == 0` এবং `15 % 5 == 0`। তাই `15` prime নয়।

এই code-এ ধরে নেওয়া হয়েছে যে user valid integer দেবেন। অক্ষর বা decimal input দিলে `int()` থেকে `ValueError` হতে পারে।

## 8. Prime Checking Using a `while` Loop

একই logic `while` loop দিয়েও প্রয়োগ করা যায়।

### Code

```python
number = 11
i = 2
is_prime = True

if number <= 1:
    is_prime = False
else:
    while i < number:
        if number % i == 0:
            is_prime = False
            break

        i += 1

if is_prime:
    print("Prime number")
else:
    print("Not a prime number")
```

### Output

```text
Prime number
```

### Explanation

- `i = 2` দিয়ে divisor checking শুরু হয়।
- `while i < number` সম্ভাব্য divisor পরীক্ষা করে।
- `number % i == 0` হলে সংখ্যাটি prime নয়।
- `break` loop বন্ধ করে।
- কোনো divisor না পাওয়া গেলে `i` বাড়তে থাকে।
- শেষে flag দেখে ফলাফল print হয়।

**সতর্কতা:** `i += 1` বাদ দিলে divisor না পাওয়া অবস্থায় loop অনন্তকাল চলতে পারে।

## 9. Counting Divisors to Check Prime

Prime check করার আরেকটি পদ্ধতি হলো divisor গণনা করা।

কোনো সংখ্যার positive divisor ঠিক দুটি হলে সংখ্যাটি prime।

### Code

```python
number = 7
divisor_count = 0

if number > 0:
    for i in range(1, number + 1):
        if number % i == 0:
            divisor_count += 1

if divisor_count == 2:
    print("Prime number")
else:
    print("Not a prime number")
```

### Output

```text
Prime number
```

### Explanation

`7`-এর জন্য:

- `1` দিয়ে ভাগ যায়।
- `7` দিয়ে ভাগ যায়।

অর্থাৎ `divisor_count = 2`। তাই `7` prime।

কিন্তু `6`-এর divisor হলো `1`, `2`, `3` ও `6`। তাই `divisor_count = 4` এবং `6` prime নয়।

**তুলনা:** Divisor count পদ্ধতিটি বোঝার জন্য সহজ, তবে এটি প্রয়োজনের চেয়ে বেশি পরীক্ষা করে। Prime checking-এর জন্য flag ও `break` ব্যবহার করা সাধারণত বেশি কার্যকর।

## 10. Efficient Prime Checking up to the Square Root

আগের code-এ `2` থেকে `number - 1` পর্যন্ত পরীক্ষা করা হয়। কিন্তু সব divisor পরীক্ষা করা প্রয়োজন নেই।

যদি কোনো composite number-এর divisor থাকে, তাহলে তার অন্তত একটি divisor সংখ্যাটির square root-এর সমান বা ছোট হবে।

তাই আমরা `2` থেকে \(\sqrt{n}\) পর্যন্ত পরীক্ষা করতে পারি।

Python-এ `math.sqrt()` ব্যবহার করা যায়। তবে integer comparison-এর জন্য `i * i <= number`-ও ব্যবহার করা যায়।

### Code

```python
number = 29
is_prime = True

if number <= 1:
    is_prime = False
else:
    i = 2

    while i * i <= number:
        if number % i == 0:
            is_prime = False
            break

        i += 1

if is_prime:
    print("Prime number")
else:
    print("Not a prime number")
```

### Output

```text
Prime number
```

### কেন `i * i <= number`?

ধরি, `number = 29`।

- `2 * 2 <= 29` — True
- `3 * 3 <= 29` — True
- `4 * 4 <= 29` — True
- `5 * 5 <= 29` — True
- `6 * 6 <= 29` — False

তাই `6` দিয়ে পরীক্ষা করার প্রয়োজন নেই।

**সুবিধা:** এই পদ্ধতিতে বড় সংখ্যার জন্য অনেক কম divisor পরীক্ষা করতে হয়।

সাধারণ divisor checking-এর time complexity \(O(n)\), আর square-root পর্যন্ত checking-এর time complexity \(O(\sqrt{n})\)। এখানে \(n\) হলো পরীক্ষাধীন সংখ্যা।

## 11. Printing Prime Numbers in a Range

কখনো একটি range-এর মধ্যে সব prime number print করতে হয়।

যেমন, `1` থেকে `20` পর্যন্ত prime number:

```text
2 3 5 7 11 13 17 19
```

### Code

```python
for number in range(2, 21):
    is_prime = True

    for i in range(2, number):
        if number % i == 0:
            is_prime = False
            break

    if is_prime:
        print(number, end=" ")
```

### Output

```text
2 3 5 7 11 13 17 19
```

### Explanation

এখানে দুটি loop আছে:

- Outer loop `2` থেকে `20` পর্যন্ত প্রতিটি সংখ্যা নেয়।
- Inner loop পরীক্ষা করে সংখ্যাটি prime কি না।
- Prime হলে সেটি print হয়।

এটি **nested loop**-এর একটি বাস্তব উদাহরণ।

**গুরুত্বপূর্ণ:** `is_prime = True` প্রতিটি নতুন `number`-এর জন্য reset করতে হবে। এটি outer loop-এর বাইরে রাখলে আগের সংখ্যার result পরের সংখ্যার calculation-কে প্রভাবিত করতে পারে।

## 12. Printing Prime Numbers Using Square-Root Checking

Range-এর মধ্যে prime বের করার সময়ও square-root optimization ব্যবহার করা যায়।

### Code

```python
for number in range(2, 51):
    is_prime = True
    i = 2

    while i * i <= number:
        if number % i == 0:
            is_prime = False
            break

        i += 1

    if is_prime:
        print(number, end=" ")
```

### Output

```text
2 3 5 7 11 13 17 19 23 29 31 37 41 43 47
```

এখানে প্রতিটি সংখ্যার জন্য কেবল square root পর্যন্ত divisor পরীক্ষা করা হয়।

## 13. Handling Special Cases

Prime checking-এর সময় কয়েকটি special case মনে রাখতে হবে।

| Number | Prime? | Reason |
|---:|---|---|
| -5 | No | Negative integer |
| 0 | No | Prime নয় |
| 1 | No | মাত্র একটি positive divisor |
| 2 | Yes | ঠিক দুটি positive divisor |
| 3 | Yes | ঠিক দুটি positive divisor |
| 4 | No | `2` দিয়ে বিভাজ্য |
| 9 | No | `3` দিয়ে বিভাজ্য |

বিশেষ করে `2` হলো সবচেয়ে ছোট prime number এবং একমাত্র even prime number।

২-এর চেয়ে বড় প্রতিটি even number `2` দিয়ে বিভাজ্য, তাই সেগুলো prime নয়।

## 14. Common Mistakes

### Mistake 1: Treating 1 as a Prime Number

ভুল ধারণা: `1` prime, কারণ এটি শুধু `1` দিয়ে ভাগ যায়।

সঠিক ধারণা: Prime number-এর ঠিক দুটি distinct positive divisor থাকতে হবে। `1`-এর মাত্র একটি divisor আছে।

### Mistake 2: Starting Divisor Checking from 1

যদি `range(1, number)` দিয়ে শুরু করো, তাহলে প্রতিটি positive number-ই `1` দিয়ে বিভাজ্য হবে।

তাই flag-based prime checking-এ divisor checking সাধারণত `2` থেকে শুরু হয়।

### Mistake 3: Forgetting `break`

```python
if number % i == 0:
    is_prime = False
```

এটি result সঠিক রাখতে পারে, কিন্তু divisor পাওয়া গেলেও loop চলতে থাকবে।

অপ্রয়োজনীয় iteration বন্ধ করতে:

```python
if number % i == 0:
    is_prime = False
    break
```

### Mistake 4: Forgetting to Reset the Flag

Range-এর মধ্যে prime বের করার সময়:

```python
for number in range(2, 21):
    is_prime = True
```

এই initialization outer loop-এর ভেতরে রাখতে হবে।

### Mistake 5: Using the Wrong Loop Range

```python
for i in range(2, number):
```

এটি `2` থেকে `number - 1` পর্যন্ত পরীক্ষা করে। Stop value বাদ যায়, যা এখানে সঠিক—কারণ সংখ্যাটি নিজে দিয়ে ভাগ যায় কি না, সেটি prime নির্ধারণের জন্য পরীক্ষা করতে হয় না।

### Mistake 6: Incorrect Square-Root Condition

Efficient checking-এ:

```python
while i * i <= number:
```

ব্যবহার করতে হবে। শুধু `i < number` ব্যবহার করলে আগের পদ্ধতির মতো বেশি iteration হতে পারে।

## 15. Practice Exercises

### Exercise 1

`for` loop ব্যবহার করে `17` prime কি না পরীক্ষা করো।

### Exercise 2

`while` loop ব্যবহার করে `21` prime কি না পরীক্ষা করো।

### Exercise 3

User-এর কাছ থেকে একটি integer নিয়ে prime check করো।

### Exercise 4

Divisor count করে `12` prime কি না পরীক্ষা করো।

### Exercise 5

`1` থেকে `50` পর্যন্ত সব prime number print করো।

### Exercise 6

নিচের code-এর output নির্ণয় করো:

```python
number = 9
is_prime = True

for i in range(2, number):
    if number % i == 0:
        is_prime = False
        break

print(is_prime)
```

### Exercise 7

নিচের code-এ ভুলটি খুঁজে বের করো:

```python
number = 1
is_prime = True

for i in range(2, number):
    if number % i == 0:
        is_prime = False
        break

print(is_prime)
```

### Exercise 8

কেন `1` prime number নয়, ব্যাখ্যা করো।

### Exercise 9

`i * i <= number` ব্যবহার করে `97` prime কি না পরীক্ষা করো।

### Exercise 10

একটি range-এর মধ্যে prime number বের করতে outer loop ও inner loop কী কাজ করে, ব্যাখ্যা করো।

## 16. Practice Answer Key

### Answer 1

```python
number = 17
is_prime = True

for i in range(2, number):
    if number % i == 0:
        is_prime = False
        break

print(is_prime)
```

Output:

```text
True
```

### Answer 2

```python
number = 21
i = 2
is_prime = True

while i < number:
    if number % i == 0:
        is_prime = False
        break

    i += 1

print(is_prime)
```

Output:

```text
False
```

কারণ `21` হলো `3` ও `7` দিয়ে বিভাজ্য।

### Answer 3

```python
number = int(input("Enter an integer: "))

if number <= 1:
    print("Not a prime number")
else:
    is_prime = True

    for i in range(2, number):
        if number % i == 0:
            is_prime = False
            break

    if is_prime:
        print("Prime number")
    else:
        print("Not a prime number")
```

### Answer 4

`12`-এর positive divisor হলো `1`, `2`, `3`, `4`, `6`, `12`। মোট ৬টি divisor আছে। তাই `12` prime নয়।

### Answer 5

```python
for number in range(2, 51):
    is_prime = True

    for i in range(2, number):
        if number % i == 0:
            is_prime = False
            break

    if is_prime:
        print(number, end=" ")
```

Output:

```text
2 3 5 7 11 13 17 19 23 29 31 37 41 43 47
```

### Answer 6

Output:

```text
False
```

কারণ `9 % 3 == 0`, তাই `9` prime নয়।

### Answer 7

সমস্যা হলো code-এ `number <= 1`-এর জন্য আলাদা condition নেই। `1`-এর জন্য divisor checking loop চলে না, তাই `is_prime` ভুলভাবে `True` থেকে যায়।

সঠিকভাবে শুরুতে পরীক্ষা করতে হবে:

```python
if number <= 1:
    is_prime = False
```

### Answer 8

`1`-এর মাত্র একটি positive divisor আছে, সেটি `1` নিজেই। Prime number-এর ঠিক দুটি distinct positive divisor থাকতে হয়। তাই `1` prime নয়।

### Answer 9

```python
number = 97
is_prime = True
i = 2

while i * i <= number:
    if number % i == 0:
        is_prime = False
        break

    i += 1

print(is_prime)
```

Output:

```text
True
```

### Answer 10

Outer loop range-এর প্রতিটি সংখ্যাকে নির্বাচন করে। Inner loop সেই সংখ্যাটি অন্য কোনো সংখ্যা দিয়ে নিঃশেষে বিভাজ্য কি না পরীক্ষা করে। Divisor না পাওয়া গেলে সংখ্যাটি prime হিসেবে print হয়।

## 17. Chapter Summary

- Prime number-এর ঠিক দুটি distinct positive divisor থাকে।
- `1`, `0` ও negative integer prime নয়।
- `number % i == 0` দিয়ে divisor পরীক্ষা করা যায়।
- Flag variable দিয়ে prime status সংরক্ষণ করা যায়।
- Divisor পাওয়া গেলে `break` দিয়ে loop বন্ধ করা যায়।
- `for` ও `while`—দুই loop দিয়েই prime checking করা সম্ভব।
- Divisor count পদ্ধতিতে ঠিক দুটি divisor পাওয়া গেলে সংখ্যাটি prime।
- `i * i <= number` ব্যবহার করে square root পর্যন্ত checking করা যায়।
- Nested loop ব্যবহার করে একটি range-এর মধ্যে prime number বের করা যায়।
- Range-এর প্রতিটি নতুন সংখ্যার জন্য flag reset করতে হয়।

## 18. Completion Checklist

- [ ] Prime number-এর সংজ্ঞা বুঝি।
- [ ] Divisor ও modulus operator-এর ব্যবহার বুঝি।
- [ ] `for` loop দিয়ে prime check করতে পারি।
- [ ] `while` loop দিয়ে prime check করতে পারি।
- [ ] Flag variable ও `break` ব্যবহার করতে পারি।
- [ ] Divisor count করে prime check করতে পারি।
- [ ] Square-root optimization বুঝি।
- [ ] একটি range-এর সব prime number print করতে পারি।
- [ ] Prime checking-এর common mistakes শনাক্ত করতে পারি।

**Next Topic:** `57_Reversing_a_Number.md`