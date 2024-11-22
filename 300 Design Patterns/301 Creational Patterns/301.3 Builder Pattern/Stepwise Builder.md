Status: 
Tag:
Links: [[301.3 Builder Pattern]]

---
> [!note] 
>  # Stepwise Builder

The Stepwise Builder is a creational design pattern 


that simplifies the creation of complex objects. It allows for cleaner and more expressive code when creating object by encapsulating all of the complexity inside of the builder implementation.


> [!warning] 
> ## Problem: 

- How do you get the builder to perform a set of steps one after another in a specific order?

> [!success] 
> ## Solution: 

To perform a set of steps in a specific order, you can use several interfaces that follow one another.

![[Stepwise Builder Pattern.svg | center]]

``` run-csharp 
public enum CarType
{
	Sedan, 
	Crossover
}
```

``` run-csharp 
public class Car
{
	public CarType Type;
	public int WheelSize;
}
```

``` run-csharp
public interface ISpecifyCarType
{
	ISpecifyWheelSize OfType(CarType type);
}
```

``` run-csharp
public interface ISpecifyWheelType
{
	IBuildCar WithWheels(int size);
}
```

``` run-csharp
public interface IBuildCar
{
	public Car Build();
}
```

``` run-csharp
public class CarBuilder
{
	private class Implementation : ISpecifyCarType, ISpecifyWheelSize, IBuildCar
	{
		private Car car = new Car();
	
		public ISpecifyWheelSize OfType(CarType type)
		{
			car.Type = type;
			return this;
		}
	
		public IBuildCar WithWheel(int size)
		{
			switch(car.Type)
			{
				case CarType.Crossover when size < 17 || size > 20:
				case CarType.Sedan when size < 15 || size > 17:
					throw new ArgumentException($"Wrong size of wheel for {car.Type}.");
			}
	
			car.WheelSize = size;
			return this;
		}
	
		public Car Build()
		{
			return car;
		}
	}
	
	public static ISpecifyCarType Create()
	{
		return new Implementation();
	}
}
```

``` run-csharp
public class Program
{
	static void Main(string[] args)
	{
		var car = CarBuilder.Create()	// ISpecifyCarType
			.OfType(CarType.Sedan)		// ISpecifyWheelSize
			.WithWheel(18)				   // IBuildCar
			.Build();
		}
}
```

---
References: