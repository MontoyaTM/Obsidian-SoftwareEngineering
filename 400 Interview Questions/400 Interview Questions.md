Status: 
Tag:
Links: 

---

> [!question] 
# What are the main concepts of OOP? Classes? Objects?

Link(s): [[118 Object Oriented Programming]], [[102.5.1 Class Object]], [[102.5 Class]]

The main concepts of Object Oriented Programming are:
- <span style="color:#81fd83">Inheritance</span>
- <span style="color:#81fd83">Polymorphism</span>
- <span style="color:#81fd83">Abstraction</span>
- <span style="color:#81fd83">Encapsulation</span>
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
# What is Inheritance? Why is it important?

Link(s): [[121 Inheritance]]

<span style="color:#81fd83">Inheritance</span> is a fundamental concept in OOP that allows you to <span style="color:#81fd83">create a new class based on existing classes</span>. It allows for a class to inherit the <span style="color:#00eeff">members</span> (<span style="color:#81fd83">field</span>, <span style="color:#81fd83">properties</span>, and <span style="color:#81fd83">methods</span>) and <span style="color:#00eeff">behavior</span> of the parent class.

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

Inheritance is important because it allows for <span style="color:#81fd83">reusability</span> and <span style="color:#81fd83">abstraction</span> of code.

---

> [!question] 
>
# What are the different types of Inheritance? 

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

<span style="color:#81fd83">Multiple inheritance</span> is a feature where a class can inherit from more than one base class. However, C# does not support multiple inheritance for classe. Instead, C# supports multiple inheritance through <span style="color:#00eeff">interfaces</span>.

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
# How to prevent a class from being Inherited?

Link(s):

To prevent a class from being inherited in C#, you must use the <span style="color:#b562f9">sealed</span> or <span style="color:#b562f9">static</span> keyword. However, you must change all members of the class to static as well.

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
# What is Abstraction?

Link(s): [[123 Abstraction]]

<span style="color:#81fd83">Abstraction</span> is a fundamental concept in OOP that allows you to <span style="color:#81fd83">hide the implementation details</span> of a <span style="color:#b562f9">class</span> or an <span style="color:#b562f9">object</span> so that you can focus on the essential features and behaviors. This can be achieve in many ways such as Interfaces, Abstract classes

``` run-csharp
public class Employee
{
	public int Experience { get; set; }
	
	public void CalculateSalary()
	{
		int salary = Experience * 300000;
		
		Console.WriteLine("Salary: {0}", salary);
		
		CalculateBasicSalary(); // Hidden Methods
		CalculateHRA();  // Hidden Methods
	}
	
	public void CalculateBasicSalary()
	{
		...
	}

	public void CalculateHRA()
	{
		...
	}
}
```

![[Pasted image 20240522133302.png]]

--- 

> [!question] 
# What is Encapsulation?

Link(s): [[120 Encapsulation]]

Encapsulation is a fundamental principle of OOP that combines data and methods into a single unit called a <span style="color:#81fd83">class</span>. Encapsulation helps in restricting access to certain components through the use of access modifiers such as <span style="color:#b562f9">public</span>, <span style="color:#b562f9">private</span>, <span style="color:#b562f9">protected</span>, and <span style="color:#b562f9">internal</span>.


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
# What is Polymorphism and what are its types? 

Link(s): [[122 Polymorphism]]

Polymorphism is a fundamental principle of OOP that allows a <span style="color:#b562f9">variable</span>, <span style="color:#b562f9">object</span>, or <span style="color:#b562f9">method</span> to take on <span style="color:#81fd83">multiple forms</span>.

Polymorphism is achieved through <span style="color:#81fd83">Method Overloading</span> and <span style="color:#81fd83">Method Overriding</span>. In the case of Method Overloading; it is a form of Compile-Time Polymorphism while Method Overriding is a Run-Time Polymorphism. 

---

> [!question] 
# What is Method Overloading? In how many ways a method can be overloaded?

Link(s): 

Method overloading is a type of Polymorphism that allows for <span style="color:#81fd83">multiple methods of the same name</span> in the <span style="color:#81fd83">same class</span> but with different signatures.

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

Method Overloading can be achieved by:
- Number of parameters
- Data type of parameters
- Order of parameters
- Return type

---

> [!question] 
# What is the difference between Overloading and Overriding?

Link(s): 

Method Overriding is a type of Polymorphism that allows a <span style="color:#81fd83">derived class to provide their own implementation of methods</span> described in the base class.

To achieve Method Overriding, the method signature must include the <span style="color:#b562f9">virtual</span> keyword so that it can be overridden; <span style="color:#b562f9">override</span> keyword. 

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
# What is the difference between Method Overriding and Method Hiding?

Link(s):

<span style="color:#81fd83">Method Overriding</span> is having methods with the same name and signature but in <span style="color:#81fd83">different classes</span>.

In <span style="color:#81fd83">Method Hiding</span>, you can hide the implementation of the methods of a base class from the derived class using the <span style="color:#b562f9">new</span> keyword. 

The main difference is that in Method Hiding, using the new keyword redefines the method which severs any connection or relationship to the base class definition.

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
# What are the advantages and limitations of OOPS?

Link(s):

Advantages:
- <span style="color:#81fd83">Reuse</span> of code through Inheritance
- <span style="color:#81fd83">Flexibility</span> through Polymorphism
- <span style="color:#81fd83">Security</span> of data through data hiding or Encapsulation
- <span style="color:#81fd83">Scalability</span> through proper implementation
- <span style="color:#81fd83">Modularity</span> for easier troubleshooting 
  
Limitations:
- It is not suitable for small application
- Time requirement for proper implementation

--- 

> [!question] 
# What is the difference between an Abstract class and an Interface?

Link(s): 

An <span style="color:#81fd83">Abstract Class</span> contains both <span style="color:#e493fb">declaration</span> and <span style="color:#e493fb">definition</span> of methods. 
- Abstract class uses the keyword: <span style="color:#b562f9">abstract</span>
- Abstract class can contain <span style="color:#81fd83">methods</span>, <span style="color:#81fd83">field</span>, <span style="color:#81fd83">constructor</span>, and other class members
- Abstract class does not support multiple inheritance

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

An <span style="color:#81fd83">Interface</span> can only contain <span style="color:#e493fb">declaration</span> of methods. However, in the latest version of C#; it allows for defining the body of an interface. 
- Interfaces use the keyword: <span style="color:#b562f9">interface</span>
- Interfaces supports multiple inheritance

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
# When to use Interface and when Abstract class?

Link(s): 

<span style="color:#81fd83">Abstract class</span> is a good choice when you are sure <span style="color:#81fd83">some methods are concrete or defined</span> and must be implemented in the <span style="color:#e493fb">same way</span> in all derived classes.

 
An <span style="color:#81fd83">Interface</span> is a good choice when you know that a method has to be included but can be implemented differently by the derived class.

---
> [!question] 
>  
# Why to even create Interfaces?

Link(s): 

The reason for using Interfaces is for <span style="color:#81fd83">consistency</span> through the use of a contract. A set of public methods any implementing class has to have.

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
# Can Interface have a Constructor?

Link(s):

No. Interfaces can only be derived from.

--- 
> [!question] 
>  
# Can you create an instance of an Abstract class or an Interface?

Link(s):

No. In both Interfaces and Abstract classes, they cannot be instantiated or used to create objects.

However, Abstract classes allows for the use of constructors. The abstract constructor will be called in the derived class alongside its own constructor.

--- 
> [!question] 
>  
# What are Access Specifiers? What is the default access modifier in a class?

Link(s):

Access specifiers are keywords to specify the accessibility of a class, method, property, or field.
- Public
- Private
- Protected
- Internal
- ProtectedInternal

The default access modifier is internal.

![[Pasted image 20240523111613.png | 500]]

---
> [!question] 
>  
# What is Boxing and Unboxing?

Link(s): [[103 Value Type]], [[102 Reference Type]]

<span style="color:#81fd83">Boxing</span> is the process of converting from <span style="color:#81fd83">value type to reference type.
</span>

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

<span style="color:#81fd83">Unboxing</span> is the process of converting <span style="color:#81fd83">reference type to value type</span>.

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
# What is the difference between “String” and “StringBuilder”? When to use what?

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
# What are the basic string operations in C#?

Link(s):

- Concatenate(+)
- Replace(a, b)
- Trim()
- Contains("")

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
# What are Nullable types?

Link(s): [[103.7 Nullable]]

<span style="color:#81fd83">Nullable types</span> are used to <span style="color:#81fd83">hold null values</span> because variable types cannot do so.

 
You can declare nullable types using Nullable⋖T⋗ where T is a type.

