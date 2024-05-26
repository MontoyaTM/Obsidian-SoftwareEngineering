Status: 
Tag: #Inheritance
Links: [[118 Object Oriented Programming]]

---
> [!note] 
>  # Inheritance

Inheritance is a fundamental concept in object-oriented programming (OOP) that allows you to create new classes based on existing classes. In C#, <font style="color:#b562f9">inheritance</font> enables you to define a <font style="color:#b562f9">class</font> that <font style="color:#81fd83">inherits</font> the members (<font style="color:#81fd83">fields</font>, <font style="color:#81fd83">properties</font>, <font style="color:#81fd83">methods</font>) and <font style="color:#81fd83">behavior</font> of another class, called the <font style="color:#b562f9">base class</font> or <font style="color:#b562f9">parent class</font>.

## Inheritance Declaration 

To establish an <font style="color:#b562f9">inheritance</font> relationship between classes in C#, you use the colon <font style="color:#b562f9">:</font> symbol followed by the <font style="color:#b562f9">name</font> of the <font style="color:#b562f9">base class</font>. The <font style="color:#81fd83">derived class</font> then <font style="color:#81fd83">inherits</font> all the accessible members of the base class, which can be used as if they were defined within the derived class itself.

``` run-csharp
class Vehicle 
{ 
	public string Brand { get; set; } 
	public void StartEngine() 
	{ 
		Console.WriteLine("Engine started."); 
	} 
}

class Car : Vehicle
{
	public void Accelrate()
	{
		Console.WriteLine("Car is accelerating.");
	}
}

Car myCar = new Car();
myCar.Brand = "Toyota";
myCar.StartEngine();
myCar.Accelerate();

```

---
References: