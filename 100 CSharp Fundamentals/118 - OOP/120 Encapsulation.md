Status: 
Tag: #Encapsulation
Links: [[118 Object Oriented Programming]]

---
> [!note] 
>  # Encapsulation

<font style="color:#b562f9">Encapsulation</font> in C# is a fundamental principle of object-oriented programming (OOP) that combines data and methods into a single unit called a <font style="color:#b562f9">class</font>. It involves the <font style="color:#b562f9">bundling</font> of <font style="color:#81fd83">data</font> members (variables) and <font style="color:#81fd83">methods</font> (functions) that operate on that data within a class, while providing controlled access to the internal state of the object.

## Encapsulation Declaration

In C#, encapsulation is achieved through the use of access modifiers such as <font style="color:#b562f9">public</font>, <font style="color:#b562f9">private</font>, <font style="color:#b562f9">protected</font>, and <font style="color:#b562f9">internal</font>. These access modifiers <font style="color:#81fd83">control</font> the <font style="color:#81fd83">visibility</font> of the class members (<font style="color:#81fd83">fields</font>, <font style="color:#81fd83">properties</font>, <font style="color:#81fd83">methods</font>, and <font style="color:#81fd83">events</font>) to other code in the application.

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

--- 

> [!faq] 
>  # Use Case:

> [!example] 
> #### Data Hiding and Protection 

Encapsulation allows you to <font style="color:#b562f9">hide</font> the <font style="color:#b562f9">internal data</font> of an <font style="color:#b562f9">object</font> by making it <font style="color:#81fd83">private</font> and providing <font style="color:#81fd83">controlled access</font> through public <font style="color:#81fd83">properties</font> or <font style="color:#81fd83">methods</font>. This helps protect sensitive data from unauthorized access or modification.

> [!example] 
> #### Code Maintainability

Encapsulation promotes <font style="color:#b562f9">code modularity</font> and encapsulation by <font style="color:#b562f9">grouping</font> related <font style="color:#b562f9">data</font> and <font style="color:#b562f9">behaviors</font> together within a class. This makes it easier to <font style="color:#81fd83">understand</font>, <font style="color:#81fd83">modify</font>, and <font style="color:#81fd83">maintain</font> the codebase over time. It also allows you to change the internal implementation of a class without affecting other parts of the code that use the class.

> [!example] 
> #### Abstraction & Interface Definition

Encapsulation helps define <font style="color:#b562f9">interfaces</font> and <font style="color:#b562f9">abstractions</font> for interacting with objects. By exposing only necessary properties and methods while hiding the implementation details, you create a clear contract or interface that other code can rely on.

> [!example] 
> #### Data Validation & Consistency 

Encapsulation allows you to <font style="color:#b562f9">enforce</font> data <font style="color:#b562f9">validation</font> and <font style="color:#b562f9">consistency</font> rules within the <font style="color:#b562f9">class</font>. By encapsulating the data and providing controlled access through properties or methods, you can validate and sanitize the input before modifying the internal state of an object.

> [!example] 
> #### Encapulation through Inheritance & Polymorphism>  

By encapsulating the data and behaviors within a base class, you can define a <font style="color:#b562f9">common interface</font> for <font style="color:#81fd83">multiple derived classes</font>. This allows you to treat objects of different classes uniformly based on their common base class, enabling code reusability and extensibility.

---
References: