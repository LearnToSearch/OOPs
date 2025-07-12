# Introduction to Object-Oriented Programming (OOP) 🧱

#### ❓ **What is OOP?**   
Object-Oriented Programming (OOP) is a programming model based on the concept of "objects," which can contain data (attributes) and code (methods). In OOP, the focus is on modeling real-world entities as objects, which makes it easier to structure and manage large, complex programs. The key idea is to encapsulate data and behavior into these objects and allow them to interact with one another.  

- **Example:** 🔍
  In OOP, you might represent a **Car** 🚗 as a class, with attributes such as `color`, `model`, and `year`, and methods like `start()`, `stop()`, and `drive()`.  

---  

#### **Procedural vs. Object-Oriented Programming** 📢

- **Procedural Programming:** ✨ 
  - The program is divided into functions, and each function operates on data passed to it. 📝  
  - Focus is on procedures (functions) rather than data.  
  - Example: C, Pascal  

- **Object-Oriented Programming:** ✨
  - The program is organized around objects that combine both data and functions (methods). 🎨  
  - Focus is on creating reusable objects that represent real-world entities.  
  - Example: Python, Java, C++  

- **Key Differences:** 🛠️
  1. **Data Handling:**  
     - Procedural: Functions act on data separately.  
     - OOP: Data and functions are combined into objects.  
  2. **Modularity:**  
     - Procedural: Program is split into functions.  
     - OOP: Program is split into objects and classes.  
  3. **Reusability:**  
     - OOP encourages code reuse through inheritance and polymorphism, which makes it easier to extend programs.  

---  

#### **Four Pillars of OOP** 🚀  

1. **Encapsulation:** 🔒  
   - Encapsulation is the process of bundling data (attributes) and methods (functions) that operate on the data into a single unit, or class.  
   - It restricts direct access to some of the object’s components, which is known as **data hiding**.  
   - **Example:** 🔍
    You might hide the internal state of an object and only expose certain methods to interact with it.  
     ```python  
     class Car:  
         def __init__(self, model, year):  
             self.__model = model    # Private attribute  
             self.year = year        # Public attribute  
         
         def get_model(self):  
             return self.__model  
     ```  

2. **Abstraction:** 🎩  
   - Abstraction means hiding the complex reality while exposing only the necessary parts. It reduces complexity by allowing the user to interact with an object without needing to understand its internal workings.  
   - Abstraction focuses on **what** an object does rather than **how** it does it.  
   - **Example:** 🔍
    When driving a car 🚗, you don’t need to understand how the engine works, but you know how to start it using a key.  
     ```python  
     class Car:  
         def start(self):  
             print("Car is starting...")  
     ```  

3. **Inheritance:** 🧬  
   - Inheritance allows one class to inherit attributes and methods from another class. It promotes code reuse and logical structure by creating a "parent-child" relationship between classes.  
   - **Example:** 🔍 
    You can create a subclass `ElectricCar` that inherits from a parent class `Car`.  
     ```python  
     class Car:  
         def drive(self):  
             print("Driving...")  

     class ElectricCar(Car):  
         def charge(self):  
             print("Charging the car...")  
     ```  

4. **Polymorphism:** 🎭  
   - Polymorphism means "many forms." It allows objects of different classes to be treated as objects of a common superclass. Polymorphism enables the same method to behave differently based on the object calling it.  
   - **Example:** 🔍
    Different objects (like `Dog` 🐕 and `Cat` 🐈) might have the same method `speak()`, but each object implements it differently.  
     ```python  
     class Animal:  
         def speak(self):  
             pass  

     class Dog(Animal):  
         def speak(self):  
             print("Woof!")  

     class Cat(Animal):  
         def speak(self):  
             print("Meow!")  
     ```  

### 🏁 Conclusion 
As we all know that the basic fundamentals is the fist step to learn a new thing.These are some important topics that we will read in details in further lectures.So for now have an idea of these topics these are the basic fundamentals of OOP.  