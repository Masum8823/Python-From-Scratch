# 57. Reversing a Number

## 1. Introduction

Reversing a Number মানে কোনো সংখ্যার digit-গুলোকে উল্টো ক্রমে সাজানো।

উদাহরণ:

| Original Number | Reversed Number |
|---:|---:|
| 1234 | 4321 |
| 567 | 765 |
| 120 | 21 |
| 908 | 809 |
| 45 | 54 |

এখানে `120` reverse করলে `021` পাওয়া গেলেও integer হিসেবে সেটি `21` হবে। কারণ integer-এর শুরুতে থাকা zero সাধারণত সংরক্ষিত থাকে না।

Python-এ `while` loop ব্যবহার করে digit একে একে বের করে একটি নতুন reversed number তৈরি করা যায়।

এই Topic-এ আমরা শিখব:

- `%` ও `//` operator দিয়ে digit বের করা
- `while` loop দিয়ে number reverse করা
- প্রতিটি ধাপের dry run
- User input ব্যবহার করা
- Zero ও negative number handle করা
- String method দিয়ে reverse করার সঙ্গে তুলনা
- Common mistakes ও practice problems

## 2. Understanding `%` and `//` Operators

Number reverse করার আগে দুটি operator বুঝতে হবে।

### Modulus Operator (`%`)

`%` operator ভাগশেষ বের করে।

```python
print(1234 % 10)
print(567 % 10)
print(120 % 10)
```

Output:

```text
4
7
0
```

কোনো positive integer-কে `10` দিয়ে ভাগ করলে `% 10` দিয়ে তার শেষ digit পাওয়া যায়।

### Floor Division Operator (`//`)

`//` operator floor division করে। Positive integer-কে `10` দিয়ে ভাগ করলে এটি শেষ digit বাদ দিয়ে বাকি অংশ দেয়।

```python
print(1234 // 10)
print(567 // 10)
print(120 // 10)
```

Output:

```text
123
56
12
```

### গুরুত্বপূর্ণ নিয়ম

| Operation | Purpose | Example |
|---|---|---|
| `number % 10` | শেষ digit বের করে | `1234 % 10 = 4` |
| `number // 10` | শেষ digit বাদ দেয় | `1234 // 10 = 123` |

Number reverse করার মূল ভিত্তি হলো এই দুটি operation।

## 3. Basic Logic of Reversing a Number

ধরি, আমাদের `1234` reverse করতে হবে।

প্রথমে:

```python
number = 1234
reversed_number = 0
```

এবার প্রতিবার তিনটি কাজ করব:

1. `number % 10` দিয়ে শেষ digit বের করব।
2. `reversed_number * 10 + digit` দিয়ে reversed number-এ digit যোগ করব।
3. `number // 10` দিয়ে original number-এর শেষ digit বাদ দেব।

Formula:

```python
digit = number % 10
reversed_number = reversed_number * 10 + digit
number = number // 10
```

এই তিনটি statement loop-এর মধ্যে বারবার চলবে।

## 4. Reversing a Number Using a `while` Loop

### Code

```python
number = 1234
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number = number // 10

print("Reversed number:", reversed_number)
```

### Output

```text
Reversed number: 4321
```

### Explanation

- `number = 1234` হলো original number।
- `reversed_number = 0` দিয়ে নতুন reversed number শুরু হয়।
- `number > 0` থাকা পর্যন্ত loop চলে।
- `number % 10` শেষ digit বের করে।
- `reversed_number * 10 + digit` নতুন digit-টিকে ডান পাশে যোগ করে।
- `number // 10` original number থেকে শেষ digit বাদ দেয়।

শেষে `number` শূন্য হলে loop বন্ধ হয়।

## 5. Understanding the Reversed Number Formula

এই statement-টি সবচেয়ে গুরুত্বপূর্ণ:

```python
reversed_number = reversed_number * 10 + digit
```

ধরি:

```python
reversed_number = 43
digit = 2
```

তাহলে:

```python
reversed_number = 43 * 10 + 2
```

অর্থাৎ:

```text
430 + 2 = 432
```

নতুন digit যোগ করার আগে আগের সংখ্যাকে `10` দিয়ে গুণ করলে তার digit-গুলো এক ঘর বামে সরে যায়। এরপর নতুন digit ডান পাশে বসে।

আরেকটি উদাহরণ:

```text
reversed_number = 432
digit = 1

432 × 10 + 1 = 4321
```

এভাবেই reversed number তৈরি হয়।

## 6. Dry Run of Reversing a Number

Code:

```python
number = 1234
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number = number // 10

print(reversed_number)
```

### Dry Run Table

| Iteration | Original `number` | `digit = number % 10` | New `reversed_number` | Updated `number` |
|---:|---:|---:|---:|---:|
| 1 | 1234 | 4 | 4 | 123 |
| 2 | 123 | 3 | 43 | 12 |
| 3 | 12 | 2 | 432 | 1 |
| 4 | 1 | 1 | 4321 | 0 |

### Final Output

```text
4321
```

প্রতিবার original number থেকে শেষ digit বের করে reversed number-এর শেষে যোগ করা হয়েছে।

## 7. Reversing a Number with User Input

এবার user-এর কাছ থেকে একটি positive integer নিয়ে reverse করি।

### Code

```python
number = int(input("Enter a positive integer: "))
reversed_number = 0

if number < 0:
    print("Please enter a non-negative integer.")
else:
    while number > 0:
        digit = number % 10
        reversed_number = reversed_number * 10 + digit
        number //= 10

    print("Reversed number:", reversed_number)
```

### Sample Input and Output

```text
Enter a positive integer: 5678
Reversed number: 8765
```

এখানে `number //= 10` হলো `number = number // 10`-এর সংক্ষিপ্ত রূপ।

**Note:** এই code-এ original `number` variable-টি loop চলাকালে পরিবর্তিত হয়। Original value-ও প্রয়োজন হলে আগে অন্য variable-এ সংরক্ষণ করে রাখতে পারো।

## 8. Reversing a Number with a `for` Loop

Number reverse করার জন্য `while` loop বেশি স্বাভাবিক, কারণ কতটি digit আছে তা আগে থেকে জানা নাও থাকতে পারে। তবে `for` loop দিয়েও করা যায়।

### Code

```python
number = 12345
reversed_number = 0

for i in range(len(str(number))):
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

print("Reversed number:", reversed_number)
```

### Output

```text
Reversed number: 54321
```

### Explanation

- `str(number)` সংখ্যাটিকে string-এ রূপান্তর করে।
- `len(str(number))` digit-এর সংখ্যা বের করে।
- `range()` সেই সংখ্যক iteration চালায়।
- প্রতিটি iteration-এ শেষ digit বের হয় এবং original number ছোট হয়।

এই পদ্ধতিতে `len()` ও `str()` ব্যবহার করা হয়েছে। শুধু loop ও arithmetic operation শেখার জন্য `while` পদ্ধতিটি বেশি সহজবোধ্য।

এই উদাহরণটি non-negative integer-এর জন্য লেখা।

## 9. Reversing Zero

যদি input `0` হয়, তাহলে:

```python
number = 0
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

print(reversed_number)
```

Output:

```text
0
```

এখানে loop একবারও চলে না, কারণ `number > 0` condition শুরুতেই False।

তবুও `reversed_number`-এর initial value `0` হওয়ায় সঠিক output পাওয়া যায়।

## 10. Reversing a Number with Trailing Zeros

ধরি, original number `1200`।

```python
number = 1200
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

print(reversed_number)
```

Output:

```text
21
```

কেন `0021` নয়?

কারণ `reversed_number` একটি integer। Integer-এর শুরুতে থাকা zero-এর আলাদা কোনো স্থানমান নেই।

যদি leading zero-সহ reversed digits সংরক্ষণ করতে হয়, তাহলে string ব্যবহার করা বেশি উপযুক্ত।

## 11. Reversing a Negative Number

আগের সাধারণ loop-এ condition ছিল:

```python
while number > 0:
```

তাই negative input সরাসরি দিলে loop চলবে না।

