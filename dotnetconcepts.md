# Final Preparation for .NET Core

## 1. What is .NET?
.NET is an **open-source**, **cross-platform** framework created by **Microsoft**.

It supports multiple languages:
- C#
- F#
- VB.NET

There are two major variants:
- **.NET Framework** – old, Windows-only
- **.NET (Core)** – modern, fast, cross-platform

---

## 2. What is .NET Framework?
- Older version of .NET  
- **Not recommended** for new projects  
- Works **only on Windows**  
- Modern apps should use **.NET 6/7/8/9 (CoreCLR)**  

---

## 3. CLR (Common Language Runtime)
### Responsibilities of CLR
1. **Converts IL to Machine Code**
2. **Memory Management (Garbage Collection)**
3. **Type Safety**
4. **Exception Handling**

### Execution Flow
1. Write C# code  
2. C# compiler → IL  
3. CLR → JIT → machine code  
4. Program runs  

---

## 4. CTS, CLS, IL, JIT

### CTS
Unifies types across C#, VB.NET, F#, etc.

### CLS
Subset of CTS ensuring language compatibility.

### IL
Platform-independent intermediate code.

### JIT
Converts IL → machine code at runtime.

---

## 5. Data Types in .NET
### Value Types
int, float, double, bool, struct, enum

### Reference Types
string, class, array, interface, delegate

### Nullable Types
int?, string?

---

## Access Modifiers
public, private, protected, internal, protected internal

---

## Classes & Objects
Blueprints for creating objects. Contains fields, methods, properties.

---

## Constructors & Destructors
Constructors initialize objects.  
Destructors run during garbage collection (rarely used).

---

## OOP Concepts
- **Inheritance**
- **Polymorphism**
- **Encapsulation**
- **Abstraction**

---

## Exception Handling
```csharp
try { }
catch (Exception ex) { }
finally { }
```

---

## Async / Await
```csharp
public async Task<string> FetchDataAsync() =>
    await httpClient.GetStringAsync(url);
```

---

## Controllers in .NET
Controllers handle incoming requests and return Views or JSON.

```csharp
public class HomeController : Controller
{
    public IActionResult Index() => View();

    public IActionResult GetData() =>
        Json(new { Name = "Ram", Age = 25 });
}
```
