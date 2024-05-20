Status: 
Tag:
Links: [[200 Data Structures & Algorithms]]

---
> [!note] 
>  # Graph

In C#, a graph data structure can be implemented using various approaches, such as using adjacency lists or adjacency matrices.

![[Pasted image 20240509200309.png | 1000]]
![[Pasted image 20240509200736.png | 1000]]


> [!note] 
>  # Abstract Class BaseGraph

The BaseGraph class will be an abstract class used to implement two variations of the Graph Data Structure:
- Adjacency Matrix
- Adjacency List


``` run-csharp
public abstract class BaseGraph
{
	protected readonly int numVerticies;
	protected readonly bool directed;
	
	public BaseGraph(int numVerticies, bool directed = false)
	{
		this.numVerticies = numVerticies;
		this.directed = directed;
	}
	
	public abstract void AddEdge(vertexOne, int vertexTwo, int weight);
	public abstract IEnumerable<int> GetAdjacencyVerticies(int vertex);
	public abstact int GetEdgeWeight(int vertexOne, int vertexTwo);
	public abstract void Display();
	public int NumVerticies {get {return this.numVerticies;} }
}
```


> [!note] 
>  # Adjacency Matrix Graph

In the _adjacency matrix_ representation, we will use a matrix structure to represent our graph. Indices of row and column will represent the vertices and the values in each cell represent edges.

![[Adjacency Matrix Graph — Graph.svg]]



``` run-csharp
public class AdjacencyMatrixGraph : BaseGraph
{
	private int[,] Matrix;
	
	public AdjacencyMatrixGraph(int numVerticies, bool directed = false) : base(numVerticies, directed)
	{
		GenerateEmptyMatrix(numVerticies);
	}
}
```

``` run-csharp
public static void Main(string[] args)
{
	var adjacencyMatrix = mew AdjacencyMatrixGraph(7, true);
	
	adjacencyMatrixGraph.AddEdge(0, 2);
	adjacencyMatrixGraph.AddEdge(1, 3);
	adjacencyMatrixGraph.AddEdge(1, 4);
	adjacencyMatrixGraph.AddEdge(2, 5);
	adjacencyMatrixGraph.AddEdge(3, 5);
	adjacencyMatrixGraph.AddEdge(4, 6);
	adjacencyMatrixGraph.AddEdge(6, 7);
}
```

![[Adjacency Matrix Graph — Matrix.svg]]

## GenerateEmptyMatrix()

This methods creates a 2-dimensional empty matrix with values of zero.

``` run-csharp
public void GenerateEmptyMatrix(int numVerticies)
{
	this.Matrix = new int[numVerticies, numVerticies];
	
	for(int row = 0; row < numVerticies; row++)
	{
		for(int col = 0; col < numVerticies; col++)
		{
			this.Matrix[row, col] = 0;
		}
	}
}
```


![[Adjacency Matrix Graph — GenerateEmptyMatrix().svg| 700]]


## AddEdge()

AddEdge() method has two parameters, vertex one and vertex two, that will be used to link both vertices by an edge weight.

``` run-csharp
public override void AddEdge(int vertexOne, int vertexTwo, int weight = 1)
{
	if(vertexOne >= this.numVerticies || vertexTwo >= this.numVerticies || vertexOne < 0 || vertexTwo < 0)
			throw new ArgumentOutOfRangeException("Verticies are out of bounds.");
	
	if (weight < 1) throw new ArgumentException("Weight cannot be less than 1");
	
	this.Matrix[vertexOne, vertexTwo] = weight;
	
	if(!this.Directed)
	{
		this.Matrix[vertexTwo, vertexOne] = weight;
	}
}
```

``` run-csharp
public static void Main(string[] args)
{
	var adjacencyMatrix = mew AdjacencyMatrixGraph(7, true);
	
	adjacencyMatrixGraph.AddEdge(0, 2);
}
```

![[Adjacency Matrix Graph — AddEdge().svg| 800]]

## GetAdjacencyVerticies()

GetAdjacencyVerticies() method receives an integer value, vertex. The row corresponding to the value within the matrix will be looped through to find additional vertex connected to the vertex received. 

``` run-csharp
public override IEnumerable<int> GetAdjacencyVerticies(int vertex)
{
	if(vertex < 0 || vertex >= this.numVerticies) 
		throw new ArguementOutOfRangeException("Cannot access vertex!");
		
	List<int> adjacentVerticies = new List<int>();
	
	for(int i = 0; i < this.numVerticies; i++)
	{
		if(this.Matrix[vertex, i] > 0)
		{
			adjacentVerticies.Add(i);
		}
	}
	
	return adjacentVerticies;
}
```

![[Adjacency Matrix Graph — GetAdjacencyVerticies().svg | 800]]

## GetEdgeWeight()

``` run-csharp
public override int GetEdgeWeight(int vertexOne, int vertexTwo)
{
	return this.Matrix(vertexOne, vertexTwo);
}
```

## Display()

``` run-csharp
public override void Display()
{
	Console.WriteLine("===============================");
	Console.WriteLine("Adjacency Matrux Graph:");
	Console.WriteLine("===============================");
	Console.Write("Nodes  ");

	for (int i = 0; i < this.NumVerticies; i++)
	{
		Console.Write(string.Format("{0}  ", i));
	}

	Console.Write("\n");

	for (int row = 0; row < this.NumVerticies; row++)
	{
		Console.Write(string.Format("{0} | [ ", row));

		for(int col = 0; col < this.NumVerticies; col++)
		{
			if(row == col)
			{
				Console.Write(" x ");
			} 
			else if (this.Matrix[row, col] == 0)
			{
				Console.Write(" . ");
			}
			else
			{
				Console.Write(string.Format(" {0} ", this.Matrix[row, col]));
			}
		}
		Console.Write(" ]\r\n");
	}
	Console.ReadLine();
}
```

``` run-csharp
===============================
Adjacency Matrix Graph:
===============================
Nodes  0  1  2  3  4  5  6  7
0 | [  x  .  1  .  .  .  .  .  ]
1 | [  .  x  .  1  1  .  .  .  ]
2 | [  .  .  x  .  .  1  .  .  ]
3 | [  .  .  .  x  .  1  .  .  ]
4 | [  .  .  .  .  x  .  1  .  ]
5 | [  .  .  .  .  .  x  .  .  ]
6 | [  .  .  .  .  .  .  x  1  ]
7 | [  .  .  .  .  .  .  .  x  ]
```


> [!note] 
>  # Adjacency List Graph

``` run-csharp 
public class AdjacencytListGraph : BaseGraph
{
	private LinkedList<Tuple<int, int>>[] adjacencyList;
	
	public AdjacencyListGraph(int numVerticies, bool directed = false)
	{
		GenerateEmptyList(numVerticies);
	}	
}
```

``` run-csharp
public static void Main(string[] args)
{
	var adjacencyListGraph = new AdjacencyListGraph(8, true);
	
	adjacencyListGraph.AddEdge(0, 2);
	adjacencyListGraph.AddEdge(1, 3);
	adjacencyListGraph.AddEdge(1, 4);
	adjacencyListGraph.AddEdge(2, 5);
	adjacencyListGraph.AddEdge(3, 5);
	adjacencyListGraph.AddEdge(4, 6);
	adjacencyListGraph.AddEdge(6, 7);
}
```


![[Adjacency List Graph.svg| 500]]

## GenerateEmptyList()

``` run-csharp
public void GenerateEmptyList(int numVerticies)
{
	adjacencyList = new LinkedList<Tuple<int, int>>[numVerticies];

	for(int i = 0; i < numVerticies; i++)
	{
		adjacencyList[i] = new LinkedList<Tuple<int, int>>();
	}
}
```

## AddEdge()

``` run-csharp
public override void AddEdge(int vertexOne, int vertexTwo, int weight = 1)
{
	if (vertexOne >= this.numVerticies || vertexTwo >= this.numVerticies || vertexOne < 0 || vertexTwo < 0)
		throw new ArgumentOutOfRangeException("Verticies are out of bounds.");

	if (weight < 1) throw new ArgumentException("Weight cannot be less than 1");


	this.adjacencyList[vertexOne].AddLast(new Tuple<int, int>(vertexTwo, weight));

	if(!Directed)
	{
		this.adjacencyList[vertexTwo].AddLast(new Tuple<int, int>(vertexOne, weight));
	}
}
```


![[Adjacency List Graph — AddEdge().svg]]



## GetAdjacencyVerticies()

``` run-csharp
public override IEnumerable<int> GetAdjacencyVertices(int vertex)
{
	if (vertex < 0 || vertex >= this.numVerticies)
		throw new ArgumentOutOfRangeException("Cannot access vertex!");

	List<int> adjacentVerticies = new List<int>();

	foreach(var item in this.adjacencyList[vertex])
	{
		if(item.Item2 > 0)
		{
			adjacentVerticies.Add(item.Item1);
		}
	}

	return adjacentVerticies;
}
```

## GetEdgeWeight()

``` run-csharp
public override int GetEdgeWeight(int vertexOne, int vertexTwo)
{
	int weight = -1;
	
	foreach (var item in adjacencyList[vertexOne])
	{
		if(item.Item1 == vertexTwo)
		{
			weight = item.Item2;
		}
	}

	return weight;
}
```

## Display()

``` run-csharp
public override void Display()
{
	Console.WriteLine("===============================");
	Console.WriteLine("Adjacency List Graph:");
	Console.WriteLine("===============================");

	int i = 0;

	foreach (var list in adjacencyList)
	{
		Console.Write("Node[ " + i + " ] -> ");

		foreach (var edge in list)
		{
			Console.Write(edge.Item1 + "(" + edge.Item2 + ") ->");
		}

		i++;
		Console.WriteLine();
	}
}
```

``` run-csharp
===============================
Adjacency List Graph:
===============================
Node[ 0 ] -> 2(1) ->
Node[ 1 ] -> 3(1) -> 4(1) ->
Node[ 2 ] -> 5(1) ->
Node[ 3 ] -> 5(1) ->
Node[ 4 ] -> 6(1) ->
Node[ 5 ] ->
Node[ 6 ] -> 7(1) ->
Node[ 7 ] ->
```

---
References: https://dev.to/russianguycoding/how-to-represent-a-graph-in-c-4cmo, https://theoryofprogramming.wordpress.com/adjacency-list-in-c-sharp/