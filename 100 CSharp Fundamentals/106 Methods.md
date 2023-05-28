Status: 
Tag: #Method 
Links: [[102.4 Class]]

---
> [!note] 
>  # Method

Methods are generally the <font style="color:#b562f9">block of codes</font> or statements in a program that gives the user the ability to <font style="color:#81fd83">reuse</font> the same code which ultimately saves the excessive use of memory, acts as a <font style="color:#81fd83">time saver</font> and more importantly, it provides a better <font style="color:#81fd83">readability</font> of code.

# Method Declaration:

Method declaration means the way to construct method including its naming.

```
<Access_Modifier> <return_type> <method_name>(param_list)
```

![[Pasted image 20230509222925.png]]

---
> [!example] 
>  ## Code Snippet

``` run-csharp
static void MyMethod() 
{
  Console.WriteLine("I just got executed!");
}

static void Main(string[] args)
{
  MyMethod();
}
```

---
References: