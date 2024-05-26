Status: 
Tag: #GenericCollections
Links: [[124 Collections]]

---
> [!note] 
>  # Generic Collections

<font style="color:#b562f9">Generic Collections</font>, introduced in C# 2.0, are <font style="color:#b562f9">strongly typed</font> collections that allow you to specify the type of elements they can contain at <font style="color:#81fd83">compile time</font>. They provide type safety and eliminate the need for explicit type casting when retrieving elements from the collection.

Generic Collections are designed to work with <font style="color:#b562f9">specific</font> types of <font style="color:#b562f9">objects</font>. These collections specify the type of object that will be stored in the collection, making them "<font style="color:#81fd83">generic</font>".


Generic collections are part of the <font style="color:#81fd83">System.Collections.Generic</font> namespace. Examples of generic collections include:


> [!example] 
> #### Lists 

Lists, represented by the <font style="color:#b562f9">List⋖T></font> class, are dynamic arrays that can grow or shrink in size. They provide indexed access to elements and support operations like adding, removing, sorting, and searching.

> [!example] 
> #### Dictionaries 

<font style="color:#b562f9">Dictionaries</font>, represented by the <font style="color:#b562f9">Dictionary⋖TKey, TValue⋗</font> class, store <font style="color:#81fd83">key-value pairs</font>. They provide <font style="color:#81fd83">fast retrieval of values</font> based on a <font style="color:#81fd83">unique key</font>. Keys must be unique within the dictionary, and they are used to access corresponding values efficiently.

> [!example] 
> #### HashSets 

<font style="color:#b562f9">HashSets</font>, represented by the <font style="color:#b562f9">HashSet⋖T⋗ </font>class, <font style="color:#b562f9">store unique elements</font> in <font style="color:#81fd83">no</font> particular <font style="color:#81fd83">order</font>. They provide fast lookup, insertion, and removal of elements. Sets are <font style="color:#81fd83">useful</font> when you need to check for the presence of an <font style="color:#81fd83">element</font> or perform operations like <font style="color:#81fd83">union</font>, <font style="color:#81fd83">intersection</font>, and <font style="color:#81fd83">difference</font> between sets.

> [!example] 
> #### Queues 

Queues, represented by the <font style="color:#b562f9">Queue⋖T⋗</font> class, follow a <font style="color:#b562f9">first-in</font>, <font style="color:#b562f9">first-out (FIFO) </font>order. Elements are added to the end of the queue and removed from the front. Queues are suitable for scenarios where you need to process items in the <font style="color:#81fd83">order</font> they were added.


> [!example] 
> #### Stacks 

<font style="color:#b562f9">Stacks</font>, represented by the <font style="color:#b562f9">Stack⋖T⋗</font> class, follow a <font style="color:#b562f9">last-in</font>, <font style="color:#b562f9">first-out (LIFO)</font> order. Elements are added and removed from the top of the stack. Stacks are useful when you need to keep <font style="color:#81fd83">track</font> of <font style="color:#81fd83">nested operations</font> or implement <font style="color:#81fd83">algorithms</font> like <font style="color:#81fd83">depth-first search.
</font>

---
References: