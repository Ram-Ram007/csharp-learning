C# Basic Programs (Markdown Content)

# C# Basic Programs

This document contains simple and essential C# beginner programs with explanations and code samples.

## 1. Hello World
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Hello, World!");
    }
}
```

## 2. Add Two Numbers (Hard-coded)
```csharp
using System;

class Program
{
    static void Main()
    {
        int a = 10;
        int b = 20;
        int sum = a + b;

        Console.WriteLine($"Sum = {sum}");
    }
}
```

## 3. Add Two Numbers (User Input)
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter first number: ");
        string input1 = Console.ReadLine();

        Console.Write("Enter second number: ");
        string input2 = Console.ReadLine();

        if (int.TryParse(input1, out int a) && int.TryParse(input2, out int b))
        {
            Console.WriteLine($"Sum = {a + b}");
        }
        else
        {
            Console.WriteLine("Invalid input. Please enter integers.");
        }
    }
}
```

## 4. If / Else (Odd or Even)
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter an integer: ");
        if (int.TryParse(Console.ReadLine(), out int n))
        {
            if (n % 2 == 0)
                Console.WriteLine($"{n} is even.");
            else
                Console.WriteLine($"{n} is odd.");
        }
        else
        {
            Console.WriteLine("Invalid integer.");
        }
    }
}
```

## 5. For Loop (1 to 10)
```csharp
using System;

class Program
{
    static void Main()
    {
        for (int i = 1; i <= 10; i++)
            Console.WriteLine(i);
    }
}
```

## 6. Method / Function Example (Square of Number)
```csharp
using System;

class Program
{
    static int Square(int x) => x * x;

    static void Main()
    {
        Console.Write("Enter a number: ");
        if (int.TryParse(Console.ReadLine(), out int n))
        {
            Console.WriteLine($"Square: {Square(n)}");
        }
    }
}
```

## 7. Simple Class & Object
```csharp
using System;

class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    public void Introduce()
    {
        Console.WriteLine($"Hi, I'm {Name} and I'm {Age} years old.");
    }
}

class Program
{
    static void Main()
    {
        var p = new Person { Name = "Ram", Age = 25 };
        p.Introduce();
    }
}
```

## 8. List and foreach
```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        var fruits = new List<string> { "Apple", "Banana", "Mango" };

        foreach (var f in fruits)
            Console.WriteLine(f);
    }
}
```

## 9. Simple LINQ Example
```csharp
using System;
using System.Linq;

class Program
{
    static void Main()
    {
        int[] nums = { 1, 2, 3, 4, 5, 6 };

        var evens = nums.Where(n => n % 2 == 0);

        Console.WriteLine("Even numbers: " + string.Join(", ", evens));
    }
}
```
