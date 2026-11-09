# 07. Entry-Controlled and Exit-Controlled Loops

## 1. Introduction

Loop-এর execution বোঝার জন্য একটি গুরুত্বপূর্ণ বিষয় হলো—loop body execute করার আগে condition পরীক্ষা করা হয়, নাকি body execute করার পরে condition পরীক্ষা করা হয়।

এই ভিত্তিতে সাধারণভাবে loop-কে দুই ভাগে আলোচনা করা হয়:

1. Entry-Controlled Loop
2. Exit-Controlled Loop

এই পার্থক্য বুঝলে বোঝা যায়, কোনো condition শুরুতেই `False` হলে loop body চলবে কি না।

## 2. What Is an Entry-Controlled Loop?

**Definition:** An entry-controlled loop checks its condition before executing the loop body.

সহজ ভাষায়, যে loop body execute করার আগে condition পরীক্ষা করে, তাকে entry-controlled loop বলা হয়।

Condition `True` হলে loop body execute হয়। Condition `False` হলে body execute না করেই loop শেষ হয়।

### Example

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

**Output:**

```text
1
2
3
```

### How It Works

1. `count = 1` দিয়ে loop শুরু হয়।
2. `count <= 3` condition পরীক্ষা করা হয়।
3. Condition `True` হওয়ায় `print(count)` execute হয়।
4. `count += 1` দিয়ে value বাড়ানো হয়।
5. আবার condition পরীক্ষা করা হয়।
6. `count`-এর value `4` হলে condition `False` হয় এবং loop শেষ হয়।

### When the Initial Condition Is False

```python
count = 5

while count < 3:
    print(count)
```

**Output:** কোনো output নেই।

কারণ `count < 3` শুরুতেই `False`। তাই loop body একবারও execute হয় না।

## 3. What Is an Exit-Controlled Loop?

**Definition:** An exit-controlled loop checks its condition after executing the loop body.

সহজ ভাষায়, যে loop body অন্তত একবার execute করার পরে condition পরীক্ষা করে, তাকে exit-controlled loop বলা হয়।

এ ধরনের loop-এর সাধারণ উদাহরণ হলো `do-while` loop, যা C ও C++-এর মতো কিছু programming language-এ রয়েছে।

### Example in C

```c
#include <stdio.h>

int main(void) {
    int count = 5;

    do {
        printf("%d\n", count);
        count++;
    } while (count < 3);

    return 0;
}
```

**Output:**

```text
5
```

এখানে প্রথমে `do` block execute হয়। তারপর `count < 3` condition পরীক্ষা করা হয়। Condition `False` হলেও body ইতোমধ্যে একবার execute হয়েছে।

**মনে রাখবে:** এই `do-while` syntax Python-এ সরাসরি নেই।

## 4. Entry-Controlled vs Exit-Controlled Loops

| বিষয় | Entry-Controlled Loop | Exit-Controlled Loop |
|---|---|---|
| Condition কখন পরীক্ষা হয়? | Body-এর আগে | Body-এর পরে |
| Body অন্তত একবার চলে? | না, condition শুরুতেই `False` হলে চলবে না | হ্যাঁ, অন্তত একবার চলে |
| সাধারণ উদাহরণ | Python-এর `while`, `for`; C-এর `while`, `for` | C/C++-এর `do-while` |
| প্রধান বৈশিষ্ট্য | আগে condition যাচাই | আগে body execute |

## 5. Are Python's `for` and `while` Loops Entry-Controlled?

হ্যাঁ, প্রচলিত সংজ্ঞা অনুযায়ী Python-এর `for` ও `while` loop দুটোই entry-controlled ধরনের।

### Python `while` Loop

```python
number = 10

while number < 5:
    print(number)
```

Output: কোনো output নেই।

Condition শুরুতেই `False`, তাই body execute হয় না।

### Python `for` Loop

```python
for number in []:
    print(number)
```

Output: কোনো output নেই।

এখানে list খালি, তাই কোনো item পাওয়া যায় না এবং loop body execute হয় না।

## 6. How Can We Repeat Code at Least Once in Python?

Python-এ built-in `do-while` loop নেই। তবে `while True` এবং `break` ব্যবহার করে একই ধরনের behaviour তৈরি করা যায়।

### Example: Execute First, Then Check

```python
while True:
    number = int(input("Enter a number greater than 0: "))

    if number > 0:
        break

print("Valid number:", number)
```

এখানে:

1. প্রথমে input নেওয়া হয়।
2. Number `0`-এর চেয়ে বড় কি না পরীক্ষা করা হয়।
3. Valid হলে `break` loop শেষ করে।
4. Invalid হলে আবার input নেওয়া হয়।

এভাবে body অন্তত একবার execute হয়।

**Note:** এই উদাহরণে non-numeric input দিলে `int()` থেকে `ValueError` হতে পারে। পরবর্তী exception handling topic-এ এ ধরনের error সামলানো শিখব।

## 7. Why Is This Difference Important?

এই পার্থক্য বিশেষ করে input validation, menu-driven program এবং condition-based repetition-এ গুরুত্বপূর্ণ।

ধরো, User-এর কাছ থেকে অন্তত একবার input নিতে হবে।

```python
choice = input("Enter your choice: ")
```

এখানে input নেওয়ার জন্য loop প্রয়োজন নেই, যদি শুধু একবার input নেওয়াই উদ্দেশ্য হয়।

কিন্তু valid input না পাওয়া পর্যন্ত input নিতে চাইলে loop ব্যবহার করা যায়:

```python
choice = ""

while choice != "yes":
    choice = input("Type yes to continue: ")

print("Continuing...")
```

এখানে condition আগে পরীক্ষা হয়। শুরুতে `choice` খালি string হওয়ায় loop body execute হয়।

## 8. Common Beginner Mistakes

### Mistake 1: Python-এ সরাসরি `do-while` লিখতে চেষ্টা করা

নিচের syntax Python-এ valid নয়:

```text
do:
    print("Hello")
while condition
```

Python-এ `do-while` statement নেই।

### Mistake 2: `while` Loop-এর Body অন্তত একবার চলবে ধরে নেওয়া

```python
number = 10

while number < 5:
    print(number)
```

এখানে body একবারও execute হবে না।

### Mistake 3: `while True`-এর Exit Condition ভুলে যাওয়া

```python
while True:
    print("Running")
```

এই loop স্বাভাবিকভাবে শেষ হবে না। কোনো উপযুক্ত exit condition বা `break` না থাকলে এটি চলতেই থাকবে।

## 9. Practice Exercises

### Exercise 1

Entry-controlled loop কী?

### Exercise 2

Exit-controlled loop কী?

### Exercise 3

নিচের code-এর output কী হবে?

```python
number = 5

while number < 3:
    print(number)
```

### Exercise 4

Python-এর `for` ও `while` loop কি সাধারণত entry-controlled?

### Exercise 5

Python-এ কি সরাসরি `do-while` loop রয়েছে?

### Exercise 6

নিচের code-এর output কী হবে?

```python
for number in []:
    print(number)

print("Finished")
```

### Exercise 7

Python-এ `do-while`-এর মতো behaviour তৈরি করতে কোন দুটি keyword একসঙ্গে ব্যবহার করা যায়?

## 10. Answer Key

**Exercise 1:** যে loop body execute করার আগে condition পরীক্ষা করে, সেটি entry-controlled loop।

**Exercise 2:** যে loop body execute করার পরে condition পরীক্ষা করে, সেটি exit-controlled loop।

**Exercise 3:** কোনো output হবে না, কারণ `5 < 3` হলো `False`।

**Exercise 4:** হ্যাঁ। Python-এর built-in `for` ও `while` loop entry-controlled ধরনের।

**Exercise 5:** না। Python-এ built-in `do-while` loop নেই।

**Exercise 6:**

```text
Finished
```

খালি list-এ কোনো item নেই, তাই loop body execute হবে না।

**Exercise 7:** `while True` এবং `break`।

## 11. Chapter Progress Checklist

- [ ] Entry-controlled loop বুঝেছি।
- [ ] Exit-controlled loop বুঝেছি।
- [ ] দুই ধরনের loop-এর পার্থক্য জানি।
- [ ] Python-এর `for` ও `while` loop-এর behaviour বুঝেছি।
- [ ] Python-এ `do-while` loop নেই, জানি।
- [ ] `while True` ও `break` দিয়ে অন্তত একবার body execute করার পদ্ধতি বুঝেছি।

## 12. Summary

- Entry-controlled loop body execute করার আগে condition পরীক্ষা করে।
- Exit-controlled loop body execute করার পরে condition পরীক্ষা করে।
- Python-এর `for` ও `while` loop সাধারণত entry-controlled।
- Python-এ সরাসরি `do-while` loop নেই।
- `while True` ও `break` ব্যবহার করে exit-controlled loop-এর মতো behaviour তৈরি করা যায়।

**Next Topic:** `08_Choosing_the_Right_Loop.md`
