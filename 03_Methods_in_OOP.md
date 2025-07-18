# **Methods in OOPs (Object-Oriented Programming) in Python** 🐍

In Object-Oriented Programming (OOP), **methods** are functions defined within a class that operate on its instances (objects). They provide behaviors to objects, allowing us to manipulate object attributes or perform specific actions.

Here’s a **detailed explanation of types of methods in Python OOP** along with examples for each type.  

---

### **1. Instance Methods** 📦
**Definition:**  
These are the most common type of methods. They operate on **instance variables** (object attributes) and require a reference to the object (via `self`).  

**Key Points:**  
- Accesses and modifies instance attributes.  
- Requires `self` as the first parameter to refer to the current instance.  

**Syntax:**  
```python
class ClassName:
    def instance_method(self, arg1, arg2): 
        # 'self' represents the instance of the class
        pass
```

**Example:** 🔍
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def introduce(self):  # Instance method
        print(f"Hi, I am {self.name} and I am {self.age} years old.")

# Creating an object
person1 = Person("Alice", 25)
person1.introduce()  # Output: Hi, I am Alice and I am 25 years old.
```

---

### **2. Class Methods** 🏫
**Definition:**  
Class methods operate on **class variables** (not instance variables) and affect all instances of the class. They are bound to the class rather than the object.  

**Key Points:**  
- They use `@classmethod` decorator.  
- Uses `cls` instead of `self` to refer to the class.  
- Can modify class-level attributes but cannot access instance attributes.  

**Syntax:**  
```python
class ClassName:
    @classmethod
    def class_method(cls, arg1, arg2): 
        # 'cls' refers to the class itself
        pass
```

**Example:** 🔍
```python
class Student:
    school_name = "Greenwood High"  # Class variable

    @classmethod
    def change_school(cls, new_name):  # Class method
        cls.school_name = new_name

# Accessing and modifying the class variable using the class method
print(Student.school_name)  # Output: Greenwood High
Student.change_school("Sunrise Public School")
print(Student.school_name)  # Output: Sunrise Public School
```

**Use Case:**  
When you need to modify or access class-level attributes.  

---

### **3. Static Methods** ⚙️
**Definition:**  
Static methods are general-purpose methods that **do not access or modify** class-level or instance-level attributes. They are independent of class and instance but logically belong to the class.  

**Key Points:**  
- Uses `@staticmethod` decorator.  
- They do not require `self` or `cls`.  
- Used for utility functions that relate to the class but don't operate on the instance or class.  

**Syntax:**  
```python
class ClassName:
    @staticmethod
    def static_method(arg1, arg2): 
        # No 'self' or 'cls' required
        pass
```

**Example:** 🔍
```python
class MathOperations:
    @staticmethod
    def add_numbers(a, b):  # Static method
        return a + b

# Call static method directly using the class name
result = MathOperations.add_numbers(10, 20)
print(f"Sum: {result}")  # Output: Sum: 30
```

**Use Case:**  
When you need a utility method that logically belongs to the class but doesn't interact with class or instance variables.  

---

### **4. Special Methods (Magic/Dunder Methods)** ✨
**Definition:**  
Special methods (also called "Dunder" methods, short for "Double UNDERscore") have **double underscores** (`__method__`) and define special behavior for objects, such as how they are represented, compared, or converted to other types.  

**Key Points:**  
- They are also known as **magic methods**.  
- Used for operator overloading and defining special object behavior (like how objects are printed).  
- Common special methods include `__init__`, `__str__`, `__repr__`, `__len__`, `__add__`, etc.  

**Example 1: `__init__` (Constructor)**
```python
class Person:
    def __init__(self, name, age):  # This method runs automatically when an object is created
        self.name = name
        self.age = age

person1 = Person("Alice", 25)  # Calls __init__ method
print(person1.name)  # Output: Alice
```

**Example 2: `__str__` (String Representation)**
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):  # This controls how an object is displayed using print()
        return f"{self.name} is {self.age} years old"

person1 = Person("Alice", 25)
print(person1)  # Output: Alice is 25 years old
```

**Example 3: `__add__` (Operator Overloading)**
```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):  # Operator overloading
        return Point(self.x + other.x, self.y + other.y)

    def __str__(self):
        return f"({self.x}, {self.y})"

p1 = Point(2, 3)
p2 = Point(4, 5)
p3 = p1 + p2  # Uses __add__ method
print(p3)  # Output: (6, 8)
```

**Use Case:**  
When you want to define how objects interact with built-in operators (`+`, `-`, `*`, etc.) or control object behavior for `print()`, comparison, and so on.  

---

### **Summary of Method Types** 📝

| **Method Type**     | **Requires Self?** | **Requires Cls?** | **Access Instance Variables?** | **Access Class Variables?** | **Example Use Case**                |
|-------------------|-------------------|-------------------|---------------------------------|-----------------------------|-------------------------------------|
| **Instance Method** | ✅ Yes            | ❌ No             | ✅ Yes                        | ✅ Yes                      | Access and modify instance variables|
| **Class Method**    | ❌ No             | ✅ Yes            | ❌ No                         | ✅ Yes                      | Access and modify class variables    |
| **Static Method**   | ❌ No             | ❌ No             | ❌ No                         | ❌ No                       | General-purpose utility methods     |
| **Special Method**  | ✅ Yes            | ❌ No             | ✅ Yes                        | ✅ Yes                      | Define custom behavior for objects  |

---

### **Example Combining All Methods** 🧪
```python
class Employee:
    company_name = "TechCorp"  # Class variable

    def __init__(self, name, salary):  # Instance method
        self.name = name
        self.salary = salary

    def display_employee_info(self):  # Instance method
        print(f"Name: {self.name}, Salary: ${self.salary}, Company: {Employee.company_name}")

    @classmethod
    def change_company_name(cls, new_name):  # Class method
        cls.company_name = new_name

    @staticmethod
    def is_high_salary(salary):  # Static method
        return salary > 50000

    def __str__(self):  # Special method (for print)
        return f"{self.name} works at {Employee.company_name} with a salary of ${self.salary}"

# Creating an instance of Employee
emp1 = Employee("Alice", 70000)
emp1.display_employee_info()  # Instance method

# Call class method to change the company name
Employee.change_company_name("NextGen Tech")
emp1.display_employee_info()

# Use static method
print(Employee.is_high_salary(70000))  # True

# Use special method
print(emp1)  # Output: Alice works at NextGen Tech with a salary of $70000
```

---

### **Conclusion** ✨
1. **Instance Methods** modify and access object-specific data.  
2. **Class Methods** modify and access class-level data shared across all instances.  
3. **Static Methods** act like normal functions but are logically part of the class.  
4. **Special Methods** provide custom behavior for operators, print statements, and more.  

By using this methods you can get to know the use of certain keywords in OOPs which are very important to know.