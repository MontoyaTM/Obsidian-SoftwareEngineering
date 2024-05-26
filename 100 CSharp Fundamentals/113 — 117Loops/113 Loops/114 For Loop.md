Status: 
Tag:  #For #Loop 
Links: [[113 Loops]]

---
> [!note] 
>  # For Loop

<font style="color:#b562f9">For</font> loops are preferred when the <font style="color:#b562f9">number of times</font> loop statements are to be executed is <font style="color:#b562f9">known</font> beforehand. 

## For Loop Declaration:

The <font style="color:#b562f9">initialization</font> part is executed once at the beginning. The <font style="color:#b562f9">condition</font> is checked before each iteration, and if it evaluates to <font style="color:#b562f9">true</font>, the code block is <font style="color:#b562f9">executed</font>. After each iteration, the <font style="color:#b562f9">iteration</font> expression is executed.

``` run-csharp
for (loop variable initialization ; testing condition; iteration)
{    
    // statements to be executed
}
```

---
> [!example] 
>  ## Code Snippet

``` run-csharp
for (int x = 1; x <= 4; x++)
{
    Console.WriteLine("GeeksforGeeks");
}
```

---
References: