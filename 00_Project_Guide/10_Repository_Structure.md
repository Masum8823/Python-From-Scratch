# 10. Repository Structure

## 1. Introduction

একটি well-organized repository তৈরি করা programming শেখার গুরুত্বপূর্ণ অংশ। Repository-তে অনেক chapter, topic, code example, practice problem এবং project যুক্ত হলে সঠিক structure না থাকলে প্রয়োজনীয় information খুঁজে পাওয়া কঠিন হয়ে যায়।

এই repository-তে Python শেখার materials এমনভাবে সাজানো হবে, যাতে:

- Beginner সহজে learning শুরু করতে পারে।
- প্রতিটি chapter-এর topic আলাদাভাবে খুঁজে পাওয়া যায়।
- Documentation এবং code examples সংগঠিত থাকে।
- Practice problems ও projects পরিচালনা করা সহজ হয়।
- ভবিষ্যতে নতুন topic যোগ করা যায়।
- GitHub-এ repository পরিষ্কার ও readable থাকে।

এই ফাইলে repository-এর recommended folder hierarchy এবং file organization-এর নিয়ম ব্যাখ্যা করা হয়েছে।

---

## 2. Root Directory

Root directory হলো repository-এর প্রধান folder। Repository-এর মূল README, progress files এবং chapter folders এখানে থাকবে।

Recommended structure:

```text
Python-Learning/
├── README.md
├── PROGRESS.md
├── LEARNING_JOURNAL.md
├── WEAK_TOPICS.md
├── LICENSE
├── .gitignore
│
├── 00_Project_Guide/
├── 01_Installation_and_Environment/
├── 02_Python_Fundamentals/
├── 03_Data_Types_and_Type_Conversion/
├── 04_Operators/
├── 05_Input_Output_and_String_Formatting/
├── ...
└── 41_Career_and_Learning_Resources/
```

এখানে `Python-Learning` repository-এর নাম হিসেবে ব্যবহৃত হয়েছে। Actual repository name ভিন্ন হলেও structure একই রাখা যাবে।

### Root-Level Files

| File | Purpose |
|---|---|
| `README.md` | Repository introduction এবং main navigation |
| `PROGRESS.md` | Chapter ও project-এর overall progress |
| `LEARNING_JOURNAL.md` | Study session-এর learning record |
| `WEAK_TOPICS.md` | যেসব topic-এ আরও practice দরকার |
| `LICENSE` | Repository ব্যবহারের license terms |
| `.gitignore` | Git-এ কোন files track করা হবে না তা নির্ধারণ |

সব file শুরুতেই তৈরি করা বাধ্যতামূলক নয়। Repository-এর প্রয়োজন অনুযায়ী এগুলো ধীরে ধীরে যোগ করা যাবে।

---

## 3. Chapter Folder Naming

প্রতিটি chapter-এর জন্য আলাদা folder থাকবে।

Folder naming convention:

`ChapterNumber_Descriptive_Name`

উদাহরণ:

```text
00_Project_Guide/
01_Installation_and_Environment/
02_Python_Fundamentals/
03_Data_Types_and_Type_Conversion/
04_Operators/
05_Input_Output_and_String_Formatting/
```

### Naming Rules

1. Chapter number দুই digit-এ লেখা হবে।
2. Numbering `00` থেকে `41` পর্যন্ত চলবে।
3. Folder name-এ শব্দ আলাদা করতে underscore (`_`) ব্যবহার করা হবে।
4. Folder name descriptive হতে হবে।
5. একই chapter-এর file একই folder-এর মধ্যে রাখা হবে।
6. Folder rename করলে সংশ্লিষ্ট links update করতে হবে।

Numbering chapter-এর learning order বুঝতে সাহায্য করবে। তবে সব topic সব learner-এর জন্য একই order-এ শেখা বাধ্যতামূলক নয়।

---

## 4. Standard Chapter Structure

প্রতিটি chapter folder-এ একটি `README.md` এবং প্রয়োজন অনুযায়ী একাধিক topic file থাকবে।

উদাহরণ:

```text
02_Python_Fundamentals/
├── README.md
├── 01_What_Is_Python.md
├── 02_Python_Syntax.md
├── 03_Comments_and_Indentation.md
├── 04_Variables.md
├── 05_Naming_Conventions.md
├── 06_Keywords_and_Identifiers.md
└── 07_Basic_Program_Structure.md
```

এটি একটি illustrative structure। Actual chapter-এর subtopic list অনুযায়ী file সংখ্যা ও নাম নির্ধারণ করা হবে।

### Purpose of `README.md`

প্রতিটি chapter-এর `README.md` হবে সেই chapter-এর overview এবং navigation page।

এতে সাধারণত থাকবে:

- Chapter introduction
- Learning objectives
- Topic list
- প্রতিটি topic-এর Markdown link
- Recommended learning order
- Practice guidance
- Chapter completion checklist
- Related chapters-এর link

### Purpose of Individual Topic Files

প্রতিটি topic file-এ নির্দিষ্ট concept-এর বিস্তারিত explanation থাকবে।

এতে প্রয়োজন অনুযায়ী থাকবে:

- Introduction
- Core concepts
- Syntax
- Code examples
- Expected output
- Explanation
- Common mistakes
- Practice problems
- Summary
- References

সব topic-এর জন্য প্রতিটি section থাকা বাধ্যতামূলক নয়। Content-এর প্রয়োজন অনুযায়ী structure পরিবর্তন করা যাবে।

---

## 5. Use Separate Files for Separate Topics

একটি chapter-এর সব content একটি বিশাল Markdown file-এ রাখা উচিত নয়, যদি topic-গুলো সহজে আলাদা করা যায়।

উদাহরণস্বরূপ, `Built-in Data Structures` chapter-এ নিচের বিষয়গুলো থাকতে পারে:

```text
09_Built_in_Data_Structures/
├── README.md
├── 01_Lists.md
├── 02_Tuples.md
├── 03_Sets.md
├── 04_Dictionaries.md
├── 05_Sequence_Operations.md
├── 06_Mutability_and_Immutability.md
├── 07_Copying_Collections.md
└── 08_Comparing_Data_Structures.md
```

### Advantages

- প্রতিটি topic আলাদাভাবে পড়া যায়।
- নির্দিষ্ট concept দ্রুত খুঁজে পাওয়া যায়।
- ছোট file review ও update করা সহজ।
- Git diff-এ পরিবর্তন বোঝা সহজ হয়।
- ভবিষ্যতে topic যোগ বা সরানো সহজ হয়।

তবে খুব ছোট এবং ঘনিষ্ঠভাবে সম্পর্কিত বিষয়ের জন্য একটি file ব্যবহার করা যেতে পারে। File splitting-এর উদ্দেশ্য অপ্রয়োজনীয়ভাবে file সংখ্যা বাড়ানো নয়; বরং content পরিচালনা সহজ করা।

---

## 6. File Naming Convention

সব topic file-এর নাম descriptive এবং consistent হতে হবে।

Recommended format:

`TopicNumber_Descriptive_Name.md`

উদাহরণ:

```text
01_What_Is_Python.md
02_Python_Syntax.md
03_Comments_and_Indentation.md
04_Variables.md
05_Naming_Conventions.md
```

### Rules

- File name-এ `.md` extension ব্যবহার করতে হবে।
- Topic-এর নাম দেখে file-এর content বোঝা যেতে হবে।
- একই folder-এ numbering duplicate করা যাবে না।
- অপ্রয়োজনীয় abbreviation এড়িয়ে চলতে হবে।
- File rename করলে সংশ্লিষ্ট Markdown links পরীক্ষা করতে হবে।
- File name এবং heading-এর wording যথাসম্ভব consistent রাখতে হবে।

`README.md` প্রতিটি chapter folder-এর overview হিসেবে ব্যবহার করা হবে।

---

## 7. Organize Code Examples and Practice Files

এই repository মূলত documentation-ভিত্তিক হলেও প্রয়োজন অনুযায়ী runnable Python code আলাদাভাবে রাখা যেতে পারে।

একটি সম্ভাব্য structure:

```text
Python-Learning/
├── 02_Python_Fundamentals/
│   ├── README.md
│   ├── 01_What_Is_Python.md
│   ├── 02_Python_Syntax.md
│   └── ...
│
├── practice/
│   ├── fundamentals/
│   │   ├── variables.py
│   │   ├── operators.py
│   │   └── conditions.py
│   │
│   ├── data_structures/
│   └── problem_solving/
│
└── projects/
    ├── simple_calculator/
    └── number_guessing_game/
```

এটি একটি optional structure। শুরুতেই সব folder তৈরি করতে হবে না।

### Documentation Code vs Runnable Files

**Documentation code:** Markdown file-এর মধ্যে শেখানোর জন্য ব্যবহৃত ছোট example।

**Runnable Python files:** আলাদাভাবে `.py` file-এ রাখা code, যা সরাসরি execute করা যায়।

একই code Markdown ও `.py` file-এ রাখলে ভবিষ্যতে দুই জায়গার version আলাদা হয়ে যাওয়ার সম্ভাবনা থাকে। তাই duplicated code maintain করার প্রয়োজন আছে কি না, সেটি বিবেচনা করতে হবে।

শুধু ছোট example-এর জন্য আলাদা `.py` file তৈরি করা বাধ্যতামূলক নয়।

---

## 8. Organize Practice Problems

Practice problems chapter অনুযায়ী বা difficulty অনুযায়ী সংগঠিত করা যেতে পারে।

উদাহরণ:

```text
practice/
├── README.md
├── fundamentals/
│   ├── basic_variables.md
│   ├── operators.md
│   └── conditional_statements.md
├── loops/
│   ├── basic_loops.md
│   └── nested_loops.md
├── data_structures/
│   ├── list_problems.md
│   └── dictionary_problems.md
└── algorithms/
    ├── searching.md
    └── sorting.md
```

### Practice Organization Rules

- Problem-এর title ও statement পরিষ্কার হতে হবে।
- Input ও expected output প্রয়োজন অনুযায়ী উল্লেখ করতে হবে।
- Difficulty label ব্যবহার করলে consistent রাখতে হবে।
- Solution একই file-এ বা আলাদা solution file-এ রাখা যেতে পারে।
- Solution আলাদা রাখলে তার link স্পষ্টভাবে দিতে হবে।
- অন্য source-এর problem ব্যবহার করলে প্রয়োজন অনুযায়ী source উল্লেখ করতে হবে।

Practice folder-এর structure repository-এর growth অনুযায়ী পরিবর্তন করা যাবে।

---

## 9. Organize Projects

Project folder-এর মধ্যে একটি নির্দিষ্ট application-এর প্রয়োজনীয় files রাখা হবে।

উদাহরণ:

```text
projects/
└── simple_calculator/
    ├── README.md
    ├── main.py
    ├── calculator.py
    └── tests/
        └── test_calculator.py
```

### Project README

প্রতিটি উল্লেখযোগ্য project-এর README-তে প্রয়োজন অনুযায়ী থাকবে:

- Project overview
- Features
- Requirements
- Installation instructions
- How to run
- Example usage
- Testing instructions
- Limitations
- Future improvements

Project ছোট হলে একটি `main.py` file-ই যথেষ্ট হতে পারে। Project বড় হলে code, tests, configuration এবং documentation আলাদা করা যেতে পারে।

---

## 10. Internal Markdown Links

একটি Markdown file থেকে অন্য file-এ যাওয়ার জন্য relative link ব্যবহার করা হবে।

### Link Within the Same Folder

```markdown
[Python Syntax](02_Python_Syntax.md)
```

### Link to Another Chapter

```markdown
[Python Fundamentals](../02_Python_Fundamentals/README.md)
```

### Link to the Parent Repository

```markdown
[Repository Home](../README.md)
```

### Link Rules

1. Link destination actual file path-এর সঙ্গে মিলতে হবে।
2. File move বা rename করলে related links update করতে হবে।
3. Link text meaningful হতে হবে।
4. অপ্রয়োজনীয়ভাবে পুরো URL লিখে link text হিসেবে ব্যবহার করা এড়িয়ে চলতে হবে।
5. Case-sensitive environment-এর জন্য file name-এর capitalization consistent রাখতে হবে।

Relative links repository clone করার পরও সাধারণত কাজ করে, তাই internal navigation-এর জন্য এগুলো উপযোগী।

---

## 11. Chapter Table of Contents

প্রতিটি chapter-এর `README.md`-এ একটি Table of Contents (TOC) থাকবে।

উদাহরণ:

```markdown
# Python Fundamentals

## Learning Objectives

এই chapter শেষে তুমি Python-এর basic syntax, variable এবং
program structure সম্পর্কে ধারণা পাবে।

## Topics

1. [What Is Python?](01_What_Is_Python.md)
2. [Python Syntax](02_Python_Syntax.md)
3. [Comments and Indentation](03_Comments_and_Indentation.md)
4. [Variables](04_Variables.md)
5. [Naming Conventions](05_Naming_Conventions.md)

## Practice

- Basic syntax practice
- Variable-based problems
- Small programming exercises
```

### TOC Rules

- Topic list actual file-এর সঙ্গে মিলতে হবে।
- Learning order থাকলে সেই অনুযায়ী সাজাতে হবে।
- নতুন topic যোগ করলে TOC update করতে হবে।
- File rename করলে সংশ্লিষ্ট TOC link update করতে হবে।
- অপ্রয়োজনীয় duplicate links রাখা যাবে না।

---

## 12. Repository Navigation

Repository ব্যবহারকারীর জন্য navigation সহজ হওয়া উচিত।

Recommended navigation flow:

```text
Root README
    |
    v
Chapter README
    |
    v
Individual Topic
    |
    v
Practice Problems
    |
    v
Mini Project
    |
    v
Progress Update
```

এটি একটি conceptual learning flow, বাধ্যতামূলক file dependency নয়।

প্রতিটি chapter-এর README থেকে topic files-এ যাওয়া যাবে। Topic file-এ প্রয়োজন অনুযায়ী related topic, prerequisite এবং next topic-এর link থাকবে।

### Navigation Guidelines

- Root README থেকে major chapters-এ যাওয়া যাবে।
- Chapter README থেকে সব subtopic-এ যাওয়া যাবে।
- Related chapters-এর মধ্যে cross-reference থাকবে।
- Broken link এড়ানোর জন্য নিয়মিত link check করতে হবে।
- Navigation যেন নতুন learner-এর জন্য অতিরিক্ত জটিল না হয়।

---

## 13. Manage Shared Resources

কিছু resource একাধিক chapter-এ কাজে লাগতে পারে। সেগুলো উপযুক্ত central location-এ রাখা যেতে পারে।

উদাহরণ:

- Glossary
- Coding conventions
- Learning resources
- Progress tracking
- Reusable project templates
- Common troubleshooting guidance

একই explanation অনেক file-এ পুরোপুরি copy করার বদলে প্রয়োজন অনুযায়ী মূল file-এর link দেওয়া যেতে পারে।

তবে beginner-friendly context-এর জন্য কোনো concept সংক্ষেপে পুনরায় ব্যাখ্যা করা উপকারী হলে সেটি করা যাবে।

লক্ষ্য হবে অপ্রয়োজনীয় duplication কমানো, কিন্তু learning experience দুর্বল না করা।

---

## 14. Avoid Overengineering

Repository শুরুতেই অতিরিক্ত complex structure তৈরি করার প্রয়োজন নেই।

### Recommended Approach

1. প্রথমে root README ও chapter folders তৈরি করো।
2. প্রতিটি chapter-এর README এবং topic files যোগ করো।
3. প্রয়োজন অনুযায়ী practice ও project folders তৈরি করো।
4. Repository বড় হলে shared resources আলাদা করো।
5. বাস্তব প্রয়োজন দেখা দিলে structure উন্নত করো।

### Avoid

- প্রতিটি ছোট code example-এর জন্য আলাদা folder তৈরি করা।
- একই information অনেক জায়গায় duplicate করা।
- প্রয়োজন ছাড়া অতিরিক্ত nesting ব্যবহার করা।
- শুধু দেখতে professional করার জন্য অপ্রয়োজনীয় configuration যোগ করা।
- Structure পরিবর্তন করে internal links update করতে ভুলে যাওয়া।

একটি ভালো structure হলো এমন structure, যা সহজে বোঝা, ব্যবহার এবং maintain করা যায়।

---

## 15. Use `.gitignore` Appropriately

Python project-এ কিছু generated file এবং local environment repository-তে রাখা উচিত নয়।

উদাহরণ:

```gitignore
# Python cache
__pycache__/
*.py[cod]

# Virtual environments
.venv/
venv/

# Environment variables and secrets
.env

# Test and coverage artifacts
.pytest_cache/
.coverage
htmlcov/

# Editor and operating system files
.vscode/
.DS_Store
Thumbs.db
```

### Important Notes

- `.gitignore` Git-এ untracked matching files যোগ হওয়া থেকে বিরত রাখতে সাহায্য করে।
- আগে থেকেই tracked file-কে `.gitignore`-এ যোগ করলেই সেটি tracking থেকে স্বয়ংক্রিয়ভাবে বাদ যায় না।
- সব `.vscode/` configuration বাদ দেওয়া বাধ্যতামূলক নয়; team-shared settings দরকার হলে সেগুলো commit করা যেতে পারে।
- `.env`-এ secret থাকলে সেটি repository-তে commit করা যাবে না।
- Project-এর প্রয়োজন অনুযায়ী `.gitignore` update করতে হবে।

Documentation-only repository-তে সব pattern দরকার নাও হতে পারে। Python code ও project যোগ হওয়ার সঙ্গে সঙ্গে প্রাসঙ্গিক pattern রাখা যাবে।

---

## 16. Keep the Structure Consistent

Repository-র বিভিন্ন chapter-এ একই ধরনের structure ব্যবহার করা উচিত।

### Consistency Checklist

- [ ] Chapter folder-এর numbering consistent।
- [ ] Topic file-এর naming convention consistent।
- [ ] প্রতিটি chapter-এ `README.md` আছে।
- [ ] TOC links সঠিক।
- [ ] Code examples সঠিক file-এ রাখা হয়েছে।
- [ ] Practice ও project files সংগঠিত।
- [ ] Cross-references কার্যকর।
- [ ] Unnecessary duplicate content নেই।
- [ ] Root README update করা হয়েছে।
- [ ] Repository structure beginner-friendly।

সব chapter-এর content একরকম হবে না, কিন্তু organization-এর মৌলিক নিয়ম consistent থাকা উচিত।

---

## 17. Validate the Repository Structure

নতুন file যোগ করা বা পুরোনো file rename করার পর repository review করতে হবে।

### Manual Review

1. Folder ও file names পরীক্ষা করো।
2. Chapter README-এর TOC পরীক্ষা করো।
3. Internal links খুলে দেখো।
4. Code files সঠিক folder-এ আছে কি না যাচাই করো।
5. Duplicate file বা পুরোনো version আছে কি না দেখো।
6. Root README-তে নতুন chapter বা resource-এর link যোগ করো।

### Optional Automated Checks

Repository বড় হলে link checker, Markdown linter বা অন্যান্য validation tools ব্যবহার করা যেতে পারে।

Automated tool ব্যবহার করলে তার installation, configuration এবং limitations বুঝে নিতে হবে। ছোট repository-তে manual review-ই যথেষ্ট হতে পারে।

---

## 18. Final Repository Structure Checklist

Repository update করার সময় নিচের checklist ব্যবহার করা যেতে পারে।

### Organization

- [ ] Root README সঠিক।
- [ ] Chapter folders numbering অনুযায়ী সাজানো।
- [ ] প্রতিটি chapter-এর README আছে।
- [ ] Topic files descriptive name ব্যবহার করছে।
- [ ] Practice ও project folders প্রয়োজন অনুযায়ী তৈরি।

### Navigation

- [ ] Chapter TOC update করা হয়েছে।
- [ ] Internal links সঠিক।
- [ ] Related topics-এর cross-reference আছে।
- [ ] Root README থেকে navigation সহজ।

### Maintenance

- [ ] Duplicate files review করা হয়েছে।
- [ ] `.gitignore` প্রয়োজন অনুযায়ী update।
- [ ] Secrets ও local environment files commit করা হয়নি।
- [ ] নতুন file যোগ করার পর links যাচাই করা হয়েছে।
- [ ] Structure future expansion-এর উপযোগী।

---

## 19. Conclusion

একটি ভালো repository structure learning material খুঁজে পাওয়া, code practice করা এবং ভবিষ্যতে documentation maintain করা সহজ করে।

এই repository-তে:

1. Root directory-তে central navigation ও progress files থাকবে।
2. প্রতিটি chapter-এর আলাদা numbered folder থাকবে।
3. Chapter overview-এর জন্য `README.md` থাকবে।
4. Individual topics আলাদা Markdown files-এ রাখা হবে।
5. Practice problems ও projects প্রয়োজন অনুযায়ী আলাদা করা হবে।
6. Internal navigation-এর জন্য relative links ব্যবহার করা হবে।
7. Shared resources central location-এ রাখা হবে।
8. Repository-এর growth অনুযায়ী structure ধীরে ধীরে উন্নত করা হবে।

মূল লক্ষ্য হলো এমন একটি organized Python learning repository তৈরি করা, যা beginner হিসেবে ব্যবহার করা সহজ এবং advanced topic যোগ হলেও maintain করা সম্ভব।

---

## Next Step

পরবর্তী ফাইল: [11. Tools and Resources](11_Tools_and_Resources.md)

সেখানে Python শেখার জন্য প্রয়োজনীয় software, editor, interpreter, official documentation, debugging tools, practice platforms এবং অন্যান্য learning resources কীভাবে নির্বাচন ও ব্যবহার করতে হবে, তা আলোচনা করা হবে।
