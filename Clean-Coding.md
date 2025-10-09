# Clean-Coding : A basic guide to clean coding
---
### Table of Content
> - Foundations of Clean Coding
> - SOLID Principles
> - Refactoring Basics
> - Design patterns for MVC
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

  **IV. I - Interface Segregation Principle (ISP):**

  **V. D - Dependency Inversion Principle (DIP):**
