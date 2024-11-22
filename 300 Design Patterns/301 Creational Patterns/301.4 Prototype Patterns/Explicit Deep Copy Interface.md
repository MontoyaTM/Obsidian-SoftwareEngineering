Status: 
Tag:
Links: [[301.4 Prototype Pattern]]

---
> [!note] 
>  # Explicit Deep Copy Interface

Similarly to the ICloneable; we create an interface called <span style="color:#81fd83">IPrototype</span> that has one method——DeepCopy(). This method will return the correct object instance instead of the default object.

> [!warning] 
> ## Problem: 

In software development, it’s often necessary to create new objects that are similar to existing ones, with only a few differences between those. 

Rather than creating these objects from scratch, a more efficient approach is to clone an existing one and make the necessary modifications to the copy.


> [!success] 
> ## Solution: 

``` run-csharp
public interface IPrototype<T>
{
	T DeepCopy();
}
```

``` run-csharp
public class Person : IPrototype<Person>
{
	public string[] Names;
	public Address Address;
	
	public Person(string[] names, Address address)
	{
		Names = names;
		Address = address;
	}
	
	public Person DeepCopy()
	{
		return new Address(Names, Address.DeepCopy());
	}
}
```

``` run-csharp
public class Address : IPrototype<Address>
{
	public string StreetName;
	public int HouseNumber;
	
	public Address(string streetName, int houseNumber)
	{
		StreetName = streetName;
		HouseNumber = houseNumber;
	}
	
	public Address DeepCopy()
	{
		return new Address(StreetName, HouseNumber);
	}
	
}
```

---

``` run-csharp
public void Main(string[] args)
{
	Person john = new Person(new string[] {"John", "Smith"}, new Address("Little Rd", 7882));
	
	Person jane = john.DeepCopy();
	jane.Names = new string[] {"Jane", "Doe"};
	jane.Address.HouseNumber = 5584;
}
```

![[Pasted image 20240615161844.png | center | 300]]

---
References: