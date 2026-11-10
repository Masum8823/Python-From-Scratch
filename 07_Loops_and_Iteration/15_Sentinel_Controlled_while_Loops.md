# 15. Sentinel-Controlled `while` Loops

## 1. Introduction

**Sentinel-controlled loop** হলো এমন একটি loop, যা একটি বিশেষ value বা signal না পাওয়া পর্যন্ত চলতে থাকে। এই বিশেষ value-কে বলা হয় **sentinel value**।

উদাহরণস্বরূপ, user যতক্ষণ `0` input না দেয়, ততক্ষণ সংখ্যা input নেওয়া হবে।

```python
number = int(input("Enter a number (0 to stop): "))

while number != 0:
    print("You entered:", number)
    number = int(input("Enter a number (0 to stop): "))

print("Loop ended.")
```

Sample Output:

```text
Enter a number (0 to stop): 5
You entered: 5
Enter a number (0 to stop): 8
You entered: 8
Enter a number (0 to stop): 3
You entered: 3
Enter a number (0 to stop): 0
Loop ended.
```

এখানে `0` হলো sentinel value। User `0` দিলে loop বন্ধ হয়ে যায়।

**মনে রাখবে:** Sentinel value সাধারণত data input-এর কাজ শেষ হওয়ার সংকেত হিসেবে ব্যবহৃত হয়।

## 2. What Is a Sentinel Value?

Sentinel value হলো এমন একটি বিশেষ value, যা program-কে জানায় কখন loop থামাতে হবে।

কিছু উদাহরণ:

| Sentinel value | সম্ভাব্য ব্যবহার |
|---|---|
| `0` | সংখ্যা input বন্ধ করা |
| `-1` | score input শেষ করা |
| `"stop"` | text input বন্ধ করা |
| `"exit"` | menu বা command loop থেকে বের হওয়া |

Sentinel এমন একটি value হওয়া উচিত, যা সাধারণ data হিসেবে ব্যবহার না করে শেষ হওয়ার সংকেত হিসেবে নির্ধারণ করা হয়েছে।

যেমন, পরীক্ষার marks যদি `0` থেকে `100` পর্যন্ত হতে পারে, তাহলে `-1` sentinel হিসেবে ব্যবহার করা যেতে পারে—কারণ `-1` বৈধ marks নয়।

## 3. General Structure

Sentinel-controlled `while` loop-এর সাধারণ structure:

```python
value = input_value()

while value != sentinel:
    # প্রয়োজনীয় কাজ
    value = input_value()
```

এখানে:

1. প্রথমে একটি value নেওয়া হয়।
2. Value sentinel-এর সমান কি না পরীক্ষা করা হয়।
3. Sentinel না হলে loop body execute হয়।
4. আবার নতুন value নেওয়া হয়।
5. Sentinel পাওয়া গেলে loop শেষ হয়।

**গুরুত্বপূর্ণ:** Loop-এর বাইরে প্রথম input নিতে হয়, কারণ condition পরীক্ষা করার আগেই variable-এর একটি value থাকতে হবে।

## 4. How Sentinel-Controlled Loops Work

নিচের code-টি দেখো:

```python
number = int(input("Enter a number (0 to stop): "))

while number != 0:
    print(number)
    number = int(input("Enter a number (0 to stop): "))
```

ধরো, user পর্যায়ক্রমে `4`, `7`, `2`, `0` input দিল।

| Step | `number` | `number != 0` | Action |
|---:|---:|---|---|
| 1 | 4 | `True` | 4 print |
| 2 | 7 | `True` | 7 print |
| 3 | 2 | `True` | 2 print |
| 4 | 0 | `False` | Loop বন্ধ |

Sentinel value `0` condition পরীক্ষা করার সময় পাওয়া গেলে body আর execute হয় না। তাই `0` print হবে না।

## 5. Example: Summing Numbers Until Sentinel

User যতগুলো সংখ্যা input দেবে, তাদের যোগফল বের করা যাক। User `-1` দিলে input নেওয়া বন্ধ হবে।

```python
total = 0

number = int(input("Enter a number (-1 to stop): "))

while number != -1:
    total += number
    number = int(input("Enter a number (-1 to stop): "))

print("Total:", total)
```

Sample Input:

```text
10
20
5
-1
```

Output:

```text
Total: 35
```

এখানে `total`-এ শুধু সাধারণ সংখ্যাগুলো যোগ করা হয়েছে। Sentinel `-1` যোগ করা হয়নি।

**সতর্কতা:** এই program-এ `-1` কেবল input বন্ধ করার সংকেত। তাই যদি ঋণাত্মক সংখ্যা বৈধ data হিসেবে গ্রহণ করতে হয়, তাহলে অন্য sentinel বা অন্য termination method বেছে নিতে হবে।

## 6. Example: Counting Inputs Until Sentinel

Sentinel আসার আগে user কয়টি সংখ্যা দিয়েছে, তা গণনা করা যায়।

```python
count = 0

number = int(input("Enter a number (-1 to stop): "))

while number != -1:
    count += 1
    number = int(input("Enter a number (-1 to stop): "))

print("Total inputs:", count)
```

Sample Input:

```text
12
8
15
4
-1
```

Output:

```text
Total inputs: 4
```

এখানে sentinel `-1`-কে input-এর count-এর মধ্যে ধরা হয়নি।

## 7. Example: Finding the Largest Number

Sentinel ব্যবহার করে একাধিক সংখ্যা input নিয়ে সবচেয়ে বড় সংখ্যাটি খুঁজে বের করা যায়।

```python
number = int(input("Enter a number (-1 to stop): "))

if number == -1:
    print("No numbers were entered.")
else:
    largest = number

    number = int(input("Enter a number (-1 to stop): "))

    while number != -1:
        if number > largest:
            largest = number

        number = int(input("Enter a number (-1 to stop): "))

    print("Largest number:", largest)
```

Sample Input:

```text
12
7
25
9
-1
```

Output:

```text
Largest number: 25
```

এখানে প্রথম valid number-কে `largest` হিসেবে ধরা হয়েছে। এরপর প্রতিটি নতুন সংখ্যা তার চেয়ে বড় কি না পরীক্ষা করা হয়।

এই উদাহরণে `-1` sentinel হওয়ায় `-1`-এর চেয়ে ছোট সংখ্যাগুলো data হিসেবে দেওয়া যাবে না। সব integer গ্রহণ করতে চাইলে অন্য sentinel strategy প্রয়োজন।

## 8. Example: Text Sentinel

Sentinel শুধু number নয়, text-ও হতে পারে।

```python
text = input("Enter text (type 'stop' to finish): ")

while text != "stop":
    print("You wrote:", text)
    text = input("Enter text (type 'stop' to finish): ")

print("Input finished.")
```

Sample Output:

```text
Enter text (type 'stop' to finish): Hello
You wrote: Hello
Enter text (type 'stop' to finish): Python
You wrote: Python
Enter text (type 'stop' to finish): stop
Input finished.
```

এখানে `"stop"` এবং `"STOP"` এক নয়। Python-এর string comparison case-sensitive।

## 9. Sentinel-Controlled vs Counter-Controlled Loops

| বিষয় | Counter-controlled | Sentinel-controlled |
|---|---|---|
| Loop থামার কারণ | নির্দিষ্ট count বা limit | নির্দিষ্ট sentinel value |
| Iteration-এর সংখ্যা | সাধারণত আগে থেকে নির্ধারিত | আগে থেকে জানা নাও থাকতে পারে |
| উদাহরণ | ১ থেকে ১০ print করা | `0` না দেওয়া পর্যন্ত input নেওয়া |
| সাধারণ ব্যবহার | নির্দিষ্ট কাজ নির্দিষ্টবার করা | user input বা data collection |

### Counter-Controlled Example

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

### Sentinel-Controlled Example

```python
number = int(input("Enter a number (0 to stop): "))

while number != 0:
    print(number)
    number = int(input("Enter a number (0 to stop): "))
```

দুটিই `while` loop, কিন্তু termination condition আলাদা।

## 10. Common Mistakes

### Mistake 1: Forgetting to Read the Next Input

ভুল code:

```python
number = int(input("Enter a number (0 to stop): "))

while number != 0:
    print(number)
```

এখানে `number`-এর value পরিবর্তিত হচ্ছে না। Sentinel input নেওয়ার সুযোগও নেই, তাই non-zero input দিলে loop অনির্দিষ্টকাল চলবে।

সঠিক code:

```python
number = int(input("Enter a number (0 to stop): "))

while number != 0:
    print(number)
    number = int(input("Enter a number (0 to stop): "))
```

### Mistake 2: Processing the Sentinel as Normal Data

ভুল code:

```python
number = int(input("Enter a number (-1 to stop): "))
total = 0

while True:
    total += number

    if number == -1:
        break

    number = int(input("Enter a number (-1 to stop): "))

print(total)
```

এখানে `-1`-কেও যোগ করা হচ্ছে। তাই sentinel data হিসেবে process হয়ে যাচ্ছে।

সঠিক পদ্ধতি:

```python
number = int(input("Enter a number (-1 to stop): "))
total = 0

while number != -1:
    total += number
    number = int(input("Enter a number (-1 to stop): "))

print(total)
```

### Mistake 3: Choosing a Valid Data Value as Sentinel

যদি `0` সাধারণ data হিসেবে গ্রহণ করতে হয়, তাহলে `0`-কে sentinel করলে সমস্যা হবে।

উদাহরণ: কোনো student-এর score `0` হতে পারে। তাই score input বন্ধ করার জন্য `-1` ব্যবহার করা যেতে পারে।

