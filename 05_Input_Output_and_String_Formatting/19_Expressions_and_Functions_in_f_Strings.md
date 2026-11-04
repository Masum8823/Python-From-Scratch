# 19. Expressions and Functions in f-Strings

## 1. Introduction

f-string-এর মধ্যে শুধু variable ব্যবহার করা যায় না; এর পাশাপাশি expression, function call, method call এবং conditional expression-ও ব্যবহার করা যায়।

এতে calculation বা ছোট কোনো operation-এর result সরাসরি string-এর মধ্যে দেখানো সম্ভব হয়।

### Example

```python
a = 10
b = 20

print(f"Sum: {a + b}")
```

Output:

```text
Sum: 30
```

এখানে `{a + b}` একটি expression। Python প্রথমে expression-এর result হিসাব করে, তারপর result-টি string-এর মধ্যে বসায়।

এই topic-এ আমরা শিখব:

- f-string-এর মধ্যে expression ব্যবহার
- Arithmetic ও comparison expression
- Function এবং method call
- Conditional expression
- List, dictionary ও indexing
- Formatting specification
- Nested f-string এবং common errors

## 2. Understanding Expressions in f-Strings

**Expression** হলো Python code-এর এমন একটি অংশ, যা evaluate হয়ে একটি value দেয়।

যেমন:

```python
10 + 20
```

এর result হলো `30`।

f-string-এর মধ্যে expression লিখতে curly braces `{}` ব্যবহার করা হয়।

### Example 1: Simple Expression

```python
a = 15
b = 5

print(f"Result: {a + b}")
print(f"Result: {a - b}")
print(f"Result: {a * b}")
```

Output:

```text
Result: 20
Result: 10
Result: 75
```

### Example 2: Multiple Operations

```python
a = 10
b = 4

print(f"Calculation: {a + b * 2}")
```

Output:

```text
Calculation: 18
```

এখানে multiplication-এর precedence addition-এর চেয়ে বেশি। তাই প্রথমে `4 * 2 = 8`, এরপর `10 + 8 = 18`।

### Example 3: Using Parentheses

```python
a = 10
b = 4

print(f"Calculation: {(a + b) * 2}")
```

Output:

```text
Calculation: 28
```

Parentheses ব্যবহার করে calculation-এর order নিয়ন্ত্রণ করা হয়েছে।

## 3. Comparison Expressions in f-Strings

Comparison expression-এর result সাধারণত `True` অথবা `False` হয়।

### Example

```python
age = 22

print(f"Adult: {age >= 18}")
print(f"Minor: {age < 18}")
```

Output:

```text
Adult: True
Minor: False
```

### Comparing Two Values

```python
a = 50
b = 40

print(f"a is greater than b: {a > b}")
print(f"a equals b: {a == b}")
```

Output:

```text
a is greater than b: True
a equals b: False
```

এখানে comparison operator-এর result সরাসরি দেখানো হয়েছে।

**মনে রাখবে:** `=` assignment-এর জন্য ব্যবহৃত হয়, আর `==` দুটি value সমান কি না তা পরীক্ষা করে।

## 4. Logical Expressions in f-Strings

`and`, `or` এবং `not` ব্যবহার করেও expression লেখা যায়।

### Example

```python
age = 22
has_id = True

print(f"Can enter: {age >= 18 and has_id}")
```

Output:

```text
Can enter: True
```

কারণ `age >= 18` এবং `has_id`—দুটিই `True`।

### Another Example

```python
is_raining = False

print(f"Should carry an umbrella: {not is_raining}")
```

Output:

```text
Should carry an umbrella: True
```

Logical expression-এর result এবং truthiness সম্পর্কে পরিষ্কার ধারণা থাকা প্রয়োজন।

## 5. Calling Functions Inside f-Strings

Function call-এর result সরাসরি f-string-এর মধ্যে ব্যবহার করা যায়।

### Example 1: `len()`

```python
name = "Masum"

print(f"Number of characters: {len(name)}")
```

Output:

```text
Number of characters: 5
```

### Example 2: `max()` and `min()`

```python
a = 10
b = 25
c = 15

print(f"Maximum: {max(a, b, c)}")
print(f"Minimum: {min(a, b, c)}")
```

Output:

```text
Maximum: 25
Minimum: 10
```

### Example 3: `sum()`

```python
numbers = [10, 20, 30]

print(f"Total: {sum(numbers)}")
```

Output:

```text
Total: 60
```

### Example 4: Custom Function

```python
def square(number):
    return number * number

value = 5

print(f"Square of {value}: {square(value)}")
```

Output:

```text
Square of 5: 25
```

এখানে `square(value)` function call-এর result f-string-এ বসেছে।

**গুরুত্বপূর্ণ:** Function call-এর result ব্যবহার করতে function-টি আগে define করা থাকতে হবে, অথবা Python-এর built-in function হতে হবে।

## 6. Using Methods Inside f-Strings

Method হলো object-এর সঙ্গে যুক্ত function। String-এর বিভিন্ন method f-string-এর মধ্যে ব্যবহার করা যায়।

### Example 1: `upper()`

```python
name = "masum"

print(f"Uppercase: {name.upper()}")
```

Output:

```text
Uppercase: MASUM
```

### Example 2: `title()`

```python
name = "md abdulla al masum"

print(f"Name: {name.title()}")
```

Output:

```text
Name: Md Abdulla Al Masum
```

### Example 3: `replace()`

```python
text = "I like Java"

print(f"Updated text: {text.replace('Java', 'Python')}")
```

Output:

```text
Updated text: I like Python
```

### Example 4: `strip()`

```python
name = "  Masum  "

print(f"Name: {name.strip()}")
```

Output:

```text
Name: Masum
```

Method call-এর result দেখানো হয়; সাধারণত original string পরিবর্তিত হয় না, কারণ Python string immutable।

## 7. Using Conditional Expressions

Conditional expression ব্যবহার করে condition অনুযায়ী একটি value নির্বাচন করা যায়।

### Syntax

```python
value_if_true if condition else value_if_false
```

### Example 1: Pass or Fail

```python
marks = 75

print(f"Result: {'Pass' if marks >= 40 else 'Fail'}")
```

Output:

```text
Result: Pass
```

### Example 2: Even or Odd

```python
number = 8

print(f"Number type: {'Even' if number % 2 == 0 else 'Odd'}")
```

Output:

```text
Number type: Even
```

### Example 3: Positive or Negative

```python
number = -5

print(f"Status: {'Positive' if number > 0 else 'Non-positive'}")
```

Output:

```text
Status: Non-positive
```

এখানে `Non-positive` বলতে zero এবং negative number—দুটিই বোঝানো হয়েছে।

### Example 4: Store the Result First

```python
marks = 85

result = "Pass" if marks >= 40 else "Fail"

print(f"Result: {result}")
```

Output:

```text
Result: Pass
```

Logic জটিল হলে conditional expression-টি আলাদা variable-এ রাখলে code পড়তে সহজ হয়।

## 8. Using List Indexing and Slicing

f-string-এর মধ্যে list-এর index এবং slice ব্যবহার করা যায়।

### Example 1: List Indexing

```python
subjects = ["Python", "Java", "C++"]

print(f"First subject: {subjects[0]}")
print(f"Last subject: {subjects[-1]}")
```

Output:

```text
First subject: Python
Last subject: C++
```

### Example 2: List Slicing

```python
numbers = [10, 20, 30, 40, 50]

print(f"First three: {numbers[:3]}")
```

Output:

```text
First three: [10, 20, 30]
```

### Example 3: Length of a List

```python
subjects = ["Python", "Java", "C++"]

print(f"Total subjects: {len(subjects)}")
```

Output:

```text
Total subjects: 3
```

Index ভুল হলে `IndexError` হতে পারে। তাই প্রয়োজন অনুযায়ী list-এর length ও index যাচাই করতে হবে।

## 9. Accessing Dictionary Values

Dictionary-এর key দিয়ে value access করে f-string-এ দেখানো যায়।

### Example

```python
student = {
    "name": "Masum",
    "department": "CSE",
    "marks": 90
}

print(f"Name: {student['name']}")
print(f"Department: {student['department']}")
print(f"Marks: {student['marks']}")
```

Output:

```text
Name: Masum
Department: CSE
Marks: 90
```

### Using a Dictionary Method

```python
student = {
    "name": "Masum",
    "marks": 90
}

print(f"Name: {student.get('name')}")
print(f"Grade: {student.get('grade', 'Not assigned')}")
```

Output:

```text
Name: Masum
Grade: Not assigned
```

`get()` method key না থাকলে default value দিতে পারে। অন্যদিকে `student['grade']` ব্যবহার করলে key অনুপস্থিত থাকলে `KeyError` হবে।

## 10. Formatting Expressions Directly

Expression-এর result-কে একই সঙ্গে format করা যায়।

### Example 1: Division Result

```python
a = 10
b = 3

print(f"Result: {a / b:.2f}")
```

Output:

```text
Result: 3.33
```

এখানে expression-এর পরে `:.2f` formatting specification ব্যবহার করা হয়েছে।

### Example 2: Percentage Calculation

```python
obtained = 450
total = 500

print(f"Percentage: {obtained / total:.2%}")
```

Output:

```text
Percentage: 90.00%
```

### Example 3: Total Price

```python
price = 199.99
quantity = 3

print(f"Total: Tk {(price * quantity):,.2f}")
```

Output:

```text
Total: Tk 599.97
```

Parentheses calculation-টি পরিষ্কারভাবে বোঝাতে সাহায্য করে।

## 11. Using Multiple Expressions in One f-String

একটি f-string-এ একাধিক expression থাকতে পারে।

### Example

```python
a = 12
b = 8

print(f"Sum: {a + b}, Difference: {a - b}, Product: {a * b}")
```

Output:

```text
Sum: 20, Difference: 4, Product: 96
```

### Another Example

```python
name = "Masum"
marks = [80, 90, 85]

print(f"{name} received {sum(marks)} total marks.")
print(f"Average: {sum(marks) / len(marks):.2f}")
```

Output:

```text
Masum received 255 total marks.
Average: 85.00
```

তবে একই expression বারবার লিখলে অপ্রয়োজনীয় calculation হতে পারে। তাই complex বা repeated calculation আলাদা variable-এ রাখা ভালো।

## 12. Nested f-Strings

একটি f-string-এর expression-এর মধ্যে আরেকটি f-string ব্যবহার করা যায়, তবে প্রয়োজন না হলে এটি এড়িয়ে চলা ভালো।

### Example

```python
name = "Masum"
marks = 85

message = f"Student: {name}, Result: {f'{marks} marks'}"

print(message)
```

Output:

```text
Student: Masum, Result: 85 marks
```

এখানে nested f-string-এর result বাইরের f-string-এ বসেছে।

### Recommended Alternative

```python
name = "Masum"
marks = 85

result_text = f"{marks} marks"
message = f"Student: {name}, Result: {result_text}"

print(message)
```

Output একই:

```text
Student: Masum, Result: 85 marks
```

দ্বিতীয় পদ্ধতিটি beginner-দের জন্য বেশি readable এবং maintain করা সহজ।

## 13. Expressions Versus Statements

f-string-এর মধ্যে expression এবং statement-এর পার্থক্য বোঝা জরুরি।

**Expression** একটি value দেয়। যেমন:

```python
a + b
len("Python")
marks >= 40
```

**Statement** কোনো action সম্পাদন করে। যেমন:

```python
a = 10
print("Hello")
```

সাধারণ f-string expression-এর জায়গায় assignment statement লেখা যায় না।

### Incorrect Example

```python
number = 10

# সাধারণ assignment এখানে বৈধ expression নয়
# print(f"{number = 20}")
```

এই উদাহরণে `{number = 20}`-কে assignment হিসেবে ব্যবহার করা যাবে না। Python 3.8-এর debug syntax `f"{number=}"`-এর সঙ্গে এটি এক নয়।

### Correct Approach

```python
number = 20

print(f"Number: {number}")
```

Output:

```text
Number: 20
```

প্রথমে variable-এ value assign করো, তারপর f-string-এ ব্যবহার করো।

## 14. Debugging with Expression Labels

Python 3.8 থেকে `=` syntax দিয়ে expression এবং result একসঙ্গে দেখা যায়।

### Example

```python
price = 100
quantity = 3

print(f"{price=}")
print(f"{quantity=}")
print(f"{price * quantity=}")
```

Output:

```text
price=100
quantity=3
price * quantity=300
```

এটি debugging-এর সময় সুবিধাজনক।

### With Formatting

```python
price = 125.678

print(f"{price=:.2f}")
```

Output:

```text
price=125.68
```

এখানে debug syntax-এর সঙ্গে format specification ব্যবহার করা হয়েছে।

## 15. Practical Program: Student Result

```python
name = input("Enter student name: ")
marks1 = float(input("Enter marks for subject 1: "))
marks2 = float(input("Enter marks for subject 2: "))
marks3 = float(input("Enter marks for subject 3: "))

total = marks1 + marks2 + marks3
average = total / 3

result = "Pass" if all(
    mark >= 40 for mark in [marks1, marks2, marks3]
) else "Fail"

print("=" * 35)
print("STUDENT RESULT".center(35))
print("=" * 35)
print(f"Name    : {name}")
print(f"Total   : {total:.2f}/300")
print(f"Average : {average:.2f}")
print(f"Result  : {result}")
print("=" * 35)
```

Example output:

```text
===================================
          STUDENT RESULT
===================================
Name    : Masum
Total   : 255.00/300
Average : 85.00
Result  : Pass
===================================
```

এই program-এ f-string-এর মধ্যে variable এবং formatted numeric value ব্যবহার করা হয়েছে। এখানে ধরে নেওয়া হয়েছে যে প্রতিটি subject-এর পূর্ণমান 100 এবং pass mark 40। Input validation এখনো যোগ করা হয়নি।

## 16. Common Errors and Best Practices

### Common Errors

1. **Missing `f`:** `"{name}"` লিখলে variable-এর value বসবে না।
2. **Missing braces:** `{` বা `}` ভুলভাবে ব্যবহার করলে `SyntaxError` হতে পারে।
3. **Invalid dictionary key:** অনুপস্থিত key ব্যবহার করলে `KeyError` হতে পারে।
4. **Invalid list index:** list-এর বাইরে index ব্যবহার করলে `IndexError` হতে পারে।
5. **Division by zero:** `{a / b}`-এ `b` শূন্য হলে `ZeroDivisionError` হবে।
6. **Incorrect percentage:** `85`-কে `:.2%` দিলে `8500.00%` দেখা যাবে।
7. **Complex expressions:** অনেক logic এক লাইনে লিখলে code বোঝা কঠিন হয়।

### Best Practices

- ছোট এবং সহজ expression f-string-এর মধ্যে রাখো।
- Complex calculation আগে আলাদা variable-এ করো।
- প্রয়োজন অনুযায়ী `.2f`, `,.2f` ও `.2%` ব্যবহার করো।
- Dictionary access-এর ক্ষেত্রে key অনুপস্থিত হতে পারে কি না বিবেচনা করো।
- User input থেকে পাওয়া data validate করো।
- Debugging-এর জন্য `f"{variable=}"` ব্যবহার করতে পারো।
- Readability বজায় রাখো; শুধু code ছোট করার জন্য সব calculation f-string-এ লিখবে না।

## 17. Practice Exercises

### Exercise 1: Arithmetic Expression

`a = 20` এবং `b = 6` দিয়ে f-string ব্যবহার করে sum, difference ও product দেখাও।

### Exercise 2: Comparison

`age = 19` ব্যবহার করে দেখাও যে ব্যক্তি 18 বা তার বেশি বয়সী কি না।

### Exercise 3: Function Call

`numbers = [12, 25, 8, 40]` থেকে f-string দিয়ে maximum, minimum ও total দেখাও।

### Exercise 4: String Method

`name = "masum"` ব্যবহার করে uppercase এবং title-case output দেখাও।

### Exercise 5: Conditional Expression

`marks = 32` হলে f-string দিয়ে `Pass` অথবা `Fail` দেখাও; pass mark 40।

### Exercise 6: Dictionary

নিচের dictionary থেকে name এবং CGPA দেখাও।

```python
student = {
    "name": "Masum",
    "cgpa": 3.95
}
```

### Exercise 7: Formatting

`price = 98765.4321`-কে হাজারের separator ও দুই decimal place-সহ দেখাও।

### Exercise 8: Percentage

`completed = 37`, `total = 40` থেকে completion percentage দুই decimal place-এ দেখাও।

### Exercise 9: Output Prediction

```python
a = 7
b = 3

print(f"{a + b * 2=}")
print(f"{a / b:.2f}")
```

Output কী হবে?

### Exercise 10: Mini Challenge

একটি program লেখো, যা তিনটি subject-এর marks নিয়ে total, average এবং pass/fail result দেখাবে। প্রতিটি mark 0–100-এর মধ্যে হতে হবে। f-string ব্যবহার করে সুন্দর report তৈরি করো।

## 18. Practice Answer Key

### Answer 1

```python
a = 20
b = 6

print(f"Sum: {a + b}")
print(f"Difference: {a - b}")
print(f"Product: {a * b}")
```

### Answer 2

```python
age = 19

print(f"Adult: {age >= 18}")
```

Output:

```text
Adult: True
```

### Answer 3

```python
numbers = [12, 25, 8, 40]

print(f"Maximum: {max(numbers)}")
print(f"Minimum: {min(numbers)}")
print(f"Total: {sum(numbers)}")
```

### Answer 4

```python
name = "masum"

print(f"Uppercase: {name.upper()}")
print(f"Title case: {name.title()}")
```

### Answer 5

```python
marks = 32

print(f"Result: {'Pass' if marks >= 40 else 'Fail'}")
```

Output:

```text
Result: Fail
```

### Answer 6

```python
student = {
    "name": "Masum",
    "cgpa": 3.95
}

print(f"Name: {student['name']}")
print(f"CGPA: {student['cgpa']:.2f}")
```

### Answer 7

```python
price = 98765.4321

print(f"Price: {price:,.2f}")
```

Output:

```text
Price: 98,765.43
```

### Answer 8

```python
completed = 37
total = 40

print(f"Completion: {completed / total:.2%}")
```

Output:

```text
Completion: 92.50%
```

### Answer 9

Output:

```text
a + b * 2=13
2.33
```

প্রথম লাইনে multiplication আগে হয়েছে: `7 + 3 * 2 = 13`।

### Answer 10

```python
try:
    marks1 = float(input("Subject 1 marks: "))
    marks2 = float(input("Subject 2 marks: "))
    marks3 = float(input("Subject 3 marks: "))

    marks = [marks1, marks2, marks3]

    if not all(0 <= mark <= 100 for mark in marks):
        print("Marks must be between 0 and 100.")
    else:
        total = sum(marks)
        average = total / len(marks)
        result = "Pass" if all(mark >= 40 for mark in marks) else "Fail"

        print("\n--- Result Report ---")
        print(f"Total   : {total:.2f}/300")
        print(f"Average : {average:.2f}")
        print(f"Result  : {result}")

except ValueError:
    print("Please enter valid numeric marks.")
```

## 19. Chapter Summary

- f-string-এর `{}`-এর মধ্যে expression evaluate হয়।
- Arithmetic, comparison ও logical expression ব্যবহার করা যায়।
- Built-in এবং custom function call-এর result দেখানো যায়।
- String method, list indexing এবং dictionary access করা যায়।
- Conditional expression দিয়ে condition অনুযায়ী value নির্বাচন করা যায়।
- `:.2f`, `:,.2f` এবং `:.2%` দিয়ে numeric output format করা যায়।
- Python 3.8+ এ `f"{expression=}"` debugging-এর জন্য কাজে লাগে।
- সাধারণ f-string expression-এর মধ্যে assignment statement লেখা যায় না।
- Complex logic আলাদা variable-এ রাখলে code বেশি readable হয়।

## 20. Self-Assessment Checklist

- [ ] f-string-এর মধ্যে arithmetic expression লিখতে পারি।
- [ ] Comparison ও logical expression ব্যবহার করতে পারি।
- [ ] Function ও method call-এর result দেখাতে পারি।
- [ ] Conditional expression ব্যবহার করতে পারি।
- [ ] List ও dictionary থেকে value access করতে পারি।
- [ ] Expression-এর result format করতে পারি।
- [ ] Debugging-এর জন্য `=` syntax বুঝি।
- [ ] Expression ও statement-এর পার্থক্য বুঝি।
- [ ] Practical result report তৈরি করতে পারি।

**Next Topic:** `20_Formatting_Numbers_with_f_Strings.md` — এখানে integer, float, decimal places, percentage, scientific notation, sign, হাজারের separator এবং numeric formatting-এর অন্যান্য নিয়ম বিস্তারিতভাবে শিখব।