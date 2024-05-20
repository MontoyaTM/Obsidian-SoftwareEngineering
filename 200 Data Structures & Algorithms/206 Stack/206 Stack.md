Status: 
Tag:
Links: [[200 Data Structures & Algorithms]]

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
public void Push(int data)
{
	Node curr = new Node(data);

	if(this.top == null)
	{
		top = curr;
		bottom = curr;
		length++;
		return;
	}

	node.next = top;
	top = node;
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
	if (this.top == null) throw
		new ArgumentNullException("Stack is empty; initialize to use method.");

	return this.top;
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
public Node Pop()
{
	if (this.top == null) throw
		new ArgumentNullException("Stack is empty; initialize to use method.");

	Node pop = this.top;
	top = top.next;
	length--;
	
	return pop;
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