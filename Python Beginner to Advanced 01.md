# Garbage Collection in Python
Memory management is handled automatically. When objects are no longer needed, Python's **Garbage Collector (GC)** steps in to free up memory, and **Destructors** provide a way to perform cleanup tasks before an object is destroyed.

---

### 1. Garbage Collection

Garbage Collection is the process of automatically reclaiming memory by destroying objects that are no longer reachable or "referenced."

* **Primary Mechanism:** Python uses **Reference Counting**. Every object keeps track of how many variables point to it. When the reference count drops to zero, the object is eligible for deletion.
* **Secondary Mechanism:** Python also has a cycle-detecting garbage collector to handle "circular references" (e.g., Object A points to B, and B points back to A, but both are otherwise unreachable).

---

### 2. How to Enable and Disable Garbage Collector

While GC runs automatically, you can manually control it using the `gc` module. This is sometimes done in high-performance computing to prevent the GC from pausing the program at a critical moment.

```python
import gc

# To check if GC is enabled
print(gc.isenabled()) # Returns True by default

# To disable Garbage Collector
gc.disable()
print("GC is disabled...")

# To enable Garbage Collector
gc.enable()
print("GC is enabled...")

```

* **Note:** You can also manually trigger a collection using `gc.collect()`.

---

### 3. Destructors (`__del__`)

A **Destructor** is a special method that is called just before an object is destroyed by the garbage collector.

* **Method Name:** `__del__(self)`
* **Purpose:** To perform cleanup activities like closing database connections or closing open files.

**Example Snippet:**

```python
import time

class Test:
    def __init__(self):
        print("Object Initialization/Resource Acquisition...")

    def __del__(self):
        print("Fulfilling Last Wish: Closing Resources/Cleanup...")

t1 = Test()
t1 = None   # Removing the reference; Destructor is called
time.sleep(2)
print("End of application")

```

**Constructor VS Destrucor**

| Feature | Constructor (`__init__`) | Destructor (`__del__`) |
| :--- | :--- | :--- |
| **Execution** | When object is created. | Just before object is destroyed. |
| **Purpose** | To initialize instance variables. | To perform cleanup/resource release. |

---

### 4. How to Find the Number of References

To find out how many variables are currently pointing to an object, we use the `sys` module's `getrefcount()` function.

* **Important:** `sys.getrefcount()` always returns a count that is **one higher** than the actual count. This is because passing the object to the function itself creates a temporary reference.

**Example Snippet:**

```python
import sys

class Test:
    pass

t1 = Test()
t2 = t1
t3 = t1
t4 = t1

# Actual references are 4 (t1, t2, t3, t4)
# Output will be 5 because getrefcount(t1) adds +1
print(sys.getrefcount(t1)) 

```

---

### Summary for Students:

1. **GC:** A background assistant that cleans up memory.
2. **`gc` module:** Used to `enable()`, `disable()`, or manually `collect()`.
3. **`__del__`:** The final goodbye of an object; use it for closing files or connections.
4. **`sys.getrefcount()`:** Used to peek at how many variables are holding an object in memory.



# Inner Class Code

```python
class OuterClass:
    o_var = 10
    def __init__(self):
        print("outer constructor")
        #print(InnerClass.i_var)

    def outer_m1(self):
        print("instance method of outer")
    @classmethod
    def outer_m2(cls):
        print("class method outer_m2()")

    @staticmethod
    def outer_m3():
        print("static method outer_m3()")
        
    class InnerClass:
        i_var = 20
        def __init__(self):
            print("inner constructor")
            print(OuterClass.o_var)


        def inner_m1(self):
            print("instance method inner_m1()")
            
        @classmethod
        def inner_m2(cls):
            print("class method outer_m2()")

        @staticmethod
        def inner_m3():
            print("static method outer_m3()")
            

#demo
o = OuterClass()
i = o.InnerClass()
ii = OuterClass.InnerClass()
print(OuterClass.o_var)
print(o.o_var)
print(i.i_var)
print(OuterClass.InnerClass.i_var)
o.outer_m1()
o.outer_m2()
OuterClass.outer_m2()
o.outer_m3()
OuterClass.outer_m3()

i.inner_m1()
i.inner_m2()
OuterClass.InnerClass.inner_m2()

i.inner_m3()
OuterClass.InnerClass.inner_m3()

```

# Simple Inheritance Code
```python
class Shape:
    def __init__(self, dim):
        self.dim = dim
    #setter
    def setDim(self, dim):
        self.dim = dim
    #getter
    def getDim(self):
        return self.dim

class Circle(Shape):
    def area(self):
        return 3.1415 * self.getDim() * self.getDim()
    def perimeter(self):
        return 2 * 3.1415 * self.getDim()
    

#Demo
s = Shape(15)
print(s.getDim())
c = Circle(25)
print(c.getDim())
print(f"Circle Area: {c.area()}")
print(f"Circle Perimeter: {c.perimeter()}")

```

# Multilevel Inheritance Code
```python
class Shape:
    def __init__(self, dim):
        self.dim = dim
    #setter
    def setDim(self, dim):
        self.dim = dim
    #getter
    def getDim(self):
        return self.dim    

class Square(Shape):
    def area(self):
        return self.getDim() * self.getDim()
    def perimeter(self):
        return 4 * self.getDim()
    
class Rectangle(Square):
    def __init__(self, length, width):
        self.dim = length
        self.width = width
    def area(self):
        return self.dim * self.width

    def perimeter(self):
        return 2 * (self.dim + self.width)

class Cuboid(Rectangle):
    def __init__(self, length, width, height):
        self.dim = length
        self.width = width
        self.height = height
    def volume(self):
        return self.dim * self.width * self.height

    def surfaceArea(self):
        return 2 * (self.dim*self.width + self.width*self.height + self.height*self.dim)
    
        
#Demo
s = Shape(15)
print(s.getDim())

sqr = Square(15.5)
print(f"Square Area: {sqr.area()}")
print(f"Square Perimeter: {sqr.perimeter()}")

r1 = Rectangle(15.5, 45.5)
print(f"Rectangle Area: {r1.area()}")
print(f"Rectangle Perimeter: {r1.perimeter()}")

cub = Cuboid(15.5, 12.5, 45.5)
print(f"Cuboid Volume: {cub.volume()}\nCuboid Surface Area: {cub.surfaceArea()}")
 

```

# Hierarchical Inheritance Code
```python
class Shape:
    def __init__(self, dim):
        self.dim = dim
    #setter
    def setDim(self, dim):
        self.dim = dim
    #getter
    def getDim(self):
        return self.dim

class Circle(Shape):
    def area(self):
        return 3.1415 * self.getDim() * self.getDim()
    def perimeter(self):
        return 2 * 3.1415 * self.getDim()
    

class Square(Shape):
    def area(self):
        return self.getDim() * self.getDim()
    def perimeter(self):
        return 4 * self.getDim()
    

#Demo    
s = Shape(15)
print(s.getDim())

c = Circle(25)
print(c.getDim())
print(f"Circle Area: {c.area()}")
print(f"Circle Perimeter: {c.perimeter()}")

sqr = Square(15.5)
print(f"Square Area: {sqr.area()}")
print(f"Square Perimeter: {sqr.perimeter()}")   

```


# Multiple Inheritance 

```python
class Parent1:
    def __init__(self, a):
        self.a = a
        print("Parent1 Constructor")
    def p1m1(self):
        print("Parent1 m1()")

class Parent2:
    def __init__(self, b):
        self.b = b
        print("Parent2 Constructor")
    def p2m1(self):
        print("Parent2 m1()")

class Child(Parent1, Parent2):
    def __init__(self, a, b):
        super().__init__(b)
        print("Child Constructor")

#demo
c = Child(12, 15)
print(c.a)

c.p1m1()
c.p2m1()

```



```python
class Person:
    def __init__(self, name):
        self.name = name

class Job:
    def __init__(self, salary):
        self.salary = salary

class Employee(Person, Job):  # Inherits from both Person and Job
    def __init__(self, name, salary):
        Person.__init__(self, name)
        Job.__init__(self, salary)

    def details(self):
        print(self.name, "earns", self.salary)

emp = Employee("Jennifer", 50000)
emp.details()
```

# Hybrid Inheritance Code

```python
class Vehicle:
    def identify_vehicle(self):
        print("I am a vehicle.")

class Car(Vehicle): # Single/Hierarchical inheritance
    def drive(self):
        print("I can drive.")

class Boat(Vehicle): # Single/Hierarchical inheritance
    def sail(self):
        print("I can sail.")

class AmphibiousVehicle(Car, Boat): # Multiple inheritance (creating the hybrid structure)
    def operate(self):
        print("I can do both!")

# Usage example:
amphibious = AmphibiousVehicle()
amphibious.identify_vehicle() # Inherited from Vehicle via Car/Boat
amphibious.drive() # Inherited from Car
amphibious.sail() # Inherited from Boat
amphibious.operate() # Defined in AmphibiousVehicle

```