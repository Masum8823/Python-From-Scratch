# 71. Loop Performance Basics

## 1. Introduction

Loop performance বলতে বোঝায়, একটি loop নির্দিষ্ট কাজ সম্পন্ন করতে কতটা সময় ও computational resources ব্যবহার করে।

একটি loop সঠিক output দিলেও সেটি অপ্রয়োজনীয়ভাবে অনেকবার চললে program ধীর হতে পারে।

উদাহরণ:

```python
for number in range(1, 6):
    print(number)
```

এই loop পাঁচবার চলে।

অন্যদিকে:

```python
for number in range(1, 1000001):
    pass
```

এই loop এক মিলিয়ন বার চলে। এখানে কোনো meaningful কাজ করা হচ্ছে না, তবুও loop অনেক iteration সম্পন্ন করে।

**মূল ধারণা:** Loop performance উন্নত করতে হলে কাজের সংখ্যা, iteration-এর পরিমাণ এবং প্রতিটি iteration-এ কী কাজ হচ্ছে, তা বুঝতে হবে।

## 2. Why Loop Performance Matters

Loop performance গুরুত্বপূর্ণ, কারণ:

- বড় dataset process করতে কম সময় লাগে।
- অপ্রয়োজনীয় computation কমানো যায়।
- Program দ্রুত response দিতে পারে।
- Nested loop-এর খরচ বোঝা যায়।
- বড় problem সমাধানের উপযুক্ত algorithm নির্বাচন করা যায়।

ছোট program-এ performance-এর পার্থক্য বোঝা কঠিন হতে পারে। কিন্তু input বড় হলে একই পার্থক্য গুরুত্বপূর্ণ হয়ে উঠতে পারে।

## 3. Number of Iterations

Loop কতবার চলে, তা performance বোঝার একটি গুরুত্বপূর্ণ অংশ।

### Example 1: Five Iterations

```python
for number in range(1, 6):
    print(number)
```

এখানে মোট ৫টি iteration হয়।

### Example 2: One Hundred Iterations

```python
for number in range(100):
    pass
```

এখানে মোট ১০০টি iteration হয়।

### Example 3: One Thousand Iterations

```python
for number in range(1000):
    pass
```

এখানে মোট ১,০০০টি iteration হয়।

একই ধরনের কাজ হলে সাধারণভাবে iteration বাড়ার সঙ্গে মোট কাজের পরিমাণও বাড়ে।

তবে শুধু iteration-এর সংখ্যা দিয়ে সম্পূর্ণ performance নির্ধারণ করা যায় না। প্রতিটি iteration কতটা ব্যয়বহুল, সেটিও গুরুত্বপূর্ণ।

## 4. Work Performed in Each Iteration

দুটি loop-এর iteration সংখ্যা সমান হলেও তাদের execution time আলাদা হতে পারে।

### Loop A

```python
for number in range(1000):
    total = number + 1
```

### Loop B

```python
for number in range(1000):
    total = number ** 100
```

দুটি loop-ই ১,০০০ বার চলে। কিন্তু প্রতিটি iteration-এর operation আলাদা।

সাধারণভাবে বড় বা জটিল computation-এর খরচ সাধারণ arithmetic operation-এর তুলনায় বেশি হতে পারে। তবে বাস্তব সময় Python implementation, processor এবং operation-এর ওপর নির্ভর করে।

**মনে রাখবে:** Performance বিশ্লেষণে iteration-এর সংখ্যা এবং প্রতি iteration-এর কাজ—দুটিই বিবেচনা করতে হবে।

## 5. Introduction to Time Complexity

Time complexity হলো input size বাড়ার সঙ্গে algorithm-এর কাজের পরিমাণ কীভাবে বাড়ে, তার একটি বর্ণনা।

এটি সাধারণত Big O notation দিয়ে প্রকাশ করা হয়।

এখানে আমরা কয়েকটি basic complexity শিখব।

| Complexity | নাম | সাধারণ উদাহরণ |
|---|---|---|
| \(O(1)\) | Constant | নির্দিষ্ট index-এর একটি element access |
| \(O(n)\) | Linear | একটি list-এর সব element একবার দেখা |
| \(O(n^2)\) | Quadratic | প্রতিটি element-এর জন্য পুরো list scan করা |
| \(O(\log n)\) | Logarithmic | প্রতি ধাপে problem-এর search space অর্ধেক করা |

এগুলো algorithm-এর growth বোঝায়। বাস্তব execution time সরাসরি কত সেকেন্ড হবে, তা বলে না।

## 6. Single Loop and Linear Growth — O(n)

একটি list-এর প্রতিটি element একবার process করলে কাজের পরিমাণ সাধারণত list-এর size-এর সঙ্গে সরলরৈখিকভাবে বাড়ে।

```python
numbers = [10, 20, 30, 40, 50]

for number in numbers:
    print(number)
```

যদি list-এ \(n\)টি element থাকে, তাহলে loop \(n\)টি iteration করে।

তাই এই loop-এর time complexity:

\[
O(n)
\]

### Example

| Number of elements | Iterations |
|---:|---:|
| 5 | 5 |
| 10 | 10 |
| 100 | 100 |
| 1,000 | 1,000 |

Input দ্বিগুণ হলে এই loop-এর iteration-ও দ্বিগুণ হয়।

## 7. Nested Loops and Quadratic Growth — O(n²)

একটি loop-এর ভেতরে আরেকটি loop থাকলে iteration সংখ্যা দ্রুত বাড়তে পারে।

### Example

```python
n = 4

for row in range(n):
    for column in range(n):
        print(row, column)
```

Outer loop চারবার চলে। প্রতিবার inner loop চারবার চলে।

মোট inner-loop execution:

\[
4 \times 4 = 16
\]

সাধারণভাবে দুইটি nested loop যদি প্রত্যেকটি \(n\) বার চলে, তাহলে মোট iteration:

\[
n \times n = n^2
\]

তাই time complexity:

\[
O(n^2)
\]

### Iteration Comparison

| \(n\) | Single loop: \(n\) | Nested loop: \(n^2\) |
|---:|---:|---:|
| 5 | 5 | 25 |
| 10 | 10 | 100 |
| 100 | 100 | 10,000 |
| 1,000 | 1,000 | 1,000,000 |

এই কারণেই বড় input-এর ক্ষেত্রে nested loop performance-এর ওপর বেশি প্রভাব ফেলতে পারে।

**Important:** সব nested loop-এর complexity \(O(n^2)\) নয়। Inner loop কতবার চলে এবং input-এর সঙ্গে তার iteration কীভাবে বাড়ে, তার ওপর complexity নির্ভর করে।

## 8. Nested Loops Do Not Always Mean O(n²)

নিচের উদাহরণটি দেখো:

```python
for number in range(5):
    for value in range(3):
        print(number, value)
```

Outer loop পাঁচবার এবং inner loop তিনবার চলে।

মোট iteration:

\[
5 \times 3 = 15
\]

যদি outer loop \(n\) বার এবং inner loop সবসময় নির্দিষ্ট তিনবার চলে, তাহলে মোট কাজ \(3n\) হবে।

Big O notation-এ constant factor বাদ দেওয়া হয়। তাই complexity:

\[
O(n)
\]

অতএব, nested loop দেখেই \(O(n^2)\) ধরে নেওয়া ঠিক নয়।

## 9. Sequential Loops

একটির পরে আরেকটি loop থাকলে তাদের কাজের পরিমাণ সাধারণত যোগ করা হয়।

```python
n = 5

for number in range(n):
    print(number)

for number in range(n):
    print(number * 2)
```

প্রথম loop \(n\) বার এবং দ্বিতীয় loop-ও \(n\) বার চলে।

মোট কাজ:

\[
n+n=2n
\]

Big O notation-এ constant factor বাদ দিলে:

\[
O(n)
\]

**মনে রাখবে:** Sequential loop-এর complexity সাধারণত যোগ হয়; nested loop-এর ক্ষেত্রে iteration-এর সংখ্যা গুণ হতে পারে।

## 10. Avoid Repeating Unnecessary Calculations

একই calculation loop-এর ভেতরে বারবার করা হলে অপ্রয়োজনীয় কাজ বাড়তে পারে।

### Less Efficient Example

```python
numbers = [10, 20, 30, 40, 50]

for index in range(len(numbers)):
    print(len(numbers), numbers[index])
```

এখানে প্রতিবার `len(numbers)` লেখা হয়েছে।

### Clearer Example

```python
numbers = [10, 20, 30, 40, 50]
number_count = len(numbers)

for index in range(number_count):
    print(number_count, numbers[index])
```

দ্বিতীয় code-এ list-এর length একবার হিসাব করা হয়েছে।

তবে Python-এর built-in `len()` সাধারণ built-in collection-এর ক্ষেত্রে constant-time operation। তাই এই উদাহরণে performance improvement সাধারণত খুব সামান্য হতে পারে। মূল শিক্ষা হলো, ব্যয়বহুল calculation বারবার করা এড়িয়ে চলা।

## 11. Use Direct Iteration When Possible

List-এর element শুধু পড়তে হলে index ব্যবহার না করে direct iteration করা সহজ।

### Index-Based Loop

```python
numbers = [10, 20, 30, 40]

for index in range(len(numbers)):
    print(numbers[index])
```

### Direct Iteration

```python
numbers = [10, 20, 30, 40]

for number in numbers:
    print(number)
```

দুটি loop-এর time complexity সাধারণত \(O(n)\)।

Direct iteration code-কে সহজ করে এবং অপ্রয়োজনীয় indexing কমায়। তবে এটি সব ক্ষেত্রে বড় performance improvement নিশ্চিত করে না।

## 12. Use `break` to Stop Unnecessary Searching

কোনো item পাওয়া গেলে আর search করার প্রয়োজন না থাকলে `break` ব্যবহার করা যায়।

### Without `break`

```python
numbers = [10, 20, 30, 40, 50]
target = 30

for number in numbers:
    if number == target:
        print("Found")
```

এখানে target পাওয়া গেলেও loop বাকি element-গুলো পরীক্ষা করে।

### With `break`

```python
numbers = [10, 20, 30, 40, 50]
target = 30

for number in numbers:
    if number == target:
        print("Found")
        break
```

এখানে target পাওয়া গেলে loop বন্ধ হয়ে যায়।

Linear search-এর ক্ষেত্রে:

- Best case: \(O(1)\), প্রথম element-এই target পাওয়া গেলে।
- Worst case: \(O(n)\), target শেষ দিকে থাকলে বা না থাকলে।

`break` ব্যবহার করলে কিছু input-এর ক্ষেত্রে কাজ কমতে পারে, কিন্তু worst-case complexity এখনও \(O(n)\)।

## 13. Avoid Unnecessary Nested Loops

কোনো problem সমাধানে nested loop ব্যবহার করার আগে চিন্তা করবে, একই কাজ কম iteration-এ করা সম্ভব কি না।

### Example: Duplicate Pair Checking

```python
numbers = [1, 2, 3, 4]

for first in numbers:
    for second in numbers:
        print(first, second)
```

এখানে সব সম্ভাব্য ordered pair তৈরি করা হচ্ছে। চারটি element-এর জন্য মোট:

\[
4 \times 4 = 16
\]

টি pair তৈরি হয়।

যদি problem-এ সত্যিই সব ordered pair প্রয়োজন হয়, তাহলে এই nested loop যৌক্তিক।

কিন্তু যদি শুধু list-এর element print করাই উদ্দেশ্য হয়, তাহলে:

```python
for number in numbers:
    print(number)
```

যথেষ্ট। এতে চারটি iteration হয়।

**Rule:** Nested loop বাদ দেওয়ার আগে নিশ্চিত হবে, problem-এর প্রয়োজনীয় কাজ বাদ পড়ে যাচ্ছে না।

## 14. Use Built-in Functions When Appropriate

Python-এর built-in function অনেক সাধারণ কাজ সহজে করতে পারে।

### Manual Sum

```python
numbers = [10, 20, 30, 40]
total = 0

for number in numbers:
    total += number

print(total)
```

### Using `sum()`

```python
numbers = [10, 20, 30, 40]

total = sum(numbers)

print(total)
```

দুটি code-এর output:

```text
100
```

`sum()` ব্যবহার করলে code ছোট ও readable হয়। এটি সাধারণভাবে iterable-এর element-গুলো process করে, তাই মোট কাজ list-এর size-এর সঙ্গে বাড়ে।

Built-in function সব সময় যেকোনো custom loop-এর চেয়ে দ্রুত হবে—এমন নিশ্চয়তা নেই। উপযুক্ত function ব্যবহার করবে readability, correctness এবং প্রয়োজনীয় performance বিবেচনা করে।

