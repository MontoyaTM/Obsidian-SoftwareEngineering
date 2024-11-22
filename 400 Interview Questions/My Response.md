Status: 
Tag:
Links: [[400 Interview Questions]]

---
# Q.1: What are the main concepts of OOP? Classes? Objects?

- <span style="color:#81fd83">Abstraction</span>
- <span style="color:#81fd83">Encapsulation</span>
- <span style="color:#81fd83">Inheritance</span>
- <span style="color:#81fd83">Polymorphism</span>
- <span style="color:#81fd83">Class</span>
- <span style="color:#81fd83">Object</span>

A <span style="color:#81fd83">class</span> is a <span style="color:#81fd83">blueprint</span> that contains constructors, fields, properties, and methods.

- A <span style="color:#81fd83">constructor</span> is a special method that is executed when the class is instantiated.
- A <span style="color:#81fd83">fields</span> is a variable of any type that represents data.
- A <span style="color:#81fd83">property</span> is a member that provides read/write access to private methods.
- A <span style="color:#81fd83">method</span> is a block of code that contains a series of statements.


An <span style="color:#81fd83">object</span> is an <span style="color:#81fd83">instance of a class</span> represented using the new keyword and has access to a class's fields, properties, and methods.


# Q.2: What is Inheritance? Why is it important?

<span style="color:#81fd83">Inheritance</span> is one of the main concepts of OOP that allows for the <span style="color:#81fd83">creation of a new class based on an existing class</span>. 

It allows for the new class to inherit data members (fields, properties, and methods) and the behavior of the parent class resulting on reusability of code.


# Q.3: What are the different types of Inheritance? 

- <span style="color:#81fd83">Single Inheritance</span>

Single Inheritance is when exactly one class inherits from a base class.


- <span style="color:#81fd83">Multiple Inheritance</span>
Multiple Inheritance is when one class inherit from multiple base classes. In C#, multiple inheritance is done through interfaces.


- <span style="color:#81fd83">Multi-Level Inheritance</span>
Multi-Level Inheritance is when one class inherits from a derived class creating a chain of inheritance.


- <span style="color:#81fd83">Hierarchical Inheritance </span>
Hierarchical Inheritance is when multiple classes inherit from a single base class. 


# Q.4: How to prevent a class from being Inherited?

To prevent a class from being inherited you would use the <span style="color:#81fd83">sealed</span> or <span style="color:#81fd83">static</span> access modifier.


# Q.5: What is Abstraction?

<span style="color:#81fd83">Abstraction</span> is one of the main concepts of OOP that allows you to <span style="color:#81fd83">hide the implementation details</span> of a class and showing only the required information to the user.

Abstraction can be achieved by using <span style="color:#81fd83">Interfaces</span>, <span style="color:#81fd83">Abstract Methods</span> or <span style="color:#81fd83">Abstract Classes</span>


An <span style="color:#81fd83">Abstract Class</span> is a restricted class that <span style="color:#81fd83">prevents it from being instantiated as objects</span>. The class must be inherited to access its data members and methods.

# Q.6: What is Encapsulation?

<span style="color:#81fd83">Encapsulation</span> is one of the main concepts of OOP that allows you to bundle data and methods together in a class while limiting access to the data members.

Encapsulation is achieved using access modifiers such as <span style="color:#81fd83">public</span>, <span style="color:#81fd83">private</span>, <span style="color:#81fd83">protected</span>, and <span style="color:#81fd83">internal</span>.


# Q.7: What is Polymorphism and what are its types? 

<span style="color:#81fd83">Polymorphism</span> is one of the fundamental concepts of OOP that allow a variable, object or methods to take on <span style="color:#81fd83">multiple forms</span>.

Polymorphism can be achieved through <span style="color:#81fd83">Method Overloading</span> or <span style="color:#81fd83">Methods Overriding</span>. 


# Q.8: What is Method Overloading? In how many ways a method can be overloaded?

<span style="color:#81fd83">Method Overloading</span> is a type of Polymorphism that allows for multiple methods of the same name in the same class but with different signatures through:

- Changing the <span style="color:#81fd83">number</span> of parameters
- Changing the <span style="color:#81fd83">order</span> of parameters
- Changing the <span style="color:#81fd83">type</span> of parameters
- Changing the <span style="color:#81fd83">return type</span>


# Q.9: What is the difference between Overloading and Overriding?

<span style="color:#81fd83">Method Overriding</span> is a type of Polymorphism that allows a derived class to <span style="color:#81fd83">override</span> a method in the base class containing the <span style="color:#81fd83">virtual keyword</span>. However, it must have the same signature.

The main difference between both forms of Polymorphism is that in Method Overriding; you must inherit from a base class and override the virtual method. In Method Overloading, you must be within the same class to modify the method signature.


# Q.10: What is the difference between Method Overriding and Method Hiding?


In <span style="color:#81fd83">Method Hiding</span>, instead of overriding a virtual method; the base method inherited uses the <span style="color:#81fd83">new keyword</span> in it method signature. This essentially create an entire new method that has no relationship with the base class method.


# Q.11: What are the advantages and limitations of OOPS?

Advantages:
- <span style="color:#81fd83">Reusability</span> of code through <span style="color:#81fd83">Inheritance</span>
- <span style="color:#81fd83">Flexibility</span> through <span style="color:#81fd83">Polymorphism</span>
- <span style="color:#81fd83">Security</span> of data through data hiding or <span style="color:#81fd83">Encapsulation</span>
- <span style="color:#81fd83">Scalability</span> through proper implementation
- <span style="color:#81fd83">Modularity</span> for easier troubleshooting


Limitations:
- Time requirement for proper implementation
- Not suitable for small applications


# Q.12: What is the difference between an Abstract class and an Interface?

An <span style="color:#81fd83">Abstract class</span> is a restricted class that prevent itself from being instantiated as an object. The class must be inherited to access the data members or methods.

- An Abstract Class contains both <span style="color:#81fd83">declaration</span> and <span style="color:#81fd83">definition</span> of methods.
- An Abstract Class can contain <span style="color:#81fd83">methods</span>, <span style="color:#81fd83">fields</span>, <span style="color:#81fd83">constructor</span>, and other class members.
- An Abstract Class does not support multiple Inheritance.
- An Abstract Class use the keyword: <span style="color:#b562f9">abstract</span>.

An <span style="color:#81fd83">Interface</span> is a restricted class that cannot be instantiated directly. It must be inherited so that its members can be implemented.

An <span style="color:#81fd83">Interface</span> is a contract that defines a set of <span style="color:#81fd83">methods</span>, <span style="color:#81fd83">properties</span>, and <span style="color:#81fd83">events</span> that must be implemented.

- An Interface can only contain <span style="color:#81fd83">declaration</span> of methods.
- An Interface supports multiple inheritance.
- An Interface uses the keyword: <span style="color:#b562f9">interface</span>


# Q.13: When to use Interface and when Abstract class?

An <span style="color:#81fd83">Interface</span> is a good choice when you know that a <span style="color:#81fd83">method has to be included</span> but can be <span style="color:#b562f9">implemented differently</span> in the inherited class.

- Interfaces provide a more <span style="color:#81fd83">flexible</span> approach


An <span style="color:#81fd83">Abstract Class</span> is a good choice when you are sure some <span style="color:#81fd83">methods are concrete</span> and must be <span style="color:#b562f9">implemented in the same way</span> in all inherited classes.

- Provide a more <span style="color:#81fd83">structured</span> approach 


# Q.14: Why to even create Interfaces?


<span style="color:#81fd83">Interfaces</span> allow for a contract relationship between two class while allowing flexibility to implement the methods, properties, or event in their own way.

- <span style="color:#81fd83">Consistency</span> 


# Q.15: Can Interface have a Constructor?


No.


# Q.16: Can you create an instance of an Abstract class or an Interface?

No. However, an <span style="color:#81fd83">Abstract Class</span> allows for the use of constructors but an Abstract Class cannot be instantiated.

- <span style="color:#81fd83">Initialization of fields</span>: Constructors in Abstract Classes can be used to initialize fields.
- <span style="color:#81fd83">Constructor Chaining</span>: Subclasses can call the constructor of the abstract class using the base keyword, allowing for the initialization of fields defined in the abstract class before the subclass-specific initialization logic is executed.


# Q.17: What are Access Specifiers? What is the default access modifier in a class?

<span style="color:#81fd83">Access specifiers</span> are another name for <span style="color:#81fd83">access modifiers</span> which aid in access of code throughout a project.

- <span style="color:#81fd83">Public</span>
- <span style="color:#81fd83">Private</span>
- <span style="color:#81fd83">Protected</span>
- <span style="color:#81fd83">Internal</span> (Default)
- <span style="color:#81fd83">Protected Internal</span>

# Q.18: What is Boxing and Unboxing?

<span style="color:#81fd83">Boxing</span> is the process of converting from <span style="color:#b562f9">value type</span> to <span style="color:#b562f9">reference type</span> implicitly.

<span style="color:#81fd83">Unboxing</span> is the process of converting <span style="color:#b562f9">reference type</span> to <span style="color:#b562f9">value type</span> explicitly.


# Q.19: What is the difference between “String” and “StringBuilder”? When to use what?

A <span style="color:#81fd83">String</span> is an <span style="color:#81fd83">immutable</span> collection of characters in memory. This means that if you assign a new value, it will occupy a new location in memory.



A <span style="color:#81fd83">StringBuilder</span> is a <span style="color:#81fd83">mutable</span> collection of characters in memory. It will dynamically expand memory to accommodate the modified string.

You would prefer StringBuilder over String in cases where you plan on modifying the variable multiple times.


# Q.20: What are the basic string operations in C#?

- Concatenate
- Replace()
- Trim()
- Contains()


# Q.21: What are Nullable types?

<span style="color:#81fd83">Nullable</span> types are used to hold null values since variable type cannot.

``` run-csharp
Nullable<T> i = null;
```


# Q.22: Explain Generics in C#? When and why to use them?

<span style="color:#81fd83">Generics</span> are a concept that allows for classes, methods, and data structures to use a <span style="color:#81fd83">placeholder</span> for the <span style="color:#81fd83">data type</span> they use.

It allows for:

- Type Safety 
- Code Reusability
- Performance


# Q.23: How to implement Exception Handling in C#?

Exception Handling is a concept that allow for managing errors using:

- Try-Catch
- Finally
- Throw 


# Q.24: Can we execute multiple Catch blocks?

No. You can have multiple catch block but only one of them will ever be executed


# Q.25: What is a Finally block and give an example when to use it?


A <span style="color:#81fd83">finally block</span> is a block of code that runs after a try-catch block <span style="color:#81fd83">regardless</span> of an exception.

It is most commonly used to provide resource cleanup such as closing a database connection.


# Q.26: Can we have only “Try” block without “Catch” block?

Yes. However, you would need to implement the finally block.


# Q.27: What is the difference between “throw ex” and “throw”?

<span style="color:#81fd83">Throw Ex</span> will <span style="color:#81fd83">change</span> the stack trace while <span style="color:#81fd83">throw</span> will <span style="color:#81fd83">preserve</span> the entire stack trace.


# Q.28: What are the Loop types in C#?

- For Loop
- While Loop
- Do While Loop
- Foreach Loop


# Q.29: What is the difference between “continue” and “break” statement?

Both statements are used to escape a loop but does so in different ways. The <span style="color:#81fd83">break</span> statement break out of the <span style="color:#81fd83">current iteration</span> while the <span style="color:#81fd83">continue</span> statement exits out of the <span style="color:#81fd83">loop entirely</span>


# Q.30: What is the difference between Array and ArrayList?

An <span style="color:#81fd83">Array</span> is a <span style="color:#81fd83">fixed-size collection</span> of data of the <span style="color:#81fd83">same type</span> stored in contiguous memory.

An <span style="color:#81fd83">ArrayList</span> is a <span style="color:#81fd83">nonfixed-size collection</span> of data of <span style="color:#81fd83">different data types</span>. However, unboxing (casting) is required for retrieving elements.


# Q.31: What is the difference between Arraylist and Hashtable?

A <span style="color:#81fd83">HashTable</span> is a data structure that stores a collection of data as a <span style="color:#81fd83">key-value pair</span> based on a hashing function on the key.

An ArrayList stores a collection of data without any associated information.


# Q.32: What are Collections in C# and what are their types?

<span style="color:#81fd83">Collections</span> are <span style="color:#81fd83">data structures</span> that allow for <span style="color:#b562f9">storing</span>, <span style="color:#b562f9">managing</span>, and <span style="color:#b562f9">manipulating</span> a group of related object effectively.

These data structures allow for operations such as <span style="color:#81fd83">adding</span>, <span style="color:#81fd83">removing</span>, and <span style="color:#81fd83">iterating</span> over elements.

There are two types of Collections: 

<span style="color:#81fd83">Non-Generic Collections</span> are weakly typed meaning it can contain any type of data type but requires explicit casting.

- ArrayList
- HashTable
- Queue
- Stack

<span style="color:#81fd83">Generic Collections</span> are strongly typed that require you to specify the type of elements:

- List⋖T⋗
- Queue⋖T⋗
- Dictionary⋖T⋗
- Stack⋖T⋗


# Q.33: What is IEnumerable in C#?

<span style="color:#81fd83">IEnumerable</span> is an Interface that is used to <span style="color:#81fd83">define a collection</span> that can be iterated over.

- Provides a method to get an enumerator GetEnumerator


# Q.34: What is the difference between IEnumerable and IEnumerator in C#?

<span style="color:#81fd83">IEnumerator</span> is an Interface that is used to <span style="color:#81fd83">define the actual mechanism</span> to iterate over a collection.

- Provide the functionality to move though the collection


# Q.35: What is the difference between IEnumerable and IQueryable in C#? Why to use IQueryable in SQL queries?

<span style="color:#81fd83">IQueryable</span> is an Interface that is used to iterate data from a <span style="color:#81fd83">SQL query collection</span>.

- Fetches the required data filtered before

# Q.36: What is the difference between “out” and “ref” parameters?

Both keywords allow for <span style="color:#81fd83">parameters</span> to be <span style="color:#81fd83">passed by reference</span> and useful for when you want to return more than one value from a method.

<span style="color:#81fd83">Out</span>:

Parameters passed with the <span style="color:#b562f9">out</span> keyword <span style="color:#81fd83">do not need to be initialized</span> before being passed into the method. 

- Must be instantiated before it returns.

<span style="color:#81fd83">Ref</span>:

Parameters passed with the <span style="color:#b562f9">ref</span> keyword <span style="color:#81fd83">have to be initialized</span> before being passed into the method.


# Q.37: What is the purpose of “params” keyword?

The <span style="color:#b562f9">params</span> keyword is a parameter modifier that allows any number of arguments of the same type to be passed into a method.


# Q.38: What is a Constructor and what are its types?

A <span style="color:#81fd83">constructor</span> is a special method that executes when a class is <span style="color:#81fd83">instantiated</span>. It is used to initialize the objects state and perform necessary startup operations.

- <span style="color:#b562f9">Default</span> Constructor
- <span style="color:#b562f9">Private</span> Constructor
- <span style="color:#b562f9">Parameterized</span> Constructor
- <span style="color:#b562f9">Static</span> Constructor
- <span style="color:#b562f9">Copy</span> Constructor


# Q.39: When to use Private constructor?


A <span style="color:#81fd83">private constructo</span>r is a special instance constructor which is used in a class that contains only static members.

- Denies any class from deriving it or create an instance of it
- Used in Singleton design pattern


# Q.40: What are Extension Methods in C#? When to use them?

<span style="color:#81fd83">Extension methods</span> allow you to add new methods in the existing class without modifying the original source code of the class.

- Extension methods are <span style="color:#b562f9">static</span> methods define in <span style="color:#81fd83">static classes</span>
- Extension method use the <span style="color:#b562f9">this</span> keyword as the <span style="color:#81fd83">first parameter</span> to specify which type they extend


# Q.41: What you mean by Delegate? When to use them?

A <span style="color:#81fd83">delegate</span> is a variable that holds the reference to a method (pointer to a function).

- Can refer to more than one method as long as it has the <span style="color:#81fd83">same return type and parameters</span>


# Q.42: What are Multicast Delegates?


A <span style="color:#81fd83">multicast delegate</span> is a delegate that is wrapped with more than on method meaning that it can <span style="color:#81fd83">point to more that one function</span> at a time.

- Method are called in a (FIFO) <span style="color:#b562f9">First in First Out</span> order.
- ‘<span style="color:#81fd83">+</span>’ or ‘<span style="color:#81fd83">+=</span>’ Operator is used to add the methods to delegates.
- ‘<span style="color:#81fd83">–</span>’ or ‘<span style="color:#81fd83">-=</span>’ Operator is used to remove the methods from the delegates list.


# Q.43: What are Anonymous Delegates in C#?

Anonymous delegates are delegates that are declared without the use of a method call. 

# Q.44: What are the differences between Events and Delegates?

A <span style="color:#81fd83">delegate</span> is a variable that <span style="color:#81fd83">holds a reference</span> to a method.

An <span style="color:#81fd83">event</span> is a <span style="color:#81fd83">notification mechanism</span> that depends on delegates. 

- Subscribing to an event means adding an event handler to an event. "<span style="color:#b562f9">+=</span>"


# Q.45: What is “this” keyword in C#? When to use it?

The "this" keyword is used to refer to the current instance of the class.

- Reference to the objects itself
- Disambiguation
- Constructor Chaining
- Extension Methods
- Method Chaining


# Q.46: What is the purpose of “using” keyword in C#?

The purpose of the "<span style="color:#81fd83">using</span>" keyword is for: 

- <span style="color:#81fd83">Using Directives</span>
- Ensures that <span style="color:#81fd83">Dispose</span>() method of a class object is called even if an exception occurs.


# Q.47: What is the difference between “is” and “as” operators?

The "<span style="color:#81fd83">is</span>" operator is used to check the type of an object.

The "<span style="color:#81fd83">as</span>" operator is used to perform conversion between compatible reference type.


# Q.48: What is the difference between “Readonly” and “Constant” variables?

<span style="color:#81fd83">Readonly</span> variables can be assigned in <span style="color:#81fd83">declaration</span> or in the <span style="color:#81fd83">constructor</span>.

<span style="color:#81fd83">Const</span> variables must be assigned during <span style="color:#81fd83">declaration</span>.


# Q.49: What is “Static” class? When to use it?

A <span style="color:#81fd83">static class</span> is a class that cannot be <span style="color:#81fd83">instantiated</span> or <span style="color:#81fd83">inherited</span>.

- Container


# Q.50: What is the difference between “var” and “dynamic” in C#?

The "<span style="color:#81fd83">var</span>" keyword is used when creating variables where the data type is decide by the complier at compile time.

The "<span style="color:#81fd83">dynamic</span>" keyword is used when creating variables where its data is decided at run time.


# Q.51: What is Enum keyword used for?

An enum is a special class that represents a group of constants






