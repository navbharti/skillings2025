# Polymorphism
# Overloading
## Method Overloading
```python
class Arithmetic:
    @staticmethod
    def calc(a=None, b=None):
        if a==None and b==None:
            return "no params passed"
        elif a!=None and b==None:
            sum = 0
            for i in range(1,a+1):
                sum += i
            return sum
        elif a==None and b!=None:
            fact = 1
            for i in range(1, b+1):
                fact *= i
            return fact
        elif a!=None and b!=None:
            return a+b, a*b, a/b, a%b


res = Arithmetic.calc()
print(res)
res1 = Arithmetic.calc(10)
print(res1)
res2 = Arithmetic.calc(b=5)
print(res2)
res3 = Arithmetic.calc(10, 5)
print(res3)

```
## Operator Overloading
```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def distance(self, p1):
        pass

    def display(self):
        print(f"Point({self.x}, {self.y})")
        
    def __add__(self, p2):
        x = self.x + p2.x
        y = self.y + p2.y
        p = Point(x, y)
        return p

p1 = Point(5, 3)
p2 = Point(4, 4)
p3 = p1 + p2
p1.display()
p2.display()
p3.display()

```
## Constructor Overloading
```python
class Rectangle:
    def __init__(self, length=None, breadth=None):
        self.length = 10.0
        self.breadth = 10.0
        if length==None and breadth==None:
            self.length = 10.0
            self.breadth = 10.0
        elif length!=None and breadth==None:
            self.length = length
            self.breadth = 10.0
        elif length!=None and breadth!=None:
            self.length = length
            self.breadth = breadth

    def display(self):
        print(f"Rectangle({self.length}, {self.breadth})")

r1 = Rectangle()
r2 = Rectangle(12.5)
r3 = Rectangle(12.5, 15.5)
r1.display()
r2.display()
r3.display()

```


# toString() implementation in Python OOPS
```python
class Dog:
    def __init__(self, name, breed, color):
        self.name = name
        self.breed = breed
        self.color = color

    def __str__(self):
        """Returns a user-friendly string representation."""
        return f"{self.name} is a {self.color} {self.breed}"

    def __repr__(self):
        """Returns a developer-friendly string representation."""
        return f"Dog(name='{self.name}', breed='{self.breed}', color='{self.color}')"

# Create an instance of the class
my_dog = Dog("Buddy", "Golden Retriever", "golden")

# Usage examples
print(str(my_dog))  # Calls __str__()
print(repr(my_dog)) # Calls __repr__()
print(my_dog)       # Calls __str__() implicitly

# Output:
# Buddy is a golden Golden Retriever
# Dog(name='Buddy', breed='Golden Retriever', color='golden')
# Buddy is a golden Golden Retriever

```


```python
class Rectangle:
    def __init__(self, length, breadth):
        self.length = length
        self.breadth = breadth

    def area(self):
        return self.length * self.breadth

    def perimeter(self):
        return 2* (self.length + self.breadth)

    def __del__(self):
        print(f"Area: {self.area()} and Perimeter: {self.perimeter()}")

    def __str__(self):
        s = f"Length: {self.length}\nBreadth: {self.breadth}\nArea: {self.area()}\nPerimeter: {self.perimeter()}"
        return s
    
r1 = Rectangle(12.5, 15.5)
print(f"r1.area(): {r1.area()}")
print(f"r1.perimeter(): {r1.perimeter()}")
print(r1)
del r1

```