# 06. Documentation Standards

## 1. Introduction

Documentation হলো কোনো software, programming concept, library বা project সম্পর্কে লিখিত explanation এবং reference material।

এই repository-তে Python programming-এর প্রতিটি topic Markdown (`.md`) file-এ document করা হবে। Notes-এর প্রধান ভাষা হবে বাংলা, তবে Python syntax, code, keywords এবং প্রয়োজনীয় technical terms ইংরেজিতে রাখা হবে।

Documentation-এর মূল উদ্দেশ্য হলো এমন notes তৈরি করা, যা একজন beginner সহজে বুঝতে পারে এবং পরবর্তীতে revision বা reference হিসেবে ব্যবহার করতে পারে।

এই ফাইলের standards অনুসরণ করে repository-র সব notes-এ consistency, readability এবং accuracy বজায় রাখার চেষ্টা করা হবে।

---

## 2. Core Documentation Principles

প্রতিটি documentation file তৈরির সময় নিচের principles অনুসরণ করতে হবে।

### 2.1 Clarity

প্রতিটি explanation সহজ, পরিষ্কার এবং সরাসরি হতে হবে।

কোনো concept বোঝানোর সময় অপ্রয়োজনীয় কঠিন শব্দ বা জটিল বাক্য ব্যবহার করা যাবে না।

### 2.2 Accuracy

Technical information, syntax এবং code examples সঠিক হতে হবে।

কোনো behavior Python version-এর ওপর নির্ভর করলে প্রয়োজন অনুযায়ী সেই version উল্লেখ করতে হবে।

### 2.3 Completeness

Topic-এর গুরুত্বপূর্ণ অংশগুলো বাদ দেওয়া যাবে না।

তবে completeness-এর অর্থ অপ্রয়োজনীয় information যোগ করা নয়। Topic বোঝা, ব্যবহার করা এবং practice করার জন্য যতটুকু প্রয়োজন, সেটি অন্তর্ভুক্ত করতে হবে।

### 2.4 Consistency

একই ধরনের topic-এর documentation-এ একই ধরনের formatting, heading structure এবং code presentation ব্যবহার করতে হবে।

### 2.5 Practical Learning

সম্ভব হলে explanation-এর সঙ্গে practical code example, expected output এবং প্রয়োজনীয় exercise থাকবে।

### 2.6 Maintainability

File structure, internal links এবং references এমনভাবে সাজাতে হবে, যাতে ভবিষ্যতে notes update করা সহজ হয়।

---

## 3. Language Standards

### 3.1 Primary Language

Documentation-এর প্রধান ভাষা হবে বাংলা।

বাংলা explanation সহজ ও স্বাভাবিক হতে হবে, যেন একজন beginner প্রথমবার পড়েই concept বোঝার চেষ্টা করতে পারে।

### 3.2 Technical Terms

Python-এর keywords, function names, class names এবং গুরুত্বপূর্ণ technical terms সাধারণত ইংরেজিতে রাখা হবে।

উদাহরণ:

- Variable
- Data Type
- Function
- Parameter
- Argument
- Return Value
- Loop
- Exception
- Object
- Class
- Module
- Package
- Iterator
- Generator

প্রয়োজন অনুযায়ী প্রথমবার term-এর পাশে বাংলা অর্থ বা explanation দেওয়া হবে।

উদাহরণ:

**Function:** নির্দিষ্ট কাজ সম্পন্ন করার জন্য তৈরি reusable code block।

### 3.3 Avoid Unnecessary Translation

Python-এর reserved keywords এবং syntax বাংলায় অনুবাদ করা যাবে না।

সঠিক:

`if`, `else`, `for`, `while`, `def`, `return`

ভুল পদ্ধতি:

Python keyword-কে বাংলায় লিখে code example তৈরি করা।

### 3.4 Natural Bangla

Explanation এমন হতে হবে যেন একজন শিক্ষক beginner-কে সহজভাবে বুঝিয়ে দিচ্ছেন।

অপ্রয়োজনীয়ভাবে প্রতিটি English word-এর বাংলা অনুবাদ করার প্রয়োজন নেই। যে technical term ইংরেজিতে রাখলে বোঝা সহজ হয়, সেটি ইংরেজিতেই রাখা যাবে।

---

## 4. File Naming Standards

সব Markdown file-এর নাম descriptive এবং consistent হতে হবে।

Recommended conventions:

- Chapter folder-এর নাম numbered হবে।
- Topic file-এর নাম numbered হবে।
- File name-এ শব্দ আলাদা করতে underscore (`_`) ব্যবহার করা হবে।
- File extension হবে `.md`।
- একই folder-এ numbering duplicate করা যাবে না।

উদাহরণ:

```text
02_Python_Fundamentals/
├── README.md
├── 01_What_Is_Python.md
├── 02_Python_Syntax.md
├── 03_Comments_and_Indentation.md
├── 04_Variables.md
└── 05_Naming_Conventions.md
```

এখানে numbering topic-এর recommended order নির্দেশ করে।

### File Naming Rules

1. File name দেখে topic বোঝা যেতে হবে।
2. Numbering ধারাবাহিক রাখতে হবে।
3. অপ্রয়োজনীয় abbreviation এড়িয়ে চলতে হবে।
4. File rename করলে সংশ্লিষ্ট Markdown links update করতে হবে।
5. Existing file-এর নাম পরিবর্তনের আগে internal links পরীক্ষা করতে হবে।

---

## 5. Heading Standards

Markdown heading-এর জন্য `#` ব্যবহার করা হবে।

Heading hierarchy সঠিকভাবে অনুসরণ করতে হবে।

```markdown
# Topic Title

## 1. Introduction

### 1.1 Basic Concept

### 1.2 Why It Is Important

## 2. Syntax

## 3. Examples
```

### Heading Rules

- প্রতিটি standalone note-এ একটি প্রধান `#` heading থাকবে।
- প্রধান section-এর জন্য `##` ব্যবহার করা হবে।
- Subsection-এর জন্য `###` ব্যবহার করা হবে।
- প্রয়োজন হলে আরও গভীর subsection-এর জন্য `####` ব্যবহার করা যাবে।
- শুধু text বড় দেখানোর জন্য heading ব্যবহার করা যাবে না।
- Heading-এর wording সংক্ষিপ্ত ও অর্থপূর্ণ হতে হবে।

সব topic-এর জন্য একই heading বাধ্যতামূলক নয়। Topic-এর nature অনুযায়ী structure পরিবর্তন করা যাবে।

---

## 6. Standard Structure of a Topic File

প্রতিটি topic file-এর জন্য একটি common structure অনুসরণ করা হবে।

```markdown
# Topic Name

## 1. Introduction

## 2. Learning Objectives

## 3. Core Concept

## 4. Syntax

## 5. Code Examples

## 6. Output and Explanation

## 7. Common Mistakes

## 8. Best Practices

## 9. Practice Problems

## 10. Summary

## 11. References
```

এই structure একটি guideline, rigid template নয়।

Topic ছোট হলে অপ্রয়োজনীয় section বাদ দেওয়া যাবে। Advanced topic হলে internal working, comparison, performance considerations বা additional sections যোগ করা যাবে।

### Purpose of Each Section

| Section | Purpose |
|---|---|
| Introduction | Topic কী এবং কেন গুরুত্বপূর্ণ তা বোঝানো |
| Learning Objectives | কী কী শিখতে পারবে তা উল্লেখ করা |
| Core Concept | মূল ধারণা ব্যাখ্যা করা |
| Syntax | Code লেখার নিয়ম দেখানো |
| Code Examples | Practical example দেওয়া |
| Output and Explanation | Code কীভাবে কাজ করে তা বোঝানো |
| Common Mistakes | সাধারণ ভুল চিহ্নিত করা |
| Best Practices | ভালো coding habits শেখানো |
| Practice Problems | নিজে অনুশীলনের সুযোগ দেওয়া |
| Summary | গুরুত্বপূর্ণ বিষয় সংক্ষেপে তুলে ধরা |
| References | নির্ভরযোগ্য source দেওয়া |

---

## 7. Introduction Standards

Introduction সংক্ষিপ্ত এবং informative হতে হবে।

এখানে সাধারণত নিচের প্রশ্নগুলোর উত্তর থাকবে:

- Topic-টি কী?
- কেন এটি শেখা দরকার?
- Python programming-এ এটি কোথায় ব্যবহৃত হয়?

উদাহরণ:

```markdown
## 1. Introduction

A variable is a name used to refer to a value in a program.

Python-এ variable ব্যবহার করে data-কে একটি নামে refer করা যায়।
এতে program-এর মধ্যে value ব্যবহার ও পরিবর্তন করা সহজ হয়।
```

Introduction-এ পুরো topic-এর বিস্তারিত explanation দেওয়ার প্রয়োজন নেই। বিস্তারিত আলোচনা পরবর্তী section-এ থাকবে।

---

## 8. Learning Objectives Standards

Learning objectives-এ topic শেষ করার পর কী করতে পারবে তা উল্লেখ করতে হবে।

উদাহরণ:

```markdown
## 2. Learning Objectives

এই topic শেষ করার পর তুমি পারবে:

- Variable তৈরি করতে।
- Variable-এর value ব্যবহার করতে।
- Variable-এর value update করতে।
- Naming conventions অনুসরণ করতে।
```

Objectives বাস্তবসম্মত এবং topic-এর সঙ্গে সম্পর্কিত হতে হবে।

---

## 9. Explanation Standards

Concept explanation beginner-friendly হতে হবে।

### 9.1 Explain One Concept at a Time

একটি paragraph-এ একসঙ্গে অনেক নতুন concept বোঝানোর চেষ্টা করা যাবে না।

প্রথমে মূল concept, তারপর তার behavior, এরপর example দেওয়া ভালো।

### 9.2 Explain Why, Not Only What

শুধু syntax দেখিয়ে থেমে যাওয়া যাবে না। প্রয়োজন অনুযায়ী কেন syntax-টি ব্যবহার করা হয়, সেটিও বোঝাতে হবে।

### 9.3 Use Examples

Abstract concept বোঝাতে ছোট, relevant এবং practical example ব্যবহার করা হবে।

### 9.4 Avoid Unnecessary Complexity

Beginner topic-এ অপ্রয়োজনীয় advanced code বা advanced terminology যোগ করা যাবে না।

যদি advanced term উল্লেখ করতেই হয়, তাহলে সংক্ষিপ্ত explanation দিতে হবে অথবা সংশ্লিষ্ট advanced topic-এর link দিতে হবে।

---

## 10. Code Example Standards

সব Python code example fenced code block-এ দিতে হবে এবং language হিসেবে `python` উল্লেখ করতে হবে।

সঠিক:

````markdown
```python
name = "Masum"
print(name)
```
````

### 10.1 Code Must Be Runnable

যে example-কে runnable বলা হবে, সেটি সংশ্লিষ্ট Python version ও required dependencies অনুযায়ী চালানো সম্ভব হতে হবে।

কোনো snippet শুধু একটি বড় program-এর অংশ হলে সেটি পরিষ্কারভাবে উল্লেখ করতে হবে।

### 10.2 Use Meaningful Names

Variable এবং function-এর নাম অর্থপূর্ণ হতে হবে।

সঠিক:

```python
student_name = "Rahim"
total_marks = 85
```

কম পরিষ্কার:

```python
x = "Rahim"
y = 85
```

`x` ও `y` কিছু mathematical বা short example-এ যথাযথ হতে পারে। কিন্তু সাধারণ explanation-এ meaningful naming বেশি উপকারী।

### 10.3 Keep Examples Focused

একটি example-এ সাধারণত একটি মূল concept শেখানো হবে।

একসঙ্গে অনেক unrelated concept যোগ করা যাবে না।

### 10.4 Follow Consistent Formatting

Python code-এ consistent indentation এবং readable spacing ব্যবহার করতে হবে।

```python
def calculate_sum(a, b):
    result = a + b
    return result


print(calculate_sum(5, 3))
```

Python code-এ সাধারণত প্রতি indentation level-এ চারটি space ব্যবহার করা হয়।

### 10.5 Avoid Unexplained Shortcuts

Beginner topic-এ এমন advanced syntax ব্যবহার করা যাবে না, যা আগে ব্যাখ্যা করা হয়নি—যদি না সেটি শেখানোর উদ্দেশ্যেই example-এ ব্যবহার করা হয়।

---

## 11. Output Standards

যে code example-এর output নির্দিষ্ট ও গুরুত্বপূর্ণ, তার output আলাদা fenced code block-এ দেখানো হবে।

উদাহরণ:

```python
name = "Masum"
print(name)
```

Output:

```text
Masum
```

### Output Rules

- Expected output সঠিক হতে হবে।
- Output-এ অতিরিক্ত text যোগ করা যাবে না, যদি program সেটি print না করে।
- Input-dependent output হলে input উল্লেখ করতে হবে।
- Interactive example-এর ক্ষেত্রে sample input ও output দুটিই দেখানো যেতে পারে।
- Random, time-dependent বা environment-dependent output হলে সেই বিষয়টি উল্লেখ করতে হবে।
- Error example-এর ক্ষেত্রে error type এবং প্রয়োজনীয় explanation দিতে হবে।

---

## 12. Line-by-Line Explanation Standards

যেসব example-এ একাধিক নতুন concept আছে, সেগুলোর গুরুত্বপূর্ণ line ব্যাখ্যা করতে হবে।

উদাহরণ:

```python
price = 100
quantity = 3

total = price * quantity

print(total)
```

Explanation:

1. `price = 100` — `price` variable-এ `100` রাখা হয়েছে।
2. `quantity = 3` — `quantity` variable-এ `3` রাখা হয়েছে।
3. `total = price * quantity` — দুটি value গুণ করে result `total`-এ রাখা হয়েছে।
4. `print(total)` — `total`-এর value output হিসেবে দেখানো হয়েছে।

প্রতিটি trivial line-এর explanation সব সময় প্রয়োজন নেই। মূল লক্ষ্য হলো নতুন বা গুরুত্বপূর্ণ concept বোঝানো।

---

## 13. Tables and Comparisons

একাধিক concept-এর পার্থক্য বা বৈশিষ্ট্য তুলনা করার সময় Markdown table ব্যবহার করা যেতে পারে।

উদাহরণ:

| Operator | Meaning | Example |
|---|---|---|
| `+` | Addition | `5 + 3` |
| `-` | Subtraction | `5 - 3` |
| `*` | Multiplication | `5 * 3` |
| `/` | Division | `6 / 3` |

### Table Rules

- Column heading অর্থপূর্ণ হতে হবে।
- প্রতিটি cell সংক্ষিপ্ত ও পরিষ্কার রাখতে হবে।
- Table-এ অপ্রয়োজনীয় paragraph লেখা যাবে না।
- জটিল explanation table-এর বাইরে দিতে হবে।
- Table ব্যবহার করলে তথ্য যেন পড়তে সুবিধা হয়, সেটি নিশ্চিত করতে হবে।

সব information table-এ দেওয়ার প্রয়োজন নেই। দীর্ঘ explanation-এর জন্য paragraph এবং list বেশি উপযুক্ত হতে পারে।

---

## 14. Lists and Checklists

একাধিক related item থাকলে bullet list ব্যবহার করা হবে।

উদাহরণ:

```markdown
- Read the concept.
- Write the code.
- Run the program.
- Check the output.
```

ধাপে ধাপে কোনো কাজ করার নির্দেশনা থাকলে numbered list ব্যবহার করা হবে।

Checklist-এর ক্ষেত্রে:

```markdown
- [ ] Read the topic.
- [ ] Run the examples.
- [ ] Solve the exercises.
```

List-এ একই ধরনের grammar এবং consistent wording বজায় রাখতে হবে।

---

## 15. Common Mistakes and Best Practices

Topic-এর সঙ্গে সম্পর্কিত গুরুত্বপূর্ণ mistakes ও best practices অন্তর্ভুক্ত করা হবে।

### Common Mistakes

এখানে দেখানো হবে:

- ভুল code বা ভুল approach
- কেন ভুল হচ্ছে
- Expected behavior কী
- কীভাবে ঠিক করতে হবে

### Best Practices

এখানে readable, maintainable, reliable এবং secure code লেখার উপযোগী নির্দেশনা থাকবে।

Best practice বোঝানোর সময় প্রয়োজন অনুযায়ী example দেওয়া হবে।

তবে সব topic-এর জন্য একই ধরনের mistake বা best practice প্রযোজ্য হবে না। Topic অনুযায়ী relevant information যোগ করতে হবে।

---

## 16. Practice Problems Standards

Practice problems সহজ থেকে কঠিন ক্রমে সাজানো হবে।

সম্ভব হলে তিনটি difficulty level রাখা হবে:

| Level | Description |
|---|---|
| Basic | মূল syntax ও concept practice |
| Intermediate | একাধিক concept একসঙ্গে ব্যবহার |
| Challenging | তুলনামূলক জটিল problem-solving |

### Exercise Rules

- Problem statement পরিষ্কার হতে হবে।
- প্রয়োজনীয় input এবং expected output উল্লেখ করতে হবে।
- Problem সংশ্লিষ্ট topic-এর সঙ্গে সম্পর্কিত হতে হবে।
- নতুন learner-এর জন্য অপ্রয়োজনীয় advanced dependency রাখা যাবে না।
- Solution থাকলে problem statement-এর পরপরই না দিয়ে আলাদা solution section বা file-এ রাখা যেতে পারে।

Practice problems-এর উদ্দেশ্য হলো নিজে চিন্তা করে solution তৈরি করার দক্ষতা উন্নত করা।

---

## 17. Summary Standards

প্রতিটি topic file-এর শেষে একটি সংক্ষিপ্ত summary রাখা যেতে পারে।

Summary-তে থাকবে:

- মূল concept
- গুরুত্বপূর্ণ syntax
- সবচেয়ে জরুরি পার্থক্য
- মনে রাখার মতো বিষয়

Summary-তে পুরো chapter-এর explanation পুনরাবৃত্তি করা যাবে না। এটি revision-এর জন্য সংক্ষিপ্ত reference হিসেবে কাজ করবে।

---

## 18. References and External Links

যে topic-এর জন্য official বা reliable external documentation প্রয়োজন, সেখানে references যোগ করা হবে।

উদাহরণ:

```markdown
## References

- [Python Official Tutorial](https://docs.python.org/3/tutorial/)
- [Python Built-in Functions](https://docs.python.org/3/library/functions.html)
```

### Reference Rules

- সম্ভব হলে official documentation ব্যবহার করতে হবে।
- Link প্রাসঙ্গিক ও কার্যকর হতে হবে।
- External source থেকে তথ্য নেওয়া হলে প্রয়োজন অনুযায়ী source উল্লেখ করতে হবে।
- নির্দিষ্ট Python version-এর documentation গুরুত্বপূর্ণ হলে সঠিক version ব্যবহার করতে হবে।
- যাচাই না করে কোনো reference link তৈরি করা যাবে না।
- External resource-কে নিজের লেখা content হিসেবে উপস্থাপন করা যাবে না।

---

## 19. Markdown Formatting Standards

Repository-এর notes GitHub-এ readable রাখার জন্য standard Markdown formatting অনুসরণ করা হবে।

### 19.1 Bold Text

গুরুত্বপূর্ণ term বা short phrase highlight করতে:

```markdown
**Important concept**
```

### 19.2 Inline Code

Code-এর ছোট অংশ, variable, function বা keyword দেখাতে:

```markdown
`print()`
`student_name`
`if`
```

### 19.3 Fenced Code Blocks

Python code, terminal command, output এবং plain text example দেখাতে fenced code block ব্যবহার করতে হবে।

### 19.4 Links

Repository-এর অন্য file link করতে relative path ব্যবহার করা হবে।

```markdown
[Python Fundamentals](../02_Python_Fundamentals/README.md)
```

Path অবশ্যই actual repository structure-এর সঙ্গে মিলতে হবে।

### 19.5 Horizontal Rules

একই file-এ বড় section আলাদা করার জন্য প্রয়োজন অনুযায়ী `---` ব্যবহার করা যাবে। তবে প্রতিটি section-এর পরে এটি যোগ করা বাধ্যতামূলক নয়।

### 19.6 Emojis

Documentation-এর মূল content পরিষ্কার ও professional রাখতে অপ্রয়োজনীয় emoji ব্যবহার করা হবে না। Learning objectives বা special callout-এ প্রয়োজন হলে সীমিতভাবে ব্যবহার করা যেতে পারে।

---

## 20. Python Version and Compatibility

Python সময়ের সঙ্গে update হয়। তাই version-dependent feature ব্যবহার করার সময় version compatibility বিবেচনা করতে হবে।

### Rules

1. Code example-এর জন্য supported Python version নির্ধারণ করতে হবে।
2. নতুন syntax ব্যবহার করলে সেটি কোন version-এ যুক্ত হয়েছে তা প্রাসঙ্গিক হলে উল্লেখ করতে হবে।
3. Deprecated feature থাকলে প্রয়োজন অনুযায়ী warning দিতে হবে।
4. Third-party library ব্যবহার করলে installation এবং dependency requirement উল্লেখ করতে হবে।
5. Example-এ ব্যবহৃত feature সংশ্লিষ্ট environment-এ যাচাই করতে হবে।

একটি example সব Python version-এ কাজ করবে—এমন দাবি করা যাবে না, যদি compatibility যাচাই করা না হয়ে থাকে।

---

## 21. Accuracy and Verification

Documentation-এ প্রকাশ করার আগে code এবং technical explanation যাচাই করতে হবে।

### Verification Checklist

- [ ] Explanation সঠিক।
- [ ] Syntax সঠিক।
- [ ] Runnable code example পরীক্ষা করা হয়েছে।
- [ ] Expected output যাচাই করা হয়েছে।
- [ ] Code formatting consistent।
- [ ] Variable ও function-এর নাম অর্থপূর্ণ।
- [ ] Python version-এর প্রয়োজনীয়তা উল্লেখ করা হয়েছে।
- [ ] External links সঠিক।
- [ ] Internal links সঠিক।
- [ ] কোনো গুরুত্বপূর্ণ concept বাদ পড়েনি।
- [ ] অপ্রয়োজনীয় repetition নেই।

কোনো code environment-dependent হলে verification-এর সীমাবদ্ধতা স্পষ্টভাবে উল্লেখ করতে হবে।

---

## 22. Accessibility and Readability

Documentation এমনভাবে সাজানো হবে, যাতে beginner এবং experienced learner উভয়েই প্রয়োজনীয় information খুঁজে পেতে পারে।

এ জন্য:

- Heading hierarchy ঠিক রাখতে হবে।
- দীর্ঘ paragraph ভেঙে ছোট paragraph করতে হবে।
- Meaningful link text ব্যবহার করতে হবে।
- Table প্রয়োজন অনুযায়ী ব্যবহার করতে হবে।
- Code block-এ সঠিক language identifier দিতে হবে।
- অপ্রয়োজনীয় formatting এড়াতে হবে।
- গুরুত্বপূর্ণ warning ও limitation পরিষ্কারভাবে লিখতে হবে।

Readability শুধু সুন্দর formatting নয়; information সহজে খুঁজে পাওয়া এবং বুঝতে পারাও এর অংশ।

---

## 23. Documentation Maintenance

Repository বড় হওয়ার সঙ্গে সঙ্গে documentation update করা প্রয়োজন হতে পারে।

Maintenance-এর সময়:

1. পুরোনো information যাচাই করতে হবে।
2. Broken links ঠিক করতে হবে।
3. পরিবর্তিত Python behavior অনুযায়ী example update করতে হবে।
4. Duplicate explanation কমাতে হবে।
5. Related files-এর cross-reference ঠিক রাখতে হবে।
6. নতুন topic যোগ হলে Table of Contents update করতে হবে।
7. File rename বা move করলে internal links পরীক্ষা করতে হবে।

Documentation একটি ongoing process। একবার লিখে রাখলেই সব সময় update ছাড়া ব্যবহারযোগ্য থাকবে, এমন নয়।

---

## 24. Standard Quality Checklist

কোনো note file complete ঘোষণা করার আগে এই checklist ব্যবহার করা হবে।

### Content Quality

- [ ] Topic-এর purpose পরিষ্কার।
- [ ] Core concepts ব্যাখ্যা করা হয়েছে।
- [ ] প্রয়োজনীয় syntax অন্তর্ভুক্ত।
- [ ] Relevant code examples আছে।
- [ ] Expected output দেওয়া হয়েছে, যেখানে প্রযোজ্য।
- [ ] গুরুত্বপূর্ণ code-এর explanation আছে।
- [ ] Common mistakes আলোচনা করা হয়েছে, যেখানে প্রাসঙ্গিক।
- [ ] Practice problems আছে, যেখানে প্রাসঙ্গিক।
- [ ] Summary এবং references যোগ করা হয়েছে, যেখানে উপযোগী।

### Formatting Quality

- [ ] File name সঠিক।
- [ ] Heading hierarchy ঠিক।
- [ ] Markdown syntax সঠিক।
- [ ] Code blocks সঠিকভাবে বন্ধ করা হয়েছে।
- [ ] Tables ও lists readable।
- [ ] Internal links যাচাই করা হয়েছে।
- [ ] English technical terms consistent।
- [ ] অপ্রয়োজনীয় repetition নেই।

---

## 25. Final Documentation Principles

এই repository-র documentation তৈরি ও update করার সময় মূল principles হবে:

1. সহজ ও পরিষ্কার বাংলা explanation।
2. Original Python syntax ও technical terminology বজায় রাখা।
3. Correct এবং relevant code examples।
4. Explanation ও practical learning-এর মধ্যে balance।
5. Consistent Markdown formatting।
6. Accurate references ও working links।
7. Beginner-friendly progression।
8. প্রয়োজন অনুযায়ী version compatibility উল্লেখ।
9. Verification-এর মাধ্যমে quality নিশ্চিত করা।
10. Maintenance ও future updates সহজ রাখা।

এই standards অনুসরণ করে repository-র notes এমনভাবে তৈরি করা হবে, যাতে সেগুলো learning material, revision guide এবং future reference—তিনভাবেই কাজে লাগে।

---

## Next Step

পরবর্তী ফাইল: [07. Code Example Conventions](07_Code_Example_Conventions.md)

সেখানে Python code কীভাবে উপস্থাপন করা হবে, sample input ও output কীভাবে দেখানো হবে, line-by-line explanation কখন প্রয়োজন এবং code example-এর জন্য কোন conventions অনুসরণ করা হবে, তা আরও নির্দিষ্টভাবে নির্ধারণ করা হবে।