## 15. Space Complexity Basics

Space complexity বোঝায়, input size বাড়ার সঙ্গে algorithm-এর অতিরিক্ত memory ব্যবহারের পরিমাণ কীভাবে বাড়ে।

### Example 1: Constant Extra Space

```python
numbers = [10, 20, 30, 40, 50]
total = 0

for number in numbers:
    total += number

print(total)
```

Loop-এর জন্য শুধু `total` ও `number`-এর মতো অল্প কিছু variable ব্যবহার হচ্ছে। Input list বাদ দিয়ে বিবেচনা করলে auxiliary space হলো:

\[
O(1)
\]

### Example 2: Creating a New List

```python
numbers = [10, 20, 30, 40, 50]
squares = []

for number in numbers:
    squares.append(number ** 2)

print(squares)
```

এখানে `squares`-এ input-এর প্রতিটি element-এর জন্য একটি result সংরক্ষিত হয়।

Input size \(n\) হলে নতুন list-এ \(n\)টি item থাকতে পারে। তাই auxiliary space:

\[
O(n)
\]

**মনে রাখবে:** শুধু loop-এর সংখ্যা নয়, loop-এর মধ্যে নতুন data structure তৈরি হচ্ছে কি না, সেটিও memory ব্যবহারে প্রভাব ফেলে।

## 16. Measuring Execution Time with `time`

Python-এ সাধারণভাবে execution time মাপতে `time` module ব্যবহার করা যায়।

```python
import time

start_time = time.perf_counter()

total = 0

for number in range(1_000_001):
    total += number

end_time = time.perf_counter()

print("Total:", total)
print("Execution time:", end_time - start_time, "seconds")
```

এখানে:

- `time.perf_counter()` একটি high-resolution performance counter দেয়।
- `start_time`-এ শুরু হওয়ার সময় রাখা হয়।
- `end_time`-এ শেষ হওয়ার সময় রাখা হয়।
- দুইটির পার্থক্য আনুমানিক elapsed time নির্দেশ করে।

Output-এর উদাহরণ:

```text
Total: 500000500000
Execution time: ... seconds
```

Execution time-এর জায়গায় তোমার computer-এ পাওয়া সময় দেখাবে। নির্দিষ্ট সময় আগে থেকে বলা যায় না।

### Important Measurement Tips

- একই code একাধিকবার চালিয়ে ফলাফল তুলনা করো।
- ছোট কাজের ক্ষেত্রে timer ও system overhead-এর প্রভাব মনে রাখো।
- অন্য program চলার কারণে সময় পরিবর্তিত হতে পারে।
- শুধু একবারের measurement দেখে চূড়ান্ত সিদ্ধান্ত নিও না।
- Benchmark করার সময় একই input ও একই environment ব্যবহার করার চেষ্টা করো।

## 17. Common Performance Mistakes

| Mistake | Problem | Better approach |
|---|---|---|
| অপ্রয়োজনীয় nested loop | কাজ অনেক বেড়ে যেতে পারে | প্রয়োজনীয় iteration নির্ধারণ |
| Target পাওয়ার পরও search | অতিরিক্ত iteration | প্রয়োজন হলে `break` |
| একই ব্যয়বহুল calculation বারবার | Execution time বাড়তে পারে | সম্ভব হলে result পুনরায় ব্যবহার |
| অপ্রয়োজনীয় list তৈরি | অতিরিক্ত memory লাগে | দরকার অনুযায়ী data store |
| ভুল algorithm নির্বাচন | বড় input-এ ধীর হতে পারে | Algorithm-এর growth বিশ্লেষণ |
| Measurement ছাড়া optimization | ভুল সিদ্ধান্ত হতে পারে | সময় মেপে তুলনা |
| Readability নষ্ট করে optimization | Code maintain করা কঠিন | Clarity ও performance-এর ভারসাম্য |

## 18. Practice Exercises

### Exercise 1: Count the Iterations

```python
for number in range(10):
    print(number)
```

মোট কতটি iteration হয়?

### Exercise 2: Nested Loop

```python
for row in range(4):
    for column in range(3):
        print(row, column)
```

মোট কতবার `print()` execute হবে?