Negative number-এর absolute value reverse করতে চাইলে `abs()` ব্যবহার করা যায়।

### Code

```python
number = int(input("Enter an integer: "))

sign = -1 if number < 0 else 1
number = abs(number)

reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

reversed_number *= sign

print("Reversed number:", reversed_number)
```

### Sample Output

```text
Enter an integer: -123
Reversed number: -321
```

এখানে:

- `abs(number)` সংখ্যাটির absolute value নেয়।
- `sign` মূল সংখ্যাটি negative কি না মনে রাখে।
- Reverse করার পরে sign আবার প্রয়োগ করা হয়।

এটি negative integer-এর জন্য একটি ব্যবহারিক পদ্ধতি।

## 12. Reversing a Number Using String Slicing

Python-এ string slicing ব্যবহার করেও একটি সংখ্যার digit reverse করা যায়।

### Code

```python
number = 12345

reversed_number = str(number)[::-1]

print(reversed_number)
```

Output:

```text
54321
```

এখানে `[::-1]` string-টিকে উল্টো দিক থেকে নেয়।

কিন্তু মনে রাখবে, `str(number)[::-1]`-এর result একটি **string**, integer নয়।

Integer প্রয়োজন হলে:

```python
number = 12345

reversed_number = int(str(number)[::-1])

print(reversed_number)
```

Output:

```text
54321
```

তবে `number = 1200` হলে string reverse করলে `"0021"` পাওয়া যায়, কিন্তু `int("0021")` করলে `21` হয়।

**কোন পদ্ধতি কখন ব্যবহার করবে?**

- `%` ও `//` দিয়ে reverse: loop, arithmetic ও digit processing শেখার জন্য।
- String slicing দিয়ে reverse: string operation দিয়ে দ্রুত reverse করার জন্য।
- Leading zero সংরক্ষণ করতে হলে string result ব্যবহার করো।

## 13. Common Mistakes

### Mistake 1: Initializing `reversed_number` with the Original Number

ভুল:

```python
number = 123
reversed_number = number
```

এভাবে শুরু করলে reversed number-এর মধ্যে original number আগেই থেকে যায়।

সঠিক:

```python
reversed_number = 0
```

### Mistake 2: Forgetting to Multiply by 10

ভুল:

```python
reversed_number = reversed_number + digit
```

এতে digit-গুলো সঠিক স্থানমান অনুযায়ী যুক্ত হবে না।

সঠিক:

```python
reversed_number = reversed_number * 10 + digit
```

### Mistake 3: Forgetting to Remove the Last Digit

ভুল:

```python
digit = number % 10
reversed_number = reversed_number * 10 + digit
```

যদি `number` update না করা হয়, তাহলে একই digit বারবার পাওয়া যাবে এবং loop শেষ হবে না।

সঠিক:

```python
number //= 10
```

### Mistake 4: Using `/` Instead of `//`

ভুল:

```python
number = number / 10
```

`/` ব্যবহার করলে result float হয়, যেমন `123 / 10 = 12.3`। এতে digit processing জটিল হয়ে যায়।

সঠিক:

```python
number = number // 10
```

### Mistake 5: Expecting Leading Zeros in an Integer

`1200` reverse করলে integer result `21` হবে, `0021` নয়।

Leading zero প্রয়োজন হলে reversed digits-কে string হিসেবে রাখো।

### Mistake 6: Forgetting Negative Input Handling

`while number > 0` দিয়ে লেখা code negative number-এর digit process করবে না। Negative input গ্রহণ করতে চাইলে `abs()` এবং sign handling যোগ করতে হবে।

## 14. Practice Exercises

### Exercise 1

`1234` reverse করার জন্য `while` loop লিখো।

### Exercise 2

User-এর কাছ থেকে একটি integer নিয়ে reverse করো।

### Exercise 3

`1200` reverse করলে কী output হবে? কারণ ব্যাখ্যা করো।

### Exercise 4

`for` loop ব্যবহার করে `9876` reverse করো।

### Exercise 5

নিচের code-এর output নির্ণয় করো:

```python
number = 456
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

print(reversed_number)
```

### Exercise 6

নিচের code-এ ভুলটি খুঁজে বের করো:

```python
number = 123
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number + digit

print(reversed_number)
```

### Exercise 7

`% 10` ও `// 10`-এর মধ্যে পার্থক্য ব্যাখ্যা করো।

### Exercise 8

`0` reverse করার জন্য loop কতবার চলবে?

### Exercise 9

String slicing ব্যবহার করে `"Bangladesh"` reverse করো।

### Exercise 10

Negative integer `-456` reverse করে `-654` পাওয়ার জন্য program লেখো।

## 15. Practice Answer Key

### Answer 1

```python
number = 1234
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

print(reversed_number)
```

Output:

```text
4321
```

### Answer 2

```python
number = int(input("Enter an integer: "))
reversed_number = 0

if number < 0:
    print("Enter a non-negative integer.")
else:
    while number > 0:
        digit = number % 10
        reversed_number = reversed_number * 10 + digit
        number //= 10

    print(reversed_number)
```

### Answer 3

Output:

```text
21
```

কারণ reversed digits হলো `0021`, কিন্তু integer-এর শুরুতে থাকা zero সংরক্ষিত থাকে না।

### Answer 4

```python
number = 9876
reversed_number = 0

for i in range(len(str(number))):
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

print(reversed_number)
```

Output:

```text
6789
```

### Answer 5

Output:

```text
654
```

### Answer 6

এখানে দুটি ভুল আছে:

1. `reversed_number`-কে `10` দিয়ে গুণ করা হয়নি।
2. `number` থেকে শেষ digit বাদ দেওয়া হয়নি।

সঠিক code:

```python
number = 123
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

print(reversed_number)
```

Output:

```text
321
```

### Answer 7

- `number % 10` শেষ digit বের করে।
- `number // 10` positive integer-এর শেষ digit বাদ দেয়।

উদাহরণ: `123 % 10 = 3`, কিন্তু `123 // 10 = 12`।

### Answer 8

Loop একবারও চলবে না। কারণ `number > 0` condition শুরুতেই False। `reversed_number`-এর initial value `0` থাকায় output হবে `0`।

### Answer 9

```python
text = "Bangladesh"
print(text[::-1])
```

Output:

```text
hsedalgnaB
```

### Answer 10

```python
number = -456

sign = -1 if number < 0 else 1
number = abs(number)
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

reversed_number *= sign

print(reversed_number)
```

Output:

```text
-654
```

## 16. Chapter Summary

- Reversing a Number মানে digit-গুলোকে উল্টো ক্রমে সাজানো।
- `% 10` দিয়ে শেষ digit পাওয়া যায়।
- `// 10` দিয়ে positive integer-এর শেষ digit বাদ দেওয়া যায়।
- `reversed_number * 10 + digit` দিয়ে নতুন reversed number তৈরি হয়।
- `while` loop দিয়ে digit একে একে process করা যায়।
- `reversed_number` শুরুতে `0` রাখতে হয়।
- Original number-এর প্রতিটি digit process করার পর সেটিকে ছোট করতে হয়।
- Integer-এ leading zero সংরক্ষিত থাকে না।
- Negative number reverse করতে sign handling প্রয়োজন।
- String slicing `[::-1]` দিয়েও reverse করা যায়, তবে সেটি প্রথমে string result দেয়।

## 17. Completion Checklist

- [ ] `%` operator দিয়ে শেষ digit বের করতে পারি।
- [ ] `//` operator দিয়ে শেষ digit বাদ দিতে পারি।
- [ ] `while` loop দিয়ে number reverse করতে পারি।
- [ ] Reversed number-এর formula বুঝি।
- [ ] Dry run table তৈরি করতে পারি।
- [ ] User input নিয়ে reverse করতে পারি।
- [ ] Zero ও negative input handle করতে পারি।
- [ ] Integer ও string reversal-এর পার্থক্য বুঝি।
- [ ] Common mistakes শনাক্ত করতে পারি।

**Next Topic:** `58_Finding_the_Sum_of_Digits.md`