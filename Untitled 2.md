# Python MCQ from datatypes to inner classes
Here are 10 multiple-choice questions for each of the requested topics, totaling 140 questions.

### 1. Data Types

1. **Which of the following is an immutable data type?**
* A) list
* B) set
* C) tuple
* D) dict
* **Answer: C**


2. **What is the result of `type(3.14)`?**
* A) `<class 'int'>`
* B) `<class 'float'>`
* C) `<class 'str'>`
* D) `<class 'complex'>`
* **Answer: B**


3. **Which data type is used to represent a sequence of characters?**
* A) int
* B) float
* C) bool
* D) str
* **Answer: D**


4. **What is the output of `bool("")`?**
* A) True
* B) False
* C) None
* D) Error
* **Answer: B**


5. **Which of these represents a complex number?**
* A) `2 + 3i`
* B) `2 + 3j`
* C) `2 + 3k`
* D) `complex(2, 3i)`
* **Answer: B**


6. **What is the maximum length of an identifier in Python?**
* A) 31 characters
* B) 63 characters
* C) 128 characters
* D) No fixed limit
* **Answer: D**


7. **How do you create a variable with the numeric value 5?**
* A) `x = 5`
* B) `x = int(5)`
* C) Both A and B
* D) `int x = 5`
* **Answer: C**


8. **Which function returns the length of a string?**
* A) `size()`
* B) `len()`
* C) `length()`
* D) `count()`
* **Answer: B**


9. **What is the data type of `[1, 2, 3]`?**
* A) tuple
* B) list
* C) set
* D) array
* **Answer: B**


10. **In Python, `True` is equivalent to which integer?**
* A) 0
* B) 1
* C) -1
* D) 10
* **Answer: B**



---

### 2. Lists

1. **Which method adds an element to the end of a list?**
* A) `insert()`
* B) `add()`
* C) `append()`
* D) `extend()`
* **Answer: C**


2. **How do you access the last element of a list `L`?**
* A) `L[0]`
* B) `L[-1]`
* C) `L[last]`
* D) `L.end()`
* **Answer: B**


3. **What does `L.pop()` do?**
* A) Removes the first element
* B) Removes the last element and returns it
* C) Deletes the entire list
* D) Removes a specific value
* **Answer: B**


4. **Which slice returns the entire list?**
* A) `L[0:0]`
* B) `L[:]`
* C) `L[1:]`
* D) `L[:-1]`
* **Answer: B**


5. **What is the result of `[1, 2] * 2`?**
* A) `[2, 4]`
* B) `[1, 2, 1, 2]`
* C) `[[1, 2], [1, 2]]`
* D) Error
* **Answer: B**


6. **Which method removes the first occurrence of a specific value?**
* A) `pop()`
* B) `remove()`
* C) `delete()`
* D) `discard()`
* **Answer: B**


7. **How do you sort a list in place?**
* A) `sorted(L)`
* B) `L.sort()`
* C) `L.arrange()`
* D) `L.order()`
* **Answer: B**


8. **What is the output of `len([[1, 2], [3, 4], [5, 6]])`?**
* A) 6
* B) 3
* C) 2
* D) 1
* **Answer: B**


9. **Which function converts a string into a list of characters?**
* A) `list("str")`
* B) `to_list("str")`
* C) `split("str")`
* D) `str.tolist()`
* **Answer: A**


10. **What is list comprehension?**
* A) A way to delete lists
* B) A concise way to create lists
* C) A method to sort lists
* D) A tool for debugging lists
* **Answer: B**



---

### 3. Tuples

1. **How do you create a tuple with a single element?**
* A) `t = (1)`
* B) `t = [1]`
* C) `t = (1,)`
* D) `t = tuple(1)`
* **Answer: C**


2. **Can you change an element inside a tuple?**
* A) Yes, using `t[0] = value`
* B) No, tuples are immutable
* C) Only if it contains a list
* D) Only using `update()`
* **Answer: B**


3. **Which method counts occurrences of a value in a tuple?**
* A) `sum()`
* B) `count()`
* *C) `index()`
* D) `find()`
* **Answer: B**


4. **How do you join two tuples?**
* A) `t1.extend(t2)`
* B) `t1 + t2`
* C) `t1.add(t2)`
* D) `join(t1, t2)`
* **Answer: B**


5. **What is tuple unpacking?**
* A) Deleting a tuple
* B) Assigning tuple elements to multiple variables
* C) Converting a list to a tuple
* D) Printing tuple elements
* **Answer: B**


6. **What is the output of `(1, 2) == (1, 2, 0)`?**
* A) True
* B) False
* C) Error
* D) None
* **Answer: B**


7. **What does `t.index(x)` return?**
* A) The value at index x
* B) The first index where x occurs
* C) The frequency of x
* D) A boolean if x exists
* **Answer: B**


8. **Tuples are typically faster than lists?**
* A) True
* B) False
* **Answer: A**


9. **What characters are used to define a tuple?**
* A) `[]`
* B) `{}`
* C) `()`
* D) `<>`
* **Answer: C**


10. **Which is valid: `x, y = (10, 20)`?**
* A) Valid
* B) Invalid
* **Answer: A**



---

### 4. Sets

1. **Does a set allow duplicate elements?**
* A) Yes
* B) No
* **Answer: B**


2. **How do you create an empty set?**
* A) `{}`
* B) `set()`
* C) `[]`
* D) `empty_set()`
* **Answer: B**


3. **Which method adds an element to a set?**
* A) `append()`
* B) `add()`
* C) `insert()`
* D) `push()`
* **Answer: B**


4. **What is the result of `{1, 2} | {2, 3}`?**
* A) `{2}`
* B) `{1, 2, 3}`
* C) `{1, 3}`
* D) `{1, 2, 2, 3}`
* **Answer: B**


5. **Which operation finds common elements between two sets?**
* A) Union
* B) Intersection
* C) Difference
* D) Symmetric Difference
* **Answer: B**


6. **Which method removes an element and raises an error if it doesn't exist?**
* A) `discard()`
* B) `remove()`
* C) `pop()`
* D) `delete()`
* **Answer: B**


7. **Are sets ordered?**
* A) Yes
* B) No
* **Answer: B**


8. **What is the output of `len({1, 1, 2, 2, 3})`?**
* A) 5
* B) 2
* C) 3
* D) 1
* **Answer: C**


9. **Which operator is used for set difference?**
* A) `&`
* B) `|`
* C) `-`
* D) `^`
* **Answer: C**


10. **Can a set contain a list?**
* A) Yes
* B) No, elements must be hashable
* **Answer: B**



---

### 5. Dictionaries (Dict)

1. **What is a dictionary key-value pair separator?**
* A) `,`
* B) `:`
* C) `-`
* D) `=`
* **Answer: B**


2. **How do you access the value associated with key 'k' in dict `D`?**
* A) `D('k')`
* B) `D['k']`
* C) `D.get_value('k')`
* D) `D{k}`
* **Answer: B**


3. **Which method returns all keys of a dictionary?**
* A) `all_keys()`
* B) `keys()`
* C) `get_keys()`
* D) `list_keys()`
* **Answer: B**


4. **What happens if you assign a value to an existing key?**
* A) Raises an error
* B) Creates a duplicate key
* C) Overwrites the existing value
* D) Adds to a list of values
* **Answer: C**


5. **Which method safely returns a value or `None` if the key isn't found?**
* A) `fetch()`
* B) `get()`
* C) `find()`
* D) `retrieve()`
* **Answer: B**


6. **How do you remove a key-value pair?**
* A) `D.remove(key)`
* B) `del D[key]`
* C) `D.delete(key)`
* D) `D.discard(key)`
* **Answer: B**


7. **What does `D.items()` return?**
* A) A list of keys
* B) A list of values
* C) A view of tuple pairs (key, value)
* D) The number of items
* **Answer: C**


8. **Are dictionary keys mutable?**
* A) Yes
* B) No, they must be immutable
* **Answer: B**


9. **What is the output of `{}.get("name", "Guest")`?**
* A) None
* B) "Guest"
* C) Error
* D) ""
* **Answer: B**


10. **How do you clear all items from a dictionary?**
* A) `D.empty()`
* B) `D.clear()`
* C) `D.reset()`
* D) `del D`
* **Answer: B**



---

### 6. Conditional Statements

1. **Which keyword is used for "else if" in Python?**
* A) `elseif`
* B) `elsif`
* C) `elif`
* D) `else if`
* **Answer: C**


2. **What is the mandatory character at the end of an `if` statement?**
* A) `;`
* B) `.`
* C) `:`
* D) `{`
* **Answer: C**


3. **How does Python define a block of code?**
* A) Brackets `{}`
* B) Parentheses `()`
* C) Indentation
* D) Quotation marks
* **Answer: C**


4. **Which operator is used for equality comparison?**
* A) `=`
* B) `==`
* C) `===`
* D) `is`
* **Answer: B**


5. **What is a ternary operator in Python?**
* A) `x ? y : z`
* B) `if x then y else z`
* C) `y if x else z`
* D) `x if y : z`
* **Answer: C**


6. **Which value is considered `False` in a condition?**
* A) 1
* B) "False"
* C) `[]` (empty list)
* D) `[0]`
* **Answer: C**


7. **What does the `is` operator check?**
* A) Value equality
* B) Identity (same memory address)
* C) Data type
* D) If a variable exists
* **Answer: B**


8. **Can you have an `if` statement without an `else`?**
* A) Yes
* B) No
* **Answer: A**


9. **What is the result of `not (5 > 2)`?**
* A) True
* B) False
* **Answer: B**


10. **Which keyword is used to skip a block of code (do nothing)?**
* A) `stop`
* B) `skip`
* C) `pass`
* D) `null`
* **Answer: C**



---

### 7. Loop Statements

1. **Which loop is used to iterate over a sequence (list, string, etc.)?**
* A) `while`
* B) `for`
* C) `do-while`
* D) `foreach`
* **Answer: B**


2. **What does `range(5)` produce?**
* A) 0, 1, 2, 3, 4, 5
* B) 1, 2, 3, 4, 5
* C) 0, 1, 2, 3, 4
* D) 5, 5, 5, 5, 5
* **Answer: C**


3. **Which keyword stops the loop entirely?**
* A) `continue`
* B) `break`
* C) `exit`
* D) `stop`
* **Answer: B**


4. **Which keyword skips the current iteration?**
* A) `skip`
* B) `pass`
* C) `continue`
* D) `next`
* **Answer: C**


5. **What is the output of `for i in range(1, 10, 2): print(i)`?**
* A) 1, 3, 5, 7, 9
* B) 1, 2, 3...9
* C) 2, 4, 6, 8, 10
* D) 1, 10, 2
* **Answer: A**


6. **When does the `else` block of a loop execute?**
* A) When the loop is terminated by `break`
* B) When the loop finishes normally without `break`
* C) Every iteration
* D) Only if the loop never starts
* **Answer: B**


7. **Which loop condition leads to an infinite loop?**
* A) `while False:`
* B) `while 1:`
* C) `for i in []:`
* D) `while 0:`
* **Answer: B**


8. **What is the purpose of `enumerate()` in a loop?**
* A) To count the items
* B) To get both index and value
* C) To sort the sequence
* D) To repeat the loop
* **Answer: B**


9. **What does `zip()` do in a loop?**
* A) Compresses data
* B) Iterates over multiple sequences simultaneously
* C) Deletes duplicates
* D) Joins strings
* **Answer: B**


10. **Which function generates a sequence in reverse?**
* A) `reverse()`
* B) `reversed()`
* C) `back()`
* D) `range_back()`
* **Answer: B**



---

### 8. Functions (Parameters & Types)

1. **Which keyword is used to define a function?**
* A) `func`
* B) `def`
* C) `define`
* D) `function`
* **Answer: B**


2. **What are default parameters?**
* A) Parameters that must be provided
* B) Parameters that take a value if none is provided
* C) Parameters that cannot be changed
* D) Parameters used only in recursion
* **Answer: B**


3. **Which syntax represents `*args` (varargs)?**
* A) Variable number of keyword arguments
* B) Variable number of positional arguments (tuple)
* C) Required parameters
* D) Recursive calls
* **Answer: B**


4. **Which syntax represents `**kwargs`?**
* A) Dictionary of variable keyword arguments
* B) Tuple of positional arguments
* C) Default parameters
* D) Local variables
* **Answer: A**


5. **What is a recursive function?**
* A) A function that returns another function
* B) A function that calls itself
* C) A function with no parameters
* D) A function inside a class
* **Answer: B**


6. **In `def greet(name, msg="Hi"):`, what is `msg`?**
* A) Required parameter
* B) Default parameter
* C) Named argument
* D) Vararg
* **Answer: B**


7. **How do you call a function using named parameters?**
* A) `func(10, 20)`
* B) `func(a=10, b=20)`
* C) `func(a:10)`
* D) `func.call(10)`
* **Answer: B**


8. **What happens if a recursive function has no base case?**
* A) It runs once
* B) It returns None
* C) It causes a `RecursionError` (Stack Overflow)
* D) It executes faster
* **Answer: C**


9. **What is the keyword to return a value from a function?**
* A) `get`
* B) `give`
* C) `return`
* D) `yield`
* **Answer: C**


10. **Can a function return multiple values?**
* A) No
* B) Yes, as a tuple
* **Answer: B**



---

### 9. Python Class and Object

1. **Which keyword is used to create a class?**
* A) `obj`
* B) `class`
* C) `struct`
* D) `def`
* **Answer: B**


2. **What is an object?**
* A) A blueprint for a class
* B) An instance of a class
* C) A type of function
* D) A library
* **Answer: B**


3. **Which method is called when an object is created?**
* A) `__new__`
* B) `__init__`
* C) `__start__`
* D) `__create__`
* **Answer: B**


4. **How do you instantiate a class `Dog`?**
* A) `d = Dog`
* B) `d = Dog()`
* C) `d = new Dog()`
* D) `d = create Dog`
* **Answer: B**


5. **What is the first parameter of any instance method?**
* A) `this`
* B) `cls`
* C) `self`
* D) `object`
* **Answer: C**


6. **What is Inheritance?**
* A) Creating multiple objects
* B) A class deriving properties from another class
* C) Deleting a class
* D) Private variables
* **Answer: B**


7. **What is the purpose of `super()`?**
* A) To call the parent class methods
* B) To delete an object
* C) To create a static method
* D) To bypass `self`
* **Answer: A**


8. **Which function checks if an object is an instance of a class?**
* A) `type()`
* B) `isinstance()`
* C) `check()`
* D) `issubclass()`
* **Answer: B**


9. **Attributes defined inside `__init__` are?**
* A) Class attributes
* B) Instance attributes
* C) Static attributes
* D) Local variables
* **Answer: B**


10. **What is Polymorphism?**
* A) Having many classes
* B) One interface/method acting differently on different types
* C) Private data
* D) Automatic memory management
* **Answer: B**



---

### 10. Managing Variables (Instance, Static, Local)

1. **Where are instance variables defined?**
* A) Outside all methods
* B) Inside methods using `self`
* C) Inside the class but outside methods
* D) In a global scope
* **Answer: B**


2. **Where are static (class) variables defined?**
* A) Inside `__init__`
* B) Inside the class body, but outside any methods
* C) Inside a local function
* D) Outside the class file
* **Answer: B**


3. **What is a local variable in a class?**
* A) A variable starting with `self.`
* B) A variable defined inside a method without `self.`
* C) A variable shared by all objects
* D) A global variable
* **Answer: B**


4. **How do you modify a static variable from outside the class?**
* A) `obj.var = val` (creates instance var)
* B) `ClassName.var = val`
* C) `self.var = val`
* D) Static variables cannot be modified
* **Answer: B**


5. **Which keyword deletes an attribute?**
* A) `remove`
* B) `del`
* C) `discard`
* D) `pop`
* **Answer: B**


6. **Static variables are shared by all instances?**
* A) True
* B) False
* **Answer: A**


7. **What happens if you do `obj.static_var = 5`?**
* A) Updates the static variable for all objects
* B) Creates a new instance variable for `obj` only
* C) Raises an error
* D) Deletes the variable
* **Answer: B**


8. **How do you access an instance variable?**
* A) `ClassName.var`
* B) `self.var` or `obj.var`
* C) `var`
* D) `global var`
* **Answer: B**


9. **Can a local variable be accessed outside its method?**
* A) Yes
* B) No
* **Answer: B**


10. **Which built-in function returns all attributes of an object?**
* A) `list()`
* B) `dir()`
* C) `attr()`
* D) `vars()`
* **Answer: B**



---

### 11. Methods (Instance, Static, Class)

1. **Which decorator defines a class method?**
* A) `@static`
* B) `@classmethod`
* C) `@class`
* D) `@instancemethod`
* **Answer: B**


2. **What is the first argument of a class method?**
* A) `self`
* B) `cls`
* C) `this`
* D) `base`
* **Answer: B**


3. **Which decorator defines a static method?**
* A) `@staticmethod`
* B) `@static`
* C) `@utility`
* D) `@method`
* **Answer: A**


4. **Does a static method receive `self` or `cls`?**
* A) Yes, `self`
* B) Yes, `cls`
* C) No
* **Answer: C**


5. **Instance methods are used to?**
* A) Manage class-level data
* B) Access/Modify instance state via `self`
* C) Perform general calculations
* D) Define the class blueprint
* **Answer: B**


6. **Which method type can modify class state?**
* A) Static Method
* B) Class Method
* C) Both B and Instance Method
* D) None
* **Answer: C**


7. **Can you call a class method using an object instance?**
* A) Yes
* B) No
* **Answer: A**


8. **Why use a static method?**
* A) To access instance variables
* B) For logic that doesn't depend on instance or class state
* C) To inherit from parent classes
* D) To initialize objects
* **Answer: B**


9. **Which method is used as a factory method?**
* A) Static Method
* B) Class Method
* C) Instance Method
* D) Destructor
* **Answer: B**


10. **Regular methods (without decorators) are?**
* A) Static methods
* B) Class methods
* C) Instance methods
* **Answer: C**



---

### 12. Self, Cls, and Object Creation

1. **What is `self`?**
* A) A reserved keyword
* B) A convention for the current instance reference
* C) A global variable
* D) A method name
* **Answer: B**


2. **Is `self` mandatory to be named "self"?**
* A) Yes
* B) No, but highly recommended
* **Answer: B**


3. **What does `cls` represent?**
* A) The current instance
* B) The class itself
* C) The parent class
* D) A local variable
* **Answer: B**


4. **Object creation happens when we call?**
* A) `class()`
* B) `ClassName()`
* C) `def()`
* D) `init()`
* **Answer: B**


5. **Which function creates the actual instance before `__init__`?**
* A) `__init__`
* B) `__new__`
* C) `__start__`
* D) `__instance__`
* **Answer: B**


6. **`self.name = name` creates?**
* A) A class variable
* B) An instance variable
* C) A local variable
* D) A global variable
* **Answer: B**


7. **Can you call an instance method from another instance method?**
* A) No
* B) Yes, using `self.method_name()`
* **Answer: B**


8. **Where is `self` passed?**
* A) Explicitly by the programmer during call
* B) Implicitly by Python during call
* **Answer: B**


9. **`cls` is primarily used in?**
* A) Instance methods
* B) Class methods
* C) Static methods
* D) Constructors
* **Answer: B**


10. **What is the type of an object created from class `A`?**
* A) `<class 'A'>`
* B) `<type 'object'>`
* C) `<class 'instance'>`
* D) `<type 'dict'>`
* **Answer: A**



---

### 13. Constructors, Destructors, and Garbage Collection

1. **The destructor method name is?**
* A) `__init__`
* B) `__del__`
* C) `__destroy__`
* D) `__exit__`
* **Answer: B**


2. **When is the destructor called?**
* A) When the program starts
* B) When an object is about to be destroyed/garbage collected
* C) When `del obj` is called (if no other references exist)
* D) Both B and C
* **Answer: D**


3. **What is the primary role of the constructor?**
* A) To delete objects
* B) To initialize object state
* C) To clear memory
* D) To define static variables
* **Answer: B**


4. **What is Garbage Collection?**
* A) Deleting code
* B) Automatic memory management to reclaim unused objects
* C) Cleaning the console
* D) Handling syntax errors
* **Answer: B**


5. **Python's garbage collector primarily uses?**
* A) Manual Deletion
* B) Reference Counting
* C) Mark and Sweep
* D) Both B and C
* **Answer: D**


6. **Can you manually trigger garbage collection?**
* A) No
* B) Yes, using `gc.collect()`
* **Answer: B**


7. **What is a circular reference?**
* A) A loop in a function
* B) Two objects referring to each other
* C) A recursive call
* D) A sorted list
* **Answer: B**


8. **Does `del obj` always call the destructor immediately?**
* A) Yes
* B) No, only if the reference count becomes zero
* **Answer: B**


9. **Which module handles Garbage Collection?**
* A) `sys`
* B) `gc`
* C) `mem`
* D) `os`
* **Answer: B**


10. **What is the output of `__init__`?**
* A) The object
* B) None
* C) True
* D) An integer
* **Answer: B**



---

### 14. Inner Classes

1. **What is an inner class?**
* A) A class outside a module
* B) A class defined inside another class
* C) A parent class
* D) A hidden class
* **Answer: B**


2. **Why use an inner class?**
* A) For better organization/grouping of related classes
* B) To increase code size
* C) To replace inheritance
* D) For global access
* **Answer: A**


3. **How do you create an object of an inner class `Inner` inside `Outer`?**
* A) `i = Inner()`
* B) `i = Outer.Inner()`
* C) `o = Outer(); i = o.Inner()`
* D) Both B and C
* **Answer: D**


4. **Can an inner class access outer class variables?**
* A) Yes
* B) No
* **Answer: A**


5. **Can an outer class access inner class variables directly?**
* A) Yes
* B) No, needs an instance of the inner class
* **Answer: B**


6. **How many levels of nesting are allowed for classes?**
* A) 1
* B) 2
* C) 5
* D) Unlimited (limited by memory/readability)
* **Answer: D**


7. **Is an inner class object tied to an outer class object?**
* A) Yes, typically
* B) No
* **Answer: A**


8. **If `class A: class B: pass`, how do you reach B?**
* A) `A.B`
* B) `B`
* C) `A->B`
* D) `self.B`
* **Answer: A**


9. **Can an inner class have its own `__init__`?**
* A) Yes
* B) No
* **Answer: A**


10. **Does deleting the outer object delete the inner object?**
* A) If only the outer object held the reference
* B) Never
* C) Always
* **Answer: A**



---

Good luck with your studies! This is a great set of topics to master Python OOP and core concepts. Encouraging you to try coding these examples to see them in action!