``` run-csharp
Nullable<int> i = null;
```

You can use the '<font style="color:#b562f9">?</font>' operator to shorthand the syntax e.g. <font style="color:#b562f9">int?</font>, <font style="color:#b562f9">long?</font> instead of using `Nullable<t>

``` run-csharp
int? i = null;
```

Use the '??' operator to assign a nullable type to a non-nullable type.

``` run-csharp
int? i = null;

int j = i ?? 0;

Console.WriteLine(j);
```

---
> [!question] 
>  
# Explain Generics in C#? When and why to use them?

Link(s): [[125 Generic Collections]]

<span style="color:#81fd83">Generics</span> provides a way to define classes, methods, and data structures with a <span style="color:#81fd83">placeholder for the data type</span> they store or use.
 
- <span style="color:#81fd83">Type Safety</span> help catch type errors at compile time rather than at runtime, reducing the likelihood of runtime errors.
- <span style="color:#81fd83">Code Reusability</span> allows a class, method, or data structure to be used with any data type without the need to duplicate code.
- <span style="color:#81fd83">Performance</span> from generics allows us to avoid the need for boxing and unboxing when working with value types, leading to better performance compared to using non-generic collections.

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
# How to implement Exception Handling in C#?

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
# Can we execute multiple Catch blocks?

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
>  
 # What is a Finally block and give an example when to use it?

Link(s):

A finally block will execute irrespective of exception. It is commonly used for resource cleanup.

``` run-csharp
static void Main(string[] args)
{
	SqlConnection conn = new SqlConnection("connectionString");
	
	try
	{
		con.Open();
		...
	}
	catch(Exception ex)
	{
		// Error handled
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
# Can we have only “Try” block without “Catch” block?

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
# What is the difference between “throw ex” and “throw”?

Link(s):

<span style="color:#81fd83">Throw ex</span> will <span style="color:#81fd83">change</span> the stack trace, where as <span style="color:#81fd83">throw</span> will <span style="color:#81fd83">preserve</span> the entire stack trace.

``` run-csharp
static void Main(string[] args)
{
	try
	{
		DivideZeroByZero();
	}
	catch (Exception ex)
	{
		Console.WriteLine(ex.StackTrace);
		Console.ReadLine();
	}
}

public static void DivideZeroByZero()
{
	try
	{
		int i = 0, j = 0;
		int k = i / j;
	} 
	catch(Excepton ex)
	{
		throw;
		throw ex;
	}
}

```

---
> [!question] 
>  
# What are the Loop types in C#?

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
# What is the difference between “continue” and “break” statement?

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
# What is the difference between Array and ArrayList?

Link(s): [[102.1 Array]], [[126.1 ArrayList]]

An <span style="color:#81fd83">Array</span> is a <span style="color:#e493fb">fixed-sized strongly typed collection</span> of elements stored in <span style="color:#e493fb">contiguous memory</span>.

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

An <span style="color:#81fd83">ArrayList</span> is a <span style="color:#e493fb">nonfixed-size collection of object type</span> elements. This means that any type of elements can be stored within the ArrayList. 

However, casting is required when retrieving elements which can lead to run time errors if not handled correctly.

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
# What is the difference between Arraylist and Hashtable?

Link(s): [[205 Hash Table Implementation]]

A <span style="color:#81fd83">HashTable</span> is a data structure that stores <span style="color:#81fd83">key/value pairs</span> that are arranged based on the HashCode of each key. It provides a <font style="color:#81fd83">fast</font> way to <font style="color:#81fd83">access</font> values based on their corresponding keys. 

``` run-csharp
Hashtable table = new Hashtable();

table.Add("Number", 1);
table.Add("Car", "Ferrari");
```

In an <span style="color:#81fd83">ArrayList</span>, it stores object elements or just items without any associated information.

---
> [!question] 
>  
# What are Collections in C# and what are their types?

Link(s): [[124 Collections]], [[125 Generic Collections]], [[126 Non-Generic Collections]]

<span style="color:#81fd83">Collections</span> are data structures that allow for <span style="color:#81fd83">storing</span>, <span style="color:#81fd83">managing</span>, and <span style="color:#81fd83">manipulating</span> a group of related objects efficiently.

It provides a way to organize and manage data efficiently, enabling you to perform common operations like <span style="color:#81fd83">adding</span>, <span style="color:#81fd83">removing</span>, or <span style="color:#81fd83">iterating</span> over elements.

There are two main types of Collections:
- Non-Generic Collections
- Generic Collections

<span style="color:#81fd83">Non-Generic Collection</span>, also known as legacy collection, were used prior to the introduction of generic collections in C# 2.0. They are <span style="color:#81fd83">not type-safe</span> and require <span style="color:#81fd83">explicit casting</span> when retrieving elements.

- ArrayList
- Hashtable
- Queue
- Stack

<span style="color:#81fd83">Generic Collection</span> are <span style="color:#81fd83">strongly typed</span> collections that allow you to specify the type of elements they can contain at compile time.

- List⋖T⋗
- Queue⋖T⋗
- Dictionary⋖T⋗
- Stack⋖T⋗

---
> [!question] 
>  
# What is IEnumerable in C#?

Link(s):

IEnumerable Interface is used when you want to iterate among a collection class using a foreach loop.

``` run-csharp
class Program
{
	var employees = new List<Employee>()
	{
		new Employee() { Id = 1, Name = "Bill" },
		new Employee() { Id = 2, Name = "Steve" }
	}
	
	foreach(var employee in employees)
	{
		Console.WriteLine(employee.Id +  ", " + emplyee.Name);
	}
}
```

---
> [!question] 
>  
# What is the difference between IEnumerable and IEnumerator in C#?

Link(s):

IEnumerable and IEnumerator are related interfaces in C# that are used for iterating over collections, but they serve different purposes and have different roles:

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
# What is the difference between IEnumerable and IQueryable in C#? Why to use IQueryable in SQL queries?


<span style="color:#81fd83">IQueryable</span> Interface provides similar functionality as IEnumerable Interface and is found under the System.LINQ namespace. 

- However, it is used to iterate SQL query collection from data.

``` run-csharp
DataClassDataContext dc = new DataClassDataContext()
IQueryable<Employee> list = dc.Employees.Where( d => d.Department.Equals("IT"));

list = list.Take<Employee>(3);

foreach(var item in list)
{
	Response.Write(item.Name + "<br/>");
}
```

IQueryable Interface is preferred when using SQL queries because it <span style="color:#81fd83">fetches the required data filtered before</span> return to the client side.

![[Pasted image 20240523221435.png]]

---
> [!question] 
>  
# What is the difference between “out” and “ref” parameters?

Link(s):

Using keywords such as <span style="color:#b562f9">out</span> and <span style="color:#b562f9">ref</span> allows for parameter to be passed by reference. These keywords are useful for when you want to return more than one value from a method.

``` run-csharp
static void Main(string[] args)
{
	int a;
	int b = 5;
	
	WithRefOut p = new WithRefOut();
	
	int x = p.Update(out a, ref b;)
	
	Console.WriteLine("WithtRefOut: " + a + " " + b);  
}

public class WithRefOut
{
	public int Update(out int c, ref int d)
	{
		c = 100;
		return c + d;
	}
}
```

<span style="color:#81fd83">Out</span>:

Variables passed with the <span style="color:#b562f9">out</span> keyword <span style="color:#81fd83">do not need to be initialized</span> before it is passed to the method. However, it <span style="color:#81fd83">must be initialized before it returns</span>.

- Commonly used when a method needs to return multiple values or when the method needs to return a value that will be set within the method.

<span style="color:#81fd83">Ref</span>:

Variables passed with the <span style="color:#b562f9">ref</span> keyword must be <span style="color:#81fd83">initialized before</span> it can be passed to the method. The method can then read and modify the value of the parameter.

- Typically used when you want to pass a value to a method, have the method modify it, and then use the modified value after the method call.

---
> [!question] 
>  
# What is the purpose of “params” keyword?

Link(s): [[122.1.2 Params]]

The <span style="color:#b562f9">params</span> keyword is used to pass an arbitrary number of arguments of the same type to a method without explicitly creating an array or specifying each argument individually.

``` run-csharp
void PrintNumbers(params int[] numbers) 
{ 
	foreach (int num in numbers) 
	{ 
		Console.WriteLine(num); 
	} 
}
PrintNumbers(1);
PrintNumbers(2, 3, 4);

int[] array = {5, 6, 7, 8, 9};
PrintNumbers(array);
```


---
> [!question] 
>  
# What is a Constructor and what are its types?

Link(s): [[119 Constructors]], [[119.1 Default Constructor]], [[119.2 Parameterized Constructor]], [[119.5 Static Constructor]], [[119.4 Private Constructor]], [[119.3 Copy Constructor]]

A <span style="color:#81fd83">constructor</span> is a special method that is called when an instance of a class is created. It is used to initialize the object's state and perform necessary startup operations.

![[Pasted image 20230511205912.png | 600]]

<span style="color:#81fd83">Default Constructor</span>:

- Constructor without and parameters is a default constructor.

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
# When to use Private constructor?

Link(s): 

A <span style="color:#81fd83">private constructor</span> is a special instance constructor which is used in a class that contains only <span style="color:#b562f9">static</span> members.

- Used in Singleton design pattern.

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
# What are Extension Methods in C#? When to use them?

Link(s): 

<span style="color:#81fd83">Extension Methods</span> allow you to add new methods in the existing class <span style="color:#81fd83">without modify the original</span> source code of the class.

- Extension methods are static methods defined in static classes, and they use the <span style="color:#b562f9">this</span> keyword as the first parameter to specify which type they extend.

``` run-csharp
class Program
{
	string test = "HelloWorld";
	
	string left = test.Substring(0, 5);
	
	string right = test.RightSubstring(5);
}
```

``` run-csharp
public static class StringExtensions
{
	public static string RightSubstring(this String s, int count)
	{
		return s.Substring(s.length - count, count);
	}
}
```

Extension methods are used when enhancing existing types, improve readability, utility methods.

---
> [!question] 
>  
# What you mean by Delegate? When to use them?

Link(s): [[102.6 Delegate]]

A <span style="color:#81fd83">delegate</span> is a variable that holds the reference to a method or pointer to a function.

- A delegate can refer to <span style="color:#81fd83">more than once method</span> as long as it has the <span style="color:#81fd83">same return type and parameters</span>.

![[Pasted image 20230509145533.png]]

``` run-csharp
delegate void Calculator(int x, int y);

class Program
{
	public static void Add(int a, int b)
	{
		Console.WriteLine(a + b);
	}
	
	public static void Mul(int a, int b)
	{
		Console.WriteLine(a * b*)
	}
}
```

Delegate type can be declared using the <font style="color:#b562f9">delegate</font> keyword. Once a delegate is declared, delegate <font style="color:#81fd83">instance</font> will refer and call those <font style="color:#81fd83">methods</font> whose <font style="color:#81fd83">return type</font> and <font style="color:#81fd83">parameter-list</font> matches with the delegate declaration.

``` run-csharp
// [modifier] delegate [return_type] [delegate_name] ([parameter_list]);

public delegate int GeeksForGeeks(int G, int F, int G);
```

---
> [!question] 
>  
# What are Multicast Delegates?

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
# What are Anonymous Delegates in C#?

Link(s): [[102.6 Delegate]]

An anonymous delegate is when you declare a delegate but there is no need to declare the method associated with it.

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
# What are the differences between Events and Delegates?

Link(s): [[131 Event]], [[102.6 Delegate]]

A <span style="color:#81fd83">delegate</span> is a variable that <span style="color:#81fd83">holds the reference</span> to a method or pointer to a function.

An <span style="color:#81fd83">event</span> is a <span style="color:#81fd83">notification mechanism</span> that depends on delegates.
- An event is used to implement the Observer Design Pattern.

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
# What is “this” keyword in C#? When to use it?

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
# What is the purpose of “using” keyword in C#?

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
# What is the difference between “is” and “as” operators?

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
# What is the difference between “Readonly” and “Constant” variables?

Link(s):

Both <span style="color:#81fd83">readonly</span> and <span style="color:#81fd83">const</span> are used to define variables whose values cannot be changed after initialization, but they have different characteristics and use cases.

- readonly variables can be assigned in declaration and in the constructor
- const variables must be assigned during declaration


``` run-csharp
class Example
{
	public readonly int myReadOnly1 = 100;
	public readonly int myReadOnly2 = 100;
	
	public Example(int i)
	{
		myReadOnly2 = i * 100;
	}
}
```

---
> [!question] 
>  
# What is “Static” class? When to use it?

Link(s):

A <span style="color:#81fd83">static class</span> is a class which object cannot be created or inherited. Static classes are used as containers for static members.

---
> [!question] 
>  
# What is the difference between “var” and “dynamic” in C#?

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
# What is Enum keyword used for?

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