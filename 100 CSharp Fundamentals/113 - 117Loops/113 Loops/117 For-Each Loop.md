Status: 
Tag: #ForEach #Loop
Links: [[113 Loops]]

---
> [!note] 
>  # For-Each Loop

The <font style="color:#b562f9">foreach</font> loop is specifically designed for <font style="color:#b562f9">iterating</font> over <font style="color:#b562f9">elements</font> in <font style="color:#81fd83">collections</font>, such as <font style="color:#81fd83">arrays</font>, <font style="color:#81fd83">lists</font>, or other <font style="color:#81fd83">enumerable objects</font>. It simplifies the process of iterating over each element without worrying about indices or bounds.

## For Each Declaration:

In each iteration, the item variable represents the current element from the collection, and the code block is executed.

``` run-csharp
foreach (var item in collection)
{
    // code to be executed
}

```

---
> [!example] 
>  ## Code Snippet

``` run-csharp
string[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

foreach (string i in cars) 
{
  Console.WriteLine(i);
}
```

---
References: