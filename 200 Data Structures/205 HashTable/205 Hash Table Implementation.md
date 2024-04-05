wStatus: 
Tag: #HashTableDS
Links: [[200 Data Structures]]

---
> [!note] 
>  # HashTable Implementation

In C#, a <font style="color:#b562f9">HashTable</font> is a data structure that stores <span style="color:#81fd83">key/value pairs</span> that are arranged based on the HashCode of each key. It provides a <font style="color:#81fd83">fast</font> way to <font style="color:#81fd83">access</font> values based on their corresponding <font style="color:#b562f9">keys</font>. 

- When you <span style="color:#81fd83">store</span> a <span style="color:#81fd83">value</span> in a HashtTable, you associate it with a <span style="color:#b562f9">unique key</span>. Later, you can retrieve the value by providing the key, and the HashtTable will quickly locate the corresponding value.



![[Pasted image 20230717112913.png]]

> [!info] 
> ## Node 

A <font style="color:#81fd83">Node </font>is a fundamental building block that is used to implement various data structures such as the Hash Table A <font style="color:#81fd83">Node</font> contains:
- <span style="color:#b562f9">Key</span> — The key is a unique value which helps in storing data that is formed by using a Hashing Function.
- <span style="color:#b562f9">Value</span> — The value is essentially the data that is stored based on the location computed by the key.
- <span style="color:#b562f9">Next</span> — The next is a reference to the following chaining Node.

![[HashTable — Node.svg | 300]]
``` run-csharp
public class Node 
{
	public string key;
	public int value;
	public Node next;

	public Node(string key, int value)
	{
		this.key = key;
		this.value = value;
		this.next = null;
	}
}
```

> [!info] 
> # HashTable
> 

A <span style="color:#b562f9">HashTable</span> in C# is a data structure that stores <span style="color:#81fd83">key-value pairs</span> in a way that allows for <span style="color:#b562f9">efficient</span> <span style="color:#81fd83">insertion</span>, <span style="color:#81fd83">retrieval</span>, and <span style="color:#81fd83">deletion</span> of elements.

The class <span style="color:#b562f9">HashTable</span> consists of an Array of Nodes of size declared by its constructor parameter. The <span style="color:#b562f9">length</span> variable is equal to the <span style="color:#81fd83">size</span> of the HashTable and its <span style="color:#b562f9">quantity</span> denotes the<span style="color:#81fd83"> number of individual Nodes</span> within the HashTable. 

``` run-csharp
public class HashTable
{
	Node[] _buckets;

	public HashTable(int size)
	{
		_buckets = new Node[size];
	}
}
```

``` run-csharp
static void Main(string[] args) 
{ 
	HashTable hashTable = new HashTable(10); 
}
```

![[HashTable — HashTable{}.svg | 400]]

## Hash() 

<span style="color:#b562f9">Hash() </span>is a function that takes an input, <span style="color:#b562f9">key</span>, and returns a <span style="color:#81fd83">fixed-size integer value</span>. The value is passed through a while loop that retrieves the <span style="color:#81fd83">UTF-16 encoding</span> for the char at position "<span style="color:#b562f9">i</span>" of the string key. 

The encoding received is used within an algorithm to return an integer value within the range of the HashTable. 

![[HashTable — HashKey().1.svg | 550]]

``` run-csharp
public int Hash(string key)
{
	int hashedKey = 0;
	
	for(int i - 0; i < key.Length; i++)
	{
		hash = (hash + (int)key[i] * i) % this.length;
	}
	
	return hash;
}
```

![[HashTable — HashKey().2.svg | 400]]
## Set()

<span style="color:#b562f9">Set() </span>is a function that receives a string(<span style="color:#81fd83">key</span>) and an integer(<span style="color:#81fd83">value</span>) for insertion to the HashTable. The key parameter will be used to determine the <span style="color:#b562f9">index</span> within the HashTable using the <span style="color:#b562f9">HashKey() </span>function.

A while loop is incorporated to first determine whether the key already exists within the index of the HashTable. If it exist then the value will get replaced and the function will return.

``` run-csharp
public void Set(string key, int value)
{
	int index = Hash(key);
	Node curr = _buckets[index];
	Node node = new Node(key, value);
	
	if(curr == null)
	{
		_buckets[index] = node;
		return;
	}

	While(curr != null)
	{
		if(curr.key.Equals(key))
		{
			curr.value = value;
			return;
		}
		curr = curr.next;
	}

	curr = _buckets[index];
	node.next = curr;
	_buckets[index] = node;
}
```

![[HashTable — Put().1.svg | 600]]

``` run-csharp
static void Main(string[] args) 
{ 
	HashTable hashTable = new HashTable(10); 
	hashTable.Put("Montoya");
}
```

![[HashTable — Put().2.svg | 600]]

## Get

Get() is a function that receives a string key to be hashed so that the index in the buckets array can be found; assuming it exists.

``` run-csharp

public int? Get(string key)
{
	int index = Hash(key);
	Node curr = _buckets[index];

	if(curr == null) throw
		new ArgumentOutOfRangeException($"{key}: was not found!"); 

	while(curr != null)
	{
		if(curr.key.Equals(key))
		{
			return curr.value;
		}
		curr = curr.next;
	}

	return curr.value;
}


```

``` run-csharp
static void Main(string[] args) 
{ 
	HashTable hashTable = new HashTable(10); 
	hashTable.Get("Montoya");
}
```

![[HashTable — Put().2.svg | 600]]

## Remove()

<span style="color:#b562f9">Remove()</span> is a method that receives a string(<span style="color:#81fd83">key</span>) that will be hashed using the <span style="color:#b562f9">HashKey()</span> function to retrieve its <span style="color:#81fd83">index</span> in the HashTable.

<span style="color:#b562f9">Remove()</span> contains a <span style="color:#b562f9">while</span> loop to find the <span style="color:#81fd83">Node—LinkedList</span>  at the index while also using a second Node to hold the position of the <span style="color:#81fd83">previous Node</span>. The loop will terminate whether the key is found in the Node(<span style="color:#81fd83">index</span>).


![[HashTable — Remove().1.svg | 700]]

``` run-csharp
public void Remove(string key)
{
	int index = Hash(key);
	Node curr = _buckets[index];
	Node prev = null;

	if(curr == null) throw
		new ArgumentOutOfRangeException($"{key}: was not found!"); 
		
	while(curr != null)
	{
		if(curr.key.Equals(key))
		{
			break;
		}
		prev = curr;
		curr = curr.next;
	}

	if(prev != null)
	{
		prev.next = curr.next;
	} else 
	{
		_buckets[index] = curr.next;
	}
}
```

![[HashTable — Remove().2.svg | 900]]


``` run-csharp
static void Main(string[] args) 
{ 
	HashTable hashTable = new HashTable(10); 
	hashTable.Put("Montoya");
	.
	.
	.
	hashTable.Remove("Maddie");
}
```

![[HashTable — Remove().3.svg | 700]]

---
References: