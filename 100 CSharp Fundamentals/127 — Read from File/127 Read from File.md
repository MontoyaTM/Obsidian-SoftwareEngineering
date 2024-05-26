Status: 
Tag: #ReadFromFile
Links: [[100 CSharp Fundamentals]]

---
> [!note] 
>  # Read from File

To read from a file in C# (assuming a text file), you can use the <font style="color:#b562f9">StreamReader</font> class from the <font style="color:#81fd83">System.IO</font> namespace. The <font style="color:#b562f9">StreamReader</font> class provides methods to read characters or lines from a file.

``` run-csharp
using System;
using System.IO;

string filePath = "path_to_your_file.txt";

// Check if the file exists
if (File.Exists(filePath))
{
    // Open the file for reading
    using (StreamReader reader = new StreamReader(filePath))
    {
        // Read the file line by line
        string line;
        while ((line = reader.ReadLine()) != null)
        {
            // Process each line
            Console.WriteLine(line);
        }
    }
}
else
{
    Console.WriteLine("File does not exist.");
}
```

---
References: