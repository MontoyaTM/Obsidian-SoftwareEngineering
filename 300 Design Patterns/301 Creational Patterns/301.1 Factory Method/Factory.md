Status: 
Tag:
Links: [[301.1 Factory Method]]

---
> [!note] 
>  # Factory


> [!warning] 
> ## Problem: 

The Separation of Concerns and Single Responsibility principle can argue that the construction of an object is a separate responsibility from what the object actually does.

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


> [!success] 
> ## Solution: 

The solution would be to create a separate class to handle object creation. However, the Point Class's constructor would have to change from private to public to allow object creation. This will allow other classes to create a Point object so keep that in mind.

![[Factory Solution.svg| center | 600]]

``` run-csharp
public static class PointFactory
{
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

``` run-csharp
public class Point
{
	private double x, y; 
	
	public Point(double x, double y) 
	{ 
		this.x = x; this.y = y; 
	}
}
```

``` run-csharp
public class Program
{
	public static void Main(string[] args)
	{
		var p = new Point();
		var point = PointFactory.NewPolarPoint(1.0, Math.PI / 2);
	}
}
```

---
Reference: