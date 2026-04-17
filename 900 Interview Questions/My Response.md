Status: 
Tag:
Links: [[400 Interview Questions]]

---
# Q.1: What are the main concepts of OOP? Classes? Objects?

- Abstraction
- Encapsulation
- Inheritance
- Polymorphism
- Classes
- Objects

A class is a logical unit of data, methods, fields, variables that serve as a blueprint. An object is a specific instance of the class that has access to its data and behavior. 

# Q.2: What is Inheritance? Why is it important?

Inheritance is a fundamental concept of OOP that allows for the creation of a new class based on an existing one. It allows a class to inherit its members (fields, properties, methods) and behavior.

- Allows for the reusability of code
- Abstraction of code

# Q.3: What are the different types of Inheritance? 

##### Single Inheritance: 
Concept in which a derived class inherits from one base class.

##### Multiple Inheritance: 
Concept in which a class inherits from more than one base class. In C# multiple inheritance is implemented through interfaces.

##### Multilevel Inheritance:
Concept in which a derived class inherits from another derived class— creating a chain of inheritance.

##### Hierarchical Inheritance:
Concept in which multiple derived classes inherit from a single base class.


# Q.4: How to prevent a class from being Inherited?

To prevent a class from being inherited you would use <span style="color:rgb(132, 255, 0)">sealed</span> or <span style="color:rgb(132, 255, 0)">static</span> class modifier

# Q.5: What is Abstraction?

Abstraction is a fundamental concept in OOP that allows a class to hide its internal implementation details while showing only the essential functionality to the user. It is implemented through:

- Interfaces
- Abstract Classes
- Abstract Methods

# Q.6: What is Encapsulation?

Encapsulation is a fundamental concept in OOP that bundles related data and method into a single unit while providing controlled access to its internal states.

- Restricts access to components by access modifiers


# Q.7: What is Polymorphism and what are its types? 

Polymorphism is a fundamental concept in OOP that allows a base class reference to invoke different implementations of a method depending on the actual object type through:

- `virtual` or `override` keyword
- Method overloading — same method name but multiple method signatures
- Method overriding — allows for a method to be overridden 

# Q.8: What is Method Overloading? In how many ways a method can be overloaded?

Method overloading is a concept that allows a method to use polymorphism through different method signatures.

- Parameter overloading
- Return value overloading
- 


# Q.9: What is the difference between Overloading and Overriding?

Method Overloading:

- Occurs at compile-time
- Same method name, different signature

Method Overriding is concept that allows a method to use polymorphism by overriding an existing method.

- Occurs at runtime
- Require the `virtual` keyword on method signature
- Requires the `override` keyword to declare method overriding


# Q.10: What is the difference between Method Overriding and Method Hiding?

Method Overriding is a form of Polymorphism that uses virtual methods to override the base method implementation. Method hiding is a form of Encapsulation that  

# Q.11: What are the advantages and limitations of OOPS?

Allows for a structured reusable codebase that can be maintained. The limitation is the overhead required that may slow down progression.

# Q.12: What is the difference between an Abstract class and an Interface?

An Abstract Class uses the abstract keyword to denote its implementation. 

- Methods cannot contain implementation

# Q.13: When to use Interface and when Abstract class?

You want to use an Interface when the structure and definition of an Interface is known and the opposite for abstract classes

# Q.14: Why to even create Interfaces?

It serves as a contract between classes to let its derived classes know what is required of them.


# Q.15: Can Interface have a Constructor?

No



# Q.16: Can you create an instance of an Abstract class or an Interface?

No 
# Q.17: What are Access Specifiers? What is the default access modifier in a class?

Access specifiers are keywords used to control the access to a classes data members. Default is internal

- Public
- Private
- Protected
- Internal
- ProtectedInternal

# Q.18: What is Boxing and Unboxing?

Boxing is the process of converting a value type to a reference type.
Unboxing is the process of wrapping a reference type to a value type.


# Q.19: What is the difference between “String” and “StringBuilder”? When to use what?

A String is an immutable type in C# where once it is define, it cannot be modified. Whenever you assign a new value, it create an entirely new string in a memory.

A StringBuilder is the opposite, it can be modified without creating a new instance each time.

# Q.20: What are the basic string operations in C#?

- Concatenate +
- Replace(a, b)
- Trim()
- Contains("")

String concatenate is the process of combining two string into a single one using the `+` character.
String replace is a method used to 



# Q.21: What are Nullable types?

Nullable types are value types that represent the absence of a value using the ? operator for shorthand syntax.


# Q.22: Explain Generics in C#? When and why to use them?

Generics is a fundamental concept in C# that provides a way to define classes, methods, and data structures with a placeholder for the data type they store or use.

- Type Safety




# Q.23: How to implement Exception Handling in C#?

- Try-catch block
- Finally
- Throw

# Q.24: Can we execute multiple Catch blocks?

No, only one catch block will be executed if multiple catch blocks are written.

# Q.25: What is a Finally block and give an example when to use it?

A finally block is a form of exception handling that will always be run at the end of a try-catch block regardless of an exception.

- Commonly used as a resource cleanup


# Q.26: Can we have only “Try” block without “Catch” block?

Yes but the finally block must be implemented

# Q.27: What is the difference between “throw ex” and “throw”?

throw ex resets the stack trace while throw retains it.

A stack trace is a breadcrumb that allows a user to see where an exception originated and how it moved through the code. 

# Q.28: What are the Loop types in C#?

- For
- While
- Do-while
- Foreach

# Q.29: What is the difference between “continue” and “break” statement?

Continue allows you to jump over the current iteration of a loop.

Break escapes the entire loop entirely.



# Q.30: What is the difference between Array and ArrayList?

An array is a data structure that exists as a contiguous memory that allows for a specific data type.

An arraylist exists in different parts of memory without needing to be of same data type.

# Q.31: What is the difference between Arraylist and Hashtable?

A Hasthable is a data structure that stores data as a key/value pair based on the hash code of each key.

An Array list does not store any related data

# Q.32: What are Collections in C# and what are their types?

Collections in C# represent data structures that allow for the storing, managing, and manipulating a group of related objects efficiently. 

Non-Generic:
- Hashtable
- ArrayList
- Queue
- Stack

Generic:

- HashSet`<T>`
- List`<T>
- Queue`<T>`
- Stack`<T>
- Dictionary`<TKey,TValue>`
- LinkedList`<T>`

# Q.33: What is IEnumerable in C#? Why use it as a parameter type?

IEnumerable is a fundamental collection interface that allows anything to iterate over a foreach loop.

Using IEnumerable as a parameter type allows for any collection type to be used

- Allows for any collection type
- Lazy Evaluation
- Deferred Execution
- Allows for a custom class to have looping functionality
- Allows for yield return; sequence the collection one item at a time without storing it all in memory


# Q.34: What is the difference between IEnumerable and IEnumerator in C#?

IEnumerable and IEnumerator are related interfaces that are used for iterating over a collection but server different purposes.

IEnumerable purpose is to provide a way to iterate over a collection of objects while IEnumerator provides methods for iterating through a collection one element at a  time

# Q.35: What is the difference between IEnumerable and IQueryable in C#? Why to use IQueryable in SQL queries and how does it work?

IEnumerable and IQueryable difference can be more critical when working with databases. IQueryable extends IEnumerable, so everything IEnumerable can do so can IQueryable.

- Adds the ability to translate LINQ into SQL.
- Allow for building a query conditionally without hitting the database early.
- Builds an expression tree then translates it to SQL

IQueryable is recommended when using SQL queries because it fetches the required data filtered before returning to the client side.

# Q.36: What is the difference between “out” and “ref” parameters?

Both out and ref allow for a parameter to be passed by reference but have different initialization rules.

Out does not have to be initialized, the method will do the work.
Ref must be initialized before passing in the variable.

# Q.37: What is the purpose of “params” keyword?

Params allows a method to accept any number of parameters

# Q.38: What is a Constructor and what are its types?

A Constructor is a special method that is called when an instance of a class is created. It is used to initialize an object's state and perform necessary startup operations

- Default Constructor
- Parameterized Constructer
- Static Constructor
- Private Constructor
- Copy Constructor

# Q.39: When to use Private constructor?

Use a private constructor when you don't want the class to be derived or instantiated

- Singleton Pattern


# Q.40: What are Extension Methods in C#? When to use them?

Extension Methods lets you add new methods to existing types without modifying them

# Q.41: What are Delegate? When to use them?

Delegate define a method signature (return type + parameters), and any method that matches can be assigned to it
# Q.42: What are Multicast Delegates?

Multicast delegates are delegate wrapped with more than one method.
# Q.43: What are Anonymous Delegates in C#?

Anonymous delegate are delegates that are define inline without explicitly declaring a method name
# Q.44: What are the differences between Events and Delegates?

A Delegate is essentially a pointer to a function with the same method signature.
An Event is a wrapper around a delegate for notification. 


# Q.45: What is “this” keyword in C#? When to use it?

This is a keyword used refer to the current instance of the class so that it can differentiate between parameters or local variable of the same name.

Also used in:

- Extension Methods

# Q.46: What is the purpose of “using” keyword in C#?

The using statement ensure that the Dispose() method of a class object is called even if an exception occurs.

# Q.47: What is the difference between “is” and “as” operators?

<span style="color:rgb(129, 253, 131)">Is</span> -> check the type of an object
<span style="color:rgb(129, 253, 131)">As</span> -> attempts to perform conversion between compatible reference type.

# Q.48: What is the difference between “Readonly” and “Constant” variables?

<span style="color:rgb(129, 253, 131)">Readonly</span> -> assigned in declaration or in the constructor
<span style="color:rgb(129, 253, 131)">Const</span> -> must be assigned during declaration

# Q.49: What is “Static” class? When to use it?



# Q.50: What is the difference between “var” and “dynamic” in C#?



# Q.51: What is Enum keyword used for?







