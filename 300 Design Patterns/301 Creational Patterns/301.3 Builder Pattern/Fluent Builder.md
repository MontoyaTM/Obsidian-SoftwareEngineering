Status: 
Tag:
Links: [[301.3 Builder Pattern]]

---
> [!note] 
>  # Fluent Builder

The Fluent Builder is a creational design pattern that simplifies the creation of complex objects. It allows for cleaner and more expressive code when creating object by encapsulating all of the complexity inside of the builder implementation.


> [!warning] 
> ## Problem: 

In the classic representation of the Builder Pattern, the pattern consists of a specific Builder Class and may contain Director Class. In these specific classes it is common to hard code the values being used to create the objects.

- Why should I need to create a new Builder Class for every minor variation of the object that I want to create?
- Why should I even use the Director Class?
- Why can't the logic be encapsulated inside the builder itself?


> [!success] 
> ## Solution: 
  
![[Fluent Builder Pattern.svg| center]]


``` run-csharp
public class Order
{
	public int Number { set; get; }
	public DatTime CreatedOn { set; get; }
	public Address ShippingAddress {set; get;}
}
```

``` run-csharp
public class OrderBuilder
{
	private int _number;
	private DatTime _createdOn;
	private readonly AddressBuilder _addressBuilder = AddressBuilder.Empty();
	
	private OrderBuilder()
	{
	
	}
	
	public static OrderBuilder Empty() => new();
	
	public OrderBuilder WithNumber(int number)
	{
		_number = number;
		return this;
	}
	
	public OrderBuilder WithCreatedOn(Datetime createdOn)
	{
		_createdOn = createdOn;
		return this;
	}
	
	public OrderBuilder WithShippingAddress(Action<AddressBuilder> action)
	{
		action(_addressBuilder);
		returnt this;
	}
	
	public Order Build()
	{
		return new Order
		{
			Number = _number;
			CreatedOn = _createdOn;
		}
	}
}
```

``` run-csharp
public class Address
{
	public string Street { set; get; }
	public string City { set; get; }
	public string Zip { set; get; }
	public string State { set; get; }
	public string Country { set; get; }
}
```

``` run-csharp
public class AddressBuilder
{
	private string _street;
	private string _city;
	private string _zip;
	private string _state;
	private string _country;
	
	private AddressBuilder()
	{
	}
	
	public static AddressBuilder Empty() => new();
	
	public AddressBuilder Street(string street)
	{
		_street = street;
		return this;
	}
	
	public AddressBuilder City(string city)
	{
		_city = city;
		return this;
	}
	
	public AddressBuilder Zip(string zip)
	{
		_zip = zip;
		return this;
	}
	
	public AddressBuilder State(string state)
	{
		_state = state;
		return this;
	}
	
	public AddressBuilder Country(string country)
	{
		_country = country;
		return this;
	}
	
	public Address Build()
	{
		return new Address
		{
			Street = _street;
			City = _city;
			Zip = _zip;
			State = _state;
			Country = _country;
		}
	}
}
```

``` run-csharp
public static void Main(string[] ags)
{
	var order = OrderBuilder.Empty()
		.WithNumber(10)
		.WithCreatedOn(DateTime.UtcNow)
		.WithShippingAddress(x => x
			.Street("street")
			.City("city")
			.Zip("zip")
			.State("state")
			.Country("country"))
		.Build();
}
```

---
References: https://www.youtube.com/watch?v=qCIr30WxJQw