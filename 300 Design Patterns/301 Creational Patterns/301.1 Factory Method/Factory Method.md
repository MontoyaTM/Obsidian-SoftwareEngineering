Status: 
Tag:
Links: [[301.1 Factory Method]]

---
> [!note] 
>  # Factory Method

The Factory Method defines a method, which should be used for creating objects instead of using a direct constructor call (`new` operator). Subclasses can override this method to change the class of objects that will be created.

> [!warning] 
> ## Problem: 

Imagine trying to create a Point Class that can either be a cartesian or a polar coordinate. The constructor has too much going on each time it is being invoked. The constructor parameters are not descriptive enough to differentiate between either coordinate system. Inheritance is a good solution but can be excessive for this simple problem.

``` run-csharp
public enum CoordinateSystem
{
	Cartesian,
	Polar
}

public class Point
{
	public Point(double a, double b, CoordinateSystem system = CoordincateSystem.Cartesian)
	{
		switch(system):
		{
			case CoordinateSystem.Cartesian:
				x = a;
				y = b;
				break;
				
			case CoordinateSystem.Polar:
				x = a * Math.Cos(b);
				y = a * Math.Sin(b);
				
			default:
				throw new ArguementOutOfRangeException(nameof(system), system, null);
		}
	}
}
```


> [!success] 
> ## Solution: 

Explicit naming for parameters while initializing the correct coordinate system.

![[Factory Method.svg| center | 700]]

``` run-csharp
public class Point
{
	private double x, y;
	
	private Point(double  x, double y)
	{
		this.x = x;
		this.y = y;
	}
	
	
	public static Point NewCartesianPoint(double x, double y)
	{
		return new Point(x, y);
	}
	
	public static Point NewPolarPoint(double rho, double theta)
	{
		return new Point(rho * Math.Cos(theta), rho * Math.Sin(theta));
	}
}

```

---
References: