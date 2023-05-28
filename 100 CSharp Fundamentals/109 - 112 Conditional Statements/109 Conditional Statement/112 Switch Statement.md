Status: 
Tag: #Switch #SwitchSyntax
Links:  [[109 Conditional Statements]]

---
> [!note] 
>  # Switch Statement

In C#, Switch statement is a <font style="color:#b562f9">multiway</font> branch statement. It provides an efficient way to transfer the execution to different parts of a code based on the value of the <font style="color:#b562f9">expression</font>. The switch expression is of integer type such as int, char, byte, or short, or of an enumeration type, or of string type. The expression is checked for different cases and the one match is executed.

![[Switch Statement.svg]]
## Escape Switch Statement:

The <font style="color:#b562f9">switch</font> statement can also contain an optional default label. The default label will be executed if no cases executed. The <font style="color:#b562f9">break</font>, <font style="color:#b562f9">return</font>, or <font style="color:#b562f9">goto</font> keyword is used to exit the program control from a switch case.

> [!example] 
>  ## Break

``` run-csharp
int x = 125;

switch (x % 2)
{ 
    case 0:
        Console.WriteLine($"{x} is an even value");
        break;
    case 1:
        Console.WriteLine($"{x} is an odd Value");
        break;
}
```


> [!example] 
>  ## Return

``` run-csharp
static bool isOdd(int i, int j)
{
    switch (x % 2)
    { 
        case 0:
            return true;
        case 1:
            return false;
        default:
            return false;
    }
    
    return false;
}
```


> [!example] 
>  ## Goto

``` run-csharp 
int greeting = 2;
  
        switch (greeting) {
        case 1:
            Console.WriteLine("Hello");
            goto default;
        case 2:
            Console.WriteLine("Bonjour");
            goto case 3;
        case 3:
            Console.WriteLine("Namaste");
            goto default;
        default:
            Console.WriteLine("Entered value is: " + greeting);
            break;
```

---
References: