Status: 
Tag: #IfElse #TernaryOperator
Links: [[109 Conditional Statements]]

---
> [!note] 
>  # If-Else Statement

The “<font style="color:#b562f9">if</font>… else if…” statement has an “<font style="color:#b562f9">else if</font>” positioned after the “if” statement. This condition is very useful for handling various conditions by using a single if followed by multiple “else if” each of which represents a separate condition.

## If-Else Statement Declaration:

``` run-csharp
if(condition1)
{
    // code block to be executed when if condition1 evaluates to true
}
else if(condition2)
{
    // code block to be executed when 
    //      condition1 evaluates to flase
    //      condition2 evaluates to true
}
else if(condition3)
{
    // code block to be executed when 
    //      condition1 evaluates to flase
    //      condition2 evaluates to false
    //      condition3 evaluates to true
}
```

---
> [!example] 
>  ## Code Snippet

``` run-csharp
int i = 10, j = 20;

if (i == j)
{
    Console.WriteLine("i is equal to j");
}
else if (i > j)
{
    Console.WriteLine("i is greater than j");
}
else if (i < j)
{
    Console.WriteLine("i is less than j");
}
```

## Tenary Operator

C# includes a decision-making operator <font style="color:#b562f9">?:</font> which is called the conditional operator or <font style="color:#b562f9">ternary operator</font>. It is the <font style="color:#81fd83">short form</font> of the <font style="color:#81fd83">if else</font> conditions.

> [!hint] 
>  condition ? statement 1 : statement 2 

The ternary operator starts with a boolean condition. If this condition evaluates to true then it will execute the first statement after <font style="color:#b562f9">?</font>, otherwise the second statement after <font style="color:#b562f9">:</font> will be executed.

> [!example] 
> ## Code Snippet 

``` run-csharp
int x = 10, y = 100;

if (x > y)
    Console.WriteLine("x is greater than y");
else
    Console.WriteLine("x is less than y");
```

``` run-csharp
int x = 10, y = 100;

var result = x > y ? "x is greater than y" : "x is less than y";

Console.WriteLine(result);
```

---
References: