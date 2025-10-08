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

a. Use Meaningful and Descriptive names
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
b. Use Comments where necessary
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
d. Follow established code-writing standards

**Types of Cases:**
- **camelCase** : myVariableName (e.g: Java, JavaScript)
- **PascalCase** : MyClassName (e.g: C#)
- **snake_case** : my_variable_name (e.g: Python)
- **dash-case** : my-element-class (e.g: html, css)

**Indentation:**
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
