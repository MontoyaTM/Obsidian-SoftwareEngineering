Status: 
Tag:
Links: [[200 Data Structures & Algorithms]]

---
> [!note] 
>  # Binary Heap


A Minimum Binary Heap in C# is a data structure that satisfies the heap property and is implemented using a binary tree.

![[Pasted image 20230717112913.png]]

## Binary Heap

In a minimum binary heap:
- <span style="color:#81fd83">Heap Property</span>: Every node's value is less than or equal to the values of its children (if any).
- <span style="color:#81fd83">Binary Tree Structure</span>: It's a complete binary tree, which means all levels except possibly the last are fully filled, and the last level is filled from left to right.

![[Minimum Binary Heap.svg| 650]]

``` run-csharp
public class BinarySearchTree
{
	private int[] heap;
	private int capacity { get; set; }
	private int size;

	public BinarySearchTree()
	{
		this.capacity = 10;
		this.size = 0;
		this.heap = new int[capacity];
	}
}
```

![[Minimum Binary Heap — Index.svg| 500]]
## ParentIndex()

``` run-csharp
public int ParentIndex(int index)
{
	return (index - 1) / 2;
}
```

## LeftChildIndex()

``` run-csharp
public int LeftChildIndex(int index)
{
	return (index * 2) + 1;
}
```

## RightChildIndex()

``` run-csharp
public int RightChildIndex(int index)
{
	return (index * 2) + 2;
}
```

## hasParent()

``` run-csharp 
public bool hasParent(int index)
{
	return ParentIndex(index) >= 0;
}
```

## hasLeftChild()

``` run-csharp 
public bool hasLeftChild(int index)
{
	return LeftChildIndex(index) < size;
}
```

## hasRightChild()

``` run-csharp
public bool hasRightChild(int index)
{
	return RightChildIndex(index) < size;
}
```

## Parent()

``` run-csharp
public int Parent(int index)
{
	return heap[ParentIndex];
}
```

## LeftChild()

``` run-csharp
public int LeftChild(int index)
{
	return heap[LeftChildIndex];
}
```

## RightChild()

``` run-csharp
public int RightChild(int index)
{
	return heap[RightChildIndex];
}
```

## Peek()

``` run-csharp
public int Peek(int index)
{
	if(size == 0) throw new InvalidOperationException();
	
	return heap[0];
}
```

## Swap()

This functions swaps the integer values from 2 position within the heap array.

``` run-csharp
public void Swap(int indexOne, int indexTwo)
{
	int temp = heap[indexOne];
	heap[indexOne] = heap[indexTwo];
	heap[indexTwo] = temp;
}
```

![[Minimum Binary Heap — Swap().svg | 750]]

## ExtraCapacity()

This function doubles the capacity of the Binary Heap in cases where size is equal to capacity.

``` run-csharp 
public void ExtraCapacity()
{
	if(size == capacity)
	{
		int[] target = new int[capacity * 2];
		minHeap.CopyTo(target, 0);
		minHeap = target;
		capacity *= 2;
	}
}
```

![[Minimum Binary Heap — ExtraCapacity().svg]]

## Add()

This functions added an integer value into the Heap array while determining if extra capacity is needed and whether the value needs to be heapified upwards.

``` run-csharp
public void Add(int value)
{
	ExtraCapacity();
	minHeap[size] = value;
	size++;
	HeapifyUp();
}
```

``` run-csharp
public static void Main(string[] args)
{
	BinaryHeap minHeap = new BinaryHeap();

	minHeap.Add(5);
	minHeap.Add(10);
	minHeap.Add(15);
	minHeap.Add(8);
}
```


![[Minimum Binary Heap — Add().svg]]


## Poll()

``` run-csharp
public int Poll()
{
	if(size == 0) throw new InvalidOperationException();

	int value = minHeap[0];
	minHeap[0] = minHeap[size - 1];
	size--;
	HeapifyDown();

	return value;
}
```


![[Minimum Binary Heap — Poll().svg]]



> [!note] 
>  # Minimum Binary Heap

## HeapifyUp()

``` run-csharp
public void HeapifyUp()
{
	int index  = size - 1;
	while(hasParent(index) && Parent(index) > heap[index])
	{
		Swap(ParentIndex(index), index);
		index = ParentIndex(index);
	}
}
```

![[Minimum Binary Heap — HeapifyUp().svg]]

## HeapifyDown()

``` run-csharp
public void HeapifyDown()
{
	int index = 0;
	
	while(hasLeftChild(index))
	{
		int smallerChildIndex = LeftChildIndex(index);
		
		if(hasRightChild(index) && RightChild(index) < LeftChildIndex(index))
		{
			smallerChildIndex = RightChildIndex(index);
		}
		
		if(minHeap[smallerChildIndex] >= minHeap[index])
		{
			break;
		} 
		
		Swap(index, smallerChildIndex);
		
		index = smallerChildIndex;
	}
}
```

![[Minimum Binary Heap — HeapifyDown().svg]]


> [!note] 
>  # Maximum Binary Heap

## HeapifyUp()

``` run-csharp 
public void HeapifyUp()
{
	int index = size - 1;
	
	while(hasParent(index) && maxHeap[index] > Parent(index))
	{
		Swap(ParentIndex(index), index);
		index = ParentIndex(index);
	}
}
```


![[Maximum Binary Heap — HeapifyUp().svg]]


## HeapifyDown()

``` run-csharp
public void HeapifyDown()
{
	int index = 0;
	
	while(hasLeftChild(index))
	{
		int biggerChildIndex = LeftChildIndex(index);
		
		if(hasRightChild(index) && RightChild(index) > LeftChild(index))
		{
			biggerChildIndex = RightChildIndex(index);
		}
		
		if(maxHeap[biggerchildIndex] < maxHeap[index])
		{
			break;
		}
		
		
	}
}
```


![[Maximum Binary Heap — HeapifyDown().svg]]

---
References: https://www.geeksforgeeks.org/introduction-to-heap-data-structure-and-algorithm-tutorials/, https://www.youtube.com/watch?v=t0Cq6tVNRBA, https://egorikas.com/max-and-min-heap-implementation-with-csharp/