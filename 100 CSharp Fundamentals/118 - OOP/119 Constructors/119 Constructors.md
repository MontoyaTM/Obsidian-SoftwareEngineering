Status: 
Tag: #Constructor #DependencyInjection #OverloadedConstructor
Links: [[118 Object Oriented Programming]]

---
> [!note] 
>  # Constructors

In C#, a <font style="color:#b562f9">constructor</font> is a special <font style="color:#b562f9">method</font> that is called when an <font style="color:#b562f9">instance</font> of a <font style="color:#b562f9">class</font> is created. It is used to <font style="color:#81fd83">initialize</font> the <font style="color:#81fd83">object</font>'s <font style="color:#81fd83">state</font> and perform any necessary setup <font style="color:#81fd83">operations</font>. 

Constructors play a crucial role in Object-Oriented Programming (OOP) because they allow you to define how objects of a class should be created and initialized. Here are some key points regarding constructors and their relation to OOP:
![[Pasted image 20230511205912.png]]
## Constructor Declaration:

> [!attention] 
>  Constructors have the same name as the class and do not have a return type.

``` run-csharp
class Person {
	public string name;
	
	public Person(string name)
	{
		this.name = name;
	}
}

Person User = new Person("Thomas");
Console.WriteLine(User.name)
```

--- 

> [!faq] 
>  # Use Case:

> [!example] 
>  #### Object Initialization:

Constructors are primarily used to <font style="color:#b562f9">initialize</font> the state of an <font style="color:#b562f9">object</font>. They allow you to set the initial values of the object's <font style="color:#81fd83">fields</font> and <font style="color:#81fd83">properties</font>, ensuring that the object is in a valid and <font style="color:#81fd83">usable state</font> from the start.

``` run-csharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    // Constructor
    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
}

// Creating an instance of the Person class and initializing its properties
Person person = new Person("John", 30);

```


> [!example] 
>  #### Dependency Injection:

Dependency injection is a <font style="color:#b562f9">design pattern</font> where the <font style="color:#b562f9">dependencies</font> of an object are <font style="color:#b562f9">injected</font> into it <font style="color:#b562f9">rather</font> than being <font style="color:#b562f9">created</font> within the object itself. Constructors can be used to receive and assign these dependencies, making the object more flexible and testable

``` run-csharp
public class Logger
{
    // Constructor
    public Logger(string logFilePath)
    {
        // Initialize the logger with the provided log file path
    }

    // Other methods and properties
}

// Creating an instance of the Logger class with a specific log file path
Logger logger = new Logger("C:/Logs/application.log");

```


> [!example] 
>  #### Overloaded Constructors:

Constructors can be <font style="color:#b562f9">overloaded</font>, allowing you to define <font style="color:#b562f9">multiple constructors</font> with <font style="color:#b562f9">different</font> sets of <font style="color:#b562f9">parameters</font>. This enables flexibility in object creation by providing various ways to initialize the object. Users can choose the constructor that suits their needs best.

``` run-csharp
public class Rectangle
{
    public int Width { get; set; }
    public int Height { get; set; }

    // Constructor with default values
    public Rectangle()
    {
        Width = 0;
        Height = 0;
    }

    // Constructor with custom width and height
    public Rectangle(int width, int height)
    {
        Width = width;
        Height = height;
    }
}

// Creating instances of the Rectangle class using different constructors
Rectangle defaultRectangle = new Rectangle(); // Width = 0, Height = 0
Rectangle customRectangle = new Rectangle(10, 5); // Width = 10, Height = 5

```


> [!example] 
>  #### Base Class Initialization:

In <font style="color:#b562f9">inheritance</font> scenarios, constructors are used to <font style="color:#b562f9">initialize</font> the <font style="color:#b562f9">base class</font> before initializing the derived class. This ensures that the base class's fields and properties are properly initialized before the derived class's specific initialization logic is executed.

``` run-csharp
public class Shape
{
    public int Area { get; protected set; }

    // Constructor
    public Shape()
    {
        // Base class initialization logic
    }
}

public class Rectangle : Shape
{
    public int Width { get; set; }
    public int Height { get; set; }

    // Constructor
    public Rectangle(int width, int height)
    {
        Width = width;
        Height = height;

        // Derived class initialization logic
        Area = Width * Height;
    }
}

// Creating an instance of the Rectangle class and initializing its properties and base class
Rectangle rectangle = new Rectangle(10, 5); // Width = 10, Height = 5, Area = 50

```

---
References: