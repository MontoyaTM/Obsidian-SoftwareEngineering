Status: 
Tag:
Links: [[301.4 Prototype Pattern]]

---
> [!note] 
>  # Prototype Interface




> [!warning] 
> ## Problem: 

In software development, it’s often necessary to create new objects that are similar to existing ones, with only a few differences between those. 

Rather than creating these objects from scratch, a more efficient approach is to clone an existing one and make the necessary modifications to the copy.


> [!success] 
> ## Solution: 

![[Prototype Interface.svg| center | 1100]]

``` run-csharp
public interface IDeepCopyable<T>
	where T : new()
{
	void CopyTo(T target);
	
	public T DeepCopy()
	{
		T t = new T();
		CopyTo(t);
		
		return t;
	}
}
```

``` run-csharp
public static class ExtensionMethods
{
	public static T DeepCopy<T>(this IDeepCopyable<T> item)
		where T : new()
	{
		return item.DeepCopy();
	}
	
	public static T DeepCopy<T>(this T person)
		where T : Person, new()
	{
		return ((IDeepCopyable<T>) person).DeepCopy();
	}
}
```

``` run-csharp
public class Address : IDeepCopyable<Address>
{
	public string StreetName;
	public int HouseNumber;
	
	public Address() {}
	
	public Address(string streetName, int houseNumber)
	{
		StreetName = streetName;
		HouseNumber = houseNumber;
	}
	
	public void CopyTo(Address target)
	{
		target.StreetName = StreetName;
		target.HouseNumber = HouseNumber;
	}
}
```

``` run-csharp
public class Person : IDeepCopyable<Person>
{
	public string[] Names;
	public Address Address;
	
	public Address() {};
	
	public Person(string[] names, Address address)
	{
		Names = names;
		Address = address;
	}
	
	public void CopyTo(Person Target)
	{
		target.Names = (string[]) Names.Clone();
		target.Address = Address.DeepCopy();
	}
}
```

``` run-csharp
public class Employee : Person, IDeepCopyable<Employee>
{
	public int Salary;
	
	public Employee() {}
	
	public Employee(string[] names, Address address, int salary)   
        : base(names, address)  
	{  
	  Salary = salary;  
	}
	
	public void CopyTo(Employee target)
	{
		base.CoptTo(target);
		target.Salary = Salary;
	} 
}
```

---

``` run-csharp
public void Main()  
{  
	Employee john = new Employee();  
	john.Names = new[] {"John", "Doe"};  
	john.Address = new Address  
	  {  
			HouseNumber = 123,  
			StreetName = "Little Rd"        };  
	john.Salary = 321000;  
	
	Employee copy = john.DeepCopy();  
	
	copy.Names[1] = "Smith";  
	copy.Address.HouseNumber++;  
	copy.Salary = 123000;  
	
	Employee e = john.DeepCopy<Employee>();  
	Person p = john.DeepCopy<Person>();  
	
	Console.WriteLine(john);  
	Console.WriteLine(copy);  
	Console.WriteLine(e);  
	Console.WriteLine(p);  
}
```

![[Pasted image 20240616132255.png | center]]

---
Reference: