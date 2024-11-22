
Status: 
Tag:
Links: [[301.1 Factory Method]]

---
> [!note] 
>  # Inner Factory


> [!warning] 
> ## Problem: 

Recalling the solution in the Factory Pattern. To comply with the Separation of Concerns and Single Responsibility principle, the Point Class constructor was made to be public so that the PointFactory Class had access to it.

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
		this.x = x; 
		this.y = y; 
	}
}
```


> [!success] 
> ## Solution: 

The solution to this problem is to place the PointFactory Class within the existing class so that the constructor for the Point Class can remain private.

![[Inner Factory.svg| center | 600]]

``` run-csharp
public class Point
{
	private double x, y;
	
	private Point(double x, double y)
	{
		this.x = x;
		this.y = y;
	}
	
	public static class Factory
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
}
```

``` run-csharp
public class Program
{
	public static void Main(string[] args)
	{
		var Point = Point.Factory.NewPolarPoint(1.0, Math.PI / 2);
	}
}
```

---
Reference: