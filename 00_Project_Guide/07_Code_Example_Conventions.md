# 07. Code Example Conventions

## 1. Introduction

Python শেখার জন্য শুধু theory পড়া যথেষ্ট নয়। Code লেখা, run করা, output দেখা এবং code কীভাবে কাজ করে তা বোঝা অত্যন্ত গুরুত্বপূর্ণ।

এই repository-তে প্রতিটি code example এমনভাবে উপস্থাপন করা হবে, যাতে একজন beginner সহজে বুঝতে পারে এবং নিজে code লিখে practice করতে পারে।

এই ফাইলে Python code examples লেখার, উপস্থাপন করার, explain করার এবং verify করার standard নির্ধারণ করা হয়েছে।

---

## 2. Basic Rules for Code Examples

প্রতিটি code example তৈরির সময় নিচের নিয়মগুলো অনুসরণ করতে হবে।

1. Code সহজে পড়া ও বোঝা যায় এমন হতে হবে।
2. Example-এর উদ্দেশ্য পরিষ্কার হতে হবে।
3. Code block-এ সঠিক language identifier ব্যবহার করতে হবে।
4. প্রয়োজন অনুযায়ী expected output দেখাতে হবে।
5. নতুন concept থাকলে তার explanation দিতে হবে।
6. Runnable example-এ প্রয়োজনীয় code অন্তর্ভুক্ত থাকতে হবে।
7. Example-এ ব্যবহৃত syntax আগে শেখানো না হলে সেটি ব্যাখ্যা করতে হবে।
8. Code-এর সঙ্গে অপ্রয়োজনীয় complexity যোগ করা যাবে না।
9. ভুল code দেখালে কেন ভুল এবং কীভাবে ঠিক করতে হবে তা ব্যাখ্যা করতে হবে।
10. Code এবং output বাস্তবে যাচাই করার চেষ্টা করতে হবে।

---

## 3. Use Correct Code Blocks

Python code লেখার জন্য fenced code block ব্যবহার করতে হবে।

সঠিক format:

````markdown
```python
print("Hello, World!")
```
````

এখানে `python` language identifier ব্যবহার করার কারণে Markdown viewer code-টি Python syntax হিসেবে চিনতে পারে এবং syntax highlighting দেখাতে পারে।

### 3.1 Python Code

```python
name = "Masum"
age = 22

print(name)
print(age)
```

### 3.2 Terminal Commands

Terminal বা command prompt-এর command দেখাতে `bash` ব্যবহার করা যেতে পারে।

```bash
python --version
```

Windows-এ `py` command ব্যবহার করলে সেটিও স্পষ্টভাবে দেখানো যাবে।

```bash
py --version
```

### 3.3 Expected Output

Output দেখানোর জন্য `text` code block ব্যবহার করা হবে।

```text
Masum
22
```

**মনে রাখতে হবে:** Code, terminal command এবং output একই code block-এ মিশিয়ে দেওয়া যাবে না, যদি না example-এর উদ্দেশ্য সেটিই হয়।

---

## 4. Keep Examples Small and Focused

একটি example-এ সাধারণত একটি মূল concept শেখানোর চেষ্টা করতে হবে।

### Example: Variable

```python
name = "Masum"
print(name)
```

Output:

```text
Masum
```

এই example-এর উদ্দেশ্য হলো variable তৈরি করা এবং তার value print করা।

একই example-এ অপ্রয়োজনীয় loop, function, class বা অন্য advanced feature যোগ করার প্রয়োজন নেই।

### When a Larger Example Is Needed

কোনো concept বোঝাতে একাধিক feature ব্যবহার করা প্রয়োজন হলে larger example দেওয়া যাবে। তবে প্রতিটি feature-এর ভূমিকা ব্যাখ্যা করতে হবে।

---

## 5. Use Meaningful Variable Names

Code example-এ variable এবং function-এর নাম এমন হতে হবে, যাতে তাদের উদ্দেশ্য বোঝা যায়।

সঠিক:

```python
student_name = "Rahim"
total_marks = 85
```

কম descriptive:

```python
x = "Rahim"
y = 85
```

`x`, `y`, `i` এবং `n`-এর মতো ছোট নাম mathematical example বা নির্দিষ্ট context-এ উপযুক্ত হতে পারে। তবে সাধারণ beginner example-এ descriptive name ব্যবহার করা ভালো।

### Naming Guidelines

- Variable-এর নাম তার কাজ বা data বোঝাবে।
- Function-এর নাম তার action বোঝাবে।
- Python-এর reserved keywords variable name হিসেবে ব্যবহার করা যাবে না।
- Python-এর naming conventions অনুসরণ করতে হবে।
- একটি example-এর মধ্যে একই naming style বজায় রাখতে হবে।

উদাহরণ:

```python
def calculate_total(price, quantity):
    return price * quantity
```

এখানে `calculate_total`, `price` এবং `quantity` নামগুলো code-এর উদ্দেশ্য বুঝতে সাহায্য করে।

---

## 6. Follow Proper Indentation and Formatting

Python-এ indentation শুধু code সাজানোর বিষয় নয়; এটি program-এর structure নির্ধারণ করে।

সাধারণভাবে প্রতি indentation level-এ চারটি space ব্যবহার করতে হবে।

সঠিক:

```python
age = 20

if age >= 18:
    print("Adult")
```

ভুল indentation:

```python
age = 20

if age >= 18:
print("Adult")
```

দ্বিতীয় example-এ `if` block-এর body সঠিকভাবে indent করা হয়নি।

### Formatting Rules

1. Consistent indentation ব্যবহার করতে হবে।
2. প্রয়োজন অনুযায়ী blank line ব্যবহার করতে হবে।
3. Operator-এর দুই পাশে সাধারণত space রাখতে হবে।
4. Code-এর readability বজায় রাখতে হবে।
5. অপ্রয়োজনীয়ভাবে অনেক statement এক লাইনে লেখা এড়াতে হবে।

উদাহরণ:

```python
total = price * quantity
average = total / number_of_items
```

এই format পড়তে সহজ এবং beginner-এর জন্য উপযুক্ত।

---

## 7. Explain the Code Before or After the Example

Code example-এর আগে সংক্ষেপে বলা যেতে পারে এটি কী শেখাবে। এরপর code, output এবং explanation দেওয়া হবে।

Recommended pattern:

1. Concept introduction
2. Code example
3. Expected output
4. Explanation
5. Important observation, if needed

উদাহরণ:

### Example: Addition

Python-এ `+` operator ব্যবহার করে দুটি সংখ্যার যোগফল বের করা যায়।

```python
a = 10
b = 20

result = a + b

print(result)
```

Output:

```text
30
```

Explanation:

- `a = 10` — `a` variable-এ `10` রাখা হয়েছে।
- `b = 20` — `b` variable-এ `20` রাখা হয়েছে।
- `result = a + b` — দুটি value যোগ করে result রাখা হয়েছে।
- `print(result)` — result output হিসেবে দেখানো হয়েছে।

এভাবে learner code-এর প্রতিটি গুরুত্বপূর্ণ অংশের উদ্দেশ্য বুঝতে পারবে।

---

## 8. Line-by-Line Explanation Guidelines

প্রতিটি code example-এর সব line আলাদাভাবে explain করা বাধ্যতামূলক নয়।

যখন code-এ নতুন syntax, একাধিক ধাপ বা সহজে ভুল বোঝার মতো behavior থাকবে, তখন line-by-line explanation দেওয়া উচিত।

### Example

```python
numbers = [10, 20, 30]

for number in numbers:
    print(number)
```

Explanation:

1. `numbers = [10, 20, 30]` — তিনটি integer নিয়ে একটি list তৈরি করা হয়েছে।
2. `for number in numbers:` — list-এর প্রতিটি item একে একে `number` variable-এ নেওয়া হচ্ছে।
3. `print(number)` — প্রতিটি item আলাদাভাবে print করা হচ্ছে।

Output:

```text
10
20
30
```

এই explanation-এ `list`, `for loop` এবং iteration-এর সম্পর্ক পরিষ্কার করা হয়েছে।

### Avoid Repetition

একই সহজ syntax বারবার ব্যাখ্যা করার প্রয়োজন নেই, যদি learner ইতোমধ্যে সেটি শিখে থাকে এবং নতুন কোনো behavior না থাকে।

---

## 9. Show Expected Output Correctly

যে example-এর output নির্দিষ্ট, সেখানে expected output দেখাতে হবে।

উদাহরণ:

```python
x = 15
y = 5

print(x - y)
```

Output:

```text
10
```

### Output Rules

- Output code-এর সঙ্গে মিলতে হবে।
- `print()` না থাকলে output স্বয়ংক্রিয়ভাবে দেখানো হচ্ছে—এমন ধারণা তৈরি করা যাবে না।
- String-এর quotation marks source code-এ থাকে; `print()` সাধারণত সেগুলো output-এ দেখায় না।
- Multiple output থাকলে সঠিক order বজায় রাখতে হবে।
- Input নেওয়া হলে প্রয়োজন অনুযায়ী sample input দেখাতে হবে।
- Output environment-dependent হলে সেটি উল্লেখ করতে হবে।

### Example with Input

```python
name = input("Enter your name: ")
print("Hello,", name)
```

Sample interaction:

```text
Enter your name: Masum
Hello, Masum
```

এখানে `Masum` হলো sample user input।

---

## 10. Use Comments When They Add Value

Python code-এ comment ব্যবহার করে গুরুত্বপূর্ণ line বা logic explain করা যায়।

উদাহরণ:

```python
# Calculate the total price
price = 100
quantity = 3

total = price * quantity
print(total)
```

Comment code-এর উদ্দেশ্য বুঝতে সাহায্য করছে।

### Comment Guidelines

- Comment প্রয়োজনীয় information দেবে।
- Obvious code-এর জন্য অপ্রয়োজনীয় comment লেখা যাবে না।
- Comment এবং code-এর মধ্যে consistency থাকতে হবে।
- Comment দিয়ে ভুল বা misleading explanation দেওয়া যাবে না।
- Bangla explanation-এর সঙ্গে code comment English বা Bangla—যেটি context-এ বেশি পরিষ্কার, সেটি ব্যবহার করা যেতে পারে।

অপ্রয়োজনীয় comment:

```python
age = 20  # Assign 20 to age
```

এখানে code নিজেই সহজে বোঝা যাচ্ছে, তাই comment না দিলেও চলে।

---

## 11. Demonstrate Incorrect Code Carefully

কোনো common mistake শেখানোর জন্য ভুল code দেখানো যেতে পারে। তবে সেটি ইচ্ছাকৃতভাবে ভুল example হিসেবে চিহ্নিত করতে হবে।

### Incorrect Example

```python
if 10 > 5
    print("Ten is greater")
```

এই code-এ `if` condition-এর শেষে colon (`:`) নেই।

### Correct Example

```python
if 10 > 5:
    print("Ten is greater")
```

Output:

```text
Ten is greater
```

### Error Explanation Guidelines

ভুল code দেখালে:

1. কী ভুল হয়েছে তা চিহ্নিত করতে হবে।
2. কেন error হচ্ছে তা ব্যাখ্যা করতে হবে।
3. Correct code দেখাতে হবে।
4. প্রয়োজন অনুযায়ী error message দেখাতে হবে।
5. একই ধরনের ভুল ভবিষ্যতে কীভাবে এড়ানো যায় তা বোঝাতে হবে।

ভুল example-কে runnable বা correct code হিসেবে উপস্থাপন করা যাবে না।

---

## 12. Teach Concepts in the Correct Order

একটি example-এ এমন concept ব্যবহার করা যাবে না, যা learner-এর জন্য অপ্রয়োজনীয়ভাবে অজানা।

যেমন, Variable chapter-এ মূলত variable ও assignment বোঝানো উচিত।

```python
name = "Masum"
print(name)
```

এখানে `print()` আগে পরিচিত না থাকলে সংক্ষেপে ব্যাখ্যা করা যেতে পারে।

অন্যদিকে, beginner-কে variable শেখানোর সময় decorator, generator, lambda বা complex class structure ব্যবহার করা উচিত নয়।

### Prerequisite Rules

- Basic topic-এ basic syntax ব্যবহার করতে হবে।
- Advanced topic-এ পূর্ববর্তী concept পুনরায় কাজে লাগানো যাবে।
- নতুন syntax ব্যবহার করলে তার explanation দিতে হবে।
- প্রয়োজন অনুযায়ী পূর্ববর্তী topic-এর internal link দিতে হবে।

---

## 13. Use Progressive Examples

কোনো concept শেখানোর জন্য example-গুলো ধাপে ধাপে কঠিন করা ভালো।

উদাহরণ হিসেবে, function শেখানোর সময়:

### Example 1: Basic Function

```python
def greet():
    print("Hello!")
```

### Example 2: Function with a Parameter

```python
def greet(name):
    print("Hello,", name)
```

### Example 3: Function with a Return Value

```python
def add(a, b):
    return a + b
```

এই sequence-এ learner প্রথমে function definition, তারপর parameter এবং শেষে return value সম্পর্কে শিখতে পারে।

প্রতিটি example-এর output বা function call দেখানোর প্রয়োজন অনুযায়ী তা অন্তর্ভুক্ত করতে হবে।

---

## 14. Distinguish Between Similar Concepts

দুটি concept দেখতে কাছাকাছি হলে তাদের পার্থক্য আলাদাভাবে দেখাতে হবে।

উদাহরণ: `print()` এবং `return`

### Using `print()`

```python
def add(a, b):
    print(a + b)

add(5, 3)
```

Output:

```text
8
```

### Using `return`

```python
def add(a, b):
    return a + b

result = add(5, 3)
print(result)
```

Output:

```text
8
```

দুটি example-এর output একই হলেও behavior এক নয়।

- `print()` value-টি screen-এ দেখায়।
- `return` function থেকে value ফিরিয়ে দেয়, যাতে সেটি অন্যত্র ব্যবহার করা যায়।

এ ধরনের তুলনা learner-কে superficial similarity-এর বাইরে গিয়ে concept বুঝতে সাহায্য করে।

---

## 15. Use Type Hints When Appropriate

Beginner-level code example-এ type hints সব সময় প্রয়োজন নেই।

তবে type hints শেখানোর topic-এ বা advanced code-এ এগুলো ব্যবহার করা যেতে পারে।

```python
def add(a: int, b: int) -> int:
    return a + b
```

এখানে:

- `a: int` — `a`-এর expected type `int`।
- `b: int` — `b`-এর expected type `int`।
- `-> int` — function-এর expected return type `int`।

মনে রাখতে হবে, Python type hints সাধারণত runtime-এ স্বয়ংক্রিয়ভাবে type enforce করে না।

Type hints ব্যবহার করলে প্রয়োজন অনুযায়ী এই বিষয়টি ব্যাখ্যা করতে হবে।

---

## 16. External Libraries and Dependencies

কোনো example-এ Python-এর built-in feature-এর বাইরে third-party library ব্যবহার করলে dependency স্পষ্টভাবে উল্লেখ করতে হবে।

উদাহরণ:

```python
import requests

response = requests.get("https://example.com", timeout=10)
print(response.status_code)
```

এই example-এ `requests` third-party package ব্যবহার করা হয়েছে।

Documentation-এ প্রয়োজন অনুযায়ী উল্লেখ করতে হবে:

- কোন package ইনস্টল করতে হবে।
- Installation command কী।
- কোন Python version বা package version প্রয়োজন।
- Internet connection বা external service দরকার কি না।
- Example চালাতে কোনো configuration দরকার কি না।

Installation command-এর উদাহরণ:

```bash
python -m pip install requests
```

শুধু example দেখানোর জন্য অপ্রয়োজনীয় external dependency যোগ করা যাবে না। Standard library দিয়ে কাজ করা সম্ভব হলে beginner example-এ সেটি ব্যবহার করা যেতে পারে।

---

## 17. Handle Environment-Dependent Examples

সব code example প্রতিটি computer-এ একইভাবে কাজ করবে না।

যেমন:

- File handling
- Operating system operations
- Network requests
- Database connections
- Environment variables
- Random number generation
- Current date and time

এ ধরনের example-এর ক্ষেত্রে প্রয়োজনীয় assumptions ও limitations উল্লেখ করতে হবে।

### Example: Random Number

```python
import random

print(random.randint(1, 10))
```

এই code-এ `1` থেকে `10`-এর মধ্যে একটি random integer তৈরি করা হয়।

Output প্রতিবার একই হবে—এমন নিশ্চয়তা নেই।

তাই documentation-এ একটি sample output দেখালে সেটি শুধু উদাহরণ হিসেবে বিবেচনা করতে হবে।

---

## 18. Security and Safe Code Examples

Security-sensitive topic-এ code example তৈরির সময় নিরাপত্তার বিষয়টি বিবেচনা করতে হবে।

- Password বা API key সরাসরি code-এ রাখা যাবে না।
- Real credentials বা personal data example-এ ব্যবহার করা যাবে না।
- Database query শেখানোর সময় parameterized query-এর মতো নিরাপদ পদ্ধতি দেখাতে হবে।
- File operation-এর ক্ষেত্রে path ও permission বিবেচনা করতে হবে।
- Network request-এর ক্ষেত্রে timeout ও error handling প্রাসঙ্গিক হলে দেখাতে হবে।
- Dangerous operation থাকলে তার সম্ভাব্য প্রভাব ব্যাখ্যা করতে হবে।

Example-এ placeholder ব্যবহার করা যেতে পারে:

```python
api_key = "YOUR_API_KEY"
```

এটি শুধু placeholder—বাস্তব API key নয়। Documentation-এ key নিরাপদভাবে configure করার পদ্ধতি প্রাসঙ্গিক হলে দেখাতে হবে।

---

## 19. Code Verification Standards

Code example publish করার আগে যতটা সম্ভব বাস্তবে run করে যাচাই করতে হবে।

### Verification Process

1. Code-এর syntax পরীক্ষা করা।
2. প্রয়োজনীয় input ও dependency প্রস্তুত করা।
3. Code run করা।
4. Output প্রত্যাশার সঙ্গে মিলিয়ে দেখা।
5. Error handling প্রাসঙ্গিক হলে পরীক্ষা করা।
6. Python version compatibility যাচাই করা।
7. Code পরিবর্তন করলে output আবার পরীক্ষা করা।

### Verification Checklist

- [ ] Code syntax সঠিক।
- [ ] Indentation সঠিক।
- [ ] Variable ও function-এর নাম consistent।
- [ ] Example-এর উদ্দেশ্য পরিষ্কার।
- [ ] Output সঠিক।
- [ ] প্রয়োজনীয় import আছে।
- [ ] External dependency উল্লেখ করা হয়েছে।
- [ ] Version requirement প্রাসঙ্গিক হলে দেওয়া হয়েছে।
- [ ] Security risk বিবেচনা করা হয়েছে।
- [ ] Explanation code-এর সঙ্গে মিলে।

কোনো example বাস্তবে পরীক্ষা করা না হলে সেটিকে verified বলে দাবি করা যাবে না।

---

## 20. Standard Code Example Template

প্রয়োজন অনুযায়ী নিচের structure ব্যবহার করা যেতে পারে।

```markdown
### Example: Topic Name

এই example-এ কী শেখানো হবে, তা সংক্ষেপে উল্লেখ করো।

```python
# Python code
```

**Output:**

```text
Expected output
```

**Explanation:**

- গুরুত্বপূর্ণ line-এর ব্যাখ্যা।
- Code কীভাবে কাজ করে তার explanation।
- প্রয়োজনীয় observation বা limitation।


সব example-এ এই template হুবহু ব্যবহার করা বাধ্যতামূলক নয়। ছোট example-এর জন্য শুধু code ও output যথেষ্ট হতে পারে; complex example-এর জন্য বিস্তারিত explanation প্রয়োজন হতে পারে।

---

## 21. Final Code Example Checklist

প্রতিটি code example review করার সময় এই checklist ব্যবহার করা হবে।

### Readability

- [ ] Code সহজে পড়া যায়।
- [ ] Naming meaningful।
- [ ] Formatting consistent।
- [ ] Example-এর purpose পরিষ্কার।

### Learning Quality

- [ ] Concept সঠিকভাবে উপস্থাপন করা হয়েছে।
- [ ] Difficulty learner-এর level অনুযায়ী।
- [ ] প্রয়োজনীয় explanation আছে।
- [ ] Expected output দেওয়া হয়েছে, যেখানে প্রযোজ্য।
- [ ] Common mistake প্রাসঙ্গিক হলে দেখানো হয়েছে।

### Technical Quality

- [ ] Syntax সঠিক।
- [ ] Code যাচাই করা হয়েছে অথবা verification status পরিষ্কার।
- [ ] Dependency ও version requirement উল্লেখ করা হয়েছে।
- [ ] Environment-dependent behavior ব্যাখ্যা করা হয়েছে।
- [ ] Security considerations প্রাসঙ্গিক হলে অন্তর্ভুক্ত।

---

## 22. Conclusion

এই repository-তে code example শুধু syntax দেখানোর জন্য ব্যবহার করা হবে না। প্রতিটি example-এর উদ্দেশ্য হবে learner-কে concept বুঝতে, code-এর behavior ব্যাখ্যা করতে এবং নিজে problem solve করতে সাহায্য করা।

মূল নিয়মগুলো হলো:

1. Code readable ও focused হতে হবে।
2. Output সঠিকভাবে দেখাতে হবে।
3. নতুন concept সহজ ভাষায় explain করতে হবে।
4. ভুল code ও correct code স্পষ্টভাবে আলাদা করতে হবে।
5. Examples ধাপে ধাপে কঠিন করতে হবে।
6. প্রয়োজনীয় dependency ও limitations উল্লেখ করতে হবে।
7. Code যাচাই না করে verified বলে দাবি করা যাবে না।

এই conventions অনুসরণ করলে repository-র code examples consistent, beginner-friendly এবং ভবিষ্যতে reference হিসেবে ব্যবহারযোগ্য থাকবে।

---

## Next Step

পরবর্তী ফাইল: [08. Practice Guidelines](08_Practice_Guidelines.md)

সেখানে Python শেখার সময় কীভাবে নিয়মিত practice করতে হবে, problem-solving skill তৈরি করতে হবে, code নিজে লিখতে হবে এবং practice-এর অগ্রগতি যাচাই করতে হবে—তা বিস্তারিতভাবে আলোচনা করা হবে।
