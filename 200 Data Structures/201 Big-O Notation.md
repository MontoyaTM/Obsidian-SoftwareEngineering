Status: 
Tag: #Big-O #Notation
Links: [[200 Data Structures]]

---
> [!note] 
>  # Big-O Notation

<font style="color:#b562f9">Big-O notation</font> is a <font style="color:#81fd83">mathematical notation</font> used in computer science to describe the <font style="color:#81fd83">performance</font> characteristics of <font style="color:#b562f9">algorithms</font>. It provides a way to analyze and compare the efficiency of algorithms in terms of how their execution <font style="color:#81fd83">time</font> or <font style="color:#81fd83">space</font> requirements grow with respect to the input size.

![[Pasted image 20230607210015.png]]

---
> [!example] 
>  ## 0(1) — Constant

Constant time complexity. The algorithm's <font style="color:#b562f9">performance</font> remains <font style="color:#81fd83">constant</font> regardless of the input size.

``` run-csharp
// Assignment
var test = 0;

// Declaration
var test;

// Arithmetic
2 + 2;

// Comparison
2 > 1;

// Accessing Element
array[1];

// Calling Functions
someFunction();

```


``` run-csharp
public void InsertFirst(int data)
{
	// Create the Node
	Node newNoe = new Node();
	
	//Put the data in the node
	newNode.Data = data;

	// Put the old node in next
	newNode.Next = First;

	// Make first the new node
	First = newNode;
}
```

> [!example] 
> ## O(N) — Linear 

Linear time complexity. The algorithm's <font style="color:#b562f9">performance</font> scales <font style="color:#81fd83">linearly</font> with the input size.
- Loops
	- Number of inputs increase time

``` run-csharp
int total = 0;
int i = 2;

while(i <= 10) 
{
	total += i;
	i += 1;
}
```

> [!example] 
> ## O(N^2) — Quadratic

Quadratic time complexity. The algorithm's <font style="color:#b562f9">performance</font> is directly proportional to the <font style="color:#81fd83">square</font> of the input size.
- Nested Loops

``` run-csharp
var n = int.Parse(Console.ReadLine());

for(var r = 1; r <= n; r++) 
{
	for(var c = 1; c <= n; c++)
	{
		Console.Write("-");
	}
	Console.WriteLine();
}
```

Big-O notation focuses on the dominant term or the highest order term in the algorithm's complexity expression, discarding lower-order terms and constants.

---
References: [Road Map](https://www.codingninjas.com/codestudio/library/complete-data-structures-and-algorithms-roadmap-for-placements)