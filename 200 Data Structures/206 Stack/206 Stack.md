Status: 
Tag:
Links: [[200 Data Structures]]

---
> [!note] 
>  # Stack Implementation

A <span style="color:#b562f9">Stack</span> is a fundamental <span style="color:#81fd83">data structure</span> in computer science that follows the <span style="color:#81fd83">Last-In-First-Out</span> (<span style="color:#b562f9">LIFO</span>) principle. 

![[Pasted image 20230717112913.png]]

> [!info] 
> ## Node

A <span style="color:#b562f9">Node</span> is a fundamental building block that is used to implement various data structures such as the <span style="color:#b562f9">Stack</span>. 
- <span style="color:#81fd83">Data</span> — This component contains the actual data type information associated with the node.
- <span style="color:#81fd83">Next</span> — This component contains a reference to the following Node in the Stack. This component is a valuable tool for traversing the Stack.

![[Stack — Node().1.svg | 300]]

``` run-csharp
public class Node
{
	public int data;
	public Node next;

	public Node(int data)
	{
		this.data = data;
		this.next = null;
	}
}
```

> [!info] 
> ## Stack 

A <span style="color:#b562f9">Stack</span> requires each new item to be placed at the top, where this item can only be removed first. To remove items below the top, each item has to be removed individually.

![[Stack — Stack().1.svg | 500]]

``` run-csharp
public class Stack
{
	public Node top;
	public Node bottom;
	public int length;

	public Stack()
	{
		this.top = null;
		this.bottom = null;
		this.length = 0;
	}

	public bool isEmpty()
	{
		return this.length == 0;
	}
}
```

``` run-csharp
public static void Main(string[] args)
{
	Stack stack = new Stack();
}
```


## Push() 

<span style="color:#81fd83">Push()</span> is a method that receives an integer parameter, <span style="color:#b562f9">value</span>, that will be used to create a Node to be inserted at the top of the Stack.

![[Stack — Push().1.svg | 600]]

``` run-csharp
public void Push(int value)
{
	Node curr = new Node(value);

	if(isEmpty)
	{
		this.top = curr;
		this.bottom = curr;
		this.length++;
		return;
	}

	Node beneath = this.top;
	this.top = node;
	this.top.next = beneath;
	this.length++;
}
```

![[Stack — Push().2.svg | 600]]
``` run-csharp
public static void Main(string[] args)
{
	Stack stack = new Stack();
	stack.push(1);
	stack.push(2);
	stack.push(3);
	stack.push(4);
}
```

![[Stack — Push().3.svg | 400]]

## Peek()

<span style="color:#81fd83">Peek()</span> is a method that displays the top Node in the stack using the <span style="color:#b562f9">ToString()</span> method.

``` run-csharp
public void Peek()
{
	if(isEmpty)
	{
		throw new Exception("There is no data in the stack!")
	} else 
	{
		Console.WriteLine(this.top.ToString());
	}
}
```

![[Stack — Push().3.svg | 400]]

``` run-csharp
public static void Main(string[] args)
{
	Stack stack = new Stack();
	stack.push(1);
	stack.push(2);
	stack.push(3);
	stack.push(4);
	stack.peek();
}
```

![[Stack — Peek().1.svg | 250]]

## Pop()

<span style="color:#81fd83">Pop()</span> is a method that removes the top <span style="color:#b562f9">Node</span> in the Stack.

![[Stack — Push().3.svg | 400]]

``` run-csharp
public void Pop()
{
	if(isEmpty)
	{
		Console.WriteLine("The stack is empty!")
		return;
	}
	Node popped = this.top;
	this.top = this.top.next;
	this.length--;

	Console.WriteLine(popped.ToString());
}
```

![[Stack — Pop().1.svg | 700]]
``` run-csharp
public static void Main(string[] args)
{
	Stack stack = new Stack();
	stack.push(1);
	stack.push(2);
	stack.push(3);
	stack.push(4);
	stack.peek();
	stack.pop();	
}
```

![[Stack — Pop().2.svg | 250]]

---
References: