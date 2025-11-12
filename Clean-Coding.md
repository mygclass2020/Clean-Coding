# Clean-Coding : A basic guide to clean coding
---
### Table of Content
> - Foundations of Clean Coding
> - SOLID Principles
> - Refactoring Existing Code
> - Unit Testing
---
## What is Clean Coding?
When writing code, you shouldn't just focus on making it work. You should also aim to make it **readable**, **understandable**, and **maintainable** for future readers.

"Anybody can write code that a computer can understand. Good programmers write code that humans can understand."

\- Martin Fowler

## Importance of Clean Coding
- **Readability** and **Maintainance**
- **Team Collaboration**
- **Debugging** and Issue resolution
- **Improved quality** and **Reliability**
---
## 1. Foundations of Clean Coding
**A. Naming Convention -**

I. Use Meaningful and Descriptive names
  ```
  # Avoid naming like this
  def function1(input):
      a = 0.1
      b = input * a
      return input - b

  # Use meaningful names
  def calculate_discount(price):
      discount_percent = 0.1
      discount = price * discount_percent
      return price - discount
  ```
II. Use Comments where necessary
  ```
  # Avoid unnecessary comments

  # calculate the discounted price
  # takes price as input
  def calculate_discount(price):
      # discount percent (10 percent here)
      discount_percent = 0.1
      # calculating discount
      discount = price * discount_percent
      # returning the discounted price
      return price - discount

  # write useful comments

  # Calculting discounted price
  def calculate_discount(price):
      discount_percent = 0.1
      discount = price * discount_percent
      return price - discount
  ```
III. Follow established code-writing standards

**a. Types of Cases:**
- **camelCase** : myVariableName (e.g: Java, JavaScript)
- **PascalCase** : MyClassName (e.g: C#)
- **snake_case** : my_variable_name (e.g: Python)
- **dash-case** : my-element-class (e.g: html, css)

**b. Indentation:**
```
# Without indentation

def get_discount_rate(product_price):
if product_price > 100:
return 0.1
elif product_price > 50:
return 0.05
else:
return 0

# With indentation

def get_discount_rate(product_price):
  if product_price > 100:
    return 0.1
  elif product_price > 50:
    return 0.05
  else:
    return 0
```
**B. DRY (Don't Repeat Yourself) Principle -**
- Avoid writing the same code more than once
- Reuse your code using functions, classes, modules
- Makes code more efficient, consistent, maintainable
- Reduces risk of errors and bugs

```
# Repeating code

def calculate_book_price(quantity, price):
  return quantity * price
def calculate_laptop_price(quantity, price):
  return quantity * price

# More efficient

def calculate_product_price(product_quantity, product_price):
  return product_quantity * product_price
```
---
## **2. SOLID Principles**
- **Robert C. Martin** compiled these principles in the 1990s
- These principles enable us to manage several software design problems
- From **tightly coupled code, no encapsulation** to the desired results of **loosely coupled, encapsulated real business needs**

  **I. S - Single Responsibility Principle (SRP):**

  - SRP says, "Every software module should have only one reason to change."
  - Every class in your code should have only **one job** and be related to a **single purpose**
  - Does not mean that your classes should only contain one method or property
  - SRP gives us a good way of identifying classes at the design phase of an application
 
  **II. O - Open / Closed Principle (OCP):**

  - OCP says, "A software module/class is open for extension and closed for modification."
  - **"Open for extension"** means we must design our module/class so that the new functionality can be added only when new requirements are generated.
  - **"Closed for modification"** means we have already developed a class, and it has gone through unit testing. We should then not alter it until we find bugs.
  - Since a class should be open for extensions; we can use inheritance
 
  **III. L - Liskov Substitution Principle (LSP):**

  - Derived class should not affect the behavior of the parent class
  - A derived class must be substitutable for its base class
  - It is an extension of the Open Closed Principle

  **IV. I - Interface Segregation Principle (ISP):**

  - Instead of using one large interface, many small interfaces are preferred based on groups of methods, each serving one submodule.
  - Clients should not be forced to depend upon interfaces they don't use
  - Each interface should have a specific purpose/responsibility
  - The larger the interface, the more likely it includes methods not all implementers can use.

  **V. D - Dependency Inversion Principle (DIP):**

  - High-level module/classes should not depend on Low-level modules/classes
  - A high-level module/class that depends on low-level modules/classes is said to be tightly coupled
  - Both of them need to be dependent on abstractions instead of each other
 
> Also check : https://www.c-sharpcorner.com/UploadFile/damubetha/solid-principles-in-C-Sharp/
---

## 3. Refactoring Existing Code

- **Code Smells** :-
  - Signs in source code that suggest a deeper problem, even if the code is still functional
  - Those patterns which either duplicates, or complicates, or might make code dependent on other code
  - Signify the weakness in design and might increase the risk of bugs and program failure in the future
  - Does not alter the external behavior of the code, only improves its internal structure
  - Makes code much cleaner, clear, and simpler to understand
 
**Broadly divided into 2 major types:**

**1. Code smell within classes :**

- Comments:
    - Comments should make the code self-documenting and intension-revealing
- Long Method:
    - Functions and methods should be small and easy-to-read
    - Any code more than 25 lines should be questioned
- Long Parameter List
    - Use maximum of 3-4 parameters in a function
    - If values of parameters are output of some other function, pass it as a function instead of parameter
- Large Classes
    - Class with many lines of code is considered a code smell
    - Refactoring techniques like extract class, extract subclass, extract interface etc. should be applied
- Duplicate Code
    - When code is repeated 2 or more times, merge it into single function or method
- Dead Code
    - Code that is not being used is dead code
    - Functions with no calls or conditions should be deleted

**2. Code smell between classes :**

- Data Classes
    - Classes with only data and no methods doesn't have any functionality
    - Use global or local variables to refactor this code smell
- Data Clumps
    - Different parts of the code containing identical groups of variables are called clumps
    - Create a new class to encapsulate the related data items 
- Alternative Classes with Different Interfaces
    - Two similar classes can be modified to share a common interface
- Refused Bequest
    - Subclass inherits methods and functionality from a parent class but doesn't use them, either by overriding them with empty implementations or by not calling them at all
    - Indicates a problem with the inheritence heirarchy
- Lazy Class
    - Class with little or no use should be deleted as it can cost time and money both
- Shotgun Surgery
    - Single change leading to cascading changes in several classes should be avoided
    - Code is hard to change, easy to break and has high chances of bugs as changes are needed in multiple places

**How to prevent Code Smells?**
- Adhere to solid principles
- Give your code self-documenting names
- Maintain short methods
- Refactor frequently

> Also check : https://www.geeksforgeeks.org/blogs/code-smell-a-general-introduction-and-its-type/

---
## 4. Unit Testing

- A unit test is a test that exercises individual software components or methods, also known as a "unit of work."

**Benefits of Unit Testing:**
- Less time performing functional tests
- Protection against regression
- Executable documentation
- Less coupled code

  **Characters of Good Unit Tests:**
  - Fast
  - Isolated
  - Repeatable
  - Self-checking
  - Timely
 
> Also check : https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-best-practices
