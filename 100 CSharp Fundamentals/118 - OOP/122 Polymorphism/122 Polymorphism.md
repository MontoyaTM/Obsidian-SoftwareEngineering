Status: 
Tag: #Polymorphism #StaticTimePolymorphism #CompileTimePolymorphism
Links: [[118 Object Oriented Programming]]

---
> [!note] 
>  # Polymorphism

In C#, polymorphism enables you to write code that can work with objects of <font style="color:#b562f9">different</font> derived <font style="color:#b562f9">classes</font> through a <font style="color:#b562f9">common interface</font> provided by the base class. In other words, one object has many forms or has one name with multiple functionalities. Polymorphism allows a class to have multiple implementations with the same name.

There are two types of polymorphism in C#:
-   Static / Compile Time Polymorphism
-   Dynamic / Runtime Polymorphism

![[Pasted image 20230512190708.png]]

> [!important] 
>  ## Static / Compile Time:

<font style="color:#b562f9">Static</font> or <font style="color:#b562f9">compile-time</font> polymorphism in C# is a type of polymorphism where the appropriate method or function to <font style="color:#b562f9">execute</font> is determined by the <font style="color:#b562f9">compiler</font> at compile time, based on the method signature and arguments.

> [!important] 
> ## Dynamic / Runtime:

<font style="color:#b562f9">Dynamic/runtime</font> polymorphism is also known as late binding. Here, the method name and the method signature (the number of parameters and parameter type must be the same and may have a different implementation). Method overriding is an example of dynamic polymorphism.

--- 

> [!faq] 
>  # Use Case:

> [!example] 
> #### Method Overloading 

<font style="color:#b562f9">Static polymorphism</font> achieved through method overloading allows you to define multiple methods with the same name but different parameter lists. 

This enables you to provide <font style="color:#b562f9">different</font> ways to interact with objects based on the types or <font style="color:#b562f9">number</font> of <font style="color:#b562f9">arguments</font>. It simplifies code by offering a consistent interface for related operations with varying input types.

> [!example] 
> #### Method Overriding 

<font style="color:#b562f9">Dynamic</font> polymorphism achieved through method overriding allows derived classes to provide their <font style="color:#b562f9">own implementation</font> of <font style="color:#b562f9">methods</font> defined in the base class.

This is useful when you want to <font style="color:#b562f9">specialize</font> or <font style="color:#b562f9">extend</font> the <font style="color:#b562f9">behavior</font> of a <font style="color:#81fd83">base class method</font> in derived classes. It allows you to define a <font style="color:#81fd83">common interface</font> in the base class while providing specific behavior in different derived classes.

> [!example] 
> #### Polymorphic Collections 

Polymorphism enables you to create <font style="color:#b562f9">collections</font> that can hold objects of different types but share a <font style="color:#b562f9">common base</font> type or <font style="color:#b562f9">interface</font>.

This allows you to write code that <font style="color:#b562f9">operates</font> on the collection <font style="color:#b562f9">uniformly</font>, regardless of the actual type of the objects. It simplifies the management of heterogeneous objects and provides a way to process them in a consistent manner.

> [!example] 
> #### Dependency Injection 

Polymorphism plays a crucial role in implementing <font style="color:#b562f9">dependency injection</font>, a <font style="color:#81fd83">design pattern</font> used for <font style="color:#81fd83">decoupling</font> components and promoting <font style="color:#81fd83">testability</font> and <font style="color:#81fd83">flexibility</font>.

By defining dependencies through interfaces, you can inject different implementations of those interfaces at runtime. This allows you to swap implementations without modifying the code that relies on the interface, facilitating extensibility and modular development.

> [!example] 
> #### Frameworks and Libraries 

Polymorphism is extensively used in frameworks and libraries to provide extensibility points and customization options. By defining interfaces or base classes, frameworks allow developers to provide their <font style="color:#b562f9">own implementations</font> that adhere to the required contract.

> [!example] 
> #### Polymorphic Behavior in Design Patterns: 

Many design patterns, such as <font style="color:#b562f9">Strategy</font>, <font style="color:#b562f9">State</font>, and <font style="color:#b562f9">Factory Method</font>, rely on polymorphism to achieve their goals. These patterns often involve defining interfaces or base classes that can be implemented or extended by different classes, allowing for interchangeable behavior or customizable object creation.

---
References: [Understanding Polymorphism](https://www.c-sharpcorner.com/UploadFile/ff2f08/understanding-polymorphism-in-C-Sharp/) 