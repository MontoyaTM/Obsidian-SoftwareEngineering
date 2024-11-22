
Status: 
Tag:
Links: [[301.2 Abstract Factory]]

---
> [!note] 
>  # Abstract Factory

<span style="color:#81fd83">Abstract Factory</span> is a creational design pattern, which solves the problem of creating entire product families without specifying their concrete classes.

- Defines an interface for creating all distinct products but leaves the actual product creation to concrete factory classes.

> [!warning] 
> ## Problem: 

Imagine a machine that creates hot beverages; tea, coffee. However, you want allow a user to consume the beverage without the user holding onto the object type.


> [!success] 
> ## Solution: 

![[Abstract Factory.svg| center | 800]]

``` run-csharp
public interface IHotDrink
{
	void Consume();
}

internal class Tea : IHotDrink
{
	public void Consume()
	{
		Console.WriteLine("This tea is nice but I'd prefer it with milk.")
	}
}

internal class Coffee : IHotDrink
{
	public void Consume()
	{
		Console.WriteLine("This coffee is sensational.")
	}
}

public interface IHotDrinkFactory
{
	IHotDrink Prepare(int amount);
}

internal class TeaFactory : IHotDrinkFactory
{
	public IHotDrink Prepare(int amount)
	{
		// Customizing tea...
		return new Tea();
	}
}

internal class CoffeeFactory : IHotDrinkFactory
{
	public IHotDrink Prepare(int amount)
	{
		// Customizing coffee...
		return new Coffee();
	}
}

public class HotDrinkMachine
{
	public enum AvailableDrink
	{
		Coffee, 
		Tea
	}
	
	private Dictionary<AvailableDrink, IHotDrinkFactory> factories =
		new Dictionary<AvailableDrink, IHotDrinkFactory>();
	
	public HotDrinkMachine()
	{
		var factory = (IHotDrinkFactory)Activator.CreateInstance(
			Type.GetType("DesignPatterns." + Enum.GetName(typeof(AvailableDrink), drink))
			);
		
		factories.Add(drink, factory);
	}
	
	public IHotDrink MakeDrink(AvailableDrink drink, int amount)
	{
		return factories[drink].Prepare(amount);
	}
}


public class Program
{
	public static void Main(string[] args)
	{
		var machine = new HotDrinkMachine();
		var drink = machine.MakeDrink(HotDrinkMachine.AvailableDrink.Tea, 100);
		drink.Consume();
	}
}
```

---
References: