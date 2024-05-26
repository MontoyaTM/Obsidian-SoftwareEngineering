Status: 
Tag: #ExceptionHandling #Throw #TryCatch #Finally
Links: [[100 CSharp Fundamentals]]

---
> [!note] 
>  # Exception Handling

Exception handling in C# is a mechanism that allows developers to handle and manage <font style="color:#b562f9">runtime errors</font> or exceptional situations that may occur during the execution of a program. It provides a structured way to <font style="color:#b562f9">catch</font> and respond to these <font style="color:#b562f9">exceptions</font>, preventing the program from terminating abruptly and enabling graceful error recovery.

The process of handling exceptions involves two main components: <font style="color:#b562f9">throwing</font> exceptions and <font style="color:#b562f9">catching</font> exceptions.

## Throw Exceptions:

An exception can be raised manually by using the <font style="color:#b562f9">throw</font> keyword. Any type of exceptions which is derived from <font style="color:#81fd83">Exception</font> class can be raised using the throw keyword.

``` run-csharp
private static void PrintStudenName(Student std)
{
	if(std == null) 
	{
		throw new NullReferenceException("Student object is nulll");
	}
}
```

## Try-Catch Block

The <font style="color:#b562f9">try block</font> contains the code that may throw an exception, while the <font style="color:#b562f9">catch block</font> specifies the exception type to catch and the code to handle the exception. Multiple catch blocks can be used to handle different types of exceptions.

``` run-csharp
try
{
  int[] myNumbers = {1, 2, 3};
  Console.WriteLine(myNumbers[10]);
}
catch (Exception e)
{
  Console.WriteLine(e.Message);
}
```

## Finally Block:

The <font style="color:#b562f9">finally block</font> is <font style="color:#81fd83">optional</font> and can be added <font style="color:#b562f9">after</font> the <font style="color:#b562f9">catch block</font>. It contains code that executes regardless of whether an exception occurred or not. This block is commonly used for resource <font style="color:#81fd83">cleanup</font>, ensuring that resources like file handles or database connections are properly released, even if an exception is thrown.

``` run-csharp
try
{
    // Code that may throw an exception
}
catch (ExceptionType1 ex1)
{
    // Handle exception of type ExceptionType1
finally
{
    // Optional: Code that executes regardless of whether an exception occurred or not
}

```

---
References: