# 54. Factorial Using Loops

## 1. Introduction

Factorial হলো কোনো non-negative integer-এর চেয়ে ছোট বা সমান সব positive integer-এর গুণফল।

Factorial প্রকাশ করতে `!` চিহ্ন ব্যবহার করা হয়।

উদাহরণ:

- `3! = 3 × 2 × 1 = 6`
- `4! = 4 × 3 × 2 × 1 = 24`
- `5! = 5 × 4 × 3 × 2 × 1 = 120`

এখানে `!`-কে factorial symbol বলা হয়।

Python-এ loop ব্যবহার করে factorial বের করা যায়। এর জন্য একটি variable-এ গুণফল জমা রাখতে হয়।

এই Topic-এ আমরা শিখব:

- Factorial-এর ধারণা ও formula
- `for` loop দিয়ে factorial
- `while` loop দিয়ে factorial
- User input ব্যবহার করা
- Dry run ও step-by-step execution
- `0! = 1` কেন
- Input validation
- Common mistakes ও practice problems

## 2. Understanding Factorial

কোনো non-negative integer `n`-এর factorial হলো:

\[
n! = n \times (n-1) \times (n-2) \times \cdots \times 1
\]

উদাহরণ:

\[
5! = 5 \times 4 \times 3 \times 2 \times 1 = 120
\]

আরও কয়েকটি উদাহরণ:

| Number | Factorial | Result |
|---:|---|---:|
| 0 | \(0!\) | 1 |
| 1 | \(1!\) | 1 |
| 2 | \(2 \times 1\) | 2 |
| 3 | \(3 \times 2 \times 1\) | 6 |
| 4 | \(4 \times 3 \times 2 \times 1\) | 24 |
| 5 | \(5 \times 4 \times 3 \times 2 \times 1\) | 120 |

**গুরুত্বপূর্ণ:** Factorial সাধারণত non-negative integer-এর জন্য সংজ্ঞায়িত। এই অধ্যায়ের code-গুলোও সেই input ধরে কাজ করবে।

## 3. Why Do We Need a Loop?

ধরা যাক, আমাদের `5!` বের করতে হবে।

আমরা সরাসরি লিখতে পারি:

```python
factorial = 5 * 4 * 3 * 2 * 1
print(factorial)
```

Output:

```text
120
```

কিন্তু user যদি ১০, ২০ বা অন্য কোনো সংখ্যা দেন, তাহলে প্রতিবার multiplication আলাদাভাবে লেখা সুবিধাজনক নয়।

Loop ব্যবহার করলে একই কাজ স্বয়ংক্রিয়ভাবে করা যায়।

## 4. Factorial Using a `for` Loop

এবার `for` loop দিয়ে ৫-এর factorial বের করি।

### Code

```python
number = 5
factorial = 1

for i in range(1, number + 1):
    factorial *= i

print("Factorial:", factorial)
```

### Output

```text
Factorial: 120
```

### Explanation

**Step 1:** `number = 5` দিয়ে যে সংখ্যার factorial বের করব, সেটি নির্ধারণ করা হয়েছে।

**Step 2:** `factorial = 1` দিয়ে accumulator initialize করা হয়েছে।

**Step 3:** `range(1, number + 1)` থেকে ১, ২, ৩, ৪, ৫ পাওয়া যায়।

**Step 4:** প্রতিবার `factorial *= i` দিয়ে বর্তমান গুণফলকে `i` দিয়ে গুণ করা হয়।

**Step 5:** Loop শেষ হলে factorial-এর final result print হয়।

এখানে:

```python
factorial *= i
```

এর অর্থ:

```python
factorial = factorial * i
```

## 5. Dry Run of Factorial

নিচের code-টি বিবেচনা করি:

```python
number = 5
factorial = 1

for i in range(1, number + 1):
    factorial *= i

print(factorial)
```

### Dry Run Table

| Iteration | `i` | Previous factorial | New factorial |
|---:|---:|---:|---:|
| 1 | 1 | 1 | 1 |
| 2 | 2 | 1 | 2 |
| 3 | 3 | 2 | 6 |
| 4 | 4 | 6 | 24 |
| 5 | 5 | 24 | 120 |

### Final Output

```text
120
```

### কীভাবে হিসাব হলো?

প্রথমে:

`factorial = 1 × 1 = 1`

দ্বিতীয়বার:

`factorial = 1 × 2 = 2`

তৃতীয়বার:

`factorial = 2 × 3 = 6`

চতুর্থবার:

`factorial = 6 × 4 = 24`

পঞ্চমবার:

`factorial = 24 × 5 = 120`

সুতরাং, `5! = 120`।

## 6. Why Initialize Factorial with 1?

Factorial বের করার সময়:

```python
factorial = 1
```

ব্যবহার করা হয়।

কেন `0` নয়?

যদি লিখি:

```python
factorial = 0

for i in range(1, 6):
    factorial *= i

print(factorial)
```

Output:

```text
0
```

কারণ, শূন্যকে যেকোনো সংখ্যা দিয়ে গুণ করলে ফলাফল শূন্যই থাকে।

Factorial বের করতে multiplication-এর identity element, অর্থাৎ `1` দিয়ে শুরু করতে হয়।

তাই:

```python
factorial = 1
```

সঠিক initialization।

## 7. Factorial of Zero

Mathematics অনুযায়ী:

\[
0! = 1
\]

এটি factorial-এর একটি বিশেষ নিয়ম।

আমাদের আগের code-টিই `number = 0`-এর জন্য সঠিক ফল দেয়:

```python
number = 0
factorial = 1

for i in range(1, number + 1):
    factorial *= i

print(factorial)
```

Output:

```text
1
```

কারণ `range(1, 1)` খালি range। Loop একবারও চলে না এবং `factorial`-এর মান `1`-ই থাকে।

একইভাবে `1! = 1`।

## 8. Factorial Using a `while` Loop

এবার `while` loop দিয়ে factorial বের করি।

### Code

```python
number = 5
factorial = 1
i = 1

while i <= number:
    factorial *= i
    i += 1

print("Factorial:", factorial)
```

### Output

```text
Factorial: 120
```

### Explanation

- `number = 5` factorial-এর target নির্ধারণ করে।
- `factorial = 1` গুণফল জমা রাখে।
- `i = 1` দিয়ে counter শুরু হয়।
- `while i <= number` condition পরীক্ষা করে।
- `factorial *= i` বর্তমান গুণফল update করে।
- `i += 1` পরবর্তী সংখ্যায় নিয়ে যায়।

Condition মিথ্যা হলে loop শেষ হয়।

**মনে রাখবে:** `i += 1` বাদ দিলে loop অনন্তকাল চলতে পারে।

## 9. Taking User Input

এবার user-এর দেওয়া সংখ্যার factorial বের করি।

### Code

```python
number = int(input("Enter a non-negative integer: "))
factorial = 1

for i in range(1, number + 1):
    factorial *= i

print("Factorial:", factorial)
```

### Sample Input and Output

```text
Enter a non-negative integer: 6
Factorial: 720
```

কারণ:

\[
6! = 6 \times 5 \times 4 \times 3 \times 2 \times 1 = 720
\]

এই code-এ ধরে নেওয়া হয়েছে যে user একটি valid non-negative integer দেবেন। Negative input-এর জন্য validation যোগ করা প্রয়োজন।

## 10. Validating Factorial Input

Factorial-এর জন্য negative integer গ্রহণ করা যাবে না। তাই input validation করা উচিত।

### Code

```python
number = int(input("Enter a non-negative integer: "))

if number < 0:
    print("Factorial is not defined for negative integers.")
else:
    factorial = 1

    for i in range(1, number + 1):
        factorial *= i

    print("Factorial:", factorial)
```

### Sample Output 1

```text
Enter a non-negative integer: 5
Factorial: 120
```

### Sample Output 2

```text
Enter a non-negative integer: -3
Factorial is not defined for negative integers.
```

এখানে negative input-এর ক্ষেত্রে factorial calculation করা হয় না।

**Note:** `int(input())`-এ user যদি `"abc"` বা `"2.5"` দেন, তাহলে `ValueError` হবে। সেটি সামলাতে পরবর্তী সময়ে `try-except` শেখা প্রয়োজন।

## 11. Factorial of Different Numbers

নিচের code দিয়ে বিভিন্ন সংখ্যার factorial বের করা যায়:

```python
for number in range(6):
    factorial = 1

    for i in range(1, number + 1):
        factorial *= i

    print(number, "! =", factorial)
```

### Output

```text
0 ! = 1
1 ! = 1
2 ! = 2
3 ! = 6
4 ! = 24
5 ! = 120
```

### Explanation

- Outer loop `number`-এর মান ০ থেকে ৫ পর্যন্ত নেয়।
- প্রতিটি নতুন সংখ্যার জন্য `factorial = 1` করা হয়।
- Inner loop সেই সংখ্যার factorial হিসাব করে।
- তারপর result print হয়।

**গুরুত্বপূর্ণ:** `factorial = 1` outer loop-এর ভেতরে রাখা হয়েছে, যাতে প্রতিটি সংখ্যার calculation নতুন করে শুরু হয়।

## 12. Factorial Using a Decreasing Loop

Factorial বের করার জন্য counter-কে বড় সংখ্যা থেকে ছোট সংখ্যার দিকেও চালানো যায়।

### Code

```python
number = 5
factorial = 1

for i in range(number, 0, -1):
    factorial *= i

print("Factorial:", factorial)
```

### Output

```text
Factorial: 120
```

এখানে `range(5, 0, -1)` থেকে ৫, ৪, ৩, ২, ১ পাওয়া যায়।

তাই:

`5 × 4 × 3 × 2 × 1 = 120`

Ascending বা descending—দুইভাবেই factorial বের করা যায়।

## 13. Factorial with a `while` Loop in Decreasing Order

```python
number = 5
factorial = 1

while number > 0:
    factorial *= number
    number -= 1

print("Factorial:", factorial)
```

Output:

```text
Factorial: 120
```

এখানে প্রতিবার `number` এক করে কমে।

- প্রথমে `5`
- তারপর `4`
- তারপর `3`
- তারপর `2`
- তারপর `1`

`number` শূন্য হলে condition মিথ্যা হয় এবং loop শেষ হয়।

এই code-এ `number` variable-এর original value পরিবর্তিত হয়ে যায়।

## 14. Common Mistakes

### Mistake 1: Initializing Factorial with Zero

ভুল:

```python
factorial = 0
```

সঠিক:

```python
factorial = 1
```

কারণ শূন্য দিয়ে শুরু করলে সব multiplication-এর ফল শূন্য হবে।

### Mistake 2: Using the Wrong Range

ভুল:

```python
for i in range(1, number):
    factorial *= i
```

`range()`-এর stop value অন্তর্ভুক্ত হয় না। তাই এই code-এ `number` নিজেই বাদ পড়ে যায়।

সঠিক:

```python
for i in range(1, number + 1):
    factorial *= i
```

### Mistake 3: Forgetting to Update the Counter

ভুল:

```python
i = 1

while i <= 5:
    factorial *= i
```

এখানে `i` বাড়ছে না, তাই loop শেষ হবে না।

সঠিক:

```python
i = 1
factorial = 1

while i <= 5:
    factorial *= i
    i += 1
```

### Mistake 4: Resetting Factorial Inside the Loop

ভুল:

```python
factorial = 1

for i in range(1, 6):
    factorial = 1
    factorial *= i

print(factorial)
```

এখানে প্রতিবার `factorial` আবার `1` হয়ে যায়। ফলে সঠিক গুণফল জমা থাকে না।

সঠিক:

```python
factorial = 1

for i in range(1, 6):
    factorial *= i

print(factorial)
```

### Mistake 5: Ignoring Negative Numbers

Negative integer-এর জন্য এই সাধারণ factorial algorithm ব্যবহার করা উচিত নয়।

Input validation দিয়ে নিশ্চিত করতে হবে যে `number >= 0`।

## 15. Practice Exercises

### Exercise 1

`for` loop ব্যবহার করে ৪-এর factorial বের করো।

### Exercise 2

`while` loop ব্যবহার করে ৬-এর factorial বের করো।

### Exercise 3

User-এর কাছ থেকে একটি non-negative integer নিয়ে factorial বের করো।

### Exercise 4

০ থেকে ৭ পর্যন্ত প্রতিটি সংখ্যার factorial print করো।

### Exercise 5

নিচের code-এর output নির্ণয় করো:

```python
factorial = 1

for i in range(1, 5):
    factorial *= i

print(factorial)
```

### Exercise 6

নিচের code-এ ভুলটি খুঁজে বের করো:

```python
number = 5
factorial = 0

for i in range(1, number + 1):
    factorial *= i

print(factorial)
```

### Exercise 7

নিচের code-এর output নির্ণয় করো:

```python
number = 4
factorial = 1

while number > 1:
    factorial *= number
    number -= 1

print(factorial)
```

### Exercise 8

`0! = 1` কেন, তা নিজের ভাষায় ব্যাখ্যা করো।

### Exercise 9

User negative integer দিলে factorial calculation বন্ধ করার জন্য validation যোগ করো।

### Exercise 10

`for` loop ব্যবহার করে descending order-এ একটি সংখ্যার factorial বের করো।

## 16. Practice Answer Key

### Answer 1

```python
factorial = 1

for i in range(1, 5):
    factorial *= i

print(factorial)
```

Output:

```text
24
```

### Answer 2

```python
number = 6
factorial = 1
i = 1

while i <= number:
    factorial *= i
    i += 1

print(factorial)
```

Output:

```text
720
```

### Answer 3

```python
number = int(input("Enter a non-negative integer: "))

if number < 0:
    print("Invalid input")
else:
    factorial = 1

    for i in range(1, number + 1):
        factorial *= i

    print(factorial)
```

### Answer 4

```python
for number in range(8):
    factorial = 1

    for i in range(1, number + 1):
        factorial *= i

    print(number, "! =", factorial)
```

Output:

```text
0 ! = 1
1 ! = 1
2 ! = 2
3 ! = 6
4 ! = 24
5 ! = 120
6 ! = 720
7 ! = 5040
```

### Answer 5

Output:

```text
24
```

কারণ `4! = 4 × 3 × 2 × 1 = 24`।

### Answer 6

সমস্যা হলো `factorial = 0`। সঠিক initialization:

```python
factorial = 1
```

### Answer 7

Output:

```text
24
```

কারণ calculation হয় `4 × 3 × 2 = 24`। `number` এক হয়ে গেলে loop শেষ হয়; এখানে `1` দিয়ে গুণ না করলেও ফল পরিবর্তিত হয় না।

### Answer 8

`0! = 1` হলো factorial-এর গাণিতিক সংজ্ঞা। Loop-based code-এ `factorial = 1` দিয়ে শুরু করলে `0`-এর জন্য loop চলে না এবং result `1` থাকে।

### Answer 9

```python
number = int(input("Enter a non-negative integer: "))

if number < 0:
    print("Negative numbers are not allowed.")
else:
    factorial = 1

    for i in range(1, number + 1):
        factorial *= i

    print(factorial)
```

### Answer 10

```python
number = 5
factorial = 1

for i in range(number, 0, -1):
    factorial *= i

print(factorial)
```

Output:

```text
120
```

## 17. Chapter Summary

- Factorial হলো একটি non-negative integer থেকে ১ পর্যন্ত সব positive integer-এর গুণফল।
- `n! = n × (n-1) × ... × 1`।
- Factorial বের করতে `factorial = 1` দিয়ে শুরু করতে হয়।
- `for` ও `while` loop—দুইভাবেই factorial বের করা যায়।
- `range(1, number + 1)` ব্যবহার করলে `number`-ও calculation-এ অন্তর্ভুক্ত হয়।
- `0! = 1` এবং `1! = 1`।
- Negative integer-এর জন্য input validation করা প্রয়োজন।
- বড় integer-এর factorial খুব দ্রুত বড় হয়, যদিও Python integer বড় মান ধারণ করতে পারে।
- Loop-এর counter update ও initialization সঠিক রাখা জরুরি।

## 18. Completion Checklist

- [ ] Factorial-এর ধারণা বুঝি।
- [ ] `for` loop দিয়ে factorial বের করতে পারি।
- [ ] `while` loop দিয়ে factorial বের করতে পারি।
- [ ] User input নিতে পারি।
- [ ] Negative input validate করতে পারি।
- [ ] Factorial-এর dry run করতে পারি।
- [ ] `0! = 1` ব্যাখ্যা করতে পারি।
- [ ] Common loop mistakes শনাক্ত করতে পারি।
- [ ] একাধিক সংখ্যার factorial nested loop দিয়ে বের করতে পারি।

**Next Topic:** `55_Fibonacci_Series_Using_Loops.md`