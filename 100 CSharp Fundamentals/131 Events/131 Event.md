Status: 
Tag: #Event
Links: [[100 CSharp Fundamentals]]

---
> [!note] 
>  # Event

In C#, an <font style="color:#b562f9">event</font> is a language construct that enables the implementation of the <font style="color:#81fd83">observer design pattern</font>. It allows <font style="color:#fd9bd4">objects</font> to <font style="color:#fd9bd4">notify</font> other <font style="color:#fd9bd4">objects</font> when a particular action or state change occurs.

In C#, an event is an <font style="color:#b562f9">encapsulated delegate</font>. It is dependent on the delegate. The delegate defines the signature for the event handler method of the subscriber class.

![[Pasted image 20230518111550.png]]

## Event Declaration

Events provide a way for <font style="color:#b562f9">objects</font> (called <font style="color:#fd9bd4">publishers</font> or <font style="color:#fd9bd4">event sources</font>) to publish notifications to <font style="color:#b562f9">other objects</font> (called <font style="color:#fd9bd4">subscribers</font> or <font style="color:#fd9bd4">event handlers</font>) that are interested in receiving and responding to those notifications.

The publisher defines an event, and subscribers can subscribe to or unsubscribe from the event to receive or stop receiving notifications, respectively.

> [!hint] 
> An event can be declared in two steps:
> - Declare a <font style="color:#b562f9">delegate</font>
> - Declare a variable of the delegate with the <font style="color:#b562f9">event</font> keyword 

``` run-csharp
public delegate void Notify();

public class ProcessBusinessLogic
{
	public event Notify ProcessCompleted;

	public void Notification()
	{
		Console.WriteLine("Notifying...")
	}
}
```


## Raising an Event

Raising an event is the same as<font style="color:#b562f9"> invoking a method</font>. An event that doesn’t have any event handlers is null. Therefore, before raising an event, you need to compare it to <font style="color:#b562f9">null</font>.

``` run-csharp
delegate void OrderEventHandler();

class Order
{
    public event OrderEventHandler OnCreated;

    public void Create()
    {
        Console.WriteLine("Order created");
        
        if(OnCreated != null)
        {
            OnCreated();
        }
    }
}
```

> [!tip] 
> ## Shortcut Method 

``` run-csharp
if(OnCreated != null)
{
	OnCreated();
}
```

``` run-csharp
OnCreated?.Invoke(this,EventArgs.Empty);
```

## Subscribing to Event

Subscribing to an event means adding event handlers to an event. The event handlers must have the same return type and signature as the event’s delegate.

To add an event handler to an event, you use the <font style="color:#b562f9">+=</font> operator. The <font style="color:#b562f9">event handler</font> can be an instance <font style="color:#81fd83">method</font>, a <font style="color:#81fd83">static method</font>, an <font style="color:#81fd83">anonymous method</font>, or a<font style="color:#81fd83"> lambda expression</font>.

``` run-csharp
class Program
{
    static void Main(string[] args)
    {
        var order = new Order();

        order.OnCreated += Email.Send;
        order.OnCreated += SMS.Send;

        order.Create();
    }
}
```

> [!example] 
> ## Code Snippit 

``` run-csharp
delegate void OrderEventHandler();

class Order
{
    public event OrderEventHandler OnCreated;

    public void Create()
    {
        Console.WriteLine("Order created");
        
        if(OnCreated != null)
        {
            OnCreated();
        }
    }
}


class Email 
{
    public static void Send()
    {
        Console.WriteLine($"Send an email");
    }
}

class SMS
{
    public static void Send()
    {
        Console.WriteLine($"Send an SMS");
    }
}

class Program
{
    static void Main(string[] args)
    {
        var order = new Order();

        order.OnCreated += Email.Send;
        order.OnCreated += SMS.Send;

        order.Create();
    }
}
```

---
References: [Events](https://www.csharptutorial.net/csharp-tutorial/csharp-events/)