Status: 
Tag: #DoWhile #Loop
Links: [[113 Loops]]

---
> [!note] 
>  # Do-While Loop

Similar to the while loop, the <font style="color:#b562f9">do-while</font> loop executes a block of code repeatedly as long as the given condition remains <font style="color:#b562f9">true</font>. However, the <font style="color:#b562f9">condition</font> is checked at the <font style="color:#b562f9">end</font> of each <font style="color:#b562f9">iteration</font>, which means the code block is <font style="color:#b562f9">guaranteed</font> to <font style="color:#b562f9">execute</font> at least <font style="color:#b562f9">once</font>.

## Do-While Declaration:

The code block is executed first, and then the <font style="color:#b562f9">condition</font> is evaluated. If it's <font style="color:#b562f9">true</font>, the loop continues; otherwise, it terminates.

``` run-csharp
do
{
    // code to be executed
} while (condition);

```

---
> [!example] 
>  ## Code Snippet

``` run-csharp
int x = 21;
do
{
	// The line will be printed even
	// if the condition is false
	Console.WriteLine("GeeksforGeeks");
	x++;
}
while (x < 20);

```

---
References: