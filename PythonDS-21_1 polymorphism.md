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
