Status: 
Tag: #Big-O #Notation
Links: [[200 Data Structures & Algorithms]]

---
> [!note] 
>  # Big-O Notation

<font style="color:#b562f9">Big-O notation</font> is a <font style="color:#81fd83">mathematical notation</font> used in computer science to describe the <font style="color:#81fd83">performance</font> characteristics of <font style="color:#b562f9">algorithms</font>. It provides a way to analyze and compare the efficiency of algorithms in terms of how their execution <font style="color:#81fd83">time</font> or <font style="color:#81fd83">space</font> requirements grow with respect to the input size.

![[Pasted image 20230607210015.png]]


> [!important] 
> # Rule Book 

#### Rule 1: Worst Case

#### Rule 2: Remove Constants

#### Rule 3: Different Terms for Inputs

#### Rule 4: Drop Non Dominates

---

> [!important] 
> ## Stopwatch 


The <font style="color:#b562f9">Stopwatch</font> class in C# is a utility class provided by the .NET Framework that allows you to measure <font style="color:#81fd83">elapsed time</font> with high precision. It provides a convenient way to perform timing operations, such as benchmarking code or measuring the execution time of specific parts of a program.

- To use the <font style="color:#b562f9">Stopwatch</font> class, you need to include the <font style="color:#b562f9">System.Diagnostics</font> namespace in your code.

``` run-csharp
using System.Diagnostics;

Stopwatch stopwatch = new Stopwatch();
stopwatch.Start();
stopwatch.Stop();

TimeSpan elapsedTime = stopwatch.Elapsed;

Console.WriteLine("Elapsed Time: " + elapsedTime);
Console.WriteLine("Elapsed Time (in milliseconds): " + elapsedTime.TotalMilliseconds);
```


---
References: [Road Map](https://www.codingninjas.com/codestudio/library/complete-data-structures-and-algorithms-roadmap-for-placements)