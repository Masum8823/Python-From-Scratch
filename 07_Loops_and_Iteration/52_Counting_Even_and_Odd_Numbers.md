# 52. Counting Even and Odd Numbers

## 1. Introduction

Programming-এ অনেক সময় একটি range বা list-এর মধ্যে কতগুলো even এবং odd number আছে, তা গণনা করতে হয়।

উদাহরণস্বরূপ, নিচের সংখ্যাগুলো বিবেচনা করি:

```python
numbers = [1, 2, 3, 4, 5, 6]
```

এখানে:

- Even numbers: `2, 4, 6`
- Odd numbers: `1, 3, 5`
- Even count: `3`
- Odd count: `3`

Python-এ loop, `if` condition এবং counter variable ব্যবহার করে সহজেই এই কাজ করা যায়।

এই Topic-এ আমরা শিখব:

- Even ও odd number চেনার নিয়ম
- Even ও odd সংখ্যা গণনা করা
- নির্দিষ্ট range-এর even/odd count বের করা
- List থেকে even/odd সংখ্যা গণনা করা
- Even ও odd সংখ্যার sum বের করা
- User input এবং nested loop-এর ব্যবহার
- Common mistakes ও debugging

## 2. Understanding Even and Odd Numbers

### Even Number

যে পূর্ণসংখ্যাকে ২ দিয়ে ভাগ করলে remainder বা ভাগশেষ ০ হয়, সেটি even number।

উদাহরণ: `2, 4, 6, 8, 10`

Python condition:

```python
number % 2 == 0
```

### Odd Number

যে পূর্ণসংখ্যাকে ২ দিয়ে ভাগ করলে remainder ০ হয় না, সেটি odd number।

উদাহরণ: `1, 3, 5, 7, 9`

Python condition:

```python
number % 2 != 0
```

এখানে `%` হলো modulus operator, যা ভাগশেষ বের করে।

### Example

```python
number = 8

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

Output:

```text
Even
```

**মনে রাখবে:** এই নিয়মটি integer বা পূর্ণসংখ্যার জন্য ব্যবহার করা হয়। `float` value-কে একইভাবে even বা odd বলা হয় না।

## 3. Counting Even Numbers from 1 to 10

প্রথমে ১ থেকে ১০ পর্যন্ত even number-এর সংখ্যা গণনা করি।

### Code

```python
count = 0

for number in range(1, 11):
    if number % 2 == 0:
        count += 1

print("Even count:", count)
```

### Output

```text
Even count: 5
```

### Explanation

- `count = 0` দিয়ে counter শুরু হয়েছে।
- `range(1, 11)` সংখ্যা তৈরি করে ১ থেকে ১০ পর্যন্ত।
- `number % 2 == 0` even number শনাক্ত করে।
- Even number পাওয়া গেলে `count += 1` দিয়ে counter বাড়ে।

১ থেকে ১০ পর্যন্ত even number হলো `2, 4, 6, 8, 10`। তাই count হলো ৫।

## 4. Counting Odd Numbers from 1 to 10

এবার odd number গণনা করি।

### Code

```python
count = 0

for number in range(1, 11):
    if number % 2 != 0:
        count += 1

print("Odd count:", count)
```

### Output

```text
Odd count: 5
```

Odd number হলো `1, 3, 5, 7, 9`। তাই count হলো ৫।

## 5. Counting Even and Odd Numbers Together

একটি loop ব্যবহার করে even ও odd—দুটির count বের করা যায়।

### Code

```python
even_count = 0
odd_count = 0

for number in range(1, 11):
    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

print("Even count:", even_count)
print("Odd count:", odd_count)
```

### Output

```text
Even count: 5
Odd count: 5
```

### Explanation

- `even_count` even number গণনা করে।
- `odd_count` odd number গণনা করে।
- `if` condition even number শনাক্ত করে।
- `else` block odd number-এর count বাড়ায়।

এই program-এ প্রতিটি সংখ্যার জন্য একটি মাত্র branch কার্যকর হয়।

## 6. Dry Run of Even and Odd Counting

Code:

```python
even_count = 0
odd_count = 0

for number in range(1, 6):
    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

print(even_count, odd_count)
```

### Dry Run Table

| Number | Type | Even count | Odd count |
|---:|---|---:|---:|
| 1 | Odd | 0 | 1 |
| 2 | Even | 1 | 1 |
| 3 | Odd | 1 | 2 |
| 4 | Even | 2 | 2 |
| 5 | Odd | 2 | 3 |

### Output

```text
2 3
```

১ থেকে ৫ পর্যন্ত দুটি even number এবং তিনটি odd number রয়েছে।

## 7. Counting Even and Odd Numbers in a List

বাস্তবে সব সংখ্যা সবসময় ১ থেকে শুরু করে ধারাবাহিকভাবে থাকে না। অনেক সময় একটি list-এর মধ্যে বিভিন্ন সংখ্যা দেওয়া থাকে।

### Code

```python
numbers = [12, 7, 4, 9, 15, 20, 3]

even_count = 0
odd_count = 0

for number in numbers:
    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

print("Even count:", even_count)
print("Odd count:", odd_count)
```

### Output

```text
Even count: 3
Odd count: 4
```

Even numbers: `12, 4, 20`

Odd numbers: `7, 9, 15, 3`

সুতরাং even count = ৩ এবং odd count = ৪।

## 8. Counting Even and Odd Numbers Using a `while` Loop

একই কাজ `while` loop দিয়েও করা যায়।

### Code

```python
number = 1
even_count = 0
odd_count = 0

while number <= 10:
    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

    number += 1

print("Even count:", even_count)
print("Odd count:", odd_count)
```

### Output

```text
Even count: 5
Odd count: 5
```

### Explanation

- `number = 1` দিয়ে শুরু হয়েছে।
- `while number <= 10` condition পরীক্ষা করে।
- প্রতিটি সংখ্যাকে even বা odd হিসেবে গণনা করা হয়।
- `number += 1` পরবর্তী সংখ্যায় নিয়ে যায়।

**গুরুত্বপূর্ণ:** `number += 1` ভুলে গেলে loop অনন্তকাল চলতে পারে।

## 9. Counting Even and Odd Numbers in a User-Defined Range

ব্যবহারকারী start এবং end দিলে সেই range-এর মধ্যে even ও odd সংখ্যা গণনা করা যায়।

### Code

```python
start = int(input("Enter start: "))
end = int(input("Enter end: "))

even_count = 0
odd_count = 0

for number in range(start, end + 1):
    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

print("Even count:", even_count)
print("Odd count:", odd_count)
```

### Sample Input and Output

```text
Enter start: 5
Enter end: 12
Even count: 4
Odd count: 4
```

এখানে সংখ্যাগুলো হলো `5, 6, 7, 8, 9, 10, 11, 12`।

Even numbers: `6, 8, 10, 12`

Odd numbers: `5, 7, 9, 11`

এই code-এ `start <= end` ধরে নেওয়া হয়েছে। উল্টো range গ্রহণ করতে হলে আগে validation বা range-এর দিক নির্ধারণ করতে হবে।

## 10. Finding the Sum of Even Numbers

শুধু even number গণনা নয়, even number-গুলোর sum-ও বের করা যায়।

### Code

```python
total = 0

for number in range(1, 11):
    if number % 2 == 0:
        total += number

print("Sum of even numbers:", total)
```

### Output

```text
Sum of even numbers: 30
```

Even numbers:

`2 + 4 + 6 + 8 + 10 = 30`

এখানে `total` একটি accumulator, যা প্রতিটি even number-এর যোগফল জমা রাখে।

## 11. Finding the Sum of Odd Numbers

### Code

```python
total = 0

for number in range(1, 11):
    if number % 2 != 0:
        total += number

print("Sum of odd numbers:", total)
```

### Output

```text
Sum of odd numbers: 25
```

Odd numbers:

`1 + 3 + 5 + 7 + 9 = 25`

## 12. Counting and Summing Even and Odd Numbers Together

একটি loop ব্যবহার করে even ও odd number-এর count এবং sum—সবগুলো বের করা যায়।

### Code

```python
even_count = 0
odd_count = 0

even_sum = 0
odd_sum = 0

for number in range(1, 11):
    if number % 2 == 0:
        even_count += 1
        even_sum += number
    else:
        odd_count += 1
        odd_sum += number

print("Even count:", even_count)
print("Odd count:", odd_count)
print("Even sum:", even_sum)
print("Odd sum:", odd_sum)
```

### Output

```text
Even count: 5
Odd count: 5
Even sum: 30
Odd sum: 25
```

### Explanation

প্রতিটি even number-এর জন্য:

- `even_count` এক বাড়ে।
- `even_sum`-এর সঙ্গে সংখ্যাটি যোগ হয়।

প্রতিটি odd number-এর জন্য:

- `odd_count` এক বাড়ে।
- `odd_sum`-এর সঙ্গে সংখ্যাটি যোগ হয়।

এভাবে একই loop-এ চারটি result বের করা যায়।

## 13. Counting Even and Odd Numbers in a List with Negative Values

Negative integer-ও even বা odd হতে পারে।

### Code

```python
numbers = [-5, -4, -3, -2, -1, 0, 1, 2]

even_count = 0
odd_count = 0

for number in numbers:
    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

print("Even count:", even_count)
print("Odd count:", odd_count)
```

### Output

```text
Even count: 4
Odd count: 4
```

Even numbers: `-4, -2, 0, 2`

Odd numbers: `-5, -3, -1, 1`

**মনে রাখবে:** `0` একটি even integer, কারণ `0 % 2 == 0`।

## 14. Separating Even and Odd Numbers into Lists

কখনো count বের করার পাশাপাশি even ও odd সংখ্যাগুলো আলাদা list-এ রাখতে হয়।

### Code

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8]

even_numbers = []
odd_numbers = []

for number in numbers:
    if number % 2 == 0:
        even_numbers.append(number)
    else:
        odd_numbers.append(number)

print("Even numbers:", even_numbers)
print("Odd numbers:", odd_numbers)
```

### Output

```text
Even numbers: [2, 4, 6, 8]
Odd numbers: [1, 3, 5, 7]
```

### Explanation

- `even_numbers = []` একটি খালি list তৈরি করে।
- `odd_numbers = []` আরেকটি খালি list তৈরি করে।
- `append()` list-এর শেষে একটি value যোগ করে।
- Condition অনুযায়ী প্রতিটি সংখ্যা সঠিক list-এ যোগ হয়।

## 15. Counting Even and Odd Digits in a Number

কোনো integer-এর প্রতিটি digit even নাকি odd, তা গণনা করাও সম্ভব। এজন্য `% 10` দিয়ে শেষ digit বের করা এবং `// 10` দিয়ে শেষ digit বাদ দেওয়া হয়।

### Code

```python
number = 123456

even_count = 0
odd_count = 0

while number > 0:
    digit = number % 10

    if digit % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

    number //= 10

print("Even digits:", even_count)
print("Odd digits:", odd_count)
```

### Output

```text
Even digits: 3
Odd digits: 3
```

Digits: `1, 2, 3, 4, 5, 6`

Even digits: `2, 4, 6`

Odd digits: `1, 3, 5`

এই উদাহরণটি positive integer-এর জন্য লেখা। `0` বা negative integer-সহ সব ক্ষেত্রে কাজ করাতে হলে input-এর sign এবং zero-কে আলাদাভাবে বিবেচনা করতে হবে।

## 16. Counting Even and Odd Numbers Using Nested Loops

Nested loop ব্যবহার করে একাধিক range-এর even ও odd সংখ্যা গণনা করা যায়।

### Code

```python
for start in range(1, 4):
    even_count = 0
    odd_count = 0

    for number in range(start, 6):
        if number % 2 == 0:
            even_count += 1
        else:
            odd_count += 1

    print("Start:", start)
    print("Even count:", even_count)
    print("Odd count:", odd_count)
```

### Output

```text
Start: 1
Even count: 2
Odd count: 3
Start: 2
Even count: 2
Odd count: 2
Start: 3
Even count: 1
Odd count: 2
```

### Explanation

- Outer loop `start`-এর মান ১, ২ ও ৩ নেয়।
- Inner loop প্রতিটি start থেকে ৫ পর্যন্ত সংখ্যা পরীক্ষা করে।
- প্রতিটি নতুন start-এর জন্য count দুটো আবার শূন্য করা হয়।
- প্রতিটি range-এর ফল আলাদাভাবে print হয়।

## 17. Common Mistakes

### Mistake 1: Using the Wrong Condition

Even number-এর জন্য:

```python
number % 2 == 0
```

Odd number-এর জন্য:

```python
number % 2 != 0
```

Condition ভুল হলে count-ও ভুল হবে।

### Mistake 2: Forgetting to Initialize the Counter

ভুল:

```python
for number in range(1, 11):
    if number % 2 == 0:
        even_count += 1
```

এখানে `even_count` আগে initialize করা হয়নি।

সঠিক:

```python
even_count = 0

for number in range(1, 11):
    if number % 2 == 0:
        even_count += 1
```

### Mistake 3: Increasing Both Counters

ভুল:

```python
if number % 2 == 0:
    even_count += 1

odd_count += 1
```

এখানে প্রতিটি সংখ্যার জন্য `odd_count` বাড়ছে, এমনকি even number-এর ক্ষেত্রেও।

সঠিক:

```python
if number % 2 == 0:
    even_count += 1
else:
    odd_count += 1
```

### Mistake 4: Forgetting to Update a `while` Loop

ভুল:

```python
number = 1

while number <= 10:
    if number % 2 == 0:
        print(number)
```

এখানে `number` পরিবর্তন হচ্ছে না। তাই loop থামবে না।

সঠিক:

```python
number = 1

while number <= 10:
    if number % 2 == 0:
        print(number)

    number += 1
```

### Mistake 5: Resetting the Counter Inside the Loop

ভুল:

```python
for number in range(1, 11):
    even_count = 0

    if number % 2 == 0:
        even_count += 1
```

প্রতিবার loop চলার সময় counter আবার শূন্য হয়ে যায়।

সঠিকভাবে counter loop-এর আগে initialize করতে হবে।

## 18. Practice Exercises

### Exercise 1

১ থেকে ২০ পর্যন্ত even number-এর count বের করো।

### Exercise 2

১ থেকে ৫০ পর্যন্ত odd number-এর count বের করো।

### Exercise 3

একটি loop ব্যবহার করে ১ থেকে ১০০ পর্যন্ত even ও odd number-এর count বের করো।

### Exercise 4

নিচের list-এ কতগুলো even এবং odd number আছে, তা বের করো:

```python
numbers = [10, 15, 22, 33, 40, 51, 60]
```

### Exercise 5

১ থেকে ২০ পর্যন্ত even number-এর sum বের করো।

### Exercise 6

নিচের list থেকে even ও odd number আলাদা দুটি list-এ রাখো:

```python
numbers = [3, 8, 11, 14, 17, 20]
```

### Exercise 7

নিচের code-এর output নির্ণয় করো:

```python
even_count = 0
odd_count = 0

for number in range(1, 6):
    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

print(even_count, odd_count)
```

### Exercise 8

`0` even number কেন?

### Exercise 9

`while` loop ব্যবহার করে ১ থেকে ১০ পর্যন্ত odd number-এর count বের করো।

### Exercise 10

`12345` সংখ্যাটিতে কতটি even digit এবং কতটি odd digit আছে, তা বের করো।

## 19. Practice Answer Key

### Answer 1

```python
count = 0

for number in range(1, 21):
    if number % 2 == 0:
        count += 1

print(count)
```

Output: `10`

### Answer 2

```python
count = 0

for number in range(1, 51):
    if number % 2 != 0:
        count += 1

print(count)
```

Output: `25`

### Answer 3

```python
even_count = 0
odd_count = 0

for number in range(1, 101):
    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

print("Even:", even_count)
print("Odd:", odd_count)
```

Output:

```text
Even: 50
Odd: 50
```

### Answer 4

```python
numbers = [10, 15, 22, 33, 40, 51, 60]

even_count = 0
odd_count = 0

for number in numbers:
    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

print("Even:", even_count)
print("Odd:", odd_count)
```

Output:

```text
Even: 4
Odd: 3
```

### Answer 5

```python
total = 0

for number in range(2, 21, 2):
    total += number

print(total)
```

Output: `110`

### Answer 6

```python
numbers = [3, 8, 11, 14, 17, 20]

even_numbers = []
odd_numbers = []

for number in numbers:
    if number % 2 == 0:
        even_numbers.append(number)
    else:
        odd_numbers.append(number)

print(even_numbers)
print(odd_numbers)
```

Output:

```text
[8, 14, 20]
[3, 11, 17]
```

### Answer 7

Output:

```text
2 3
```

১ থেকে ৫ পর্যন্ত even number হলো ২টি এবং odd number হলো ৩টি।

### Answer 8

`0 % 2 == 0` হওয়ায় ০-কে even integer বলা হয়।

### Answer 9

```python
number = 1
count = 0

while number <= 10:
    if number % 2 != 0:
        count += 1

    number += 1

print(count)
```

Output: `5`

### Answer 10

```python
number = 12345

even_count = 0
odd_count = 0

while number > 0:
    digit = number % 10

    if digit % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

    number //= 10

print("Even digits:", even_count)
print("Odd digits:", odd_count)
```

Output:

```text
Even digits: 2
Odd digits: 3
```

## 20. Chapter Summary

- Even number শনাক্ত করতে `number % 2 == 0` ব্যবহার করা হয়।
- Odd number শনাক্ত করতে `number % 2 != 0` ব্যবহার করা হয়।
- Counter variable দিয়ে even ও odd সংখ্যা গণনা করা যায়।
- একটি loop-এ even ও odd—দুটির count বের করা সম্ভব।
- Accumulator ব্যবহার করে even ও odd সংখ্যার sum বের করা যায়।
- `append()` ব্যবহার করে even ও odd সংখ্যাগুলো আলাদা list-এ রাখা যায়।
- Negative integer-ও even বা odd হতে পারে; `0` একটি even integer।
- `while` loop-এ counter update করতে ভুললে infinite loop হতে পারে।
- Digit counting-এর জন্য `% 10` এবং `// 10` ব্যবহার করা যায়।

## 21. Completion Checklist

- [ ] Even ও odd number-এর পার্থক্য বুঝি।
- [ ] `if` condition দিয়ে even ও odd শনাক্ত করতে পারি।
- [ ] `for` loop দিয়ে even ও odd count করতে পারি।
- [ ] `while` loop দিয়ে even ও odd count করতে পারি।
- [ ] List-এর even ও odd count বের করতে পারি।
- [ ] Even ও odd সংখ্যার sum বের করতে পারি।
- [ ] Even ও odd সংখ্যাকে আলাদা list-এ রাখতে পারি।
- [ ] Negative integer ও zero-এর ক্ষেত্রে সঠিক ফল বুঝি।
- [ ] একটি integer-এর even ও odd digit গণনা করতে পারি।

**Next Topic:** `53_Multiplication_Table_Programs.md`