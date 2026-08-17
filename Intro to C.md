# Chapter - 0 
## Input and Output

In C programming, input and output (I/O) operations are performed using standard library functions defined in the `<stdio.h>` header file. These functions allow programs to interact with the user through the standard console (keyboard and screen) or with files for data storage. 
C I/O functions are categorized as either **formatted** (using format specifiers like %d, %f) or **unformatted** (dealing with raw data, typically single characters or strings). 

### Standard Console I/O Functions
The most common I/O functions interact with the standard input (stdin, usually the keyboard) and standard output (stdout, usually the screen). 
#### Formatted I/O
`printf():` This is the primary function for displaying formatted output to the console. It uses format specifiers and escape sequences (like \n for a newline) to control the appearance of the output.

Example: 
```c 
printf("Hello, %s! Your age is %d.\n", name, age);
```

`scanf():` This is the primary function for reading formatted input from the keyboard. It requires the memory address of variables (using the & operator) to store the input values.

Example: 
```c
scanf("%d %f", &age, &salary); 
```

#### Unformatted I/O
These functions handle data without specific format control, usually for single characters or whole strings. 
- `getchar():` Reads a single character from the standard input.
- `putchar():` Writes a single character to the standard output.
- `gets():` Reads an entire string, including spaces, from standard input (this function is deprecated and considered unsafe due to buffer overflow risks; fgets() is preferred for strings).
- `puts():` Writes a string to standard output, automatically adding a newline character at the end. 
#### File I/O Functions
These functions are used to read from and write to files on disk, enabling data persistence beyond a program's execution. 
- `fopen():` Opens a file and associates it with a file pointer (FILE *).
- `fclose():` Closes an opened file to free system resources.
- `fprintf():` Writes formatted output to a file.
- `fscanf():` Reads formatted input from a file.
- `fgets():` Reads a line of text from a file or stdin into a string, up to a specified size.
- `fputs():` Writes a string to a file without adding a newline automatically.
- `fread()` and fwrite(): Used for reading and writing binary data. 

#### Key Concepts
Header File: The #include <stdio.h> preprocessor directive is required to use these standard I/O functions.
Format Specifiers: Placeholders that begin with a % sign (e.g., %d for integer, %f for float, %c for character, %s for string) used to tell the compiler the type of data being handled.
Address Operator (&): Used with scanf() (except for strings, as the array name is already a pointer) to provide the memory address where the input data should be stored. 

Printing Some Text
```c
#include <stdio.h>

int main() {
  
    // Prints some text
    printf("First Print");  
  
    return 0;
}
```

text inside "" is called a string in C

Printing Variable value

```c
#include <stdio.h>

int main() {
  	int age = 22;
  
    // Prints Age
    printf("%d\n", age);  
  
    return 0;
}
```
%d in the formatted string also called **format specifier** which are used as **placeholders** for the value in the formatted string.

'\n' character is an **escape sequence** and is used to enter a newline.

Printing Variables Along with String

```c
#include <stdio.h>

int main() {
  	int age = 22;
  
    // Prints Age
    printf("The value of the variable age is %d\n", age);  
  
    return 0;
}
```

Reading User Input

```c
scanf("formatted_string", address_of_variables/values);
```

Reading an Integer
```c
#include <stdio.h>

int main() {
    int age;
    printf("Enter your age: ");
  
    // Reads an integer
    scanf("%d", &age);  
  
    // Prints the age
    printf("Age is: %d\n", age);  
    return 0;
}
```

`%d` is used to read an integer; and `&age` provides the address of the variable where the input will be stored.

Reading a Character
```c
#include <stdio.h>

int main() {
    char ch;
    printf("Enter a character: \n");
  
    // Reads an Character
    scanf("%c", &ch);  
  
    // Prints the Character
    printf("Entered character is: %c\n", ch);  
    return 0;
}
```

Reading a String
```c
#include <stdio.h>

int main() {
    char str[100];  // Declare an array to hold the input string

    printf("Enter a string: ");
    scanf("%s", str);  // Reads input until the first space or newline

    printf("You entered: %s\n", str);

    return 0;
}
```

## Format Specifiers in C
tell the compiler what type of data to be printed or scanned in input and output operations.
1. Character Format Specifier - %c in C

```c
#include <stdio.h>

int main(){
    char c;
    
    // Using %c for character input
    scanf("%c", &c);

    // Using %c for character output
    printf("The entered character: %c", c);
    return 0;
}
```


2. Integer Format Specifier (signed) - %d in C
```c
#include <stdio.h>

int main() {
    int x;
    
    // taking integer input
    scanf("%d", &x);

    // printing integer output
    printf("Printed using %%d: %d\n", x);
    printf("Printed using %%i: %i", x);
    return 0;
}
```


3. Unsigned Integer Format Specifier - %u in C
```c
#include <stdio.h>

int main(){
    unsigned int var;
    scanf("%u", &var);
    printf("Unsigned Integer: %u\n", var);

    // trying to print negative value using %u
    printf("Printing -10 using %%u: %u\n", -10);
    return 0;
}
```


4. Floating-point format specifier - %f in C
```c
#include <stdio.h>

int main(){
    float a = 12.67;
    printf("Using %%f: %f\n", a);
    printf("Using %%e: %e\n", a);
    printf("Using %%E: %E", a);
    return 0;
}
```


5. Unsigned Octal number for integer - %o in C

```c
#include <stdio.h>

int main() {
    int a = 67;
    printf("%o\n", a);
    return 0;
}
```


6. Unsigned Hexadecimal for integer - %x in C
```c
#include <stdio.h>
int main() {
    int a = 15454;
    printf("%x\n", a);
    printf("%X", a);
    return 0;
}
```


7. String Format Specifier - %s in C
```c
#include <stdio.h>

int main(){
    char a[] = "Hi Computer Science";
    printf("%s", a);
    return 0;
}
```


```c
#include <stdio.h>

int main(){
    char str[50];
    
    // taking string as input
    scanf("%s", str);
    printf("Entered String: %s", str);
    return 0;
}
```

8. Address Format Specifier - %p in C
```c
#include <stdio.h>

int main(){
    int a = 10;
    printf("The Memory Address of a: %p", &a);
    return 0;
}
```


## Input and Output Formatting
Inserted between the % sign and the format specifier symbol:

- A minus(-) sign tells left alignment.
- A number after % specifies the minimum field width to be printed if the characters are less than the size of the width the remaining space is filled with space and if it is greater then it is printed as it is without truncation.
- A period( . ) symbol separates field width with precision.

Precision tells the minimum number of digits in an integer, the maximum number of characters in a string, and the number of digits after the decimal part in a floating value.

```c
#include <stdio.h>
int main()
{
    char str[] = "geeksforgeeks";
    printf("%20s\n", str);
    printf("%-20s\n", str);
    printf("%20.5s\n", str);
    printf("%-20.5s\n", str);
    return 0;
}
```

### List of C Format Specifiers

|Format Specifier |Description|
|-----------------|-----------|
| %c | For character type. |
|%d|For signed integer type.|
|%e or %E|For scientific notation of floats.|
|%f|For float type.|
|%g or %G|For float type with the current precision.|
|%i|signed integer|
|%ld or %li|Long|
|%lf|Double|
|%Lf|Long double|
|%lu|Unsigned int or unsigned long|
|%lli or %lld|Long long|
|%llu|Unsigned long long|
|%o|Octal representation|
|%p|Pointer|
|%s|String|
|%u|Unsigned int|
|%x or %X|Hexadecimal representation|
|%n|Prints nothing|
|%%|Prints % character|

## Escape Sequence in C
Special character representations in strings, and a specific control function. They start with a backslash \ followed by a character (e.g., \n, \t).

\n - Prints a new line


```c
#include <stdio.h>
​
int main(void)
{
    // Here we are using \n, which is a new line character.
    printf("Hello\n");
    printf("GeeksforGeeks");
    
    return (0);
}
```


\t - Prints a tab

```c

#include <stdio.h>
​
int main(void)
{
    // \t will provide a tab space between two words.
    printf("Hello \t GFG");
    
    return (0);
}
```


\\ - Prints a single backslash (\)


```c
#include <stdio.h>
​
int main(void)
{
    // \\ prints a single backslash (\)
    printf("Hello\\GFG");
    
    return (0);
}
```



\b - Moves the cursor one position back


```c
#include <stdio.h>
​
int main(void)
{
    // \b (backspace) character moves the cursor one position back
    printf("Hello \b\b\b\b\b\bHi Geeks");
    
    return (0);
}
```


\' and \'' - Prints single (') and double (") quote.


```c
#include <stdio.h>
​
int main(void)
{
    // \' prints a single quote (')
    printf("\' Hello Geeks\n");
​
    // \" prints a double quote (")
    printf("\" Hello Geeks");
​
    return 0;
}
```

\v - Prints a vertical tab

```c

#include <stdio.h>
​
int main(void)
{
    // \v prints a vertical tab and moves the cursor down to the next vertical tab position.
    printf("Hello friends\v");
​
    printf("Welcome to GFG");
​
    return (0);
}
```


\r - Moves the cursor to the beginning of the current line.


```c
#include <stdio.h>
​
int main(void)
{
    // \r Moves the cursor to the beginning of the current line
    printf("Hello   Geeks \rGeeksfor");
    
    return (0);
}
```

\? - Prints a question mark


```c
#include <stdio.h>
​
int main(void)
{
    // \? is used to print a question mark (?)
    printf("\?\?!\n");
​
    return 0;
}
```


\a - Produces a beep/alert sound.


```c
#include <stdio.h>
​
int main(void)
{
    // \a triggers a sound or system beep in the console
    printf("Hello!\a\n");
    printf("This is a beep\a\n");
​
    return 0;
}
```

\ooo - Represents a character using its octal value.


```c
#include <stdio.h>
​
int main(void)
{
    // \ooo Represents a character using its octal value (0-7)
    char *s = "A\072\065";
    printf("%s", s);
​
    return 0;
}
```


\xhh - Represents a character using its hexadecimal value.


```c
#include <stdio.h>
​
int main(void)
{
    // \xhh Represents a character using its hex value (0-9, a-f, A-F)
    char *s = "B\x4a";
    printf("%s", s);
​
    return 0;
}
```


### Escape Sequence List

|Escape Sequence|	Name	|Description|
|---|---|---|
|\a	|Alarm or Beep	|It is used to generate a bell sound in the C program.|
|\b	|Backspace	|It is used to move the cursor one place backward.|
|\f	|Form Feed	|It is used to move the cursor to the start of the next logical page.|
|\n	|New Line	|It moves the cursor to the start of the next line.|
|\r	|Carriage Return	|It moves the cursor to the start of the current line.|
|\t	|Horizontal Tab	|It inserts some whitespace to the left of the cursor and moves the cursor accordingly.|
|\v	|Vertical Tab|	It is used to insert vertical space.|
|\\	|Backslash	|Use to insert backslash character.|
|\'	|Single Quote	|It is used to display a single quotation mark.|
|\"	|Double Quote	|It is used to display double quotation marks.|
|\?	|Question Mark	|It is used to display a question mark.|
|\ooo	|Octal Number	|It is used to represent an octal number.|
|\xhh	|Hexadecimal Number |	It represents the hexadecimal number.|
|\0	|NULL|	It represents the NULL character.|

# Keywords in C
Keywords are predefined or reserved words that have special meanings to the compiler. These are part of the syntax and cannot be used as **identifiers** in the program. 


|auto | break | case | char | const | continue | default | do |
|---|---|---|---|---|---|---|---|
|double | else | enum | extern | float | for | goto | if |
|int|long|register|return|short|signed|sizeof|static|
|struct|switch|typedef|union|unsigned|void|volatile|while|

We cannot use these **keywords** as **identifiers** (such as variable names, function names, or struct names). The compiler will throw an **error** if we try to do so.

```c
#include <stdio.h>

int main() {
    int return = 10;   
    printf("%d\n", return);
    return 0;
}
```

```console
./Solution.c: In function 'main':
./Solution.c:4:9: error: expected identifier or '(' before 'return'
     int return = 10;   
         ^
./Solution.c:5:20: error: expected expression before 'return'
     printf("%d\n", return);
                    ^
```

|Category	|Keywords|
|---|---|
|Data Type Keywords|char, int, float, double, void, short, long, signed, unsigned|
|Operator & Utility Keywords	|sizeof, return, goto, typedef|
|Control Flow Keywords|if, else, switch, case, default, for, while, do, break, continue|
|Storage Class Keywords	|auto, register, static, extern|
|Type Qualifiers	|const, volatile|
|User Defined Types	|struct, union, enum|

# Identifiers in C
identifiers are the names used to identify **variables**, **functions**, **arrays**, **structures**, or any other **user-defined items**. It is a name that uniquely identifies a program element and can be used to refer to it later in the program.

## Rules for Naming Identifiers in C
- Uppercase (A-Z) and lowercase (a-z) alphabets.
- Numeric digits (0-9).
- Underscore (_).
- The first character of an identifier must be a letter or an underscore.
- Identifiers are case-sensitive.
- Identifiers cannot be keywords in C (such as int, return, if, while etc.).

```c
#include <stdio.h>

int main() {
      
      // Creating an integer variable and
      // assign it the identifier 'var'
      int var;
  
      // Assigning value to the variable
      // using assigned name
      var = 10;
  
      // Referring to same variable using 
      // assigned name
      printf("%d", var);
      
      return 0;
}
```

## Naming Convention
- For Variables:
	- Use camelCase for variable names (e.g., frequencyCount, personName).
 	- Constants can use UPPER_SNAKE_CASE (e.g., MAX_SIZE, PI).
 	- Start variable names with a lowercase letter.
 	- Use descriptive and meaningful names.
- For Functions:
	- Use camelCase for function names (e.g., getName(), countFrequency()).
	- Function names should generally be verbs or verb phrases that describe the action.
- For Structures:
	- Use PascalCase for structure names (e.g., Car, Person).
	- Structure names should be nouns or noun phrases.

## Difference Between Keywords and Identifiers

|Keywords	|Identifiers|
|---|----|
|Reserved Words in C that have a specific meaning and use in the syntax	| Names given to variables, functions, structs, etc.|
|Cannot be used as variable names.	|Can be used as variable names (if not a keyword).|
|Examples: int, return, if, while	| Examples: x, total, count|
|Part of the C language grammar.	|User-defined, meaningful names in the code.|
|Cannot be redefined or repurposed.	|Can be defined redefined and reused as needed.|


## Variable in C
- A variable in C is a name given to a memory location which is used to store data and access it whenever required.
- It allows us to use the memory without having to memorize the exact memory address.
- To create a variable in C, we have to specify a name and the type of data it is going to store.
- C provides different data types that can store almost all kinds of data. For example, int, char, float, double, etc.
- Every variable must be declared before it is used. We can also declare multiple variables of same data type in a single statement by separating them using comma .

```c
#include <stdio.h>

int main()
{
    // integer variable
    int age = 20;

    // floating-point variable
    float height = 5.7;

    // character variable
    char grade = 'A';

    printf("Age: %d\n", age);
    printf("Height: %.1f\n", height);
    printf("Grade: %c\n", grade);

    return 0;
}
```

## C Variable Initialization
Once the variable is **declared**, we can store useful values in it. The first value we store is called **initial value** and the process is called **Initialization**. It is done using **assignment operator (=)**.
It is important to initialize a variable because a C variable only contains **garbage value** when it is declared. We can also initialize a variable along with declaration.

```c
#include <stdio.h>

int main()
{
    // 1. Initialization at the time of declaration
    int age = 20;
    float height = 5.7;

    // 2. Initialization after declaration
    char grade;
    grade = 'A';

    printf("Age: %d\n", age);
    printf("Height: %.1f\n", height);
    printf("Grade: %c\n", grade);

    return 0;
}
```

## Accessing Variables
The data stored inside a C variable can be easily accessed by using the variable's name.


```c
#include <stdio.h>
​
int main() {
    
    // Create integer variable
    int num = 3;
    
    // Access the value stored in
    // variable
    printf("%d", num);
    return 0;
}
```

## Changing Stored Values
We can also update the value of a variable with a new value whenever needed by using the assignment operator =.

```c
#include <stdio.h>

int main()
{

    // initial value
    int number = 10;
    printf("Initial value: %d\n", number);

    // updating value
    number = 25;
    printf("Updated value: %d\n", number);

    // updating again using expression
    number = number + 5;
    printf("After adding 5: %d\n", number);

    return 0;
}
```

## Memory Allocation of C Variables
When a variable is **declared**, no memory is allocated to it yet. Memory is allocated when the variable is **defined**.

Most programming languages like C generally declare and define a variable in the single step. For example, in the above part where we create a variable, variable is declared and defined in a single statement.

The size of memory assigned for variables depends on the type of variable. We can check the size of the variables using **sizeof operator**.

```c
#include <stdio.h>

int main() {
    int num = 22;
    
    // Finding size of num
    printf("%d bytes", sizeof(num));
    return 0;
}
```

## Different ways of declaring and defining a variable in C
In C programming, a variable must be declared to tell the compiler its name and type, and it must be defined (memory allocated) before use. The most common approach combines both steps with initialization in a single statement. 

### 1. Separate Declaration and Definition
You can declare a variable without defining it (allocating memory) by using the **extern keyword**. This is typically used when a variable is defined in another source file and you need to reference it in the current file. 
Declaration (in a header file or current file): Informs the compiler about the variable's existence and type, but allocates no memory.

```c
extern int my_variable; 
```

Definition (in one source file): Allocates storage for the variable.
```c
int my_variable; 
```

### 2. Combined Declaration and Definition (with Optional Initialization)
This is the most frequent way to handle variables. The definition happens when you specify the data type and name, which also allocates memory. 
Declaration/Definition without initialization: The variable gets a "garbage" value (whatever data was previously in that memory location).
```c
int count; // Declares and defines 'count' with a garbage value
```

Declaration/Definition with initialization: The variable is assigned a specific initial value when defined. This is considered a best practice to prevent unexpected behavior.
```c
int count = 0; // Declares, defines, and initializes 'count' to 0
```

### 3. Multiple Variables in a Single Statement
You can declare and define multiple variables of the same data type in a single line, separated by commas. 
```c
int length, width, depth; // Declares three int variables
float salary = 45000.50, wages = 20000.0; // Initializes two float variables
```

### 4. Using Storage Class Specifiers
Storage class specifiers like static, auto, and register define the scope and lifetime of a variable. 
static: Retains its value between function calls and is initialized only once.
```c
static int call_count = 0; 
```

const: Declares a variable whose value cannot be changed after initialization, effectively creating a constant.
```c
const float PI = 3.14159;
```
 

