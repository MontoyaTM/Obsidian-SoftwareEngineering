Status: 
Tag: #Abstraction
Links: [[118 Object Oriented Programming]]

---
> [!note] 
>  # Abstraction

In C#, abstraction is a fundamental concept in object-oriented programming (OOP) that allows you to define and use complex systems by simplifying their representation.

<font style="color:#b562f9">Abstraction</font> allows you to <font style="color:#b562f9">hide</font> the <font style="color:#b562f9">implementation</font> details of a <font style="color:#81fd83">class</font> or an <font style="color:#81fd83">object</font> and focus on its essential features and behaviors. By abstracting away the implementation, you can create a higher-level view of an object that is independent of its specific implementation details.

## Abstraction Declaration

In C# abstraction is achieved with the help of <font style="color:#b562f9">Abstract classes</font> and <font style="color:#b562f9">Access modifiers</font>

> [!example] 
> #### Abstract Classes 

An <font style="color:#b562f9">abstract class</font> is a class that <font style="color:#81fd83">cannot</font> be <font style="color:#81fd83">instantiated</font> and serves as a blueprint for other classes. It may contain <font style="color:#81fd83">one</font> or <font style="color:#81fd83">more</font> abstract methods, which are declared <font style="color:#b562f9">without</font> any <font style="color:#b562f9">implementation</font>.

<font style="color:#b562f9">Subclasses</font> that derive from an abstract class must provide <font style="color:#b562f9">implementations</font> for these abstract methods. Abstract classes allow you to define common functionality and behaviors that can be shared among multiple derived classes.


> [!attention] 
> - You cannot create objects of the abstract class. Or in other words, you cannot use the abstract class directly with the new operator.

``` run-csharp
abstract class Shape 
{
    public abstract int area();
}

class Square : Shape 
{
    private int side;

    public Square(int x = 0)
    {
        side = x;
    }

    public override int area()
    {
        Console.Write("Area of Square: ");
        return (side * side);
    }
}

Shape sh = new Square(4);

double result = sh.area();

Console.Write("{0}", result);

```



--- 

> [!faq] 
>  # Use Case:

> [!example] 
> #### Creating Frameworks and Libraries 

<font style="color:#b562f9">Abstraction</font> allows you to define a set of <font style="color:#b562f9">interfaces</font> and <font style="color:#b562f9">abstract classes</font> that serve as the foundation for a <font style="color:#81fd83">framework</font> or <font style="color:#81fd83">library</font>. By providing abstract classes and interfaces, you can define the contract that users of the framework or library must adhere to while hiding the implementation details.

> [!example] 
> #### Polymorphism 

Abstraction enables <font style="color:#b562f9">polymorphism</font>, which is the ability of <font style="color:#b562f9">objects</font> to take on <font style="color:#b562f9">different forms</font>. Through abstract classes and interfaces, you can define a common interface for a set of related objects, allowing them to be treated interchangeably.

---
References: