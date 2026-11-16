# 60. Palindrome Number Checking

## 1. Introduction

Palindrome Number হলো এমন একটি সংখ্যা, যেটিকে সামনে থেকে বা পেছন থেকে পড়লে একই থাকে।

উদাহরণ:

| Number | Reversed Number | Palindrome? |
|---:|---:|---|
| 121 | 121 | Yes |
| 1331 | 1331 | Yes |
| 12321 | 12321 | Yes |
| 123 | 321 | No |
| 1234 | 4321 | No |
| 4554 | 4554 | Yes |

Palindrome checking-এর মূল ধারণা খুব সহজ:

1. Original number-এর reverse তৈরি করো।
2. Reversed number-এর সঙ্গে original number তুলনা করো।
3. দুটি সমান হলে palindrome, অন্যথায় palindrome নয়।

এই Topic-এ আমরা শিখব:

- Palindrome number-এর ধারণা
- Number reverse করে palindrome check
- `while` loop ও `for` loop ব্যবহার
- Dry run table
- User input ও negative number handling
- String slicing দিয়ে palindrome check
- Common mistakes ও practice problems

## 2. Understanding a Palindrome Number

ধরি, আমাদের পরীক্ষা করতে হবে `121` palindrome কি না।

Original number:

```text
121
```

Reversed number:

```text
121
```

দুটি সমান:

```text
121 == 121
```

তাই `121` একটি palindrome number।

এবার `123` বিবেচনা করি।

Original number:

```text
123
```

Reversed number:

```text
321
```

দুটি সমান নয়:

```text
123 != 321
```

তাই `123` palindrome নয়।

**মূল নিয়ম:**

```python
original_number == reversed_number
```

এই condition True হলে সংখ্যাটি palindrome।

## 3. Logic of Palindrome Checking

Palindrome checking-এর জন্য প্রথমে number reverse করতে হবে।

ধরি:

```python
number = 121
original_number = number
reversed_number = 0
```

এখানে:

- `number` দিয়ে digit process করব।
- `original_number`-এ আসল সংখ্যাটি সংরক্ষণ করব।
- `reversed_number`-এ উল্টো সংখ্যা তৈরি করব।

প্রতিটি iteration-এ:

```python
digit = number % 10
reversed_number = reversed_number * 10 + digit
number //= 10
```

Loop শেষ হলে:

```python
original_number == reversed_number
```

দিয়ে palindrome পরীক্ষা করব।

**গুরুত্বপূর্ণ:** Original number আলাদা variable-এ রাখতে হবে, কারণ loop-এর মধ্যে `number` পরিবর্তিত হবে।

## 4. Palindrome Checking Using a `while` Loop

### Code

```python
number = 121
original_number = number
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

if original_number == reversed_number:
    print("Palindrome number")
else:
    print("Not a palindrome number")
```

### Output

```text
Palindrome number
```

### Explanation

- `original_number = number` দিয়ে original value সংরক্ষণ করা হয়।
- `reversed_number = 0` দিয়ে reverse তৈরি শুরু হয়।
- `number % 10` শেষ digit বের করে।
- `reversed_number * 10 + digit` নতুন digit যোগ করে।
- `number //= 10` শেষ digit বাদ দেয়।
- Loop শেষ হলে original ও reversed number তুলনা করা হয়।

যেহেতু `121` reverse করলেও `121` পাওয়া যায়, তাই এটি palindrome।

## 5. Checking a Non-Palindrome Number

এবার `number = 123` ধরি।

### Code

```python
number = 123
original_number = number
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

if original_number == reversed_number:
    print("Palindrome number")
else:
    print("Not a palindrome number")
```

### Output

```text
Not a palindrome number
```

কারণ:

```text
Original number: 123
Reversed number: 321
```

এখানে `123 != 321`। তাই সংখ্যাটি palindrome নয়।

## 6. Dry Run of Palindrome Checking

Code:

```python
number = 121
original_number = number
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

print(original_number == reversed_number)
```

### Dry Run Table

| Iteration | `number` | Extracted Digit | `reversed_number` | Updated `number` |
|---:|---:|---:|---:|---:|
| 1 | 121 | 1 | 1 | 12 |
| 2 | 12 | 2 | 12 | 1 |
| 3 | 1 | 1 | 121 | 0 |

### Final Comparison

```text
Original number = 121
Reversed number = 121
```

### Output

```text
True
```

তাই `121` একটি palindrome number।

## 7. Palindrome Checking with User Input

এবার user-এর কাছ থেকে একটি non-negative integer নিয়ে palindrome পরীক্ষা করি।

### Code

```python
number = int(input("Enter a non-negative integer: "))

original_number = number
reversed_number = 0

if number < 0:
    print("Negative numbers are not considered palindrome here.")
else:
    while number > 0:
        digit = number % 10
        reversed_number = reversed_number * 10 + digit
        number //= 10

    if original_number == reversed_number:
        print("Palindrome number")
    else:
        print("Not a palindrome number")
```

### Sample Output 1

```text
Enter a non-negative integer: 1331
Palindrome number
```

### Sample Output 2

```text
Enter a non-negative integer: 1234
Not a palindrome number
```

### Sample Output 3

```text
Enter a non-negative integer: 0
Palindrome number
```

এই code-এ negative number-কে palindrome হিসেবে গণনা করা হয়নি। এখানে `0`-কেও palindrome ধরা হয়েছে, কারণ `0` reverse করলেও `0` থাকে।

এই উদাহরণে ধরে নেওয়া হয়েছে user valid integer দেবেন।

## 8. Why Must We Store the Original Number?

Palindrome checking-এর সময় original number সংরক্ষণ করা গুরুত্বপূর্ণ।

ভুল উদাহরণ:

```python
number = 121
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

if number == reversed_number:
    print("Palindrome")
else:
    print("Not palindrome")
```

Output:

```text
Not palindrome
```

কেন?

Loop শেষ হওয়ার পর `number`-এর value `0` হয়ে যায়। তাই code-টি `0 == 121` পরীক্ষা করে, যা False।

### Correct Solution

```python
number = 121
original_number = number
```

Loop-এর শেষে `original_number`-এর সঙ্গে `reversed_number` তুলনা করতে হবে।

```python
if original_number == reversed_number:
    print("Palindrome")
```

## 9. Palindrome Checking Using a `for` Loop

`for` loop দিয়েও number reverse করে palindrome check করা যায়।

### Code

```python
number = 12321
original_number = number
reversed_number = 0

for i in range(len(str(number))):
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

if original_number == reversed_number:
    print("Palindrome number")
else:
    print("Not a palindrome number")
```

### Output

```text
Palindrome number
```

### Explanation

- `len(str(number))` দিয়ে digit-এর সংখ্যা বের করা হয়।
- `range()` সেই সংখ্যক iteration চালায়।
- প্রতিটি iteration-এ শেষ digit বের করে reverse তৈরি হয়।
- শেষে original ও reversed number তুলনা করা হয়।

এটি non-negative integer-এর উদাহরণ। শুধু digit process করার জন্য `while` loop সাধারণত আরও সরাসরি।

## 10. Palindrome Checking Using String Slicing

Python-এ string slicing ব্যবহার করে সহজেই palindrome check করা যায়।

### Code

```python
number = 12321
text = str(number)

if text == text[::-1]:
    print("Palindrome number")
else:
    print("Not a palindrome number")
```

### Output

```text
Palindrome number
```

### Explanation

- `str(number)` number-কে string-এ রূপান্তর করে।
- `text[::-1]` string-টিকে উল্টো করে।
- Original string ও reversed string সমান হলে palindrome।

উদাহরণ:

```python
text = "12321"

print(text[::-1])
```

Output:

```text
12321
```

### String Method কখন ব্যবহার করবে?

- Loop ও arithmetic শেখার জন্য `%` এবং `//` ব্যবহার করো।
- দ্রুত string-based palindrome checking-এর জন্য slicing ব্যবহার করতে পারো।

মনে রাখবে, string slicing মূলত character-এর ক্রম পরীক্ষা করে। Arithmetic পদ্ধতিতে integer-এর digit নিয়ে কাজ করা হয়।

## 11. Palindrome Checking for Negative Numbers

Negative number-এর ক্ষেত্রে আগে নিয়ম ঠিক করতে হবে।

যেমন:

```text
-121
```

সংখ্যাটিকে sign-সহ string হিসেবে reverse করলে:

```text
121-
```

এটি original `-121`-এর সমান নয়।

এই কারণে সাধারণভাবে negative integer-কে palindrome ধরা হয় না।

### Code

```python
number = int(input("Enter an integer: "))

if number < 0:
    print("Not a palindrome number")
else:
    text = str(number)

    if text == text[::-1]:
        print("Palindrome number")
    else:
        print("Not a palindrome number")
```

### Sample Output

```text
Enter an integer: -121
Not a palindrome number
```

এটি একটি প্রচলিত convention। কোনো problem statement ভিন্ন নিয়ম দিলে সেই নিয়ম অনুসরণ করতে হবে।

## 12. Checking Multiple Palindrome Numbers in a Range

এবার `1` থেকে `200` পর্যন্ত palindrome number print করি।

### Code

```python
for number in range(1, 201):
    original_number = number
    reversed_number = 0
    temp = number

    while temp > 0:
        digit = temp % 10
        reversed_number = reversed_number * 10 + digit
        temp //= 10

    if original_number == reversed_number:
        print(number, end=" ")
```

### Output

```text
1 2 3 4 5 6 7 8 9 11 22 33 44 55 66 77 88 99 101 111 121 131 141 151 161 171 181 191 202
```

**Output correction:** উপরের range `1` থেকে `200` পর্যন্ত, তাই `202` output-এ থাকবে না। সঠিক output-এর শেষ অংশ হলো:

```text
... 171 181 191
```

### Explanation

এখানে:

- Outer `for` loop প্রতিটি সংখ্যা নির্বাচন করে।
- `temp`-এ সংখ্যার copy রাখা হয়।
- Inner `while` loop reverse তৈরি করে।
- Original ও reversed number সমান হলে সংখ্যাটি print হয়।

`temp` ব্যবহার করায় outer loop-এর `number` পরিবর্তিত হয় না।

## 13. Common Mistakes

### Mistake 1: Not Storing the Original Number

Loop শেষে original working variable `0` হয়ে যায়। তাই original number আলাদা variable-এ রাখতে হবে।

### Mistake 2: Forgetting to Initialize `reversed_number`

সঠিক initialization:

```python
reversed_number = 0
```

### Mistake 3: Forgetting `number //= 10`

এটি বাদ দিলে একই digit বারবার process হবে এবং `while` loop অনন্তকাল চলতে পারে।

### Mistake 4: Incorrect Reverse Formula

ভুল:

```python
reversed_number = reversed_number + digit
```

সঠিক:

```python
reversed_number = reversed_number * 10 + digit
```

### Mistake 5: Treating Every Number as a Palindrome

সব সংখ্যা palindrome নয়। Original ও reversed number তুলনা করতে হবে।

### Mistake 6: Ignoring Zero and Negative Numbers

- `0` reverse করলেও `0` হয়, তাই এটিকে palindrome ধরা যায়।
- Negative number-এর ক্ষেত্রে সাধারণ convention অনুযায়ী palindrome ধরা হয় না।

### Mistake 7: Forgetting to Reset Variables in a Range

একাধিক সংখ্যা পরীক্ষা করার সময় প্রতিটি নতুন সংখ্যার জন্য `reversed_number = 0` করতে হবে। নইলে আগের সংখ্যার result পরের calculation-এ থেকে যেতে পারে।

## 14. Practice Exercises

### Exercise 1

`121` palindrome কি না, তা `while` loop দিয়ে পরীক্ষা করো।

### Exercise 2

User-এর কাছ থেকে একটি non-negative integer নিয়ে palindrome check করো।

### Exercise 3

`1234` palindrome নয় কেন, ব্যাখ্যা করো।

### Exercise 4

নিচের code-এর output নির্ণয় করো:

```python
number = 1331
original_number = number
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

print(original_number == reversed_number)
```

### Exercise 5

String slicing ব্যবহার করে `12321` palindrome কি না পরীক্ষা করো।

### Exercise 6

নিচের code-এ ভুলটি খুঁজে বের করো:

```python
number = 121
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

print(number == reversed_number)
```

### Exercise 7

`0` palindrome কি না? কারণ ব্যাখ্যা করো।

### Exercise 8

`-121`-কে এই Topic-এর convention অনুযায়ী palindrome ধরা হবে কি?

### Exercise 9

একটি loop ব্যবহার করে `1` থেকে `100` পর্যন্ত সব palindrome number print করো।

### Exercise 10

Palindrome checking-এ `original_number` ও `temp` আলাদা variable হিসেবে রাখার সুবিধা কী?

## 15. Practice Answer Key

### Answer 1

```python
number = 121
original_number = number
reversed_number = 0

while number > 0:
    digit = number % 10
    reversed_number = reversed_number * 10 + digit
    number //= 10

print(original_number == reversed_number)
```

Output:

```text
True
```

### Answer 2

```python
number = int(input("Enter a non-negative integer: "))

if number < 0:
    print("Invalid input")
else:
    original_number = number
    reversed_number = 0

    while number > 0:
        digit = number % 10
        reversed_number = reversed_number * 10 + digit
        number //= 10

    if original_number == reversed_number:
        print("Palindrome number")
    else:
        print("Not a palindrome number")
```

### Answer 3

`1234` reverse করলে `4321` হয়। যেহেতু `1234 != 4321`, তাই এটি palindrome নয়।

### Answer 4

Output:

```text
True
```

কারণ `1331` reverse করলেও `1331` পাওয়া যায়।

### Answer 5

```python
text = "12321"

if text == text[::-1]:
    print("Palindrome")
else:
    print("Not palindrome")
```

Output:

```text
Palindrome
```

### Answer 6

সমস্যা হলো loop শেষে `number`-এর value `0` হয়ে গেছে। তাই `number == reversed_number` দিয়ে original number পরীক্ষা করা হচ্ছে না।

সঠিকভাবে শুরুতে `original_number = number` রাখতে হবে এবং শেষে `original_number == reversed_number` পরীক্ষা করতে হবে।

### Answer 7

হ্যাঁ, `0` palindrome। কারণ reverse করলেও `0`-ই থাকে।

### Answer 8

না। এই Topic-এ negative number-কে palindrome ধরা হচ্ছে না। তাই `-121` palindrome নয়।

### Answer 9

```python
for number in range(1, 101):
    original_number = number
    temp = number
    reversed_number = 0

    while temp > 0:
        digit = temp % 10
        reversed_number = reversed_number * 10 + digit
        temp //= 10

    if original_number == reversed_number:
        print(number, end=" ")
```

Output:

```text
1 2 3 4 5 6 7 8 9 11 22 33 44 55 66 77 88 99
```

### Answer 10

`original_number`-এ আসল সংখ্যাটি সংরক্ষিত থাকে, যাতে reverse করার পরে তুলনা করা যায়। `temp`-এ কাজ করলে original number পরিবর্তিত হয় না। এতে একই original number অন্য calculation-এও ব্যবহার করা যায়।

## 16. Chapter Summary

- Palindrome number সামনে ও পেছন থেকে একই থাকে।
- Number reverse করে palindrome পরীক্ষা করা যায়।
- Original number আলাদা variable-এ রাখতে হয়।
- `% 10` দিয়ে শেষ digit বের করা যায়।
- `// 10` দিয়ে শেষ digit বাদ দেওয়া যায়।
- `reversed_number * 10 + digit` দিয়ে reverse তৈরি হয়।
- `while` ও `for` loop দিয়ে palindrome check করা যায়।
- String slicing `[::-1]` দিয়েও palindrome check করা যায়।
- `0` palindrome, কিন্তু এই Topic-এর convention অনুযায়ী negative number palindrome নয়।
- Range-এর মধ্যে palindrome বের করতে nested loops ব্যবহার করা যায়।

## 17. Completion Checklist

- [ ] Palindrome number-এর সংজ্ঞা বুঝি।
- [ ] `while` loop দিয়ে number reverse করতে পারি।
- [ ] Original number সংরক্ষণ করতে পারি।
- [ ] Dry run table তৈরি করতে পারি।
- [ ] User input নিয়ে palindrome check করতে পারি।
- [ ] String slicing দিয়ে palindrome check করতে পারি।
- [ ] Zero ও negative number handle করতে পারি।
- [ ] Range-এর মধ্যে palindrome number print করতে পারি।
- [ ] Common mistakes শনাক্ত করতে পারি।

**Next Topic:** `61_Searching_Using_Loops.md`