Status: 
Tag: #Parse #ParseDeclaration #TryParse #ParseSyntax
Links: [[102.2 String]]

---
> [!note] 
>  # Parse()

<font style="color:#b562f9">Parse() </font>converts the <font style="color:#b562f9">string</font> data type to another data type. Before using Parse(), we have to make sure the conversion will take place successfully. Otherwise, the program will crash.


# Parse Declaration:

To convert <font style="color:#81fd83">string</font> into any data type, we use the following syntax: 

``` run-csharp
data_type.Parse(string);
```

Parse() receives one string parameter to be converted to the desired data type.

``` run-csharp
string var_string = "4.5"; 

Console.WriteLine(int.Parse("4") + 3); 
Console.WriteLine(float.Parse(var_string) + 4.4f);
```

Consider the following example where conversion fails:

``` run-csharp
Console.WriteLine(int.Parse("Seven") + 1);
```

> [!error] 
>  The string `"Seven"` cannot be converted into an `int` value. Therefore, the method call of `int.Parse()` above produces an exception of the incorrect format.


# TryParse() 

<font style="color:#b562f9">TryParse()</font> converts the string data type into another data type. It <font style="color:#b562f9">returns 0</font> if the conversion <font style="color:#b562f9">fails</font>. TryParse() is a safer approach because it does <font style="color:#b562f9">not terminate</font> the execution of the <font style="color:#b562f9">program</font>.

# TryParse Declaration:

Use the following syntax to convert <font style="color:#b562f9">string</font> into any variable.

``` run-csharp
data_type.TryParse(string, out output_variable);
```

The TryParse() method receives <font style="color:#b562f9">two parameters</font>. The first parameter is the <font style="color:#b562f9">string</font> to be converted. The second parameter is the variable to store the <font style="color:#b562f9">converted value</font>. The <font style="color:#b562f9">out</font> keyword is used before the second parameter.

The TryParse() method <font style="color:#b562f9">returns</font> <font style="color:#81fd83">True</font> or <font style="color:#81fd83">False</font> value based on successful or unsuccessful conversion.

---
> [!example] 
>  ## Code Snippet

``` run-csharp
string textExample = "Seven"; 
Console.WriteLine(textExample); 

int textExampleInt; 
int.TryParse(textExample, out textExampleInt); 
// "Seven" cannot be converted to int, hence textExampleInt store 0 value. 
Console.WriteLine(textExampleInt); 

string textExample2 = "5.5"; 
Console.WriteLine(textExample2); 

float textExampleFloat; 
float.TryParse(textExample2, out textExampleFloat); 
// "5.5" will be converted to float value 5.5 and stored in textExampleFloat 
Console.WriteLine(textExampleFloat);
```

---
References: