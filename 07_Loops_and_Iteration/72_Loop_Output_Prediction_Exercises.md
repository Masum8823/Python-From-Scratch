# 72. Loop Output Prediction Exercises

## 1. Introduction

Loop output prediction হলো Python code execute করার আগে তার output কী হবে, তা নির্ধারণ করা।

এটি programming শেখার একটি গুরুত্বপূর্ণ practice, কারণ এর মাধ্যমে বোঝা যায়:

- Loop কতবার execute হবে।
- Variable কীভাবে পরিবর্তিত হবে।
- `range()` কোন কোন value তৈরি করবে।
- `break` ও `continue` কীভাবে কাজ করবে।
- Nested loop-এর output কীভাবে তৈরি হবে।
- Loop-এর `else` কখন execute হবে।
- Counter ও accumulator কীভাবে কাজ করবে।

**Practice rule:** প্রথমে নিজে output predict করবে, তারপর code run করে উত্তর যাচাই করবে।

## 2. How to Predict Loop Output

Output predict করার সময় নিচের ধাপগুলো অনুসরণ করো:

1. Variable-এর initial value শনাক্ত করো।
2. Loop-এর condition বা iterable পরীক্ষা করো।
3. প্রথম iteration-এ কোন statement execute হবে তা দেখো।
4. প্রতিটি variable update লিখে রাখো।
5. `break` বা `continue` থাকলে তার প্রভাব বিবেচনা করো।
6. Loop শেষ হলে final output নির্ধারণ করো।

জটিল code-এর ক্ষেত্রে একটি dry-run table তৈরি করো।

## 3. Level 1: Basic `for` Loop

### Question 1

```python
for number in range(1, 5):
    print(number)
```

### Question 2

```python
for number in range(3):
    print("Python")
```

### Question 3

```python
for number in range(2, 11, 2):
    print(number)
```

### Question 4

```python
for number in range(5, 0, -1):
    print(number)
```

### Question 5

```python
for number in range(1, 8, 3):
    print(number)
```

### Question 6

```python
for number in range(5, 1):
    print(number)
print("Finished")
```

## 4. Level 2: Basic `while` Loop

### Question 7

```python
number = 1

while number <= 4:
    print(number)
    number += 1
```

### Question 8

```python
number = 5

while number > 0:
    print(number)
    number -= 2
```

### Question 9

```python
number = 2

while number < 10:
    print(number)
    number += 3
```

### Question 10

```python
number = 1
total = 0

while number <= 4:
    total += number
    number += 1

print(total)
```

### Question 11

```python
number = 10

while number < 5:
    print(number)

print("Done")
```

### Question 12

```python
number = 3

while number >= 1:
    print(number)
    number -= 1

print("Go!")
```

## 5. Level 3: Conditions Inside Loops

### Question 13

```python
for number in range(1, 7):
    if number % 2 == 0:
        print(number)
```

### Question 14

```python
for number in range(1, 6):
    if number % 2 != 0:
        print(number)
```

### Question 15

```python
total = 0

for number in range(1, 6):
    if number > 3:
        total += number

print(total)
```

### Question 16

```python
for number in range(1, 6):
    if number == 3:
        print("Three")
    else:
        print(number)
```

### Question 17

```python
for number in range(1, 6):
    if number < 3:
        print("Small")
    elif number == 3:
        print("Middle")
    else:
        print("Large")
```

### Question 18

```python
count = 0

for number in range(1, 11):
    if number % 2 == 0:
        count += 1

print(count)
```

## 6. Level 4: Accumulation and Counting

### Question 19

```python
total = 0

for number in range(1, 5):
    total += number

print(total)
```

### Question 20

```python
product = 1

for number in range(1, 5):
    product *= number

print(product)
```

### Question 21

```python
total = 0

for number in range(2, 11, 2):
    total += number

print(total)
```

### Question 22

```python
numbers = [4, 7, 2, 9]
total = 0

for number in numbers:
    total += number

print(total)
```

### Question 23

```python
numbers = [5, 12, 8, 20, 3]
count = 0

for number in numbers:
    if number >= 10:
        count += 1

print(count)
```

### Question 24

```python
numbers = [2, 5, 8, 11]
total = 0

for number in numbers:
    if number % 2 == 0:
        total += number

print(total)
```

## 7. Level 5: `break` and `continue`

### Question 25

```python
for number in range(1, 7):
    if number == 4:
        break
    print(number)
```

### Question 26

```python
for number in range(1, 7):
    if number == 4:
        continue
    print(number)
```

### Question 27

```python
number = 1

while number <= 5:
    if number == 3:
        number += 1
        continue

    print(number)
    number += 1
```

### Question 28

```python
for number in range(1, 6):
    if number % 2 == 0:
        break
    print(number)
```

### Question 29

```python
for number in range(1, 6):
    if number % 2 == 0:
        continue
    print(number * 2)
```

### Question 30

```python
for number in range(1, 5):
    print("Start", number)

    if number == 2:
        break

    print("End", number)
```

## 8. Level 6: Nested Loops

### Question 31

```python
for row in range(2):
    for column in range(3):
        print("*", end=" ")
    print()
```

### Question 32

```python
for row in range(1, 4):
    for column in range(1, 3):
        print(row, column)
```

### Question 33

```python
for row in range(1, 4):
    for column in range(row):
        print("*", end=" ")
    print()
```

### Question 34

```python
for row in range(1, 4):
    for column in range(1, 4):
        print(row * column, end=" ")
    print()
```

### Question 35

```python
for row in range(1, 4):
    for column in range(1, 4):
        if column == 2:
            continue
        print(row, column)
```

### Question 36

```python
for row in range(1, 4):
    for column in range(1, 4):
        if column == 2:
            break
        print(row, column)
```

## 9. Level 7: Loop `else`

### Question 37

```python
for number in range(3):
    print(number)
else:
    print("Completed")
```

### Question 38

```python
for number in range(5):
    if number == 2:
        break
    print(number)
else:
    print("Completed")
```

### Question 39

```python
for number in range(3):
    if number == 1:
        continue
    print(number)
else:
    print("Completed")
```

### Question 40

```python
number = 1

while number <= 3:
    print(number)
    number += 1
else:
    print("Loop ended")
```

## 10. Level 8: Strings and Lists

### Question 41

```python
for character in "CODE":
    print(character)
```

### Question 42

```python
word = "banana"
count = 0

for character in word:
    if character == "a":
        count += 1

print(count)
```

### Question 43

```python
numbers = [10, 20, 30]

for number in numbers:
    print(number // 10)
```

### Question 44

```python
numbers = [1, 2, 3, 4, 5]

for number in numbers:
    if number > 3:
        print(number)
```

### Question 45

```python
names = ["Ritu", "Masum", "Mahin"]

for index, name in enumerate(names, start=1):
    print(index, name)
```

## 11. Level 9: Mixed Logic

### Question 46

```python
total = 0

for number in range(1, 6):
    if number % 2 == 0:
        total += number
    else:
        total -= number

print(total)
```

### Question 47

```python
number = 1
total = 0

while number <= 5:
    total += number * 2
    number += 2

print(total)
```

### Question 48

```python
for number in range(1, 4):
    for value in range(1, 3):
        print(number + value, end=" ")
    print()
```

### Question 49

```python
count = 0

for number in range(1, 10):
    if number % 3 == 0:
        count += 1
    elif number % 2 == 0:
        count += 2

print(count)
```

### Question 50

```python
total = 0

for number in range(1, 6):
    if number == 3:
        continue
    total += number

print(total)
```

## 12. Challenge Questions

### Question 51: Find the Output

```python
number = 1

while number <= 4:
    print(number, end=" ")
    number *= 2
```

### Question 52: Find the Output

```python
for number in range(1, 5):
    for value in range(number):
        print(value, end="")
    print()
```

### Question 53: Find the Output

```python
total = 0

for number in range(1, 6):
    for value in range(1, number + 1):
        total += 1

print(total)
```

### Question 54: Find the Output

```python
for number in range(1, 6):
    if number > 3:
        print("Stop")
        break
    print(number)
else:
    print("Finished")
```

### Question 55: Find the Output

```python
numbers = [2, 4, 6]
total = 0

for index in range(len(numbers)):
    total += numbers[index]

print(total, len(numbers))
```

### Question 56: Find the Output

```python
for number in range(1, 4):
    print(number, end="")

    for value in range(2):
        print(value, end="")

    print()
```

### Question 57: Find the Output

```python
number = 1

while number <= 5:
    if number % 2 == 0:
        number += 1
        continue

    print(number, end=" ")
    number += 1
```

### Question 58: Find the Output

```python
for number in range(1, 4):
    for value in range(1, 4):
        if number == value:
            print("X", end=" ")
        else:
            print("-", end=" ")
    print()
```

### Question 59: Find the Output

```python
total = 0

for number in range(1, 5):
    total += number

    if total >= 6:
        break

print(total)
```

### Question 60: Find the Output

```python
for number in range(1, 5):
    if number == 2:
        pass
    print(number)
```

## 13. Answer Key

**পরামর্শ:** উত্তর দেখার আগে নিজে সব প্রশ্ন solve করার চেষ্টা করবে।

### Level 1 Answers

**1.**
```text
1
2
3
4
```

**2.**
```text
Python
Python
Python
```

**3.**
```text
2
4
6
8
10
```

**4.**
```text
5
4
3
2
1
```

**5.**
```text
1
4
7
```

**6.**
```text
Finished
```

কারণ `range(5, 1)`-এর default step `1`; এই direction-এ range empty।

### Level 2 Answers

**7.**
```text
1
2
3
4
```

**8.**
```text
5
3
1
```

**9.**
```text
2
5
8
```

**10.**
```text
10
```

**11.**
```text
Done
```

**12.**
```text
3
2
1
Go!
```

### Level 3 Answers

**13.**
```text
2
4
6
```

**14.**
```text
1
3
5
```

**15.**
```text
9
```

**16.**
```text
1
2
Three
4
5
```

**17.**
```text
Small
Small
Middle
Large
Large
```

**18.**
```text
5
```

### Level 4 Answers

**19.**
```text
10
```

**20.**
```text
24
```

**21.**
```text
30
```

**22.**
```text
22
```

**23.**
```text
2
```

**24.**
```text
10
```

### Level 5 Answers

**25.**
```text
1
2
3
```

**26.**
```text
1
2
3
5
6
```

**27.**
```text
1
2
4
5
```

**28.**
```text
1
```

**29.**
```text
2
6
10
```

**30.**
```text
Start 1
End 1
Start 2
```

### Level 6 Answers

**31.**
```text
* * *
* * *
```

**32.**
```text
1 1
1 2
2 1
2 2
3 1
3 2
```

**33.**
```text
*
* *
* * *
```

**34.**
```text
1 2 3
2 4 6
3 6 9
```

**35.**
```text
1 1
1 3
2 1
2 3
3 1
3 3
```

**36.**
```text
1 1
2 1
3 1
```

### Level 7 Answers

**37.**
```text
0
1
2
Completed
```

**38.**
```text
0
1
```

`break`-এর কারণে `else` execute হয় না।

**39.**
```text
0
2
Completed
```

`continue` loop-কে অস্বাভাবিকভাবে শেষ করে না, তাই `else` execute হয়।

**40.**
```text
1
2
3
Loop ended
```

### Level 8 Answers

**41.**
```text
C
O
D
E
```

**42.**
```text
3
```

**43.**
```text
1
2
3
```

**44.**
```text
4
5
```

**45.**
```text
1 Ritu
2 Masum
3 Mahin
```

### Level 9 Answers

**46.**
```text
3
```

হিসাব: \(-1+2-3+4-5=-3\)।

**সংশোধন:** উপরের হিসাব ও code অনুযায়ী সঠিক output হলো `-3`, `3` নয়।

**47.**
```text
18
```

হিসাব: \(2+6+10=18\)।

**48.**
```text
2 3
3 4
4 5
```

**49.**
```text
11
```

**50.**
```text
12
```

### Challenge Answers

**51.**
```text
1 2 4
```

**52.**
```text

0
01
012
```

প্রথম iteration-এ inner loop empty হওয়ায় প্রথম line blank।

**53.**
```text
15
```

**54.**
```text
1
2
3
Stop
```

**55.**
```text
12 3
```

**56.**
```text
100
200
300
```

**57.**
```text
1 3 5
```

**58.**
```text
X - -
- X -
- - X
```

**59.**
```text
6
```

**60.**
```text
1
2
3
4
```

`pass` কোনো কাজ করে না; এটি শুধু একটি placeholder statement।

## 14. Self-Assessment

নিজের প্রস্তুতি যাচাই করো:

- [ ] `range()`-এর output predict করতে পারি।
- [ ] `while` loop-এর condition ও update track করতে পারি।
- [ ] Counter ও accumulator-এর final value বের করতে পারি।
- [ ] Condition-এর কারণে কোন statement execute হবে তা বুঝতে পারি।
- [ ] `break`, `continue` ও `pass`-এর পার্থক্য বুঝি।
- [ ] Nested loop-এর output predict করতে পারি।
- [ ] Loop-এর `else` কখন execute হয় বুঝি।
- [ ] Code run করার আগেই output বের করার চেষ্টা করতে পারি।

## 15. Final Advice

Loop output prediction-এ দক্ষ হতে নিয়মিত practice করো। প্রথমে সহজ loop দিয়ে শুরু করবে, তারপর condition, accumulator, control statements এবং nested loop-এর প্রশ্ন solve করবে।

প্রতিটি প্রশ্নের ক্ষেত্রে variable-এর initial value, condition, update এবং output আলাদা করে লিখলে ভুল কম হবে।

**Next Topic:** `73_Loop_Programming_Exercises.md`