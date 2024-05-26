Status: 
Tag: #DataType #Memory
Links: [[101 Data Type]]

---
> [!note] 
>  # Memory Management

# Stack Data Structure:

The defining property of stacks is that they're last-in, first-out, meaning the last item added to the stack is the first item to be removed. In other words, to place a new item onto a stack it has to go on the top, and only the item currently at the top can be removed, therefore if you wanted to remove an item from the middle of a stack, say, the third item down from the top, you would first have to remove the top two items.

![[Pasted image 20230509165451.png]]

# Call Stack

Again, the call stack is an implementation of a stack and is an intrinsic part of the C# runtime; it is an important component in the memory management of C# programs.


The stack has two main purposes: (1) to keep <font style="color:#b562f9">track</font> of the <font style="color:#b562f9">method</font> that control should return to once the currently <font style="color:#b562f9">executing</font> method has finished, (2) to <font style="color:#b562f9">hold</font> the <font style="color:#b562f9">values</font> of local variables (i.e. the variables that are not needed once their containing method finishes executing).

# Heap Data Structure:

"The heap" refers to the <font style="color:#b562f9">managed heap</font>, which, like the stack, plays an important (but different) role in the memory management of C# programs. The heap is an intrinsic part of the C# runtime and is an implementation of a heap data structure.

> [!attention] 
> The purpose of the heap is to store data that needs to outlive specific methods. This means the heap is used to store reference type variables, which are referred to as _objects_. 

# Difference:

Whereas the stack only allows items to be added and removed to/from the top, any item in a heap can be accessed at any time. This additional flexibility of the heap compared to the stack makes it a more complex data structure with higher overheads for managing the items that it holds.

# Reference Type:

The value of a reference type is a reference (or null), meaning the value of a reference type is the memory address of the object to which it refers. So, a reference type variable does not hold the value of the object it refers to, it holds a reference to that object.

``` run-csharp
Car car = new Car("bmw");
```

![[Pasted image 20230509170600.png]]

# Value Type:

A data type is a <font style="color:#b562f9">value type</font> if it holds a data value within its <font style="color:#b562f9">own memory space</font>. It means the variables of these data types directly contain values.

``` run-csharp
int x = 2;
```

![[Pasted image 20230509170913.png]]


# Where do variables get storaged?

C# variables are stored on either the <font style="color:#b562f9">stack</font> or <font style="color:#b562f9">heap</font>, which one depends on whether the variable is of <font style="color:#b562f9">reference</font> or <font style="color:#b562f9">value</font> type, and on the context in which the variable is declared.


> [!attention] 
>  -   <font style="color:#b562f9">Local variables</font> (i.e. those that are declared inside methods) are stored on the <font style="color:#b562f9">stack</font>. This means their values are stored on the stack, therefore meaning that local reference type variables have references stored on the stack and local value type variables have actual values stored on the stack.
>  - <font style="color:#b562f9">Objects</font> of <font style="color:#b562f9">reference</font> type variables (i.e. the things that references point to) always live on the <font style="color:#b562f9">heap</font>.
>  - <font style="color:#b562f9">Instance variables</font> that are part of a reference type instance (e.g. a field on a class) are stored on the <font style="color:#b562f9">heap</font> with the object itself
>  - Instance variables that are part of a value type instance are stored in the same context as the variable that declares the value type. This means that a variable of a struct that is declared in a method will live on the stack, whilst a variable of a struct that is declared inside a class (i.e. a field on the class) will live on the heap.

---
> [!example] 
>  ## Code Snippet

``` run-csharp
public class Car 
{ 
	public string manufacturer; 
	public int price; 
	
	public Car(string manufacturer, int price) 
	{ 
		this.manufacturer = manufacturer; this.price = price; 
	} 
}
```

``` run-csharp
static void Main(string[] args) 
{ 
	int price = 20000; 
	Car testCar = new Car("Audi", price); 
}
```

![[Pasted image 20230509171731.png]]

In the <font style="color:#b562f9">Main</font> method of this example we're declaring and initializing a <font style="color:#b562f9">local variable</font>, <font style="color:#b562f9">price</font>, of type <font style="color:#81fd83">int</font> (value type), we're then declaring a variable of type <font style="color:#b562f9">Car</font> (reference type), <font style="color:#b562f9">testCar</font>, and initializing it with a <font style="color:#81fd83">reference</font> to a `Car` object. 

- `price` is a local variable of value type, therefore it will live on the stack; 
- `testCar` is a local variable of reference type, therefore it will live on the stack, but, again, it's a reference type and so the thing stored on the stack is a reference (i.e. a memory address), as depicted in the diagram above. 
- The actual `Car` object that the reference in `testCar` points to lives on the heap.

---
References: [Memory Management](https://endjin.com/blog/2022/07/understanding-the-stack-and-heap-in-csharp-dotnet#:~:text=Whereas%20the%20stack%20only%20allows,the%20items%20that%20it%20holds.)