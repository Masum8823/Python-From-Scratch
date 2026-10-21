# 12. Glossary and Technical Terms

## 1. Introduction

Programming শেখার সময় অনেক English technical term বারবার ব্যবহার করা হয়। এসব term-এর অর্থ পরিষ্কার না হলে code এবং documentation বুঝতে সমস্যা হতে পারে।

এই ফাইলে Python ও software development-এর গুরুত্বপূর্ণ technical terms-এর সহজ বাংলা ব্যাখ্যা দেওয়া হয়েছে।

এই glossary-তে রয়েছে:

- Programming fundamentals
- Python language terms
- Data structures
- Functions ও OOP
- Errors ও debugging
- Algorithms ও problem solving
- Software development tools
- Web development ও APIs
- Data science ও machine learning
- গুরুত্বপূর্ণ abbreviations

**ব্যবহারের নিয়ম:** কোনো technical term বুঝতে অসুবিধা হলে এই ফাইলে সেটি খুঁজে তার অর্থ পড়বে। প্রতিটি term মুখস্থ করা জরুরি নয়; শেখার সঙ্গে সঙ্গে অর্থগুলো বুঝে নেওয়াই মূল উদ্দেশ্য।

---

## 2. Basic Programming Terms

| Term | সহজ বাংলা অর্থ |
|---|---|
| Programming | Computer-কে নির্দিষ্ট কাজ করানোর জন্য instruction লেখা |
| Program | নির্দিষ্ট কাজ সম্পন্ন করার জন্য লেখা instruction-এর সমষ্টি |
| Programming Language | Computer program লেখার জন্য ব্যবহৃত language |
| Python | একটি high-level, general-purpose programming language |
| Code | Programming language-এ লেখা instruction |
| Source Code | Programmer-এর লেখা মূল program |
| Syntax | Code লেখার নিয়ম |
| Semantics | Code-এর অর্থ বা behavior |
| Statement | Program-এর একটি instruction |
| Expression | এমন code, যা evaluate করে একটি value তৈরি করে |
| Keyword | Language-এর সংরক্ষিত বিশেষ শব্দ |
| Identifier | Variable, function, class ইত্যাদির নাম |
| Variable | কোনো value-কে একটি নামে reference করার উপায় |
| Constant | যে value অপরিবর্তিত রাখার উদ্দেশ্যে ব্যবহার করা হয় |
| Literal | Code-এ সরাসরি লেখা নির্দিষ্ট value |
| Value | Data-এর নির্দিষ্ট মান |
| Data | Program-এ ব্যবহৃত তথ্য |
| Algorithm | সমস্যা সমাধানের ধাপে ধাপে পদ্ধতি |
| Logic | সমস্যা সমাধানের যুক্তি ও সিদ্ধান্তের নিয়ম |
| Input | Program-এ দেওয়া data |
| Output | Program থেকে পাওয়া ফলাফল |
| Execution | Program চালানোর প্রক্রিয়া |
| Runtime | Program execute হওয়ার সময় |
| Interpreter | Source code execute করতে ব্যবহৃত software |
| Compiler | Source code বা অন্য representation-কে target code-এ রূপান্তরকারী software |
| Debugging | Program-এর সমস্যা খুঁজে বের করে সমাধান করা |
| IDE | Code লেখা, run ও debug করার সমন্বিত development environment |
| Code Editor | Code লেখা ও edit করার software |
| Terminal | Command লিখে system বা development tools ব্যবহার করার interface |

---

## 3. Python Language Terms

| Term | সহজ বাংলা অর্থ |
|---|---|
| Built-in | Python-এর সঙ্গে আগে থেকেই দেওয়া feature |
| Built-in Function | Python-এ আগে থেকে থাকা function, যেমন `print()` |
| Built-in Type | Python-এর অন্তর্ভুক্ত data type |
| Module | Python code ও definitions-সহ একটি unit; সাধারণত একটি `.py` file |
| Package | Related modules ও subpackages সংগঠিত করার structure |
| Library | নির্দিষ্ট কাজের জন্য reusable code-এর collection |
| Framework | Application তৈরির জন্য structure ও conventions দেওয়া system |
| Import | অন্য module-এর functionality ব্যবহার করার জন্য সেটি load বা access করার ব্যবস্থা |
| Namespace | নাম ও সংশ্লিষ্ট object-এর mapping |
| Scope | কোন অংশে একটি name access করা যায় তার পরিসর |
| Indentation | Code-এর শুরুতে space দিয়ে block-এর structure বোঝানো |
| Block | একসঙ্গে সম্পর্কিত code statements-এর group |
| Interactive Mode | যেখানে code লিখে সঙ্গে সঙ্গে result দেখা যায় |
| Script | সাধারণত file-এ সংরক্ষিত এবং execute করা যায় এমন program |
| REPL | Read-Eval-Print Loop; code পড়ে, evaluate করে, result দেখিয়ে আবার input নেয় |
| Bytecode | Python-এর ক্ষেত্রে interpreter-এর ব্যবহৃত intermediate instruction representation |
| `__name__` | Python module-এর বিশেষ attribute |
| `__main__` | কোনো module সরাসরি program হিসেবে execute হলে প্রচলিত main-module নাম |
| Docstring | Module, class বা function সম্পর্কে documentation হিসেবে ব্যবহৃত string |
| Type Hint | Variable, parameter বা return value-এর প্রত্যাশিত type বোঝানোর annotation |
| Dynamic Typing | Runtime-এ object-এর type নির্ধারিত হওয়ার ব্যবস্থা |
| Duck Typing | Object-এর নির্দিষ্ট type-এর বদলে তার behavior বা capabilities-এর ওপর নির্ভর করা |

---

## 4. Data Types and Data Structures

| Term | সহজ বাংলা অর্থ |
|---|---|
| Data Type | কোনো value-এর ধরন ও তার ওপর প্রযোজ্য operation নির্ধারণকারী type |
| Integer (`int`) | পূর্ণসংখ্যার type |
| Float (`float`) | Floating-point number-এর type |
| String (`str`) | Text সংরক্ষণের type |
| Boolean (`bool`) | `True` বা `False` value-এর type |
| `None` | কোনো value নেই বা অনুপস্থিত বোঝাতে ব্যবহৃত special object |
| List | Ordered ও mutable collection |
| Tuple | Ordered ও immutable collection |
| Set | Unique element-সমৃদ্ধ collection |
| Dictionary (`dict`) | Key-value pair সংরক্ষণের mapping |
| Collection | একাধিক item একসঙ্গে সংরক্ষণের structure |
| Sequence | নির্দিষ্ট order-এ item রাখে এমন collection type |
| Mapping | Key-এর মাধ্যমে value access করার structure |
| Mutable | তৈরি হওয়ার পরে পরিবর্তন করা যায় |
| Immutable | তৈরি হওয়ার পরে পরিবর্তন করা যায় না |
| Iterable | যার item-গুলোর ওপর iteration করা যায় |
| Iterator | একবারে পরবর্তী item সরবরাহ করে এমন object |
| Generator | সাধারণত `yield` ব্যবহার করে item একে একে তৈরি করে এমন iterator-ভিত্তিক ব্যবস্থা |
| Index | Sequence-এর item-এর অবস্থান নির্দেশকারী সংখ্যা |
| Slice | Sequence-এর একটি অংশ নির্বাচন করার পদ্ধতি |
| Key | Dictionary-তে value শনাক্ত করার জন্য ব্যবহৃত identifier |
| Value | কোনো key-এর সঙ্গে সম্পর্কিত data |
| Hashable | Lifetime জুড়ে hash value অপরিবর্তিত থাকে এবং equality behavior উপযুক্ত থাকে এমন object; dictionary key বা set element হতে পারে |
| Comprehension | সংক্ষিপ্ত syntax দিয়ে collection তৈরি করার পদ্ধতি |
| Nested Structure | একটি data structure-এর মধ্যে আরেকটি data structure থাকা |
| Type Conversion | এক type-এর value-কে অন্য type-এ রূপান্তর করা |
| Type Casting | সাধারণভাবে type conversion বোঝাতে ব্যবহৃত term |
| Truthy | Boolean context-এ `True` হিসেবে গণ্য হওয়া value |
| Falsy | Boolean context-এ `False` হিসেবে গণ্য হওয়া value |

---

## 5. Operators and Control Flow

| Term | সহজ বাংলা অর্থ |
|---|---|
| Operator | Value বা variable-এর ওপর operation সম্পন্ন করার symbol বা keyword |
| Operand | যে value বা variable-এর ওপর operator কাজ করে |
| Arithmetic Operator | যোগ, বিয়োগ, গুণ, ভাগ ইত্যাদির operator |
| Comparison Operator | Value-এর মধ্যে তুলনা করার operator |
| Logical Operator | একাধিক condition-এর logical relationship নির্ধারণ করে |
| Assignment | Variable-এ value bind বা assign করা |
| Condition | কোনো সিদ্ধান্তের জন্য যাচাই করা expression |
| Conditional Statement | Condition অনুযায়ী code execute করার statement |
| `if` | Condition সত্য হলে code চালায় |
| `elif` | আগের condition false হলে অন্য condition পরীক্ষা করে |
| `else` | আগের condition-গুলো পূরণ না হলে বিকল্প block চালায় |
| Loop | Code বারবার execute করার ব্যবস্থা |
| Iteration | Loop-এর একটি ধাপ বা কোনো iterable-এর item ধরে এগোনোর প্রক্রিয়া |
| `for` Loop | Iterable-এর item ধরে iteration করার জন্য ব্যবহৃত loop |
| `while` Loop | Condition সত্য থাকা পর্যন্ত iteration করার জন্য ব্যবহৃত loop |
| `break` | Loop থেকে বেরিয়ে আসে |
| `continue` | বর্তমান iteration-এর বাকি অংশ বাদ দিয়ে পরের iteration-এ যায় |
| `pass` | কোনো কাজ না করে syntactically প্রয়োজনীয় statement হিসেবে ব্যবহৃত হয় |
| Infinite Loop | যে loop নিজে থেকে শেষ হয় না |
| Nested Loop | একটি loop-এর ভেতরে আরেকটি loop |
| Loop Control | Loop-এর execution নিয়ন্ত্রণের পদ্ধতি |
| Short-Circuit Evaluation | Logical expression-এর ফল নির্ধারণে যতটুকু evaluation দরকার, ততটুকুই করা |

---

## 6. Functions and Functional Programming

| Term | সহজ বাংলা অর্থ |
|---|---|
| Function | নির্দিষ্ট কাজ করার জন্য তৈরি reusable code block |
| Function Definition | Function তৈরি করার প্রক্রিয়া |
| Function Call | Function execute করার জন্য সেটিকে invoke করা |
| Parameter | Function definition-এ ব্যবহৃত input name |
| Argument | Function call করার সময় পাঠানো value বা object |
| Return Value | Function `return` দিয়ে যে result দেয় |
| `return` | Function থেকে result দিয়ে execution শেষ করে |
| Default Parameter | Argument না দিলে ব্যবহৃত default value |
| Keyword Argument | Parameter-এর নাম উল্লেখ করে পাঠানো argument |
| Positional Argument | অবস্থান অনুযায়ী পাঠানো argument |
| Variable-Length Arguments | পরিবর্তনশীল সংখ্যক argument গ্রহণের ব্যবস্থা |
| `*args` | অতিরিক্ত positional arguments tuple হিসেবে গ্রহণের প্রচলিত পদ্ধতি |
| `**kwargs` | অতিরিক্ত keyword arguments dictionary হিসেবে গ্রহণের প্রচলিত পদ্ধতি |
| Lambda Function | `lambda` দিয়ে লেখা ছোট anonymous function |
| Anonymous Function | যার সাধারণভাবে নির্দিষ্ট function name থাকে না |
| Recursion | Function নিজের মধ্যে নিজেকে call করে |
| Base Case | Recursive process থামার condition |
| Higher-Order Function | Function গ্রহণ করে বা function return করে এমন function |
| Callback | অন্য code দ্বারা পরে call করার জন্য দেওয়া function |
| Closure | বাইরের scope-এর variable মনে রাখতে পারে এমন nested function |
| Decorator | অন্য function বা class-এর behavior wrap বা extend করার ব্যবস্থা |
| Pure Function | একই input-এ একই output দেয় এবং observable side effect নেই এমন function |
| Side Effect | Function-এর return value-এর বাইরেও observable পরিবর্তন, যেমন file লেখা |
| Functional Programming | Function ও data transformation-কে গুরুত্ব দেওয়া programming approach |
| Generator Expression | Generator তৈরি করার concise expression |

---

## 7. Object-Oriented Programming (OOP)

| Term | সহজ বাংলা অর্থ |
|---|---|
| OOP | Object ও class-এর ধারণার ওপর ভিত্তি করে programming approach |
| Class | Object তৈরির জন্য ব্যবহৃত blueprint বা definition |
| Object | Class বা অন্য mechanism থেকে তৈরি runtime entity |
| Instance | কোনো class-এর নির্দিষ্ট object |
| Attribute | Object বা class-এর সঙ্গে সম্পর্কিত data বা function |
| Method | Class বা object-এর সঙ্গে সম্পর্কিত function |
| Constructor | প্রচলিতভাবে object initialization-এর সঙ্গে সম্পর্কিত mechanism |
| `__init__()` | Python-এ instance তৈরি হওয়ার পর initialize করার বিশেষ method |
| `self` | Instance method-এ বর্তমান instance-কে নির্দেশ করা প্রচলিত parameter |
| Encapsulation | Data ও সংশ্লিষ্ট behavior একত্রে রাখা এবং access নিয়ন্ত্রণের নকশা |
| Inheritance | বিদ্যমান class-এর behavior ব্যবহার করে নতুন class তৈরি করা |
| Polymorphism | একই interface দিয়ে ভিন্ন object-এর উপযুক্ত behavior ব্যবহার করা |
| Abstraction | অপ্রয়োজনীয় implementation detail আড়াল করে গুরুত্বপূর্ণ interface দেখানো |
| Composition | একটি object-এর মধ্যে অন্য object ব্যবহার করে behavior গঠন করা |
| Inheritance Hierarchy | Inheritance সম্পর্কের structure |
| Method Overriding | Subclass-এ inherited method-এর implementation নতুন করে নির্ধারণ করা |
| Method Overloading | একই নামের একাধিক method ভিন্ন signature-এ ব্যবহার করার ধারণা; Python-এ প্রচলিত ভাষার মতো সাধারণভাবে compile-time overloading নেই |
| Class Variable | Class-এর সঙ্গে সম্পর্কিত variable |
| Instance Variable | নির্দিষ্ট instance-এর সঙ্গে সম্পর্কিত variable |
| Property | Attribute-এর মতো interface দিয়ে controlled access দেওয়ার ব্যবস্থা |
| Dunder Method | Double underscore দিয়ে শুরু ও শেষ হওয়া special method, যেমন `__str__()` |
| Abstract Class | সাধারণত সরাসরি ব্যবহার করার বদলে subclass-এর interface বা behavior নির্ধারণে ব্যবহৃত class |
| Interface | বিভিন্ন implementation-এর জন্য নির্দিষ্ট behavior বা contract-এর ধারণা |
| Mixin | অন্য class-এ reusable behavior যোগ করার জন্য তৈরি class |

---

## 8. File Handling and Exception Handling

| Term | সহজ বাংলা অর্থ |
|---|---|
| File Handling | File পড়া, লেখা ও পরিচালনা করা |
| File Path | File-এর অবস্থান নির্দেশকারী path |
| Absolute Path | Root বা নির্দিষ্ট system location থেকে সম্পূর্ণ path |
| Relative Path | বর্তমান working directory বা নির্দিষ্ট base path-এর তুলনায় path |
| File Mode | File কীভাবে খোলা হবে তা নির্ধারণ করে, যেমন read বা write |
| Read | File থেকে data পড়া |
| Write | File-এ data লেখা |
| Append | বিদ্যমান content-এর শেষে data যোগ করা |
| Context Manager | Resource পরিচালনা ও cleanup-এর ব্যবস্থা |
| `with` Statement | Context manager ব্যবহার করার প্রচলিত statement |
| Exception | Runtime-এ কোনো exceptional condition বা error নির্দেশকারী object |
| Exception Handling | Exception ধরার ও উপযুক্তভাবে পরিচালনা করার প্রক্রিয়া |
| `try` | Exception হতে পারে এমন code রাখে |
| `except` | নির্দিষ্ট exception handle করে |
| `else` | `try` block-এ exception না হলে execute হয় |
| `finally` | সাধারণত exception ঘটুক বা না ঘটুক cleanup-এর জন্য execute হয় |
| `raise` | Exception ঘটায় বা আবার raise করে |
| Traceback | Exception ঘটার সময় execution-এর call path ও সংশ্লিষ্ট তথ্য |
| Custom Exception | নিজের প্রয়োজন অনুযায়ী তৈরি exception class |
| Resource Cleanup | File বা অন্য resource ব্যবহার শেষে যথাযথভাবে release করা |

---

## 9. Algorithms and Problem Solving

| Term | সহজ বাংলা অর্থ |
|---|---|
| Problem Solving | কোনো সমস্যার উপযুক্ত সমাধান তৈরি করার প্রক্রিয়া |
| Pseudocode | Programming language-এর নির্দিষ্ট syntax ছাড়া algorithm-এর ধাপ লেখা |
| Flowchart | Diagram দিয়ে program বা algorithm-এর flow দেখানো |
| Time Complexity | Input size বাড়লে algorithm-এর কাজের পরিমাণ কীভাবে বাড়ে তার বিশ্লেষণ |
| Space Complexity | Input size বাড়লে algorithm-এর memory requirement কীভাবে বাড়ে তার বিশ্লেষণ |
| Big O Notation | Algorithm-এর growth rate-এর asymptotic upper bound বোঝানোর notation |
| Best Case | নির্দিষ্ট input size-এর মধ্যে সবচেয়ে সুবিধাজনক পরিস্থিতি |
| Average Case | নির্দিষ্ট assumptions অনুযায়ী গড় performance |
| Worst Case | নির্দিষ্ট input size-এর মধ্যে সবচেয়ে অসুবিধাজনক পরিস্থিতি |
| Linear Search | একের পর এক item পরীক্ষা করে search করা |
| Binary Search | Sorted sequence-এ search space বারবার অর্ধেক করা |
| Sorting | Data নির্দিষ্ট order-এ সাজানো |
| Searching | নির্দিষ্ট item খোঁজা |
| Recursion | কোনো problem ছোট version-এ ভেঙে একই ধরনের process ব্যবহার করা |
| Data Structure | Data সংগঠিত ও পরিচালনা করার পদ্ধতি |
| Stack | Last In, First Out (LIFO) নীতির structure |
| Queue | First In, First Out (FIFO) নীতির structure |
| Linked List | Node ও link ব্যবহার করে data সংরক্ষণের structure |
| Tree | Hierarchical relationship প্রকাশকারী data structure |
| Graph | Vertex বা node এবং edge দিয়ে সম্পর্ক প্রকাশকারী structure |
| Hash Table | Hash ব্যবহার করে key-এর মাধ্যমে data access করার structure |
| Greedy Algorithm | প্রতিটি ধাপে স্থানীয়ভাবে ভালো choice নেওয়ার approach |
| Dynamic Programming | Overlapping subproblem-এর result reuse করে problem solve করার technique |
| Brute Force | সম্ভাব্য option সরাসরি পরীক্ষা করার approach |
| Optimization | কোনো objective অনুযায়ী solution বা performance উন্নত করা |

**গুরুত্বপূর্ণ:** Big O-কে সব সময় exact execution time হিসেবে ভাববে না। এটি সাধারণত input size বাড়ার সঙ্গে algorithm-এর resource usage কীভাবে বাড়ে তা বোঝাতে ব্যবহৃত হয়।

---

## 10. Errors and Software Testing

| Term | সহজ বাংলা অর্থ |
|---|---|
| Error | Program-এর কোনো সমস্যা বা ভুল |
| Syntax Error | Language-এর syntax rules ভঙ্গ হওয়া |
| Runtime Error | Program execute হওয়ার সময় ঘটে যাওয়া error |
| Logic Error | Program execute হলেও প্রত্যাশিত result না পাওয়ার কারণ |
| Bug | Software-এর defect বা অনাকাঙ্ক্ষিত সমস্যা |
| Debugging | Bug-এর কারণ শনাক্ত ও সমাধান করা |
| Testing | Software প্রত্যাশা অনুযায়ী কাজ করছে কি না যাচাই করা |
| Test Case | নির্দিষ্ট input, condition ও expected result-সহ একটি test |
| Unit Test | ছোট component বা function-এর behavior পরীক্ষা করা |
| Integration Test | একাধিক component একসঙ্গে ঠিকভাবে কাজ করে কি না পরীক্ষা করা |
| Regression Test | পরিবর্তনের কারণে আগে কাজ করা feature নষ্ট হয়েছে কি না যাচাই করা |
| Assertion | কোনো condition সত্য হওয়া প্রত্যাশা করে যাচাই করা |
| Test Coverage | Code-এর কতটুকু অংশ test-এর মাধ্যমে execute হয়েছে তার পরিমাপ |
| Test Suite | একসঙ্গে পরিচালিত test-এর collection |
| Mock | Test-এর সময় real dependency-এর বদলে ব্যবহার করা controlled substitute |
| Refactoring | External behavior না বদলে code structure উন্নত করা |
| Code Review | অন্যের বা নিজের code যাচাই করা |
| Linting | Code-এর সম্ভাব্য সমস্যা ও style issue পরীক্ষা করা |
| Formatting | Code-এর layout consistent রাখা |
| Static Analysis | Program execute না করে code বিশ্লেষণ করা |
| Type Checking | Type information ব্যবহার করে type-related inconsistency শনাক্ত করা |

---

## 11. Modules, Packages and Environments

| Term | সহজ বাংলা অর্থ |
|---|---|
| Dependency | কোনো project-এর কাজ করার জন্য প্রয়োজনীয় package বা component |
| Dependency Management | Project-এর dependency install, update ও maintain করা |
| Package Manager | Package install ও manage করার tool |
| `pip` | Python package install ও manage করার tool |
| PyPI | Python Package Index; Python package-এর প্রধান public index |
| Virtual Environment | Project-specific isolated Python environment |
| `venv` | Python-এর built-in virtual environment creation module |
| Environment Variable | Process বা application-এর configuration-এ ব্যবহৃত named value |
| Configuration | Application কীভাবে চলবে তার settings |
| Requirements File | Project-এর dependency তালিকা রাখার প্রচলিত file, সাধারণত `requirements.txt` |
| Lock File | Dependency-এর নির্দিষ্ট resolved version ও সম্পর্কিত তথ্য সংরক্ষণের file |
| Version | Software বা package-এর নির্দিষ্ট release identifier |
| Semantic Versioning | Version প্রকাশের একটি প্রচলিত convention, সাধারণত `MAJOR.MINOR.PATCH` |
| Compatibility | ভিন্ন version বা system-এর মধ্যে একসঙ্গে কাজ করার সামর্থ্য |
| Reproducible Environment | একই বা নির্ধারিত setup পুনরায় তৈরি করা যায় এমন environment |

---

## 12. Git and Software Development

| Term | সহজ বাংলা অর্থ |
|---|---|
| Version Control | File-এর পরিবর্তন ও history পরিচালনার ব্যবস্থা |
| Git | Distributed version control system |
| Repository | Project ও তার version history রাখার স্থান |
| Local Repository | নিজের computer-এ থাকা repository |
| Remote Repository | অন্য server বা hosting service-এ থাকা repository |
| GitHub | Git repository hosting ও collaboration platform |
| Commit | Repository history-তে একটি change snapshot সংরক্ষণ করা |
| Branch | আলাদা line of development |
| Merge | ভিন্ন branch-এর পরিবর্তন একত্র করা |
| Clone | Remote repository-এর local copy তৈরি করা |
| Pull | Remote-এর পরিবর্তন local repository-তে আনা ও integrate করা |
| Push | Local commit remote repository-তে পাঠানো |
| Merge Conflict | একই অংশের পরিবর্তন স্বয়ংক্রিয়ভাবে একত্র করা না গেলে তৈরি হওয়া conflict |
| `.gitignore` | Git-কে নির্দিষ্ট file বা directory track না করতে নির্দেশ দেওয়ার file |
| README | Project-এর purpose, setup ও usage ব্যাখ্যা করা document |
| Open Source | নির্দিষ্ট license-এর অধীনে source code দেখা, ব্যবহার বা পরিবর্তনের সুযোগ |
| License | Software বা content ব্যবহারের আইনগত শর্ত |
| Pull Request | পরিবর্তন review ও merge করার জন্য প্রস্তাব |
| Continuous Integration (CI) | Code change-এর সঙ্গে automated build ও test চালানোর practice |
| Continuous Delivery (CD) | Software release-এর জন্য change প্রস্তুত রাখার practice |
| Deployment | Software-কে ব্যবহারের উপযোগী environment-এ প্রকাশ বা চালু করা |

---

## 13. Web Development and APIs

| Term | সহজ বাংলা অর্থ |
|---|---|
| Web Development | Website বা web application তৈরি করা |
| Frontend | User-এর সঙ্গে সরাসরি interaction করা application অংশ |
| Backend | Server-side logic, data processing ও related functionality |
| Client | Server-এর service request করে এমন application বা device |
| Server | Request গ্রহণ করে response বা service দেয় এমন system |
| HTTP | Web communication-এর একটি application-layer protocol |
| HTTPS | TLS-এর মাধ্যমে সুরক্ষিত HTTP communication |
| Request | Server বা service-এর কাছে পাঠানো message |
| Response | Request-এর উত্তরে পাওয়া message |
| API | Software component-এর মধ্যে communication-এর interface |
| REST | Web API design-এর একটি architectural style |
| Endpoint | নির্দিষ্ট API resource বা operation access করার address |
| JSON | Data interchange-এর একটি text format |
| Serialization | Data-কে সংরক্ষণ বা পাঠানোর উপযোগী representation-এ রূপান্তর |
| Deserialization | Serialized representation থেকে data পুনরুদ্ধার করা |
| Authentication | User বা system-এর পরিচয় যাচাই করা |
| Authorization | কোন resource বা action access করা যাবে তা নির্ধারণ করা |
| Session | একাধিক interaction জুড়ে সম্পর্কিত state বজায় রাখার ব্যবস্থা |
| Cookie | Browser-এ সংরক্ষিত ছোট data, যা request-এর সঙ্গে পাঠানো হতে পারে |
| Database | Structured বা অন্যভাবে সংগঠিত data সংরক্ষণ ও পরিচালনার system |
| SQL | Relational database-এর data query ও management-এর language |
| ORM | Object-Relational Mapping; object ও relational database-এর মধ্যে mapping করার ব্যবস্থা |

---

## 14. Concurrency and Asynchronous Programming

| Term | সহজ বাংলা অর্থ |
|---|---|
| Concurrency | একাধিক কাজের progress overlapping হতে দেওয়ার ব্যবস্থা |
| Parallelism | একাধিক কাজ একই সময়ে বাস্তব execution-এ চলা |
| Thread | Process-এর মধ্যে execution-এর একটি path |
| Process | চলমান program-এর execution instance |
| Multiprocessing | একাধিক process ব্যবহার করে কাজ পরিচালনা |
| Multithreading | একাধিক thread ব্যবহার করে কাজ পরিচালনা |
| Asynchronous Programming | অপেক্ষার সময় অন্য কাজের progress সম্ভব করে এমন programming approach |
| `async` | Python-এ asynchronous function বা context-এর syntax-এর অংশ |
| `await` | Awaitable operation-এর completion-এর জন্য অপেক্ষা করার syntax |
| Coroutine | Asynchronous execution-এর সঙ্গে ব্যবহৃত বিশেষ object/function concept |
| Event Loop | Asynchronous task ও event পরিচালনার mechanism |
| I/O-bound | যেসব কাজের সময়ের বড় অংশ input/output অপেক্ষায় যায় |
| CPU-bound | যেসব কাজের সময়ের বড় অংশ processor computation-এ যায় |
| Race Condition | Timing বা execution order-এর ওপর নির্ভর করে result বদলে যেতে পারে এমন সমস্যা |
| Deadlock | একাধিক task একে অপরের resource-এর জন্য অপেক্ষা করে আটকে যাওয়া |

---

## 15. Data Science and Machine Learning

| Term | সহজ বাংলা অর্থ |
|---|---|
| Data Analysis | Data পরীক্ষা করে pattern, insight বা conclusion বের করা |
| Dataset | বিশ্লেষণ বা modeling-এর জন্য ব্যবহৃত data collection |
| DataFrame | সাধারণত row ও column-ভিত্তিক tabular data structure |
| Array | নির্দিষ্টভাবে সংগঠিত element-এর collection; numerical computing-এ বহুল ব্যবহৃত |
| Numerical Computing | Mathematical ও numerical calculation কম্পিউটারের মাধ্যমে করা |
| Data Visualization | Graph বা chart দিয়ে data উপস্থাপন করা |
| Statistics | Data সংগ্রহ, বিশ্লেষণ ও ব্যাখ্যার পদ্ধতি |
| Machine Learning (ML) | Data থেকে pattern শেখার মাধ্যমে prediction বা decision তৈরির পদ্ধতি |
| Artificial Intelligence (AI) | এমন system তৈরির বিস্তৃত ক্ষেত্র, যা বিভিন্ন ধরনের intelligent task সম্পাদন করে |
| Model | Data বা rules ব্যবহার করে prediction বা decision তৈরির learned বা designed system |
| Feature | Model-এর input হিসেবে ব্যবহৃত data attribute |
| Label | Supervised learning-এ target value |
| Training | Data ব্যবহার করে model-এর parameter শেখানো |
| Validation | Model বা configuration মূল্যায়ন ও নির্বাচন করার জন্য data ব্যবহার |
| Testing Dataset | Model-এর final performance মূল্যায়নের জন্য আলাদা রাখা data |
| Classification | Input-কে নির্দিষ্ট category-তে ভাগ করা |
| Regression | সাধারণত continuous numerical value predict করা |
| Overfitting | Training data-তে ভালো হলেও নতুন data-তে খারাপ perform করার প্রবণতা |
| Underfitting | Model data-এর গুরুত্বপূর্ণ pattern যথেষ্টভাবে শিখতে না পারা |
| Feature Engineering | Model-এর জন্য useful feature তৈরি বা transform করা |
| Data Preprocessing | Model বা analysis-এর আগে data পরিষ্কার ও প্রস্তুত করা |
| Normalization | নির্দিষ্ট range বা scale-এ data রূপান্তর করা; সুনির্দিষ্ট অর্থ context অনুযায়ী ভিন্ন হতে পারে |
| Standardization | সাধারণত mean ও standard deviation ব্যবহার করে feature scale রূপান্তর করা |
| Neural Network | Interconnected computational units-ভিত্তিক model |
| Deep Learning | একাধিক layer-যুক্ত neural network-ভিত্তিক machine learning পদ্ধতি |