### Mistake 4: Incorrect String Comparison

```python
command = input("Enter command: ")

while command != "exit":
    print(command)
    command = input("Enter command: ")
```

এখানে `"Exit"` বা `"EXIT"` লিখলে loop বন্ধ হবে না। Case-insensitive comparison চাইলে `command.lower() != "exit"` ব্যবহার করা যায়।

### Mistake 5: Invalid Numeric Input

```python
number = int(input("Enter a number: "))
```

User যদি `hello` লেখে, তাহলে `ValueError` হবে। এই chapter-এর উদাহরণগুলোতে বৈধ integer input ধরে নেওয়া হয়েছে। Invalid input সামলানো আমরা exception handling অধ্যায়ে বিস্তারিত শিখব।

## 11. Practice Exercises

### Exercise 1

Sentinel-controlled loop কী?

### Exercise 2

নিচের program-এর sentinel value কোনটি?

```python
number = int(input("Enter a number (-1 to stop): "))

while number != -1:
    print(number)
    number = int(input("Enter a number (-1 to stop): "))
```

### Exercise 3

Input হলো `5`, `3`, `0`। নিচের program-এর output কী হবে?

```python
number = int(input())
total = 0

while number != 0:
    total += number
    number = int(input())

print(total)
```

### Exercise 4

User `8`, `2`, `6`, `-1` input দিলে কতটি valid number গণনা হবে?

### Exercise 5

`0` যদি বৈধ data value হয়, তাহলে কেন সেটিকে sentinel হিসেবে বেছে নেওয়া অনুপযুক্ত হতে পারে?

### Exercise 6

User `"stop"` না লেখা পর্যন্ত text input নিয়ে প্রতিটি text print করার program লেখো।

### Exercise 7

`-1` sentinel ব্যবহার করে সংখ্যাগুলোর যোগফল বের করার program লেখো। Sentinel যেন যোগফলের মধ্যে অন্তর্ভুক্ত না হয়।

### Exercise 8

নিচের code-এ সমস্যা কী?

```python
number = int(input("Enter a number (0 to stop): "))

while number != 0:
    print(number)
```

## 12. Answer Key

### Exercise 1

যে loop একটি নির্দিষ্ট sentinel value পাওয়া পর্যন্ত চলতে থাকে, তাকে sentinel-controlled loop বলে।

### Exercise 2

`-1`।

### Exercise 3

```text
8
```

কারণ `5 + 3 = 8`; `0` sentinel হওয়ায় যোগ করা হয় না।

### Exercise 4

৩টি valid number: `8`, `2`, `6`।

### Exercise 5

কারণ `0` সাধারণ data হিসেবে দরকার হলে, `0` পেলেই loop বন্ধ হয়ে যাবে এবং পরবর্তী data গ্রহণ করা হবে না।

### Exercise 6

```python
text = input("Enter text ('stop' to finish): ")

while text != "stop":
    print(text)
    text = input("Enter text ('stop' to finish): ")
```

### Exercise 7

```python
total = 0
number = int(input("Enter a number (-1 to stop): "))

while number != -1:
    total += number
    number = int(input("Enter a number (-1 to stop): "))

print("Total:", total)
```

### Exercise 8

`number`-এর value loop-এর মধ্যে নতুন করে নেওয়া হচ্ছে না। তাই প্রথম input `0` না হলে loop অনির্দিষ্টকাল চলবে। Loop-এর মধ্যে নতুন input নিতে হবে।

## 13. Chapter Progress Checklist

- [ ] Sentinel value কী বুঝেছি।
- [ ] Sentinel-controlled `while` loop লিখতে পারি।
- [ ] Sentinel না পাওয়া পর্যন্ত input নিতে পারি।
- [ ] Sentinel বাদ দিয়ে sum ও count হিসাব করতে পারি।
- [ ] Text sentinel ব্যবহার করতে পারি।
- [ ] Counter-controlled ও sentinel-controlled loop-এর পার্থক্য বুঝেছি।
- [ ] উপযুক্ত sentinel নির্বাচন করতে পারি।
- [ ] Infinite loop ও sentinel-সংক্রান্ত ভুল শনাক্ত করতে পারি।

## 14. Summary

- Sentinel-controlled loop একটি নির্দিষ্ট value পাওয়ার আগ পর্যন্ত চলে।
- Sentinel value loop শেষ হওয়ার signal হিসেবে কাজ করে।
- Sentinel-কে সাধারণ data হিসেবে process করা উচিত নয়।
- Sentinel নির্বাচন করার সময় সেটি valid data হতে পারে কি না বিবেচনা করতে হয়।
- এই loop user input, data collection, counting ও summation-এর কাজে ব্যবহার করা যায়।
- Input variable প্রতিবার update না করলে infinite loop হতে পারে।

**Next Topic:** `16_Input_Validation_Using_while.md`
