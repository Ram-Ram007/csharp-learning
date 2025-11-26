# 7-Day .NET Basics Study Plan

## Day 1: Introduction to .NET and C# Fundamentals

### Topics to Cover
- What is .NET? (.NET Framework vs .NET Core vs .NET 5+)
- .NET Architecture Overview
- Setting up Visual Studio or VS Code
- Your first C# program
- Variables, data types, and operators
- Console input/output

### Detailed Explanations

**What is .NET?**
.NET is a free, open-source developer platform for building many types of applications. It includes a runtime (CLR - Common Language Runtime) that manages code execution, a large class library (BCL - Base Class Library), and support for multiple programming languages with C# being the most popular.

**Key Components:**
- **CLR (Common Language Runtime)**: Manages memory, handles exceptions, provides security, and executes code
- **BCL (Base Class Library)**: Pre-written code for common programming tasks
- **Languages**: C#, F#, Visual Basic

**C# Basics:**
C# is a modern, object-oriented programming language. It's strongly typed, which means variables must have a specific type.

### Code Examples

```csharp
// Example 1: Hello World
using System;

namespace Day1Examples
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello, .NET World!");
            Console.ReadLine();
        }
    }
}

// Example 2: Variables and Data Types
int age = 25;                    // Integer
double price = 19.99;            // Decimal number
string name = "John";            // Text
bool isStudent = true;           // Boolean
char grade = 'A';                // Single character

// Example 3: User Input
Console.Write("Enter your name: ");
string userName = Console.ReadLine();
Console.WriteLine($"Welcome, {userName}!");

// Example 4: Basic Operations
int a = 10, b = 5;
Console.WriteLine($"Sum: {a + b}");
Console.WriteLine($"Difference: {a - b}");
Console.WriteLine($"Product: {a * b}");
Console.WriteLine($"Quotient: {a / b}");
```

### Practice Tasks
1. Create a program that asks for your name and age, then displays "Hello [name], you are [age] years old"
2. Write a calculator that adds two numbers entered by the user
3. Create a program that converts Celsius to Fahrenheit (Formula: F = C * 9/5 + 32)

### Daily Quiz
1. What does CLR stand for?
2. Name three data types in C#
3. What method is used to display output to the console?
4. How do you read user input from the console?
5. What symbol is used for string interpolation in C#?

### Coding Exercise
**Temperature Converter**: Create a program that:
- Asks if the user wants to convert from Celsius or Fahrenheit
- Takes the temperature input
- Converts and displays the result with appropriate labels

### Revision Points
- .NET is a platform, C# is a language
- CLR manages code execution
- Variables must be declared with a type
- `Console.WriteLine()` for output, `Console.ReadLine()` for input
- Use `$"{variable}"` for string interpolation

---

## Day 2: Control Flow and Methods

### Topics to Cover
- Conditional statements (if, else, switch)
- Loops (for, while, do-while, foreach)
- Methods/Functions
- Method parameters and return values
- Scope and lifetime of variables

### Detailed Explanations

**Control Flow:**
Control flow statements let you direct the execution of your program based on conditions or repeat actions multiple times.

**Methods:**
Methods are reusable blocks of code that perform specific tasks. They help organize code and avoid repetition.

### Code Examples

```csharp
// Example 1: If-Else Statement
int score = 85;

if (score >= 90)
{
    Console.WriteLine("Grade: A");
}
else if (score >= 80)
{
    Console.WriteLine("Grade: B");
}
else if (score >= 70)
{
    Console.WriteLine("Grade: C");
}
else
{
    Console.WriteLine("Grade: F");
}

// Example 2: Switch Statement
string day = "Monday";

switch (day)
{
    case "Monday":
    case "Tuesday":
    case "Wednesday":
    case "Thursday":
    case "Friday":
        Console.WriteLine("It's a weekday");
        break;
    case "Saturday":
    case "Sunday":
        Console.WriteLine("It's the weekend!");
        break;
    default:
        Console.WriteLine("Invalid day");
        break;
}

// Example 3: For Loop
for (int i = 1; i <= 5; i++)
{
    Console.WriteLine($"Iteration {i}");
}

// Example 4: While Loop
int count = 0;
while (count < 3)
{
    Console.WriteLine($"Count: {count}");
    count++;
}

// Example 5: Methods
static int Add(int num1, int num2)
{
    return num1 + num2;
}

static void Greet(string name)
{
    Console.WriteLine($"Hello, {name}!");
}

// Using methods
int result = Add(5, 3);
Console.WriteLine($"Result: {result}");
Greet("Alice");

// Example 6: Method with Default Parameters
static void PrintMessage(string message, int times = 1)
{
    for (int i = 0; i < times; i++)
    {
        Console.WriteLine(message);
    }
}

PrintMessage("Hello");        // Prints once
PrintMessage("Hi", 3);        // Prints 3 times
```

### Practice Tasks
1. Write a program that checks if a number is positive, negative, or zero
2. Create a multiplication table (1-10) using a for loop
3. Write a method that checks if a number is even or odd and returns a boolean
4. Create a method that finds the maximum of three numbers

### Daily Quiz
1. What's the difference between a while loop and a do-while loop?
2. When should you use a switch statement instead of if-else?
3. What keyword is used to return a value from a method?
4. Can a method have multiple parameters? Give an example.
5. What is method overloading?

### Coding Exercise
**Simple Menu System**: Create a console program with a menu that:
- Displays options: 1) Add two numbers, 2) Multiply two numbers, 3) Check if number is prime, 4) Exit
- Uses a switch statement to handle user choice
- Each operation should be in its own method
- Loops until the user chooses to exit

### Revision Points
- Use `if-else` for conditional logic, `switch` for multiple specific values
- Loops repeat code: `for` when you know iterations, `while` when condition-based
- Methods should have a single, clear purpose
- Methods can return values or be void (return nothing)
- Parameters pass data into methods

---

## Day 3: Object-Oriented Programming (OOP) - Part 1

### Topics to Cover
- What is OOP?
- Classes and Objects
- Properties and Fields
- Constructors
- Access Modifiers (public, private, protected)
- Encapsulation

### Detailed Explanations

**Object-Oriented Programming:**
OOP is a programming paradigm based on the concept of "objects" which contain data (fields/properties) and code (methods). It helps organize complex programs into manageable, reusable pieces.

**Four Pillars of OOP:**
1. **Encapsulation**: Bundling data and methods, hiding internal details
2. **Inheritance**: Creating new classes from existing ones
3. **Polymorphism**: Objects taking multiple forms
4. **Abstraction**: Hiding complex implementation details

**Classes vs Objects:**
- A **class** is a blueprint or template
- An **object** is an instance of a class (an actual thing created from the blueprint)

### Code Examples

```csharp
// Example 1: Simple Class
public class Person
{
    // Fields (private by convention)
    private string name;
    private int age;
    
    // Properties (public access to private fields)
    public string Name
    {
        get { return name; }
        set { name = value; }
    }
    
    public int Age
    {
        get { return age; }
        set 
        { 
            if (value >= 0)
                age = value;
        }
    }
    
    // Auto-implemented properties (shorthand)
    public string Email { get; set; }
    
    // Constructor
    public Person(string name, int age)
    {
        this.name = name;
        this.age = age;
    }
    
    // Method
    public void Introduce()
    {
        Console.WriteLine($"Hi, I'm {name} and I'm {age} years old.");
    }
}

// Using the class
Person person1 = new Person("Alice", 30);
person1.Email = "alice@example.com";
person1.Introduce();

// Example 2: Bank Account Class
public class BankAccount
{
    private decimal balance;
    public string AccountNumber { get; private set; }
    public string Owner { get; set; }
    
    public BankAccount(string accountNumber, string owner)
    {
        AccountNumber = accountNumber;
        Owner = owner;
        balance = 0;
    }
    
    public void Deposit(decimal amount)
    {
        if (amount > 0)
        {
            balance += amount;
            Console.WriteLine($"Deposited {amount:C}. New balance: {balance:C}");
        }
    }
    
    public bool Withdraw(decimal amount)
    {
        if (amount > 0 && amount <= balance)
        {
            balance -= amount;
            Console.WriteLine($"Withdrawn {amount:C}. New balance: {balance:C}");
            return true;
        }
        Console.WriteLine("Insufficient funds or invalid amount");
        return false;
    }
    
    public decimal GetBalance()
    {
        return balance;
    }
}

// Using the BankAccount
BankAccount account = new BankAccount("12345", "John Doe");
account.Deposit(1000);
account.Withdraw(250);
Console.WriteLine($"Current balance: {account.GetBalance():C}");

// Example 3: Student Class with Multiple Constructors
public class Student
{
    public string Name { get; set; }
    public int StudentId { get; set; }
    public string Major { get; set; }
    
    // Default constructor
    public Student()
    {
        Name = "Unknown";
        StudentId = 0;
        Major = "Undeclared";
    }
    
    // Parameterized constructor
    public Student(string name, int id, string major)
    {
        Name = name;
        StudentId = id;
        Major = major;
    }
    
    public void DisplayInfo()
    {
        Console.WriteLine($"Name: {Name}, ID: {StudentId}, Major: {Major}");
    }
}
```

### Practice Tasks
1. Create a `Book` class with properties: Title, Author, ISBN, Pages
2. Create a `Rectangle` class with width and height properties, and methods to calculate area and perimeter
3. Create a `Product` class with name, price, and quantity. Add methods to calculate total value
4. Implement a `Car` class with make, model, year, and a method to display information

### Daily Quiz
1. What is the difference between a class and an object?
2. What is encapsulation and why is it important?
3. What is the purpose of a constructor?
4. Name three access modifiers and their visibility
5. What's the difference between a field and a property?

### Coding Exercise
**Library Book Management**: Create a `Book` class and a simple library system:
- Book properties: Title, Author, ISBN, IsCheckedOut
- Methods: CheckOut(), Return(), DisplayInfo()
- Create multiple book objects
- Implement a simple menu to check out and return books

### Revision Points
- Classes are blueprints, objects are instances
- Use properties to control access to fields
- Constructors initialize objects
- `private` members are only accessible within the class
- `public` members are accessible from anywhere
- Encapsulation protects data integrity

---

## Day 4: OOP - Part 2 (Inheritance and Polymorphism)

### Topics to Cover
- Inheritance (base and derived classes)
- The `base` keyword
- Method overriding
- Virtual and override keywords
- Abstract classes and methods
- Polymorphism

### Detailed Explanations

**Inheritance:**
Inheritance allows a class to inherit properties and methods from another class. The parent class is called the base class, and the child class is called the derived class.

**Polymorphism:**
Polymorphism allows objects of different classes to be treated as objects of a common base class. It enables you to write more flexible and maintainable code.

### Code Examples

```csharp
// Example 1: Basic Inheritance
public class Animal
{
    public string Name { get; set; }
    public int Age { get; set; }
    
    public Animal(string name, int age)
    {
        Name = name;
        Age = age;
    }
    
    public virtual void MakeSound()
    {
        Console.WriteLine("Some generic animal sound");
    }
    
    public void Sleep()
    {
        Console.WriteLine($"{Name} is sleeping");
    }
}

public class Dog : Animal
{
    public string Breed { get; set; }
    
    public Dog(string name, int age, string breed) : base(name, age)
    {
        Breed = breed;
    }
    
    public override void MakeSound()
    {
        Console.WriteLine($"{Name} says: Woof! Woof!");
    }
    
    public void Fetch()
    {
        Console.WriteLine($"{Name} is fetching the ball");
    }
}

public class Cat : Animal
{
    public Cat(string name, int age) : base(name, age)
    {
    }
    
    public override void MakeSound()
    {
        Console.WriteLine($"{Name} says: Meow!");
    }
}

// Using inheritance
Dog dog = new Dog("Buddy", 3, "Golden Retriever");
dog.MakeSound();  // Woof! Woof!
dog.Sleep();      // Inherited method
dog.Fetch();      // Dog-specific method

Cat cat = new Cat("Whiskers", 2);
cat.MakeSound();  // Meow!

// Example 2: Polymorphism
Animal[] animals = new Animal[]
{
    new Dog("Max", 5, "Labrador"),
    new Cat("Luna", 3),
    new Dog("Charlie", 2, "Beagle")
};

foreach (Animal animal in animals)
{
    animal.MakeSound();  // Calls the appropriate method for each type
}

// Example 3: Abstract Classes
public abstract class Shape
{
    public string Name { get; set; }
    
    public Shape(string name)
    {
        Name = name;
    }
    
    // Abstract method (must be implemented by derived classes)
    public abstract double CalculateArea();
    
    // Concrete method (can be used by all derived classes)
    public void DisplayInfo()
    {
        Console.WriteLine($"Shape: {Name}, Area: {CalculateArea():F2}");
    }
}

public class Circle : Shape
{
    public double Radius { get; set; }
    
    public Circle(double radius) : base("Circle")
    {
        Radius = radius;
    }
    
    public override double CalculateArea()
    {
        return Math.PI * Radius * Radius;
    }
}

public class Rectangle : Shape
{
    public double Width { get; set; }
    public double Height { get; set; }
    
    public Rectangle(double width, double height) : base("Rectangle")
    {
        Width = width;
        Height = height;
    }
    
    public override double CalculateArea()
    {
        return Width * Height;
    }
}

// Using abstract classes
Shape circle = new Circle(5);
Shape rectangle = new Rectangle(4, 6);

circle.DisplayInfo();
rectangle.DisplayInfo();

// Example 4: Employee Hierarchy
public class Employee
{
    public string Name { get; set; }
    public int EmployeeId { get; set; }
    protected decimal BaseSalary { get; set; }
    
    public Employee(string name, int id, decimal salary)
    {
        Name = name;
        EmployeeId = id;
        BaseSalary = salary;
    }
    
    public virtual decimal CalculateSalary()
    {
        return BaseSalary;
    }
    
    public virtual void DisplayInfo()
    {
        Console.WriteLine($"Employee: {Name}, ID: {EmployeeId}, Salary: {CalculateSalary():C}");
    }
}

public class Manager : Employee
{
    public decimal Bonus { get; set; }
    
    public Manager(string name, int id, decimal salary, decimal bonus) 
        : base(name, id, salary)
    {
        Bonus = bonus;
    }
    
    public override decimal CalculateSalary()
    {
        return BaseSalary + Bonus;
    }
    
    public override void DisplayInfo()
    {
        Console.WriteLine($"Manager: {Name}, ID: {EmployeeId}, Total Salary: {CalculateSalary():C}");
    }
}

public class Developer : Employee
{
    public string ProgrammingLanguage { get; set; }
    
    public Developer(string name, int id, decimal salary, string language) 
        : base(name, id, salary)
    {
        ProgrammingLanguage = language;
    }
    
    public override void DisplayInfo()
    {
        base.DisplayInfo();
        Console.WriteLine($"  Specialization: {ProgrammingLanguage}");
    }
}
```

### Practice Tasks
1. Create a `Vehicle` base class and derive `Car` and `Motorcycle` classes with specific properties
2. Create a `BankAccount` base class and derive `SavingsAccount` and `CheckingAccount` with different interest calculation methods
3. Build a shape hierarchy with `Triangle`, `Square`, and implement area calculations
4. Create an abstract `Payment` class and derive `CreditCardPayment` and `CashPayment` classes

### Daily Quiz
1. What keyword is used to inherit from a base class?
2. What's the difference between `virtual` and `override`?
3. Can you instantiate an abstract class? Why or why not?
4. What is polymorphism and give a real-world example?
5. What does the `base` keyword do?

### Coding Exercise
**Zoo Management System**: Create an inheritance hierarchy:
- Abstract base class `Animal` with properties and an abstract method `Speak()`
- Derived classes: `Lion`, `Elephant`, `Monkey` with unique behaviors
- Create a list of animals and make each one speak
- Add a `Feed()` method that shows different feeding behaviors

### Revision Points
- Use `:` to inherit from a base class
- `virtual` methods can be overridden in derived classes
- Use `override` to provide a new implementation
- Abstract classes cannot be instantiated
- Abstract methods must be implemented by derived classes
- Polymorphism allows treating derived objects as base type
- Use `base` to call base class constructors or methods

---

## Day 5: Exception Handling and Collections

### Topics to Cover
- Exceptions and error handling
- Try-catch-finally blocks
- Common exception types
- Throwing exceptions
- Arrays
- Collections: List, Dictionary, Queue, Stack
- LINQ basics

### Detailed Explanations

**Exception Handling:**
Exceptions are errors that occur during program execution. Proper exception handling prevents your program from crashing and provides meaningful error messages.

**Collections:**
Collections are data structures that store multiple items. Unlike arrays, most collections can grow dynamically.

### Code Examples

```csharp
// Example 1: Basic Exception Handling
try
{
    Console.Write("Enter a number: ");
    int number = int.Parse(Console.ReadLine());
    int result = 100 / number;
    Console.WriteLine($"Result: {result}");
}
catch (DivideByZeroException)
{
    Console.WriteLine("Error: Cannot divide by zero!");
}
catch (FormatException)
{
    Console.WriteLine("Error: Please enter a valid number!");
}
catch (Exception ex)
{
    Console.WriteLine($"An unexpected error occurred: {ex.Message}");
}
finally
{
    Console.WriteLine("Execution completed.");
}

// Example 2: Throwing Exceptions
public class BankAccount
{
    private decimal balance;
    
    public void Withdraw(decimal amount)
    {
        if (amount < 0)
        {
            throw new ArgumentException("Amount cannot be negative");
        }
        
        if (amount > balance)
        {
            throw new InvalidOperationException("Insufficient funds");
        }
        
        balance -= amount;
    }
}

// Using the method with exception handling
try
{
    BankAccount account = new BankAccount();
    account.Withdraw(-100);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid argument: {ex.Message}");
}
catch (InvalidOperationException ex)
{
    Console.WriteLine($"Operation failed: {ex.Message}");
}

// Example 3: Arrays
int[] numbers = new int[5] { 1, 2, 3, 4, 5 };
string[] names = { "Alice", "Bob", "Charlie" };

// Accessing elements
Console.WriteLine(numbers[0]);  // 1

// Iterating through array
foreach (int num in numbers)
{
    Console.WriteLine(num);
}

// Multi-dimensional array
int[,] matrix = new int[2, 3]
{
    { 1, 2, 3 },
    { 4, 5, 6 }
};

Console.WriteLine(matrix[1, 2]);  // 6

// Example 4: List<T>
using System.Collections.Generic;

List<string> fruits = new List<string>();

// Adding items
fruits.Add("Apple");
fruits.Add("Banana");
fruits.Add("Cherry");

// Accessing items
Console.WriteLine(fruits[0]);  // Apple

// Removing items
fruits.Remove("Banana");

// Checking if exists
if (fruits.Contains("Apple"))
{
    Console.WriteLine("We have apples!");
}

// Count
Console.WriteLine($"Total fruits: {fruits.Count}");

// Iterating
foreach (string fruit in fruits)
{
    Console.WriteLine(fruit);
}

// Example 5: Dictionary<TKey, TValue>
Dictionary<string, int> ages = new Dictionary<string, int>();

// Adding items
ages.Add("Alice", 30);
ages.Add("Bob", 25);
ages["Charlie"] = 35;  // Alternative way

// Accessing items
Console.WriteLine($"Alice is {ages["Alice"]} years old");

// Checking if key exists
if (ages.ContainsKey("Bob"))
{
    Console.WriteLine($"Bob's age: {ages["Bob"]}");
}

// Iterating
foreach (KeyValuePair<string, int> kvp in ages)
{
    Console.WriteLine($"{kvp.Key}: {kvp.Value}");
}

// Removing items
ages.Remove("Bob");

// Example 6: Stack and Queue
Stack<int> stack = new Stack<int>();
stack.Push(1);
stack.Push(2);
stack.Push(3);
Console.WriteLine(stack.Pop());  // 3 (LIFO - Last In First Out)

Queue<string> queue = new Queue<string>();
queue.Enqueue("First");
queue.Enqueue("Second");
queue.Enqueue("Third");
Console.WriteLine(queue.Dequeue());  // First (FIFO - First In First Out)

// Example 7: Basic LINQ
using System.Linq;

List<int> numbers2 = new List<int> { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

// Find even numbers
var evenNumbers = numbers2.Where(n => n % 2 == 0).ToList();

// Find numbers greater than 5
var largeNumbers = numbers2.Where(n => n > 5).ToList();

// Get first element
int first = numbers2.First();

// Get sum
int sum = numbers2.Sum();

// Get average
double average = numbers2.Average();

// Order by descending
var descending = numbers2.OrderByDescending(n => n).ToList();

Console.WriteLine($"Even numbers: {string.Join(", ", evenNumbers)}");
Console.WriteLine($"Sum: {sum}, Average: {average}");
```

### Practice Tasks
1. Create a program that handles user input for age with proper exception handling
2. Build a simple contact list using a Dictionary<string, string> for name and phone number
3. Create a to-do list application using List<string> with add, remove, and display functions
4. Implement a number guessing game with exception handling for invalid input

### Daily Quiz
1. What's the purpose of the finally block?
2. When should you throw an exception versus handling it?
3. What's the difference between a List and an array?
4. How does a Dictionary differ from a List?
5. What does LINQ stand for and what is it used for?

### Coding Exercise
**Student Grade Manager**: Create a program that:
- Uses a Dictionary to store student names and their grades (List<int>)
- Implements exception handling for invalid grades (must be 0-100)
- Calculates average grade for each student using LINQ
- Displays students with average above 80
- Allows adding, removing, and displaying students

### Revision Points
- Use try-catch to handle exceptions gracefully
- finally block always executes, good for cleanup
- List<T> is a dynamic array that can grow
- Dictionary<TKey, TValue> stores key-value pairs
- Stack is LIFO (Last In, First Out)
- Queue is FIFO (First In, First Out)
- LINQ provides query capabilities for collections
- Always validate user input and handle exceptions

---

## Day 6: .NET Architecture Deep Dive

### Topics to Cover
- CLR (Common Language Runtime) in detail
- CTS (Common Type System)
- CLS (Common Language Specification)
- Assemblies (DLL and EXE)
- GAC (Global Assembly Cache)
- Namespaces
- Garbage Collection
- Value Types vs Reference Types

### Detailed Explanations

**Common Language Runtime (CLR):**
The CLR is the execution engine of .NET. It provides services like memory management, type safety, exception handling, garbage collection, and thread management.

**Key CLR Components:**
- **JIT Compiler**: Converts IL (Intermediate Language) code to native machine code
- **Garbage Collector**: Automatically manages memory
- **Class Loader**: Loads classes when needed
- **Security Engine**: Enforces code access security

**Compilation Process:**
1. C# source code → Compiler → IL (MSIL/CIL) code + Metadata
2. IL code → JIT Compiler → Native machine code
3. Native code executes on the CPU

**Assemblies:**
An assembly is a compiled code library used for deployment, versioning, and security. Assemblies can be:
- **Private**: Used only by a single application
- **Shared**: Stored in GAC, used by multiple applications

### Code Examples

```csharp
// Example 1: Value Types vs Reference Types

// Value Types (stored on stack)
int x = 10;
int y = x;  // Copy of value
y = 20;
Console.WriteLine($"x = {x}, y = {y}");  // x = 10, y = 20

struct Point
{
    public int X;
    public int Y;
}

Point p1 = new Point { X = 5, Y = 10 };
Point p2 = p1;  // Copy of entire struct
p2.X = 20;
Console.WriteLine($"p1.X = {p1.X}, p2.X = {p2.X}");  // p1.X = 5, p2.X = 20

// Reference Types (stored on heap)
class Person
{
    public string Name { get; set; }
}

Person person1 = new Person { Name = "Alice" };
Person person2 = person1;  // Copy of reference (both point to same object)
person2.Name = "Bob";
Console.WriteLine($"person1: {person1.Name}, person2: {person2.Name}");  
// Both show "Bob"

// Example 2: Namespaces
namespace MyApplication.Models
{
    public class User
    {
        public string Username { get; set; }
    }
}

namespace MyApplication.Services
{
    using MyApplication.Models;
    
    public class UserService
    {
        public User GetUser(string username)
        {
            return new User { Username = username };
        }
    }
}

// Using namespaces
using MyApplication.Services;
UserService service = new UserService();
var user = service.GetUser("john");

// Example 3: Understanding Garbage Collection
public class ResourceDemo : IDisposable
{
    private bool disposed = false;
    
    public ResourceDemo()
    {
        Console.WriteLine("Resource allocated");
    }
    
    public void DoWork()
    {
        if (disposed)
            throw new ObjectDisposedException("ResourceDemo");
        
        Console.WriteLine("Working...");
    }
    
    public void Dispose()
    {
        if (!disposed)
        {
            Console.WriteLine("Resource released");
            disposed = true;
            GC.SuppressFinalize(this);
        }
    }
    
    ~ResourceDemo()
    {
        Dispose();
    }
}

// Using the resource
using (ResourceDemo resource = new ResourceDemo())
{
    resource.DoWork();
}  // Dispose called automatically

// Example 4: Boxing and Unboxing
// Boxing: Converting value type to reference type
int num = 123;
object obj = num;  // Boxing

// Unboxing: Converting reference type to value type
int num2 = (int)obj;  // Unboxing

// Performance consideration
List<int> numbers = new List<int>();  // Good: no boxing
List<object> objects = new List<object>();
objects.Add(123);  // Bad: causes boxing

// Example 5: Working with Assembly Information
using System.Reflection;

// Get current assembly
Assembly currentAssembly = Assembly.GetExecutingAssembly();
Console.WriteLine($"Assembly Name: {currentAssembly.FullName}");

// Get all types in assembly
Type[] types = currentAssembly.GetTypes();
foreach (Type type in types)
{
    Console.WriteLine($"Type: {type.Name}");
}

// Example 6: Strong vs Weak References
class LargeObject
{
    public byte[] Data { get; set; } = new byte[1000000];
}

// Strong reference (prevents garbage collection)
LargeObject obj1 = new LargeObject();

// Weak reference (allows garbage collection)
WeakReference weakRef = new WeakReference(new LargeObject());

GC.Collect();  // Force garbage collection

if (weakRef.IsAlive)
{
    Console.WriteLine("Object still alive");
}
else
{
    Console.WriteLine("Object was collected");
}
```

### Conceptual Examples

```
CLR Architecture:
┌─────────────────────────────────────┐
│         Your C# Code                │
└─────────────────┬───────────────────┘
                  │
                  ▼
┌─────────────────────────────────────┐
│    C# Compiler (csc.exe)            │
│    Converts to IL + Metadata        │
└─────────────────┬───────────────────┘
                  │
                  ▼
┌─────────────────────────────────────┐
│      Assembly (.dll or .exe)        │
│      Contains IL Code               │
└─────────────────┬───────────────────┘
                  │
                  ▼
┌─────────────────────────────────────┐
│   CLR (Common Language Runtime)     │
│   ┌───────────────────────────┐     │
│   │  JIT Compiler             │     │
│   │  Memory Manager           │     │
│   │  Garbage Collector        │     │
│   │  Security Manager         │     │
│   └───────────────────────────┘     │
└─────────────────┬───────────────────┘
                  │
                  ▼
┌─────────────────────────────────────┐
│    Native Machine Code              │
│    Executes on CPU                  │
└─────────────────────────────────────┘

Memory Layout:
┌────────────────────┐
│      Stack         │  ← Value types, method calls
│  (Fast, Limited)   │     References to heap objects
├────────────────────┤
│                    │
│       Heap         │  ← Reference types (objects)
│  (Slower, Larger)  │     Managed by GC
│                    │
└────────────────────┘
```

### Practice Tasks
1. Create a value type (struct) and reference type (class) with similar properties and observe the differences
2. Implement IDisposable pattern in a custom class
3. Use reflection to list all methods in a class
4. Create nested namespaces and practice using statements

### Daily Quiz
1. What are the main responsibilities of the CLR?
2. What's the difference between value types and reference types?
3. Where are value types stored? Where are reference types stored?
4. What is an assembly?
5. What is the purpose of the GAC?
6. What is boxing and unboxing?
7. How does garbage collection work in .NET?

### Coding Exercise
**Memory Management Explorer**: Create a program that:
- Demonstrates value type vs reference type behavior
- Shows boxing and unboxing with performance timing
- Implements IDisposable pattern for resource cleanup
- Uses weak references to observe garbage collection

### Revision Points
- CLR manages code execution and provides services
- IL is the intermediate code that CLR executes
- Value types: stored on stack, contain actual data
- Reference types: stored on heap, variables hold references
- Assemblies are building blocks of .NET applications
- Namespaces organize code logically
- GC automatically manages heap memory
- Use `using` statement or IDisposable for resource cleanup
- Boxing has performance cost, avoid when possible

---

## Day 7: Building a Complete Console Application

### Topics to Cover
- File I/O operations
- Working with JSON
- Design patterns (basic)
- Putting it all together
- Best practices
- Debugging basics

### Detailed Explanations

**File Operations:**
.NET provides comprehensive classes for file and directory operations in the System.IO namespace.

**JSON in .NET:**
System.Text.Json provides high-performance JSON serialization and deserialization.

**Best Practices:**
- Use meaningful names
- Keep methods small and focused
- Handle exceptions appropriately
- Use proper access modifiers
- Comment complex logic
- Follow naming conventions (PascalCase for classes/methods, camelCase for variables)

### Code Examples

```csharp
// Example 1: File I/O Operations
using System.IO;

// Writing to a file
string[] lines = { "Line 1", "Line 2", "Line 3" };
File.WriteAllLines("output.txt", lines);

// Reading from a file
string content = File.ReadAllText("output.txt");
Console.WriteLine(content);

string[] readLines = File.ReadAllLines("output.txt");
foreach (string line in readLines)
{
    Console.WriteLine(line);
}

// Appending to a file
File.AppendAllText("output.txt", "\nNew line");

// Check if file exists
if (File.Exists("output.txt"))
{
    Console.WriteLine("File exists!");
}

// Directory operations
Directory.CreateDirectory("MyFolder");
string[] files = Directory.GetFiles(".", "*.txt");
foreach (string file in files)
{
    Console.WriteLine(file);
}

// Example 2: Working with JSON
using System.Text.Json;

public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
    public string Email { get; set; }
}

// Serializing to JSON
Person person = new Person 
{ 
    Name = "John Doe", 
    Age = 30, 
    Email = "john@example.com" 
};

string jsonString = JsonSerializer.Serialize(person);
Console.WriteLine(jsonString);

// Writing JSON to file
File.WriteAllText("person.json", jsonString);

// Deserializing from JSON
string jsonFromFile = File.ReadAllText("person.json");
Person deserializedPerson = JsonSerializer.Deserialize<Person>(jsonFromFile);
Console.WriteLine($"{deserializedPerson.Name}, {deserializedPerson.Age}");

// Example 3: Complete Task Manager Application
public class Task
{
    public int Id { get; set; }
    public string Title { get; set; }
    public string Description { get; set; }
    public bool IsCompleted { get; set; }
    public DateTime CreatedDate { get; set; }
    
    public Task()
    {
        CreatedDate = DateTime.Now;
    }
}

public class TaskManager
{
    private List<Task> tasks;
    private const string FileName = "tasks.json";
    private int nextId = 1;
    
    public TaskManager()
    {
        LoadTasks();
    }
    
    private void LoadTasks()
    {
        if (File.Exists(FileName))
        {
            string json = File.ReadAllText(FileName);
            tasks = JsonSerializer.Deserialize<List<Task>>(json) ?? new List<Task>();
            nextId = tasks.Count > 0 ? tasks.Max(t => t.Id) + 1 : 1;
        }
        else
        {
            tasks = new List<Task>();
        }
    }
    
    private void SaveTasks()
    {
        string json = JsonSerializer.Serialize(tasks, new JsonSerializerOptions 
        { 
            WriteIndented = true 
        });
        File.WriteAllText(FileName, json);
    }
    
    public void AddTask(string title, string description)
    {
        var task = new Task
        {
            Id = nextId++,
            Title = title,
            Description = description,
            IsCompleted = false
        };
        
        tasks.Add(task);
        SaveTasks();
        Console.WriteLine($"Task added successfully! ID: {task.Id}");
    }
    
    public void ListTasks()
    {
        if (tasks.Count == 0)
        {
            Console.WriteLine("No tasks found.");
            return;
        }
        
        Console.WriteLine("\n=== Task List ===");
        foreach (var task in tasks)
        {
            string status = task.IsCompleted ? "[✓]" : "[ ]";
            Console.WriteLine($"{status} ID: {task.Id} - {task.Title}");
            Console.WriteLine($"    {task.Description}");
            Console.WriteLine($"    Created: {task.CreatedDate:yyyy-MM-dd}");
            Console.WriteLine();
        }
    }
    
    public void CompleteTask(int id)
    {
        var task = tasks.FirstOrDefault(t => t.Id == id);
        if (task != null)
        {
            task.IsCompleted = true;
            SaveTasks();
            Console.WriteLine($"Task {id} marked as completed!");
        }
        else
        {
            Console.WriteLine($"Task with ID {id} not found.");
        }
    }
    
    public void DeleteTask(int id)
    {
        var task = tasks.FirstOrDefault(t => t.Id == id);
        if (task != null)
        {
            tasks.Remove(task);
            SaveTasks();
            Console.WriteLine($"Task {id} deleted!");
        }
        else
        {
            Console.WriteLine($"Task with ID {id} not found.");
        }
    }
}

// Main Program
class Program
{
    static void Main(string[] args)
    {
        TaskManager taskManager = new TaskManager();
        bool exit = false;
        
        Console.WriteLine("=== Task Manager Application ===\n");
        
        while (!exit)
        {
            Console.WriteLine("\n1. Add Task");
            Console.WriteLine("2. List Tasks");
            Console.WriteLine("3. Complete Task");
            Console.WriteLine("4. Delete Task");
            Console.WriteLine("5. Exit");
            Console.Write("\nSelect an option: ");
            
            string choice = Console.ReadLine();
            Console.WriteLine();
            
            try
            {
                switch (choice)
                {
                    case "1":
                        Console.Write("Enter task title: ");
                        string title = Console.ReadLine();
                        Console.Write("Enter task description: ");
                        string description = Console.ReadLine();
                        taskManager.AddTask(title, description);
                        break;
                        
                    case "2":
                        taskManager.ListTasks();
                        break;
                        
                    case "3":
                        Console.Write("Enter task ID to complete: ");
                        int completeId = int.Parse(Console.ReadLine());
                        taskManager.CompleteTask(completeId);
                        break;
                        
                    case "4":
                        Console.Write("Enter task ID to delete: ");
                        int deleteId = int.Parse(Console.ReadLine());
                        taskManager.DeleteTask(deleteId);
                        break;
                        
                    case "5":
                        exit = true;
                        Console.WriteLine("Goodbye!");
                        break;
                        
                    default:
                        Console.WriteLine("Invalid option. Please try again.");
                        break;
                }
            }
            catch (FormatException)
            {
                Console.WriteLine("Error: Please enter a valid number.");
            }
            catch (Exception ex)
            {
                Console.WriteLine($"An error occurred: {ex.Message}");
            }
        }
    }
}

// Example 4: Singleton Pattern
public sealed class Logger
{
    private static Logger instance = null;
    private static readonly object lockObj = new object();
    private string logFilePath;
    
    private Logger()
    {
        logFilePath = "app.log";
    }
    
    public static Logger Instance
    {
        get
        {
            if (instance == null)
            {
                lock (lockObj)
                {
                    if (instance == null)
                    {
                        instance = new Logger();
                    }
                }
            }
            return instance;
        }
    }
    
    public void Log(string message)
    {
        string logEntry = $"[{DateTime.Now:yyyy-MM-dd HH:mm:ss}] {message}";
        Console.WriteLine(logEntry);
        File.AppendAllText(logFilePath, logEntry + Environment.NewLine);
    }
}

// Usage
Logger.Instance.Log("Application started");
Logger.Instance.Log("Processing data");
```

### Practice Tasks
1. Create a simple contact book that saves to JSON
2. Build a note-taking application with file storage
3. Implement a simple logging system
4. Create a product inventory system with CRUD operations

### Daily Quiz
1. What namespace is used for file operations?
2. How do you serialize an object to JSON?
3. What's the difference between File.WriteAllText and File.AppendAllText?
4. Why is the Singleton pattern useful?
5. What's the purpose of the using statement with file streams?

### Coding Exercise
**Personal Budget Tracker**: Build a complete application that:
- Stores expenses and income as JSON
- Categories for transactions
- Shows total balance
- Filters transactions by date or category
- Exports monthly reports to text file
- Uses proper OOP principles and exception handling
- Implements at least one design pattern

### Revision Points
- Use System.IO for file operations
- System.Text.Json for JSON serialization
- Always handle file exceptions (FileNotFoundException, IOException)
- Close streams and files properly (use `using` statement)
- Design patterns solve common problems
- Keep concerns separated (data access, business logic, UI)
- Test edge cases and error conditions

---

## Final Project Ideas

Now that you've completed the 7-day study plan, here are comprehensive project ideas to practice:

### 1. Library Management System
**Features:**
- Add, remove, search books
- Member registration
- Check-out and return books
- Due date tracking
- Late fee calculation
- Data persistence with JSON

**Concepts Used:** OOP, Collections, File I/O, Exception Handling

### 2. Student Grade Management
**Features:**
- Add students and courses
- Record grades for assignments/exams
- Calculate GPA
- Generate report cards
- Export to file

**Concepts Used:** Inheritance, Collections, LINQ, File I/O

### 3. Banking Application
**Features:**
- Create accounts
- Deposit and withdrawal
- Transfer between accounts
- Transaction history
- Interest calculation
- Account types (Savings, Checking)

**Concepts Used:** OOP, Encapsulation, Exception Handling, Collections

### 4. Inventory Management
**Features:**
- Product CRUD operations
- Stock level tracking
- Low stock alerts
- Sales recording
- Reports generation

**Concepts Used:** Full OOP, File I/O, LINQ, Collections

### 5. Simple Game (Text-Based Adventure)
**Features:**
- Player character with stats
- Room navigation
- Inventory system
- Combat system
- Save/load game state

**Concepts Used:** OOP, Collections, File I/O, Game loop

---

## Additional Learning Resources

### Official Documentation
- Microsoft .NET Documentation: https://docs.microsoft.com/dotnet
- C# Programming Guide: https://docs.microsoft.com/dotnet/csharp

### Practice Platforms
- HackerRank
- LeetCode
- Codewars
- Exercism.io

### Next Steps
After completing this 7-day plan:
1. Learn about ASP.NET Core for web development
2. Explore Entity Framework Core for database operations
3. Study unit testing with xUnit or NUnit
4. Learn about async/await and parallel programming
5. Explore design patterns in depth
6. Build real-world projects

---

## Tips for Success

1. **Code Every Day**: Practice is essential. Even 30 minutes daily is better than cramming
2. **Type Code Yourself**: Don't copy-paste. Typing helps muscle memory
3. **Experiment**: Modify examples to see what happens
4. **Debug**: When errors occur, read error messages carefully
5. **Build Projects**: Apply what you learn in practical projects
6. **Ask Questions**: Join .NET communities on Reddit, Stack Overflow, Discord
7. **Review Regularly**: Revisit earlier concepts to reinforce learning
8. **Take Breaks**: Your brain needs time to process information

---

## Daily Schedule Suggestion

- **Morning (1-2 hours)**: Study new concepts, read explanations
- **Afternoon (1 hour)**: Work through code examples
- **Evening (1-2 hours)**: Complete practice tasks and coding exercises
- **Before Bed (15-30 min)**: Review quiz questions and revision points

Remember: Everyone learns at their own pace. If you need more time on a particular day, that's perfectly fine. The goal is understanding, not speed.

Good luck with your .NET learning journey! 🚀