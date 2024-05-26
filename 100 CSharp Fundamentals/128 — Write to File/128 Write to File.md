Status: 
Tag: #WriteToFile
Links: [[100 CSharp Fundamentals]]

---
> [!note] 
>  # Write to File

To write to a file in C# (assuming a text file), you can use the <font style="color:#b562f9">StreamWriter</font> class from the <font style="color:#81fd83">System.IO</font> namespace. The <font style="color:#b562f9">StreamWriter</font> class provides methods for writing characters or strings to a file.

``` run-csharp
using System;
using System.IO;

string filePath = "path_to_your_file.txt";

// Open the file for writing
using (StreamWriter writer = new StreamWriter(filePath))
{
    // Write lines of text to the file
    writer.WriteLine("Hello, World!");
    writer.WriteLine("This is a sample line.");
}

Console.WriteLine("Write operation completed.");
```

---
References: