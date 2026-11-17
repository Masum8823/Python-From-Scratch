# 73. Loop Programming Exercises

## 1. Introduction

এই topic-এর মূল উদ্দেশ্য হলো `for` loop, `while` loop, `range()`, conditions, nested loops, `break`, `continue` এবং accumulator ব্যবহার করে নিজে program তৈরি করা।

শুধু code দেখে output বোঝা আর নিজে problem solve করে code লেখা এক বিষয় নয়। তাই এই topic-এ প্রতিটি problem নিজে solve করার চেষ্টা করবে।

## 2. How to Solve Loop Problems

প্রতিটি problem সমাধানের সময় নিচের ধাপগুলো অনুসরণ করো:

1. **Problem বুঝো:** কী input দেওয়া হবে এবং কী output প্রয়োজন?
2. **Variables নির্বাচন করো:** Counter, accumulator বা অন্য কোনো variable লাগবে কি?
3. **Loop নির্বাচন করো:** নির্দিষ্ট সংখ্যক iteration-এর জন্য `for`, condition-নির্ভর repetition-এর জন্য `while` বিবেচনা করো।
4. **Condition তৈরি করো:** কোন ক্ষেত্রে কাজ হবে বা loop বন্ধ হবে?
5. **Variable update করো:** প্রয়োজনীয় variable সঠিকভাবে পরিবর্তন হচ্ছে কি?
6. **Dry run করো:** ছোট input দিয়ে code হাতে trace করো।
7. **Test করো:** Normal input, boundary value এবং বিশেষ case পরীক্ষা করো।

## 3. Level 1: Basic Loop Exercises

### Exercise 1: Print Numbers from 1 to 10

**Task:** `for` loop ব্যবহার করে 1 থেকে 10 পর্যন্ত সংখ্যা print করো।

**Expected output:**

```text
1
2
3
4
5
6
7
8
9
10
```

**Hint:** `range()` ব্যবহার করো।

### Exercise 2: Print Even Numbers

**Task:** 1 থেকে 20 পর্যন্ত সব জোড় সংখ্যা print করো।

**Expected output:**

```text
2 4 6 8 10 12 14 16 18 20
```

**Hint:** `number % 2 == 0` অথবা `range()`-এর step ব্যবহার করা যায়।

### Exercise 3: Print Odd Numbers

**Task:** 1 থেকে 20 পর্যন্ত সব বিজোড় সংখ্যা print করো।

**Expected output:**

```text
1 3 5 7 9 11 13 15 17 19
```

### Exercise 4: Countdown

**Task:** 10 থেকে 1 পর্যন্ত উল্টোভাবে print করো।

**Expected output:**

```text
10 9 8 7 6 5 4 3 2 1
```

### Exercise 5: Multiplication Table

**Task:** 5-এর নামতা print করো।

**Expected output:**

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

### Exercise 6: Print a Message Five Times

**Task:** `Hello Python` পাঁচবার print করো।

### Exercise 7: Numbers in a Custom Range

**Task:** 15 থেকে 30 পর্যন্ত সব সংখ্যা print করো।

### Exercise 8: Multiples of 3

**Task:** 1 থেকে 50-এর মধ্যে 3 দিয়ে বিভাজ্য সব সংখ্যা print করো।

## 4. Level 2: Sum and Accumulation

### Exercise 9: Sum from 1 to N

**Task:** User-এর কাছ থেকে `n` নিয়ে 1 থেকে `n` পর্যন্ত সংখ্যার যোগফল বের করো।

**Example:**

```text
Enter n: 5
Sum: 15
```

**Hint:** `total = 0` দিয়ে শুরু করবে।

### Exercise 10: Sum of Even Numbers

**Task:** 1 থেকে 100 পর্যন্ত সব জোড় সংখ্যার যোগফল বের করো।

**Expected output:**

```text
2550
```

### Exercise 11: Sum of Odd Numbers

**Task:** 1 থেকে 50 পর্যন্ত সব বিজোড় সংখ্যার যোগফল বের করো।

**Expected output:**

```text
625
```

### Exercise 12: Sum of Multiples

**Task:** 1 থেকে 100 পর্যন্ত 5 দিয়ে বিভাজ্য সংখ্যাগুলোর যোগফল বের করো।

**Expected output:**

```text
1050
```

### Exercise 13: Calculate Average

**Task:** 1 থেকে 10 পর্যন্ত সংখ্যার average বের করো।

**Expected output:**

```text
5.5
```

**Hint:** Average = Sum / Count

### Exercise 14: Sum of User-Entered Numbers

**Task:** User কতটি সংখ্যা দিতে চায়, তা প্রথমে input নাও। তারপর সেই সংখ্যক input নিয়ে মোট যোগফল বের করো।

**Example:**

```text
How many numbers? 3
Enter number: 10
Enter number: 20
Enter number: 30
Sum: 60
```

### Exercise 15: Sum Until Sentinel

**Task:** User যতক্ষণ `0` না দেয়, ততক্ষণ সংখ্যা input নাও এবং তাদের যোগফল বের করো। Sentinel `0`-কে যোগফলে অন্তর্ভুক্ত করবে না।

**Example:**

```text
Enter number (0 to stop): 5
Enter number (0 to stop): 10
Enter number (0 to stop): 3
Enter number (0 to stop): 0
Sum: 18
```

## 5. Level 3: Counting Problems

### Exercise 16: Count Even and Odd Numbers

**Task:** 1 থেকে 100 পর্যন্ত কতটি even এবং কতটি odd number আছে, তা বের করো।

**Expected output:**

```text
Even count: 50
Odd count: 50
```

### Exercise 17: Count Positive, Negative and Zero

**Task:** User পাঁচটি সংখ্যা input দেবে। কতটি positive, negative এবং zero—তা count করো।

### Exercise 18: Count Numbers Divisible by 3

**Task:** 1 থেকে 100 পর্যন্ত 3 দিয়ে বিভাজ্য সংখ্যার সংখ্যা বের করো।

**Expected output:**

```text
33
```

### Exercise 19: Count Digits

**Task:** একটি integer-এর digit সংখ্যা বের করো।

**Example:**

```text
Enter number: 58321
Digit count: 5
```

**Hint:** `% 10` ও `// 10` ব্যবহার করা যায়। `0` এবং negative number-এর case-ও বিবেচনা করো।

### Exercise 20: Count Vowels

**Task:** User-এর দেওয়া string-এ কতটি vowel আছে তা বের করো। English vowels হলো `a`, `e`, `i`, `o`, `u`।

**Example:**

```text
Enter text: Education
Vowel count: 5
```

### Exercise 21: Count Numbers Above a Threshold

**Task:** `[10, 25, 7, 40, 18, 5]` list-এ 15-এর চেয়ে বড় কতটি সংখ্যা আছে তা বের করো।

**Expected output:**

```text
3
```

## 6. Level 4: Number-Based Problems

### Exercise 22: Factorial

**Task:** User-এর দেওয়া non-negative integer-এর factorial বের করো।

**Example:**

```text
Enter number: 5
Factorial: 120
```

মনে রাখবে, \(0! = 1\)।

### Exercise 23: Fibonacci Series

**Task:** প্রথম `n`টি Fibonacci term print করো।

**Example:**

```text
Enter terms: 7
0 1 1 2 3 5 8
```

### Exercise 24: Prime Number Check

**Task:** User-এর দেওয়া integer prime কি না তা পরীক্ষা করো।

**Example:**

```text
Enter number: 17
Prime
```

**Hint:** 1 বা তার কম সংখ্যা prime নয়। Divisor পরীক্ষা করার সময় `break` ব্যবহার করতে পারো।

### Exercise 25: Print Prime Numbers in a Range

**Task:** 1 থেকে 50 পর্যন্ত সব prime number print করো।

**Expected output:**

```text
2 3 5 7 11 13 17 19 23 29 31 37 41 43 47
```

### Exercise 26: Reverse a Number

**Task:** একটি integer-এর digit উল্টো করে নতুন integer তৈরি করো।

**Example:**

```text
Enter number: 12345
Reversed: 54321
```

### Exercise 27: Sum of Digits

**Task:** একটি integer-এর সব digit-এর যোগফল বের করো।

**Example:**

```text
Enter number: 5832
Sum of digits: 18
```

### Exercise 28: Palindrome Number

**Task:** একটি non-negative integer palindrome কি না পরীক্ষা করো।

**Example 1:**

```text
Enter number: 121
Palindrome
```

**Example 2:**

```text
Enter number: 123
Not palindrome
```

### Exercise 29: Armstrong Number

**Task:** একটি non-negative integer Armstrong number কি না পরীক্ষা করো। প্রতিটি digit-কে মোট digit সংখ্যার power-এ উন্নীত করে যোগ করতে হবে।

**Example:**

```text
Enter number: 153
Armstrong number
```

কারণ:

\[
1^3 + 5^3 + 3^3 = 153
\]

### Exercise 30: Greatest Common Divisor (GCD)

**Task:** দুটি non-negative integer-এর GCD বের করো।

**Example:**

```text
Enter first number: 12
Enter second number: 18
GCD: 6
```

**Hint:** Euclidean algorithm ব্যবহার করতে পারো:

```python
while second != 0:
    first, second = second, first % second
```

এই পদ্ধতিতে প্রথম সংখ্যাটি এবং দ্বিতীয় সংখ্যাটি update করতে হবে।

## 7. Level 5: List Processing

### Exercise 31: Find Maximum

**Task:** একটি list-এর সর্বোচ্চ সংখ্যা loop ব্যবহার করে বের করো।

```python
numbers = [12, 45, 7, 89, 23]
```

**Expected output:**

```text
Maximum: 89
```

### Exercise 32: Find Minimum

**Task:** একই list-এর সর্বনিম্ন সংখ্যা বের করো।

**Expected output:**

```text
Minimum: 7
```

### Exercise 33: Count Occurrences

**Task:** একটি list-এ target কতবার আছে তা বের করো।

```python
numbers = [2, 4, 2, 7, 2, 9]
target = 2
```

**Expected output:**

```text
Occurrences: 3
```

### Exercise 34: Linear Search

**Task:** একটি list-এ target থাকলে তার index বের করো; না থাকলে `-1` return করো।

```python
numbers = [10, 20, 30, 40]
target = 30
```

**Expected output:**

```text
Index: 2
```

### Exercise 35: Copy Positive Numbers

**Task:** একটি list থেকে শুধু positive number নিয়ে নতুন list তৈরি করো।

```python
numbers = [-5, 10, 0, -2, 8, 3]
```

**Expected output:**

```text
[10, 8, 3]
```

এখানে zero positive নয়।

### Exercise 36: Remove Duplicates

**Task:** একটি list-এর duplicate value বাদ দিয়ে প্রথম occurrence-এর order বজায় রেখে নতুন list তৈরি করো।

```python
numbers = [1, 2, 1, 3, 2, 4]
```

**Expected output:**

```text
[1, 2, 3, 4]
```

**Hint:** নতুন list-এ কোনো item যোগ করার আগে সেটি আগে থেকেই আছে কি না পরীক্ষা করো।

### Exercise 37: Second Largest Distinct Number

**Task:** একটি list থেকে দ্বিতীয় বৃহত্তম distinct number বের করো।

```python
numbers = [10, 5, 20, 20, 8]
```

**Expected output:**

```text
Second largest: 10
```

**Hint:** Duplicate value-কে আলাদা সংখ্যা হিসেবে গণনা করবে না। দ্বিতীয় বৃহত্তম distinct value না থাকলে সেটি handle করবে।

## 8. Level 6: Nested Loop Exercises

### Exercise 38: Square Star Pattern

**Task:** Nested loop ব্যবহার করে 4 × 4 star pattern print করো।

**Expected output:**

```text
* * * *
* * * *
* * * *
* * * *
```

### Exercise 39: Right Triangle

**Task:** নিচের pattern তৈরি করো।

```text
*
* *
* * *
* * * *
* * * * *
```

### Exercise 40: Inverted Triangle

**Task:** নিচের pattern তৈরি করো।

```text
* * * * *
* * * *
* * *
* *
*
```

### Exercise 41: Number Triangle

**Task:** নিচের pattern তৈরি করো।

```text
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

### Exercise 42: Multiplication Grid

**Task:** 1 থেকে 5 পর্যন্ত সংখ্যার multiplication grid তৈরি করো।

**Expected output:**

```text
 1  2  3  4  5
 2  4  6  8 10
 3  6  9 12 15
 4  8 12 16 20
 5 10 15 20 25
```

### Exercise 43: All Ordered Pairs

**Task:** `[1, 2, 3]` list থেকে প্রতিটি ordered pair তৈরি করো।

**Expected output:**

```text
1 1
1 2
1 3
2 1
2 2
2 3
3 1
3 2
3 3
```

### Exercise 44: Find Pairs with a Target Sum

**Task:** `[1, 2, 3, 4, 5]` list থেকে এমন ordered pairs print করো, যাদের যোগফল 6।

**Hint:** Nested loop ব্যবহার করো। একই pair-এর reverse এবং একই element দুবার ব্যবহার করা অনুমোদিত কি না, আগে নির্ধারণ করো। এই exercise-এ উভয়ই অনুমোদিত।

## 9. Level 7: Input and Menu-Based Problems

### Exercise 45: Input Validation

**Task:** User-এর কাছ থেকে 0–100-এর মধ্যে একটি marks value নাও। সঠিক range-এর মধ্যে না থাকলে আবার input নাও।

### Exercise 46: Password Attempts

**Task:** একটি predefined password-এর সঙ্গে user input মিলিয়ে সর্বোচ্চ তিনবার চেষ্টা করার সুযোগ দাও। সঠিক password দিলে loop বন্ধ হবে।

**Note:** এটি শুধু loop practice-এর উদাহরণ; real application-এ plaintext password সংরক্ষণ করা নিরাপদ নয়।

### Exercise 47: Menu-Driven Calculator

**Task:** `while` loop ও `if-elif-else` ব্যবহার করে একটি calculator তৈরি করো।

Menu:

```text
1. Addition
2. Subtraction
3. Multiplication
4. Division
5. Exit
```

**Requirements:**

- সঠিক option অনুযায়ী operation হবে।
- Division-এর আগে zero divisor পরীক্ষা করতে হবে।
- Invalid option handle করতে হবে।
- Exit নির্বাচন করলে loop বন্ধ হবে।

### Exercise 48: Guess the Number

**Task:** একটি predefined secret number অনুমান করতে user-কে বারবার input দিতে দাও।

**Requirements:**

- অনুমান ছোট হলে `Too low` দেখাবে।
- বড় হলে `Too high` দেখাবে।
- সঠিক হলে `Correct` দেখিয়ে loop বন্ধ করবে।

### Exercise 49: Student Marks Summary

**Task:** `[75, 32, 60, 25, 90, 40]` list থেকে pass ও fail student-এর সংখ্যা বের করো। Pass mark 40।

**Expected output:**

```text
Passed: 4
Failed: 2
```

### Exercise 50: Simple Menu for a List

**Task:** একটি list-এর জন্য menu তৈরি করো:

```text
1. Display all numbers
2. Find sum
3. Find maximum
4. Exit
```

প্রতিটি operation-এর জন্য loop ও conditional statements ব্যবহার করো।

## 10. Level 8: Challenge Problems

### Exercise 51: Perfect Number

একটি positive integer-এর proper divisors-এর যোগফল যদি সংখ্যাটির সমান হয়, তবে সেটি perfect number।

**Example:** `6` একটি perfect number, কারণ:

\[
1+2+3=6
\]

Loop ব্যবহার করে একটি number perfect কি না পরীক্ষা করো।

### Exercise 52: Strong Number

একটি non-negative integer-এর প্রতিটি digit-এর factorial-এর যোগফল যদি মূল সংখ্যার সমান হয়, তবে সেটি Strong number।

**Example:**

\[
145=1!+4!+5!
\]

### Exercise 53: Find All Divisors

একটি positive integer-এর সব positive divisor print করো।

**Example:**

```text
Enter number: 12
1 2 3 4 6 12
```

### Exercise 54: Check Whether a Number Is a Power of Two

একটি positive integer দুইয়ের কোনো non-negative integer power কি না, তা পরীক্ষা করো।

**Examples:**

- `8` → Yes
- `16` → Yes
- `12` → No

### Exercise 55: Find Common Elements

দুটি list-এর common elements loop ব্যবহার করে বের করো। Result-এ duplicate রাখতে হবে কি না, তা নির্ধারণ করো।

```python
first = [1, 2, 3, 4]
second = [3, 4, 5, 6]
```

**Expected output:**

```text
[3, 4]
```

### Exercise 56: Run-Length Counting

একটি string-এর প্রতিটি consecutive character group-এর দৈর্ঘ্য বের করো।

**Example:**

```text
Input: aaabbc
Output: a:3 b:2 c:1
```

### Exercise 57: Find a Pair with a Given Sum

একটি list এবং target sum দেওয়া থাকবে। এমন দুটি distinct position-এর element খুঁজে বের করো, যাদের যোগফল target-এর সমান।

```python
numbers = [2, 7, 11, 15]
target = 9
```

**Expected result:** indices `0` এবং `1`।

### Exercise 58: Generate a Simple Histogram

একটি list-এর প্রতিটি positive integer-এর জন্য সেই সংখ্যক `*` print করো।

```python
numbers = [3, 1, 4]
```

**Expected output:**

```text
***
*
****
```

### Exercise 59: Find the Longest Word

একটি list of words থেকে সবচেয়ে দীর্ঘ word বের করো।

```python
words = ["Python", "Programming", "Code", "Loop"]
```

**Expected output:**

```text
Programming
```

### Exercise 60: Combine Loop Concepts

একটি list থেকে:

- সব even number-এর যোগফল বের করো।
- সব odd number-এর সংখ্যা count করো।
- সর্বোচ্চ সংখ্যা বের করো।

```python
numbers = [12, 7, 4, 9, 15, 20, 3]
```

**Expected output:**

```text
Even sum: 36
Odd count: 4
Maximum: 20
```

## 11. Selected Solutions

নিচে কয়েকটি গুরুত্বপূর্ণ problem-এর complete solution দেওয়া হলো। অন্য problem-গুলো আগে নিজে solve করার চেষ্টা করবে।

### Solution 1: Print Numbers from 1 to 10

```python
for number in range(1, 11):
    print(number)
```

### Solution 9: Sum from 1 to N

```python
n = int(input("Enter n: "))

total = 0

for number in range(1, n + 1):
    total += number

print("Sum:", total)
```

এই solution-এ `n` positive integer বা zero হলে কাজ করবে। Negative `n`-এর জন্য আলাদা validation যোগ করা যেতে পারে।

### Solution 16: Count Even and Odd Numbers

```python
even_count = 0
odd_count = 0

for number in range(1, 101):
    if number % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

print("Even count:", even_count)
print("Odd count:", odd_count)
```

### Solution 22: Factorial

```python
number = int(input("Enter a non-negative integer: "))

if number < 0:
    print("Factorial is not defined for negative integers.")
else:
    factorial = 1

    for value in range(1, number + 1):
        factorial *= value

    print("Factorial:", factorial)
```

### Solution 24: Prime Number Check

```python
number = int(input("Enter number: "))

if number <= 1:
    print("Not prime")
else:
    is_prime = True

    for divisor in range(2, number):
        if number % divisor == 0:
            is_prime = False
            break

    if is_prime:
        print("Prime")
    else:
        print("Not prime")
```

এই basic solution-এ divisor `2` থেকে `number - 1` পর্যন্ত পরীক্ষা করা হয়। বড় input-এর জন্য `divisor * divisor <= number` শর্ত ব্যবহার করে পরীক্ষা কমানো যায়।

### Solution 26: Reverse a Number

```python
number = int(input("Enter number: "))

original = abs(number)
reversed_number = 0

while original > 0:
    digit = original % 10
    reversed_number = reversed_number * 10 + digit
    original //= 10

if number < 0:
    reversed_number = -reversed_number

print("Reversed:", reversed_number)
```

এটি `0` এবং negative integer-ও handle করে। Integer হিসেবে reverse করলে শুরুর zero সংরক্ষিত থাকে না।

### Solution 31: Find Maximum

```python
numbers = [12, 45, 7, 89, 23]

if len(numbers) == 0:
    print("List is empty")
else:
    maximum = numbers[0]

    for number in numbers:
        if number > maximum:
            maximum = number

    print("Maximum:", maximum)
```

### Solution 34: Linear Search

```python
numbers = [10, 20, 30, 40]
target = 30

found_index = -1

for index in range(len(numbers)):
    if numbers[index] == target:
        found_index = index
        break

print("Index:", found_index)
```

Target পাওয়া গেলে `break` loop বন্ধ করে। Target না পেলে `found_index`-এর মান `-1` থাকে।

### Solution 38: Square Star Pattern

```python
for row in range(4):
    for column in range(4):
        print("*", end=" ")
    print()
```

Outer loop row নিয়ন্ত্রণ করে এবং inner loop প্রতিটি row-তে star print করে।

### Solution 45: Input Validation

```python
marks = float(input("Enter marks (0-100): "))

while marks < 0 or marks > 100:
    print("Invalid marks")
    marks = float(input("Enter marks (0-100): "))

print("Accepted:", marks)
```

এই version ধরে নেয় user numeric input দিচ্ছে। Non-numeric input handle করতে `try-except` ব্যবহার করা যেতে পারে।

### Solution 47: Menu-Driven Calculator

```python
while True:
    print("\n1. Addition")
    print("2. Subtraction")
    print("3. Multiplication")
    print("4. Division")
    print("5. Exit")

    choice = input("Choose an option: ")

    if choice == "5":
        print("Goodbye!")
        break

    if choice not in ("1", "2", "3", "4"):
        print("Invalid option")
        continue

    first = float(input("Enter first number: "))
    second = float(input("Enter second number: "))

    if choice == "1":
        print("Result:", first + second)
    elif choice == "2":
        print("Result:", first - second)
    elif choice == "3":
        print("Result:", first * second)
    elif choice == "4":
        if second == 0:
            print("Cannot divide by zero")
        else:
            print("Result:", first / second)
```

### Solution 51: Perfect Number

```python
number = int(input("Enter a positive integer: "))

if number <= 0:
    print("Please enter a positive integer.")
else:
    total = 0

    for divisor in range(1, number):
        if number % divisor == 0:
            total += divisor

    if total == number:
        print("Perfect number")
    else:
        print("Not a perfect number")
```

### Solution 60: Combine Loop Concepts

```python
numbers = [12, 7, 4, 9, 15, 20, 3]

even_sum = 0
odd_count = 0
maximum = numbers[0]

for number in numbers:
    if number % 2 == 0:
        even_sum += number
    else:
        odd_count += 1

    if number > maximum:
        maximum = number

print("Even sum:", even_sum)
print("Odd count:", odd_count)
print("Maximum:", maximum)
```

## 12. Testing Your Solutions

প্রতিটি program-এর ক্ষেত্রে সম্ভব হলে নিচের test case-গুলো বিবেচনা করো:

| Test case | কেন পরীক্ষা করবে |
|---|---|
| সাধারণ input | মূল logic ঠিক আছে কি না |
| `0` | Zero-এর special case |
| Negative input | Sign-সম্পর্কিত error |
| Empty list | Index error এড়ানো |
| Single element | Boundary case |
| Repeated values | Duplicate handling |
| Target নেই | Search-এর not-found case |
| Invalid input | Input validation |

সব test case প্রতিটি problem-এর জন্য প্রযোজ্য নয়। Problem-এর requirements অনুযায়ী উপযুক্ত test বেছে নেবে।

## 13. Common Mistakes

1. `range()`-এর stop value বাদ পড়ে—এটি মনে না রাখা।
2. `while` loop-এ variable update না করা।
3. Accumulator-এর initial value ভুল দেওয়া।
4. Counter increment করতে ভুলে যাওয়া।
5. `break` ও `continue` গুলিয়ে ফেলা।
6. Nested loop-এর indentation ভুল করা।
7. Empty list-এ `numbers[0]` ব্যবহার করা।
8. Division-এর আগে zero divisor পরীক্ষা না করা।
9. Sentinel value-কে data হিসেবে গণনা করা।
10. শুধু একটি input দিয়ে test করা।

## 14. Recommended Practice Plan

| Session | Exercises |
|---|---|
| Session 1 | 1–8: Basic loops |
| Session 2 | 9–18: Sum and counting |
| Session 3 | 19–30: Number problems |
| Session 4 | 31–37: List processing |
| Session 5 | 38–44: Nested loops and patterns |
| Session 6 | 45–50: Input and menus |
| Session 7 | 51–60: Challenge problems |

প্রতিটি problem-এর code নিজে লিখবে। আটকে গেলে প্রথমে hint দেখবে, তারপর selected solutions-এর সঙ্গে নিজের approach তুলনা করবে।

## 15. Completion Checklist

- [ ] Basic `for` ও `while` loop ব্যবহার করতে পারি।
- [ ] Sum, average ও counting problem solve করতে পারি।
- [ ] Factorial, Fibonacci ও prime checking করতে পারি।
- [ ] Digit-based problem solve করতে পারি।
- [ ] List search, maximum ও minimum বের করতে পারি।
- [ ] Nested loop দিয়ে pattern তৈরি করতে পারি।
- [ ] Menu-based program লিখতে পারি।
- [ ] Input validation ও boundary case বিবেচনা করতে পারি।
- [ ] নিজের solution test ও debug করতে পারি।

## 16. Next Topic

পরবর্তী ও এই chapter-এর শেষ topic:

`74_Chapter_Review_and_Self_Assessment.md`

এখানে Chapter 07-এর গুরুত্বপূর্ণ concept, revision checklist এবং final self-assessment থাকবে।