### Exercise 3: Complexity

নিচের loop-এর time complexity কী?

```python
for number in numbers:
    print(number)
```

ধরে নাও, `numbers`-এ \(n\)টি element আছে।

### Exercise 4: Sequential Loops

```python
for number in range(n):
    print(number)

for number in range(n):
    print(number)
```

দুটি loop মিলিয়ে time complexity কী?

### Exercise 5: Nested Loop Growth

```python
for first in range(n):
    for second in range(n):
        print(first, second)
```

Time complexity কী?

### Exercise 6: Auxiliary Space

```python
squares = []

for number in numbers:
    squares.append(number * number)
```

ধরে নাও, `numbers`-এ \(n\)টি element আছে। `squares` list-এর auxiliary space complexity কী?

### Exercise 7: Search Optimization

একটি list-এ target খুঁজে পাওয়ার পর কেন `break` ব্যবহার করা উপকারী হতে পারে?

### Exercise 8: Performance Measurement

Python-এ elapsed time মাপার জন্য কোন function ব্যবহার করা হয়েছে এই topic-এ?

## 19. Practice Answer Key

### Answer 1

`range(10)` থেকে `0` থেকে `9` পর্যন্ত মোট ১০টি value পাওয়া যায়। তাই ১০টি iteration।

### Answer 2

Outer loop ৪ বার এবং inner loop প্রতিবার ৩ বার চলে।

মোট iteration:

\[
4 \times 3 = 12
\]

### Answer 3

প্রতিটি element একবার process করা হয়।

Time complexity: \(O(n)\)

### Answer 4

মোট কাজ:

\[
n+n=2n
\]

Constant factor বাদ দিলে time complexity: \(O(n)\)

### Answer 5

মোট iteration:

\[
n \times n=n^2
\]

Time complexity: \(O(n^2)\)

### Answer 6

`squares` list-এ সর্বোচ্চ \(n\)টি result সংরক্ষিত হয়।

Auxiliary space complexity: \(O(n)\)

### Answer 7

Target পাওয়া গেলে আর বাকি element পরীক্ষা করার প্রয়োজন না থাকলে `break` loop বন্ধ করে দেয়। এতে best বা average case-এ কম কাজ হতে পারে।

### Answer 8

`time.perf_counter()` elapsed time মাপার জন্য ব্যবহার করা হয়েছে।

## 20. Chapter Summary

- Loop performance নির্ভর করে iteration সংখ্যা ও প্রতি iteration-এর কাজের ওপর।
- একটি সাধারণ single loop প্রায়ই \(O(n)\) time complexity-এর হয়।
- দুটি \(n\)-বার চলা nested loop প্রায়ই \(O(n^2)\) হয়।
- Sequential loop-এর কাজ যোগ হয়; nested loop-এর iteration গুণ হতে পারে।
- সব nested loop-এর complexity \(O(n^2)\) নয়।
- প্রয়োজন না থাকলে অতিরিক্ত iteration ও data storage এড়িয়ে চলা ভালো।
- `break` search-এর ক্ষেত্রে অপ্রয়োজনীয় iteration কমাতে পারে।
- `sum()`-এর মতো built-in function code সহজ করতে পারে।
- Auxiliary space input size-এর সঙ্গে বাড়তে পারে।
- Performance measurement-এর জন্য `time.perf_counter()` ব্যবহার করা যায়।
- বাস্তব performance যাচাই করতে benchmark করা গুরুত্বপূর্ণ।

## 21. Completion Checklist

- [ ] Loop-এর iteration সংখ্যা হিসাব করতে পারি।
- [ ] Single loop-এর \(O(n)\) complexity বুঝি।
- [ ] Nested loop-এর \(O(n^2)\) growth বুঝি।
- [ ] Sequential ও nested loop-এর পার্থক্য ব্যাখ্যা করতে পারি।
- [ ] Time complexity ও space complexity-এর basic ধারণা বুঝি।
- [ ] `break` দিয়ে অপ্রয়োজনীয় search বন্ধ করতে পারি।
- [ ] `time.perf_counter()` দিয়ে elapsed time মাপতে পারি।
- [ ] Performance উন্নত করার আগে code-এর correctness বজায় রাখতে পারি।

**Next Topic:** `72_Loop_Output_Prediction_Exercises.md`