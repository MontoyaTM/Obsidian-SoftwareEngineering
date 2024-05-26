Status: 
Tag: #If
Links: [[109 Conditional Statements]]

---
> [!note] 
>  # If Statement

The If Statement is made up of a boolean expression followed by a statement. The statement inside the “if” condition is executed only if the boolean expression returns “true”. If it returns false then the program will simply ignore the statement.

## If Statement Declaration:

``` run-csharp
if(condition)
{
    // code block to be executed when if condition evaluates to true
}
```

---
> [!example] 
>  ## Code Snippet

``` run-csharp
int a = 11;
int b = 10;

/* if the boolean condition returns true execute following statement*/
if (a == b) {
	Console.WriteLine("Both a and b are equal");
} else{
    /* if the boolean condition returns true execute following statement*/
	Console.WriteLine("Both a and b are not equal");
}

Console.ReadLine();
```

---
References: