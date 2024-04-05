Status: 
Tag: #ArrayDS
Links: [[200 Data Structures]] , [[102.1 Array]]

---
> [!note] 
>  # Array Implementation:

To store elements of any type in an Array, you can specify <span style="color:#81fd83">Object</span> as its type. In the  C#, all types, predefined and user-defined, reference types and value types, <span style="color:#ffff00">inherit</span> directly or indirectly from Object.
****
> [!important] 
> In C#, arrays are <span style="color:#ffff00">immutable</span> after creation. This means that you would need to create a separate array to allocate the space needed and then duplicate its content.

![[Array — Implementation.1.svg | 700]]

``` run-csharp
Class Array 
{
	public int length;
	private Object[] data;

	public Array()
	{
		this.length = 0;
		this.data = new Object[] {};
	}
}
```


---

#### Insert Data (End):

<span style="color:#81fd83">Push()</span> is a method that inserts an Object item at the <font style="color:#e493fb">end</font> of the Array. 
- It checks to see if there is room in the Array to insert the item otherwise it create a temporary Array to store the data to increase the size.


``` run-csharp
public Object[] Push(Object item)
{
    //Checks if there is room in Array to insert item
    if(data.Length == length)
    {
        Object[] temp = new Object[length];        
        System.Array.Copy(data, temp, length);     
        data = new Object[length + 1];              
        System.Array.Copy(temp, data, length);     
                
    }
        data[length] = item;
        length++;

        return data;
}
```


``` run-csharp
public static Main(string[] args)
{
	Array myArray = new Array();
	myArray.Push(1);
}
```


---

#### Insert Params Data (End)  
<font style="color:#b562f9">ParamsPush() </font>is a method using the '<font style="color:#81fd83">params</font>' keyword to insert any number of <font style="color:#81fd83">Object[]</font> items regardless of the type.  It is better practice than overloading the Push method.

``` run-csharp
Class Array 
{
	public int length;
	private Object[] data;

	public Array()
	{
		this.length = 0;
		this.data = new Object[] {};
	}
}
```

``` run-csharp
public Object[] ParamsPush(params Object[] item)
{
    foreach (Object obj in item)
    {
		// Checks if there is room in Array to insert item
	    if (data.Length == length)
	    {
		    Object[] temp = new Object[length];
		    System.Array.Copy(data, temp, length);
			data = new Object[length + 1];
			System.Array.Copy(temp, data, length);
		}
		data[length] = obj;
		length++;
	}
	return data;
}
```

``` run-csharp
static void Main(string[] args)
{
	Object myArray = new Array();
	myArray.Push("Hi");
	 myArray.Push(1202020);
				
	 myArray.ParamsPush("hi", 2, 3,2.2, 'c');
}
```

---

#### Access Index:
<font style="color:#b562f9">GetIndex()</font> is a method to <font style="color:#81fd83">access</font> the position of the Array at Index.

``` run-csharp
Class Array 
{
	public int length;
	private Object[] data;

	public Array()
	{
		this.length = 0;
		this.data = new Object[] {};
	}
}
```

``` run-csharp
public Object getIndex(int index)
{
    try
    {
        return data[index];
    }
	catch
    {
	    Console.WriteLine("Initialize Object[] before accessing index.");
    } 
    return null;
            
}
```

``` run-csharp
public static void Main(string[] args) 
{ 
	Object myArray = new Array(); 
	myArray.Push("Hi"); 
	myArray.Push(1202020); 
	myArray.ParamsPush("hi", 2, 3,2.2, 'c'); 
	Console.WriteLine(myArray.getIndex(6)); 
}
```

The <font style="color:#b562f9">Try-Catch</font> block is being used to throw an <font style="color:#e493fb">IndexOutOfRangeException</font> and to prevent the program from terminating early. 

---

#### Delete (End)

<font style="color:#b562f9">Pop()</font> is a method that removes the final item in the Array.

``` run-csharp
Class Array 
{
	public int length;
	private Object[] data;

	public Array()
	{
		this.length = 0;
		this.data = new Object[] {};
	}
}
```

``` run-csharp
public Object Pop()
{
	Object itemPopped = data[length - 1];
	
	//this.data[this.length - 1] = null;
	System.Array.Resize(ref data, data.Length - 1);
	
	length--;
	return itemPopped;
}
```

``` run-csharp
static void Main(string[] args)
{
	Object myArray = new Array();
	myArray.Push("Hi");
	myArray.Push(1202020);
			
	myArray.ParamsPush("hi", 2, 3,2.2, 'c');

	Console.WriteLine(myArray.getIndex(6));

	myArray.Pop();
 }
```

---
#### Delete (Index)

<font style="color:#b562f9">DeleteData()</font> is a method to delete Array Data at <font style="color:#81fd83">Index</font> while using <font style="color:#b562f9">ShiftItems()</font> method to shift the data.

``` run-csharp
Class Array 
{
	public int length;
	private Object[] data;

	public Array()
	{
		this.length = 0;
		this.data = new Object[] {};
	}
}
```

``` run-csharp
public Object DeleteData(int index)
{
    Object deletedItem = data[index];
    ShiftItems(index);

    return deletedItem;
}
```

``` run-csharp
public void ShiftItems(int index)
{
    for(int i = index; i < length - 1; i++)
    {
        // [0, 5, 6, 7] => [5, 6, 7, x]
        // Shifting item to left by 1
        data[i] = data[i + 1];
    }
    
    //this.data[this.length - 1] = null;
    System.Array.Resize(ref data, data.Length - 1);
    length--;
}
```

``` run-csharp
static void Main(string[] args)
{
	Object myArray = new Array();
	myArray.Push("Hi");
	myArray.Push(1202020);
		
	myArray.ParamsPush("hi", 2, 3,2.2, 'c');
	
	Console.WriteLine(myArray.getIndex(6));
	
	myArray.Pop();
	myArray.DeleteData(4);
}
```

---
References: 