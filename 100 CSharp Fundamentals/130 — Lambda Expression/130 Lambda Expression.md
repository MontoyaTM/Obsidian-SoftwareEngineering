Status: 
Tag: #LambdaExpression
Links: [[102.6 Delegate]]

---
> [!note] 
>  # Lamba Expression

<font style="color:#b562f9">Lambda expressions </font>in C# are a concise way to define <font style="color:#b562f9">anonymous</font> functions. They provide a shorthand syntax for creating delegates or implementing functional interfaces with a single method (such as <font style="color:#81fd83">Func⋖⋗</font> and <font style="color:#81fd83">Action⋖⋗</font> delegates).

> [!important] 
> Lambda expression is a shorter way of representing anonymous methods. 

## Lambda Declaration

A <font style="color:#b562f9">lambda</font> expression uses <font style="color:#b562f9">=></font>, the lambda declaration <font style="color:#b562f9">operator</font>, to separate the lambda's parameter list from its executable code. To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator, and you put the expression or statement block on the other side.

``` run-csharp
namespace LambdaExpressions
{
    delegate void ArithmeticOperation(double operand1, double operand2);

    class Program
    {
        static void Main(string[] args)
        {
            ArithmeticOperation sum = (double number1, double number2) =>
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