---

## 16. Security and Professional Practices

| Term | সহজ বাংলা অর্থ |
|---|---|
| Cybersecurity | System, network ও data-কে অননুমোদিত access বা attack থেকে রক্ষা করা |
| Secure Coding | Security risk কমানোর উদ্দেশ্যে code লেখা |
| Authentication | পরিচয় যাচাই করা |
| Authorization | অনুমোদিত access নির্ধারণ করা |
| Encryption | Cryptographic technique ব্যবহার করে data-কে সুরক্ষিত representation-এ রূপান্তর করা |
| Hashing | Input থেকে নির্দিষ্ট ধরনের hash value তৈরি করা |
| Password Hashing | Password-কে সরাসরি সংরক্ষণ না করে উপযুক্ত password-hashing algorithm দিয়ে সংরক্ষণ করা |
| Secret | Password, token বা API key-এর মতো sensitive value |
| API Key | কোনো API ব্যবহারকারী বা application শনাক্ত বা authorize করতে ব্যবহৃত key |
| Environment Variable | Configuration বা secret reference রাখার একটি উপায়; নিজে থেকে secret storage-এর নিশ্চয়তা নয় |
| Input Validation | Input গ্রহণের আগে তার validity ও expected format পরীক্ষা করা |
| SQL Injection | Untrusted input-এর মাধ্যমে SQL query-এর intended structure পরিবর্তন করে attack করা |
| Least Privilege | কাজের জন্য যতটুকু permission দরকার, শুধু ততটুকু দেওয়া |
| Logging | Program-এর event ও diagnostic information record করা |
| Monitoring | System-এর health, behavior ও performance পর্যবেক্ষণ করা |
| Maintainability | Software বোঝা, পরিবর্তন ও maintain করা কতটা সহজ |
| Scalability | Workload বাড়লে system কতটা ভালোভাবে মানিয়ে নিতে পারে |
| Reliability | System ধারাবাহিকভাবে প্রত্যাশিতভাবে কাজ করার সক্ষমতা |
| Technical Debt | দ্রুত সিদ্ধান্ত বা অসম্পূর্ণ design-এর কারণে ভবিষ্যতে যে অতিরিক্ত maintenance cost তৈরি হয় |
| Documentation | Software, code বা process সম্পর্কে লিখিত ব্যাখ্যা |
| Code Readability | Code কত সহজে পড়া ও বোঝা যায় |
| Best Practice | নির্দিষ্ট পরিস্থিতিতে বহুল ব্যবহৃত ও উপকারী পদ্ধতি; সব ক্ষেত্রে একমাত্র সঠিক পদ্ধতি নয় |

---

## 17. Important Abbreviations

| Abbreviation | Full Form | সহজ বাংলা ব্যাখ্যা |
|---|---|---|
| API | Application Programming Interface | Software-এর মধ্যে যোগাযোগের interface |
| AI | Artificial Intelligence | কৃত্রিম বুদ্ধিমত্তা |
| CLI | Command-Line Interface | Command লিখে software ব্যবহার করার interface |
| CPU | Central Processing Unit | Computer-এর প্রধান processing unit |
| CSV | Comma-Separated Values | Tabular data সংরক্ষণের text format |
| CRUD | Create, Read, Update, Delete | Data-এর মৌলিক operation |
| CSS | Cascading Style Sheets | Webpage-এর presentation ও styling |
| DB | Database | Data সংরক্ষণ ও পরিচালনার system |
| DBMS | Database Management System | Database পরিচালনার software |
| DS | Data Structures | Data সংগঠিত করার structure |
| DSA | Data Structures and Algorithms | Data structure ও algorithm |
| GUI | Graphical User Interface | Visual element দিয়ে software ব্যবহার করার interface |
| HTML | HyperText Markup Language | Webpage-এর structure তৈরির markup language |
| HTTP | HyperText Transfer Protocol | Web communication protocol |
| HTTPS | HyperText Transfer Protocol Secure | TLS-সুরক্ষিত HTTP |
| IDE | Integrated Development Environment | Code development-এর সমন্বিত environment |
| I/O | Input/Output | Data input ও output |
| JSON | JavaScript Object Notation | Data interchange format |
| LIFO | Last In, First Out | সর্বশেষ item আগে বের হয় |
| ML | Machine Learning | Data থেকে pattern শেখার পদ্ধতি |
| OOP | Object-Oriented Programming | Object ও class-ভিত্তিক programming |
| OS | Operating System | Computer-এর resources পরিচালনাকারী system software |
| PEP | Python Enhancement Proposal | Python ecosystem-এর প্রস্তাব ও design document |
| REPL | Read-Eval-Print Loop | Interactive code execution cycle |
| SQL | Structured Query Language | Relational database query ও management language |
| TDD | Test-Driven Development | Test আগে লিখে development করার approach |
| TLS | Transport Layer Security | Communication সুরক্ষার cryptographic protocol |
| UI | User Interface | User-এর সঙ্গে interaction-এর অংশ |
| URL | Uniform Resource Locator | Resource-এর location নির্দেশকারী address |
| UTF | Unicode Transformation Format | Unicode character encode করার পদ্ধতির family |
| VCS | Version Control System | File-এর পরিবর্তনের history পরিচালনার system |
| VM | Virtual Machine | Software-এর মাধ্যমে তৈরি virtual computing environment |
| venv | Virtual Environment | Python project-এর isolated environment তৈরির module/tool |

---

## 18. Commonly Confused Terms

### 18.1 Argument vs Parameter

- **Parameter:** Function definition-এ লেখা input name।
- **Argument:** Function call করার সময় পাঠানো value।

```python
def greet(name):  # name is a parameter
    print("Hello", name)

greet("Masum")    # "Masum" is an argument
```

### 18.2 List vs Tuple

- **List:** Mutable; তৈরি হওয়ার পরে item পরিবর্তন করা যায়।
- **Tuple:** Immutable; tuple তৈরি হওয়ার পরে তার item assignment করে পরিবর্তন করা যায় না।

### 18.3 Syntax Error vs Logic Error

- **Syntax Error:** Code Python-এর syntax rules মেনে লেখা হয়নি।
- **Logic Error:** Code execute হলেও ভুল result তৈরি করে।

### 18.4 Module vs Package vs Library

- **Module:** Python code-এর একটি importable unit।
- **Package:** Related modules ও subpackages সংগঠিত করার structure।
- **Library:** Reusable functionality-এর collection।

এই terms-এর ব্যবহার বাস্তবে কিছুটা overlap করতে পারে।

### 18.5 Compiler vs Interpreter

- **Compiler:** Code-কে target representation-এ রূপান্তর করে।
- **Interpreter:** Program বা তার intermediate representation execute করে।

বাস্তব language implementation-এ compilation ও interpretation একসঙ্গে থাকতে পারে। Python implementation-ও একাধিক ধাপ ব্যবহার করতে পারে।

### 18.6 Concurrency vs Parallelism

- **Concurrency:** একাধিক task-এর progress overlapping হতে পারে।
- **Parallelism:** একাধিক task একই সময়ে execute হয়।

Concurrency মানেই parallel execution নয়।

### 18.7 Authentication vs Authorization

- **Authentication:** তুমি কে, তা যাচাই করা।
- **Authorization:** তুমি কী করতে পারবে, তা নির্ধারণ করা।

### 18.8 Mutable vs Immutable

- **Mutable:** Object-এর state পরিবর্তন করা যায়।
- **Immutable:** Object-এর state তৈরি হওয়ার পরে পরিবর্তন করা যায় না।

### 18.9 Library vs Framework

- **Library:** নিজের code থেকে library-এর functionality call করা হয়।
- **Framework:** Framework-এর নির্ধারিত structure ও lifecycle অনুসরণ করে application তৈরি করা হয়।

এটি একটি সাধারণ পার্থক্য; সব tool-এর ক্ষেত্রে boundary একরকম নয়।

### 18.10 Testing vs Debugging

- **Testing:** Program-এর behavior প্রত্যাশা অনুযায়ী হচ্ছে কি না যাচাই করা।
- **Debugging:** কোনো সমস্যা ঘটলে তার কারণ খুঁজে সমাধান করা।

---

## 19. How to Use This Glossary

এই glossary কার্যকরভাবে ব্যবহার করার জন্য:

1. নতুন কোনো term দেখলে তার অর্থ খুঁজে দেখো।
2. শুধু বাংলা meaning মুখস্থ না করে বাস্তব code example-এর সঙ্গে মিলিয়ে বোঝো।
3. Confusing terms-এর পার্থক্য আলাদাভাবে অনুশীলন করো।
4. নতুন topic শেখার সঙ্গে সঙ্গে সংশ্লিষ্ট terms revise করো।
5. কোনো term-এর বিস্তারিত জানতে সংশ্লিষ্ট chapter ও official documentation পড়ো।

এই glossary একটি introductory reference। Python-এর advanced topic শেখার সঙ্গে সঙ্গে আরও নতুন terminology শিখতে হবে।

---

## 20. Chapter 00 Completion Checklist

Chapter 00 — Project Guide সম্পন্ন হয়েছে কি না যাচাই করো।

- [ ] `README.md` — Project Guide overview
- [ ] `01_Project_Overview.md`
- [ ] `02_How_to_Use_This_Repository.md`
- [ ] `03_Python_Learning_Roadmap.md`
- [ ] `04_Prerequisites.md`
- [ ] `05_Learning_Methodology.md`
- [ ] `06_Documentation_Standards.md`
- [ ] `07_Code_Example_Conventions.md`
- [ ] `08_Practice_Guidelines.md`
- [ ] `09_Progress_Tracking.md`
- [ ] `10_Repository_Structure.md`
- [ ] `11_Tools_and_Resources.md`
- [ ] `12_Glossary_and_Technical_Terms.md`

সবগুলো file তৈরি ও review করা হলে Chapter 00 সম্পন্ন।

---

## Next Chapter

**Chapter 01 — Installation & Development Environment**

এই chapter-এ Python install করা, installation যাচাই করা, VS Code configure করা, terminal ব্যবহার, Python file execute করা এবং virtual environment তৈরি করার মতো practical topic ধাপে ধাপে শেখা হবে।