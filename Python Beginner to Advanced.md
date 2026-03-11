# Python History
Python was created by Guido van Rossum in the late 1980s as a hobby project and was first released in 1991. It was designed to emphasize code readability and simplicity, serving as a successor to the ABC programming language.

## Key Milestones in Python History 

-  **Genesis (1989):** Guido van Rossum began implementation as a "hobby" project at the Centrum Wiskunde & Informatica (CWI) in the Netherlands during the Christmas holidays. 
-  Initial Public Release (1991): Python version 0.9.0 was published to the  Usenet group in February 1991. This version already included core features like classes with inheritance, exception handling, functions, and a module system. 
-  **Python 1.0 (1994):** The official  Python 1.0 release in January introduced functional programming tools such as , , , and , along with support for complex numbers. 
-  **Python 2.0 (2000):** Released in October, this major version added new features including list comprehensions, a cycle-detecting garbage collector, and enhanced Unicode support. The Python Software Foundation (PSF) was formed shortly after, in 2001, to own Python-related intellectual property and manage the language's development. 
-  **Python 3.0 (2008):** Known as "Python 3000" or "Py3k", this was a major, backward-incompatible revision designed to fix fundamental design flaws and remove redundant constructs. Key changes included the  function (instead of a statement) and a change in integer division behavior. A tool called  was provided to help automate code translation. 
-  **End of Python 2 Support (2020):** After a long transition period, support for the final Python 2 release,  Python 2.7, officially ended on January 1, 2020, shifting the community's focus entirely to Python 3. 
-  **Modern Python:** Development continues with a focus on performance improvements, with recent versions like 3.11 showing significant speed enhancements. As of early 2026, Python 3.14.3 is the latest stable release, with 3.15 in the alpha development phase. 

## Naming and Philosophy 

-  **Name Origin:** The name "Python" was chosen by Van Rossum because he was a big fan of the British comedy series Monty Python's Flying Circus. 
-  **Design Philosophy:** Python emphasizes code readability and simplicity, as summarized in the "Zen of Python" (PEP 20), which states "There should be one—and preferably only one—obvious way to do it".

Today, Python is one of the most popular and widely used programming languages globally, applied in data science, artificial intelligence, web development, and automation. 


# Class in Python
A class in Python is a **blueprint** or **template** for creating *objects*, which are *instances* of the class that bundle together related **data** (**attributes**) and **behaviors** (**methods**). This approach, known as **object-oriented programming (OOP)**, helps organize code, making it *modular*, *reusable*, and *easier to manage*.  
## Defining a Class 
You define a class using the `class` keyword, followed by the class name (conventionally in ) and a *colon*. 

## Key Concepts 
- **Class:**  A blueprint that defines the attributes and methods that all objects of a certain type will have. Classes are created using the  keyword. 

-  **Objects (Instances):** Objects are concrete instances created from a class, each with its own unique data. 
-   **Method:** This is a special method, also known as the constructor, that runs automatically when a new object is created. Its purpose is to set the initial attributes for the new instance. 
-   **Parameter:** The first parameter of any instance method (by convention named ) refers to the current object instance itself. This allows you to access and modify the object's unique attributes and methods within the class definition. 
-  **Attributes:** Variables within a class that store data.
	- **Instance Attributes:** Unique to each object and typically defined within the __init__ method using the self keyword.
	- **Class Attributes:** Shared by all instances of a class and defined directly within the class body, outside any method.
-  **Methods:** These are functions defined within a class that describe the behaviors or actions an object can perform. 
-  **Inheritance:** Classes can inherit attributes and methods from other classes (parent/base classes), promoting code reuse and creating a logical hierarchy. 
- **self reference:** A reference to the current instance of the class, allowing methods to access and modify that specific object's attributes. 
 

## Defining and Using a Class 

Here is a basic example of a Python class: 
```python
class Dog:
    """A simple example class for a dog.""" # Docstring
    species = "canine" # Class attribute

    def __init__(self, name, age):
        """Constructor method to initialize instance attributes."""
        self.name = name  # Instance attribute
        self.age = age    # Instance attribute

    def bark(self):
        """An instance method."""
        return f"{self.name} says woof!"

# Create instances (objects) of the Dog class
dog1 = Dog("Buddy", 3)
dog2 = Dog("Lucy", 5)

# Access attributes and call methods
print(f"{dog1.name} is {dog1.age} years old and is a {Dog.species}.")
print(dog2.bark())

```

## Core OOP Principles 
Classes are the foundation for Python's object-oriented programming features: 

-  **Encapsulation:** The bundling of data (attributes) and methods into a single unit (the class), which helps in organizing code and controlling access to data. 
-  **Inheritance:** Allows a new class (child/subclass) to inherit attributes and methods from an existing class (parent/superclass), promoting code reuse and creating a hierarchical relationship. The  function is often used to call methods of the parent class. 
-  **Polymorphism:** The ability for different classes to be treated as instances of a common superclass, allowing methods with the same name to work differently depending on the object they are acting upon. 
-  **Abstraction:** Hiding the complex implementation details and showing only the necessary features of an object. 

## All about Object in Python
In Python, an object is a fundamental concept representing a self-contained entity that bundles data (attributes) and behavior (methods). Almost everything in Python, from simple integers and strings to functions and classes, is an object. Objects are instances of a class, which acts as a blueprint.  

In Python, an object is a fundamental unit in Object-Oriented Programming (OOP) that represents a real-world entity and is an instance of a class. Almost everything in Python, including numbers, strings, and even functions, is an object. [1, 2]  
 

## The Four Pillars of OOP in Python 
Object-Oriented Programming also relies on four core principles, which Python supports: 

• Encapsulation: The bundling of data and methods that operate on that data into a single unit (a class). This helps in data hiding and maintaining data integrity by restricting direct access to some components. 
• Inheritance: A mechanism allowing a new class (child/derived class) to inherit attributes and methods from an existing class (parent/base class). This promotes code reuse and helps in creating a hierarchical relationship between classes. 
• Polymorphism: The ability of different objects to respond to the same method call in their own specific way. For example, a method could produce "Bark" for a object and "Meow" for a object. 
• Abstraction: Hiding complex implementation details and exposing only the necessary features or interface to the user. Abstract base classes (ABCs) and interfaces are used to achieve this in Python. 

Creating and Using Objects (Example) 
```python
# A simple example of a class and objects in Python
class Car:
    """A blueprint for creating car objects."""  # Class attribute shared by all instances
    wheels = 4

    def __init__(self, model, color):
        """Initializes the instance attributes."""
        self.model = model  # Instance attribute unique to each object
        self.color = color

    def display_info(self):
        """An instance method to display car info."""
        print(f"This is a {self.color} {self.model} with {self.wheels} wheels.")

# Create objects (instances) of the Car class
car1 = Car("Audi R8", "Red")
car2 = Car("BMW I8", "Blue")

# Access attributes and call methods using the objects
car1.display_info()
car2.display_info()

# Modify an object's attribute
car1.color = "Black"
car1.display_info()

```
Output of the above code: 
```console
This is a Red Audi R8 with 4 wheels.
This is a Blue BMW I8 with 4 wheels.
This is a Black Audi R8 with 4 wheels.
```

## Core Characteristics of an Object 
Every object in Python has three key characteristics: 

- **Identity:** A unique identifier, often the object's memory address, which allows it to interact with other objects. This can be checked using the built-in function. 
- **State:** The data or properties the object holds, represented by its attributes (variables). 
- **Behavior:** The actions an object can perform, defined by its methods (functions within a class). 

**Classes:** The Object's Blueprint  
A class serves as a blueprint or template for creating objects. It defines the structure and the potential behaviors that all instances of that class will share. 
```python
class Dog:
    # Class attribute (shared by all instances)
    species = "canine"

    def __init__(self, name, age):
        # Instance attributes (unique to each object)
        self.name = name
        self.age = age

    # Instance method (defines behavior)
    def description(self):
        return f"{self.name} is {self.age} years old"

```
## Creating and Using Objects 
The process of creating an object from a class is called instantiation. 

1. **Instantiation:** An object is created by calling the class name like a function. 
2. **Constructor:** This special method is automatically called when a new object is created. It initializes the object's instance attributes with specific values, using the parameter to refer to the new instance. 
3. **Accessing Members:** You use the dot () operator to access an object's attributes and methods. 
```python
# Create an object (instance) of the Dog class
dog1 = Dog("Buddy", 3)

# Access attributes
print(f"{dog1.name} species: {dog1.species}") # Output: Buddy species: canine

# Call a method
print(dog1.description()) # Output: Buddy is 3 years old

# Create another independent object
dog2 = Dog("Miles", 4)
print(dog2.description()) # Output: Miles is 4 years old

```
# self in Python

**self** is a convention-based parameter used in instance methods to refer to the **current instance (object)** of the class. It is not a reserved keyword but is universally used by convention for code readability and consistency among Python programmers. 

Key Concepts 

- **Instance Reference:** When you call an instance method, Python automatically passes the specific object (instance) on which the method was called as the first argument. The `self` parameter receives this object. 
- **Accessing Attributes and Methods:** `self` allows you to access and modify the attributes (data) and call other methods associated with that specific instance. Without it, a method wouldn't know which object's data to use, especially when multiple objects of the same class exist. 
- **Explicitness:** Python emphasizes "explicit is better than implicit". Requiring `self` as an explicit parameter in method definitions makes it clear that the method is operating on an instance of the class, avoiding confusion between local variables and instance variables. 
-  **__init__ Method:** The `__init__` method (the constructor) always takes as its first parameter. This is where instance attributes are typically initialized for a new object. 

Example 
```python
class Dog:
    # The __init__ method initializes the instance attributes
    def __init__(self, name, age):
        self.name = name  # 'self.name' refers to the instance's name attribute
        self.age = age    # 'self.age' refers to the instance's age attribute

    # The speak method uses 'self' to access the instance's data
    def speak(self):
        print(f"{self.name} says Woof! I am {self.age} years old.")

# Create instances of the Dog class
dog1 = Dog("Buddy", 3)
dog2 = Dog("Max", 5)

# Call methods on the instances
dog1.speak() # Output: Buddy says Woof! I am 3 years old.
dog2.speak() # Output: Max says Woof! I am 5 years old.

```
In this example: 

- When `dog1 = Dog("Buddy", 3)` is called, Python automatically passes the `dog1` object as `self ` to the `__init__ ` method. 
- When `dog1.speak()` is called, Python passes the `dog1` object as `self` to the `speak()` method. This allows the method to know which dog's name to print. 

# Constructor in Python

A constructor is a special method used to initialize a new object's attributes when an instance of a class is created. This is primarily handled by the `__init__` method, which is automatically called after the object has been created in memory. 

## Key Concepts
**__init__:** The instance initializer method. It is the most common method used as a constructor in Python. It defines the initial state of the object by assigning values to instance variables using the self parameter, which refers to the newly created object.
**__new__:** This is the actual method responsible for creating and returning a new instance of the class and allocating memory for it. It is a static method and runs before `__init__`. For most standard use cases, you don't need to override `__new__`; Python handles it automatically.
**Automatic Invocation:** The constructor is called automatically every time an object is instantiated from a class, ensuring the object starts in a consistent, valid state.
**No Overloading:** Unlike languages like Java or C++, Python does not support multiple `__init__` methods directly. If you define more than one, only the last one will be used. 

## Types of Constructors
Constructors are generally categorized by whether they accept parameters: 
- **Default Constructor:** A constructor that accepts no parameters other than self. It initializes objects with default values.
```python
class Robot:
    def __init__(self):
        self.name = "Unnamed"
        self.color = "Grey"
```
- **Parameterized Constructor:** A constructor that accepts additional arguments to initialize object attributes with specific, unique values provided during object creation.
```python
class Robot:
    def __init__(self, name, color):
        self.name = name
        self.color = color

# Create an object with specific values
robot_instance = Robot("Robbie", "red")
```

## Simulating Multiple Constructors
To achieve the functionality of multiple constructors, professional Python developers often use default arguments or class methods with the `@classmethod` decorator:

```python
class Robot:
    def __init__(self, name, color='grey'):
        self.name = name
        self.color = color

    @classmethod
    def from_json(cls, json_data):
        """Alternative constructor to create a Robot from JSON data."""
        name = json_data.get('name', 'Unnamed')
        color = json_data.get('color', 'grey')
        return cls(name, color) # Calls the __init__ method

# Using the primary constructor
robot1 = Robot("Robbie", "red")

# Using the alternative class method constructor
json_data = {'name': 'Bobby', 'color': 'blue'}
robot2 = Robot.from_json(json_data)
```

Using `@classmethod` provides a clean, "Pythonic" way to offer multiple, clearly named methods for creating objects in different ways.

```python
class Dog:
    def __init__(self, name):
        # This print statement inside the constructor will only run once per object
        print(f"A new Dog object named '{name}' is being initialized.")
        self.name = name
    
    def bark(self):
        print(f"{self.name} says Woof!")

# --- Demonstration ---

print("Creating the first dog object:")
# The constructor is called here, and the message prints once
dog1 = Dog("Buddy")
dog1.bark()

print("\nCreating the second dog object:")
# The constructor is called again for the new object, and the message prints once more
dog2 = Dog("Max")
dog2.bark()

print("\nCalling methods on existing objects:")
# Calling other methods on existing objects does not call the constructor again
dog1.bark()
dog2.bark()


```

## Explanation
- `class Dog:`: Defines a class named Dog.
- `def __init__(self, name):`: This is the constructor method. The self parameter refers to the specific instance being created, and name is an argument passed during creation.
- `dog1 = Dog("Buddy"):` This line instantiates the first Dog object. The Python interpreter automatically calls the __init__ method, and the message "A new Dog object named 'Buddy' is being initialized." is printed exactly once.
- `dog2 = Dog("Max"):` This line instantiates a second, separate Dog object. The __init__ method is called again, printing its specific message exactly once for this new instance.
- `dog1.bark():` Calling standard methods like bark() on the already existing objects does not trigger the constructor again, confirming that the constructor runs strictly during the initial object creation phase.


# method vs constructor
The key distinction is that a constructor (`__init__`) is a special method used specifically for initializing a new object, while a general method performs operations on an existing object. 

| Feature |	Constructor (__init__)|	Method|
|--------|------------------------|------|
| Purpose |	Initializes the newly created object's attributes.| Defines the behaviors and operations of an existing object.|
| Invocation	| Invoked automatically when an object is instantiated (using the class name, e.g., my_class_instance = MyClass()).| Invoked explicitly by the programmer using the object's name (e.g., my_class_instance.do_work()).|
| Naming |	Has a fixed, special name: __init__.| Can have any meaningful name (e.g., calculate_salary, display_details).|
| Return Value	| Does not return a value (implicitly returns None). | May or may not return a value (e.g., a calculation result, a status).|
| Object State	| Operates on a new object instance that is still in the process of being created.	| Operates on an object that has already been fully created and initialized.|

In short, a constructor sets up the initial state of an object so it is ready for use, while methods provide the functionality for that object throughout its lifecycle. 

# Types of Variables 
In Python object-oriented programming (OOP), variables are categorized based on their scope and ownership into three main types: **instance variables**, **class variables (also known as static variables)**, and **local variables**. 

## 1. Instance Variables (Object-Level Variables) 
Instance variables are unique to each instance (object) of a class. They are used to store data that varies from one object to another. 

**Declaration:** They are typically defined inside the class's constructor method, __init__() method using the `self` keyword (e.g., self.name = name). They can also be created in other `instance methods` or even `outside the class using an object` reference.
**Scope:** Each object has its own separate copy of the instance variables. Changes made to an instance variable through one object do not affect other objects.

**Example:** In a Student class, name and roll_number would be instance variables, as each student has a unique name and roll number. 

## 2. Class Variables (Static Variables)
Class variables are **shared** by all instances of a class. They belong to the class itself rather than any specific object and are used for data that is common to all instances. 

**Declaration:** They are defined directly inside the class body, outside of any method or constructor.
**Scope:** Only one copy of the class variable exists in memory, and all objects access this same copy. Changes made to a class variable using the class name will reflect across all instances.

**Example:** In the same Student class, the school_name would be a class variable, as all students in the school share the same school name. The official Python documentation provides an example using kind as a class variable for a Dog class. 

## 3. Local Variables (Method-Level Variables)
Local variables are declared inside a specific **method or function.** 

**Scope:** They are accessible only within the method where they are defined. They are created when the method is called and destroyed when the method finishes execution.

**Example:** A variable wamt (withdrawal amount) declared inside a withdraw method of a bank Customer class would be a local variable, as it's only relevant during that specific transaction. 

Additionally, there are global variables declared outside of a class or function, accessible throughout the entire program.

# global Variable in Python
A global variable in Python is a variable defined outside of any function or class, making it accessible throughout the entire program. 

## Key Characteristics
- **Scope:** Global variables exist in the global (module-level) scope and can be read from anywhere in the code, including inside functions.
- **Lifetime:** They are created when the program starts and are destroyed only when the program terminates.
- **Modification:** To modify a global variable from within a function, you must explicitly declare it using the **global** keyword. Otherwise, Python will create a local variable with the same name that "shadows" the global one within that specific function's scope.
- **Mutability:** For mutable objects (like lists or dictionaries), you can modify their contents inside a function without the **global** keyword because you are not reassigning the variable name itself, but rather using the existing object reference. 

Examples
1. Accessing a Global Variable:
```python
x = "awesome" # Global variable

def myfunc():
    print("Python is " + x) # Accessing the global variable

myfunc()
```
```console
# Output: Python is awesome
```
2. Modifying a Global Variable Inside a Function:
```python
x = "awesome" # Global variable

def myfunc():
    global x # Declare the intention to modify the global variable
    x = "fantastic" # Modify the global variable's value

myfunc()
print("Python is " + x)
```
```console
# Output: Python is fantastic
```
## Best Practices
While global variables are a fundamental feature, overuse can make code difficult to track, debug, and maintain. 
- **Minimize Use:** Prefer passing data into functions via arguments and retrieving results via return statements.
- **Use for Constants:** Global variables work well for constants or configuration settings that don't change during runtime (by convention, use UPPERCASE names for constants).
- **Encapsulate State:** For complex state management, consider using classes and objects to encapsulate data and related functions (methods).
- **Module-level data:** For sharing data across modules, define the variable in one module (e.g., config.py) and import that module everywhere you need to access the data, referring to it with the module name (e.g., config.x).

# Rules for Declaring, Accessing, Modifying and Deleting Instance Variables in OOP Python

Rules for managing instance variables rely on conventions for visibility, as all members are public by default. The key mechanisms involve the **self** keyword, the **dot (.)** operator, and specific **built-in functions**. 

## Creating Instance Variables
- **Definition:** Instance variables are unique to each object (instance) of a class.
- **Location:** They are typically defined within the `__init__()` method (the constructor) using the `self` keyword as the first parameter. This ensures a separate copy is created for each new instance.
- **Syntax:** Inside the method, you use self.variable_name = value to create and initialize the variable. 

```python
class Dog:
    def __init__(self, name, age):
        self.name = name # Creates the 'name' instance variable
        self.age = age   # Creates the 'age' instance variable
```

- **Dynamic Creation:** You can also add new instance variables to an object dynamically after its creation using the object reference and the assignment operator (e.g., my_object.new_var = value). This variable will only exist for that specific object. 

## Accessing Instance Variables
- **Within the Class:** Use the self keyword followed by the dot (.) operator and the variable name (e.g., self.name).
- **Outside the Class:** Use the object reference (instance name) followed by the dot (.) operator and the variable name (e.g., dog1.name).
- **Dynamically:** Use the built-in getattr(object, name[, default]) function to access an attribute by its name as a string, with an optional default value to prevent AttributeError if the attribute doesn't exist. 

## Modifying Instance Variables
- **Within or Outside the Class:** Instance variables are public by default, so you can modify their values using the assignment operator (=) via the object reference (e.g., dog1.age = 4). The change only affects that specific object's copy of the variable.
- **Dynamically:** The built-in setattr(object, name, value) function can be used to set the value of an attribute dynamically using strings. 

## Deleting Instance Variables
- **Using del statement:** The del statement can be used to delete an instance variable from a specific object (e.g., del dog1.age). The variable will then no longer be accessible for that object.
- **Using delattr() function:** The built-in delattr(object, name) function provides a dynamic way to delete an attribute using a string for the name. 

## Naming Conventions and Access Control
Python does not have strict "public," "protected," or "private" keywords but uses naming conventions to suggest intended usage: 

- **Public:** Standard names (no leading underscores). Accessible anywhere.
- **Protected:** Prefix the name with a single underscore (e.g., self._age). This is a convention to indicate it's for internal use within the class and its subclasses, but it can still be accessed from outside.
- **Private:** Prefix the name with double underscores (e.g., self.__age). Python performs "name mangling" on these, making them harder to access directly from outside the class (e.g., they become _ClassName__age), which helps prevent name clashes in subclasses.

# Static Variables in OOPS Python

In Python Object-Oriented Programming (OOP), **Static Variables** (also known as Class-Level Variables) are variables whose value is shared by all instances of a class. Unlike instance variables, which are unique to each object, only one copy of a static variable exists for the entire class.

---

### 1. Creating Static Variables

Static variables are typically defined directly inside the class body but outside any methods. However, Python is flexible and allows them to be created in several locations.

**Locations for Creation:**

* **Inside Class Body:** Most common approach.
* **Inside Constructor/Method:** By using the syntax `ClassName.variable_name`.
* **Outside the Class:** Using the class name directly.

```python
class Test:
    a = 10  # Created in class body

    def __init__(self):
        Test.b = 20  # Created in constructor

    def m1(self):
        Test.c = 30  # Created in instance method

    @classmethod
    def m2(cls):
        cls.d = 40   # Created in class method using 'cls'

```

---

### 2. Accessing Static Variables

Static variables can be accessed using either the **Class Name** or an **Object Reference**. Using the Class Name is the recommended practice to maintain clarity.

| Location | Access Syntax |
| --- | --- |
| **Inside Constructor** | `self.var_name` or `Test.var_name` |
| **Inside Instance Method** | `self.var_name` or `Test.var_name` |
| **Inside Class Method** | `cls.var_name` or `Test.var_name` |
| **Inside Static Method** | `Test.var_name` |
| **Outside Class** | `object_ref.var_name` or `Test.var_name` |

---

### 3. Modifying Static Variables

There is a critical rule regarding modification: **You must modify static variables using the Class Name or `cls` variable.**

**The "Shadowing" Trap:**
If you try to modify a static variable using `self` or an object reference, Python will not update the static variable. Instead, it will create a **new instance variable** for that specific object, "shadowing" the static one.

```python
class Test:
    x = 10

t1 = Test()
t1.x = 888  # Error: This creates an instance variable 'x' for t1 only.
print(Test.x) # Output: 10 (Static variable remains unchanged)

Test.x = 999 # Success: This modifies the actual static variable.

```

---

### 4. Deleting Static Variables

To delete a static variable, you use the `del` keyword paired with the Class Name.

**Rules for Deletion:**

1. **Syntax:** `del ClassName.variable_name` or `del cls.variable_name` (inside class methods).
2. **Restriction:** You **cannot** delete a static variable using an object reference or `self`. Attempting to do so will result in an `AttributeError`.

```python
class Test:
    a = 10
    b = 20

# Valid Deletion
del Test.a 

# Invalid Deletion
t1 = Test()
# del t1.b  --> Raises AttributeError

```

---

### Summary Table: Static Variable Operations

| Operation | Recommended Method | Using Object Ref (`self`) |
| --- | --- | --- |
| **Create** | Inside class body | Not recommended (creates instance var) |
| **Access** | `ClassName.var` | Works (reads the shared value) |
| **Modify** | `ClassName.var = val` | **Fails** (creates new instance var) |
| **Delete** | `del ClassName.var` | **Fails** (raises AttributeError) |

---

# Static Variable vs Instance Variable

Understanding the distinction between **Instance Variables** and **Static (Class) Variables** is crucial for efficient memory management and correct program logic.

---

### Comparison at a Glance

| Feature | Instance Variable | Static (Class) Variable |
| --- | --- | --- |
| **Scope** | Object Level | Class Level |
| **Copies** | A separate copy for every object | Only one copy shared by all objects |
| **Value** | Varies from object to object | Generally remains same for all objects |
| **Memory** | Allocated when object is created | Allocated when class is loaded |
| **Storage** | Stored in `object.__dict__` | Stored in `ClassName.__dict__` |

---

### 1. Instance Variables (Object Level)

If the value of a variable changes from one object to another, it should be declared as an instance variable.

* **Declaration:** Usually inside the constructor (`__init__`) using the `self` keyword.
* **Access:** Using `self` inside the class or the `object_reference` outside the class.
* **Example:** For a `Student` class, `name` and `rollno` are instance variables because every student has unique details.

```python
class Student:
    def __init__(self, name, rollno):
        self.name = name   # Instance Variable
        self.rollno = rollno # Instance Variable

s1 = Student("Alice", 101)
s2 = Student("Bob", 102)
# Changing s1 does not affect s2
s1.name = "Alex" 

```

---

### 2. Static Variables (Class Level)

If the value of a variable is common to all objects, it is more memory-efficient to declare it as a static variable.

* **Declaration:** Inside the class directly, but outside any methods.
* **Access:** Recommended via the **Class Name**.
* **Example:** In a `Student` class, `college_name` would be a static variable since all students belong to the same institution.

```python
class Student:
    college_name = "AIIT"  # Static Variable

    def __init__(self, name):
        self.name = name

s1 = Student("Alice")
s2 = Student("Bob")
# Accessing via class name
print(Student.college_name) # Output: AIIT

```

---

### Key Behavioral Differences

#### The Modification Rule

This is the most common area for bugs.

* **Static Variables:** If you modify a static variable using the **Class Name**, the change is reflected in all existing and future objects.
* **Shadowing:** If you try to modify a static variable using `self` or an object reference (e.g., `s1.college_name = "New College"`), Python creates a **new instance variable** for that specific object. It does **not** change the static variable for others.

#### Memory Efficiency

* **Instance Variables:** If you have 1,000 objects and 5 instance variables, Python maintains 5,000 values in memory.
* **Static Variables:** If you have 1,000 objects and 5 static variables, Python maintains only 5 values in memory, shared by all.

---

Static (class) variables are shared across all instances. Because they belong to the class rather than a specific object, their lifecycle and rules for modification are unique.

---

### 1. Various Places to Declare Static Variables

You can define static variables in several locations depending on when you need them to be initialized:

* **Inside the Class Body:** The most common place; defined outside any method.
* **Inside the Constructor (`__init__`):** Using the Class Name.
* **Inside an Instance Method:** Using the Class Name.
* **Inside a Class Method:** Using either the Class Name or the `cls` variable.
* **Inside a Static Method:** Using the Class Name.

```python
class Test:
    a = 10  # 1. Directly in class body

    def __init__(self):
        Test.b = 20  # 2. Inside constructor

    def m1(self):
        Test.c = 30  # 3. Inside instance method

    @classmethod
    def m2(cls):
        cls.d1 = 40      # 4. Inside class method via cls
        Test.d2 = 400    # 4. Inside class method via Class Name

    @staticmethod
    def m3():
        Test.e = 50  # 5. Inside static method

```

---

### 2. How to Access Static Variables

Static variables are flexible in how they are read, but using the **Class Name** is the best practice for readability.

* **Inside Constructor/Instance Method:** Use `self.var_name` or `ClassName.var_name`.
* **Inside Class Method:** Use `cls.var_name` or `ClassName.var_name`.
* **Inside Static Method:** Use `ClassName.var_name`.
* **Outside the Class:** Use `object_reference.var_name` or `ClassName.var_name`.

---

### 3. Where to Modify Static Variables

You can modify a static variable from **anywhere**, but you must do so using the **Class Name** or the **`cls` variable** (in class methods).

```python
class Test:
    x = 10

# Modifying outside the class
Test.x = 20 

# Modifying inside a class method
@classmethod
def update(cls):
    cls.x = 30

```

---

### 4. Changing Values via `self` or Object Reference (Shadowing)

This is a critical rule: **If you try to modify a static variable using `self` or an object reference, you are not actually modifying the static variable.**

Instead, Python creates a **new instance variable** for that specific object with the same name. This is called **Shadowing**.

```python
class Test:
    a = 10

t1 = Test()
t1.a = 888  # This creates an INSTANCE variable for t1
print(Test.a) # Output: 10 (Static remains unchanged)
print(t1.a)   # Output: 888 (Accessing t1's instance variable)

```

---

### 5. How to Delete Static Variables

To remove a static variable from memory, you must use the `del` keyword with the Class Name or `cls`.

* **Correct Way:** `del ClassName.variable_name` or `del cls.variable_name`.
* **Incorrect Way:** You **cannot** delete a static variable using `self` or an object reference. Doing so will raise an `AttributeError`.

```python
class Test:
    a = 10

# Successful deletion
del Test.a

# Attempting to delete via object
t1 = Test()
# del t1.a  # This would raise: AttributeError: a

```

---

# Methods in OOPs Python

Methods are categorized based on whether they belong to the object (instance) or the class itself. Choosing the right method type ensures your code is memory-efficient and logically sound.

---

### 1. Instance Methods

These are the most common types of methods. They are used to describe the behavior of an **object**.

* **Key Requirement:** They must take `self` as the first parameter, which points to the current object.
* **Usage:** Use these when the method needs to access or modify **instance variables** (data unique to each object).
* **Access:** Called using the object reference (`s.display()`) or `self`.

```python
class Student:
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def display(self):  # Instance Method
        print(f"Hi {self.name}, your marks are: {self.marks}")

```

---

### 2. Class Methods

These methods belong to the **class** rather than any specific object.

* **Key Requirement:** Use the `@classmethod` decorator and pass `cls` as the first parameter.
* **Usage:** Use these when the method only needs to access **static (class-level) variables**. They are often used for "factory methods" (creating objects in specific ways).
* **Access:** Called using the Class Name (`Student.get_college_name()`).

```python
class Student:
    college = "AIIT"

    @classmethod
    def get_college(cls):  # Class Method
        print(f"College Name: {cls.college}")

```

---

### 3. Static Methods

These are general **utility methods** that do not require access to either instance or class variables.

* **Key Requirement:** Use the `@staticmethod` decorator. They do **not** take `self` or `cls` as parameters.
* **Usage:** Use these for independent logic, such as mathematical calculations or data formatting, that is still logically related to the class.
* **Access:** Called using the Class Name.

```python
class MathOperations:
    @staticmethod
    def add(x, y):  # Static Method
        return x + y

```

---

### 4. Setter and Getter Methods (Accessors & Mutators)

In professional programming, we often avoid accessing instance variables directly. Instead, we use specific methods to "get" and "set" values. This is known as **Data Encapsulation**.

#### **Setter Methods (Mutators)**

Used to set or update the value of an instance variable. This is useful for adding **validation logic** (e.g., ensuring marks aren't negative).

* **Syntax:** `def setVariable(self, value):`

#### **Getter Methods (Accessors)**

Used to retrieve the value of an instance variable without modifying it.

* **Syntax:** `def getVariable(self):`

**Example:**

```python
class Student:
    def setName(self, name): # Setter
        self.name = name

    def getName(self):       # Getter
        return self.name

s = Student()
s.setName("Durga")
print(s.getName())

```

---

### Summary Table: Which Method Should You Use?

| Method Type | Decorator | First Arg | Accesses | Purpose |
| --- | --- | --- | --- | --- |
| **Instance** | None | `self` | Instance + Static | Object-specific behavior |
| **Class** | `@classmethod` | `cls` | Static only | Class-level operations |
| **Static** | `@staticmethod` | None | None | General utility/Helper |

Here are the structured notes and code explanations for these two advanced object-oriented concepts in Python.

---

### 1. Program to track the Number of Objects created for a Class

To track how many objects (instances) are created for a specific class, we use a **Static Variable** (Class Level Variable) combined with a **Constructor** and a **Class Method**.

**How it works:**

1. **Static Variable:** We initialize a counter (e.g., `count = 0`) at the class level.
2. **Constructor (`__init__`):** Since the constructor executes every time a new object is born, we increment the static counter inside it.
3. **Class Method:** We use a class method to display the final count because the counter belongs to the class, not any single object.

**Example Program:**

```python
class Test:
    count = 0  # Static variable to act as a counter

    def __init__(self):
        # Increment the counter every time an object is created
        Test.count = Test.count + 1

    @classmethod
    def noOfObjects(cls):
        print('The total number of objects created:', cls.count)

# Creating objects
t1 = Test()
t2 = Test()
Test.noOfObjects() # Output: 2

t3 = Test()
t4 = Test()
t5 = Test()
Test.noOfObjects() # Output: 5

```

---

### 2. Passing Members of One Class to Another Class

We can pass an object of one class as an argument to a method of another class. This allows the second class to access the attributes and methods of the first class. This is a common way to achieve **communication between objects**.

**The Logic:**

* Class A (e.g., `Employee`) holds the data.
* Class B (e.g., `Manager`) has a method that accepts an instance of Class A as a parameter.
* Inside Class B's method, you can use the object reference to modify or display Class A's data.

**Example Program:**

```python
class Employee:
    def __init__(self, eno, ename, esal):
        self.eno = eno
        self.ename = ename
        self.esal = esal

    def display(self):
        print(f'ID: {self.eno}, Name: {self.ename}, Salary: {self.esal}')

class Manager:
    # This method receives an 'Employee' object as 'emp'
    def update_and_display(emp):
        # Accessing and modifying members of the Employee class
        emp.esal = emp.esal + 5000 
        print("--- Updated Employee Details ---")
        emp.display()

# 1. Create Employee object
e = Employee(101, 'Durga', 15000)

# 2. Pass the object 'e' to the Manager class method
Manager.update_and_display(e)

```

**Key Takeaways:**

* The `Manager` class does not inherit from `Employee`.
* It simply "uses" the `Employee` object to perform specific operations.
* This promotes **loose coupling**, making the code more modular and easier to maintain.

---

# Innser (Nested) class In Python

An **Inner Class** (or Nested Class) is a class defined inside another class. If an object's existence depends entirely on another object, it is natural to define the dependent class as an inner class.

---

### 1. Concept of Inner Classes

A class is called an "Inner Class" when it is declared within the scope of another class (the "Outer Class").

* **The Relationship:** You should use an inner class when one object cannot exist without the physical existence of another.
* **Analogy:** Without a **University**, there is no **Department**. Without a **Car**, there is no **Engine**. In these cases, `University` and `Car` are outer classes, while `Department` and `Engine` are inner classes.

---

### 2. Why Use Inner Classes?

* **Encapsulation:** It hides the inner class from the outside world if it is only relevant to the outer class.
* **Organization:** It groups logically related classes together, making the code more readable and maintainable.

---

### 3. Syntax for Defining and Accessing

Defining an inner class is straightforward: you simply write a `class` block inside another.

#### **Defining:**

```python
class Outer:
    def __init__(self):
        print("Outer class object creation")

    class Inner:
        def __init__(self):
            print("Inner class object creation")
        
        def m1(self):
            print("Inner class method execution")

```

#### **Accessing (Object Creation):**

You cannot create an object of the Inner class without an object of the Outer class. There are two ways to do this:

**Case 1: Step-by-Step Creation**

```python
o = Outer()          # 1. Create Outer object
i = o.Inner()        # 2. Use Outer object to create Inner object
i.m1()               # 3. Call Inner method

```

**Case 2: Direct Creation (Shortcut)**

```python
i = Outer().Inner()  # Creates both objects in one line
i.m1()

```

---

### 4. Nesting to Multiple Levels

Python allows you to nest classes to any depth (e.g., a class inside a class inside a class). However, accessing them requires navigating the hierarchy.

```python
class Head:
    def __init__(self):
        self.brain = self.Brain()

    class Brain:
        def talk(self):
            print("Thinking...")

h = Head()
h.brain.talk()

```

---

### 5. Practical Example: Human and Brain

This example demonstrates that a "Brain" is only useful when associated with a "Human."

```python
class Human:
    def __init__(self):
        self.name = 'Durga'
        self.head = self.Head() # Inner class object created during Outer init

    def display(self):
        print("Hello, I am", self.name)
        self.head.talk()

    class Head:
        def talk(self):
            print("Talking with my head...")

human = Human()
human.display()

```

---

### 6. Key Rules for UG Students

* **Dependency:** Inner classes are used to represent **"Has-A"** relationships where the "part" (inner) cannot exist without the "whole" (outer).
* **Accessing Outer Variables:** Inner classes can access the members of the outer class, but they typically require an instance of the outer class to do so.
* **Performance:** There is no significant performance penalty, but over-nesting can make code hard to read (keep it to 1 or 2 levels).

---

