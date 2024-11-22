Status: 
Tag:
Links: [[301.4 Prototype Pattern]]

---
> [!note] 
>  # Copy Constructor

A <span style="color:#81fd83">Copy Constructor</span> allow you to create a new object as a copy of an existing object. Copy constructors come in handy when you need to duplicate an object, modify the new object without affecting the original, or pass objects by value in functions or methods.


> [!warning] 
> ## Problem: 

In software development, it’s often necessary to create new objects that are similar to existing ones, with only a few differences between those. 

Rather than creating these objects from scratch, a more efficient approach is to clone an existing one and make the necessary modifications to the copy.


> [!success] 
> ## Solution: 

``` run-csharp
public class Person
{
	public string[] Names;
	public Address Address;
	
	public Person(string[] names, Address address)
	{
		Names = names;
		Address = address;
	}
	
	public Person(Person other)
	{
		Names = other.Names;
		Address = other.Address;
	}
}
```

``` run-csharp
public class Address
{
	public string StreetName;
	public int HouseNumber;
	
	public Address(string streetName, int houseNumber)
	{
		StreetName = streetName;
		HouseNumber = houseNumber;
	}
	
	public Address(Address other)
	{
		Streetname = other.StreetName;
		HouseNumber = other.HouseNumber;
	}
}
```

---

``` run-csharp
public void Main(string[] args)
{
	Person john = new Person(new string[] {"John", "Smith"}, new Address("Little Rd", 7882));
	
	Person jane = new Person(john);
	jane.Names = new string[] {"Jane", "Doe"};
	jane.Address.HouseNumber = 5584;
}
```

![[Pasted image 20240615161844.png | center | 300]]

---
Reference: