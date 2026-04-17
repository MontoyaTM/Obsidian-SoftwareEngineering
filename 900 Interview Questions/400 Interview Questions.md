Status: 
Tag:
Links: 

---

> [!question] 
# Q.1: What are the main concepts of OOP? Classes? Objects?

Link(s): [[118 Object Oriented Programming]], [[102.5.1 Class Object]], [[102.5 Class]]

The main concepts of Object Oriented Programming are:

- <span style="color:#81fd83">Abstraction</span>
- <span style="color:#81fd83">Encapsulation</span>
- <span style="color:#81fd83">Inheritance</span>
- <span style="color:#81fd83">Polymorphism</span>
- <span style="color:#81fd83">Class</span>
- <span style="color:#81fd83">Object</span>


A Class is a <span style="color:#00eeff">logical unit</span> or <span style="color:#00eeff">blueprint</span> that contains:

<span style="color:#81fd83">Constructor</span>
A method in the class which gets executed when a class object is created.

<span style="color:#81fd83">Fields</span>  
A variable of any type that represents data.

<span style="color:#81fd83">Properties</span>
A property is a member that provide help in read & write of private fields.

<span style="color:#81fd83">Methods</span> 
A method is a code block that contains a series of statements
  
``` run-csharp
public class Employee
{
	public Employee()   // Constructor
	{
	}
	
	private int experience;  // Field
	
	public int Experience  // Property
	{
		get
		{ 
			return experience; 
		}
		set 
		{ 
			experience = value; 
		}
	}
	
	public void CalculateSalary()  // Method
	{
		int salary = Experience * 300000;
		Console.WriteLine("Salary:{0}", salary);
	}
}
```


An Object is an <span style="color:#00eeff">instance</span> of a class that can be used to access the data members and member functions of a class represented using the <span style="color:#b562f9">new</span> keyword.

``` run-csharp
class Program
{
	static void Main(string[] args)
	{
		Employee employeeObj = new Employee(); // Class Object
		
		employeeObj.Experience = 3;
		employeeObj.CalculateSalary();
	}
}
```

---

> [!question] 
> 
# Q.2: What is Inheritance? Why is it important?

Link(s): [[121 Inheritance]]

<span style="color:#81fd83">Inheritance</span> is a fundamental concept in OOP that allows you to <span style="color:#81fd83">create a new class based on existing classes</span>. It allows for a class to inherit the <span style="color:rgb(228, 147, 251)">members</span> (<span style="color:#81fd83">field</span>, <span style="color:#81fd83">properties</span>, and <span style="color:#81fd83">methods</span>) and <span style="color:rgb(228, 147, 251)">behavior</span> of the parent class.

Inheritance is important because: 

- Reusability of code
- Extends functionality of code

``` run-csharp
class Vehicle 
{ 
	public string Brand { get; set; } 
	public void StartEngine() 
	{ 
		Console.WriteLine("Engine started."); 
	} 
}

class Car : Vehicle
{
	public void Accelrate()
	{
		Console.WriteLine("Car is accelerating.");
	}
}
```

``` run-csharp
class Program
{
	static void Main(string[] args)
	{
		Car myCar = new Car();
		
		myCar.Brand = "Toyota";
		myCar.StartEngine();
		myCar.Accelerate();
	}
}
```

---

> [!question] 
>
# Q.3: What are the different types of Inheritance? 

Link(s):

<span style="color:#81fd83">Single inheritance</span> in C# is a concept where a class (derived class) inherits from one and only one base class.

![[Single Inheritance.svg| 250]]

``` run-csharp
class BaseClass
{
	public void Animal()
	{
		Console.WriteLine("Animal");
	}
}

class DerivedClass : BaseClass
{
	public void Dog()
	{
		Console.WriteLine("Dog");
	}
}
```

<span style="color:#81fd83">Multiple inheritance</span> is a feature where a class can inherit from more than one base class. However, C# does not support multiple inheritance for classes. Instead, C# supports multiple inheritance through <span style="color:#00eeff">interfaces</span>.

![[Multiple inheritance.svg| 500]]

``` run-csharp
class BaseClass
{
	public void Animal()
	{
		Console.WriteLine("Animal");
	}
}

interface I2
{
	public void Fly();
}

class DerivedClass : BaseClass, I2
{
	public void Eagle()
	{
		Console.WriteLine("Eagle");
	}
	
	public void Fly()
	{
		Console.WriteLine("Flying...");
	}
}
```

<span style="color:#81fd83">Multilevel Inheritance</span> in C# is a type of inheritance where a class is derived from another derived class, creating a chain of inheritance. This allows a class to inherit from another class that is itself a derived class, forming a hierarchy of classes.

![[Multilevel Inheritance.svg| 250]]

``` run-csharp
class BaseClass
{
	public void Animal()
	{
		Console.WriteLine("Animal");
	}
}

class DerivedClass1 : BaseClass
{
	public void Dog()
	{
		Console.WriteLine("Dog");
	}
}

class DerivedClass2 : DerivedClass1
{
	public void Labrador()
	{
		Console.WriteLine("Labrador");
	}
}
```

<span style="color:#81fd83">Hierarchical inheritance</span> in C# occurs when multiple derived classes inherit from a single base class. This type of inheritance allows different derived classes to share the properties and methods of a common base class, while also adding their own specific features.

![[Hierarchical Inheritance.svg| 800]]


``` run-csharp
class BaseClass
{
	public void Animal()
	{
		Console.WriteLine("Animal");
	}
}

class DerivedClass1 : BaseClass
{
	public void Dog()
	{
		Console.WriteLine("Dog");
	}
}

class DerivedClass2 : BaseClass
{
	public void Bird()
	{
		Console.WriteLine("Bird");
	}
}

class DerivedClass3 : BaseClass
{
	public void Fish()
	{
		Console.WriteLine("Fishh");
	}
}

```

---

> [!question] 
# Q.4: How to prevent a class from being Inherited?

Link(s):

To prevent a class from being inherited in C#, you must use the <span style="color:rgb(129, 253, 131)">sealed</span> or <span style="color:rgb(129, 253, 131)">static</span> keyword.

``` run-csharp
public sealed class Employee
{
	public Employee() 
	{
	}
	
	private int Experience { get; set; }
		
	public void CalculateSalary() 
	{
		int salary = Experience * 300000;
		Console.WriteLine("Salary:{0}", salary);
	}
}
```

---

> [!question] 
# Q.5: What is Abstraction?

Link(s): [[123 Abstraction]]

<span style="color:#81fd83">Abstraction</span> is a fundamental concept in OOP that allows a system to <span style="color:rgb(129, 253, 131)">hide the complexity of its implementation</span> by <span style="color:rgb(129, 253, 131)">demonstrating the functionality to the user</span>. Abstraction can be achieve through the use of <span style="color:rgb(129, 253, 131)">Interfaces</span> or <span style="color:rgb(129, 253, 131)">Abstract Classes</span> or <span style="color:rgb(129, 253, 131)">Abstract Methods</span>.

> [!tldr]  
> You define what something should do, without worrying about how it does it.

| Question it answers | What should we expose                 |
| ------------------- | ------------------------------------- |
| Focus               | Complexity hiding & design            |
| Implemented via     | Abstract classes/methods & Interfaces |
| Goal                | Simplify interaction with a system    |

An <span style="color:rgb(129, 253, 131)">Abstract Class</span> is a restricted class that <span style="color:rgb(129, 253, 131)">cannot be instantiated</span> to create new objects.

- To access `Abstract Classes`, it must be inherited

An <span style="color:rgb(129, 253, 131)">Abstract Method</span> is a method <span style="color:rgb(129, 253, 131)">without a body</span> found in an Abstract Class.

- The definition is provided by the derived class.


``` run-csharp
public abstract class Employee
{
	public int Experience { get; set; }
	
	public abstract void CalculateBonus();
	public void CalculateSalary()
	{
		int salary = Experience * 300000;
		
		Console.WriteLine("Salary: {0}", salary);
		
		CalculateBasicSalary(); // Hidden Methods
	}
	
	public void CalculateBasicSalary()
	{
		...
	}
}
```

--- 

> [!question] 
# Q.6: What is Encapsulation?

Link(s): [[120 Encapsulation]]

<span style="color:rgb(129, 253, 131)">Encapsulation</span> is a fundamental principle of OOP that allows a system to <span style="color:rgb(129, 253, 131)">hide the internal implementation details or state</span> by <span style="color:rgb(129, 253, 131)">controlled access</span>. Encapsulation can be achieved through access modifier and properties.

Access modifiers:
 - <span style="color:#b562f9">public</span>
 - <span style="color:#b562f9">private</span>
 - <span style="color:#b562f9">protected</span>
 - <span style="color:#b562f9">internal</span>

> [!tldr] 
> Think of it as a **capsule (pill)** — the medicine (data) is inside, protected from the outside. 

| Question it answers | How do we protect                 |
| ------------------- | --------------------------------- |
| Focus               | Data hiding & access control      |
| Implemented via     | Access modifiers                  |
| Goal                | Prevents misuse of internal state |

``` run-csharp
public class Person
{
    private string name;
    private int age;

    public string Name
    {
        get { return name; }
        set { name = value; }
    }

    public int Age
    {
        get { return age; }
        set { age = value; }
    }
}
```

``` run-csharp
public class Program
{
	static void Main(string[] args)
	{
		Person person = new Person();
		person.age = 25; // Not possible because of the access modifer
		person.Age = 25;
	}
}
```

---

> [!question] 
# Q.7: What is Polymorphism and what are its types? 

Link(s): [[122 Polymorphism]]

Polymorphism is a fundamental concept of OOP that allows a base class reference to <span style="color:rgb(129, 253, 131)">invoke different implementations of a method</span>.

> [!tldr] 
> Many forms. 

```columns
id: Tqm_71SN2hQUl7Xn5_V56
===
## Method Overloading



|                     |                      Compile-time (Static)                       |
| ------------------- | :--------------------------------------------------------------: |
| Resolved When       |                           Compile-time                           |
| Keyword used        |                             (*none*)                             |
| Question it answers |                Same method, different signatures                 |


===
## Method Overriding



|                     |                                             Runtime (Dynamic)                                              |
| ------------------- | :--------------------------------------------------------------------------------------------------------: |
| Resolved When       |                                                Compile-time                                                |
| Keyword used        | <span style="color:rgb(181, 98, 249)">virtual</span>/<span style="color:rgb(181, 98, 249)">override</span> |
| Question it answers |                                   Same method, different object behavior                                   |

```

---

> [!question] 
# Q.8: What is Method Overloading? In how many ways a method can be overloaded?

Link(s): 

<span style="color:rgb(129, 253, 131)">Method Overloading</span> is a type of Polymorphism that allows a method to use the <span style="color:rgb(129, 253, 131)">same method name with different signatures</span>.

Method Overloading can be achieved by:

- Number of parameters
- Data type of parameters
- Order of parameters
- Return type

![[Q.8.svg|581x355]]

``` run-csharp
public class MethodOverloading
{
	public int Add(int a, int b)
	{
		return a + b;
	}
	
	public string Add(string str1, string str2)
	{
		return str1 + str2;
	}
	
	public double Add(double a, int b, int c)
	{
		return a + b + c;
	} 
}
```

---

> [!question] 
# Q.9: What is the difference between Overloading and Overriding?

Link(s): 

Method Overriding is a type of Polymorphism that allows a <span style="color:#81fd83">derived class to provide their own implementation of methods</span> described in the base class.

To achieve Method Overriding: 

- Method signature must include the <span style="color:#b562f9">virtual</span> keyword so that it can be overridden using the <span style="color:#b562f9">override</span> keyword. 

``` run-csharp
public class BaseClass
{
    public virtual void Display()
    {
        Console.WriteLine("Display method in BaseClass");
    }
}
```

``` run-csharp
public class DerivedClass : BaseClass
{
    public override void Display()
    {
        Console.WriteLine("Display method in DerivedClass");
    }
}
```

---

> [!question] 
# Q.10: What is the difference between Method Overriding and Method Hiding?

Link(s):

<span style="color:#81fd83">Method Overriding</span> is a form of Polymorphism that uses <span style="color:rgb(181, 98, 249)">virtual</span> methods to override the base method implementation.

<span style="color:rgb(129, 253, 131)">Method Hiding</span> is a form of Polymorphism where a derived class hide the method implementation of its base class using the <span style="color:rgb(181, 98, 249)">new</span> keyword. 

- Parent method still exists but is concealed when accessing through the derived class.
- Resolved at compile time
- Cast back to Parent to reveal hidden method

``` run-csharp
public class Parent
{
    public void Speak()
    {
        Console.WriteLine("Parent speaking...");
    }
}

public class Child : Parent
{
    public new void Speak()
    {
        Console.WriteLine("Child speaking...");
    }

    public void SpeakAsParent()
    {
        base.Speak();  // Explicitly calling the hidden parent method
    }
}

Child child = new Child(); 
child.Speak(); // → "Child speaking..." 
child.SpeakAsParent(); // → "Parent speaking..." 

// Cast back to Parent to reveal hidden method 
((Parent)child).Speak(); // → "Parent speaking..."
```

``` run-csharp
public class BaseClass
{
	public void Print()
	{
		Console.WriteLine("BaseClass..");
	}
}
```

``` run-csharp
public class DerivedClass : BaseClass
{
	public new void Print()
	{
		Console.WriteLine("DerivedClass...")
	}
}
```

---

> [!question] 
# Q.11: What are the advantages and limitations of OOPS?

Link(s):

```columns
id: zSoNVOmg8EhkrhwCVTryo
===
## Advantages:

- <span style="color:#81fd83">Reuse</span> of code through Inheritance
- <span style="color:#81fd83">Flexibility</span> through Polymorphism
- <span style="color:#81fd83">Security</span> of data through data hiding or Encapsulation
- <span style="color:#81fd83">Scalability</span> through proper implementation
- <span style="color:#81fd83">Modularity</span> for easier troubleshooting 

===
## Limitations:

- It is not suitable for small application
- Time requirement for proper implementation

```

--- 

> [!question] 
# Q.12: What is the difference between an Abstract class and an Interface?

Link(s): 

```columns
id: dGSmwqzcxgu70k0-CMmkr
===
## Abstract Class

An Abstract Class uses the <span style="color:rgb(181, 98, 249)">abstract</span> keyword in its class signature to denote its implementation.

- Contains both declaration and definition of methods.
- Contains class members such as methods, fields, variables, or constructor
- Does not support multiple inheritance


===
## Interface

An Interface is a contract between classes that defines its implementation.

- Contains declaration of methods (latest versions allow for definition)
- Uses the <span style="color:rgb(181, 98, 249)">interface</span> keyword
- Supports mutliple inheritance

```

``` run-csharp
public abstract class Employee
{
	public Employee()
	{
	}
	
	private string name;
	
	public abstract void Proect(); // Method declared
	
	public void Role() // Method defined
	{
		Console.WriteLine("Software Engineer");
	}
}
```


``` run-csharp
interface IEmployee
{
	public void Project();
	public void Manager();
}
```

---
> [!question] 
>  
# Q.13: When to use Interface and when Abstract class?

Link(s): 

An <span style="color:rgb(129, 253, 131)">Interface</span> is used when the <span style="color:rgb(129, 253, 131)">structure or declaration of its class members are known</span> but can be <span style="color:rgb(129, 253, 131)">defined by its derived class</span>. 

An <span style="color:rgb(129, 253, 131)">Abstract Class</span> is used when the <span style="color:rgb(129, 253, 131)">implementation of some methods are concrete</span> and implemented the same in <span style="color:rgb(129, 253, 131)">all derived classes</span>.


---
> [!question] 
>  
# Q.14: Why to even create Interfaces?

Link(s): 

It serves as a contract or consistency between classes as to let its derived classes know what is required to implement.

``` run-csharp
interface IEmployee
{
	public void SetSalary();
	public void SetProject();
}
```

``` run-csharp
public class PermanentEmployee : IEmployee
{
	public void SetSalary() { ... }
	public void SetProject() { ... }
}
```

``` run-csharp
public class ContractEmployee : IEmployee
{
	public void SetSalary() { ... }
	public void SetProject() { ... }
}
```

--- 
> [!question] 
>  
# Q.15: Can Interface have a Constructor?

Link(s):

No. 

- Interfaces can only be derived from as they define a contract, not a state.

--- 
> [!question] 
>  
# Q.16: Can you create an instance of an Abstract class or an Interface?

Link(s):

No. 

- In both Interfaces and Abstract classes, they cannot be instantiated or used to create objects.
- However, Abstract classes allows for the use of constructors. The abstract constructor will be called in the derived class alongside its own constructor.

--- 
> [!question] 
>  
# Q.17: What are Access Specifiers? What is the default access modifier in a class?

Link(s):

<span style="color:rgb(129, 253, 131)">Access specifiers</span> are keywords to specify the accessibility of a class, method, property, or field.

- Public
- Private
- Protected
- Internal
- ProtectedInternal

The <span style="color:rgb(129, 253, 131)">default</span> access modifier is <span style="color:rgb(129, 253, 131)">internal</span>.

![[Pasted image 20240523111613.png |636]]

---
> [!question] 
>  
# Q.18: What is Boxing and Unboxing?

Link(s): [[103 Value Type]], [[102 Reference Type]]

Boxing and Unboxing is a fundamental concept in C# tied to how it handles value types and reference types in memory. Before boxing makes sense, you need to know where data lives in memory:

```columns
id: 1GI0wtCb7mW3_ZTOgTWFa
===
## Stack

- Fast, fixed-size
- Stores value directly
- Auto-managed
---
Value types holds a data value within it own memory space 
- integer types
- floating-point types
- character types
- boolean types
  

===
## Heap

- Slower, dynamic size
- Stores objects
- Managed by the garbage collector
---
Reference types contains a pointer to another memory locaction that holds the date
- Arrays
- String
- StringBuilder
- Class
- Delegates


```

<span style="color:#81fd83">Boxing</span> is the process of wrapping a <span style="color:rgb(129, 253, 131)">value type into a reference type</span> (object); Stack -> Heap.

``` run-csharp
class Program
{
	static void Main(string[] args)
	{
		int num = 100;
		
		object obj = num;  // Boxing
	}
}
```

<span style="color:#81fd83">Unboxing</span> is the process of wrapping a <span style="color:#81fd83">reference type to value type</span>; Heap -> Stack.

``` run-csharp
class Program
{
	static void Main(string[] args)
	{
		int num = 100;
		
		object obj = num;  // Boxing
		
		int i = (int)obj;  // Unboxing
	}
}
```

---
> [!question] 
>  
# Q.19: What is the difference between “String” and “StringBuilder”? When to use what?

Link(s): [[102.2 String]], [[102.3 String Builder]]

A <span style="color:#81fd83">String</span> is <span style="color:#81fd83">immutable</span> in C#.
- Once a string is defined, it cannot be modified. Each time you assign it some value, it will create a new string. 
- Modified string occupy different locations in memory

``` run-csharp
class Program
{
	static void Main(string[] args)
	{
		string str = "Intervew";
		str1 = str1 + "Happy";
	}
}
```

A <span style="color:#81fd83">StringBuilder</span> is <span style="color:#81fd83">mutable</span> in C#.
- Any manipulation or modification to the StringBuilder will not create a new instance each time.

``` run-csharp
class Program
{
	static void Main(string[] args)
	{
		StringBuilder str2 = new StringBuilder();
		str2.Append("Interview");
		str2.Append("Happy");
	}
}
```

If you plan on modifying a string multiple times, then a StringBuilder will be a better option from a performance standpoint. 

---
> [!question] 
>  
# Q.20: What are the basic string operations in C#?

Link(s):

## Quick Reference

| Operation    | Method                        | Example                 |
| ------------ | ----------------------------- | ----------------------- |
| Length       | `.Length`                     | `str.Length`            |
| Find         | `.IndexOf()`                  | `str.IndexOf("x")`      |
| Check        | `.Contains()`                 | `str.Contains("x")`     |
| Slice        | `.Substring()` / `[..]`       | `str[2..5]`             |
| Replace      | `.Replace()`                  | `str.Replace("a","b")`  |
| Trim         | `.Trim()`                     | `str.Trim()`            |
| Split        | `.Split()`                    | `str.Split(',')`        |
| Join         | `string.Join()`               | `string.Join(",", arr)` |
| Case         | `.ToUpper()` / `.ToLower()`   | `str.ToUpper()`         |
| Null check   | `string.IsNullOrWhiteSpace()` | safest null check       |
| Heavy concat | `StringBuilder`               | avoids memory waste     |

<span style="color:#81fd83">String Concatenation</span>:

In C#, string concatenation is the process of combining two or more strings into a single string. This is typically done using the <font style="color:#81fd83">"+"</font> operator, which takes two strings and returns a new string that contains the characters of both strings.

``` run-csharp
string str1 = "Hello";
string str2 = "World";
string result = str1 + " " + str2;

Console.WriteLine(result);
```

<span style="color:#81fd83">String Interpolation</span>:

This is the most modern and preferred way of formatting strings in C#. It uses the <font style="color:#81fd83">$"..."</font> syntax to include variable values directly in a string.

``` run-csharp
string name = "John";
int age = 30;
string message = $"My name is {name} and I'm {age} years old.";

Console.WriteLine(message);
```

<span style="color:#81fd83">Composite Formatting</span>:

This method uses the <font style="color:#81fd83">string.Format</font> method to format strings by inserting values into placeholders within a string.

``` run-csharp
string name = "John";
int age = 30;
string message = string.Format("My name is {0} and I'm {1} years old.", name, age);

Console.WriteLine("Hello, my name is {0}, I am {1} years old", name, age);
```

---
> [!question] 
>  
# Q.21: What are Nullable types?

Link(s): [[103.7 Nullable]]

By default, <span style="color:rgb(129, 253, 131)">value types in C# cannot be null</span> — but sometimes you need to represent the absence of a value. That's where nullable types come in.

``` run-csharp
int age = null;     // ❌ Compile error — int cannot be null
bool active = null; // ❌ Compile error — bool cannot be null

// Reference types are fine with null
string name = null; // ✅ Reference types can always be null
```

### Nullable Types
 
You can declare nullable types using <span style="color:rgb(129, 253, 131)">Nullable⋖T⋗</span> where <span style="color:rgb(129, 253, 131)">T</span> is a type.

``` run-csharp
Nullable<int> i = null;
```

You can use the '<span style="color:rgb(129, 253, 131)">?</span>' operator to <span style="color:rgb(129, 253, 131)">shorthand</span> the syntax e.g. int<span style="color:rgb(129, 253, 131)">?</span>, long<span style="color:rgb(129, 253, 131)">?</span> instead of using `Nullable<t>

``` run-csharp
int? i = null;
```


### Null Coalescing Operator

Use the '<span style="color:rgb(129, 253, 131)">??</span>' operator to assign a nullable type to a non-nullable type. 

- Returns the left side <span style="color:rgb(129, 253, 131)">if not null</span>, otherwise the right side:

``` run-csharp
int? i = null;

int j = i ?? 0;

Console.WriteLine(j);
```

- Chaining '<span style="color:rgb(129, 253, 131)">??</span>'

``` run-csharp
int? a = null; 
int? b = null; 
int? c = 42; 

int result = a ?? b ?? c ?? 0; // → 42 (first non-null wins)
```


### Null Coalescing Assignment

Assigns a value only if the variable is currently null:

``` run-csharp
int? age = null;
age ??= 18;                     // age was null → assigned 18
Console.WriteLine(age);         // → 18

int? score = 95;
score ??= 0;                    // score was NOT null → unchanged
Console.WriteLine(score);       // → 95
```


### Null Conditional Operator

Safely accesses members — returns null instead of throwing if the object is null:

``` run-csharp
string? name = null;

int? length = name?.Length;     // → null  (no exception)
string? upper = name?.ToUpper(); // → null  (no exception)

// Without ?. this would throw NullReferenceException
int crash = name.Length;        // ❌ NullReferenceException
```

- Chaining '?.'

``` run-csharp
public class Order
{
    public Customer? Customer { get; set; }
}

public class Customer
{
    public Address? Address { get; set; }
}

public class Address
{
    public string? City { get; set; }
}

Order order = new Order();  // Customer is null

// Without null checks — crashes
string city = order.Customer.Address.City;  // ❌ NullReferenceException

// With ?. chaining — safe
string? city = order?.Customer?.Address?.City;  // → null, no crash

// Combined with ??
string display = order?.Customer?.Address?.City ?? "City unknown";  // → "City unknown"
```

---
> [!question] 
>  
# Q.22: Explain Generics in C#? When and why to use them?

Link(s): [[125 Generic Collections]]

<span style="color:rgb(129, 253, 131)">Generics</span> provide a way to <span style="color:rgb(129, 253, 131)">define classes, methods, or data structure</span> using a <span style="color:rgb(129, 253, 131)">placeholder for the data type</span>. It allows for reusable code that works with any type while keeping full type safety.


<span style="color:rgb(129, 253, 131)">Type Safety</span>:
- Compiler helps catch type errors at compile time, reducing the likelihood of runtime errors.
 
<span style="color:rgb(129, 253, 131)">Code Reusability</span>:
- Solves the issue of duplicated code

<span style="color:rgb(129, 253, 131)">Performance</span>:
- Avoids the need for boxing and unboxing when working with value types that uses <span style="color:rgb(129, 253, 131)">object</span> 

### Constraints

Restricting What T Can Be by limiting what types are allowed using the <span style="color:rgb(129, 253, 131)">where</span> keyword.


``` run-csharp
public class GenericList<T> 
{ 
	private List<T> _items = new List<T>(); 
	
	public void Add(T item) 
	{ 
		_items.Add(item); 
	} 
	
	public T Get(int index) 
	{ 
		return _items[index]; 
	} 
}
```

``` run-csharp
static void Main(string[] args)
{
	GenericList<int> intList = new GenericList<int>();
	intList.Add(1);
	int value = intList.Get(0);
	
	GenericList<string> stringList = new GenericList<string>();
	stringList.Add("Hello");
	string text = stringList.Get(0);
}
```

--- 
> [!question] 
>  
# Q.23: How to implement Exception Handling in C#?

Link(s): [[108 Exception Handling]]

Exception Handling in OOP is used to manage errors.

<span style="color:#81fd83">Try-Catch Block</span>:

The try block contains the code that may throw an exception, while the catch block specifies the exception type to catch and the code to handle the exception.

``` run-csharp
try
{
  int[] myNumbers = {1, 2, 3};
  Console.WriteLine(myNumbers[10]);
}
catch (Exception e)
{
  Console.WriteLine(e.Message);
}
```

<span style="color:#81fd83">Finally Block</span>:

The finally block is <span style="color:#81fd83">optional</span> and can be added after the catch block. It contains code that executes regardless of whether an exception occurred or not. 
- This block is commonly used for resource <font style="color:#81fd83">cleanup</font>, ensuring that resources like file handles or database connections are properly released, even if an exception is thrown.

``` run-csharp
try
{
    // Code that may throw an exception
}
catch (ExceptionType1 ex1)
{
    // Handle exception of type ExceptionType1
finally
{
    // Optional: Code that executes regardless of whether an exception occurred or not
}

```

<span style="color:#81fd83">Throw</span>:

An exception can be raised manually by using the <font style="color:#b562f9">throw</font> keyword. Any type of exceptions which is derived from <font style="color:#81fd83">Exception</font> class can be raised using the throw keyword.
- The throw keyword is used to pass the stack trace to one level up.

``` run-csharp
private static void PrintStudenName(Student std)
{
	if(std == null) 
	{
		throw new NullReferenceException("Student object is nulll");
	}
}
```

---
> [!question] 
>  
# Q.24: Can we execute multiple Catch blocks?

Link(s):

No. While you can write multiple catch blocks, only one of them will be executed.

``` run-csharp
static void Main(string[] args)
{
	try
	{
		int i = 0;
		int j = 0;
		
		int k = i/j;
	}
	catch(ArithmeticException ex)
	{
	
	}
	catch(ArguementOutOfRangeException ex)
	{
	
	}
}
```

---
> [!question] 
  
# Q.25 What is a Finally block and give an example when to use it?

Link(s):

A finally block contains code that will <span style="color:rgb(129, 253, 131)">execute irrespective of exception</span>. Commonly used for resource cleanup such as closing a database connection, releasing locks, logging.

### Why does it exist?

- Without finally, cleanup code can be skipped if an exception occurs.

``` run-csharp
//Manual finally cleanup
StreamReader reader = null;

try
{
    reader = new StreamReader("file.txt");
    string content = reader.ReadToEnd();
}
finally
{
    reader?.Dispose();  // Manual cleanup
}
```

### Modern Alternative:

For objects that implement `IDisposable`, the <span style="color:rgb(129, 253, 131)">using</span> statement is cleaner than `finally` and does the same thing:

``` run-csharp
// Modern way — using handles cleanup automatically
using (StreamReader reader = new StreamReader("file.txt"))
{
    string content = reader.ReadToEnd();
}   // reader.Dispose() called automatically here
```

``` run-csharp
// Even cleaner — using declaration (C# 8.0+)
using StreamReader reader = new StreamReader("file.txt");

string content = reader.ReadToEnd();
// reader.Dispose() called when it goes out of scope
```

---
> [!question] 
>  
# Q.26: Can we have only “Try” block without “Catch” block?

Link(s):

Yes. However, you would have to implement the finally block.

``` run-csharp
static void Main(string[] args)
{
	SqlConnection conn = new SqlConnection("connectionString");
	
	try
	{
		con.Open();
		Random rnd = new Random();
		int num = rnd.Next();
		
		if(num == 5)
		{
			return;
		}
		con.Close()
	}
	finally
	{
		con.Close()
	}
}
```

---
> [!question] 
>  
# Q.27: What is the difference between “throw ex” and “throw”?

Link(s):

### What is a Stack Trace?

A stack trace is the <span style="color:rgb(129, 253, 131)"><b>breadcrumb trail</b></span> showing exactly where an <span style="color:rgb(129, 253, 131)">exception originated and how it travelled through your code</span>:

``` run-csharp
System.NullReferenceException: Object reference not set
   at OrderService.GetOrderTotal()        ← Where it actually happened
   at PaymentService.ProcessPayment()     ← Called by this
   at CheckoutController.Checkout()       ← Called by this
   at Program.Main()                      ← Entry point
```

<span style="color:rgb(129, 253, 131)">throw ex</span> resets the stack trace 
- Loses original error location

``` run-csharp
System.NullReferenceException: Order is null
   at OrderService.ProcessOrder()   ← Points here — WRONG!
                                      Real origin is GetOrderTotal()
                                      That information is now GONE
```

<span style="color:rgb(129, 253, 131)">throw</span> preserves the stack trace
- keeps full error history

``` run-csharp
System.NullReferenceException: Order is null
   at OrderService.GetOrderTotal()   ← Points here — CORRECT!
   at OrderService.ProcessOrder()    ← Full trail preserved
```


### The Three Rethrowing Patterns

``` run-csharp
// Pattern 1 — Just rethrow (most common)
catch (Exception ex)
{
    Log(ex);
    throw;              // ✅ Preserve everything, rethrow as-is
}

// Pattern 2 — Wrap with context (add meaning)
catch (SqlException ex)
{
    throw new ApplicationException("DB failed", ex);  // ✅ New exception, original preserved inside
}

// Pattern 3 — Handle and swallow (rare — only when truly handled)
catch (Exception ex)
{
    Log(ex);
    // No throw — exception is fully handled here
    return defaultValue;
}

// ❌ Anti-pattern — never do this
catch (Exception ex)
{
    throw ex;           // ❌ Destroys stack trace — no benefit over plain throw
}
```

---
> [!question] 
>  
# Q.28: What are the Loop types in C#?

Link(s): [[113 Loops]], [[115 While Loop]], [[116 Do-While Loop]], [[114 For Loop]], [[117 For-Each Loop]]

<span style="color:#81fd83">While Loop</span>:

The while loop executes a block of code repeatedly as long as a given condition remains true. This means it must contain a boolean conditional

``` run-csharp
while (condition)
{
    // code to be executed
}
```

<span style="color:#81fd83">Do-While Loop</span>:

The do-while loop executes a block of code repeatedly as long as a given condition remains true. However, the condition is checked at the end of the iteration which means the code block is guaranteed to execute at least once.

``` run-csharp
do
{
    // code to be executed
} while (condition);

```

<span style="color:#81fd83">For Loop</span>:

The for loop executes a block of code for a set number of time as long as a given condition remains true. After each iteration, the variable can be incremented or decremented. 

``` run-csharp
for (loop variable initialization ; testing condition; iteration)
{    
    // statements to be executed
}
```

<span style="color:#81fd83">Foreach Loop</span>:

The foreach loop is specifically designed for iterating over a collection of elements such as arrays, list, or other enumerable objects.

``` run-csharp
foreach (var item in collection)
{
    // code to be executed
}

```

---
> [!question] 
>  
# Q.29: What is the difference between “continue” and “break” statement?

Link(s): 

The <span style="color:#81fd83">continue</span> statement is used to skip the current iteration of the loop and proceed to the next one.  

``` run-csharp
for (int i = 0; i < 10; i++)
{
    if (i % 2 == 0)
    {
        continue; // Skip the rest of the loop body for even numbers
    }
    Console.WriteLine(i); // This line will only execute for odd numbers
}
```

The <span style="color:#81fd83">break</span> statement is used to exit the loop entirely, terminating it.

``` run-csharp
for (int i = 0; i < 10; i++)
{
    if (i == 5)
    {
        break; // Exit the loop when i is 5
    }
    Console.WriteLine(i); // This line will print numbers from 0 to 4
}
```

---
> [!question] 
>  
# Q.30: What is the difference between Array and ArrayList?

Link(s): [[102.1 Array]], [[126.1 ArrayList]]

Both store collections of items but they differ fundamentally in type safety, performance, and flexibility.

An <span style="color:rgb(129, 253, 131)">Array</span> is a <span style="color:rgb(129, 253, 131)">fixed-sized strongly typed collections</span> of elements store in <span style="color:rgb(129, 253, 131)">contiguous memory</span>.

When to use?

- Size is known upfront


``` run-csharp
int [] evenNums;
string[] cities;

int [] evenNums = new int[] {2, 4, 6, 8, 10}; 
string[] cities = new string[3] {"Mumbai", "London", "New York"};

int [] evenNums = new int[] {2, 4, 6, 8, 10}; 
string[] cities = new string[] {"Mumbai", "London", "New York"};

int [] evenNums = {2, 4, 6, 8, 10}; 
string[] cities = {"Mumbai", "London", "New York"};
```


An <span style="color:rgb(129, 253, 131)">ArrayList</span> is a <span style="color:rgb(129, 253, 131)">nonfixed-size collection of object type elements</span> stored in various locations in memory.

Why to avoid?

- Performance cost of boxing/unboxing
- Predate Generics

``` run-csharp
using System; 
using System.Collections;

ArrayList arrayList = new ArrayList(); 
arrayList.Add(10); 
arrayList.Add("Hello"); 
arrayList.Add(new DateTime(2022, 5, 1));

Console.WriteLine("Count: " + arrayList.Count);

foreach(var item in arrayList)
{
	Console.WriteLine(item);
}
```

---
> [!question] 
>  
# Q.31: What is the difference between Arraylist and Hashtable?

Link(s): [[205 Hash Table Implementation]]

A <span style="color:#81fd83">HashTable</span> is a data structure that stores <span style="color:#81fd83">key/value pairs</span> based on the hash code of each key. 

- Provides a fast way to access values based on their corresponding keys

``` run-csharp
Hashtable table = new Hashtable();

table.Add("Number", 1);
table.Add("Car", "Ferrari");
```


In an <span style="color:#81fd83">ArrayList</span>, it stores object elements or just items without any associated information.

---
> [!question] 
>  
# Q.32: What are Collections in C# and what are their types?

Link(s): [[124 Collections]], [[125 Generic Collections]], [[126 Non-Generic Collections]]

<span style="color:#81fd83">Collections</span> are data structures that allow for <span style="color:#81fd83">storing</span>, <span style="color:#81fd83">managing</span>, and <span style="color:#81fd83">manipulating</span> a group of related objects <span style="color:rgb(129, 253, 131)">efficiently</span>.

- Enabling you to perform common operations like <span style="color:#81fd83">adding</span>, <span style="color:#81fd83">removing</span>, or <span style="color:#81fd83">iterating</span> over elements.

There are two main types of Collections:
- Non-Generic Collections
- Generic Collections


<span style="color:#81fd83">Non-Generic Collection</span>, also known as legacy collection, were used prior to the introduction of generic collections in C# 2.0. 

<span style="color:#81fd83">Generic Collection</span> are <span style="color:#81fd83">strongly typed</span> collections that allow you to specify the type of elements they can contain at compile time.

Collections in C#
│
├── Non-Generic (System.Collections)        ← Old, avoid in new code
│     ├── ArrayList
│     ├── Hashtable
│     ├── Queue
│     └── Stack
│
└── Generic (System.Collections.Generic)   ← Modern, use these
      ├── List`<T>` 
      ├── Dictionary`<TKey, TValue>`
      ├── Queue`<T>`
      ├── Stack`<T>`
      ├── HashSet`<T>`
      └── LinkedList`<T>`

```
Need ordered items with duplicates?
    Access by index?                    → List<T>
    Access from front only (FIFO)?      → Queue<T>
    Access from top only (LIFO)?        → Stack<T>
    Frequent middle insertions?         → LinkedList<T>

Need key/value pairs?
    Unsorted, fast lookup?              → Dictionary<TKey, TValue>
    Always sorted by key?               → SortedDictionary<TKey, TValue>

Need unique items only?
    Unsorted?                           → HashSet<T>
    Always sorted?                      → SortedSet<T>
```


---
> [!question] 
>  
# Q.33: What is IEnumerable in C#?

Link(s):

<span style="color:rgb(129, 253, 131)">IEnumerable</span> is the most <span style="color:rgb(129, 253, 131)">fundamental collection interface</span> in C# that represents anything that can be iterated over with a <span style="color:rgb(129, 253, 131)">foreach</span> loop.

```columns
id: v-VoSOWjdNpgmgho4uUdW
===
## IEnumerable

- Non-generic (old)
- Returns object
- Requires casting  
  
===
## IEnumerable`<T>`

- Generic (modern)
- Type-safe
- No casting
```

``` run-csharp
// The entire IEnumerable<T> interface
public interface IEnumerable<T>
{
    IEnumerator<T> GetEnumerator();  // That's it — just one method
}

// IEnumerator — the actual cursor that walks through items
public interface IEnumerator<T>
{
    T Current { get; }         // Current item
    bool MoveNext();           // Move to next — returns false when done
    void Reset();              // Go back to start
}
```


### Why use IEnumerable as a parameter type?

- Writing methods that accept **any collection type**

``` run-csharp
// ❌ Too restrictive — only accepts List<int>
public void PrintNumbers(List<int> numbers)
{
    foreach (int n in numbers) Console.WriteLine(n);
}

// ❌ Also too restrictive — only accepts arrays
public void PrintNumbers(int[] numbers)
{
    foreach (int n in numbers) Console.WriteLine(n);
}

// ✅ Accepts ANY collection — List, Array, HashSet, Queue, anything
public void PrintNumbers(IEnumerable<int> numbers)
{
    foreach (int n in numbers) Console.WriteLine(n);
}
```

- Lazy evaluation (does not execute until you actually iterate)
- Deferred execution

``` run-csharp
List<int> numbers = new List<int> { 1, 2, 3, 4, 5 };

IEnumerable<int> query = numbers.Where(n => n > 2);  // Not executed yet

// Modify the source AFTER defining the query
numbers.Add(6);
numbers.Add(7);

// Query executes NOW — sees the updated list
foreach (int n in query)
{
    Console.WriteLine(n);
}
// → 3, 4, 5, 6, 7   (includes items added after query was defined)
```

- Custom Class IEnumerable

- Powering Lazy IEnumerable — `yield return` lets you build sequences **one item at a time** without storing them all in memory:

``` run-csharp
// Generates infinite even numbers — never runs out of memory
public IEnumerable<int> EvenNumbers()
{
    int n = 0;
    while (true)
    {
        yield return n;   // Returns one, pauses until next is needed
        n += 2;
    }
}

// Safe — Take(5) stops after 5 items
foreach (int n in EvenNumbers().Take(5))
{
    Console.WriteLine(n);
}
// → 0, 2, 4, 6, 8


// Read a huge file line by line — no loading entire file into memory
public IEnumerable<string> ReadLines(string path)
{
    using StreamReader reader = new StreamReader(path);
    string? line;

    while ((line = reader.ReadLine()) != null)
    {
        yield return line;  // One line at a time — memory efficient
    }
}

foreach (string line in ReadLines("hugefile.txt"))
{
    Console.WriteLine(line);  // Processes one line, then moves on
}
```

---
> [!question] 
>  
# Q.34: What is the difference between IEnumerable and IEnumerator in C#?

Link(s):

<span style="color:rgb(129, 253, 131)">IEnumerable</span> and <span style="color:rgb(129, 253, 131)">IEnumerator</span> are related <span style="color:rgb(129, 253, 131)">interfaces</span> in C# that are used for <span style="color:rgb(129, 253, 131)">iterating over collections</span>, but they serve different purposes and have different roles:

```columns
id: v-VoSOWjdNpgmgho4uUdW
===
## IEnumerable

- Purpose: IEnumerable is used to provide a way to iteracter of a collection
- Members: GetEnumerator is a method that returns an IEnumerator object that allows iteration over the collection
- Base interface for all non-
  
===
## IEnumerator

- Generic (modern)
- Type-safe
- No casting
```


<span style="color:#81fd83">IEnumerable</span>:

- Purpose: IEnumerable is used to provide a way to iterate over a collection of objects.
- Members: GetEnumerator is a method that returns an IEnumerator object that allows iteration over the collection.
- IEnumerable is the base interface for all non-generic collections that can be enumerated.

<span style="color:#81fd83">IEnumerator</span>:

- Purpose: IEnumerator is used to provide methods for iterating through a collection one element at a time. 

![[Pasted image 20240523220539.png | 700]]

---
> [!question] 
>  
# Q.35: What is the difference between IEnumerable and IQueryable in C#? Why to use IQueryable in SQL queries?

Link(s):

This difference is critically important when working with databases — getting it wrong can **destroy your application's performance.**

<span style="color:rgb(129, 253, 131)">IQueryable</span> extends <span style="color:rgb(129, 253, 131)">IEnumerable</span> — so anything IEnumerable can do, IQueryable can too.

- IQueryable adds the ability to <span style="color:rgb(129, 253, 131)">translate LINQ into SQL</span>.
- IQueryable lets you **<span style="color:rgb(129, 253, 131)">build queries conditionally</span>** without hitting the database early:

IQueryable is preferred when using SQL queries because it <span style="color:#81fd83">fetches the required data filtered before</span> return to the client side.


- With a million users, `IEnumerable` transfers 1,000,000 rows. `IQueryable` transfers only the ones matching the filter.

``` run-csharp
// Setup — Entity Framework DbContext
AppDbContext db = new AppDbContext();


// IEnumerable — query runs IN MEMORY (C# side)
IEnumerable<User> enumerable = db.Users
    .Where(u => u.Age > 18);
// SQL generated: SELECT * FROM Users        ← fetches ALL rows
// Then filters in C# memory                 ← 1 million rows transferred!


// IQueryable — query runs IN DATABASE (SQL side)
IQueryable<User> queryable = db.Users
    .Where(u => u.Age > 18);
// SQL generated: SELECT * FROM Users WHERE Age > 18  ← only matching rows
// Database does the work                              ← only 50,000 rows transferred
```

### How does it work?

IQueryable does not execute LINQ immediately, instead it <span style="color:rgb(129, 253, 131)">builds an expression tree</span>; data structure representing a query, then translates it to SQL when needed.

``` run-csharp
IQueryable<User> query = db.Users
    .Where(u => u.Age > 18)
    .OrderBy(u => u.LastName)
    .Select(u => new { u.Name, u.Email });

// At this point — NO SQL sent yet
// The query is stored as an expression tree:
//
// Select
//   └── OrderBy (LastName)
//         └── Where (Age > 18)
//               └── Users table

// SQL is generated and sent ONLY when you iterate
List<...> results = query.ToList();
// NOW it sends:
// SELECT Name, Email FROM Users
// WHERE Age > 18
// ORDER BY LastName
```



![[Pasted image 20240523221435.png]]

---
> [!question] 
>  
# Q.36: What is the difference between “out” and “ref” parameters?

Link(s):

Both <span style="color:rgb(129, 253, 131)">out</span> and <span style="color:rgb(129, 253, 131)">ref</span> allows for a <span style="color:rgb(129, 253, 131)">parameter to be passed by reference</span> but have differences in initialization rules.

```columns
id: J964BFQOdxMF_CV2Sy6Ve
===
### Out

- Variable must be initialized `before` passing in
- Used when a method returns multiple values or when the method needs to return a value that will be set within the method
- Most common use case is TryParse Pattern


===
### Ref

- Variable must be initialized `inside` the method
- Used when you want to pass a value to a method, have the method modify it, and use the modified value after the call.

```

## Out

``` run-csharp
string result;                                    // No initialization needed
GetFullName("John", "Doe", out string result);    // Method sets it
Console.WriteLine(result);                        // → "John Doe"


// Inline declaration (C# 7.0+) — cleaner syntax
GetFullName("John", "Doe", out string name);
Console.WriteLine(name);                          // → "John Doe"

public void GetFullName(string first, string last, out string fullName)
{
    // Cannot READ fullName here — it has no value yet
    // Console.WriteLine(fullName)  ❌ Compile error — unassigned

    fullName = $"{first} {last}";  // ✅ MUST assign before method ends
}
```

- Multiple out paramater

``` run-csharp
GetCircleMetrics(5,
    out double area,
    out double circumference,
    out double diameter);

Console.WriteLine($"Area:          {area:F2}");           // → 78.54
Console.WriteLine($"Circumference: {circumference:F2}");  // → 31.42
Console.WriteLine($"Diameter:      {diameter:F2}");       // → 10.00

public void GetCircleMetrics(double radius,
    out double area,
    out double circumference,
    out double diameter)
{
    diameter      = radius * 2;
    area          = Math.PI * radius * radius;
    circumference = Math.PI * diameter;
}
```

## Ref

``` run-csharp
int value = 10;              // ✅ Must initialize first
Double(ref value);
Console.WriteLine(value);    // → 20  (modified by method)


int uninitalized;
Double(ref uninitalized);    // ❌ Compile error — must assign before using ref

public void Double(ref int number)
{
    // Can READ the existing value — it's already initialized
    Console.WriteLine($"Before: {number}");  // → 10
    number = number * 2;                     // Modify it
    Console.WriteLine($"After: {number}");   // → 20
}
```

---
> [!question] 
>  
# Q.37: What is the purpose of “params” keyword?

Link(s): [[122.1.2 Params]]

The <span style="color:rgb(129, 253, 131)">params</span> keyword is used to pass an arbitrary number of arguments of the same type to a method without explicitly creating an array or specifying each argument individually.

- Must be the last parameter
- Only one params per method
- Must be single-dimensional array

``` run-csharp
// Clean call — no array needed
List<User> users = GetUsersByIds(1, 5, 10, 23, 47);

public List<User> GetUsersByIds(params int[] ids)
{
    return _db.Users
        .Where(u => ids.Contains(u.Id))
        .ToList();
}
```

### Params vs Method Overloading

Use params over method overloading when you have multiple methods with the same data type but amount differs.

``` run-csharp
// ❌ Without params — need overload for each count
public int Add(int a) => a;
public int Add(int a, int b) => a + b;
public int Add(int a, int b, int c) => a + b + c;
public int Add(int a, int b, int c, int d) => a + b + c + d;
// What about 5? 6? 10 numbers?


// ✅ With params — one method handles all cases
public int Add(params int[] numbers) => numbers.Sum();

Add(1);
Add(1, 2);
Add(1, 2, 3);
Add(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);  // All work ✅
```


---
> [!question] 
>  
# Q.38: What is a Constructor and what are its types?

Link(s): [[119 Constructors]], [[119.1 Default Constructor]], [[119.2 Parameterized Constructor]], [[119.5 Static Constructor]], [[119.4 Private Constructor]], [[119.3 Copy Constructor]]

A <span style="color:#81fd83">constructor</span> is a special method that is called when an instance of a class is created. It is used to initialize the object's state and perform necessary startup operations.

![[Pasted image 20230511205912.png | 600]]

<span style="color:#81fd83">Default Constructor</span>:

- Constructor without any parameters is a default constructor.

<span style="color:#81fd83">Parameterized Constructor</span>:

- A constructor with at least one parameter is a parametrized constructor

<span style="color:#81fd83">Static Constructor</span>:

- A static constructor is used to be called before any static members of a class is called.

<span style="color:#81fd83">Private Constructor</span>:

- A private constructor is one created using the private modifier that make it not possible for other classes to derive from this class nor create an instance of this class.

<span style="color:#81fd83">Copy Constructor</span>:

- A copy constructor is when the constructor copies an object by copying variables from another object. 

---
> [!question] 
>  
# Q.39: When to use Private constructor?

Link(s): 

A <span style="color:#81fd83">private constructor</span> is a special instance constructor which is used in a class that contains only <span style="color:#b562f9">static</span> members.

- Used in Singleton design pattern.


### When to Use Private Constructor

| Scenario                 | Why                                      |
| ------------------------ | ---------------------------------------- |
| **Singleton**            | Ensure only one instance ever exists     |
| **Factory methods**      | Control and name how objects are created |
| **Static utility class** | Prevent pointless instantiation          |
| **Object pooling**       | Limit number of instances                |
| **Prevent inheritance**  | No accessible constructor for subclasses |
| **Internal cloning**     | Expose only controlled creation paths    |


``` run-csharp
class Program
{
	static void Main(string[] args)
	{
		Employee.GetManager();
	}
}
```

``` run-csharp
public class Employee
{
	private Employee()
	{
	}
	
	public static void GetManager()
	{
		Console.WriteLine("Happy");
	}
}
```

---
> [!question] 
>  
# Q.40: What are Extension Methods in C#? When to use them?

Link(s): 

<span style="color:#81fd83">Extension Methods</span> allow you to <span style="color:rgb(129, 253, 131)">add new methods</span> in the existing class <span style="color:#81fd83">without modify the original</span> source code of the class. Extension methods are used when enhancing existing types, improve readability, utility methods.

Three Rules:

- Must be in a static class
- Method must be static
- First parameter uses `this` keyword to specify the type being extended

``` run-csharp
// Static class — required
public static class StringExtensions
{
    // Static method — required
    // 'this string input' — extends the string type
    public static string Capitalize(this string input)
    {
        if (string.IsNullOrEmpty(input)) return input;
        return char.ToUpper(input[0]) + input.Substring(1);
    }

    public static bool IsNullOrEmpty(this string input)
    {
        return string.IsNullOrEmpty(input);
    }

    public static string Truncate(this string input, int maxLength)
    {
        if (input.Length <= maxLength) return input;
        return input.Substring(0, maxLength) + "...";
    }

    public static string Repeat(this string input, int times)
    {
        return string.Concat(Enumerable.Repeat(input, times));
    }
}
```



---
> [!question] 
>  
# Q.41: What are Delegate? When to use them?

Link(s): [[102.6 Delegate]]

A <span style="color:rgb(129, 253, 131)">delegate</span> defines a <span style="color:rgb(129, 253, 131)">method signature</span> (return type + parameters), and any method that <span style="color:rgb(129, 253, 131)">matches that signature can be assigned to it</span>.

```columns
id: eSBEJWKtLWZg1Z3RHZ-0i
===
### Delegates enable:

- Passing methods as parameters
- Writing flexible, reusable code
- Event-driven programming
- Callbacks and async patterns

### Built-in Delegate Types:

- `Func<T>` -> returns a value
- `Action<T>` -> returns void
- `Predicate<T>` -> returns bool

===
![[Pasted image 20230509145533.png]]

```

``` run-csharp
public delegate int MathOperation(int a, int b);

public class Program
{
    static int Add(int x, int y) => x + y;

    static void Main()
    {
        MathOperation op = Add;  // Assign method to delegate
        int result = op(3, 4);   // Invoke delegate
        Console.WriteLine(result); // 7
    }
}
```


---
> [!question] 
>  
# Q.42: What are Multicast Delegates?

Link(s): [[102.6 Delegate]]

When a delegate is <span style="color:#81fd83">wrapped with more than one method</span>, that is known as a <span style="color:#81fd83">multicast delegate</span>. In C#, delegates are multicast, meaning they can point to more than one function at a time and be called one by one.

-   Delegates are combined and when you call a delegate then a complete list of methods is called.
-   All methods are called in First in First Out(FIFO) order.
-   ‘+’ or ‘+=’ Operator is used to add the methods to delegates.
-   ‘–’ or ‘-=’ Operator is used to remove the methods from the delegates list.

``` run-csharp
namespace Delegates
{
    delegate void ArithmeticOperation(double operand1, double operand2);

    class Program
    {
        static void Addition(double number1, double number2)
        {
            Console.WriteLine($"{number1} + {number2} = {number1 + number2}");
        }

        static void Subtraction(double number1, double number2)
        {
            Console.WriteLine($"{number1} - {number2} = {number1 - number2}");
        }

        static void Multiplication(double number1, double number2)
        {
            Console.WriteLine($"{number1} * {number2} = {number1 * number2}");
        }

        static void Division(double number1, double number2)
        {
            Console.WriteLine($"{number1} / {number2} = {number1 / number2}");
        }

        static void Main(string[] args)
        {
            ArithmeticOperation operations = Addition;
            operations += Subtraction;
            operations += Multiplication;
            operations += Division;
            operations(10, 5);
            Console.WriteLine();
        }
    }
}
```

---
> [!question] 
>  
# Q.43: What are Anonymous Delegates in C#?

Link(s): [[102.6 Delegate]]

<span style="color:rgb(129, 253, 131)">Anonymous Delegates</span> in C# are a way to <span style="color:rgb(129, 253, 131)">define inline method implementations</span> without explicitly declaring a named method.

``` run-csharp
delegate void Calculator(int x, int y);

class Program
{
	static void Main(string[] args)
	{
		Calculator calcAdd = delegate(int a, int b)
		{
			Console.WriteLine(a + b);
		};
		
		calAdd(20, 30);
	}
}
```

---
> [!question] 
>  
# Q.44: What are the differences between Events and Delegates?

Link(s): [[131 Event]], [[102.6 Delegate]]

A <span style="color:#81fd83">delegate</span> is essentially a type-safe function pointer.

An <span style="color:rgb(129, 253, 131)">event</span> is a wrapper around delegates for notification.

- An event is used to implement the Observer Design Pattern.
- 
## Real-World Analogy

- **Delegate** → A phone number
    - Anyone who has it can call directly
- **Event** → A subscription service
    - You can subscribe/unsubscribe
    - Only the service decides when to notify you

``` run-csharp
public delegate void Notify();

public class ProcessBusinessLogic
{
	public event Notify ProcessCompleted;

	public void Notification()
	{
		Console.WriteLine("Notifying...")
	}
}
```

<span style="color:#81fd83">Raising an event</span>:
Raising an event is the same as<font style="color:#b562f9"> invoking a method</font>. An event that doesn’t have any event handlers is null. Therefore, before raising an event, you need to compare it to <font style="color:#b562f9">null</font>.

``` run-csharp
delegate void OrderEventHandler();

class Order
{
    public event OrderEventHandler OnCreated;

    public void Create()
    {
        Console.WriteLine("Order created");
        
        if(OnCreated != null)
        {
            OnCreated();
        }
    }
}
```

Shortcut method: 

``` run-csharp
if(OnCreated != null)
{
	OnCreated();
}
```

``` run-csharp
OnCreated?.Invoke(this,EventArgs.Empty);
```

<span style="color:#81fd83">Subscribing to an event</span>:

Subscribing to an event means adding event handlers to an event. The event handlers must have the same return type and signature as the event’s delegate.

To add an event handler to an event, you use the <font style="color:#b562f9">+=</font> operator. The <font style="color:#b562f9">event handler</font> can be an instance <font style="color:#81fd83">method</font>, a <font style="color:#81fd83">static method</font>, an <font style="color:#81fd83">anonymous method</font>, or a<font style="color:#81fd83"> lambda expression</font>.

``` run-csharp
class Program
{
    static void Main(string[] args)
    {
        var order = new Order();

        order.OnCreated += Email.Send;
        order.OnCreated += SMS.Send;

        order.Create();
    }
}
```


---
> [!question] 
>  
# Q.45: What is “this” keyword in C#? When to use it?

Link(s):

<span style="color:#81fd83">This</span> keyword is used to refer to the <span style="color:#81fd83">current instance of the class</span>. It is a reference to the object itself, allowing access to its members (fields, properties, methods, and events) and differentiating between instance members and parameters or local variables with the same name. Use cases:

<span style="color:#81fd83">Disambiguation</span>:

``` run-csharp
public class Car
{
    private string model;

    public void SetModel(string model)
    {
        this.model = model; // "this.model" refers to the instance variable, "model" refers to the parameter
    }
}
```

<span style="color:#81fd83">Constructor Chaining</span>:

``` run-csharp
public class Car
{
    private string model;
    private int year;

    public Car(string model)
    {
        this.model = model;
    }

    public Car(string model, int year) : this(model)
    {
        this.year = year;
    }
}

```

<span style="color:#81fd83">Extension Methods</span>:

``` run-csharp
public static class StringExtensions
{
	public static string RightSubstring(this String s, int count)
	{
		return s.Substring(s.length - count, count);
	}
}
```

<span style="color:#81fd83">Method Chaining</span>:

``` run-csharp
public class Car
{
    private string model;
    private int year;
    private string color;

    public Car SetModel(string model)
    {
        this.model = model;
        return this;
    }

    public Car SetYear(int year)
    {
        this.year = year;
        return this;
    }

    public Car SetColor(string color)
    {
        this.color = color;
        return this;
    }

    public void DisplayInfo()
    {
        Console.WriteLine($"Model: {model}, Year: {year}, Color: {color}");
    }
}

class Program
{
    static void Main()
    {
        Car car = new Car()
            .SetModel("Tesla Model S")
            .SetYear(2022)
            .SetColor("Red");

        car.DisplayInfo(); // Output: Model: Tesla Model S, Year: 2022, Color: Red
    }
}

```

---
> [!question] 
>  
# Q.46: What is the purpose of “using” keyword in C#?

Link(s): 

The purpose of using keywords can be for multiple reasons:

<span style="color:#81fd83">Using Directive</span>: 

- using System.IO;

<span style="color:#81fd83">Using Statement</span>:

The using statement ensures that Dispose() method of a class object is called even if an exception occurs.

``` run-csharp
static void Main(string[] args)
{
	using(var connection = new SqlConnection("ConnectionString"))
	{
		...
		
		//connection.Dispose();
	}
}
```

---
> [!question] 
>  
# Q.47: What is the difference between “is” and “as” operators?

Link(s):

The <span style="color:#81fd83">is</span> operator is used to check the type of an object.

``` run-csharp
static void Main(string[] args)
{
	int i = 5;
	
	bool check = i is int;
	
	Console.WriteLine(check);
}
```

The <span style="color:#81fd83">as</span> operator is used to perform conversion between compatible reference type.

``` run-csharp
static void Main(string[] args)
{
	object ob = "Hello";
	
	string str = obj as sring;
	
	Console.WriteLine(str)
}
```

---
> [!question] 
>  
# Q.48: What is the difference between “Readonly” and “Constant” variables?

Link(s):

Both <span style="color:#81fd83">readonly</span> and <span style="color:#81fd83">const</span> are used to define variables whose values cannot be changed after initialization, but they have different characteristics and use cases.

- readonly variables can be assigned in declaration and in the constructor
- const variables must be assigned during declaration


``` run-csharp
class Example
{
	public readonly int myReadOnly1 = 100;
	public const int myReadOnly2 = 100;
	
	public Example(int i)
	{
		myReadOnly2 = i * 100;
	}
}
```

---
> [!question] 
>  
# Q.49: What is “Static” class? When to use it?

Link(s):

A <span style="color:#81fd83">static class</span> is a class which object cannot be created or inherited. Static classes are used as containers for static members.


---
> [!question] 
>  
# Q.50: What is the difference between “var” and “dynamic” in C#?</span>

Link(s):

The <span style="color:#81fd83">var</span> keyword is used when creating variable where its data type is decided by the complier at compile time.

The <span style="color:#81fd83">dynamic</span> keyword is used when creating variables where its data type is decided at run time.

``` run-csharp
class Program
{
	static void Main(string[] args)
	{
		dyanmic b = 10;
		b = "Happy"
	}
}
```

---
> [!question] 
>  
# Q.51: What is Enum keyword used for?

Link(s):

An enum is a special class that represents a group of constants.

``` run-csharp
enum Temperature
{
	Low,
	Medium,
	High,
	Extreme
}
```

---
References: https://www.youtube.com/watch?v=Bai9_LSZfAI&list=WL&index=54