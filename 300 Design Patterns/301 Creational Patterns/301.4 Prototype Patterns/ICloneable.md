Status: 
Tag:
Links: [[301.4 Prototype Pattern]]

---
> [!note] 
>  # ICloneable

The <span style="color:#81fd83">ICloneable</span> interface simply requires that your implementation of the Clone() method return a copy of the current object instance.


> [!warning] 
> ## Problem: 

In software development, it’s often necessary to create new objects that are similar to existing ones, with only a few differences between those. 

Rather than creating these objects from scratch, a more efficient approach is to clone an existing one and make the necessary modifications to the copy.


> [!success] 
> ## Solution: 

``` run-csharp
public class Person : ICloneable
{
	public string[] Names;
	public Address Address;
	
	public Person(string[] names, Address address)
	{
		Names = names;
		Address = address;
	}
	
	public object Clone()
	{
		return new Person(Names, (Address) Address.Clone());
	}
}
```

``` run-csharp
public class Address : ICloneable
{
	public string StreetName;
	public int HouseNumber;
	
	public Address(string streetName, int houseNumber)
	{
		StreetName = streetname;
		HouseNumber = houseNumber;
	}
	
	public object Clone()
	{
		return new Address(StreetName, HouseNumber);
	}
}
```

``` run-csharp
public void Main(string[] args)
{
	var john = new Person(new string[] {"John", "Smith"},
		new Address("Little Rd", 7882));
	
	var jane = john;
	jane.Address.HouseNumber = 321;
	
	Console.WriteLine(john);
	Console.WriteLine(jane);
}
```

_Note: The ICloneable is not always a good option as it does not offer a deep clone or can be difficult to hand when copying complex classes._

---
References: https://medium.com/@iamprovidence/implement-icloneable-as-a-senior-327f31de5f25