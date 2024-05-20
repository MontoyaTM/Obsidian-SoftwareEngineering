Status: 
Tag:
Links: [[200 Data Structures & Algorithms]]

---
> [!note] 
>  # Queue Implementation


In C#, a <span style="color:#b562f9">Queue</span> is a <span style="color:#81fd83">linear data structure</span> that follows the <span style="color:#81fd83">First-In-First-Out (FIFO)</span> principle. This means that the first element added to the queue will be the first one to be removed.


![[Pasted image 20230717112913.png]]


> [!note] 
> ## Node 

A <span style="color:#b562f9">Node</span> is a fundamental building block that is used to implement various data structures such as the <span style="color:#b562f9">Queue</span>. 
- <span style="color:#81fd83">Data</span> — This component contains the actual data type information associated with the node.
- <span style="color:#81fd83">Next</span> — This component contains a reference to the following Node in the Queue. This component is a valuable tool for traversing the Queue.

![[Queue — Node().svg | 350]]

``` run-csharp
public class Node
{
	int data;
	Node next;

	public Node (int data)
	{
		this.data = data;
		this.next = null;
	}
}
```


> [!note] 
> ## Queue 

<span style="color:#b562f9">Queues</span> are commonly used to manage tasks in a <span style="color:#b562f9">sequential order</span>, such as <span style="color:#81fd83">scheduling</span>, <span style="color:#81fd83">task processing,</span> or implementing <span style="color:#81fd83">breadth-first search algorithms</span>.


![[Queue — Queue().svg | 900]]

``` run-csharp
public class Queue
{
	Node first;
	Node last;
	int length;

	public Queue()
	{
		this.first = null;
		this.last = null;
		this.length = 0;
	}
}
```

``` run-csharp
public static void Main(string[] args)
{
	Queue queue = new Queue();
}
```


## Enqueue()

![[Queue — Enqueue().1.svg| 800]]

<span style="color:#81fd83">Enqueue()</span> is a method that receives an integer parameter, <span style="color:#b562f9">data</span>, that will be used to create a Node to be inserted at the end of the Queue.

``` run-csharp
public void Enqueue(int data)
{
	Node node = new Node(data);
	
	if(this.first == null)
	{
		this.first = node;
		this.last = node;
		this.length++;
		return;
	}

	this.last.next = node;
	this.last = node;
	this.length++;
}
```

![[Queue — Enqueue().2.svg | 1000]]

``` run-csharp
public static void Main(string[] args)
{
	Queue queue = new Queue();
	queue.Enqueue(1);
	queue.Enqueue(5);
	queue.Enqueue(10);
	queue.Enqueue(15);
	queue.Enqueue(20);
}
```


## Dequeue()

![[Queue — Enqueue().2.svg | 1000]]

<span style="color:#81fd83">Dequeue() </span>is a method that removed the node at the front of the queue. The dequeued node's next pointer will become the new first node pointer.

``` run-csharp
public Node Dequeue()
{
	if (this.first == null) throw
		new ArgumentNullException("Queue is empty; initialize to use method.");

	Node dequeued = this.first;
	this.first = dequeued.next;
	this.length--;

	return dequeued;
}
```

``` run-csharp

public static void Main(string[] args)
{
	Queue queue = new Queue();
	queue.Enqueue(1);
	queue.Enqueue(5);
	queue.Enqueue(10);
	queue.Enqueue(15);
	queue.Enqueue(20);

	queue.Dequeue();
}

```


![[Queue — Dequeue().svg | 1000]]


---
References: