Status: 
Tag:
Links: [[301.3 Builder Pattern]]

---
> [!note] 
>  # Faceted Builder

The Faceted Builder is a creational design pattern that combines the Builder Pattern with a fluent API to create a more expressive and readable way of constructing complex objects with multiple configuration objects.


The Faceted Builder is a creational design pattern that allows for a facade over the builder so that multiple builders can be used in an object's creation.

> [!warning] 
> ## Problem: 

Sometimes we may have a complex object, and the creational process requires more than one builder class.

- Introduce multiple builder classes in such a way that you can jump from one builder to another while creating the object.

> [!success] 
> ## Solution: 

![[Faceted Builder Pattern.svg| center]]

``` run-csharp
public class Person
{
	public string StreetAddress, Postcode, City;
	
	public string CompanyName, Position;
	public int AnnualIncome;
}
```

``` run-csharp
public class PersonBuilder
{
	protected Person person {get; set; }
	
	public PersonBuilderFacade()
	{
		 person = new Person();
	}
	
	public Person Build() => person;
	
	public PersonJobBuilder Work => new PersonJobBuilder(person);
	public PersonAddressBuilder Lives => new PersonAddressBuilder(person);
}
```

``` run-csharp
public class PersonJobBuilder : PersonBuilder
{
	public PersonJobBuilder(Person person)
	{
		this.person = person;
	}
	
	public PersonJobBuilder At(string companyName)
	{
		person.CompanyName = companyName;
		return this;
	}
	
	public PersonJobBuilder AsA(string position)
	{
		person.Position = position;
		return this;
	}
	
	public PersonJobBuilder Earning(int amount)
	{
		person.AnnualIncome = amount;
		return this;
	}
}
```

``` run-csharp
public class PersonAddressBuilder : PersonBuilder
{
	public PersonAddressBuilder(Person person)
	{
		this.person = person;
	}
	public PersonAddressBuilder At(string streetAddress)
	{
		person.StreetAddress = streetAddress;
		return this;
	}
	
	public PersonAddressBuilder In(string city)
	{
		person.City = city;
		return this;
	}
	public PersonAddressBuilder WithPostCode(string postcode)
	{
		person.Postcode = postcode;
		return this;
	}
}
```

``` run-csharp
public class Program
{
	PersonBuilder builder = new PersonBuilder();
	
	 Person person = builder
		.Lives.At("123 Strret")
			  .In("City")
			  .WithPostCode("1111")
		.Works.At("Fabriam")
			 .AsA("Engineer")
			 .Earning(123000)
		 .Build();
}
```

---
References: https://code-maze.com/faceted-builder/