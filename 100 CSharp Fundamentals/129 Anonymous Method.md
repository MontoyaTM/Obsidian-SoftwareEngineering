Status: 
Tag: #AnonymousMethod
Links: [[102.6 Delegate]]

---
> [!note] 
>  # Anonymous Method

In C#, <font style="color:#b562f9">anonymous methods</font> were the <font style="color:#81fd83">predecessor</font> to <font style="color:#81fd83">lambda expressions</font> and provided a similar capability for defining inline methods without explicitly declaring a separate named method.

An anonymous method is a method without a name. Anonymous methods in C# can be defined using the <font style="color:#b562f9">delegate</font> keyword and can be assigned to a variable of delegate type.

``` run-csharp
namespace AnonymousMethod
{
    delegate void ArithmeticOperation(double operand1, double operand2);

    class Program
    {
        static void Main(string[] args)
        {
            ArithmeticOperation sum = delegate (double number1, double number2)
            {
                Console.WriteLine($"{number1} + {number2} = {number1 + number2}");
            };
            sum(10, 5);
            Console.WriteLine();
        }
    }
}
```

---
References: